# VIDMM_GLOBAL::CreateContextAllocation(_DXGK_CREATECONTEXTALLOCATIONFLAGS,uint,DXGDEVICE *,DXGCONTEXT *,void *,unsigned __int64,ulong,_DXGK_PAGESIZE,_DXGK_PAGESIZE,ulong,ulong,ulong,_D3DDDI_SEGMENTPREFERENCE,_DXGK_SEGMENTBANKPREFERENCE,_DXGK_ALLOCATIONINFOFLAGS,VIDMM_CONTEXT_ALLOC * *)

- ea: `0x1400f18cc`
- end: `0x1400f1dc6`
- name: `?CreateContextAllocation@VIDMM_GLOBAL@@QEAAJU_DXGK_CREATECONTEXTALLOCATIONFLAGS@@IPEAVDXGDEVICE@@PEAVDXGCONTEXT@@PEAX_KKW4_DXGK_PAGESIZE@@5KKKU_D3DDDI_SEGMENTPREFERENCE@@U_DXGK_SEGMENTBANKPREFERENCE@@U_DXGK_ALLOCATIONINFOFLAGS@@PEAPEAUVIDMM_CONTEXT_ALLOC@@@Z`
- size: `1274`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140035ad0`

## callees

- `0x140004268`
- `0x140059380`
- `0x1400a9df8`
- `0x1400aacf4`
- `0x1400b4cd8`
- `0x1400ea904`
- `0x1400f18cc`
- `0x1400f24e0`
- `0x1400fdc1c`
- `0x1400feb90`
- `0x1400ff470`
- `0x1400ffd4c`

## import_xrefs

- `watchdog!WdLogSingleEntry0` at `0x1400f1941`
- `watchdog!WdLogSingleEntry0` at `0x1400f1992`
- `watchdog!WdLogSingleEntry0` at `0x1400f1d14`
- `watchdog!WdLogSingleEntry0` at `0x1400f1941`
- `watchdog!WdLogSingleEntry0` at `0x1400f1992`
- `watchdog!WdLogSingleEntry0` at `0x1400f1d14`
- `watchdog!WdLogSingleEntry1` at `0x1400f1b22`
- `watchdog!WdLogSingleEntry1` at `0x1400f1bf9`
- `watchdog!WdLogSingleEntry1` at `0x1400f1cb1`
- `watchdog!WdLogSingleEntry1` at `0x1400f1cd5`
- `watchdog!WdLogSingleEntry1` at `0x1400f1b22`
- `watchdog!WdLogSingleEntry1` at `0x1400f1bf9`
- `watchdog!WdLogSingleEntry1` at `0x1400f1cb1`
- `watchdog!WdLogSingleEntry1` at `0x1400f1cd5`

## string_xrefs

- `0x1400f1b2e`: `Falied to create and insert context allocation 0x%I64x`

## pseudocode

```c
__int64 __fastcall VIDMM_GLOBAL::CreateContextAllocation(
        VIDMM_GLOBAL *a1,
        int a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        unsigned __int64 a7,
        unsigned int a8,
        int a9,
        int a10,
        unsigned int a11,
        unsigned int a12,
        unsigned int a13,
        _D3DDDI_SEGMENTPREFERENCE a14,
        int a15,
        int a16,
        void **a17)
{
  void *v20; // r15
  struct VIDMM_DEVICE *v21; // rsi
  int v22; // r15d
  char v23; // r9
  int v24; // ecx
  int v25; // r8d
  __int64 v26; // rax
  const wchar_t *v27; // r9
  int inserted; // r14d
  __int64 v29; // r10
  bool v30; // zf
  int v31; // edx
  int v32; // ecx
  int v33; // r8d
  const wchar_t *v34; // r9
  struct CVirtualAddressAllocator *VirtualAddressAllocator; // rax
  int v36; // ecx
  int v37; // r8d
  int v38; // eax
  int v39; // ecx
  int v40; // r8d
  int v42; // [rsp+68h] [rbp-F8h]
  int v43; // [rsp+70h] [rbp-F0h]
  struct VIDMM_ALLOC *v44; // [rsp+E0h] [rbp-80h] BYREF
  struct VIDMM_GLOBAL_ALLOC *v45; // [rsp+E8h] [rbp-78h] BYREF
  _QWORD v46[18]; // [rsp+F0h] [rbp-70h] BYREF
  unsigned int v47; // [rsp+1A0h] [rbp+40h]
  void *v48; // [rsp+1A8h] [rbp+48h] BYREF

  v47 = a3;
  v45 = 0;
  v44 = 0;
  v48 = 0;
  v20 = 0;
  if ( !a4 )
  {
    v21 = 0;
    goto LABEL_29;
  }
  v21 = *(struct VIDMM_DEVICE **)(a4 + 792);
  if ( (*(_DWORD *)(*(_QWORD *)(a4 + 40) + 408LL) & 2) != 0 )
  {
LABEL_29:
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 2487;
    DxgkLogInternalTriageEvent(
      v39,
      0x40000,
      v40,
      (unsigned int)L"System device allocations are not supported yet",
      2487,
      0,
      0,
      0);
    inserted = -1073741811;
    goto LABEL_30;
  }
  v22 = a5;
  v23 = a2 & 1;
  if ( (a2 & 1) != 0 )
  {
    if ( a5 )
    {
      WdLogSingleEntry0(1);
      v26 = 2507;
      v27 = L"The caller specified a non-NULL context for a cross context allocation, return an error to catch logical err"
             "ors in caller's code";
      goto LABEL_6;
    }
    goto LABEL_10;
  }
  if ( a5 )
  {
LABEL_10:
    if ( (a2 & 1) != 0 )
    {
      v29 = a4;
    }
    else
    {
      LOBYTE(a3) = -1;
      v30 = !_BitScanForward((unsigned int *)&v31, *(_DWORD *)(a5 + 384));
      v29 = a5;
      a15 = 0;
      if ( !v30 )
        LOBYTE(a3) = v31;
      a3 = (char)a3;
      v47 = (char)a3;
    }
    LOBYTE(a15) = 0;
    inserted = VIDMM_GLOBAL::CreateOneAllocation(
                 (__int64)a1,
                 v21,
                 a3,
                 a7,
                 a7,
                 a8,
                 a9,
                 a10,
                 a11,
                 a12,
                 a13,
                 a14,
                 a16,
                 0,
                 0,
                 0,
                 0,
                 0,
                 a6,
                 -1610612736,
                 v23,
                 v29,
                 0,
                 0,
                 0,
                 &v45,
                 &a15);
    if ( inserted < 0 )
      goto LABEL_32;
    inserted = VIDMM_GLOBAL::OpenOneAllocation(a1, (struct VIDMM_PROCESS **)v21, v45, 0, 0, &v44);
    if ( inserted < 0 )
      goto LABEL_32;
    inserted = VidMmCreateAndInsertContextAllocation((_DWORD)a1, a4, v22, (_DWORD)v44, (__int64)&v48);
    if ( inserted < 0 )
    {
      v20 = v48;
      WdLogSingleEntry1(1, v48);
      v34 = L"Falied to create and insert context allocation 0x%I64x";
      WdLogGlobalForLineNumber = 2582;
LABEL_19:
      DxgkLogInternalTriageEvent(v32, 0x40000, v33, (_DWORD)v34, (__int64)v20, 0, 0, 0);
      goto LABEL_30;
    }
    if ( (a2 & 2) == 0
      || (VirtualAddressAllocator = VIDMM_PROCESS::GetVirtualAddressAllocator(
                                      *(VIDMM_PROCESS **)(*(_QWORD *)v44 + 8LL),
                                      *(_DWORD *)(*((_QWORD *)a1 + 3) + 240LL),
                                      v47),
          LOBYTE(v43) = 0,
          LOBYTE(v42) = 0,
          CVirtualAddressAllocator::MapVirtualAddressRange(
            VirtualAddressAllocator,
            v44,
            0,
            1,
            *(_QWORD *)(*(_QWORD *)v45 + 16LL),
            0,
            0,
            0,
            *(_DWORD *)(*(_QWORD *)v45 + 32LL),
            17,
            0,
            v47,
            0,
            v42,
            v43)) )
    {
      memset(v46, 0, 0x58u);
      v46[2] = v44;
      LODWORD(v46[0]) = 209;
      LODWORD(v46[4]) = a2;
      v38 = VIDMM_GLOBAL::QueueDeferredCommand(
              a1,
              *(struct VIDMM_PAGING_QUEUE **)(32LL * ((unsigned __int8)*(_DWORD *)(*(_QWORD *)v45 + 60LL) >> 2)
                                            + *(_QWORD *)(*((_QWORD *)v44 + 1) + 72LL)),
              (struct _VIDMM_DEFERRED_COMMAND *)v46,
              1,
              0);
      inserted = v38;
      if ( v38 >= 0 )
      {
        *a17 = v48;
        return (unsigned int)inserted;
      }
      if ( v38 != -1071775232 )
      {
        v20 = v48;
        WdLogSingleEntry1(1, v48);
        v34 = L"Failed to init context allocation 0x%I64x";
        WdLogGlobalForLineNumber = 2640;
        goto LABEL_19;
      }
      v20 = v48;
      WdLogSingleEntry1(3, v48);
      WdLogGlobalForLineNumber = 2635;
    }
    else
    {
      v20 = v48;
      WdLogSingleEntry1(1, v48);
      WdLogGlobalForLineNumber = 2613;
      DxgkLogInternalTriageEvent(
        v36,
        0x40000,
        v37,
        (unsigned int)L"Falied to map a virtual address range for the context allocation 0x%I64x",
        (__int64)v20,
        0,
        0,
        0);
      inserted = -1073741801;
    }
LABEL_30:
    if ( v20 )
      VidMmDestroyContextAllocation_0(v20);
    goto LABEL_32;
  }
  WdLogSingleEntry0(1);
  v26 = 2497;
  v27 = L"System context allocations are not supported yet";
LABEL_6:
  WdLogGlobalForLineNumber = v26;
  DxgkLogInternalTriageEvent(v24, 0x40000, v25, (_DWORD)v27, v26, 0, 0, 0);
  inserted = -1073741811;
LABEL_32:
  if ( v44 )
    VIDMM_GLOBAL::CloseOneAllocation(a1, (__int64 **)v44, 0, 0, (struct _D3DDDICB_DESTROYALLOCATION2FLAGS)1, 0);
  if ( v45 )
    VIDMM_GLOBAL::DestroyOneAllocation(a1, v21, v45, 1);
  *a17 = 0;
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1400f18cc  mov     [rsp-8+arg_0], rbx
0x1400f18d1  mov     [rsp-8+arg_10], r8d
0x1400f18d6  push    rbp
0x1400f18d7  push    rsi
0x1400f18d8  push    rdi
0x1400f18d9  push    r12
0x1400f18db  push    r13
0x1400f18dd  push    r14
0x1400f18df  push    r15
0x1400f18e1  lea     rbp, [rsp+10h]
0x1400f18e6  sub     rsp, 150h
0x1400f18ed  xor     r14d, r14d
0x1400f18f0  mov     r13, r9
0x1400f18f3  mov     [rbp+20h+var_98], r14
0x1400f18f7  mov     edi, edx
0x1400f18f9  mov     [rbp+20h+var_A0], r14
0x1400f18fd  mov     r12, rcx
0x1400f1900  mov     [rbp+20h+arg_18], r14
0x1400f1904  mov     r15d, r14d
0x1400f1907  test    r9, r9
0x1400f190a  jz      loc_1400F1D0A
0x1400f1910  mov     rax, [r9+28h]
0x1400f1914  mov     rsi, [r9+318h]
0x1400f191b  mov     edx, [rax+198h]
0x1400f1921  test    dl, 2
0x1400f1924  jnz     loc_1400F1D0D
0x1400f192a  mov     r15, [rbp+20h+arg_20]
0x1400f192e  lea     ebx, [r14+1]
0x1400f1932  mov     r9d, edi
0x1400f1935  and     r9d, ebx
0x1400f1938  jnz     short loc_1400F198B
0x1400f193a  test    r15, r15
0x1400f193d  jnz     short loc_1400F19AC
0x1400f193f  mov     ecx, ebx
0x1400f1941  call    cs:__imp_WdLogSingleEntry0
0x1400f1948  nop     dword ptr [rax+rax+00h]
0x1400f194d  mov     eax, 9C1h
0x1400f1952  lea     r9, aSystemContextA; "System context allocations are not supp"...
0x1400f1959  mov     [rsp+180h+var_148], r14
0x1400f195e  mov     edx, 40000h
0x1400f1963  mov     [rsp+180h+var_150], r14
0x1400f1968  mov     [rsp+180h+var_158], r14
0x1400f196d  mov     qword ptr [rsp+180h+var_160], rax
0x1400f1972  mov     cs:WdLogGlobalForLineNumber, eax
0x1400f1978  call    DxgkLogInternalTriageEvent
0x1400f197d  mov     r14d, 0C000000Dh
0x1400f1983  xor     r13d, r13d
0x1400f1986  jmp     loc_1400F1D66
0x1400f198b  test    r15, r15
0x1400f198e  jz      short loc_1400F19AC
0x1400f1990  mov     ecx, ebx
0x1400f1992  call    cs:__imp_WdLogSingleEntry0
0x1400f1999  nop     dword ptr [rax+rax+00h]
0x1400f199e  mov     eax, 9CBh
0x1400f19a3  lea     r9, aTheCallerSpeci; "The caller specified a non-NULL context"...
0x1400f19aa  jmp     short loc_1400F1959
0x1400f19ac  test    r9d, r9d
0x1400f19af  jz      short loc_1400F19B6
0x1400f19b1  mov     r10, r13
0x1400f19b4  jmp     short loc_1400F19DF
0x1400f19b6  mov     ecx, [r15+180h]
0x1400f19bd  mov     r8d, 0FFFFFFFFh
0x1400f19c3  bsf     edx, ecx
0x1400f19c6  mov     r10, r15
0x1400f19c9  mov     [rbp+20h+arg_70], r14d
0x1400f19d0  movzx   ecx, dl
0x1400f19d3  cmovnz  r8d, ecx
0x1400f19d7  movsx   r8d, r8b
0x1400f19db  mov     [rbp+20h+arg_10], r8d
0x1400f19df  mov     eax, [rbp+20h+arg_78]
0x1400f19e5  lea     rcx, [rbp+20h+arg_70]
0x1400f19ec  mov     [rsp+180h+var_B0], rcx
0x1400f19f4  mov     rdx, rsi
0x1400f19f7  lea     rcx, [rbp+20h+var_98]
0x1400f19fb  mov     byte ptr [rbp+20h+arg_70], r14b
0x1400f1a02  mov     [rsp+180h+var_B8], rcx
0x1400f1a0a  mov     rcx, [rbp+20h+arg_28]
0x1400f1a0e  mov     [rsp+180h+var_C0], r14
0x1400f1a16  mov     [rsp+180h+var_C8], r14
0x1400f1a1e  mov     [rsp+180h+var_D0], r14
0x1400f1a26  mov     [rsp+180h+var_D8], r10
0x1400f1a2e  mov     [rsp+180h+var_E0], r9b
0x1400f1a36  mov     r9, [rbp+20h+arg_30]
0x1400f1a3a  mov     [rsp+180h+var_E8], 0A0000000h
0x1400f1a45  mov     [rsp+180h+var_F0], rcx
0x1400f1a4d  mov     rcx, r12
0x1400f1a50  mov     [rsp+180h+var_F8], r14
0x1400f1a58  mov     [rsp+180h+var_100], r14
0x1400f1a60  mov     [rsp+180h+var_108], r14
0x1400f1a65  mov     [rsp+180h+var_110], r14
0x1400f1a6a  mov     [rsp+180h+var_118], r14d
0x1400f1a6f  mov     dword ptr [rsp+180h+var_120], eax
0x1400f1a73  mov     eax, [rbp+20h+arg_68]
0x1400f1a79  mov     [rsp+180h+var_128], eax
0x1400f1a7d  mov     eax, [rbp+20h+arg_60]
0x1400f1a83  mov     dword ptr [rsp+180h+var_130], eax
0x1400f1a87  mov     eax, [rbp+20h+arg_58]
0x1400f1a8d  mov     dword ptr [rsp+180h+var_138], eax
0x1400f1a91  mov     eax, [rbp+20h+arg_50]
0x1400f1a97  mov     [rsp+180h+var_140], eax
0x1400f1a9b  mov     eax, [rbp+20h+arg_48]
0x1400f1a9e  mov     dword ptr [rsp+180h+var_148], eax
0x1400f1aa2  mov     eax, [rbp+20h+arg_40]
0x1400f1aa5  mov     dword ptr [rsp+180h+var_150], eax
0x1400f1aa9  mov     eax, [rbp+20h+arg_38]
0x1400f1aac  mov     dword ptr [rsp+180h+var_158], eax
0x1400f1ab0  mov     qword ptr [rsp+180h+var_160], r9
0x1400f1ab5  call    ?CreateOneAllocation@VIDMM_GLOBAL@@QEAAJPEAVVIDMM_DEVICE@@K_K1KW4_DXGK_PAGESIZE@@2KKKU_D3DDDI_SEGMENTPREFERENCE@@U_DXGK_ALLOCATIONINFOFLAGS@@U_DXGK_ALLOCATIONINFOFLAGS2@@PEBVDXGADAPTERALLOCATION@@PEAX777KE7PEAVVIDMM_PAGE_TABLE_BASE@@PEAPEAUVIDMM_CROSSADAPTER_ALLOC@@PEAVVIDMM_FENCE_STORAGE_PAGE@@PEAPEAUVIDMM_GLOBAL_ALLOC@@PEAE@Z; VIDMM_GLOBAL::CreateOneAllocation(VIDMM_DEVICE *,ulong,unsigned __int64,unsigned __int64,ulong,_DXGK_PAGESIZE,_DXGK_PAGESIZE,ulong,ulong,ulong,_D3DDDI_SEGMENTPREFERENCE,_DXGK_ALLOCATIONINFOFLAGS,_DXGK_ALLOCATIONINFOFLAGS2,DXGADAPTERALLOCATION const *,void *,void *,void *,void *,ulong,uchar,void *,VIDMM_PAGE_TABLE_BASE *,VIDMM_CROSSADAPTER_ALLOC * *,VIDMM_FENCE_STORAGE_PAGE *,VIDMM_GLOBAL_ALLOC * *,uchar *)
0x1400f1aba  mov     r14d, eax
0x1400f1abd  test    eax, eax
0x1400f1abf  js      loc_1400F1983
0x1400f1ac5  mov     r8, [rbp+20h+var_98]; struct VIDMM_GLOBAL_ALLOC *
0x1400f1ac9  lea     rax, [rbp+20h+var_A0]
0x1400f1acd  mov     [rsp+180h+var_158], rax; struct VIDMM_ALLOC **
0x1400f1ad2  xor     r9d, r9d; bool
0x1400f1ad5  mov     rdx, rsi; struct VIDMM_DEVICE *
0x1400f1ad8  mov     qword ptr [rsp+180h+var_160], 0; struct DXGALLOCATION *
0x1400f1ae1  mov     rcx, r12; this
0x1400f1ae4  call    ?OpenOneAllocation@VIDMM_GLOBAL@@QEAAJPEAVVIDMM_DEVICE@@PEAUVIDMM_GLOBAL_ALLOC@@_NPEAVDXGALLOCATION@@PEAPEAUVIDMM_ALLOC@@@Z; VIDMM_GLOBAL::OpenOneAllocation(VIDMM_DEVICE *,VIDMM_GLOBAL_ALLOC *,bool,DXGALLOCATION *,VIDMM_ALLOC * *)
0x1400f1ae9  mov     r14d, eax
0x1400f1aec  test    eax, eax
0x1400f1aee  js      loc_1400F1983
0x1400f1af4  mov     r9, [rbp+20h+var_A0]
0x1400f1af8  lea     rax, [rbp+20h+arg_18]
0x1400f1afc  mov     r8, r15
0x1400f1aff  mov     qword ptr [rsp+180h+var_160], rax
0x1400f1b04  mov     rdx, r13
0x1400f1b07  mov     rcx, r12
0x1400f1b0a  call    VidMmCreateAndInsertContextAllocation
0x1400f1b0f  xor     r13d, r13d
0x1400f1b12  mov     r14d, eax
0x1400f1b15  test    eax, eax
0x1400f1b17  jns     short loc_1400F1B62
0x1400f1b19  mov     r15, [rbp+20h+arg_18]
0x1400f1b1d  mov     ecx, ebx
0x1400f1b1f  mov     rdx, r15
0x1400f1b22  call    cs:__imp_WdLogSingleEntry1
0x1400f1b29  nop     dword ptr [rax+rax+00h]
0x1400f1b2e  lea     r9, aFaliedToCreate; "Falied to create and insert context all"...
0x1400f1b35  mov     cs:WdLogGlobalForLineNumber, 0A16h
0x1400f1b3f  mov     [rsp+180h+var_148], r13
0x1400f1b44  mov     edx, 40000h
0x1400f1b49  mov     [rsp+180h+var_150], r13
0x1400f1b4e  mov     [rsp+180h+var_158], r13
0x1400f1b53  mov     qword ptr [rsp+180h+var_160], r15
0x1400f1b58  call    DxgkLogInternalTriageEvent
0x1400f1b5d  jmp     loc_1400F1D59
0x1400f1b62  test    dil, 2
0x1400f1b66  jz      loc_1400F1C3F
0x1400f1b6c  mov     rax, [rbp+20h+var_A0]
0x1400f1b70  mov     rdx, [r12+18h]
0x1400f1b75  mov     r14d, [rbp+20h+arg_10]
0x1400f1b79  mov     r8d, r14d; unsigned int
0x1400f1b7c  mov     rcx, [rax]
0x1400f1b7f  mov     edx, [rdx+0F0h]; unsigned int
0x1400f1b85  mov     rcx, [rcx+8]; this
0x1400f1b89  call    ?GetVirtualAddressAllocator@VIDMM_PROCESS@@QEAAPEAVCVirtualAddressAllocator@@KI@Z; VIDMM_PROCESS::GetVirtualAddressAllocator(ulong,uint)
0x1400f1b8e  mov     rcx, [rbp+20h+var_98]
0x1400f1b92  mov     r10, rax
0x1400f1b95  mov     rdx, [rbp+20h+var_A0]
0x1400f1b99  mov     r9d, ebx
0x1400f1b9c  mov     byte ptr [rsp+180h+var_110], r13b
0x1400f1ba1  xor     r8d, r8d
0x1400f1ba4  mov     byte ptr [rsp+180h+var_118], r13b
0x1400f1ba9  mov     rax, [rcx]
0x1400f1bac  mov     [rsp+180h+var_120], r13
0x1400f1bb1  mov     [rsp+180h+var_128], r14d
0x1400f1bb6  mov     [rsp+180h+var_130], r13
0x1400f1bbb  mov     ecx, [rax+20h]
0x1400f1bbe  mov     rax, [rax+10h]
0x1400f1bc2  mov     [rsp+180h+var_138], 11h
0x1400f1bcb  mov     [rsp+180h+var_140], ecx
0x1400f1bcf  mov     rcx, r10
0x1400f1bd2  mov     [rsp+180h+var_148], r13
0x1400f1bd7  mov     [rsp+180h+var_150], r13
0x1400f1bdc  mov     [rsp+180h+var_158], r13
0x1400f1be1  mov     qword ptr [rsp+180h+var_160], rax
0x1400f1be6  call    ?MapVirtualAddressRange@CVirtualAddressAllocator@@QEAAPEAUVIDMM_MAPPED_VA_RANGE@@PEAX_KW4VIDMM_VAD_OWNER_TYPE@@_K333IU_D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE@@1IPEAPEAUVIDMM_VAD_PENDING_OPERATION@@_N6@Z; CVirtualAddressAllocator::MapVirtualAddressRange(void *,unsigned __int64,VIDMM_VAD_OWNER_TYPE,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,uint,_D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE,unsigned __int64,uint,VIDMM_VAD_PENDING_OPERATION * *,bool,bool)
0x1400f1beb  test    rax, rax
0x1400f1bee  jnz     short loc_1400F1C3F
0x1400f1bf0  mov     r15, [rbp+20h+arg_18]
0x1400f1bf4  mov     ecx, ebx
0x1400f1bf6  mov     rdx, r15
0x1400f1bf9  call    cs:__imp_WdLogSingleEntry1
0x1400f1c00  nop     dword ptr [rax+rax+00h]
0x1400f1c05  mov     [rsp+180h+var_148], r13
0x1400f1c0a  lea     r9, aFaliedToMapAVi; "Falied to map a virtual address range f"...
0x1400f1c11  mov     [rsp+180h+var_150], r13
0x1400f1c16  mov     edx, 40000h
0x1400f1c1b  mov     [rsp+180h+var_158], r13
0x1400f1c20  mov     qword ptr [rsp+180h+var_160], r15
0x1400f1c25  mov     cs:WdLogGlobalForLineNumber, 0A35h
0x1400f1c2f  call    DxgkLogInternalTriageEvent
0x1400f1c34  mov     r14d, 0C0000017h
0x1400f1c3a  jmp     loc_1400F1D59
0x1400f1c3f  xor     edx, edx; Val
0x1400f1c41  lea     rcx, [rbp+20h+var_90]; void *
0x1400f1c45  lea     r8d, [rdx+58h]; Size
0x1400f1c49  call    memset
0x1400f1c4e  mov     rdx, [rbp+20h+var_A0]
0x1400f1c52  lea     r8, [rbp+20h+var_90]; struct _VIDMM_DEFERRED_COMMAND *
0x1400f1c56  mov     rax, [rbp+20h+var_98]
0x1400f1c5a  mov     r9b, bl; bool
0x1400f1c5d  mov     [rbp+20h+var_80], rdx
0x1400f1c61  mov     [rbp+20h+var_90], 0D1h
0x1400f1c68  mov     [rbp+20h+var_70], edi
0x1400f1c6b  mov     rcx, [rax]
0x1400f1c6e  mov     rax, [rdx+8]
0x1400f1c72  mov     qword ptr [rsp+180h+var_160], r13; unsigned __int64 *
0x1400f1c77  mov     r10d, [rcx+3Ch]
0x1400f1c7b  mov     rcx, r12; this
0x1400f1c7e  mov     rdx, [rax+48h]
0x1400f1c82  shr     r10, 2
0x1400f1c86  and     r10d, 3Fh
0x1400f1c8a  shl     r10, 5
0x1400f1c8e  mov     rdx, [r10+rdx]; struct VIDMM_PAGING_QUEUE *
0x1400f1c92  call    ?QueueDeferredCommand@VIDMM_GLOBAL@@QEAAJAEAUVIDMM_PAGING_QUEUE@@PEAU_VIDMM_DEFERRED_COMMAND@@_NPEA_K@Z; VIDMM_GLOBAL::QueueDeferredCommand(VIDMM_PAGING_QUEUE &,_VIDMM_DEFERRED_COMMAND *,bool,unsigned __int64 *)
0x1400f1c97  mov     r14d, eax
0x1400f1c9a  test    eax, eax
0x1400f1c9c  jns     short loc_1400F1CF7
0x1400f1c9e  cmp     eax, 0C01E0200h
0x1400f1ca3  jnz     short loc_1400F1CCC
0x1400f1ca5  mov     r15, [rbp+20h+arg_18]
0x1400f1ca9  mov     ecx, 3
0x1400f1cae  mov     rdx, r15
0x1400f1cb1  call    cs:__imp_WdLogSingleEntry1
0x1400f1cb8  nop     dword ptr [rax+rax+00h]
0x1400f1cbd  mov     cs:WdLogGlobalForLineNumber, 0A4Bh
0x1400f1cc7  jmp     loc_1400F1D59
0x1400f1ccc  mov     r15, [rbp+20h+arg_18]
0x1400f1cd0  mov     ecx, ebx
0x1400f1cd2  mov     rdx, r15
0x1400f1cd5  call    cs:__imp_WdLogSingleEntry1
0x1400f1cdc  nop     dword ptr [rax+rax+00h]
0x1400f1ce1  lea     r9, aFailedToInitCo; "Failed to init context allocation 0x%I6"...
0x1400f1ce8  mov     cs:WdLogGlobalForLineNumber, 0A50h
0x1400f1cf2  jmp     loc_1400F1B3F
0x1400f1cf7  mov     rcx, [rbp+20h+arg_80]
0x1400f1cfe  mov     rax, [rbp+20h+arg_18]
0x1400f1d02  mov     [rcx], rax
0x1400f1d05  jmp     loc_1400F1DA7
0x1400f1d0a  mov     rsi, r14
0x1400f1d0d  mov     ebx, 1
0x1400f1d12  mov     ecx, ebx
0x1400f1d14  call    cs:__imp_WdLogSingleEntry0
0x1400f1d1b  nop     dword ptr [rax+rax+00h]
0x1400f1d20  mov     [rsp+180h+var_148], r14
0x1400f1d25  lea     r9, aSystemDeviceAl; "System device allocations are not suppo"...
0x1400f1d2c  mov     eax, 9B7h
0x1400f1d31  mov     [rsp+180h+var_150], r14
0x1400f1d36  mov     [rsp+180h+var_158], r14
0x1400f1d3b  mov     edx, 40000h
0x1400f1d40  mov     cs:WdLogGlobalForLineNumber, eax
0x1400f1d46  mov     qword ptr [rsp+180h+var_160], rax
0x1400f1d4b  call    DxgkLogInternalTriageEvent
0x1400f1d50  xor     r13d, r13d
0x1400f1d53  mov     r14d, 0C000000Dh
0x1400f1d59  test    r15, r15
0x1400f1d5c  jz      short loc_1400F1D66
0x1400f1d5e  mov     rcx, r15; void *
0x1400f1d61  call    VidMmDestroyContextAllocation_0
0x1400f1d66  mov     rdx, [rbp+20h+var_A0]; struct VIDMM_ALLOC *
0x1400f1d6a  test    rdx, rdx
0x1400f1d6d  jz      short loc_1400F1D86
0x1400f1d6f  mov     [rsp+180h+var_158], r13; struct _KEVENT **
0x1400f1d74  xor     r9d, r9d; bool
0x1400f1d77  xor     r8d, r8d; struct VIDMM_LOCAL_ALLOC **
0x1400f1d7a  mov     dword ptr [rsp+180h+var_160], ebx; struct _D3DDDICB_DESTROYALLOCATION2FLAGS
0x1400f1d7e  mov     rcx, r12; this
0x1400f1d81  call    ?CloseOneAllocation@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_ALLOC@@PEAPEAUVIDMM_LOCAL_ALLOC@@_NU_D3DDDICB_DESTROYALLOCATION2FLAGS@@PEAPEAU_KEVENT@@@Z; VIDMM_GLOBAL::CloseOneAllocation(VIDMM_ALLOC *,VIDMM_LOCAL_ALLOC * *,bool,_D3DDDICB_DESTROYALLOCATION2FLAGS,_KEVENT * *)
0x1400f1d86  mov     r8, [rbp+20h+var_98]; struct VIDMM_GLOBAL_ALLOC *
0x1400f1d8a  test    r8, r8
0x1400f1d8d  jz      short loc_1400F1D9D
0x1400f1d8f  mov     r9b, bl; bool
0x1400f1d92  mov     rdx, rsi; struct VIDMM_DEVICE *
0x1400f1d95  mov     rcx, r12; this
0x1400f1d98  call    ?DestroyOneAllocation@VIDMM_GLOBAL@@QEAAXPEAVVIDMM_DEVICE@@PEAUVIDMM_GLOBAL_ALLOC@@_N@Z; VIDMM_GLOBAL::DestroyOneAllocation(VIDMM_DEVICE *,VIDMM_GLOBAL_ALLOC *,bool)
0x1400f1d9d  mov     rax, [rbp+20h+arg_80]
0x1400f1da4  mov     [rax], r13
0x1400f1da7  mov     rbx, [rsp+180h+arg_0]
0x1400f1daf  mov     eax, r14d
0x1400f1db2  add     rsp, 150h
0x1400f1db9  pop     r15
0x1400f1dbb  pop     r14
0x1400f1dbd  pop     r13
0x1400f1dbf  pop     r12
0x1400f1dc1  pop     rdi
0x1400f1dc2  pop     rsi
0x1400f1dc3  pop     rbp
0x1400f1dc4  retn
```
