# CNovInterDlg::SetFullWindowDrag(int,int)

- ea: `0x140024b5c`
- end: `0x140024c3c`
- name: `?SetFullWindowDrag@CNovInterDlg@@QEAAJHH@Z`
- size: `224`
- prototype: `__int64 __fastcall(CNovInterDlg *__hidden this, int, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000ea24`
- `0x1400241a0`
- `0x140025138`

## callees

- `0x140024b5c`
- `0x140034ce4`
- `0x140035288`
- `0x140035fb8`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x140024b80`
- `USER32!SystemParametersInfoW` at `0x140024be1`
- `USER32!SystemParametersInfoW` at `0x140024c0c`
- `USER32!SystemParametersInfoW` at `0x140024b80`
- `USER32!SystemParametersInfoW` at `0x140024be1`
- `USER32!SystemParametersInfoW` at `0x140024c0c`

## pseudocode

```c
__int64 __fastcall CNovInterDlg::SetFullWindowDrag(CNovInterDlg *this, int a2, int a3)
{
  _DWORD *v3; // rbx
  CEventLogger *v4; // rcx
  unsigned int v5; // r9d

  if ( a2 )
  {
    if ( SystemParametersInfoW(0x25u, *((_DWORD *)this + 34), 0, 2u) )
    {
      DeleteRegistryValue(L"Window Drag");
      return 0;
    }
    v5 = 3809;
    goto LABEL_5;
  }
  if ( a3 == 1 )
  {
    v3 = (_DWORD *)((char *)this + 136);
    if ( !SystemParametersInfoW(0x26u, 0, (char *)this + 136, 0) )
    {
      v5 = 3785;
      goto LABEL_5;
    }
    SetRegistryValue(L"Window Drag", *v3 == 1);
  }
  if ( SystemParametersInfoW(0x25u, 0, 0, 2u) )
    return 0;
  v5 = 3801;
LABEL_5:
  CEventLogger::LogError(
    v4,
    &Recoverable_Error,
    L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
    v5,
    L"CNovInterDlg::SetFullWindowDrag",
    0);
  return 0;
}

```

## disassembly

```asm
0x140024b5c  push    rbx
0x140024b5e  sub     rsp, 30h
0x140024b62  test    edx, edx
0x140024b64  jnz     loc_140024BF9
0x140024b6a  cmp     r8d, 1
0x140024b6e  jnz     short loc_140024BD3
0x140024b70  lea     rbx, [rcx+88h]
0x140024b77  xor     r9d, r9d; fWinIni
0x140024b7a  mov     r8, rbx; pvParam
0x140024b7d  lea     ecx, [rdx+26h]; uiAction
0x140024b80  call    cs:__imp_SystemParametersInfoW
0x140024b87  nop     dword ptr [rax+rax+00h]
0x140024b8c  test    eax, eax
0x140024b8e  jnz     short loc_140024BBF
0x140024b90  mov     r9d, 0EC9h; unsigned int
0x140024b96  lea     rax, aCnovinterdlgSe_3; "CNovInterDlg::SetFullWindowDrag"
0x140024b9d  mov     [rsp+38h+var_10], 0; unsigned int
0x140024ba5  lea     r8, aBaseDiagnosisR_32; "base\\diagnosis\\ra\\ui\\novinterdialog"...
0x140024bac  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x140024bb1  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140024bb8  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140024bbd  jmp     short loc_140024C33
0x140024bbf  xor     edx, edx
0x140024bc1  lea     rcx, aWindowDrag; "Window Drag"
0x140024bc8  cmp     dword ptr [rbx], 1
0x140024bcb  setz    dl; unsigned int
0x140024bce  call    ?SetRegistryValue@@YAJPEAGK@Z; SetRegistryValue(ushort *,ulong)
0x140024bd3  xor     edx, edx; uiParam
0x140024bd5  mov     r9d, 2; fWinIni
0x140024bdb  xor     r8d, r8d; pvParam
0x140024bde  lea     ecx, [rdx+25h]; uiAction
0x140024be1  call    cs:__imp_SystemParametersInfoW
0x140024be8  nop     dword ptr [rax+rax+00h]
0x140024bed  test    eax, eax
0x140024bef  jnz     short loc_140024C33
0x140024bf1  mov     r9d, 0ED9h
0x140024bf7  jmp     short loc_140024B96
0x140024bf9  mov     edx, [rcx+88h]; uiParam
0x140024bff  mov     r9d, 2; fWinIni
0x140024c05  xor     r8d, r8d; pvParam
0x140024c08  lea     ecx, [r9+23h]; uiAction
0x140024c0c  call    cs:__imp_SystemParametersInfoW
0x140024c13  nop     dword ptr [rax+rax+00h]
0x140024c18  test    eax, eax
0x140024c1a  jnz     short loc_140024C27
0x140024c1c  mov     r9d, 0EE1h
0x140024c22  jmp     loc_140024B96
0x140024c27  lea     rcx, aWindowDrag; "Window Drag"
0x140024c2e  call    ?DeleteRegistryValue@@YAJPEAG@Z; DeleteRegistryValue(ushort *)
0x140024c33  xor     eax, eax
0x140024c35  add     rsp, 30h
0x140024c39  pop     rbx
0x140024c3a  retn
```
