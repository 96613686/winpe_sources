# CFtpDialogTemplate::_InitType(HWND__ *,CFtpFolder *,CFtpPidlList *)

- ea: `0x180010e2c`
- end: `0x180010f01`
- name: `?_InitType@CFtpDialogTemplate@@AEAAJPEAUHWND__@@PEAVCFtpFolder@@PEAVCFtpPidlList@@@Z`
- size: `213`
- prototype: `__int64 __fastcall(CFtpDialogTemplate *__hidden this, HWND, struct CFtpFolder *, struct CFtpPidlList *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180010390`

## callees

- `0x180002240`
- `0x180010e2c`
- `0x180010f08`
- `0x18001bd78`
- `0x18001bda4`
- `0x18001c7e8`
- `0x1800269f4`
- `0x1800271f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180010ece`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180010ece`

## pseudocode

```c
int __fastcall CFtpDialogTemplate::_InitType(
        CFtpDialogTemplate *this,
        HWND a2,
        struct CFtpFolder *a3,
        struct CFtpPidlList *a4)
{
  const struct _ITEMIDLIST *Ptr; // rax
  __int64 v6; // rdx
  struct _DPA *v7; // r9
  UINT v8; // edx
  CFtpDialogTemplate *v9; // rcx
  const struct _ITEMIDLIST *LastIDReferense; // rax
  WCHAR Buffer[2088]; // [rsp+20h] [rbp-1068h] BYREF

  Ptr = 0;
  v6 = *((_QWORD *)a4 + 2);
  Buffer[0] = 0;
  v7 = *(struct _DPA **)(v6 + 16);
  if ( *(_DWORD *)v7 )
  {
    if ( *(_DWORD *)v7 != 1 )
    {
      v8 = 264;
LABEL_9:
      LoadStringW(g_hinst, v8, Buffer, 2084);
      return CFtpDialogTemplate::_ReinsertDlgText(v9, a2, Buffer, L"%s");
    }
    if ( v6 )
      Ptr = (const struct _ITEMIDLIST *)DPA_GetPtr(v7, 0);
    FtpPidl_GetFileType(Ptr, Buffer, 0x824u);
  }
  else
  {
    LastIDReferense = FtpID_GetLastIDReferense((const struct _ITEMIDLIST *)(*((_QWORD *)a3 + 6) + *((int *)a3 + 16)));
    if ( LastIDReferense )
    {
      v8 = ((unsigned int)FtpID_IsServerItemID(LastIDReferense) != 0) + 286;
      goto LABEL_9;
    }
  }
  return CFtpDialogTemplate::_ReinsertDlgText(v9, a2, Buffer, L"%s");
}

```

## disassembly

```asm
0x180010e2c  push    rbx
0x180010e2e  mov     eax, 1080h
0x180010e33  call    _alloca_probe
0x180010e38  sub     rsp, rax
0x180010e3b  mov     rax, cs:__security_cookie
0x180010e42  xor     rax, rsp
0x180010e45  mov     [rsp+1088h+var_18], rax
0x180010e4d  xor     eax, eax
0x180010e4f  mov     rbx, rdx
0x180010e52  mov     rdx, [r9+10h]
0x180010e56  mov     [rsp+1088h+Buffer], ax
0x180010e5b  mov     r9, [rdx+10h]
0x180010e5f  mov     ecx, [r9]
0x180010e62  test    ecx, ecx
0x180010e64  jz      short loc_180010E96
0x180010e66  cmp     ecx, 1
0x180010e69  jz      short loc_180010E72
0x180010e6b  mov     edx, 108h
0x180010e70  jmp     short loc_180010EBC
0x180010e72  test    rdx, rdx
0x180010e75  jz      short loc_180010E81
0x180010e77  xor     edx, edx; i
0x180010e79  mov     rcx, r9; hdpa
0x180010e7c  call    DPA_GetPtr
0x180010e81  mov     r8d, 824h; unsigned int
0x180010e87  lea     rdx, [rsp+1088h+Buffer]; unsigned __int16 *
0x180010e8c  mov     rcx, rax; struct _ITEMIDLIST *
0x180010e8f  call    ?FtpPidl_GetFileType@@YAJPEFBU_ITEMIDLIST@@PEAGK@Z; FtpPidl_GetFileType(_ITEMIDLIST const *,ushort *,ulong)
0x180010e94  jmp     short loc_180010ED4
0x180010e96  movsxd  rcx, dword ptr [r8+40h]
0x180010e9a  add     rcx, [r8+30h]; struct _ITEMIDLIST *
0x180010e9e  call    ?FtpID_GetLastIDReferense@@YAPEFBU_ITEMIDLIST@@PEFBU1@@Z; FtpID_GetLastIDReferense(_ITEMIDLIST const *)
0x180010ea3  test    rax, rax
0x180010ea6  jz      short loc_180010ED4
0x180010ea8  mov     rcx, rax; struct _ITEMIDLIST *
0x180010eab  call    ?FtpID_IsServerItemID@@YAHPEFBU_ITEMIDLIST@@@Z; FtpID_IsServerItemID(_ITEMIDLIST const *)
0x180010eb0  neg     eax
0x180010eb2  sbb     edx, edx
0x180010eb4  neg     edx
0x180010eb6  add     edx, 11Eh; uID
0x180010ebc  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x180010ec3  lea     r8, [rsp+1088h+Buffer]; lpBuffer
0x180010ec8  mov     r9d, 824h; cchBufferMax
0x180010ece  call    cs:__imp_LoadStringW
0x180010ed4  lea     r9, aS; "%s"
0x180010edb  mov     rdx, rbx; HWND
0x180010ede  lea     r8, [rsp+1088h+Buffer]; void *
0x180010ee3  call    ?_ReinsertDlgText@CFtpDialogTemplate@@AEAAJPEAUHWND__@@PEBXPEBG@Z; CFtpDialogTemplate::_ReinsertDlgText(HWND__ *,void const *,ushort const *)
0x180010ee8  mov     rcx, [rsp+1088h+var_18]
0x180010ef0  xor     rcx, rsp; StackCookie
0x180010ef3  call    __security_check_cookie
0x180010ef8  add     rsp, 1080h
0x180010eff  pop     rbx
0x180010f00  retn
```
