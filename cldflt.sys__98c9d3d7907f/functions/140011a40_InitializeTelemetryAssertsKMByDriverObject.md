# InitializeTelemetryAssertsKMByDriverObject

- ea: `0x140011a40`
- end: `0x140011b3c`
- name: `InitializeTelemetryAssertsKMByDriverObject`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140087490`

## callees

- `0x140011a40`
- `0x140011b44`

## import_xrefs

- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140011aab`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140011aab`
- `ntoskrnl!RtlFreeAnsiString` at `0x140011b22`
- `ntoskrnl!RtlFreeAnsiString` at `0x140011b22`
- `ntoskrnl!IoQueryFullDriverPath` at `0x140011a8c`
- `ntoskrnl!IoQueryFullDriverPath` at `0x140011a8c`
- `ntoskrnl!RtlInitAnsiString` at `0x140011afe`
- `ntoskrnl!RtlInitAnsiString` at `0x140011afe`
- `ntoskrnl!RtlInitUnicodeString` at `0x140011a79`
- `ntoskrnl!RtlInitUnicodeString` at `0x140011a79`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011abf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011abf`

## pseudocode

```c
__int64 __fastcall InitializeTelemetryAssertsKMByDriverObject(__int64 a1)
{
  __int64 result; // rax
  NTSTATUS v3; // ebx
  __int64 i; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  _STRING AnsiString; // [rsp+30h] [rbp-30h] BYREF
  struct _STRING v7; // [rsp+40h] [rbp-20h] BYREF
  struct _STRING v8; // [rsp+50h] [rbp-10h] BYREF

  AnsiString = 0;
  DestinationString = 0;
  if ( _InterlockedExchangeAdd(&g_AssertsOperational, 0) )
    return 0;
  RtlInitUnicodeString(&DestinationString, 0);
  result = IoQueryFullDriverPath(a1, &DestinationString);
  if ( (int)result >= 0 )
  {
    v3 = RtlUnicodeStringToAnsiString(&AnsiString, &DestinationString, 1u);
    ExFreePoolWithTag(DestinationString.Buffer, 0);
    if ( v3 >= 0 )
    {
      for ( i = (unsigned int)AnsiString.Length - 1; (_DWORD)i; i = (unsigned int)(i - 1) )
      {
        if ( AnsiString.Buffer[i] == 92 )
        {
          if ( (_DWORD)i != AnsiString.Length )
          {
            v7 = 0;
            RtlInitAnsiString(&v7, &AnsiString.Buffer[(unsigned int)(i + 1)]);
            v8 = v7;
            v3 = InitializeTelemetryAssertsKMWorkerInternal(&v8);
          }
          break;
        }
      }
      RtlFreeAnsiString(&AnsiString);
    }
    return (unsigned int)v3;
  }
  return result;
}

```

## disassembly

```asm
0x140011a40  mov     [rsp-8+arg_0], rbx
0x140011a45  push    rbp
0x140011a46  mov     rbp, rsp
0x140011a49  sub     rsp, 60h
0x140011a4d  xorps   xmm0, xmm0
0x140011a50  xorps   xmm1, xmm1
0x140011a53  movups  xmmword ptr [rbp+AnsiString.Length], xmm0
0x140011a57  mov     rbx, rcx
0x140011a5a  xor     eax, eax
0x140011a5c  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x140011a60  lock xadd cs:g_AssertsOperational, eax
0x140011a68  test    eax, eax
0x140011a6a  jz      short loc_140011A73
0x140011a6c  xor     eax, eax
0x140011a6e  jmp     loc_140011B30
0x140011a73  xor     edx, edx; SourceString
0x140011a75  lea     rcx, [rbp+DestinationString]; DestinationString
0x140011a79  call    cs:__imp_RtlInitUnicodeString
0x140011a80  nop     dword ptr [rax+rax+00h]
0x140011a85  lea     rdx, [rbp+DestinationString]
0x140011a89  mov     rcx, rbx
0x140011a8c  call    cs:__imp_IoQueryFullDriverPath
0x140011a93  nop     dword ptr [rax+rax+00h]
0x140011a98  test    eax, eax
0x140011a9a  js      loc_140011B30
0x140011aa0  mov     r8b, 1; AllocateDestinationString
0x140011aa3  lea     rdx, [rbp+DestinationString]; SourceString
0x140011aa7  lea     rcx, [rbp+AnsiString]; DestinationString
0x140011aab  call    cs:__imp_RtlUnicodeStringToAnsiString
0x140011ab2  nop     dword ptr [rax+rax+00h]
0x140011ab7  mov     rcx, [rbp+DestinationString.Buffer]; P
0x140011abb  xor     edx, edx; Tag
0x140011abd  mov     ebx, eax
0x140011abf  call    cs:__imp_ExFreePoolWithTag
0x140011ac6  nop     dword ptr [rax+rax+00h]
0x140011acb  test    ebx, ebx
0x140011acd  js      short loc_140011B2E
0x140011acf  movzx   edx, [rbp+AnsiString.Length]
0x140011ad3  mov     r8, [rbp+AnsiString.Buffer]
0x140011ad7  lea     ecx, [rdx-1]
0x140011ada  test    ecx, ecx
0x140011adc  jz      short loc_140011B1E
0x140011ade  cmp     byte ptr [rcx+r8], 5Ch ; '\'
0x140011ae3  jz      short loc_140011AE9
0x140011ae5  dec     ecx
0x140011ae7  jmp     short loc_140011ADA
0x140011ae9  cmp     ecx, edx
0x140011aeb  jz      short loc_140011B1E
0x140011aed  lea     edx, [rcx+1]
0x140011af0  xorps   xmm0, xmm0
0x140011af3  add     rdx, r8; SourceString
0x140011af6  lea     rcx, [rbp+var_20]; DestinationString
0x140011afa  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x140011afe  call    cs:__imp_RtlInitAnsiString
0x140011b05  nop     dword ptr [rax+rax+00h]
0x140011b0a  movaps  xmm0, xmmword ptr [rbp+var_20.Length]
0x140011b0e  lea     rcx, [rbp+var_10]
0x140011b12  movdqa  [rbp+var_10], xmm0
0x140011b17  call    InitializeTelemetryAssertsKMWorkerInternal
0x140011b1c  mov     ebx, eax
0x140011b1e  lea     rcx, [rbp+AnsiString]; AnsiString
0x140011b22  call    cs:__imp_RtlFreeAnsiString
0x140011b29  nop     dword ptr [rax+rax+00h]
0x140011b2e  mov     eax, ebx
0x140011b30  mov     rbx, [rsp+60h+arg_0]
0x140011b35  add     rsp, 60h
0x140011b39  pop     rbp
0x140011b3a  retn
```
