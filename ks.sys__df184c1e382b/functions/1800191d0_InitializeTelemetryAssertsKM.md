# InitializeTelemetryAssertsKM

- ea: `0x1800191d0`
- end: `0x180019376`
- name: `InitializeTelemetryAssertsKM`
- size: `422`
- prototype: `__int64 __fastcall(const void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18007b090`

## callees

- `0x1800191d0`
- `0x18001937c`
- `0x180019d00`
- `0x18001a000`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18001925e`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001925e`
- `ntoskrnl!ExAllocatePool2` at `0x180019229`
- `ntoskrnl!ExAllocatePool2` at `0x180019229`
- `ntoskrnl!RtlInitAnsiString` at `0x18001920b`
- `ntoskrnl!RtlInitAnsiString` at `0x180019323`
- `ntoskrnl!RtlInitAnsiString` at `0x18001920b`
- `ntoskrnl!RtlInitAnsiString` at `0x180019323`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800192e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001935b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800192e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001935b`
- `ntoskrnl!RtlFreeAnsiString` at `0x180019347`
- `ntoskrnl!RtlFreeAnsiString` at `0x180019347`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1800192af`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1800192af`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x1800192d0`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x1800192d0`

## string_xrefs

- `0x180019279`: `ImagePath`

## pseudocode

```c
__int64 __fastcall InitializeTelemetryAssertsKM(const void **a1)
{
  NTSTATUS RegistryValues; // ebx
  void *Pool2; // rax
  void *v5; // rdi
  __int64 i; // rcx
  struct _STRING DestinationString; // [rsp+30h] [rbp-79h] BYREF
  UNICODE_STRING SourceString; // [rsp+40h] [rbp-69h] BYREF
  struct _STRING v9; // [rsp+50h] [rbp-59h] BYREF
  struct _STRING v10; // [rsp+60h] [rbp-49h] BYREF
  _QWORD v11[18]; // [rsp+70h] [rbp-39h] BYREF

  DestinationString = 0;
  if ( _InterlockedExchangeAdd(&g_AssertsOperational, 0) )
    return 0;
  RegistryValues = -1073741801;
  RtlInitAnsiString(&DestinationString, 0);
  Pool2 = (void *)ExAllocatePool2(64, *(unsigned __int16 *)a1 + 2LL, 1953657665);
  v5 = Pool2;
  if ( Pool2 )
  {
    memmove(Pool2, a1[1], *(unsigned __int16 *)a1);
    SourceString = 0;
    RtlInitUnicodeString(&SourceString, 0);
    memset(v11, 0, 0x70u);
    LODWORD(v11[1]) = 32;
    v11[2] = L"ImagePath";
    LODWORD(v11[4]) = 2;
    v11[3] = &SourceString;
    RegistryValues = RtlQueryRegistryValuesEx(0, v5, v11, 0, 0);
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
              v9 = 0;
              RtlInitAnsiString(&v9, &DestinationString.Buffer[(unsigned int)(i + 1)]);
              v10 = v9;
              RegistryValues = InitializeTelemetryAssertsKMWorkerInternal(&v10);
            }
            break;
          }
        }
        RtlFreeAnsiString(&DestinationString);
      }
    }
    ExFreePoolWithTag(v5, 0x74727341u);
  }
  return (unsigned int)RegistryValues;
}

```

## disassembly

```asm
0x1800191d0  push    rbp
0x1800191d2  push    rbx
0x1800191d3  push    rsi
0x1800191d4  push    rdi
0x1800191d5  lea     rbp, [rsp-3Fh]
0x1800191da  sub     rsp, 0E8h
0x1800191e1  xorps   xmm0, xmm0
0x1800191e4  mov     rsi, rcx
0x1800191e7  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800191eb  xor     eax, eax
0x1800191ed  lock xadd cs:g_AssertsOperational, eax
0x1800191f5  test    eax, eax
0x1800191f7  jz      short loc_180019200
0x1800191f9  xor     eax, eax
0x1800191fb  jmp     loc_180019369
0x180019200  xor     edx, edx; SourceString
0x180019202  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180019206  mov     ebx, 0C0000017h
0x18001920b  call    cs:__imp_RtlInitAnsiString
0x180019212  nop     dword ptr [rax+rax+00h]
0x180019217  movzx   edx, word ptr [rsi]
0x18001921a  mov     ecx, 40h ; '@'
0x18001921f  add     rdx, 2
0x180019223  mov     r8d, 74727341h
0x180019229  call    cs:__imp_ExAllocatePool2
0x180019230  nop     dword ptr [rax+rax+00h]
0x180019235  mov     rdi, rax
0x180019238  test    rax, rax
0x18001923b  jz      loc_180019367
0x180019241  movzx   r8d, word ptr [rsi]; Size
0x180019245  mov     rcx, rax; void *
0x180019248  mov     rdx, [rsi+8]; Src
0x18001924c  call    memmove
0x180019251  xorps   xmm0, xmm0
0x180019254  lea     rcx, [rbp+57h+SourceString]; DestinationString
0x180019258  xor     edx, edx; SourceString
0x18001925a  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm0
0x18001925e  call    cs:__imp_RtlInitUnicodeString
0x180019265  nop     dword ptr [rax+rax+00h]
0x18001926a  xor     edx, edx; Val
0x18001926c  lea     rcx, [rbp+57h+var_90]; void *
0x180019270  lea     r8d, [rdx+70h]; Size
0x180019274  call    memset
0x180019279  lea     rax, aImagepath; "ImagePath"
0x180019280  mov     [rbp+57h+var_88], 20h ; ' '
0x180019287  mov     [rbp+57h+var_80], rax
0x18001928b  lea     r8, [rbp+57h+var_90]
0x18001928f  lea     rax, [rbp+57h+SourceString]
0x180019293  mov     [rbp+57h+var_70], 2
0x18001929a  xor     r9d, r9d
0x18001929d  mov     [rbp+57h+var_78], rax
0x1800192a1  mov     rdx, rdi
0x1800192a4  mov     [rsp+100h+var_E0], 0
0x1800192ad  xor     ecx, ecx
0x1800192af  call    cs:__imp_RtlQueryRegistryValuesEx
0x1800192b6  nop     dword ptr [rax+rax+00h]
0x1800192bb  mov     ebx, eax
0x1800192bd  test    eax, eax
0x1800192bf  js      loc_180019353
0x1800192c5  mov     r8b, 1; AllocateDestinationString
0x1800192c8  lea     rdx, [rbp+57h+SourceString]; SourceString
0x1800192cc  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800192d0  call    cs:__imp_RtlUnicodeStringToAnsiString
0x1800192d7  nop     dword ptr [rax+rax+00h]
0x1800192dc  mov     rcx, [rbp+57h+SourceString.Buffer]; P
0x1800192e0  xor     edx, edx; Tag
0x1800192e2  mov     ebx, eax
0x1800192e4  call    cs:__imp_ExFreePoolWithTag
0x1800192eb  nop     dword ptr [rax+rax+00h]
0x1800192f0  test    ebx, ebx
0x1800192f2  js      short loc_180019353
0x1800192f4  movzx   edx, [rbp+57h+DestinationString.Length]
0x1800192f8  mov     r8, [rbp+57h+DestinationString.Buffer]
0x1800192fc  lea     ecx, [rdx-1]
0x1800192ff  test    ecx, ecx
0x180019301  jz      short loc_180019343
0x180019303  cmp     byte ptr [rcx+r8], 5Ch ; '\'
0x180019308  jz      short loc_18001930E
0x18001930a  dec     ecx
0x18001930c  jmp     short loc_1800192FF
0x18001930e  cmp     ecx, edx
0x180019310  jz      short loc_180019343
0x180019312  lea     edx, [rcx+1]
0x180019315  xorps   xmm0, xmm0
0x180019318  add     rdx, r8; SourceString
0x18001931b  lea     rcx, [rbp+57h+var_B0]; DestinationString
0x18001931f  movups  xmmword ptr [rbp+57h+var_B0.Length], xmm0
0x180019323  call    cs:__imp_RtlInitAnsiString
0x18001932a  nop     dword ptr [rax+rax+00h]
0x18001932f  movaps  xmm0, xmmword ptr [rbp+57h+var_B0.Length]
0x180019333  lea     rcx, [rbp+57h+var_A0]
0x180019337  movdqa  [rbp+57h+var_A0], xmm0
0x18001933c  call    InitializeTelemetryAssertsKMWorkerInternal
0x180019341  mov     ebx, eax
0x180019343  lea     rcx, [rbp+57h+DestinationString]; AnsiString
0x180019347  call    cs:__imp_RtlFreeAnsiString
0x18001934e  nop     dword ptr [rax+rax+00h]
0x180019353  mov     edx, 74727341h; Tag
0x180019358  mov     rcx, rdi; P
0x18001935b  call    cs:__imp_ExFreePoolWithTag
0x180019362  nop     dword ptr [rax+rax+00h]
0x180019367  mov     eax, ebx
0x180019369  add     rsp, 0E8h
0x180019370  pop     rdi
0x180019371  pop     rsi
0x180019372  pop     rbx
0x180019373  pop     rbp
0x180019374  retn
```
