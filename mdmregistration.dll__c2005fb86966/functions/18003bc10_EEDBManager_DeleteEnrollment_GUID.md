# EEDBManager::DeleteEnrollment(_GUID)

- ea: `0x18003bc10`
- end: `0x18003bdbf`
- name: `?DeleteEnrollment@EEDBManager@@UEAAJU_GUID@@@Z`
- size: `431`
- prototype: `int(EEDBManager *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800026d0`
- `0x18000bd7c`
- `0x18003bc10`
- `0x18003cd7c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003bd8e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003bd8e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003bc51`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003bc51`

## pseudocode

```c
__int64 __fastcall EEDBManager::DeleteEnrollment(EEDBManager *this, struct _GUID *a2)
{
  __int64 v2; // rcx
  OLECHAR *p_sz; // rax
  unsigned int v4; // ebx
  __int64 v5; // rax
  char *v6; // rcx
  __int64 v7; // rdx
  _WORD *v8; // r8
  _WORD *v9; // rcx
  __int64 v10; // rcx
  _WORD *v11; // rax
  __int64 v12; // rdx
  const unsigned __int16 *EnrollmentsRootKey; // rax
  _WORD v16[40]; // [rsp+30h] [rbp-D0h] BYREF
  OLECHAR sz; // [rsp+80h] [rbp-80h] BYREF
  char v18; // [rsp+82h] [rbp-7Eh] BYREF
  WCHAR SubKey[264]; // [rsp+D0h] [rbp-30h] BYREF

  SubKey[0] = 0;
  v16[0] = 0;
  sz = 0;
  if ( StringFromGUID2(a2, &sz, 39) != 39 )
    return (unsigned int)-2147418113;
  v2 = 39;
  p_sz = &sz;
  do
  {
    if ( !*p_sz )
      break;
    ++p_sz;
    --v2;
  }
  while ( v2 );
  v4 = v2 == 0 ? 0x80070057 : 0;
  if ( v2 )
  {
    if ( (unsigned __int64)(37 - v2) > 0x24 )
      return (unsigned int)-2147418113;
    v5 = 2147483646;
    v6 = &v18;
    v7 = 39;
    v8 = v16;
    do
    {
      if ( !v5 )
        break;
      if ( !*(_WORD *)v6 )
        break;
      *v8 = *(_WORD *)v6;
      v6 += 2;
      ++v8;
      --v5;
      --v7;
    }
    while ( v7 );
    v9 = v8 - 1;
    v4 = v7 == 0 ? 0x8007007A : 0;
    if ( v7 )
      v9 = v8;
    *v9 = 0;
    if ( v7 )
    {
      v10 = 39;
      v11 = v16;
      do
      {
        if ( !*v11 )
          break;
        ++v11;
        --v10;
      }
      while ( v10 );
      v4 = v10 == 0 ? 0x80070057 : 0;
      v12 = (39 - v10) & ((unsigned __int128)-(__int128)(unsigned __int64)v10 >> 64);
      if ( v10 )
      {
        if ( (unsigned __int64)(v12 - 2) <= 0x24 )
        {
          v16[v12 - 1] = 0;
          EnrollmentsRootKey = EEDBManager::GetEnrollmentsRootKey();
          v4 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", EnrollmentsRootKey, v16);
          if ( (v4 & 0x80000000) == 0 )
            RegDeleteTreeW(HKEY_LOCAL_MACHINE, SubKey);
          return v4;
        }
        return (unsigned int)-2147418113;
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18003bc10  push    rbp
0x18003bc12  push    rbx
0x18003bc13  push    rsi
0x18003bc14  push    rdi
0x18003bc15  lea     rbp, [rsp-1F8h]
0x18003bc1d  sub     rsp, 2F8h
0x18003bc24  mov     rax, cs:__security_cookie
0x18003bc2b  xor     rax, rsp
0x18003bc2e  mov     [rbp+210h+var_30], rax
0x18003bc35  xor     esi, esi
0x18003bc37  mov     rcx, rdx; rguid
0x18003bc3a  lea     rdx, [rbp+210h+sz]; lpsz
0x18003bc3e  mov     [rbp+210h+SubKey], si
0x18003bc42  mov     [rsp+310h+var_2E0], si
0x18003bc47  mov     [rbp+210h+sz], si
0x18003bc4b  lea     edi, [rsi+27h]
0x18003bc4e  mov     r8d, edi; cchMax
0x18003bc51  call    cs:__imp_StringFromGUID2
0x18003bc58  nop     dword ptr [rax+rax+00h]
0x18003bc5d  cmp     eax, edi
0x18003bc5f  jnz     loc_18003BD9C
0x18003bc65  mov     ecx, edi
0x18003bc67  lea     rax, [rbp+210h+sz]
0x18003bc6b  cmp     [rax], si
0x18003bc6e  jz      short loc_18003BC7A
0x18003bc70  add     rax, 2
0x18003bc74  sub     rcx, 1
0x18003bc78  jnz     short loc_18003BC6B
0x18003bc7a  mov     rax, rcx
0x18003bc7d  mov     r10d, 80070057h
0x18003bc83  neg     rax
0x18003bc86  sbb     ebx, ebx
0x18003bc88  not     ebx
0x18003bc8a  and     ebx, r10d
0x18003bc8d  test    rcx, rcx
0x18003bc90  jz      loc_18003BDA1
0x18003bc96  mov     eax, 25h ; '%'
0x18003bc9b  mov     rdx, 0FFFFFFFFFFFFFFFEh
0x18003bca2  sub     rax, rcx
0x18003bca5  test    rcx, rcx
0x18003bca8  cmovz   rax, rdx
0x18003bcac  cmp     rax, 24h ; '$'
0x18003bcb0  ja      loc_18003BD9C
0x18003bcb6  mov     eax, 7FFFFFFEh
0x18003bcbb  lea     rcx, [rbp+210h+var_28E]
0x18003bcbf  mov     rdx, rdi
0x18003bcc2  lea     r8, [rsp+310h+var_2E0]
0x18003bcc7  test    rax, rax
0x18003bcca  jz      short loc_18003BCEB
0x18003bccc  movzx   r9d, word ptr [rcx]
0x18003bcd0  test    r9w, r9w
0x18003bcd4  jz      short loc_18003BCEB
0x18003bcd6  mov     [r8], r9w
0x18003bcda  add     rcx, 2
0x18003bcde  add     r8, 2
0x18003bce2  dec     rax
0x18003bce5  sub     rdx, 1
0x18003bce9  jnz     short loc_18003BCC7
0x18003bceb  mov     rax, rdx
0x18003bcee  lea     rcx, [r8-2]
0x18003bcf2  neg     rax
0x18003bcf5  sbb     ebx, ebx
0x18003bcf7  not     ebx
0x18003bcf9  and     ebx, 8007007Ah
0x18003bcff  test    rdx, rdx
0x18003bd02  cmovnz  rcx, r8
0x18003bd06  mov     [rcx], si
0x18003bd09  jz      loc_18003BDA1
0x18003bd0f  mov     rcx, rdi
0x18003bd12  lea     rax, [rsp+310h+var_2E0]
0x18003bd17  cmp     [rax], si
0x18003bd1a  jz      short loc_18003BD26
0x18003bd1c  add     rax, 2
0x18003bd20  sub     rcx, 1
0x18003bd24  jnz     short loc_18003BD17
0x18003bd26  mov     rax, rcx
0x18003bd29  neg     rax
0x18003bd2c  mov     rax, rcx
0x18003bd2f  sbb     ebx, ebx
0x18003bd31  sub     rdi, rcx
0x18003bd34  not     ebx
0x18003bd36  and     ebx, r10d
0x18003bd39  neg     rax
0x18003bd3c  sbb     rdx, rdx
0x18003bd3f  and     rdx, rdi
0x18003bd42  test    rcx, rcx
0x18003bd45  jz      short loc_18003BDA1
0x18003bd47  lea     rax, [rdx-2]
0x18003bd4b  cmp     rax, 24h ; '$'
0x18003bd4f  ja      short loc_18003BD9C
0x18003bd51  mov     [rsp+rdx*2+310h+var_2E2], si
0x18003bd56  call    ?GetEnrollmentsRootKey@EEDBManager@@SAPEBGXZ; EEDBManager::GetEnrollmentsRootKey(void)
0x18003bd5b  mov     r9, rax
0x18003bd5e  lea     r8, aSS; "%s\\%s"
0x18003bd65  lea     rax, [rsp+310h+var_2E0]
0x18003bd6a  mov     edx, 104h; unsigned __int64
0x18003bd6f  lea     rcx, [rbp+210h+SubKey]; unsigned __int16 *
0x18003bd73  mov     [rsp+310h+var_2F0], rax
0x18003bd78  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003bd7d  mov     ebx, eax
0x18003bd7f  test    eax, eax
0x18003bd81  js      short loc_18003BDA1
0x18003bd83  lea     rdx, [rbp+210h+SubKey]; lpSubKey
0x18003bd87  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003bd8e  call    cs:__imp_RegDeleteTreeW
0x18003bd95  nop     dword ptr [rax+rax+00h]
0x18003bd9a  jmp     short loc_18003BDA1
0x18003bd9c  mov     ebx, 8000FFFFh
0x18003bda1  mov     eax, ebx
0x18003bda3  mov     rcx, [rbp+210h+var_30]
0x18003bdaa  xor     rcx, rsp; StackCookie
0x18003bdad  call    __security_check_cookie
0x18003bdb2  add     rsp, 2F8h
0x18003bdb9  pop     rdi
0x18003bdba  pop     rsi
0x18003bdbb  pop     rbx
0x18003bdbc  pop     rbp
0x18003bdbd  retn
```
