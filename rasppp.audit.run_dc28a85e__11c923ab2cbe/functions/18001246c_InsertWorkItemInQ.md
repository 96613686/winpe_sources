# InsertWorkItemInQ

- ea: `0x18001246c`
- end: `0x1800125ce`
- name: `InsertWorkItemInQ`
- size: `354`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180003340`
- `0x180008d10`
- `0x1800096b0`
- `0x18000fafc`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x18001246c`
- `0x18002b0dc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800124fb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800124fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800124b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800124b2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180012589`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180012589`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001259c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001259c`

## string_xrefs

- `0x180012526`: `Inserting extra PROTOCOL_MSG_LineDown for hPort=%d`

## pseudocode

```c
void __fastcall InsertWorkItemInQ(__int64 a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rdi
  int v4; // [rsp+20h] [rbp-818h] BYREF
  _BYTE v5[2044]; // [rsp+24h] [rbp-814h] BYREF

  v4 = 0;
  memset_0(v5, 0, sizeof(v5));
  EnterCriticalSection(&CriticalSection);
  if ( *(&WorkItemQ + 1) )
  {
    *(_QWORD *)*(&WorkItemQ + 1) = a1;
    *(&WorkItemQ + 1) = (void *)a1;
    if ( ProcessLineDown == *(__int64 (__fastcall **)())(a1 + 8) )
    {
      v2 = HeapAlloc(hHeap, 8u, 0x1C10u);
      v3 = v2;
      if ( v2 )
      {
        v2[2] = *(_QWORD *)(a1 + 16);
        v2[1] = ProcessLineDown;
        if ( (byte_18004DF34 & 1) != 0 )
        {
          LOWORD(v4) = 0;
          FormatRRASErrorString(&v4, L"Inserting extra PROTOCOL_MSG_LineDown for hPort=%d", v2[2]);
          if ( (byte_18004DF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(
              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (const EVENT_DESCRIPTOR *)RasPppTraceInfo,
              (const wchar_t *)&v4);
        }
        *v3 = WorkItemQ;
        WorkItemQ = v3;
      }
    }
  }
  else
  {
    WorkItemQ = (void *)a1;
    *(&WorkItemQ + 1) = (void *)a1;
  }
  SetEvent(hEvent);
  LeaveCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x18001246c  mov     [rsp+arg_8], rbx
0x180012471  mov     [rsp+arg_10], rsi
0x180012476  push    rdi
0x180012477  sub     rsp, 830h
0x18001247e  mov     rax, cs:__security_cookie
0x180012485  xor     rax, rsp
0x180012488  mov     [rsp+838h+var_18], rax
0x180012490  mov     rbx, rcx
0x180012493  xor     eax, eax
0x180012495  lea     rcx, [rsp+838h+var_814]; void *
0x18001249a  mov     [rsp+838h+var_818], eax
0x18001249e  xor     edx, edx; Val
0x1800124a0  mov     r8d, 7FCh; Size
0x1800124a6  call    memset_0
0x1800124ab  lea     rcx, CriticalSection; lpCriticalSection
0x1800124b2  call    cs:__imp_EnterCriticalSection
0x1800124b9  nop     dword ptr [rax+rax+00h]
0x1800124be  mov     rax, qword ptr cs:WorkItemQ+8
0x1800124c5  test    rax, rax
0x1800124c8  jz      loc_180012574
0x1800124ce  mov     [rax], rbx
0x1800124d1  lea     rsi, ProcessLineDown
0x1800124d8  mov     qword ptr cs:WorkItemQ+8, rbx
0x1800124df  cmp     rsi, [rbx+8]
0x1800124e3  jnz     loc_180012582
0x1800124e9  mov     rcx, cs:hHeap; hHeap
0x1800124f0  mov     edx, 8; dwFlags
0x1800124f5  mov     r8d, 1C10h; dwBytes
0x1800124fb  call    cs:__imp_HeapAlloc
0x180012502  nop     dword ptr [rax+rax+00h]
0x180012507  mov     rdi, rax
0x18001250a  test    rax, rax
0x18001250d  jz      short loc_180012582
0x18001250f  mov     rcx, [rbx+10h]
0x180012513  mov     [rax+10h], rcx
0x180012517  mov     [rax+8], rsi
0x18001251b  test    cs:byte_18004DF34, 1
0x180012522  jz      short loc_180012561
0x180012524  xor     ecx, ecx
0x180012526  lea     rdx, aInsertingExtra; "Inserting extra PROTOCOL_MSG_LineDown f"...
0x18001252d  mov     word ptr [rsp+838h+var_818], cx
0x180012532  lea     rcx, [rsp+838h+var_818]
0x180012537  mov     r8, [rax+10h]
0x18001253b  call    FormatRRASErrorString
0x180012540  test    cs:byte_18004DF34, 1
0x180012547  jz      short loc_180012561
0x180012549  lea     r8, [rsp+838h+var_818]
0x18001254e  lea     rdx, RasPppTraceInfo
0x180012555  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001255c  call    McTemplateU0z_EventWriteTransfer
0x180012561  mov     rax, qword ptr cs:WorkItemQ
0x180012568  mov     [rdi], rax
0x18001256b  mov     qword ptr cs:WorkItemQ, rdi
0x180012572  jmp     short loc_180012582
0x180012574  mov     qword ptr cs:WorkItemQ, rbx
0x18001257b  mov     qword ptr cs:WorkItemQ+8, rbx
0x180012582  mov     rcx, cs:hEvent; hEvent
0x180012589  call    cs:__imp_SetEvent
0x180012590  nop     dword ptr [rax+rax+00h]
0x180012595  lea     rcx, CriticalSection; lpCriticalSection
0x18001259c  call    cs:__imp_LeaveCriticalSection
0x1800125a3  nop     dword ptr [rax+rax+00h]
0x1800125a8  mov     rcx, [rsp+838h+var_18]
0x1800125b0  xor     rcx, rsp; StackCookie
0x1800125b3  call    __security_check_cookie
0x1800125b8  lea     r11, [rsp+838h+var_8]
0x1800125c0  mov     rbx, [r11+18h]
0x1800125c4  mov     rsi, [r11+20h]
0x1800125c8  mov     rsp, r11
0x1800125cb  pop     rdi
0x1800125cc  retn
```
