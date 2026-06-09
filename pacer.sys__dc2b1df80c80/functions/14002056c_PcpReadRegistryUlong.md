# PcpReadRegistryUlong

- ea: `0x14002056c`
- end: `0x140020802`
- name: `PcpReadRegistryUlong`
- size: `662`
- prototype: `__int64 __usercall@<rax>(NDIS_HANDLE ConfigurationHandle@<rcx>, PNDIS_STRING Keyword@<rdx>, int, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001fee0`

## callees

- `0x14001144c`
- `0x140013110`
- `0x140013600`
- `0x14002056c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400206f7`
- `ntoskrnl!ZwClose` at `0x1400206f7`
- `ntoskrnl!ZwOpenKey` at `0x1400206dc`
- `ntoskrnl!ZwOpenKey` at `0x1400206dc`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14002067c`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14002067c`
- `NDIS!NdisReadConfiguration` at `0x140020720`
- `NDIS!NdisReadConfiguration` at `0x140020720`

## pseudocode

```c
char __fastcall PcpReadRegistryUlong(
        NDIS_HANDLE ConfigurationHandle,
        PNDIS_STRING Keyword,
        unsigned int *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        _DWORD *a7,
        __int64 a8)
{
  PNDIS_CONFIGURATION_PARAMETER v10; // rcx
  char v13; // si
  int v14; // eax
  NTSTATUS v16; // edx
  int v17; // r8d
  unsigned int IntegerData; // eax
  unsigned int v19; // [rsp+30h] [rbp-D0h] BYREF
  int Status; // [rsp+34h] [rbp-CCh] BYREF
  PNDIS_CONFIGURATION_PARAMETER ParameterValue; // [rsp+38h] [rbp-C8h] BYREF
  void *KeyHandle; // [rsp+40h] [rbp-C0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v24[22]; // [rsp+80h] [rbp-80h] BYREF

  Status = 0;
  v19 = 0;
  v10 = 0;
  ParameterValue = 0;
  v13 = 0;
  if ( ConfigurationHandle )
  {
    NdisReadConfiguration(&Status, &ParameterValue, ConfigurationHandle, Keyword, NdisParameterInteger);
    v10 = ParameterValue;
    v14 = Status;
  }
  else
  {
    v14 = -1073741823;
    Status = -1073741823;
  }
  if ( v14 )
  {
    if ( !*a7 )
    {
      *a3 = a6;
      return v13;
    }
    v19 = a6;
    memset(v24, 0, 0xA8u);
    v24[5] = 0;
    LODWORD(v24[6]) = 0;
    if ( a8 )
    {
      v24[2] = *(_QWORD *)(a8 + 8);
      v24[9] = Keyword->Buffer;
      v24[10] = &v19;
      LODWORD(v24[1]) = 1;
      v24[3] = 0;
      LODWORD(v24[4]) = 0;
      v24[7] = 0;
      LODWORD(v24[8]) = 36;
      LODWORD(v24[11]) = 4;
      v24[12] = 0;
      LODWORD(v24[13]) = 0;
    }
    else
    {
      v24[2] = Keyword->Buffer;
      v24[3] = &v19;
      LODWORD(v24[1]) = 36;
      LODWORD(v24[4]) = 4;
    }
    if ( (int)RtlQueryRegistryValuesEx(0, off_140018090, v24, 0, 0) >= 0 && v19 >= a4 && v19 <= a5 )
    {
      *a3 = v19;
      v13 = 1;
      goto LABEL_13;
    }
    *a3 = a6;
    if ( *a7 != -1 )
      return v13;
    KeyHandle = 0;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)PcRegKeyMachine;
    *(_QWORD *)&ObjectAttributes.Attributes = 576;
    ObjectAttributes.RootDirectory = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v16 = ZwOpenKey(&KeyHandle, 0x80000000, &ObjectAttributes);
    if ( v16 >= 0 )
    {
      ZwClose(KeyHandle);
LABEL_13:
      *a7 = 1;
      return v13;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
    {
      WPP_SF_Zd(WPP_GLOBAL_Control->AttachedDevice, v16, v17, (unsigned int)PcRegKeyMachine, v16);
    }
    *a7 = 0;
  }
  else
  {
    IntegerData = v10->ParameterData.IntegerData;
    if ( IntegerData < a4 || IntegerData > a5 )
      IntegerData = a6;
    else
      v13 = 1;
    *a3 = IntegerData;
  }
  return v13;
}

```

## disassembly

```asm
0x14002056c  mov     [rsp-8+arg_18], rbx
0x140020571  push    rbp
0x140020572  push    rsi
0x140020573  push    rdi
0x140020574  push    r12
0x140020576  push    r13
0x140020578  push    r14
0x14002057a  push    r15
0x14002057c  lea     rbp, [rsp-40h]
0x140020581  sub     rsp, 140h
0x140020588  mov     rax, cs:__security_cookie
0x14002058f  xor     rax, rsp
0x140020592  mov     [rbp+70h+var_40], rax
0x140020596  mov     rbx, [rbp+70h+arg_30]
0x14002059d  xor     r12d, r12d
0x1400205a0  mov     rdi, r8
0x1400205a3  mov     [rsp+170h+Status], r12d
0x1400205a8  mov     r8, rcx; ConfigurationHandle
0x1400205ab  mov     [rsp+170h+var_140], r12d
0x1400205b0  mov     ecx, r12d
0x1400205b3  mov     r15d, r9d
0x1400205b6  mov     [rsp+170h+ParameterValue], rcx
0x1400205bb  mov     r13, rdx
0x1400205be  mov     sil, r12b
0x1400205c1  test    r8, r8
0x1400205c4  jnz     loc_14002070E
0x1400205ca  mov     eax, 0C0000001h
0x1400205cf  mov     [rsp+170h+Status], eax
0x1400205d3  test    eax, eax
0x1400205d5  jz      loc_14002079C
0x1400205db  cmp     [rbx], r12d
0x1400205de  jnz     short loc_140020613
0x1400205e0  mov     ecx, [rbp+70h+arg_28]
0x1400205e6  mov     [rdi], ecx
0x1400205e8  mov     al, sil
0x1400205eb  mov     rcx, [rbp+70h+var_40]
0x1400205ef  xor     rcx, rsp; StackCookie
0x1400205f2  call    __security_check_cookie
0x1400205f7  mov     rbx, [rsp+170h+arg_18]
0x1400205ff  add     rsp, 140h
0x140020606  pop     r15
0x140020608  pop     r14
0x14002060a  pop     r13
0x14002060c  pop     r12
0x14002060e  pop     rdi
0x14002060f  pop     rsi
0x140020610  pop     rbp
0x140020611  retn
0x140020613  mov     r14d, [rbp+70h+arg_28]
0x14002061a  lea     rcx, [rbp+70h+var_F0]; void *
0x14002061e  xor     edx, edx; Val
0x140020620  mov     [rsp+170h+var_140], r14d
0x140020625  mov     r8d, 0A8h; Size
0x14002062b  call    memset
0x140020630  mov     rax, [rbp+70h+arg_38]
0x140020637  mov     [rbp+70h+var_C8], r12
0x14002063b  mov     [rbp+70h+var_C0], r12d
0x14002063f  test    rax, rax
0x140020642  jnz     loc_14002073A
0x140020648  mov     rax, [r13+8]
0x14002064c  mov     [rbp+70h+var_E0], rax
0x140020650  lea     rax, [rsp+170h+var_140]
0x140020655  mov     [rbp+70h+var_D8], rax
0x140020659  mov     [rbp+70h+var_E8], 24h ; '$'
0x140020660  mov     [rbp+70h+var_D0], 4
0x140020667  mov     rdx, cs:off_140018090; "\\Registry\\Machine\\SOFTWARE\\Policies"...
0x14002066e  lea     r8, [rbp+70h+var_F0]
0x140020672  xor     r9d, r9d
0x140020675  mov     qword ptr [rsp+170h+ParameterType], r12
0x14002067a  xor     ecx, ecx
0x14002067c  call    cs:__imp_RtlQueryRegistryValuesEx
0x140020683  nop     dword ptr [rax+rax+00h]
0x140020688  test    eax, eax
0x14002068a  jns     loc_1400207BE
0x140020690  mov     [rdi], r14d
0x140020693  cmp     dword ptr [rbx], 0FFFFFFFFh
0x140020696  jnz     loc_1400205E8
0x14002069c  xorps   xmm0, xmm0
0x14002069f  mov     [rsp+170h+KeyHandle], r12
0x1400206a4  lea     rdi, PcRegKeyMachine; "xz"
0x1400206ab  mov     qword ptr [rsp+170h+ObjectAttributes.Length], 30h ; '0'
0x1400206b4  lea     r8, [rsp+170h+ObjectAttributes]; ObjectAttributes
0x1400206b9  mov     [rsp+170h+ObjectAttributes.ObjectName], rdi
0x1400206be  mov     edx, 80000000h; DesiredAccess
0x1400206c3  mov     qword ptr [rsp+170h+ObjectAttributes.Attributes], 240h
0x1400206cc  lea     rcx, [rsp+170h+KeyHandle]; KeyHandle
0x1400206d1  mov     [rsp+170h+ObjectAttributes.RootDirectory], r12
0x1400206d6  movdqu  xmmword ptr [rsp+170h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400206dc  call    cs:__imp_ZwOpenKey
0x1400206e3  nop     dword ptr [rax+rax+00h]
0x1400206e8  mov     edx, eax
0x1400206ea  test    eax, eax
0x1400206ec  js      loc_140020781
0x1400206f2  mov     rcx, [rsp+170h+KeyHandle]; Handle
0x1400206f7  call    cs:__imp_ZwClose
0x1400206fe  nop     dword ptr [rax+rax+00h]
0x140020703  mov     dword ptr [rbx], 1
0x140020709  jmp     loc_1400205E8
0x14002070e  mov     r9, r13; Keyword
0x140020711  mov     [rsp+170h+ParameterType], r12d; ParameterType
0x140020716  lea     rdx, [rsp+170h+ParameterValue]; ParameterValue
0x14002071b  lea     rcx, [rsp+170h+Status]; Status
0x140020720  call    cs:__imp_NdisReadConfiguration
0x140020727  nop     dword ptr [rax+rax+00h]
0x14002072c  mov     rcx, [rsp+170h+ParameterValue]
0x140020731  mov     eax, [rsp+170h+Status]
0x140020735  jmp     loc_1400205D3
0x14002073a  mov     rax, [rax+8]
0x14002073e  mov     [rbp+70h+var_E0], rax
0x140020742  mov     rax, [r13+8]
0x140020746  mov     [rbp+70h+var_A8], rax
0x14002074a  lea     rax, [rsp+170h+var_140]
0x14002074f  mov     [rbp+70h+var_A0], rax
0x140020753  mov     [rbp+70h+var_E8], 1
0x14002075a  mov     [rbp+70h+var_D8], r12
0x14002075e  mov     [rbp+70h+var_D0], r12d
0x140020762  mov     [rbp+70h+var_B8], r12
0x140020766  mov     [rbp+70h+var_B0], 24h ; '$'
0x14002076d  mov     [rbp+70h+var_98], 4
0x140020774  mov     [rbp+70h+var_90], r12
0x140020778  mov     [rbp+70h+var_88], r12d
0x14002077c  jmp     loc_140020667
0x140020781  mov     rcx, cs:WPP_GLOBAL_Control
0x140020788  lea     rax, WPP_GLOBAL_Control
0x14002078f  cmp     rcx, rax
0x140020792  jnz     short loc_1400207E1
0x140020794  mov     [rbx], r12d
0x140020797  jmp     loc_1400205E8
0x14002079c  mov     eax, [rcx+8]
0x14002079f  cmp     eax, r15d
0x1400207a2  jb      short loc_1400207B1
0x1400207a4  cmp     eax, [rbp+70h+arg_20]
0x1400207aa  ja      short loc_1400207B1
0x1400207ac  mov     sil, 1
0x1400207af  jmp     short loc_1400207B7
0x1400207b1  mov     eax, [rbp+70h+arg_28]
0x1400207b7  mov     [rdi], eax
0x1400207b9  jmp     loc_1400205E8
0x1400207be  mov     eax, [rsp+170h+var_140]
0x1400207c2  cmp     eax, r15d
0x1400207c5  jb      loc_140020690
0x1400207cb  cmp     eax, [rbp+70h+arg_20]
0x1400207d1  ja      loc_140020690
0x1400207d7  mov     [rdi], eax
0x1400207d9  mov     sil, 1
0x1400207dc  jmp     loc_140020703
0x1400207e1  cmp     byte ptr [rcx+29h], 3
0x1400207e5  jb      short loc_140020794
0x1400207e7  test    dword ptr [rcx+2Ch], 800h
0x1400207ee  jz      short loc_140020794
0x1400207f0  mov     rcx, [rcx+18h]
0x1400207f4  mov     r9, rdi
0x1400207f7  mov     [rsp+170h+ParameterType], edx
0x1400207fb  call    WPP_SF_Zd
0x140020800  jmp     short loc_140020794
```
