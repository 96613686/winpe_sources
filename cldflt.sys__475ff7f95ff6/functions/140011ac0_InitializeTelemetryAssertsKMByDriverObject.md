# InitializeTelemetryAssertsKMByDriverObject

- ea: `0x140011ac0`
- end: `0x140011bbc`
- name: `InitializeTelemetryAssertsKMByDriverObject`
- size: `252`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140087490`

## callees

- `0x140011ac0`
- `0x140011bc4`

## import_xrefs

- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140011b2b`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140011b2b`
- `ntoskrnl!RtlFreeAnsiString` at `0x140011ba2`
- `ntoskrnl!RtlFreeAnsiString` at `0x140011ba2`
- `ntoskrnl!IoQueryFullDriverPath` at `0x140011b0c`
- `ntoskrnl!IoQueryFullDriverPath` at `0x140011b0c`
- `ntoskrnl!RtlInitAnsiString` at `0x140011b7e`
- `ntoskrnl!RtlInitAnsiString` at `0x140011b7e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140011af9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140011af9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011b3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011b3f`

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
0x140011ac0  mov     [rsp-8+arg_0], rbx
0x140011ac5  push    rbp
0x140011ac6  mov     rbp, rsp
0x140011ac9  sub     rsp, 60h
0x140011acd  xorps   xmm0, xmm0
0x140011ad0  xorps   xmm1, xmm1
0x140011ad3  movups  xmmword ptr [rbp+AnsiString.Length], xmm0
0x140011ad7  mov     rbx, rcx
0x140011ada  xor     eax, eax
0x140011adc  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x140011ae0  lock xadd cs:g_AssertsOperational, eax
0x140011ae8  test    eax, eax
0x140011aea  jz      short loc_140011AF3
0x140011aec  xor     eax, eax
0x140011aee  jmp     loc_140011BB0
0x140011af3  xor     edx, edx; SourceString
0x140011af5  lea     rcx, [rbp+DestinationString]; DestinationString
0x140011af9  call    cs:__imp_RtlInitUnicodeString
0x140011b00  nop     dword ptr [rax+rax+00h]
0x140011b05  lea     rdx, [rbp+DestinationString]
0x140011b09  mov     rcx, rbx
0x140011b0c  call    cs:__imp_IoQueryFullDriverPath
0x140011b13  nop     dword ptr [rax+rax+00h]
0x140011b18  test    eax, eax
0x140011b1a  js      loc_140011BB0
0x140011b20  mov     r8b, 1; AllocateDestinationString
0x140011b23  lea     rdx, [rbp+DestinationString]; SourceString
0x140011b27  lea     rcx, [rbp+AnsiString]; DestinationString
0x140011b2b  call    cs:__imp_RtlUnicodeStringToAnsiString
0x140011b32  nop     dword ptr [rax+rax+00h]
0x140011b37  mov     rcx, [rbp+DestinationString.Buffer]; P
0x140011b3b  xor     edx, edx; Tag
0x140011b3d  mov     ebx, eax
0x140011b3f  call    cs:__imp_ExFreePoolWithTag
0x140011b46  nop     dword ptr [rax+rax+00h]
0x140011b4b  test    ebx, ebx
0x140011b4d  js      short loc_140011BAE
0x140011b4f  movzx   edx, [rbp+AnsiString.Length]
0x140011b53  mov     r8, [rbp+AnsiString.Buffer]
0x140011b57  lea     ecx, [rdx-1]
0x140011b5a  test    ecx, ecx
0x140011b5c  jz      short loc_140011B9E
0x140011b5e  cmp     byte ptr [rcx+r8], 5Ch ; '\'
0x140011b63  jz      short loc_140011B69
0x140011b65  dec     ecx
0x140011b67  jmp     short loc_140011B5A
0x140011b69  cmp     ecx, edx
0x140011b6b  jz      short loc_140011B9E
0x140011b6d  lea     edx, [rcx+1]
0x140011b70  xorps   xmm0, xmm0
0x140011b73  add     rdx, r8; SourceString
0x140011b76  lea     rcx, [rbp+var_20]; DestinationString
0x140011b7a  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x140011b7e  call    cs:__imp_RtlInitAnsiString
0x140011b85  nop     dword ptr [rax+rax+00h]
0x140011b8a  movaps  xmm0, xmmword ptr [rbp+var_20.Length]
0x140011b8e  lea     rcx, [rbp+var_10]
0x140011b92  movdqa  [rbp+var_10], xmm0
0x140011b97  call    InitializeTelemetryAssertsKMWorkerInternal
0x140011b9c  mov     ebx, eax
0x140011b9e  lea     rcx, [rbp+AnsiString]; AnsiString
0x140011ba2  call    cs:__imp_RtlFreeAnsiString
0x140011ba9  nop     dword ptr [rax+rax+00h]
0x140011bae  mov     eax, ebx
0x140011bb0  mov     rbx, [rsp+60h+arg_0]
0x140011bb5  add     rsp, 60h
0x140011bb9  pop     rbp
0x140011bba  retn
```
