# InitializeTelemetryAssertsKM

- ea: `0x180019180`
- end: `0x180019326`
- name: `InitializeTelemetryAssertsKM`
- size: `422`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18007b090`

## callees

- `0x180019180`
- `0x18001932c`
- `0x180019cc0`
- `0x180019fc0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18001920e`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001920e`
- `ntoskrnl!ExAllocatePool2` at `0x1800191d9`
- `ntoskrnl!ExAllocatePool2` at `0x1800191d9`
- `ntoskrnl!RtlInitAnsiString` at `0x1800191bb`
- `ntoskrnl!RtlInitAnsiString` at `0x1800192d3`
- `ntoskrnl!RtlInitAnsiString` at `0x1800191bb`
- `ntoskrnl!RtlInitAnsiString` at `0x1800192d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x180019294`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001930b`
- `ntoskrnl!ExFreePoolWithTag` at `0x180019294`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001930b`
- `ntoskrnl!RtlFreeAnsiString` at `0x1800192f7`
- `ntoskrnl!RtlFreeAnsiString` at `0x1800192f7`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x18001925f`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x18001925f`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x180019280`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x180019280`

## string_xrefs

- `0x180019229`: `ImagePath`

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
0x180019180  push    rbp
0x180019182  push    rbx
0x180019183  push    rsi
0x180019184  push    rdi
0x180019185  lea     rbp, [rsp-3Fh]
0x18001918a  sub     rsp, 0E8h
0x180019191  xorps   xmm0, xmm0
0x180019194  mov     rsi, rcx
0x180019197  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18001919b  xor     eax, eax
0x18001919d  lock xadd cs:g_AssertsOperational, eax
0x1800191a5  test    eax, eax
0x1800191a7  jz      short loc_1800191B0
0x1800191a9  xor     eax, eax
0x1800191ab  jmp     loc_180019319
0x1800191b0  xor     edx, edx; SourceString
0x1800191b2  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800191b6  mov     ebx, 0C0000017h
0x1800191bb  call    cs:__imp_RtlInitAnsiString
0x1800191c2  nop     dword ptr [rax+rax+00h]
0x1800191c7  movzx   edx, word ptr [rsi]
0x1800191ca  mov     ecx, 40h ; '@'
0x1800191cf  add     rdx, 2
0x1800191d3  mov     r8d, 74727341h
0x1800191d9  call    cs:__imp_ExAllocatePool2
0x1800191e0  nop     dword ptr [rax+rax+00h]
0x1800191e5  mov     rdi, rax
0x1800191e8  test    rax, rax
0x1800191eb  jz      loc_180019317
0x1800191f1  movzx   r8d, word ptr [rsi]; Size
0x1800191f5  mov     rcx, rax; void *
0x1800191f8  mov     rdx, [rsi+8]; Src
0x1800191fc  call    memmove
0x180019201  xorps   xmm0, xmm0
0x180019204  lea     rcx, [rbp+57h+SourceString]; DestinationString
0x180019208  xor     edx, edx; SourceString
0x18001920a  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm0
0x18001920e  call    cs:__imp_RtlInitUnicodeString
0x180019215  nop     dword ptr [rax+rax+00h]
0x18001921a  xor     edx, edx; Val
0x18001921c  lea     rcx, [rbp+57h+var_90]; void *
0x180019220  lea     r8d, [rdx+70h]; Size
0x180019224  call    memset
0x180019229  lea     rax, aImagepath; "ImagePath"
0x180019230  mov     [rbp+57h+var_88], 20h ; ' '
0x180019237  mov     [rbp+57h+var_80], rax
0x18001923b  lea     r8, [rbp+57h+var_90]
0x18001923f  lea     rax, [rbp+57h+SourceString]
0x180019243  mov     [rbp+57h+var_70], 2
0x18001924a  xor     r9d, r9d
0x18001924d  mov     [rbp+57h+var_78], rax
0x180019251  mov     rdx, rdi
0x180019254  mov     [rsp+100h+var_E0], 0
0x18001925d  xor     ecx, ecx
0x18001925f  call    cs:__imp_RtlQueryRegistryValuesEx
0x180019266  nop     dword ptr [rax+rax+00h]
0x18001926b  mov     ebx, eax
0x18001926d  test    eax, eax
0x18001926f  js      loc_180019303
0x180019275  mov     r8b, 1; AllocateDestinationString
0x180019278  lea     rdx, [rbp+57h+SourceString]; SourceString
0x18001927c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180019280  call    cs:__imp_RtlUnicodeStringToAnsiString
0x180019287  nop     dword ptr [rax+rax+00h]
0x18001928c  mov     rcx, [rbp+57h+SourceString.Buffer]; P
0x180019290  xor     edx, edx; Tag
0x180019292  mov     ebx, eax
0x180019294  call    cs:__imp_ExFreePoolWithTag
0x18001929b  nop     dword ptr [rax+rax+00h]
0x1800192a0  test    ebx, ebx
0x1800192a2  js      short loc_180019303
0x1800192a4  movzx   edx, [rbp+57h+DestinationString.Length]
0x1800192a8  mov     r8, [rbp+57h+DestinationString.Buffer]
0x1800192ac  lea     ecx, [rdx-1]
0x1800192af  test    ecx, ecx
0x1800192b1  jz      short loc_1800192F3
0x1800192b3  cmp     byte ptr [rcx+r8], 5Ch ; '\'
0x1800192b8  jz      short loc_1800192BE
0x1800192ba  dec     ecx
0x1800192bc  jmp     short loc_1800192AF
0x1800192be  cmp     ecx, edx
0x1800192c0  jz      short loc_1800192F3
0x1800192c2  lea     edx, [rcx+1]
0x1800192c5  xorps   xmm0, xmm0
0x1800192c8  add     rdx, r8; SourceString
0x1800192cb  lea     rcx, [rbp+57h+var_B0]; DestinationString
0x1800192cf  movups  xmmword ptr [rbp+57h+var_B0.Length], xmm0
0x1800192d3  call    cs:__imp_RtlInitAnsiString
0x1800192da  nop     dword ptr [rax+rax+00h]
0x1800192df  movaps  xmm0, xmmword ptr [rbp+57h+var_B0.Length]
0x1800192e3  lea     rcx, [rbp+57h+var_A0]
0x1800192e7  movdqa  [rbp+57h+var_A0], xmm0
0x1800192ec  call    InitializeTelemetryAssertsKMWorkerInternal
0x1800192f1  mov     ebx, eax
0x1800192f3  lea     rcx, [rbp+57h+DestinationString]; AnsiString
0x1800192f7  call    cs:__imp_RtlFreeAnsiString
0x1800192fe  nop     dword ptr [rax+rax+00h]
0x180019303  mov     edx, 74727341h; Tag
0x180019308  mov     rcx, rdi; P
0x18001930b  call    cs:__imp_ExFreePoolWithTag
0x180019312  nop     dword ptr [rax+rax+00h]
0x180019317  mov     eax, ebx
0x180019319  add     rsp, 0E8h
0x180019320  pop     rdi
0x180019321  pop     rsi
0x180019322  pop     rbx
0x180019323  pop     rbp
0x180019324  retn
```
