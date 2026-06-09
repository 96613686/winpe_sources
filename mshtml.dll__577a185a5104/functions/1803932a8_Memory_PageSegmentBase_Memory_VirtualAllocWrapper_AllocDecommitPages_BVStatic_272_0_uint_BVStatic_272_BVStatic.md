# Memory::PageSegmentBase<Memory::VirtualAllocWrapper>::AllocDecommitPages<BVStatic<272>,0>(uint,BVStatic<272>,BVStatic<272>)

- ea: `0x1803932a8`
- end: `0x1803939ad`
- name: `??$AllocDecommitPages@V?$BVStatic@$0BBA@@@$0A@@?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@Memory@@QEAAPEADIV?$BVStatic@$0BBA@@@0@Z`
- size: `1797`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180391d7c`

## callees

- `0x1803932a8`
- `0x1803939b4`
- `0x180393a8c`
- `0x180393e24`
- `0x1810bc928`
- `0x1810c0bf4`
- `0x1810f6516`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x1803938a4`
- `KERNEL32!GetCurrentThread` at `0x1803938e5`
- `KERNEL32!GetCurrentThread` at `0x18039394d`
- `KERNEL32!GetCurrentThread` at `0x1803938a4`
- `KERNEL32!GetCurrentThread` at `0x1803938e5`
- `KERNEL32!GetCurrentThread` at `0x18039394d`
- `KERNEL32!GetProcAddress` at `0x1803937c9`
- `KERNEL32!GetProcAddress` at `0x1803937e3`
- `KERNEL32!GetProcAddress` at `0x180393800`
- `KERNEL32!GetProcAddress` at `0x1803937c9`
- `KERNEL32!GetProcAddress` at `0x1803937e3`
- `KERNEL32!GetProcAddress` at `0x180393800`
- `KERNEL32!GetModuleHandleW` at `0x1803937a7`
- `KERNEL32!GetModuleHandleW` at `0x1803937a7`
- `KERNEL32!LeaveCriticalSection` at `0x18039385d`
- `KERNEL32!LeaveCriticalSection` at `0x18039385d`
- `KERNEL32!EnterCriticalSection` at `0x180393785`
- `KERNEL32!EnterCriticalSection` at `0x180393785`
- `KERNEL32!GetCurrentProcess` at `0x18039381c`
- `KERNEL32!GetCurrentProcess` at `0x18039381c`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1803934a0`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18039391a`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x1803934a0`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18039391a`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180393987`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180393987`

## string_xrefs

- `0x1803937f6`: `GetThreadInformation`
- `0x1803937a0`: `api-ms-win-core-processthreads-l1-1-3.dll`
- `0x1803937d9`: `SetThreadInformation`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LPVOID __fastcall Memory::PageSegmentBase<Memory::VirtualAllocWrapper>::AllocDecommitPages<BVStatic<272>,0>(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v5; // r12d
  _QWORD *v7; // rbx
  __int64 v8; // rsi
  unsigned __int64 v9; // r8
  int v10; // eax
  __int64 v11; // r10
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rax
  unsigned int v14; // esi
  unsigned __int64 *v15; // rdx
  unsigned int v16; // esi
  bool j; // zf
  __int64 v18; // rcx
  unsigned __int64 v19; // rcx
  SIZE_T v20; // r13
  unsigned __int64 v21; // rdx
  char v22; // cl
  __int64 v23; // rax
  char v24; // bl
  unsigned int v25; // edx
  unsigned __int64 *v27; // rcx
  int v28; // edx
  __int64 v29; // r8
  _QWORD *v30; // r8
  unsigned int i; // eax
  unsigned __int64 v32; // r12
  int v33; // esi
  unsigned int v34; // r13d
  DWORD v35; // edx
  unsigned int v36; // ebx
  int v37; // eax
  unsigned __int64 *v38; // r8
  unsigned int v39; // edx
  bool k; // zf
  __int64 v41; // rcx
  _QWORD *v42; // r9
  unsigned int v43; // r13d
  _QWORD *v44; // rsi
  HMODULE ModuleHandleW; // rax
  HMODULE v46; // r12
  unsigned int (__fastcall *v47)(HANDLE, __int64, struct _PROCESS_MITIGATION_DYNAMIC_CODE_POLICY *); // r12
  HANDLE CurrentProcess; // rax
  int (*v49)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int); // r12
  HANDLE CurrentThread; // rax
  int (*v51)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int); // rbx
  HANDLE v52; // rax
  void *v53; // rax
  int (*v54)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int); // rbx
  HANDLE v55; // rax
  _BYTE v56[4]; // [rsp+38h] [rbp-59h] BYREF
  int v57; // [rsp+3Ch] [rbp-55h]
  DWORD flOldProtect; // [rsp+40h] [rbp-51h] BYREF
  int v59; // [rsp+44h] [rbp-4Dh] BYREF
  unsigned int v60; // [rsp+48h] [rbp-49h]
  int v61; // [rsp+4Ch] [rbp-45h] BYREF
  int v62; // [rsp+50h] [rbp-41h]
  LPVOID lpAddress; // [rsp+58h] [rbp-39h]
  FARPROC ProcAddress; // [rsp+60h] [rbp-31h]
  struct _RTL_CRITICAL_SECTION *v65; // [rsp+68h] [rbp-29h]
  _OWORD v66[2]; // [rsp+70h] [rbp-21h] BYREF
  __int64 v67; // [rsp+90h] [rbp-1h]
  _QWORD v68[10]; // [rsp+98h] [rbp+7h] BYREF

  v5 = a2;
  v60 = a2;
  if ( *(_DWORD *)(a1 + 136) + *(_DWORD *)(a1 + 140) >= a2 )
  {
    v66[0] = *(_OWORD *)a3;
    v66[1] = *(_OWORD *)(a3 + 16);
    v67 = *(_QWORD *)(a3 + 32);
    v7 = v66;
    do
      BVUnitT<unsigned __int64>::Or(v7++, *a4++);
    while ( v7 != v68 );
    v62 = *(_DWORD *)(a1 + 136);
    flOldProtect = 0;
    j = !_BitScanForward64((unsigned __int64 *)&v8, *(unsigned __int64 *)&v66[0]);
    if ( j || (_DWORD)v8 == -1 )
    {
      v27 = (unsigned __int64 *)v66;
      v28 = 0;
      do
      {
        if ( ++v27 == v68 )
        {
          LODWORD(v8) = -1;
          goto LABEL_6;
        }
        v28 += 64;
        flOldProtect = 0;
        j = !_BitScanForward64((unsigned __int64 *)&v29, *v27);
      }
      while ( j || (_DWORD)v29 == -1 );
      LODWORD(v8) = v29 + v28;
    }
    while ( 1 )
    {
LABEL_6:
      if ( (_DWORD)v8 == -1 || *(_DWORD *)(a1 + 32) - *(_DWORD *)(a1 + 48) - (int)v8 < v5 )
        return 0;
      if ( v5 != 1 )
      {
        v9 = (unsigned __int64)(unsigned int)v8 >> 6;
        v10 = v8 & 0x3F;
        v11 = *((_QWORD *)v66 + v9);
        if ( v10 + v5 <= 0x40 )
        {
          v12 = 0xFFFFFFFFFFFFFFFFuLL >> (64 - (unsigned __int8)v5) << v10;
          v13 = v11 & v12;
          goto LABEL_11;
        }
        if ( (v11 & (0xFFFFFFFFFFFFFFFFuLL >> v10 << v10)) != 0xFFFFFFFFFFFFFFFFuLL >> v10 << v10 )
          goto LABEL_12;
        v30 = (_QWORD *)v66 + v9 + 1;
        for ( i = v10 + v5 - 64; i >= 0x40; i -= 64 )
        {
          if ( *v30 != -1 )
            goto LABEL_12;
          ++v30;
        }
        if ( i )
        {
          v12 = 0xFFFFFFFFFFFFFFFFuLL >> (64 - (unsigned __int8)i);
          v13 = *v30 & v12;
LABEL_11:
          if ( v13 != v12 )
            goto LABEL_12;
        }
      }
      v19 = *(_QWORD *)(a1 + 24) + (unsigned int)((_DWORD)v8 << 12);
      lpAddress = (LPVOID)v19;
      v20 = (unsigned __int64)v5 << 12;
      if ( ((v20 - 1) & v19) != 0 )
      {
        v21 = (v19 % v20) >> 12;
        v22 = 0;
      }
      else
      {
        LODWORD(v21) = 0;
        v22 = 1;
      }
      v23 = *(_QWORD *)(a1 + 8);
      if ( v22 )
      {
        v57 = *(_DWORD *)(v23 + 216);
        v24 = 0;
        v56[0] = 0;
        if ( v57 == 2 )
        {
          if ( !Memory::AutoEnableDynamicCodeGen::processPolicyObtained )
          {
            v65 = &Memory::AutoEnableDynamicCodeGen::processPolicyCS;
            EnterCriticalSection(&Memory::AutoEnableDynamicCodeGen::processPolicyCS);
            if ( !Memory::AutoEnableDynamicCodeGen::processPolicyObtained )
            {
              ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-processthreads-l1-1-3.dll");
              v46 = ModuleHandleW;
              if ( !ModuleHandleW
                || (ProcAddress = GetProcAddress(ModuleHandleW, "GetProcessMitigationPolicy"),
                    Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc = (int (*)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int))GetProcAddress(v46, "SetThreadInformation"),
                    Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc = (int (*)(void *, enum _THREAD_INFORMATION_CLASS, void *, unsigned int))GetProcAddress(v46, "GetThreadInformation"),
                    (v47 = (unsigned int (__fastcall *)(HANDLE, __int64, struct _PROCESS_MITIGATION_DYNAMIC_CODE_POLICY *))ProcAddress) == 0)
                || (CurrentProcess = GetCurrentProcess(),
                    !v47(CurrentProcess, 2, &Memory::AutoEnableDynamicCodeGen::processPolicy)) )
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
              v49 = Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc;
              if ( Memory::AutoEnableDynamicCodeGen::GetThreadInformationProc )
              {
                v59 = 0;
                CurrentThread = GetCurrentThread();
                if ( !((unsigned int (__fastcall *)(HANDLE, __int64, int *))v49)(CurrentThread, 2, &v59) || v59 != 1 )
                {
                  v59 = 1;
                  v51 = Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc;
                  v52 = GetCurrentThread();
                  ((void (__fastcall *)(HANDLE, __int64, int *))v51)(v52, 2, &v59);
                  v24 = 1;
                  v56[0] = 1;
                }
              }
            }
          }
        }
        flOldProtect = 0;
        if ( v57 == 2 )
        {
          v53 = VirtualAlloc(lpAddress, v20, 0x1000u, 0x40000040u);
          if ( v53 )
          {
            if ( !VirtualProtect(v53, v20, 4u, &flOldProtect) )
              CustomHeap_BadPageState_fatal_error((unsigned __int64)&Memory::VirtualAllocWrapper::Instance);
LABEL_40:
            Memory::AutoEnableDynamicCodeGen::~AutoEnableDynamicCodeGen((Memory::AutoEnableDynamicCodeGen *)v56);
            v32 = (unsigned __int64)(unsigned int)v8 >> 6;
            v33 = v8 & 0x3F;
            v34 = v60;
            v35 = v33 + v60;
            flOldProtect = v33 + v60;
            v36 = v33 + v60 - 64;
            if ( v33 + v60 > 0x40 )
            {
              *(_QWORD *)(a1 + 8 * v32 + 56) &= ~(0xFFFFFFFFFFFFFFFFuLL >> v33 << v33);
              v42 = (_QWORD *)(a1 + 64 + 8 * v32);
              v43 = v36;
              if ( v36 >= 0x40 )
              {
                memset_0((void *)(a1 + 64 + 8 * v32), 0, 8 * ((unsigned __int64)v36 >> 6));
                v42 = (_QWORD *)(a1 + 64 + 8 * v32);
                do
                {
                  ++v42;
                  v43 -= 64;
                }
                while ( v43 >= 0x40 );
                v35 = flOldProtect;
              }
              if ( v43 )
                *v42 &= ~(0xFFFFFFFFFFFFFFFFuLL >> (64 - (unsigned __int8)v43));
              v34 = v60;
            }
            else
            {
              *(_QWORD *)(a1 + 8 * v32 + 56) &= ~(0xFFFFFFFFFFFFFFFFuLL >> (64 - (unsigned __int8)v60) << v33);
            }
            if ( v35 > 0x40 )
            {
              *(_QWORD *)(a1 + 8 * v32 + 96) &= ~(0xFFFFFFFFFFFFFFFFuLL >> v33 << v33);
              v44 = (_QWORD *)(a1 + 104 + 8 * v32);
              if ( v36 >= 0x40 )
              {
                memset_0((void *)(a1 + 104 + 8 * v32), 0, 8 * ((unsigned __int64)v36 >> 6));
                do
                {
                  ++v44;
                  v36 -= 64;
                }
                while ( v36 >= 0x40 );
              }
              if ( v36 )
                *v44 &= ~(0xFFFFFFFFFFFFFFFFuLL >> (64 - (unsigned __int8)v36));
            }
            else
            {
              *(_QWORD *)(a1 + 8 * v32 + 96) &= ~(0xFFFFFFFFFFFFFFFFuLL >> (64 - (unsigned __int8)v34) << v33);
            }
            v37 = BVStatic<272>::Count(a1 + 56);
            *(_DWORD *)(a1 + 136) = v37 + *(_DWORD *)(a1 + 136) - v62;
            *(_DWORD *)(a1 + 140) = v62 + *(_DWORD *)(a1 + 140) - v34 - v37;
            return lpAddress;
          }
          Memory::MemoryOperationLastError::RecordLastError();
          Memory::AutoEnableDynamicCodeGen::~AutoEnableDynamicCodeGen((Memory::AutoEnableDynamicCodeGen *)v56);
        }
        else
        {
          if ( VirtualAlloc(lpAddress, v20, 0x1000u, 4u) )
            goto LABEL_40;
          Memory::MemoryOperationLastError::RecordLastError();
          if ( v24 )
          {
            v61 = 0;
            v54 = Memory::AutoEnableDynamicCodeGen::SetThreadInformationProc;
            v55 = GetCurrentThread();
            ((void (__fastcall *)(HANDLE, __int64, int *))v54)(v55, 2, &v61);
          }
        }
        v5 = v60;
        if ( v60 == 1 )
          return 0;
LABEL_12:
        v14 = v8 + 1;
        LOBYTE(v18) = v14;
        v15 = (unsigned __int64 *)v66 + ((unsigned __int64)v14 >> 6);
        v16 = v14 & 0xFFFFFFC0;
        for ( j = !_BitScanForward64((unsigned __int64 *)&v18, *v15 & (-1LL << v18));
              ;
              j = !_BitScanForward64((unsigned __int64 *)&v18, *v15) )
        {
          v57 = 0;
          if ( !j && (_DWORD)v18 != -1 )
            break;
          if ( ++v15 == v68 )
            goto LABEL_52;
          v16 += 64;
        }
        LODWORD(v8) = v18 + v16;
      }
      else
      {
        v25 = v8 + v21;
        if ( v25 >= *(_DWORD *)(v23 + 104) )
          return 0;
        LOBYTE(v41) = v25;
        v38 = (unsigned __int64 *)v66 + ((unsigned __int64)v25 >> 6);
        v39 = v25 & 0xFFFFFFC0;
        for ( k = !_BitScanForward64((unsigned __int64 *)&v41, *v38 & (-1LL << v41));
              ;
              k = !_BitScanForward64((unsigned __int64 *)&v41, *v38) )
        {
          v57 = 0;
          if ( !k && (_DWORD)v41 != -1 )
          {
            LODWORD(v8) = v41 + v39;
            goto LABEL_6;
          }
          if ( ++v38 == v68 )
            break;
          v39 += 64;
        }
LABEL_52:
        LODWORD(v8) = -1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1803932a8  mov     rax, rsp
0x1803932ab  mov     [rax+20h], r9
0x1803932af  mov     [rax+18h], r8
0x1803932b3  mov     [rax+10h], edx
0x1803932b6  mov     [rax+8], rcx
0x1803932ba  push    rbp
0x1803932bb  push    rbx
0x1803932bc  push    rsi
0x1803932bd  push    rdi
0x1803932be  push    r12
0x1803932c0  push    r13
0x1803932c2  push    r14
0x1803932c4  push    r15
0x1803932c6  lea     rbp, [rax-5Fh]
0x1803932ca  sub     rsp, 0A8h
0x1803932d1  mov     rax, cs:__security_cookie
0x1803932d8  xor     rax, rsp
0x1803932db  mov     [rbp+57h+var_50], rax
0x1803932df  mov     r15, [rbp+57h+arg_0]
0x1803932e3  mov     r12d, [rbp+57h+arg_8]
0x1803932e7  mov     [rbp+57h+var_A0], r12d
0x1803932eb  mov     rcx, [rbp+57h+arg_10]
0x1803932ef  mov     rdi, [rbp+57h+arg_18]
0x1803932f3  mov     eax, [r15+8Ch]
0x1803932fa  add     eax, [r15+88h]
0x180393301  cmp     eax, r12d
0x180393304  jb      loc_1803934E3
0x18039330a  movaps  xmm0, xmmword ptr [rcx]
0x18039330d  movups  [rbp+57h+var_78], xmm0
0x180393311  movaps  xmm1, xmmword ptr [rcx+10h]
0x180393315  movups  [rbp+57h+var_68], xmm1
0x180393319  movsd   xmm0, qword ptr [rcx+20h]
0x18039331e  movsd   [rbp+57h+var_58], xmm0
0x180393323  lea     rbx, [rbp+57h+var_78]
0x180393327  mov     rdx, [rdi]
0x18039332a  mov     rcx, rbx
0x18039332d  call    ?Or@?$BVUnitT@_K@@QEAAXV1@@Z; BVUnitT<unsigned __int64>::Or(BVUnitT<unsigned __int64>)
0x180393332  add     rbx, 8
0x180393336  lea     rdi, [rdi+8]
0x18039333a  lea     rax, [rbp+57h+var_50]
0x18039333e  cmp     rbx, rax
0x180393341  jnz     short loc_180393327
0x180393343  mov     eax, [r15+88h]
0x18039334a  mov     [rbp+57h+var_98], eax
0x18039334d  xor     r11d, r11d
0x180393350  mov     [rbp+57h+flOldProtect], r11d
0x180393354  bsf     rsi, qword ptr [rbp+57h+var_78]
0x180393359  setnz   al
0x18039335c  lea     r14d, [r11+40h]
0x180393360  or      ebx, 0FFFFFFFFh
0x180393363  test    al, al
0x180393365  jz      loc_180393506
0x18039336b  cmp     esi, ebx
0x18039336d  jz      loc_180393506
0x180393373  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180393377  lea     r8, ?processPolicyCS@AutoEnableDynamicCodeGen@Memory@@0VCriticalSection@@A; CriticalSection Memory::AutoEnableDynamicCodeGen::processPolicyCS
0x18039337e  cmp     esi, ebx
0x180393380  jz      loc_1803934E3
0x180393386  mov     eax, [r15+20h]
0x18039338a  sub     eax, [r15+30h]
0x18039338e  sub     eax, esi
0x180393390  cmp     eax, r12d
0x180393393  jb      loc_1803934E3
0x180393399  cmp     r12d, 1
0x18039339d  jz      loc_180393436
0x1803933a3  mov     r8d, esi
0x1803933a6  shr     r8, 6
0x1803933aa  mov     eax, esi
0x1803933ac  and     eax, 3Fh
0x1803933af  lea     r9d, [rax+r12]
0x1803933b3  mov     r10, qword ptr [rbp+r8*8+57h+var_78]
0x1803933b8  mov     rdx, rdi
0x1803933bb  cmp     r9d, r14d
0x1803933be  ja      loc_18039353E
0x1803933c4  mov     ecx, r14d
0x1803933c7  sub     ecx, r12d
0x1803933ca  shr     rdx, cl
0x1803933cd  mov     ecx, eax
0x1803933cf  shl     rdx, cl
0x1803933d2  mov     rax, rdx
0x1803933d5  and     rax, r10
0x1803933d8  cmp     rax, rdx
0x1803933db  jz      short loc_18039342F
0x1803933dd  inc     esi
0x1803933df  mov     ecx, esi
0x1803933e1  mov     eax, esi
0x1803933e3  shr     rax, 6
0x1803933e7  lea     rdx, [rbp+57h+var_78]
0x1803933eb  lea     rdx, [rdx+rax*8]
0x1803933ef  and     esi, 0FFFFFFC0h
0x1803933f2  mov     rax, rdi
0x1803933f5  shl     rax, cl
0x1803933f8  and     rax, [rdx]
0x1803933fb  bsf     rcx, rax
0x1803933ff  mov     [rbp+57h+var_AC], r11d
0x180393403  setnz   al
0x180393406  test    al, al
0x180393408  jz      short loc_180393415
0x18039340a  cmp     ecx, ebx
0x18039340c  jz      short loc_180393415
0x18039340e  add     esi, ecx
0x180393410  jmp     loc_180393377
0x180393415  add     rdx, 8
0x180393419  lea     rax, [rbp+57h+var_50]
0x18039341d  cmp     rdx, rax
0x180393420  jz      loc_180393683
0x180393426  add     esi, r14d
0x180393429  bsf     rcx, [rdx]
0x18039342d  jmp     short loc_1803933FF
0x18039342f  lea     r8, ?processPolicyCS@AutoEnableDynamicCodeGen@Memory@@0VCriticalSection@@A; CriticalSection Memory::AutoEnableDynamicCodeGen::processPolicyCS
0x180393436  mov     ecx, esi
0x180393438  shl     ecx, 0Ch
0x18039343b  add     rcx, [r15+18h]
0x18039343f  mov     [rbp+57h+lpAddress], rcx
0x180393443  mov     r13d, r12d
0x180393446  shl     r13, 0Ch
0x18039344a  lea     rax, [r13-1]
0x18039344e  test    rcx, rax
0x180393451  jnz     loc_180393622
0x180393457  mov     edx, r11d
0x18039345a  mov     cl, 1
0x18039345c  mov     rax, [r15+8]
0x180393460  test    cl, cl
0x180393462  jz      short loc_1803934D8
0x180393464  mov     ecx, [rax+0D8h]
0x18039346a  mov     [rbp+57h+var_AC], ecx
0x18039346d  mov     bl, r11b
0x180393470  mov     [rbp+57h+var_B0], bl
0x180393473  cmp     ecx, 2
0x180393476  jz      loc_180393770
0x18039347c  mov     [rbp+57h+flOldProtect], 0
0x180393483  mov     r8d, 1000h; flAllocationType
0x180393489  mov     rdx, r13; dwSize
0x18039348c  mov     rcx, [rbp+57h+lpAddress]; lpAddress
0x180393490  cmp     [rbp+57h+var_AC], 2
0x180393494  jz      loc_180393914
0x18039349a  mov     r9d, 4; flProtect
0x1803934a0  call    cs:__imp_VirtualAlloc
0x1803934a7  nop     dword ptr [rax+rax+00h]
0x1803934ac  test    rax, rax
0x1803934af  jnz     loc_180393585
0x1803934b5  call    ?RecordLastError@MemoryOperationLastError@Memory@@SAXXZ; Memory::MemoryOperationLastError::RecordLastError(void)
0x1803934ba  nop
0x1803934bb  test    bl, bl
0x1803934bd  jnz     loc_18039393F
0x1803934c3  mov     r12d, [rbp+57h+var_A0]
0x1803934c7  cmp     r12d, 1
0x1803934cb  jz      short loc_1803934E3
0x1803934cd  xor     r11d, r11d
0x1803934d0  or      ebx, 0FFFFFFFFh
0x1803934d3  jmp     loc_1803933DD
0x1803934d8  add     edx, esi
0x1803934da  cmp     edx, [rax+68h]
0x1803934dd  jb      loc_180393636
0x1803934e3  xor     eax, eax
0x1803934e5  mov     rcx, [rbp+57h+var_50]
0x1803934e9  xor     rcx, rsp; StackCookie
0x1803934ec  call    __security_check_cookie
0x1803934f1  add     rsp, 0A8h
0x1803934f8  pop     r15
0x1803934fa  pop     r14
0x1803934fc  pop     r13
0x1803934fe  pop     r12
0x180393500  pop     rdi
0x180393501  pop     rsi
0x180393502  pop     rbx
0x180393503  pop     rbp
0x180393504  retn
0x180393506  lea     rcx, [rbp+57h+var_78]
0x18039350a  mov     edx, r11d
0x18039350d  add     rcx, 8
0x180393511  lea     rax, [rbp+57h+var_50]
0x180393515  cmp     rcx, rax
0x180393518  jz      loc_18039368A
0x18039351e  add     edx, r14d
0x180393521  mov     [rbp+57h+flOldProtect], r11d
0x180393525  bsf     r8, [rcx]
0x180393529  setnz   al
0x18039352c  test    al, al
0x18039352e  jz      short loc_18039350D
0x180393530  cmp     r8d, ebx
0x180393533  jz      short loc_18039350D
0x180393535  lea     esi, [r8+rdx]
0x180393539  jmp     loc_180393373
0x18039353e  mov     ecx, eax
0x180393540  shr     rdx, cl
0x180393543  shl     rdx, cl
0x180393546  mov     rax, rdx
0x180393549  and     rax, r10
0x18039354c  cmp     rax, rdx
0x18039354f  jnz     loc_1803933DD
0x180393555  lea     r8, [rbp+r8*8+57h+var_78+8]
0x18039355a  lea     eax, [r9-40h]
0x18039355e  cmp     eax, r14d
0x180393561  jnb     loc_18039375B
0x180393567  test    eax, eax
0x180393569  jz      loc_18039342F
0x18039356f  mov     ecx, r14d
0x180393572  sub     ecx, eax
0x180393574  mov     rdx, rdi
0x180393577  shr     rdx, cl
0x18039357a  mov     rax, rdx
0x18039357d  and     rax, [r8]
0x180393580  jmp     loc_1803933D8
0x180393585  lea     rcx, [rbp+57h+var_B0]; this
0x180393589  call    ??1AutoEnableDynamicCodeGen@Memory@@QEAA@XZ; Memory::AutoEnableDynamicCodeGen::~AutoEnableDynamicCodeGen(void)
0x18039358e  mov     r12d, esi
0x180393591  shr     r12, 6
0x180393595  and     esi, 3Fh
0x180393598  mov     r13d, [rbp+57h+var_A0]
0x18039359c  lea     edx, [rsi+r13]
0x1803935a0  mov     [rbp+57h+flOldProtect], edx
0x1803935a3  lea     ebx, [rdx-40h]
0x1803935a6  mov     rax, rdi
0x1803935a9  cmp     edx, r14d
0x1803935ac  ja      loc_180393691
0x1803935b2  mov     ecx, r14d
0x1803935b5  sub     ecx, r13d
0x1803935b8  shr     rax, cl
0x1803935bb  mov     ecx, esi
0x1803935bd  shl     rax, cl
0x1803935c0  not     rax
0x1803935c3  and     [r15+r12*8+38h], rax
0x1803935c8  cmp     edx, r14d
0x1803935cb  ja      loc_1803936FE
0x1803935d1  sub     r14d, r13d
0x1803935d4  mov     cl, r14b
0x1803935d7  shr     rdi, cl
0x1803935da  mov     ecx, esi
0x1803935dc  shl     rdi, cl
0x1803935df  not     rdi
0x1803935e2  and     [r15+r12*8+60h], rdi
0x1803935e7  lea     rcx, [r15+38h]
0x1803935eb  call    ?Count@?$BVStatic@$0BBA@@@QEBAIXZ; BVStatic<272>::Count(void)
0x1803935f0  mov     ecx, [r15+88h]
0x1803935f7  sub     ecx, [rbp+57h+var_98]
0x1803935fa  add     ecx, eax
0x1803935fc  mov     [r15+88h], ecx
0x180393603  mov     ecx, [r15+8Ch]
0x18039360a  sub     ecx, r13d
0x18039360d  sub     ecx, eax
0x18039360f  add     ecx, [rbp+57h+var_98]
0x180393612  mov     [r15+8Ch], ecx
0x180393619  mov     rax, [rbp+57h+lpAddress]
0x18039361d  jmp     loc_1803934E5
0x180393622  xor     edx, edx
0x180393624  mov     rax, rcx
0x180393627  div     r13
0x18039362a  shr     rdx, 0Ch
0x18039362e  mov     cl, r11b
0x180393631  jmp     loc_18039345C
0x180393636  mov     ecx, edx
0x180393638  mov     eax, edx
0x18039363a  shr     rax, 6
0x18039363e  lea     r8, [rbp+57h+var_78]
0x180393642  lea     r8, [r8+rax*8]
0x180393646  and     edx, 0FFFFFFC0h
0x180393649  mov     rax, rdi
0x18039364c  shl     rax, cl
0x18039364f  and     rax, [r8]
0x180393652  bsf     rcx, rax
0x180393656  mov     [rbp+57h+var_AC], r11d
0x18039365a  setnz   al
0x18039365d  test    al, al
0x18039365f  jz      short loc_18039366D
0x180393661  cmp     ecx, ebx
0x180393663  jz      short loc_18039366D
0x180393665  lea     esi, [rcx+rdx]
0x180393668  jmp     loc_180393377
0x18039366d  add     r8, 8
0x180393671  lea     rax, [rbp+57h+var_50]
0x180393675  cmp     r8, rax
0x180393678  jz      short loc_180393683
0x18039367a  add     edx, r14d
0x18039367d  bsf     rcx, [r8]
0x180393681  jmp     short loc_180393656
0x180393683  mov     esi, ebx
0x180393685  jmp     loc_180393377
0x18039368a  mov     esi, ebx
0x18039368c  jmp     loc_180393373
0x180393691  mov     ecx, esi
0x180393693  shr     rax, cl
0x180393696  shl     rax, cl
0x180393699  not     rax
0x18039369c  and     [r15+r12*8+38h], rax
0x1803936a1  lea     r9, [r15+40h]
0x1803936a5  lea     r9, [r9+r12*8]
0x1803936a9  mov     r13d, ebx
0x1803936ac  cmp     ebx, r14d
0x1803936af  jb      short loc_1803936DE
0x1803936b1  mov     r8d, ebx
0x1803936b4  shr     r8, 6
0x1803936b8  shl     r8, 3; Size
0x1803936bc  xor     edx, edx; Val
0x1803936be  mov     rcx, r9; void *
0x1803936c1  call    memset_0
0x1803936c6  lea     r9, [r15+40h]
0x1803936ca  lea     r9, [r9+r12*8]
0x1803936ce  add     r9, 8
0x1803936d2  add     r13d, 0FFFFFFC0h
  ... truncated ...
```
