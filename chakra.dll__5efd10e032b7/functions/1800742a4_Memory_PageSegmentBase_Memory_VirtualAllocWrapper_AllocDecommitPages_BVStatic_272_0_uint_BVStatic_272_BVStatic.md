# Memory::PageSegmentBase<Memory::VirtualAllocWrapper>::AllocDecommitPages<BVStatic<272>,0>(uint,BVStatic<272>,BVStatic<272>)

- ea: `0x1800742a4`
- end: `0x1800749a9`
- name: `??$AllocDecommitPages@V?$BVStatic@$0BBA@@@$0A@@?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@Memory@@QEAAPEADIV?$BVStatic@$0BBA@@@0@Z`
- size: `1797`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002570c`
- `0x180074e10`

## callees

- `0x1800742a4`
- `0x1800749b0`
- `0x180074d68`
- `0x1801b5cc8`
- `0x1802ebecc`
- `0x180408f60`
- `0x18048e5d8`
- `0x1805a9c5a`
- `0x1805a9e80`
- `0x1805cd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007494f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007494f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180074877`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180074877`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180074899`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180074899`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800748bb`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800748d5`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800748f2`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800748bb`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800748d5`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800748f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007490e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007490e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180074638`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180074673`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007497e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180074638`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180074673`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18007497e`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800744ab`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180074738`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1800744ab`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180074738`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18007475c`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x18007475c`

## string_xrefs

- `0x180074892`: `api-ms-win-core-processthreads-l1-1-3.dll`
- `0x1800748e8`: `GetThreadInformation`
- `0x1800748cb`: `SetThreadInformation`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LPVOID __fastcall Memory::PageSegmentBase<Memory::VirtualAllocWrapper>::AllocDecommitPages<BVStatic<272>,0>(
        __int64 *a1,
        unsigned int a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v5; // r12d
  _QWORD *v7; // rbx
  unsigned __int64 v8; // r8
  __int64 v9; // rsi
  int v10; // r11d
  int v11; // eax
  __int64 v12; // r10
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // rax
  unsigned int v15; // esi
  unsigned __int64 *v16; // rdx
  unsigned int v17; // esi
  bool j; // zf
  __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  SIZE_T v21; // r13
  unsigned __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rcx
  char v25; // bl
  LPVOID v26; // r12
  unsigned __int64 v27; // r12
  int v28; // esi
  unsigned int v29; // r13d
  unsigned int v30; // edx
  unsigned int v31; // ebx
  int v32; // eax
  unsigned __int64 *v34; // rcx
  int v35; // edx
  int (*v36)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int); // r12
  HANDLE CurrentThread; // rax
  int (*v38)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int); // rbx
  HANDLE v39; // rax
  unsigned int i; // eax
  __int64 v41; // rdx
  void *v42; // rax
  __int64 *v43; // r9
  unsigned int v44; // r13d
  __int64 *v45; // rsi
  HMODULE ModuleHandleW; // rax
  HMODULE v47; // r12
  unsigned int (__fastcall *v48)(HANDLE, __int64, struct _PROCESS_MITIGATION_DYNAMIC_CODE_POLICY *); // r12
  HANDLE CurrentProcess; // rax
  int (*v50)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int); // rbx
  HANDLE v51; // rax
  char v52[4]; // [rsp+38h] [rbp-59h] BYREF
  unsigned int v53; // [rsp+3Ch] [rbp-55h] BYREF
  int v54; // [rsp+40h] [rbp-51h] BYREF
  unsigned int v55; // [rsp+44h] [rbp-4Dh]
  int v56; // [rsp+48h] [rbp-49h]
  DWORD flOldProtect; // [rsp+4Ch] [rbp-45h] BYREF
  int v58; // [rsp+50h] [rbp-41h]
  LPVOID lpAddress; // [rsp+58h] [rbp-39h]
  FARPROC ProcAddress; // [rsp+60h] [rbp-31h]
  __int64 v61; // [rsp+68h] [rbp-29h]
  struct _RTL_CRITICAL_SECTION *v62; // [rsp+70h] [rbp-21h]
  _OWORD v63[2]; // [rsp+78h] [rbp-19h] BYREF
  __int64 v64; // [rsp+98h] [rbp+7h]
  _QWORD v65[9]; // [rsp+A0h] [rbp+Fh] BYREF

  v61 = -2;
  v5 = a2;
  v55 = a2;
  if ( *((_DWORD *)a1 + 32) + *((_DWORD *)a1 + 33) >= a2 )
  {
    v63[0] = *(_OWORD *)a3;
    v63[1] = *(_OWORD *)(a3 + 16);
    v64 = *(_QWORD *)(a3 + 32);
    v7 = v63;
    do
      BVUnitT<unsigned __int64>::Or(v7++, *a4++);
    while ( v7 != v65 );
    v58 = *((_DWORD *)a1 + 32);
    v53 = 0;
    j = !_BitScanForward64((unsigned __int64 *)&v9, *(unsigned __int64 *)&v63[0]);
    v10 = -1;
    if ( j || (_DWORD)v9 == -1 )
    {
      v34 = (unsigned __int64 *)v63;
      v35 = 0;
      do
      {
        if ( ++v34 == v65 )
        {
          LODWORD(v9) = -1;
          goto LABEL_6;
        }
        v35 += 64;
        v53 = 0;
        j = !_BitScanForward64(&v8, *v34);
      }
      while ( j || (_DWORD)v8 == -1 );
      LODWORD(v9) = v8 + v35;
    }
    while ( 1 )
    {
LABEL_6:
      if ( (_DWORD)v9 == v10 || *((_DWORD *)a1 + 6) - *((_DWORD *)a1 + 10) - (int)v9 < v5 )
        return 0;
      if ( v5 != 1 )
      {
        v8 = (unsigned __int64)(unsigned int)v9 >> 6;
        v11 = v9 & 0x3F;
        v12 = *((_QWORD *)v63 + v8);
        if ( v11 + v5 <= 0x40 )
        {
          v13 = 0xFFFFFFFFFFFFFFFFuLL >> (64 - (unsigned __int8)v5) << v11;
          v14 = v12 & v13;
          goto LABEL_11;
        }
        if ( (v12 & (0xFFFFFFFFFFFFFFFFuLL >> v11 << v11)) != 0xFFFFFFFFFFFFFFFFuLL >> v11 << v11 )
          goto LABEL_12;
        v8 = (unsigned __int64)v63 + 8 * v8 + 8;
        for ( i = v11 + v5 - 64; i >= 0x40; i -= 64 )
        {
          if ( *(_QWORD *)v8 != -1 )
            goto LABEL_12;
          v8 += 8LL;
        }
        if ( i )
        {
          v13 = 0xFFFFFFFFFFFFFFFFuLL >> (64 - (unsigned __int8)i);
          v14 = *(_QWORD *)v8 & v13;
LABEL_11:
          if ( v14 != v13 )
            goto LABEL_12;
        }
      }
      v20 = a1[2] + (unsigned int)((_DWORD)v9 << 12);
      lpAddress = (LPVOID)v20;
      v21 = (unsigned __int64)v5 << 12;
      if ( ((v21 - 1) & v20) != 0 )
      {
        v22 = (v20 % v21) >> 12;
        LOBYTE(v8) = 0;
      }
      else
      {
        LODWORD(v22) = 0;
        LOBYTE(v8) = 1;
      }
      v23 = *a1;
      v24 = *a1 - 8;
      if ( (_BYTE)v8 )
      {
        v56 = *(_DWORD *)((v24 & -(__int64)(v23 != 0)) + 0xE0);
        v25 = 0;
        v52[0] = 0;
        if ( v56 == 2 )
        {
          if ( !Memory::AutoEnableDynamicCodeGen::processPolicyObtained )
          {
            v62 = &Memory::AutoEnableDynamicCodeGen::processPolicyCS;
            EnterCriticalSection(&Memory::AutoEnableDynamicCodeGen::processPolicyCS);
            if ( !Memory::AutoEnableDynamicCodeGen::processPolicyObtained )
            {
              ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-processthreads-l1-1-3.dll");
              v47 = ModuleHandleW;
              if ( !ModuleHandleW
                || (ProcAddress = GetProcAddress(ModuleHandleW, "GetProcessMitigationPolicy"),
                    Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc = (int (*)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int))GetProcAddress(v47, "SetThreadInformation"),
                    Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc = (int (*)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int))GetProcAddress(v47, "GetThreadInformation"),
                    (v48 = (unsigned int (__fastcall *)(HANDLE, __int64, struct _PROCESS_MITIGATION_DYNAMIC_CODE_POLICY *))ProcAddress) == 0)
                || (CurrentProcess = GetCurrentProcess(),
                    !v48(CurrentProcess, 2, &Memory::AutoEnableDynamicCodeGen::processPolicy)) )
              {
                Memory::AutoEnableDynamicCodeGen::processPolicy.Flags &= ~1u;
              }
              Memory::AutoEnableDynamicCodeGen::processPolicyObtained = 1;
            }
            LeaveCriticalSection(&Memory::AutoEnableDynamicCodeGen::processPolicyCS);
          }
          if ( (Memory::AutoEnableDynamicCodeGen::processPolicy.Flags & 1) != 0
            && (Memory::AutoEnableDynamicCodeGen::processPolicy.Flags & 2) != 0 )
          {
            if ( Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc )
            {
              v36 = Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc;
              if ( Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc )
              {
                v54 = 0;
                CurrentThread = GetCurrentThread();
                if ( !((unsigned int (__fastcall *)(HANDLE, __int64, int *))v36)(CurrentThread, 2, &v54) || v54 != 1 )
                {
                  v54 = 1;
                  v38 = Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc;
                  v39 = GetCurrentThread();
                  ((void (__fastcall *)(HANDLE, __int64, int *))v38)(v39, 2, &v54);
                  v25 = 1;
                  v52[0] = 1;
                }
              }
            }
          }
        }
        flOldProtect = 0;
        if ( v56 == 2 )
        {
          v42 = VirtualAlloc(lpAddress, v21, 0x1000u, 0x40000040u);
          v26 = v42;
          if ( v42 )
          {
            if ( !VirtualProtect(v42, v21, 4u, &flOldProtect) )
              CustomHeap_BadPageState_unrecoverable_error((unsigned __int64)&Memory::VirtualAllocWrapper::Instance);
LABEL_22:
            if ( v25 )
            {
              v53 = 0;
              v50 = Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc;
              v51 = GetCurrentThread();
              ((void (__fastcall *)(HANDLE, __int64, unsigned int *))v50)(v51, 2, &v53);
            }
            if ( v26 )
            {
              v27 = (unsigned __int64)(unsigned int)v9 >> 6;
              v28 = v9 & 0x3F;
              v29 = v55;
              v30 = v28 + v55;
              v53 = v28 + v55;
              v31 = v28 + v55 - 64;
              if ( v28 + v55 > 0x40 )
              {
                a1[v27 + 6] &= ~(0xFFFFFFFFFFFFFFFFuLL >> v28 << v28);
                v43 = &a1[v27 + 7];
                v44 = v31;
                if ( v31 >= 0x40 )
                {
                  memset_0(&a1[v27 + 7], 0, 8 * ((unsigned __int64)v31 >> 6));
                  v43 = &a1[v27 + 7];
                  do
                  {
                    ++v43;
                    v44 -= 64;
                  }
                  while ( v44 >= 0x40 );
                  v30 = v53;
                }
                if ( v44 )
                  *v43 &= ~(0xFFFFFFFFFFFFFFFFuLL >> (64 - (unsigned __int8)v44));
                v29 = v55;
              }
              else
              {
                a1[v27 + 6] &= ~(0xFFFFFFFFFFFFFFFFuLL >> (64 - (unsigned __int8)v55) << v28);
              }
              if ( v30 > 0x40 )
              {
                a1[v27 + 11] &= ~(0xFFFFFFFFFFFFFFFFuLL >> v28 << v28);
                v45 = &a1[v27 + 12];
                if ( v31 >= 0x40 )
                {
                  memset_0(&a1[v27 + 12], 0, 8 * ((unsigned __int64)v31 >> 6));
                  do
                  {
                    ++v45;
                    v31 -= 64;
                  }
                  while ( v31 >= 0x40 );
                }
                if ( v31 )
                  *v45 &= ~(0xFFFFFFFFFFFFFFFFuLL >> (64 - (unsigned __int8)v31));
              }
              else
              {
                a1[v27 + 11] &= ~(0xFFFFFFFFFFFFFFFFuLL >> (64 - (unsigned __int8)v29) << v28);
              }
              v32 = BVStatic<272>::Count(a1 + 6);
              *((_DWORD *)a1 + 32) = v32 + *((_DWORD *)a1 + 32) - v58;
              *((_DWORD *)a1 + 33) = v58 + *((_DWORD *)a1 + 33) - v29 - v32;
              return lpAddress;
            }
            goto LABEL_54;
          }
        }
        else
        {
          v26 = VirtualAlloc(lpAddress, v21, 0x1000u, 4u);
          if ( v26 )
            goto LABEL_22;
        }
        Memory::MemoryOperationLastError::RecordLastError();
        Memory::AutoEnableDynamicCodeGen::~AutoEnableDynamicCodeGen((Memory::AutoEnableDynamicCodeGen *)v52);
LABEL_54:
        v5 = v55;
        if ( v55 == 1 )
          return 0;
        v10 = -1;
LABEL_12:
        v15 = v9 + 1;
        LOBYTE(v19) = v15;
        v16 = (unsigned __int64 *)v63 + ((unsigned __int64)v15 >> 6);
        v17 = v15 & 0xFFFFFFC0;
        for ( j = !_BitScanForward64((unsigned __int64 *)&v19, *v16 & (-1LL << v19));
              ;
              j = !_BitScanForward64((unsigned __int64 *)&v19, *v16) )
        {
          v56 = 0;
          if ( !j && (_DWORD)v19 != v10 )
          {
            LODWORD(v9) = v19 + v17;
            goto LABEL_6;
          }
          if ( ++v16 == v65 )
            break;
          v17 += 64;
        }
        LODWORD(v9) = v10;
      }
      else
      {
        v41 = (unsigned int)(v9 + v22);
        if ( (unsigned int)v41 >= *(_DWORD *)((v24 & -(__int64)(v23 != 0)) + 0x68) )
          return 0;
        LODWORD(v9) = BVStatic<272>::GetNextBit(v63, v41, v8, &Memory::AutoEnableDynamicCodeGen::processPolicyCS);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800742a4  mov     rax, rsp
0x1800742a7  mov     [rax+20h], r9
0x1800742ab  mov     [rax+18h], r8
0x1800742af  mov     [rax+10h], edx
0x1800742b2  mov     [rax+8], rcx
0x1800742b6  push    rbp
0x1800742b7  push    rbx
0x1800742b8  push    rsi
0x1800742b9  push    rdi
0x1800742ba  push    r12
0x1800742bc  push    r13
0x1800742be  push    r14
0x1800742c0  push    r15
0x1800742c2  lea     rbp, [rax-5Fh]
0x1800742c6  sub     rsp, 0A8h
0x1800742cd  mov     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFEh
0x1800742d5  mov     rax, cs:__security_cookie
0x1800742dc  xor     rax, rsp
0x1800742df  mov     [rbp+57h+var_48], rax
0x1800742e3  mov     r14, [rbp+57h+arg_0]
0x1800742e7  mov     r12d, [rbp+57h+arg_8]
0x1800742eb  mov     [rbp+57h+var_A4], r12d
0x1800742ef  mov     rcx, [rbp+57h+arg_10]
0x1800742f3  mov     rdi, [rbp+57h+arg_18]
0x1800742f7  mov     eax, [r14+84h]
0x1800742fe  add     eax, [r14+80h]
0x180074305  cmp     eax, r12d
0x180074308  jb      loc_180074709
0x18007430e  movaps  xmm0, xmmword ptr [rcx]
0x180074311  movups  [rbp+57h+var_70], xmm0
0x180074315  movaps  xmm1, xmmword ptr [rcx+10h]
0x180074319  movups  [rbp+57h+var_60], xmm1
0x18007431d  movsd   xmm0, qword ptr [rcx+20h]
0x180074322  movsd   [rbp+57h+var_50], xmm0
0x180074327  lea     rbx, [rbp+57h+var_70]
0x18007432b  mov     rdx, [rdi]
0x18007432e  mov     rcx, rbx
0x180074331  call    ?Or@?$BVUnitT@_K@@QEAAXV1@@Z; BVUnitT<unsigned __int64>::Or(BVUnitT<unsigned __int64>)
0x180074336  add     rbx, 8
0x18007433a  lea     rdi, [rdi+8]
0x18007433e  lea     rax, [rbp+57h+var_48]
0x180074342  cmp     rbx, rax
0x180074345  jnz     short loc_18007432B
0x180074347  mov     eax, [r14+80h]
0x18007434e  mov     [rbp+57h+var_98], eax
0x180074351  mov     [rbp+57h+var_AC], 0
0x180074358  bsf     rsi, qword ptr [rbp+57h+var_70]
0x18007435d  setnz   al
0x180074360  mov     r15d, 40h ; '@'
0x180074366  or      r11d, 0FFFFFFFFh
0x18007436a  test    al, al
0x18007436c  jz      loc_1800745A1
0x180074372  cmp     esi, r11d
0x180074375  jz      loc_1800745A1
0x18007437b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18007437f  lea     r9, ?processPolicyCS@AutoEnableDynamicCodeGen@Memory@@0VCriticalSection@@A; CriticalSection Memory::AutoEnableDynamicCodeGen::processPolicyCS
0x180074386  cmp     esi, r11d
0x180074389  jz      loc_180074709
0x18007438f  mov     eax, [r14+18h]
0x180074393  sub     eax, [r14+28h]
0x180074397  sub     eax, esi
0x180074399  cmp     eax, r12d
0x18007439c  jb      loc_180074709
0x1800743a2  cmp     r12d, 1
0x1800743a6  jz      loc_180074431
0x1800743ac  mov     r8d, esi
0x1800743af  shr     r8, 6
0x1800743b3  mov     eax, esi
0x1800743b5  and     eax, 3Fh
0x1800743b8  lea     r9d, [rax+r12]
0x1800743bc  mov     r10, qword ptr [rbp+r8*8+57h+var_70]
0x1800743c1  mov     rdx, rdi
0x1800743c4  cmp     r9d, r15d
0x1800743c7  ja      loc_1800746A2
0x1800743cd  mov     ecx, r15d
0x1800743d0  sub     ecx, r12d
0x1800743d3  shr     rdx, cl
0x1800743d6  mov     ecx, eax
0x1800743d8  shl     rdx, cl
0x1800743db  mov     rax, rdx
0x1800743de  and     rax, r10
0x1800743e1  cmp     rax, rdx
0x1800743e4  jz      short loc_18007442A
0x1800743e6  inc     esi
0x1800743e8  mov     ecx, esi
0x1800743ea  mov     eax, esi
0x1800743ec  shr     rax, 6
0x1800743f0  lea     rdx, [rbp+57h+var_70]
0x1800743f4  lea     rdx, [rdx+rax*8]
0x1800743f8  and     esi, 0FFFFFFC0h
0x1800743fb  mov     rax, rdi
0x1800743fe  shl     rax, cl
0x180074401  and     rax, [rdx]
0x180074404  bsf     rcx, rax
0x180074408  mov     [rbp+57h+var_A0], 0
0x18007440f  setnz   al
0x180074412  test    al, al
0x180074414  jz      loc_180074584
0x18007441a  cmp     ecx, r11d
0x18007441d  jz      loc_180074584
0x180074423  add     esi, ecx
0x180074425  jmp     loc_18007437F
0x18007442a  lea     r9, ?processPolicyCS@AutoEnableDynamicCodeGen@Memory@@0VCriticalSection@@A; CriticalSection Memory::AutoEnableDynamicCodeGen::processPolicyCS
0x180074431  mov     ecx, esi
0x180074433  shl     ecx, 0Ch
0x180074436  add     rcx, [r14+10h]
0x18007443a  mov     [rbp+57h+lpAddress], rcx
0x18007443e  mov     r13d, r12d
0x180074441  shl     r13, 0Ch
0x180074445  lea     rax, [r13-1]
0x180074449  test    rcx, rax
0x18007444c  jnz     loc_1800745DB
0x180074452  xor     edx, edx
0x180074454  mov     r8b, 1
0x180074457  mov     rax, [r14]
0x18007445a  lea     rcx, [rax-8]
0x18007445e  test    r8b, r8b
0x180074461  jz      loc_1800746E9
0x180074467  neg     rax
0x18007446a  sbb     rax, rax
0x18007446d  and     rax, rcx
0x180074470  mov     ecx, [rax+0E0h]
0x180074476  mov     [rbp+57h+var_A0], ecx
0x180074479  xor     bl, bl
0x18007447b  mov     [rbp+57h+var_B0], bl
0x18007447e  cmp     ecx, 2
0x180074481  jz      loc_1800745EF
0x180074487  mov     [rbp+57h+flOldProtect], 0
0x18007448e  mov     r8d, 1000h; flAllocationType
0x180074494  mov     rdx, r13; dwSize
0x180074497  mov     rcx, [rbp+57h+lpAddress]; lpAddress
0x18007449b  cmp     [rbp+57h+var_A0], 2
0x18007449f  jz      loc_180074732
0x1800744a5  mov     r9d, 4; flProtect
0x1800744ab  call    cs:__imp_VirtualAlloc
0x1800744b2  nop     dword ptr [rax+rax+00h]
0x1800744b7  mov     r12, rax
0x1800744ba  test    rax, rax
0x1800744bd  jz      loc_180074710
0x1800744c3  test    bl, bl
0x1800744c5  jnz     loc_180074970
0x1800744cb  test    r12, r12
0x1800744ce  jz      loc_18007471F
0x1800744d4  mov     r12d, esi
0x1800744d7  shr     r12, 6
0x1800744db  and     esi, 3Fh
0x1800744de  mov     r13d, [rbp+57h+var_A4]
0x1800744e2  lea     edx, [rsi+r13]
0x1800744e6  mov     [rbp+57h+var_AC], edx
0x1800744e9  lea     ebx, [rdx-40h]
0x1800744ec  mov     rax, rdi
0x1800744ef  cmp     edx, r15d
0x1800744f2  ja      loc_180074791
0x1800744f8  mov     ecx, r15d
0x1800744fb  sub     ecx, r13d
0x1800744fe  shr     rax, cl
0x180074501  mov     ecx, esi
0x180074503  shl     rax, cl
0x180074506  not     rax
0x180074509  and     [r14+r12*8+30h], rax
0x18007450e  cmp     edx, r15d
0x180074511  ja      loc_1800747FE
0x180074517  sub     r15d, r13d
0x18007451a  mov     cl, r15b
0x18007451d  shr     rdi, cl
0x180074520  mov     ecx, esi
0x180074522  shl     rdi, cl
0x180074525  not     rdi
0x180074528  and     [r14+r12*8+58h], rdi
0x18007452d  lea     rcx, [r14+30h]
0x180074531  call    ?Count@?$BVStatic@$0BBA@@@QEBAIXZ; BVStatic<272>::Count(void)
0x180074536  mov     ecx, [r14+80h]
0x18007453d  sub     ecx, [rbp+57h+var_98]
0x180074540  add     ecx, eax
0x180074542  mov     [r14+80h], ecx
0x180074549  mov     ecx, [r14+84h]
0x180074550  sub     ecx, r13d
0x180074553  sub     ecx, eax
0x180074555  add     ecx, [rbp+57h+var_98]
0x180074558  mov     [r14+84h], ecx
0x18007455f  mov     rax, [rbp+57h+lpAddress]
0x180074563  mov     rcx, [rbp+57h+var_48]
0x180074567  xor     rcx, rsp; StackCookie
0x18007456a  call    __security_check_cookie
0x18007456f  add     rsp, 0A8h
0x180074576  pop     r15
0x180074578  pop     r14
0x18007457a  pop     r13
0x18007457c  pop     r12
0x18007457e  pop     rdi
0x18007457f  pop     rsi
0x180074580  pop     rbx
0x180074581  pop     rbp
0x180074582  retn
0x180074584  add     rdx, 8
0x180074588  lea     rax, [rbp+57h+var_48]
0x18007458c  cmp     rdx, rax
0x18007458f  jz      loc_180074789
0x180074595  add     esi, r15d
0x180074598  bsf     rcx, [rdx]
0x18007459c  jmp     loc_180074408
0x1800745a1  lea     rcx, [rbp+57h+var_70]
0x1800745a5  xor     edx, edx
0x1800745a7  add     rcx, 8
0x1800745ab  lea     rax, [rbp+57h+var_48]
0x1800745af  cmp     rcx, rax
0x1800745b2  jz      loc_180074781
0x1800745b8  add     edx, r15d
0x1800745bb  mov     [rbp+57h+var_AC], 0
0x1800745c2  bsf     r8, [rcx]
0x1800745c6  setnz   al
0x1800745c9  test    al, al
0x1800745cb  jz      short loc_1800745A7
0x1800745cd  cmp     r8d, r11d
0x1800745d0  jz      short loc_1800745A7
0x1800745d2  lea     esi, [r8+rdx]
0x1800745d6  jmp     loc_18007437B
0x1800745db  xor     edx, edx
0x1800745dd  mov     rax, rcx
0x1800745e0  div     r13
0x1800745e3  shr     rdx, 0Ch
0x1800745e7  xor     r8b, r8b
0x1800745ea  jmp     loc_180074457
0x1800745ef  mov     al, cs:?processPolicyObtained@AutoEnableDynamicCodeGen@Memory@@0_NC; bool volatile Memory::AutoEnableDynamicCodeGen::processPolicyObtained
0x1800745f5  test    al, al
0x1800745f7  jz      loc_180074870
0x1800745fd  mov     eax, cs:?processPolicy@AutoEnableDynamicCodeGen@Memory@@0U_PROCESS_MITIGATION_DYNAMIC_CODE_POLICY@@A; _PROCESS_MITIGATION_DYNAMIC_CODE_POLICY Memory::AutoEnableDynamicCodeGen::processPolicy
0x180074603  test    al, 1
0x180074605  jz      loc_180074487
0x18007460b  test    al, 2
0x18007460d  jz      loc_180074487
0x180074613  cmp     cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@Memory@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@@0K@ZEA, 0; int (*Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,_THREAD_INFORMATION_CLASS,void *,ulong)
0x18007461b  jz      loc_180074487
0x180074621  mov     r12, cs:?GetThreadInformationProc@AutoEnableDynamicCodeGen@Memory@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@@0K@ZEA; int (*Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc)(void *,_THREAD_INFORMATION_CLASS,void *,ulong)
0x180074628  test    r12, r12
0x18007462b  jz      loc_180074487
0x180074631  mov     [rbp+57h+var_A8], 0
0x180074638  call    cs:__imp_GetCurrentThread
0x18007463f  nop     dword ptr [rax+rax+00h]
0x180074644  mov     rcx, rax
0x180074647  mov     r9d, 4
0x18007464d  lea     r8, [rbp+57h+var_A8]
0x180074651  lea     edx, [r9-2]
0x180074655  mov     rax, r12
0x180074658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007465d  test    eax, eax
0x18007465f  jnz     loc_180074961
0x180074665  mov     [rbp+57h+var_A8], 1
0x18007466c  mov     rbx, cs:?SetThreadInformationProc@AutoEnableDynamicCodeGen@Memory@@0P6AHPEAXW4_THREAD_INFORMATION_CLASS@@0K@ZEA; int (*Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc)(void *,_THREAD_INFORMATION_CLASS,void *,ulong)
0x180074673  call    cs:__imp_GetCurrentThread
0x18007467a  nop     dword ptr [rax+rax+00h]
0x18007467f  mov     rcx, rax
0x180074682  mov     r9d, 4
0x180074688  lea     r8, [rbp+57h+var_A8]
0x18007468c  lea     edx, [r9-2]
0x180074690  mov     rax, rbx
0x180074693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074698  mov     bl, 1
0x18007469a  mov     [rbp+57h+var_B0], bl
0x18007469d  jmp     loc_180074487
0x1800746a2  mov     ecx, eax
0x1800746a4  shr     rdx, cl
0x1800746a7  shl     rdx, cl
0x1800746aa  mov     rax, rdx
0x1800746ad  and     rax, r10
0x1800746b0  cmp     rax, rdx
0x1800746b3  jnz     loc_1800743E6
0x1800746b9  lea     r8, [rbp+r8*8+57h+var_70+8]
0x1800746be  lea     eax, [r9-40h]
0x1800746c2  cmp     eax, r15d
0x1800746c5  jnb     loc_18007485B
0x1800746cb  test    eax, eax
0x1800746cd  jz      loc_18007442A
0x1800746d3  mov     ecx, r15d
0x1800746d6  sub     ecx, eax
0x1800746d8  mov     rdx, rdi
0x1800746db  shr     rdx, cl
0x1800746de  mov     rax, rdx
0x1800746e1  and     rax, [r8]
0x1800746e4  jmp     loc_1800743E1
0x1800746e9  add     edx, esi
0x1800746eb  neg     rax
0x1800746ee  sbb     rax, rax
0x1800746f1  and     rax, rcx
0x1800746f4  cmp     edx, [rax+68h]
0x1800746f7  jnb     short loc_180074709
0x1800746f9  lea     rcx, [rbp+57h+var_70]
0x1800746fd  call    ?GetNextBit@?$BVStatic@$0BBA@@@QEBAII@Z; BVStatic<272>::GetNextBit(uint)
0x180074702  mov     esi, eax
0x180074704  jmp     loc_18007437F
0x180074709  xor     eax, eax
0x18007470b  jmp     loc_180074563
0x180074710  call    ?RecordLastError@MemoryOperationLastError@Memory@@SAXXZ; Memory::MemoryOperationLastError::RecordLastError(void)
0x180074715  nop
0x180074716  lea     rcx, [rbp+57h+var_B0]; this
0x18007471a  call    ??1AutoEnableDynamicCodeGen@Memory@@QEAA@XZ; Memory::AutoEnableDynamicCodeGen::~AutoEnableDynamicCodeGen(void)
0x18007471f  mov     r12d, [rbp+57h+var_A4]
0x180074723  cmp     r12d, 1
0x180074727  jz      short loc_180074709
0x180074729  or      r11d, 0FFFFFFFFh
  ... truncated ...
```
