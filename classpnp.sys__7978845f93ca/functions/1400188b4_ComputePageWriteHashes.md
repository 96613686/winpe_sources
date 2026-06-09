# ComputePageWriteHashes

- ea: `0x1400188b4`
- end: `0x140018ae7`
- name: `ComputePageWriteHashes`
- size: `563`
- prototype: `void __fastcall(__int64, unsigned __int64, int, __int64, char, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002fb0`
- `0x14001ccb0`

## callees

- `0x1400188b4`
- `0x1400264d0`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400188fa`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400188fa`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140018ac9`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140018ac9`

## pseudocode

```c
void __fastcall ComputePageWriteHashes(__int64 a1, unsigned __int64 a2, int a3, __int64 a4, char a5, __int64 a6)
{
  __int64 v6; // rbp
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v10; // rcx
  __int64 *i; // rdx
  __int64 v12; // r9
  __int64 v13; // r11
  unsigned __int64 *j; // rdi
  unsigned __int64 v15; // r11
  _QWORD *v16; // r14
  int *v17; // r15
  int v18; // eax
  __int64 v19; // r11
  int v20; // r10d
  unsigned __int32 v21; // r9d
  __int64 v22; // [rsp+70h] [rbp+8h]

  v6 = a4;
  if ( *(_QWORD *)(a1 + 672) )
  {
    if ( a4 )
    {
      v10 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(a1 + 752);
      if ( v10 )
      {
        if ( ExAcquireRundownProtectionCacheAware(v10) )
        {
          for ( i = *(__int64 **)(a1 + 736); i; i = (__int64 *)*i )
          {
            v12 = *((unsigned int *)i + 6);
            if ( (_DWORD)v12 )
            {
              v13 = 0;
              for ( j = (unsigned __int64 *)(i + 4); j < (unsigned __int64 *)((char *)i + v12 + 32); j += 2 )
              {
                if ( a2 >= *j && a2 < j[1] + *j )
                {
                  if ( a3 )
                  {
                    v15 = (a2 + v13 - *j) >> 12;
                    v16 = (_QWORD *)(a6 + 48);
                    v22 = 0;
                    if ( a5 )
                      v16 = 0;
                    v17 = (int *)((char *)i + 4 * v15 + v12 + 32);
                    do
                    {
                      if ( a2 >= j[1] + *j )
                        break;
                      v18 = ComputePageHash(v6, v15);
                      if ( a5 )
                      {
                        *v17 = v18;
                      }
                      else
                      {
                        v20 = *v17;
                        if ( *v17 && v18 != v20 && v22 != *v16 )
                        {
                          v21 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 824), 1u);
                          *(_QWORD *)(32LL * (v21 % *(_DWORD *)(a1 + 820)) + *(_QWORD *)(a1 + 672)) = a2;
                          *(_QWORD *)(32LL * (v21 % *(_DWORD *)(a1 + 820)) + *(_QWORD *)(a1 + 672) + 8) = v19;
                          *(_DWORD *)(32LL * (v21 % *(_DWORD *)(a1 + 820)) + *(_QWORD *)(a1 + 672) + 16) = v20;
                          *(_DWORD *)(32LL * (v21 % *(_DWORD *)(a1 + 820)) + *(_QWORD *)(a1 + 672) + 20) = v18;
                          *(_QWORD *)(32LL * (v21 % *(_DWORD *)(a1 + 820)) + *(_QWORD *)(a1 + 672) + 24) = *v16;
                          v22 = *v16;
                        }
                      }
                      ++v17;
                      v6 += 4096;
                      a2 += 4096LL;
                      v15 = v19 + 1;
                      ++v16;
                      a3 -= 4096;
                    }
                    while ( a3 );
                  }
                  goto LABEL_28;
                }
                v13 += j[1];
              }
            }
          }
LABEL_28:
          ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 752));
        }
        else
        {
          _InterlockedIncrement((volatile signed __int32 *)(a1 + 816));
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1400188b4  push    rbx
0x1400188b6  push    rbp
0x1400188b7  push    rsi
0x1400188b8  push    rdi
0x1400188b9  push    r12
0x1400188bb  push    r13
0x1400188bd  push    r14
0x1400188bf  push    r15
0x1400188c1  sub     rsp, 28h
0x1400188c5  xor     r13d, r13d
0x1400188c8  mov     rbp, r9
0x1400188cb  mov     r12d, r8d
0x1400188ce  mov     rsi, rdx
0x1400188d1  mov     rbx, rcx
0x1400188d4  cmp     [rcx+2A0h], r13
0x1400188db  jz      loc_140018AD5
0x1400188e1  test    r9, r9
0x1400188e4  jz      loc_140018AD5
0x1400188ea  mov     rcx, [rcx+2F0h]; RunRefCacheAware
0x1400188f1  test    rcx, rcx
0x1400188f4  jz      loc_140018AD5
0x1400188fa  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x140018901  nop     dword ptr [rax+rax+00h]
0x140018906  test    al, al
0x140018908  jnz     short loc_140018916
0x14001890a  lock inc dword ptr [rbx+330h]
0x140018911  jmp     loc_140018AD5
0x140018916  mov     rdx, [rbx+2E0h]
0x14001891d  jmp     short loc_140018959
0x14001891f  mov     r9d, [rdx+18h]
0x140018923  test    r9d, r9d
0x140018926  jz      short loc_140018956
0x140018928  lea     r10, [r9+20h]
0x14001892c  mov     r11, r13
0x14001892f  add     r10, rdx
0x140018932  lea     rdi, [rdx+20h]
0x140018936  cmp     rdi, r10
0x140018939  jnb     short loc_140018956
0x14001893b  mov     rcx, [rdi]
0x14001893e  cmp     rsi, rcx
0x140018941  jb      short loc_14001894C
0x140018943  add     rcx, [rdi+8]
0x140018947  cmp     rsi, rcx
0x14001894a  jb      short loc_140018963
0x14001894c  add     r11, [rdi+8]
0x140018950  add     rdi, 10h
0x140018954  jmp     short loc_140018936
0x140018956  mov     rdx, [rdx]
0x140018959  test    rdx, rdx
0x14001895c  jnz     short loc_14001891F
0x14001895e  jmp     loc_140018AC2
0x140018963  test    r12d, r12d
0x140018966  jz      loc_140018AC2
0x14001896c  sub     r11, [rdi]
0x14001896f  lea     rcx, [rdx+r9]
0x140018973  mov     r14, [rsp+68h+arg_28]
0x14001897b  add     r11, rsi
0x14001897e  shr     r11, 0Ch
0x140018982  add     r14, 30h ; '0'
0x140018986  cmp     [rsp+68h+arg_20], r13b
0x14001898e  mov     [rsp+68h+arg_0], r13
0x140018993  cmovnz  r14, r13
0x140018997  lea     r15, [r11+8]
0x14001899b  lea     r15, [rcx+r15*4]
0x14001899f  mov     rax, [rdi]
0x1400189a2  add     rax, [rdi+8]
0x1400189a6  cmp     rsi, rax
0x1400189a9  jnb     loc_140018AC2
0x1400189af  mov     rdx, r11
0x1400189b2  mov     rcx, rbp
0x1400189b5  call    ComputePageHash
0x1400189ba  cmp     [rsp+68h+arg_20], 0
0x1400189c2  mov     r13d, eax
0x1400189c5  jz      short loc_1400189CF
0x1400189c7  mov     [r15], eax
0x1400189ca  jmp     loc_140018A9F
0x1400189cf  mov     r10d, [r15]
0x1400189d2  test    r10d, r10d
0x1400189d5  jz      loc_140018A9F
0x1400189db  cmp     r13d, r10d
0x1400189de  jz      loc_140018A9F
0x1400189e4  mov     rax, [rsp+68h+arg_0]
0x1400189e9  cmp     rax, [r14]
0x1400189ec  jz      loc_140018A9F
0x1400189f2  mov     r9d, 1
0x1400189f8  lock xadd [rbx+338h], r9d
0x140018a01  xor     edx, edx
0x140018a03  mov     eax, r9d
0x140018a06  div     dword ptr [rbx+334h]
0x140018a0c  mov     rax, [rbx+2A0h]
0x140018a13  mov     ecx, edx
0x140018a15  xor     edx, edx
0x140018a17  shl     rcx, 5
0x140018a1b  mov     [rcx+rax], rsi
0x140018a1f  mov     eax, r9d
0x140018a22  div     dword ptr [rbx+334h]
0x140018a28  mov     rax, [rbx+2A0h]
0x140018a2f  mov     ecx, edx
0x140018a31  xor     edx, edx
0x140018a33  shl     rcx, 5
0x140018a37  mov     [rcx+rax+8], r11
0x140018a3c  mov     eax, r9d
0x140018a3f  div     dword ptr [rbx+334h]
0x140018a45  mov     rcx, [rbx+2A0h]
0x140018a4c  mov     eax, r9d
0x140018a4f  mov     r8d, edx
0x140018a52  xor     edx, edx
0x140018a54  shl     r8, 5
0x140018a58  mov     [r8+rcx+10h], r10d
0x140018a5d  div     dword ptr [rbx+334h]
0x140018a63  mov     rcx, [rbx+2A0h]
0x140018a6a  mov     eax, r9d
0x140018a6d  mov     r8d, edx
0x140018a70  xor     edx, edx
0x140018a72  shl     r8, 5
0x140018a76  mov     [r8+rcx+14h], r13d
0x140018a7b  div     dword ptr [rbx+334h]
0x140018a81  mov     rax, [r14]
0x140018a84  mov     rcx, [rbx+2A0h]
0x140018a8b  mov     r8d, edx
0x140018a8e  shl     r8, 5
0x140018a92  mov     [r8+rcx+18h], rax
0x140018a97  mov     rax, [r14]
0x140018a9a  mov     [rsp+68h+arg_0], rax
0x140018a9f  mov     ecx, 1000h
0x140018aa4  add     r15, 4
0x140018aa8  add     rbp, rcx
0x140018aab  add     rsi, rcx
0x140018aae  inc     r11
0x140018ab1  add     r14, 8
0x140018ab5  add     r12d, 0FFFFF000h
0x140018abc  jnz     loc_14001899F
0x140018ac2  mov     rcx, [rbx+2F0h]; RunRefCacheAware
0x140018ac9  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140018ad0  nop     dword ptr [rax+rax+00h]
0x140018ad5  add     rsp, 28h
0x140018ad9  pop     r15
0x140018adb  pop     r14
0x140018add  pop     r13
0x140018adf  pop     r12
0x140018ae1  pop     rdi
0x140018ae2  pop     rsi
0x140018ae3  pop     rbp
0x140018ae4  pop     rbx
0x140018ae5  retn
```
