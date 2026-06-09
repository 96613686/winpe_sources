# ClrDataAccess::GetGCHeapStaticData(DacpGcHeapDetails *)

- ea: `0x18003aca0`
- end: `0x18003b435`
- name: `?GetGCHeapStaticData@ClrDataAccess@@UEAAJPEAUDacpGcHeapDetails@@@Z`
- size: `1941`
- prototype: `__int64 __fastcall(ClrDataAccess *__hidden this, struct DacpGcHeapDetails *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000d1c4`
- `0x180020e20`
- `0x180020f50`
- `0x1800210f0`
- `0x18003aca0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18003acd6`
- `KERNEL32!EnterCriticalSection` at `0x18003acd6`
- `KERNEL32!LeaveCriticalSection` at `0x18003b40d`
- `KERNEL32!LeaveCriticalSection` at `0x18003b40d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall ClrDataAccess::GetGCHeapStaticData(ClrDataAccess *this, struct DacpGcHeapDetails *a2)
{
  ClrDataAccess *v5; // r13
  unsigned __int64 *v6; // rax
  _QWORD *v7; // rax
  unsigned __int64 *v8; // rax
  _QWORD *v9; // rax
  unsigned __int64 *v10; // rax
  _QWORD *v11; // rax
  unsigned __int64 *v12; // rax
  _QWORD *v13; // rax
  unsigned __int64 *v14; // rax
  _QWORD *v15; // rax
  unsigned __int64 *v16; // rax
  _QWORD *v17; // rax
  unsigned __int64 *v18; // rax
  _QWORD *v19; // rax
  unsigned __int64 *v20; // rax
  _QWORD *v21; // rax
  unsigned __int64 *v22; // rax
  _QWORD *v23; // rax
  unsigned __int64 *v24; // rax
  _QWORD *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  unsigned __int64 *v29; // rax
  unsigned __int64 v30; // rbx
  __int64 v31; // rdi
  unsigned int i; // r14d
  unsigned __int64 *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rcx
  unsigned __int64 v36; // rbx
  __int64 v37; // r8
  unsigned int j; // edi
  unsigned __int64 *v39; // rax
  _QWORD *v40; // rax
  char v41; // r9
  unsigned __int64 v42; // rcx
  char v43; // r8
  unsigned __int64 v44; // rcx
  __int64 *v45; // rax
  struct Exception *v46; // rbx
  BOOL v47; // edi
  struct IExecutionEngine *ExecutionEngine; // rax
  struct Exception *v49; // rcx
  unsigned __int64 v50; // [rsp+38h] [rbp-100h]
  unsigned __int64 v51; // [rsp+38h] [rbp-100h]
  __int128 v52; // [rsp+40h] [rbp-F8h]
  __int128 v53; // [rsp+50h] [rbp-E8h] BYREF
  __int64 v54; // [rsp+60h] [rbp-D8h]
  ClrDataAccess *v55; // [rsp+70h] [rbp-C8h]
  char v56; // [rsp+78h] [rbp-C0h] BYREF
  struct Exception *v57; // [rsp+80h] [rbp-B8h]
  __int128 v58; // [rsp+90h] [rbp-A8h]
  __int64 v59; // [rsp+A0h] [rbp-98h]
  unsigned __int64 v60; // [rsp+A8h] [rbp-90h]
  unsigned __int64 v61; // [rsp+B0h] [rbp-88h]
  __int64 v62; // [rsp+B8h] [rbp-80h]
  __int64 v63; // [rsp+C0h] [rbp-78h]
  unsigned __int64 v64; // [rsp+C8h] [rbp-70h]
  __int64 v65; // [rsp+D8h] [rbp-60h]
  char v66; // [rsp+E0h] [rbp-58h]
  __int128 v67; // [rsp+F0h] [rbp-48h]
  int v69; // [rsp+148h] [rbp+10h] BYREF
  char *v70; // [rsp+150h] [rbp+18h] BYREF
  unsigned __int64 v71; // [rsp+158h] [rbp+20h] BYREF

  if ( !a2 )
    return 2147942487LL;
  EnterCriticalSection(&g_dacCritSec);
  v5 = g_dacImpl;
  v55 = g_dacImpl;
  g_dacImpl = (ClrDataAccess *)((char *)this - 16);
  v57 = 0;
  try
  {
    v70 = &v56;
    v70 = (char *)((unsigned int)*g_lowest_address + ((__int64 (*)(void))DacGlobalBase)());
    *((_QWORD *)a2 + 33) = *(_QWORD *)DacInstantiateTypeByAddressHelper((unsigned __int64)v70, 8u, 1, 1);
    v70 = (char *)((unsigned int)*g_highest_address + ((__int64 (*)(void))DacGlobalBase)());
    *((_QWORD *)a2 + 34) = *(_QWORD *)DacInstantiateTypeByAddressHelper((unsigned __int64)v70, 8u, 1, 1);
    v70 = (char *)((unsigned int)*g_card_table + ((__int64 (*)(void))DacGlobalBase)());
    *((_QWORD *)a2 + 35) = *(_QWORD *)DacInstantiateTypeByAddressHelper((unsigned __int64)v70, 8u, 1, 1);
    *(_QWORD *)a2 = 0;
    v70 = (char *)((unsigned int)*g_gcDacGlobals + ((__int64 (*)(void))DacGlobalBase)());
    v6 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper((unsigned __int64)v70, 8u, 1, 1);
    v7 = DacInstantiateTypeByAddressHelper(*v6, 0xE8u, 1, 1);
    *((_QWORD *)a2 + 1) = *(_QWORD *)DacInstantiateTypeByAddressHelper(v7[14], 8u, 1, 1);
    v70 = (char *)((unsigned int)*g_gcDacGlobals + ((__int64 (*)(void))DacGlobalBase)());
    v8 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper((unsigned __int64)v70, 8u, 1, 1);
    v9 = DacInstantiateTypeByAddressHelper(*v8, 0xE8u, 1, 1);
    *((_QWORD *)a2 + 25) = *(_QWORD *)DacInstantiateTypeByAddressHelper(v9[9], 8u, 1, 1);
    v70 = (char *)((unsigned int)*g_gcDacGlobals + ((__int64 (*)(void))DacGlobalBase)());
    v10 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper((unsigned __int64)v70, 8u, 1, 1);
    v11 = DacInstantiateTypeByAddressHelper(*v10, 0xE8u, 1, 1);
    *((_QWORD *)a2 + 2) = *(_QWORD *)DacInstantiateTypeByAddressHelper(v11[7], 8u, 1, 1);
    v70 = (char *)((unsigned int)*g_gcDacGlobals + ((__int64 (*)(void))DacGlobalBase)());
    v12 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper((unsigned __int64)v70, 8u, 1, 1);
    v13 = DacInstantiateTypeByAddressHelper(*v12, 0xE8u, 1, 1);
    *((_QWORD *)a2 + 3) = *(int *)DacInstantiateTypeByAddressHelper(v13[8], 4u, 1, 1);
    v70 = (char *)((unsigned int)*g_gcDacGlobals + ((__int64 (*)(void))DacGlobalBase)());
    v14 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper((unsigned __int64)v70, 8u, 1, 1);
    v15 = DacInstantiateTypeByAddressHelper(*v14, 0xE8u, 1, 1);
    *((_QWORD *)a2 + 4) = *(_QWORD *)DacInstantiateTypeByAddressHelper(v15[15], 8u, 1, 1);
    v70 = (char *)((unsigned int)*g_gcDacGlobals + ((__int64 (*)(void))DacGlobalBase)());
    v16 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper((unsigned __int64)v70, 8u, 1, 1);
    v17 = DacInstantiateTypeByAddressHelper(*v16, 0xE8u, 1, 1);
    *((_QWORD *)a2 + 5) = *(_QWORD *)DacInstantiateTypeByAddressHelper(v17[10], 8u, 1, 1);
    v70 = (char *)((unsigned int)*g_gcDacGlobals + ((__int64 (*)(void))DacGlobalBase)());
    v18 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper((unsigned __int64)v70, 8u, 1, 1);
    v19 = DacInstantiateTypeByAddressHelper(*v18, 0xE8u, 1, 1);
    *((_QWORD *)a2 + 6) = *(_QWORD *)DacInstantiateTypeByAddressHelper(v19[11], 8u, 1, 1);
    v70 = (char *)((unsigned int)*g_gcDacGlobals + ((__int64 (*)(void))DacGlobalBase)());
    v20 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper((unsigned __int64)v70, 8u, 1, 1);
    v21 = DacInstantiateTypeByAddressHelper(*v20, 0xE8u, 1, 1);
    *((_QWORD *)a2 + 7) = *(_QWORD *)DacInstantiateTypeByAddressHelper(v21[12], 8u, 1, 1);
    v70 = (char *)((unsigned int)*g_gcDacGlobals + ((__int64 (*)(void))DacGlobalBase)());
    v22 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper((unsigned __int64)v70, 8u, 1, 1);
    v23 = DacInstantiateTypeByAddressHelper(*v22, 0xE8u, 1, 1);
    *((_QWORD *)a2 + 8) = *(_QWORD *)DacInstantiateTypeByAddressHelper(v23[13], 8u, 1, 1);
    for ( i = 0; ; ++i )
    {
      v50 = (unsigned int)*g_gcDacGlobals + ((__int64 (*)(void))DacGlobalBase)();
      v24 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper(v50, 8u, 1, 1);
      v25 = DacInstantiateTypeByAddressHelper(*v24, 0xE8u, 1, 1);
      if ( i >= *(_DWORD *)DacInstantiateTypeByAddressHelper(v25[6], 4u, 1, 1) + 2 )
        break;
      v51 = (unsigned int)*g_gcDacGlobals + DacGlobalBase(v27, v26, v28);
      v29 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper(v51, 8u, 1, 1);
      v70 = (char *)*((_QWORD *)DacInstantiateTypeByAddressHelper(*v29, 0xE8u, 1, 1) + 5);
      GenerationTableIndex(&v71, &v70, i);
      v30 = v71;
      v59 = *((_QWORD *)DacInstantiateTypeByAddressHelper(v71, 0x48u, 1, 1) + 7);
      v31 = 32LL * i;
      *(_QWORD *)((char *)a2 + v31 + 72) = v59;
      *(_QWORD *)((char *)a2 + v31 + 80) = *((_QWORD *)DacInstantiateTypeByAddressHelper(v30, 0x48u, 1, 1) + 8);
      *(_QWORD *)((char *)a2 + v31 + 88) = *(_QWORD *)DacInstantiateTypeByAddressHelper(v30, 0x38u, 1, 1);
      *((_QWORD *)a2 + 4 * i + 12) = *((_QWORD *)DacInstantiateTypeByAddressHelper(v30, 0x38u, 1, 1) + 1);
    }
    v70 = (char *)((unsigned int)*g_gcDacGlobals + ((__int64 (*)(void))DacGlobalBase)());
    v33 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper((unsigned __int64)v70, 8u, 1, 1);
    v71 = *((_QWORD *)DacInstantiateTypeByAddressHelper(*v33, 0xE8u, 1, 1) + 17);
    v36 = *(_QWORD *)DacInstantiateTypeByAddressHelper(v71, 8u, 1, 1);
    v60 = v36;
    v70 = (char *)v36;
    for ( j = 0; ; ++j )
    {
      v70 = (char *)((unsigned int)*g_gcDacGlobals + DacGlobalBase(v35, v34, v37));
      v39 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper((unsigned __int64)v70, 8u, 1, 1);
      v40 = DacInstantiateTypeByAddressHelper(*v39, 0xE8u, 1, 1);
      if ( j >= *(_DWORD *)DacInstantiateTypeByAddressHelper(v40[6], 4u, 1, 1) + 4 )
        break;
      v61 = v36;
      v41 = 0;
      *(_QWORD *)&v58 = 8;
      BYTE8(v58) = 0;
      v67 = v58;
      v65 = j;
      v66 = 0;
      v42 = 0;
      *(_QWORD *)&v52 = 0;
      v43 = 0;
      BYTE8(v52) = 0;
      v62 = 8;
      v63 = j;
      if ( j )
      {
        if ( 0xFFFFFFFFFFFFFFFFuLL / j >= 8 )
        {
          v42 = 8LL * j;
          *(_QWORD *)&v52 = v42;
        }
        else
        {
          v43 = 1;
          BYTE8(v52) = 1;
        }
      }
      else
      {
        v42 = 0;
        *(_QWORD *)&v52 = 0;
      }
      v53 = v52;
      if ( v43 || ~v36 < v42 )
      {
        v41 = 1;
        v44 = 0;
      }
      else
      {
        v44 = v36 + v42;
      }
      if ( v41 )
        DacError(-2146231242);
      v64 = v44;
      v45 = (__int64 *)DacInstantiateTypeByAddressHelper(v44, 8u, 1, 1);
      v35 = *v45;
      *((_QWORD *)a2 + j + 26) = *v45;
    }
  }
  catch ( ... )
  {
    *((_QWORD *)&v53 + 1) = 0;
    *(_QWORD *)&v53 = &DelegatingException::`vftable';
    v54 = -1;
    v46 = v57;
    v47 = v57 != 0;
    if ( !(__int64)__ClrFlsGetBlock() )
    {
      ExecutionEngine = GetExecutionEngine();
      (*(void (__fastcall **)(struct IExecutionEngine *, __int64))(*(_QWORD *)ExecutionEngine + 40LL))(
        ExecutionEngine,
        18);
    }
    v49 = (struct Exception *)&v53;
    if ( v46 )
      v49 = v46;
    if ( !DacExceptionFilter(v49, (ClrDataAccess *)((char *)this - 16), &v69) )
      throw;
    if ( v47 && v46 && !(*(unsigned int (__fastcall **)(struct Exception *))(*(_QWORD *)v46 + 80LL))(v46) )
      (**(void (__fastcall ***)(struct Exception *, __int64))v46)(v46, 5);
    DelegatingException::~DelegatingException((DelegatingException *)&v53);
    v5 = v55;
  }
  g_dacImpl = v5;
  LeaveCriticalSection(&g_dacCritSec);
  return 0;
}

```

## disassembly

```asm
0x18003aca0  mov     [rsp+arg_0], rcx
0x18003aca5  push    rbx
0x18003aca6  push    rsi
0x18003aca7  push    rdi
0x18003aca8  push    r12
0x18003acaa  push    r13
0x18003acac  push    r14
0x18003acae  push    r15
0x18003acb0  sub     rsp, 100h
0x18003acb7  mov     r12, rdx
0x18003acba  mov     rbx, rcx
0x18003acbd  xor     r15d, r15d
0x18003acc0  test    rdx, rdx
0x18003acc3  jnz     short loc_18003ACCF
0x18003acc5  mov     eax, 80070057h
0x18003acca  jmp     loc_18003B416
0x18003accf  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003acd6  call    cs:__imp_EnterCriticalSection
0x18003acdc  mov     r13, cs:?g_dacImpl@@3PEAVClrDataAccess@@EA; ClrDataAccess * g_dacImpl
0x18003ace3  mov     [rsp+138h+var_C8], r13
0x18003ace8  lea     rax, [rbx-10h]
0x18003acec  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, rax; ClrDataAccess * g_dacImpl
0x18003acf3  mov     [rsp+138h+arg_8], r15d
0x18003acfb  mov     [rsp+138h+var_B8], r15
0x18003ad03  lea     rax, [rsp+138h+var_C0]
0x18003ad08  mov     [rsp+138h+arg_10], rax
0x18003ad10  call    DacGlobalBase
0x18003ad15  mov     r10, rax
0x18003ad18  mov     rax, cs:?g_lowest_address@@3V?$__GlobalPtr@PEAEV?$__ArrayDPtr@E@@@@A; __GlobalPtr<uchar *,__ArrayDPtr<uchar>> g_lowest_address
0x18003ad1f  mov     ecx, [rax]
0x18003ad21  add     r10, rcx
0x18003ad24  mov     [rsp+138h+arg_10], r10
0x18003ad2c  mov     r9b, 1; bool
0x18003ad2f  mov     r8b, r9b; bool
0x18003ad32  mov     esi, 8
0x18003ad37  mov     edx, esi; unsigned int
0x18003ad39  mov     rcx, r10; unsigned __int64
0x18003ad3c  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003ad41  mov     rax, [rax]
0x18003ad44  mov     [r12+108h], rax
0x18003ad4c  call    DacGlobalBase
0x18003ad51  mov     rcx, rax
0x18003ad54  mov     rax, cs:?g_highest_address@@3V?$__GlobalPtr@PEAEV?$__ArrayDPtr@E@@@@A; __GlobalPtr<uchar *,__ArrayDPtr<uchar>> g_highest_address
0x18003ad5b  mov     edx, [rax]
0x18003ad5d  add     rcx, rdx; unsigned __int64
0x18003ad60  mov     [rsp+138h+arg_10], rcx
0x18003ad68  mov     r9b, 1; bool
0x18003ad6b  mov     r8b, r9b; bool
0x18003ad6e  mov     edx, esi; unsigned int
0x18003ad70  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003ad75  mov     rax, [rax]
0x18003ad78  mov     [r12+110h], rax
0x18003ad80  call    DacGlobalBase
0x18003ad85  mov     rcx, rax
0x18003ad88  mov     rax, cs:?g_card_table@@3V?$__GlobalPtr@PEAIV?$__DPtr@I@@@@A; __GlobalPtr<uint *,__DPtr<uint>> g_card_table
0x18003ad8f  mov     edx, [rax]
0x18003ad91  add     rcx, rdx; unsigned __int64
0x18003ad94  mov     [rsp+138h+arg_10], rcx
0x18003ad9c  mov     r9b, 1; bool
0x18003ad9f  mov     r8b, r9b; bool
0x18003ada2  mov     edx, esi; unsigned int
0x18003ada4  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003ada9  mov     rax, [rax]
0x18003adac  mov     [r12+118h], rax
0x18003adb4  mov     [r12], r15
0x18003adb8  call    DacGlobalBase
0x18003adbd  mov     rcx, rax
0x18003adc0  mov     rax, cs:?g_gcDacGlobals@@3V?$__GlobalPtr@PEAUGcDacVars@@V?$__DPtr@UGcDacVars@@@@@@A; __GlobalPtr<GcDacVars *,__DPtr<GcDacVars>> g_gcDacGlobals
0x18003adc7  mov     edx, [rax]
0x18003adc9  add     rcx, rdx; unsigned __int64
0x18003adcc  mov     [rsp+138h+arg_10], rcx
0x18003add4  mov     r9b, 1; bool
0x18003add7  mov     r8b, r9b; bool
0x18003adda  mov     edx, esi; unsigned int
0x18003addc  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003ade1  mov     r9b, 1; bool
0x18003ade4  mov     r8b, r9b; bool
0x18003ade7  mov     ebx, 0E8h
0x18003adec  mov     edx, ebx; unsigned int
0x18003adee  mov     rcx, [rax]; unsigned __int64
0x18003adf1  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003adf6  mov     r9b, 1; bool
0x18003adf9  mov     r8b, r9b; bool
0x18003adfc  mov     edx, esi; unsigned int
0x18003adfe  mov     rcx, [rax+70h]; unsigned __int64
0x18003ae02  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003ae07  mov     rcx, [rax]
0x18003ae0a  mov     [r12+8], rcx
0x18003ae0f  call    DacGlobalBase
0x18003ae14  mov     rcx, rax
0x18003ae17  mov     rax, cs:?g_gcDacGlobals@@3V?$__GlobalPtr@PEAUGcDacVars@@V?$__DPtr@UGcDacVars@@@@@@A; __GlobalPtr<GcDacVars *,__DPtr<GcDacVars>> g_gcDacGlobals
0x18003ae1e  mov     edx, [rax]
0x18003ae20  add     rcx, rdx; unsigned __int64
0x18003ae23  mov     [rsp+138h+arg_10], rcx
0x18003ae2b  mov     r9b, 1; bool
0x18003ae2e  mov     r8b, r9b; bool
0x18003ae31  mov     edx, esi; unsigned int
0x18003ae33  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003ae38  mov     r9b, 1; bool
0x18003ae3b  mov     r8b, r9b; bool
0x18003ae3e  mov     edx, ebx; unsigned int
0x18003ae40  mov     rcx, [rax]; unsigned __int64
0x18003ae43  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003ae48  mov     r9b, 1; bool
0x18003ae4b  mov     r8b, r9b; bool
0x18003ae4e  mov     edx, esi; unsigned int
0x18003ae50  mov     rcx, [rax+48h]; unsigned __int64
0x18003ae54  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003ae59  mov     rcx, [rax]
0x18003ae5c  mov     [r12+0C8h], rcx
0x18003ae64  call    DacGlobalBase
0x18003ae69  mov     rcx, rax
0x18003ae6c  mov     rax, cs:?g_gcDacGlobals@@3V?$__GlobalPtr@PEAUGcDacVars@@V?$__DPtr@UGcDacVars@@@@@@A; __GlobalPtr<GcDacVars *,__DPtr<GcDacVars>> g_gcDacGlobals
0x18003ae73  mov     edx, [rax]
0x18003ae75  add     rcx, rdx; unsigned __int64
0x18003ae78  mov     [rsp+138h+arg_10], rcx
0x18003ae80  mov     r9b, 1; bool
0x18003ae83  mov     r8b, r9b; bool
0x18003ae86  mov     edx, esi; unsigned int
0x18003ae88  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003ae8d  mov     r9b, 1; bool
0x18003ae90  mov     r8b, r9b; bool
0x18003ae93  mov     edx, ebx; unsigned int
0x18003ae95  mov     rcx, [rax]; unsigned __int64
0x18003ae98  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003ae9d  mov     r9b, 1; bool
0x18003aea0  mov     r8b, r9b; bool
0x18003aea3  mov     edx, esi; unsigned int
0x18003aea5  mov     rcx, [rax+38h]; unsigned __int64
0x18003aea9  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003aeae  mov     rcx, [rax]
0x18003aeb1  mov     [r12+10h], rcx
0x18003aeb6  call    DacGlobalBase
0x18003aebb  mov     rcx, rax
0x18003aebe  mov     rax, cs:?g_gcDacGlobals@@3V?$__GlobalPtr@PEAUGcDacVars@@V?$__DPtr@UGcDacVars@@@@@@A; __GlobalPtr<GcDacVars *,__DPtr<GcDacVars>> g_gcDacGlobals
0x18003aec5  mov     edx, [rax]
0x18003aec7  add     rcx, rdx; unsigned __int64
0x18003aeca  mov     [rsp+138h+arg_10], rcx
0x18003aed2  mov     r9b, 1; bool
0x18003aed5  mov     r8b, r9b; bool
0x18003aed8  mov     edx, esi; unsigned int
0x18003aeda  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003aedf  mov     r9b, 1; bool
0x18003aee2  mov     r8b, r9b; bool
0x18003aee5  mov     edx, ebx; unsigned int
0x18003aee7  mov     rcx, [rax]; unsigned __int64
0x18003aeea  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003aeef  mov     r9b, 1; bool
0x18003aef2  mov     r8b, r9b; bool
0x18003aef5  lea     edx, [rsi-4]; unsigned int
0x18003aef8  mov     rcx, [rax+40h]; unsigned __int64
0x18003aefc  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003af01  movsxd  rax, dword ptr [rax]
0x18003af04  mov     [r12+18h], rax
0x18003af09  call    DacGlobalBase
0x18003af0e  mov     rcx, rax
0x18003af11  mov     rax, cs:?g_gcDacGlobals@@3V?$__GlobalPtr@PEAUGcDacVars@@V?$__DPtr@UGcDacVars@@@@@@A; __GlobalPtr<GcDacVars *,__DPtr<GcDacVars>> g_gcDacGlobals
0x18003af18  mov     edx, [rax]
0x18003af1a  add     rcx, rdx; unsigned __int64
0x18003af1d  mov     [rsp+138h+arg_10], rcx
0x18003af25  mov     r9b, 1; bool
0x18003af28  mov     r8b, r9b; bool
0x18003af2b  mov     edx, esi; unsigned int
0x18003af2d  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003af32  mov     r9b, 1; bool
0x18003af35  mov     r8b, r9b; bool
0x18003af38  mov     edx, ebx; unsigned int
0x18003af3a  mov     rcx, [rax]; unsigned __int64
0x18003af3d  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003af42  mov     r9b, 1; bool
0x18003af45  mov     r8b, r9b; bool
0x18003af48  mov     edx, esi; unsigned int
0x18003af4a  mov     rcx, [rax+78h]; unsigned __int64
0x18003af4e  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003af53  mov     rcx, [rax]
0x18003af56  mov     [r12+20h], rcx
0x18003af5b  call    DacGlobalBase
0x18003af60  mov     rcx, rax
0x18003af63  mov     rax, cs:?g_gcDacGlobals@@3V?$__GlobalPtr@PEAUGcDacVars@@V?$__DPtr@UGcDacVars@@@@@@A; __GlobalPtr<GcDacVars *,__DPtr<GcDacVars>> g_gcDacGlobals
0x18003af6a  mov     edx, [rax]
0x18003af6c  add     rcx, rdx; unsigned __int64
0x18003af6f  mov     [rsp+138h+arg_10], rcx
0x18003af77  mov     r9b, 1; bool
0x18003af7a  mov     r8b, r9b; bool
0x18003af7d  mov     edx, esi; unsigned int
0x18003af7f  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003af84  mov     r9b, 1; bool
0x18003af87  mov     r8b, r9b; bool
0x18003af8a  mov     edx, ebx; unsigned int
0x18003af8c  mov     rcx, [rax]; unsigned __int64
0x18003af8f  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003af94  mov     r9b, 1; bool
0x18003af97  mov     r8b, r9b; bool
0x18003af9a  mov     edx, esi; unsigned int
0x18003af9c  mov     rcx, [rax+50h]; unsigned __int64
0x18003afa0  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003afa5  mov     rcx, [rax]
0x18003afa8  mov     [r12+28h], rcx
0x18003afad  call    DacGlobalBase
0x18003afb2  mov     rcx, rax
0x18003afb5  mov     rax, cs:?g_gcDacGlobals@@3V?$__GlobalPtr@PEAUGcDacVars@@V?$__DPtr@UGcDacVars@@@@@@A; __GlobalPtr<GcDacVars *,__DPtr<GcDacVars>> g_gcDacGlobals
0x18003afbc  mov     edx, [rax]
0x18003afbe  add     rcx, rdx; unsigned __int64
0x18003afc1  mov     [rsp+138h+arg_10], rcx
0x18003afc9  mov     r9b, 1; bool
0x18003afcc  mov     r8b, r9b; bool
0x18003afcf  mov     edx, esi; unsigned int
0x18003afd1  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003afd6  mov     r9b, 1; bool
0x18003afd9  mov     r8b, r9b; bool
0x18003afdc  mov     edx, ebx; unsigned int
0x18003afde  mov     rcx, [rax]; unsigned __int64
0x18003afe1  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003afe6  mov     r9b, 1; bool
0x18003afe9  mov     r8b, r9b; bool
0x18003afec  mov     edx, esi; unsigned int
0x18003afee  mov     rcx, [rax+58h]; unsigned __int64
0x18003aff2  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003aff7  mov     rcx, [rax]
0x18003affa  mov     [r12+30h], rcx
0x18003afff  call    DacGlobalBase
0x18003b004  mov     rcx, rax
0x18003b007  mov     rax, cs:?g_gcDacGlobals@@3V?$__GlobalPtr@PEAUGcDacVars@@V?$__DPtr@UGcDacVars@@@@@@A; __GlobalPtr<GcDacVars *,__DPtr<GcDacVars>> g_gcDacGlobals
0x18003b00e  mov     edx, [rax]
0x18003b010  add     rcx, rdx; unsigned __int64
0x18003b013  mov     [rsp+138h+arg_10], rcx
0x18003b01b  mov     r9b, 1; bool
0x18003b01e  mov     r8b, r9b; bool
0x18003b021  mov     edx, esi; unsigned int
0x18003b023  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003b028  mov     r9b, 1; bool
0x18003b02b  mov     r8b, r9b; bool
0x18003b02e  mov     edx, ebx; unsigned int
0x18003b030  mov     rcx, [rax]; unsigned __int64
0x18003b033  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003b038  mov     r9b, 1; bool
0x18003b03b  mov     r8b, r9b; bool
0x18003b03e  mov     edx, esi; unsigned int
0x18003b040  mov     rcx, [rax+60h]; unsigned __int64
0x18003b044  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003b049  mov     rcx, [rax]
0x18003b04c  mov     [r12+38h], rcx
0x18003b051  call    DacGlobalBase
0x18003b056  mov     rcx, rax
0x18003b059  mov     rax, cs:?g_gcDacGlobals@@3V?$__GlobalPtr@PEAUGcDacVars@@V?$__DPtr@UGcDacVars@@@@@@A; __GlobalPtr<GcDacVars *,__DPtr<GcDacVars>> g_gcDacGlobals
0x18003b060  mov     edx, [rax]
0x18003b062  add     rcx, rdx; unsigned __int64
0x18003b065  mov     [rsp+138h+arg_10], rcx
0x18003b06d  mov     r9b, 1; bool
0x18003b070  mov     r8b, r9b; bool
0x18003b073  mov     edx, esi; unsigned int
0x18003b075  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003b07a  mov     r9b, 1; bool
0x18003b07d  mov     r8b, r9b; bool
0x18003b080  mov     edx, ebx; unsigned int
0x18003b082  mov     rcx, [rax]; unsigned __int64
0x18003b085  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003b08a  mov     r9b, 1; bool
0x18003b08d  mov     r8b, r9b; bool
0x18003b090  mov     edx, esi; unsigned int
0x18003b092  mov     rcx, [rax+68h]; unsigned __int64
0x18003b096  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003b09b  mov     rcx, [rax]
0x18003b09e  mov     [r12+40h], rcx
0x18003b0a3  mov     r14d, r15d
0x18003b0a6  mov     [rsp+138h+var_108], r15d
0x18003b0ab  call    DacGlobalBase
0x18003b0b0  mov     rcx, rax
0x18003b0b3  mov     rax, cs:?g_gcDacGlobals@@3V?$__GlobalPtr@PEAUGcDacVars@@V?$__DPtr@UGcDacVars@@@@@@A; __GlobalPtr<GcDacVars *,__DPtr<GcDacVars>> g_gcDacGlobals
0x18003b0ba  mov     edx, [rax]
0x18003b0bc  add     rcx, rdx; unsigned __int64
0x18003b0bf  mov     [rsp+138h+var_100], rcx
0x18003b0c4  mov     r9b, 1; bool
0x18003b0c7  mov     r8b, r9b; bool
0x18003b0ca  mov     edx, esi; unsigned int
0x18003b0cc  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003b0d1  mov     r9b, 1; bool
0x18003b0d4  mov     r8b, r9b; bool
0x18003b0d7  mov     edx, ebx; unsigned int
0x18003b0d9  mov     rcx, [rax]; unsigned __int64
0x18003b0dc  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003b0e1  mov     r9b, 1; bool
0x18003b0e4  mov     r8b, r9b; bool
0x18003b0e7  mov     edx, 4; unsigned int
0x18003b0ec  mov     rcx, [rax+30h]; unsigned __int64
0x18003b0f0  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003b0f5  mov     eax, [rax]
0x18003b0f7  add     eax, 2
0x18003b0fa  cmp     r14d, eax
0x18003b0fd  jnb     loc_18003B20D
0x18003b103  call    DacGlobalBase
0x18003b108  mov     rcx, rax
0x18003b10b  mov     rax, cs:?g_gcDacGlobals@@3V?$__GlobalPtr@PEAUGcDacVars@@V?$__DPtr@UGcDacVars@@@@@@A; __GlobalPtr<GcDacVars *,__DPtr<GcDacVars>> g_gcDacGlobals
0x18003b112  mov     edx, [rax]
0x18003b114  add     rcx, rdx; unsigned __int64
0x18003b117  mov     [rsp+138h+var_100], rcx
0x18003b11c  mov     r9b, 1; bool
0x18003b11f  mov     r8b, r9b; bool
0x18003b122  mov     edx, esi; unsigned int
0x18003b124  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
  ... truncated ...
```
