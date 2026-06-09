# HrCommandHandlerThread(long (*)(std::vector<CPConFoldPidl<ConFoldPidl_v3>,std::allocator<CPConFoldPidl<ConFoldPidl_v3>>> const &,HWND__ *,IShellFolder *),std::vector<CPConFoldPidl<ConFoldPidl_v3>,std::allocator<CPConFoldPidl<ConFoldPidl_v3>>> const &,HWND__ *,IShellFolder *)

- ea: `0x180019204`
- end: `0x18001933b`
- name: `?HrCommandHandlerThread@@YAJP6AJAEBV?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@PEAUHWND__@@PEAUIShellFolder@@@Z012@Z`
- size: `311`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180044680`
- `0x180044720`
- `0x180044988`

## callees

- `0x180002010`
- `0x180005d80`
- `0x180018f74`
- `0x180019204`
- `0x180019344`
- `0x18001a74c`
- `0x180044254`
- `0x1800448b0`
- `0x180065010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800192ed`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800192ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800192fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800192fb`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800192b6`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800192b6`

## string_xrefs

- `0x1800192af`: `netshell.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HrCommandHandlerThread(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v7; // r8
  __int64 v8; // r10
  _QWORD *v9; // rdx
  int v10; // edi
  ConFoldOnCommandParams *v11; // rax
  ConFoldOnCommandParams *v12; // rax
  ConFoldOnCommandParams *v13; // rbx
  HMODULE LibraryW; // rax
  HANDLE v15; // rax
  _QWORD v17[4]; // [rsp+30h] [rbp-38h] BYREF
  DWORD ThreadId; // [rsp+78h] [rbp+10h] BYREF

  std::vector<CPConFoldPidl<ConFoldPidl_v3>>::vector<CPConFoldPidl<ConFoldPidl_v3>>(v17);
  if ( *v9 == v9[1] )
  {
    v10 = 0;
  }
  else
  {
    v10 = HrCloneRgIDL(v8, 0, v7, v17);
    if ( v10 < 0 )
      goto LABEL_13;
  }
  v11 = (ConFoldOnCommandParams *)MemAlloc(0x38u);
  if ( v11 && (v12 = ConFoldOnCommandParams::ConFoldOnCommandParams(v11), (v13 = v12) != 0) )
  {
    *(_QWORD *)v12 = a1;
    std::vector<CPConFoldPidl<ConFoldPidl_v3>>::operator=((char *)v12 + 8, v17);
    *((_QWORD *)v13 + 4) = a3;
    *((_QWORD *)v13 + 5) = a4;
    *((_QWORD *)v13 + 6) = 0;
    if ( a4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a4 + 8LL))(a4);
    LibraryW = LoadLibraryW(L"netshell.dll");
    if ( LibraryW
      && (*((_QWORD *)v13 + 6) = LibraryW,
          ThreadId = 0,
          (v15 = CreateThread(0, 0, FolderCommandHandlerThreadProc, v13, 0, &ThreadId)) != 0) )
    {
      CloseHandle(v15);
    }
    else
    {
      *((_QWORD *)v13 + 6) = 0;
      FolderCommandHandlerThreadProc(v13);
    }
  }
  else
  {
    v10 = -2147024882;
  }
LABEL_13:
  std::vector<CPConFoldPidl<ConFoldPidl_v3>>::~vector<CPConFoldPidl<ConFoldPidl_v3>>((__int64)v17);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180019204  mov     [rsp+arg_0], rbx
0x180019209  mov     [rsp+arg_10], rbp
0x18001920e  push    rsi
0x18001920f  push    rdi
0x180019210  push    r14
0x180019212  sub     rsp, 50h
0x180019216  mov     rsi, r9
0x180019219  mov     rbp, r8
0x18001921c  mov     r10, rdx
0x18001921f  mov     r14, rcx
0x180019222  lea     rcx, [rsp+68h+var_38]
0x180019227  call    ??0?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@QEAA@XZ; std::vector<CPConFoldPidl<ConFoldPidl_v3>>::vector<CPConFoldPidl<ConFoldPidl_v3>>(void)
0x18001922c  nop
0x18001922d  mov     rax, [rdx+8]
0x180019231  cmp     [rdx], rax
0x180019234  jnz     short loc_18001923A
0x180019236  xor     edi, edi
0x180019238  jmp     short loc_180019253
0x18001923a  lea     r9, [rsp+68h+var_38]
0x18001923f  xor     edx, edx
0x180019241  mov     rcx, r10
0x180019244  call    ?HrCloneRgIDL@@YAJAEBV?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@HHAEAV12@@Z; HrCloneRgIDL(std::vector<CPConFoldPidl<ConFoldPidl_v3>> const &,int,int,std::vector<CPConFoldPidl<ConFoldPidl_v3>> &)
0x180019249  mov     edi, eax
0x18001924b  test    eax, eax
0x18001924d  js      loc_18001931A
0x180019253  mov     ecx, 38h ; '8'; unsigned __int64
0x180019258  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18001925d  test    rax, rax
0x180019260  jz      loc_180019315
0x180019266  mov     rcx, rax; this
0x180019269  call    ??0ConFoldOnCommandParams@@QEAA@XZ; ConFoldOnCommandParams::ConFoldOnCommandParams(void)
0x18001926e  mov     rbx, rax
0x180019271  test    rax, rax
0x180019274  jz      loc_180019315
0x18001927a  mov     [rax], r14
0x18001927d  lea     rcx, [rax+8]
0x180019281  lea     rdx, [rsp+68h+var_38]
0x180019286  call    ??4?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<CPConFoldPidl<ConFoldPidl_v3>>::operator=(std::vector<CPConFoldPidl<ConFoldPidl_v3>> const &)
0x18001928b  mov     [rbx+20h], rbp
0x18001928f  mov     [rbx+28h], rsi
0x180019293  mov     qword ptr [rbx+30h], 0
0x18001929b  test    rsi, rsi
0x18001929e  jz      short loc_1800192AF
0x1800192a0  mov     rax, [rsi]
0x1800192a3  mov     rcx, rsi
0x1800192a6  mov     rax, [rax+8]
0x1800192aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192af  lea     rcx, ?c_szNetShellDll@@3QBGB; "netshell.dll"
0x1800192b6  call    cs:__imp_LoadLibraryW
0x1800192bc  test    rax, rax
0x1800192bf  jz      short loc_180019303
0x1800192c1  mov     [rbx+30h], rax
0x1800192c5  mov     [rsp+68h+ThreadId], 0
0x1800192cd  lea     rax, [rsp+68h+ThreadId]
0x1800192d2  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x1800192d7  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x1800192df  mov     r9, rbx; lpParameter
0x1800192e2  lea     r8, ?FolderCommandHandlerThreadProc@@YAKPEAX@Z; lpStartAddress
0x1800192e9  xor     edx, edx; dwStackSize
0x1800192eb  xor     ecx, ecx; lpThreadAttributes
0x1800192ed  call    cs:__imp_CreateThread
0x1800192f3  test    rax, rax
0x1800192f6  jz      short loc_180019303
0x1800192f8  mov     rcx, rax; hObject
0x1800192fb  call    cs:__imp_CloseHandle
0x180019301  jmp     short loc_18001931A
0x180019303  mov     qword ptr [rbx+30h], 0
0x18001930b  mov     rcx, rbx; Parameter
0x18001930e  call    ?FolderCommandHandlerThreadProc@@YAKPEAX@Z; FolderCommandHandlerThreadProc(void *)
0x180019313  jmp     short loc_18001931A
0x180019315  mov     edi, 8007000Eh
0x18001931a  lea     rcx, [rsp+68h+var_38]
0x18001931f  call    ??1?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@QEAA@XZ; std::vector<CPConFoldPidl<ConFoldPidl_v3>>::~vector<CPConFoldPidl<ConFoldPidl_v3>>(void)
0x180019324  mov     eax, edi
0x180019326  lea     r11, [rsp+68h+var_18]
0x18001932b  mov     rbx, [r11+20h]
0x18001932f  mov     rbp, [r11+30h]
0x180019333  mov     rsp, r11
0x180019336  pop     r14
0x180019338  pop     rdi
0x180019339  pop     rsi
0x18001933a  retn
```
