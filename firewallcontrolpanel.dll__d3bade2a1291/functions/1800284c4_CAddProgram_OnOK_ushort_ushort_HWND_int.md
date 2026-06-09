# CAddProgram::OnOK(ushort,ushort,HWND__ *,int &)

- ea: `0x1800284c4`
- end: `0x180028704`
- name: `?OnOK@CAddProgram@@AEAA_JGGPEAUHWND__@@AEAH@Z`
- size: `576`
- prototype: `__int64 __fastcall(CAddProgram *__hidden this, unsigned __int16, unsigned __int16, HWND, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180028710`

## callees

- `0x180009040`
- `0x180011650`
- `0x180015780`
- `0x180018010`
- `0x1800284c4`
- `0x180030e6e`
- `0x180030ea0`
- `0x180032010`

## import_xrefs

- `ntdll!WinSqmIncrementDWORD` at `0x1800286a9`
- `ntdll!WinSqmIncrementDWORD` at `0x1800286a9`
- `ntdll!EtwEventWrite` at `0x180028554`
- `ntdll!EtwEventWrite` at `0x1800286d5`
- `ntdll!EtwEventWrite` at `0x180028554`
- `ntdll!EtwEventWrite` at `0x1800286d5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800285ff`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800285ff`
- `USER32!SendMessageW` at `0x18002856d`
- `USER32!SendMessageW` at `0x1800285aa`
- `USER32!SendMessageW` at `0x18002856d`
- `USER32!SendMessageW` at `0x1800285aa`
- `USER32!EndDialog` at `0x1800286b6`
- `USER32!EndDialog` at `0x1800286b6`
- `USER32!SetFocus` at `0x180028696`
- `USER32!SetFocus` at `0x180028696`

## pseudocode

```c
__int64 __fastcall CAddProgram::OnOK(CAddProgram *this, __int16 a2, __int64 a3, HWND a4, int *a5)
{
  int v7; // eax
  HWND v8; // rcx
  const WCHAR *v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rax
  LPCWSTR **Next; // rax
  LPCWSTR *v13; // rsi
  UINT v14; // r9d
  int v15; // eax
  INT_PTR v16; // rbx
  HWND *DlgItem; // rax
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD lParam[6]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v22; // [rsp+58h] [rbp-A8h]
  int v23; // [rsp+60h] [rbp-A0h]
  LPCWSTR lpString1; // [rsp+68h] [rbp-98h]
  unsigned __int16 v25[264]; // [rsp+A0h] [rbp-60h] BYREF

  memset_0(v25, 0, 0x208u);
  memset_0(lParam, 0, 0x58u);
  *a5 = 1;
  v20 = 0;
  if ( a2 )
  {
    *a5 = 0;
  }
  else
  {
    if ( g_Provider )
      EtwEventWrite(g_Provider, AddAppException_Start, 0, 0);
    v7 = SendMessageW(*((HWND *)this + 11), 0x100Cu, 0xFFFFFFFFFFFFFFFFuLL, 3);
    if ( v7 != -1 )
    {
      v8 = (HWND)*((_QWORD *)this + 11);
      lParam[1] = v7;
      lParam[0] = 5;
      v22 = v25;
      v23 = 260;
      if ( (unsigned int)SendMessageW(v8, 0x104Bu, 0, (LPARAM)lParam) )
      {
        v9 = lpString1;
        v10 = *(_QWORD *)(*((_QWORD *)this + 12) + 48LL);
        v11 = *(_QWORD *)(v10 + 16);
        v19 = v11;
        while ( v11 )
        {
          Next = (LPCWSTR **)ATL::CAtlList<CFwProfileViewUpdate *,ATL::CElementTraits<CFwProfileViewUpdate *>>::GetNext(
                               v10,
                               &v19);
          v13 = *Next;
          if ( !(*((unsigned int (__fastcall **)(LPCWSTR *))**Next + 12))(*Next) && v9 && !lstrcmpiW(v9, v13[6]) )
          {
            (*((void (__fastcall **)(LPCWSTR *, __int64 *))*v13 + 3))(v13, &v20);
            v14 = 46;
LABEL_16:
            MessageBoxFromResourceWithArgs(*((HWND *)this + 1), g_hinst, 0x2F5Au, v14, 0x10010u, v25);
            DlgItem = (HWND *)ATL::CWindow::GetDlgItem((char *)this + 8, &v19, 1630);
            SetFocus(*DlgItem);
            goto LABEL_18;
          }
          v11 = v19;
        }
        v15 = CConfigureApps::AddProgram(
                *((CConfigureApps **)this + 12),
                v25,
                lpString1,
                *((_DWORD *)this + 30),
                *((struct IFwCplLua **)this + 13));
        v16 = v15;
        if ( v15 < 0 )
        {
          v14 = 58;
          goto LABEL_16;
        }
        WinSqmIncrementDWORD(0, 3102, 1);
        EndDialog(*((HWND *)this + 1), v16);
      }
    }
  }
LABEL_18:
  if ( g_Provider )
    EtwEventWrite(g_Provider, AddAppException_End, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x1800284c4  mov     [rsp-8+arg_8], rbx
0x1800284c9  mov     [rsp-8+arg_10], rsi
0x1800284ce  push    rbp
0x1800284cf  push    rdi
0x1800284d0  push    r14
0x1800284d2  lea     rbp, [rsp-1C0h]
0x1800284da  sub     rsp, 2C0h
0x1800284e1  mov     rax, cs:__security_cookie
0x1800284e8  xor     rax, rsp
0x1800284eb  mov     [rbp+1D0h+var_20], rax
0x1800284f2  mov     rsi, [rbp+1D0h+arg_20]
0x1800284f9  movzx   ebx, dx
0x1800284fc  mov     rdi, rcx
0x1800284ff  xor     edx, edx; Val
0x180028501  lea     rcx, [rbp+1D0h+var_230]; void *
0x180028505  mov     r8d, 208h; Size
0x18002850b  call    memset_0
0x180028510  xor     edx, edx; Val
0x180028512  lea     rcx, [rsp+2D0h+lParam]; void *
0x180028517  lea     r8d, [rdx+58h]; Size
0x18002851b  call    memset_0
0x180028520  xor     r14d, r14d
0x180028523  mov     dword ptr [rsi], 1
0x180028529  mov     [rsp+2D0h+var_298], r14
0x18002852e  test    bx, bx
0x180028531  jz      short loc_18002853B
0x180028533  mov     [rsi], r14d
0x180028536  jmp     loc_1800286BC
0x18002853b  mov     rcx, cs:g_Provider
0x180028542  test    rcx, rcx
0x180028545  jz      short loc_18002855A
0x180028547  xor     r9d, r9d
0x18002854a  lea     rdx, AddAppException_Start
0x180028551  xor     r8d, r8d
0x180028554  call    cs:__imp_EtwEventWrite
0x18002855a  mov     rcx, [rdi+58h]; hWnd
0x18002855e  mov     r9d, 3; lParam
0x180028564  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x180028568  mov     edx, 100Ch; Msg
0x18002856d  call    cs:__imp_SendMessageW
0x180028573  cmp     eax, 0FFFFFFFFh
0x180028576  jz      loc_1800286BC
0x18002857c  mov     rcx, [rdi+58h]; hWnd
0x180028580  lea     r9, [rsp+2D0h+lParam]; lParam
0x180028585  mov     [rsp+2D0h+lParam+4], eax
0x180028589  xor     r8d, r8d; wParam
0x18002858c  lea     rax, [rbp+1D0h+var_230]
0x180028590  mov     [rsp+2D0h+lParam], 5
0x180028598  mov     edx, 104Bh; Msg
0x18002859d  mov     [rsp+2D0h+var_278], rax
0x1800285a2  mov     [rsp+2D0h+var_270], 104h
0x1800285aa  call    cs:__imp_SendMessageW
0x1800285b0  test    eax, eax
0x1800285b2  jz      loc_1800286BC
0x1800285b8  mov     rax, [rdi+60h]
0x1800285bc  mov     rbx, [rsp+2D0h+lpString1]
0x1800285c1  mov     rcx, [rax+30h]
0x1800285c5  mov     rax, [rcx+10h]
0x1800285c9  mov     [rsp+2D0h+var_2A0], rax
0x1800285ce  test    rax, rax
0x1800285d1  jz      short loc_18002862C
0x1800285d3  lea     rdx, [rsp+2D0h+var_2A0]
0x1800285d8  call    ?GetNext@?$CAtlList@PEAVCFwProfileViewUpdate@@V?$CElementTraits@PEAVCFwProfileViewUpdate@@@ATL@@@ATL@@QEAAAEAPEAVCFwProfileViewUpdate@@AEAPEAU__POSITION@@@Z; ATL::CAtlList<CFwProfileViewUpdate *,ATL::CElementTraits<CFwProfileViewUpdate *>>::GetNext(__POSITION * &)
0x1800285dd  mov     rsi, [rax]
0x1800285e0  mov     rcx, rsi
0x1800285e3  mov     rax, [rsi]
0x1800285e6  mov     rax, [rax+60h]
0x1800285ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285ef  test    eax, eax
0x1800285f1  jnz     short loc_180028609
0x1800285f3  test    rbx, rbx
0x1800285f6  jz      short loc_180028609
0x1800285f8  mov     rdx, [rsi+30h]; lpString2
0x1800285fc  mov     rcx, rbx; lpString1
0x1800285ff  call    cs:__imp_lstrcmpiW
0x180028605  test    eax, eax
0x180028607  jz      short loc_180028610
0x180028609  mov     rax, [rsp+2D0h+var_2A0]
0x18002860e  jmp     short loc_1800285CE
0x180028610  mov     rax, [rsi]
0x180028613  lea     rdx, [rsp+2D0h+var_298]
0x180028618  mov     rcx, rsi
0x18002861b  mov     rax, [rax+18h]
0x18002861f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028624  mov     r9d, 2Eh ; '.'
0x18002862a  jmp     short loc_180028658
0x18002862c  mov     rax, [rdi+68h]
0x180028630  lea     rdx, [rbp+1D0h+var_230]; unsigned __int16 *
0x180028634  mov     r9d, [rdi+78h]; unsigned int
0x180028638  mov     r8, [rsp+2D0h+lpString1]; unsigned __int16 *
0x18002863d  mov     rcx, [rdi+60h]; this
0x180028641  mov     qword ptr [rsp+2D0h+uType], rax; struct IFwCplLua *
0x180028646  call    ?AddProgram@CConfigureApps@@QEAAJPEBG0KPEAUIFwCplLua@@@Z; CConfigureApps::AddProgram(ushort const *,ushort const *,ulong,IFwCplLua *)
0x18002864b  movsxd  rbx, eax
0x18002864e  test    eax, eax
0x180028650  jns     short loc_18002869E
0x180028652  mov     r9d, 3Ah ; ':'; UINT
0x180028658  mov     rdx, cs:g_hinst; hInstance
0x18002865f  lea     rax, [rbp+1D0h+var_230]
0x180028663  mov     rcx, [rdi+8]; hWnd
0x180028667  mov     r8d, 2F5Ah; uID
0x18002866d  mov     [rsp+2D0h+var_2A8], rax
0x180028672  mov     [rsp+2D0h+uType], 10010h; uType
0x18002867a  call    ?MessageBoxFromResourceWithArgs@@YAHPEAUHWND__@@PEAUHINSTANCE__@@IIIZZ; MessageBoxFromResourceWithArgs(HWND__ *,HINSTANCE__ *,uint,uint,uint,...)
0x18002867f  lea     rcx, [rdi+8]
0x180028683  mov     r8d, 65Eh
0x180028689  lea     rdx, [rsp+2D0h+var_2A0]
0x18002868e  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180028693  mov     rcx, [rax]; hWnd
0x180028696  call    cs:__imp_SetFocus
0x18002869c  jmp     short loc_1800286BC
0x18002869e  xor     ecx, ecx
0x1800286a0  mov     edx, 0C1Eh
0x1800286a5  lea     r8d, [rcx+1]
0x1800286a9  call    cs:__imp_WinSqmIncrementDWORD
0x1800286af  mov     rcx, [rdi+8]; hDlg
0x1800286b3  mov     rdx, rbx; nResult
0x1800286b6  call    cs:__imp_EndDialog
0x1800286bc  mov     rcx, cs:g_Provider
0x1800286c3  test    rcx, rcx
0x1800286c6  jz      short loc_1800286DB
0x1800286c8  xor     r9d, r9d
0x1800286cb  lea     rdx, AddAppException_End
0x1800286d2  xor     r8d, r8d
0x1800286d5  call    cs:__imp_EtwEventWrite
0x1800286db  xor     eax, eax
0x1800286dd  mov     rcx, [rbp+1D0h+var_20]
0x1800286e4  xor     rcx, rsp; StackCookie
0x1800286e7  call    __security_check_cookie
0x1800286ec  lea     r11, [rsp+2D0h+var_10]
0x1800286f4  mov     rbx, [r11+28h]
0x1800286f8  mov     rsi, [r11+30h]
0x1800286fc  mov     rsp, r11
0x1800286ff  pop     r14
0x180028701  pop     rdi
0x180028702  pop     rbp
0x180028703  retn
```
