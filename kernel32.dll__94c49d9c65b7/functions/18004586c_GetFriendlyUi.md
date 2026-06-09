# GetFriendlyUi

- ea: `0x18004586c`
- end: `0x180045c3a`
- name: `GetFriendlyUi`
- size: `974`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180055f50`
- `0x180059030`
- `0x180060a10`

## callees

- `0x18000f920`
- `0x18004586c`
- `0x18007a7a1`
- `0x18007a7dd`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlQueryRegistryValuesEx` at `0x180045a95`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180045aee`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180045bb8`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180045a95`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180045aee`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180045bb8`
- `ntdll!wcslen` at `0x180045b52`
- `ntdll!wcslen` at `0x180045b52`
- `ntdll!RtlSetLastWin32Error` at `0x180045c21`
- `ntdll!RtlSetLastWin32Error` at `0x180045c21`
- `ntdll!RtlFreeHeap` at `0x180045b77`
- `ntdll!RtlFreeHeap` at `0x18007b4b2`
- `ntdll!RtlFreeHeap` at `0x180045b77`
- `ntdll!RtlFreeHeap` at `0x18007b4b2`
- `ntdll!RtlAllocateHeap` at `0x1800459ae`
- `ntdll!RtlAllocateHeap` at `0x180045be4`
- `ntdll!RtlAllocateHeap` at `0x1800459ae`
- `ntdll!RtlAllocateHeap` at `0x180045be4`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180045993`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180045bc9`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180045993`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180045bc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045aa7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045b13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045b32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045aa7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045b13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045b32`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800458e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800458f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180045909`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004591c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800458e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800458f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180045909`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004591c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180045b85`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007b4cd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180045b85`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007b4cd`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800458c2`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800458c2`

## string_xrefs

- `0x1800458bb`: `cfgmgr32.dll`
- `0x180045912`: `CM_Open_DevNode_Key`
- `0x180045bac`: `SERIALCOMM`
- `0x180045ac5`: `ConfigDialog`

## pseudocode

```c
void __fastcall GetFriendlyUi(__int64 a1, __int64 a2)
{
  HMODULE LibraryW; // rax
  HMODULE v5; // r14
  FARPROC ProcAddress; // rbx
  FARPROC v7; // r15
  FARPROC v8; // r12
  FARPROC v9; // rax
  __int64 (__fastcall *v10)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD); // r13
  wchar_t *Heap; // rdi
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r9
  __int64 v15; // r8
  unsigned int v16; // ebx
  ULONG *GlobalData; // rax
  const wchar_t *i; // rbx
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  ULONG *v24; // rax
  _OWORD *v25; // rax
  __int64 v26; // [rsp+0h] [rbp-118h] BYREF
  _QWORD v27[2]; // [rsp+40h] [rbp-D8h] BYREF
  wchar_t *v28; // [rsp+50h] [rbp-C8h]
  __int64 *v29; // [rsp+58h] [rbp-C0h]
  HMODULE v30; // [rsp+60h] [rbp-B8h]
  void *v31; // [rsp+70h] [rbp-A8h] BYREF
  int v32; // [rsp+78h] [rbp-A0h]
  _BYTE v33[4]; // [rsp+7Ch] [rbp-9Ch] BYREF
  const wchar_t *v34; // [rsp+80h] [rbp-98h]
  unsigned int v35; // [rsp+120h] [rbp+8h] BYREF
  unsigned int v36; // [rsp+130h] [rbp+18h] BYREF
  HANDLE hObject; // [rsp+138h] [rbp+20h] BYREF

  v29 = &v26;
  memset_0(v33, 0, 0x64u);
  v27[0] = 0;
  v27[1] = a1;
  v31 = &GetFriendlyMatchComm;
  v32 = 4;
  LibraryW = LoadLibraryW(L"cfgmgr32.dll");
  v5 = LibraryW;
  v30 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "CM_Get_Device_ID_List_SizeW");
    v7 = GetProcAddress(v5, "CM_Get_Device_ID_ListW");
    v8 = GetProcAddress(v5, "CM_Locate_DevNodeW");
    v9 = GetProcAddress(v5, "CM_Open_DevNode_Key");
    v10 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))v9;
    if ( ProcAddress )
    {
      if ( v7 )
      {
        if ( v8 )
        {
          if ( v9 )
          {
            Heap = 0;
            v28 = 0;
            v35 = 0;
            if ( !((__int64 (__fastcall *)(unsigned int *, const wchar_t *, __int64))ProcAddress)(&v35, L"MODEM", 2) )
            {
              v15 = v35;
              v16 = v35 + 2;
              if ( v35 + 2 > v35 && v16 < 2 * v16 )
              {
                GlobalData = (ULONG *)KernelBaseGetGlobalData(v13, v12, v35, v14);
                Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *GlobalData, 2LL * v16);
                v28 = Heap;
                v15 = v35;
              }
              if ( Heap )
              {
                if ( !((__int64 (__fastcall *)(const wchar_t *, wchar_t *, __int64, __int64))v7)(L"modem", Heap, v15, 2) )
                {
                  for ( i = Heap; *i; i += wcslen(i) + 1 )
                  {
                    v36 = 0;
                    if ( !((__int64 (__fastcall *)(unsigned int *, const wchar_t *, _QWORD))v8)(&v36, i, 0) )
                    {
                      hObject = 0;
                      if ( !v10(v36, 983103, 0, 0, &hObject, 1) )
                      {
                        LODWORD(v27[0]) = 0;
                        v34 = L"FriendlyName";
                        if ( (int)RtlQueryRegistryValuesEx(0x40000000, hObject, &v31, v27, 0) >= 0 && LODWORD(v27[0]) )
                        {
                          v31 = &GetConfigDialogName;
                          v34 = L"ConfigDialog";
                          v19 = RtlQueryRegistryValuesEx(0x40000000, hObject, &v31, a2, 0);
                          v31 = &GetFriendlyMatchComm;
                          if ( v19 < 0 )
                          {
                            BaseSetLastNTError((unsigned int)v19);
                            CloseHandle(hObject);
                            local_unwind_1(v29, &loc_180045C27);
                          }
                          CloseHandle(hObject);
                          if ( *(_QWORD *)(a2 + 8) )
                            local_unwind_1(v29, &loc_180045C27);
                        }
                        else
                        {
                          CloseHandle(hObject);
                        }
                      }
                    }
                  }
                }
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
              }
            }
          }
        }
      }
    }
    FreeLibrary(v5);
  }
  if ( !*(_QWORD *)(a2 + 8) )
  {
    v34 = 0;
    if ( (int)RtlQueryRegistryValuesEx(4, L"SERIALCOMM", &v31, v27, 0) >= 0 && LODWORD(v27[0]) )
    {
      v24 = (ULONG *)KernelBaseGetGlobalData(v21, v20, v22, v23);
      v25 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *v24, 0x1Au);
      *(_QWORD *)(a2 + 8) = v25;
      if ( v25 )
      {
        *(_DWORD *)a2 = 1703960;
        *v25 = xmmword_1800896C8;
        *(_OWORD *)((char *)v25 + 10) = *(__int128 *)((char *)&xmmword_1800896C8 + 10);
      }
      else
      {
        BaseSetLastNTError(3221225626LL);
      }
    }
    else
    {
      RtlSetLastWin32Error(0x57u);
    }
  }
}

```

## disassembly

```asm
0x18004586c  push    rbx
0x18004586e  push    rsi
0x18004586f  push    rdi
0x180045870  push    r12
0x180045872  push    r13
0x180045874  push    r14
0x180045876  push    r15
0x180045878  sub     rsp, 0E0h
0x18004587f  mov     [rsp+118h+var_C0], rsp
0x180045884  mov     rsi, rdx
0x180045887  mov     rbx, rcx
0x18004588a  xor     edx, edx; Val
0x18004588c  lea     r8d, [rdx+64h]; Size
0x180045890  lea     rcx, [rsp+118h+var_9C]; void *
0x180045895  call    memset_0
0x18004589a  xor     r15d, r15d
0x18004589d  mov     [rsp+118h+var_D8], r15
0x1800458a2  mov     [rsp+118h+var_D0], rbx
0x1800458a7  lea     rax, GetFriendlyMatchComm
0x1800458ae  mov     [rsp+118h+var_A8], rax
0x1800458b3  mov     [rsp+118h+var_A0], 4
0x1800458bb  lea     rcx, CfgmgrDllString; "cfgmgr32.dll"
0x1800458c2  call    cs:__imp_LoadLibraryW
0x1800458c8  mov     r14, rax
0x1800458cb  mov     [rsp+118h+var_B8], rax
0x1800458d0  test    rax, rax
0x1800458d3  jz      loc_180045B8B
0x1800458d9  lea     rdx, aCmGetDeviceIdL; "CM_Get_Device_ID_List_SizeW"
0x1800458e0  mov     rcx, rax; hModule
0x1800458e3  call    cs:__imp_GetProcAddress
0x1800458e9  mov     rbx, rax
0x1800458ec  lea     rdx, aCmGetDeviceIdL_0; "CM_Get_Device_ID_ListW"
0x1800458f3  mov     rcx, r14; hModule
0x1800458f6  call    cs:__imp_GetProcAddress
0x1800458fc  mov     r15, rax
0x1800458ff  lea     rdx, aCmLocateDevnod; "CM_Locate_DevNodeW"
0x180045906  mov     rcx, r14; hModule
0x180045909  call    cs:__imp_GetProcAddress
0x18004590f  mov     r12, rax
0x180045912  lea     rdx, aCmOpenDevnodeK; "CM_Open_DevNode_Key"
0x180045919  mov     rcx, r14; hModule
0x18004591c  call    cs:__imp_GetProcAddress
0x180045922  mov     r13, rax
0x180045925  test    rbx, rbx
0x180045928  jz      loc_180045B7F
0x18004592e  test    r15, r15
0x180045931  jz      loc_180045B7F
0x180045937  test    r12, r12
0x18004593a  jz      loc_180045B7F
0x180045940  test    rax, rax
0x180045943  jz      loc_180045B7F
0x180045949  xor     edi, edi
0x18004594b  mov     [rsp+118h+var_C8], rdi
0x180045950  mov     [rsp+118h+arg_0], edi
0x180045957  lea     r8d, [rdi+2]
0x18004595b  lea     rdx, aModem; "MODEM"
0x180045962  lea     rcx, [rsp+118h+arg_0]
0x18004596a  mov     rax, rbx
0x18004596d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045972  test    rax, rax
0x180045975  jnz     loc_180045B7F
0x18004597b  mov     r8d, [rsp+118h+arg_0]
0x180045983  lea     ebx, [r8+2]
0x180045987  cmp     ebx, r8d
0x18004598a  jbe     short loc_1800459C4
0x18004598c  lea     eax, [rbx+rbx]
0x18004598f  cmp     ebx, eax
0x180045991  jnb     short loc_1800459C4
0x180045993  call    cs:__imp_KernelBaseGetGlobalData
0x180045999  mov     r8d, ebx
0x18004599c  add     r8, r8; Size
0x18004599f  mov     rcx, gs:60h
0x1800459a8  mov     edx, [rax]; Flags
0x1800459aa  mov     rcx, [rcx+30h]; HeapHandle
0x1800459ae  call    cs:__imp_RtlAllocateHeap
0x1800459b4  mov     rdi, rax
0x1800459b7  mov     [rsp+118h+var_C8], rax
0x1800459bc  mov     r8d, [rsp+118h+arg_0]
0x1800459c4  test    rdi, rdi
0x1800459c7  jz      loc_180045B7F
0x1800459cd  mov     r9d, 2
0x1800459d3  mov     rdx, rdi
0x1800459d6  lea     rcx, aModem_0; "modem"
0x1800459dd  mov     rax, r15
0x1800459e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800459e5  xor     r15d, r15d
0x1800459e8  test    rax, rax
0x1800459eb  jnz     loc_180045B65
0x1800459f1  mov     rbx, rdi
0x1800459f4  cmp     [rbx], r15w
0x1800459f8  jz      loc_180045B65
0x1800459fe  mov     [rsp+118h+arg_10], r15d
0x180045a06  xor     r8d, r8d
0x180045a09  mov     rdx, rbx
0x180045a0c  lea     rcx, [rsp+118h+arg_10]
0x180045a14  mov     rax, r12
0x180045a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a1c  test    rax, rax
0x180045a1f  jnz     loc_180045B4F
0x180045a25  mov     [rsp+118h+hObject], r15
0x180045a2d  mov     [rsp+118h+var_F0], 1
0x180045a35  lea     rax, [rsp+118h+hObject]
0x180045a3d  mov     [rsp+118h+var_F8], rax
0x180045a42  xor     r9d, r9d
0x180045a45  xor     r8d, r8d
0x180045a48  mov     edx, 0F003Fh
0x180045a4d  mov     ecx, [rsp+118h+arg_10]
0x180045a54  mov     rax, r13
0x180045a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a5c  test    rax, rax
0x180045a5f  jnz     loc_180045B4F
0x180045a65  mov     dword ptr [rsp+118h+var_D8], r15d
0x180045a6a  lea     rax, aFriendlyname; "FriendlyName"
0x180045a71  mov     [rsp+118h+var_98], rax
0x180045a79  mov     [rsp+118h+var_F8], r15
0x180045a7e  lea     r9, [rsp+118h+var_D8]
0x180045a83  lea     r8, [rsp+118h+var_A8]
0x180045a88  mov     rdx, [rsp+118h+hObject]
0x180045a90  mov     ecx, 40000000h
0x180045a95  call    cs:__imp_RtlQueryRegistryValuesEx
0x180045a9b  test    eax, eax
0x180045a9d  jns     short loc_180045AB2
0x180045a9f  mov     rcx, [rsp+118h+hObject]; hObject
0x180045aa7  call    cs:__imp_CloseHandle
0x180045aad  jmp     loc_180045B4F
0x180045ab2  cmp     dword ptr [rsp+118h+var_D8], r15d
0x180045ab7  jz      short loc_180045A9F
0x180045ab9  lea     rax, GetConfigDialogName
0x180045ac0  mov     [rsp+118h+var_A8], rax
0x180045ac5  lea     rax, aConfigdialog; "ConfigDialog"
0x180045acc  mov     [rsp+118h+var_98], rax
0x180045ad4  mov     [rsp+118h+var_F8], r15
0x180045ad9  mov     r9, rsi
0x180045adc  lea     r8, [rsp+118h+var_A8]
0x180045ae1  mov     rdx, [rsp+118h+hObject]
0x180045ae9  mov     ecx, 40000000h
0x180045aee  call    cs:__imp_RtlQueryRegistryValuesEx
0x180045af4  lea     rcx, GetFriendlyMatchComm
0x180045afb  mov     [rsp+118h+var_A8], rcx
0x180045b00  test    eax, eax
0x180045b02  jns     short loc_180045B2A
0x180045b04  mov     ecx, eax
0x180045b06  call    BaseSetLastNTError
0x180045b0b  mov     rcx, [rsp+118h+hObject]; hObject
0x180045b13  call    cs:__imp_CloseHandle
0x180045b19  lea     rdx, loc_180045C27
0x180045b20  mov     rcx, [rsp+118h+var_C0]
0x180045b25  call    _local_unwind_1
0x180045b2a  mov     rcx, [rsp+118h+hObject]; hObject
0x180045b32  call    cs:__imp_CloseHandle
0x180045b38  cmp     [rsi+8], r15
0x180045b3c  jz      short loc_180045B4F
0x180045b3e  lea     rdx, loc_180045C27
0x180045b45  mov     rcx, [rsp+118h+var_C0]
0x180045b4a  call    _local_unwind_1
0x180045b4f  mov     rcx, rbx; String
0x180045b52  call    cs:__imp_wcslen
0x180045b58  lea     rbx, [rbx+rax*2]
0x180045b5c  add     rbx, 2
0x180045b60  jmp     loc_1800459F4
0x180045b65  mov     rcx, gs:60h
0x180045b6e  mov     r8, rdi; P
0x180045b71  xor     edx, edx; Flags
0x180045b73  mov     rcx, [rcx+30h]; HeapHandle
0x180045b77  call    cs:__imp_RtlFreeHeap
0x180045b7d  jmp     short loc_180045B82
0x180045b7f  xor     r15d, r15d
0x180045b82  mov     rcx, r14; hLibModule
0x180045b85  call    cs:__imp_FreeLibrary
0x180045b8b  cmp     [rsi+8], r15
0x180045b8f  jnz     loc_180045C27
0x180045b95  mov     [rsp+118h+var_98], r15
0x180045b9d  mov     [rsp+118h+var_F8], r15
0x180045ba2  lea     r9, [rsp+118h+var_D8]
0x180045ba7  lea     r8, [rsp+118h+var_A8]
0x180045bac  lea     rdx, aSerialcomm; "SERIALCOMM"
0x180045bb3  mov     ecx, 4
0x180045bb8  call    cs:__imp_RtlQueryRegistryValuesEx
0x180045bbe  test    eax, eax
0x180045bc0  js      short loc_180045C1C
0x180045bc2  cmp     dword ptr [rsp+118h+var_D8], r15d
0x180045bc7  jz      short loc_180045C1C
0x180045bc9  call    cs:__imp_KernelBaseGetGlobalData
0x180045bcf  mov     rcx, gs:60h
0x180045bd8  mov     r8d, 1Ah; Size
0x180045bde  mov     edx, [rax]; Flags
0x180045be0  mov     rcx, [rcx+30h]; HeapHandle
0x180045be4  call    cs:__imp_RtlAllocateHeap
0x180045bea  mov     [rsi+8], rax
0x180045bee  test    rax, rax
0x180045bf1  jnz     short loc_180045BFF
0x180045bf3  mov     ecx, 0C000009Ah
0x180045bf8  call    BaseSetLastNTError
0x180045bfd  jmp     short loc_180045C27
0x180045bff  mov     dword ptr [rsi], 1A0018h
0x180045c05  movups  xmm0, cs:xmmword_1800896C8
0x180045c0c  movups  xmmword ptr [rax], xmm0
0x180045c0f  movups  xmm1, cs:xmmword_1800896C8+0Ah
0x180045c16  movups  xmmword ptr [rax+0Ah], xmm1
0x180045c1a  jmp     short loc_180045C27
0x180045c1c  mov     ecx, 57h ; 'W'; LastError
0x180045c21  call    cs:__imp_RtlSetLastWin32Error
0x180045c27  add     rsp, 0E0h
0x180045c2e  pop     r15
0x180045c30  pop     r14
0x180045c32  pop     r13
0x180045c34  pop     r12
0x180045c36  pop     rdi
0x180045c37  pop     rsi
0x180045c38  pop     rbx
0x180045c39  retn
0x18007b496  push    rbp
0x18007b498  sub     rsp, 40h
0x18007b49c  mov     rbp, rdx
0x18007b49f  mov     rcx, gs:60h
0x18007b4a8  mov     r8, [rbp+50h]; P
0x18007b4ac  xor     edx, edx; Flags
0x18007b4ae  mov     rcx, [rcx+30h]; HeapHandle
0x18007b4b2  call    cs:__imp_RtlFreeHeap
0x18007b4b8  nop
0x18007b4b9  add     rsp, 40h
0x18007b4bd  pop     rbp
0x18007b4be  retn
0x18007b4c0  push    rbp
0x18007b4c2  sub     rsp, 40h
0x18007b4c6  mov     rbp, rdx
0x18007b4c9  mov     rcx, [rbp+60h]; hLibModule
0x18007b4cd  call    cs:__imp_FreeLibrary
0x18007b4d3  nop
0x18007b4d4  add     rsp, 40h
0x18007b4d8  pop     rbp
0x18007b4d9  retn
```
