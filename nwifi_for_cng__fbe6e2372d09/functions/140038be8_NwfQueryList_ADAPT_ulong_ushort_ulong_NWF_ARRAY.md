# NwfQueryList(_ADAPT *,ulong,ushort,ulong *,NWF_ARRAY * *)

- ea: `0x140038be8`
- end: `0x140038e48`
- name: `?NwfQueryList@@YAHPEAU_ADAPT@@KGPEAKPEAPEAUNWF_ARRAY@@@Z`
- size: `608`
- prototype: `__int64 __usercall@<rax>(struct _ADAPT *@<rcx>, unsigned int@<edx>, unsigned __int16@<r8w>, unsigned int *@<r9>, struct NWF_ARRAY **)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14006c9c0`
- `0x14006cea0`
- `0x14006d030`

## callees

- `0x14000d21c`
- `0x140015b0c`
- `0x140038be8`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140038c6d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140038c6d`
- `ntoskrnl!ExAllocatePool2` at `0x140038c88`
- `ntoskrnl!ExAllocatePool2` at `0x140038c88`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140038d5b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140038dfa`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140038d5b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140038dfa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038d72`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038e0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038d72`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038e0e`

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
      p_DeviceQueue = &stru_1400B31C0;
      goto LABEL_11;
    }
    p_DeviceQueue = 0;
    Pool2 = (_DWORD *)ExAllocatePool2(64, v10, 845771639);
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
0x140038be8  mov     rax, rsp
0x140038beb  mov     [rax+8], rbx
0x140038bef  mov     [rax+10h], rbp
0x140038bf3  mov     [rax+18h], r8w
0x140038bf8  push    rsi
0x140038bf9  push    rdi
0x140038bfa  push    r12
0x140038bfc  push    r14
0x140038bfe  push    r15
0x140038c00  sub     rsp, 40h
0x140038c04  mov     r14, r9
0x140038c07  mov     dword ptr [rax+18h], 0
0x140038c0e  mov     r15d, edx
0x140038c11  mov     dword ptr [rax-38h], 0
0x140038c18  mov     r12, rcx
0x140038c1b  mov     ebp, 0Ch
0x140038c20  xor     esi, esi
0x140038c22  lea     eax, [rbp+10h]
0x140038c25  cmp     eax, 10h
0x140038c28  jb      loc_140038E1E
0x140038c2e  cmp     eax, 40h ; '@'
0x140038c31  ja      short loc_140038C3C
0x140038c33  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x140038c3a  jmp     short loc_140038C6A
0x140038c3c  cmp     eax, 100h
0x140038c41  ja      short loc_140038C4C
0x140038c43  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140038c4a  jmp     short loc_140038C6A
0x140038c4c  cmp     eax, 400h
0x140038c51  ja      short loc_140038C5C
0x140038c53  lea     rbx, Lookaside
0x140038c5a  jmp     short loc_140038C6A
0x140038c5c  cmp     eax, 800h
0x140038c61  ja      short loc_140038C7B
0x140038c63  lea     rbx, stru_1400B31C0
0x140038c6a  mov     rcx, rbx; Lookaside
0x140038c6d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140038c74  nop     dword ptr [rax+rax+00h]
0x140038c79  jmp     short loc_140038C94
0x140038c7b  xor     ebx, ebx
0x140038c7d  mov     edx, eax
0x140038c7f  mov     r8d, 32697377h
0x140038c85  lea     ecx, [rbx+40h]
0x140038c88  call    cs:__imp_ExAllocatePool2
0x140038c8f  nop     dword ptr [rax+rax+00h]
0x140038c94  mov     rdi, rax
0x140038c97  test    rax, rax
0x140038c9a  jz      loc_140038E1E
0x140038ca0  lea     rsi, [rax+10h]
0x140038ca4  mov     [rax], rbx
0x140038ca7  mov     dword ptr [rax+8], 32697377h
0x140038cae  mov     r9d, ebp; unsigned int
0x140038cb1  lea     rax, [rsp+68h+var_38]
0x140038cb6  mov     r8, rsi; void *
0x140038cb9  mov     [rsp+68h+var_40], rax; unsigned int *
0x140038cbe  mov     edx, r15d; unsigned int
0x140038cc1  lea     rax, [rsp+68h+arg_10]
0x140038cc9  mov     rcx, r12; struct _ADAPT *
0x140038ccc  mov     [rsp+68h+var_48], rax; unsigned int *
0x140038cd1  call    ?PtQueryAdapterSyncEx@@YAHPEAU_ADAPT@@KPEAXKPEAK2@Z; PtQueryAdapterSyncEx(_ADAPT *,ulong,void *,ulong,ulong *,ulong *)
0x140038cd6  mov     ebx, eax
0x140038cd8  cmp     eax, 80000005h
0x140038cdd  jz      short loc_140038CE7
0x140038cdf  test    eax, eax
0x140038ce1  jnz     loc_140038DEA
0x140038ce7  cmp     [rsp+68h+arg_10], 0Ch
0x140038cef  mov     edx, ebp
0x140038cf1  jb      short loc_140038D3B
0x140038cf3  cmp     byte ptr [rsi], 80h
0x140038cf6  jnz     loc_140038DBD
0x140038cfc  movzx   eax, byte ptr [rsi+1]
0x140038d00  test    al, al
0x140038d02  jz      loc_140038DA3
0x140038d08  cmp     al, 1
0x140038d0a  ja      loc_140038DE5
0x140038d10  test    ebx, ebx
0x140038d12  jz      short loc_140038D83
0x140038d14  mov     ecx, [rsi+8]
0x140038d17  cmp     [rsi+4], ecx
0x140038d1a  jnb     loc_140038DE5
0x140038d20  mov     ebp, [r14+rax*4-4]
0x140038d25  imul    rbp, rcx
0x140038d29  cmp     rbp, 20000h
0x140038d30  jnb     loc_140038DE5
0x140038d36  add     ebp, 0Ch
0x140038d39  jmp     short loc_140038D3F
0x140038d3b  mov     ebp, [rsp+68h+var_38]
0x140038d3f  cmp     ebp, edx
0x140038d41  jbe     loc_140038DE5
0x140038d47  test    rsi, rsi
0x140038d4a  jz      loc_140038C20
0x140038d50  mov     rcx, [rdi]; Lookaside
0x140038d53  test    rcx, rcx
0x140038d56  jz      short loc_140038D6C
0x140038d58  mov     rdx, rdi; Entry
0x140038d5b  call    cs:__imp_ExFreeToNPagedLookasideList
0x140038d62  nop     dword ptr [rax+rax+00h]
0x140038d67  jmp     loc_140038C20
0x140038d6c  mov     edx, [rdi+8]; Tag
0x140038d6f  mov     rcx, rdi; P
0x140038d72  call    cs:__imp_ExFreePoolWithTag
0x140038d79  nop     dword ptr [rax+rax+00h]
0x140038d7e  jmp     loc_140038C20
0x140038d83  mov     ecx, [r14+rax*4-4]
0x140038d88  xor     edx, edx
0x140038d8a  mov     eax, [rsp+68h+arg_10]
0x140038d91  sub     rax, 0Ch
0x140038d95  div     rcx
0x140038d98  mov     [rsi+4], eax
0x140038d9b  mov     [rsi+8], eax
0x140038d9e  jmp     loc_140038E23
0x140038da3  mov     rcx, cs:WPP_GLOBAL_Control
0x140038daa  lea     rax, WPP_GLOBAL_Control
0x140038db1  cmp     rcx, rax
0x140038db4  jz      short loc_140038DE5
0x140038db6  mov     edx, 16h
0x140038dbb  jmp     short loc_140038DD5
0x140038dbd  mov     rcx, cs:WPP_GLOBAL_Control
0x140038dc4  lea     rax, WPP_GLOBAL_Control
0x140038dcb  cmp     rcx, rax
0x140038dce  jz      short loc_140038DE5
0x140038dd0  mov     edx, 15h
0x140038dd5  mov     rcx, [rcx+18h]
0x140038dd9  lea     r8, WPP_1a16315538383c43a34195ffa1e5eef4_Traceguids
0x140038de0  call    WPP_SF_
0x140038de5  mov     ebx, 0C0000001h
0x140038dea  test    rsi, rsi
0x140038ded  jz      short loc_140038E23
0x140038def  mov     rcx, [rdi]; Lookaside
0x140038df2  test    rcx, rcx
0x140038df5  jz      short loc_140038E08
0x140038df7  mov     rdx, rdi; Entry
0x140038dfa  call    cs:__imp_ExFreeToNPagedLookasideList
0x140038e01  nop     dword ptr [rax+rax+00h]
0x140038e06  jmp     short loc_140038E1A
0x140038e08  mov     edx, [rdi+8]; Tag
0x140038e0b  mov     rcx, rdi; P
0x140038e0e  call    cs:__imp_ExFreePoolWithTag
0x140038e15  nop     dword ptr [rax+rax+00h]
0x140038e1a  xor     esi, esi
0x140038e1c  jmp     short loc_140038E23
0x140038e1e  mov     ebx, 0C000009Ah
0x140038e23  mov     rax, [rsp+68h+arg_20]
0x140038e2b  mov     rbp, [rsp+68h+arg_8]
0x140038e30  mov     [rax], rsi
0x140038e33  mov     eax, ebx
0x140038e35  mov     rbx, [rsp+68h+arg_0]
0x140038e3a  add     rsp, 40h
0x140038e3e  pop     r15
0x140038e40  pop     r14
0x140038e42  pop     r12
0x140038e44  pop     rdi
0x140038e45  pop     rsi
0x140038e46  retn
```
