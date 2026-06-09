# UlQueryConsumerProcessInfo

- ea: `0x140013030`
- end: `0x1400131bb`
- name: `UlQueryConsumerProcessInfo`
- size: `395`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140011560`
- `0x140013d90`
- `0x140014040`
- `0x1400147f0`
- `0x140015054`
- `0x1400ebb8c`

## callees

- `0x140013030`
- `0x140167810`
- `0x140167c40`
- `0x1401c3008`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!PsGetProcessActiveThreadCount` at `0x14001315e`
- `ntoskrnl!PsGetProcessActiveThreadCount` at `0x14001315e`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140013103`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140013103`
- `ntoskrnl!PsGetThreadId` at `0x1400130d1`
- `ntoskrnl!PsGetThreadId` at `0x140013122`
- `ntoskrnl!PsGetThreadId` at `0x1400130d1`
- `ntoskrnl!PsGetThreadId` at `0x140013122`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14001314a`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14001314a`
- `ntoskrnl!PsGetProcessId` at `0x1400130b8`
- `ntoskrnl!PsGetProcessId` at `0x140013136`
- `ntoskrnl!PsGetProcessId` at `0x1400130b8`
- `ntoskrnl!PsGetProcessId` at `0x140013136`

## pseudocode

```c
__int64 __fastcall UlQueryConsumerProcessInfo(__int64 a1, __int64 a2)
{
  NTSTATUS InformationProcess; // esi
  struct _KPROCESS *v5; // rcx
  ULONG ReturnLength[4]; // [rsp+30h] [rbp-88h] BYREF
  _QWORD ProcessInformation[12]; // [rsp+40h] [rbp-78h] BYREF

  InformationProcess = 0;
  memset(ProcessInformation, 0, 0x58u);
  ReturnLength[0] = 0;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qq(1032, 243, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids, a1, a2);
  if ( !*(_BYTE *)(a2 + 92) )
  {
    if ( a1 )
    {
      InformationProcess = ZwQueryInformationProcess(
                             *(HANDLE *)(a1 + 80),
                             ProcessVmCounters,
                             ProcessInformation,
                             0x58u,
                             ReturnLength);
      if ( InformationProcess < 0 )
        goto LABEL_9;
      *(_QWORD *)(a2 + 80) = ProcessInformation[4];
      *(_QWORD *)(a2 + 64) = PsGetThreadId(*(PETHREAD *)(a1 + 88));
      *(_QWORD *)(a2 + 56) = PsGetProcessId(*(PEPROCESS *)(a1 + 72));
      *(_QWORD *)(a2 + 72) = PsGetProcessImageFileName(*(_QWORD *)(a1 + 72));
      *(_DWORD *)(a2 + 88) = PsGetProcessActiveThreadCount(*(_QWORD *)(a1 + 72));
    }
    else
    {
      v5 = UxSystemProcess;
      *(_QWORD *)(a2 + 72) = "SYSTEM";
      *(_QWORD *)(a2 + 56) = PsGetProcessId(v5);
      *(_QWORD *)(a2 + 64) = PsGetThreadId(KeGetCurrentThread());
    }
    *(_BYTE *)(a2 + 92) = 1;
  }
LABEL_9:
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_d(1032, 244, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids, (unsigned int)InformationProcess);
  return (unsigned int)InformationProcess;
}

```

## disassembly

```asm
0x140013030  mov     [rsp+arg_10], rbx
0x140013035  mov     [rsp+arg_18], rsi
0x14001303a  push    rdi
0x14001303b  sub     rsp, 0B0h
0x140013042  mov     rax, cs:__security_cookie
0x140013049  xor     rax, rsp
0x14001304c  mov     [rsp+0B8h+var_18], rax
0x140013054  xor     esi, esi
0x140013056  mov     rbx, rdx
0x140013059  mov     rdi, rcx
0x14001305c  xor     edx, edx; Val
0x14001305e  lea     rcx, [rsp+0B8h+ProcessInformation]; void *
0x140013063  lea     r8d, [rsi+58h]; Size
0x140013067  call    memset
0x14001306c  mov     [rsp+0B8h+var_88], esi
0x140013070  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140013077  jz      short loc_140013097
0x140013079  mov     edx, 0F3h
0x14001307e  mov     [rsp+0B8h+ReturnLength], rbx
0x140013083  mov     ecx, 408h
0x140013088  lea     r8, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids
0x14001308f  mov     r9, rdi
0x140013092  call    WPP_SF_qq
0x140013097  cmp     [rbx+5Ch], sil
0x14001309b  jnz     loc_140013171
0x1400130a1  test    rdi, rdi
0x1400130a4  jnz     short loc_1400130E6
0x1400130a6  mov     rcx, cs:UxSystemProcess; Process
0x1400130ad  lea     rax, aSystem_0; "SYSTEM"
0x1400130b4  mov     [rbx+48h], rax
0x1400130b8  call    cs:__imp_PsGetProcessId
0x1400130bf  nop     dword ptr [rax+rax+00h]
0x1400130c4  mov     [rbx+38h], rax
0x1400130c8  mov     rcx, gs:188h; Thread
0x1400130d1  call    cs:__imp_PsGetThreadId
0x1400130d8  nop     dword ptr [rax+rax+00h]
0x1400130dd  mov     [rbx+40h], rax
0x1400130e1  jmp     loc_14001316D
0x1400130e6  mov     rcx, [rdi+50h]; ProcessHandle
0x1400130ea  lea     rax, [rsp+0B8h+var_88]
0x1400130ef  mov     r9d, 58h ; 'X'; ProcessInformationLength
0x1400130f5  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x1400130fa  lea     r8, [rsp+0B8h+ProcessInformation]; ProcessInformation
0x1400130ff  lea     edx, [r9-55h]; ProcessInformationClass
0x140013103  call    cs:__imp_ZwQueryInformationProcess
0x14001310a  nop     dword ptr [rax+rax+00h]
0x14001310f  mov     esi, eax
0x140013111  test    eax, eax
0x140013113  js      short loc_140013171
0x140013115  mov     rcx, [rsp+0B8h+var_58]
0x14001311a  mov     [rbx+50h], rcx
0x14001311e  mov     rcx, [rdi+58h]; Thread
0x140013122  call    cs:__imp_PsGetThreadId
0x140013129  nop     dword ptr [rax+rax+00h]
0x14001312e  mov     [rbx+40h], rax
0x140013132  mov     rcx, [rdi+48h]; Process
0x140013136  call    cs:__imp_PsGetProcessId
0x14001313d  nop     dword ptr [rax+rax+00h]
0x140013142  mov     [rbx+38h], rax
0x140013146  mov     rcx, [rdi+48h]
0x14001314a  call    cs:__imp_PsGetProcessImageFileName
0x140013151  nop     dword ptr [rax+rax+00h]
0x140013156  mov     [rbx+48h], rax
0x14001315a  mov     rcx, [rdi+48h]
0x14001315e  call    cs:__imp_PsGetProcessActiveThreadCount
0x140013165  nop     dword ptr [rax+rax+00h]
0x14001316a  mov     [rbx+58h], eax
0x14001316d  mov     byte ptr [rbx+5Ch], 1
0x140013171  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140013178  jz      short loc_140013193
0x14001317a  mov     edx, 0F4h
0x14001317f  lea     r8, WPP_641cb11b863d33fe415835eff38f0fa1_Traceguids
0x140013186  mov     ecx, 408h
0x14001318b  mov     r9d, esi
0x14001318e  call    WPP_SF_d
0x140013193  mov     eax, esi
0x140013195  mov     rcx, [rsp+0B8h+var_18]
0x14001319d  xor     rcx, rsp; StackCookie
0x1400131a0  call    __security_check_cookie
0x1400131a5  lea     r11, [rsp+0B8h+var_8]
0x1400131ad  mov     rbx, [r11+20h]
0x1400131b1  mov     rsi, [r11+28h]
0x1400131b5  mov     rsp, r11
0x1400131b8  pop     rdi
0x1400131b9  retn
```
