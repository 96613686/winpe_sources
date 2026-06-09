# CClfsKernelMarshallingContext::DeallocateIocb(_LOGIOCB * const)

- ea: `0x1400577c0`
- end: `0x140057970`
- name: `?DeallocateIocb@CClfsKernelMarshallingContext@@AEAAXQEAU_LOGIOCB@@@Z`
- size: `432`
- prototype: `void __fastcall(CClfsKernelMarshallingContext *__hidden this, PVOID Entry)`
- caller_count: `12`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14000bf48`
- `0x14000df74`
- `0x1400548c4`
- `0x14005584c`
- `0x140055ef0`
- `0x1400572a0`
- `0x140058210`
- `0x1400587cc`
- `0x140058ed0`
- `0x14005935c`
- `0x14005c770`
- `0x14006e500`

## callees

- `0x14000cad0`
- `0x140016d90`
- `0x1400577c0`
- `0x14006e670`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400578f0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400578f0`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14005780a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14005786d`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14005780a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14005786d`
- `ntoskrnl!IoFreeIrp` at `0x140057901`
- `ntoskrnl!IoFreeIrp` at `0x140057901`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400578e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400578e2`

## pseudocode

```c
void __fastcall CClfsKernelMarshallingContext::DeallocateIocb(CClfsKernelMarshallingContext *this, _QWORD *Entry)
{
  int v3; // ebx
  void *v5; // rdx
  struct _PAGED_LOOKASIDE_LIST *v6; // rcx
  char v7; // bp
  IRP *v8; // rcx
  char v9; // bp
  void *v10; // rcx
  __int64 v11; // rdx
  int v12; // r8d

  v3 = *(_DWORD *)Entry;
  v5 = (void *)Entry[1];
  if ( v5 )
  {
    v6 = (struct _PAGED_LOOKASIDE_LIST *)*((_QWORD *)this + 22);
    if ( *((_DWORD *)this + 4) == 1 )
      ExFreeToPagedLookasideList(v6, v5);
    else
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v6, v5);
  }
  Entry[1] = 0;
  Entry[19] = 0;
  if ( v3 == -1040322545 )
  {
    v9 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 7, 0xFFFFFFFF) - 1;
  }
  else
  {
    v7 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 8, 0xFFFFFFFF);
    v8 = (IRP *)Entry[20];
    v9 = v7 - 1;
    if ( v8 )
    {
      IoFreeIrp(v8);
      Entry[20] = 0;
    }
    v10 = (void *)Entry[21];
    if ( v10 )
    {
      CClfsRequest::`scalar deleting destructor'(v10, (unsigned int)v5);
      Entry[21] = 0;
    }
  }
  ExFreeToPagedLookasideList(*((PPAGED_LOOKASIDE_LIST *)this + 21), Entry);
  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_slqqDddd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      13,
      v12,
      (unsigned int)"CClfsKernelMarshallingContext::DeallocateIocb",
      238,
      (char)this,
      (char)Entry,
      v3 != -1040322545,
      v9,
      *((_DWORD *)this + 10),
      *((_DWORD *)this + 46));
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 6, 0xFFFFFFFF) == 1 )
  {
    CClfsKernelMarshallingContext::~CClfsKernelMarshallingContext(this, v11);
    ExFreePoolWithTag(this, 0);
  }
}

```

## disassembly

```asm
0x1400577c0  mov     rax, rsp
0x1400577c3  push    rdi
0x1400577c4  sub     rsp, 70h
0x1400577c8  mov     [rax+10h], rbx
0x1400577cc  mov     rdi, rcx
0x1400577cf  mov     ebx, [rdx]
0x1400577d1  mov     [rax+20h], rsi
0x1400577d5  mov     rsi, rdx
0x1400577d8  mov     rdx, [rdx+8]; Entry
0x1400577dc  mov     [rax-10h], r14
0x1400577e0  mov     [rax-18h], r15
0x1400577e4  xor     r15d, r15d
0x1400577e7  cmp     ebx, 0C1FDF00Fh
0x1400577ed  mov     r14d, r15d
0x1400577f0  setnz   r14b
0x1400577f4  test    rdx, rdx
0x1400577f7  jz      short loc_140057816
0x1400577f9  cmp     dword ptr [rdi+10h], 1
0x1400577fd  mov     rcx, [rcx+0B0h]; Lookaside
0x140057804  jnz     loc_1400578F0
0x14005780a  call    cs:__imp_ExFreeToPagedLookasideList
0x140057811  nop     dword ptr [rax+rax+00h]
0x140057816  cmp     ebx, 0C1FDF00Fh
0x14005781c  mov     [rsp+78h+arg_10], rbp
0x140057824  mov     ebx, 0FFFFFFFFh
0x140057829  mov     [rsi+8], r15
0x14005782d  mov     ebp, ebx
0x14005782f  mov     [rsi+98h], r15
0x140057836  jz      loc_1400578CC
0x14005783c  lock xadd [rdi+20h], ebp
0x140057841  mov     rcx, [rsi+0A0h]; Irp
0x140057848  dec     ebp
0x14005784a  test    rcx, rcx
0x14005784d  jnz     loc_140057901
0x140057853  mov     rcx, [rsi+0A8h]; Entry
0x14005785a  test    rcx, rcx
0x14005785d  jnz     loc_140057919
0x140057863  mov     rcx, [rdi+0A8h]; Lookaside
0x14005786a  mov     rdx, rsi; Entry
0x14005786d  call    cs:__imp_ExFreeToPagedLookasideList
0x140057874  nop     dword ptr [rax+rax+00h]
0x140057879  mov     rcx, cs:WPP_GLOBAL_Control
0x140057880  lea     rax, WPP_GLOBAL_Control
0x140057887  mov     r15, [rsp+78h+var_18]
0x14005788c  cmp     rcx, rax
0x14005788f  jz      short loc_14005789E
0x140057891  test    dword ptr [rcx+2Ch], 4000000h
0x140057898  jnz     loc_14005792A
0x14005789e  lock xadd [rdi+18h], ebx
0x1400578a3  mov     r14, [rsp+78h+var_10]
0x1400578a8  cmp     ebx, 1
0x1400578ab  mov     rbx, [rsp+78h+arg_8]
0x1400578b3  mov     rsi, [rsp+78h+arg_18]
0x1400578bb  mov     rbp, [rsp+78h+arg_10]
0x1400578c3  jz      short loc_1400578D5
0x1400578c5  add     rsp, 70h
0x1400578c9  pop     rdi
0x1400578ca  retn
0x1400578cc  lock xadd [rdi+1Ch], ebp
0x1400578d1  dec     ebp
0x1400578d3  jmp     short loc_140057863
0x1400578d5  mov     rcx, rdi; this
0x1400578d8  call    ??1CClfsKernelMarshallingContext@@QEAA@XZ; CClfsKernelMarshallingContext::~CClfsKernelMarshallingContext(void)
0x1400578dd  xor     edx, edx; Tag
0x1400578df  mov     rcx, rdi; P
0x1400578e2  call    cs:__imp_ExFreePoolWithTag
0x1400578e9  nop     dword ptr [rax+rax+00h]
0x1400578ee  jmp     short loc_1400578C5
0x1400578f0  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400578f7  nop     dword ptr [rax+rax+00h]
0x1400578fc  jmp     loc_140057816
0x140057901  call    cs:__imp_IoFreeIrp
0x140057908  nop     dword ptr [rax+rax+00h]
0x14005790d  mov     [rsi+0A0h], r15
0x140057914  jmp     loc_140057853
0x140057919  call    ??_GCClfsRequest@@QEAAPEAXI@Z; CClfsRequest::`scalar deleting destructor'(uint)
0x14005791e  mov     [rsi+0A8h], r15
0x140057925  jmp     loc_140057863
0x14005792a  mov     eax, [rdi+0B8h]
0x140057930  lea     r9, aCclfskernelmar; "CClfsKernelMarshallingContext::Dealloca"...
0x140057937  mov     rcx, [rcx+18h]
0x14005793b  mov     edx, 0Dh
0x140057940  mov     [rsp+78h+var_28], eax
0x140057944  mov     eax, [rdi+28h]
0x140057947  mov     [rsp+78h+var_30], eax
0x14005794b  mov     [rsp+78h+var_38], ebp
0x14005794f  mov     [rsp+78h+var_40], r14d
0x140057954  mov     [rsp+78h+var_48], rsi
0x140057959  mov     [rsp+78h+var_50], rdi
0x14005795e  mov     [rsp+78h+var_58], 5EEh
0x140057966  call    WPP_SF_slqqDddd
0x14005796b  jmp     loc_14005789E
```
