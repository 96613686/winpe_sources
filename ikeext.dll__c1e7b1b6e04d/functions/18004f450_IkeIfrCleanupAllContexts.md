# IkeIfrCleanupAllContexts

- ea: `0x18004f450`
- end: `0x18004f591`
- name: `IkeIfrCleanupAllContexts`
- size: `321`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180058100`

## callees

- `0x1800037c4`
- `0x18001afe0`
- `0x18001b970`
- `0x180020c2c`
- `0x18004f450`
- `0x18004ff88`
- `0x180050850`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x18004f522`
- `ntdll!RtlRemoveEntryHashTable` at `0x18004f522`
- `ntdll!RtlInitEnumerationHashTable` at `0x18004f4a8`
- `ntdll!RtlInitEnumerationHashTable` at `0x18004f4a8`
- `ntdll!RtlEndEnumerationHashTable` at `0x18004f564`
- `ntdll!RtlEndEnumerationHashTable` at `0x18004f564`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f513`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f56d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f513`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f56d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f494`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f4c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f494`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f4c6`

## pseudocode

```c
void IkeIfrCleanupAllContexts()
{
  LPCRITICAL_SECTION v0; // rbx
  struct _RTL_CRITICAL_SECTION *v1; // r14
  LPCRITICAL_SECTION v2; // rsi
  __int64 v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  _QWORD *v5; // rax
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // [rsp+20h] [rbp-50h] BYREF
  LPCVOID v9; // [rsp+28h] [rbp-48h] BYREF
  LPCVOID v10; // [rsp+30h] [rbp-40h] BYREF
  _OWORD v11[3]; // [rsp+38h] [rbp-38h] BYREF

  v0 = gIkeExtGlobals;
  v8 = 0;
  memset(v11, 0, sizeof(v11));
  v1 = (LPCRITICAL_SECTION)((char *)gIkeExtGlobals + 3848);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)gIkeExtGlobals + 3848));
  v2 = v0 + 95;
  RtlInitEnumerationHashTable(&v0[95], (char *)v11 + 8);
  *(_QWORD *)&v11[0] = v0 + 95;
  while ( (unsigned int)WfpHashtableIteratorGetNext(v11, &v8) )
  {
    v3 = v8;
    v10 = (LPCVOID)v8;
    v4 = (struct _RTL_CRITICAL_SECTION *)(v8 + 24);
    EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 24));
    while ( 1 )
    {
      v5 = (_QWORD *)(v3 + 208);
      v6 = *(_QWORD **)(v3 + 208);
      if ( v6 == (_QWORD *)(v3 + 208) )
        break;
      if ( (_QWORD *)v6[1] != v5 || (v7 = *v6, *(_QWORD **)(*v6 + 8LL) != v6) )
        __fastfail(3u);
      *v5 = v7;
      *(_QWORD *)(v7 + 8) = v5;
      v9 = v6;
      IkeIfrFireEvent(v6, v3);
      WfpMemFree(&v9);
    }
    LeaveCriticalSection(v4);
    RtlRemoveEntryHashTable(v2, v3, 0);
    WfpRestructureHashtable(v2);
    if ( *(_DWORD *)(v3 + 72) )
      WfpCriticalSectionDestroy(v4);
    WfpMemFree(&v10);
  }
  RtlEndEnumerationHashTable(*(_QWORD *)&v11[0], (char *)v11 + 8);
  LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x18004f450  push    rbp
0x18004f452  push    rbx
0x18004f453  push    rsi
0x18004f454  push    rdi
0x18004f455  push    r14
0x18004f457  mov     rbp, rsp
0x18004f45a  sub     rsp, 70h
0x18004f45e  mov     rax, cs:__security_cookie
0x18004f465  xor     rax, rsp
0x18004f468  mov     [rbp+var_8], rax
0x18004f46c  mov     rbx, cs:gIkeExtGlobals
0x18004f473  xorps   xmm0, xmm0
0x18004f476  mov     [rbp+var_50], 0
0x18004f47e  movups  [rbp+var_38], xmm0
0x18004f482  lea     r14, [rbx+0F08h]
0x18004f489  mov     rcx, r14; lpCriticalSection
0x18004f48c  movups  [rbp+var_28], xmm0
0x18004f490  movups  [rbp+var_18], xmm0
0x18004f494  call    cs:__imp_EnterCriticalSection
0x18004f49a  lea     rsi, [rbx+0ED8h]
0x18004f4a1  mov     rcx, rsi
0x18004f4a4  lea     rdx, [rbp+var_38+8]
0x18004f4a8  call    cs:__imp_RtlInitEnumerationHashTable
0x18004f4ae  mov     qword ptr [rbp+var_38], rsi
0x18004f4b2  jmp     loc_18004F547
0x18004f4b7  mov     rbx, [rbp+var_50]
0x18004f4bb  mov     [rbp+var_40], rbx
0x18004f4bf  lea     rdi, [rbx+18h]
0x18004f4c3  mov     rcx, rdi; lpCriticalSection
0x18004f4c6  call    cs:__imp_EnterCriticalSection
0x18004f4cc  lea     rax, [rbx+0D0h]
0x18004f4d3  mov     rcx, [rax]
0x18004f4d6  cmp     rcx, rax
0x18004f4d9  jz      short loc_18004F510
0x18004f4db  cmp     [rcx+8], rax
0x18004f4df  jnz     loc_18004F58A
0x18004f4e5  mov     rdx, [rcx]
0x18004f4e8  cmp     [rdx+8], rcx
0x18004f4ec  jnz     loc_18004F58A
0x18004f4f2  mov     [rax], rdx
0x18004f4f5  mov     [rdx+8], rax
0x18004f4f9  mov     rdx, rbx
0x18004f4fc  mov     [rbp+var_48], rcx
0x18004f500  call    IkeIfrFireEvent
0x18004f505  lea     rcx, [rbp+var_48]
0x18004f509  call    WfpMemFree
0x18004f50e  jmp     short loc_18004F4CC
0x18004f510  mov     rcx, rdi; lpCriticalSection
0x18004f513  call    cs:__imp_LeaveCriticalSection
0x18004f519  xor     r8d, r8d
0x18004f51c  mov     rdx, rbx
0x18004f51f  mov     rcx, rsi
0x18004f522  call    cs:__imp_RtlRemoveEntryHashTable
0x18004f528  mov     rcx, rsi
0x18004f52b  call    WfpRestructureHashtable
0x18004f530  cmp     dword ptr [rbx+48h], 0
0x18004f534  jz      short loc_18004F53E
0x18004f536  mov     rcx, rdi
0x18004f539  call    WfpCriticalSectionDestroy
0x18004f53e  lea     rcx, [rbp+var_40]
0x18004f542  call    WfpMemFree
0x18004f547  lea     rdx, [rbp+var_50]
0x18004f54b  lea     rcx, [rbp+var_38]
0x18004f54f  call    WfpHashtableIteratorGetNext
0x18004f554  test    eax, eax
0x18004f556  jnz     loc_18004F4B7
0x18004f55c  mov     rcx, qword ptr [rbp+var_38]
0x18004f560  lea     rdx, [rbp+var_38+8]
0x18004f564  call    cs:__imp_RtlEndEnumerationHashTable
0x18004f56a  mov     rcx, r14; lpCriticalSection
0x18004f56d  call    cs:__imp_LeaveCriticalSection
0x18004f573  mov     rcx, [rbp+var_8]
0x18004f577  xor     rcx, rsp; StackCookie
0x18004f57a  call    __security_check_cookie
0x18004f57f  add     rsp, 70h
0x18004f583  pop     r14
0x18004f585  pop     rdi
0x18004f586  pop     rsi
0x18004f587  pop     rbx
0x18004f588  pop     rbp
0x18004f589  retn
0x18004f58a  mov     ecx, 3
0x18004f58f  int     29h; Win8: RtlFailFast(ecx)
```
