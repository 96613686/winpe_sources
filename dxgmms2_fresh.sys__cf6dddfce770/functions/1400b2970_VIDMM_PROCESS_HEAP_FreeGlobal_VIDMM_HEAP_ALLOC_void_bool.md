# VIDMM_PROCESS_HEAP::FreeGlobal(VIDMM_HEAP_ALLOC *,void *,bool)

- ea: `0x1400b2970`
- end: `0x1400b2bef`
- name: `?FreeGlobal@VIDMM_PROCESS_HEAP@@UEAAXPEAUVIDMM_HEAP_ALLOC@@PEAX_N@Z`
- size: `639`
- prototype: `void __fastcall(VIDMM_PROCESS_HEAP *__hidden this, PVOID Entry, void *, bool)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation`

## callees

- `0x140012ed4`
- `0x14002f7d0`
- `0x140031434`
- `0x14003196c`
- `0x14003a8dc`
- `0x140058f50`
- `0x140059030`
- `0x1400b2970`
- `0x1400dadac`
- `0x1400f1668`

## import_xrefs

- `ntoskrnl!MmUnsecureVirtualMemory` at `0x1400b2ab1`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x1400b2ab1`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x1400b2a2e`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x1400b2a2e`
- `ntoskrnl!ObCloseHandle` at `0x1400b2a48`
- `ntoskrnl!ObCloseHandle` at `0x1400b2a48`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400b2ba7`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400b2ba7`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b29b1`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b29b1`
- `watchdog!WdLogSingleEntry5` at `0x1400b29ef`
- `watchdog!WdLogSingleEntry5` at `0x1400b29ef`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400b29c2`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
void __fastcall VIDMM_PROCESS_HEAP::FreeGlobal(VIDMM_PROCESS_HEAP *this, char *Entry, void *a3)
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
  _BYTE v20[64]; // [rsp+40h] [rbp-68h] BYREF

  VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH(
    (VIDMM_PROCESS_AUTOATTACH *)v20,
    *((struct VIDMM_PROCESS **)this + 1),
    1);
  v5 = *(_QWORD *)(*((_QWORD *)this + 1) + 16LL);
  if ( PsGetCurrentProcess(v6) != v5 )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 30, 0, 0, 0);
    WdLogGlobalForLineNumber = 227;
  }
  if ( (*(_DWORD *)Entry & 1) == 0 )
  {
    VIDMM_PROCESS_HEAP::FreeSmallAllocation(this, Entry);
    goto LABEL_26;
  }
  v7 = (PVOID *)(Entry + 8);
  v8 = *((_DWORD *)Entry + 6);
  if ( (unsigned int)(v8 - 3) > 1 )
  {
    if ( (unsigned int)(v8 - 5) > 1 )
    {
      MmUnsecureVirtualMemory(*((HANDLE *)Entry + 6));
      v10 = (__int64 *)(Entry + 56);
      VirtualMemoryInterface = DxgkGetVirtualMemoryInterface();
      (*((void (__fastcall **)(__int64, char *, char *, __int64))VirtualMemoryInterface + 2))(
        -1,
        Entry + 8,
        Entry + 56,
        0x8000);
      goto LABEL_8;
    }
    MmUnmapViewInSystemSpace(*v7);
  }
  ObCloseHandle(*((HANDLE *)Entry + 5), (*((_QWORD *)Entry + 5) & 0xFFFFFFFF80000000uLL) == 0);
  VidMmDereferenceObjectAsync(*((PVOID *)Entry + 4));
  v10 = (__int64 *)(Entry + 56);
LABEL_8:
  *(_QWORD *)(*((_QWORD *)this + 1) + 192LL) -= *v10;
  *(_QWORD *)(*((_QWORD *)this + 1) + 184LL) -= *v10;
  --*(_DWORD *)(*((_QWORD *)this + 1) + 204LL);
  v11 = *((_DWORD *)Entry + 6);
  v12 = (_QWORD *)*((_QWORD *)this + 1);
  if ( v11 == 1 )
  {
    v12[26] -= *v10;
    v13 = (_QWORD *)*((_QWORD *)this + 1);
    v13[27] -= *v10;
  }
  else
  {
    v15 = v11 == 2;
    v16 = *v10;
    if ( v15 )
    {
      v12[28] -= v16;
      v13 = (_QWORD *)*((_QWORD *)this + 1);
      v13[29] -= *v10;
    }
    else
    {
      v12[30] -= v16;
      v13 = (_QWORD *)*((_QWORD *)this + 1);
      v13[31] -= *v10;
    }
  }
  if ( (byte_140087201 & 0x10) != 0 )
  {
    if ( (unsigned int)(*((_DWORD *)Entry + 6) - 3) > 3 )
      v17 = *v7;
    else
      v17 = (PVOID)*((_QWORD *)Entry + 4);
    McTemplateK0qxxx_EtwWriteTransfer(
      (_DWORD)v13,
      (unsigned int)&EventDestroyProcessAllocationDetails,
      v9,
      *(_DWORD *)(*((_QWORD *)this + 1) + 24LL),
      (char)Entry,
      *v10,
      (char)v17);
  }
  if ( (byte_140087202 & 4) != 0 )
  {
    v18 = *((_DWORD *)Entry + 6);
    if ( (unsigned int)(v18 - 3) > 3 )
      v19 = *v7;
    else
      v19 = (PVOID)*((_QWORD *)Entry + 4);
    McTemplateK0pxqqt_EtwWriteTransfer(
      v18,
      (unsigned int)&EventDestroyProcessAllocation,
      *v10,
      (_DWORD)v19,
      *v10,
      v18,
      *(_DWORD *)(*((_QWORD *)this + 1) + 24LL),
      0);
  }
  ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)this + 64), Entry);
LABEL_26:
  VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH((VIDMM_PROCESS_AUTOATTACH *)v20);
}

```

## disassembly

```asm
0x1400b2970  mov     [rsp+arg_10], rbx
0x1400b2975  push    rsi
0x1400b2976  push    rdi
0x1400b2977  push    r14
0x1400b2979  sub     rsp, 90h
0x1400b2980  mov     rax, cs:__security_cookie
0x1400b2987  xor     rax, rsp
0x1400b298a  mov     [rsp+0A8h+var_28], rax
0x1400b2992  mov     rdi, rdx
0x1400b2995  mov     rsi, rcx
0x1400b2998  mov     rdx, [rcx+8]; struct VIDMM_PROCESS *
0x1400b299c  mov     r8b, 1; bool
0x1400b299f  lea     rcx, [rsp+0A8h+var_68]; this
0x1400b29a4  call    ??0VIDMM_PROCESS_AUTOATTACH@@QEAA@PEAVVIDMM_PROCESS@@_N@Z; VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH(VIDMM_PROCESS *,bool)
0x1400b29a9  mov     rax, [rsi+8]
0x1400b29ad  mov     rbx, [rax+10h]
0x1400b29b1  call    cs:__imp_PsGetCurrentProcess
0x1400b29b8  nop     dword ptr [rax+rax+00h]
0x1400b29bd  cmp     rax, rbx
0x1400b29c0  jz      short loc_1400B2A05
0x1400b29c2  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400b29c9  mov     dword ptr [rax], 1
0x1400b29cf  xor     r9d, r9d
0x1400b29d2  mov     [rsp+0A8h+var_80], 0
0x1400b29db  mov     edx, 10Eh
0x1400b29e0  mov     [rsp+0A8h+var_88], 0
0x1400b29e9  xor     ecx, ecx
0x1400b29eb  lea     r8d, [r9+1Eh]
0x1400b29ef  call    cs:__imp_WdLogSingleEntry5
0x1400b29f6  nop     dword ptr [rax+rax+00h]
0x1400b29fb  mov     cs:WdLogGlobalForLineNumber, 0E3h
0x1400b2a05  mov     eax, [rdi]
0x1400b2a07  test    al, 1
0x1400b2a09  jz      loc_1400B2BB5
0x1400b2a0f  lea     r14, [rdi+8]
0x1400b2a13  mov     ecx, [r14+10h]
0x1400b2a17  lea     eax, [rcx-3]
0x1400b2a1a  cmp     eax, 1
0x1400b2a1d  jbe     short loc_1400B2A3A
0x1400b2a1f  lea     eax, [rcx-5]
0x1400b2a22  cmp     eax, 1
0x1400b2a25  ja      loc_1400B2AAD
0x1400b2a2b  mov     rcx, [r14]; MappedBase
0x1400b2a2e  call    cs:__imp_MmUnmapViewInSystemSpace
0x1400b2a35  nop     dword ptr [rax+rax+00h]
0x1400b2a3a  mov     rcx, [rdi+28h]; Handle
0x1400b2a3e  test    rcx, 0FFFFFFFF80000000h
0x1400b2a45  setz    dl; PreviousMode
0x1400b2a48  call    cs:__imp_ObCloseHandle
0x1400b2a4f  nop     dword ptr [rax+rax+00h]
0x1400b2a54  mov     rcx, [rdi+20h]; Object
0x1400b2a58  call    ?VidMmDereferenceObjectAsync@@YAXPEAX@Z; VidMmDereferenceObjectAsync(void *)
0x1400b2a5d  lea     rbx, [rdi+38h]
0x1400b2a61  mov     rcx, [rsi+8]
0x1400b2a65  mov     rax, [rbx]
0x1400b2a68  sub     [rcx+0C0h], rax
0x1400b2a6f  mov     rcx, [rsi+8]
0x1400b2a73  mov     rax, [rbx]
0x1400b2a76  sub     [rcx+0B8h], rax
0x1400b2a7d  mov     rax, [rsi+8]
0x1400b2a81  dec     dword ptr [rax+0CCh]
0x1400b2a87  mov     eax, [rdi+18h]
0x1400b2a8a  mov     rcx, [rsi+8]
0x1400b2a8e  cmp     eax, 1
0x1400b2a91  jnz     short loc_1400B2AE1
0x1400b2a93  mov     rax, [rbx]
0x1400b2a96  sub     [rcx+0D0h], rax
0x1400b2a9d  mov     rcx, [rsi+8]
0x1400b2aa1  mov     rax, [rbx]
0x1400b2aa4  sub     [rcx+0D8h], rax
0x1400b2aab  jmp     short loc_1400B2B15
0x1400b2aad  mov     rcx, [rdi+30h]; SecureHandle
0x1400b2ab1  call    cs:__imp_MmUnsecureVirtualMemory
0x1400b2ab8  nop     dword ptr [rax+rax+00h]
0x1400b2abd  lea     rbx, [rdi+38h]
0x1400b2ac1  call    ?DxgkGetVirtualMemoryInterface@@YAPEBUDXGK_VIRTUAL_MEMORY_INTERFACE@@XZ; DxgkGetVirtualMemoryInterface(void)
0x1400b2ac6  mov     r9d, 8000h
0x1400b2acc  mov     r8, rbx
0x1400b2acf  mov     rdx, r14
0x1400b2ad2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400b2ad6  mov     rax, [rax+10h]
0x1400b2ada  call    _guard_dispatch_icall
0x1400b2adf  jmp     short loc_1400B2A61
0x1400b2ae1  cmp     eax, 2
0x1400b2ae4  mov     rax, [rbx]
0x1400b2ae7  jnz     short loc_1400B2B00
0x1400b2ae9  sub     [rcx+0E0h], rax
0x1400b2af0  mov     rcx, [rsi+8]
0x1400b2af4  mov     rax, [rbx]
0x1400b2af7  sub     [rcx+0E8h], rax
0x1400b2afe  jmp     short loc_1400B2B15
0x1400b2b00  sub     [rcx+0F0h], rax
0x1400b2b07  mov     rcx, [rsi+8]
0x1400b2b0b  mov     rax, [rbx]
0x1400b2b0e  sub     [rcx+0F8h], rax
0x1400b2b15  test    cs:byte_140087201, 10h
0x1400b2b1c  jz      short loc_1400B2B58
0x1400b2b1e  mov     eax, [rdi+18h]
0x1400b2b21  sub     eax, 3
0x1400b2b24  cmp     eax, 3
0x1400b2b27  ja      short loc_1400B2B2F
0x1400b2b29  mov     rax, [r14+18h]
0x1400b2b2d  jmp     short loc_1400B2B32
0x1400b2b2f  mov     rax, [r14]
0x1400b2b32  mov     r9, [rsi+8]
0x1400b2b36  lea     rdx, EventDestroyProcessAllocationDetails
0x1400b2b3d  mov     [rsp+0A8h+var_78], rax
0x1400b2b42  mov     rax, [rbx]
0x1400b2b45  mov     [rsp+0A8h+var_80], rax
0x1400b2b4a  mov     r9d, [r9+18h]
0x1400b2b4e  mov     [rsp+0A8h+var_88], rdi
0x1400b2b53  call    McTemplateK0qxxx_EtwWriteTransfer
0x1400b2b58  test    cs:byte_140087202, 4
0x1400b2b5f  jz      short loc_1400B2BA0
0x1400b2b61  mov     rax, [rsi+8]
0x1400b2b65  mov     ecx, [rdi+18h]
0x1400b2b68  mov     r8, [rbx]
0x1400b2b6b  mov     edx, [rax+18h]
0x1400b2b6e  lea     eax, [rcx-3]
0x1400b2b71  cmp     eax, 3
0x1400b2b74  ja      short loc_1400B2B7C
0x1400b2b76  mov     r9, [r14+18h]
0x1400b2b7a  jmp     short loc_1400B2B7F
0x1400b2b7c  mov     r9, [r14]
0x1400b2b7f  mov     [rsp+0A8h+var_70], 0
0x1400b2b87  mov     dword ptr [rsp+0A8h+var_78], edx
0x1400b2b8b  lea     rdx, EventDestroyProcessAllocation
0x1400b2b92  mov     dword ptr [rsp+0A8h+var_80], ecx
0x1400b2b96  mov     [rsp+0A8h+var_88], r8
0x1400b2b9b  call    McTemplateK0pxqqt_EtwWriteTransfer
0x1400b2ba0  lea     rcx, [rsi+40h]; Lookaside
0x1400b2ba4  mov     rdx, rdi; Entry
0x1400b2ba7  call    cs:__imp_ExFreeToPagedLookasideList
0x1400b2bae  nop     dword ptr [rax+rax+00h]
0x1400b2bb3  jmp     short loc_1400B2BC0
0x1400b2bb5  mov     rdx, rdi; Entry
0x1400b2bb8  mov     rcx, rsi; this
0x1400b2bbb  call    ?FreeSmallAllocation@VIDMM_PROCESS_HEAP@@AEAAXPEAU_VIDMM_PROCESS_HEAP_ALLOC@@@Z; VIDMM_PROCESS_HEAP::FreeSmallAllocation(_VIDMM_PROCESS_HEAP_ALLOC *)
0x1400b2bc0  lea     rcx, [rsp+0A8h+var_68]; this
0x1400b2bc5  call    ??1VIDMM_PROCESS_AUTOATTACH@@QEAA@XZ; VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH(void)
0x1400b2bca  mov     rcx, [rsp+0A8h+var_28]
0x1400b2bd2  xor     rcx, rsp; StackCookie
0x1400b2bd5  call    __security_check_cookie
0x1400b2bda  mov     rbx, [rsp+0A8h+arg_10]
0x1400b2be2  add     rsp, 90h
0x1400b2be9  pop     r14
0x1400b2beb  pop     rdi
0x1400b2bec  pop     rsi
0x1400b2bed  retn
```
