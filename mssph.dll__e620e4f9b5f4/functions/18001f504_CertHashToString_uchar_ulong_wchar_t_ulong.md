# CertHashToString(uchar *,ulong,wchar_t * *,ulong *)

- ea: `0x18001f504`
- end: `0x18001f5ea`
- name: `?CertHashToString@@YAJPEAEKPEAPEA_WPEAK@Z`
- size: `230`
- prototype: `__int64 __fastcall(BYTE *pbBinary, DWORD cbBinary, wchar_t **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800219a0`

## callees

- `0x180005eb0`
- `0x18001f504`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18001f5a3`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18001f5a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f58b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f58b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f54b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f54b`
- `CRYPT32!CryptBinaryToStringW` at `0x18001f528`
- `CRYPT32!CryptBinaryToStringW` at `0x18001f56e`
- `CRYPT32!CryptBinaryToStringW` at `0x18001f528`
- `CRYPT32!CryptBinaryToStringW` at `0x18001f56e`

## pseudocode

```c
__int64 __fastcall CertHashToString(BYTE *pbBinary, DWORD cbBinary, wchar_t **a3, unsigned int *pcchString)
{
  wchar_t *v8; // rdi
  int Error; // ebx
  __int64 v10; // rsi
  __int64 i; // rbp
  wint_t v12; // ax

  if ( CryptBinaryToStringW(pbBinary, cbBinary, 4u, 0, pcchString) )
  {
    v8 = (wchar_t *)CoTaskMemAlloc(2LL * *pcchString);
    if ( !v8 )
      return (unsigned int)-2147024882;
    Error = 0;
  }
  else
  {
    v8 = 0;
    Error = ResultFromLastError();
    if ( Error < 0 )
      return (unsigned int)Error;
  }
  if ( CryptBinaryToStringW(pbBinary, cbBinary, 4u, v8, pcchString) || (Error = ResultFromLastError(), Error >= 0) )
  {
    v10 = 0;
    *a3 = v8;
    for ( i = 0; (unsigned int)i < *pcchString; i = (unsigned int)(i + 1) )
    {
      v12 = towupper(v8[i]);
      if ( (unsigned __int16)(v12 - 48) <= 9u || (unsigned __int16)(v12 - 65) <= 5u )
      {
        v8[v10] = v12;
        v10 = (unsigned int)(v10 + 1);
      }
    }
    v8[v10] = 0;
    *pcchString = v10 + 1;
  }
  else if ( v8 )
  {
    CoTaskMemFree(v8);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001f504  push    rbx
0x18001f506  push    rbp
0x18001f507  push    rsi
0x18001f508  push    rdi
0x18001f509  push    r14
0x18001f50b  push    r15
0x18001f50d  sub     rsp, 38h
0x18001f511  mov     r14, r9
0x18001f514  mov     [rsp+68h+pcchString], r9; pcchString
0x18001f519  xor     r9d, r9d; pszString
0x18001f51c  mov     r15, r8
0x18001f51f  mov     esi, edx
0x18001f521  mov     rbp, rcx
0x18001f524  lea     r8d, [r9+4]; dwFlags
0x18001f528  call    cs:__imp_CryptBinaryToStringW
0x18001f52e  test    eax, eax
0x18001f530  jnz     short loc_18001F545
0x18001f532  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001f537  xor     edi, edi
0x18001f539  mov     ebx, eax
0x18001f53b  test    eax, eax
0x18001f53d  js      loc_18001F5DB
0x18001f543  jmp     short loc_18001F55B
0x18001f545  mov     ecx, [r14]
0x18001f548  add     rcx, rcx; cb
0x18001f54b  call    cs:__imp_CoTaskMemAlloc
0x18001f551  mov     rdi, rax
0x18001f554  test    rax, rax
0x18001f557  jz      short loc_18001F5D6
0x18001f559  xor     ebx, ebx
0x18001f55b  mov     r9, rdi; pszString
0x18001f55e  mov     [rsp+68h+pcchString], r14; pcchString
0x18001f563  mov     r8d, 4; dwFlags
0x18001f569  mov     edx, esi; cbBinary
0x18001f56b  mov     rcx, rbp; pbBinary
0x18001f56e  call    cs:__imp_CryptBinaryToStringW
0x18001f574  test    eax, eax
0x18001f576  jnz     short loc_18001F593
0x18001f578  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001f57d  mov     ebx, eax
0x18001f57f  test    eax, eax
0x18001f581  jns     short loc_18001F593
0x18001f583  test    rdi, rdi
0x18001f586  jz      short loc_18001F5DB
0x18001f588  mov     rcx, rdi; pv
0x18001f58b  call    cs:__imp_CoTaskMemFree
0x18001f591  jmp     short loc_18001F5DB
0x18001f593  xor     esi, esi
0x18001f595  mov     [r15], rdi
0x18001f598  xor     ebp, ebp
0x18001f59a  cmp     [r14], esi
0x18001f59d  jbe     short loc_18001F5C8
0x18001f59f  movzx   ecx, word ptr [rdi+rbp*2]; C
0x18001f5a3  call    cs:__imp_towupper
0x18001f5a9  lea     ecx, [rax-30h]
0x18001f5ac  cmp     cx, 9
0x18001f5b0  jbe     short loc_18001F5BB
0x18001f5b2  lea     ecx, [rax-41h]
0x18001f5b5  cmp     cx, 5
0x18001f5b9  ja      short loc_18001F5C1
0x18001f5bb  mov     [rdi+rsi*2], ax
0x18001f5bf  inc     esi
0x18001f5c1  inc     ebp
0x18001f5c3  cmp     ebp, [r14]
0x18001f5c6  jb      short loc_18001F59F
0x18001f5c8  xor     eax, eax
0x18001f5ca  mov     [rdi+rsi*2], ax
0x18001f5ce  lea     eax, [rsi+1]
0x18001f5d1  mov     [r14], eax
0x18001f5d4  jmp     short loc_18001F5DB
0x18001f5d6  mov     ebx, 8007000Eh
0x18001f5db  mov     eax, ebx
0x18001f5dd  add     rsp, 38h
0x18001f5e1  pop     r15
0x18001f5e3  pop     r14
0x18001f5e5  pop     rdi
0x18001f5e6  pop     rsi
0x18001f5e7  pop     rbp
0x18001f5e8  pop     rbx
0x18001f5e9  retn
```
