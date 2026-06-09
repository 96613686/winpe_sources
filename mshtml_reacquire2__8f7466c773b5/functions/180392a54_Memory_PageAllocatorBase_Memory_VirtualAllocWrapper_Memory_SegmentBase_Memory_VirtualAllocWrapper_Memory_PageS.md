# Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>::TryAllocDecommittedPages<0>(uint,Memory::PageSegmentBase<Memory::VirtualAllocWrapper> * *)

- ea: `0x180392a54`
- end: `0x18039329f`
- name: `??$TryAllocDecommittedPages@$0A@@?$PageAllocatorBase@VVirtualAllocWrapper@Memory@@V?$SegmentBase@VVirtualAllocWrapper@Memory@@@2@V?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@2@@Memory@@IEAAPEADIPEAPEAV?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@1@@Z`
- size: `2123`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180391d7c`

## callees

- `0x180392a54`
- `0x1803939b4`
- `0x1803939d0`
- `0x180393a8c`
- `0x180393e24`
- `0x1807cb134`
- `0x1810bc928`
- `0x1810c0bf4`
- `0x1810f6516`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x180393155`
- `KERNEL32!GetCurrentThread` at `0x180393196`
- `KERNEL32!GetCurrentThread` at `0x180393204`
- `KERNEL32!GetCurrentThread` at `0x180393155`
- `KERNEL32!GetCurrentThread` at `0x180393196`
- `KERNEL32!GetCurrentThread` at `0x180393204`
- `KERNEL32!GetProcAddress` at `0x18039307a`
- `KERNEL32!GetProcAddress` at `0x180393093`
- `KERNEL32!GetProcAddress` at `0x1803930b0`
- `KERNEL32!GetProcAddress` at `0x18039307a`
- `KERNEL32!GetProcAddress` at `0x180393093`
- `KERNEL32!GetProcAddress` at `0x1803930b0`
- `KERNEL32!GetModuleHandleW` at `0x180393058`
- `KERNEL32!GetModuleHandleW` at `0x180393058`
- `KERNEL32!LeaveCriticalSection` at `0x18039310d`
- `KERNEL32!LeaveCriticalSection` at `0x18039310d`
- `KERNEL32!EnterCriticalSection` at `0x180393036`
- `KERNEL32!EnterCriticalSection` at `0x180393036`
- `KERNEL32!GetCurrentProcess` at `0x1803930c8`
- `KERNEL32!GetCurrentProcess` at `0x1803930c8`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180392cc9`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1803931d0`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180392cc9`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1803931d0`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18039323e`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18039323e`

## string_xrefs

- `0x1803930a6`: `GetThreadInformation`
- `0x180393051`: `api-ms-win-core-processthreads-l1-1-3.dll`
- `0x180393089`: `SetThreadInformation`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LPVOID __fastcall Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>::TryAllocDecommittedPages<0>(
        __int64 *a1,
        unsigned int a2,
        __int64 **a3)
{
  unsigned int v3; // esi
  __int64 *v4; // rax
  __int64 *v5; // r15
  __int64 *v7; // rdi
  _QWORD *v8; // rbx
  _QWORD *v9; // rsi
  __int64 v10; // r14
  unsigned __int64 v11; // r8
  int v12; // eax
  __int64 v13; // r10
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rax
  unsigned __int64 *v16; // r8
  unsigned int v17; // edx
  bool k; // zf
  __int64 v19; // rcx
  int v20; // eax
  unsigned __int64 v21; // rcx
  __int64 v22; // r12
  SIZE_T v23; // r13
  unsigned __int64 v24; // rdx
  char v25; // cl
  __int64 v26; // rax
  char v27; // bl
  SIZE_T v28; // rdx
  LPVOID v29; // r13
  unsigned __int64 *v30; // rcx
  int v31; // edx
  __int64 v32; // r8
  _QWORD *v33; // r8
  unsigned int i; // eax
  unsigned __int64 v35; // rdx
  int v36; // r8d
  int v37; // ebx
  int v38; // eax
  int v39; // edx
  unsigned int v40; // edx
  __int64 *v41; // rbx
  unsigned __int64 v42; // r12
  signed __int64 v43; // rax
  __int64 v44; // rcx
  __int64 *v45; // rbx
  __int64 v46; // rdx
  unsigned int v47; // edx
  bool v48; // cf
  unsigned __int64 *v49; // r8
  bool j; // zf
  __int64 *v51; // rsi
  unsigned int v52; // ebx
  HMODULE ModuleHandleW; // rax
  HMODULE v54; // rsi
  FARPROC ProcAddress; // r12
  HANDLE CurrentProcess; // rax
  int (*v57)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int); // rsi
  HANDLE CurrentThread; // rax
  int (*v59)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int); // rbx
  HANDLE v60; // rax
  void *v61; // rax
  int (*v62)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int); // rbx
  HANDLE v63; // rax
  int v64; // [rsp+38h] [rbp-89h] BYREF
  int v65; // [rsp+3Ch] [rbp-85h]
  unsigned int v66; // [rsp+40h] [rbp-81h]
  int v67; // [rsp+44h] [rbp-7Dh] BYREF
  __int64 *v68; // [rsp+48h] [rbp-79h]
  LPVOID lpAddress; // [rsp+50h] [rbp-71h]
  int v70; // [rsp+58h] [rbp-69h] BYREF
  DWORD flOldProtect; // [rsp+5Ch] [rbp-65h] BYREF
  int v72; // [rsp+60h] [rbp-61h]
  unsigned int v73; // [rsp+64h] [rbp-5Dh]
  __int64 v74; // [rsp+68h] [rbp-59h]
  __int64 *v75; // [rsp+70h] [rbp-51h]
  __int64 **v76; // [rsp+78h] [rbp-49h]
  struct _RTL_CRITICAL_SECTION *v77; // [rsp+80h] [rbp-41h]
  _OWORD v78[2]; // [rsp+88h] [rbp-39h] BYREF
  __int64 v79; // [rsp+A8h] [rbp-19h]
  _OWORD v80[2]; // [rsp+B8h] [rbp-9h] BYREF
  __int64 v81; // [rsp+D8h] [rbp+17h]
  _QWORD v82[7]; // [rsp+E0h] [rbp+1Fh] BYREF

  v75 = a1;
  v3 = a2;
  v66 = a2;
  v76 = a3;
  v4 = a1 + 9;
  v68 = a1 + 9;
  v5 = a1 + 9;
  while ( 1 )
  {
    v5 = (__int64 *)*v5;
    if ( v5 == v4 )
      return 0;
    v7 = v5 + 2;
    v73 = *((_DWORD *)v5 + 38);
    v78[0] = *((_OWORD *)v5 + 7);
    v78[1] = *((_OWORD *)v5 + 8);
    v79 = v5[18];
    v4 = v68;
    if ( *((_DWORD *)v5 + 39) + v73 >= v3 )
    {
      v80[0] = *(_OWORD *)(v5 + 9);
      v80[1] = *(_OWORD *)(v5 + 11);
      v81 = v5[13];
      v8 = v80;
      v9 = v78;
      do
        BVUnitT<unsigned __int64>::Or(v8++, *v9++);
      while ( v8 != v82 );
      v72 = *((_DWORD *)v5 + 38);
      v65 = 0;
      k = !_BitScanForward64((unsigned __int64 *)&v10, *(unsigned __int64 *)&v80[0]);
      if ( k || (_DWORD)v10 == -1 )
      {
        v30 = (unsigned __int64 *)v80;
        v31 = 0;
        while ( ++v30 != v82 )
        {
          v31 += 64;
          v65 = 0;
          k = !_BitScanForward64((unsigned __int64 *)&v32, *v30);
          if ( !k && (_DWORD)v32 != -1 )
          {
            LODWORD(v10) = v32 + v31;
            goto LABEL_9;
          }
        }
        LODWORD(v10) = -1;
      }
LABEL_9:
      v3 = v66;
LABEL_10:
      v4 = v68;
      if ( (_DWORD)v10 == -1 )
        continue;
      v4 = v68;
      if ( *((_DWORD *)v5 + 12) - (int)v10 - *((_DWORD *)v5 + 16) < v3 )
        continue;
      if ( v3 == 1 )
        goto LABEL_23;
      v11 = (unsigned __int64)(unsigned int)v10 >> 6;
      v12 = v10 & 0x3F;
      v13 = *((_QWORD *)v80 + v11);
      if ( v12 + v3 <= 0x40 )
      {
        v14 = 0xFFFFFFFFFFFFFFFFuLL >> (64 - (unsigned __int8)v3) << v12;
        v15 = v13 & v14;
        goto LABEL_15;
      }
      if ( (v13 & (0xFFFFFFFFFFFFFFFFuLL >> v12 << v12)) != 0xFFFFFFFFFFFFFFFFuLL >> v12 << v12 )
        goto LABEL_16;
      v33 = (_QWORD *)v80 + v11 + 1;
      for ( i = v12 + v3 - 64; i >= 0x40; i -= 64 )
      {
        if ( *v33 != -1 )
          goto LABEL_16;
        ++v33;
      }
      if ( !i )
        goto LABEL_23;
      v14 = 0xFFFFFFFFFFFFFFFFuLL >> (64 - (unsigned __int8)i);
      v15 = v14 & *v33;
LABEL_15:
      if ( v15 == v14 )
      {
LABEL_23:
        v21 = v5[5] + (unsigned int)((_DWORD)v10 << 12);
        lpAddress = (LPVOID)v21;
        v22 = v3;
        v74 = v3;
        v23 = (unsigned __int64)v3 << 12;
        if ( ((v23 - 1) & v21) != 0 )
        {
          v24 = (v21 % v23) >> 12;
          v25 = 0;
        }
        else
        {
          LODWORD(v24) = 0;
          v25 = 1;
        }
        v26 = v5[3];
        if ( v25 )
        {
          v65 = *(_DWORD *)(v26 + 216);
          v27 = 0;
          LOBYTE(v64) = 0;
          if ( v65 == 2 )
          {
            if ( !Memory::AutoEnableDynamicCodeGen::processPolicyObtained )
            {
              v77 = &Memory::AutoEnableDynamicCodeGen::processPolicyCS;
              EnterCriticalSection(&Memory::AutoEnableDynamicCodeGen::processPolicyCS);
              if ( !Memory::AutoEnableDynamicCodeGen::processPolicyObtained )
              {
                ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-processthreads-l1-1-3.dll");
                v54 = ModuleHandleW;
                if ( !ModuleHandleW
                  || (ProcAddress = GetProcAddress(ModuleHandleW, "GetProcessMitigationPolicy"),
                      Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc = (int (*)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int))GetProcAddress(v54, "SetThreadInformation"),
                      Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc = (int (*)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int))GetProcAddress(v54, "GetThreadInformation"),
                      !ProcAddress)
                  || (CurrentProcess = GetCurrentProcess(),
                      !((unsigned int (__fastcall *)(HANDLE, __int64, struct _PROCESS_MITIGATION_DYNAMIC_CODE_POLICY *))ProcAddress)(
                         CurrentProcess,
                         2,
                         &Memory::AutoEnableDynamicCodeGen::processPolicy)) )
                {
                  Memory::AutoEnableDynamicCodeGen::processPolicy.Flags &= ~1u;
                }
                Memory::AutoEnableDynamicCodeGen::processPolicyObtained = 1;
                v22 = v74;
              }
              LeaveCriticalSection(&Memory::AutoEnableDynamicCodeGen::processPolicyCS);
            }
            if ( (Memory::AutoEnableDynamicCodeGen::processPolicy.Flags & 1) != 0
              && (Memory::AutoEnableDynamicCodeGen::processPolicy.Flags & 2) != 0 )
            {
              if ( Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc )
              {
                v57 = Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc;
                if ( Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc )
                {
                  v67 = 0;
                  CurrentThread = GetCurrentThread();
                  if ( !((unsigned int (__fastcall *)(HANDLE, __int64, int *))v57)(CurrentThread, 2, &v67) || v67 != 1 )
                  {
                    v67 = 1;
                    v59 = Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc;
                    v60 = GetCurrentThread();
                    ((void (__fastcall *)(HANDLE, __int64, int *))v59)(v60, 2, &v67);
                    v27 = 1;
                    LOBYTE(v64) = 1;
                  }
                }
              }
            }
          }
          flOldProtect = 0;
          v28 = v23;
          if ( v65 == 2 )
          {
            v61 = VirtualAlloc(lpAddress, v23, 0x1000u, 0x40000040u);
            if ( v61 )
            {
              if ( !VirtualProtect(v61, v23, 4u, &flOldProtect) )
                CustomHeap_BadPageState_fatal_error((unsigned __int64)&Memory::VirtualAllocWrapper::Instance);
              v29 = lpAddress;
LABEL_43:
              Memory::AutoEnableDynamicCodeGen::~AutoEnableDynamicCodeGen((Memory::AutoEnableDynamicCodeGen *)&v64);
              v35 = (unsigned __int64)(unsigned int)v10 >> 6;
              v36 = v10 & 0x3F;
              v3 = v66;
              v37 = v36 + v66;
              if ( v36 + v66 > 0x40 )
              {
                v7[v35 + 7] &= ~(0xFFFFFFFFFFFFFFFFuLL >> v36 << v36);
                v51 = &v7[v35 + 8];
                v52 = v37 - 64;
                if ( v52 >= 0x40 )
                {
                  memset_0(v51, 0, 8 * ((unsigned __int64)v52 >> 6));
                  do
                  {
                    ++v51;
                    v52 -= 64;
                  }
                  while ( v52 >= 0x40 );
                }
                if ( v52 )
                  *v51 &= ~(0xFFFFFFFFFFFFFFFFuLL >> (64 - (unsigned __int8)v52));
                v3 = v66;
              }
              else
              {
                v7[v35 + 7] &= ~(0xFFFFFFFFFFFFFFFFuLL >> (64 - (unsigned __int8)v66) << v36);
              }
              BVStatic<272>::ClearRange(v5 + 14, (unsigned int)v10, v3);
              v38 = BVStatic<272>::Count(v5 + 9);
              v39 = v72;
              *((_DWORD *)v5 + 38) += v38 - v72;
              *((_DWORD *)v5 + 39) += v39 - v38 - v3;
              v4 = v68;
              if ( v29 )
              {
                v40 = v73;
                v41 = v75;
                v75[15] += *((unsigned int *)v5 + 38) - (unsigned __int64)v73;
                v41[29] += (unsigned __int64)(v3 + *((_DWORD *)v5 + 38) - v40) << 12;
                v42 = v22 << 12;
                v41[26] += v42;
                v43 = _InterlockedExchangeAdd64(&qword_1815C5860, v42);
                if ( qword_1815C5860 > (unsigned __int64)qword_1815C5858 )
                  qword_1815C5858 = qword_1815C5860;
                if ( (byte_1815C57C1 & 2) != 0 )
                  McTemplateU0x_EventWriteTransfer(
                    PROVIDER_JSCRIPT9_Context,
                    JSCRIPT_PAGE_ALLOCATOR_USED_SIZE,
                    v43 + v42);
                if ( !*((_DWORD *)v5 + 39) )
                {
                  if ( *((_DWORD *)v5 + 12) == *((_DWORD *)v5 + 16) )
                  {
                    v45 = 0;
                  }
                  else if ( *((_DWORD *)v5 + 38)
                         && ((v44 = v5[4]) == 0
                          || (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v44 + 24LL))(v44)) )
                  {
                    if ( *((_DWORD *)v5 + 39) )
                    {
                      v45 = v68;
                    }
                    else if ( *((_DWORD *)v5 + 38) == *((_DWORD *)v5 + 12) - *((_DWORD *)v5 + 16) )
                    {
                      v45 = v41 + 7;
                    }
                    else
                    {
                      v45 = v41 + 3;
                    }
                  }
                  else
                  {
                    v45 = v41 + 5;
                  }
                  *(_QWORD *)v5[1] = *v5;
                  *(_QWORD *)(*v5 + 8) = v5[1];
                  v46 = *v45;
                  v5[1] = *(_QWORD *)(*v45 + 8);
                  *v5 = v46;
                  **(_QWORD **)(v46 + 8) = v5;
                  *(_QWORD *)(v46 + 8) = v5;
                }
                *v76 = v7;
                return v29;
              }
              continue;
            }
            Memory::MemoryOperationLastError::RecordLastError();
            Memory::AutoEnableDynamicCodeGen::~AutoEnableDynamicCodeGen((Memory::AutoEnableDynamicCodeGen *)&v64);
          }
          else
          {
            v29 = lpAddress;
            if ( VirtualAlloc(lpAddress, v28, 0x1000u, 4u) )
              goto LABEL_43;
            Memory::MemoryOperationLastError::RecordLastError();
            if ( v27 )
            {
              v70 = 0;
              v62 = Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc;
              v63 = GetCurrentThread();
              ((void (__fastcall *)(HANDLE, __int64, int *))v62)(v63, 2, &v70);
            }
          }
          v3 = v66;
          v4 = v68;
          if ( v66 == 1 )
            continue;
          goto LABEL_16;
        }
        v47 = v10 + v24;
        v48 = v47 < *(_DWORD *)(v26 + 104);
        v4 = v68;
        if ( !v48 )
          continue;
        LOBYTE(v19) = v47;
        v49 = (unsigned __int64 *)v80 + ((unsigned __int64)v47 >> 6);
        v17 = v47 & 0xFFFFFFC0;
        for ( j = !_BitScanForward64((unsigned __int64 *)&v19, *v49 & (-1LL << v19));
              ;
              j = !_BitScanForward64((unsigned __int64 *)&v19, *v49) )
        {
          v65 = 0;
          if ( !j && (_DWORD)v19 != -1 )
            break;
          if ( ++v49 == v82 )
          {
LABEL_71:
            v20 = -1;
            goto LABEL_20;
          }
          v17 += 64;
        }
      }
      else
      {
LABEL_16:
        v16 = (unsigned __int64 *)v80 + ((unsigned __int64)(unsigned int)(v10 + 1) >> 6);
        v17 = (v10 + 1) & 0xFFFFFFC0;
        for ( k = !_BitScanForward64((unsigned __int64 *)&v19, *v16 & (-1LL << ((unsigned __int8)v10 + 1)));
              ;
              k = !_BitScanForward64((unsigned __int64 *)&v19, *v16) )
        {
          v65 = 0;
          if ( !k && (_DWORD)v19 != -1 )
            break;
          if ( ++v16 == v82 )
            goto LABEL_71;
          v17 += 64;
        }
      }
      v20 = v19 + v17;
LABEL_20:
      LODWORD(v10) = v20;
      goto LABEL_10;
    }
  }
}

```

## disassembly

```asm
0x180392a54  mov     rax, rsp
0x180392a57  mov     [rax+20h], rbx
0x180392a5b  mov     [rax+18h], r8
0x180392a5f  mov     [rax+10h], edx
0x180392a62  mov     [rax+8], rcx
0x180392a66  push    rbp
0x180392a67  push    rsi
0x180392a68  push    rdi
0x180392a69  push    r12
0x180392a6b  push    r13
0x180392a6d  push    r14
0x180392a6f  push    r15
0x180392a71  lea     rbp, [rax-5Fh]
0x180392a75  sub     rsp, 0E0h
0x180392a7c  mov     rax, cs:__security_cookie
0x180392a83  xor     rax, rsp
0x180392a86  mov     [rbp+57h+var_38], rax
0x180392a8a  mov     rax, [rbp+57h+arg_0]
0x180392a8e  mov     [rbp+57h+var_A8], rax
0x180392a92  mov     esi, [rbp+57h+arg_8]
0x180392a95  mov     [rsp+110h+var_D8], esi
0x180392a99  mov     rcx, [rbp+57h+arg_10]
0x180392a9d  mov     [rbp+57h+var_A0], rcx
0x180392aa1  add     rax, 48h ; 'H'
0x180392aa5  mov     [rbp+57h+var_D0], rax
0x180392aa9  mov     r15, rax
0x180392aac  mov     r15, [r15]
0x180392aaf  cmp     r15, rax
0x180392ab2  jnz     short loc_180392ADE
0x180392ab4  xor     eax, eax
0x180392ab6  mov     rcx, [rbp+57h+var_38]
0x180392aba  xor     rcx, rsp; StackCookie
0x180392abd  call    __security_check_cookie
0x180392ac2  mov     rbx, [rsp+110h+arg_18]
0x180392aca  add     rsp, 0E0h
0x180392ad1  pop     r15
0x180392ad3  pop     r14
0x180392ad5  pop     r13
0x180392ad7  pop     r12
0x180392ad9  pop     rdi
0x180392ada  pop     rsi
0x180392adb  pop     rbp
0x180392adc  retn
0x180392ade  lea     rdi, [r15+10h]
0x180392ae2  mov     ecx, [rdi+88h]
0x180392ae8  mov     [rbp+57h+var_B4], ecx
0x180392aeb  movups  xmm0, xmmword ptr [rdi+60h]
0x180392aef  movaps  [rbp+57h+var_90], xmm0
0x180392af3  movups  xmm1, xmmword ptr [rdi+70h]
0x180392af7  movaps  [rbp+57h+var_80], xmm1
0x180392afb  movsd   xmm0, qword ptr [rdi+80h]
0x180392b03  movsd   [rbp+57h+var_70], xmm0
0x180392b08  add     ecx, [rdi+8Ch]
0x180392b0e  cmp     ecx, esi
0x180392b10  mov     rax, [rbp+57h+var_D0]
0x180392b14  jb      short loc_180392AAC
0x180392b16  movups  xmm0, xmmword ptr [rdi+38h]
0x180392b1a  movups  [rbp+57h+var_60], xmm0
0x180392b1e  movups  xmm1, xmmword ptr [rdi+48h]
0x180392b22  movups  [rbp+57h+var_50], xmm1
0x180392b26  movsd   xmm0, qword ptr [rdi+58h]
0x180392b2b  movsd   [rbp+57h+var_40], xmm0
0x180392b30  lea     rbx, [rbp+57h+var_60]
0x180392b34  lea     rsi, [rbp+57h+var_90]
0x180392b38  mov     rdx, [rsi]
0x180392b3b  mov     rcx, rbx
0x180392b3e  call    ?Or@?$BVUnitT@_K@@QEAAXV1@@Z; BVUnitT<unsigned __int64>::Or(BVUnitT<unsigned __int64>)
0x180392b43  add     rbx, 8
0x180392b47  lea     rsi, [rsi+8]
0x180392b4b  lea     rax, [rbp+57h+var_38]
0x180392b4f  cmp     rbx, rax
0x180392b52  jnz     short loc_180392B38
0x180392b54  mov     eax, [rdi+88h]
0x180392b5a  mov     [rbp+57h+var_B8], eax
0x180392b5d  mov     [rsp+110h+var_DC], 0
0x180392b65  bsf     r14, qword ptr [rbp+57h+var_60]
0x180392b6a  setnz   al
0x180392b6d  or      r11d, 0FFFFFFFFh
0x180392b71  test    al, al
0x180392b73  jz      loc_180392D0A
0x180392b79  cmp     r14d, r11d
0x180392b7c  jz      loc_180392D0A
0x180392b82  mov     esi, [rsp+110h+var_D8]
0x180392b86  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180392b8a  cmp     r14d, r11d
0x180392b8d  mov     rax, [rbp+57h+var_D0]
0x180392b91  jz      loc_180392AAC
0x180392b97  mov     eax, [rdi+20h]
0x180392b9a  sub     eax, r14d
0x180392b9d  sub     eax, [rdi+30h]
0x180392ba0  cmp     eax, esi
0x180392ba2  mov     rax, [rbp+57h+var_D0]
0x180392ba6  jb      loc_180392AAC
0x180392bac  cmp     esi, 1
0x180392baf  jz      loc_180392C4F
0x180392bb5  mov     r8d, r14d
0x180392bb8  shr     r8, 6
0x180392bbc  mov     eax, r14d
0x180392bbf  and     eax, 3Fh
0x180392bc2  lea     r9d, [rax+rsi]
0x180392bc6  mov     r10, qword ptr [rbp+r8*8+57h+var_60]
0x180392bcb  mov     rdx, rbx
0x180392bce  cmp     r9d, 40h ; '@'
0x180392bd2  ja      loc_180392D45
0x180392bd8  mov     ecx, 40h ; '@'
0x180392bdd  sub     ecx, esi
0x180392bdf  shr     rdx, cl
0x180392be2  mov     ecx, eax
0x180392be4  shl     rdx, cl
0x180392be7  mov     rax, rdx
0x180392bea  and     rax, r10
0x180392bed  cmp     rax, rdx
0x180392bf0  jz      short loc_180392C4F
0x180392bf2  lea     edx, [r14+1]
0x180392bf6  mov     ecx, edx
0x180392bf8  mov     eax, edx
0x180392bfa  shr     rax, 6
0x180392bfe  lea     r8, [rbp+57h+var_60]
0x180392c02  lea     r8, [r8+rax*8]
0x180392c06  and     edx, 0FFFFFFC0h
0x180392c09  mov     rax, rbx
0x180392c0c  shl     rax, cl
0x180392c0f  and     rax, [r8]
0x180392c12  bsf     rcx, rax
0x180392c16  setnz   al
0x180392c19  test    al, al
0x180392c1b  mov     [rsp+110h+var_DC], 0
0x180392c23  jz      short loc_180392C35
0x180392c25  cmp     ecx, r11d
0x180392c28  jz      short loc_180392C35
0x180392c2a  lea     eax, [rcx+rdx]
0x180392c2d  mov     r14d, eax
0x180392c30  jmp     loc_180392B8A
0x180392c35  add     r8, 8
0x180392c39  lea     rax, [rbp+57h+var_38]
0x180392c3d  cmp     r8, rax
0x180392c40  jz      loc_180392FA1
0x180392c46  add     edx, 40h ; '@'
0x180392c49  bsf     rcx, [r8]
0x180392c4d  jmp     short loc_180392C16
0x180392c4f  mov     ecx, r14d
0x180392c52  shl     ecx, 0Ch
0x180392c55  add     rcx, [rdi+18h]
0x180392c59  mov     [rbp+57h+lpAddress], rcx
0x180392c5d  mov     r12d, esi
0x180392c60  mov     [rbp+57h+var_B0], r12
0x180392c64  mov     r13d, esi
0x180392c67  shl     r13, 0Ch
0x180392c6b  lea     rax, [r13-1]
0x180392c6f  test    rcx, rax
0x180392c72  jnz     loc_180392F7C
0x180392c78  xor     edx, edx
0x180392c7a  mov     cl, 1
0x180392c7c  mov     rax, [rdi+8]
0x180392c80  test    cl, cl
0x180392c82  jz      loc_180392F1E
0x180392c88  mov     ecx, [rax+0D8h]
0x180392c8e  mov     [rsp+110h+var_DC], ecx
0x180392c92  xor     bl, bl
0x180392c94  mov     byte ptr [rsp+110h+var_E0], bl
0x180392c98  cmp     ecx, 2
0x180392c9b  jz      loc_18039301A
0x180392ca1  mov     [rbp+57h+flOldProtect], 0
0x180392ca8  mov     r8d, 1000h; flAllocationType
0x180392cae  mov     rdx, r13; dwSize
0x180392cb1  cmp     [rsp+110h+var_DC], 2
0x180392cb6  jz      loc_1803931C6
0x180392cbc  mov     r9d, 4; flProtect
0x180392cc2  mov     r13, [rbp+57h+lpAddress]
0x180392cc6  mov     rcx, r13; lpAddress
0x180392cc9  call    cs:__imp_VirtualAlloc
0x180392cd0  nop     dword ptr [rax+rax+00h]
0x180392cd5  test    rax, rax
0x180392cd8  jnz     loc_180392D8E
0x180392cde  call    ?RecordLastError@MemoryOperationLastError@Memory@@SAXXZ; Memory::MemoryOperationLastError::RecordLastError(void)
0x180392ce3  nop
0x180392ce4  test    bl, bl
0x180392ce6  jnz     loc_1803931F6
0x180392cec  mov     esi, [rsp+110h+var_D8]
0x180392cf0  cmp     esi, 1
0x180392cf3  mov     rax, [rbp+57h+var_D0]
0x180392cf7  jz      loc_180392AAC
0x180392cfd  or      r11d, 0FFFFFFFFh
0x180392d01  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180392d05  jmp     loc_180392BF2
0x180392d0a  lea     rcx, [rbp+57h+var_60]
0x180392d0e  xor     edx, edx
0x180392d10  add     rcx, 8
0x180392d14  lea     rax, [rbp+57h+var_38]
0x180392d18  cmp     rcx, rax
0x180392d1b  jz      loc_180392FB2
0x180392d21  add     edx, 40h ; '@'
0x180392d24  mov     [rsp+110h+var_DC], 0
0x180392d2c  bsf     r8, [rcx]
0x180392d30  setnz   al
0x180392d33  test    al, al
0x180392d35  jz      short loc_180392D10
0x180392d37  cmp     r8d, r11d
0x180392d3a  jz      short loc_180392D10
0x180392d3c  lea     r14d, [r8+rdx]
0x180392d40  jmp     loc_180392B82
0x180392d45  mov     ecx, eax
0x180392d47  shr     rdx, cl
0x180392d4a  shl     rdx, cl
0x180392d4d  mov     rax, rdx
0x180392d50  and     rax, r10
0x180392d53  cmp     rax, rdx
0x180392d56  jnz     loc_180392BF2
0x180392d5c  lea     r8, [rbp+r8*8+57h+var_60+8]
0x180392d61  lea     eax, [r9-40h]
0x180392d65  cmp     eax, 40h ; '@'
0x180392d68  jnb     loc_180393005
0x180392d6e  test    eax, eax
0x180392d70  jz      loc_180392C4F
0x180392d76  mov     ecx, 40h ; '@'
0x180392d7b  sub     ecx, eax
0x180392d7d  mov     rdx, rbx
0x180392d80  shr     rdx, cl
0x180392d83  mov     rax, [r8]
0x180392d86  and     rax, rdx
0x180392d89  jmp     loc_180392BED
0x180392d8e  lea     rcx, [rsp+110h+var_E0]; this
0x180392d93  call    ??1AutoEnableDynamicCodeGen@Memory@@QEAA@XZ; Memory::AutoEnableDynamicCodeGen::~AutoEnableDynamicCodeGen(void)
0x180392d98  mov     edx, r14d
0x180392d9b  shr     rdx, 6
0x180392d9f  mov     r8d, r14d
0x180392da2  and     r8d, 3Fh
0x180392da6  mov     esi, [rsp+110h+var_D8]
0x180392daa  lea     ebx, [r8+rsi]
0x180392dae  or      rax, 0FFFFFFFFFFFFFFFFh
0x180392db2  cmp     ebx, 40h ; '@'
0x180392db5  ja      loc_180392FBA
0x180392dbb  lea     ecx, [rax+41h]
0x180392dbe  sub     ecx, esi
0x180392dc0  shr     rax, cl
0x180392dc3  mov     ecx, r8d
0x180392dc6  shl     rax, cl
0x180392dc9  not     rax
0x180392dcc  and     [rdi+rdx*8+38h], rax
0x180392dd1  jmp     short loc_180392DEF
0x180392dd3  test    ebx, ebx
0x180392dd5  jz      short loc_180392DEB
0x180392dd7  mov     ecx, 40h ; '@'
0x180392ddc  sub     ecx, ebx
0x180392dde  or      rax, 0FFFFFFFFFFFFFFFFh
0x180392de2  shr     rax, cl
0x180392de5  not     rax
0x180392de8  and     [rsi], rax
0x180392deb  mov     esi, [rsp+110h+var_D8]
0x180392def  mov     r8d, esi
0x180392df2  mov     edx, r14d
0x180392df5  lea     rcx, [rdi+60h]
0x180392df9  call    ?ClearRange@?$BVStatic@$0BBA@@@QEAAXII@Z; BVStatic<272>::ClearRange(uint,uint)
0x180392dfe  lea     rcx, [rdi+38h]
0x180392e02  call    ?Count@?$BVStatic@$0BBA@@@QEBAIXZ; BVStatic<272>::Count(void)
0x180392e07  mov     ecx, eax
0x180392e09  mov     edx, [rbp+57h+var_B8]
0x180392e0c  sub     eax, edx
0x180392e0e  add     [rdi+88h], eax
0x180392e14  sub     edx, ecx
0x180392e16  sub     edx, esi
0x180392e18  add     [rdi+8Ch], edx
0x180392e1e  test    r13, r13
0x180392e21  mov     rax, [rbp+57h+var_D0]
0x180392e25  jz      loc_180392AAC
0x180392e2b  mov     ecx, [rdi+88h]
0x180392e31  mov     edx, [rbp+57h+var_B4]
0x180392e34  sub     rcx, rdx
0x180392e37  mov     rbx, [rbp+57h+var_A8]
0x180392e3b  add     [rbx+78h], rcx
0x180392e3f  mov     eax, [rdi+88h]
0x180392e45  sub     eax, edx
0x180392e47  add     eax, esi
0x180392e49  shl     rax, 0Ch
0x180392e4d  add     [rbx+0E8h], rax
0x180392e54  shl     r12, 0Ch
0x180392e58  add     [rbx+0D0h], r12
0x180392e5f  mov     rax, r12
0x180392e62  lock xadd cs:qword_1815C5860, rax
0x180392e6b  mov     rcx, cs:qword_1815C5860
0x180392e72  cmp     rcx, cs:qword_1815C5858
0x180392e79  jbe     short loc_180392E82
0x180392e7b  mov     cs:qword_1815C5858, rcx
0x180392e82  test    cs:byte_1815C57C1, 2
0x180392e89  jnz     loc_180393263
0x180392e8f  cmp     dword ptr [rdi+8Ch], 0
0x180392e96  jnz     short loc_180392F0F
0x180392e98  mov     eax, [rdi+20h]
0x180392e9b  cmp     eax, [rdi+30h]
0x180392e9e  jz      loc_18039327F
0x180392ea4  cmp     dword ptr [rdi+88h], 0
0x180392eab  jz      loc_180392FA9
0x180392eb1  mov     rcx, [rdi+10h]
0x180392eb5  test    rcx, rcx
0x180392eb8  jnz     loc_180393286
0x180392ebe  cmp     dword ptr [rdi+8Ch], 0
0x180392ec5  jnz     loc_180392F98
0x180392ecb  mov     eax, [rdi+20h]
0x180392ece  sub     eax, [rdi+30h]
0x180392ed1  cmp     [rdi+88h], eax
  ... truncated ...
```
