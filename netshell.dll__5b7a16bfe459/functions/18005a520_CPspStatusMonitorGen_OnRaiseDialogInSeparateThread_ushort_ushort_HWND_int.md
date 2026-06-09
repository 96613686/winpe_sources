# CPspStatusMonitorGen::OnRaiseDialogInSeparateThread(ushort,ushort,HWND__ *,int &)

- ea: `0x18005a520`
- end: `0x18005a60c`
- name: `?OnRaiseDialogInSeparateThread@CPspStatusMonitorGen@@QEAA_JGGPEAUHWND__@@AEAH@Z`
- size: `236`
- prototype: `__int64 __fastcall(CPspStatusMonitorGen *__hidden this, unsigned __int16, unsigned __int16, HWND, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x180054180`

## callees

- `0x18000a904`
- `0x180018d74`
- `0x180034ba0`
- `0x18005a520`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005a5f6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005a5f6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005a5c2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005a5c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a5d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a5d0`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005a594`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005a594`

## string_xrefs

- `0x18005a58d`: `netshell.dll`

## pseudocode

```c
__int64 __fastcall CPspStatusMonitorGen::OnRaiseDialogInSeparateThread(
        CPspStatusMonitorGen *this,
        __int16 a2,
        __int16 a3,
        HWND a4)
{
  ULONG (__stdcall *v5)(PVOID); // rbx
  HMODULE LibraryW; // rdi
  void *v7; // r9
  HANDLE v8; // rax
  DWORD ThreadId; // [rsp+68h] [rbp+10h] BYREF

  if ( a3 == 1026 )
    goto LABEL_6;
  if ( a3 == 23505 )
  {
    v5 = (ULONG (__stdcall *)(PVOID))RepairThread;
    goto LABEL_7;
  }
  if ( a3 != 24020 )
  {
LABEL_6:
    v5 = (ULONG (__stdcall *)(PVOID))PropertyThread;
    goto LABEL_7;
  }
  v5 = WlanPropertyThread;
LABEL_7:
  if ( !a2 || a2 == 5 )
  {
    AddRefObj((struct IUnknown *)((*((_QWORD *)this + 11) + 32LL) & -(__int64)(*((_QWORD *)this + 11) != 0)));
    LibraryW = LoadLibraryW(L"netshell.dll");
    if ( LibraryW
      && (v7 = (void *)*((_QWORD *)this + 11), ThreadId = 0, (v8 = CreateThread(0, 0x8000u, v5, v7, 0, &ThreadId)) != 0) )
    {
      CloseHandle(v8);
    }
    else
    {
      ReleaseObj((struct IUnknown *)((*((_QWORD *)this + 11) + 32LL) & -(__int64)(*((_QWORD *)this + 11) != 0)));
      if ( LibraryW )
        FreeLibrary(LibraryW);
      HrFromLastWin32Error();
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18005a520  push    rbx
0x18005a522  push    rbp
0x18005a523  push    rsi
0x18005a524  push    rdi
0x18005a525  sub     rsp, 38h
0x18005a529  mov     eax, 402h
0x18005a52e  mov     rsi, rcx
0x18005a531  cmp     r8w, ax
0x18005a535  jz      short loc_18005A55F
0x18005a537  mov     eax, 5BD1h
0x18005a53c  cmp     r8w, ax
0x18005a540  jz      short loc_18005A556
0x18005a542  mov     eax, 5DD4h
0x18005a547  cmp     r8w, ax
0x18005a54b  jnz     short loc_18005A55F
0x18005a54d  lea     rbx, ?WlanPropertyThread@@YAKPEAVCNetStatisticsEngine@@@Z; WlanPropertyThread(CNetStatisticsEngine *)
0x18005a554  jmp     short loc_18005A566
0x18005a556  lea     rbx, ?RepairThread@@YAKPEAVCNetStatisticsEngine@@@Z; RepairThread(CNetStatisticsEngine *)
0x18005a55d  jmp     short loc_18005A566
0x18005a55f  lea     rbx, ?PropertyThread@@YAKPEAVCNetStatisticsEngine@@@Z; PropertyThread(CNetStatisticsEngine *)
0x18005a566  xor     ebp, ebp
0x18005a568  test    dx, dx
0x18005a56b  jz      short loc_18005A577
0x18005a56d  cmp     dx, 5
0x18005a571  jnz     loc_18005A601
0x18005a577  mov     rax, [rcx+58h]
0x18005a57b  lea     rdx, [rax+20h]
0x18005a57f  neg     rax
0x18005a582  sbb     rcx, rcx
0x18005a585  and     rcx, rdx; struct IUnknown *
0x18005a588  call    ?AddRefObj@@YAKPEAUIUnknown@@@Z; AddRefObj(IUnknown *)
0x18005a58d  lea     rcx, ?c_szNetShellDll@@3QBGB; "netshell.dll"
0x18005a594  call    cs:__imp_LoadLibraryW
0x18005a59a  mov     rdi, rax
0x18005a59d  test    rax, rax
0x18005a5a0  jz      short loc_18005A5D8
0x18005a5a2  mov     r9, [rsi+58h]; lpParameter
0x18005a5a6  lea     rax, [rsp+58h+ThreadId]
0x18005a5ab  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x18005a5b0  mov     r8, rbx; lpStartAddress
0x18005a5b3  mov     edx, 8000h; dwStackSize
0x18005a5b8  mov     [rsp+58h+dwCreationFlags], ebp; dwCreationFlags
0x18005a5bc  xor     ecx, ecx; lpThreadAttributes
0x18005a5be  mov     [rsp+58h+ThreadId], ebp
0x18005a5c2  call    cs:__imp_CreateThread
0x18005a5c8  test    rax, rax
0x18005a5cb  jz      short loc_18005A5D8
0x18005a5cd  mov     rcx, rax; hObject
0x18005a5d0  call    cs:__imp_CloseHandle
0x18005a5d6  jmp     short loc_18005A601
0x18005a5d8  mov     rax, [rsi+58h]
0x18005a5dc  lea     rdx, [rax+20h]
0x18005a5e0  neg     rax
0x18005a5e3  sbb     rcx, rcx
0x18005a5e6  and     rcx, rdx; struct IUnknown *
0x18005a5e9  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18005a5ee  test    rdi, rdi
0x18005a5f1  jz      short loc_18005A5FC
0x18005a5f3  mov     rcx, rdi; hLibModule
0x18005a5f6  call    cs:__imp_FreeLibrary
0x18005a5fc  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18005a601  xor     eax, eax
0x18005a603  add     rsp, 38h
0x18005a607  pop     rdi
0x18005a608  pop     rsi
0x18005a609  pop     rbp
0x18005a60a  pop     rbx
0x18005a60b  retn
```
