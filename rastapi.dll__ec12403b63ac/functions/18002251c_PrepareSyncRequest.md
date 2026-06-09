# PrepareSyncRequest

- ea: `0x18002251c`
- end: `0x1800226ea`
- name: `PrepareSyncRequest`
- size: `462`
- prototype: `__int64 __fastcall(unsigned int, int, unsigned int, _QWORD *)`
- caller_count: `10`
- callee_count: `5`
- tags: ``

## callers

- `0x1800226f0`
- `0x180023610`
- `0x180023a14`
- `0x1800240a8`
- `0x1800244ec`
- `0x180024b38`
- `0x180024e60`
- `0x180025244`
- `0x18002619c`
- `0x180026a2c`

## callees

- `0x18002251c`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800225f2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800225f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800225e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800225e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800226b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800226b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022688`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022688`
- `rtutils!TracePrintfA` at `0x1800225cf`
- `rtutils!TracePrintfA` at `0x180022660`
- `rtutils!TracePrintfA` at `0x1800225cf`
- `rtutils!TracePrintfA` at `0x180022660`

## pseudocode

```c
__int64 __fastcall PrepareSyncRequest(unsigned int a1, int a2, unsigned int a3, _QWORD *a4)
{
  unsigned int v8; // edi
  HANDLE ProcessHeap; // rax
  _DWORD *v10; // rax
  _DWORD *v11; // rbx
  bool v12; // zf
  unsigned int v13; // edx
  int v15; // [rsp+20h] [rbp-838h] BYREF
  _BYTE v16[2044]; // [rsp+24h] [rbp-834h] BYREF

  v15 = 0;
  memset_0(v16, 0, sizeof(v16));
  if ( a3 + 56 >= a3 )
  {
    ProcessHeap = GetProcessHeap();
    v10 = HeapAlloc(ProcessHeap, 8u, a3 + 56);
    v11 = v10;
    if ( v10 )
    {
      v8 = 0;
      v10[8] = a1;
      v12 = g_fUseReqId == 0;
      v10[9] = a2;
      v10[10] = a3;
      if ( !v12 )
      {
        EnterCriticalSection(&g_RequestIDCritSec);
        v13 = g_dwRequestID + 1;
        g_dwRequestID = v13;
        v11[12] = v13;
        if ( v13 >= 0x7FFFFFFF )
          g_dwRequestID = 1;
        LeaveCriticalSection(&g_RequestIDCritSec);
      }
      *a4 = v11;
    }
    else
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( qword_18003EC40 )
        {
          LOWORD(v15) = 0;
          FormatRRASErrorString(&v15, L"PrepareSyncRequest: Failed to allocate sync request for oid (%x)", a1);
          ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v15);
        }
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(dwTraceId, "PrepareSyncRequest: Failed to allocate sync request for oid (%x)", a1);
      }
      return 14;
    }
  }
  else
  {
    if ( gIsndpspEtwTracingAvailable )
    {
      if ( qword_18003EC40 )
      {
        LOWORD(v15) = 0;
        FormatRRASErrorString(
          &v15,
          L"PrepareSyncRequest: Arithmetic Overflow error. Failed to allocate sync request for oid (%x)",
          a1);
        ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v15);
      }
    }
    else if ( dwTraceId != -1 )
    {
      TracePrintfA(
        dwTraceId,
        "PrepareSyncRequest: Arithmetic Overflow error. Failed to allocate sync request for oid (%x)",
        a1);
    }
    return 534;
  }
  return v8;
}

```

## disassembly

```asm
0x18002251c  mov     [rsp+arg_8], rbx
0x180022521  push    rbp
0x180022522  push    rsi
0x180022523  push    rdi
0x180022524  push    r14
0x180022526  push    r15
0x180022528  sub     rsp, 830h
0x18002252f  mov     rax, cs:__security_cookie
0x180022536  xor     rax, rsp
0x180022539  mov     [rsp+858h+var_38], rax
0x180022541  mov     ebp, r8d
0x180022544  mov     r15d, edx
0x180022547  mov     esi, ecx
0x180022549  xor     eax, eax
0x18002254b  xor     edx, edx; Val
0x18002254d  mov     [rsp+858h+var_838], eax
0x180022551  mov     r8d, 7FCh; Size
0x180022557  lea     rcx, [rsp+858h+var_834]; void *
0x18002255c  mov     r14, r9
0x18002255f  call    memset_0
0x180022564  lea     eax, [rbp+38h]
0x180022567  cmp     eax, ebp
0x180022569  jnb     short loc_1800225DF
0x18002256b  cmp     cs:gIsndpspEtwTracingAvailable, 0
0x180022572  jz      short loc_1800225BA
0x180022574  cmp     cs:qword_18003EC40, 0
0x18002257c  jz      short loc_1800225D5
0x18002257e  xor     eax, eax
0x180022580  lea     rdx, aPreparesyncreq_0; "PrepareSyncRequest: Arithmetic Overflow"...
0x180022587  mov     r8d, esi
0x18002258a  mov     word ptr [rsp+858h+var_838], ax
0x18002258f  lea     rcx, [rsp+858h+var_838]
0x180022594  call    FormatRRASErrorString
0x180022599  mov     rdx, cs:qword_18003EC40
0x1800225a0  lea     r8, [rsp+858h+var_838]
0x1800225a5  mov     rcx, cs:gNdpspEtwContext
0x1800225ac  mov     rax, cs:gNdpspTemplateFunc
0x1800225b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225b8  jmp     short loc_1800225D5
0x1800225ba  mov     ecx, cs:dwTraceId; dwTraceID
0x1800225c0  cmp     ecx, 0FFFFFFFFh
0x1800225c3  jz      short loc_1800225D5
0x1800225c5  mov     r8d, esi
0x1800225c8  lea     rdx, aPreparesyncreq; "PrepareSyncRequest: Arithmetic Overflow"...
0x1800225cf  call    cs:__imp_TracePrintfA
0x1800225d5  mov     edi, 216h
0x1800225da  jmp     loc_1800226C1
0x1800225df  mov     ebx, eax
0x1800225e1  call    cs:__imp_GetProcessHeap
0x1800225e7  mov     r8d, ebx; dwBytes
0x1800225ea  mov     edx, 8; dwFlags
0x1800225ef  mov     rcx, rax; hHeap
0x1800225f2  call    cs:__imp_HeapAlloc
0x1800225f8  mov     rbx, rax
0x1800225fb  test    rax, rax
0x1800225fe  jnz     short loc_18002266D
0x180022600  cmp     cs:gIsndpspEtwTracingAvailable, eax
0x180022606  jz      short loc_18002264B
0x180022608  cmp     cs:qword_18003EC40, rax
0x18002260f  jz      short loc_180022666
0x180022611  mov     r8d, esi
0x180022614  mov     word ptr [rsp+858h+var_838], ax
0x180022619  lea     rdx, aPreparesyncreq_2; "PrepareSyncRequest: Failed to allocate "...
0x180022620  lea     rcx, [rsp+858h+var_838]
0x180022625  call    FormatRRASErrorString
0x18002262a  mov     rdx, cs:qword_18003EC40
0x180022631  lea     r8, [rsp+858h+var_838]
0x180022636  mov     rcx, cs:gNdpspEtwContext
0x18002263d  mov     rax, cs:gNdpspTemplateFunc
0x180022644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022649  jmp     short loc_180022666
0x18002264b  mov     ecx, cs:dwTraceId; dwTraceID
0x180022651  cmp     ecx, 0FFFFFFFFh
0x180022654  jz      short loc_180022666
0x180022656  mov     r8d, esi
0x180022659  lea     rdx, aPreparesyncreq_1; "PrepareSyncRequest: Failed to allocate "...
0x180022660  call    cs:__imp_TracePrintfA
0x180022666  mov     edi, 0Eh
0x18002266b  jmp     short loc_1800226C1
0x18002266d  xor     edi, edi
0x18002266f  mov     [rax+20h], esi
0x180022672  cmp     cs:g_fUseReqId, edi
0x180022678  mov     [rax+24h], r15d
0x18002267c  mov     [rax+28h], ebp
0x18002267f  jz      short loc_1800226BE
0x180022681  lea     rcx, g_RequestIDCritSec; lpCriticalSection
0x180022688  call    cs:__imp_EnterCriticalSection
0x18002268e  mov     edx, cs:g_dwRequestID
0x180022694  inc     edx
0x180022696  mov     cs:g_dwRequestID, edx
0x18002269c  mov     [rbx+30h], edx
0x18002269f  cmp     edx, 7FFFFFFFh
0x1800226a5  jb      short loc_1800226B1
0x1800226a7  mov     cs:g_dwRequestID, 1
0x1800226b1  lea     rcx, g_RequestIDCritSec; lpCriticalSection
0x1800226b8  call    cs:__imp_LeaveCriticalSection
0x1800226be  mov     [r14], rbx
0x1800226c1  mov     eax, edi
0x1800226c3  mov     rcx, [rsp+858h+var_38]
0x1800226cb  xor     rcx, rsp; StackCookie
0x1800226ce  call    __security_check_cookie
0x1800226d3  mov     rbx, [rsp+858h+arg_8]
0x1800226db  add     rsp, 830h
0x1800226e2  pop     r15
0x1800226e4  pop     r14
0x1800226e6  pop     rdi
0x1800226e7  pop     rsi
0x1800226e8  pop     rbp
0x1800226e9  retn
```
