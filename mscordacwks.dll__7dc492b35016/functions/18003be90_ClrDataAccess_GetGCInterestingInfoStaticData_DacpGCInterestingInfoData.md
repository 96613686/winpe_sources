# ClrDataAccess::GetGCInterestingInfoStaticData(DacpGCInterestingInfoData *)

- ea: `0x18003be90`
- end: `0x18003c550`
- name: `?GetGCInterestingInfoStaticData@ClrDataAccess@@UEAAJPEAUDacpGCInterestingInfoData@@@Z`
- size: `1728`
- prototype: `int(ClrDataAccess *__hidden this, struct DacpGCInterestingInfoData *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180020e20`
- `0x180020f50`
- `0x1800210f0`
- `0x18003be90`
- `0x1800f3020`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18003bec3`
- `KERNEL32!EnterCriticalSection` at `0x18003bec3`
- `KERNEL32!LeaveCriticalSection` at `0x18003c50d`
- `KERNEL32!LeaveCriticalSection` at `0x18003c50d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall ClrDataAccess::GetGCInterestingInfoStaticData(
        ClrDataAccess *this,
        struct DacpGCInterestingInfoData *a2)
{
  unsigned int v4; // ebx
  ClrDataAccess *v6; // r15
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  int i; // edi
  unsigned __int64 *v14; // rax
  __int64 v15; // r9
  char v16; // r10
  __int64 v17; // rsi
  unsigned __int64 v18; // rcx
  char v19; // r8
  unsigned __int64 v20; // rcx
  int j; // edi
  unsigned __int64 *v22; // rax
  __int64 v23; // r9
  char v24; // r10
  __int64 v25; // rsi
  unsigned __int64 v26; // rcx
  char v27; // r8
  unsigned __int64 v28; // rcx
  int k; // edi
  unsigned __int64 *v30; // rax
  __int64 v31; // r9
  char v32; // r10
  __int64 v33; // rsi
  unsigned __int64 v34; // rcx
  char v35; // r8
  unsigned __int64 v36; // rcx
  int m; // edi
  unsigned __int64 *v38; // rax
  __int64 v39; // r9
  char v40; // r10
  __int64 v41; // rsi
  unsigned __int64 v42; // rcx
  char v43; // r8
  unsigned __int64 v44; // rcx
  struct Exception *v45; // rbx
  BOOL v46; // edi
  struct IExecutionEngine *ExecutionEngine; // rax
  struct Exception *v48; // rcx
  __int128 v49; // [rsp+20h] [rbp-228h]
  __int128 v50; // [rsp+40h] [rbp-208h]
  __int128 v51; // [rsp+50h] [rbp-1F8h]
  __int128 v52; // [rsp+60h] [rbp-1E8h]
  __int128 v53; // [rsp+B0h] [rbp-198h] BYREF
  __int64 v54; // [rsp+C0h] [rbp-188h]
  struct Exception *v55; // [rsp+D8h] [rbp-170h]
  __int128 v56; // [rsp+E0h] [rbp-168h]
  __int128 v57; // [rsp+F0h] [rbp-158h]
  __int128 v58; // [rsp+100h] [rbp-148h]
  __int128 v59; // [rsp+110h] [rbp-138h]
  __int64 v60; // [rsp+120h] [rbp-128h]
  __int64 v61; // [rsp+128h] [rbp-120h]
  __int64 v62; // [rsp+130h] [rbp-118h]
  __int64 v63; // [rsp+138h] [rbp-110h]
  __int64 v64; // [rsp+140h] [rbp-108h]
  __int64 v65; // [rsp+148h] [rbp-100h]
  __int64 v66; // [rsp+150h] [rbp-F8h]
  __int64 v67; // [rsp+160h] [rbp-E8h]
  char v68; // [rsp+168h] [rbp-E0h]
  __int64 v69; // [rsp+170h] [rbp-D8h]
  char v70; // [rsp+178h] [rbp-D0h]
  __int64 v71; // [rsp+180h] [rbp-C8h]
  char v72; // [rsp+188h] [rbp-C0h]
  __int64 v73; // [rsp+190h] [rbp-B8h]
  char v74; // [rsp+198h] [rbp-B0h]
  __int128 v75; // [rsp+1A0h] [rbp-A8h]
  __int128 v76; // [rsp+1B0h] [rbp-98h]
  __int128 v77; // [rsp+1C0h] [rbp-88h]
  __int128 v78; // [rsp+1D0h] [rbp-78h]
  __int128 v79; // [rsp+1E0h] [rbp-68h]
  __int128 v80; // [rsp+1F0h] [rbp-58h]
  __int128 v81; // [rsp+200h] [rbp-48h]
  unsigned int v83; // [rsp+258h] [rbp+10h] BYREF
  ClrDataAccess *v84; // [rsp+260h] [rbp+18h]
  unsigned __int64 v85; // [rsp+268h] [rbp+20h]

  v4 = 0;
  if ( !a2 )
    return 2147942487LL;
  EnterCriticalSection(&g_dacCritSec);
  v6 = g_dacImpl;
  v84 = g_dacImpl;
  g_dacImpl = (ClrDataAccess *)((char *)this - 32);
  v83 = 0;
  v55 = 0;
  try
  {
    memset(a2, 0, 0x110u);
    v85 = (unsigned int)*g_heap_type + DacGlobalBase(v8, v7, v9);
    if ( *(_DWORD *)DacInstantiateTypeByAddressHelper(v85, 4u, 1, 1) == 2 )
    {
      v4 = -2147467259;
      v83 = -2147467259;
    }
    else
    {
      for ( i = 0; i < 9; ++i )
      {
        v85 = (unsigned int)*g_gcDacGlobals + DacGlobalBase(v11, v10, v12);
        v14 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper(v85, 8u, 1, 1);
        v15 = *((_QWORD *)DacInstantiateTypeByAddressHelper(*v14, 0xE8u, 1, 1) + 24);
        if ( i < 0 )
        {
          v17 = i;
          v20 = v15 + 8LL * i;
        }
        else
        {
          v16 = 0;
          *(_QWORD *)&v56 = 8;
          BYTE8(v56) = 0;
          v75 = v56;
          v17 = i;
          v67 = i;
          v68 = 0;
          v18 = 0;
          *(_QWORD *)&v50 = 0;
          v19 = 0;
          BYTE8(v50) = 0;
          v60 = i;
          if ( i )
          {
            if ( 0xFFFFFFFFFFFFFFFFuLL / i >= 8 )
            {
              v18 = 8LL * i;
              *(_QWORD *)&v50 = v18;
            }
            else
            {
              v19 = 1;
              BYTE8(v50) = 1;
            }
          }
          else
          {
            v18 = 0;
            *(_QWORD *)&v50 = 0;
          }
          v76 = v50;
          if ( v19 || ~v15 < v18 )
          {
            v16 = 1;
            v20 = 0;
          }
          else
          {
            v20 = v15 + v18;
          }
          if ( v16 )
            DacError(-2146231242);
        }
        *((_QWORD *)a2 + v17) = *(_QWORD *)DacInstantiateTypeByAddressHelper(v20, 8u, 1, 1);
      }
      for ( j = 0; j < 11; ++j )
      {
        v85 = (unsigned int)*g_gcDacGlobals + DacGlobalBase(v11, v10, v12);
        v22 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper(v85, 8u, 1, 1);
        v23 = *((_QWORD *)DacInstantiateTypeByAddressHelper(*v22, 0xE8u, 1, 1) + 25);
        if ( j < 0 )
        {
          v25 = j;
          v28 = v23 + 8LL * j;
        }
        else
        {
          v24 = 0;
          *(_QWORD *)&v57 = 8;
          BYTE8(v57) = 0;
          v77 = v57;
          v25 = j;
          v69 = j;
          v70 = 0;
          v26 = 0;
          *(_QWORD *)&v51 = 0;
          v27 = 0;
          BYTE8(v51) = 0;
          v61 = 8;
          v62 = j;
          if ( j )
          {
            if ( 0xFFFFFFFFFFFFFFFFuLL / j >= 8 )
            {
              v26 = 8LL * j;
              *(_QWORD *)&v51 = v26;
            }
            else
            {
              v27 = 1;
              BYTE8(v51) = 1;
            }
          }
          else
          {
            v26 = 0;
            *(_QWORD *)&v51 = 0;
          }
          v78 = v51;
          if ( v27 || ~v23 < v26 )
          {
            v24 = 1;
            v28 = 0;
          }
          else
          {
            v28 = v23 + v26;
          }
          if ( v24 )
            DacError(-2146231242);
        }
        *((_QWORD *)a2 + v25 + 9) = *(_QWORD *)DacInstantiateTypeByAddressHelper(v28, 8u, 1, 1);
      }
      for ( k = 0; k < 6; ++k )
      {
        v85 = (unsigned int)*g_gcDacGlobals + DacGlobalBase(v11, v10, v12);
        v30 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper(v85, 8u, 1, 1);
        v31 = *((_QWORD *)DacInstantiateTypeByAddressHelper(*v30, 0xE8u, 1, 1) + 26);
        if ( k < 0 )
        {
          v33 = k;
          v36 = v31 + 8LL * k;
        }
        else
        {
          v32 = 0;
          *(_QWORD *)&v58 = 8;
          BYTE8(v58) = 0;
          v79 = v58;
          v33 = k;
          v71 = k;
          v72 = 0;
          v34 = 0;
          *(_QWORD *)&v52 = 0;
          v35 = 0;
          BYTE8(v52) = 0;
          v63 = 8;
          v64 = k;
          if ( k )
          {
            if ( 0xFFFFFFFFFFFFFFFFuLL / k >= 8 )
            {
              v34 = 8LL * k;
              *(_QWORD *)&v52 = v34;
            }
            else
            {
              v35 = 1;
              BYTE8(v52) = 1;
            }
          }
          else
          {
            v34 = 0;
            *(_QWORD *)&v52 = 0;
          }
          v80 = v52;
          if ( v35 || ~v31 < v34 )
          {
            v32 = 1;
            v36 = 0;
          }
          else
          {
            v36 = v31 + v34;
          }
          if ( v32 )
            DacError(-2146231242);
        }
        *((_QWORD *)a2 + v33 + 20) = *(_QWORD *)DacInstantiateTypeByAddressHelper(v36, 8u, 1, 1);
      }
      for ( m = 0; m < 2; ++m )
      {
        v85 = (unsigned int)*g_gcDacGlobals + DacGlobalBase(v11, v10, v12);
        v38 = (unsigned __int64 *)DacInstantiateTypeByAddressHelper(v85, 8u, 1, 1);
        v39 = *((_QWORD *)DacInstantiateTypeByAddressHelper(*v38, 0xE8u, 1, 1) + 27);
        if ( m < 0 )
        {
          v41 = m;
          v44 = v39 + 8LL * m;
        }
        else
        {
          v40 = 0;
          *(_QWORD *)&v59 = 8;
          BYTE8(v59) = 0;
          v81 = v59;
          v41 = m;
          v73 = m;
          v74 = 0;
          v42 = 0;
          *(_QWORD *)&v49 = 0;
          v43 = 0;
          BYTE8(v49) = 0;
          v65 = 8;
          v66 = m;
          if ( m )
          {
            if ( 0xFFFFFFFFFFFFFFFFuLL / m >= 8 )
            {
              v42 = 8LL * m;
              *(_QWORD *)&v49 = v42;
            }
            else
            {
              v43 = 1;
              BYTE8(v49) = 1;
            }
          }
          else
          {
            v42 = 0;
            *(_QWORD *)&v49 = 0;
          }
          v53 = v49;
          if ( v43 || ~v39 < v42 )
          {
            v40 = 1;
            v44 = 0;
          }
          else
          {
            v44 = v39 + v42;
          }
          if ( v40 )
            DacError(-2146231242);
        }
        *((_QWORD *)a2 + v41 + 26) = *(_QWORD *)DacInstantiateTypeByAddressHelper(v44, 8u, 1, 1);
      }
    }
  }
  catch ( ... )
  {
    *((_QWORD *)&v53 + 1) = 0;
    *(_QWORD *)&v53 = &DelegatingException::`vftable';
    v54 = -1;
    v45 = v55;
    v46 = v55 != 0;
    if ( !(__int64)__ClrFlsGetBlock() )
    {
      ExecutionEngine = GetExecutionEngine();
      (*(void (__fastcall **)(struct IExecutionEngine *, __int64))(*(_QWORD *)ExecutionEngine + 40LL))(
        ExecutionEngine,
        18);
    }
    v48 = (struct Exception *)&v53;
    if ( v45 )
      v48 = v45;
    if ( !DacExceptionFilter(v48, (ClrDataAccess *)((char *)this - 32), (int *)&v83) )
      throw;
    if ( v46 && v45 && !(*(unsigned int (__fastcall **)(struct Exception *))(*(_QWORD *)v45 + 80LL))(v45) )
      (**(void (__fastcall ***)(struct Exception *, __int64))v45)(v45, 5);
    DelegatingException::~DelegatingException((DelegatingException *)&v53);
    v6 = v84;
    v4 = v83;
  }
  g_dacImpl = v6;
  LeaveCriticalSection(&g_dacCritSec);
  return v4;
}

```

## disassembly

```asm
0x18003be90  mov     [rsp+arg_0], rcx
0x18003be95  push    rbx
0x18003be96  push    rsi
0x18003be97  push    rdi
0x18003be98  push    r12
0x18003be9a  push    r14
0x18003be9c  push    r15
0x18003be9e  sub     rsp, 218h
0x18003bea5  mov     r14, rdx
0x18003bea8  mov     rdi, rcx
0x18003beab  xor     ebx, ebx
0x18003bead  test    rdx, rdx
0x18003beb0  jnz     short loc_18003BEBC
0x18003beb2  mov     eax, 80070057h
0x18003beb7  jmp     loc_18003C515
0x18003bebc  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003bec3  call    cs:__imp_EnterCriticalSection
0x18003bec9  mov     r15, cs:?g_dacImpl@@3PEAVClrDataAccess@@EA; ClrDataAccess * g_dacImpl
0x18003bed0  mov     [rsp+248h+arg_10], r15
0x18003bed8  lea     rax, [rdi-20h]
0x18003bedc  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, rax; ClrDataAccess * g_dacImpl
0x18003bee3  mov     [rsp+248h+arg_8], ebx
0x18003beea  mov     [rsp+248h+var_170], rbx
0x18003bef2  lea     rax, [rsp+248h+var_178]
0x18003befa  mov     [rsp+248h+arg_18], rax
0x18003bf02  xor     edx, edx; Val
0x18003bf04  mov     r8d, 110h; Size
0x18003bf0a  mov     rcx, r14; void *
0x18003bf0d  call    memset
0x18003bf12  call    DacGlobalBase
0x18003bf17  mov     r10, rax
0x18003bf1a  mov     rax, cs:?g_heap_type@@3V?$__GlobalVal@W4GCHeapType@@@@A; __GlobalVal<GCHeapType> g_heap_type
0x18003bf21  mov     ecx, [rax]
0x18003bf23  add     r10, rcx
0x18003bf26  mov     [rsp+248h+arg_18], r10
0x18003bf2e  mov     r9b, 1; bool
0x18003bf31  mov     r8b, r9b; bool
0x18003bf34  mov     edx, 4; unsigned int
0x18003bf39  mov     rcx, r10; unsigned __int64
0x18003bf3c  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003bf41  cmp     dword ptr [rax], 2
0x18003bf44  jz      loc_18003C4E2
0x18003bf4a  mov     edi, ebx
0x18003bf4c  mov     [rsp+248h+var_218], ebx
0x18003bf50  mov     r12d, 8
0x18003bf56  cmp     edi, 9
0x18003bf59  jge     loc_18003C0A7
0x18003bf5f  call    DacGlobalBase
0x18003bf64  mov     rcx, rax
0x18003bf67  mov     rax, cs:?g_gcDacGlobals@@3V?$__GlobalPtr@PEAUGcDacVars@@V?$__DPtr@UGcDacVars@@@@@@A; __GlobalPtr<GcDacVars *,__DPtr<GcDacVars>> g_gcDacGlobals
0x18003bf6e  mov     edx, [rax]
0x18003bf70  add     rcx, rdx; unsigned __int64
0x18003bf73  mov     [rsp+248h+arg_18], rcx
0x18003bf7b  mov     r9b, 1; bool
0x18003bf7e  mov     r8b, r9b; bool
0x18003bf81  mov     edx, r12d; unsigned int
0x18003bf84  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003bf89  mov     r9b, 1; bool
0x18003bf8c  mov     r8b, r9b; bool
0x18003bf8f  mov     edx, 0E8h; unsigned int
0x18003bf94  mov     rcx, [rax]; unsigned __int64
0x18003bf97  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003bf9c  mov     r9, [rax+0C0h]
0x18003bfa3  test    edi, edi
0x18003bfa5  js      loc_18003C080
0x18003bfab  mov     [rsp+248h+var_1D8], r9
0x18003bfb0  mov     r10b, bl
0x18003bfb3  mov     [rsp+248h+var_1D0], bl
0x18003bfb7  mov     qword ptr [rsp+248h+var_168], r12
0x18003bfbf  mov     byte ptr [rsp+248h+var_168+8], bl
0x18003bfc6  movaps  xmm0, [rsp+248h+var_168]
0x18003bfce  movdqa  [rsp+248h+var_A8], xmm0
0x18003bfd7  movsxd  rsi, edi
0x18003bfda  mov     [rsp+248h+var_E8], rsi
0x18003bfe2  mov     [rsp+248h+var_E0], bl
0x18003bfe9  mov     rcx, rbx
0x18003bfec  mov     qword ptr [rsp+248h+var_208], rbx
0x18003bff1  mov     r8b, bl
0x18003bff4  mov     byte ptr [rsp+248h+var_208+8], bl
0x18003bff8  mov     [rsp+248h+arg_18], r12
0x18003c000  mov     [rsp+248h+var_128], rsi
0x18003c008  test    edi, edi
0x18003c00a  jz      short loc_18003C033
0x18003c00c  xor     edx, edx
0x18003c00e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003c012  div     rsi
0x18003c015  cmp     rax, r12
0x18003c018  jnb     short loc_18003C024
0x18003c01a  mov     r8b, 1
0x18003c01d  mov     byte ptr [rsp+248h+var_208+8], r8b
0x18003c022  jmp     short loc_18003C03B
0x18003c024  lea     rcx, ds:0[rsi*8]
0x18003c02c  mov     qword ptr [rsp+248h+var_208], rcx
0x18003c031  jmp     short loc_18003C03B
0x18003c033  mov     rcx, rbx
0x18003c036  mov     qword ptr [rsp+248h+var_208], rbx
0x18003c03b  movaps  xmm0, [rsp+248h+var_208]
0x18003c040  movdqa  [rsp+248h+var_98], xmm0
0x18003c049  test    r8b, r8b
0x18003c04c  jnz     short loc_18003C059
0x18003c04e  mov     rax, r9
0x18003c051  not     rax
0x18003c054  cmp     rax, rcx
0x18003c057  jnb     short loc_18003C074
0x18003c059  mov     r10b, 1
0x18003c05c  mov     [rsp+248h+var_1D0], r10b
0x18003c061  mov     [rsp+248h+var_1D8], rbx
0x18003c066  mov     rcx, rbx
0x18003c069  test    r10b, r10b
0x18003c06c  jnz     loc_18003C526
0x18003c072  jmp     short loc_18003C07E
0x18003c074  add     rcx, r9
0x18003c077  mov     [rsp+248h+var_1D8], rcx
0x18003c07c  jmp     short loc_18003C069
0x18003c07e  jmp     short loc_18003C087
0x18003c080  movsxd  rsi, edi
0x18003c083  lea     rcx, [r9+rsi*8]; unsigned __int64
0x18003c087  mov     r9b, 1; bool
0x18003c08a  mov     r8b, r9b; bool
0x18003c08d  mov     edx, r12d; unsigned int
0x18003c090  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003c095  mov     rax, [rax]
0x18003c098  mov     [r14+rsi*8], rax
0x18003c09c  inc     edi
0x18003c09e  mov     [rsp+248h+var_218], edi
0x18003c0a2  jmp     loc_18003BF56
0x18003c0a7  mov     edi, ebx
0x18003c0a9  mov     [rsp+248h+var_214], ebx
0x18003c0ad  cmp     edi, 0Bh
0x18003c0b0  jge     loc_18003C20E
0x18003c0b6  call    DacGlobalBase
0x18003c0bb  mov     rcx, rax
0x18003c0be  mov     rax, cs:?g_gcDacGlobals@@3V?$__GlobalPtr@PEAUGcDacVars@@V?$__DPtr@UGcDacVars@@@@@@A; __GlobalPtr<GcDacVars *,__DPtr<GcDacVars>> g_gcDacGlobals
0x18003c0c5  mov     edx, [rax]
0x18003c0c7  add     rcx, rdx; unsigned __int64
0x18003c0ca  mov     [rsp+248h+arg_18], rcx
0x18003c0d2  mov     r9b, 1; bool
0x18003c0d5  mov     r8b, r9b; bool
0x18003c0d8  mov     edx, r12d; unsigned int
0x18003c0db  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003c0e0  mov     r9b, 1; bool
0x18003c0e3  mov     r8b, r9b; bool
0x18003c0e6  mov     edx, 0E8h; unsigned int
0x18003c0eb  mov     rcx, [rax]; unsigned __int64
0x18003c0ee  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003c0f3  mov     r9, [rax+0C8h]
0x18003c0fa  test    edi, edi
0x18003c0fc  js      loc_18003C1E6
0x18003c102  mov     [rsp+248h+var_1C8], r9
0x18003c10a  mov     r10b, bl
0x18003c10d  mov     [rsp+248h+var_1C0], bl
0x18003c114  mov     qword ptr [rsp+248h+var_158], r12
0x18003c11c  mov     byte ptr [rsp+248h+var_158+8], bl
0x18003c123  movaps  xmm0, [rsp+248h+var_158]
0x18003c12b  movdqa  [rsp+248h+var_88], xmm0
0x18003c134  movsxd  rsi, edi
0x18003c137  mov     [rsp+248h+var_D8], rsi
0x18003c13f  mov     [rsp+248h+var_D0], bl
0x18003c146  mov     rcx, rbx
0x18003c149  mov     qword ptr [rsp+248h+var_1F8], rbx
0x18003c14e  mov     r8b, bl
0x18003c151  mov     byte ptr [rsp+248h+var_1F8+8], bl
0x18003c155  mov     [rsp+248h+var_120], r12
0x18003c15d  mov     [rsp+248h+var_118], rsi
0x18003c165  test    edi, edi
0x18003c167  jz      short loc_18003C190
0x18003c169  xor     edx, edx
0x18003c16b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003c16f  div     rsi
0x18003c172  cmp     rax, r12
0x18003c175  jnb     short loc_18003C181
0x18003c177  mov     r8b, 1
0x18003c17a  mov     byte ptr [rsp+248h+var_1F8+8], r8b
0x18003c17f  jmp     short loc_18003C198
0x18003c181  lea     rcx, ds:0[rsi*8]
0x18003c189  mov     qword ptr [rsp+248h+var_1F8], rcx
0x18003c18e  jmp     short loc_18003C198
0x18003c190  mov     rcx, rbx
0x18003c193  mov     qword ptr [rsp+248h+var_1F8], rbx
0x18003c198  movaps  xmm0, [rsp+248h+var_1F8]
0x18003c19d  movdqa  [rsp+248h+var_78], xmm0
0x18003c1a6  test    r8b, r8b
0x18003c1a9  jnz     short loc_18003C1B6
0x18003c1ab  mov     rax, r9
0x18003c1ae  not     rax
0x18003c1b1  cmp     rax, rcx
0x18003c1b4  jnb     short loc_18003C1D7
0x18003c1b6  mov     r10b, 1
0x18003c1b9  mov     [rsp+248h+var_1C0], r10b
0x18003c1c1  mov     [rsp+248h+var_1C8], rbx
0x18003c1c9  mov     rcx, rbx
0x18003c1cc  test    r10b, r10b
0x18003c1cf  jnz     loc_18003C530
0x18003c1d5  jmp     short loc_18003C1E4
0x18003c1d7  add     rcx, r9
0x18003c1da  mov     [rsp+248h+var_1C8], rcx
0x18003c1e2  jmp     short loc_18003C1CC
0x18003c1e4  jmp     short loc_18003C1ED
0x18003c1e6  movsxd  rsi, edi
0x18003c1e9  lea     rcx, [r9+rsi*8]; unsigned __int64
0x18003c1ed  mov     r9b, 1; bool
0x18003c1f0  mov     r8b, r9b; bool
0x18003c1f3  mov     edx, r12d; unsigned int
0x18003c1f6  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003c1fb  mov     rax, [rax]
0x18003c1fe  mov     [r14+rsi*8+48h], rax
0x18003c203  inc     edi
0x18003c205  mov     [rsp+248h+var_214], edi
0x18003c209  jmp     loc_18003C0AD
0x18003c20e  mov     edi, ebx
0x18003c210  mov     [rsp+248h+var_210], ebx
0x18003c214  cmp     edi, 6
0x18003c217  jge     loc_18003C378
0x18003c21d  call    DacGlobalBase
0x18003c222  mov     rcx, rax
0x18003c225  mov     rax, cs:?g_gcDacGlobals@@3V?$__GlobalPtr@PEAUGcDacVars@@V?$__DPtr@UGcDacVars@@@@@@A; __GlobalPtr<GcDacVars *,__DPtr<GcDacVars>> g_gcDacGlobals
0x18003c22c  mov     edx, [rax]
0x18003c22e  add     rcx, rdx; unsigned __int64
0x18003c231  mov     [rsp+248h+arg_18], rcx
0x18003c239  mov     r9b, 1; bool
0x18003c23c  mov     r8b, r9b; bool
0x18003c23f  mov     edx, r12d; unsigned int
0x18003c242  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003c247  mov     r9b, 1; bool
0x18003c24a  mov     r8b, r9b; bool
0x18003c24d  mov     edx, 0E8h; unsigned int
0x18003c252  mov     rcx, [rax]; unsigned __int64
0x18003c255  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003c25a  mov     r9, [rax+0D0h]
0x18003c261  test    edi, edi
0x18003c263  js      loc_18003C34D
0x18003c269  mov     [rsp+248h+var_1B8], r9
0x18003c271  mov     r10b, bl
0x18003c274  mov     [rsp+248h+var_1B0], bl
0x18003c27b  mov     qword ptr [rsp+248h+var_148], r12
0x18003c283  mov     byte ptr [rsp+248h+var_148+8], bl
0x18003c28a  movaps  xmm0, [rsp+248h+var_148]
0x18003c292  movdqa  [rsp+248h+var_68], xmm0
0x18003c29b  movsxd  rsi, edi
0x18003c29e  mov     [rsp+248h+var_C8], rsi
0x18003c2a6  mov     [rsp+248h+var_C0], bl
0x18003c2ad  mov     rcx, rbx
0x18003c2b0  mov     qword ptr [rsp+248h+var_1E8], rbx
0x18003c2b5  mov     r8b, bl
0x18003c2b8  mov     byte ptr [rsp+248h+var_1E8+8], bl
0x18003c2bc  mov     [rsp+248h+var_110], r12
0x18003c2c4  mov     [rsp+248h+var_108], rsi
0x18003c2cc  test    edi, edi
0x18003c2ce  jz      short loc_18003C2F7
0x18003c2d0  xor     edx, edx
0x18003c2d2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003c2d6  div     rsi
0x18003c2d9  cmp     rax, r12
0x18003c2dc  jnb     short loc_18003C2E8
0x18003c2de  mov     r8b, 1
0x18003c2e1  mov     byte ptr [rsp+248h+var_1E8+8], r8b
0x18003c2e6  jmp     short loc_18003C2FF
0x18003c2e8  lea     rcx, ds:0[rsi*8]
0x18003c2f0  mov     qword ptr [rsp+248h+var_1E8], rcx
0x18003c2f5  jmp     short loc_18003C2FF
0x18003c2f7  mov     rcx, rbx
0x18003c2fa  mov     qword ptr [rsp+248h+var_1E8], rbx
0x18003c2ff  movaps  xmm0, [rsp+248h+var_1E8]
0x18003c304  movdqa  [rsp+248h+var_58], xmm0
0x18003c30d  test    r8b, r8b
0x18003c310  jnz     short loc_18003C31D
0x18003c312  mov     rax, r9
0x18003c315  not     rax
0x18003c318  cmp     rax, rcx
0x18003c31b  jnb     short loc_18003C33E
0x18003c31d  mov     r10b, 1
0x18003c320  mov     [rsp+248h+var_1B0], r10b
0x18003c328  mov     [rsp+248h+var_1B8], rbx
0x18003c330  mov     rcx, rbx
0x18003c333  test    r10b, r10b
0x18003c336  jnz     loc_18003C53A
0x18003c33c  jmp     short loc_18003C34B
0x18003c33e  add     rcx, r9
0x18003c341  mov     [rsp+248h+var_1B8], rcx
0x18003c349  jmp     short loc_18003C333
0x18003c34b  jmp     short loc_18003C354
0x18003c34d  movsxd  rsi, edi
0x18003c350  lea     rcx, [r9+rsi*8]; unsigned __int64
0x18003c354  mov     r9b, 1; bool
0x18003c357  mov     r8b, r9b; bool
0x18003c35a  mov     edx, r12d; unsigned int
0x18003c35d  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x18003c362  mov     rax, [rax]
0x18003c365  mov     [r14+rsi*8+0A0h], rax
0x18003c36d  inc     edi
0x18003c36f  mov     [rsp+248h+var_210], edi
0x18003c373  jmp     loc_18003C214
0x18003c378  mov     edi, ebx
0x18003c37a  mov     [rsp+248h+var_20C], ebx
0x18003c37e  cmp     edi, 2
0x18003c381  jge     loc_18003C4EE
0x18003c387  call    DacGlobalBase
0x18003c38c  mov     rcx, rax
0x18003c38f  mov     rax, cs:?g_gcDacGlobals@@3V?$__GlobalPtr@PEAUGcDacVars@@V?$__DPtr@UGcDacVars@@@@@@A; __GlobalPtr<GcDacVars *,__DPtr<GcDacVars>> g_gcDacGlobals
0x18003c396  mov     edx, [rax]
  ... truncated ...
```
