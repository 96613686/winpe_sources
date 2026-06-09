# SocketBrokerTable::CleanAll(void)

- ea: `0x1800262c0`
- end: `0x18002636c`
- name: `?CleanAll@SocketBrokerTable@@AEAAXXZ`
- size: `172`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800261b4`

## callees

- `0x180001ebc`
- `0x180017804`
- `0x1800262c0`

## import_xrefs

- `ntdll!RtlDeleteHashTable` at `0x180026349`
- `ntdll!RtlDeleteHashTable` at `0x180026349`
- `ntdll!RtlRemoveEntryHashTable` at `0x18002630c`
- `ntdll!RtlRemoveEntryHashTable` at `0x18002630c`
- `ntdll!RtlInitEnumerationHashTable` at `0x1800262fe`
- `ntdll!RtlInitEnumerationHashTable` at `0x1800262fe`
- `ntdll!RtlEndEnumerationHashTable` at `0x180026340`
- `ntdll!RtlEndEnumerationHashTable` at `0x180026340`
- `ntdll!RtlEnumerateEntryHashTable` at `0x18002632a`
- `ntdll!RtlEnumerateEntryHashTable` at `0x18002632a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800262e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800262e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026356`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026356`

## pseudocode

```c
void __fastcall SocketBrokerTable::CleanAll(LPCRITICAL_SECTION lpCriticalSection)
{
  __int64 v2; // rax
  SocketBrokerContext *v3; // rsi
  LPCRITICAL_SECTION v4; // rcx
  _OWORD v5[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+40h] [rbp-18h]

  memset(v5, 0, sizeof(v5));
  v6 = 0;
  EnterCriticalSection(lpCriticalSection);
  if ( LOBYTE(lpCriticalSection[2].DebugInfo) )
  {
    RtlInitEnumerationHashTable(&lpCriticalSection[1], v5);
    while ( 1 )
    {
      v2 = RtlEnumerateEntryHashTable(&lpCriticalSection[1], v5);
      v3 = (SocketBrokerContext *)v2;
      v4 = lpCriticalSection + 1;
      if ( !v2 )
        break;
      RtlRemoveEntryHashTable(v4, v2, 0);
      SocketBrokerContext::CleanupSockets(v3);
      SocketBrokerContext::ReleaseRef(v3);
    }
    RtlEndEnumerationHashTable(v4, v5);
    RtlDeleteHashTable(&lpCriticalSection[1]);
    LOBYTE(lpCriticalSection[2].DebugInfo) = 0;
  }
  LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x1800262c0  mov     [rsp+arg_0], rbx
0x1800262c5  mov     [rsp+arg_8], rsi
0x1800262ca  push    rdi
0x1800262cb  sub     rsp, 50h
0x1800262cf  xorps   xmm0, xmm0
0x1800262d2  xor     eax, eax
0x1800262d4  movups  [rsp+58h+var_38], xmm0
0x1800262d9  mov     [rsp+58h+var_18], rax
0x1800262de  mov     rbx, rcx
0x1800262e1  movups  [rsp+58h+var_28], xmm0
0x1800262e6  call    cs:__imp_EnterCriticalSection
0x1800262ec  cmp     byte ptr [rbx+50h], 0
0x1800262f0  jz      short loc_180026353
0x1800262f2  lea     rdi, [rbx+28h]
0x1800262f6  mov     rcx, rdi
0x1800262f9  lea     rdx, [rsp+58h+var_38]
0x1800262fe  call    cs:__imp_RtlInitEnumerationHashTable
0x180026304  jmp     short loc_180026322
0x180026306  xor     r8d, r8d
0x180026309  mov     rdx, rsi
0x18002630c  call    cs:__imp_RtlRemoveEntryHashTable
0x180026312  mov     rcx, rsi; this
0x180026315  call    ?CleanupSockets@SocketBrokerContext@@QEAAXXZ; SocketBrokerContext::CleanupSockets(void)
0x18002631a  mov     rcx, rsi; this
0x18002631d  call    ?ReleaseRef@SocketBrokerContext@@QEAAXXZ; SocketBrokerContext::ReleaseRef(void)
0x180026322  lea     rdx, [rsp+58h+var_38]
0x180026327  mov     rcx, rdi
0x18002632a  call    cs:__imp_RtlEnumerateEntryHashTable
0x180026330  mov     rsi, rax
0x180026333  mov     rcx, rdi
0x180026336  test    rax, rax
0x180026339  jnz     short loc_180026306
0x18002633b  lea     rdx, [rsp+58h+var_38]
0x180026340  call    cs:__imp_RtlEndEnumerationHashTable
0x180026346  mov     rcx, rdi
0x180026349  call    cs:__imp_RtlDeleteHashTable
0x18002634f  mov     byte ptr [rbx+50h], 0
0x180026353  mov     rcx, rbx; lpCriticalSection
0x180026356  call    cs:__imp_LeaveCriticalSection
0x18002635c  mov     rbx, [rsp+58h+arg_0]
0x180026361  mov     rsi, [rsp+58h+arg_8]
0x180026366  add     rsp, 50h
0x18002636a  pop     rdi
0x18002636b  retn
```
