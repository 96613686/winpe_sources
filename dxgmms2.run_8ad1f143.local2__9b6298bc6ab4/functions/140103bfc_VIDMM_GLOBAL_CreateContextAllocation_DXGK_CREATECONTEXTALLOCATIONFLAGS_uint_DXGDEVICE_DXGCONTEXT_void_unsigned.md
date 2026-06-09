# VIDMM_GLOBAL::CreateContextAllocation(_DXGK_CREATECONTEXTALLOCATIONFLAGS,uint,DXGDEVICE *,DXGCONTEXT *,void *,unsigned __int64,ulong,_DXGK_PAGESIZE,_DXGK_PAGESIZE,ulong,ulong,ulong,_D3DDDI_SEGMENTPREFERENCE,_DXGK_SEGMENTBANKPREFERENCE,_DXGK_ALLOCATIONINFOFLAGS,VIDMM_CONTEXT_ALLOC * *)

- ea: `0x140103bfc`
- end: `0x1401040ee`
- name: `?CreateContextAllocation@VIDMM_GLOBAL@@QEAAJU_DXGK_CREATECONTEXTALLOCATIONFLAGS@@IPEAVDXGDEVICE@@PEAVDXGCONTEXT@@PEAX_KKW4_DXGK_PAGESIZE@@5KKKU_D3DDDI_SEGMENTPREFERENCE@@U_DXGK_SEGMENTBANKPREFERENCE@@U_DXGK_ALLOCATIONINFOFLAGS@@PEAPEAUVIDMM_CONTEXT_ALLOC@@@Z`
- size: `1266`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140036cc0`

## callees

- `0x1400045ec`
- `0x140058ac0`
- `0x1400a8ca8`
- `0x1400a9ba4`
- `0x1400e2504`
- `0x1400e84b4`
- `0x1400e9900`
- `0x1400ea1dc`
- `0x140102390`
- `0x140103bfc`
- `0x14010416c`
- `0x140105808`

## import_xrefs

- `watchdog!WdLogSingleEntry0` at `0x140103c71`
- `watchdog!WdLogSingleEntry0` at `0x140103cc2`
- `watchdog!WdLogSingleEntry0` at `0x14010403c`
- `watchdog!WdLogSingleEntry0` at `0x140103c71`
- `watchdog!WdLogSingleEntry0` at `0x140103cc2`
- `watchdog!WdLogSingleEntry0` at `0x14010403c`
- `watchdog!WdLogSingleEntry1` at `0x140103e4a`
- `watchdog!WdLogSingleEntry1` at `0x140103f21`
- `watchdog!WdLogSingleEntry1` at `0x140103fd9`
- `watchdog!WdLogSingleEntry1` at `0x140103ffd`
- `watchdog!WdLogSingleEntry1` at `0x140103e4a`
- `watchdog!WdLogSingleEntry1` at `0x140103f21`
- `watchdog!WdLogSingleEntry1` at `0x140103fd9`
- `watchdog!WdLogSingleEntry1` at `0x140103ffd`

## string_xrefs

- `0x140103e56`: `Falied to create and insert context allocation 0x%I64x`

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
        UINT a13,
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
  int v42; // [rsp+68h] [rbp-E8h]
  int v43; // [rsp+70h] [rbp-E0h]
  struct VIDMM_ALLOC *v44; // [rsp+D0h] [rbp-80h] BYREF
  struct VIDMM_GLOBAL_ALLOC *v45; // [rsp+D8h] [rbp-78h] BYREF
  _QWORD v46[18]; // [rsp+E0h] [rbp-70h] BYREF
  unsigned int v47; // [rsp+190h] [rbp+40h]
  void *v48; // [rsp+198h] [rbp+48h] BYREF

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
    WdLogGlobalForLineNumber = 2436;
    DxgkLogInternalTriageEvent(
      v39,
      0x40000,
      v40,
      (unsigned int)L"System device allocations are not supported yet",
      2436,
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
      v26 = 2456;
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
      WdLogGlobalForLineNumber = 2530;
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
        WdLogGlobalForLineNumber = 2588;
        goto LABEL_19;
      }
      v20 = v48;
      WdLogSingleEntry1(3, v48);
      WdLogGlobalForLineNumber = 2583;
    }
    else
    {
      v20 = v48;
      WdLogSingleEntry1(1, v48);
      WdLogGlobalForLineNumber = 2561;
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
  v26 = 2446;
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
0x140103bfc  mov     [rsp-8+arg_0], rbx
0x140103c01  mov     [rsp-8+arg_10], r8d
0x140103c06  push    rbp
0x140103c07  push    rsi
0x140103c08  push    rdi
0x140103c09  push    r12
0x140103c0b  push    r13
0x140103c0d  push    r14
0x140103c0f  push    r15
0x140103c11  lea     rbp, [rsp+10h]
0x140103c16  sub     rsp, 140h
0x140103c1d  xor     r14d, r14d
0x140103c20  mov     r13, r9
0x140103c23  mov     [rbp+20h+var_98], r14
0x140103c27  mov     edi, edx
0x140103c29  mov     [rbp+20h+var_A0], r14
0x140103c2d  mov     r12, rcx
0x140103c30  mov     [rbp+20h+arg_18], r14
0x140103c34  mov     r15d, r14d
0x140103c37  test    r9, r9
0x140103c3a  jz      loc_140104032
0x140103c40  mov     rax, [r9+28h]
0x140103c44  mov     rsi, [r9+318h]
0x140103c4b  mov     edx, [rax+198h]
0x140103c51  test    dl, 2
0x140103c54  jnz     loc_140104035
0x140103c5a  mov     r15, [rbp+20h+arg_20]
0x140103c5e  lea     ebx, [r14+1]
0x140103c62  mov     r9d, edi
0x140103c65  and     r9d, ebx
0x140103c68  jnz     short loc_140103CBB
0x140103c6a  test    r15, r15
0x140103c6d  jnz     short loc_140103CDC
0x140103c6f  mov     ecx, ebx
0x140103c71  call    cs:__imp_WdLogSingleEntry0
0x140103c78  nop     dword ptr [rax+rax+00h]
0x140103c7d  mov     eax, 98Eh
0x140103c82  lea     r9, aSystemContextA; "System context allocations are not supp"...
0x140103c89  mov     [rsp+170h+var_138], r14
0x140103c8e  mov     edx, 40000h
0x140103c93  mov     [rsp+170h+var_140], r14
0x140103c98  mov     [rsp+170h+var_148], r14
0x140103c9d  mov     qword ptr [rsp+170h+var_150], rax
0x140103ca2  mov     cs:WdLogGlobalForLineNumber, eax
0x140103ca8  call    DxgkLogInternalTriageEvent
0x140103cad  mov     r14d, 0C000000Dh
0x140103cb3  xor     r13d, r13d
0x140103cb6  jmp     loc_14010408E
0x140103cbb  test    r15, r15
0x140103cbe  jz      short loc_140103CDC
0x140103cc0  mov     ecx, ebx
0x140103cc2  call    cs:__imp_WdLogSingleEntry0
0x140103cc9  nop     dword ptr [rax+rax+00h]
0x140103cce  mov     eax, 998h
0x140103cd3  lea     r9, aTheCallerSpeci; "The caller specified a non-NULL context"...
0x140103cda  jmp     short loc_140103C89
0x140103cdc  test    r9d, r9d
0x140103cdf  jz      short loc_140103CE6
0x140103ce1  mov     r10, r13
0x140103ce4  jmp     short loc_140103D0F
0x140103ce6  mov     ecx, [r15+180h]
0x140103ced  mov     r8d, 0FFFFFFFFh
0x140103cf3  bsf     edx, ecx
0x140103cf6  mov     r10, r15
0x140103cf9  mov     [rbp+20h+arg_70], r14d
0x140103d00  movzx   ecx, dl
0x140103d03  cmovnz  r8d, ecx
0x140103d07  movsx   r8d, r8b
0x140103d0b  mov     [rbp+20h+arg_10], r8d
0x140103d0f  mov     eax, [rbp+20h+arg_78]
0x140103d15  lea     rcx, [rbp+20h+arg_70]
0x140103d1c  mov     [rsp+170h+var_A8], rcx
0x140103d24  mov     rdx, rsi
0x140103d27  lea     rcx, [rbp+20h+var_98]
0x140103d2b  mov     byte ptr [rbp+20h+arg_70], r14b
0x140103d32  mov     [rsp+170h+var_B0], rcx
0x140103d3a  mov     rcx, [rbp+20h+arg_28]
0x140103d3e  mov     [rsp+170h+var_B8], r14
0x140103d46  mov     [rsp+170h+var_C0], r14
0x140103d4e  mov     [rsp+170h+var_C8], r14
0x140103d56  mov     [rsp+170h+var_D0], r10
0x140103d5e  mov     [rsp+170h+var_D8], r9b
0x140103d66  mov     r9, [rbp+20h+arg_30]
0x140103d6a  mov     [rsp+170h+var_E0], 0A0000000h
0x140103d75  mov     [rsp+170h+var_E8], rcx
0x140103d7d  mov     rcx, r12
0x140103d80  mov     [rsp+170h+var_F0], r14
0x140103d88  mov     [rsp+170h+var_F8], r14
0x140103d8d  mov     [rsp+170h+var_100], r14
0x140103d92  mov     [rsp+170h+var_108], r14d
0x140103d97  mov     dword ptr [rsp+170h+var_110], eax
0x140103d9b  mov     eax, [rbp+20h+arg_68]
0x140103da1  mov     [rsp+170h+var_118], eax
0x140103da5  mov     eax, [rbp+20h+arg_60]
0x140103dab  mov     dword ptr [rsp+170h+var_120], eax
0x140103daf  mov     eax, [rbp+20h+arg_58]
0x140103db5  mov     dword ptr [rsp+170h+var_128], eax
0x140103db9  mov     eax, [rbp+20h+arg_50]
0x140103dbf  mov     [rsp+170h+var_130], eax
0x140103dc3  mov     eax, [rbp+20h+arg_48]
0x140103dc6  mov     dword ptr [rsp+170h+var_138], eax
0x140103dca  mov     eax, [rbp+20h+arg_40]
0x140103dcd  mov     dword ptr [rsp+170h+var_140], eax
0x140103dd1  mov     eax, [rbp+20h+arg_38]
0x140103dd4  mov     dword ptr [rsp+170h+var_148], eax
0x140103dd8  mov     qword ptr [rsp+170h+var_150], r9
0x140103ddd  call    ?CreateOneAllocation@VIDMM_GLOBAL@@QEAAJPEAVVIDMM_DEVICE@@K_K1KW4_DXGK_PAGESIZE@@2KKKU_D3DDDI_SEGMENTPREFERENCE@@U_DXGK_ALLOCATIONINFOFLAGS@@U_DXGK_ALLOCATIONINFOFLAGS2@@PEBVDXGADAPTERALLOCATION@@PEAX77KE7PEAVVIDMM_PAGE_TABLE_BASE@@PEAPEAUVIDMM_CROSSADAPTER_ALLOC@@PEAVVIDMM_FENCE_STORAGE_PAGE@@PEAPEAUVIDMM_GLOBAL_ALLOC@@PEAE@Z; VIDMM_GLOBAL::CreateOneAllocation(VIDMM_DEVICE *,ulong,unsigned __int64,unsigned __int64,ulong,_DXGK_PAGESIZE,_DXGK_PAGESIZE,ulong,ulong,ulong,_D3DDDI_SEGMENTPREFERENCE,_DXGK_ALLOCATIONINFOFLAGS,_DXGK_ALLOCATIONINFOFLAGS2,DXGADAPTERALLOCATION const *,void *,void *,void *,ulong,uchar,void *,VIDMM_PAGE_TABLE_BASE *,VIDMM_CROSSADAPTER_ALLOC * *,VIDMM_FENCE_STORAGE_PAGE *,VIDMM_GLOBAL_ALLOC * *,uchar *)
0x140103de2  mov     r14d, eax
0x140103de5  test    eax, eax
0x140103de7  js      loc_140103CB3
0x140103ded  mov     r8, [rbp+20h+var_98]; struct VIDMM_GLOBAL_ALLOC *
0x140103df1  lea     rax, [rbp+20h+var_A0]
0x140103df5  mov     [rsp+170h+var_148], rax; struct VIDMM_ALLOC **
0x140103dfa  xor     r9d, r9d; bool
0x140103dfd  mov     rdx, rsi; struct VIDMM_DEVICE *
0x140103e00  mov     qword ptr [rsp+170h+var_150], 0; struct DXGALLOCATION *
0x140103e09  mov     rcx, r12; this
0x140103e0c  call    ?OpenOneAllocation@VIDMM_GLOBAL@@QEAAJPEAVVIDMM_DEVICE@@PEAUVIDMM_GLOBAL_ALLOC@@_NPEAVDXGALLOCATION@@PEAPEAUVIDMM_ALLOC@@@Z; VIDMM_GLOBAL::OpenOneAllocation(VIDMM_DEVICE *,VIDMM_GLOBAL_ALLOC *,bool,DXGALLOCATION *,VIDMM_ALLOC * *)
0x140103e11  mov     r14d, eax
0x140103e14  test    eax, eax
0x140103e16  js      loc_140103CB3
0x140103e1c  mov     r9, [rbp+20h+var_A0]
0x140103e20  lea     rax, [rbp+20h+arg_18]
0x140103e24  mov     r8, r15
0x140103e27  mov     qword ptr [rsp+170h+var_150], rax
0x140103e2c  mov     rdx, r13
0x140103e2f  mov     rcx, r12
0x140103e32  call    VidMmCreateAndInsertContextAllocation
0x140103e37  xor     r13d, r13d
0x140103e3a  mov     r14d, eax
0x140103e3d  test    eax, eax
0x140103e3f  jns     short loc_140103E8A
0x140103e41  mov     r15, [rbp+20h+arg_18]
0x140103e45  mov     ecx, ebx
0x140103e47  mov     rdx, r15
0x140103e4a  call    cs:__imp_WdLogSingleEntry1
0x140103e51  nop     dword ptr [rax+rax+00h]
0x140103e56  lea     r9, aFaliedToCreate; "Falied to create and insert context all"...
0x140103e5d  mov     cs:WdLogGlobalForLineNumber, 9E2h
0x140103e67  mov     [rsp+170h+var_138], r13
0x140103e6c  mov     edx, 40000h
0x140103e71  mov     [rsp+170h+var_140], r13
0x140103e76  mov     [rsp+170h+var_148], r13
0x140103e7b  mov     qword ptr [rsp+170h+var_150], r15
0x140103e80  call    DxgkLogInternalTriageEvent
0x140103e85  jmp     loc_140104081
0x140103e8a  test    dil, 2
0x140103e8e  jz      loc_140103F67
0x140103e94  mov     rax, [rbp+20h+var_A0]
0x140103e98  mov     rdx, [r12+18h]
0x140103e9d  mov     r14d, [rbp+20h+arg_10]
0x140103ea1  mov     r8d, r14d; unsigned int
0x140103ea4  mov     rcx, [rax]
0x140103ea7  mov     edx, [rdx+0F0h]; unsigned int
0x140103ead  mov     rcx, [rcx+8]; this
0x140103eb1  call    ?GetVirtualAddressAllocator@VIDMM_PROCESS@@QEAAPEAVCVirtualAddressAllocator@@KI@Z; VIDMM_PROCESS::GetVirtualAddressAllocator(ulong,uint)
0x140103eb6  mov     rcx, [rbp+20h+var_98]
0x140103eba  mov     r10, rax
0x140103ebd  mov     rdx, [rbp+20h+var_A0]
0x140103ec1  mov     r9d, ebx
0x140103ec4  mov     byte ptr [rsp+170h+var_100], r13b
0x140103ec9  xor     r8d, r8d
0x140103ecc  mov     byte ptr [rsp+170h+var_108], r13b
0x140103ed1  mov     rax, [rcx]
0x140103ed4  mov     [rsp+170h+var_110], r13
0x140103ed9  mov     [rsp+170h+var_118], r14d
0x140103ede  mov     [rsp+170h+var_120], r13
0x140103ee3  mov     ecx, [rax+20h]
0x140103ee6  mov     rax, [rax+10h]
0x140103eea  mov     [rsp+170h+var_128], 11h
0x140103ef3  mov     [rsp+170h+var_130], ecx
0x140103ef7  mov     rcx, r10
0x140103efa  mov     [rsp+170h+var_138], r13
0x140103eff  mov     [rsp+170h+var_140], r13
0x140103f04  mov     [rsp+170h+var_148], r13
0x140103f09  mov     qword ptr [rsp+170h+var_150], rax
0x140103f0e  call    ?MapVirtualAddressRange@CVirtualAddressAllocator@@QEAAPEAUVIDMM_MAPPED_VA_RANGE@@PEAX_KW4VIDMM_VAD_OWNER_TYPE@@_K333IU_D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE@@1IPEAPEAUVIDMM_VAD_PENDING_OPERATION@@_N6@Z; CVirtualAddressAllocator::MapVirtualAddressRange(void *,unsigned __int64,VIDMM_VAD_OWNER_TYPE,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,uint,_D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE,unsigned __int64,uint,VIDMM_VAD_PENDING_OPERATION * *,bool,bool)
0x140103f13  test    rax, rax
0x140103f16  jnz     short loc_140103F67
0x140103f18  mov     r15, [rbp+20h+arg_18]
0x140103f1c  mov     ecx, ebx
0x140103f1e  mov     rdx, r15
0x140103f21  call    cs:__imp_WdLogSingleEntry1
0x140103f28  nop     dword ptr [rax+rax+00h]
0x140103f2d  mov     [rsp+170h+var_138], r13
0x140103f32  lea     r9, aFaliedToMapAVi; "Falied to map a virtual address range f"...
0x140103f39  mov     [rsp+170h+var_140], r13
0x140103f3e  mov     edx, 40000h
0x140103f43  mov     [rsp+170h+var_148], r13
0x140103f48  mov     qword ptr [rsp+170h+var_150], r15
0x140103f4d  mov     cs:WdLogGlobalForLineNumber, 0A01h
0x140103f57  call    DxgkLogInternalTriageEvent
0x140103f5c  mov     r14d, 0C0000017h
0x140103f62  jmp     loc_140104081
0x140103f67  xor     edx, edx; Val
0x140103f69  lea     rcx, [rbp+20h+var_90]; void *
0x140103f6d  lea     r8d, [rdx+58h]; Size
0x140103f71  call    memset
0x140103f76  mov     rdx, [rbp+20h+var_A0]
0x140103f7a  lea     r8, [rbp+20h+var_90]; struct _VIDMM_DEFERRED_COMMAND *
0x140103f7e  mov     rax, [rbp+20h+var_98]
0x140103f82  mov     r9b, bl; bool
0x140103f85  mov     [rbp+20h+var_80], rdx
0x140103f89  mov     [rbp+20h+var_90], 0D1h
0x140103f90  mov     [rbp+20h+var_70], edi
0x140103f93  mov     rcx, [rax]
0x140103f96  mov     rax, [rdx+8]
0x140103f9a  mov     qword ptr [rsp+170h+var_150], r13; unsigned __int64 *
0x140103f9f  mov     r10d, [rcx+3Ch]
0x140103fa3  mov     rcx, r12; this
0x140103fa6  mov     rdx, [rax+48h]
0x140103faa  shr     r10, 2
0x140103fae  and     r10d, 3Fh
0x140103fb2  shl     r10, 5
0x140103fb6  mov     rdx, [r10+rdx]; struct VIDMM_PAGING_QUEUE *
0x140103fba  call    ?QueueDeferredCommand@VIDMM_GLOBAL@@QEAAJAEAUVIDMM_PAGING_QUEUE@@PEAU_VIDMM_DEFERRED_COMMAND@@_NPEA_K@Z; VIDMM_GLOBAL::QueueDeferredCommand(VIDMM_PAGING_QUEUE &,_VIDMM_DEFERRED_COMMAND *,bool,unsigned __int64 *)
0x140103fbf  mov     r14d, eax
0x140103fc2  test    eax, eax
0x140103fc4  jns     short loc_14010401F
0x140103fc6  cmp     eax, 0C01E0200h
0x140103fcb  jnz     short loc_140103FF4
0x140103fcd  mov     r15, [rbp+20h+arg_18]
0x140103fd1  mov     ecx, 3
0x140103fd6  mov     rdx, r15
0x140103fd9  call    cs:__imp_WdLogSingleEntry1
0x140103fe0  nop     dword ptr [rax+rax+00h]
0x140103fe5  mov     cs:WdLogGlobalForLineNumber, 0A17h
0x140103fef  jmp     loc_140104081
0x140103ff4  mov     r15, [rbp+20h+arg_18]
0x140103ff8  mov     ecx, ebx
0x140103ffa  mov     rdx, r15
0x140103ffd  call    cs:__imp_WdLogSingleEntry1
0x140104004  nop     dword ptr [rax+rax+00h]
0x140104009  lea     r9, aFailedToInitCo; "Failed to init context allocation 0x%I6"...
0x140104010  mov     cs:WdLogGlobalForLineNumber, 0A1Ch
0x14010401a  jmp     loc_140103E67
0x14010401f  mov     rcx, [rbp+20h+arg_80]
0x140104026  mov     rax, [rbp+20h+arg_18]
0x14010402a  mov     [rcx], rax
0x14010402d  jmp     loc_1401040CF
0x140104032  mov     rsi, r14
0x140104035  mov     ebx, 1
0x14010403a  mov     ecx, ebx
0x14010403c  call    cs:__imp_WdLogSingleEntry0
0x140104043  nop     dword ptr [rax+rax+00h]
0x140104048  mov     [rsp+170h+var_138], r14
0x14010404d  lea     r9, aSystemDeviceAl; "System device allocations are not suppo"...
0x140104054  mov     eax, 984h
0x140104059  mov     [rsp+170h+var_140], r14
0x14010405e  mov     [rsp+170h+var_148], r14
0x140104063  mov     edx, 40000h
0x140104068  mov     cs:WdLogGlobalForLineNumber, eax
0x14010406e  mov     qword ptr [rsp+170h+var_150], rax
0x140104073  call    DxgkLogInternalTriageEvent
0x140104078  xor     r13d, r13d
0x14010407b  mov     r14d, 0C000000Dh
0x140104081  test    r15, r15
0x140104084  jz      short loc_14010408E
0x140104086  mov     rcx, r15; void *
0x140104089  call    VidMmDestroyContextAllocation_0
0x14010408e  mov     rdx, [rbp+20h+var_A0]; struct VIDMM_ALLOC *
0x140104092  test    rdx, rdx
0x140104095  jz      short loc_1401040AE
0x140104097  mov     [rsp+170h+var_148], r13; struct _KEVENT **
0x14010409c  xor     r9d, r9d; bool
0x14010409f  xor     r8d, r8d; struct VIDMM_LOCAL_ALLOC **
0x1401040a2  mov     dword ptr [rsp+170h+var_150], ebx; struct _D3DDDICB_DESTROYALLOCATION2FLAGS
0x1401040a6  mov     rcx, r12; this
0x1401040a9  call    ?CloseOneAllocation@VIDMM_GLOBAL@@QEAAJPEAUVIDMM_ALLOC@@PEAPEAUVIDMM_LOCAL_ALLOC@@_NU_D3DDDICB_DESTROYALLOCATION2FLAGS@@PEAPEAU_KEVENT@@@Z; VIDMM_GLOBAL::CloseOneAllocation(VIDMM_ALLOC *,VIDMM_LOCAL_ALLOC * *,bool,_D3DDDICB_DESTROYALLOCATION2FLAGS,_KEVENT * *)
0x1401040ae  mov     r8, [rbp+20h+var_98]; struct VIDMM_GLOBAL_ALLOC *
0x1401040b2  test    r8, r8
0x1401040b5  jz      short loc_1401040C5
0x1401040b7  mov     r9b, bl; bool
0x1401040ba  mov     rdx, rsi; struct VIDMM_DEVICE *
0x1401040bd  mov     rcx, r12; this
0x1401040c0  call    ?DestroyOneAllocation@VIDMM_GLOBAL@@QEAAXPEAVVIDMM_DEVICE@@PEAUVIDMM_GLOBAL_ALLOC@@_N@Z; VIDMM_GLOBAL::DestroyOneAllocation(VIDMM_DEVICE *,VIDMM_GLOBAL_ALLOC *,bool)
0x1401040c5  mov     rax, [rbp+20h+arg_80]
0x1401040cc  mov     [rax], r13
0x1401040cf  mov     rbx, [rsp+170h+arg_0]
0x1401040d7  mov     eax, r14d
0x1401040da  add     rsp, 140h
0x1401040e1  pop     r15
0x1401040e3  pop     r14
0x1401040e5  pop     r13
0x1401040e7  pop     r12
0x1401040e9  pop     rdi
0x1401040ea  pop     rsi
0x1401040eb  pop     rbp
0x1401040ec  retn
```
