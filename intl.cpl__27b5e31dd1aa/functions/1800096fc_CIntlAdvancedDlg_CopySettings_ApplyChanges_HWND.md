# CIntlAdvancedDlg::_CopySettings_ApplyChanges(HWND__ *)

- ea: `0x1800096fc`
- end: `0x180009867`
- name: `?_CopySettings_ApplyChanges@CIntlAdvancedDlg@@AEAAXPEAUHWND__@@@Z`
- size: `363`
- prototype: `void(CIntlAdvancedDlg *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009870`

## callees

- `0x1800096fc`
- `0x18000a6e4`
- `0x180025eb8`
- `0x180025f40`
- `0x18002a150`
- `0x18002b010`

## import_xrefs

- `ntdll!WinSqmAddToStream` at `0x18000980a`
- `ntdll!WinSqmAddToStream` at `0x18000980a`
- `USER32!SetCursor` at `0x180009748`
- `USER32!SetCursor` at `0x180009813`
- `USER32!SetCursor` at `0x180009748`
- `USER32!SetCursor` at `0x180009813`
- `USER32!LoadCursorW` at `0x18000973f`
- `USER32!LoadCursorW` at `0x18000973f`

## pseudocode

```c
void __fastcall CIntlAdvancedDlg::_CopySettings_ApplyChanges(CIntlAdvancedDlg *this, HWND a2)
{
  _DWORD *v2; // rbx
  HCURSOR CursorW; // rax
  HCURSOR v6; // rbp
  __int64 v7; // rcx
  __int64 v8; // r8
  int v9; // eax
  bool v10; // zf
  int v11; // [rsp+30h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+38h] [rbp-30h] BYREF

  v2 = (_DWORD *)((char *)this + 8);
  if ( *(_QWORD *)((char *)this + 4) )
  {
    v11 = 0;
    CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
    v6 = SetCursor(CursorW);
    (*(void (__fastcall **)(_QWORD, HWND, _QWORD, _QWORD, int *))(**((_QWORD **)this + 3) + 72LL))(
      *((_QWORD *)this + 3),
      a2,
      (unsigned int)*v2,
      *((unsigned int *)this + 1),
      &v11);
    if ( *v2 && (Microsoft_Windows_International_RegionalOptionsControlPanelEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(v7, &RLOUI_ETW_EVENT_COPY_SETTINGS_SYS, v8, 1u, &v12);
    if ( *((_DWORD *)this + 1) && (Microsoft_Windows_International_RegionalOptionsControlPanelEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(v7, &RLOUI_ETW_EVENT_COPY_SETTINGS_DEF, v8, 1u, &v12);
    if ( g_fWinSqmIsOptedIn )
    {
      v9 = *((_DWORD *)this + 1);
      v10 = *v2 == 0;
      v12 = 0;
      LODWORD(v12.Ptr) = 1;
      v12.Size = (v9 != 0 ? 2 : 0) | !v10;
      WinSqmAddToStream(0, 3768, 1, &v12);
    }
    SetCursor(v6);
    if ( (v11 & 0x200) != 0 )
    {
      Intl_RebootMessage(a2, 0xCCu, 0x48u);
    }
    else if ( (v11 & 0x100) != 0 )
    {
      Intl_LogoffMessage(a2);
    }
  }
}

```

## disassembly

```asm
0x1800096fc  mov     [rsp+arg_10], rbx
0x180009701  push    rbp
0x180009702  push    rsi
0x180009703  push    rdi
0x180009704  sub     rsp, 50h
0x180009708  mov     rax, cs:__security_cookie
0x18000970f  xor     rax, rsp
0x180009712  mov     [rsp+68h+var_20], rax
0x180009717  cmp     dword ptr [rcx+4], 0
0x18000971b  lea     rbx, [rcx+8]
0x18000971f  mov     rsi, rdx
0x180009722  mov     rdi, rcx
0x180009725  jnz     short loc_180009730
0x180009727  cmp     dword ptr [rbx], 0
0x18000972a  jz      loc_18000984A
0x180009730  mov     edx, 7F02h; lpCursorName
0x180009735  mov     [rsp+68h+var_38], 0
0x18000973d  xor     ecx, ecx; hInstance
0x18000973f  call    cs:__imp_LoadCursorW
0x180009745  mov     rcx, rax; hCursor
0x180009748  call    cs:__imp_SetCursor
0x18000974e  mov     rcx, [rdi+18h]
0x180009752  mov     rbp, rax
0x180009755  mov     r9d, [rdi+4]
0x180009759  mov     r8d, [rbx]
0x18000975c  mov     rdx, [rcx]
0x18000975f  mov     rax, [rdx+48h]
0x180009763  lea     rdx, [rsp+68h+var_38]
0x180009768  mov     [rsp+68h+var_48], rdx
0x18000976d  mov     rdx, rsi
0x180009770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009775  cmp     dword ptr [rbx], 0
0x180009778  jz      short loc_18000979F
0x18000977a  test    byte ptr cs:Microsoft_Windows_International_RegionalOptionsControlPanelEnableBits, 1
0x180009781  jz      short loc_18000979F
0x180009783  lea     rax, [rsp+68h+var_30]
0x180009788  mov     r9d, 1
0x18000978e  lea     rdx, RLOUI_ETW_EVENT_COPY_SETTINGS_SYS
0x180009795  mov     [rsp+68h+var_48], rax
0x18000979a  call    McGenEventWrite_EventWriteTransfer
0x18000979f  cmp     dword ptr [rdi+4], 0
0x1800097a3  jz      short loc_1800097CA
0x1800097a5  test    byte ptr cs:Microsoft_Windows_International_RegionalOptionsControlPanelEnableBits, 1
0x1800097ac  jz      short loc_1800097CA
0x1800097ae  lea     rax, [rsp+68h+var_30]
0x1800097b3  mov     r9d, 1
0x1800097b9  lea     rdx, RLOUI_ETW_EVENT_COPY_SETTINGS_DEF
0x1800097c0  mov     [rsp+68h+var_48], rax
0x1800097c5  call    McGenEventWrite_EventWriteTransfer
0x1800097ca  cmp     cs:?g_fWinSqmIsOptedIn@@3HA, 0; int g_fWinSqmIsOptedIn
0x1800097d1  jz      short loc_180009810
0x1800097d3  mov     eax, [rdi+4]
0x1800097d6  lea     r9, [rsp+68h+var_30]
0x1800097db  xor     edx, edx
0x1800097dd  xorps   xmm0, xmm0
0x1800097e0  cmp     [rbx], edx
0x1800097e2  movups  [rsp+68h+var_30], xmm0
0x1800097e7  setnz   dl
0x1800097ea  mov     dword ptr [rsp+68h+var_30], 1
0x1800097f2  neg     eax
0x1800097f4  sbb     ecx, ecx
0x1800097f6  and     ecx, 2
0x1800097f9  or      edx, ecx
0x1800097fb  xor     ecx, ecx
0x1800097fd  mov     dword ptr [rsp+68h+var_30+8], edx
0x180009801  mov     edx, 0EB8h
0x180009806  lea     r8d, [rcx+1]
0x18000980a  call    cs:__imp_WinSqmAddToStream
0x180009810  mov     rcx, rbp; hCursor
0x180009813  call    cs:__imp_SetCursor
0x180009819  test    [rsp+68h+var_38], 200h
0x180009821  jz      short loc_180009838
0x180009823  mov     edx, 0CCh; unsigned int
0x180009828  mov     r8d, 48h ; 'H'; unsigned int
0x18000982e  mov     rcx, rsi; HWND
0x180009831  call    ?Intl_RebootMessage@@YAXPEAUHWND__@@KK@Z; Intl_RebootMessage(HWND__ *,ulong,ulong)
0x180009836  jmp     short loc_18000984A
0x180009838  test    [rsp+68h+var_38], 100h
0x180009840  jz      short loc_18000984A
0x180009842  mov     rcx, rsi; HWND
0x180009845  call    ?Intl_LogoffMessage@@YAXPEAUHWND__@@@Z; Intl_LogoffMessage(HWND__ *)
0x18000984a  mov     rcx, [rsp+68h+var_20]
0x18000984f  xor     rcx, rsp; StackCookie
0x180009852  call    __security_check_cookie
0x180009857  mov     rbx, [rsp+68h+arg_10]
0x18000985f  add     rsp, 50h
0x180009863  pop     rdi
0x180009864  pop     rsi
0x180009865  pop     rbp
0x180009866  retn
```
