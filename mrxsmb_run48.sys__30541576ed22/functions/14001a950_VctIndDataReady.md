# VctIndDataReady

- ea: `0x14001a950`
- end: `0x14001ac1c`
- name: `VctIndDataReady`
- size: `716`
- prototype: `__int64 __fastcall(PVOID pContext, PVOID P)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000c270`
- `0x140011910`
- `0x140013470`
- `0x14001a950`
- `0x1400420b8`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001ab40`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001abb5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001ab40`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001abb5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ab56`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001abcb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001abf1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ab56`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001abcb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001abf1`
- `rdbss!RxFreeMdl` at `0x14001a998`
- `rdbss!RxFreeMdl` at `0x14001ab14`
- `rdbss!RxFreeMdl` at `0x14001ab89`
- `rdbss!RxFreeMdl` at `0x14001a998`
- `rdbss!RxFreeMdl` at `0x14001ab14`
- `rdbss!RxFreeMdl` at `0x14001ab89`

## pseudocode

```c
__int64 __fastcall VctIndDataReady(volatile signed __int64 *pContext, _QWORD *P, __int64 a3, unsigned int a4)
{
  _QWORD *v4; // rdi
  unsigned int v5; // r14d
  _QWORD *v8; // rcx
  _QWORD *v9; // rdi
  _QWORD *v10; // rcx
  _QWORD *v11; // r8
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  _QWORD *v14; // rdi
  __int64 v15; // rax
  __int64 v16; // rcx
  void *v17; // rax
  __int64 v18; // rcx
  char *v20; // [rsp+50h] [rbp-38h] BYREF
  int v21; // [rsp+90h] [rbp+8h] BYREF
  char *v22; // [rsp+98h] [rbp+10h] BYREF
  int v23; // [rsp+A8h] [rbp+20h] BYREF

  v4 = (_QWORD *)P[2];
  v5 = 0;
  if ( a4 != -2147483643 )
    v5 = a4;
  if ( v4 )
  {
    do
    {
      if ( v4 == (_QWORD *)P[3] )
        break;
      if ( v4 == (_QWORD *)P[6] )
        break;
      v8 = v4;
      v4 = (_QWORD *)*v4;
      *v8 = 0;
      RxFreeMdl(v8);
    }
    while ( v4 );
    *((_DWORD *)P + 3) = 0;
    P[2] = 0;
  }
  if ( *((_DWORD *)P + 11) )
  {
    if ( *((_DWORD *)P + 10) )
    {
      v9 = (_QWORD *)P[3];
      v10 = (_QWORD *)*v9;
      if ( *v9 )
      {
        v11 = (_QWORD *)P[6];
        while ( v10 != v11 )
        {
          v9 = v10;
          v10 = (_QWORD *)*v10;
          if ( !v10 )
            goto LABEL_20;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qDDqq(
            WPP_GLOBAL_Control->AttachedDevice,
            18,
            (unsigned int)&WPP_39c16dc859303064795977fd63584161_Traceguids,
            (_DWORD)v9,
            *((_DWORD *)v9 + 10),
            *((_DWORD *)P + 2),
            (char)v11,
            *v11);
        }
        *((_DWORD *)v9 + 10) = *((_DWORD *)P + 2);
        *v9 = *(_QWORD *)P[6];
        *(_QWORD *)P[6] = 0;
        *((_DWORD *)P + 2) = 0;
      }
    }
  }
LABEL_20:
  v12 = *((_DWORD *)P + 10);
  if ( v12 )
    SmbCeDataReadyInd((__int64)pContext, P[4], v12, v5);
  v13 = *((_DWORD *)P + 11);
  v14 = P + 7;
  if ( v13 )
    VctIndReceive((__int64)pContext, 0, v13, v13, 0, &v21, *v14 & 0xFFFFFFFFFFFFFFF8uLL, &v20, &v22, &v23);
  *(_OWORD *)P = 0;
  *((_OWORD *)P + 1) = 0;
  *((_OWORD *)P + 2) = 0;
  if ( *v14 )
  {
    v15 = *v14 & 7LL;
    if ( (unsigned int)v15 <= 4 && dword_140065880[v15] > 0x11000 )
    {
      RxFreeMdl(P[6]);
      if ( *v14 )
      {
        v16 = *v14 & 7LL;
        if ( (unsigned int)v16 > 4 )
          ExFreePoolWithTag((PVOID)(*v14 & 0xFFFFFFFFFFFFFFF8uLL), 0x6D535056u);
        else
          ExFreeToNPagedLookasideList(&SmbBufferLookasideList + v16, (PVOID)(*v14 & 0xFFFFFFFFFFFFFFF8uLL));
      }
      v14 = P + 7;
      *(_OWORD *)P = 0;
      *((_OWORD *)P + 1) = 0;
      *((_OWORD *)P + 2) = 0;
      *((_OWORD *)P + 3) = 0;
    }
  }
  if ( _InterlockedCompareExchange64(pContext + 60, (signed __int64)P, 0) )
  {
    RxFreeMdl(P[6]);
    if ( *v14 )
    {
      v17 = (void *)(*v14 & 0xFFFFFFFFFFFFFFF8uLL);
      v18 = *v14 & 7LL;
      if ( (unsigned int)v18 > 4 )
        ExFreePoolWithTag(v17, 0x6D535056u);
      else
        ExFreeToNPagedLookasideList(&SmbBufferLookasideList + v18, v17);
    }
    *(_OWORD *)P = 0;
    *((_OWORD *)P + 1) = 0;
    *((_OWORD *)P + 2) = 0;
    *((_OWORD *)P + 3) = 0;
    ExFreePoolWithTag(P, 0x6D534352u);
  }
  VctDereferenceEndpoint((PVOID)pContext);
  return 0;
}

```

## disassembly

```asm
0x14001a950  mov     [rsp+arg_10], rbx
0x14001a955  push    rbp
0x14001a956  push    rsi
0x14001a957  push    rdi
0x14001a958  push    r14
0x14001a95a  push    r15
0x14001a95c  sub     rsp, 60h
0x14001a960  mov     rdi, [rdx+10h]
0x14001a964  xor     r15d, r15d
0x14001a967  cmp     r9d, 80000005h
0x14001a96e  mov     r14d, r15d
0x14001a971  mov     rbx, rdx
0x14001a974  mov     rbp, rcx
0x14001a977  cmovnz  r14d, r9d
0x14001a97b  test    rdi, rdi
0x14001a97e  jz      short loc_14001A9B1
0x14001a980  cmp     rdi, [rbx+18h]
0x14001a984  jz      short loc_14001A9A9
0x14001a986  cmp     rdi, [rbx+30h]
0x14001a98a  jz      short loc_14001A9A9
0x14001a98c  mov     rcx, rdi
0x14001a98f  mov     rax, rdi
0x14001a992  mov     rdi, [rdi]
0x14001a995  mov     [rcx], r15
0x14001a998  call    cs:__imp_RxFreeMdl
0x14001a99f  nop     dword ptr [rax+rax+00h]
0x14001a9a4  test    rdi, rdi
0x14001a9a7  jnz     short loc_14001A980
0x14001a9a9  mov     [rbx+0Ch], r15d
0x14001a9ad  mov     [rbx+10h], r15
0x14001a9b1  cmp     [rbx+2Ch], r15d
0x14001a9b5  jz      loc_14001AA63
0x14001a9bb  cmp     [rbx+28h], r15d
0x14001a9bf  jz      loc_14001AA63
0x14001a9c5  mov     rdi, [rbx+18h]
0x14001a9c9  mov     rcx, [rdi]
0x14001a9cc  test    rcx, rcx
0x14001a9cf  jz      loc_14001AA63
0x14001a9d5  mov     r8, [rbx+30h]
0x14001a9d9  nop     dword ptr [rax+00000000h]
0x14001a9e0  cmp     rcx, r8
0x14001a9e3  jz      short loc_14001A9F5
0x14001a9e5  mov     rax, [rcx]
0x14001a9e8  mov     rdi, rcx
0x14001a9eb  mov     rcx, rax
0x14001a9ee  test    rax, rax
0x14001a9f1  jnz     short loc_14001A9E0
0x14001a9f3  jmp     short loc_14001AA63
0x14001a9f5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001a9fc  lea     rax, WPP_GLOBAL_Control
0x14001aa03  cmp     rcx, rax
0x14001aa06  jz      short loc_14001AA48
0x14001aa08  mov     eax, [rcx+2Ch]
0x14001aa0b  test    al, 4
0x14001aa0d  jz      short loc_14001AA48
0x14001aa0f  cmp     byte ptr [rcx+29h], 4
0x14001aa13  jb      short loc_14001AA48
0x14001aa15  mov     rax, [r8]
0x14001aa18  mov     edx, 12h
0x14001aa1d  mov     rcx, [rcx+18h]
0x14001aa21  mov     r9, rdi
0x14001aa24  mov     [rsp+88h+var_50], rax
0x14001aa29  mov     eax, [rbx+8]
0x14001aa2c  mov     [rsp+88h+var_58], r8
0x14001aa31  lea     r8, WPP_39c16dc859303064795977fd63584161_Traceguids
0x14001aa38  mov     dword ptr [rsp+88h+var_60], eax
0x14001aa3c  mov     eax, [rdi+28h]
0x14001aa3f  mov     dword ptr [rsp+88h+var_68], eax
0x14001aa43  call    WPP_SF_qDDqq
0x14001aa48  mov     eax, [rbx+8]
0x14001aa4b  mov     [rdi+28h], eax
0x14001aa4e  mov     rax, [rbx+30h]
0x14001aa52  mov     rcx, [rax]
0x14001aa55  mov     [rdi], rcx
0x14001aa58  mov     rax, [rbx+30h]
0x14001aa5c  mov     [rax], r15
0x14001aa5f  mov     [rbx+8], r15d
0x14001aa63  mov     r8d, [rbx+28h]
0x14001aa67  test    r8d, r8d
0x14001aa6a  jz      short loc_14001AA7B
0x14001aa6c  mov     rdx, [rbx+20h]
0x14001aa70  mov     r9d, r14d
0x14001aa73  mov     rcx, rbp
0x14001aa76  call    SmbCeDataReadyInd
0x14001aa7b  mov     r8d, [rbx+2Ch]
0x14001aa7f  lea     rdi, [rbx+38h]
0x14001aa83  test    r8d, r8d
0x14001aa86  jz      short loc_14001AAD7
0x14001aa88  mov     rax, [rdi]
0x14001aa8b  lea     rcx, [rsp+88h+arg_18]
0x14001aa93  mov     [rsp+88h+var_40], rcx
0x14001aa98  and     rax, 0FFFFFFFFFFFFFFF8h
0x14001aa9c  lea     rcx, [rsp+88h+arg_8]
0x14001aaa4  mov     r9d, r8d
0x14001aaa7  mov     [rsp+88h+var_48], rcx
0x14001aaac  xor     edx, edx
0x14001aaae  lea     rcx, [rsp+88h+var_38]
0x14001aab3  mov     [rsp+88h+var_50], rcx
0x14001aab8  mov     rcx, rbp
0x14001aabb  mov     [rsp+88h+var_58], rax
0x14001aac0  lea     rax, [rsp+88h+arg_0]
0x14001aac8  mov     [rsp+88h+var_60], rax
0x14001aacd  mov     [rsp+88h+var_68], r15
0x14001aad2  call    VctIndReceive
0x14001aad7  xorps   xmm0, xmm0
0x14001aada  lea     rsi, SmbBufferLookasideList
0x14001aae1  movups  xmmword ptr [rbx], xmm0
0x14001aae4  movups  xmmword ptr [rbx+10h], xmm0
0x14001aae8  movups  xmmword ptr [rbx+20h], xmm0
0x14001aaec  mov     rax, [rdi]
0x14001aaef  test    rax, rax
0x14001aaf2  jz      loc_14001AB78
0x14001aaf8  and     eax, 7
0x14001aafb  cmp     eax, 4
0x14001aafe  ja      short loc_14001AB78
0x14001ab00  lea     rcx, dword_140065880
0x14001ab07  cmp     dword ptr [rcx+rax*4], 11000h
0x14001ab0e  jbe     short loc_14001AB78
0x14001ab10  mov     rcx, [rbx+30h]
0x14001ab14  call    cs:__imp_RxFreeMdl
0x14001ab1b  nop     dword ptr [rax+rax+00h]
0x14001ab20  mov     rax, [rdi]
0x14001ab23  test    rax, rax
0x14001ab26  jz      short loc_14001AB62
0x14001ab28  mov     ecx, eax
0x14001ab2a  and     rax, 0FFFFFFFFFFFFFFF8h
0x14001ab2e  and     ecx, 7
0x14001ab31  cmp     ecx, 4
0x14001ab34  ja      short loc_14001AB4E
0x14001ab36  shl     rcx, 7
0x14001ab3a  mov     rdx, rax; Entry
0x14001ab3d  add     rcx, rsi; Lookaside
0x14001ab40  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001ab47  nop     dword ptr [rax+rax+00h]
0x14001ab4c  jmp     short loc_14001AB62
0x14001ab4e  mov     edx, 6D535056h; Tag
0x14001ab53  mov     rcx, rax; P
0x14001ab56  call    cs:__imp_ExFreePoolWithTag
0x14001ab5d  nop     dword ptr [rax+rax+00h]
0x14001ab62  xorps   xmm0, xmm0
0x14001ab65  lea     rdi, [rbx+38h]
0x14001ab69  movups  xmmword ptr [rbx], xmm0
0x14001ab6c  movups  xmmword ptr [rbx+10h], xmm0
0x14001ab70  movups  xmmword ptr [rbx+20h], xmm0
0x14001ab74  movups  xmmword ptr [rbx+30h], xmm0
0x14001ab78  xor     eax, eax
0x14001ab7a  lock cmpxchg [rbp+1E0h], rbx
0x14001ab83  jz      short loc_14001ABFD
0x14001ab85  mov     rcx, [rbx+30h]
0x14001ab89  call    cs:__imp_RxFreeMdl
0x14001ab90  nop     dword ptr [rax+rax+00h]
0x14001ab95  mov     rax, [rdi]
0x14001ab98  test    rax, rax
0x14001ab9b  jz      short loc_14001ABD7
0x14001ab9d  mov     ecx, eax
0x14001ab9f  and     rax, 0FFFFFFFFFFFFFFF8h
0x14001aba3  and     ecx, 7
0x14001aba6  cmp     ecx, 4
0x14001aba9  ja      short loc_14001ABC3
0x14001abab  shl     rcx, 7
0x14001abaf  mov     rdx, rax; Entry
0x14001abb2  add     rcx, rsi; Lookaside
0x14001abb5  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001abbc  nop     dword ptr [rax+rax+00h]
0x14001abc1  jmp     short loc_14001ABD7
0x14001abc3  mov     edx, 6D535056h; Tag
0x14001abc8  mov     rcx, rax; P
0x14001abcb  call    cs:__imp_ExFreePoolWithTag
0x14001abd2  nop     dword ptr [rax+rax+00h]
0x14001abd7  xorps   xmm0, xmm0
0x14001abda  mov     edx, 6D534352h; Tag
0x14001abdf  movups  xmmword ptr [rbx], xmm0
0x14001abe2  mov     rcx, rbx; P
0x14001abe5  movups  xmmword ptr [rbx+10h], xmm0
0x14001abe9  movups  xmmword ptr [rbx+20h], xmm0
0x14001abed  movups  xmmword ptr [rbx+30h], xmm0
0x14001abf1  call    cs:__imp_ExFreePoolWithTag
0x14001abf8  nop     dword ptr [rax+rax+00h]
0x14001abfd  mov     rcx, rbp; pContext
0x14001ac00  call    VctDereferenceEndpoint
0x14001ac05  mov     rbx, [rsp+88h+arg_10]
0x14001ac0d  xor     eax, eax
0x14001ac0f  add     rsp, 60h
0x14001ac13  pop     r15
0x14001ac15  pop     r14
0x14001ac17  pop     rdi
0x14001ac18  pop     rsi
0x14001ac19  pop     rbp
0x14001ac1a  retn
```
