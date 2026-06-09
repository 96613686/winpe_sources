# RasmanServiceNotify

- ea: `0x180015350`
- end: `0x1800153d9`
- name: `RasmanServiceNotify`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180015350`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015379`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015398`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015379`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015398`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800153cd`

## pseudocode

```c
void __fastcall RasmanServiceNotify(__int64 a1)
{
  int v1; // ecx
  int v2; // ecx

  if ( !*(_DWORD *)(a1 + 24) )
  {
    v1 = *(_DWORD *)(a1 + 64) - 1;
    if ( v1 && (v2 = v1 - 3) != 0 )
    {
      if ( v2 != 4 )
        return;
      EnterCriticalSection(&g_RasCriticalSection);
      g_fRasmanStarted = 1;
    }
    else
    {
      EnterCriticalSection(&g_RasCriticalSection);
      g_fRasmanStarted = 0;
      g_fRCNInitialized = 0;
      g_fRasReferenced = 0;
    }
    LeaveCriticalSection(&g_RasCriticalSection);
  }
}

```

## disassembly

```asm
0x180015350  sub     rsp, 28h
0x180015354  cmp     dword ptr [rcx+18h], 0
0x180015358  jz      short loc_180015360
0x18001535a  add     rsp, 28h
0x18001535e  retn
0x180015360  mov     ecx, [rcx+40h]
0x180015363  sub     ecx, 1
0x180015366  jz      short loc_180015391
0x180015368  sub     ecx, 3
0x18001536b  jz      short loc_180015391
0x18001536d  cmp     ecx, 4
0x180015370  jnz     short loc_18001535A
0x180015372  lea     rcx, g_RasCriticalSection; lpCriticalSection
0x180015379  call    cs:__imp_EnterCriticalSection
0x180015380  nop     dword ptr [rax+rax+00h]
0x180015385  mov     cs:g_fRasmanStarted, 1
0x18001538f  jmp     short loc_1800153C2
0x180015391  lea     rcx, g_RasCriticalSection; lpCriticalSection
0x180015398  call    cs:__imp_EnterCriticalSection
0x18001539f  nop     dword ptr [rax+rax+00h]
0x1800153a4  mov     cs:g_fRasmanStarted, 0
0x1800153ae  mov     cs:g_fRCNInitialized, 0
0x1800153b8  mov     cs:g_fRasReferenced, 0
0x1800153c2  lea     rcx, g_RasCriticalSection
0x1800153c9  add     rsp, 28h
0x1800153cd  jmp     cs:__imp_LeaveCriticalSection
```
