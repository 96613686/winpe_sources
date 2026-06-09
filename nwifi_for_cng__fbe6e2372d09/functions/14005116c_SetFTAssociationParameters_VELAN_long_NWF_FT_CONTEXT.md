# SetFTAssociationParameters(_VELAN *,long,NWF_FT_CONTEXT *)

- ea: `0x14005116c`
- end: `0x1400513ae`
- name: `?SetFTAssociationParameters@@YAJPEAU_VELAN@@JPEAUNWF_FT_CONTEXT@@@Z`
- size: `578`
- prototype: `__int64 __fastcall(struct _VELAN *, int, struct NWF_FT_CONTEXT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x140042a1c`

## callees

- `0x140020dc0`
- `0x140030b7c`
- `0x140031038`
- `0x14005116c`
- `0x14009bcc0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005121d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005121d`
- `ntoskrnl!ExAllocatePool2` at `0x140051232`
- `ntoskrnl!ExAllocatePool2` at `0x140051232`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005136f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005136f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051383`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051383`

## pseudocode

```c
__int64 __fastcall SetFTAssociationParameters(struct _VELAN *a1, int a2, struct NWF_FT_CONTEXT *a3)
{
  int v3; // r12d
  int v5; // r14d
  unsigned int v6; // r15d
  unsigned int v7; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  _DWORD *Pool2; // rax
  PNPAGED_LOOKASIDE_LIST *v10; // rdi
  char *v11; // rsi
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  __int64 v14; // rcx
  unsigned int v15; // ebx
  int v18; // [rsp+68h] [rbp+10h] BYREF

  LOBYTE(v3) = 0;
  v5 = a2;
  v6 = 56;
  if ( !a2 )
  {
    if ( !a3 )
    {
      v5 = -1073741595;
      goto LABEL_11;
    }
    v3 = a3->pFTE_R0KH_IDSubElement[1];
    v6 = a3->MDDIELength + a3->FTEIELength + a3->RSNIELength + v3 + 56;
  }
  v7 = v6 + 360;
  if ( v6 + 360 < 0x10 )
    return (unsigned int)-1073741670;
  if ( v7 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_14:
    Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_16;
  }
  if ( v7 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_14;
  }
  if ( v7 <= 0x400 )
  {
LABEL_11:
    p_DeviceQueue = &Lookaside;
    goto LABEL_14;
  }
  if ( v7 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B31C0;
    goto LABEL_14;
  }
  p_DeviceQueue = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, v7, 2053731191);
LABEL_16:
  v10 = (PNPAGED_LOOKASIDE_LIST *)Pool2;
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  Pool2[2] = 2053731191;
  v11 = (char *)(Pool2 + 4);
  *(_QWORD *)Pool2 = p_DeviceQueue;
  memset(Pool2 + 4, 0, v6);
  *(_DWORD *)v11 = 3670400;
  *((_DWORD *)v11 + 1) = v5;
  if ( !v5 )
  {
    *(_OWORD *)(v11 + 8) = *(_OWORD *)a3->PmkR0Name;
    *((_DWORD *)v11 + 6) = (unsigned __int8)v3;
    *((_DWORD *)v11 + 7) = 56;
    memmove(v11 + 56, a3->pFTE_R0KH_IDSubElement + 2, (unsigned __int8)v3);
    v12 = (unsigned __int8)v3 + 56;
    *((_DWORD *)v11 + 9) = v12;
    *((_DWORD *)v11 + 8) = a3->RSNIELength;
    memmove(&v11[v12], a3->pRSNIE, a3->RSNIELength);
    v13 = a3->RSNIELength + v12;
    *((_DWORD *)v11 + 11) = v13;
    *((_DWORD *)v11 + 10) = a3->MDDIELength;
    memmove(&v11[v13], a3->pMDDIE, a3->MDDIELength);
    v14 = v13 + a3->MDDIELength;
    *((_DWORD *)v11 + 13) = v14;
    *((_DWORD *)v11 + 12) = a3->FTEIELength;
    memmove(&v11[v14], a3->pFTEIE, a3->FTEIELength);
  }
  v18 = NwifiSetDirectOidRequestAsync(a1->pAdapt, 0xE010168u, v11, v6);
  MapPendingDirectOidStatus(&v18);
  v15 = v18;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      463,
      WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
      (unsigned int)v18);
  memset(v11, 0, v6);
  if ( *v10 )
    ExFreeToNPagedLookasideList(*v10, v10);
  else
    ExFreePoolWithTag(v10, *((_DWORD *)v10 + 2));
  return v15;
}

```

## disassembly

```asm
0x14005116c  mov     [rsp+arg_10], rbx
0x140051171  mov     [rsp+arg_0], rcx
0x140051176  push    rbp
0x140051177  push    rsi
0x140051178  push    rdi
0x140051179  push    r12
0x14005117b  push    r13
0x14005117d  push    r14
0x14005117f  push    r15
0x140051181  sub     rsp, 20h
0x140051185  xor     r12b, r12b
0x140051188  mov     rbp, r8
0x14005118b  mov     r14d, edx
0x14005118e  mov     esi, 7A697377h
0x140051193  mov     r15d, 38h ; '8'
0x140051199  test    edx, edx
0x14005119b  jnz     short loc_1400511C2
0x14005119d  test    r8, r8
0x1400511a0  jz      short loc_1400511E4
0x1400511a2  mov     rax, [r8+0B8h]
0x1400511a9  movzx   r12d, byte ptr [rax+1]
0x1400511ae  mov     eax, [r8+3Ch]
0x1400511b2  add     eax, [r8+38h]
0x1400511b6  add     eax, [r8+34h]
0x1400511ba  lea     r15d, [r12+38h]
0x1400511bf  add     r15d, eax
0x1400511c2  lea     eax, [r15+168h]
0x1400511c9  cmp     eax, 10h
0x1400511cc  jb      loc_140051391
0x1400511d2  mov     ecx, 40h ; '@'
0x1400511d7  cmp     eax, ecx
0x1400511d9  ja      short loc_1400511EC
0x1400511db  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x1400511e2  jmp     short loc_14005121A
0x1400511e4  mov     r14d, 0C00000E5h
0x1400511ea  jmp     short loc_140051203
0x1400511ec  cmp     eax, 100h
0x1400511f1  ja      short loc_1400511FC
0x1400511f3  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400511fa  jmp     short loc_14005121A
0x1400511fc  cmp     eax, 400h
0x140051201  ja      short loc_14005120C
0x140051203  lea     rbx, Lookaside
0x14005120a  jmp     short loc_14005121A
0x14005120c  cmp     eax, 800h
0x140051211  ja      short loc_14005122B
0x140051213  lea     rbx, stru_1400B31C0
0x14005121a  mov     rcx, rbx; Lookaside
0x14005121d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140051224  nop     dword ptr [rax+rax+00h]
0x140051229  jmp     short loc_14005123E
0x14005122b  xor     ebx, ebx
0x14005122d  mov     edx, eax
0x14005122f  mov     r8d, esi
0x140051232  call    cs:__imp_ExAllocatePool2
0x140051239  nop     dword ptr [rax+rax+00h]
0x14005123e  mov     rdi, rax
0x140051241  test    rax, rax
0x140051244  jz      loc_140051391
0x14005124a  mov     [rax+8], esi
0x14005124d  xor     edx, edx; Val
0x14005124f  lea     rsi, [rax+10h]
0x140051253  mov     r8d, r15d; Size
0x140051256  mov     rcx, rsi; void *
0x140051259  mov     [rax], rbx
0x14005125c  mov     r13d, r15d
0x14005125f  call    memset
0x140051264  mov     dword ptr [rsi], 380180h
0x14005126a  mov     eax, 38h ; '8'
0x14005126f  mov     [rsi+4], r14d
0x140051273  test    r14d, r14d
0x140051276  jnz     loc_140051301
0x14005127c  movups  xmm0, xmmword ptr [rbp+68h]
0x140051280  movzx   ebx, r12b
0x140051284  lea     rcx, [rsi+38h]; void *
0x140051288  movzx   r8d, r12b; Size
0x14005128c  movdqu  xmmword ptr [rsi+8], xmm0
0x140051291  mov     [rsi+18h], ebx
0x140051294  mov     [rsi+1Ch], eax
0x140051297  mov     rdx, [rbp+0B8h]
0x14005129e  add     rdx, 2; Src
0x1400512a2  call    memmove
0x1400512a7  add     ebx, 38h ; '8'
0x1400512aa  mov     [rsi+24h], ebx
0x1400512ad  mov     eax, [rbp+3Ch]
0x1400512b0  mov     [rsi+20h], eax
0x1400512b3  mov     r8d, [rbp+3Ch]; Size
0x1400512b7  mov     rdx, [rbp+50h]; Src
0x1400512bb  mov     ecx, ebx
0x1400512bd  add     rcx, rsi; void *
0x1400512c0  call    memmove
0x1400512c5  add     ebx, [rbp+3Ch]
0x1400512c8  mov     [rsi+2Ch], ebx
0x1400512cb  mov     eax, [rbp+34h]
0x1400512ce  mov     [rsi+28h], eax
0x1400512d1  mov     r8d, [rbp+34h]; Size
0x1400512d5  mov     rdx, [rbp+40h]; Src
0x1400512d9  mov     ecx, ebx
0x1400512db  add     rcx, rsi; void *
0x1400512de  call    memmove
0x1400512e3  mov     ecx, [rbp+34h]
0x1400512e6  add     ecx, ebx
0x1400512e8  mov     [rsi+34h], ecx
0x1400512eb  add     rcx, rsi; void *
0x1400512ee  mov     eax, [rbp+38h]
0x1400512f1  mov     [rsi+30h], eax
0x1400512f4  mov     r8d, [rbp+38h]; Size
0x1400512f8  mov     rdx, [rbp+48h]; Src
0x1400512fc  call    memmove
0x140051301  mov     rcx, [rsp+58h+arg_0]
0x140051306  mov     r9d, r15d; unsigned int
0x140051309  mov     r8, rsi; void *
0x14005130c  mov     edx, 0E010168h; unsigned int
0x140051311  mov     rcx, [rcx+10h]; struct _ADAPT *
0x140051315  call    ?NwifiSetDirectOidRequestAsync@@YAHPEAU_ADAPT@@KPEAXK@Z; NwifiSetDirectOidRequestAsync(_ADAPT *,ulong,void *,ulong)
0x14005131a  lea     rcx, [rsp+58h+arg_8]; int *
0x14005131f  mov     [rsp+58h+arg_8], eax
0x140051323  call    ?MapPendingDirectOidStatus@@YAXPEAH@Z; MapPendingDirectOidStatus(int *)
0x140051328  mov     rcx, cs:WPP_GLOBAL_Control
0x14005132f  lea     rax, WPP_GLOBAL_Control
0x140051336  mov     ebx, [rsp+58h+arg_8]
0x14005133a  cmp     rcx, rax
0x14005133d  jz      short loc_140051357
0x14005133f  mov     rcx, [rcx+18h]
0x140051343  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14005134a  mov     edx, 1CFh
0x14005134f  mov     r9d, ebx
0x140051352  call    WPP_SF_d
0x140051357  mov     r8, r13; Size
0x14005135a  xor     edx, edx; Val
0x14005135c  mov     rcx, rsi; void *
0x14005135f  call    memset
0x140051364  mov     rcx, [rdi]; Lookaside
0x140051367  test    rcx, rcx
0x14005136a  jz      short loc_14005137D
0x14005136c  mov     rdx, rdi; Entry
0x14005136f  call    cs:__imp_ExFreeToNPagedLookasideList
0x140051376  nop     dword ptr [rax+rax+00h]
0x14005137b  jmp     short loc_140051396
0x14005137d  mov     edx, [rdi+8]; Tag
0x140051380  mov     rcx, rdi; P
0x140051383  call    cs:__imp_ExFreePoolWithTag
0x14005138a  nop     dword ptr [rax+rax+00h]
0x14005138f  jmp     short loc_140051396
0x140051391  mov     ebx, 0C000009Ah
0x140051396  mov     eax, ebx
0x140051398  mov     rbx, [rsp+58h+arg_10]
0x14005139d  add     rsp, 20h
0x1400513a1  pop     r15
0x1400513a3  pop     r14
0x1400513a5  pop     r13
0x1400513a7  pop     r12
0x1400513a9  pop     rdi
0x1400513aa  pop     rsi
0x1400513ab  pop     rbp
0x1400513ac  retn
```
