# ExtAPIoctlSetDefaultKey(_EXTAP_IOCTL_HANDLER_ENTRY const *,_EXTAP_VELAN *,_IRP *,uchar *,ulong)

- ea: `0x140071ff0`
- end: `0x1400722a9`
- name: `?ExtAPIoctlSetDefaultKey@@YAHPEBU_EXTAP_IOCTL_HANDLER_ENTRY@@PEAU_EXTAP_VELAN@@PEAU_IRP@@PEAEK@Z`
- size: `697`
- prototype: `__int64 __fastcall(const struct _EXTAP_IOCTL_HANDLER_ENTRY *, struct _EXTAP_VELAN *, struct _IRP *, unsigned __int8 *, unsigned int Size)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x14000d22c`
- `0x140019bbc`
- `0x140020dc0`
- `0x140071ff0`
- `0x14009a4c0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400720e5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400720e5`
- `ntoskrnl!ExAllocatePool2` at `0x1400720fa`
- `ntoskrnl!ExAllocatePool2` at `0x1400720fa`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400721e1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400721e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400721f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400721f5`

## pseudocode

```c
__int64 __fastcall ExtAPIoctlSetDefaultKey(
        const struct _EXTAP_IOCTL_HANDLER_ENTRY *a1,
        struct _EXTAP_VELAN *a2,
        struct _IRP *a3,
        unsigned __int8 *a4,
        unsigned int Size)
{
  unsigned int v8; // eax
  unsigned int v9; // ecx
  unsigned int v10; // edi
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // ebp
  unsigned int v14; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rdi
  _DWORD *Pool2; // rax
  PNPAGED_LOOKASIDE_LIST *v17; // rbx
  _DWORD *v18; // r14
  size_t v19; // r8
  unsigned int v20; // eax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 98, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids);
  v8 = *((_DWORD *)a1 + 6);
  v9 = *((_DWORD *)a4 + 6);
  if ( v8 + v9 < v8 )
  {
    v10 = -1073676267;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_32;
    v12 = 99;
LABEL_31:
    WPP_SF_(v11->AttachedDevice, v12, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids);
    goto LABEL_32;
  }
  if ( v9 > 0xFFFF || Size < v8 + v9 || (unsigned int)(*((_DWORD *)a4 + 1) - 1) > 7 )
  {
    v10 = -1073741811;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_32;
    v12 = 100;
    goto LABEL_31;
  }
  v13 = v9 + 22;
  v14 = v9 + 38;
  if ( v9 + 38 < 0x10 )
    goto LABEL_27;
  if ( v14 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_18:
    Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_20;
  }
  if ( v14 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_18;
  }
  if ( v14 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_18;
  }
  if ( v14 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B0180;
    goto LABEL_18;
  }
  p_DeviceQueue = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, v14, 808464432, a4);
LABEL_20:
  v17 = (PNPAGED_LOOKASIDE_LIST *)Pool2;
  if ( Pool2 )
  {
    Pool2[2] = 808464432;
    v18 = Pool2 + 4;
    *(_QWORD *)Pool2 = p_DeviceQueue;
    memset(Pool2 + 4, 0, v13);
    *v18 = 1573248;
    v18[1] = *((_DWORD *)a4 + 1) - 1;
    *((_BYTE *)v18 + 18) = *((_DWORD *)a4 + 5) != 1;
    *((_BYTE *)v18 + 19) = *(_DWORD *)a4 != 0;
    v18[2] = *((_DWORD *)a4 + 2);
    v19 = *((unsigned __int16 *)a4 + 12);
    *((_WORD *)v18 + 10) = *((_WORD *)a4 + 12);
    memmove((char *)v18 + 22, a4 + 28, v19);
    v20 = PtRequestAdapterSync(a2->pVElan->pAdapt, 1u, *((_DWORD *)a1 + 2), v18, v13);
    v10 = v20;
    if ( v20 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 102, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids, v20);
    memset(v18, 0, v13);
    if ( *v17 )
      ExFreeToNPagedLookasideList(*v17, v17);
    else
      ExFreePoolWithTag(v17, *((_DWORD *)v17 + 2));
    goto LABEL_32;
  }
LABEL_27:
  v10 = -1073741670;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 101, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids);
LABEL_32:
  memset(a4, 0, Size);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 103, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x140071ff0  push    rbx
0x140071ff2  push    rbp
0x140071ff3  push    rsi
0x140071ff4  push    rdi
0x140071ff5  push    r12
0x140071ff7  push    r13
0x140071ff9  push    r14
0x140071ffb  push    r15
0x140071ffd  sub     rsp, 38h
0x140072001  mov     rsi, r9
0x140072004  mov     r13, rdx
0x140072007  mov     r15, rcx
0x14007200a  mov     rcx, cs:WPP_GLOBAL_Control
0x140072011  lea     r8, WPP_GLOBAL_Control
0x140072018  cmp     rcx, r8
0x14007201b  jz      short loc_140072039
0x14007201d  mov     rcx, [rcx+18h]
0x140072021  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140072028  mov     edx, 62h ; 'b'
0x14007202d  call    WPP_SF_
0x140072032  lea     r8, WPP_GLOBAL_Control
0x140072039  mov     eax, [r15+18h]
0x14007203d  mov     ecx, [rsi+18h]
0x140072040  lea     edx, [rax+rcx]
0x140072043  cmp     edx, eax
0x140072045  jnb     short loc_140072066
0x140072047  mov     edi, 0C0010015h
0x14007204c  mov     rcx, cs:WPP_GLOBAL_Control
0x140072053  cmp     rcx, r8
0x140072056  jz      loc_140072258
0x14007205c  mov     edx, 63h ; 'c'
0x140072061  jmp     loc_140072248
0x140072066  cmp     ecx, 0FFFFh
0x14007206c  ja      loc_140072232
0x140072072  cmp     dword ptr [rsp+78h+Size], edx
0x140072079  jb      loc_140072232
0x14007207f  mov     eax, [rsi+4]
0x140072082  dec     eax
0x140072084  cmp     eax, 7
0x140072087  ja      loc_140072232
0x14007208d  lea     ebp, [rcx+16h]
0x140072090  lea     eax, [rbp+10h]
0x140072093  cmp     eax, 10h
0x140072096  jb      loc_140072203
0x14007209c  mov     ecx, 40h ; '@'
0x1400720a1  mov     r14d, 30303030h
0x1400720a7  cmp     eax, ecx
0x1400720a9  ja      short loc_1400720B4
0x1400720ab  lea     rdi, WPP_MAIN_CB.DeviceQueue
0x1400720b2  jmp     short loc_1400720E2
0x1400720b4  cmp     eax, 100h
0x1400720b9  ja      short loc_1400720C4
0x1400720bb  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400720c2  jmp     short loc_1400720E2
0x1400720c4  cmp     eax, 400h
0x1400720c9  ja      short loc_1400720D4
0x1400720cb  lea     rdi, Lookaside
0x1400720d2  jmp     short loc_1400720E2
0x1400720d4  cmp     eax, 800h
0x1400720d9  ja      short loc_1400720F3
0x1400720db  lea     rdi, stru_1400B0180
0x1400720e2  mov     rcx, rdi; Lookaside
0x1400720e5  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400720ec  nop     dword ptr [rax+rax+00h]
0x1400720f1  jmp     short loc_140072106
0x1400720f3  xor     edi, edi
0x1400720f5  mov     edx, eax
0x1400720f7  mov     r8d, r14d
0x1400720fa  call    cs:__imp_ExAllocatePool2
0x140072101  nop     dword ptr [rax+rax+00h]
0x140072106  mov     rbx, rax
0x140072109  test    rax, rax
0x14007210c  jz      loc_140072203
0x140072112  mov     [rax+8], r14d
0x140072116  xor     edx, edx; Val
0x140072118  lea     r14, [rax+10h]
0x14007211c  mov     r8d, ebp; Size
0x14007211f  mov     rcx, r14; void *
0x140072122  mov     [rax], rdi
0x140072125  mov     r12d, ebp
0x140072128  call    memset
0x14007212d  mov     dword ptr [r14], 180180h
0x140072134  lea     rdx, [rsi+1Ch]; Src
0x140072138  mov     eax, [rsi+4]
0x14007213b  lea     rcx, [r14+16h]; void *
0x14007213f  dec     eax
0x140072141  mov     [r14+4], eax
0x140072145  cmp     dword ptr [rsi+14h], 1
0x140072149  setnz   al
0x14007214c  mov     [r14+12h], al
0x140072150  cmp     dword ptr [rsi], 0
0x140072153  setnz   al
0x140072156  mov     [r14+13h], al
0x14007215a  mov     eax, [rsi+8]
0x14007215d  mov     [r14+8], eax
0x140072161  movzx   eax, word ptr [rsi+18h]
0x140072165  mov     r8d, eax; Size
0x140072168  mov     [r14+14h], ax
0x14007216d  call    memmove
0x140072172  mov     rcx, [r13+0]
0x140072176  mov     r9, r14; void *
0x140072179  mov     r8d, [r15+8]; unsigned int
0x14007217d  mov     edx, 1; unsigned int
0x140072182  mov     [rsp+78h+var_58], ebp; unsigned int
0x140072186  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14007218a  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x14007218f  mov     edi, eax
0x140072191  test    eax, eax
0x140072193  jz      short loc_1400721C2
0x140072195  mov     rcx, cs:WPP_GLOBAL_Control
0x14007219c  lea     rbp, WPP_GLOBAL_Control
0x1400721a3  cmp     rcx, rbp
0x1400721a6  jz      short loc_1400721C9
0x1400721a8  mov     rcx, [rcx+18h]
0x1400721ac  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x1400721b3  mov     edx, 66h ; 'f'
0x1400721b8  mov     r9d, eax
0x1400721bb  call    WPP_SF_d
0x1400721c0  jmp     short loc_1400721C9
0x1400721c2  lea     rbp, WPP_GLOBAL_Control
0x1400721c9  mov     r8, r12; Size
0x1400721cc  xor     edx, edx; Val
0x1400721ce  mov     rcx, r14; void *
0x1400721d1  call    memset
0x1400721d6  mov     rcx, [rbx]; Lookaside
0x1400721d9  test    rcx, rcx
0x1400721dc  jz      short loc_1400721EF
0x1400721de  mov     rdx, rbx; Entry
0x1400721e1  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400721e8  nop     dword ptr [rax+rax+00h]
0x1400721ed  jmp     short loc_14007225F
0x1400721ef  mov     edx, [rbx+8]; Tag
0x1400721f2  mov     rcx, rbx; P
0x1400721f5  call    cs:__imp_ExFreePoolWithTag
0x1400721fc  nop     dword ptr [rax+rax+00h]
0x140072201  jmp     short loc_14007225F
0x140072203  mov     edi, 0C000009Ah
0x140072208  mov     rcx, cs:WPP_GLOBAL_Control
0x14007220f  lea     rbp, WPP_GLOBAL_Control
0x140072216  cmp     rcx, rbp
0x140072219  jz      short loc_14007225F
0x14007221b  mov     rcx, [rcx+18h]
0x14007221f  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140072226  mov     edx, 65h ; 'e'
0x14007222b  call    WPP_SF_
0x140072230  jmp     short loc_14007225F
0x140072232  mov     edi, 0C000000Dh
0x140072237  mov     rcx, cs:WPP_GLOBAL_Control
0x14007223e  cmp     rcx, r8
0x140072241  jz      short loc_140072258
0x140072243  mov     edx, 64h ; 'd'
0x140072248  mov     rcx, [rcx+18h]
0x14007224c  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140072253  call    WPP_SF_
0x140072258  lea     rbp, WPP_GLOBAL_Control
0x14007225f  mov     r8d, dword ptr [rsp+78h+Size]; Size
0x140072267  xor     edx, edx; Val
0x140072269  mov     rcx, rsi; void *
0x14007226c  call    memset
0x140072271  mov     rcx, cs:WPP_GLOBAL_Control
0x140072278  cmp     rcx, rbp
0x14007227b  jz      short loc_140072295
0x14007227d  mov     rcx, [rcx+18h]
0x140072281  lea     r8, WPP_76a911bd7a11329cbee3f7682e4ff9c4_Traceguids
0x140072288  mov     edx, 67h ; 'g'
0x14007228d  mov     r9d, edi
0x140072290  call    WPP_SF_d
0x140072295  mov     eax, edi
0x140072297  add     rsp, 38h
0x14007229b  pop     r15
0x14007229d  pop     r14
0x14007229f  pop     r13
0x1400722a1  pop     r12
0x1400722a3  pop     rdi
0x1400722a4  pop     rsi
0x1400722a5  pop     rbp
0x1400722a6  pop     rbx
0x1400722a7  retn
```
