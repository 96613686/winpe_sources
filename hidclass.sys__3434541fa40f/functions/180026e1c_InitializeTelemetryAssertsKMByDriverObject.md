# InitializeTelemetryAssertsKMByDriverObject

- ea: `0x180026e1c`
- end: `0x180026f18`
- name: `InitializeTelemetryAssertsKMByDriverObject`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800385f0`

## callees

- `0x180026e1c`
- `0x180026f20`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180026e9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x180026e9b`
- `ntoskrnl!RtlInitUnicodeString` at `0x180026e55`
- `ntoskrnl!RtlInitUnicodeString` at `0x180026e55`
- `ntoskrnl!IoQueryFullDriverPath` at `0x180026e68`
- `ntoskrnl!IoQueryFullDriverPath` at `0x180026e68`
- `ntoskrnl!RtlFreeAnsiString` at `0x180026efe`
- `ntoskrnl!RtlFreeAnsiString` at `0x180026efe`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x180026e87`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x180026e87`
- `ntoskrnl!RtlInitAnsiString` at `0x180026eda`
- `ntoskrnl!RtlInitAnsiString` at `0x180026eda`

## pseudocode

```c
__int64 __fastcall InitializeTelemetryAssertsKMByDriverObject(__int64 a1)
{
  __int64 result; // rax
  NTSTATUS v3; // ebx
  __int64 i; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _STRING AnsiString; // [rsp+30h] [rbp-30h] BYREF
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
0x180026e1c  mov     [rsp-8+arg_0], rbx
0x180026e21  push    rbp
0x180026e22  mov     rbp, rsp
0x180026e25  sub     rsp, 60h
0x180026e29  xorps   xmm0, xmm0
0x180026e2c  xorps   xmm1, xmm1
0x180026e2f  movups  xmmword ptr [rbp+AnsiString.Length], xmm0
0x180026e33  mov     rbx, rcx
0x180026e36  xor     eax, eax
0x180026e38  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x180026e3c  lock xadd cs:g_AssertsOperational, eax
0x180026e44  test    eax, eax
0x180026e46  jz      short loc_180026E4F
0x180026e48  xor     eax, eax
0x180026e4a  jmp     loc_180026F0C
0x180026e4f  xor     edx, edx; SourceString
0x180026e51  lea     rcx, [rbp+DestinationString]; DestinationString
0x180026e55  call    cs:__imp_RtlInitUnicodeString
0x180026e5c  nop     dword ptr [rax+rax+00h]
0x180026e61  lea     rdx, [rbp+DestinationString]
0x180026e65  mov     rcx, rbx
0x180026e68  call    cs:__imp_IoQueryFullDriverPath
0x180026e6f  nop     dword ptr [rax+rax+00h]
0x180026e74  test    eax, eax
0x180026e76  js      loc_180026F0C
0x180026e7c  mov     r8b, 1; AllocateDestinationString
0x180026e7f  lea     rdx, [rbp+DestinationString]; SourceString
0x180026e83  lea     rcx, [rbp+AnsiString]; DestinationString
0x180026e87  call    cs:__imp_RtlUnicodeStringToAnsiString
0x180026e8e  nop     dword ptr [rax+rax+00h]
0x180026e93  mov     rcx, [rbp+DestinationString.Buffer]; P
0x180026e97  xor     edx, edx; Tag
0x180026e99  mov     ebx, eax
0x180026e9b  call    cs:__imp_ExFreePoolWithTag
0x180026ea2  nop     dword ptr [rax+rax+00h]
0x180026ea7  test    ebx, ebx
0x180026ea9  js      short loc_180026F0A
0x180026eab  movzx   edx, [rbp+AnsiString.Length]
0x180026eaf  mov     r8, [rbp+AnsiString.Buffer]
0x180026eb3  lea     ecx, [rdx-1]
0x180026eb6  test    ecx, ecx
0x180026eb8  jz      short loc_180026EFA
0x180026eba  cmp     byte ptr [rcx+r8], 5Ch ; '\'
0x180026ebf  jz      short loc_180026EC5
0x180026ec1  dec     ecx
0x180026ec3  jmp     short loc_180026EB6
0x180026ec5  cmp     ecx, edx
0x180026ec7  jz      short loc_180026EFA
0x180026ec9  lea     edx, [rcx+1]
0x180026ecc  xorps   xmm0, xmm0
0x180026ecf  add     rdx, r8; SourceString
0x180026ed2  lea     rcx, [rbp+var_20]; DestinationString
0x180026ed6  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x180026eda  call    cs:__imp_RtlInitAnsiString
0x180026ee1  nop     dword ptr [rax+rax+00h]
0x180026ee6  movaps  xmm0, xmmword ptr [rbp+var_20.Length]
0x180026eea  lea     rcx, [rbp+var_10]
0x180026eee  movdqa  [rbp+var_10], xmm0
0x180026ef3  call    InitializeTelemetryAssertsKMWorkerInternal
0x180026ef8  mov     ebx, eax
0x180026efa  lea     rcx, [rbp+AnsiString]; AnsiString
0x180026efe  call    cs:__imp_RtlFreeAnsiString
0x180026f05  nop     dword ptr [rax+rax+00h]
0x180026f0a  mov     eax, ebx
0x180026f0c  mov     rbx, [rsp+60h+arg_0]
0x180026f11  add     rsp, 60h
0x180026f15  pop     rbp
0x180026f16  retn
```
