# FveReadWriteDriverReconfig

- ea: `0x1400bdf54`
- end: `0x1400be3ba`
- name: `FveReadWriteDriverReconfig`
- size: `1126`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140027db8`

## callees

- `0x14000fa9c`
- `0x14000fb98`
- `0x14000fc1c`
- `0x140023560`
- `0x1400bdf54`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400be364`
- `ntoskrnl!KeReleaseMutex` at `0x1400be364`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400be378`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400be378`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bdfb0`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bdfb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bdfdd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400be38c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bdfdd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400be38c`

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
  KeWaitForSingleObject((PVOID)(a1 + 9856), Executive, 0, 0, 0);
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
    *(_DWORD *)(a1 + 3932) = *((_DWORD *)a3 + v14 + 3);
    *(_DWORD *)(a1 + 7188) = *((_DWORD *)a3 + v14 + 6);
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
    v9 = (struct _NPAGED_LOOKASIDE_LIST *)_InterlockedExchange64((volatile __int64 *)(a1 + 9256), (__int64)v9);
    v11 = (void *)_InterlockedExchange64((volatile __int64 *)(a1 + 9264), (__int64)v11);
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
  KeReleaseMutex((PRKMUTEX)(a1 + 9856), 0);
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
0x1400bdf54  push    rbx
0x1400bdf56  push    rbp
0x1400bdf57  push    rsi
0x1400bdf58  push    rdi
0x1400bdf59  push    r12
0x1400bdf5b  push    r13
0x1400bdf5d  push    r14
0x1400bdf5f  push    r15
0x1400bdf61  sub     rsp, 88h
0x1400bdf68  mov     r10, [rsp+0C8h+arg_20]
0x1400bdf70  mov     rbx, rcx
0x1400bdf73  mov     rax, [rsp+0C8h+arg_28]
0x1400bdf7b  xor     ecx, ecx
0x1400bdf7d  mov     rsi, r9
0x1400bdf80  mov     byte ptr [rsp+0C8h+arg_20], cl
0x1400bdf87  mov     rdi, r8
0x1400bdf8a  mov     [rsp+0C8h+Timeout], rcx; Timeout
0x1400bdf8f  mov     rbp, [r10]
0x1400bdf92  mov     r15, rdx
0x1400bdf95  mov     r14, [rax]
0x1400bdf98  mov     r13b, cl
0x1400bdf9b  mov     [r10], rcx
0x1400bdf9e  xor     r9d, r9d; Alertable
0x1400bdfa1  mov     [rax], rcx
0x1400bdfa4  xor     r8d, r8d; WaitMode
0x1400bdfa7  lea     rcx, [rbx+2680h]; Object
0x1400bdfae  xor     edx, edx; WaitReason
0x1400bdfb0  call    cs:__imp_KeWaitForSingleObject
0x1400bdfb7  nop     dword ptr [rax+rax+00h]
0x1400bdfbc  lea     r12, [rbx+598h]
0x1400bdfc3  cmp     r15, r12
0x1400bdfc6  jz      loc_1400BE0B5
0x1400bdfcc  mov     rcx, [rbx+658h]; P
0x1400bdfd3  test    rcx, rcx
0x1400bdfd6  jz      short loc_1400BDFF4
0x1400bdfd8  mov     edx, 30455646h; Tag
0x1400bdfdd  call    cs:__imp_ExFreePoolWithTag
0x1400bdfe4  nop     dword ptr [rax+rax+00h]
0x1400bdfe9  mov     qword ptr [rbx+658h], 0
0x1400bdff4  movups  xmm0, xmmword ptr [r15]
0x1400bdff8  movups  xmmword ptr [r12], xmm0
0x1400bdffd  movups  xmm1, xmmword ptr [r15+10h]
0x1400be002  movups  xmmword ptr [r12+10h], xmm1
0x1400be008  movups  xmm0, xmmword ptr [r15+20h]
0x1400be00d  movups  xmmword ptr [r12+20h], xmm0
0x1400be013  movups  xmm1, xmmword ptr [r15+30h]
0x1400be018  movups  xmmword ptr [r12+30h], xmm1
0x1400be01e  movups  xmm0, xmmword ptr [r15+40h]
0x1400be023  movups  xmmword ptr [r12+40h], xmm0
0x1400be029  movups  xmm1, xmmword ptr [r15+50h]
0x1400be02e  movups  xmmword ptr [r12+50h], xmm1
0x1400be034  movups  xmm0, xmmword ptr [r15+60h]
0x1400be039  movups  xmmword ptr [r12+60h], xmm0
0x1400be03f  movups  xmm1, xmmword ptr [r15+70h]
0x1400be044  movups  xmmword ptr [r12+70h], xmm1
0x1400be04a  movups  xmm0, xmmword ptr [r15+80h]
0x1400be052  movups  xmmword ptr [r12+80h], xmm0
0x1400be05b  movups  xmm1, xmmword ptr [r15+90h]
0x1400be063  movups  xmmword ptr [r12+90h], xmm1
0x1400be06c  movups  xmm0, xmmword ptr [r15+0A0h]
0x1400be074  movups  xmmword ptr [r12+0A0h], xmm0
0x1400be07d  movups  xmm1, xmmword ptr [r15+0B0h]
0x1400be085  movups  xmmword ptr [r12+0B0h], xmm1
0x1400be08e  movups  xmm0, xmmword ptr [r15+0C0h]
0x1400be096  movups  xmmword ptr [r12+0C0h], xmm0
0x1400be09f  mov     qword ptr [r15+0C0h], 0
0x1400be0aa  mov     qword ptr [r15+0C8h], 0
0x1400be0b5  mov     r8, [rdi+40h]; Size
0x1400be0b9  lea     r15, [rbx+550h]
0x1400be0c0  mov     rcx, r15; Buf1
0x1400be0c3  mov     rdx, rdi; Buf2
0x1400be0c6  call    memcmp
0x1400be0cb  test    eax, eax
0x1400be0cd  jz      short loc_1400BE0EC
0x1400be0cf  mov     ecx, [rbx+374h]
0x1400be0d5  mov     r13b, 1
0x1400be0d8  mov     eax, [rdi+rcx*4+0Ch]
0x1400be0dc  mov     [rbx+0F5Ch], eax
0x1400be0e2  mov     eax, [rdi+rcx*4+18h]
0x1400be0e6  mov     [rbx+1C14h], eax
0x1400be0ec  movaps  xmm0, xmmword ptr [rdi]
0x1400be0ef  mov     rdx, rsi; Buf2
0x1400be0f2  movups  xmmword ptr [r15], xmm0
0x1400be0f6  movaps  xmm1, xmmword ptr [rdi+10h]
0x1400be0fa  movups  xmmword ptr [r15+10h], xmm1
0x1400be0ff  movaps  xmm0, xmmword ptr [rdi+20h]
0x1400be103  movups  xmmword ptr [r15+20h], xmm0
0x1400be108  movaps  xmm1, xmmword ptr [rdi+30h]
0x1400be10c  movups  xmmword ptr [r15+30h], xmm1
0x1400be111  movsd   xmm0, qword ptr [rdi+40h]
0x1400be116  lea     rdi, [rbx+3A8h]
0x1400be11d  movsd   qword ptr [r15+40h], xmm0
0x1400be123  mov     rcx, rdi; Buf1
0x1400be126  mov     r8, [rsi+1A0h]; Size
0x1400be12d  call    memcmp
0x1400be132  test    eax, eax
0x1400be134  jz      short loc_1400BE149
0x1400be136  xchg    rbp, [rbx+2428h]
0x1400be13d  xchg    r14, [rbx+2430h]
0x1400be144  mov     r15b, 1
0x1400be147  jmp     short loc_1400BE151
0x1400be149  mov     r15b, byte ptr [rsp+0C8h+arg_20]
0x1400be151  mov     eax, 3
0x1400be156  lea     r12d, [rax+7Dh]
0x1400be15a  movups  xmm0, xmmword ptr [rsi]
0x1400be15d  movups  xmmword ptr [rdi], xmm0
0x1400be160  movups  xmm1, xmmword ptr [rsi+10h]
0x1400be164  movups  xmmword ptr [rdi+10h], xmm1
0x1400be168  movups  xmm0, xmmword ptr [rsi+20h]
0x1400be16c  movups  xmmword ptr [rdi+20h], xmm0
0x1400be170  movups  xmm1, xmmword ptr [rsi+30h]
0x1400be174  movups  xmmword ptr [rdi+30h], xmm1
0x1400be178  movups  xmm0, xmmword ptr [rsi+40h]
0x1400be17c  movups  xmmword ptr [rdi+40h], xmm0
0x1400be180  movups  xmm1, xmmword ptr [rsi+50h]
0x1400be184  movups  xmmword ptr [rdi+50h], xmm1
0x1400be188  movups  xmm0, xmmword ptr [rsi+60h]
0x1400be18c  movups  xmmword ptr [rdi+60h], xmm0
0x1400be190  movups  xmm1, xmmword ptr [rsi+70h]
0x1400be194  add     rsi, r12
0x1400be197  movups  xmmword ptr [rdi+70h], xmm1
0x1400be19b  add     rdi, r12
0x1400be19e  sub     rax, 1
0x1400be1a2  jnz     short loc_1400BE15A
0x1400be1a4  movups  xmm0, xmmword ptr [rsi]
0x1400be1a7  movups  xmmword ptr [rdi], xmm0
0x1400be1aa  movups  xmm1, xmmword ptr [rsi+10h]
0x1400be1ae  movups  xmmword ptr [rdi+10h], xmm1
0x1400be1b2  mov     rax, [rsi+20h]
0x1400be1b6  lea     rsi, WPP_GLOBAL_Control
0x1400be1bd  mov     [rdi+20h], rax
0x1400be1c1  mov     dil, 4
0x1400be1c4  test    r13b, r13b
0x1400be1c7  jz      short loc_1400BE228
0x1400be1c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400be1d0  cmp     rcx, rsi
0x1400be1d3  jz      short loc_1400BE228
0x1400be1d5  mov     eax, [rcx+2Ch]
0x1400be1d8  test    r12b, al
0x1400be1db  jz      short loc_1400BE228
0x1400be1dd  cmp     [rcx+29h], dil
0x1400be1e1  jb      short loc_1400BE228
0x1400be1e3  mov     r9d, [rbx+374h]
0x1400be1ea  mov     edx, 37h ; '7'
0x1400be1ef  mov     rcx, [rcx+18h]
0x1400be1f3  mov     eax, [rbx+r9*4+574h]
0x1400be1fb  mov     [rsp+0C8h+var_90], eax
0x1400be1ff  mov     eax, [rbx+r9*4+550h]
0x1400be207  mov     [rsp+0C8h+var_98], eax
0x1400be20b  mov     eax, [rbx+r9*4+568h]
0x1400be213  mov     [rsp+0C8h+var_A0], eax
0x1400be217  mov     eax, [rbx+r9*4+55Ch]
0x1400be21f  mov     dword ptr [rsp+0C8h+Timeout], eax
0x1400be223  call    WPP_SF_LDDDD
0x1400be228  test    r15b, r15b
0x1400be22b  jz      loc_1400BE35B
0x1400be231  mov     rcx, cs:WPP_GLOBAL_Control
0x1400be238  cmp     rcx, rsi
0x1400be23b  jz      loc_1400BE35B
0x1400be241  mov     eax, [rcx+2Ch]
0x1400be244  test    r12b, al
0x1400be247  jz      loc_1400BE2FC
0x1400be24d  cmp     [rcx+29h], dil
0x1400be251  jb      loc_1400BE2FC
0x1400be257  mov     r9d, [rbx+374h]
0x1400be25e  mov     edx, 38h ; '8'
0x1400be263  mov     rcx, [rcx+18h]
0x1400be267  mov     eax, [rbx+r9*4+444h]
0x1400be26f  mov     [rsp+0C8h+var_50], eax
0x1400be273  mov     eax, [rbx+r9*4+438h]
0x1400be27b  mov     [rsp+0C8h+var_58], eax
0x1400be27f  mov     eax, [rbx+r9*4+42Ch]
0x1400be287  mov     [rsp+0C8h+var_60], eax
0x1400be28b  mov     eax, [rbx+r9*4+420h]
0x1400be293  mov     [rsp+0C8h+var_68], eax
0x1400be297  mov     eax, [rbx+r9*4+414h]
0x1400be29f  mov     [rsp+0C8h+var_70], eax
0x1400be2a3  mov     eax, [rbx+r9*4+408h]
0x1400be2ab  mov     [rsp+0C8h+var_78], eax
0x1400be2af  mov     eax, [rbx+r9*4+3FCh]
0x1400be2b7  mov     [rsp+0C8h+var_80], eax
0x1400be2bb  mov     eax, [rbx+r9*4+3E4h]
0x1400be2c3  mov     [rsp+0C8h+var_88], eax
0x1400be2c7  mov     eax, [rbx+r9*4+3D8h]
0x1400be2cf  mov     [rsp+0C8h+var_90], eax
0x1400be2d3  mov     eax, [rbx+r9*4+3C0h]
0x1400be2db  mov     [rsp+0C8h+var_98], eax
0x1400be2df  mov     eax, [rbx+r9*4+3B4h]
0x1400be2e7  mov     [rsp+0C8h+var_A0], eax
0x1400be2eb  mov     eax, [rbx+r9*4+3A8h]
0x1400be2f3  mov     dword ptr [rsp+0C8h+Timeout], eax
0x1400be2f7  call    WPP_SF_LDDDDDDDDDDDD
0x1400be2fc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400be303  cmp     rcx, rsi
0x1400be306  jz      short loc_1400BE35B
0x1400be308  mov     eax, [rcx+2Ch]
0x1400be30b  test    r12b, al
0x1400be30e  jz      short loc_1400BE35B
0x1400be310  cmp     [rcx+29h], dil
0x1400be314  jb      short loc_1400BE35B
0x1400be316  mov     r9d, [rbx+374h]
0x1400be31d  mov     edx, 39h ; '9'
0x1400be322  mov     rcx, [rcx+18h]
0x1400be326  mov     eax, [rbx+r9*4+3F0h]
0x1400be32e  mov     [rsp+0C8h+var_90], eax
0x1400be332  mov     eax, [rbx+r9*4+3CCh]
0x1400be33a  mov     [rsp+0C8h+var_98], eax
0x1400be33e  mov     eax, [rbx+r9*4+45Ch]
0x1400be346  mov     [rsp+0C8h+var_A0], eax
0x1400be34a  mov     eax, [rbx+r9*4+450h]
0x1400be352  mov     dword ptr [rsp+0C8h+Timeout], eax
0x1400be356  call    WPP_SF_LDDDD
0x1400be35b  xor     edx, edx; Wait
0x1400be35d  lea     rcx, [rbx+2680h]; Mutex
0x1400be364  call    cs:__imp_KeReleaseMutex
0x1400be36b  nop     dword ptr [rax+rax+00h]
0x1400be370  test    rbp, rbp
0x1400be373  jz      short loc_1400BE398
0x1400be375  mov     rcx, rbp; Lookaside
0x1400be378  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400be37f  nop     dword ptr [rax+rax+00h]
0x1400be384  mov     edx, 30455646h; Tag
0x1400be389  mov     rcx, rbp; P
0x1400be38c  call    cs:__imp_ExFreePoolWithTag
0x1400be393  nop     dword ptr [rax+rax+00h]
0x1400be398  test    r14, r14
0x1400be39b  jz      short loc_1400BE3A5
0x1400be39d  mov     rcx, r14; P
0x1400be3a0  call    PplDestroyLookasideList
0x1400be3a5  add     rsp, 88h
0x1400be3ac  pop     r15
0x1400be3ae  pop     r14
0x1400be3b0  pop     r13
0x1400be3b2  pop     r12
0x1400be3b4  pop     rdi
0x1400be3b5  pop     rsi
0x1400be3b6  pop     rbp
0x1400be3b7  pop     rbx
0x1400be3b8  retn
```
