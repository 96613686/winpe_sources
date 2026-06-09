# IopInitializeDumpPolicySettings

- ea: `0x140755344`
- end: `0x140755625`
- name: `IopInitializeDumpPolicySettings`
- size: `737`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x1405d4260`
- `0x140754c50`
- `0x140c5c6f4`

## callees

- `0x140307510`
- `0x1403075d0`
- `0x1403f2d50`
- `0x14049f064`
- `0x1404e7c00`
- `0x140525ce4`
- `0x1405d4acc`
- `0x1406d9d70`
- `0x140755344`
- `0x1408eef70`
- `0x140930fe0`
- `0x14097499c`
- `0x140aaf718`
- `0x140bae8e0`

## string_xrefs

- `0x1407553d3`: `\Registry\Machine\System\CurrentControlSet\Control\CrashControl`
- `0x140755461`: `\Registry\Machine\OSDATA\System\CurrentControlSet\Control\LiveDump`
- `0x140755490`: `\Registry\Machine\OSBOOT\System\CurrentControlSet\Control\LiveDump`
- `0x14075549d`: `\Registry\Machine\System\CurrentControlSet\Control\LiveDump`
- `0x1407553c5`: `\Registry\Machine\OSBOOT\System\CurrentControlSet\Control\CrashControl`
- `0x140755395`: `\Registry\Machine\OSDATA\System\CurrentControlSet\Control\CrashControl`

## pseudocode

```c
NTSTATUS __fastcall IopInitializeDumpPolicySettings(char a1)
{
  const WCHAR *v2; // rdx
  UNICODE_STRING *p_DestinationString; // rdi
  const WCHAR *v4; // rdx
  NTSTATUS result; // eax
  int UserData; // [rsp+20h] [rbp-79h]
  char UserDataa; // [rsp+20h] [rbp-79h]
  HANDLE Handle; // [rsp+30h] [rbp-69h] BYREF
  PVOID P; // [rsp+38h] [rbp-61h] BYREF
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-59h] BYREF
  UNICODE_STRING v11; // [rsp+50h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v13[32]; // [rsp+70h] [rbp-29h] BYREF
  PVOID *p_P; // [rsp+90h] [rbp-9h]
  __int64 v15; // [rsp+98h] [rbp-1h]

  Handle = 0;
  P = 0;
  DestinationString = 0;
  HIDWORD(v12.Ptr) = 0;
  v11 = 0;
  if ( !(unsigned __int8)CmIsStateSeparationEnabled() )
  {
    v2 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\CrashControl";
LABEL_5:
    RtlInitUnicodeString(&DestinationString, v2);
    LOBYTE(UserData) = 0;
    if ( (int)IopOpenRegistryKey(&Handle, 0, &DestinationString, 131097, UserData) < 0 )
      goto LABEL_12;
    goto LABEL_6;
  }
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\OSDATA\\System\\CurrentControlSet\\Control\\CrashControl");
  UserDataa = 0;
  if ( (int)IopOpenRegistryKey(&Handle, 0, &DestinationString, 131097, UserDataa) < 0 )
  {
    v2 = L"\\Registry\\Machine\\OSBOOT\\System\\CurrentControlSet\\Control\\CrashControl";
    goto LABEL_5;
  }
LABEL_6:
  if ( (int)IopGetRegistryValue(Handle) >= 0 )
  {
    if ( *((_DWORD *)P + 1) == 4 && *((_DWORD *)P + 3) == 4 )
      AllowCrashDump = *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) != 0;
    ExFreePoolWithTag(P, 0);
  }
  ObCloseHandle(Handle, 0);
LABEL_12:
  if ( !(unsigned __int8)CmIsStateSeparationEnabled() )
  {
    p_DestinationString = &DestinationString;
    v4 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\LiveDump";
LABEL_16:
    RtlInitUnicodeString(p_DestinationString, v4);
    LOBYTE(UserData) = 0;
    result = IopOpenRegistryKey(&Handle, 0, p_DestinationString, 131097, UserData);
    if ( result < 0 )
      goto LABEL_23;
    goto LABEL_17;
  }
  RtlInitUnicodeString(&v11, L"\\Registry\\Machine\\OSDATA\\System\\CurrentControlSet\\Control\\LiveDump");
  LOBYTE(UserData) = 0;
  if ( (int)IopOpenRegistryKey(&Handle, 0, &v11, 131097, UserData) < 0 )
  {
    p_DestinationString = &v11;
    v4 = L"\\Registry\\Machine\\OSBOOT\\System\\CurrentControlSet\\Control\\LiveDump";
    goto LABEL_16;
  }
LABEL_17:
  if ( (int)IopGetRegistryValue(Handle) >= 0 )
  {
    if ( *((_DWORD *)P + 1) == 4 && *((_DWORD *)P + 3) == 4 )
      AllowLiveDump = *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) != 0;
    ExFreePoolWithTag(P, 0);
  }
  result = ObCloseHandle(Handle, 0);
LABEL_23:
  if ( a1 )
  {
    if ( (int)ExSubscribeWnfStateChange(
                (unsigned int)&P,
                (unsigned int)&WNF_DUMP_ALLOW_CRASHDUMP_POLICY_VALUE_CHANGED,
                1,
                0,
                (__int64)IopCrashDumpPolicyChangeWnfCallback,
                0) < 0 )
    {
      if ( (unsigned __int8)IopDumpIsTracingEnabled() )
      {
        v12.Ptr = (ULONGLONG)"Failed to subscribe for policy value change notification";
        *(_QWORD *)&v12.Size = 56;
        EtwWrite(IopDumpEtwRegHandle, &DUMP_EVENT_CRASHDUMP_POLICY_OPERATION_FAILURE, 0, 1u, &v12);
      }
      if ( (unsigned int)dword_140E0A2F8 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_140E0A2F8, 0x400000000000LL) )
        {
          P = (PVOID)0x1000000;
          p_P = &P;
          v15 = 8;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140E0A2F8, word_140046C32, 0, 0, 3, v13);
        }
      }
    }
    return IopLiveDumpRegisterWnfNotificationCallback();
  }
  return result;
}

```

## disassembly

```asm
0x140755344  push    rbp
0x140755346  push    rbx
0x140755347  push    rsi
0x140755348  push    rdi
0x140755349  push    r12
0x14075534b  push    r13
0x14075534d  push    r14
0x14075534f  push    r15
0x140755351  lea     rbp, [rsp-1Fh]
0x140755356  sub     rsp, 0B8h
0x14075535d  mov     rax, cs:__security_cookie
0x140755364  xor     rax, rsp
0x140755367  mov     [rbp+57h+var_50], rax
0x14075536b  xor     r12d, r12d
0x14075536e  xor     eax, eax
0x140755370  xorps   xmm0, xmm0
0x140755373  mov     [rbp+57h+Handle], r12
0x140755377  xorps   xmm1, xmm1
0x14075537a  mov     [rbp+57h+P], r12
0x14075537e  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140755382  mov     dword ptr [rbp+57h+var_90.Ptr+4], eax
0x140755385  mov     r13b, cl
0x140755388  movups  xmmword ptr [rbp+57h+var_A0.Length], xmm1
0x14075538c  call    CmIsStateSeparationEnabled
0x140755391  test    al, al
0x140755393  jz      short loc_1407553CE
0x140755395  lea     rdx, aRegistryMachin_233; "\\Registry\\Machine\\OSDATA\\System\\Cu"...
0x14075539c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1407553a0  call    RtlInitUnicodeString
0x1407553a5  mov     ebx, 20019h
0x1407553aa  mov     byte ptr [rsp+0F0h+UserData], r12b
0x1407553af  mov     r9d, ebx
0x1407553b2  lea     r8, [rbp+57h+DestinationString]
0x1407553b6  xor     edx, edx
0x1407553b8  lea     rcx, [rbp+57h+Handle]
0x1407553bc  call    IopOpenRegistryKey
0x1407553c1  test    eax, eax
0x1407553c3  jns     short loc_14075540A
0x1407553c5  lea     rdx, aRegistryMachin_20; "\\Registry\\Machine\\OSBOOT\\System\\Cu"...
0x1407553cc  jmp     short loc_1407553DA
0x1407553ce  mov     ebx, 20019h
0x1407553d3  lea     rdx, aRegistryMachin_79; "\\Registry\\Machine\\System\\CurrentCon"...
0x1407553da  lea     rdi, [rbp+57h+DestinationString]
0x1407553de  mov     r15d, ebx
0x1407553e1  mov     rcx, rdi; DestinationString
0x1407553e4  lea     rsi, [rbp+57h+Handle]
0x1407553e8  mov     r14, r12
0x1407553eb  call    RtlInitUnicodeString
0x1407553f0  mov     r9d, ebx
0x1407553f3  mov     byte ptr [rsp+0F0h+UserData], r12b
0x1407553f8  mov     r8, rdi
0x1407553fb  mov     rdx, r12
0x1407553fe  mov     rcx, rsi
0x140755401  call    IopOpenRegistryKey
0x140755406  test    eax, eax
0x140755408  js      short loc_140755458
0x14075540a  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x14075540e  lea     r9, [rbp+57h+P]
0x140755412  mov     r8d, 4
0x140755418  lea     rdx, aAllowcrashdump; "AllowCrashDump"
0x14075541f  call    IopGetRegistryValue
0x140755424  test    eax, eax
0x140755426  js      short loc_14075544D
0x140755428  mov     rcx, [rbp+57h+P]; P
0x14075542c  cmp     dword ptr [rcx+4], 4
0x140755430  jnz     short loc_140755446
0x140755432  cmp     dword ptr [rcx+0Ch], 4
0x140755436  jnz     short loc_140755446
0x140755438  mov     eax, [rcx+8]
0x14075543b  cmp     [rax+rcx], r12d
0x14075543f  setnz   cs:AllowCrashDump
0x140755446  xor     edx, edx; Tag
0x140755448  call    ExFreePoolWithTag
0x14075544d  mov     rcx, [rbp+57h+Handle]; Handle
0x140755451  xor     edx, edx; PreviousMode
0x140755453  call    ObCloseHandle
0x140755458  call    CmIsStateSeparationEnabled
0x14075545d  test    al, al
0x14075545f  jz      short loc_140755499
0x140755461  lea     rdx, aRegistryMachin_239; "\\Registry\\Machine\\OSDATA\\System\\Cu"...
0x140755468  lea     rcx, [rbp+57h+var_A0]; DestinationString
0x14075546c  call    RtlInitUnicodeString
0x140755471  mov     r9d, ebx
0x140755474  mov     byte ptr [rsp+0F0h+UserData], r12b
0x140755479  lea     r8, [rbp+57h+var_A0]
0x14075547d  xor     edx, edx
0x14075547f  lea     rcx, [rbp+57h+Handle]
0x140755483  call    IopOpenRegistryKey
0x140755488  test    eax, eax
0x14075548a  jns     short loc_1407554D0
0x14075548c  lea     rdi, [rbp+57h+var_A0]
0x140755490  lea     rdx, aRegistryMachin_40; "\\Registry\\Machine\\OSBOOT\\System\\Cu"...
0x140755497  jmp     short loc_1407554A4
0x140755499  lea     rdi, [rbp+57h+DestinationString]
0x14075549d  lea     rdx, aRegistryMachin_99; "\\Registry\\Machine\\System\\CurrentCon"...
0x1407554a4  mov     rcx, rdi; DestinationString
0x1407554a7  lea     rsi, [rbp+57h+Handle]
0x1407554ab  mov     r15b, r12b
0x1407554ae  mov     r14, r12
0x1407554b1  call    RtlInitUnicodeString
0x1407554b6  mov     r9d, ebx
0x1407554b9  mov     byte ptr [rsp+0F0h+UserData], r12b
0x1407554be  mov     r8, rdi
0x1407554c1  mov     rdx, r12
0x1407554c4  mov     rcx, rsi
0x1407554c7  call    IopOpenRegistryKey
0x1407554cc  test    eax, eax
0x1407554ce  js      short loc_14075551E
0x1407554d0  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x1407554d4  lea     r9, [rbp+57h+P]
0x1407554d8  mov     r8d, 4
0x1407554de  lea     rdx, aAllowlivedump_0; "AllowLiveDump"
0x1407554e5  call    IopGetRegistryValue
0x1407554ea  test    eax, eax
0x1407554ec  js      short loc_140755513
0x1407554ee  mov     rcx, [rbp+57h+P]; P
0x1407554f2  cmp     dword ptr [rcx+4], 4
0x1407554f6  jnz     short loc_14075550C
0x1407554f8  cmp     dword ptr [rcx+0Ch], 4
0x1407554fc  jnz     short loc_14075550C
0x1407554fe  mov     eax, [rcx+8]
0x140755501  cmp     [rax+rcx], r12d
0x140755505  setnz   cs:AllowLiveDump
0x14075550c  xor     edx, edx; Tag
0x14075550e  call    ExFreePoolWithTag
0x140755513  mov     rcx, [rbp+57h+Handle]; Handle
0x140755517  xor     edx, edx; PreviousMode
0x140755519  call    ObCloseHandle
0x14075551e  test    r13b, r13b
0x140755521  jz      loc_140755604
0x140755527  xor     r9d, r9d
0x14075552a  mov     [rsp+0F0h+var_C8], r12
0x14075552f  lea     rax, IopCrashDumpPolicyChangeWnfCallback
0x140755536  lea     rdx, WNF_DUMP_ALLOW_CRASHDUMP_POLICY_VALUE_CHANGED
0x14075553d  mov     [rsp+0F0h+UserData], rax
0x140755542  lea     rcx, [rbp+57h+P]
0x140755546  lea     ebx, [r9+1]
0x14075554a  mov     r8d, ebx
0x14075554d  call    ExSubscribeWnfStateChange
0x140755552  test    eax, eax
0x140755554  jns     loc_1407555FF
0x14075555a  call    IopDumpIsTracingEnabled
0x14075555f  test    al, al
0x140755561  jz      short loc_140755598
0x140755563  mov     rcx, cs:IopDumpEtwRegHandle; RegHandle
0x14075556a  lea     rax, aFailedToSubscr; "Failed to subscribe for policy value ch"...
0x140755571  mov     [rbp-39h], rax
0x140755575  lea     rdx, DUMP_EVENT_CRASHDUMP_POLICY_OPERATION_FAILURE; EventDescriptor
0x14075557c  lea     rax, [rbp+57h+var_90]
0x140755580  mov     qword ptr [rbp+57h+var_90.Size], 38h ; '8'
0x140755588  mov     r9d, ebx; UserDataCount
0x14075558b  mov     [rsp+0F0h+UserData], rax; UserData
0x140755590  xor     r8d, r8d; ActivityId
0x140755593  call    EtwWrite
0x140755598  mov     eax, cs:dword_140E0A2F8
0x14075559e  cmp     eax, 5
0x1407555a1  jbe     short loc_1407555FF
0x1407555a3  mov     rdx, 400000000000h
0x1407555ad  lea     rcx, dword_140E0A2F8
0x1407555b4  call    _tlgKeywordOn
0x1407555b9  test    al, al
0x1407555bb  jz      short loc_1407555FF
0x1407555bd  lea     rax, [rbp+57h+P]
0x1407555c1  mov     [rbp+57h+P], 1000000h
0x1407555c9  mov     [rbp+57h+var_60], rax
0x1407555cd  lea     rdx, word_140046C32
0x1407555d4  lea     rax, [rbp+57h+var_80]
0x1407555d8  mov     [rbp+57h+var_58], 8
0x1407555e0  mov     [rsp+0F0h+var_C8], rax
0x1407555e5  lea     rcx, dword_140E0A2F8
0x1407555ec  xor     r9d, r9d
0x1407555ef  mov     dword ptr [rsp+0F0h+UserData], 3
0x1407555f7  xor     r8d, r8d
0x1407555fa  call    _tlgWriteTransfer_EtwWriteTransfer
0x1407555ff  call    IopLiveDumpRegisterWnfNotificationCallback
0x140755604  mov     rcx, [rbp+57h+var_50]
0x140755608  xor     rcx, rsp; StackCookie
0x14075560b  call    __security_check_cookie
0x140755610  add     rsp, 0B8h
0x140755617  pop     r15
0x140755619  pop     r14
0x14075561b  pop     r13
0x14075561d  pop     r12
0x14075561f  pop     rdi
0x140755620  pop     rsi
0x140755621  pop     rbx
0x140755622  pop     rbp
0x140755623  retn
```
