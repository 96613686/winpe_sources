# GetProcessResourcePoolType

- ea: `0x1400c9674`
- end: `0x1400c9847`
- name: `GetProcessResourcePoolType`
- size: `467`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400c9a50`

## callees

- `0x140004268`
- `0x1400c9674`

## import_xrefs

- `ntoskrnl!PsGetProcessJob` at `0x1400c96af`
- `ntoskrnl!PsGetProcessJob` at `0x1400c96af`
- `ntoskrnl!ObQueryNameString` at `0x1400c96d7`
- `ntoskrnl!ObQueryNameString` at `0x1400c9791`
- `ntoskrnl!ObQueryNameString` at `0x1400c96d7`
- `ntoskrnl!ObQueryNameString` at `0x1400c9791`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400c97d0`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400c97f2`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400c9814`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400c97d0`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400c97f2`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400c9814`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c982f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c982f`
- `ntoskrnl!ExAllocatePool2` at `0x1400c971c`
- `ntoskrnl!ExAllocatePool2` at `0x1400c971c`
- `watchdog!WdLogSingleEntry0` at `0x1400c96ef`
- `watchdog!WdLogSingleEntry0` at `0x1400c973a`
- `watchdog!WdLogSingleEntry0` at `0x1400c97a6`
- `watchdog!WdLogSingleEntry0` at `0x1400c96ef`
- `watchdog!WdLogSingleEntry0` at `0x1400c973a`
- `watchdog!WdLogSingleEntry0` at `0x1400c97a6`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400c9699`

## pseudocode

```c
__int64 __fastcall GetProcessResourcePoolType(__int64 a1)
{
  unsigned int v2; // ebx
  void *ProcessJob; // rax
  void *v4; // rsi
  struct _OBJECT_NAME_INFORMATION *Pool2; // rax
  UNICODE_STRING *p_Name; // rdi
  int v7; // ecx
  int v8; // r8d
  ULONG ReturnLength; // [rsp+80h] [rbp+8h] BYREF

  ReturnLength = 0;
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 80) + 574LL) )
    return 2;
  v2 = 0;
  if ( g_IsInternalReleaseOrDbg )
  {
    ProcessJob = (void *)PsGetProcessJob(*(_QWORD *)(a1 + 16));
    v4 = ProcessJob;
    if ( ProcessJob )
    {
      if ( ObQueryNameString(ProcessJob, 0, 0, &ReturnLength) == -1073741820 )
      {
        Pool2 = (struct _OBJECT_NAME_INFORMATION *)ExAllocatePool2(256, ReturnLength, 1833789782);
        p_Name = &Pool2->Name;
        if ( Pool2 )
        {
          if ( ObQueryNameString(v4, Pool2, ReturnLength, &ReturnLength) >= 0 )
          {
            if ( p_Name->Length )
            {
              if ( RtlCompareUnicodeString(p_Name, &String2, 1u) )
              {
                if ( RtlCompareUnicodeString(p_Name, &stru_14005CA88, 1u) )
                {
                  if ( !RtlCompareUnicodeString(p_Name, &stru_14005CA68, 1u) )
                    v2 = 3;
                }
                else
                {
                  v2 = 2;
                }
              }
              else
              {
                v2 = 1;
              }
            }
          }
          else
          {
            WdLogSingleEntry0(3);
            WdLogGlobalForLineNumber = 218;
          }
          ExFreePoolWithTag(p_Name, 0);
        }
        else
        {
          _InterlockedIncrement(&dword_1400878C0);
          WdLogSingleEntry0(6);
          WdLogGlobalForLineNumber = 206;
          DxgkLogInternalTriageEvent(
            v7,
            262145,
            v8,
            (unsigned int)L"Failed to allocate memory for job object name string",
            206,
            0,
            0,
            0);
        }
      }
      else
      {
        WdLogSingleEntry0(3);
        WdLogGlobalForLineNumber = 193;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1400c9674  mov     rax, rsp
0x1400c9677  push    rbx
0x1400c9678  push    rbp
0x1400c9679  push    rsi
0x1400c967a  push    rdi
0x1400c967b  sub     rsp, 58h
0x1400c967f  xor     ebp, ebp
0x1400c9681  mov     [rax+8], ebp
0x1400c9684  mov     rax, [rcx+50h]
0x1400c9688  cmp     [rax+23Eh], bpl
0x1400c968f  jz      short loc_1400C9699
0x1400c9691  lea     eax, [rbp+2]
0x1400c9694  jmp     loc_1400C983D
0x1400c9699  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400c96a0  mov     ebx, ebp
0x1400c96a2  cmp     [rax], bpl
0x1400c96a5  jz      loc_1400C983B
0x1400c96ab  mov     rcx, [rcx+10h]
0x1400c96af  call    cs:__imp_PsGetProcessJob
0x1400c96b6  nop     dword ptr [rax+rax+00h]
0x1400c96bb  mov     rsi, rax
0x1400c96be  test    rax, rax
0x1400c96c1  jz      loc_1400C983B
0x1400c96c7  lea     r9, [rsp+78h+ReturnLength]; ReturnLength
0x1400c96cf  xor     r8d, r8d; Length
0x1400c96d2  xor     edx, edx; ObjectNameInfo
0x1400c96d4  mov     rcx, rax; Object
0x1400c96d7  call    cs:__imp_ObQueryNameString
0x1400c96de  nop     dword ptr [rax+rax+00h]
0x1400c96e3  cmp     eax, 0C0000004h
0x1400c96e8  jz      short loc_1400C970A
0x1400c96ea  mov     ecx, 3
0x1400c96ef  call    cs:__imp_WdLogSingleEntry0
0x1400c96f6  nop     dword ptr [rax+rax+00h]
0x1400c96fb  mov     cs:WdLogGlobalForLineNumber, 0C1h
0x1400c9705  jmp     loc_1400C983B
0x1400c970a  mov     edx, [rsp+78h+ReturnLength]
0x1400c9711  mov     ecx, 100h
0x1400c9716  mov     r8d, 6D4D6956h
0x1400c971c  call    cs:__imp_ExAllocatePool2
0x1400c9723  nop     dword ptr [rax+rax+00h]
0x1400c9728  mov     rdi, rax
0x1400c972b  test    rax, rax
0x1400c972e  jnz     short loc_1400C977B
0x1400c9730  lock inc cs:dword_1400878C0
0x1400c9737  lea     ecx, [rax+6]
0x1400c973a  call    cs:__imp_WdLogSingleEntry0
0x1400c9741  nop     dword ptr [rax+rax+00h]
0x1400c9746  mov     [rsp+78h+var_40], rbp
0x1400c974b  lea     r9, aFailedToAlloca_3; "Failed to allocate memory for job objec"...
0x1400c9752  mov     eax, 0CEh
0x1400c9757  mov     [rsp+78h+var_48], rbp
0x1400c975c  mov     [rsp+78h+var_50], rbp
0x1400c9761  mov     edx, 40001h
0x1400c9766  mov     cs:WdLogGlobalForLineNumber, eax
0x1400c976c  mov     [rsp+78h+var_58], rax
0x1400c9771  call    DxgkLogInternalTriageEvent
0x1400c9776  jmp     loc_1400C983B
0x1400c977b  mov     r8d, [rsp+78h+ReturnLength]; Length
0x1400c9783  lea     r9, [rsp+78h+ReturnLength]; ReturnLength
0x1400c978b  mov     rdx, rdi; ObjectNameInfo
0x1400c978e  mov     rcx, rsi; Object
0x1400c9791  call    cs:__imp_ObQueryNameString
0x1400c9798  nop     dword ptr [rax+rax+00h]
0x1400c979d  test    eax, eax
0x1400c979f  jns     short loc_1400C97BE
0x1400c97a1  mov     ecx, 3
0x1400c97a6  call    cs:__imp_WdLogSingleEntry0
0x1400c97ad  nop     dword ptr [rax+rax+00h]
0x1400c97b2  mov     cs:WdLogGlobalForLineNumber, 0DAh
0x1400c97bc  jmp     short loc_1400C982A
0x1400c97be  cmp     [rdi], bp
0x1400c97c1  jz      short loc_1400C982A
0x1400c97c3  mov     r8b, 1; CaseInSensitive
0x1400c97c6  lea     rdx, String2; String2
0x1400c97cd  mov     rcx, rdi; String1
0x1400c97d0  call    cs:__imp_RtlCompareUnicodeString
0x1400c97d7  nop     dword ptr [rax+rax+00h]
0x1400c97dc  test    eax, eax
0x1400c97de  jnz     short loc_1400C97E5
0x1400c97e0  lea     ebx, [rax+1]
0x1400c97e3  jmp     short loc_1400C982A
0x1400c97e5  mov     r8b, 1; CaseInSensitive
0x1400c97e8  lea     rdx, stru_14005CA88; String2
0x1400c97ef  mov     rcx, rdi; String1
0x1400c97f2  call    cs:__imp_RtlCompareUnicodeString
0x1400c97f9  nop     dword ptr [rax+rax+00h]
0x1400c97fe  test    eax, eax
0x1400c9800  jnz     short loc_1400C9807
0x1400c9802  lea     ebx, [rax+2]
0x1400c9805  jmp     short loc_1400C982A
0x1400c9807  mov     r8b, 1; CaseInSensitive
0x1400c980a  lea     rdx, stru_14005CA68; String2
0x1400c9811  mov     rcx, rdi; String1
0x1400c9814  call    cs:__imp_RtlCompareUnicodeString
0x1400c981b  nop     dword ptr [rax+rax+00h]
0x1400c9820  test    eax, eax
0x1400c9822  mov     ecx, 3
0x1400c9827  cmovz   ebx, ecx
0x1400c982a  xor     edx, edx; Tag
0x1400c982c  mov     rcx, rdi; P
0x1400c982f  call    cs:__imp_ExFreePoolWithTag
0x1400c9836  nop     dword ptr [rax+rax+00h]
0x1400c983b  mov     eax, ebx
0x1400c983d  add     rsp, 58h
0x1400c9841  pop     rdi
0x1400c9842  pop     rsi
0x1400c9843  pop     rbp
0x1400c9844  pop     rbx
0x1400c9845  retn
```
