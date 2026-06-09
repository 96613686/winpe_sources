# FltpInitFrameLookasideLists

- ea: `0x180052640`
- end: `0x180052907`
- name: `FltpInitFrameLookasideLists`
- size: `711`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18004dea0`

## callees

- `0x180052640`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180052791`
- `ntoskrnl!ExFreePoolWithTag` at `0x180052791`
- `ntoskrnl!ExAllocatePool2` at `0x180052768`
- `ntoskrnl!ExAllocatePool2` at `0x1800527ae`
- `ntoskrnl!ExAllocatePool2` at `0x180052768`
- `ntoskrnl!ExAllocatePool2` at `0x1800527ae`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1800526e8`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x180052727`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x18005283f`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1800528ac`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1800526e8`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x180052727`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x18005283f`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1800528ac`
- `ntoskrnl!MmQuerySystemSize` at `0x180052659`
- `ntoskrnl!MmQuerySystemSize` at `0x180052659`
- `ntoskrnl!MmIsThisAnNtAsSystem` at `0x18005266e`
- `ntoskrnl!MmIsThisAnNtAsSystem` at `0x18005266e`

## pseudocode

```c
__int64 __fastcall FltpInitFrameLookasideLists(__int64 a1)
{
  MM_SYSTEMSIZE SystemSize; // eax
  USHORT Depth; // r14
  USHORT v4; // r15
  unsigned int v5; // ebx
  unsigned int v6; // r12d
  __int64 result; // rax
  struct _NPAGED_LOOKASIDE_LIST *v8; // rbx
  unsigned int v9; // ecx
  unsigned int v10; // r13d
  __int64 v11; // r12
  unsigned __int64 v12; // rsi
  struct _NPAGED_LOOKASIDE_LIST *v13; // rax
  struct _NPAGED_LOOKASIDE_LIST *v14; // rax
  unsigned int v15; // [rsp+80h] [rbp+8h]
  unsigned __int64 Size; // [rsp+88h] [rbp+10h]
  unsigned __int64 v17; // [rsp+98h] [rbp+20h]

  *(_WORD *)(a1 + 64) = 261;
  SystemSize = MmQuerySystemSize();
  if ( SystemSize == MmSmallSystem )
  {
    v4 = 6;
    goto LABEL_8;
  }
  if ( SystemSize == MmMediumSystem )
  {
    v4 = 12;
    goto LABEL_8;
  }
  if ( !MmIsThisAnNtAsSystem() )
  {
    v4 = 32;
LABEL_8:
    Depth = v4;
    goto LABEL_9;
  }
  Depth = 96;
  v4 = 128;
LABEL_9:
  v5 = *(unsigned __int8 *)(a1 + 64);
  Size = ((unsigned __int64)*(unsigned __int8 *)(a1 + 65) << 7) + 400;
  ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 1024), 0, 0, 0x200u, Size, 0x63694D46u, Depth);
  v17 = ((unsigned __int64)v5 << 7) + 400;
  ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 1152), 0, 0, 0x200u, v17, 0x63694D46u, v4);
  v15 = (dword_18003E764 + 127) & ~(dword_18003E764 - 1);
  v6 = 2 * dword_18003E760 * v15;
  result = ExAllocatePool2(64, v6, 1634487622);
  v8 = (struct _NPAGED_LOOKASIDE_LIST *)result;
  if ( result && ((dword_18003E764 - 1) & (unsigned int)result) != 0 )
  {
    ExFreePoolWithTag((PVOID)result, 0x616C4D46u);
    result = ExAllocatePool2(64, v6 + dword_18003E764, 1634487622);
    *(_QWORD *)(a1 + 696) = result;
    v8 = (struct _NPAGED_LOOKASIDE_LIST *)result;
    if ( result )
    {
      result = -(__int64)(unsigned int)dword_18003E764;
      v8 = (struct _NPAGED_LOOKASIDE_LIST *)(result
                                           & ((unsigned __int64)&v8[-1].L.Future[9] + (unsigned int)dword_18003E764 + 3));
    }
  }
  else
  {
    *(_QWORD *)(a1 + 696) = result;
  }
  v9 = dword_18003E760;
  if ( dword_18003E760 )
  {
    v10 = 0;
    do
    {
      v11 = *(_QWORD *)(a1 + 680);
      v12 = (unsigned __int64)(v10 % v9) << 6;
      if ( v8 )
      {
        ExInitializeNPagedLookasideList(v8, 0, 0, 0x200u, Size, 0x63694D46u, Depth);
        v13 = v8;
        v8 = (struct _NPAGED_LOOKASIDE_LIST *)((char *)v8 + v15);
      }
      else
      {
        v13 = (struct _NPAGED_LOOKASIDE_LIST *)(a1 + 1024);
      }
      *(_QWORD *)(v12 + v11 + 8) = a1 + 1024;
      *(_QWORD *)(v12 + v11) = v13;
      if ( v8 )
      {
        ExInitializeNPagedLookasideList(v8, 0, 0, 0x200u, v17, 0x63694D46u, v4);
        v14 = v8;
        v8 = (struct _NPAGED_LOOKASIDE_LIST *)((char *)v8 + v15);
      }
      else
      {
        v14 = (struct _NPAGED_LOOKASIDE_LIST *)(a1 + 1152);
      }
      *(_QWORD *)(v12 + v11 + 16) = v14;
      ++v10;
      result = a1 + 1152;
      *(_QWORD *)(v12 + v11 + 24) = a1 + 1152;
      v9 = dword_18003E760;
    }
    while ( v10 < dword_18003E760 );
  }
  return result;
}

```

## disassembly

```asm
0x180052640  push    rbx
0x180052642  push    rsi
0x180052643  push    rdi
0x180052644  push    r12
0x180052646  push    r13
0x180052648  push    r14
0x18005264a  push    r15
0x18005264c  sub     rsp, 40h
0x180052650  mov     rdi, rcx
0x180052653  mov     word ptr [rcx+40h], 105h
0x180052659  call    cs:__imp_MmQuerySystemSize
0x180052660  nop     dword ptr [rax+rax+00h]
0x180052665  test    eax, eax
0x180052667  jz      short loc_18005269A
0x180052669  cmp     eax, 1
0x18005266c  jz      short loc_180052692
0x18005266e  call    cs:__imp_MmIsThisAnNtAsSystem
0x180052675  nop     dword ptr [rax+rax+00h]
0x18005267a  test    al, al
0x18005267c  jz      short loc_18005268A
0x18005267e  mov     r14d, 60h ; '`'
0x180052684  lea     r15d, [r14+20h]
0x180052688  jmp     short loc_1800526A4
0x18005268a  mov     r15d, 20h ; ' '
0x180052690  jmp     short loc_1800526A0
0x180052692  mov     r15d, 0Ch
0x180052698  jmp     short loc_1800526A0
0x18005269a  mov     r15d, 6
0x1800526a0  movzx   r14d, r15w
0x1800526a4  movzx   ecx, byte ptr [rdi+41h]
0x1800526a8  mov     esi, 63694D46h
0x1800526ad  movzx   ebx, byte ptr [rdi+40h]
0x1800526b1  mov     r12d, 200h
0x1800526b7  shl     rcx, 7
0x1800526bb  mov     r9d, r12d; Flags
0x1800526be  add     rcx, 190h
0x1800526c5  mov     [rsp+78h+Depth], r14w; Depth
0x1800526cb  mov     [rsp+78h+arg_8], rcx
0x1800526d3  xor     r8d, r8d; Free
0x1800526d6  mov     [rsp+78h+Tag], esi; Tag
0x1800526da  xor     edx, edx; Allocate
0x1800526dc  mov     [rsp+78h+Size], rcx; Size
0x1800526e1  lea     rcx, [rdi+400h]; Lookaside
0x1800526e8  call    cs:__imp_ExInitializeNPagedLookasideList
0x1800526ef  nop     dword ptr [rax+rax+00h]
0x1800526f4  mov     [rsp+78h+Depth], r15w; Depth
0x1800526fa  mov     ecx, ebx
0x1800526fc  shl     rcx, 7
0x180052700  mov     r9d, r12d; Flags
0x180052703  add     rcx, 190h
0x18005270a  mov     [rsp+78h+Tag], esi; Tag
0x18005270e  mov     [rsp+78h+arg_18], rcx
0x180052716  xor     r8d, r8d; Free
0x180052719  mov     [rsp+78h+Size], rcx; Size
0x18005271e  xor     edx, edx; Allocate
0x180052720  lea     rcx, [rdi+480h]; Lookaside
0x180052727  call    cs:__imp_ExInitializeNPagedLookasideList
0x18005272e  nop     dword ptr [rax+rax+00h]
0x180052733  mov     eax, cs:dword_18003E764
0x180052739  mov     r13d, 616C4D46h
0x18005273f  mov     r8d, r13d
0x180052742  mov     ecx, 40h ; '@'
0x180052747  lea     esi, [rax-1]
0x18005274a  add     eax, 7Fh
0x18005274d  not     esi
0x18005274f  and     esi, eax
0x180052751  mov     eax, esi
0x180052753  mov     [rsp+78h+arg_0], esi
0x18005275a  imul    eax, cs:dword_18003E760
0x180052761  lea     r12d, [rax+rax]
0x180052765  mov     edx, r12d
0x180052768  call    cs:__imp_ExAllocatePool2
0x18005276f  nop     dword ptr [rax+rax+00h]
0x180052774  mov     rbx, rax
0x180052777  test    rax, rax
0x18005277a  jz      short loc_1800527DD
0x18005277c  mov     r9d, cs:dword_18003E764
0x180052783  dec     r9d
0x180052786  test    rax, r9
0x180052789  jz      short loc_1800527DD
0x18005278b  mov     edx, r13d; Tag
0x18005278e  mov     rcx, rax; P
0x180052791  call    cs:__imp_ExFreePoolWithTag
0x180052798  nop     dword ptr [rax+rax+00h]
0x18005279d  mov     edx, cs:dword_18003E764
0x1800527a3  mov     r8d, r13d
0x1800527a6  add     edx, r12d
0x1800527a9  mov     ecx, 40h ; '@'
0x1800527ae  call    cs:__imp_ExAllocatePool2
0x1800527b5  nop     dword ptr [rax+rax+00h]
0x1800527ba  mov     [rdi+2B8h], rax
0x1800527c1  mov     rbx, rax
0x1800527c4  test    rax, rax
0x1800527c7  jz      short loc_1800527E4
0x1800527c9  mov     eax, cs:dword_18003E764
0x1800527cf  dec     rbx
0x1800527d2  add     rbx, rax
0x1800527d5  neg     rax
0x1800527d8  and     rbx, rax
0x1800527db  jmp     short loc_1800527E4
0x1800527dd  mov     [rdi+2B8h], rax
0x1800527e4  mov     ecx, cs:dword_18003E760
0x1800527ea  test    ecx, ecx
0x1800527ec  jz      loc_1800528F6
0x1800527f2  xor     r13d, r13d
0x1800527f5  mov     r12, [rdi+2A8h]
0x1800527fc  xor     edx, edx
0x1800527fe  mov     eax, r13d
0x180052801  div     ecx
0x180052803  mov     esi, edx
0x180052805  shl     rsi, 6
0x180052809  test    rbx, rbx
0x18005280c  jz      short loc_18005285F
0x18005280e  mov     rax, [rsp+78h+arg_8]
0x180052816  mov     r9d, 200h; Flags
0x18005281c  mov     [rsp+78h+Depth], r14w; Depth
0x180052822  xor     r8d, r8d; Free
0x180052825  mov     [rsp+78h+Tag], 63694D46h; Tag
0x18005282d  xor     edx, edx; Allocate
0x18005282f  mov     rcx, rbx; Lookaside
0x180052832  mov     [rsp+78h+Size], rax; Size
0x180052837  mov     [rsp+78h+arg_10], rbx
0x18005283f  call    cs:__imp_ExInitializeNPagedLookasideList
0x180052846  nop     dword ptr [rax+rax+00h]
0x18005284b  mov     ecx, [rsp+78h+arg_0]
0x180052852  mov     rax, [rsp+78h+arg_10]
0x18005285a  add     rbx, rcx
0x18005285d  jmp     short loc_180052866
0x18005285f  lea     rax, [rdi+400h]
0x180052866  lea     rcx, [rdi+400h]
0x18005286d  mov     [rsi+r12+8], rcx
0x180052872  mov     [rsi+r12], rax
0x180052876  test    rbx, rbx
0x180052879  jz      short loc_1800528CC
0x18005287b  mov     rax, [rsp+78h+arg_18]
0x180052883  mov     r9d, 200h; Flags
0x180052889  mov     [rsp+78h+Depth], r15w; Depth
0x18005288f  xor     r8d, r8d; Free
0x180052892  mov     [rsp+78h+Tag], 63694D46h; Tag
0x18005289a  xor     edx, edx; Allocate
0x18005289c  mov     rcx, rbx; Lookaside
0x18005289f  mov     [rsp+78h+Size], rax; Size
0x1800528a4  mov     [rsp+78h+arg_10], rbx
0x1800528ac  call    cs:__imp_ExInitializeNPagedLookasideList
0x1800528b3  nop     dword ptr [rax+rax+00h]
0x1800528b8  mov     ecx, [rsp+78h+arg_0]
0x1800528bf  mov     rax, [rsp+78h+arg_10]
0x1800528c7  add     rbx, rcx
0x1800528ca  jmp     short loc_1800528D3
0x1800528cc  lea     rax, [rdi+480h]
0x1800528d3  mov     [rsi+r12+10h], rax
0x1800528d8  inc     r13d
0x1800528db  lea     rax, [rdi+480h]
0x1800528e2  mov     [rsi+r12+18h], rax
0x1800528e7  mov     ecx, cs:dword_18003E760
0x1800528ed  cmp     r13d, ecx
0x1800528f0  jb      loc_1800527F5
0x1800528f6  add     rsp, 40h
0x1800528fa  pop     r15
0x1800528fc  pop     r14
0x1800528fe  pop     r13
0x180052900  pop     r12
0x180052902  pop     rdi
0x180052903  pop     rsi
0x180052904  pop     rbx
0x180052905  retn
```
