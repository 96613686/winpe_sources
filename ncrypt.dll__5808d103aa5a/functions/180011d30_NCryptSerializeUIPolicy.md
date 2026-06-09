# NCryptSerializeUIPolicy

- ea: `0x180011d30`
- end: `0x180011ef4`
- name: `NCryptSerializeUIPolicy`
- size: `452`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010c90`

## callees

- `0x18000e120`
- `0x180011d30`
- `0x18001f15d`
- `0x18001f175`

## string_xrefs

- `0x180011d87`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`

## pseudocode

```c
__int64 __fastcall NCryptSerializeUIPolicy(__int64 a1, _DWORD *a2, unsigned int a3, unsigned int *a4)
{
  unsigned int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // r15
  unsigned int v11; // eax
  __int64 v12; // rax
  unsigned int v13; // esi
  __int64 v14; // rdx
  __int64 v15; // rcx
  unsigned int v16; // r12d
  __int64 v17; // rcx
  unsigned int v18; // r15d
  char *v19; // rsi

  if ( !a1 || !a4 || a3 > 0x100000 )
    return (unsigned int)-2146893785;
  if ( *(_DWORD *)a1 != 1 )
  {
    v6 = -2146893783;
    v7 = 613;
    v8 = 2148073513LL;
LABEL_6:
    DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", v7);
    return v6;
  }
  v9 = *(_QWORD *)(a1 + 8);
  v10 = -1;
  v11 = 20;
  *a4 = 20;
  if ( v9 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)(v9 + 2 * v12) );
    v13 = 2 * v12 + 2;
    v11 = 2 * v12 + 22;
    *a4 = v11;
  }
  else
  {
    v13 = 0;
  }
  v14 = *(_QWORD *)(a1 + 16);
  if ( v14 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)(v14 + 2 * v15) );
    v16 = 2 * v15 + 2;
    v11 += v16;
    *a4 = v11;
  }
  else
  {
    v16 = 0;
  }
  v17 = *(_QWORD *)(a1 + 24);
  if ( v17 )
  {
    do
      ++v10;
    while ( *(_WORD *)(v17 + 2 * v10) );
    v18 = 2 * v10 + 2;
    v11 += v18;
    *a4 = v11;
  }
  else
  {
    v18 = 0;
  }
  if ( v11 > 0x100000 )
  {
    *a4 = 0;
    v6 = -2146893785;
    v7 = 624;
    v8 = 2148073511LL;
    goto LABEL_6;
  }
  v6 = 0;
  if ( a2 )
  {
    if ( a3 >= v11 )
    {
      memset_0(a2, 0, v11);
      if ( *(_DWORD *)a1 == 1 )
      {
        *a2 = 1;
        a2[1] = *(_DWORD *)(a1 + 4);
        if ( *(_QWORD *)(a1 + 8) )
        {
          a2[2] = v13;
          memcpy_0(a2 + 5, *(const void **)(a1 + 8), v13);
          v19 = (char *)a2 + (unsigned int)a2[2] + 20;
        }
        else
        {
          v19 = (char *)(a2 + 5);
        }
        if ( *(_QWORD *)(a1 + 16) )
        {
          a2[3] = v16;
          memcpy_0(v19, *(const void **)(a1 + 16), v16);
          v19 += (unsigned int)a2[3];
        }
        if ( *(_QWORD *)(a1 + 24) )
        {
          a2[4] = v18;
          memcpy_0(v19, *(const void **)(a1 + 24), v18);
        }
      }
      else
      {
        return (unsigned int)-2146893783;
      }
    }
    else
    {
      return (unsigned int)-2146893784;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180011d30  push    rbx
0x180011d32  push    rbp
0x180011d33  push    rsi
0x180011d34  push    rdi
0x180011d35  push    r12
0x180011d37  push    r13
0x180011d39  push    r14
0x180011d3b  push    r15
0x180011d3d  sub     rsp, 28h
0x180011d41  xor     r13d, r13d
0x180011d44  mov     r14, rdx
0x180011d47  mov     rdi, rcx
0x180011d4a  test    rcx, rcx
0x180011d4d  jz      loc_180011EDC
0x180011d53  test    r9, r9
0x180011d56  jz      loc_180011EDC
0x180011d5c  mov     r10d, 100000h
0x180011d62  cmp     r8d, r10d
0x180011d65  ja      loc_180011EDC
0x180011d6b  cmp     dword ptr [rcx], 1
0x180011d6e  jz      short loc_180011D98
0x180011d70  mov     ebx, 80090029h
0x180011d75  mov     r9d, 265h
0x180011d7b  mov     ecx, 80090029h
0x180011d80  lea     rdx, aStatus; "Status"
0x180011d87  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011d8e  call    DebugTraceError
0x180011d93  jmp     loc_180011EE1
0x180011d98  mov     rcx, [rcx+8]
0x180011d9c  or      r15, 0FFFFFFFFFFFFFFFFh
0x180011da0  mov     eax, 14h
0x180011da5  mov     [r9], eax
0x180011da8  test    rcx, rcx
0x180011dab  jz      short loc_180011DC9
0x180011dad  mov     rax, r15
0x180011db0  inc     rax
0x180011db3  cmp     [rcx+rax*2], r13w
0x180011db8  jnz     short loc_180011DB0
0x180011dba  lea     esi, ds:2[rax*2]
0x180011dc1  lea     eax, [rsi+14h]
0x180011dc4  mov     [r9], eax
0x180011dc7  jmp     short loc_180011DCC
0x180011dc9  mov     esi, r13d
0x180011dcc  mov     rdx, [rdi+10h]
0x180011dd0  test    rdx, rdx
0x180011dd3  jz      short loc_180011DF2
0x180011dd5  mov     rcx, r15
0x180011dd8  inc     rcx
0x180011ddb  cmp     [rdx+rcx*2], r13w
0x180011de0  jnz     short loc_180011DD8
0x180011de2  lea     r12d, ds:2[rcx*2]
0x180011dea  add     eax, r12d
0x180011ded  mov     [r9], eax
0x180011df0  jmp     short loc_180011DF5
0x180011df2  mov     r12d, r13d
0x180011df5  mov     rcx, [rdi+18h]
0x180011df9  test    rcx, rcx
0x180011dfc  jz      short loc_180011E18
0x180011dfe  inc     r15
0x180011e01  cmp     [rcx+r15*2], r13w
0x180011e06  jnz     short loc_180011DFE
0x180011e08  lea     r15d, ds:2[r15*2]
0x180011e10  add     eax, r15d
0x180011e13  mov     [r9], eax
0x180011e16  jmp     short loc_180011E1B
0x180011e18  mov     r15d, r13d
0x180011e1b  cmp     eax, r10d
0x180011e1e  jbe     short loc_180011E38
0x180011e20  mov     [r9], r13d
0x180011e23  mov     ebx, 80090027h
0x180011e28  mov     r9d, 270h
0x180011e2e  mov     ecx, 80090027h
0x180011e33  jmp     loc_180011D80
0x180011e38  mov     ebx, r13d
0x180011e3b  test    r14, r14
0x180011e3e  jz      loc_180011EE1
0x180011e44  cmp     r8d, eax
0x180011e47  jnb     short loc_180011E53
0x180011e49  mov     ebx, 80090028h
0x180011e4e  jmp     loc_180011EE1
0x180011e53  mov     r8d, eax; Size
0x180011e56  xor     edx, edx; Val
0x180011e58  mov     rcx, r14; void *
0x180011e5b  call    memset_0
0x180011e60  mov     ecx, [rdi]
0x180011e62  cmp     ecx, 1
0x180011e65  jz      short loc_180011E6E
0x180011e67  mov     ebx, 80090029h
0x180011e6c  jmp     short loc_180011EE1
0x180011e6e  mov     [r14], ecx
0x180011e71  lea     rbp, [r14+14h]
0x180011e75  mov     eax, [rdi+4]
0x180011e78  mov     [r14+4], eax
0x180011e7c  cmp     [rdi+8], r13
0x180011e80  jz      short loc_180011E9E
0x180011e82  mov     [r14+8], esi
0x180011e86  mov     rcx, rbp; void *
0x180011e89  mov     rdx, [rdi+8]; Src
0x180011e8d  mov     r8d, esi; Size
0x180011e90  call    memcpy_0
0x180011e95  mov     esi, [r14+8]
0x180011e99  add     rsi, rbp
0x180011e9c  jmp     short loc_180011EA1
0x180011e9e  mov     rsi, rbp
0x180011ea1  cmp     [rdi+10h], r13
0x180011ea5  jz      short loc_180011EC1
0x180011ea7  mov     [r14+0Ch], r12d
0x180011eab  mov     rcx, rsi; void *
0x180011eae  mov     rdx, [rdi+10h]; Src
0x180011eb2  mov     r8d, r12d; Size
0x180011eb5  call    memcpy_0
0x180011eba  mov     eax, [r14+0Ch]
0x180011ebe  add     rsi, rax
0x180011ec1  cmp     [rdi+18h], r13
0x180011ec5  jz      short loc_180011EE1
0x180011ec7  mov     [r14+10h], r15d
0x180011ecb  mov     rcx, rsi; void *
0x180011ece  mov     rdx, [rdi+18h]; Src
0x180011ed2  mov     r8d, r15d; Size
0x180011ed5  call    memcpy_0
0x180011eda  jmp     short loc_180011EE1
0x180011edc  mov     ebx, 80090027h
0x180011ee1  mov     eax, ebx
0x180011ee3  add     rsp, 28h
0x180011ee7  pop     r15
0x180011ee9  pop     r14
0x180011eeb  pop     r13
0x180011eed  pop     r12
0x180011eef  pop     rdi
0x180011ef0  pop     rsi
0x180011ef1  pop     rbp
0x180011ef2  pop     rbx
0x180011ef3  retn
```
