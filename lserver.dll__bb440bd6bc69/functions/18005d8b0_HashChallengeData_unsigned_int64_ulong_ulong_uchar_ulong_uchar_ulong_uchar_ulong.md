# HashChallengeData(unsigned __int64,ulong,ulong,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x18005d8b0`
- end: `0x18005daa5`
- name: `?HashChallengeData@@YAK_KKKPEAEK1KPEAPEAEPEAK@Z`
- size: `501`
- prototype: `__int64 __fastcall(HCRYPTPROV, int, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, DWORD pdwDataLen, unsigned __int8 **, unsigned int *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800106c0`
- `0x18005db70`
- `0x18005def4`

## callees

- `0x18005d8b0`

## import_xrefs

- `ADVAPI32!CryptCreateHash` at `0x18005d920`
- `ADVAPI32!CryptCreateHash` at `0x18005d920`
- `ADVAPI32!CryptHashData` at `0x18005d954`
- `ADVAPI32!CryptHashData` at `0x18005d988`
- `ADVAPI32!CryptHashData` at `0x18005d9ad`
- `ADVAPI32!CryptHashData` at `0x18005d954`
- `ADVAPI32!CryptHashData` at `0x18005d988`
- `ADVAPI32!CryptHashData` at `0x18005d9ad`
- `ADVAPI32!CryptDestroyHash` at `0x18005da4f`
- `ADVAPI32!CryptDestroyHash` at `0x18005da4f`
- `ADVAPI32!CryptGetHashParam` at `0x18005d9d1`
- `ADVAPI32!CryptGetHashParam` at `0x18005da21`
- `ADVAPI32!CryptGetHashParam` at `0x18005d9d1`
- `ADVAPI32!CryptGetHashParam` at `0x18005da21`
- `KERNEL32!GetLastError` at `0x18005d9e1`
- `KERNEL32!GetLastError` at `0x18005da31`
- `KERNEL32!GetLastError` at `0x18005d9e1`
- `KERNEL32!GetLastError` at `0x18005da31`
- `KERNEL32!LocalAlloc` at `0x18005d9fc`
- `KERNEL32!LocalAlloc` at `0x18005d9fc`
- `KERNEL32!LocalFree` at `0x18005da79`
- `KERNEL32!LocalFree` at `0x18005da79`

## pseudocode

```c
__int64 __fastcall HashChallengeData(
        HCRYPTPROV a1,
        int a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        DWORD pdwDataLen,
        unsigned __int8 **a8,
        unsigned int *a9)
{
  DWORD LastError; // ebx
  __int64 v10; // r14
  BYTE *v11; // rdi
  unsigned int v14; // esi
  const BYTE *v15; // rdx
  BYTE *v16; // rax
  unsigned int *v17; // rcx
  HCRYPTHASH hHash; // [rsp+60h] [rbp+30h] BYREF

  LastError = 0;
  v10 = a3;
  hHash = 0;
  v11 = 0;
  pdwDataLen = 0;
  if ( a1 && a4 && (v14 = a5, a5 - 1 <= 0x3F) && a5 >= a3 )
  {
    if ( !CryptCreateHash(a1, 0x8003u, 0, 0, &hHash) || !CryptHashData(hHash, a4, v10, 0) )
      goto LABEL_15;
    v15 = (const BYTE *)L"d46b4bf2-686d-11d2-96ae-00c04fa3080d";
    if ( a2 != 2 )
      v15 = L"d63a773e-6799-11d2-96ae-00c04fa3080d";
    if ( !CryptHashData(hHash, v15, 0x48u, 0)
      || !CryptHashData(hHash, &a4[v10], v14 - v10, 0)
      || !CryptGetHashParam(hHash, 2u, 0, &pdwDataLen, 0) && GetLastError() != 234
      || (v16 = (BYTE *)LocalAlloc(0x40u, pdwDataLen), (v11 = v16) == 0)
      || !CryptGetHashParam(hHash, 2u, v16, &pdwDataLen, 0) )
    {
LABEL_15:
      LastError = GetLastError();
    }
  }
  else
  {
    LastError = 87;
  }
  if ( hHash )
    CryptDestroyHash(hHash);
  if ( LastError )
  {
    if ( v11 )
      LocalFree(v11);
  }
  else
  {
    v17 = a9;
    *a8 = v11;
    *v17 = pdwDataLen;
  }
  return LastError;
}

```

## disassembly

```asm
0x18005d8b0  mov     r11, rsp
0x18005d8b3  mov     [r11+10h], rbx
0x18005d8b7  mov     [r11+18h], rsi
0x18005d8bb  mov     [r11+20h], rdi
0x18005d8bf  push    rbp
0x18005d8c0  push    r12
0x18005d8c2  push    r13
0x18005d8c4  push    r14
0x18005d8c6  push    r15
0x18005d8c8  mov     rbp, rsp
0x18005d8cb  sub     rsp, 30h
0x18005d8cf  xor     ebx, ebx
0x18005d8d1  mov     r14d, r8d
0x18005d8d4  and     [rbp+hHash], rbx
0x18005d8d8  xor     edi, edi
0x18005d8da  and     [rbp+pdwDataLen], ebx
0x18005d8dd  mov     r15, r9
0x18005d8e0  mov     r13d, edx
0x18005d8e3  test    rcx, rcx
0x18005d8e6  jz      loc_18005DA41
0x18005d8ec  test    r9, r9
0x18005d8ef  jz      loc_18005DA41
0x18005d8f5  mov     esi, [rbp+arg_20]
0x18005d8f8  lea     eax, [rsi-1]
0x18005d8fb  cmp     eax, 3Fh ; '?'
0x18005d8fe  ja      loc_18005DA41
0x18005d904  cmp     esi, r14d
0x18005d907  jb      loc_18005DA41
0x18005d90d  lea     rax, [rbp+hHash]
0x18005d911  xor     r9d, r9d; dwFlags
0x18005d914  xor     r8d, r8d; hKey
0x18005d917  mov     [r11-38h], rax
0x18005d91b  mov     edx, 8003h; Algid
0x18005d920  call    cs:__imp_CryptCreateHash
0x18005d927  nop     dword ptr [rax+rax+00h]
0x18005d92c  test    eax, eax
0x18005d92e  jz      loc_18005DA31
0x18005d934  mov     r12d, cs:dwDataLen
0x18005d93b  cmp     r13d, 2
0x18005d93f  mov     rcx, [rbp+hHash]; hHash
0x18005d943  mov     r8d, r14d; dwDataLen
0x18005d946  cmovz   r12d, cs:dwDataLen
0x18005d94e  mov     rdx, r15; pbData
0x18005d951  xor     r9d, r9d; dwFlags
0x18005d954  call    cs:__imp_CryptHashData
0x18005d95b  nop     dword ptr [rax+rax+00h]
0x18005d960  test    eax, eax
0x18005d962  jz      loc_18005DA31
0x18005d968  mov     rcx, [rbp+hHash]; hHash
0x18005d96c  lea     rax, pbData; "d63a773e-6799-11d2-96ae-00c04fa3080d"
0x18005d973  cmp     r13d, 2
0x18005d977  lea     rdx, aD46b4bf2686d11; "d46b4bf2-686d-11d2-96ae-00c04fa3080d"
0x18005d97e  mov     r8d, r12d; dwDataLen
0x18005d981  cmovnz  rdx, rax; pbData
0x18005d985  xor     r9d, r9d; dwFlags
0x18005d988  call    cs:__imp_CryptHashData
0x18005d98f  nop     dword ptr [rax+rax+00h]
0x18005d994  test    eax, eax
0x18005d996  jz      loc_18005DA31
0x18005d99c  mov     rcx, [rbp+hHash]; hHash
0x18005d9a0  lea     rdx, [r15+r14]; pbData
0x18005d9a4  sub     esi, r14d
0x18005d9a7  xor     r9d, r9d; dwFlags
0x18005d9aa  mov     r8d, esi; dwDataLen
0x18005d9ad  call    cs:__imp_CryptHashData
0x18005d9b4  nop     dword ptr [rax+rax+00h]
0x18005d9b9  test    eax, eax
0x18005d9bb  jz      short loc_18005DA31
0x18005d9bd  mov     rcx, [rbp+hHash]; hHash
0x18005d9c1  lea     esi, [rbx+2]
0x18005d9c4  and     [rsp+30h+var_10], ebx
0x18005d9c8  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x18005d9cc  mov     edx, esi; dwParam
0x18005d9ce  xor     r8d, r8d; pbData
0x18005d9d1  call    cs:__imp_CryptGetHashParam
0x18005d9d8  nop     dword ptr [rax+rax+00h]
0x18005d9dd  test    eax, eax
0x18005d9df  jnz     short loc_18005D9F4
0x18005d9e1  call    cs:__imp_GetLastError
0x18005d9e8  nop     dword ptr [rax+rax+00h]
0x18005d9ed  cmp     eax, 0EAh
0x18005d9f2  jnz     short loc_18005DA31
0x18005d9f4  mov     edx, [rbp+pdwDataLen]; uBytes
0x18005d9f7  mov     ecx, 40h ; '@'; uFlags
0x18005d9fc  call    cs:__imp_LocalAlloc
0x18005da03  nop     dword ptr [rax+rax+00h]
0x18005da08  mov     rdi, rax
0x18005da0b  test    rax, rax
0x18005da0e  jz      short loc_18005DA31
0x18005da10  mov     rcx, [rbp+hHash]; hHash
0x18005da14  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x18005da18  and     [rsp+30h+var_10], ebx
0x18005da1c  mov     r8, rax; pbData
0x18005da1f  mov     edx, esi; dwParam
0x18005da21  call    cs:__imp_CryptGetHashParam
0x18005da28  nop     dword ptr [rax+rax+00h]
0x18005da2d  test    eax, eax
0x18005da2f  jnz     short loc_18005DA46
0x18005da31  call    cs:__imp_GetLastError
0x18005da38  nop     dword ptr [rax+rax+00h]
0x18005da3d  mov     ebx, eax
0x18005da3f  jmp     short loc_18005DA46
0x18005da41  mov     ebx, 57h ; 'W'
0x18005da46  mov     rcx, [rbp+hHash]; hHash
0x18005da4a  test    rcx, rcx
0x18005da4d  jz      short loc_18005DA5B
0x18005da4f  call    cs:__imp_CryptDestroyHash
0x18005da56  nop     dword ptr [rax+rax+00h]
0x18005da5b  test    ebx, ebx
0x18005da5d  jnz     short loc_18005DA71
0x18005da5f  mov     rax, [rbp+arg_38]
0x18005da63  mov     rcx, [rbp+arg_40]
0x18005da67  mov     [rax], rdi
0x18005da6a  mov     eax, [rbp+pdwDataLen]
0x18005da6d  mov     [rcx], eax
0x18005da6f  jmp     short loc_18005DA85
0x18005da71  test    rdi, rdi
0x18005da74  jz      short loc_18005DA85
0x18005da76  mov     rcx, rdi; hMem
0x18005da79  call    cs:__imp_LocalFree
0x18005da80  nop     dword ptr [rax+rax+00h]
0x18005da85  mov     rsi, [rsp+30h+arg_10]
0x18005da8a  mov     eax, ebx
0x18005da8c  mov     rbx, [rsp+30h+arg_8]
0x18005da91  mov     rdi, [rsp+30h+arg_18]
0x18005da96  add     rsp, 30h
0x18005da9a  pop     r15
0x18005da9c  pop     r14
0x18005da9e  pop     r13
0x18005daa0  pop     r12
0x18005daa2  pop     rbp
0x18005daa3  retn
```
