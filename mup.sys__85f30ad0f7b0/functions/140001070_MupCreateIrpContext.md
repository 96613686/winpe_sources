# MupCreateIrpContext

- ea: `0x140001070`
- end: `0x140001356`
- name: `MupCreateIrpContext`
- size: `742`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter4, __int64, ULONG_PTR, char, __int64 **)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140019d10`
- `0x140019fb0`
- `0x14001a3c0`
- `0x14001a7b0`
- `0x14001b8b0`
- `0x14001d040`

## callees

- `0x140001070`
- `0x1400029b0`
- `0x1400059c0`
- `0x140016460`
- `0x14001daf0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140001294`
- `ntoskrnl!KeBugCheckEx` at `0x140001294`
- `ntoskrnl!ExAllocatePool2` at `0x14000110f`
- `ntoskrnl!ExAllocatePool2` at `0x14000110f`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400010c9`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400010c9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400010e5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400010e5`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14000131a`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14000131a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400012cc`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400012cc`

## pseudocode

```c
__int64 __fastcall MupCreateIrpContext(ULONG_PTR BugCheckParameter4, __int64 a2, ULONG_PTR a3, char a4, __int64 **a5)
{
  unsigned int v8; // ebp
  __int64 *v9; // rdi
  char v10; // r12
  __int64 CurrentNodeNumber; // rsi
  __int64 *Pool2; // rbx
  unsigned int v13; // r15d
  __int64 v14; // rax
  _QWORD *v15; // rdi
  __int64 *i; // rbp
  int v18; // eax

  if ( (*(_DWORD *)(BugCheckParameter4 + 240) & 1) != 0 )
    KeBugCheckEx(0x103u, 4u, a3, *(_QWORD *)(BugCheckParameter4 + 144), BugCheckParameter4);
  v8 = *(_DWORD *)(BugCheckParameter4 + 216) + 136;
  v9 = 0;
  if ( v8 > 0x118 )
  {
    v10 = 0;
    LOWORD(CurrentNodeNumber) = -1;
    Pool2 = (__int64 *)ExAllocatePool2(66, v8, 1665758541);
    if ( Pool2 )
      goto LABEL_6;
  }
  else
  {
    v10 = 0;
    CurrentNodeNumber = KeGetCurrentNodeNumber();
    Pool2 = (__int64 *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)MupiIrpContextLookasideLists + CurrentNodeNumber);
    if ( Pool2 )
    {
      v10 = 1;
LABEL_6:
      *(_OWORD *)(Pool2 + 1) = 0;
      *(_OWORD *)(Pool2 + 3) = 0;
      *(_OWORD *)(Pool2 + 5) = 0;
      *(_OWORD *)(Pool2 + 7) = 0;
      *(_OWORD *)(Pool2 + 9) = 0;
      *(_OWORD *)(Pool2 + 11) = 0;
      *(_OWORD *)(Pool2 + 13) = 0;
      *(_OWORD *)(Pool2 + 15) = 0;
      goto LABEL_7;
    }
  }
  if ( !a4 )
  {
    v13 = -1073741670;
    goto LABEL_15;
  }
  if ( _InterlockedExchangeAdd(&MupReserveIrpContext, 0xFFFFFFFF) != 1 )
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
  qword_14000AB80 = (__int64)KeGetCurrentThread();
  memset(&dword_14000AB90, 0, 0x80u);
  dword_14000AB90 = 2;
  Pool2 = &qword_14000AB88;
LABEL_7:
  *(_WORD *)Pool2 = 28938;
  v13 = 0;
  *((_WORD *)Pool2 + 1) = v8;
  *((_DWORD *)Pool2 + 1) = 1;
  if ( v10 )
    *((_WORD *)Pool2 + 51) = CurrentNodeNumber + 1;
  Pool2[10] = (__int64)(Pool2 + 9);
  Pool2[9] = (__int64)(Pool2 + 9);
  Pool2[5] = BugCheckParameter4;
  Pool2[6] = a2;
  if ( a2 )
  {
    MupReferenceContainerContext(a2);
    Pool2[7] = PsGetCurrentServerSilo();
  }
  Pool2[2] = a3;
  *((_DWORD *)Pool2 + 6) = 0;
  *((_DWORD *)Pool2 + 8) = -1073741823;
  *((_DWORD *)Pool2 + 7) = -1073741802;
  *((_DWORD *)Pool2 + 9) = -1073741802;
  Pool2[8] = 0;
  *((_WORD *)Pool2 + 50) = -1;
  v14 = *(_QWORD *)(a3 + 184);
  if ( !*(_BYTE *)v14 )
  {
    v18 = *(_DWORD *)(v14 + 32);
    *((_DWORD *)Pool2 + 24) = v18;
    if ( v18 )
      Pool2[11] = *(_QWORD *)(a3 + 24);
  }
  v15 = *(_QWORD **)(BugCheckParameter4 + 200);
  for ( i = Pool2 + 17; v15 != (_QWORD *)(BugCheckParameter4 + 200); i += 18 )
  {
    MupInitSurrogateIrpContext(v15 - 1, Pool2, i);
    v15 = (_QWORD *)*v15;
  }
  v9 = Pool2;
LABEL_15:
  *a5 = v9;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_qqD(
      WPP_GLOBAL_Control->AttachedDevice,
      16,
      WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids,
      BugCheckParameter4,
      v9,
      v13);
  }
  return v13;
}

```

## disassembly

```asm
0x140001070  mov     [rsp+arg_10], r8
0x140001075  push    r13
0x140001077  push    r14
0x140001079  push    r15
0x14000107b  sub     rsp, 40h
0x14000107f  mov     eax, [rcx+0F0h]
0x140001085  movzx   r15d, r9b
0x140001089  mov     r13, rdx
0x14000108c  mov     r14, rcx
0x14000108f  test    al, 1
0x140001091  jnz     loc_14000127E
0x140001097  mov     [rsp+58h+arg_0], rbx
0x14000109c  mov     [rsp+58h+arg_8], rbp
0x1400010a1  mov     ebp, [rcx+0D8h]
0x1400010a7  mov     [rsp+58h+arg_18], rsi
0x1400010ac  add     ebp, 88h
0x1400010b2  mov     [rsp+58h+var_20], rdi
0x1400010b7  xor     edi, edi
0x1400010b9  mov     [rsp+58h+var_28], r12
0x1400010be  cmp     ebp, 118h
0x1400010c4  ja      short loc_140001102
0x1400010c6  xor     r12b, r12b
0x1400010c9  call    cs:__imp_KeGetCurrentNodeNumber
0x1400010d0  nop     dword ptr [rax+rax+00h]
0x1400010d5  movzx   esi, ax
0x1400010d8  mov     ecx, esi
0x1400010da  shl     rcx, 7
0x1400010de  add     rcx, cs:MupiIrpContextLookasideLists; Lookaside
0x1400010e5  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400010ec  nop     dword ptr [rax+rax+00h]
0x1400010f1  mov     rbx, rax
0x1400010f4  test    rax, rax
0x1400010f7  jz      loc_1400012A1
0x1400010fd  mov     r12b, 1
0x140001100  jmp     short loc_14000112F
0x140001102  mov     edx, ebp
0x140001104  mov     ecx, 42h ; 'B'
0x140001109  mov     r8d, 6349754Dh
0x14000110f  call    cs:__imp_ExAllocatePool2
0x140001116  nop     dword ptr [rax+rax+00h]
0x14000111b  xor     r12b, r12b
0x14000111e  mov     esi, 0FFFFh
0x140001123  mov     rbx, rax
0x140001126  test    rax, rax
0x140001129  jz      loc_1400012A1
0x14000112f  xorps   xmm0, xmm0
0x140001132  movups  xmmword ptr [rbx+8], xmm0
0x140001136  movups  xmmword ptr [rbx+18h], xmm0
0x14000113a  movups  xmmword ptr [rbx+28h], xmm0
0x14000113e  movups  xmmword ptr [rbx+38h], xmm0
0x140001142  movups  xmmword ptr [rbx+48h], xmm0
0x140001146  movups  xmmword ptr [rbx+58h], xmm0
0x14000114a  movups  xmmword ptr [rbx+68h], xmm0
0x14000114e  movups  xmmword ptr [rbx+78h], xmm0
0x140001152  mov     word ptr [rbx], 710Ah
0x140001157  mov     r15d, edi
0x14000115a  mov     [rbx+2], bp
0x14000115e  mov     dword ptr [rbx+4], 1
0x140001165  test    r12b, r12b
0x140001168  jz      short loc_140001171
0x14000116a  inc     si
0x14000116d  mov     [rbx+66h], si
0x140001171  lea     rax, [rbx+48h]
0x140001175  mov     [rax+8], rax
0x140001179  mov     [rax], rax
0x14000117c  mov     [rbx+28h], r14
0x140001180  mov     [rbx+30h], r13
0x140001184  test    r13, r13
0x140001187  jnz     loc_140001312
0x14000118d  mov     rcx, [rsp+58h+arg_10]
0x140001192  mov     [rbx+10h], rcx
0x140001196  mov     [rbx+18h], edi
0x140001199  mov     dword ptr [rbx+20h], 0C0000001h
0x1400011a0  mov     dword ptr [rbx+1Ch], 0C0000016h
0x1400011a7  mov     dword ptr [rbx+24h], 0C0000016h
0x1400011ae  mov     [rbx+40h], rdi
0x1400011b2  mov     word ptr [rbx+64h], 0FFFFh
0x1400011b8  mov     rax, [rcx+0B8h]
0x1400011bf  cmp     [rax], dil
0x1400011c2  jz      loc_140001252
0x1400011c8  lea     rsi, [r14+0C8h]
0x1400011cf  mov     rdi, [rsi]
0x1400011d2  lea     rbp, [rbx+88h]
0x1400011d9  cmp     rdi, rsi
0x1400011dc  jz      short loc_1400011FC
0x1400011de  lea     rcx, [rdi-8]
0x1400011e2  mov     r8, rbp
0x1400011e5  mov     rdx, rbx
0x1400011e8  call    MupInitSurrogateIrpContext
0x1400011ed  mov     rdi, [rdi]
0x1400011f0  add     rbp, 90h
0x1400011f7  cmp     rdi, rsi
0x1400011fa  jnz     short loc_1400011DE
0x1400011fc  mov     rdi, rbx
0x1400011ff  mov     rax, [rsp+58h+arg_20]
0x140001207  mov     [rax], rdi
0x14000120a  lea     rax, WPP_GLOBAL_Control
0x140001211  mov     rcx, cs:WPP_GLOBAL_Control
0x140001218  mov     r12, [rsp+58h+var_28]
0x14000121d  mov     rsi, [rsp+58h+arg_18]
0x140001222  mov     rbp, [rsp+58h+arg_8]
0x140001227  mov     rbx, [rsp+58h+arg_0]
0x14000122c  cmp     rcx, rax
0x14000122f  jz      short loc_14000123E
0x140001231  test    dword ptr [rcx+2Ch], 4000000h
0x140001238  jnz     loc_14000132F
0x14000123e  mov     rdi, [rsp+58h+var_20]
0x140001243  mov     eax, r15d
0x140001246  add     rsp, 40h
0x14000124a  pop     r15
0x14000124c  pop     r14
0x14000124e  pop     r13
0x140001250  retn
0x140001252  mov     eax, [rax+20h]
0x140001255  mov     [rbx+60h], eax
0x140001258  test    eax, eax
0x14000125a  jz      loc_1400011C8
0x140001260  mov     rax, [rcx+18h]
0x140001264  mov     [rbx+58h], rax
0x140001268  jmp     loc_1400011C8
0x14000126d  test    rbx, rbx
0x140001270  jnz     loc_140001152
0x140001276  mov     r15d, 0C000009Ah
0x14000127c  jmp     short loc_1400011FF
0x14000127e  mov     r9, [rcx+90h]; BugCheckParameter3
0x140001285  mov     edx, 4; BugCheckParameter1
0x14000128a  mov     ecx, 103h; BugCheckCode
0x14000128f  mov     [rsp+58h+BugCheckParameter4], r14; BugCheckParameter4
0x140001294  call    cs:__imp_KeBugCheckEx
0x1400012a1  test    r15b, r15b
0x1400012a4  jz      short loc_14000126D
0x1400012a6  mov     eax, 0FFFFFFFFh
0x1400012ab  lock xadd cs:MupReserveIrpContext, eax
0x1400012b3  cmp     eax, 1
0x1400012b6  jz      short loc_1400012D8
0x1400012b8  xor     r9d, r9d; Alertable
0x1400012bb  mov     [rsp+58h+BugCheckParameter4], rdi; Timeout
0x1400012c0  xor     r8d, r8d; WaitMode
0x1400012c3  lea     rcx, Event; Object
0x1400012ca  xor     edx, edx; WaitReason
0x1400012cc  call    cs:__imp_KeWaitForSingleObject
0x1400012d3  nop     dword ptr [rax+rax+00h]
0x1400012d8  mov     rax, gs:188h
0x1400012e1  lea     rcx, dword_14000AB90; void *
0x1400012e8  xor     edx, edx; Val
0x1400012ea  mov     cs:qword_14000AB80, rax
0x1400012f1  mov     r8d, 80h; Size
0x1400012f7  call    memset
0x1400012fc  mov     cs:dword_14000AB90, 2
0x140001306  lea     rbx, qword_14000AB88
0x14000130d  jmp     loc_140001152
0x140001312  mov     rcx, r13
0x140001315  call    MupReferenceContainerContext
0x14000131a  call    cs:__imp_PsGetCurrentServerSilo
0x140001321  nop     dword ptr [rax+rax+00h]
0x140001326  mov     [rbx+38h], rax
0x14000132a  jmp     loc_14000118D
0x14000132f  mov     rcx, [rcx+18h]
0x140001333  lea     r8, WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids
0x14000133a  mov     edx, 10h
0x14000133f  mov     [rsp+58h+var_30], r15d
0x140001344  mov     r9, r14
0x140001347  mov     [rsp+58h+BugCheckParameter4], rdi
0x14000134c  call    WPP_SF_qqD
0x140001351  jmp     loc_14000123E
```
