# _anonymous_namespace_::GetStackHash

- ea: `0x18004edcc`
- end: `0x18004f5a6`
- name: `_anonymous_namespace_::GetStackHash`
- size: `2010`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180062ee0`

## callees

- `0x180021d38`
- `0x180031670`
- `0x18004edcc`
- `0x18004f890`
- `0x1800546d8`
- `0x1800580b4`
- `0x180062d20`
- `0x180083bc2`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18004edfe`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x18004edfe`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18004edf2`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18004edf2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f1db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f38f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f3a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f41e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f438`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f46f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f489`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f502`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f1db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f38f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f3a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f41e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f438`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f46f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f489`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f502`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f1e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f39d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f3b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f42c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f446`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f47d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f497`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f510`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f1e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f39d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f3b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f42c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f446`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f47d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f497`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f510`
- `dbgeng!DebugCreateEx` at `0x18004ee32`
- `dbgeng!DebugCreateEx` at `0x18004ee32`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall anonymous_namespace_::GetStackHash(void *a1, void *a2, unsigned int a3, unsigned __int16 *a4)
{
  unsigned int v5; // r12d
  DWORD ProcessId; // r14d
  DWORD ThreadId; // r15d
  HRESULT v9; // eax
  unsigned int v10; // ebx
  PVOID v11; // rbx
  __int64 (__fastcall *v12)(PVOID, GUID *, __int64 *); // rsi
  int v13; // eax
  PVOID v14; // rbx
  __int64 (__fastcall *v15)(PVOID, GUID *, __int64 *); // rsi
  int v16; // eax
  PVOID v17; // rbx
  __int64 (__fastcall *v18)(PVOID, GUID *, __int64 *); // rsi
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  char *v25; // rax
  char *v26; // r14
  int v27; // eax
  HANDLE v28; // rax
  struct _WER_STACK_FRAME *v29; // rax
  struct _WER_STACK_FRAME *v30; // rsi
  unsigned int v31; // r15d
  unsigned __int64 v32; // r12
  __int64 v33; // rbx
  unsigned __int64 v34; // rcx
  unsigned __int64 v35; // rdx
  __int64 v36; // rax
  __int64 v37; // r11
  int StackHash; // eax
  HANDLE v39; // rax
  HANDLE v40; // rax
  int v41; // eax
  HANDLE v42; // rax
  HANDLE v43; // rax
  HANDLE ProcessHeap; // rax
  HANDLE v45; // rax
  HANDLE v47; // rax
  int v48; // [rsp+20h] [rbp-79h]
  int *v49; // [rsp+20h] [rbp-79h]
  int v50; // [rsp+20h] [rbp-79h]
  PVOID Interface; // [rsp+40h] [rbp-59h] BYREF
  __int64 v52; // [rsp+48h] [rbp-51h] BYREF
  unsigned int v53; // [rsp+50h] [rbp-49h]
  __int64 v54; // [rsp+58h] [rbp-41h] BYREF
  __int64 v55; // [rsp+60h] [rbp-39h] BYREF
  unsigned int v56; // [rsp+68h] [rbp-31h] BYREF
  unsigned int v57; // [rsp+6Ch] [rbp-2Dh] BYREF
  int v58[2]; // [rsp+70h] [rbp-29h] BYREF
  __int128 v59; // [rsp+78h] [rbp-21h] BYREF
  __int64 v60; // [rsp+88h] [rbp-11h]
  char *v61; // [rsp+90h] [rbp-9h]
  struct _WER_STACK_FRAME *v62; // [rsp+98h] [rbp-1h]
  PVOID *p_Interface; // [rsp+A0h] [rbp+7h]
  char v64; // [rsp+A8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v5 = a3;
  ProcessId = GetProcessId(a1);
  ThreadId = GetThreadId(a2);
  Interface = 0;
  v52 = 0;
  v55 = 0;
  v54 = 0;
  Microsoft::WRL::ComPtr<IDebugClient3>::InternalRelease(&Interface);
  v9 = DebugCreateEx(&GUID_dd492d7f_71b8_4ad6_a8dc_1c887479ff91, 0x80000u, &Interface);
  v10 = v9;
  if ( v9 >= 0 )
  {
    p_Interface = &Interface;
    v64 = 1;
    v11 = Interface;
    v12 = **(__int64 (__fastcall ***)(PVOID, GUID *, __int64 *))Interface;
    Microsoft::WRL::ComPtr<IDebugClient3>::InternalRelease(&v52);
    v13 = v12(v11, &GUID_94e60ce9_9b41_4b19_9fc0_6d9eb35272b3, &v52);
    v10 = v13;
    if ( v13 >= 0 )
    {
      v14 = Interface;
      v15 = **(__int64 (__fastcall ***)(PVOID, GUID *, __int64 *))Interface;
      Microsoft::WRL::ComPtr<IDebugClient3>::InternalRelease(&v55);
      v16 = v15(v14, &GUID_f02fbecc_50ac_4f36_9ad9_c975e8f32ff8, &v55);
      v10 = v16;
      if ( v16 >= 0 )
      {
        v17 = Interface;
        v18 = **(__int64 (__fastcall ***)(PVOID, GUID *, __int64 *))Interface;
        Microsoft::WRL::ComPtr<IDebugClient3>::InternalRelease(&v54);
        v19 = v18(v17, &GUID_489468e6_7d0f_4af5_87ab_25207454d553, &v54);
        v10 = v19;
        if ( v19 >= 0 )
        {
          v20 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v52 + 432LL))(v52, 163848);
          v10 = v20;
          if ( v20 >= 0 )
          {
            v21 = (*(__int64 (__fastcall **)(PVOID, _QWORD, _QWORD, __int64))(*(_QWORD *)Interface + 96LL))(
                    Interface,
                    0,
                    ProcessId,
                    37);
            v10 = v21;
            if ( v21 >= 0 )
            {
              v22 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v52 + 744LL))(v52, 0, 0xFFFFFFFFLL);
              v10 = v22;
              if ( v22 >= 0 )
              {
                v56 = 0;
                v23 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v54 + 144LL))(
                        v54,
                        ThreadId,
                        &v56);
                v10 = v23;
                if ( v23 >= 0 )
                {
                  v24 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v54 + 48LL))(v54, v56);
                  v10 = v24;
                  if ( v24 >= 0 )
                  {
                    v25 = (char *)operator new[](0x6000u, (const struct std::nothrow_t *)&std::nothrow);
                    v26 = v25;
                    if ( v25 )
                      memset_0(v25, 0, 0x6000u);
                    else
                      v26 = 0;
                    v61 = v26;
                    if ( v26 )
                    {
                      v53 = 0;
                      LODWORD(v49) = (_DWORD)v26;
                      v27 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v52 + 248LL))(
                              v52,
                              0,
                              0,
                              0);
                      v10 = v27;
                      if ( v27 >= 0 )
                      {
                        v29 = (struct _WER_STACK_FRAME *)operator new[](
                                                           0x31200u,
                                                           (const struct std::nothrow_t *)&std::nothrow);
                        v30 = v29;
                        if ( v29 )
                          memset_0(v29, 0, 0x31200u);
                        else
                          v30 = 0;
                        v62 = v30;
                        if ( v30 )
                        {
                          v31 = 0;
                          if ( v53 )
                          {
                            do
                            {
                              if ( v31 >= 0xC0 )
                                break;
                              v57 = 0;
                              *(_QWORD *)v58 = 0;
                              v32 = (unsigned __int64)v31 << 7;
                              v49 = v58;
                              v33 = 1048LL * v31;
                              if ( (*(int (__fastcall **)(__int64, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)v55
                                                                                                  + 120LL))(
                                     v55,
                                     *(_QWORD *)&v26[v32],
                                     0,
                                     &v57) < 0
                                || (LODWORD(v49) = v33 + (_DWORD)v30,
                                    (*(int (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v55 + 712LL))(
                                      v55,
                                      1,
                                      v57,
                                      *(_QWORD *)v58) < 0) )
                              {
                                StringCchCopyW((unsigned __int16 *)((char *)v30 + v33), 0x104u, L"UNKNOWN");
                                *(_QWORD *)(v37 + 1040) = 0;
                              }
                              else
                              {
                                v34 = *(_QWORD *)v58;
                                v35 = *(_QWORD *)&v26[v32];
                                v36 = v35 < *(_QWORD *)v58 ? -1LL : v35 - *(_QWORD *)v58;
                                *(_QWORD *)((char *)v30 + v33 + 1040) = v36;
                                if ( v35 < v34 )
                                  *(_QWORD *)((char *)v30 + v33 + 1040) = 0;
                              }
                              ++v31;
                            }
                            while ( v31 < v53 );
                            v5 = a3;
                          }
                          v59 = 0;
                          v60 = 0;
                          StackHash = WerpGenerateStackHash(v30, v31, (struct WER_STACKHASH *)&v59);
                          v10 = StackHash;
                          if ( StackHash >= 0 )
                          {
                            v50 = BYTE5(v60);
                            v41 = StringCchPrintfW(a4, v5, L"%02x%02x", BYTE4(v60));
                            v10 = v41;
                            if ( v41 >= 0 )
                            {
                              ProcessHeap = GetProcessHeap();
                              HeapFree(ProcessHeap, 0, v30);
                              v45 = GetProcessHeap();
                              HeapFree(v45, 0, v26);
                              (*(void (__fastcall **)(PVOID, __int64))(*(_QWORD *)Interface + 208LL))(Interface, 2);
                              Microsoft::WRL::ComPtr<IDebugClient3>::InternalRelease(&v54);
                              Microsoft::WRL::ComPtr<IDebugClient3>::InternalRelease(&v55);
                              Microsoft::WRL::ComPtr<IDebugClient3>::InternalRelease(&v52);
                              Microsoft::WRL::ComPtr<IDebugClient3>::InternalRelease(&Interface);
                              return 0;
                            }
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0xFF,
                              (unsigned int)"onecoreuap\\inetcore\\iertutil\\werexceptionhandler.cpp",
                              (const char *)(unsigned int)v41,
                              v50);
                            v42 = GetProcessHeap();
                            HeapFree(v42, 0, v30);
                            v43 = GetProcessHeap();
                            HeapFree(v43, 0, v26);
                          }
                          else
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0xFE,
                              (unsigned int)"onecoreuap\\inetcore\\iertutil\\werexceptionhandler.cpp",
                              (const char *)(unsigned int)StackHash,
                              (int)v49);
                            v39 = GetProcessHeap();
                            HeapFree(v39, 0, v30);
                            v40 = GetProcessHeap();
                            HeapFree(v40, 0, v26);
                          }
                          (*(void (__fastcall **)(PVOID, __int64))(*(_QWORD *)Interface + 208LL))(Interface, 2);
                        }
                        else
                        {
                          v10 = -2147024882;
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0xD6,
                            (unsigned int)"onecoreuap\\inetcore\\iertutil\\werexceptionhandler.cpp",
                            (const char *)0x8007000ELL,
                            (int)v26);
                          v47 = GetProcessHeap();
                          HeapFree(v47, 0, v26);
                          (*(void (__fastcall **)(PVOID, __int64))(*(_QWORD *)Interface + 208LL))(Interface, 2);
                        }
                      }
                      else
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0xD3,
                          (unsigned int)"onecoreuap\\inetcore\\iertutil\\werexceptionhandler.cpp",
                          (const char *)(unsigned int)v27,
                          (int)v26);
                        v28 = GetProcessHeap();
                        HeapFree(v28, 0, v26);
                        (*(void (__fastcall **)(PVOID, __int64))(*(_QWORD *)Interface + 208LL))(Interface, 2);
                      }
                    }
                    else
                    {
                      v10 = -2147024882;
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0xD0,
                        (unsigned int)"onecoreuap\\inetcore\\iertutil\\werexceptionhandler.cpp",
                        (const char *)0x8007000ELL,
                        v48);
                      (*(void (__fastcall **)(PVOID, __int64))(*(_QWORD *)Interface + 208LL))(Interface, 2);
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0xCC,
                      (unsigned int)"onecoreuap\\inetcore\\iertutil\\werexceptionhandler.cpp",
                      (const char *)(unsigned int)v24,
                      v48);
                    (*(void (__fastcall **)(PVOID, __int64))(*(_QWORD *)Interface + 208LL))(Interface, 2);
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xCB,
                    (unsigned int)"onecoreuap\\inetcore\\iertutil\\werexceptionhandler.cpp",
                    (const char *)(unsigned int)v23,
                    v48);
                  (*(void (__fastcall **)(PVOID, __int64))(*(_QWORD *)Interface + 208LL))(Interface, 2);
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xC7,
                  (unsigned int)"onecoreuap\\inetcore\\iertutil\\werexceptionhandler.cpp",
                  (const char *)(unsigned int)v22,
                  v48);
                (*(void (__fastcall **)(PVOID, __int64))(*(_QWORD *)Interface + 208LL))(Interface, 2);
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xC6,
                (unsigned int)"onecoreuap\\inetcore\\iertutil\\werexceptionhandler.cpp",
                (const char *)(unsigned int)v21,
                v48);
              (*(void (__fastcall **)(PVOID, __int64))(*(_QWORD *)Interface + 208LL))(Interface, 2);
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xBF,
              (unsigned int)"onecoreuap\\inetcore\\iertutil\\werexceptionhandler.cpp",
              (const char *)(unsigned int)v20,
              v48);
            (*(void (__fastcall **)(PVOID, __int64))(*(_QWORD *)Interface + 208LL))(Interface, 2);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBB,
            (unsigned int)"onecoreuap\\inetcore\\iertutil\\werexceptionhandler.cpp",
            (const char *)(unsigned int)v19,
            v48);
          (*(void (__fastcall **)(PVOID, __int64))(*(_QWORD *)Interface + 208LL))(Interface, 2);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBA,
          (unsigned int)"onecoreuap\\inetcore\\iertutil\\werexceptionhandler.cpp",
          (const char *)(unsigned int)v16,
          v48);
        (*(void (__fastcall **)(PVOID, __int64))(*(_QWORD *)Interface + 208LL))(Interface, 2);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB9,
        (unsigned int)"onecoreuap\\inetcore\\iertutil\\werexceptionhandler.cpp",
        (const char *)(unsigned int)v13,
        v48);
      (*(void (__fastcall **)(PVOID, __int64))(*(_QWORD *)Interface + 208LL))(Interface, 2);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"onecoreuap\\inetcore\\iertutil\\werexceptionhandler.cpp",
      (const char *)(unsigned int)v9,
      v48);
  }
  Microsoft::WRL::ComPtr<IDebugClient3>::InternalRelease(&v54);
  Microsoft::WRL::ComPtr<IDebugClient3>::InternalRelease(&v55);
  Microsoft::WRL::ComPtr<IDebugClient3>::InternalRelease(&v52);
  Microsoft::WRL::ComPtr<IDebugClient3>::InternalRelease(&Interface);
  return v10;
}

```

## disassembly

```asm
0x18004edcc  mov     [rsp-8+arg_10], r8d
0x18004edd1  push    rbp
0x18004edd2  push    rbx
0x18004edd3  push    rsi
0x18004edd4  push    rdi
0x18004edd5  push    r12
0x18004edd7  push    r13
0x18004edd9  push    r14
0x18004eddb  push    r15
0x18004eddd  lea     rbp, [rsp-1Fh]
0x18004ede2  sub     rsp, 0B8h
0x18004ede9  mov     r13, r9
0x18004edec  mov     r12d, r8d
0x18004edef  mov     rbx, rdx
0x18004edf2  call    cs:__imp_GetProcessId
0x18004edf8  mov     r14d, eax
0x18004edfb  mov     rcx, rbx; Thread
0x18004edfe  call    cs:__imp_GetThreadId
0x18004ee04  mov     r15d, eax
0x18004ee07  xor     edi, edi
0x18004ee09  mov     [rbp+57h+Interface], rdi
0x18004ee0d  mov     [rbp+57h+var_A8], rdi
0x18004ee11  mov     [rbp+57h+var_90], rdi
0x18004ee15  mov     [rbp+57h+var_98], rdi
0x18004ee19  lea     rcx, [rbp+57h+Interface]
0x18004ee1d  call    ?InternalRelease@?$ComPtr@UIDebugClient3@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDebugClient3>::InternalRelease(void)
0x18004ee22  lea     r8, [rbp+57h+Interface]; Interface
0x18004ee26  mov     edx, 80000h; DbgEngOptions
0x18004ee2b  lea     rcx, _GUID_dd492d7f_71b8_4ad6_a8dc_1c887479ff91; InterfaceId
0x18004ee32  call    cs:__imp_DebugCreateEx
0x18004ee38  mov     ebx, eax
0x18004ee3a  test    eax, eax
0x18004ee3c  jns     short loc_18004EE5B
0x18004ee3e  mov     rcx, [rbp+5Fh]; this
0x18004ee42  mov     r9d, eax; char *
0x18004ee45  lea     r8, aOnecoreuapInet_12; "onecoreuap\\inetcore\\iertutil\\werexce"...
0x18004ee4c  mov     edx, 0B3h; void *
0x18004ee51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ee56  jmp     loc_18004F569
0x18004ee5b  lea     rdi, [rbp+57h+Interface]
0x18004ee5f  mov     [rbp+57h+var_50], rdi
0x18004ee63  mov     [rbp+57h+var_48], 1
0x18004ee67  mov     rbx, [rbp+57h+Interface]
0x18004ee6b  mov     rax, [rbx]
0x18004ee6e  mov     rsi, [rax]
0x18004ee71  lea     rcx, [rbp+57h+var_A8]
0x18004ee75  call    ?InternalRelease@?$ComPtr@UIDebugClient3@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDebugClient3>::InternalRelease(void)
0x18004ee7a  lea     r8, [rbp+57h+var_A8]
0x18004ee7e  lea     rdx, _GUID_94e60ce9_9b41_4b19_9fc0_6d9eb35272b3
0x18004ee85  mov     rcx, rbx
0x18004ee88  mov     rax, rsi
0x18004ee8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee90  mov     ebx, eax
0x18004ee92  test    eax, eax
0x18004ee94  jns     short loc_18004EECD
0x18004ee96  mov     rcx, [rbp+5Fh]; this
0x18004ee9a  mov     r9d, eax; char *
0x18004ee9d  lea     r8, aOnecoreuapInet_12; "onecoreuap\\inetcore\\iertutil\\werexce"...
0x18004eea4  mov     edx, 0B9h; void *
0x18004eea9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eeae  nop
0x18004eeaf  mov     rcx, [rbp+57h+Interface]
0x18004eeb3  mov     rax, [rcx]
0x18004eeb6  mov     edx, 2
0x18004eebb  mov     rax, [rax+0D0h]
0x18004eec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eec7  nop
0x18004eec8  jmp     loc_18004F569
0x18004eecd  mov     rbx, [rbp+57h+Interface]
0x18004eed1  mov     rax, [rbx]
0x18004eed4  mov     rsi, [rax]
0x18004eed7  lea     rcx, [rbp+57h+var_90]
0x18004eedb  call    ?InternalRelease@?$ComPtr@UIDebugClient3@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDebugClient3>::InternalRelease(void)
0x18004eee0  lea     r8, [rbp+57h+var_90]
0x18004eee4  lea     rdx, _GUID_f02fbecc_50ac_4f36_9ad9_c975e8f32ff8
0x18004eeeb  mov     rcx, rbx
0x18004eeee  mov     rax, rsi
0x18004eef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eef6  mov     ebx, eax
0x18004eef8  test    eax, eax
0x18004eefa  jns     short loc_18004EF33
0x18004eefc  mov     rcx, [rbp+5Fh]; this
0x18004ef00  mov     r9d, eax; char *
0x18004ef03  lea     r8, aOnecoreuapInet_12; "onecoreuap\\inetcore\\iertutil\\werexce"...
0x18004ef0a  mov     edx, 0BAh; void *
0x18004ef0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ef14  nop
0x18004ef15  mov     rcx, [rbp+57h+Interface]
0x18004ef19  mov     rax, [rcx]
0x18004ef1c  mov     edx, 2
0x18004ef21  mov     rax, [rax+0D0h]
0x18004ef28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef2d  nop
0x18004ef2e  jmp     loc_18004F569
0x18004ef33  mov     rbx, [rbp+57h+Interface]
0x18004ef37  mov     rax, [rbx]
0x18004ef3a  mov     rsi, [rax]
0x18004ef3d  lea     rcx, [rbp+57h+var_98]
0x18004ef41  call    ?InternalRelease@?$ComPtr@UIDebugClient3@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDebugClient3>::InternalRelease(void)
0x18004ef46  lea     r8, [rbp+57h+var_98]
0x18004ef4a  lea     rdx, _GUID_489468e6_7d0f_4af5_87ab_25207454d553
0x18004ef51  mov     rcx, rbx
0x18004ef54  mov     rax, rsi
0x18004ef57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef5c  mov     ebx, eax
0x18004ef5e  test    eax, eax
0x18004ef60  jns     short loc_18004EF99
0x18004ef62  mov     rcx, [rbp+5Fh]; this
0x18004ef66  mov     r9d, eax; char *
0x18004ef69  lea     r8, aOnecoreuapInet_12; "onecoreuap\\inetcore\\iertutil\\werexce"...
0x18004ef70  mov     edx, 0BBh; void *
0x18004ef75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ef7a  nop
0x18004ef7b  mov     rcx, [rbp+57h+Interface]
0x18004ef7f  mov     rax, [rcx]
0x18004ef82  mov     edx, 2
0x18004ef87  mov     rax, [rax+0D0h]
0x18004ef8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef93  nop
0x18004ef94  jmp     loc_18004F569
0x18004ef99  mov     rcx, [rbp+57h+var_A8]
0x18004ef9d  mov     rax, [rcx]
0x18004efa0  mov     edx, 28008h
0x18004efa5  mov     rax, [rax+1B0h]
0x18004efac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004efb1  mov     ebx, eax
0x18004efb3  test    eax, eax
0x18004efb5  jns     short loc_18004EFEE
0x18004efb7  mov     rcx, [rbp+5Fh]; this
0x18004efbb  mov     r9d, eax; char *
0x18004efbe  lea     r8, aOnecoreuapInet_12; "onecoreuap\\inetcore\\iertutil\\werexce"...
0x18004efc5  mov     edx, 0BFh; void *
0x18004efca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004efcf  nop
0x18004efd0  mov     rcx, [rbp+57h+Interface]
0x18004efd4  mov     rdx, [rcx]
0x18004efd7  mov     rax, [rdx+0D0h]
0x18004efde  mov     edx, 2
0x18004efe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004efe8  nop
0x18004efe9  jmp     loc_18004F569
0x18004efee  mov     rcx, [rbp+57h+Interface]
0x18004eff2  mov     rax, [rcx]
0x18004eff5  mov     r9d, 25h ; '%'
0x18004effb  mov     r8d, r14d
0x18004effe  xor     edx, edx
0x18004f000  mov     rax, [rax+60h]
0x18004f004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f009  mov     ebx, eax
0x18004f00b  test    eax, eax
0x18004f00d  jns     short loc_18004F046
0x18004f00f  mov     rcx, [rbp+5Fh]; this
0x18004f013  mov     r9d, eax; char *
0x18004f016  lea     r8, aOnecoreuapInet_12; "onecoreuap\\inetcore\\iertutil\\werexce"...
0x18004f01d  mov     edx, 0C6h; void *
0x18004f022  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f027  nop
0x18004f028  mov     rcx, [rbp+57h+Interface]
0x18004f02c  mov     rdx, [rcx]
0x18004f02f  mov     rax, [rdx+0D0h]
0x18004f036  mov     edx, 2
0x18004f03b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f040  nop
0x18004f041  jmp     loc_18004F569
0x18004f046  mov     rcx, [rbp+57h+var_A8]
0x18004f04a  mov     rax, [rcx]
0x18004f04d  or      r8d, 0FFFFFFFFh
0x18004f051  xor     edx, edx
0x18004f053  mov     rax, [rax+2E8h]
0x18004f05a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f05f  mov     ebx, eax
0x18004f061  test    eax, eax
0x18004f063  jns     short loc_18004F09C
0x18004f065  mov     rcx, [rbp+5Fh]; this
0x18004f069  mov     r9d, eax; char *
0x18004f06c  lea     r8, aOnecoreuapInet_12; "onecoreuap\\inetcore\\iertutil\\werexce"...
0x18004f073  mov     edx, 0C7h; void *
0x18004f078  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f07d  nop
0x18004f07e  mov     rcx, [rbp+57h+Interface]
0x18004f082  mov     rdx, [rcx]
0x18004f085  mov     rax, [rdx+0D0h]
0x18004f08c  mov     edx, 2
0x18004f091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f096  nop
0x18004f097  jmp     loc_18004F569
0x18004f09c  mov     [rbp+57h+var_88], 0
0x18004f0a3  mov     rcx, [rbp+57h+var_98]
0x18004f0a7  mov     rax, [rcx]
0x18004f0aa  lea     r8, [rbp+57h+var_88]
0x18004f0ae  mov     edx, r15d
0x18004f0b1  mov     rax, [rax+90h]
0x18004f0b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f0bd  mov     ebx, eax
0x18004f0bf  test    eax, eax
0x18004f0c1  jns     short loc_18004F0FA
0x18004f0c3  mov     rcx, [rbp+5Fh]; this
0x18004f0c7  mov     r9d, eax; char *
0x18004f0ca  lea     r8, aOnecoreuapInet_12; "onecoreuap\\inetcore\\iertutil\\werexce"...
0x18004f0d1  mov     edx, 0CBh; void *
0x18004f0d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f0db  nop
0x18004f0dc  mov     rcx, [rbp+57h+Interface]
0x18004f0e0  mov     rdx, [rcx]
0x18004f0e3  mov     rax, [rdx+0D0h]
0x18004f0ea  mov     edx, 2
0x18004f0ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f0f4  nop
0x18004f0f5  jmp     loc_18004F569
0x18004f0fa  mov     rcx, [rbp+57h+var_98]
0x18004f0fe  mov     rax, [rcx]
0x18004f101  mov     edx, [rbp+57h+var_88]
0x18004f104  mov     rax, [rax+30h]
0x18004f108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f10d  mov     ebx, eax
0x18004f10f  test    eax, eax
0x18004f111  jns     short loc_18004F14A
0x18004f113  mov     rcx, [rbp+5Fh]; this
0x18004f117  mov     r9d, eax; char *
0x18004f11a  lea     r8, aOnecoreuapInet_12; "onecoreuap\\inetcore\\iertutil\\werexce"...
0x18004f121  mov     edx, 0CCh; void *
0x18004f126  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f12b  nop
0x18004f12c  mov     rcx, [rbp+57h+Interface]
0x18004f130  mov     rdx, [rcx]
0x18004f133  mov     rax, [rdx+0D0h]
0x18004f13a  mov     edx, 2
0x18004f13f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f144  nop
0x18004f145  jmp     loc_18004F569
0x18004f14a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004f151  mov     ebx, 6000h
0x18004f156  mov     ecx, ebx; unsigned __int64
0x18004f158  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18004f15d  mov     r14, rax
0x18004f160  test    rax, rax
0x18004f163  jz      short loc_18004F174
0x18004f165  mov     r8d, ebx; Size
0x18004f168  xor     edx, edx; Val
0x18004f16a  mov     rcx, rax; void *
0x18004f16d  call    memset_0
0x18004f172  jmp     short loc_18004F177
0x18004f174  xor     r14d, r14d
0x18004f177  mov     [rbp+57h+var_60], r14
0x18004f17b  test    r14, r14
0x18004f17e  jz      loc_18004F532
0x18004f184  mov     [rbp+57h+var_A0], 0
0x18004f18b  mov     rcx, [rbp+57h+var_A8]
0x18004f18f  mov     rax, [rcx]
0x18004f192  lea     rdx, [rbp+57h+var_A0]
0x18004f196  mov     [rsp+0F0h+var_C0], rdx
0x18004f19b  mov     [rsp+0F0h+var_C8], 0C0h
0x18004f1a3  mov     qword ptr [rsp+0F0h+var_D0], r14; int
0x18004f1a8  xor     r9d, r9d
0x18004f1ab  xor     r8d, r8d
0x18004f1ae  xor     edx, edx
0x18004f1b0  mov     rax, [rax+0F8h]
0x18004f1b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f1bc  mov     ebx, eax
0x18004f1be  test    eax, eax
0x18004f1c0  jns     short loc_18004F20E
0x18004f1c2  mov     rcx, [rbp+5Fh]; this
0x18004f1c6  mov     r9d, eax; char *
0x18004f1c9  lea     r8, aOnecoreuapInet_12; "onecoreuap\\inetcore\\iertutil\\werexce"...
0x18004f1d0  mov     edx, 0D3h; void *
0x18004f1d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f1da  nop
0x18004f1db  call    cs:__imp_GetProcessHeap
0x18004f1e1  mov     rcx, rax; hHeap
0x18004f1e4  mov     r8, r14; lpMem
0x18004f1e7  xor     edx, edx; dwFlags
0x18004f1e9  call    cs:__imp_HeapFree
0x18004f1ef  nop
0x18004f1f0  mov     rcx, [rbp+57h+Interface]
0x18004f1f4  mov     rax, [rcx]
0x18004f1f7  mov     edx, 2
0x18004f1fc  mov     rax, [rax+0D0h]
0x18004f203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f208  nop
0x18004f209  jmp     loc_18004F569
0x18004f20e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004f215  mov     ebx, 31200h
0x18004f21a  mov     ecx, ebx; unsigned __int64
0x18004f21c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18004f221  mov     rsi, rax
0x18004f224  test    rax, rax
0x18004f227  jz      short loc_18004F238
0x18004f229  mov     r8d, ebx; Size
0x18004f22c  xor     edx, edx; Val
0x18004f22e  mov     rcx, rax; void *
0x18004f231  call    memset_0
0x18004f236  jmp     short loc_18004F23A
0x18004f238  xor     esi, esi
0x18004f23a  mov     [rbp+57h+var_58], rsi
0x18004f23e  test    rsi, rsi
0x18004f241  jz      loc_18004F4E4
0x18004f247  xor     r15d, r15d
0x18004f24a  cmp     [rbp+57h+var_A0], r15d
0x18004f24e  jbe     loc_18004F34F
0x18004f254  cmp     r15d, 0C0h
  ... truncated ...
```
