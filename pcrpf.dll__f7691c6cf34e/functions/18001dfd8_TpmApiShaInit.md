# TpmApiShaInit

- ea: `0x18001dfd8`
- end: `0x18001e091`
- name: `TpmApiShaInit`
- size: `185`
- prototype: `__int64 __fastcall(LPCWSTR pszAlgId, BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180029dec`

## callees

- `0x18001dbf8`
- `0x18001dfd8`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18001e045`
- `bcrypt!BCryptCreateHash` at `0x18001e045`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001e083`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001e083`

## pseudocode

```c
__int64 __fastcall TpmApiShaInit(LPCWSTR pszAlgId, BCRYPT_HASH_HANDLE *phHash, volatile signed __int64 *a3)
{
  int v5; // ebx
  int v6; // eax
  NTSTATUS Hash; // eax
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+58h] [rbp+10h] BYREF

  if ( !phHash )
    return (unsigned int)-2144796412;
  v5 = 0;
  hAlgorithm = 0;
  if ( *a3 )
    goto LABEL_6;
  v6 = TpmApiOpenAlgorithmProvider(&hAlgorithm, pszAlgId);
  if ( v6 < 0 )
  {
    v5 = v6 | 0x10000000;
    goto LABEL_6;
  }
  if ( !_InterlockedCompareExchange64(a3, (signed __int64)hAlgorithm, 0) )
  {
LABEL_6:
    if ( v5 < 0 )
      return (unsigned int)v5;
    goto LABEL_7;
  }
  BCryptCloseAlgorithmProvider(hAlgorithm, 0);
LABEL_7:
  Hash = BCryptCreateHash(*(BCRYPT_ALG_HANDLE *)a3, phHash, 0, 0, 0, 0, 0);
  if ( Hash < 0 )
    return (unsigned int)(Hash | 0x10000000);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001dfd8  mov     [rsp+arg_0], rbx
0x18001dfdd  mov     [rsp+arg_10], rsi
0x18001dfe2  push    rdi
0x18001dfe3  sub     rsp, 40h
0x18001dfe7  mov     rdi, r8
0x18001dfea  mov     rsi, rdx
0x18001dfed  test    rdx, rdx
0x18001dff0  jnz     short loc_18001DFF9
0x18001dff2  mov     ebx, 80290104h
0x18001dff7  jmp     short loc_18001E05B
0x18001dff9  xor     ebx, ebx
0x18001dffb  mov     [rsp+48h+hAlgorithm], rbx
0x18001e000  cmp     [r8], rbx
0x18001e003  jnz     short loc_18001E01C
0x18001e005  mov     rdx, rcx; pszAlgId
0x18001e008  lea     rcx, [rsp+48h+hAlgorithm]; phAlgorithm
0x18001e00d  call    ?TpmApiOpenAlgorithmProvider@@YAJPEAPEAXPEBG@Z; TpmApiOpenAlgorithmProvider(void * *,ushort const *)
0x18001e012  test    eax, eax
0x18001e014  jns     short loc_18001E06E
0x18001e016  mov     ebx, eax
0x18001e018  bts     ebx, 1Ch
0x18001e01c  test    ebx, ebx
0x18001e01e  js      short loc_18001E05B
0x18001e020  mov     rcx, [rdi]; hAlgorithm
0x18001e023  xor     r9d, r9d; cbHashObject
0x18001e026  mov     [rsp+48h+dwFlags], 0; dwFlags
0x18001e02e  xor     r8d, r8d; pbHashObject
0x18001e031  mov     [rsp+48h+cbSecret], 0; cbSecret
0x18001e039  mov     rdx, rsi; phHash
0x18001e03c  mov     [rsp+48h+pbSecret], 0; pbSecret
0x18001e045  call    cs:__imp_BCryptCreateHash
0x18001e04c  nop     dword ptr [rax+rax+00h]
0x18001e051  test    eax, eax
0x18001e053  jns     short loc_18001E05B
0x18001e055  mov     ebx, eax
0x18001e057  bts     ebx, 1Ch
0x18001e05b  mov     rsi, [rsp+48h+arg_10]
0x18001e060  mov     eax, ebx
0x18001e062  mov     rbx, [rsp+48h+arg_0]
0x18001e067  add     rsp, 40h
0x18001e06b  pop     rdi
0x18001e06c  retn
0x18001e06e  mov     rcx, [rsp+48h+hAlgorithm]
0x18001e073  xor     eax, eax
0x18001e075  lock cmpxchg [rdi], rcx
0x18001e07a  jz      short loc_18001E01C
0x18001e07c  mov     rcx, [rsp+48h+hAlgorithm]; hAlgorithm
0x18001e081  xor     edx, edx; dwFlags
0x18001e083  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18001e08a  nop     dword ptr [rax+rax+00h]
0x18001e08f  jmp     short loc_18001E020
```
