# CFtpObj::_DelayRender_URL(tagSTGMEDIUM *)

- ea: `0x18001aae4`
- end: `0x18001abf0`
- name: `?_DelayRender_URL@CFtpObj@@IEAAJPEAUtagSTGMEDIUM@@@Z`
- size: `268`
- prototype: `__int64 __fastcall(CFtpObj *__hidden this, struct tagSTGMEDIUM *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001af28`

## callees

- `0x180002240`
- `0x18001aae4`
- `0x18001bda4`
- `0x18001d6bc`
- `0x1800269f4`
- `0x1800271f0`

## import_xrefs

- `SHELL32!__imp_ILCombine` at `0x18001ab49`
- `SHELL32!__imp_ILCombine` at `0x18001ab49`
- `SHELL32!__imp_ILFree` at `0x18001abc1`
- `SHELL32!__imp_ILFree` at `0x18001abc1`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x18001abb8`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x18001abb8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ab9f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ab9f`
- `KERNEL32!lstrlenW` at `0x18001ab8f`
- `KERNEL32!lstrlenW` at `0x18001ab8f`

## pseudocode

```c
__int64 __fastcall CFtpObj::_DelayRender_URL(CFtpObj *this, struct tagSTGMEDIUM *a2)
{
  HBITMAP v3; // rdi
  __int64 v5; // rcx
  const struct _ITEMIDLIST *Ptr; // rbx
  ITEMIDLIST *v7; // rsi
  unsigned int v8; // ebx
  CHAR *v9; // rax
  WCHAR String[2088]; // [rsp+30h] [rbp-1078h] BYREF

  v3 = 0;
  v5 = *(_QWORD *)(*((_QWORD *)this + 7) + 16LL);
  if ( v5 )
    Ptr = (const struct _ITEMIDLIST *)DPA_GetPtr(*(HDPA *)(v5 + 16), 0);
  else
    Ptr = 0;
  if ( (unsigned int)FtpID_IsServerItemID(Ptr) )
  {
    v7 = 0;
  }
  else
  {
    v7 = ILCombine(*(LPCITEMIDLIST *)(*((_QWORD *)this + 6) + 48LL), Ptr);
    Ptr = v7;
  }
  if ( Ptr )
  {
    if ( (int)UrlCreateFromPidl(Ptr, 0x4000u, String, 0x824u, 0xC0000000, 1) >= 0 )
    {
      v8 = lstrlenW(String) + 1;
      v9 = (CHAR *)LocalAlloc(0x40u, v8);
      v3 = (HBITMAP)v9;
      if ( v9 )
        SHUnicodeToAnsi(String, v9, v8);
    }
    ILFree(v7);
  }
  a2->hBitmap = v3;
  return 0;
}

```

## disassembly

```asm
0x18001aae4  mov     [rsp+arg_10], rbx
0x18001aae9  push    rbp
0x18001aaea  push    rsi
0x18001aaeb  push    rdi
0x18001aaec  mov     eax, 1090h
0x18001aaf1  call    _alloca_probe
0x18001aaf6  sub     rsp, rax
0x18001aaf9  mov     rax, cs:__security_cookie
0x18001ab00  xor     rax, rsp
0x18001ab03  mov     [rsp+10A8h+var_28], rax
0x18001ab0b  mov     rax, [rcx+38h]
0x18001ab0f  mov     rsi, rcx
0x18001ab12  xor     edi, edi
0x18001ab14  mov     rbp, rdx
0x18001ab17  mov     rcx, [rax+10h]
0x18001ab1b  test    rcx, rcx
0x18001ab1e  jz      short loc_18001AB30
0x18001ab20  mov     rcx, [rcx+10h]; hdpa
0x18001ab24  xor     edx, edx; i
0x18001ab26  call    DPA_GetPtr
0x18001ab2b  mov     rbx, rax
0x18001ab2e  jmp     short loc_18001AB32
0x18001ab30  xor     ebx, ebx
0x18001ab32  mov     rcx, rbx; struct _ITEMIDLIST *
0x18001ab35  call    ?FtpID_IsServerItemID@@YAHPEFBU_ITEMIDLIST@@@Z; FtpID_IsServerItemID(_ITEMIDLIST const *)
0x18001ab3a  test    eax, eax
0x18001ab3c  jnz     short loc_18001AB57
0x18001ab3e  mov     rcx, [rsi+30h]
0x18001ab42  mov     rdx, rbx; pidl2
0x18001ab45  mov     rcx, [rcx+30h]; pidl1
0x18001ab49  call    cs:__imp_ILCombine
0x18001ab4f  mov     rsi, rax
0x18001ab52  mov     rbx, rax
0x18001ab55  jmp     short loc_18001AB59
0x18001ab57  xor     esi, esi
0x18001ab59  test    rbx, rbx
0x18001ab5c  jz      short loc_18001ABC7
0x18001ab5e  mov     [rsp+10A8h+var_1080], 1; int
0x18001ab66  lea     r8, [rsp+10A8h+String]; unsigned __int16 *
0x18001ab6b  mov     r9d, 824h; unsigned int
0x18001ab71  mov     [rsp+10A8h+var_1088], 0C0000000h; unsigned int
0x18001ab79  mov     edx, 4000h; unsigned int
0x18001ab7e  mov     rcx, rbx; struct _ITEMIDLIST *
0x18001ab81  call    ?UrlCreateFromPidl@@YAJPEFBU_ITEMIDLIST@@KPEAGKKH@Z; UrlCreateFromPidl(_ITEMIDLIST const *,ulong,ushort *,ulong,ulong,int)
0x18001ab86  test    eax, eax
0x18001ab88  js      short loc_18001ABBE
0x18001ab8a  lea     rcx, [rsp+10A8h+String]; lpString
0x18001ab8f  call    cs:__imp_lstrlenW
0x18001ab95  mov     ecx, 40h ; '@'; uFlags
0x18001ab9a  lea     ebx, [rax+1]
0x18001ab9d  mov     edx, ebx; uBytes
0x18001ab9f  call    cs:__imp_LocalAlloc
0x18001aba5  mov     rdi, rax
0x18001aba8  test    rax, rax
0x18001abab  jz      short loc_18001ABBE
0x18001abad  mov     r8d, ebx; cchBuf
0x18001abb0  lea     rcx, [rsp+10A8h+String]; pwszSrc
0x18001abb5  mov     rdx, rax; pszDst
0x18001abb8  call    cs:__imp_SHUnicodeToAnsi
0x18001abbe  mov     rcx, rsi; pidl
0x18001abc1  call    cs:__imp_ILFree
0x18001abc7  mov     [rbp+8], rdi
0x18001abcb  xor     eax, eax
0x18001abcd  mov     rcx, [rsp+10A8h+var_28]
0x18001abd5  xor     rcx, rsp; StackCookie
0x18001abd8  call    __security_check_cookie
0x18001abdd  mov     rbx, [rsp+10A8h+arg_10]
0x18001abe5  add     rsp, 1090h
0x18001abec  pop     rdi
0x18001abed  pop     rsi
0x18001abee  pop     rbp
0x18001abef  retn
```
