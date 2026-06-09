# _GetProviderName

- ea: `0x180074a4c`
- end: `0x180074aef`
- name: `_GetProviderName`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006f048`

## callees

- `0x180013220`
- `0x180074a4c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074ad0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074ad0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180074a81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180074a81`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x180074a70`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x180074a9f`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x180074a70`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x180074a9f`

## pseudocode

```c
__int64 __fastcall GetProviderName(__int64 a1, unsigned __int16 *a2, __int64 a3)
{
  int IdentityProviderInfoByGUID; // ebx
  const unsigned __int16 **v6; // rax
  const unsigned __int16 **v7; // rdi
  unsigned int cb; // [rsp+60h] [rbp+18h] BYREF
  int cb_4; // [rsp+64h] [rbp+1Ch]

  cb_4 = HIDWORD(a3);
  *a2 = 0;
  cb = 0;
  IdentityProviderInfoByGUID = GetIdentityProviderInfoByGUID(a1, 0, &cb);
  if ( IdentityProviderInfoByGUID == 122 )
  {
    v6 = (const unsigned __int16 **)CoTaskMemAlloc(cb);
    v7 = v6;
    if ( !v6 )
    {
      LOWORD(IdentityProviderInfoByGUID) = 8;
      return (unsigned __int16)IdentityProviderInfoByGUID | 0x80070000;
    }
    IdentityProviderInfoByGUID = GetIdentityProviderInfoByGUID(a1, v6, &cb);
    if ( !IdentityProviderInfoByGUID )
    {
      IdentityProviderInfoByGUID = StringCchCopyW(a2, 0x100u, v7[1]);
      if ( (IdentityProviderInfoByGUID & 0x1FFF0000) == 0x70000 )
        IdentityProviderInfoByGUID = (unsigned __int16)IdentityProviderInfoByGUID;
    }
    CoTaskMemFree(v7);
  }
  if ( IdentityProviderInfoByGUID > 0 )
    return (unsigned __int16)IdentityProviderInfoByGUID | 0x80070000;
  return (unsigned int)IdentityProviderInfoByGUID;
}

```

## disassembly

```asm
0x180074a4c  mov     [rsp+cb], r8
0x180074a51  push    rbx
0x180074a52  push    rsi
0x180074a53  push    rdi
0x180074a54  push    r14
0x180074a56  sub     rsp, 28h
0x180074a5a  xor     eax, eax
0x180074a5c  lea     r8, [rsp+48h+cb]
0x180074a61  mov     [rdx], ax
0x180074a64  mov     r14, rdx
0x180074a67  xor     edx, edx
0x180074a69  mov     dword ptr [rsp+48h+cb], eax
0x180074a6d  mov     rsi, rcx
0x180074a70  call    cs:__imp_GetIdentityProviderInfoByGUID
0x180074a76  mov     ebx, eax
0x180074a78  cmp     eax, 7Ah ; 'z'
0x180074a7b  jnz     short loc_180074AD6
0x180074a7d  mov     ecx, dword ptr [rsp+48h+cb]; cb
0x180074a81  call    cs:__imp_CoTaskMemAlloc
0x180074a87  mov     rdi, rax
0x180074a8a  test    rax, rax
0x180074a8d  jnz     short loc_180074A94
0x180074a8f  lea     ebx, [rax+8]
0x180074a92  jmp     short loc_180074ADA
0x180074a94  lea     r8, [rsp+48h+cb]
0x180074a99  mov     rdx, rdi
0x180074a9c  mov     rcx, rsi
0x180074a9f  call    cs:__imp_GetIdentityProviderInfoByGUID
0x180074aa5  mov     ebx, eax
0x180074aa7  test    eax, eax
0x180074aa9  jnz     short loc_180074ACD
0x180074aab  mov     r8, [rdi+8]; unsigned __int16 *
0x180074aaf  mov     edx, 100h; unsigned __int64
0x180074ab4  mov     rcx, r14; unsigned __int16 *
0x180074ab7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180074abc  mov     ebx, eax
0x180074abe  and     eax, 1FFF0000h
0x180074ac3  cmp     eax, 70000h
0x180074ac8  jnz     short loc_180074ACD
0x180074aca  movzx   ebx, bx
0x180074acd  mov     rcx, rdi; pv
0x180074ad0  call    cs:__imp_CoTaskMemFree
0x180074ad6  test    ebx, ebx
0x180074ad8  jle     short loc_180074AE3
0x180074ada  movzx   ebx, bx
0x180074add  or      ebx, 80070000h
0x180074ae3  mov     eax, ebx
0x180074ae5  add     rsp, 28h
0x180074ae9  pop     r14
0x180074aeb  pop     rdi
0x180074aec  pop     rsi
0x180074aed  pop     rbx
0x180074aee  retn
```
