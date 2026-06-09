# CFtpDialogTemplate::_InitTime(HWND__ *,HWND__ *,CFtpFolder *,CFtpPidlList *)

- ea: `0x180010cd4`
- end: `0x180010e26`
- name: `?_InitTime@CFtpDialogTemplate@@AEAAJPEAUHWND__@@0PEAVCFtpFolder@@PEAVCFtpPidlList@@@Z`
- size: `338`
- prototype: `int(CFtpDialogTemplate *__hidden this, HWND, HWND, struct CFtpFolder *, struct CFtpPidlList *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180010390`

## callees

- `0x180002240`
- `0x180010cd4`
- `0x180010f08`
- `0x18001bd78`
- `0x18001bda4`
- `0x18001c7a8`
- `0x1800252fc`
- `0x1800269f4`

## import_xrefs

- `SHLWAPI!__imp_SHFormatDateTimeW` at `0x180010dc5`
- `SHLWAPI!__imp_SHFormatDateTimeW` at `0x180010dc5`

## pseudocode

```c
int __fastcall CFtpDialogTemplate::_InitTime(
        CFtpDialogTemplate *this,
        HWND a2,
        HWND a3,
        struct CFtpFolder *a4,
        struct CFtpPidlList *a5)
{
  __int64 v7; // rdx
  struct _DPA *v8; // r8
  const struct _ITEMIDLIST *v9; // rax
  __int64 v10; // rcx
  const struct _ITEMIDLIST *Ptr; // rax
  const struct _ITEMIDLIST *v12; // rcx
  const struct _ITEMIDLIST *LastIDReferense; // rax
  const struct _ITEMIDLIST *v14; // rbx
  CFtpDialogTemplate *v15; // rcx
  int v17; // edx
  DWORD pdwFlags; // [rsp+20h] [rbp-E0h] BYREF
  FILETIME pft; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR pszBuf[264]; // [rsp+30h] [rbp-D0h] BYREF

  v7 = *((_QWORD *)a5 + 2);
  v8 = *(struct _DPA **)(v7 + 16);
  if ( *(_DWORD *)v8 )
  {
    if ( *(_DWORD *)v8 != 1 )
      goto LABEL_18;
    v9 = v7 ? (const struct _ITEMIDLIST *)DPA_GetPtr(v8, 0) : 0LL;
    if ( (unsigned int)FtpID_IsServerItemID(v9) )
      goto LABEL_18;
    v10 = *((_QWORD *)a5 + 2);
    if ( !v10 )
      goto LABEL_18;
    Ptr = (const struct _ITEMIDLIST *)DPA_GetPtr(*(HDPA *)(v10 + 16), 0);
    pft = 0;
    if ( !Ptr )
      goto LABEL_18;
    v12 = Ptr;
  }
  else
  {
    LastIDReferense = FtpID_GetLastIDReferense((const struct _ITEMIDLIST *)(*((_QWORD *)a4 + 6) + *((int *)a4 + 16)));
    v14 = LastIDReferense;
    if ( !LastIDReferense || (unsigned int)FtpID_IsServerItemID(LastIDReferense) )
      goto LABEL_18;
    v12 = v14;
  }
  pft = FtpPidl_GetFileTime(v12);
  pdwFlags = 5;
  if ( pft.dwHighDateTime )
    SHFormatDateTimeW(&pft, &pdwFlags, pszBuf, 0x104u);
  else
    pszBuf[0] = 0;
  if ( pszBuf[0] )
    return CFtpDialogTemplate::_ReinsertDlgText(v15, a2, pszBuf, L"%s");
LABEL_18:
  ShowEnableWindow(a2, v7);
  if ( a3 )
    ShowEnableWindow(a3, v17);
  return 0;
}

```

## disassembly

```asm
0x180010cd4  push    rbp
0x180010cd6  push    rbx
0x180010cd7  push    rsi
0x180010cd8  push    rdi
0x180010cd9  push    r14
0x180010cdb  lea     rbp, [rsp-150h]
0x180010ce3  sub     rsp, 250h
0x180010cea  mov     rax, cs:__security_cookie
0x180010cf1  xor     rax, rsp
0x180010cf4  mov     [rbp+170h+var_30], rax
0x180010cfb  mov     rbx, [rbp+170h+arg_20]
0x180010d02  mov     rsi, rdx
0x180010d05  mov     rdi, r8
0x180010d08  xor     r14d, r14d
0x180010d0b  mov     rdx, [rbx+10h]; int
0x180010d0f  mov     r8, [rdx+10h]
0x180010d13  mov     ecx, [r8]
0x180010d16  test    ecx, ecx
0x180010d18  jz      short loc_180010D72
0x180010d1a  cmp     ecx, 1
0x180010d1d  jnz     loc_180010DF1
0x180010d23  test    rdx, rdx
0x180010d26  jz      short loc_180010D34
0x180010d28  xor     edx, edx; i
0x180010d2a  mov     rcx, r8; hdpa
0x180010d2d  call    DPA_GetPtr
0x180010d32  jmp     short loc_180010D37
0x180010d34  mov     rax, r14
0x180010d37  mov     rcx, rax; struct _ITEMIDLIST *
0x180010d3a  call    ?FtpID_IsServerItemID@@YAHPEFBU_ITEMIDLIST@@@Z; FtpID_IsServerItemID(_ITEMIDLIST const *)
0x180010d3f  test    eax, eax
0x180010d41  jnz     loc_180010DF1
0x180010d47  mov     rcx, [rbx+10h]
0x180010d4b  test    rcx, rcx
0x180010d4e  jz      loc_180010DF1
0x180010d54  mov     rcx, [rcx+10h]; hdpa
0x180010d58  xor     edx, edx; i
0x180010d5a  call    DPA_GetPtr
0x180010d5f  mov     qword ptr [rsp+270h+pft.dwLowDateTime], r14
0x180010d64  test    rax, rax
0x180010d67  jz      loc_180010DF1
0x180010d6d  mov     rcx, rax
0x180010d70  jmp     short loc_180010D96
0x180010d72  movsxd  rcx, dword ptr [r9+40h]
0x180010d76  add     rcx, [r9+30h]; struct _ITEMIDLIST *
0x180010d7a  call    ?FtpID_GetLastIDReferense@@YAPEFBU_ITEMIDLIST@@PEFBU1@@Z; FtpID_GetLastIDReferense(_ITEMIDLIST const *)
0x180010d7f  mov     rbx, rax
0x180010d82  test    rax, rax
0x180010d85  jz      short loc_180010DF1
0x180010d87  mov     rcx, rax; struct _ITEMIDLIST *
0x180010d8a  call    ?FtpID_IsServerItemID@@YAHPEFBU_ITEMIDLIST@@@Z; FtpID_IsServerItemID(_ITEMIDLIST const *)
0x180010d8f  test    eax, eax
0x180010d91  jnz     short loc_180010DF1
0x180010d93  mov     rcx, rbx; struct _ITEMIDLIST *
0x180010d96  call    ?FtpPidl_GetFileTime@@YA?AU_FILETIME@@PEFBU_ITEMIDLIST@@@Z; FtpPidl_GetFileTime(_ITEMIDLIST const *)
0x180010d9b  mov     qword ptr [rsp+270h+pft.dwLowDateTime], rax
0x180010da0  shr     rax, 20h
0x180010da4  mov     [rsp+270h+pdwFlags], 5
0x180010dac  test    eax, eax
0x180010dae  jz      short loc_180010DCD
0x180010db0  mov     r9d, 104h; cchBuf
0x180010db6  lea     r8, [rsp+270h+pszBuf]; pszBuf
0x180010dbb  lea     rdx, [rsp+270h+pdwFlags]; pdwFlags
0x180010dc0  lea     rcx, [rsp+270h+pft]; pft
0x180010dc5  call    cs:__imp_SHFormatDateTimeW
0x180010dcb  jmp     short loc_180010DD3
0x180010dcd  mov     [rsp+270h+pszBuf], r14w
0x180010dd3  cmp     [rsp+270h+pszBuf], r14w
0x180010dd9  jz      short loc_180010DF1
0x180010ddb  lea     r9, aS; "%s"
0x180010de2  mov     rdx, rsi; HWND
0x180010de5  lea     r8, [rsp+270h+pszBuf]; void *
0x180010dea  call    ?_ReinsertDlgText@CFtpDialogTemplate@@AEAAJPEAUHWND__@@PEBXPEBG@Z; CFtpDialogTemplate::_ReinsertDlgText(HWND__ *,void const *,ushort const *)
0x180010def  jmp     short loc_180010E09
0x180010df1  mov     rcx, rsi; HWND
0x180010df4  call    ?ShowEnableWindow@@YAXPEAUHWND__@@H@Z; ShowEnableWindow(HWND__ *,int)
0x180010df9  test    rdi, rdi
0x180010dfc  jz      short loc_180010E06
0x180010dfe  mov     rcx, rdi; HWND
0x180010e01  call    ?ShowEnableWindow@@YAXPEAUHWND__@@H@Z; ShowEnableWindow(HWND__ *,int)
0x180010e06  mov     eax, r14d
0x180010e09  mov     rcx, [rbp+170h+var_30]
0x180010e10  xor     rcx, rsp; StackCookie
0x180010e13  call    __security_check_cookie
0x180010e18  add     rsp, 250h
0x180010e1f  pop     r14
0x180010e21  pop     rdi
0x180010e22  pop     rsi
0x180010e23  pop     rbx
0x180010e24  pop     rbp
0x180010e25  retn
```
