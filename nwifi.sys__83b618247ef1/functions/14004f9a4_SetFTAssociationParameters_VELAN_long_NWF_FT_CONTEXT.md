# SetFTAssociationParameters(_VELAN *,long,NWF_FT_CONTEXT *)

- ea: `0x14004f9a4`
- end: `0x14004fbe6`
- name: `?SetFTAssociationParameters@@YAJPEAU_VELAN@@JPEAUNWF_FT_CONTEXT@@@Z`
- size: `578`
- prototype: `__int64 __fastcall(struct _VELAN *, int, struct NWF_FT_CONTEXT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x140041f8c`

## callees

- `0x140020dc0`
- `0x1400308ec`
- `0x140030da8`
- `0x14004f9a4`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004fa55`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004fa55`
- `ntoskrnl!ExAllocatePool2` at `0x14004fa6a`
- `ntoskrnl!ExAllocatePool2` at `0x14004fa6a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004fba7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004fba7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fbbb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fbbb`

## pseudocode

```c
__int64 __fastcall SetFTAssociationParameters(struct _VELAN *a1, int a2, struct NWF_FT_CONTEXT *a3, __int64 a4)
{
  int v4; // r12d
  int v6; // r14d
  unsigned int v7; // r15d
  unsigned int v8; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  _DWORD *Pool2; // rax
  PNPAGED_LOOKASIDE_LIST *v11; // rdi
  char *v12; // rsi
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  __int64 v15; // rcx
  unsigned int v16; // ebx
  int v19; // [rsp+68h] [rbp+10h] BYREF

  LOBYTE(v4) = 0;
  v6 = a2;
  v7 = 56;
  if ( !a2 )
  {
    if ( !a3 )
    {
      v6 = -1073741595;
      goto LABEL_11;
    }
    v4 = a3->pFTE_R0KH_IDSubElement[1];
    v7 = a3->MDDIELength + a3->FTEIELength + a3->RSNIELength + v4 + 56;
  }
  v8 = v7 + 360;
  if ( v7 + 360 < 0x10 )
    return (unsigned int)-1073741670;
  if ( v8 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_14:
    Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_16;
  }
  if ( v8 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_14;
  }
  if ( v8 <= 0x400 )
  {
LABEL_11:
    p_DeviceQueue = &Lookaside;
    goto LABEL_14;
  }
  if ( v8 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B0180;
    goto LABEL_14;
  }
  p_DeviceQueue = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, v8, 2053731191, a4);
LABEL_16:
  v11 = (PNPAGED_LOOKASIDE_LIST *)Pool2;
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  Pool2[2] = 2053731191;
  v12 = (char *)(Pool2 + 4);
  *(_QWORD *)Pool2 = p_DeviceQueue;
  memset(Pool2 + 4, 0, v7);
  *(_DWORD *)v12 = 3670400;
  *((_DWORD *)v12 + 1) = v6;
  if ( !v6 )
  {
    *(_OWORD *)(v12 + 8) = *(_OWORD *)a3->PmkR0Name;
    *((_DWORD *)v12 + 6) = (unsigned __int8)v4;
    *((_DWORD *)v12 + 7) = 56;
    memmove(v12 + 56, a3->pFTE_R0KH_IDSubElement + 2, (unsigned __int8)v4);
    v13 = (unsigned __int8)v4 + 56;
    *((_DWORD *)v12 + 9) = v13;
    *((_DWORD *)v12 + 8) = a3->RSNIELength;
    memmove(&v12[v13], a3->pRSNIE, a3->RSNIELength);
    v14 = a3->RSNIELength + v13;
    *((_DWORD *)v12 + 11) = v14;
    *((_DWORD *)v12 + 10) = a3->MDDIELength;
    memmove(&v12[v14], a3->pMDDIE, a3->MDDIELength);
    v15 = v14 + a3->MDDIELength;
    *((_DWORD *)v12 + 13) = v15;
    *((_DWORD *)v12 + 12) = a3->FTEIELength;
    memmove(&v12[v15], a3->pFTEIE, a3->FTEIELength);
  }
  v19 = NwifiSetDirectOidRequestAsync(a1->pAdapt, 234946920, v12, v7);
  MapPendingDirectOidStatus(&v19);
  v16 = v19;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      446,
      WPP_e90d411d816e312466897e39e745b158_Traceguids,
      (unsigned int)v19);
  memset(v12, 0, v7);
  if ( *v11 )
    ExFreeToNPagedLookasideList(*v11, v11);
  else
    ExFreePoolWithTag(v11, *((_DWORD *)v11 + 2));
  return v16;
}

```

## disassembly

```asm
0x14004f9a4  mov     [rsp+arg_10], rbx
0x14004f9a9  mov     [rsp+arg_0], rcx
0x14004f9ae  push    rbp
0x14004f9af  push    rsi
0x14004f9b0  push    rdi
0x14004f9b1  push    r12
0x14004f9b3  push    r13
0x14004f9b5  push    r14
0x14004f9b7  push    r15
0x14004f9b9  sub     rsp, 20h
0x14004f9bd  xor     r12b, r12b
0x14004f9c0  mov     rbp, r8
0x14004f9c3  mov     r14d, edx
0x14004f9c6  mov     esi, 7A697377h
0x14004f9cb  mov     r15d, 38h ; '8'
0x14004f9d1  test    edx, edx
0x14004f9d3  jnz     short loc_14004F9FA
0x14004f9d5  test    r8, r8
0x14004f9d8  jz      short loc_14004FA1C
0x14004f9da  mov     rax, [r8+0B8h]
0x14004f9e1  movzx   r12d, byte ptr [rax+1]
0x14004f9e6  mov     eax, [r8+3Ch]
0x14004f9ea  add     eax, [r8+38h]
0x14004f9ee  add     eax, [r8+34h]
0x14004f9f2  lea     r15d, [r12+38h]
0x14004f9f7  add     r15d, eax
0x14004f9fa  lea     eax, [r15+168h]
0x14004fa01  cmp     eax, 10h
0x14004fa04  jb      loc_14004FBC9
0x14004fa0a  mov     ecx, 40h ; '@'
0x14004fa0f  cmp     eax, ecx
0x14004fa11  ja      short loc_14004FA24
0x14004fa13  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14004fa1a  jmp     short loc_14004FA52
0x14004fa1c  mov     r14d, 0C00000E5h
0x14004fa22  jmp     short loc_14004FA3B
0x14004fa24  cmp     eax, 100h
0x14004fa29  ja      short loc_14004FA34
0x14004fa2b  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004fa32  jmp     short loc_14004FA52
0x14004fa34  cmp     eax, 400h
0x14004fa39  ja      short loc_14004FA44
0x14004fa3b  lea     rbx, Lookaside
0x14004fa42  jmp     short loc_14004FA52
0x14004fa44  cmp     eax, 800h
0x14004fa49  ja      short loc_14004FA63
0x14004fa4b  lea     rbx, stru_1400B0180
0x14004fa52  mov     rcx, rbx; Lookaside
0x14004fa55  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004fa5c  nop     dword ptr [rax+rax+00h]
0x14004fa61  jmp     short loc_14004FA76
0x14004fa63  xor     ebx, ebx
0x14004fa65  mov     edx, eax
0x14004fa67  mov     r8d, esi
0x14004fa6a  call    cs:__imp_ExAllocatePool2
0x14004fa71  nop     dword ptr [rax+rax+00h]
0x14004fa76  mov     rdi, rax
0x14004fa79  test    rax, rax
0x14004fa7c  jz      loc_14004FBC9
0x14004fa82  mov     [rax+8], esi
0x14004fa85  xor     edx, edx; Val
0x14004fa87  lea     rsi, [rax+10h]
0x14004fa8b  mov     r8d, r15d; Size
0x14004fa8e  mov     rcx, rsi; void *
0x14004fa91  mov     [rax], rbx
0x14004fa94  mov     r13d, r15d
0x14004fa97  call    memset
0x14004fa9c  mov     dword ptr [rsi], 380180h
0x14004faa2  mov     eax, 38h ; '8'
0x14004faa7  mov     [rsi+4], r14d
0x14004faab  test    r14d, r14d
0x14004faae  jnz     loc_14004FB39
0x14004fab4  movups  xmm0, xmmword ptr [rbp+68h]
0x14004fab8  movzx   ebx, r12b
0x14004fabc  lea     rcx, [rsi+38h]; void *
0x14004fac0  movzx   r8d, r12b; Size
0x14004fac4  movdqu  xmmword ptr [rsi+8], xmm0
0x14004fac9  mov     [rsi+18h], ebx
0x14004facc  mov     [rsi+1Ch], eax
0x14004facf  mov     rdx, [rbp+0B8h]
0x14004fad6  add     rdx, 2; Src
0x14004fada  call    memmove
0x14004fadf  add     ebx, 38h ; '8'
0x14004fae2  mov     [rsi+24h], ebx
0x14004fae5  mov     eax, [rbp+3Ch]
0x14004fae8  mov     [rsi+20h], eax
0x14004faeb  mov     r8d, [rbp+3Ch]; Size
0x14004faef  mov     rdx, [rbp+50h]; Src
0x14004faf3  mov     ecx, ebx
0x14004faf5  add     rcx, rsi; void *
0x14004faf8  call    memmove
0x14004fafd  add     ebx, [rbp+3Ch]
0x14004fb00  mov     [rsi+2Ch], ebx
0x14004fb03  mov     eax, [rbp+34h]
0x14004fb06  mov     [rsi+28h], eax
0x14004fb09  mov     r8d, [rbp+34h]; Size
0x14004fb0d  mov     rdx, [rbp+40h]; Src
0x14004fb11  mov     ecx, ebx
0x14004fb13  add     rcx, rsi; void *
0x14004fb16  call    memmove
0x14004fb1b  mov     ecx, [rbp+34h]
0x14004fb1e  add     ecx, ebx
0x14004fb20  mov     [rsi+34h], ecx
0x14004fb23  add     rcx, rsi; void *
0x14004fb26  mov     eax, [rbp+38h]
0x14004fb29  mov     [rsi+30h], eax
0x14004fb2c  mov     r8d, [rbp+38h]; Size
0x14004fb30  mov     rdx, [rbp+48h]; Src
0x14004fb34  call    memmove
0x14004fb39  mov     rcx, [rsp+58h+arg_0]
0x14004fb3e  mov     r9d, r15d; unsigned int
0x14004fb41  mov     r8, rsi; void *
0x14004fb44  mov     edx, 0E010168h; unsigned int
0x14004fb49  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14004fb4d  call    ?NwifiSetDirectOidRequestAsync@@YAHPEAU_ADAPT@@KPEAXK@Z; NwifiSetDirectOidRequestAsync(_ADAPT *,ulong,void *,ulong)
0x14004fb52  lea     rcx, [rsp+58h+arg_8]; int *
0x14004fb57  mov     [rsp+58h+arg_8], eax
0x14004fb5b  call    ?MapPendingDirectOidStatus@@YAXPEAH@Z; MapPendingDirectOidStatus(int *)
0x14004fb60  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fb67  lea     rax, WPP_GLOBAL_Control
0x14004fb6e  mov     ebx, [rsp+58h+arg_8]
0x14004fb72  cmp     rcx, rax
0x14004fb75  jz      short loc_14004FB8F
0x14004fb77  mov     rcx, [rcx+18h]
0x14004fb7b  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x14004fb82  mov     edx, 1BEh
0x14004fb87  mov     r9d, ebx
0x14004fb8a  call    WPP_SF_d
0x14004fb8f  mov     r8, r13; Size
0x14004fb92  xor     edx, edx; Val
0x14004fb94  mov     rcx, rsi; void *
0x14004fb97  call    memset
0x14004fb9c  mov     rcx, [rdi]; Lookaside
0x14004fb9f  test    rcx, rcx
0x14004fba2  jz      short loc_14004FBB5
0x14004fba4  mov     rdx, rdi; Entry
0x14004fba7  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004fbae  nop     dword ptr [rax+rax+00h]
0x14004fbb3  jmp     short loc_14004FBCE
0x14004fbb5  mov     edx, [rdi+8]; Tag
0x14004fbb8  mov     rcx, rdi; P
0x14004fbbb  call    cs:__imp_ExFreePoolWithTag
0x14004fbc2  nop     dword ptr [rax+rax+00h]
0x14004fbc7  jmp     short loc_14004FBCE
0x14004fbc9  mov     ebx, 0C000009Ah
0x14004fbce  mov     eax, ebx
0x14004fbd0  mov     rbx, [rsp+58h+arg_10]
0x14004fbd5  add     rsp, 20h
0x14004fbd9  pop     r15
0x14004fbdb  pop     r14
0x14004fbdd  pop     r13
0x14004fbdf  pop     r12
0x14004fbe1  pop     rdi
0x14004fbe2  pop     rsi
0x14004fbe3  pop     rbp
0x14004fbe4  retn
```
