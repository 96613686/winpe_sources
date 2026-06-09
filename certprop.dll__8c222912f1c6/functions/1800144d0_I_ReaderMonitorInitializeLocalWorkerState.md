# I_ReaderMonitorInitializeLocalWorkerState

- ea: `0x1800144d0`
- end: `0x180014666`
- name: `I_ReaderMonitorInitializeLocalWorkerState`
- size: `406`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003510`

## callees

- `0x180004600`
- `0x1800144d0`
- `0x180018b58`
- `0x180018bb4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001459c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001459c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800145d4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800145f0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800145d4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800145f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145ae`

## pseudocode

```c
__int64 __fastcall I_ReaderMonitorInitializeLocalWorkerState(__int64 a1)
{
  STRSAFE_LPSTR v2; // rcx
  DWORD LastError; // edi
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  HANDLE EventW; // rax
  HANDLE v6; // rax

  WppTraceIndent(a1, 0);
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 198, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  if ( a1 )
  {
    *(_DWORD *)(a1 + 272) = 3;
    *(_QWORD *)(a1 + 280) = 0;
    *(_QWORD *)(a1 + 288) = 0;
    *(_QWORD *)(a1 + 296) = 0;
    *(_QWORD *)(a1 + 304) = 0;
    *(_QWORD *)(a1 + 312) = 0;
    *(_QWORD *)(a1 + 320) = 0;
    *(_DWORD *)(a1 + 328) = 0;
    *(_DWORD *)(a1 + 332) = 1;
    *(_DWORD *)(a1 + 336) = 72;
    ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
    *(_QWORD *)(a1 + 344) = ThreadpoolCleanupGroup;
    if ( ThreadpoolCleanupGroup
      && (*(_QWORD *)(a1 + 288) = ThreadpoolCleanupGroup,
          *(_QWORD *)(a1 + 296) = 0,
          EventW = CreateEventW(0, 0, 0, 0),
          (*(_QWORD *)(a1 + 352) = EventW) != 0)
      && (v6 = CreateEventW(0, 0, 0, 0), (*(_QWORD *)(a1 + 360) = v6) != 0) )
    {
      LastError = 0;
      *(_QWORD *)(a1 + 368) = 0;
      *(_DWORD *)(a1 + 384) = 0;
    }
    else
    {
      LastError = GetLastError();
    }
  }
  else
  {
    LastError = 87;
  }
  WppTraceIndent(v2, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      199,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800144d0  mov     [rsp+arg_0], rbx
0x1800144d5  mov     [rsp+arg_8], rdi
0x1800144da  push    r14
0x1800144dc  sub     rsp, 30h
0x1800144e0  xor     edx, edx
0x1800144e2  mov     rbx, rcx
0x1800144e5  call    WppTraceIndent
0x1800144ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800144f1  lea     r14, WPP_GLOBAL_Control
0x1800144f8  cmp     rcx, r14
0x1800144fb  jz      short loc_180014525
0x1800144fd  test    byte ptr [rcx+1Ch], 2
0x180014501  jz      short loc_180014525
0x180014503  cmp     byte ptr [rcx+19h], 5
0x180014507  jb      short loc_180014525
0x180014509  mov     r9, cs:WPP_pszIndent
0x180014510  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180014517  mov     rcx, [rcx+10h]
0x18001451b  mov     edx, 0C6h
0x180014520  call    WPP_SF_s
0x180014525  test    rbx, rbx
0x180014528  jnz     short loc_180014532
0x18001452a  lea     edi, [rbx+57h]
0x18001452d  jmp     loc_180014611
0x180014532  mov     dword ptr [rbx+110h], 3
0x18001453c  mov     qword ptr [rbx+118h], 0
0x180014547  mov     qword ptr [rbx+120h], 0
0x180014552  mov     qword ptr [rbx+128h], 0
0x18001455d  mov     qword ptr [rbx+130h], 0
0x180014568  mov     qword ptr [rbx+138h], 0
0x180014573  mov     qword ptr [rbx+140h], 0
0x18001457e  mov     dword ptr [rbx+148h], 0
0x180014588  mov     dword ptr [rbx+14Ch], 1
0x180014592  mov     dword ptr [rbx+150h], 48h ; 'H'
0x18001459c  call    cs:__imp_CreateThreadpoolCleanupGroup
0x1800145a2  mov     [rbx+158h], rax
0x1800145a9  test    rax, rax
0x1800145ac  jnz     short loc_1800145B8
0x1800145ae  call    cs:__imp_GetLastError
0x1800145b4  mov     edi, eax
0x1800145b6  jmp     short loc_180014611
0x1800145b8  xor     r9d, r9d; lpName
0x1800145bb  mov     [rbx+120h], rax
0x1800145c2  xor     r8d, r8d; bInitialState
0x1800145c5  mov     qword ptr [rbx+128h], 0
0x1800145d0  xor     edx, edx; bManualReset
0x1800145d2  xor     ecx, ecx; lpEventAttributes
0x1800145d4  call    cs:__imp_CreateEventW
0x1800145da  mov     [rbx+160h], rax
0x1800145e1  test    rax, rax
0x1800145e4  jz      short loc_1800145AE
0x1800145e6  xor     r9d, r9d; lpName
0x1800145e9  xor     r8d, r8d; bInitialState
0x1800145ec  xor     edx, edx; bManualReset
0x1800145ee  xor     ecx, ecx; lpEventAttributes
0x1800145f0  call    cs:__imp_CreateEventW
0x1800145f6  mov     [rbx+168h], rax
0x1800145fd  test    rax, rax
0x180014600  jz      short loc_1800145AE
0x180014602  xor     edi, edi
0x180014604  mov     [rbx+170h], rdi
0x18001460b  mov     [rbx+180h], edi
0x180014611  mov     edx, 1
0x180014616  call    WppTraceIndent
0x18001461b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014622  cmp     rcx, r14
0x180014625  jz      short loc_180014653
0x180014627  test    byte ptr [rcx+1Ch], 2
0x18001462b  jz      short loc_180014653
0x18001462d  cmp     byte ptr [rcx+19h], 5
0x180014631  jb      short loc_180014653
0x180014633  mov     r9, cs:WPP_pszIndent
0x18001463a  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180014641  mov     rcx, [rcx+10h]
0x180014645  mov     edx, 0C7h
0x18001464a  mov     [rsp+38h+var_18], edi
0x18001464e  call    WPP_SF_sD
0x180014653  mov     rbx, [rsp+38h+arg_0]
0x180014658  mov     eax, edi
0x18001465a  mov     rdi, [rsp+38h+arg_8]
0x18001465f  add     rsp, 30h
0x180014663  pop     r14
0x180014665  retn
```
