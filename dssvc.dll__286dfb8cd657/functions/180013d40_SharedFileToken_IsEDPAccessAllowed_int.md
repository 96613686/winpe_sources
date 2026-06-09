# SharedFileToken::IsEDPAccessAllowed(int *)

- ea: `0x180013d40`
- end: `0x180013df4`
- name: `?IsEDPAccessAllowed@SharedFileToken@@UEAAJPEAH@Z`
- size: `180`
- prototype: `__int64 __fastcall(SharedFileToken *__hidden this, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180013d40`
- `0x18001a498`

## import_xrefs

- `ext-ms-win-edputil-policy-l1-1-0!EdpIsFileAccessAllowed` at `0x180013dbb`
- `ext-ms-win-edputil-policy-l1-1-0!EdpIsFileAccessAllowed` at `0x180013dbb`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x180013d5d`
- `ext-ms-win-edputil-policy-l1-1-0!EdpGetIsManaged` at `0x180013d5d`
- `FeClient!EfsClientQueryProtectors` at `0x180013d8c`
- `FeClient!EfsClientQueryProtectors` at `0x180013d8c`
- `FeClient!EfsClientFreeProtectorList` at `0x180013ddc`
- `FeClient!EfsClientFreeProtectorList` at `0x180013ddc`

## pseudocode

```c
__int64 __fastcall SharedFileToken::IsEDPAccessAllowed(SharedFileToken *this, int *a2)
{
  signed int v4; // ebx
  const unsigned __int16 *v5; // rdx
  const WCHAR *v6; // rdi
  int v7; // eax
  __int64 v8; // rcx
  int IsFileAccessAllowed; // eax
  char v11; // [rsp+38h] [rbp+10h] BYREF
  __int64 v12; // [rsp+40h] [rbp+18h] BYREF

  *a2 = 1;
  v4 = 0;
  if ( (unsigned int)EdpGetIsManaged() )
  {
    v6 = (const WCHAR *)*((_QWORD *)this + 19);
    if ( v6 )
    {
      if ( (unsigned int)DSUtils::IsFileEncrypted(v6, v5) )
      {
        v12 = 0;
        v7 = EfsClientQueryProtectors(v6, &v12);
        v4 = v7;
        if ( v7 > 0 )
          v4 = (unsigned __int16)v7 | 0x80070000;
        v8 = v12;
        if ( v4 >= 0 )
        {
          v11 = 1;
          IsFileAccessAllowed = EdpIsFileAccessAllowed(v12, -6, &v11);
          v8 = v12;
          v4 = IsFileAccessAllowed;
          if ( IsFileAccessAllowed >= 0 )
            *a2 = v11 != 0;
        }
        if ( v8 )
          EfsClientFreeProtectorList();
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180013d40  mov     [rsp+arg_0], rbx
0x180013d45  mov     [rsp+arg_18], rsi
0x180013d4a  push    rdi
0x180013d4b  sub     rsp, 20h
0x180013d4f  mov     rsi, rdx
0x180013d52  mov     dword ptr [rdx], 1
0x180013d58  mov     rdi, rcx
0x180013d5b  xor     ebx, ebx
0x180013d5d  call    cs:__imp_EdpGetIsManaged
0x180013d63  test    eax, eax
0x180013d65  jz      short loc_180013DE2
0x180013d67  mov     rdi, [rdi+98h]
0x180013d6e  test    rdi, rdi
0x180013d71  jz      short loc_180013DE2
0x180013d73  mov     rcx, rdi; lpFileName
0x180013d76  call    ?IsFileEncrypted@DSUtils@@YAHPEBG@Z; DSUtils::IsFileEncrypted(ushort const *)
0x180013d7b  test    eax, eax
0x180013d7d  jz      short loc_180013DE2
0x180013d7f  lea     rdx, [rsp+28h+arg_10]
0x180013d84  mov     [rsp+28h+arg_10], rbx
0x180013d89  mov     rcx, rdi
0x180013d8c  call    cs:__imp_EfsClientQueryProtectors
0x180013d92  mov     ebx, eax
0x180013d94  test    eax, eax
0x180013d96  jle     short loc_180013DA1
0x180013d98  movzx   ebx, ax
0x180013d9b  or      ebx, 80070000h
0x180013da1  mov     rcx, [rsp+28h+arg_10]
0x180013da6  test    ebx, ebx
0x180013da8  js      short loc_180013DD7
0x180013daa  lea     r8, [rsp+28h+arg_8]
0x180013daf  mov     [rsp+28h+arg_8], 1
0x180013db4  mov     rdx, 0FFFFFFFFFFFFFFFAh
0x180013dbb  call    cs:__imp_EdpIsFileAccessAllowed
0x180013dc1  mov     rcx, [rsp+28h+arg_10]
0x180013dc6  mov     ebx, eax
0x180013dc8  test    eax, eax
0x180013dca  js      short loc_180013DD7
0x180013dcc  xor     eax, eax
0x180013dce  cmp     [rsp+28h+arg_8], al
0x180013dd2  setnz   al
0x180013dd5  mov     [rsi], eax
0x180013dd7  test    rcx, rcx
0x180013dda  jz      short loc_180013DE2
0x180013ddc  call    cs:__imp_EfsClientFreeProtectorList
0x180013de2  mov     rsi, [rsp+28h+arg_18]
0x180013de7  mov     eax, ebx
0x180013de9  mov     rbx, [rsp+28h+arg_0]
0x180013dee  add     rsp, 20h
0x180013df2  pop     rdi
0x180013df3  retn
```
