# CachedAdapterInformation::operator=(CachedAdapterInformation &&)

- ea: `0x140006ec0`
- end: `0x140006fd0`
- name: `??4CachedAdapterInformation@@QEAAAEAU0@$$QEAU0@@Z`
- size: `272`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x14000893c`

## callees

- `0x140002578`
- `0x140006ec0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006ee1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006ee1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006ef4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006ef4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006eec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006eec`

## pseudocode

```c
__int64 __fastcall CachedAdapterInformation::operator=(__int64 a1, __int64 *a2)
{
  HKEY v4; // rbp
  __int64 v5; // r14
  DWORD LastError; // ebx
  _OWORD *v7; // r14
  char **v8; // rbx
  unsigned __int64 v9; // rdx
  char *v10; // rax
  char *v11; // rcx

  if ( (__int64 *)a1 != a2 )
  {
    v4 = *(HKEY *)a1;
    v5 = *a2;
    if ( *(_QWORD *)a1 )
    {
      LastError = GetLastError();
      RegCloseKey(v4);
      SetLastError(LastError);
    }
    *(_QWORD *)a1 = v5;
    *a2 = 0;
  }
  v7 = a2 + 5;
  *(_QWORD *)(a1 + 8) = a2[1];
  v8 = (char **)(a1 + 40);
  *(_QWORD *)(a1 + 16) = a2[2];
  *(_QWORD *)(a1 + 24) = a2[3];
  *(_DWORD *)(a1 + 32) = *((_DWORD *)a2 + 8);
  if ( (__int64 *)(a1 + 40) != a2 + 5 )
  {
    v9 = *(_QWORD *)(a1 + 64);
    if ( v9 > 7 )
    {
      v10 = *v8;
      if ( 2 * v9 + 2 < 0x1000 )
      {
        v11 = *v8;
      }
      else
      {
        v11 = (char *)*((_QWORD *)v10 - 1);
        if ( (unsigned __int64)(v10 - v11 - 8) > 0x1F )
          __fastfail(5u);
      }
      operator delete(v11);
    }
    *(_QWORD *)(a1 + 56) = 0;
    *(_WORD *)v8 = 0;
    *(_QWORD *)(a1 + 64) = 7;
    *(_OWORD *)v8 = *v7;
    *(_OWORD *)(a1 + 56) = *(_OWORD *)(a2 + 7);
    a2[7] = 0;
    a2[8] = 7;
    *(_WORD *)v7 = 0;
  }
  *(_QWORD *)(a1 + 72) = a2[9];
  *(_QWORD *)(a1 + 80) = a2[10];
  *(_QWORD *)(a1 + 88) = a2[11];
  *(_DWORD *)(a1 + 96) = *((_DWORD *)a2 + 24);
  return a1;
}

```

## disassembly

```asm
0x140006ec0  push    rbx
0x140006ec2  push    rbp
0x140006ec3  push    rsi
0x140006ec4  push    rdi
0x140006ec5  push    r14
0x140006ec7  sub     rsp, 20h
0x140006ecb  mov     rsi, rdx
0x140006ece  mov     rdi, rcx
0x140006ed1  cmp     rcx, rdx
0x140006ed4  jz      short loc_140006F04
0x140006ed6  mov     rbp, [rcx]
0x140006ed9  mov     r14, [rdx]
0x140006edc  test    rbp, rbp
0x140006edf  jz      short loc_140006EFA
0x140006ee1  call    cs:__imp_GetLastError
0x140006ee7  mov     rcx, rbp; hKey
0x140006eea  mov     ebx, eax
0x140006eec  call    cs:__imp_RegCloseKey
0x140006ef2  mov     ecx, ebx; dwErrCode
0x140006ef4  call    cs:__imp_SetLastError
0x140006efa  mov     [rdi], r14
0x140006efd  mov     qword ptr [rsi], 0
0x140006f04  mov     rax, [rsi+8]
0x140006f08  lea     r14, [rsi+28h]
0x140006f0c  mov     [rdi+8], rax
0x140006f10  lea     rbx, [rdi+28h]
0x140006f14  mov     rax, [rsi+10h]
0x140006f18  mov     [rdi+10h], rax
0x140006f1c  mov     rax, [rsi+18h]
0x140006f20  mov     [rdi+18h], rax
0x140006f24  mov     eax, [rsi+20h]
0x140006f27  mov     [rdi+20h], eax
0x140006f2a  cmp     rbx, r14
0x140006f2d  jz      short loc_140006FA4
0x140006f2f  mov     rdx, [rbx+18h]
0x140006f33  mov     ebp, 7
0x140006f38  cmp     rdx, rbp
0x140006f3b  jbe     short loc_140006F77
0x140006f3d  mov     rax, [rbx]
0x140006f40  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x140006f48  cmp     rdx, 1000h
0x140006f4f  jb      short loc_140006F6F
0x140006f51  mov     rcx, [rax-8]
0x140006f55  sub     rax, rcx
0x140006f58  sub     rax, 8
0x140006f5c  cmp     rax, 1Fh
0x140006f60  ja      short loc_140006F68
0x140006f62  add     rdx, 27h ; '''
0x140006f66  jmp     short loc_140006F72
0x140006f68  mov     ecx, 5
0x140006f6d  int     29h; Win8: RtlFailFast(ecx)
0x140006f6f  mov     rcx, rax; void *
0x140006f72  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140006f77  mov     qword ptr [rbx+10h], 0
0x140006f7f  xor     eax, eax
0x140006f81  mov     [rbx], ax
0x140006f84  mov     [rbx+18h], rbp
0x140006f88  movups  xmm0, xmmword ptr [r14]
0x140006f8c  movups  xmmword ptr [rbx], xmm0
0x140006f8f  movups  xmm1, xmmword ptr [r14+10h]
0x140006f94  movups  xmmword ptr [rbx+10h], xmm1
0x140006f98  mov     [r14+10h], rax
0x140006f9c  mov     [r14+18h], rbp
0x140006fa0  mov     [r14], ax
0x140006fa4  mov     rax, [rsi+48h]
0x140006fa8  mov     [rdi+48h], rax
0x140006fac  mov     rax, [rsi+50h]
0x140006fb0  mov     [rdi+50h], rax
0x140006fb4  mov     rax, [rsi+58h]
0x140006fb8  mov     [rdi+58h], rax
0x140006fbc  mov     eax, [rsi+60h]
0x140006fbf  mov     [rdi+60h], eax
0x140006fc2  mov     rax, rdi
0x140006fc5  add     rsp, 20h
0x140006fc9  pop     r14
0x140006fcb  pop     rdi
0x140006fcc  pop     rsi
0x140006fcd  pop     rbp
0x140006fce  pop     rbx
0x140006fcf  retn
```
