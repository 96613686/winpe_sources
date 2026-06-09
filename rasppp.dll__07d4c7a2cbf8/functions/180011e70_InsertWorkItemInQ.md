# InsertWorkItemInQ

- ea: `0x180011e70`
- end: `0x180011fb9`
- name: `InsertWorkItemInQ`
- size: `329`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800032b0`
- `0x1800089b0`
- `0x180009330`
- `0x18000f698`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x180011e70`
- `0x18002a138`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011ef9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011ef9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011eb6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011eb6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011f81`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011f81`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011f8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011f8e`

## string_xrefs

- `0x180011f1e`: `Inserting extra PROTOCOL_MSG_LineDown for hPort=%d`

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
        if ( (byte_18004CF34 & 1) != 0 )
        {
          LOWORD(v4) = 0;
          FormatRRASErrorString(&v4, L"Inserting extra PROTOCOL_MSG_LineDown for hPort=%d", v2[2]);
          if ( (byte_18004CF34 & 1) != 0 )
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
0x180011e70  mov     [rsp+arg_8], rbx
0x180011e75  mov     [rsp+arg_10], rsi
0x180011e7a  push    rdi
0x180011e7b  sub     rsp, 830h
0x180011e82  mov     rax, cs:__security_cookie
0x180011e89  xor     rax, rsp
0x180011e8c  mov     [rsp+838h+var_18], rax
0x180011e94  mov     rbx, rcx
0x180011e97  xor     eax, eax
0x180011e99  lea     rcx, [rsp+838h+var_814]; void *
0x180011e9e  mov     [rsp+838h+var_818], eax
0x180011ea2  xor     edx, edx; Val
0x180011ea4  mov     r8d, 7FCh; Size
0x180011eaa  call    memset_0
0x180011eaf  lea     rcx, CriticalSection; lpCriticalSection
0x180011eb6  call    cs:__imp_EnterCriticalSection
0x180011ebc  mov     rax, qword ptr cs:WorkItemQ+8
0x180011ec3  test    rax, rax
0x180011ec6  jz      loc_180011F6C
0x180011ecc  mov     [rax], rbx
0x180011ecf  lea     rsi, ProcessLineDown
0x180011ed6  mov     qword ptr cs:WorkItemQ+8, rbx
0x180011edd  cmp     rsi, [rbx+8]
0x180011ee1  jnz     loc_180011F7A
0x180011ee7  mov     rcx, cs:hHeap; hHeap
0x180011eee  mov     edx, 8; dwFlags
0x180011ef3  mov     r8d, 1C10h; dwBytes
0x180011ef9  call    cs:__imp_HeapAlloc
0x180011eff  mov     rdi, rax
0x180011f02  test    rax, rax
0x180011f05  jz      short loc_180011F7A
0x180011f07  mov     rcx, [rbx+10h]
0x180011f0b  mov     [rax+10h], rcx
0x180011f0f  mov     [rax+8], rsi
0x180011f13  test    cs:byte_18004CF34, 1
0x180011f1a  jz      short loc_180011F59
0x180011f1c  xor     ecx, ecx
0x180011f1e  lea     rdx, aInsertingExtra; "Inserting extra PROTOCOL_MSG_LineDown f"...
0x180011f25  mov     word ptr [rsp+838h+var_818], cx
0x180011f2a  lea     rcx, [rsp+838h+var_818]
0x180011f2f  mov     r8, [rax+10h]
0x180011f33  call    FormatRRASErrorString
0x180011f38  test    cs:byte_18004CF34, 1
0x180011f3f  jz      short loc_180011F59
0x180011f41  lea     r8, [rsp+838h+var_818]
0x180011f46  lea     rdx, RasPppTraceInfo
0x180011f4d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180011f54  call    McTemplateU0z_EventWriteTransfer
0x180011f59  mov     rax, qword ptr cs:WorkItemQ
0x180011f60  mov     [rdi], rax
0x180011f63  mov     qword ptr cs:WorkItemQ, rdi
0x180011f6a  jmp     short loc_180011F7A
0x180011f6c  mov     qword ptr cs:WorkItemQ, rbx
0x180011f73  mov     qword ptr cs:WorkItemQ+8, rbx
0x180011f7a  mov     rcx, cs:hEvent; hEvent
0x180011f81  call    cs:__imp_SetEvent
0x180011f87  lea     rcx, CriticalSection; lpCriticalSection
0x180011f8e  call    cs:__imp_LeaveCriticalSection
0x180011f94  mov     rcx, [rsp+838h+var_18]
0x180011f9c  xor     rcx, rsp; StackCookie
0x180011f9f  call    __security_check_cookie
0x180011fa4  lea     r11, [rsp+838h+var_8]
0x180011fac  mov     rbx, [r11+18h]
0x180011fb0  mov     rsi, [r11+20h]
0x180011fb4  mov     rsp, r11
0x180011fb7  pop     rdi
0x180011fb8  retn
```
