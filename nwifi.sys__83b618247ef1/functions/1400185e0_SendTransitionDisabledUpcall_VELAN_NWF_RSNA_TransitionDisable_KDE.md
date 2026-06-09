# SendTransitionDisabledUpcall(_VELAN *,NWF_RSNA_TransitionDisable_KDE *)

- ea: `0x1400185e0`
- end: `0x140018742`
- name: `?SendTransitionDisabledUpcall@@YAJPEAU_VELAN@@PEAUNWF_RSNA_TransitionDisable_KDE@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(struct _VELAN *, struct NWF_RSNA_TransitionDisable_KDE *, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140044a48`

## callees

- `0x1400185e0`
- `0x140018a0c`
- `0x140020dc0`
- `0x14009a4c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001865d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001865d`
- `ntoskrnl!ExAllocatePool2` at `0x140018675`
- `ntoskrnl!ExAllocatePool2` at `0x140018675`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400186e0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400186e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400186f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400186f4`

## pseudocode

```c
__int64 __fastcall SendTransitionDisabledUpcall(
        struct _VELAN *a1,
        struct NWF_RSNA_TransitionDisable_KDE *a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int v4; // esi
  unsigned int v7; // ebp
  unsigned int v8; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  _DWORD *Pool2; // rax
  PNPAGED_LOOKASIDE_LIST *v11; // rdi
  char *v12; // rbx
  _FILE_OBJECT *pSecurityEndpoint; // rax
  unsigned int v14; // ebx
  __int128 v16; // [rsp+20h] [rbp-68h] BYREF
  __int128 v17; // [rsp+30h] [rbp-58h]
  __int64 v18; // [rsp+40h] [rbp-48h]

  v4 = *((unsigned __int8 *)a2 + 1);
  v18 = 0;
  v16 = 0;
  v7 = v4 - 4;
  v8 = v4 - 4 + 20;
  v17 = 0;
  if ( v8 < 0x10 )
    goto LABEL_16;
  if ( v8 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_10:
    Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_12;
  }
  if ( v8 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_10;
  }
  if ( v8 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_10;
  }
  if ( v8 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B0180;
    goto LABEL_10;
  }
  p_DeviceQueue = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, v8, 2053731191, a4);
LABEL_12:
  v11 = (PNPAGED_LOOKASIDE_LIST *)Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)Pool2 = p_DeviceQueue;
    v12 = (char *)(Pool2 + 4);
    Pool2[2] = 2053731191;
    Pool2[4] = v7;
    memmove(Pool2 + 5, (char *)a2 + 6, v7);
    pSecurityEndpoint = a1->pSecurityEndpoint;
    LODWORD(v16) = 42;
    DWORD2(v16) = v4;
    *(_QWORD *)&v17 = v12;
    v14 = NwfUpcallMsg(
            (PIO_CSQ)((char *)pSecurityEndpoint->FsContext + 40),
            (const struct DOT11_AUTH_UPCALL_REQUEST *)&v16);
    if ( *v11 )
      ExFreeToNPagedLookasideList(*v11, v11);
    else
      ExFreePoolWithTag(v11, *((_DWORD *)v11 + 2));
    return v14;
  }
LABEL_16:
  v14 = -1073741670;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 281, WPP_e90d411d816e312466897e39e745b158_Traceguids, v4);
  return v14;
}

```

## disassembly

```asm
0x1400185e0  push    rbx
0x1400185e2  push    rbp
0x1400185e3  push    rsi
0x1400185e4  push    rdi
0x1400185e5  push    r14
0x1400185e7  push    r15
0x1400185e9  sub     rsp, 58h
0x1400185ed  movzx   esi, byte ptr [rdx+1]
0x1400185f1  xor     eax, eax
0x1400185f3  xorps   xmm0, xmm0
0x1400185f6  mov     [rsp+88h+var_48], rax
0x1400185fb  mov     r14, rdx
0x1400185fe  mov     r15, rcx
0x140018601  movups  [rsp+88h+var_68], xmm0
0x140018606  lea     ebp, [rsi-4]
0x140018609  lea     eax, [rbp+14h]
0x14001860c  movups  [rsp+88h+var_58], xmm0
0x140018611  cmp     eax, 10h
0x140018614  jb      loc_140018702
0x14001861a  mov     ecx, 40h ; '@'
0x14001861f  cmp     eax, ecx
0x140018621  ja      short loc_14001862C
0x140018623  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14001862a  jmp     short loc_14001865A
0x14001862c  cmp     eax, 100h
0x140018631  ja      short loc_14001863C
0x140018633  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14001863a  jmp     short loc_14001865A
0x14001863c  cmp     eax, 400h
0x140018641  ja      short loc_14001864C
0x140018643  lea     rbx, Lookaside
0x14001864a  jmp     short loc_14001865A
0x14001864c  cmp     eax, 800h
0x140018651  ja      short loc_14001866B
0x140018653  lea     rbx, stru_1400B0180
0x14001865a  mov     rcx, rbx; Lookaside
0x14001865d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140018664  nop     dword ptr [rax+rax+00h]
0x140018669  jmp     short loc_140018681
0x14001866b  xor     ebx, ebx
0x14001866d  mov     edx, eax
0x14001866f  mov     r8d, 7A697377h
0x140018675  call    cs:__imp_ExAllocatePool2
0x14001867c  nop     dword ptr [rax+rax+00h]
0x140018681  mov     rdi, rax
0x140018684  test    rax, rax
0x140018687  jz      short loc_140018702
0x140018689  mov     [rax], rbx
0x14001868c  lea     rdx, [r14+6]; Src
0x140018690  lea     rbx, [rax+10h]
0x140018694  mov     dword ptr [rax+8], 7A697377h
0x14001869b  lea     rcx, [rbx+4]; void *
0x14001869f  mov     r8d, ebp; Size
0x1400186a2  mov     [rbx], ebp
0x1400186a4  call    memmove
0x1400186a9  mov     rax, [r15+1700h]
0x1400186b0  lea     rdx, [rsp+88h+var_68]; struct DOT11_AUTH_UPCALL_REQUEST *
0x1400186b5  mov     dword ptr [rsp+88h+var_68], 2Ah ; '*'
0x1400186bd  mov     dword ptr [rsp+88h+var_68+8], esi
0x1400186c1  mov     qword ptr [rsp+88h+var_58], rbx
0x1400186c6  mov     rcx, [rax+18h]
0x1400186ca  add     rcx, 28h ; '('; Csq
0x1400186ce  call    ?NwfUpcallMsg@@YAJPEAUNWF_AUTH_UPCALL@@PEBUDOT11_AUTH_UPCALL_REQUEST@@@Z; NwfUpcallMsg(NWF_AUTH_UPCALL *,DOT11_AUTH_UPCALL_REQUEST const *)
0x1400186d3  mov     rcx, [rdi]; Lookaside
0x1400186d6  mov     ebx, eax
0x1400186d8  test    rcx, rcx
0x1400186db  jz      short loc_1400186EE
0x1400186dd  mov     rdx, rdi; Entry
0x1400186e0  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400186e7  nop     dword ptr [rax+rax+00h]
0x1400186ec  jmp     short loc_140018732
0x1400186ee  mov     edx, [rdi+8]; Tag
0x1400186f1  mov     rcx, rdi; P
0x1400186f4  call    cs:__imp_ExFreePoolWithTag
0x1400186fb  nop     dword ptr [rax+rax+00h]
0x140018700  jmp     short loc_140018732
0x140018702  mov     ebx, 0C000009Ah
0x140018707  mov     rcx, cs:WPP_GLOBAL_Control
0x14001870e  lea     rax, WPP_GLOBAL_Control
0x140018715  cmp     rcx, rax
0x140018718  jz      short loc_140018732
0x14001871a  mov     rcx, [rcx+18h]
0x14001871e  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x140018725  mov     edx, 119h
0x14001872a  mov     r9d, esi
0x14001872d  call    WPP_SF_d
0x140018732  mov     eax, ebx
0x140018734  add     rsp, 58h
0x140018738  pop     r15
0x14001873a  pop     r14
0x14001873c  pop     rdi
0x14001873d  pop     rsi
0x14001873e  pop     rbp
0x14001873f  pop     rbx
0x140018740  retn
```
