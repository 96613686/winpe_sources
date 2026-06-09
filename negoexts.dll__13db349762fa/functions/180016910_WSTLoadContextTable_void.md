# WSTLoadContextTable(void)

- ea: `0x180016910`
- end: `0x1800169ce`
- name: `?WSTLoadContextTable@@YAJXZ`
- size: `190`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018560`

## callees

- `0x18000ca08`
- `0x180016910`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800169bb`
- `ntdll!RtlLeaveCriticalSection` at `0x1800169bb`
- `ntdll!RtlDeleteElementGenericTable` at `0x180016984`
- `ntdll!RtlDeleteElementGenericTable` at `0x180016984`
- `ntdll!RtlEnumerateGenericTable` at `0x1800169a9`
- `ntdll!RtlEnumerateGenericTable` at `0x1800169a9`
- `ntdll!RtlEnterCriticalSection` at `0x18001696d`
- `ntdll!RtlEnterCriticalSection` at `0x18001696d`
- `ntdll!RtlNumberGenericTableElements` at `0x18001695c`
- `ntdll!RtlNumberGenericTableElements` at `0x18001695c`
- `ntdll!RtlInitializeGenericTable` at `0x180016952`
- `ntdll!RtlInitializeGenericTable` at `0x180016952`
- `ntdll!RtlInitializeCriticalSection` at `0x180016921`
- `ntdll!RtlInitializeCriticalSection` at `0x180016921`

## pseudocode

```c
__int64 WSTLoadContextTable(void)
{
  NTSTATUS v0; // edi
  BOOLEAN i; // dl
  __int64 v2; // rsi
  __int64 *v3; // rax

  v0 = RtlInitializeCriticalSection(&WSTGlobalZombieContextTableLock);
  if ( v0 < 0 )
  {
    if ( RtlNumberGenericTableElements(&WSTGlobalZombieContextTable) )
    {
      RtlEnterCriticalSection(&WSTGlobalZombieContextTableLock);
      for ( i = 1; ; i = 0 )
      {
        v3 = (__int64 *)RtlEnumerateGenericTable(&WSTGlobalZombieContextTable, i);
        if ( !v3 )
          break;
        v2 = *v3;
        if ( !RtlDeleteElementGenericTable(&WSTGlobalZombieContextTable, v3) )
          break;
        _InterlockedCompareExchange((volatile signed __int32 *)(v2 + 16), 0, 1);
        WSTDereferenceContext((struct _WST_CONTEXT *)v2);
      }
      RtlLeaveCriticalSection(&WSTGlobalZombieContextTableLock);
    }
  }
  else
  {
    RtlInitializeGenericTable(&WSTGlobalZombieContextTable, WSTContextTableCompare, WSTTableAllocate, WSTTableFree, 0);
    return 0;
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180016910  mov     [rsp+arg_0], rsi
0x180016915  push    rdi
0x180016916  sub     rsp, 30h
0x18001691a  lea     rcx, ?WSTGlobalZombieContextTableLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180016921  call    cs:__imp_RtlInitializeCriticalSection
0x180016927  lea     rcx, ?WSTGlobalZombieContextTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18001692e  mov     edi, eax
0x180016930  test    eax, eax
0x180016932  js      short loc_18001695C
0x180016934  lea     r9, ?WSTTableFree@@YAXPEAU_RTL_GENERIC_TABLE@@PEAX@Z; FreeRoutine
0x18001693b  mov     [rsp+38h+TableContext], 0; TableContext
0x180016944  lea     r8, ?WSTTableAllocate@@YAPEAXPEAU_RTL_GENERIC_TABLE@@K@Z; AllocateRoutine
0x18001694b  lea     rdx, ?WSTContextTableCompare@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_GENERIC_TABLE@@PEAX1@Z; CompareRoutine
0x180016952  call    cs:__imp_RtlInitializeGenericTable
0x180016958  xor     edi, edi
0x18001695a  jmp     short loc_1800169C1
0x18001695c  call    cs:__imp_RtlNumberGenericTableElements
0x180016962  test    eax, eax
0x180016964  jz      short loc_1800169C1
0x180016966  lea     rcx, ?WSTGlobalZombieContextTableLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18001696d  call    cs:__imp_RtlEnterCriticalSection
0x180016973  mov     dl, 1
0x180016975  jmp     short loc_1800169A2
0x180016977  mov     rsi, [rax]
0x18001697a  lea     rcx, ?WSTGlobalZombieContextTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x180016981  mov     rdx, rax; Buffer
0x180016984  call    cs:__imp_RtlDeleteElementGenericTable
0x18001698a  test    al, al
0x18001698c  jz      short loc_1800169B4
0x18001698e  xor     edx, edx
0x180016990  lea     eax, [rdx+1]
0x180016993  lock cmpxchg [rsi+10h], edx
0x180016998  mov     rcx, rsi; struct _WST_CONTEXT *
0x18001699b  call    ?WSTDereferenceContext@@YAXPEAU_WST_CONTEXT@@@Z; WSTDereferenceContext(_WST_CONTEXT *)
0x1800169a0  xor     edx, edx; Restart
0x1800169a2  lea     rcx, ?WSTGlobalZombieContextTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x1800169a9  call    cs:__imp_RtlEnumerateGenericTable
0x1800169af  test    rax, rax
0x1800169b2  jnz     short loc_180016977
0x1800169b4  lea     rcx, ?WSTGlobalZombieContextTableLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800169bb  call    cs:__imp_RtlLeaveCriticalSection
0x1800169c1  mov     rsi, [rsp+38h+arg_0]
0x1800169c6  mov     eax, edi
0x1800169c8  add     rsp, 30h
0x1800169cc  pop     rdi
0x1800169cd  retn
```
