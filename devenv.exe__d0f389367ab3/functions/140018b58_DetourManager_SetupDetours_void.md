# DetourManager::SetupDetours(void)

- ea: `0x140018b58`
- end: `0x1400195e6`
- name: `?SetupDetours@DetourManager@@YAJXZ`
- size: `2702`
- prototype: `__int64 __fastcall(DetourManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000ccfc`

## callees

- `0x140001020`
- `0x140017bec`
- `0x140017bf0`
- `0x140018b58`
- `0x1400195e8`
- `0x140029230`
- `0x140067700`

## import_xrefs

- `ADVAPI32!RegDeleteKeyW` at `0x140018d71`
- `ADVAPI32!RegDeleteKeyA` at `0x140018d82`
- `ADVAPI32!RegDeleteKeyValueW` at `0x140018eb6`
- `ADVAPI32!RegDeleteKeyValueA` at `0x140018ee0`
- `ADVAPI32!RegisterTraceGuidsW` at `0x140018f6c`
- `ADVAPI32!UnregisterTraceGuids` at `0x140018f7a`
- `KERNEL32!HeapLock` at `0x140018fc9`
- `KERNEL32!HeapLock` at `0x140018fc9`
- `KERNEL32!LoadLibraryExA` at `0x140018fa4`
- `KERNEL32!LoadLibraryA` at `0x140018f88`
- `KERNEL32!HeapUnlock` at `0x1400195c1`
- `KERNEL32!HeapUnlock` at `0x1400195c1`
- `KERNEL32!LoadLibraryW` at `0x140018f96`
- `KERNEL32!LoadLibraryExW` at `0x140018fb2`
- `KERNEL32!GetModuleHandleW` at `0x140018b7d`
- `KERNEL32!GetModuleHandleW` at `0x140018b8d`
- `KERNEL32!GetModuleHandleW` at `0x140018b9d`
- `KERNEL32!GetModuleHandleW` at `0x140018baf`
- `KERNEL32!GetModuleHandleW` at `0x140018bbc`
- `KERNEL32!GetModuleHandleW` at `0x140018be1`
- `KERNEL32!GetModuleHandleW` at `0x140018b7d`
- `KERNEL32!GetModuleHandleW` at `0x140018b8d`
- `KERNEL32!GetModuleHandleW` at `0x140018b9d`
- `KERNEL32!GetModuleHandleW` at `0x140018baf`
- `KERNEL32!GetModuleHandleW` at `0x140018bbc`
- `KERNEL32!GetModuleHandleW` at `0x140018be1`
- `KERNEL32!GetProcAddress` at `0x140018bcf`
- `KERNEL32!GetProcAddress` at `0x140018c80`
- `KERNEL32!GetProcAddress` at `0x140018c9c`
- `KERNEL32!GetProcAddress` at `0x140018cb3`
- `KERNEL32!GetProcAddress` at `0x140018cd3`
- `KERNEL32!GetProcAddress` at `0x140018cea`
- `KERNEL32!GetProcAddress` at `0x140018d01`
- `KERNEL32!GetProcAddress` at `0x140018d18`
- `KERNEL32!GetProcAddress` at `0x140018d2f`
- `KERNEL32!GetProcAddress` at `0x140018d46`
- `KERNEL32!GetProcAddress` at `0x140018d5d`
- `KERNEL32!GetProcAddress` at `0x140018d90`
- `KERNEL32!GetProcAddress` at `0x140018da7`
- `KERNEL32!GetProcAddress` at `0x140018dbe`
- `KERNEL32!GetProcAddress` at `0x140018dd5`
- `KERNEL32!GetProcAddress` at `0x140018dec`
- `KERNEL32!GetProcAddress` at `0x140018e03`
- `KERNEL32!GetProcAddress` at `0x140018e1a`
- `KERNEL32!GetProcAddress` at `0x140018e31`
- `KERNEL32!GetProcAddress` at `0x140018e48`
- `KERNEL32!GetProcAddress` at `0x140018e5f`
- `KERNEL32!GetProcAddress` at `0x140018e76`
- `KERNEL32!GetProcAddress` at `0x140018e8d`
- `KERNEL32!GetProcAddress` at `0x140018ea4`
- `KERNEL32!GetProcAddress` at `0x140018ece`
- `KERNEL32!GetProcAddress` at `0x140018bcf`
- `KERNEL32!GetProcAddress` at `0x140018c80`
- `KERNEL32!GetProcAddress` at `0x140018c9c`
- `KERNEL32!GetProcAddress` at `0x140018cb3`
- `KERNEL32!GetProcAddress` at `0x140018cd3`
- `KERNEL32!GetProcAddress` at `0x140018cea`
- `KERNEL32!GetProcAddress` at `0x140018d01`
- `KERNEL32!GetProcAddress` at `0x140018d18`
- `KERNEL32!GetProcAddress` at `0x140018d2f`
- `KERNEL32!GetProcAddress` at `0x140018d46`
- `KERNEL32!GetProcAddress` at `0x140018d5d`
- `KERNEL32!GetProcAddress` at `0x140018d90`
- `KERNEL32!GetProcAddress` at `0x140018da7`
- `KERNEL32!GetProcAddress` at `0x140018dbe`
- `KERNEL32!GetProcAddress` at `0x140018dd5`
- `KERNEL32!GetProcAddress` at `0x140018dec`
- `KERNEL32!GetProcAddress` at `0x140018e03`
- `KERNEL32!GetProcAddress` at `0x140018e1a`
- `KERNEL32!GetProcAddress` at `0x140018e31`
- `KERNEL32!GetProcAddress` at `0x140018e48`
- `KERNEL32!GetProcAddress` at `0x140018e5f`
- `KERNEL32!GetProcAddress` at `0x140018e76`
- `KERNEL32!GetProcAddress` at `0x140018e8d`
- `KERNEL32!GetProcAddress` at `0x140018ea4`
- `KERNEL32!GetProcAddress` at `0x140018ece`
- `KERNEL32!GetProcessHeap` at `0x140018fc0`
- `KERNEL32!GetProcessHeap` at `0x1400195b8`
- `KERNEL32!GetProcessHeap` at `0x140018fc0`
- `KERNEL32!GetProcessHeap` at `0x1400195b8`
- `USER32!GetMessageA` at `0x140018c10`
- `USER32!WaitMessage` at `0x140018c3a`
- `USER32!ShowScrollBar` at `0x140018f5e`
- `USER32!SetScrollRange` at `0x140018f50`
- `USER32!SetScrollPos` at `0x140018f42`
- `USER32!SetScrollInfo` at `0x140018f34`
- `USER32!GetScrollRange` at `0x140018f26`
- `USER32!GetScrollPos` at `0x140018f18`
- `USER32!GetScrollInfo` at `0x140018f0a`
- `USER32!GetScrollBarInfo` at `0x140018efc`
- `USER32!EnableScrollBar` at `0x140018eee`
- `USER32!PeekMessageA` at `0x140018bea`
- `USER32!GetMessageW` at `0x140018c1e`
- `USER32!DefWindowProcW` at `0x140018c64`
- `USER32!DefWindowProcA` at `0x140018c56`
- `USER32!PeekMessageW` at `0x140018c02`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x140018c2c`
- `USER32!GetQueueStatus` at `0x140018c48`
- `ole32!CoWaitForMultipleHandles` at `0x140018c72`

## string_xrefs

- `0x140018d6a`: `RegDeleteKeyExW`
- `0x140018b76`: `user32.dll`
- `0x140018b83`: `ntdll.dll`
- `0x140018b93`: `combase.dll`
- `0x140018bb5`: `kernelbase.dll`
- `0x140018bc5`: `RegCreateKeyExA`
- `0x140018cd9`: `RegCreateKeyExA`
- `0x140018cc9`: `RegCreateKeyExW`
- `0x140018cf0`: `RegOpenKeyExW`
- `0x140018d07`: `RegOpenKeyExA`
- `0x140018d96`: `RegDeleteKeyExA`
- `0x140018dad`: `RegDeleteTreeW`
- `0x140018dc4`: `RegDeleteTreeA`
- `0x140018ddb`: `RegDeleteValueW`
- `0x140018df2`: `RegDeleteValueA`
- `0x140018e9a`: `RegDeleteKeyValueW`
- `0x140018ec4`: `RegDeleteKeyValueA`
- `0x140018bda`: `kernel32.dll`
- `0x140018ba8`: `ole32.dll`

## pseudocode

```c
__int64 __fastcall DetourManager::SetupDetours(DetourManager *this)
{
  HMODULE ModuleHandleW; // rsi
  HMODULE v2; // rdi
  HMODULE v3; // rbx
  HANDLE ProcessHeap; // rax
  int v5; // eax
  int v6; // edi
  unsigned int v7; // ebx
  HANDLE v8; // rax
  __int64 v10; // [rsp+20h] [rbp-18h] BYREF

  ModuleHandleW = GetModuleHandleW(L"user32.dll");
  v2 = GetModuleHandleW(L"ntdll.dll");
  if ( !GetModuleHandleW(L"combase.dll") )
    GetModuleHandleW(L"ole32.dll");
  v3 = GetModuleHandleW(L"kernelbase.dll");
  if ( !GetProcAddress(v3, "RegCreateKeyExA") )
    v3 = GetModuleHandleW(L"kernel32.dll");
  qword_14009C170 = (__int64)PeekMessageA;
  qword_14009C180 = (__int64)PeekMessageW;
  qword_14009C190 = (__int64)GetMessageA;
  qword_14009C1A0 = (__int64)GetMessageW;
  qword_14009C1C0 = (__int64)MsgWaitForMultipleObjectsEx;
  qword_14009C1D0 = (__int64)WaitMessage;
  qword_14009C1E0 = (__int64)GetQueueStatus;
  qword_14009C1F0 = (__int64)DefWindowProcA;
  qword_14009C200 = (__int64)DefWindowProcW;
  qword_14009C1B0 = (__int64)CoWaitForMultipleHandles;
  qword_14009C2A0 = (__int64)GetProcAddress(v2, "RtlAllocateHeap");
  if ( ModuleHandleW )
  {
    qword_14009C2B0 = (__int64)GetProcAddress(ModuleHandleW, "DialogBoxIndirectParamA");
    qword_14009C2C0 = (__int64)GetProcAddress(ModuleHandleW, "DialogBoxIndirectParamW");
  }
  if ( v3 )
  {
    DetourManager::g_arrDetourTableEntry = (struct DetourManager::DetourTableEntry near *)GetProcAddress(
                                                                                            v3,
                                                                                            "RegCreateKeyExW");
    qword_14009C010 = (__int64)GetProcAddress(v3, "RegCreateKeyExA");
    qword_14009C020 = (__int64)GetProcAddress(v3, "RegOpenKeyExW");
    qword_14009C030 = (__int64)GetProcAddress(v3, "RegOpenKeyExA");
    qword_14009C040 = (__int64)GetProcAddress(v3, "RegCloseKey");
    qword_14009C050 = (__int64)GetProcAddress(v3, "RegQueryValueExW");
    qword_14009C060 = (__int64)GetProcAddress(v3, "RegQueryValueExA");
    qword_14009C070 = (__int64)RegDeleteKeyW;
    qword_14009C080 = (__int64)RegDeleteKeyA;
    qword_14009C090 = (__int64)GetProcAddress(v3, "RegDeleteKeyExW");
    qword_14009C0A0 = (__int64)GetProcAddress(v3, "RegDeleteKeyExA");
    qword_14009C0D0 = (__int64)GetProcAddress(v3, "RegDeleteTreeW");
    qword_14009C0E0 = (__int64)GetProcAddress(v3, "RegDeleteTreeA");
    qword_14009C0F0 = (__int64)GetProcAddress(v3, "RegDeleteValueW");
    qword_14009C100 = (__int64)GetProcAddress(v3, "RegDeleteValueA");
    qword_14009C110 = (__int64)GetProcAddress(v3, "RegEnumKeyExW");
    qword_14009C120 = (__int64)GetProcAddress(v3, "RegEnumKeyExA");
    qword_14009C130 = (__int64)GetProcAddress(v3, "RegEnumValueW");
    qword_14009C140 = (__int64)GetProcAddress(v3, "RegEnumValueA");
    qword_14009C150 = (__int64)GetProcAddress(v3, "RegQueryInfoKeyW");
    qword_14009C160 = (__int64)GetProcAddress(v3, "RegQueryInfoKeyA");
    qword_14009C0B0 = (__int64)GetProcAddress(v3, "RegDeleteKeyValueW");
    if ( !qword_14009C0B0 )
      qword_14009C0B0 = (__int64)RegDeleteKeyValueW;
    qword_14009C0C0 = (__int64)GetProcAddress(v3, "RegDeleteKeyValueA");
    if ( !qword_14009C0C0 )
      qword_14009C0C0 = (__int64)RegDeleteKeyValueA;
  }
  qword_14009C210 = (__int64)EnableScrollBar;
  qword_14009C220 = (__int64)GetScrollBarInfo;
  qword_14009C230 = (__int64)GetScrollInfo;
  qword_14009C240 = (__int64)GetScrollPos;
  qword_14009C250 = (__int64)GetScrollRange;
  qword_14009C260 = (__int64)SetScrollInfo;
  qword_14009C270 = (__int64)SetScrollPos;
  qword_14009C280 = (__int64)SetScrollRange;
  qword_14009C290 = (__int64)ShowScrollBar;
  qword_14009C2D0 = (__int64)RegisterTraceGuidsW;
  qword_14009C2E0 = (__int64)UnregisterTraceGuids;
  qword_14009C2F0 = (__int64)LoadLibraryA;
  qword_14009C300 = (__int64)LoadLibraryW;
  qword_14009C310 = (__int64)LoadLibraryExA;
  qword_14009C320 = (__int64)LoadLibraryExW;
  ProcessHeap = GetProcessHeap();
  HeapLock(ProcessHeap);
  v5 = DetourTransactionBegin();
  if ( !v5 )
  {
    v6 = DetourAttach(&qword_14009C170, DetourManager::DetourPeekMessageA);
    if ( v6 )
      goto LABEL_65;
    v6 = DetourAttach(&qword_14009C180, DetourManager::DetourPeekMessageW);
    if ( v6 )
      goto LABEL_65;
    v6 = DetourAttach(&qword_14009C190, DetourManager::DetourGetMessageA);
    if ( v6 )
      goto LABEL_65;
    v6 = DetourAttach(&qword_14009C1A0, DetourManager::DetourGetMessageW);
    if ( v6 )
      goto LABEL_65;
    v6 = DetourAttach(&qword_14009C1B0, DetourManager::DetourCoWaitForMultipleHandles);
    if ( v6 )
      goto LABEL_65;
    v6 = DetourAttach(&qword_14009C1C0, DetourManager::DetourMsgWaitForMultipleObjectsEx);
    if ( v6 )
      goto LABEL_65;
    v6 = DetourAttach(&qword_14009C1E0, DetourManager::DetourGetQueueStatus);
    if ( v6 )
      goto LABEL_65;
    v6 = DetourAttach(&qword_14009C1F0, DetourManager::DetourDefWindowProcA);
    if ( v6 )
      goto LABEL_65;
    v6 = DetourAttach(&qword_14009C200, DetourManager::DetourDefWindowProcW);
    if ( v6 )
      goto LABEL_65;
    v6 = DetourAttach(&qword_14009C2A0, DetourManager::DetourRtlAllocateHeap);
    if ( v6 )
      goto LABEL_65;
    if ( ModuleHandleW )
    {
      v6 = DetourAttach(&qword_14009C2B0, DetourManager::DetourDialogBoxIndirectParamA);
      if ( v6 )
        goto LABEL_65;
      v6 = DetourAttach(&qword_14009C2C0, DetourManager::DetourDialogBoxIndirectParamW);
      if ( v6 )
        goto LABEL_65;
    }
    if ( v3 )
    {
      v6 = DetourAttach(&DetourManager::g_arrDetourTableEntry, DetourManager::DetourRegCreateKeyExW);
      if ( v6 )
        goto LABEL_65;
      v6 = DetourAttach(&qword_14009C010, DetourManager::DetourRegCreateKeyExA);
      if ( v6 )
        goto LABEL_65;
      v6 = DetourAttach(&qword_14009C020, DetourManager::DetourRegOpenKeyExW);
      if ( v6 )
        goto LABEL_65;
      v6 = DetourAttach(&qword_14009C030, DetourManager::DetourRegOpenKeyExA);
      if ( v6 )
        goto LABEL_65;
      v6 = DetourAttach(&qword_14009C040, DetourManager::DetourRegCloseKey);
      if ( v6 )
        goto LABEL_65;
      v6 = DetourAttach(&qword_14009C050, DetourManager::DetourRegQueryValueExW);
      if ( v6 )
        goto LABEL_65;
      v6 = DetourAttach(&qword_14009C060, DetourManager::DetourRegQueryValueExA);
      if ( v6 )
        goto LABEL_65;
      v6 = DetourAttach(&qword_14009C070, DetourManager::DetourRegDeleteKeyW);
      if ( v6 )
        goto LABEL_65;
      v6 = DetourAttach(&qword_14009C080, DetourManager::DetourRegDeleteKeyA);
      if ( v6 )
        goto LABEL_65;
      v6 = DetourAttach(&qword_14009C090, DetourManager::DetourRegDeleteKeyExW);
      if ( v6 )
        goto LABEL_65;
      v6 = DetourAttach(&qword_14009C0A0, DetourManager::DetourRegDeleteKeyExA);
      if ( v6 )
        goto LABEL_65;
      v6 = DetourAttach(&qword_14009C0B0, DetourManager::DetourRegDeleteKeyValueW);
      if ( v6 )
        goto LABEL_65;
      v6 = DetourAttach(&qword_14009C0C0, DetourManager::DetourRegDeleteKeyValueA);
      if ( v6 )
        goto LABEL_65;
      v6 = DetourAttach(&qword_14009C0D0, DetourManager::DetourRegDeleteTreeW);
      if ( v6 )
        goto LABEL_65;
      v6 = DetourAttach(&qword_14009C0E0, DetourManager::DetourRegDeleteTreeA);
      if ( v6 )
        goto LABEL_65;
      v6 = DetourAttach(&qword_14009C0F0, DetourManager::DetourRegDeleteValueW);
      if ( v6 )
        goto LABEL_65;
      v6 = DetourAttach(&qword_14009C100, DetourManager::DetourRegDeleteValueA);
      if ( v6 )
        goto LABEL_65;
      v6 = DetourAttach(&qword_14009C110, DetourManager::DetourRegEnumKeyExW);
      if ( v6 )
        goto LABEL_65;
      v6 = DetourAttach(&qword_14009C120, DetourManager::DetourRegEnumKeyExA);
      if ( v6 )
        goto LABEL_65;
      v6 = DetourAttach(&qword_14009C130, DetourManager::DetourRegEnumValueW);
      if ( v6 )
        goto LABEL_65;
      v6 = DetourAttach(&qword_14009C140, DetourManager::DetourRegEnumValueA);
      if ( v6 )
        goto LABEL_65;
      v6 = DetourAttach(&qword_14009C150, DetourManager::DetourRegQueryInfoKeyW);
      if ( v6 )
        goto LABEL_65;
      v6 = DetourAttach(&qword_14009C160, DetourManager::DetourRegQueryInfoKeyA);
      if ( v6 )
        goto LABEL_65;
    }
    v6 = DetourAttach(&qword_14009C210, DetourManager::DetourEnableScrollBar);
    if ( v6 )
      goto LABEL_65;
    v6 = DetourAttach(&qword_14009C220, DetourManager::DetourGetScrollBarInfo);
    if ( v6 )
      goto LABEL_65;
    v6 = DetourAttach(&qword_14009C230, DetourManager::DetourGetScrollInfo);
    if ( v6 )
      goto LABEL_65;
    v6 = DetourAttach(&qword_14009C240, DetourManager::DetourGetScrollPos);
    if ( v6 )
      goto LABEL_65;
    v6 = DetourAttach(&qword_14009C250, DetourManager::DetourGetScrollRange);
    if ( v6 )
      goto LABEL_65;
    v6 = DetourAttach(&qword_14009C260, DetourManager::DetourSetScrollInfo);
    if ( v6 )
      goto LABEL_65;
    v6 = DetourAttach(&qword_14009C270, DetourManager::DetourSetScrollPos);
    if ( v6 )
      goto LABEL_65;
    v6 = DetourAttach(&qword_14009C280, DetourManager::DetourSetScrollRange);
    if ( v6
      || (v6 = DetourAttach(&qword_14009C290, DetourManager::DetourShowScrollBar)) != 0
      || (v6 = DetourAttach(&qword_14009C2D0, DetourManager::DetourRegisterTraceGuids)) != 0
      || (v6 = DetourAttach(&qword_14009C2E0, DetourManager::DetourUnregisterTraceGuids)) != 0
      || (v6 = DetourAttach(&qword_14009C2F0, DetourManager::DetourLoadLibraryA)) != 0
      || (v6 = DetourAttach(&qword_14009C300, DetourManager::DetourLoadLibraryW)) != 0
      || (v6 = DetourAttach(&qword_14009C310, DetourManager::DetourLoadLibraryExA)) != 0
      || (v6 = DetourAttach(&qword_14009C320, DetourManager::DetourLoadLibraryExW)) != 0 )
    {
LABEL_65:
      DetourTransactionAbort();
      v7 = (unsigned __int16)v6 | 0x80070000;
      if ( v6 <= 0 )
        v7 = v6;
      goto LABEL_72;
    }
    v5 = DetourTransactionCommit();
    if ( v5 )
    {
      v10 = 0;
      v5 = DetourTransactionCommitEx(&v10);
    }
  }
  v7 = (unsigned __int16)v5 | 0x80070000;
  if ( v5 <= 0 )
    v7 = v5;
LABEL_72:
  v8 = GetProcessHeap();
  HeapUnlock(v8);
  return v7;
}

```

## disassembly

```asm
0x140018b58  mov     [rsp+arg_0], rbx
0x140018b5d  mov     [rsp+arg_8], rsi
0x140018b62  push    rdi
0x140018b63  sub     rsp, 30h
0x140018b67  mov     rax, cs:__security_cookie
0x140018b6e  xor     rax, rsp
0x140018b71  mov     [rsp+38h+var_10], rax
0x140018b76  lea     rcx, aUser32Dll_0; "user32.dll"
0x140018b7d  call    cs:__imp_GetModuleHandleW
0x140018b83  lea     rcx, aNtdllDll; "ntdll.dll"
0x140018b8a  mov     rsi, rax
0x140018b8d  call    cs:__imp_GetModuleHandleW
0x140018b93  lea     rcx, aCombaseDll; "combase.dll"
0x140018b9a  mov     rdi, rax
0x140018b9d  call    cs:__imp_GetModuleHandleW
0x140018ba3  test    rax, rax
0x140018ba6  jnz     short loc_140018BB5
0x140018ba8  lea     rcx, aOle32Dll_0; "ole32.dll"
0x140018baf  call    cs:__imp_GetModuleHandleW
0x140018bb5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140018bbc  call    cs:__imp_GetModuleHandleW
0x140018bc2  mov     rcx, rax; hModule
0x140018bc5  lea     rdx, aRegcreatekeyex; "RegCreateKeyExA"
0x140018bcc  mov     rbx, rax
0x140018bcf  call    cs:__imp_GetProcAddress
0x140018bd5  test    rax, rax
0x140018bd8  jnz     short loc_140018BEA
0x140018bda  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x140018be1  call    cs:__imp_GetModuleHandleW
0x140018be7  mov     rbx, rax
0x140018bea  mov     rax, cs:__imp_PeekMessageA
0x140018bf1  lea     rdx, aRtlallocatehea; "RtlAllocateHeap"
0x140018bf8  mov     cs:qword_14009C170, rax
0x140018bff  mov     rcx, rdi; hModule
0x140018c02  mov     rax, cs:__imp_PeekMessageW
0x140018c09  mov     cs:qword_14009C180, rax
0x140018c10  mov     rax, cs:__imp_GetMessageA
0x140018c17  mov     cs:qword_14009C190, rax
0x140018c1e  mov     rax, cs:__imp_GetMessageW
0x140018c25  mov     cs:qword_14009C1A0, rax
0x140018c2c  mov     rax, cs:__imp_MsgWaitForMultipleObjectsEx
0x140018c33  mov     cs:qword_14009C1C0, rax
0x140018c3a  mov     rax, cs:__imp_WaitMessage
0x140018c41  mov     cs:qword_14009C1D0, rax
0x140018c48  mov     rax, cs:__imp_GetQueueStatus
0x140018c4f  mov     cs:qword_14009C1E0, rax
0x140018c56  mov     rax, cs:__imp_DefWindowProcA
0x140018c5d  mov     cs:qword_14009C1F0, rax
0x140018c64  mov     rax, cs:__imp_DefWindowProcW
0x140018c6b  mov     cs:qword_14009C200, rax
0x140018c72  mov     rax, cs:__imp_CoWaitForMultipleHandles
0x140018c79  mov     cs:qword_14009C1B0, rax
0x140018c80  call    cs:__imp_GetProcAddress
0x140018c86  mov     cs:qword_14009C2A0, rax
0x140018c8d  test    rsi, rsi
0x140018c90  jz      short loc_140018CC0
0x140018c92  lea     rdx, aDialogboxindir; "DialogBoxIndirectParamA"
0x140018c99  mov     rcx, rsi; hModule
0x140018c9c  call    cs:__imp_GetProcAddress
0x140018ca2  lea     rdx, aDialogboxindir_0; "DialogBoxIndirectParamW"
0x140018ca9  mov     rcx, rsi; hModule
0x140018cac  mov     cs:qword_14009C2B0, rax
0x140018cb3  call    cs:__imp_GetProcAddress
0x140018cb9  mov     cs:qword_14009C2C0, rax
0x140018cc0  test    rbx, rbx
0x140018cc3  jz      loc_140018EEE
0x140018cc9  lea     rdx, aRegcreatekeyex_0; "RegCreateKeyExW"
0x140018cd0  mov     rcx, rbx; hModule
0x140018cd3  call    cs:__imp_GetProcAddress
0x140018cd9  lea     rdx, aRegcreatekeyex; "RegCreateKeyExA"
0x140018ce0  mov     rcx, rbx; hModule
0x140018ce3  mov     cs:?g_arrDetourTableEntry@DetourManager@@3PAUDetourTableEntry@1@A, rax; DetourManager::DetourTableEntry near * DetourManager::g_arrDetourTableEntry
0x140018cea  call    cs:__imp_GetProcAddress
0x140018cf0  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x140018cf7  mov     rcx, rbx; hModule
0x140018cfa  mov     cs:qword_14009C010, rax
0x140018d01  call    cs:__imp_GetProcAddress
0x140018d07  lea     rdx, aRegopenkeyexa; "RegOpenKeyExA"
0x140018d0e  mov     rcx, rbx; hModule
0x140018d11  mov     cs:qword_14009C020, rax
0x140018d18  call    cs:__imp_GetProcAddress
0x140018d1e  lea     rdx, aRegclosekey; "RegCloseKey"
0x140018d25  mov     rcx, rbx; hModule
0x140018d28  mov     cs:qword_14009C030, rax
0x140018d2f  call    cs:__imp_GetProcAddress
0x140018d35  lea     rdx, aRegqueryvaluee_0; "RegQueryValueExW"
0x140018d3c  mov     rcx, rbx; hModule
0x140018d3f  mov     cs:qword_14009C040, rax
0x140018d46  call    cs:__imp_GetProcAddress
0x140018d4c  lea     rdx, aRegqueryvaluee; "RegQueryValueExA"
0x140018d53  mov     rcx, rbx; hModule
0x140018d56  mov     cs:qword_14009C050, rax
0x140018d5d  call    cs:__imp_GetProcAddress
0x140018d63  mov     cs:qword_14009C060, rax
0x140018d6a  lea     rdx, aRegdeletekeyex_0; "RegDeleteKeyExW"
0x140018d71  mov     rax, cs:__imp_RegDeleteKeyW
0x140018d78  mov     rcx, rbx; hModule
0x140018d7b  mov     cs:qword_14009C070, rax
0x140018d82  mov     rax, cs:__imp_RegDeleteKeyA
0x140018d89  mov     cs:qword_14009C080, rax
0x140018d90  call    cs:__imp_GetProcAddress
0x140018d96  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExA"
0x140018d9d  mov     rcx, rbx; hModule
0x140018da0  mov     cs:qword_14009C090, rax
0x140018da7  call    cs:__imp_GetProcAddress
0x140018dad  lea     rdx, aRegdeletetreew; "RegDeleteTreeW"
0x140018db4  mov     rcx, rbx; hModule
0x140018db7  mov     cs:qword_14009C0A0, rax
0x140018dbe  call    cs:__imp_GetProcAddress
0x140018dc4  lea     rdx, aRegdeletetreea; "RegDeleteTreeA"
0x140018dcb  mov     rcx, rbx; hModule
0x140018dce  mov     cs:qword_14009C0D0, rax
0x140018dd5  call    cs:__imp_GetProcAddress
0x140018ddb  lea     rdx, aRegdeletevalue_0; "RegDeleteValueW"
0x140018de2  mov     rcx, rbx; hModule
0x140018de5  mov     cs:qword_14009C0E0, rax
0x140018dec  call    cs:__imp_GetProcAddress
0x140018df2  lea     rdx, aRegdeletevalue; "RegDeleteValueA"
0x140018df9  mov     rcx, rbx; hModule
0x140018dfc  mov     cs:qword_14009C0F0, rax
0x140018e03  call    cs:__imp_GetProcAddress
0x140018e09  lea     rdx, aRegenumkeyexw; "RegEnumKeyExW"
0x140018e10  mov     rcx, rbx; hModule
0x140018e13  mov     cs:qword_14009C100, rax
0x140018e1a  call    cs:__imp_GetProcAddress
0x140018e20  lea     rdx, aRegenumkeyexa; "RegEnumKeyExA"
0x140018e27  mov     rcx, rbx; hModule
0x140018e2a  mov     cs:qword_14009C110, rax
0x140018e31  call    cs:__imp_GetProcAddress
0x140018e37  lea     rdx, aRegenumvaluew; "RegEnumValueW"
0x140018e3e  mov     rcx, rbx; hModule
0x140018e41  mov     cs:qword_14009C120, rax
0x140018e48  call    cs:__imp_GetProcAddress
0x140018e4e  lea     rdx, aRegenumvaluea; "RegEnumValueA"
0x140018e55  mov     rcx, rbx; hModule
0x140018e58  mov     cs:qword_14009C130, rax
0x140018e5f  call    cs:__imp_GetProcAddress
0x140018e65  lea     rdx, aRegqueryinfoke; "RegQueryInfoKeyW"
0x140018e6c  mov     rcx, rbx; hModule
0x140018e6f  mov     cs:qword_14009C140, rax
0x140018e76  call    cs:__imp_GetProcAddress
0x140018e7c  lea     rdx, aRegqueryinfoke_0; "RegQueryInfoKeyA"
0x140018e83  mov     rcx, rbx; hModule
0x140018e86  mov     cs:qword_14009C150, rax
0x140018e8d  call    cs:__imp_GetProcAddress
0x140018e93  mov     cs:qword_14009C160, rax
0x140018e9a  lea     rdx, aRegdeletekeyva_0; "RegDeleteKeyValueW"
0x140018ea1  mov     rcx, rbx; hModule
0x140018ea4  call    cs:__imp_GetProcAddress
0x140018eaa  mov     cs:qword_14009C0B0, rax
0x140018eb1  test    rax, rax
0x140018eb4  jnz     short loc_140018EC4
0x140018eb6  mov     rax, cs:__imp_RegDeleteKeyValueW
0x140018ebd  mov     cs:qword_14009C0B0, rax
0x140018ec4  lea     rdx, aRegdeletekeyva; "RegDeleteKeyValueA"
0x140018ecb  mov     rcx, rbx; hModule
0x140018ece  call    cs:__imp_GetProcAddress
0x140018ed4  mov     cs:qword_14009C0C0, rax
0x140018edb  test    rax, rax
0x140018ede  jnz     short loc_140018EEE
0x140018ee0  mov     rax, cs:__imp_RegDeleteKeyValueA
0x140018ee7  mov     cs:qword_14009C0C0, rax
0x140018eee  mov     rax, cs:__imp_EnableScrollBar
0x140018ef5  mov     cs:qword_14009C210, rax
0x140018efc  mov     rax, cs:__imp_GetScrollBarInfo
0x140018f03  mov     cs:qword_14009C220, rax
0x140018f0a  mov     rax, cs:__imp_GetScrollInfo
0x140018f11  mov     cs:qword_14009C230, rax
0x140018f18  mov     rax, cs:__imp_GetScrollPos
0x140018f1f  mov     cs:qword_14009C240, rax
0x140018f26  mov     rax, cs:__imp_GetScrollRange
0x140018f2d  mov     cs:qword_14009C250, rax
0x140018f34  mov     rax, cs:__imp_SetScrollInfo
0x140018f3b  mov     cs:qword_14009C260, rax
0x140018f42  mov     rax, cs:__imp_SetScrollPos
0x140018f49  mov     cs:qword_14009C270, rax
0x140018f50  mov     rax, cs:__imp_SetScrollRange
0x140018f57  mov     cs:qword_14009C280, rax
0x140018f5e  mov     rax, cs:__imp_ShowScrollBar
0x140018f65  mov     cs:qword_14009C290, rax
0x140018f6c  mov     rax, cs:__imp_RegisterTraceGuidsW
0x140018f73  mov     cs:qword_14009C2D0, rax
0x140018f7a  mov     rax, cs:__imp_UnregisterTraceGuids
0x140018f81  mov     cs:qword_14009C2E0, rax
0x140018f88  mov     rax, cs:__imp_LoadLibraryA
0x140018f8f  mov     cs:qword_14009C2F0, rax
0x140018f96  mov     rax, cs:__imp_LoadLibraryW
0x140018f9d  mov     cs:qword_14009C300, rax
0x140018fa4  mov     rax, cs:__imp_LoadLibraryExA
0x140018fab  mov     cs:qword_14009C310, rax
0x140018fb2  mov     rax, cs:__imp_LoadLibraryExW
0x140018fb9  mov     cs:qword_14009C320, rax
0x140018fc0  call    cs:__imp_GetProcessHeap
0x140018fc6  mov     rcx, rax; hHeap
0x140018fc9  call    cs:__imp_HeapLock
0x140018fcf  call    DetourTransactionBegin
0x140018fd4  test    eax, eax
0x140018fd6  jnz     loc_1400195AA
0x140018fdc  lea     rdx, ?DetourPeekMessageA@DetourManager@@YAHPEAUtagMSG@@PEAUHWND__@@III@Z; DetourManager::DetourPeekMessageA(tagMSG *,HWND__ *,uint,uint,uint)
0x140018fe3  lea     rcx, qword_14009C170
0x140018fea  call    DetourAttach
0x140018fef  mov     edi, eax
0x140018ff1  test    eax, eax
0x140018ff3  jnz     loc_14001957C
0x140018ff9  lea     rdx, ?DetourPeekMessageW@DetourManager@@YAHPEAUtagMSG@@PEAUHWND__@@III@Z; DetourManager::DetourPeekMessageW(tagMSG *,HWND__ *,uint,uint,uint)
0x140019000  lea     rcx, qword_14009C180
0x140019007  call    DetourAttach
0x14001900c  mov     edi, eax
0x14001900e  test    eax, eax
0x140019010  jnz     loc_14001957C
0x140019016  lea     rdx, ?DetourGetMessageA@DetourManager@@YAHPEAUtagMSG@@PEAUHWND__@@II@Z; DetourManager::DetourGetMessageA(tagMSG *,HWND__ *,uint,uint)
0x14001901d  lea     rcx, qword_14009C190
0x140019024  call    DetourAttach
0x140019029  mov     edi, eax
0x14001902b  test    eax, eax
0x14001902d  jnz     loc_14001957C
0x140019033  lea     rdx, ?DetourGetMessageW@DetourManager@@YAHPEAUtagMSG@@PEAUHWND__@@II@Z; DetourManager::DetourGetMessageW(tagMSG *,HWND__ *,uint,uint)
0x14001903a  lea     rcx, qword_14009C1A0
0x140019041  call    DetourAttach
0x140019046  mov     edi, eax
0x140019048  test    eax, eax
0x14001904a  jnz     loc_14001957C
0x140019050  lea     rdx, ?DetourCoWaitForMultipleHandles@DetourManager@@YAKKKKPEAPEAXPEAK@Z; DetourManager::DetourCoWaitForMultipleHandles(ulong,ulong,ulong,void * *,ulong *)
0x140019057  lea     rcx, qword_14009C1B0
0x14001905e  call    DetourAttach
0x140019063  mov     edi, eax
0x140019065  test    eax, eax
0x140019067  jnz     loc_14001957C
0x14001906d  lea     rdx, ?DetourMsgWaitForMultipleObjectsEx@DetourManager@@YAKKPEAPEAXKKK@Z; DetourManager::DetourMsgWaitForMultipleObjectsEx(ulong,void * *,ulong,ulong,ulong)
0x140019074  lea     rcx, qword_14009C1C0
0x14001907b  call    DetourAttach
0x140019080  mov     edi, eax
0x140019082  test    eax, eax
0x140019084  jnz     loc_14001957C
0x14001908a  lea     rdx, ?DetourGetQueueStatus@DetourManager@@YAKI@Z; DetourManager::DetourGetQueueStatus(uint)
0x140019091  lea     rcx, qword_14009C1E0
0x140019098  call    DetourAttach
0x14001909d  mov     edi, eax
0x14001909f  test    eax, eax
0x1400190a1  jnz     loc_14001957C
0x1400190a7  lea     rdx, ?DetourDefWindowProcA@DetourManager@@YA_JPEAUHWND__@@I_K_J@Z; DetourManager::DetourDefWindowProcA(HWND__ *,uint,unsigned __int64,__int64)
0x1400190ae  lea     rcx, qword_14009C1F0
0x1400190b5  call    DetourAttach
0x1400190ba  mov     edi, eax
0x1400190bc  test    eax, eax
0x1400190be  jnz     loc_14001957C
0x1400190c4  lea     rdx, ?DetourDefWindowProcW@DetourManager@@YA_JPEAUHWND__@@I_K_J@Z; DetourManager::DetourDefWindowProcW(HWND__ *,uint,unsigned __int64,__int64)
0x1400190cb  lea     rcx, qword_14009C200
0x1400190d2  call    DetourAttach
0x1400190d7  mov     edi, eax
0x1400190d9  test    eax, eax
0x1400190db  jnz     loc_14001957C
0x1400190e1  lea     rdx, ?DetourRtlAllocateHeap@DetourManager@@YAPEAXPEAXK_K@Z; DetourManager::DetourRtlAllocateHeap(void *,ulong,unsigned __int64)
0x1400190e8  lea     rcx, qword_14009C2A0
0x1400190ef  call    DetourAttach
0x1400190f4  mov     edi, eax
0x1400190f6  test    eax, eax
0x1400190f8  jnz     loc_14001957C
0x1400190fe  test    rsi, rsi
0x140019101  jz      short loc_14001913D
0x140019103  lea     rdx, ?DetourDialogBoxIndirectParamA@DetourManager@@YA_JPEAUHINSTANCE__@@PEBUDLGTEMPLATE@@PEAUHWND__@@P6A_J2I_K_J@Z4@Z; DetourManager::DetourDialogBoxIndirectParamA(HINSTANCE__ *,DLGTEMPLATE const *,HWND__ *,__int64 (*)(HWND__ *,uint,unsigned __int64,__int64),__int64)
0x14001910a  lea     rcx, qword_14009C2B0
0x140019111  call    DetourAttach
0x140019116  mov     edi, eax
0x140019118  test    eax, eax
0x14001911a  jnz     loc_14001957C
0x140019120  lea     rdx, ?DetourDialogBoxIndirectParamW@DetourManager@@YA_JPEAUHINSTANCE__@@PEBUDLGTEMPLATE@@PEAUHWND__@@P6A_J2I_K_J@Z4@Z; DetourManager::DetourDialogBoxIndirectParamW(HINSTANCE__ *,DLGTEMPLATE const *,HWND__ *,__int64 (*)(HWND__ *,uint,unsigned __int64,__int64),__int64)
0x140019127  lea     rcx, qword_14009C2C0
0x14001912e  call    DetourAttach
0x140019133  mov     edi, eax
0x140019135  test    eax, eax
0x140019137  jnz     loc_14001957C
0x14001913d  test    rbx, rbx
0x140019140  jz      loc_1400193E1
0x140019146  lea     rdx, ?DetourRegCreateKeyExW@DetourManager@@YAJPEAUHKEY__@@PEBGKPEADKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU2@PEAK@Z; DetourManager::DetourRegCreateKeyExW(HKEY__ *,ushort const *,ulong,char *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x14001914d  lea     rcx, ?g_arrDetourTableEntry@DetourManager@@3PAUDetourTableEntry@1@A; DetourManager::DetourTableEntry near * DetourManager::g_arrDetourTableEntry
0x140019154  call    DetourAttach
0x140019159  mov     edi, eax
0x14001915b  test    eax, eax
0x14001915d  jnz     loc_14001957C
0x140019163  lea     rdx, ?DetourRegCreateKeyExA@DetourManager@@YAJPEAUHKEY__@@PEBDKPEADKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU2@PEAK@Z; DetourManager::DetourRegCreateKeyExA(HKEY__ *,char const *,ulong,char *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x14001916a  lea     rcx, qword_14009C010
0x140019171  call    DetourAttach
0x140019176  mov     edi, eax
0x140019178  test    eax, eax
0x14001917a  jnz     loc_14001957C
0x140019180  lea     rdx, ?DetourRegOpenKeyExW@DetourManager@@YAJPEAUHKEY__@@PEBGKKPEAPEAU2@@Z; DetourManager::DetourRegOpenKeyExW(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x140019187  lea     rcx, qword_14009C020
0x14001918e  call    DetourAttach
0x140019193  mov     edi, eax
0x140019195  test    eax, eax
0x140019197  jnz     loc_14001957C
0x14001919d  lea     rdx, ?DetourRegOpenKeyExA@DetourManager@@YAJPEAUHKEY__@@PEBDKKPEAPEAU2@@Z; DetourManager::DetourRegOpenKeyExA(HKEY__ *,char const *,ulong,ulong,HKEY__ * *)
0x1400191a4  lea     rcx, qword_14009C030
0x1400191ab  call    DetourAttach
0x1400191b0  mov     edi, eax
0x1400191b2  test    eax, eax
0x1400191b4  jnz     loc_14001957C
0x1400191ba  lea     rdx, ?DetourRegCloseKey@DetourManager@@YAJPEAUHKEY__@@@Z; DetourManager::DetourRegCloseKey(HKEY__ *)
0x1400191c1  lea     rcx, qword_14009C040
  ... truncated ...
```
