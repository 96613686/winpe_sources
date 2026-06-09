# NfsReadRegistry

- ea: `0x140038550`
- end: `0x140038664`
- name: `NfsReadRegistry`
- size: `276`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, PCWSTR, __int64, int, _DWORD *, unsigned int)`
- caller_count: `9`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140022054`
- `0x14002246c`
- `0x140025484`
- `0x140025be0`
- `0x1400293c4`
- `0x14002d428`
- `0x14002dec4`
- `0x14002e8e4`
- `0x14002eb18`

## callees

- `0x1400147f0`
- `0x140038550`
- `0x14003abe0`
- `0x14003b0c0`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140038606`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140038606`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140038625`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400385f6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400385f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038647`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038647`

## string_xrefs

- `0x1400385b5`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
__int64 __fastcall NfsReadRegistry(
        PCUNICODE_STRING SourceString,
        PCWSTR a2,
        __int64 a3,
        int a4,
        _DWORD *a5,
        unsigned int a6)
{
  NTSTATUS RegistryPath; // ebx
  PWSTR Buffer; // rbx
  int v10; // eax
  PVOID SystemRoutineAddress; // rax
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-69h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-59h] BYREF
  _QWORD v15[18]; // [rsp+50h] [rbp-49h] BYREF

  *(_QWORD *)&Destination.Length = 0;
  Destination.Buffer = 0;
  RegistryPath = NfsGetRegistryPath(&Destination, SourceString, a2, a4, a5, a6);
  if ( RegistryPath >= 0 )
  {
    memset(v15, 0, 0x70u);
    Buffer = Destination.Buffer;
    v10 = 36;
    v15[2] = a3;
    v15[3] = a5;
    LODWORD(v15[4]) = 0;
    v15[5] = 0;
    LODWORD(v15[6]) = 0;
    if ( a4 == 7 )
      v10 = 52;
    LODWORD(v15[1]) = v10;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
    SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
    if ( !SystemRoutineAddress )
      SystemRoutineAddress = RtlQueryRegistryValues;
    RegistryPath = ((__int64 (__fastcall *)(_QWORD, PWSTR, _QWORD *, _QWORD, _QWORD))SystemRoutineAddress)(
                     0,
                     Buffer,
                     v15,
                     0,
                     0);
  }
  if ( Destination.Buffer )
    ExFreePoolWithTag(Destination.Buffer, 0x6373664Eu);
  return (unsigned int)RegistryPath;
}

```

## disassembly

```asm
0x140038550  push    rbp
0x140038552  push    rbx
0x140038553  push    rsi
0x140038554  push    rdi
0x140038555  push    r14
0x140038557  lea     rbp, [rsp-27h]
0x14003855c  sub     rsp, 0C0h
0x140038563  mov     eax, [rbp+47h+arg_28]
0x140038566  mov     r14, r8
0x140038569  mov     rsi, [rbp+47h+arg_20]
0x14003856d  mov     r8, rdx; PCWSTR
0x140038570  mov     rdx, rcx; SourceString
0x140038573  mov     [rsp+0E0h+var_B8], eax; int
0x140038577  lea     rcx, [rbp+47h+Destination]; Destination
0x14003857b  mov     qword ptr [rbp+47h+Destination.Length], 0
0x140038583  mov     edi, r9d
0x140038586  mov     [rbp+47h+Destination.Buffer], 0
0x14003858e  mov     [rsp+0E0h+var_C0], rsi; __int64
0x140038593  call    NfsGetRegistryPath
0x140038598  mov     ebx, eax
0x14003859a  test    eax, eax
0x14003859c  js      loc_140038639
0x1400385a2  xor     edx, edx; Val
0x1400385a4  lea     rcx, [rbp+47h+var_90]; void *
0x1400385a8  lea     r8d, [rdx+70h]; Size
0x1400385ac  call    memset
0x1400385b1  mov     rbx, [rbp+47h+Destination.Buffer]
0x1400385b5  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x1400385bc  mov     eax, 24h ; '$'
0x1400385c1  mov     [rbp+47h+var_80], r14
0x1400385c5  xorps   xmm0, xmm0
0x1400385c8  mov     [rbp+47h+var_78], rsi
0x1400385cc  cmp     edi, 7
0x1400385cf  mov     [rbp+47h+var_70], 0
0x1400385d6  mov     [rbp+47h+var_68], 0
0x1400385de  lea     ecx, [rax+10h]
0x1400385e1  mov     [rbp+47h+var_60], 0
0x1400385e8  cmovz   eax, ecx
0x1400385eb  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x1400385ef  mov     [rbp+47h+var_88], eax
0x1400385f2  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x1400385f6  call    cs:__imp_RtlInitUnicodeString
0x1400385fd  nop     dword ptr [rax+rax+00h]
0x140038602  lea     rcx, [rbp+47h+DestinationString]; SystemRoutineName
0x140038606  call    cs:__imp_MmGetSystemRoutineAddress
0x14003860d  nop     dword ptr [rax+rax+00h]
0x140038612  lea     r8, [rbp+47h+var_90]
0x140038616  mov     [rsp+0E0h+var_C0], 0
0x14003861f  test    rax, rax
0x140038622  mov     rdx, rbx
0x140038625  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14003862d  xor     r9d, r9d
0x140038630  xor     ecx, ecx
0x140038632  call    _guard_dispatch_icall
0x140038637  mov     ebx, eax
0x140038639  mov     rcx, [rbp+47h+Destination.Buffer]; P
0x14003863d  test    rcx, rcx
0x140038640  jz      short loc_140038653
0x140038642  mov     edx, 6373664Eh; Tag
0x140038647  call    cs:__imp_ExFreePoolWithTag
0x14003864e  nop     dword ptr [rax+rax+00h]
0x140038653  mov     eax, ebx
0x140038655  add     rsp, 0C0h
0x14003865c  pop     r14
0x14003865e  pop     rdi
0x14003865f  pop     rsi
0x140038660  pop     rbx
0x140038661  pop     rbp
0x140038662  retn
```
