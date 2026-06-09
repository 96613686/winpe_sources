# NCryptOpenKeyProtector

- ea: `0x180008da0`
- end: `0x1800090ce`
- name: `NCryptOpenKeyProtector`
- size: `814`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800079cc`

## callees

- `0x180007b80`
- `0x180007d50`
- `0x180007df4`
- `0x180008da0`
- `0x180009cd0`
- `0x18000d02c`
- `0x18000e120`
- `0x18001f15d`
- `0x18001f175`
- `0x180020010`

## import_xrefs

- `bcrypt!BCryptResolveProviders` at `0x180008e50`
- `bcrypt!BCryptResolveProviders` at `0x180008e50`
- `bcrypt!BCryptFreeBuffer` at `0x180008f4f`
- `bcrypt!BCryptFreeBuffer` at `0x180008f4f`

## string_xrefs

- `0x180008f89`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\router.c`
- `0x180009009`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\router.c`
- `0x180009057`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\router.c`
- `0x18000909d`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\router.c`
- `0x1800090b4`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\router.c`

## pseudocode

```c
__int64 __fastcall NCryptOpenKeyProtector(_QWORD *a1, const WCHAR *a2, unsigned int a3)
{
  int v6; // edx
  int v7; // r8d
  PVOID *v8; // r10
  unsigned int v9; // eax
  unsigned int Provider; // ebx
  __int64 v11; // rax
  size_t v12; // rbx
  _QWORD *v13; // rax
  int v14; // edx
  int v15; // r8d
  _QWORD *v16; // rdi
  __int64 v17; // rdx
  int v18; // edx
  int v19; // r8d
  __int128 v20; // xmm1
  __int64 v21; // xmm0_8
  unsigned int v22; // eax
  __int64 v24; // r9
  __int64 v25; // rcx
  _OWORD v26[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+60h] [rbp-A0h]
  ULONG pcbBuffer; // [rsp+210h] [rbp+110h] BYREF
  PCRYPT_PROVIDER_REFS ppBuffer; // [rsp+228h] [rbp+128h] BYREF

  ppBuffer = 0;
  pcbBuffer = 0;
  memset_0(v26, 0, 0x188u);
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_qSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_a7f478cd9c5e3193055148dad9f0cbe0_Traceguids,
      (_DWORD)a1,
      (__int64)a2,
      a3);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 || !a2 || !*a2 )
  {
    Provider = -2146893785;
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        (unsigned int)v8[2],
        v6,
        v7,
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\router.c",
        105);
    goto LABEL_13;
  }
  *a1 = 0;
  v9 = BCryptResolveProviders(0, 0, a2, 0, 1u, 0, &pcbBuffer, &ppBuffer);
  Provider = v9;
  if ( v9 )
  {
    v24 = 127;
    v25 = v9;
LABEL_31:
    DebugTraceError(v25, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\router.c", v24);
    goto LABEL_13;
  }
  if ( **(_DWORD **)ppBuffer->rgpProviders != 65540 )
  {
    Provider = -1073741816;
    v24 = 137;
    v25 = 3221225480LL;
    goto LABEL_31;
  }
  v11 = -1;
  do
    ++v11;
  while ( a2[v11] );
  v12 = 2 * v11 + 2;
  v13 = (_QWORD *)SafeAllocaAllocateFromHeap(2 * v11 + 74);
  v16 = v13;
  if ( v13 )
  {
    memset_0(v13, 0, 0x48u);
    *(_DWORD *)v16 = 72;
    v16[8] = v16 + 9;
    *((_DWORD *)v16 + 1) = 1;
    memcpy_0(v16 + 9, a2, v12);
    Provider = LoadProviderEx(*ppBuffer->rgpProviders, v17, 0, v16 + 1, v26);
    if ( Provider )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v18,
          v19,
          (unsigned int)"Status",
          Provider,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\router.c",
          177);
    }
    else
    {
      v20 = v26[1];
      *((_OWORD *)v16 + 1) = v26[0];
      v21 = v27;
      *((_OWORD *)v16 + 2) = v20;
      v16[6] = v21;
      v22 = ((__int64 (__fastcall *)(_QWORD *, const WCHAR *, _QWORD))v16[3])(v16 + 7, a2, a3);
      Provider = v22;
      if ( !v22 )
      {
        *a1 = v16;
        Provider = 0;
        goto LABEL_13;
      }
      DebugTraceError(v22, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\router.c", 194);
    }
    NCryptCloseKeyProtector(v16);
  }
  else
  {
    Provider = -2146893810;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        v15,
        (unsigned int)"Status",
        14,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\router.c",
        152);
  }
LABEL_13:
  if ( ppBuffer )
    BCryptFreeBuffer(ppBuffer);
  return Provider;
}

```

## disassembly

```asm
0x180008da0  mov     [rsp-8+arg_8], rbx
0x180008da5  push    rbp
0x180008da6  push    rsi
0x180008da7  push    rdi
0x180008da8  push    r12
0x180008daa  push    r13
0x180008dac  push    r14
0x180008dae  push    r15
0x180008db0  lea     rbp, [rsp-0D0h]
0x180008db8  sub     rsp, 1D0h
0x180008dbf  xor     r13d, r13d
0x180008dc2  mov     r15d, r8d
0x180008dc5  mov     rsi, rdx
0x180008dc8  mov     [rbp+100h+arg_18], r13
0x180008dcf  mov     r14, rcx
0x180008dd2  mov     [rbp+100h+arg_0], r13d
0x180008dd9  xor     edx, edx; Val
0x180008ddb  lea     rcx, [rsp+200h+var_1C0]; void *
0x180008de0  mov     r8d, 188h; Size
0x180008de6  call    memset_0
0x180008deb  mov     r10, cs:WPP_GLOBAL_Control
0x180008df2  lea     r12, WPP_GLOBAL_Control
0x180008df9  cmp     r10, r12
0x180008dfc  jnz     loc_180008FB7
0x180008e02  test    r14, r14
0x180008e05  jz      loc_18000903E
0x180008e0b  test    rsi, rsi
0x180008e0e  jz      loc_18000903E
0x180008e14  cmp     r13w, [rsi]
0x180008e18  jz      loc_18000903E
0x180008e1e  lea     rax, [rbp+100h+arg_18]
0x180008e25  mov     [r14], r13
0x180008e28  mov     [rsp+200h+ppBuffer], rax; ppBuffer
0x180008e2d  xor     r9d, r9d; pszProvider
0x180008e30  lea     rax, [rbp+100h+arg_0]
0x180008e37  mov     r8, rsi; pszFunction
0x180008e3a  mov     [rsp+200h+pcbBuffer], rax; pcbBuffer
0x180008e3f  xor     edx, edx; dwInterface
0x180008e41  mov     [rsp+200h+dwFlags], r13d; dwFlags
0x180008e46  xor     ecx, ecx; pszContext
0x180008e48  mov     [rsp+200h+dwMode], 1; dwMode
0x180008e50  call    cs:__imp_BCryptResolveProviders
0x180008e56  mov     ebx, eax
0x180008e58  test    eax, eax
0x180008e5a  jnz     loc_18000907C
0x180008e60  mov     rax, [rbp+100h+arg_18]
0x180008e67  mov     rcx, [rax+8]
0x180008e6b  mov     rax, [rcx]
0x180008e6e  cmp     dword ptr [rax], 10004h
0x180008e74  jnz     loc_180009086
0x180008e7a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008e7e  inc     rax
0x180008e81  cmp     [rsi+rax*2], r13w
0x180008e86  jnz     short loc_180008E7E
0x180008e88  lea     rbx, ds:2[rax*2]
0x180008e90  lea     rcx, [rbx+48h]
0x180008e94  call    SafeAllocaAllocateFromHeap
0x180008e99  mov     rdi, rax
0x180008e9c  test    rax, rax
0x180008e9f  jz      loc_180008F72
0x180008ea5  mov     r12d, 48h ; 'H'
0x180008eab  xor     edx, edx; Val
0x180008ead  mov     r8d, r12d; Size
0x180008eb0  mov     rcx, rax; void *
0x180008eb3  call    memset_0
0x180008eb8  lea     rcx, [rdi+48h]; void *
0x180008ebc  mov     [rdi], r12d
0x180008ebf  mov     r8, rbx; Size
0x180008ec2  mov     [rdi+40h], rcx
0x180008ec6  mov     rdx, rsi; Src
0x180008ec9  mov     dword ptr [rdi+4], 1
0x180008ed0  call    memcpy_0
0x180008ed5  mov     rax, [rbp+100h+arg_18]
0x180008edc  lea     r9, [rdi+8]
0x180008ee0  xor     r8d, r8d
0x180008ee3  mov     rcx, [rax+8]
0x180008ee7  lea     rax, [rsp+200h+var_1C0]
0x180008eec  mov     qword ptr [rsp+200h+dwMode], rax
0x180008ef1  mov     rcx, [rcx]
0x180008ef4  call    LoadProviderEx
0x180008ef9  mov     ebx, eax
0x180008efb  test    eax, eax
0x180008efd  jnz     loc_180008FF0
0x180008f03  movaps  xmm0, [rsp+200h+var_1C0]
0x180008f08  lea     rcx, [rdi+38h]
0x180008f0c  movaps  xmm1, [rsp+200h+var_1B0]
0x180008f11  mov     r8d, r15d
0x180008f14  movups  xmmword ptr [rdi+10h], xmm0
0x180008f18  mov     rdx, rsi
0x180008f1b  movsd   xmm0, [rsp+200h+var_1A0]
0x180008f21  movups  xmmword ptr [rdi+20h], xmm1
0x180008f25  movsd   qword ptr [rdi+30h], xmm0
0x180008f2a  mov     rax, [rdi+18h]
0x180008f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f33  mov     ebx, eax
0x180008f35  test    eax, eax
0x180008f37  jnz     loc_1800090AE
0x180008f3d  mov     [r14], rdi
0x180008f40  mov     ebx, r13d
0x180008f43  mov     rcx, [rbp+100h+arg_18]; pvBuffer
0x180008f4a  test    rcx, rcx
0x180008f4d  jz      short loc_180008F55
0x180008f4f  call    cs:__imp_BCryptFreeBuffer
0x180008f55  mov     eax, ebx
0x180008f57  mov     rbx, [rsp+200h+arg_8]
0x180008f5f  add     rsp, 1D0h
0x180008f66  pop     r15
0x180008f68  pop     r14
0x180008f6a  pop     r13
0x180008f6c  pop     r12
0x180008f6e  pop     rdi
0x180008f6f  pop     rsi
0x180008f70  pop     rbp
0x180008f71  retn
0x180008f72  mov     ebx, 8009000Eh
0x180008f77  mov     rax, cs:WPP_GLOBAL_Control
0x180008f7e  cmp     rax, r12
0x180008f81  jz      short loc_180008F43
0x180008f83  test    byte ptr [rax+1Ch], 1
0x180008f87  jz      short loc_180008F43
0x180008f89  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008f90  mov     dword ptr [rsp+200h+pcbBuffer], 98h
0x180008f98  mov     qword ptr [rsp+200h+dwFlags], rcx
0x180008f9d  mov     rcx, [rax+10h]
0x180008fa1  mov     [rsp+200h+dwMode], 8009000Eh
0x180008fa9  lea     r9, aStatus; "Status"
0x180008fb0  call    WPP_SF_sDsd
0x180008fb5  jmp     short loc_180008F43
0x180008fb7  test    byte ptr [r10+1Ch], 4
0x180008fbc  jz      loc_180008E02
0x180008fc2  mov     rcx, [r10+10h]
0x180008fc6  lea     r8, WPP_a7f478cd9c5e3193055148dad9f0cbe0_Traceguids
0x180008fcd  mov     edx, 0Ah
0x180008fd2  mov     [rsp+200h+dwFlags], r15d
0x180008fd7  mov     r9, r14
0x180008fda  mov     qword ptr [rsp+200h+dwMode], rsi
0x180008fdf  call    WPP_SF_qSD
0x180008fe4  mov     r10, cs:WPP_GLOBAL_Control
0x180008feb  jmp     loc_180008E02
0x180008ff0  mov     rax, cs:WPP_GLOBAL_Control
0x180008ff7  lea     rcx, WPP_GLOBAL_Control
0x180008ffe  cmp     rax, rcx
0x180009001  jz      short loc_180009031
0x180009003  test    byte ptr [rax+1Ch], 1
0x180009007  jz      short loc_180009031
0x180009009  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009010  mov     dword ptr [rsp+200h+pcbBuffer], 0B1h
0x180009018  mov     qword ptr [rsp+200h+dwFlags], rcx
0x18000901d  lea     r9, aStatus; "Status"
0x180009024  mov     rcx, [rax+10h]
0x180009028  mov     [rsp+200h+dwMode], ebx
0x18000902c  call    WPP_SF_sDsd
0x180009031  mov     rcx, rdi
0x180009034  call    NCryptCloseKeyProtector
0x180009039  jmp     loc_180008F43
0x18000903e  mov     ebx, 80090027h
0x180009043  cmp     r10, r12
0x180009046  jz      loc_180008F43
0x18000904c  test    byte ptr [r10+1Ch], 1
0x180009051  jz      loc_180008F43
0x180009057  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000905e  mov     dword ptr [rsp+200h+pcbBuffer], 69h ; 'i'
0x180009066  mov     qword ptr [rsp+200h+dwFlags], rcx
0x18000906b  mov     rcx, [r10+10h]
0x18000906f  mov     [rsp+200h+dwMode], 80090027h
0x180009077  jmp     loc_180008FA9
0x18000907c  mov     r9d, 7Fh
0x180009082  mov     ecx, eax
0x180009084  jmp     short loc_180009096
0x180009086  mov     ebx, 0C0000008h
0x18000908b  mov     r9d, 89h
0x180009091  mov     ecx, 0C0000008h
0x180009096  lea     rdx, aStatus; "Status"
0x18000909d  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800090a4  call    DebugTraceError
0x1800090a9  jmp     loc_180008F43
0x1800090ae  mov     r9d, 0C2h
0x1800090b4  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800090bb  lea     rdx, aStatus; "Status"
0x1800090c2  mov     ecx, eax
0x1800090c4  call    DebugTraceError
0x1800090c9  jmp     loc_180009031
```
