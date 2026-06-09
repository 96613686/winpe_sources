# NcsiThreadPoolInitialize(void)

- ea: `0x180044958`
- end: `0x180044a89`
- name: `?NcsiThreadPoolInitialize@@YA_NXZ`
- size: `305`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180050300`

## callees

- `0x180010200`
- `0x180044958`
- `0x180044a90`
- `0x180044ae4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004496e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004496e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004495c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004495c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180044a0e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180044a0e`

## pseudocode

```c
bool NcsiThreadPoolInitialize(void)
{
  HANDLE ProcessHeap; // rax
  LPVOID v1; // rax
  __int64 v2; // rcx
  PTP_CALLBACK_ENVIRON v3; // rax
  bool result; // al
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  __int64 v6; // rcx
  __int64 v7; // rcx
  PTP_CALLBACK_ENVIRON v8; // rcx

  ProcessHeap = GetProcessHeap();
  v1 = HeapAlloc(ProcessHeap, 8u, 0x48u);
  wil::details::unique_storage<wil::details::resource_policy<_TP_CALLBACK_ENVIRON_V3 *,void (*)(_TP_CALLBACK_ENVIRON_V3 *),&void NhmCloseThreadEnvironment(_TP_CALLBACK_ENVIRON_V3 *),wistd::integral_constant<unsigned __int64,0>,_TP_CALLBACK_ENVIRON_V3 *,_TP_CALLBACK_ENVIRON_V3 *,0,std::nullptr_t>>::reset(
    v2,
    v1);
  v3 = pcbe;
  if ( !pcbe )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_5e61501123913b53efcae049bb9b4698_Traceguids);
    }
    return 0;
  }
  pcbe->Version = 3;
  v3->Pool = 0;
  v3->CleanupGroup = 0;
  v3->CleanupGroupCancelCallback = 0;
  v3->RaceDll = 0;
  v3->ActivationContext = 0;
  v3->FinalizationCallback = 0;
  v3->u.Flags = 0;
  v3->CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  v3->Size = 72;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  wil::details::unique_storage<wil::details::resource_policy<_TP_CLEANUP_GROUP *,void (*)(_TP_CLEANUP_GROUP *),&void NhmCloseThreadCleanupGroup(_TP_CLEANUP_GROUP *),wistd::integral_constant<unsigned __int64,0>,_TP_CLEANUP_GROUP *,_TP_CLEANUP_GROUP *,0,std::nullptr_t>>::reset(
    v6,
    ThreadpoolCleanupGroup);
  if ( !qword_18009D4B0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_5e61501123913b53efcae049bb9b4698_Traceguids);
    }
    wil::details::unique_storage<wil::details::resource_policy<_TP_CALLBACK_ENVIRON_V3 *,void (*)(_TP_CALLBACK_ENVIRON_V3 *),&void NhmCloseThreadEnvironment(_TP_CALLBACK_ENVIRON_V3 *),wistd::integral_constant<unsigned __int64,0>,_TP_CALLBACK_ENVIRON_V3 *,_TP_CALLBACK_ENVIRON_V3 *,0,std::nullptr_t>>::reset(
      v7,
      0);
    return 0;
  }
  v8 = pcbe;
  byte_18009DAA0 = 1;
  pcbe->CleanupGroup = qword_18009D4B0;
  result = 1;
  v8->CleanupGroupCancelCallback = 0;
  return result;
}

```

## disassembly

```asm
0x180044958  sub     rsp, 28h
0x18004495c  call    cs:__imp_GetProcessHeap
0x180044962  mov     edx, 8; dwFlags
0x180044967  mov     rcx, rax; hHeap
0x18004496a  lea     r8d, [rdx+40h]; dwBytes
0x18004496e  call    cs:__imp_HeapAlloc
0x180044974  mov     rdx, rax
0x180044977  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_CALLBACK_ENVIRON_V3@@P6AXPEAU1@@Z$1?NhmCloseThreadEnvironment@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_CALLBACK_ENVIRON_V3@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_CALLBACK_ENVIRON_V3 *,void (*)(_TP_CALLBACK_ENVIRON_V3 *),&NhmCloseThreadEnvironment(_TP_CALLBACK_ENVIRON_V3 *),wistd::integral_constant<unsigned __int64,0>,_TP_CALLBACK_ENVIRON_V3 *,_TP_CALLBACK_ENVIRON_V3 *,0,std::nullptr_t>>::reset(_TP_CALLBACK_ENVIRON_V3 *)
0x18004497c  mov     rax, cs:pcbe
0x180044983  test    rax, rax
0x180044986  jnz     short loc_1800449C3
0x180044988  mov     rcx, cs:WPP_GLOBAL_Control
0x18004498f  lea     rax, WPP_GLOBAL_Control
0x180044996  cmp     rcx, rax
0x180044999  jz      short loc_1800449BC
0x18004499b  test    byte ptr [rcx+1Ch], 10h
0x18004499f  jz      short loc_1800449BC
0x1800449a1  cmp     byte ptr [rcx+19h], 2
0x1800449a5  jb      short loc_1800449BC
0x1800449a7  mov     rcx, [rcx+10h]
0x1800449ab  lea     r8, WPP_5e61501123913b53efcae049bb9b4698_Traceguids
0x1800449b2  mov     edx, 0Ah
0x1800449b7  call    WPP_SF_
0x1800449bc  xor     al, al
0x1800449be  jmp     loc_180044A84
0x1800449c3  mov     dword ptr [rax], 3
0x1800449c9  mov     qword ptr [rax+8], 0
0x1800449d1  mov     qword ptr [rax+10h], 0
0x1800449d9  mov     qword ptr [rax+18h], 0
0x1800449e1  mov     qword ptr [rax+20h], 0
0x1800449e9  mov     qword ptr [rax+28h], 0
0x1800449f1  mov     qword ptr [rax+30h], 0
0x1800449f9  mov     dword ptr [rax+38h], 0
0x180044a00  mov     dword ptr [rax+3Ch], 1
0x180044a07  mov     dword ptr [rax+40h], 48h ; 'H'
0x180044a0e  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180044a14  mov     rdx, rax
0x180044a17  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_CLEANUP_GROUP@@P6AXPEAU1@@Z$1?NhmCloseThreadCleanupGroup@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_CLEANUP_GROUP@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_CLEANUP_GROUP *,void (*)(_TP_CLEANUP_GROUP *),&NhmCloseThreadCleanupGroup(_TP_CLEANUP_GROUP *),wistd::integral_constant<unsigned __int64,0>,_TP_CLEANUP_GROUP *,_TP_CLEANUP_GROUP *,0,std::nullptr_t>>::reset(_TP_CLEANUP_GROUP *)
0x180044a1c  mov     rax, cs:qword_18009D4B0
0x180044a23  test    rax, rax
0x180044a26  jnz     short loc_180044A68
0x180044a28  mov     rcx, cs:WPP_GLOBAL_Control
0x180044a2f  lea     rax, WPP_GLOBAL_Control
0x180044a36  cmp     rcx, rax
0x180044a39  jz      short loc_180044A5C
0x180044a3b  test    byte ptr [rcx+1Ch], 10h
0x180044a3f  jz      short loc_180044A5C
0x180044a41  cmp     byte ptr [rcx+19h], 2
0x180044a45  jb      short loc_180044A5C
0x180044a47  mov     rcx, [rcx+10h]
0x180044a4b  lea     r8, WPP_5e61501123913b53efcae049bb9b4698_Traceguids
0x180044a52  mov     edx, 0Bh
0x180044a57  call    WPP_SF_
0x180044a5c  xor     edx, edx
0x180044a5e  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_CALLBACK_ENVIRON_V3@@P6AXPEAU1@@Z$1?NhmCloseThreadEnvironment@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_CALLBACK_ENVIRON_V3@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_CALLBACK_ENVIRON_V3 *,void (*)(_TP_CALLBACK_ENVIRON_V3 *),&NhmCloseThreadEnvironment(_TP_CALLBACK_ENVIRON_V3 *),wistd::integral_constant<unsigned __int64,0>,_TP_CALLBACK_ENVIRON_V3 *,_TP_CALLBACK_ENVIRON_V3 *,0,std::nullptr_t>>::reset(_TP_CALLBACK_ENVIRON_V3 *)
0x180044a63  jmp     loc_1800449BC
0x180044a68  mov     rcx, cs:pcbe
0x180044a6f  mov     cs:byte_18009DAA0, 1
0x180044a76  mov     [rcx+10h], rax
0x180044a7a  mov     al, 1
0x180044a7c  mov     qword ptr [rcx+18h], 0
0x180044a84  add     rsp, 28h
0x180044a88  retn
```
