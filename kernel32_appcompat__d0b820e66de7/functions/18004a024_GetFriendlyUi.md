# GetFriendlyUi

- ea: `0x18004a024`
- end: `0x18004a465`
- name: `GetFriendlyUi`
- size: `1089`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005b280`
- `0x18005e6f0`
- `0x180067260`

## callees

- `0x18000ccf0`
- `0x18004a024`
- `0x180082721`
- `0x18008275d`
- `0x180084010`

## import_xrefs

- `ntdll!RtlQueryRegistryValuesEx` at `0x18004a277`
- `ntdll!RtlQueryRegistryValuesEx` at `0x18004a2dc`
- `ntdll!RtlQueryRegistryValuesEx` at `0x18004a3ca`
- `ntdll!RtlQueryRegistryValuesEx` at `0x18004a277`
- `ntdll!RtlQueryRegistryValuesEx` at `0x18004a2dc`
- `ntdll!RtlQueryRegistryValuesEx` at `0x18004a3ca`
- `ntdll!wcslen` at `0x18004a352`
- `ntdll!wcslen` at `0x18004a352`
- `ntdll!RtlSetLastWin32Error` at `0x18004a445`
- `ntdll!RtlSetLastWin32Error` at `0x18004a445`
- `ntdll!RtlFreeHeap` at `0x18004a37d`
- `ntdll!RtlFreeHeap` at `0x180083571`
- `ntdll!RtlFreeHeap` at `0x18004a37d`
- `ntdll!RtlFreeHeap` at `0x180083571`
- `ntdll!RtlAllocateHeap` at `0x18004a18a`
- `ntdll!RtlAllocateHeap` at `0x18004a402`
- `ntdll!RtlAllocateHeap` at `0x18004a18a`
- `ntdll!RtlAllocateHeap` at `0x18004a402`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004a169`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004a3e1`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004a169`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18004a3e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a28f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a307`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a32c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a28f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a307`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a32c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004a0a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004a0ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004a0d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004a0ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004a0a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004a0ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004a0d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004a0ec`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004a391`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180083592`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004a391`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180083592`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18004a07a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18004a07a`

## string_xrefs

- `0x18004a073`: `cfgmgr32.dll`
- `0x18004a0e2`: `CM_Open_DevNode_Key`
- `0x18004a3be`: `SERIALCOMM`
- `0x18004a2b3`: `ConfigDialog`

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
                            local_unwind_1(v29, &loc_18004A451);
                          }
                          CloseHandle(hObject);
                          if ( *(_QWORD *)(a2 + 8) )
                            local_unwind_1(v29, &loc_18004A451);
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
        *v25 = xmmword_1800916B8;
        *(_OWORD *)((char *)v25 + 10) = *(__int128 *)((char *)&xmmword_1800916B8 + 10);
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
0x18004a024  push    rbx
0x18004a026  push    rsi
0x18004a027  push    rdi
0x18004a028  push    r12
0x18004a02a  push    r13
0x18004a02c  push    r14
0x18004a02e  push    r15
0x18004a030  sub     rsp, 0E0h
0x18004a037  mov     [rsp+118h+var_C0], rsp
0x18004a03c  mov     rsi, rdx
0x18004a03f  mov     rbx, rcx
0x18004a042  xor     edx, edx; Val
0x18004a044  lea     r8d, [rdx+64h]; Size
0x18004a048  lea     rcx, [rsp+118h+var_9C]; void *
0x18004a04d  call    memset_0
0x18004a052  xor     r15d, r15d
0x18004a055  mov     [rsp+118h+var_D8], r15
0x18004a05a  mov     [rsp+118h+var_D0], rbx
0x18004a05f  lea     rax, GetFriendlyMatchComm
0x18004a066  mov     [rsp+118h+var_A8], rax
0x18004a06b  mov     [rsp+118h+var_A0], 4
0x18004a073  lea     rcx, CfgmgrDllString; "cfgmgr32.dll"
0x18004a07a  call    cs:__imp_LoadLibraryW
0x18004a081  nop     dword ptr [rax+rax+00h]
0x18004a086  mov     r14, rax
0x18004a089  mov     [rsp+118h+var_B8], rax
0x18004a08e  test    rax, rax
0x18004a091  jz      loc_18004A39D
0x18004a097  lea     rdx, aCmGetDeviceIdL; "CM_Get_Device_ID_List_SizeW"
0x18004a09e  mov     rcx, rax; hModule
0x18004a0a1  call    cs:__imp_GetProcAddress
0x18004a0a8  nop     dword ptr [rax+rax+00h]
0x18004a0ad  mov     rbx, rax
0x18004a0b0  lea     rdx, aCmGetDeviceIdL_0; "CM_Get_Device_ID_ListW"
0x18004a0b7  mov     rcx, r14; hModule
0x18004a0ba  call    cs:__imp_GetProcAddress
0x18004a0c1  nop     dword ptr [rax+rax+00h]
0x18004a0c6  mov     r15, rax
0x18004a0c9  lea     rdx, aCmLocateDevnod; "CM_Locate_DevNodeW"
0x18004a0d0  mov     rcx, r14; hModule
0x18004a0d3  call    cs:__imp_GetProcAddress
0x18004a0da  nop     dword ptr [rax+rax+00h]
0x18004a0df  mov     r12, rax
0x18004a0e2  lea     rdx, aCmOpenDevnodeK; "CM_Open_DevNode_Key"
0x18004a0e9  mov     rcx, r14; hModule
0x18004a0ec  call    cs:__imp_GetProcAddress
0x18004a0f3  nop     dword ptr [rax+rax+00h]
0x18004a0f8  mov     r13, rax
0x18004a0fb  test    rbx, rbx
0x18004a0fe  jz      loc_18004A38B
0x18004a104  test    r15, r15
0x18004a107  jz      loc_18004A38B
0x18004a10d  test    r12, r12
0x18004a110  jz      loc_18004A38B
0x18004a116  test    rax, rax
0x18004a119  jz      loc_18004A38B
0x18004a11f  xor     edi, edi
0x18004a121  mov     [rsp+118h+var_C8], rdi
0x18004a126  mov     [rsp+118h+arg_0], edi
0x18004a12d  lea     r8d, [rdi+2]
0x18004a131  lea     rdx, aModem; "MODEM"
0x18004a138  lea     rcx, [rsp+118h+arg_0]
0x18004a140  mov     rax, rbx
0x18004a143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a148  test    rax, rax
0x18004a14b  jnz     loc_18004A38B
0x18004a151  mov     r8d, [rsp+118h+arg_0]
0x18004a159  lea     ebx, [r8+2]
0x18004a15d  cmp     ebx, r8d
0x18004a160  jbe     short loc_18004A1A6
0x18004a162  lea     eax, [rbx+rbx]
0x18004a165  cmp     ebx, eax
0x18004a167  jnb     short loc_18004A1A6
0x18004a169  call    cs:__imp_KernelBaseGetGlobalData
0x18004a170  nop     dword ptr [rax+rax+00h]
0x18004a175  mov     r8d, ebx
0x18004a178  add     r8, r8; Size
0x18004a17b  mov     rcx, gs:60h
0x18004a184  mov     edx, [rax]; Flags
0x18004a186  mov     rcx, [rcx+30h]; HeapHandle
0x18004a18a  call    cs:__imp_RtlAllocateHeap
0x18004a191  nop     dword ptr [rax+rax+00h]
0x18004a196  mov     rdi, rax
0x18004a199  mov     [rsp+118h+var_C8], rax
0x18004a19e  mov     r8d, [rsp+118h+arg_0]
0x18004a1a6  test    rdi, rdi
0x18004a1a9  jz      loc_18004A38B
0x18004a1af  mov     r9d, 2
0x18004a1b5  mov     rdx, rdi
0x18004a1b8  lea     rcx, aModem_0; "modem"
0x18004a1bf  mov     rax, r15
0x18004a1c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a1c7  xor     r15d, r15d
0x18004a1ca  test    rax, rax
0x18004a1cd  jnz     loc_18004A36B
0x18004a1d3  mov     rbx, rdi
0x18004a1d6  cmp     [rbx], r15w
0x18004a1da  jz      loc_18004A36B
0x18004a1e0  mov     [rsp+118h+arg_10], r15d
0x18004a1e8  xor     r8d, r8d
0x18004a1eb  mov     rdx, rbx
0x18004a1ee  lea     rcx, [rsp+118h+arg_10]
0x18004a1f6  mov     rax, r12
0x18004a1f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a1fe  test    rax, rax
0x18004a201  jnz     loc_18004A34F
0x18004a207  mov     [rsp+118h+hObject], r15
0x18004a20f  mov     [rsp+118h+var_F0], 1
0x18004a217  lea     rax, [rsp+118h+hObject]
0x18004a21f  mov     [rsp+118h+var_F8], rax
0x18004a224  xor     r9d, r9d
0x18004a227  xor     r8d, r8d
0x18004a22a  mov     edx, 0F003Fh
0x18004a22f  mov     ecx, [rsp+118h+arg_10]
0x18004a236  mov     rax, r13
0x18004a239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a23e  test    rax, rax
0x18004a241  jnz     loc_18004A34F
0x18004a247  mov     dword ptr [rsp+118h+var_D8], r15d
0x18004a24c  lea     rax, aFriendlyname; "FriendlyName"
0x18004a253  mov     [rsp+118h+var_98], rax
0x18004a25b  mov     [rsp+118h+var_F8], r15
0x18004a260  lea     r9, [rsp+118h+var_D8]
0x18004a265  lea     r8, [rsp+118h+var_A8]
0x18004a26a  mov     rdx, [rsp+118h+hObject]
0x18004a272  mov     ecx, 40000000h
0x18004a277  call    cs:__imp_RtlQueryRegistryValuesEx
0x18004a27e  nop     dword ptr [rax+rax+00h]
0x18004a283  test    eax, eax
0x18004a285  jns     short loc_18004A2A0
0x18004a287  mov     rcx, [rsp+118h+hObject]; hObject
0x18004a28f  call    cs:__imp_CloseHandle
0x18004a296  nop     dword ptr [rax+rax+00h]
0x18004a29b  jmp     loc_18004A34F
0x18004a2a0  cmp     dword ptr [rsp+118h+var_D8], r15d
0x18004a2a5  jz      short loc_18004A287
0x18004a2a7  lea     rax, GetConfigDialogName
0x18004a2ae  mov     [rsp+118h+var_A8], rax
0x18004a2b3  lea     rax, aConfigdialog; "ConfigDialog"
0x18004a2ba  mov     [rsp+118h+var_98], rax
0x18004a2c2  mov     [rsp+118h+var_F8], r15
0x18004a2c7  mov     r9, rsi
0x18004a2ca  lea     r8, [rsp+118h+var_A8]
0x18004a2cf  mov     rdx, [rsp+118h+hObject]
0x18004a2d7  mov     ecx, 40000000h
0x18004a2dc  call    cs:__imp_RtlQueryRegistryValuesEx
0x18004a2e3  nop     dword ptr [rax+rax+00h]
0x18004a2e8  lea     rcx, GetFriendlyMatchComm
0x18004a2ef  mov     [rsp+118h+var_A8], rcx
0x18004a2f4  test    eax, eax
0x18004a2f6  jns     short loc_18004A324
0x18004a2f8  mov     ecx, eax
0x18004a2fa  call    BaseSetLastNTError
0x18004a2ff  mov     rcx, [rsp+118h+hObject]; hObject
0x18004a307  call    cs:__imp_CloseHandle
0x18004a30e  nop     dword ptr [rax+rax+00h]
0x18004a313  lea     rdx, loc_18004A451
0x18004a31a  mov     rcx, [rsp+118h+var_C0]
0x18004a31f  call    _local_unwind_1
0x18004a324  mov     rcx, [rsp+118h+hObject]; hObject
0x18004a32c  call    cs:__imp_CloseHandle
0x18004a333  nop     dword ptr [rax+rax+00h]
0x18004a338  cmp     [rsi+8], r15
0x18004a33c  jz      short loc_18004A34F
0x18004a33e  lea     rdx, loc_18004A451
0x18004a345  mov     rcx, [rsp+118h+var_C0]
0x18004a34a  call    _local_unwind_1
0x18004a34f  mov     rcx, rbx; String
0x18004a352  call    cs:__imp_wcslen
0x18004a359  nop     dword ptr [rax+rax+00h]
0x18004a35e  lea     rbx, [rbx+rax*2]
0x18004a362  add     rbx, 2
0x18004a366  jmp     loc_18004A1D6
0x18004a36b  mov     rcx, gs:60h
0x18004a374  mov     r8, rdi; P
0x18004a377  xor     edx, edx; Flags
0x18004a379  mov     rcx, [rcx+30h]; HeapHandle
0x18004a37d  call    cs:__imp_RtlFreeHeap
0x18004a384  nop     dword ptr [rax+rax+00h]
0x18004a389  jmp     short loc_18004A38E
0x18004a38b  xor     r15d, r15d
0x18004a38e  mov     rcx, r14; hLibModule
0x18004a391  call    cs:__imp_FreeLibrary
0x18004a398  nop     dword ptr [rax+rax+00h]
0x18004a39d  cmp     [rsi+8], r15
0x18004a3a1  jnz     loc_18004A451
0x18004a3a7  mov     [rsp+118h+var_98], r15
0x18004a3af  mov     [rsp+118h+var_F8], r15
0x18004a3b4  lea     r9, [rsp+118h+var_D8]
0x18004a3b9  lea     r8, [rsp+118h+var_A8]
0x18004a3be  lea     rdx, aSerialcomm; "SERIALCOMM"
0x18004a3c5  mov     ecx, 4
0x18004a3ca  call    cs:__imp_RtlQueryRegistryValuesEx
0x18004a3d1  nop     dword ptr [rax+rax+00h]
0x18004a3d6  test    eax, eax
0x18004a3d8  js      short loc_18004A440
0x18004a3da  cmp     dword ptr [rsp+118h+var_D8], r15d
0x18004a3df  jz      short loc_18004A440
0x18004a3e1  call    cs:__imp_KernelBaseGetGlobalData
0x18004a3e8  nop     dword ptr [rax+rax+00h]
0x18004a3ed  mov     rcx, gs:60h
0x18004a3f6  mov     r8d, 1Ah; Size
0x18004a3fc  mov     edx, [rax]; Flags
0x18004a3fe  mov     rcx, [rcx+30h]; HeapHandle
0x18004a402  call    cs:__imp_RtlAllocateHeap
0x18004a409  nop     dword ptr [rax+rax+00h]
0x18004a40e  mov     [rsi+8], rax
0x18004a412  test    rax, rax
0x18004a415  jnz     short loc_18004A423
0x18004a417  mov     ecx, 0C000009Ah
0x18004a41c  call    BaseSetLastNTError
0x18004a421  jmp     short loc_18004A451
0x18004a423  mov     dword ptr [rsi], 1A0018h
0x18004a429  movups  xmm0, cs:xmmword_1800916B8
0x18004a430  movups  xmmword ptr [rax], xmm0
0x18004a433  movups  xmm1, cs:xmmword_1800916B8+0Ah
0x18004a43a  movups  xmmword ptr [rax+0Ah], xmm1
0x18004a43e  jmp     short loc_18004A451
0x18004a440  mov     ecx, 57h ; 'W'; LastError
0x18004a445  call    cs:__imp_RtlSetLastWin32Error
0x18004a44c  nop     dword ptr [rax+rax+00h]
0x18004a451  add     rsp, 0E0h
0x18004a458  pop     r15
0x18004a45a  pop     r14
0x18004a45c  pop     r13
0x18004a45e  pop     r12
0x18004a460  pop     rdi
0x18004a461  pop     rsi
0x18004a462  pop     rbx
0x18004a463  retn
0x180083555  push    rbp
0x180083557  sub     rsp, 40h
0x18008355b  mov     rbp, rdx
0x18008355e  mov     rcx, gs:60h
0x180083567  mov     r8, [rbp+50h]; P
0x18008356b  xor     edx, edx; Flags
0x18008356d  mov     rcx, [rcx+30h]; HeapHandle
0x180083571  call    cs:__imp_RtlFreeHeap
0x180083578  nop     dword ptr [rax+rax+00h]
0x18008357d  nop
0x18008357e  add     rsp, 40h
0x180083582  pop     rbp
0x180083583  retn
0x180083585  push    rbp
0x180083587  sub     rsp, 40h
0x18008358b  mov     rbp, rdx
0x18008358e  mov     rcx, [rbp+60h]; hLibModule
0x180083592  call    cs:__imp_FreeLibrary
0x180083599  nop     dword ptr [rax+rax+00h]
0x18008359e  nop
0x18008359f  add     rsp, 40h
0x1800835a3  pop     rbp
0x1800835a4  retn
```
