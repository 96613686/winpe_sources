# FwppDeepCopyToVerIndependent_IPSEC_SA_TRANSFORM0

- ea: `0x180012180`
- end: `0x180012338`
- name: `FwppDeepCopyToVerIndependent_IPSEC_SA_TRANSFORM0`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180025c64`

## callees

- `0x180006e40`
- `0x180007e38`
- `0x180011500`
- `0x180012180`
- `0x180012340`
- `0x1800123cc`
- `0x180023bd8`
- `0x1800343a0`
- `0x180035474`
- `0x1800372b4`
- `0x180037760`

## string_xrefs

- `0x180012271`: `FwppAllocAndDeepCopyToVerIndependent_IPSEC_AUTH_AND_CIPHER_TRANSFORM0`
- `0x1800122d6`: `FwppAllocAndDeepCopyToVerIndependent_IPSEC_CIPHER_TRANSFORM0`
- `0x1800122f1`: `FwppDeepCopyToVerIndependent_IPSEC_SA_TRANSFORM0`
- `0x180012312`: `FwppDeepCopyToVerIndependent_IPSEC_SA_TRANSFORM0`

## pseudocode

```c
__int64 __fastcall FwppDeepCopyToVerIndependent_IPSEC_SA_TRANSFORM0(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // rbp
  _QWORD *v7; // r14
  const char *v8; // rdx
  __int64 v9; // rbp

  if ( !a1 || !a2 )
  {
    v4 = WfpReportSysErrorAsNtStatus(a1, "FwppDeepCopyToVerIndependent_IPSEC_SA_TRANSFORM0", 3223453724LL);
LABEL_26:
    if ( !v4 )
      return v4;
LABEL_27:
    FwppDeepFreeContentsOnly_IPSEC_SA_TRANSFORM0(a2);
    WfpReportError(v4, "FwppDeepCopyToVerIndependent_IPSEC_SA_TRANSFORM0");
    return v4;
  }
  v4 = FwppDeepCopyToVerIndependent_IPSEC_TRANSFORM_TYPE();
  if ( v4 )
    goto LABEL_27;
  switch ( *(_DWORD *)a1 )
  {
    case 1:
    case 2:
      goto LABEL_9;
    case 3:
      v9 = *(_QWORD *)(a1 + 8);
      if ( !v9 )
        return v4;
      v7 = (_QWORD *)(a2 + 8);
      if ( a2 != -8 )
      {
        v4 = WfpPoolAllocNonPaged(0x10u);
        if ( !v4 )
        {
          MEMORY[0] = 0;
          v4 = FwppDeepCopyToVerIndependent_IPSEC_CIPHER_TRANSFORM0(v9, 0);
          if ( !v4 )
            goto LABEL_16;
        }
        FwppDeepFree_IPSEC_AUTH_TRANSFORM0(0);
        v8 = "FwppAllocAndDeepCopyToVerIndependent_IPSEC_CIPHER_TRANSFORM0";
LABEL_23:
        WfpReportError(v4, v8);
        goto LABEL_27;
      }
      goto LABEL_24;
    case 4:
      v6 = *(_QWORD *)(a1 + 8);
      if ( !v6 )
        return v4;
      v7 = (_QWORD *)(a2 + 8);
      if ( a2 != -8 )
      {
        v4 = WfpPoolAllocNonPaged(0x20u);
        if ( !v4 )
        {
          MEMORY[0] = 0;
          MEMORY[0x10] = 0;
          v4 = FwppDeepCopyToVerIndependent_IPSEC_AUTH_AND_CIPHER_TRANSFORM0(v6, 0);
          if ( !v4 )
          {
LABEL_16:
            *v7 = 0;
            return v4;
          }
        }
        FwppDeepFree_IPSEC_AUTH_AND_CIPHER_TRANSFORM0(0);
        v8 = "FwppAllocAndDeepCopyToVerIndependent_IPSEC_AUTH_AND_CIPHER_TRANSFORM0";
        goto LABEL_23;
      }
LABEL_24:
      v4 = 0;
      goto LABEL_26;
  }
  if ( *(_DWORD *)a1 != 5 )
    return v4;
LABEL_9:
  v5 = *(_QWORD *)(a1 + 8);
  if ( v5 )
  {
    v4 = FwppAllocAndDeepCopyToVerIndependent_IPSEC_AUTH_TRANSFORM0(v5, a2 + 8);
    if ( v4 )
      goto LABEL_27;
  }
  return v4;
}

```

## disassembly

```asm
0x180012180  mov     [rsp+arg_8], rbx
0x180012185  mov     [rsp+arg_10], rbp
0x18001218a  push    rsi
0x18001218b  push    rdi
0x18001218c  push    r14
0x18001218e  sub     rsp, 20h
0x180012192  mov     rsi, rdx
0x180012195  mov     rdi, rcx
0x180012198  test    rcx, rcx
0x18001219b  jz      loc_1800122EB
0x1800121a1  test    rdx, rdx
0x1800121a4  jz      loc_1800122EB
0x1800121aa  call    FwppDeepCopyToVerIndependent_IPSEC_TRANSFORM_TYPE
0x1800121af  mov     rbx, rax
0x1800121b2  test    rax, rax
0x1800121b5  jnz     loc_180012305
0x1800121bb  mov     eax, [rdi]
0x1800121bd  sub     eax, 1
0x1800121c0  jz      short loc_1800121DE
0x1800121c2  sub     eax, 1
0x1800121c5  jz      short loc_1800121DE
0x1800121c7  sub     eax, 1
0x1800121ca  jz      loc_18001227A
0x1800121d0  sub     eax, 1
0x1800121d3  jz      short loc_180012205
0x1800121d5  cmp     eax, 1
0x1800121d8  jnz     loc_180012321
0x1800121de  mov     rcx, [rdi+8]
0x1800121e2  test    rcx, rcx
0x1800121e5  jz      loc_180012321
0x1800121eb  lea     rdx, [rsi+8]
0x1800121ef  call    FwppAllocAndDeepCopyToVerIndependent_IPSEC_AUTH_TRANSFORM0
0x1800121f4  mov     rbx, rax
0x1800121f7  test    rax, rax
0x1800121fa  jnz     loc_180012305
0x180012200  jmp     loc_180012321
0x180012205  mov     rbp, [rdi+8]
0x180012209  test    rbp, rbp
0x18001220c  jz      loc_180012321
0x180012212  lea     r14, [rsi+8]
0x180012216  mov     [rsp+38h+arg_0], 0
0x18001221f  test    r14, r14
0x180012222  jz      loc_1800122E7
0x180012228  lea     r8, [rsp+38h+arg_0]
0x18001222d  mov     ecx, 20h ; ' '; dwBytes
0x180012232  call    WfpPoolAllocNonPaged
0x180012237  mov     rdi, [rsp+38h+arg_0]
0x18001223c  mov     rbx, rax
0x18001223f  test    rax, rax
0x180012242  jnz     short loc_180012269
0x180012244  xorps   xmm0, xmm0
0x180012247  mov     rdx, rdi
0x18001224a  movups  xmmword ptr [rdi], xmm0
0x18001224d  mov     rcx, rbp
0x180012250  movups  xmmword ptr [rdi+10h], xmm0
0x180012254  call    FwppDeepCopyToVerIndependent_IPSEC_AUTH_AND_CIPHER_TRANSFORM0
0x180012259  mov     rbx, rax
0x18001225c  test    rax, rax
0x18001225f  jnz     short loc_180012269
0x180012261  mov     [r14], rdi
0x180012264  jmp     loc_180012321
0x180012269  mov     rcx, rdi
0x18001226c  call    FwppDeepFree_IPSEC_AUTH_AND_CIPHER_TRANSFORM0
0x180012271  lea     rdx, aFwppallocandde_100; "FwppAllocAndDeepCopyToVerIndependent_IP"...
0x180012278  jmp     short loc_1800122DD
0x18001227a  mov     rbp, [rdi+8]
0x18001227e  test    rbp, rbp
0x180012281  jz      loc_180012321
0x180012287  lea     r14, [rsi+8]
0x18001228b  mov     [rsp+38h+arg_0], 0
0x180012294  test    r14, r14
0x180012297  jz      short loc_1800122E7
0x180012299  lea     r8, [rsp+38h+arg_0]
0x18001229e  mov     ecx, 10h; dwBytes
0x1800122a3  call    WfpPoolAllocNonPaged
0x1800122a8  mov     rdi, [rsp+38h+arg_0]
0x1800122ad  mov     rbx, rax
0x1800122b0  test    rax, rax
0x1800122b3  jnz     short loc_1800122CE
0x1800122b5  xorps   xmm0, xmm0
0x1800122b8  mov     rdx, rdi
0x1800122bb  mov     rcx, rbp
0x1800122be  movups  xmmword ptr [rdi], xmm0
0x1800122c1  call    FwppDeepCopyToVerIndependent_IPSEC_CIPHER_TRANSFORM0
0x1800122c6  mov     rbx, rax
0x1800122c9  test    rax, rax
0x1800122cc  jz      short loc_180012261
0x1800122ce  mov     rcx, rdi
0x1800122d1  call    FwppDeepFree_IPSEC_AUTH_TRANSFORM0
0x1800122d6  lea     rdx, aFwppallocandde_62; "FwppAllocAndDeepCopyToVerIndependent_IP"...
0x1800122dd  mov     rcx, rbx
0x1800122e0  call    WfpReportError
0x1800122e5  jmp     short loc_180012305
0x1800122e7  xor     ebx, ebx
0x1800122e9  jmp     short loc_180012300
0x1800122eb  mov     r8d, 0C022001Ch
0x1800122f1  lea     rdx, aFwppdeepcopyto_69; "FwppDeepCopyToVerIndependent_IPSEC_SA_T"...
0x1800122f8  call    WfpReportSysErrorAsNtStatus
0x1800122fd  mov     rbx, rax
0x180012300  test    rbx, rbx
0x180012303  jz      short loc_180012321
0x180012305  mov     rcx, rsi
0x180012308  call    FwppDeepFreeContentsOnly_IPSEC_SA_TRANSFORM0
0x18001230d  test    rbx, rbx
0x180012310  jz      short loc_180012321
0x180012312  lea     rdx, aFwppdeepcopyto_69; "FwppDeepCopyToVerIndependent_IPSEC_SA_T"...
0x180012319  mov     rcx, rbx
0x18001231c  call    WfpReportError
0x180012321  mov     rbp, [rsp+38h+arg_10]
0x180012326  mov     rax, rbx
0x180012329  mov     rbx, [rsp+38h+arg_8]
0x18001232e  add     rsp, 20h
0x180012332  pop     r14
0x180012334  pop     rdi
0x180012335  pop     rsi
0x180012336  retn
```
