# _CatDBSignalPendingJetOpen

- ea: `0x18001b670`
- end: `0x18001b6d2`
- name: `_CatDBSignalPendingJetOpen`
- size: `98`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002fd0`
- `0x18001aa80`
- `0x18001b320`
- `0x18001c6b4`

## callees

- `0x18001b670`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b6a0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b6a0`

## pseudocode

```c
struct _JET_DB_PENDING_OPEN_STRUCT *__fastcall CatDBSignalPendingJetOpen(int a1)
{
  struct _JET_DB_PENDING_OPEN_STRUCT *v1; // rbx
  struct _JET_DB_PENDING_OPEN_STRUCT *result; // rax

  v1 = g_pJetDBPendingOpenHead;
  if ( g_pJetDBPendingOpenHead )
  {
    do
    {
      *((_DWORD *)v1 + 6) = 1;
      *((_DWORD *)v1 + 7) = a1;
      if ( !a1 )
        ++g_dwJetDBOpenRefCnt;
      SetEvent(*((HANDLE *)v1 + 2));
      result = *(struct _JET_DB_PENDING_OPEN_STRUCT **)v1;
      *(_QWORD *)v1 = 0;
      *((_QWORD *)v1 + 1) = 0;
      v1 = result;
      g_pJetDBPendingOpenHead = result;
    }
    while ( result );
  }
  return result;
}

```

## disassembly

```asm
0x18001b670  mov     [rsp+arg_0], rbx
0x18001b675  push    rdi
0x18001b676  sub     rsp, 20h
0x18001b67a  mov     rbx, cs:?g_pJetDBPendingOpenHead@@3PEAU_JET_DB_PENDING_OPEN_STRUCT@@EA; _JET_DB_PENDING_OPEN_STRUCT * g_pJetDBPendingOpenHead
0x18001b681  mov     edi, ecx
0x18001b683  test    rbx, rbx
0x18001b686  jz      short loc_18001B6C7
0x18001b688  mov     dword ptr [rbx+18h], 1
0x18001b68f  mov     [rbx+1Ch], edi
0x18001b692  test    edi, edi
0x18001b694  jnz     short loc_18001B69C
0x18001b696  inc     cs:?g_dwJetDBOpenRefCnt@@3KA; ulong g_dwJetDBOpenRefCnt
0x18001b69c  mov     rcx, [rbx+10h]; hEvent
0x18001b6a0  call    cs:__imp_SetEvent
0x18001b6a6  mov     rax, [rbx]
0x18001b6a9  mov     qword ptr [rbx], 0
0x18001b6b0  mov     qword ptr [rbx+8], 0
0x18001b6b8  mov     rbx, rax
0x18001b6bb  mov     cs:?g_pJetDBPendingOpenHead@@3PEAU_JET_DB_PENDING_OPEN_STRUCT@@EA, rax; _JET_DB_PENDING_OPEN_STRUCT * g_pJetDBPendingOpenHead
0x18001b6c2  test    rax, rax
0x18001b6c5  jnz     short loc_18001B688
0x18001b6c7  mov     rbx, [rsp+28h+arg_0]
0x18001b6cc  add     rsp, 20h
0x18001b6d0  pop     rdi
0x18001b6d1  retn
```
