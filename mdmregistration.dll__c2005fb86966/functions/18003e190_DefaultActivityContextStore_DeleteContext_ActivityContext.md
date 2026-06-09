# DefaultActivityContextStore::DeleteContext(ActivityContext &)

- ea: `0x18003e190`
- end: `0x18003e34c`
- name: `?DeleteContext@DefaultActivityContextStore@@UEAAJAEAVActivityContext@@@Z`
- size: `444`
- prototype: `__int64 __fastcall(DefaultActivityContextStore *__hidden this, struct ActivityContext *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800026d0`
- `0x18000bd7c`
- `0x18003cd7c`
- `0x18003e190`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003e31b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003e31b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003e1d2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003e1d2`

## pseudocode

```c
__int64 __fastcall DefaultActivityContextStore::DeleteContext(
        DefaultActivityContextStore *this,
        struct ActivityContext *a2)
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
  if ( StringFromGUID2((const GUID *const)((char *)a2 + 8), &sz, 39) != 39 )
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
          v4 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s\\%s", EnrollmentsRootKey, L"Context", v16);
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
0x18003e190  push    rbp
0x18003e192  push    rbx
0x18003e193  push    rsi
0x18003e194  push    rdi
0x18003e195  lea     rbp, [rsp-1F8h]
0x18003e19d  sub     rsp, 2F8h
0x18003e1a4  mov     rax, cs:__security_cookie
0x18003e1ab  xor     rax, rsp
0x18003e1ae  mov     [rbp+210h+var_30], rax
0x18003e1b5  xor     esi, esi
0x18003e1b7  lea     rcx, [rdx+8]; rguid
0x18003e1bb  lea     rdx, [rbp+210h+sz]; lpsz
0x18003e1bf  mov     [rbp+210h+SubKey], si
0x18003e1c3  mov     [rsp+310h+var_2E0], si
0x18003e1c8  mov     [rbp+210h+sz], si
0x18003e1cc  lea     edi, [rsi+27h]
0x18003e1cf  mov     r8d, edi; cchMax
0x18003e1d2  call    cs:__imp_StringFromGUID2
0x18003e1d9  nop     dword ptr [rax+rax+00h]
0x18003e1de  cmp     eax, edi
0x18003e1e0  jnz     loc_18003E329
0x18003e1e6  mov     ecx, edi
0x18003e1e8  lea     rax, [rbp+210h+sz]
0x18003e1ec  cmp     [rax], si
0x18003e1ef  jz      short loc_18003E1FB
0x18003e1f1  add     rax, 2
0x18003e1f5  sub     rcx, 1
0x18003e1f9  jnz     short loc_18003E1EC
0x18003e1fb  mov     rax, rcx
0x18003e1fe  mov     r10d, 80070057h
0x18003e204  neg     rax
0x18003e207  sbb     ebx, ebx
0x18003e209  not     ebx
0x18003e20b  and     ebx, r10d
0x18003e20e  test    rcx, rcx
0x18003e211  jz      loc_18003E32E
0x18003e217  mov     eax, 25h ; '%'
0x18003e21c  mov     rdx, 0FFFFFFFFFFFFFFFEh
0x18003e223  sub     rax, rcx
0x18003e226  test    rcx, rcx
0x18003e229  cmovz   rax, rdx
0x18003e22d  cmp     rax, 24h ; '$'
0x18003e231  ja      loc_18003E329
0x18003e237  mov     eax, 7FFFFFFEh
0x18003e23c  lea     rcx, [rbp+210h+var_28E]
0x18003e240  mov     rdx, rdi
0x18003e243  lea     r8, [rsp+310h+var_2E0]
0x18003e248  test    rax, rax
0x18003e24b  jz      short loc_18003E26C
0x18003e24d  movzx   r9d, word ptr [rcx]
0x18003e251  test    r9w, r9w
0x18003e255  jz      short loc_18003E26C
0x18003e257  mov     [r8], r9w
0x18003e25b  add     rcx, 2
0x18003e25f  add     r8, 2
0x18003e263  dec     rax
0x18003e266  sub     rdx, 1
0x18003e26a  jnz     short loc_18003E248
0x18003e26c  mov     rax, rdx
0x18003e26f  lea     rcx, [r8-2]
0x18003e273  neg     rax
0x18003e276  sbb     ebx, ebx
0x18003e278  not     ebx
0x18003e27a  and     ebx, 8007007Ah
0x18003e280  test    rdx, rdx
0x18003e283  cmovnz  rcx, r8
0x18003e287  mov     [rcx], si
0x18003e28a  jz      loc_18003E32E
0x18003e290  mov     rcx, rdi
0x18003e293  lea     rax, [rsp+310h+var_2E0]
0x18003e298  cmp     [rax], si
0x18003e29b  jz      short loc_18003E2A7
0x18003e29d  add     rax, 2
0x18003e2a1  sub     rcx, 1
0x18003e2a5  jnz     short loc_18003E298
0x18003e2a7  mov     rax, rcx
0x18003e2aa  neg     rax
0x18003e2ad  mov     rax, rcx
0x18003e2b0  sbb     ebx, ebx
0x18003e2b2  sub     rdi, rcx
0x18003e2b5  not     ebx
0x18003e2b7  and     ebx, r10d
0x18003e2ba  neg     rax
0x18003e2bd  sbb     rdx, rdx
0x18003e2c0  and     rdx, rdi
0x18003e2c3  test    rcx, rcx
0x18003e2c6  jz      short loc_18003E32E
0x18003e2c8  lea     rax, [rdx-2]
0x18003e2cc  cmp     rax, 24h ; '$'
0x18003e2d0  ja      short loc_18003E329
0x18003e2d2  mov     [rsp+rdx*2+310h+var_2E2], si
0x18003e2d7  call    ?GetEnrollmentsRootKey@EEDBManager@@SAPEBGXZ; EEDBManager::GetEnrollmentsRootKey(void)
0x18003e2dc  lea     rcx, [rsp+310h+var_2E0]
0x18003e2e1  mov     r9, rax
0x18003e2e4  mov     [rsp+28h], rcx
0x18003e2e9  lea     r8, aSSS; "%s\\%s\\%s"
0x18003e2f0  lea     rcx, aContext_0; "Context"
0x18003e2f7  mov     edx, 104h; unsigned __int64
0x18003e2fc  mov     [rsp+310h+var_2F0], rcx
0x18003e301  lea     rcx, [rbp+210h+SubKey]; unsigned __int16 *
0x18003e305  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003e30a  mov     ebx, eax
0x18003e30c  test    eax, eax
0x18003e30e  js      short loc_18003E32E
0x18003e310  lea     rdx, [rbp+210h+SubKey]; lpSubKey
0x18003e314  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003e31b  call    cs:__imp_RegDeleteTreeW
0x18003e322  nop     dword ptr [rax+rax+00h]
0x18003e327  jmp     short loc_18003E32E
0x18003e329  mov     ebx, 8000FFFFh
0x18003e32e  mov     eax, ebx
0x18003e330  mov     rcx, [rbp+210h+var_30]
0x18003e337  xor     rcx, rsp; StackCookie
0x18003e33a  call    __security_check_cookie
0x18003e33f  add     rsp, 2F8h
0x18003e346  pop     rdi
0x18003e347  pop     rsi
0x18003e348  pop     rbx
0x18003e349  pop     rbp
0x18003e34a  retn
```
