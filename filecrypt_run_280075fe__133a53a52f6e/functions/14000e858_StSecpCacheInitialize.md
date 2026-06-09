# StSecpCacheInitialize

- ea: `0x14000e858`
- end: `0x14000ea46`
- name: `StSecpCacheInitialize`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000d604`

## callees

- `0x140003540`
- `0x140003580`
- `0x14000e858`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000e977`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e977`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000e988`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000e988`
- `ntoskrnl!KeInitializeEvent` at `0x14000e957`
- `ntoskrnl!KeInitializeEvent` at `0x14000e957`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14000e9a8`
- `ntoskrnl!RtlInitializeGenericTable` at `0x14000e9f0`
- `ntoskrnl!RtlInitializeGenericTable` at `0x14000e9f0`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14000e9fc`
- `FLTMGR!FltAllocateGenericWorkItem` at `0x14000e9fc`

## string_xrefs

- `0x14000e87f`: `CacheLifetime`
- `0x14000e8bb`: `CacheCleanupTriggerSize`
- `0x14000e8d1`: `CacheMaxSize`
- `0x14000e966`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
__int64 __fastcall StSecpCacheInitialize(void *a1)
{
  __int64 result; // rax
  __int64 (__fastcall *SystemRoutineAddress)(__int64, const wchar_t *, __int64 *); // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v5; // [rsp+40h] [rbp-C0h] BYREF
  int v6; // [rsp+48h] [rbp-B8h]
  const wchar_t *v7; // [rsp+50h] [rbp-B0h]
  int *v8; // [rsp+58h] [rbp-A8h]
  int v9; // [rsp+60h] [rbp-A0h]
  __int64 v10; // [rsp+68h] [rbp-98h]
  int v11; // [rsp+70h] [rbp-90h]
  __int64 v12; // [rsp+78h] [rbp-88h]
  int v13; // [rsp+80h] [rbp-80h]
  const wchar_t *v14; // [rsp+88h] [rbp-78h]
  int *v15; // [rsp+90h] [rbp-70h]
  int v16; // [rsp+98h] [rbp-68h]
  __int64 v17; // [rsp+A0h] [rbp-60h]
  int v18; // [rsp+A8h] [rbp-58h]
  __int64 v19; // [rsp+B0h] [rbp-50h]
  int v20; // [rsp+B8h] [rbp-48h]
  const wchar_t *v21; // [rsp+C0h] [rbp-40h]
  int *v22; // [rsp+C8h] [rbp-38h]
  int v23; // [rsp+D0h] [rbp-30h]
  __int64 v24; // [rsp+D8h] [rbp-28h]
  int v25; // [rsp+E0h] [rbp-20h]
  __int64 v26; // [rsp+E8h] [rbp-18h]
  int v27; // [rsp+F0h] [rbp-10h]
  __int64 v28; // [rsp+F8h] [rbp-8h]
  __int128 v29; // [rsp+100h] [rbp+0h]
  __int128 v30; // [rsp+110h] [rbp+10h]

  v7 = L"CacheLifetime";
  v5 = 0;
  v6 = 288;
  v8 = &g_CacheLifetime;
  v9 = 0x4000000;
  v10 = 0;
  v14 = L"CacheCleanupTriggerSize";
  v15 = &g_CacheCleanupTriggerSize;
  v21 = L"CacheMaxSize";
  v11 = 4;
  v22 = &g_CacheMaxSize;
  v12 = 0;
  v13 = 288;
  v16 = 0x4000000;
  v17 = 0;
  v18 = 4;
  v19 = 0;
  v20 = 288;
  v23 = 0x4000000;
  v24 = 0;
  v25 = 4;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  if ( !a1 )
    return 3221225485LL;
  g_StSecKeyMutex.Owner = 0;
  g_StSecKeyMutex.Count = 1;
  g_StSecKeyMutex.Contention = 0;
  KeInitializeEvent(&g_StSecKeyMutex.Event, SynchronizationEvent, 0);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = (__int64 (__fastcall *)(__int64, const wchar_t *, __int64 *))MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = (__int64 (__fastcall *)(__int64, const wchar_t *, __int64 *))RtlQueryRegistryValues;
  result = SystemRoutineAddress(2, L"StSec", &v5);
  if ( (int)(result + 0x80000000) < 0 || (_DWORD)result == -1073741772 )
  {
    RtlInitializeGenericTable(
      &g_StSecCacheGenericTable,
      StSecpCacheGenericTableCompareRoutine,
      StSecpCacheGenericTableAllocRoutine,
      StSecpCacheGenericTableFreeRoutine,
      0);
    g_WorkItem = FltAllocateGenericWorkItem();
    if ( g_WorkItem )
    {
      g_FilterObject = a1;
      return 0;
    }
    else
    {
      return 3221225495LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000e858  mov     [rsp-8+arg_0], rbx
0x14000e85d  mov     [rsp-8+arg_8], rdi
0x14000e862  push    rbp
0x14000e863  lea     rbp, [rsp-30h]
0x14000e868  sub     rsp, 130h
0x14000e86f  mov     rax, cs:__security_cookie
0x14000e876  xor     rax, rsp
0x14000e879  mov     [rbp+30h+var_10], rax
0x14000e87d  xor     edi, edi
0x14000e87f  lea     rax, aCachelifetime; "CacheLifetime"
0x14000e886  mov     [rsp+130h+var_E0], rax
0x14000e88b  mov     r8d, 120h
0x14000e891  mov     edx, 4000000h
0x14000e896  mov     [rsp+130h+var_F0], rdi
0x14000e89b  lea     rax, g_CacheLifetime
0x14000e8a2  mov     [rsp+130h+var_E8], r8d
0x14000e8a7  mov     [rsp+130h+var_D8], rax
0x14000e8ac  mov     rbx, rcx
0x14000e8af  mov     [rsp+130h+var_D0], edx
0x14000e8b3  lea     ecx, [rdi+4]
0x14000e8b6  mov     [rsp+130h+var_C8], rdi
0x14000e8bb  lea     rax, aCachecleanuptr; "CacheCleanupTriggerSize"
0x14000e8c2  mov     [rbp+30h+var_A8], rax
0x14000e8c6  lea     rax, g_CacheCleanupTriggerSize
0x14000e8cd  mov     [rbp+30h+var_A0], rax
0x14000e8d1  lea     rax, aCachemaxsize; "CacheMaxSize"
0x14000e8d8  mov     [rbp+30h+var_70], rax
0x14000e8dc  xorps   xmm0, xmm0
0x14000e8df  mov     [rsp+130h+var_C0], ecx
0x14000e8e3  lea     rax, g_CacheMaxSize
0x14000e8ea  mov     [rbp+30h+var_68], rax
0x14000e8ee  mov     [rsp+130h+var_B8], rdi
0x14000e8f3  mov     [rbp+30h+var_B0], r8d
0x14000e8f7  mov     [rbp+30h+var_98], edx
0x14000e8fa  mov     [rbp+30h+var_90], rdi
0x14000e8fe  mov     [rbp+30h+var_88], ecx
0x14000e901  mov     [rbp+30h+var_80], rdi
0x14000e905  mov     [rbp+30h+var_78], r8d
0x14000e909  mov     [rbp+30h+var_60], edx
0x14000e90c  mov     [rbp+30h+var_58], rdi
0x14000e910  mov     [rbp+30h+var_50], ecx
0x14000e913  mov     [rbp+30h+var_48], rdi
0x14000e917  mov     [rbp+30h+var_40], edi
0x14000e91a  mov     [rbp+30h+var_38], rdi
0x14000e91e  movups  [rbp+30h+var_30], xmm0
0x14000e922  movups  [rbp+30h+var_20], xmm0
0x14000e926  test    rbx, rbx
0x14000e929  jnz     short loc_14000E935
0x14000e92b  mov     eax, 0C000000Dh
0x14000e930  jmp     loc_14000EA24
0x14000e935  mov     edx, 1; Type
0x14000e93a  mov     cs:g_StSecKeyMutex.Owner, rdi
0x14000e941  xor     r8d, r8d; State
0x14000e944  mov     cs:g_StSecKeyMutex.Count, edx
0x14000e94a  lea     rcx, g_StSecKeyMutex.Event; Event
0x14000e951  mov     cs:g_StSecKeyMutex.Contention, edi
0x14000e957  call    cs:__imp_KeInitializeEvent
0x14000e95e  nop     dword ptr [rax+rax+00h]
0x14000e963  xorps   xmm0, xmm0
0x14000e966  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x14000e96d  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x14000e972  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm0
0x14000e977  call    cs:__imp_RtlInitUnicodeString
0x14000e97e  nop     dword ptr [rax+rax+00h]
0x14000e983  lea     rcx, [rsp+130h+DestinationString]; SystemRoutineName
0x14000e988  call    cs:__imp_MmGetSystemRoutineAddress
0x14000e98f  nop     dword ptr [rax+rax+00h]
0x14000e994  lea     r8, [rsp+130h+var_F0]
0x14000e999  mov     [rsp+130h+TableContext], rdi
0x14000e99e  test    rax, rax
0x14000e9a1  lea     rdx, aStsec; "StSec"
0x14000e9a8  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14000e9b0  xor     r9d, r9d
0x14000e9b3  lea     ecx, [r9+2]
0x14000e9b7  call    _guard_dispatch_icall
0x14000e9bc  mov     edx, 80000000h
0x14000e9c1  lea     ecx, [rax+rdx]
0x14000e9c4  test    edx, ecx
0x14000e9c6  jnz     short loc_14000E9CF
0x14000e9c8  cmp     eax, 0C0000034h
0x14000e9cd  jnz     short loc_14000EA24
0x14000e9cf  lea     r9, StSecpCacheGenericTableFreeRoutine; FreeRoutine
0x14000e9d6  mov     [rsp+130h+TableContext], rdi; TableContext
0x14000e9db  lea     r8, StSecpCacheGenericTableAllocRoutine; AllocateRoutine
0x14000e9e2  lea     rdx, StSecpCacheGenericTableCompareRoutine; CompareRoutine
0x14000e9e9  lea     rcx, g_StSecCacheGenericTable; Table
0x14000e9f0  call    cs:__imp_RtlInitializeGenericTable
0x14000e9f7  nop     dword ptr [rax+rax+00h]
0x14000e9fc  call    cs:__imp_FltAllocateGenericWorkItem
0x14000ea03  nop     dword ptr [rax+rax+00h]
0x14000ea08  mov     cs:g_WorkItem, rax
0x14000ea0f  test    rax, rax
0x14000ea12  jnz     short loc_14000EA1B
0x14000ea14  mov     eax, 0C0000017h
0x14000ea19  jmp     short loc_14000EA24
0x14000ea1b  mov     cs:g_FilterObject, rbx
0x14000ea22  mov     eax, edi
0x14000ea24  mov     rcx, [rbp+30h+var_10]
0x14000ea28  xor     rcx, rsp; StackCookie
0x14000ea2b  call    __security_check_cookie
0x14000ea30  lea     r11, [rsp+130h+var_s0]
0x14000ea38  mov     rbx, [r11+10h]
0x14000ea3c  mov     rdi, [r11+18h]
0x14000ea40  mov     rsp, r11
0x14000ea43  pop     rbp
0x14000ea44  retn
```
