# MapToEapError

- ea: `0x180022168`
- end: `0x18002237b`
- name: `MapToEapError`
- size: `531`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180026194`

## callees

- `0x180005440`
- `0x180010ae0`
- `0x1800214f0`
- `0x180022168`

## import_xrefs

- `MobileNetworking!AllocateAndCopyPointerData` at `0x180022224`
- `MobileNetworking!AllocateAndCopyPointerData` at `0x180022261`
- `MobileNetworking!AllocateAndCopyPointerData` at `0x180022224`
- `MobileNetworking!AllocateAndCopyPointerData` at `0x180022261`
- `MobileNetworking!AllocateMemory` at `0x1800221e3`
- `MobileNetworking!AllocateMemory` at `0x1800221e3`
- `MobileNetworking!FreeMemory` at `0x1800222a4`
- `MobileNetworking!FreeMemory` at `0x1800222bb`
- `MobileNetworking!FreeMemory` at `0x1800222d2`
- `MobileNetworking!FreeMemory` at `0x1800222a4`
- `MobileNetworking!FreeMemory` at `0x1800222bb`
- `MobileNetworking!FreeMemory` at `0x1800222d2`

## pseudocode

```c
__int64 __fastcall MapToEapError(__int64 a1, _QWORD *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  _QWORD v9[2]; // [rsp+20h] [rbp-10h] BYREF
  __int64 v10; // [rsp+70h] [rbp+40h] BYREF
  __int64 v11; // [rsp+78h] [rbp+48h] BYREF

  v10 = 0;
  v11 = 0;
  v9[0] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 72, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids);
  v4 = AllocateMemory(88, &v10, "MapToEapError", 1163);
  v5 = v4;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_19;
    v7 = 73;
    goto LABEL_18;
  }
  if ( (*(_BYTE *)(a1 + 72) & 1) != 0 )
  {
    v4 = AllocateAndCopyPointerData(&v11, a1 + *(unsigned int *)(a1 + 80), *(unsigned int *)(a1 + 76));
    v5 = v4;
    if ( v4 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_19;
      v7 = 74;
      goto LABEL_18;
    }
  }
  if ( (*(_BYTE *)(a1 + 72) & 2) == 0
    || (v4 = AllocateAndCopyPointerData(v9, a1 + *(unsigned int *)(a1 + 88), *(unsigned int *)(a1 + 84)), (v5 = v4) == 0) )
  {
    *(_DWORD *)v10 = *(_DWORD *)a1;
    *(_OWORD *)(v10 + 4) = *(_OWORD *)(a1 + 4);
    *(_DWORD *)(v10 + 20) = *(_DWORD *)(a1 + 20);
    *(_OWORD *)(v10 + 24) = *(_OWORD *)(a1 + 24);
    *(_OWORD *)(v10 + 40) = *(_OWORD *)(a1 + 40);
    *(_OWORD *)(v10 + 56) = *(_OWORD *)(a1 + 56);
    *(_QWORD *)(v10 + 72) = v11;
    *(_QWORD *)(v10 + 80) = v9[0];
    *a2 = v10;
    goto LABEL_21;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v7 = 75;
LABEL_18:
    WPP_SF_d(v6[7], v7, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids, v4);
  }
LABEL_19:
  FreeMemory(&v11, "MapToEapError", 1199);
  FreeMemory(v9, "MapToEapError", 1200);
  FreeMemory(&v10, "MapToEapError", 1201);
LABEL_21:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 76, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180022168  mov     [rsp-28h+arg_0], rbx
0x18002216d  push    rbp
0x18002216e  push    rsi
0x18002216f  push    rdi
0x180022170  push    r12
0x180022172  push    r15
0x180022174  mov     rbp, rsp
0x180022177  sub     rsp, 30h
0x18002217b  mov     rsi, rdx
0x18002217e  mov     [rbp+arg_10], 0
0x180022186  mov     rdi, rcx
0x180022189  mov     [rbp+arg_18], 0
0x180022191  mov     [rbp+var_10], 0
0x180022199  mov     rcx, cs:WPP_GLOBAL_Control
0x1800221a0  lea     r15, WPP_GLOBAL_Control
0x1800221a7  lea     r12, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids
0x1800221ae  cmp     rcx, r15
0x1800221b1  jz      short loc_1800221CD
0x1800221b3  test    dword ptr [rcx+44h], 800h
0x1800221ba  jz      short loc_1800221CD
0x1800221bc  mov     rcx, [rcx+38h]
0x1800221c0  mov     edx, 48h ; 'H'
0x1800221c5  mov     r8, r12
0x1800221c8  call    WPP_SF_
0x1800221cd  mov     r9d, 48Bh
0x1800221d3  lea     r8, aMaptoeaperror; "MapToEapError"
0x1800221da  lea     rdx, [rbp+arg_10]
0x1800221de  mov     ecx, 58h ; 'X'
0x1800221e3  call    cs:__imp_AllocateMemory
0x1800221e9  mov     ebx, eax
0x1800221eb  test    eax, eax
0x1800221ed  jz      short loc_180022210
0x1800221ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800221f6  cmp     rcx, r15
0x1800221f9  jz      loc_180022293
0x1800221ff  test    byte ptr [rcx+44h], 1
0x180022203  jz      loc_180022293
0x180022209  mov     edx, 49h ; 'I'
0x18002220e  jmp     short loc_180022284
0x180022210  test    byte ptr [rdi+48h], 1
0x180022214  jz      short loc_180022249
0x180022216  mov     edx, [rdi+50h]
0x180022219  lea     rcx, [rbp+arg_18]
0x18002221d  mov     r8d, [rdi+4Ch]
0x180022221  add     rdx, rdi
0x180022224  call    cs:__imp_AllocateAndCopyPointerData
0x18002222a  mov     ebx, eax
0x18002222c  test    eax, eax
0x18002222e  jz      short loc_180022249
0x180022230  mov     rcx, cs:WPP_GLOBAL_Control
0x180022237  cmp     rcx, r15
0x18002223a  jz      short loc_180022293
0x18002223c  test    byte ptr [rcx+44h], 1
0x180022240  jz      short loc_180022293
0x180022242  mov     edx, 4Ah ; 'J'
0x180022247  jmp     short loc_180022284
0x180022249  test    byte ptr [rdi+48h], 2
0x18002224d  jz      loc_1800222DA
0x180022253  mov     edx, [rdi+58h]
0x180022256  lea     rcx, [rbp+var_10]
0x18002225a  mov     r8d, [rdi+54h]
0x18002225e  add     rdx, rdi
0x180022261  call    cs:__imp_AllocateAndCopyPointerData
0x180022267  mov     ebx, eax
0x180022269  test    eax, eax
0x18002226b  jz      short loc_1800222DA
0x18002226d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022274  cmp     rcx, r15
0x180022277  jz      short loc_180022293
0x180022279  test    byte ptr [rcx+44h], 1
0x18002227d  jz      short loc_180022293
0x18002227f  mov     edx, 4Bh ; 'K'
0x180022284  mov     rcx, [rcx+38h]
0x180022288  mov     r9d, eax
0x18002228b  mov     r8, r12
0x18002228e  call    WPP_SF_d
0x180022293  mov     r8d, 4AFh
0x180022299  lea     rdx, aMaptoeaperror; "MapToEapError"
0x1800222a0  lea     rcx, [rbp+arg_18]
0x1800222a4  call    cs:__imp_FreeMemory
0x1800222aa  mov     r8d, 4B0h
0x1800222b0  lea     rdx, aMaptoeaperror; "MapToEapError"
0x1800222b7  lea     rcx, [rbp+var_10]
0x1800222bb  call    cs:__imp_FreeMemory
0x1800222c1  mov     r8d, 4B1h
0x1800222c7  lea     rdx, aMaptoeaperror; "MapToEapError"
0x1800222ce  lea     rcx, [rbp+arg_10]
0x1800222d2  call    cs:__imp_FreeMemory
0x1800222d8  jmp     short loc_18002233F
0x1800222da  mov     ecx, [rdi]
0x1800222dc  mov     rax, [rbp+arg_10]
0x1800222e0  mov     [rax], ecx
0x1800222e2  mov     rax, [rbp+arg_10]
0x1800222e6  movups  xmm0, xmmword ptr [rdi+4]
0x1800222ea  movdqu  xmmword ptr [rax+4], xmm0
0x1800222ef  mov     rax, [rbp+arg_10]
0x1800222f3  mov     ecx, [rdi+14h]
0x1800222f6  mov     [rax+14h], ecx
0x1800222f9  mov     rax, [rbp+arg_10]
0x1800222fd  movups  xmm0, xmmword ptr [rdi+18h]
0x180022301  movdqu  xmmword ptr [rax+18h], xmm0
0x180022306  mov     rax, [rbp+arg_10]
0x18002230a  movups  xmm1, xmmword ptr [rdi+28h]
0x18002230e  movdqu  xmmword ptr [rax+28h], xmm1
0x180022313  mov     rax, [rbp+arg_10]
0x180022317  movups  xmm0, xmmword ptr [rdi+38h]
0x18002231b  movdqu  xmmword ptr [rax+38h], xmm0
0x180022320  mov     rcx, [rbp+arg_10]
0x180022324  mov     rax, [rbp+arg_18]
0x180022328  mov     [rcx+48h], rax
0x18002232c  mov     rax, [rbp+var_10]
0x180022330  mov     rcx, [rbp+arg_10]
0x180022334  mov     [rcx+50h], rax
0x180022338  mov     rax, [rbp+arg_10]
0x18002233c  mov     [rsi], rax
0x18002233f  mov     rcx, cs:WPP_GLOBAL_Control
0x180022346  cmp     rcx, r15
0x180022349  jz      short loc_180022368
0x18002234b  test    dword ptr [rcx+44h], 800h
0x180022352  jz      short loc_180022368
0x180022354  mov     rcx, [rcx+38h]
0x180022358  mov     edx, 4Ch ; 'L'
0x18002235d  mov     r9d, ebx
0x180022360  mov     r8, r12
0x180022363  call    WPP_SF_D
0x180022368  mov     eax, ebx
0x18002236a  mov     rbx, [rsp+30h+arg_0]
0x18002236f  add     rsp, 30h
0x180022373  pop     r15
0x180022375  pop     r12
0x180022377  pop     rdi
0x180022378  pop     rsi
0x180022379  pop     rbp
0x18002237a  retn
```
