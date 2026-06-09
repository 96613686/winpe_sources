# NwfQueryList(_ADAPT *,ulong,ushort,ulong *,NWF_ARRAY * *)

- ea: `0x1400389c8`
- end: `0x140038c28`
- name: `?NwfQueryList@@YAHPEAU_ADAPT@@KGPEAKPEAPEAUNWF_ARRAY@@@Z`
- size: `608`
- prototype: `__int64 __usercall@<rax>(struct _ADAPT *@<rcx>, unsigned int@<edx>, unsigned __int16@<r8w>, unsigned int *@<r9>, struct NWF_ARRAY **)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14006b190`
- `0x14006b670`
- `0x14006b800`

## callees

- `0x14000d22c`
- `0x140015b1c`
- `0x1400389c8`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140038a4d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140038a4d`
- `ntoskrnl!ExAllocatePool2` at `0x140038a68`
- `ntoskrnl!ExAllocatePool2` at `0x140038a68`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140038b3b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140038bda`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140038b3b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140038bda`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038b52`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038bee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038b52`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038bee`

## pseudocode

```c
__int64 __fastcall NwfQueryList(
        struct _ADAPT *a1,
        unsigned int a2,
        __int64 a3,
        unsigned int *a4,
        struct NWF_ARRAY **a5)
{
  unsigned int v8; // ebp
  char *v9; // rsi
  unsigned int v10; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  _DWORD *Pool2; // rax
  PNPAGED_LOOKASIDE_LIST *v13; // rdi
  unsigned int v14; // eax
  unsigned int v15; // ebx
  unsigned int v16; // edx
  __int64 v17; // rax
  __int64 v18; // rcx
  unsigned __int64 v19; // rbp
  unsigned __int64 v20; // rax
  PDEVICE_OBJECT v21; // rcx
  __int64 v22; // rdx
  unsigned int v24[14]; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v25; // [rsp+80h] [rbp+18h] BYREF

  v25 = 0;
  v24[0] = 0;
  v8 = 12;
  while ( 1 )
  {
    v9 = 0;
    v10 = v8 + 16;
    if ( v8 >= 0xFFFFFFF0 )
    {
LABEL_42:
      v15 = -1073741670;
      goto LABEL_43;
    }
    if ( v10 <= 0x40 )
    {
      p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_11:
      Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
      goto LABEL_13;
    }
    if ( v10 <= 0x100 )
    {
      p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      goto LABEL_11;
    }
    if ( v10 <= 0x400 )
    {
      p_DeviceQueue = &Lookaside;
      goto LABEL_11;
    }
    if ( v10 <= 0x800 )
    {
      p_DeviceQueue = &stru_1400B0180;
      goto LABEL_11;
    }
    p_DeviceQueue = 0;
    Pool2 = (_DWORD *)ExAllocatePool2(64, v10, 845771639, a4);
LABEL_13:
    v13 = (PNPAGED_LOOKASIDE_LIST *)Pool2;
    if ( !Pool2 )
      goto LABEL_42;
    v9 = (char *)(Pool2 + 4);
    *(_QWORD *)Pool2 = p_DeviceQueue;
    Pool2[2] = 845771639;
    v14 = PtQueryAdapterSyncEx(a1, a2, Pool2 + 4, v8, &v25, v24);
    v15 = v14;
    if ( v14 != -2147483643 && v14 )
      goto LABEL_37;
    v16 = v8;
    if ( v25 < 0xC )
    {
      v8 = v24[0];
      goto LABEL_25;
    }
    if ( *v9 != (char)0x80 )
      break;
    v17 = (unsigned __int8)v9[1];
    if ( !(_BYTE)v17 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_36;
      v22 = 22;
      goto LABEL_35;
    }
    if ( (unsigned __int8)v17 > 1u )
      goto LABEL_36;
    if ( !v15 )
    {
      v20 = ((unsigned __int64)v25 - 12) / a4[v17 - 1];
      *((_DWORD *)v9 + 1) = v20;
      *((_DWORD *)v9 + 2) = v20;
      goto LABEL_43;
    }
    v18 = *((unsigned int *)v9 + 2);
    if ( *((_DWORD *)v9 + 1) >= (unsigned int)v18 )
      goto LABEL_36;
    v19 = v18 * a4[v17 - 1];
    if ( v19 >= 0x20000 )
      goto LABEL_36;
    v8 = v19 + 12;
LABEL_25:
    if ( v8 <= v16 )
      goto LABEL_36;
    if ( v9 )
    {
      if ( *v13 )
        ExFreeToNPagedLookasideList(*v13, v13);
      else
        ExFreePoolWithTag(v13, *((_DWORD *)v13 + 2));
    }
  }
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_36;
  v22 = 21;
LABEL_35:
  WPP_SF_(v21->AttachedDevice, v22, WPP_1a16315538383c43a34195ffa1e5eef4_Traceguids);
LABEL_36:
  v15 = -1073741823;
LABEL_37:
  if ( v9 )
  {
    if ( *v13 )
      ExFreeToNPagedLookasideList(*v13, v13);
    else
      ExFreePoolWithTag(v13, *((_DWORD *)v13 + 2));
    v9 = 0;
  }
LABEL_43:
  *a5 = (struct NWF_ARRAY *)v9;
  return v15;
}

```

## disassembly

```asm
0x1400389c8  mov     rax, rsp
0x1400389cb  mov     [rax+8], rbx
0x1400389cf  mov     [rax+10h], rbp
0x1400389d3  mov     [rax+18h], r8w
0x1400389d8  push    rsi
0x1400389d9  push    rdi
0x1400389da  push    r12
0x1400389dc  push    r14
0x1400389de  push    r15
0x1400389e0  sub     rsp, 40h
0x1400389e4  mov     r14, r9
0x1400389e7  mov     dword ptr [rax+18h], 0
0x1400389ee  mov     r15d, edx
0x1400389f1  mov     dword ptr [rax-38h], 0
0x1400389f8  mov     r12, rcx
0x1400389fb  mov     ebp, 0Ch
0x140038a00  xor     esi, esi
0x140038a02  lea     eax, [rbp+10h]
0x140038a05  cmp     eax, 10h
0x140038a08  jb      loc_140038BFE
0x140038a0e  cmp     eax, 40h ; '@'
0x140038a11  ja      short loc_140038A1C
0x140038a13  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140038a1a  jmp     short loc_140038A4A
0x140038a1c  cmp     eax, 100h
0x140038a21  ja      short loc_140038A2C
0x140038a23  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140038a2a  jmp     short loc_140038A4A
0x140038a2c  cmp     eax, 400h
0x140038a31  ja      short loc_140038A3C
0x140038a33  lea     rbx, Lookaside
0x140038a3a  jmp     short loc_140038A4A
0x140038a3c  cmp     eax, 800h
0x140038a41  ja      short loc_140038A5B
0x140038a43  lea     rbx, stru_1400B0180
0x140038a4a  mov     rcx, rbx; Lookaside
0x140038a4d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140038a54  nop     dword ptr [rax+rax+00h]
0x140038a59  jmp     short loc_140038A74
0x140038a5b  xor     ebx, ebx
0x140038a5d  mov     edx, eax
0x140038a5f  mov     r8d, 32697377h
0x140038a65  lea     ecx, [rbx+40h]
0x140038a68  call    cs:__imp_ExAllocatePool2
0x140038a6f  nop     dword ptr [rax+rax+00h]
0x140038a74  mov     rdi, rax
0x140038a77  test    rax, rax
0x140038a7a  jz      loc_140038BFE
0x140038a80  lea     rsi, [rax+10h]
0x140038a84  mov     [rax], rbx
0x140038a87  mov     dword ptr [rax+8], 32697377h
0x140038a8e  mov     r9d, ebp; unsigned int
0x140038a91  lea     rax, [rsp+68h+var_38]
0x140038a96  mov     r8, rsi; void *
0x140038a99  mov     [rsp+68h+var_40], rax; unsigned int *
0x140038a9e  mov     edx, r15d; unsigned int
0x140038aa1  lea     rax, [rsp+68h+arg_10]
0x140038aa9  mov     rcx, r12; struct _ADAPT *
0x140038aac  mov     [rsp+68h+var_48], rax; unsigned int *
0x140038ab1  call    ?PtQueryAdapterSyncEx@@YAHPEAU_ADAPT@@KPEAXKPEAK2@Z; PtQueryAdapterSyncEx(_ADAPT *,ulong,void *,ulong,ulong *,ulong *)
0x140038ab6  mov     ebx, eax
0x140038ab8  cmp     eax, 80000005h
0x140038abd  jz      short loc_140038AC7
0x140038abf  test    eax, eax
0x140038ac1  jnz     loc_140038BCA
0x140038ac7  cmp     [rsp+68h+arg_10], 0Ch
0x140038acf  mov     edx, ebp
0x140038ad1  jb      short loc_140038B1B
0x140038ad3  cmp     byte ptr [rsi], 80h
0x140038ad6  jnz     loc_140038B9D
0x140038adc  movzx   eax, byte ptr [rsi+1]
0x140038ae0  test    al, al
0x140038ae2  jz      loc_140038B83
0x140038ae8  cmp     al, 1
0x140038aea  ja      loc_140038BC5
0x140038af0  test    ebx, ebx
0x140038af2  jz      short loc_140038B63
0x140038af4  mov     ecx, [rsi+8]
0x140038af7  cmp     [rsi+4], ecx
0x140038afa  jnb     loc_140038BC5
0x140038b00  mov     ebp, [r14+rax*4-4]
0x140038b05  imul    rbp, rcx
0x140038b09  cmp     rbp, 20000h
0x140038b10  jnb     loc_140038BC5
0x140038b16  add     ebp, 0Ch
0x140038b19  jmp     short loc_140038B1F
0x140038b1b  mov     ebp, [rsp+68h+var_38]
0x140038b1f  cmp     ebp, edx
0x140038b21  jbe     loc_140038BC5
0x140038b27  test    rsi, rsi
0x140038b2a  jz      loc_140038A00
0x140038b30  mov     rcx, [rdi]; Lookaside
0x140038b33  test    rcx, rcx
0x140038b36  jz      short loc_140038B4C
0x140038b38  mov     rdx, rdi; Entry
0x140038b3b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140038b42  nop     dword ptr [rax+rax+00h]
0x140038b47  jmp     loc_140038A00
0x140038b4c  mov     edx, [rdi+8]; Tag
0x140038b4f  mov     rcx, rdi; P
0x140038b52  call    cs:__imp_ExFreePoolWithTag
0x140038b59  nop     dword ptr [rax+rax+00h]
0x140038b5e  jmp     loc_140038A00
0x140038b63  mov     ecx, [r14+rax*4-4]
0x140038b68  xor     edx, edx
0x140038b6a  mov     eax, [rsp+68h+arg_10]
0x140038b71  sub     rax, 0Ch
0x140038b75  div     rcx
0x140038b78  mov     [rsi+4], eax
0x140038b7b  mov     [rsi+8], eax
0x140038b7e  jmp     loc_140038C03
0x140038b83  mov     rcx, cs:WPP_GLOBAL_Control
0x140038b8a  lea     rax, WPP_GLOBAL_Control
0x140038b91  cmp     rcx, rax
0x140038b94  jz      short loc_140038BC5
0x140038b96  mov     edx, 16h
0x140038b9b  jmp     short loc_140038BB5
0x140038b9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140038ba4  lea     rax, WPP_GLOBAL_Control
0x140038bab  cmp     rcx, rax
0x140038bae  jz      short loc_140038BC5
0x140038bb0  mov     edx, 15h
0x140038bb5  mov     rcx, [rcx+18h]
0x140038bb9  lea     r8, WPP_1a16315538383c43a34195ffa1e5eef4_Traceguids
0x140038bc0  call    WPP_SF_
0x140038bc5  mov     ebx, 0C0000001h
0x140038bca  test    rsi, rsi
0x140038bcd  jz      short loc_140038C03
0x140038bcf  mov     rcx, [rdi]; Lookaside
0x140038bd2  test    rcx, rcx
0x140038bd5  jz      short loc_140038BE8
0x140038bd7  mov     rdx, rdi; Entry
0x140038bda  call    cs:__imp_ExFreeToNPagedLookasideList
0x140038be1  nop     dword ptr [rax+rax+00h]
0x140038be6  jmp     short loc_140038BFA
0x140038be8  mov     edx, [rdi+8]; Tag
0x140038beb  mov     rcx, rdi; P
0x140038bee  call    cs:__imp_ExFreePoolWithTag
0x140038bf5  nop     dword ptr [rax+rax+00h]
0x140038bfa  xor     esi, esi
0x140038bfc  jmp     short loc_140038C03
0x140038bfe  mov     ebx, 0C000009Ah
0x140038c03  mov     rax, [rsp+68h+arg_20]
0x140038c0b  mov     rbp, [rsp+68h+arg_8]
0x140038c10  mov     [rax], rsi
0x140038c13  mov     eax, ebx
0x140038c15  mov     rbx, [rsp+68h+arg_0]
0x140038c1a  add     rsp, 40h
0x140038c1e  pop     r15
0x140038c20  pop     r14
0x140038c22  pop     r12
0x140038c24  pop     rdi
0x140038c25  pop     rsi
0x140038c26  retn
```
