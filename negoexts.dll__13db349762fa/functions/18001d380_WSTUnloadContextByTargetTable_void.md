# WSTUnloadContextByTargetTable(void)

- ea: `0x18001d380`
- end: `0x18001d47d`
- name: `?WSTUnloadContextByTargetTable@@YAXXZ`
- size: `253`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d09c`

## callees

- `0x18000ca08`
- `0x18001d380`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18001d3f8`
- `ntdll!RtlDeleteCriticalSection` at `0x18001d3f8`
- `ntdll!RtlDeleteCriticalSection` at `0x18001d476`
- `ntdll!RtlLeaveCriticalSection` at `0x18001d3ef`
- `ntdll!RtlLeaveCriticalSection` at `0x18001d45e`
- `ntdll!RtlLeaveCriticalSection` at `0x18001d3ef`
- `ntdll!RtlLeaveCriticalSection` at `0x18001d45e`
- `ntdll!RtlDeleteElementGenericTable` at `0x18001d3c0`
- `ntdll!RtlDeleteElementGenericTable` at `0x18001d42f`
- `ntdll!RtlDeleteElementGenericTable` at `0x18001d3c0`
- `ntdll!RtlDeleteElementGenericTable` at `0x18001d42f`
- `ntdll!RtlEnumerateGenericTable` at `0x18001d3e1`
- `ntdll!RtlEnumerateGenericTable` at `0x18001d450`
- `ntdll!RtlEnumerateGenericTable` at `0x18001d3e1`
- `ntdll!RtlEnumerateGenericTable` at `0x18001d450`
- `ntdll!RtlEnterCriticalSection` at `0x18001d3ad`
- `ntdll!RtlEnterCriticalSection` at `0x18001d41c`
- `ntdll!RtlEnterCriticalSection` at `0x18001d3ad`
- `ntdll!RtlEnterCriticalSection` at `0x18001d41c`
- `ntdll!RtlNumberGenericTableElements` at `0x18001d399`
- `ntdll!RtlNumberGenericTableElements` at `0x18001d408`
- `ntdll!RtlNumberGenericTableElements` at `0x18001d399`
- `ntdll!RtlNumberGenericTableElements` at `0x18001d408`

## pseudocode

```c
void WSTUnloadContextByTargetTable(void)
{
  BOOLEAN i; // dl
  __int64 v1; // rbx
  __int64 *v2; // rax
  BOOLEAN j; // dl
  __int64 v4; // rbx
  __int64 *v5; // rax

  if ( RtlNumberGenericTableElements(&WSTGlobalContextByTargetTable) )
  {
    RtlEnterCriticalSection(&WSTGlobalContextByTargetTableLock);
    for ( i = 1; ; i = 0 )
    {
      v2 = (__int64 *)RtlEnumerateGenericTable(&WSTGlobalContextByTargetTable, i);
      if ( !v2 )
        break;
      v1 = *v2;
      if ( !RtlDeleteElementGenericTable(&WSTGlobalContextByTargetTable, v2) )
        break;
      _InterlockedCompareExchange((volatile signed __int32 *)(v1 + 16), 0, 1);
      WSTDereferenceContext((struct _WST_CONTEXT *)v1);
    }
    RtlLeaveCriticalSection(&WSTGlobalContextByTargetTableLock);
  }
  RtlDeleteCriticalSection(&WSTGlobalContextByTargetTableLock);
  if ( RtlNumberGenericTableElements(&WSTGlobalContextByPointerTable) )
  {
    RtlEnterCriticalSection(&WSTGlobalContextByPointerTableLock);
    for ( j = 1; ; j = 0 )
    {
      v5 = (__int64 *)RtlEnumerateGenericTable(&WSTGlobalContextByPointerTable, j);
      if ( !v5 )
        break;
      v4 = *v5;
      if ( !RtlDeleteElementGenericTable(&WSTGlobalContextByPointerTable, v5) )
        break;
      _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 16), 0, 1);
      WSTDereferenceContext((struct _WST_CONTEXT *)v4);
    }
    RtlLeaveCriticalSection(&WSTGlobalContextByPointerTableLock);
  }
  RtlDeleteCriticalSection(&WSTGlobalContextByPointerTableLock);
}

```

## disassembly

```asm
0x18001d380  mov     [rsp+arg_0], rbx
0x18001d385  mov     [rsp+arg_8], rsi
0x18001d38a  push    rdi
0x18001d38b  sub     rsp, 20h
0x18001d38f  lea     rdi, ?WSTGlobalContextByTargetTable@@3U_RTL_GENERIC_TABLE@@A; _RTL_GENERIC_TABLE WSTGlobalContextByTargetTable
0x18001d396  mov     rcx, rdi; Table
0x18001d399  call    cs:__imp_RtlNumberGenericTableElements
0x18001d39f  lea     rsi, ?WSTGlobalContextByTargetTableLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION WSTGlobalContextByTargetTableLock
0x18001d3a6  test    eax, eax
0x18001d3a8  jz      short loc_18001D3F5
0x18001d3aa  mov     rcx, rsi; CriticalSection
0x18001d3ad  call    cs:__imp_RtlEnterCriticalSection
0x18001d3b3  mov     dl, 1
0x18001d3b5  jmp     short loc_18001D3DE
0x18001d3b7  mov     rbx, [rax]
0x18001d3ba  mov     rdx, rax; Buffer
0x18001d3bd  mov     rcx, rdi; Table
0x18001d3c0  call    cs:__imp_RtlDeleteElementGenericTable
0x18001d3c6  test    al, al
0x18001d3c8  jz      short loc_18001D3EC
0x18001d3ca  xor     ecx, ecx
0x18001d3cc  lea     eax, [rcx+1]
0x18001d3cf  lock cmpxchg [rbx+10h], ecx
0x18001d3d4  mov     rcx, rbx; struct _WST_CONTEXT *
0x18001d3d7  call    ?WSTDereferenceContext@@YAXPEAU_WST_CONTEXT@@@Z; WSTDereferenceContext(_WST_CONTEXT *)
0x18001d3dc  xor     edx, edx; Restart
0x18001d3de  mov     rcx, rdi; Table
0x18001d3e1  call    cs:__imp_RtlEnumerateGenericTable
0x18001d3e7  test    rax, rax
0x18001d3ea  jnz     short loc_18001D3B7
0x18001d3ec  mov     rcx, rsi; CriticalSection
0x18001d3ef  call    cs:__imp_RtlLeaveCriticalSection
0x18001d3f5  mov     rcx, rsi; CriticalSection
0x18001d3f8  call    cs:__imp_RtlDeleteCriticalSection
0x18001d3fe  lea     rsi, ?WSTGlobalContextByPointerTable@@3U_RTL_GENERIC_TABLE@@A; _RTL_GENERIC_TABLE WSTGlobalContextByPointerTable
0x18001d405  mov     rcx, rsi; Table
0x18001d408  call    cs:__imp_RtlNumberGenericTableElements
0x18001d40e  lea     rdi, ?WSTGlobalContextByPointerTableLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION WSTGlobalContextByPointerTableLock
0x18001d415  test    eax, eax
0x18001d417  jz      short loc_18001D464
0x18001d419  mov     rcx, rdi; CriticalSection
0x18001d41c  call    cs:__imp_RtlEnterCriticalSection
0x18001d422  mov     dl, 1
0x18001d424  jmp     short loc_18001D44D
0x18001d426  mov     rbx, [rax]
0x18001d429  mov     rdx, rax; Buffer
0x18001d42c  mov     rcx, rsi; Table
0x18001d42f  call    cs:__imp_RtlDeleteElementGenericTable
0x18001d435  test    al, al
0x18001d437  jz      short loc_18001D45B
0x18001d439  xor     edx, edx
0x18001d43b  lea     eax, [rdx+1]
0x18001d43e  lock cmpxchg [rbx+10h], edx
0x18001d443  mov     rcx, rbx; struct _WST_CONTEXT *
0x18001d446  call    ?WSTDereferenceContext@@YAXPEAU_WST_CONTEXT@@@Z; WSTDereferenceContext(_WST_CONTEXT *)
0x18001d44b  xor     edx, edx; Restart
0x18001d44d  mov     rcx, rsi; Table
0x18001d450  call    cs:__imp_RtlEnumerateGenericTable
0x18001d456  test    rax, rax
0x18001d459  jnz     short loc_18001D426
0x18001d45b  mov     rcx, rdi; CriticalSection
0x18001d45e  call    cs:__imp_RtlLeaveCriticalSection
0x18001d464  mov     rcx, rdi
0x18001d467  mov     rbx, [rsp+28h+arg_0]
0x18001d46c  mov     rsi, [rsp+28h+arg_8]
0x18001d471  add     rsp, 20h
0x18001d475  pop     rdi
0x18001d476  jmp     cs:__imp_RtlDeleteCriticalSection
```
