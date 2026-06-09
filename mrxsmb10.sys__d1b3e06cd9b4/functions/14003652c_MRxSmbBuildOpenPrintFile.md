# MRxSmbBuildOpenPrintFile

- ea: `0x14003652c`
- end: `0x1400366b3`
- name: `MRxSmbBuildOpenPrintFile`
- size: `391`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140047fb0`

## callees

- `0x14000dfa8`
- `0x140016560`
- `0x14003652c`
- `0x140046380`
- `0x14004a590`
- `0x1400515f0`

## import_xrefs

- `ntoskrnl!IoGetRequestorProcessId` at `0x140036649`
- `ntoskrnl!IoGetRequestorProcessId` at `0x140036649`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400365fc`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400365fc`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140036612`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140036612`

## pseudocode

```c
__int64 __fastcall MRxSmbBuildOpenPrintFile(_QWORD *a1)
{
  __int64 v1; // r14
  __int64 v3; // rax
  __int64 v4; // rdx
  unsigned int started; // esi
  __int64 v6; // rbx
  ULONG RequestorProcessId; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v10[2]; // [rsp+70h] [rbp-90h] BYREF
  char *v11; // [rsp+78h] [rbp-88h]
  char v12; // [rsp+80h] [rbp-80h] BYREF
  char v13; // [rsp+290h] [rbp+190h] BYREF

  v1 = a1[6];
  DestinationString = 0;
  v10[1] = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
  *(_DWORD *)&DestinationString.Length = 33554944;
  DestinationString.Buffer = (PWSTR)&v12;
  v11 = &v13;
  v3 = a1[7];
  v10[0] = 33554944;
  v4 = *(_QWORD *)(v3 + 88);
  if ( v4 )
    v4 = *(_QWORD *)(v4 + 96);
  if ( (unsigned int)SmbCeGetUserNameAndDomainName(1, v4, (__int64)&DestinationString, (__int64)v10) )
    RtlInitUnicodeString(&DestinationString, L"RDR2ID");
  else
    RtlUpcaseUnicodeString(&DestinationString, &DestinationString, 0);
  started = MRxSmbStartSMBCommand((_DWORD)a1, 2, -64, 7);
  if ( !started )
  {
    v6 = a1[4];
    RequestorProcessId = IoGetRequestorProcessId(*(PIRP *)(v1 + 40));
    *(_DWORD *)(a1[7] + 72LL) |= 0x4000u;
    *(_WORD *)(v6 + 26) = RequestorProcessId;
    *(_WORD *)(v6 + 12) = HIWORD(RequestorProcessId);
    MRxSmbStuffSMB(a1, "0wwB4!", 0, 1, &DestinationString, 0x40000);
  }
  return started;
}

```

## disassembly

```asm
0x14003652c  mov     [rsp-8+arg_8], rbx
0x140036531  mov     [rsp-8+arg_10], rsi
0x140036536  push    rbp
0x140036537  push    rdi
0x140036538  push    r14
0x14003653a  lea     rbp, [rsp-3B0h]
0x140036542  sub     rsp, 4B0h
0x140036549  mov     rax, cs:__security_cookie
0x140036550  xor     rax, rsp
0x140036553  mov     [rbp+3C0h+var_20], rax
0x14003655a  mov     r14, [rcx+30h]
0x14003655e  xorps   xmm0, xmm0
0x140036561  movups  xmmword ptr [rsp+4C0h+DestinationString.Length], xmm0
0x140036566  mov     rdi, rcx
0x140036569  mov     [rsp+4C0h+var_44C], 0
0x140036571  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140036578  lea     rax, WPP_GLOBAL_Control
0x14003657f  cmp     rcx, rax
0x140036582  jz      short loc_1400365A2
0x140036584  test    dword ptr [rcx+2Ch], 400h
0x14003658b  jz      short loc_1400365A2
0x14003658d  mov     rcx, [rcx+18h]
0x140036591  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140036598  mov     edx, 23h ; '#'
0x14003659d  call    WPP_SF_
0x1400365a2  lea     rax, [rbp+3C0h+var_440]
0x1400365a6  mov     dword ptr [rsp+4C0h+DestinationString.Length], 2000200h
0x1400365ae  mov     [rsp+4C0h+DestinationString.Buffer], rax
0x1400365b3  lea     rax, [rbp+3C0h+var_230]
0x1400365ba  mov     [rsp+4C0h+var_448], rax
0x1400365bf  mov     rax, [rdi+38h]
0x1400365c3  mov     [rsp+4C0h+var_450], 2000200h
0x1400365cb  mov     rdx, [rax+58h]
0x1400365cf  test    rdx, rdx
0x1400365d2  jz      short loc_1400365D8
0x1400365d4  mov     rdx, [rdx+60h]
0x1400365d8  lea     r9, [rsp+4C0h+var_450]
0x1400365dd  mov     ecx, 1
0x1400365e2  lea     r8, [rsp+4C0h+DestinationString]
0x1400365e7  call    SmbCeGetUserNameAndDomainName
0x1400365ec  lea     rcx, [rsp+4C0h+DestinationString]; DestinationString
0x1400365f1  test    eax, eax
0x1400365f3  jz      short loc_14003660A
0x1400365f5  lea     rdx, aRdr2id; "RDR2ID"
0x1400365fc  call    cs:__imp_RtlInitUnicodeString
0x140036603  nop     dword ptr [rax+rax+00h]
0x140036608  jmp     short loc_14003661E
0x14003660a  xor     r8d, r8d; AllocateDestinationString
0x14003660d  lea     rdx, [rsp+4C0h+DestinationString]; SourceString
0x140036612  call    cs:__imp_RtlUpcaseUnicodeString
0x140036619  nop     dword ptr [rax+rax+00h]
0x14003661e  mov     r9d, 7
0x140036624  mov     [rsp+4C0h+var_498], 40000h
0x14003662c  mov     r8b, 0C0h
0x14003662f  mov     rcx, rdi
0x140036632  lea     edx, [r9-5]
0x140036636  call    MRxSmbStartSMBCommand
0x14003663b  mov     esi, eax
0x14003663d  test    eax, eax
0x14003663f  jnz     short loc_140036689
0x140036641  mov     rcx, [r14+28h]; Irp
0x140036645  mov     rbx, [rdi+20h]
0x140036649  call    cs:__imp_IoGetRequestorProcessId
0x140036650  nop     dword ptr [rax+rax+00h]
0x140036655  mov     rdx, [rdi+38h]
0x140036659  lea     r9d, [rsi+1]
0x14003665d  xor     r8d, r8d
0x140036660  mov     rcx, rdi
0x140036663  bts     dword ptr [rdx+48h], 0Eh
0x140036668  lea     rdx, a0wwb4; "0wwB4!"
0x14003666f  mov     [rbx+1Ah], ax
0x140036673  shr     eax, 10h
0x140036676  mov     [rbx+0Ch], ax
0x14003667a  lea     rax, [rsp+4C0h+DestinationString]
0x14003667f  mov     [rsp+4C0h+var_4A0], rax
0x140036684  call    MRxSmbStuffSMB
0x140036689  mov     eax, esi
0x14003668b  mov     rcx, [rbp+3C0h+var_20]
0x140036692  xor     rcx, rsp; StackCookie
0x140036695  call    __security_check_cookie
0x14003669a  lea     r11, [rsp+4C0h+var_10]
0x1400366a2  mov     rbx, [r11+28h]
0x1400366a6  mov     rsi, [r11+30h]
0x1400366aa  mov     rsp, r11
0x1400366ad  pop     r14
0x1400366af  pop     rdi
0x1400366b0  pop     rbp
0x1400366b1  retn
```
