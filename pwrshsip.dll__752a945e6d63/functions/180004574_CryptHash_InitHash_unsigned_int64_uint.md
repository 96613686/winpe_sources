# CryptHash::InitHash(unsigned __int64,uint)

- ea: `0x180004574`
- end: `0x180004647`
- name: `?InitHash@CryptHash@@QEAAK_KI@Z`
- size: `211`
- prototype: `unsigned int __fastcall(HCRYPTHASH *phHash, HCRYPTPROV hProv, ALG_ID Algid)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003d50`

## callees

- `0x180001008`
- `0x180001014`
- `0x180004574`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180004603`
- `KERNEL32!GetLastError` at `0x180004626`
- `KERNEL32!GetLastError` at `0x180004603`
- `KERNEL32!GetLastError` at `0x180004626`
- `ADVAPI32!CryptGetProvParam` at `0x1800045cb`
- `ADVAPI32!CryptGetProvParam` at `0x1800045f9`
- `ADVAPI32!CryptGetProvParam` at `0x1800045cb`
- `ADVAPI32!CryptGetProvParam` at `0x1800045f9`
- `ADVAPI32!CryptCreateHash` at `0x1800045a5`
- `ADVAPI32!CryptCreateHash` at `0x1800045a5`

## pseudocode

```c
DWORD __fastcall CryptHash::InitHash(HCRYPTHASH *phHash, HCRYPTPROV hProv, ALG_ID Algid)
{
  char v5; // bl
  BYTE *v6; // rdi
  DWORD i; // eax
  DWORD pdwDataLen; // [rsp+68h] [rbp+10h] BYREF

  if ( !hProv || !Algid )
    return 87;
  if ( CryptCreateHash(hProv, Algid, 0, 0, phHash) )
    return 0;
  v5 = 1;
  pdwDataLen = 0;
  if ( !CryptGetProvParam(hProv, 1u, 0, &pdwDataLen, 1u) )
    return -2146893816;
  v6 = (BYTE *)operator new(pdwDataLen);
  if ( !v6 )
    return -2146893816;
  for ( i = 1; CryptGetProvParam(hProv, 1u, v6, &pdwDataLen, i) || GetLastError() != 259; i = 0 )
  {
    if ( *(_DWORD *)v6 == Algid )
      goto LABEL_12;
  }
  v5 = 0;
LABEL_12:
  operator delete(v6);
  if ( v5 )
    return GetLastError();
  else
    return -2146893816;
}

```

## disassembly

```asm
0x180004574  push    rbx
0x180004576  push    rbp
0x180004577  push    rsi
0x180004578  push    rdi
0x180004579  sub     rsp, 38h
0x18000457d  mov     esi, r8d
0x180004580  mov     rbp, rdx
0x180004583  test    rdx, rdx
0x180004586  jz      loc_180004639
0x18000458c  test    r8d, r8d
0x18000458f  jz      loc_180004639
0x180004595  mov     [rsp+58h+phHash], rcx; phHash
0x18000459a  xor     r9d, r9d; dwFlags
0x18000459d  mov     rcx, rbp; hProv
0x1800045a0  xor     r8d, r8d; hKey
0x1800045a3  mov     edx, esi; Algid
0x1800045a5  call    cs:__imp_CryptCreateHash
0x1800045ab  test    eax, eax
0x1800045ad  jnz     loc_180004635
0x1800045b3  lea     ebx, [rax+1]
0x1800045b6  mov     [rsp+58h+pdwDataLen], eax
0x1800045ba  mov     edx, ebx; dwParam
0x1800045bc  mov     dword ptr [rsp+58h+phHash], ebx; dwFlags
0x1800045c0  lea     r9, [rsp+58h+pdwDataLen]; pdwDataLen
0x1800045c5  xor     r8d, r8d; pbData
0x1800045c8  mov     rcx, rbp; hProv
0x1800045cb  call    cs:__imp_CryptGetProvParam
0x1800045d1  test    eax, eax
0x1800045d3  jz      short loc_18000462E
0x1800045d5  mov     ecx, [rsp+58h+pdwDataLen]; Size
0x1800045d9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800045de  mov     rdi, rax
0x1800045e1  test    rax, rax
0x1800045e4  jz      short loc_18000462E
0x1800045e6  mov     eax, ebx
0x1800045e8  lea     r9, [rsp+58h+pdwDataLen]; pdwDataLen
0x1800045ed  mov     dword ptr [rsp+58h+phHash], eax; dwFlags
0x1800045f1  mov     r8, rdi; pbData
0x1800045f4  mov     edx, ebx; dwParam
0x1800045f6  mov     rcx, rbp; hProv
0x1800045f9  call    cs:__imp_CryptGetProvParam
0x1800045ff  test    eax, eax
0x180004601  jnz     short loc_180004610
0x180004603  call    cs:__imp_GetLastError
0x180004609  cmp     eax, 103h
0x18000460e  jz      short loc_180004618
0x180004610  cmp     [rdi], esi
0x180004612  jz      short loc_18000461A
0x180004614  xor     eax, eax
0x180004616  jmp     short loc_1800045E8
0x180004618  xor     bl, bl
0x18000461a  mov     rcx, rdi; Block
0x18000461d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004622  test    bl, bl
0x180004624  jz      short loc_18000462E
0x180004626  call    cs:__imp_GetLastError
0x18000462c  jmp     short loc_18000463E
0x18000462e  mov     eax, 80090008h
0x180004633  jmp     short loc_18000463E
0x180004635  xor     eax, eax
0x180004637  jmp     short loc_18000463E
0x180004639  mov     eax, 57h ; 'W'
0x18000463e  add     rsp, 38h
0x180004642  pop     rdi
0x180004643  pop     rsi
0x180004644  pop     rbp
0x180004645  pop     rbx
0x180004646  retn
```
