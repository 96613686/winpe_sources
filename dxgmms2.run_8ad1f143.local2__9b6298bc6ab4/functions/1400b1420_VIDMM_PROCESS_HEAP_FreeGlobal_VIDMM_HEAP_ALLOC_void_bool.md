# VIDMM_PROCESS_HEAP::FreeGlobal(VIDMM_HEAP_ALLOC *,void *,bool)

- ea: `0x1400b1420`
- end: `0x1400b169f`
- name: `?FreeGlobal@VIDMM_PROCESS_HEAP@@UEAAXPEAUVIDMM_HEAP_ALLOC@@PEAX_N@Z`
- size: `639`
- prototype: `void __fastcall(VIDMM_PROCESS_HEAP *__hidden this, PVOID Entry, void *, bool)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation`

## callees

- `0x140013434`
- `0x140031934`
- `0x1400335c4`
- `0x1400336b8`
- `0x14003bbcc`
- `0x140058680`
- `0x140058760`
- `0x1400b1420`
- `0x1400d2abc`
- `0x140109708`

## import_xrefs

- `ntoskrnl!MmUnsecureVirtualMemory` at `0x1400b1561`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x1400b1561`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x1400b14de`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x1400b14de`
- `ntoskrnl!ObCloseHandle` at `0x1400b14f8`
- `ntoskrnl!ObCloseHandle` at `0x1400b14f8`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400b1657`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400b1657`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b1461`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b1461`
- `watchdog!WdLogSingleEntry5` at `0x1400b149f`
- `watchdog!WdLogSingleEntry5` at `0x1400b149f`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400b1472`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
void __fastcall VIDMM_PROCESS_HEAP::FreeGlobal(VIDMM_PROCESS_HEAP *this, PVOID *Entry, void *a3)
{
  __int64 v5; // rbx
  __int64 v6; // rcx
  PVOID *v7; // r14
  int v8; // ecx
  int v9; // r8d
  __int64 *v10; // rbx
  int v11; // eax
  _QWORD *v12; // rcx
  _QWORD *v13; // rcx
  const struct DXGK_VIRTUAL_MEMORY_INTERFACE *VirtualMemoryInterface; // rax
  bool v15; // zf
  __int64 v16; // rax
  PVOID v17; // rax
  int v18; // ecx
  PVOID v19; // r9
  __int64 v20; // [rsp+20h] [rbp-88h]
  __int64 v21; // [rsp+28h] [rbp-80h]
  _BYTE v22[64]; // [rsp+40h] [rbp-68h] BYREF

  VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH(
    (VIDMM_PROCESS_AUTOATTACH *)v22,
    *((struct VIDMM_PROCESS **)this + 1),
    1);
  v5 = *(_QWORD *)(*((_QWORD *)this + 1) + 16LL);
  if ( PsGetCurrentProcess(v6) != v5 )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    v21 = 0;
    v20 = 0;
    WdLogSingleEntry5(0, 270, 30);
    WdLogGlobalForLineNumber = 222;
  }
  if ( (*(_DWORD *)Entry & 1) == 0 )
  {
    VIDMM_PROCESS_HEAP::FreeSmallAllocation(this, Entry);
    goto LABEL_26;
  }
  v7 = Entry + 1;
  v8 = *((_DWORD *)Entry + 6);
  if ( (unsigned int)(v8 - 3) > 1 )
  {
    if ( (unsigned int)(v8 - 5) > 1 )
    {
      MmUnsecureVirtualMemory(Entry[6]);
      v10 = (__int64 *)(Entry + 7);
      VirtualMemoryInterface = DxgkGetVirtualMemoryInterface();
      (*((void (__fastcall **)(__int64, char *, char *, __int64, __int64, __int64))VirtualMemoryInterface + 2))(
        -1,
        (char *)Entry + 8,
        (char *)Entry + 56,
        0x8000,
        v20,
        v21);
      goto LABEL_8;
    }
    MmUnmapViewInSystemSpace(*v7);
  }
  ObCloseHandle(Entry[5], ((unsigned __int64)Entry[5] & 0xFFFFFFFF80000000uLL) == 0);
  VidMmDereferenceObjectAsync(Entry[4]);
  v10 = (__int64 *)(Entry + 7);
LABEL_8:
  *(_QWORD *)(*((_QWORD *)this + 1) + 184LL) -= *v10;
  *(_QWORD *)(*((_QWORD *)this + 1) + 176LL) -= *v10;
  --*(_DWORD *)(*((_QWORD *)this + 1) + 196LL);
  v11 = *((_DWORD *)Entry + 6);
  v12 = (_QWORD *)*((_QWORD *)this + 1);
  if ( v11 == 1 )
  {
    v12[25] -= *v10;
    v13 = (_QWORD *)*((_QWORD *)this + 1);
    v13[26] -= *v10;
  }
  else
  {
    v15 = v11 == 2;
    v16 = *v10;
    if ( v15 )
    {
      v12[27] -= v16;
      v13 = (_QWORD *)*((_QWORD *)this + 1);
      v13[28] -= *v10;
    }
    else
    {
      v12[29] -= v16;
      v13 = (_QWORD *)*((_QWORD *)this + 1);
      v13[30] -= *v10;
    }
  }
  if ( (byte_140086201 & 0x10) != 0 )
  {
    if ( (unsigned int)(*((_DWORD *)Entry + 6) - 3) > 3 )
      v17 = *v7;
    else
      v17 = Entry[4];
    McTemplateK0qxxx_EtwWriteTransfer(
      (_DWORD)v13,
      (unsigned int)EventDestroyProcessAllocationDetails,
      v9,
      *(_DWORD *)(*((_QWORD *)this + 1) + 24LL),
      (char)Entry,
      *v10,
      (char)v17);
  }
  if ( (byte_140086202 & 4) != 0 )
  {
    v18 = *((_DWORD *)Entry + 6);
    if ( (unsigned int)(v18 - 3) > 3 )
      v19 = *v7;
    else
      v19 = Entry[4];
    McTemplateK0pxqqt_EtwWriteTransfer(
      v18,
      (unsigned int)EventDestroyProcessAllocation,
      *v10,
      (_DWORD)v19,
      *v10,
      v18,
      *(_DWORD *)(*((_QWORD *)this + 1) + 24LL),
      0);
  }
  ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)this + 64), Entry);
LABEL_26:
  VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH((VIDMM_PROCESS_AUTOATTACH *)v22);
}

```

## disassembly

```asm
0x1400b1420  mov     [rsp+arg_10], rbx
0x1400b1425  push    rsi
0x1400b1426  push    rdi
0x1400b1427  push    r14
0x1400b1429  sub     rsp, 90h
0x1400b1430  mov     rax, cs:__security_cookie
0x1400b1437  xor     rax, rsp
0x1400b143a  mov     [rsp+0A8h+var_28], rax
0x1400b1442  mov     rdi, rdx
0x1400b1445  mov     rsi, rcx
0x1400b1448  mov     rdx, [rcx+8]; struct VIDMM_PROCESS *
0x1400b144c  mov     r8b, 1; bool
0x1400b144f  lea     rcx, [rsp+0A8h+var_68]; this
0x1400b1454  call    ??0VIDMM_PROCESS_AUTOATTACH@@QEAA@PEAVVIDMM_PROCESS@@_N@Z; VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH(VIDMM_PROCESS *,bool)
0x1400b1459  mov     rax, [rsi+8]
0x1400b145d  mov     rbx, [rax+10h]
0x1400b1461  call    cs:__imp_PsGetCurrentProcess
0x1400b1468  nop     dword ptr [rax+rax+00h]
0x1400b146d  cmp     rax, rbx
0x1400b1470  jz      short loc_1400B14B5
0x1400b1472  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400b1479  mov     dword ptr [rax], 1
0x1400b147f  xor     r9d, r9d
0x1400b1482  mov     [rsp+0A8h+var_80], 0
0x1400b148b  mov     edx, 10Eh
0x1400b1490  mov     [rsp+0A8h+var_88], 0
0x1400b1499  xor     ecx, ecx
0x1400b149b  lea     r8d, [r9+1Eh]
0x1400b149f  call    cs:__imp_WdLogSingleEntry5
0x1400b14a6  nop     dword ptr [rax+rax+00h]
0x1400b14ab  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x1400b14b5  mov     eax, [rdi]
0x1400b14b7  test    al, 1
0x1400b14b9  jz      loc_1400B1665
0x1400b14bf  lea     r14, [rdi+8]
0x1400b14c3  mov     ecx, [r14+10h]
0x1400b14c7  lea     eax, [rcx-3]
0x1400b14ca  cmp     eax, 1
0x1400b14cd  jbe     short loc_1400B14EA
0x1400b14cf  lea     eax, [rcx-5]
0x1400b14d2  cmp     eax, 1
0x1400b14d5  ja      loc_1400B155D
0x1400b14db  mov     rcx, [r14]; MappedBase
0x1400b14de  call    cs:__imp_MmUnmapViewInSystemSpace
0x1400b14e5  nop     dword ptr [rax+rax+00h]
0x1400b14ea  mov     rcx, [rdi+28h]; Handle
0x1400b14ee  test    rcx, 0FFFFFFFF80000000h
0x1400b14f5  setz    dl; PreviousMode
0x1400b14f8  call    cs:__imp_ObCloseHandle
0x1400b14ff  nop     dword ptr [rax+rax+00h]
0x1400b1504  mov     rcx, [rdi+20h]; Object
0x1400b1508  call    ?VidMmDereferenceObjectAsync@@YAXPEAX@Z; VidMmDereferenceObjectAsync(void *)
0x1400b150d  lea     rbx, [rdi+38h]
0x1400b1511  mov     rcx, [rsi+8]
0x1400b1515  mov     rax, [rbx]
0x1400b1518  sub     [rcx+0B8h], rax
0x1400b151f  mov     rcx, [rsi+8]
0x1400b1523  mov     rax, [rbx]
0x1400b1526  sub     [rcx+0B0h], rax
0x1400b152d  mov     rax, [rsi+8]
0x1400b1531  dec     dword ptr [rax+0C4h]
0x1400b1537  mov     eax, [rdi+18h]
0x1400b153a  mov     rcx, [rsi+8]
0x1400b153e  cmp     eax, 1
0x1400b1541  jnz     short loc_1400B1591
0x1400b1543  mov     rax, [rbx]
0x1400b1546  sub     [rcx+0C8h], rax
0x1400b154d  mov     rcx, [rsi+8]
0x1400b1551  mov     rax, [rbx]
0x1400b1554  sub     [rcx+0D0h], rax
0x1400b155b  jmp     short loc_1400B15C5
0x1400b155d  mov     rcx, [rdi+30h]; SecureHandle
0x1400b1561  call    cs:__imp_MmUnsecureVirtualMemory
0x1400b1568  nop     dword ptr [rax+rax+00h]
0x1400b156d  lea     rbx, [rdi+38h]
0x1400b1571  call    ?DxgkGetVirtualMemoryInterface@@YAPEBUDXGK_VIRTUAL_MEMORY_INTERFACE@@XZ; DxgkGetVirtualMemoryInterface(void)
0x1400b1576  mov     r9d, 8000h
0x1400b157c  mov     r8, rbx
0x1400b157f  mov     rdx, r14
0x1400b1582  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400b1586  mov     rax, [rax+10h]
0x1400b158a  call    _guard_dispatch_icall
0x1400b158f  jmp     short loc_1400B1511
0x1400b1591  cmp     eax, 2
0x1400b1594  mov     rax, [rbx]
0x1400b1597  jnz     short loc_1400B15B0
0x1400b1599  sub     [rcx+0D8h], rax
0x1400b15a0  mov     rcx, [rsi+8]
0x1400b15a4  mov     rax, [rbx]
0x1400b15a7  sub     [rcx+0E0h], rax
0x1400b15ae  jmp     short loc_1400B15C5
0x1400b15b0  sub     [rcx+0E8h], rax
0x1400b15b7  mov     rcx, [rsi+8]
0x1400b15bb  mov     rax, [rbx]
0x1400b15be  sub     [rcx+0F0h], rax
0x1400b15c5  test    cs:byte_140086201, 10h
0x1400b15cc  jz      short loc_1400B1608
0x1400b15ce  mov     eax, [rdi+18h]
0x1400b15d1  sub     eax, 3
0x1400b15d4  cmp     eax, 3
0x1400b15d7  ja      short loc_1400B15DF
0x1400b15d9  mov     rax, [r14+18h]
0x1400b15dd  jmp     short loc_1400B15E2
0x1400b15df  mov     rax, [r14]
0x1400b15e2  mov     r9, [rsi+8]
0x1400b15e6  lea     rdx, EventDestroyProcessAllocationDetails
0x1400b15ed  mov     [rsp+0A8h+var_78], rax
0x1400b15f2  mov     rax, [rbx]
0x1400b15f5  mov     [rsp+0A8h+var_80], rax
0x1400b15fa  mov     r9d, [r9+18h]
0x1400b15fe  mov     [rsp+0A8h+var_88], rdi
0x1400b1603  call    McTemplateK0qxxx_EtwWriteTransfer
0x1400b1608  test    cs:byte_140086202, 4
0x1400b160f  jz      short loc_1400B1650
0x1400b1611  mov     rax, [rsi+8]
0x1400b1615  mov     ecx, [rdi+18h]
0x1400b1618  mov     r8, [rbx]
0x1400b161b  mov     edx, [rax+18h]
0x1400b161e  lea     eax, [rcx-3]
0x1400b1621  cmp     eax, 3
0x1400b1624  ja      short loc_1400B162C
0x1400b1626  mov     r9, [r14+18h]
0x1400b162a  jmp     short loc_1400B162F
0x1400b162c  mov     r9, [r14]
0x1400b162f  mov     [rsp+0A8h+var_70], 0
0x1400b1637  mov     dword ptr [rsp+0A8h+var_78], edx
0x1400b163b  lea     rdx, EventDestroyProcessAllocation
0x1400b1642  mov     dword ptr [rsp+0A8h+var_80], ecx
0x1400b1646  mov     [rsp+0A8h+var_88], r8
0x1400b164b  call    McTemplateK0pxqqt_EtwWriteTransfer
0x1400b1650  lea     rcx, [rsi+40h]; Lookaside
0x1400b1654  mov     rdx, rdi; Entry
0x1400b1657  call    cs:__imp_ExFreeToPagedLookasideList
0x1400b165e  nop     dword ptr [rax+rax+00h]
0x1400b1663  jmp     short loc_1400B1670
0x1400b1665  mov     rdx, rdi; Entry
0x1400b1668  mov     rcx, rsi; this
0x1400b166b  call    ?FreeSmallAllocation@VIDMM_PROCESS_HEAP@@AEAAXPEAU_VIDMM_PROCESS_HEAP_ALLOC@@@Z; VIDMM_PROCESS_HEAP::FreeSmallAllocation(_VIDMM_PROCESS_HEAP_ALLOC *)
0x1400b1670  lea     rcx, [rsp+0A8h+var_68]; this
0x1400b1675  call    ??1VIDMM_PROCESS_AUTOATTACH@@QEAA@XZ; VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH(void)
0x1400b167a  mov     rcx, [rsp+0A8h+var_28]
0x1400b1682  xor     rcx, rsp; StackCookie
0x1400b1685  call    __security_check_cookie
0x1400b168a  mov     rbx, [rsp+0A8h+arg_10]
0x1400b1692  add     rsp, 90h
0x1400b1699  pop     r14
0x1400b169b  pop     rdi
0x1400b169c  pop     rsi
0x1400b169d  retn
```
