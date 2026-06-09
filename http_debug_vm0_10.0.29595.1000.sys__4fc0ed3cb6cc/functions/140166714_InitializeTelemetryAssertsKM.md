# InitializeTelemetryAssertsKM

- ea: `0x140166714`
- end: `0x1401668d1`
- name: `InitializeTelemetryAssertsKM`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1401562e0`

## callees

- `0x140166714`
- `0x1401668d8`
- `0x140167940`
- `0x140167c40`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1401667b0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401667b0`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140166822`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140166822`
- `ntoskrnl!ExAllocatePool2` at `0x140166774`
- `ntoskrnl!ExAllocatePool2` at `0x140166774`
- `ntoskrnl!ExFreePoolWithTag` at `0x140166836`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401668ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140166836`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401668ad`
- `ntoskrnl!RtlFreeAnsiString` at `0x140166899`
- `ntoskrnl!RtlFreeAnsiString` at `0x140166899`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140166801`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140166801`
- `ntoskrnl!RtlInitAnsiString` at `0x140166752`
- `ntoskrnl!RtlInitAnsiString` at `0x140166875`
- `ntoskrnl!RtlInitAnsiString` at `0x140166752`
- `ntoskrnl!RtlInitAnsiString` at `0x140166875`

## string_xrefs

- `0x1401667cb`: `ImagePath`

## pseudocode

```c
__int64 InitializeTelemetryAssertsKM()
{
  NTSTATUS RegistryValues; // ebx
  void *Pool2; // rax
  void *v3; // rdi
  __int64 i; // rcx
  struct _STRING DestinationString; // [rsp+30h] [rbp-59h] BYREF
  UNICODE_STRING SourceString; // [rsp+40h] [rbp-49h] BYREF
  struct _STRING v7; // [rsp+50h] [rbp-39h] BYREF
  struct _STRING v8; // [rsp+60h] [rbp-29h] BYREF
  _QWORD v9[14]; // [rsp+70h] [rbp-19h] BYREF

  DestinationString = 0;
  if ( _InterlockedExchangeAdd(&g_AssertsOperational, 0) )
    return 0;
  RegistryValues = -1073741801;
  RtlInitAnsiString(&DestinationString, 0);
  Pool2 = (void *)ExAllocatePool2(64, UxHttpRegistryPath.Length + 2LL, 1953657665);
  v3 = Pool2;
  if ( Pool2 )
  {
    memmove(Pool2, UxHttpRegistryPath.Buffer, UxHttpRegistryPath.Length);
    SourceString = 0;
    RtlInitUnicodeString(&SourceString, 0);
    memset(v9, 0, sizeof(v9));
    LODWORD(v9[1]) = 32;
    v9[2] = L"ImagePath";
    LODWORD(v9[4]) = 2;
    v9[3] = &SourceString;
    RegistryValues = RtlQueryRegistryValuesEx(0, v3, v9, 0, 0);
    if ( RegistryValues >= 0 )
    {
      RegistryValues = RtlUnicodeStringToAnsiString(&DestinationString, &SourceString, 1u);
      ExFreePoolWithTag(SourceString.Buffer, 0);
      if ( RegistryValues >= 0 )
      {
        for ( i = (unsigned int)DestinationString.Length - 1; (_DWORD)i; i = (unsigned int)(i - 1) )
        {
          if ( DestinationString.Buffer[i] == 92 )
          {
            if ( (_DWORD)i != DestinationString.Length )
            {
              v7 = 0;
              RtlInitAnsiString(&v7, &DestinationString.Buffer[(unsigned int)(i + 1)]);
              v8 = v7;
              RegistryValues = InitializeTelemetryAssertsKMWorkerInternal(&v8);
            }
            break;
          }
        }
        RtlFreeAnsiString(&DestinationString);
      }
    }
    ExFreePoolWithTag(v3, 0x74727341u);
  }
  return (unsigned int)RegistryValues;
}

```

## disassembly

```asm
0x140166714  mov     [rsp-8+arg_0], rbx
0x140166719  mov     [rsp-8+arg_8], rdi
0x14016671e  push    rbp
0x14016671f  lea     rbp, [rsp-57h]
0x140166724  sub     rsp, 0E0h
0x14016672b  xorps   xmm0, xmm0
0x14016672e  xor     eax, eax
0x140166730  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140166734  lock xadd cs:g_AssertsOperational, eax
0x14016673c  test    eax, eax
0x14016673e  jz      short loc_140166747
0x140166740  xor     eax, eax
0x140166742  jmp     loc_1401668BB
0x140166747  xor     edx, edx; SourceString
0x140166749  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14016674d  mov     ebx, 0C0000017h
0x140166752  call    cs:__imp_RtlInitAnsiString
0x140166759  nop     dword ptr [rax+rax+00h]
0x14016675e  movzx   edx, cs:UxHttpRegistryPath.Length
0x140166765  mov     ecx, 40h ; '@'
0x14016676a  add     rdx, 2
0x14016676e  mov     r8d, 74727341h
0x140166774  call    cs:__imp_ExAllocatePool2
0x14016677b  nop     dword ptr [rax+rax+00h]
0x140166780  mov     rdi, rax
0x140166783  test    rax, rax
0x140166786  jz      loc_1401668B9
0x14016678c  movzx   r8d, cs:UxHttpRegistryPath.Length; Size
0x140166794  mov     rcx, rax; void *
0x140166797  mov     rdx, cs:UxHttpRegistryPath.Buffer; Src
0x14016679e  call    memmove
0x1401667a3  xorps   xmm0, xmm0
0x1401667a6  lea     rcx, [rbp+57h+SourceString]; DestinationString
0x1401667aa  xor     edx, edx; SourceString
0x1401667ac  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm0
0x1401667b0  call    cs:__imp_RtlInitUnicodeString
0x1401667b7  nop     dword ptr [rax+rax+00h]
0x1401667bc  xor     edx, edx; Val
0x1401667be  lea     rcx, [rbp+57h+var_70]; void *
0x1401667c2  lea     r8d, [rdx+70h]; Size
0x1401667c6  call    memset
0x1401667cb  lea     rax, aImagepath; "ImagePath"
0x1401667d2  mov     [rbp+57h+var_68], 20h ; ' '
0x1401667d9  mov     [rbp+57h+var_60], rax
0x1401667dd  lea     r8, [rbp+57h+var_70]
0x1401667e1  lea     rax, [rbp+57h+SourceString]
0x1401667e5  mov     [rbp+57h+var_50], 2
0x1401667ec  xor     r9d, r9d
0x1401667ef  mov     [rbp+57h+var_58], rax
0x1401667f3  mov     rdx, rdi
0x1401667f6  mov     [rsp+0E0h+var_C0], 0
0x1401667ff  xor     ecx, ecx
0x140166801  call    cs:__imp_RtlQueryRegistryValuesEx
0x140166808  nop     dword ptr [rax+rax+00h]
0x14016680d  mov     ebx, eax
0x14016680f  test    eax, eax
0x140166811  js      loc_1401668A5
0x140166817  mov     r8b, 1; AllocateDestinationString
0x14016681a  lea     rdx, [rbp+57h+SourceString]; SourceString
0x14016681e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140166822  call    cs:__imp_RtlUnicodeStringToAnsiString
0x140166829  nop     dword ptr [rax+rax+00h]
0x14016682e  mov     rcx, [rbp+57h+SourceString.Buffer]; P
0x140166832  xor     edx, edx; Tag
0x140166834  mov     ebx, eax
0x140166836  call    cs:__imp_ExFreePoolWithTag
0x14016683d  nop     dword ptr [rax+rax+00h]
0x140166842  test    ebx, ebx
0x140166844  js      short loc_1401668A5
0x140166846  movzx   edx, [rbp+57h+DestinationString.Length]
0x14016684a  mov     r8, [rbp+57h+DestinationString.Buffer]
0x14016684e  lea     ecx, [rdx-1]
0x140166851  test    ecx, ecx
0x140166853  jz      short loc_140166895
0x140166855  cmp     byte ptr [rcx+r8], 5Ch ; '\'
0x14016685a  jz      short loc_140166860
0x14016685c  dec     ecx
0x14016685e  jmp     short loc_140166851
0x140166860  cmp     ecx, edx
0x140166862  jz      short loc_140166895
0x140166864  lea     edx, [rcx+1]
0x140166867  xorps   xmm0, xmm0
0x14016686a  add     rdx, r8; SourceString
0x14016686d  lea     rcx, [rbp+57h+var_90]; DestinationString
0x140166871  movups  xmmword ptr [rbp+57h+var_90.Length], xmm0
0x140166875  call    cs:__imp_RtlInitAnsiString
0x14016687c  nop     dword ptr [rax+rax+00h]
0x140166881  movaps  xmm0, xmmword ptr [rbp+57h+var_90.Length]
0x140166885  lea     rcx, [rbp+57h+var_80]
0x140166889  movdqa  [rbp+57h+var_80], xmm0
0x14016688e  call    InitializeTelemetryAssertsKMWorkerInternal
0x140166893  mov     ebx, eax
0x140166895  lea     rcx, [rbp+57h+DestinationString]; AnsiString
0x140166899  call    cs:__imp_RtlFreeAnsiString
0x1401668a0  nop     dword ptr [rax+rax+00h]
0x1401668a5  mov     edx, 74727341h; Tag
0x1401668aa  mov     rcx, rdi; P
0x1401668ad  call    cs:__imp_ExFreePoolWithTag
0x1401668b4  nop     dword ptr [rax+rax+00h]
0x1401668b9  mov     eax, ebx
0x1401668bb  lea     r11, [rsp+0E0h+var_s0]
0x1401668c3  mov     rbx, [r11+10h]
0x1401668c7  mov     rdi, [r11+18h]
0x1401668cb  mov     rsp, r11
0x1401668ce  pop     rbp
0x1401668cf  retn
```
