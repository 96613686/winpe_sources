# InitializeTelemetryAssertsKM

- ea: `0x140166604`
- end: `0x1401667c1`
- name: `InitializeTelemetryAssertsKM`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1401561d0`

## callees

- `0x140166604`
- `0x1401667c8`
- `0x140167840`
- `0x140167b40`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1401666a0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401666a0`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140166712`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140166712`
- `ntoskrnl!ExAllocatePool2` at `0x140166664`
- `ntoskrnl!ExAllocatePool2` at `0x140166664`
- `ntoskrnl!ExFreePoolWithTag` at `0x140166726`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016679d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140166726`
- `ntoskrnl!ExFreePoolWithTag` at `0x14016679d`
- `ntoskrnl!RtlFreeAnsiString` at `0x140166789`
- `ntoskrnl!RtlFreeAnsiString` at `0x140166789`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1401666f1`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1401666f1`
- `ntoskrnl!RtlInitAnsiString` at `0x140166642`
- `ntoskrnl!RtlInitAnsiString` at `0x140166765`
- `ntoskrnl!RtlInitAnsiString` at `0x140166642`
- `ntoskrnl!RtlInitAnsiString` at `0x140166765`

## string_xrefs

- `0x1401666bb`: `ImagePath`

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
0x140166604  mov     [rsp-8+arg_0], rbx
0x140166609  mov     [rsp-8+arg_8], rdi
0x14016660e  push    rbp
0x14016660f  lea     rbp, [rsp-57h]
0x140166614  sub     rsp, 0E0h
0x14016661b  xorps   xmm0, xmm0
0x14016661e  xor     eax, eax
0x140166620  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140166624  lock xadd cs:g_AssertsOperational, eax
0x14016662c  test    eax, eax
0x14016662e  jz      short loc_140166637
0x140166630  xor     eax, eax
0x140166632  jmp     loc_1401667AB
0x140166637  xor     edx, edx; SourceString
0x140166639  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14016663d  mov     ebx, 0C0000017h
0x140166642  call    cs:__imp_RtlInitAnsiString
0x140166649  nop     dword ptr [rax+rax+00h]
0x14016664e  movzx   edx, cs:UxHttpRegistryPath.Length
0x140166655  mov     ecx, 40h ; '@'
0x14016665a  add     rdx, 2
0x14016665e  mov     r8d, 74727341h
0x140166664  call    cs:__imp_ExAllocatePool2
0x14016666b  nop     dword ptr [rax+rax+00h]
0x140166670  mov     rdi, rax
0x140166673  test    rax, rax
0x140166676  jz      loc_1401667A9
0x14016667c  movzx   r8d, cs:UxHttpRegistryPath.Length; Size
0x140166684  mov     rcx, rax; void *
0x140166687  mov     rdx, cs:UxHttpRegistryPath.Buffer; Src
0x14016668e  call    memmove
0x140166693  xorps   xmm0, xmm0
0x140166696  lea     rcx, [rbp+57h+SourceString]; DestinationString
0x14016669a  xor     edx, edx; SourceString
0x14016669c  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm0
0x1401666a0  call    cs:__imp_RtlInitUnicodeString
0x1401666a7  nop     dword ptr [rax+rax+00h]
0x1401666ac  xor     edx, edx; Val
0x1401666ae  lea     rcx, [rbp+57h+var_70]; void *
0x1401666b2  lea     r8d, [rdx+70h]; Size
0x1401666b6  call    memset
0x1401666bb  lea     rax, aImagepath; "ImagePath"
0x1401666c2  mov     [rbp+57h+var_68], 20h ; ' '
0x1401666c9  mov     [rbp+57h+var_60], rax
0x1401666cd  lea     r8, [rbp+57h+var_70]
0x1401666d1  lea     rax, [rbp+57h+SourceString]
0x1401666d5  mov     [rbp+57h+var_50], 2
0x1401666dc  xor     r9d, r9d
0x1401666df  mov     [rbp+57h+var_58], rax
0x1401666e3  mov     rdx, rdi
0x1401666e6  mov     [rsp+0E0h+var_C0], 0
0x1401666ef  xor     ecx, ecx
0x1401666f1  call    cs:__imp_RtlQueryRegistryValuesEx
0x1401666f8  nop     dword ptr [rax+rax+00h]
0x1401666fd  mov     ebx, eax
0x1401666ff  test    eax, eax
0x140166701  js      loc_140166795
0x140166707  mov     r8b, 1; AllocateDestinationString
0x14016670a  lea     rdx, [rbp+57h+SourceString]; SourceString
0x14016670e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140166712  call    cs:__imp_RtlUnicodeStringToAnsiString
0x140166719  nop     dword ptr [rax+rax+00h]
0x14016671e  mov     rcx, [rbp+57h+SourceString.Buffer]; P
0x140166722  xor     edx, edx; Tag
0x140166724  mov     ebx, eax
0x140166726  call    cs:__imp_ExFreePoolWithTag
0x14016672d  nop     dword ptr [rax+rax+00h]
0x140166732  test    ebx, ebx
0x140166734  js      short loc_140166795
0x140166736  movzx   edx, [rbp+57h+DestinationString.Length]
0x14016673a  mov     r8, [rbp+57h+DestinationString.Buffer]
0x14016673e  lea     ecx, [rdx-1]
0x140166741  test    ecx, ecx
0x140166743  jz      short loc_140166785
0x140166745  cmp     byte ptr [rcx+r8], 5Ch ; '\'
0x14016674a  jz      short loc_140166750
0x14016674c  dec     ecx
0x14016674e  jmp     short loc_140166741
0x140166750  cmp     ecx, edx
0x140166752  jz      short loc_140166785
0x140166754  lea     edx, [rcx+1]
0x140166757  xorps   xmm0, xmm0
0x14016675a  add     rdx, r8; SourceString
0x14016675d  lea     rcx, [rbp+57h+var_90]; DestinationString
0x140166761  movups  xmmword ptr [rbp+57h+var_90.Length], xmm0
0x140166765  call    cs:__imp_RtlInitAnsiString
0x14016676c  nop     dword ptr [rax+rax+00h]
0x140166771  movaps  xmm0, xmmword ptr [rbp+57h+var_90.Length]
0x140166775  lea     rcx, [rbp+57h+var_80]
0x140166779  movdqa  [rbp+57h+var_80], xmm0
0x14016677e  call    InitializeTelemetryAssertsKMWorkerInternal
0x140166783  mov     ebx, eax
0x140166785  lea     rcx, [rbp+57h+DestinationString]; AnsiString
0x140166789  call    cs:__imp_RtlFreeAnsiString
0x140166790  nop     dword ptr [rax+rax+00h]
0x140166795  mov     edx, 74727341h; Tag
0x14016679a  mov     rcx, rdi; P
0x14016679d  call    cs:__imp_ExFreePoolWithTag
0x1401667a4  nop     dword ptr [rax+rax+00h]
0x1401667a9  mov     eax, ebx
0x1401667ab  lea     r11, [rsp+0E0h+var_s0]
0x1401667b3  mov     rbx, [r11+10h]
0x1401667b7  mov     rdi, [r11+18h]
0x1401667bb  mov     rsp, r11
0x1401667be  pop     rbp
0x1401667bf  retn
```
