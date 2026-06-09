# FveReadWriteDriverReconfig

- ea: `0x1400ba834`
- end: `0x1400bac9a`
- name: `FveReadWriteDriverReconfig`
- size: `1126`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140026db8`

## callees

- `0x14000f724`
- `0x14000f820`
- `0x14000f8a4`
- `0x140022220`
- `0x1400ba834`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400bac44`
- `ntoskrnl!KeReleaseMutex` at `0x1400bac44`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400bac58`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400bac58`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ba890`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400ba890`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba8bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bac6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ba8bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bac6c`

## pseudocode

```c
void __fastcall FveReadWriteDriverReconfig(
        __int64 a1,
        __int64 a2,
        _OWORD *a3,
        size_t *a4,
        struct _NPAGED_LOOKASIDE_LIST **a5,
        void **a6)
{
  struct _NPAGED_LOOKASIDE_LIST *v9; // rbp
  void *v11; // r14
  char v12; // r13
  void *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // xmm0_8
  _OWORD *v16; // rdi
  int v17; // r8d
  char v18; // r15
  __int64 v19; // rax
  __int128 v20; // xmm1
  __int64 v21; // r9

  v9 = *a5;
  v11 = *a6;
  v12 = 0;
  *a5 = 0;
  *a6 = 0;
  KeWaitForSingleObject((PVOID)(a1 + 9608), Executive, 0, 0, 0);
  if ( a2 != a1 + 1432 )
  {
    v13 = *(void **)(a1 + 1624);
    if ( v13 )
    {
      ExFreePoolWithTag(v13, 0x30455646u);
      *(_QWORD *)(a1 + 1624) = 0;
    }
    *(_OWORD *)(a1 + 1432) = *(_OWORD *)a2;
    *(_OWORD *)(a1 + 1448) = *(_OWORD *)(a2 + 16);
    *(_OWORD *)(a1 + 1464) = *(_OWORD *)(a2 + 32);
    *(_OWORD *)(a1 + 1480) = *(_OWORD *)(a2 + 48);
    *(_OWORD *)(a1 + 1496) = *(_OWORD *)(a2 + 64);
    *(_OWORD *)(a1 + 1512) = *(_OWORD *)(a2 + 80);
    *(_OWORD *)(a1 + 1528) = *(_OWORD *)(a2 + 96);
    *(_OWORD *)(a1 + 1544) = *(_OWORD *)(a2 + 112);
    *(_OWORD *)(a1 + 1560) = *(_OWORD *)(a2 + 128);
    *(_OWORD *)(a1 + 1576) = *(_OWORD *)(a2 + 144);
    *(_OWORD *)(a1 + 1592) = *(_OWORD *)(a2 + 160);
    *(_OWORD *)(a1 + 1608) = *(_OWORD *)(a2 + 176);
    *(_OWORD *)(a1 + 1624) = *(_OWORD *)(a2 + 192);
    *(_QWORD *)(a2 + 192) = 0;
    *(_QWORD *)(a2 + 200) = 0;
  }
  if ( memcmp((const void *)(a1 + 1360), a3, *((_QWORD *)a3 + 8)) )
  {
    v14 = *(unsigned int *)(a1 + 884);
    v12 = 1;
    *(_DWORD *)(a1 + 3684) = *((_DWORD *)a3 + v14 + 3);
    *(_DWORD *)(a1 + 6940) = *((_DWORD *)a3 + v14 + 6);
  }
  *(_OWORD *)(a1 + 1360) = *a3;
  *(_OWORD *)(a1 + 1376) = a3[1];
  *(_OWORD *)(a1 + 1392) = a3[2];
  *(_OWORD *)(a1 + 1408) = a3[3];
  v15 = *((_QWORD *)a3 + 8);
  v16 = (_OWORD *)(a1 + 936);
  *(_QWORD *)(a1 + 1424) = v15;
  if ( !memcmp((const void *)(a1 + 936), a4, a4[52]) )
  {
    v18 = 0;
  }
  else
  {
    v9 = (struct _NPAGED_LOOKASIDE_LIST *)_InterlockedExchange64((volatile __int64 *)(a1 + 9008), (__int64)v9);
    v11 = (void *)_InterlockedExchange64((volatile __int64 *)(a1 + 9016), (__int64)v11);
    v18 = 1;
  }
  v19 = 3;
  do
  {
    *v16 = *(_OWORD *)a4;
    v16[1] = *((_OWORD *)a4 + 1);
    v16[2] = *((_OWORD *)a4 + 2);
    v16[3] = *((_OWORD *)a4 + 3);
    v16[4] = *((_OWORD *)a4 + 4);
    v16[5] = *((_OWORD *)a4 + 5);
    v16[6] = *((_OWORD *)a4 + 6);
    v20 = *((_OWORD *)a4 + 7);
    a4 += 16;
    v16[7] = v20;
    v16 += 8;
    --v19;
  }
  while ( v19 );
  *v16 = *(_OWORD *)a4;
  v16[1] = *((_OWORD *)a4 + 1);
  *((_QWORD *)v16 + 4) = a4[4];
  if ( v12
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_LDDDD(WPP_GLOBAL_Control->AttachedDevice, 55);
  }
  if ( v18 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      v21 = *(unsigned int *)(a1 + 884);
      WPP_SF_LDDDDDDDDDDDD(
        WPP_GLOBAL_Control->AttachedDevice,
        56,
        v17,
        v21,
        *(_DWORD *)(a1 + 4 * v21 + 936),
        *(_DWORD *)(a1 + 4 * v21 + 948),
        *(_DWORD *)(a1 + 4 * v21 + 960),
        *(_DWORD *)(a1 + 4 * v21 + 984),
        *(_DWORD *)(a1 + 4 * v21 + 996),
        *(_DWORD *)(a1 + 4 * v21 + 1020),
        *(_DWORD *)(a1 + 4 * v21 + 1032),
        *(_DWORD *)(a1 + 4 * v21 + 1044),
        *(_DWORD *)(a1 + 4 * v21 + 1056),
        *(_DWORD *)(a1 + 4 * v21 + 1068),
        *(_DWORD *)(a1 + 4 * v21 + 1080),
        *(_DWORD *)(a1 + 4 * v21 + 1092));
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_LDDDD(WPP_GLOBAL_Control->AttachedDevice, 57);
    }
  }
  KeReleaseMutex((PRKMUTEX)(a1 + 9608), 0);
  if ( v9 )
  {
    ExDeleteNPagedLookasideList(v9);
    ExFreePoolWithTag(v9, 0x30455646u);
  }
  if ( v11 )
    PplDestroyLookasideList(v11);
}

```

## disassembly

```asm
0x1400ba834  push    rbx
0x1400ba836  push    rbp
0x1400ba837  push    rsi
0x1400ba838  push    rdi
0x1400ba839  push    r12
0x1400ba83b  push    r13
0x1400ba83d  push    r14
0x1400ba83f  push    r15
0x1400ba841  sub     rsp, 88h
0x1400ba848  mov     r10, [rsp+0C8h+arg_20]
0x1400ba850  mov     rbx, rcx
0x1400ba853  mov     rax, [rsp+0C8h+arg_28]
0x1400ba85b  xor     ecx, ecx
0x1400ba85d  mov     rsi, r9
0x1400ba860  mov     byte ptr [rsp+0C8h+arg_20], cl
0x1400ba867  mov     rdi, r8
0x1400ba86a  mov     [rsp+0C8h+Timeout], rcx; Timeout
0x1400ba86f  mov     rbp, [r10]
0x1400ba872  mov     r15, rdx
0x1400ba875  mov     r14, [rax]
0x1400ba878  mov     r13b, cl
0x1400ba87b  mov     [r10], rcx
0x1400ba87e  xor     r9d, r9d; Alertable
0x1400ba881  mov     [rax], rcx
0x1400ba884  xor     r8d, r8d; WaitMode
0x1400ba887  lea     rcx, [rbx+2588h]; Object
0x1400ba88e  xor     edx, edx; WaitReason
0x1400ba890  call    cs:__imp_KeWaitForSingleObject
0x1400ba897  nop     dword ptr [rax+rax+00h]
0x1400ba89c  lea     r12, [rbx+598h]
0x1400ba8a3  cmp     r15, r12
0x1400ba8a6  jz      loc_1400BA995
0x1400ba8ac  mov     rcx, [rbx+658h]; P
0x1400ba8b3  test    rcx, rcx
0x1400ba8b6  jz      short loc_1400BA8D4
0x1400ba8b8  mov     edx, 30455646h; Tag
0x1400ba8bd  call    cs:__imp_ExFreePoolWithTag
0x1400ba8c4  nop     dword ptr [rax+rax+00h]
0x1400ba8c9  mov     qword ptr [rbx+658h], 0
0x1400ba8d4  movups  xmm0, xmmword ptr [r15]
0x1400ba8d8  movups  xmmword ptr [r12], xmm0
0x1400ba8dd  movups  xmm1, xmmword ptr [r15+10h]
0x1400ba8e2  movups  xmmword ptr [r12+10h], xmm1
0x1400ba8e8  movups  xmm0, xmmword ptr [r15+20h]
0x1400ba8ed  movups  xmmword ptr [r12+20h], xmm0
0x1400ba8f3  movups  xmm1, xmmword ptr [r15+30h]
0x1400ba8f8  movups  xmmword ptr [r12+30h], xmm1
0x1400ba8fe  movups  xmm0, xmmword ptr [r15+40h]
0x1400ba903  movups  xmmword ptr [r12+40h], xmm0
0x1400ba909  movups  xmm1, xmmword ptr [r15+50h]
0x1400ba90e  movups  xmmword ptr [r12+50h], xmm1
0x1400ba914  movups  xmm0, xmmword ptr [r15+60h]
0x1400ba919  movups  xmmword ptr [r12+60h], xmm0
0x1400ba91f  movups  xmm1, xmmword ptr [r15+70h]
0x1400ba924  movups  xmmword ptr [r12+70h], xmm1
0x1400ba92a  movups  xmm0, xmmword ptr [r15+80h]
0x1400ba932  movups  xmmword ptr [r12+80h], xmm0
0x1400ba93b  movups  xmm1, xmmword ptr [r15+90h]
0x1400ba943  movups  xmmword ptr [r12+90h], xmm1
0x1400ba94c  movups  xmm0, xmmword ptr [r15+0A0h]
0x1400ba954  movups  xmmword ptr [r12+0A0h], xmm0
0x1400ba95d  movups  xmm1, xmmword ptr [r15+0B0h]
0x1400ba965  movups  xmmword ptr [r12+0B0h], xmm1
0x1400ba96e  movups  xmm0, xmmword ptr [r15+0C0h]
0x1400ba976  movups  xmmword ptr [r12+0C0h], xmm0
0x1400ba97f  mov     qword ptr [r15+0C0h], 0
0x1400ba98a  mov     qword ptr [r15+0C8h], 0
0x1400ba995  mov     r8, [rdi+40h]; Size
0x1400ba999  lea     r15, [rbx+550h]
0x1400ba9a0  mov     rcx, r15; Buf1
0x1400ba9a3  mov     rdx, rdi; Buf2
0x1400ba9a6  call    memcmp
0x1400ba9ab  test    eax, eax
0x1400ba9ad  jz      short loc_1400BA9CC
0x1400ba9af  mov     ecx, [rbx+374h]
0x1400ba9b5  mov     r13b, 1
0x1400ba9b8  mov     eax, [rdi+rcx*4+0Ch]
0x1400ba9bc  mov     [rbx+0E64h], eax
0x1400ba9c2  mov     eax, [rdi+rcx*4+18h]
0x1400ba9c6  mov     [rbx+1B1Ch], eax
0x1400ba9cc  movaps  xmm0, xmmword ptr [rdi]
0x1400ba9cf  mov     rdx, rsi; Buf2
0x1400ba9d2  movups  xmmword ptr [r15], xmm0
0x1400ba9d6  movaps  xmm1, xmmword ptr [rdi+10h]
0x1400ba9da  movups  xmmword ptr [r15+10h], xmm1
0x1400ba9df  movaps  xmm0, xmmword ptr [rdi+20h]
0x1400ba9e3  movups  xmmword ptr [r15+20h], xmm0
0x1400ba9e8  movaps  xmm1, xmmword ptr [rdi+30h]
0x1400ba9ec  movups  xmmword ptr [r15+30h], xmm1
0x1400ba9f1  movsd   xmm0, qword ptr [rdi+40h]
0x1400ba9f6  lea     rdi, [rbx+3A8h]
0x1400ba9fd  movsd   qword ptr [r15+40h], xmm0
0x1400baa03  mov     rcx, rdi; Buf1
0x1400baa06  mov     r8, [rsi+1A0h]; Size
0x1400baa0d  call    memcmp
0x1400baa12  test    eax, eax
0x1400baa14  jz      short loc_1400BAA29
0x1400baa16  xchg    rbp, [rbx+2330h]
0x1400baa1d  xchg    r14, [rbx+2338h]
0x1400baa24  mov     r15b, 1
0x1400baa27  jmp     short loc_1400BAA31
0x1400baa29  mov     r15b, byte ptr [rsp+0C8h+arg_20]
0x1400baa31  mov     eax, 3
0x1400baa36  lea     r12d, [rax+7Dh]
0x1400baa3a  movups  xmm0, xmmword ptr [rsi]
0x1400baa3d  movups  xmmword ptr [rdi], xmm0
0x1400baa40  movups  xmm1, xmmword ptr [rsi+10h]
0x1400baa44  movups  xmmword ptr [rdi+10h], xmm1
0x1400baa48  movups  xmm0, xmmword ptr [rsi+20h]
0x1400baa4c  movups  xmmword ptr [rdi+20h], xmm0
0x1400baa50  movups  xmm1, xmmword ptr [rsi+30h]
0x1400baa54  movups  xmmword ptr [rdi+30h], xmm1
0x1400baa58  movups  xmm0, xmmword ptr [rsi+40h]
0x1400baa5c  movups  xmmword ptr [rdi+40h], xmm0
0x1400baa60  movups  xmm1, xmmword ptr [rsi+50h]
0x1400baa64  movups  xmmword ptr [rdi+50h], xmm1
0x1400baa68  movups  xmm0, xmmword ptr [rsi+60h]
0x1400baa6c  movups  xmmword ptr [rdi+60h], xmm0
0x1400baa70  movups  xmm1, xmmword ptr [rsi+70h]
0x1400baa74  add     rsi, r12
0x1400baa77  movups  xmmword ptr [rdi+70h], xmm1
0x1400baa7b  add     rdi, r12
0x1400baa7e  sub     rax, 1
0x1400baa82  jnz     short loc_1400BAA3A
0x1400baa84  movups  xmm0, xmmword ptr [rsi]
0x1400baa87  movups  xmmword ptr [rdi], xmm0
0x1400baa8a  movups  xmm1, xmmword ptr [rsi+10h]
0x1400baa8e  movups  xmmword ptr [rdi+10h], xmm1
0x1400baa92  mov     rax, [rsi+20h]
0x1400baa96  lea     rsi, WPP_GLOBAL_Control
0x1400baa9d  mov     [rdi+20h], rax
0x1400baaa1  mov     dil, 4
0x1400baaa4  test    r13b, r13b
0x1400baaa7  jz      short loc_1400BAB08
0x1400baaa9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400baab0  cmp     rcx, rsi
0x1400baab3  jz      short loc_1400BAB08
0x1400baab5  mov     eax, [rcx+2Ch]
0x1400baab8  test    r12b, al
0x1400baabb  jz      short loc_1400BAB08
0x1400baabd  cmp     [rcx+29h], dil
0x1400baac1  jb      short loc_1400BAB08
0x1400baac3  mov     r9d, [rbx+374h]
0x1400baaca  mov     edx, 37h ; '7'
0x1400baacf  mov     rcx, [rcx+18h]
0x1400baad3  mov     eax, [rbx+r9*4+574h]
0x1400baadb  mov     [rsp+0C8h+var_90], eax
0x1400baadf  mov     eax, [rbx+r9*4+550h]
0x1400baae7  mov     [rsp+0C8h+var_98], eax
0x1400baaeb  mov     eax, [rbx+r9*4+568h]
0x1400baaf3  mov     [rsp+0C8h+var_A0], eax
0x1400baaf7  mov     eax, [rbx+r9*4+55Ch]
0x1400baaff  mov     dword ptr [rsp+0C8h+Timeout], eax
0x1400bab03  call    WPP_SF_LDDDD
0x1400bab08  test    r15b, r15b
0x1400bab0b  jz      loc_1400BAC3B
0x1400bab11  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bab18  cmp     rcx, rsi
0x1400bab1b  jz      loc_1400BAC3B
0x1400bab21  mov     eax, [rcx+2Ch]
0x1400bab24  test    r12b, al
0x1400bab27  jz      loc_1400BABDC
0x1400bab2d  cmp     [rcx+29h], dil
0x1400bab31  jb      loc_1400BABDC
0x1400bab37  mov     r9d, [rbx+374h]
0x1400bab3e  mov     edx, 38h ; '8'
0x1400bab43  mov     rcx, [rcx+18h]
0x1400bab47  mov     eax, [rbx+r9*4+444h]
0x1400bab4f  mov     [rsp+0C8h+var_50], eax
0x1400bab53  mov     eax, [rbx+r9*4+438h]
0x1400bab5b  mov     [rsp+0C8h+var_58], eax
0x1400bab5f  mov     eax, [rbx+r9*4+42Ch]
0x1400bab67  mov     [rsp+0C8h+var_60], eax
0x1400bab6b  mov     eax, [rbx+r9*4+420h]
0x1400bab73  mov     [rsp+0C8h+var_68], eax
0x1400bab77  mov     eax, [rbx+r9*4+414h]
0x1400bab7f  mov     [rsp+0C8h+var_70], eax
0x1400bab83  mov     eax, [rbx+r9*4+408h]
0x1400bab8b  mov     [rsp+0C8h+var_78], eax
0x1400bab8f  mov     eax, [rbx+r9*4+3FCh]
0x1400bab97  mov     [rsp+0C8h+var_80], eax
0x1400bab9b  mov     eax, [rbx+r9*4+3E4h]
0x1400baba3  mov     [rsp+0C8h+var_88], eax
0x1400baba7  mov     eax, [rbx+r9*4+3D8h]
0x1400babaf  mov     [rsp+0C8h+var_90], eax
0x1400babb3  mov     eax, [rbx+r9*4+3C0h]
0x1400babbb  mov     [rsp+0C8h+var_98], eax
0x1400babbf  mov     eax, [rbx+r9*4+3B4h]
0x1400babc7  mov     [rsp+0C8h+var_A0], eax
0x1400babcb  mov     eax, [rbx+r9*4+3A8h]
0x1400babd3  mov     dword ptr [rsp+0C8h+Timeout], eax
0x1400babd7  call    WPP_SF_LDDDDDDDDDDDD
0x1400babdc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400babe3  cmp     rcx, rsi
0x1400babe6  jz      short loc_1400BAC3B
0x1400babe8  mov     eax, [rcx+2Ch]
0x1400babeb  test    r12b, al
0x1400babee  jz      short loc_1400BAC3B
0x1400babf0  cmp     [rcx+29h], dil
0x1400babf4  jb      short loc_1400BAC3B
0x1400babf6  mov     r9d, [rbx+374h]
0x1400babfd  mov     edx, 39h ; '9'
0x1400bac02  mov     rcx, [rcx+18h]
0x1400bac06  mov     eax, [rbx+r9*4+3F0h]
0x1400bac0e  mov     [rsp+0C8h+var_90], eax
0x1400bac12  mov     eax, [rbx+r9*4+3CCh]
0x1400bac1a  mov     [rsp+0C8h+var_98], eax
0x1400bac1e  mov     eax, [rbx+r9*4+45Ch]
0x1400bac26  mov     [rsp+0C8h+var_A0], eax
0x1400bac2a  mov     eax, [rbx+r9*4+450h]
0x1400bac32  mov     dword ptr [rsp+0C8h+Timeout], eax
0x1400bac36  call    WPP_SF_LDDDD
0x1400bac3b  xor     edx, edx; Wait
0x1400bac3d  lea     rcx, [rbx+2588h]; Mutex
0x1400bac44  call    cs:__imp_KeReleaseMutex
0x1400bac4b  nop     dword ptr [rax+rax+00h]
0x1400bac50  test    rbp, rbp
0x1400bac53  jz      short loc_1400BAC78
0x1400bac55  mov     rcx, rbp; Lookaside
0x1400bac58  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400bac5f  nop     dword ptr [rax+rax+00h]
0x1400bac64  mov     edx, 30455646h; Tag
0x1400bac69  mov     rcx, rbp; P
0x1400bac6c  call    cs:__imp_ExFreePoolWithTag
0x1400bac73  nop     dword ptr [rax+rax+00h]
0x1400bac78  test    r14, r14
0x1400bac7b  jz      short loc_1400BAC85
0x1400bac7d  mov     rcx, r14; P
0x1400bac80  call    PplDestroyLookasideList
0x1400bac85  add     rsp, 88h
0x1400bac8c  pop     r15
0x1400bac8e  pop     r14
0x1400bac90  pop     r13
0x1400bac92  pop     r12
0x1400bac94  pop     rdi
0x1400bac95  pop     rsi
0x1400bac96  pop     rbp
0x1400bac97  pop     rbx
0x1400bac98  retn
```
