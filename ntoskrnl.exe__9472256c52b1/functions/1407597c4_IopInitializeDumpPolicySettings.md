# IopInitializeDumpPolicySettings

- ea: `0x1407597c4`
- end: `0x140759aa5`
- name: `IopInitializeDumpPolicySettings`
- size: `737`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x1405dae40`
- `0x1407590d0`
- `0x140c619c4`

## callees

- `0x14025be90`
- `0x14025bf50`
- `0x140403380`
- `0x1404acd34`
- `0x1404f72f0`
- `0x14052cd74`
- `0x1405db6ac`
- `0x1406dc8c0`
- `0x1407597c4`
- `0x14087852c`
- `0x140929100`
- `0x14094b0a0`
- `0x140ab52a8`
- `0x140bb19f0`

## string_xrefs

- `0x140759845`: `\Registry\Machine\OSBOOT\System\CurrentControlSet\Control\CrashControl`
- `0x1407598e1`: `\Registry\Machine\OSDATA\System\CurrentControlSet\Control\LiveDump`
- `0x140759853`: `\Registry\Machine\System\CurrentControlSet\Control\CrashControl`
- `0x140759815`: `\Registry\Machine\OSDATA\System\CurrentControlSet\Control\CrashControl`
- `0x14075991d`: `\Registry\Machine\System\CurrentControlSet\Control\LiveDump`
- `0x140759910`: `\Registry\Machine\OSBOOT\System\CurrentControlSet\Control\LiveDump`

## pseudocode

```c
NTSTATUS __fastcall IopInitializeDumpPolicySettings(__int64 a1)
{
  char v1; // r13
  const WCHAR *v2; // rdx
  __int64 v3; // rcx
  UNICODE_STRING *p_DestinationString; // rdi
  const WCHAR *v5; // rdx
  NTSTATUS result; // eax
  int UserData; // [rsp+20h] [rbp-79h]
  char UserDataa; // [rsp+20h] [rbp-79h]
  HANDLE Handle; // [rsp+30h] [rbp-69h] BYREF
  PVOID P; // [rsp+38h] [rbp-61h] BYREF
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-59h] BYREF
  UNICODE_STRING v12; // [rsp+50h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v14[32]; // [rsp+70h] [rbp-29h] BYREF
  PVOID *p_P; // [rsp+90h] [rbp-9h]
  __int64 v16; // [rsp+98h] [rbp-1h]

  Handle = 0;
  P = 0;
  DestinationString = 0;
  HIDWORD(v13.Ptr) = 0;
  v1 = a1;
  v12 = 0;
  if ( !(unsigned __int8)CmIsStateSeparationEnabled(a1) )
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
  if ( IopGetRegistryValue(Handle, L"AllowCrashDump", 4, &P) >= 0 )
  {
    if ( *((_DWORD *)P + 1) == 4 && *((_DWORD *)P + 3) == 4 )
      AllowCrashDump = *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) != 0;
    ExFreePoolWithTag(P, 0);
  }
  ObCloseHandle(Handle, 0);
LABEL_12:
  if ( !(unsigned __int8)CmIsStateSeparationEnabled(v3) )
  {
    p_DestinationString = &DestinationString;
    v5 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\LiveDump";
LABEL_16:
    RtlInitUnicodeString(p_DestinationString, v5);
    LOBYTE(UserData) = 0;
    result = IopOpenRegistryKey(&Handle, 0, p_DestinationString, 131097, UserData);
    if ( result < 0 )
      goto LABEL_23;
    goto LABEL_17;
  }
  RtlInitUnicodeString(&v12, L"\\Registry\\Machine\\OSDATA\\System\\CurrentControlSet\\Control\\LiveDump");
  LOBYTE(UserData) = 0;
  if ( (int)IopOpenRegistryKey(&Handle, 0, &v12, 131097, UserData) < 0 )
  {
    p_DestinationString = &v12;
    v5 = L"\\Registry\\Machine\\OSBOOT\\System\\CurrentControlSet\\Control\\LiveDump";
    goto LABEL_16;
  }
LABEL_17:
  if ( IopGetRegistryValue(Handle, L"AllowLiveDump", 4, &P) >= 0 )
  {
    if ( *((_DWORD *)P + 1) == 4 && *((_DWORD *)P + 3) == 4 )
      AllowLiveDump = *(_DWORD *)((char *)P + *((unsigned int *)P + 2)) != 0;
    ExFreePoolWithTag(P, 0);
  }
  result = ObCloseHandle(Handle, 0);
LABEL_23:
  if ( v1 )
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
        v13.Ptr = (ULONGLONG)"Failed to subscribe for policy value change notification";
        *(_QWORD *)&v13.Size = 56;
        EtwWrite(IopDumpEtwRegHandle, &DUMP_EVENT_CRASHDUMP_POLICY_OPERATION_FAILURE, 0, 1u, &v13);
      }
      if ( (unsigned int)dword_140E0A2F8 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_140E0A2F8, 0x400000000000LL) )
        {
          P = (PVOID)0x1000000;
          p_P = &P;
          v16 = 8;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140E0A2F8, byte_1400468AD, 0, 0, 3, v14);
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
0x1407597c4  push    rbp
0x1407597c6  push    rbx
0x1407597c7  push    rsi
0x1407597c8  push    rdi
0x1407597c9  push    r12
0x1407597cb  push    r13
0x1407597cd  push    r14
0x1407597cf  push    r15
0x1407597d1  lea     rbp, [rsp-1Fh]
0x1407597d6  sub     rsp, 0B8h
0x1407597dd  mov     rax, cs:__security_cookie
0x1407597e4  xor     rax, rsp
0x1407597e7  mov     [rbp+57h+var_50], rax
0x1407597eb  xor     r12d, r12d
0x1407597ee  xor     eax, eax
0x1407597f0  xorps   xmm0, xmm0
0x1407597f3  mov     [rbp+57h+Handle], r12
0x1407597f7  xorps   xmm1, xmm1
0x1407597fa  mov     [rbp+57h+P], r12
0x1407597fe  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140759802  mov     dword ptr [rbp+57h+var_90.Ptr+4], eax
0x140759805  mov     r13b, cl
0x140759808  movups  xmmword ptr [rbp+57h+var_A0.Length], xmm1
0x14075980c  call    CmIsStateSeparationEnabled
0x140759811  test    al, al
0x140759813  jz      short loc_14075984E
0x140759815  lea     rdx, aRegistryMachin_232; "\\Registry\\Machine\\OSDATA\\System\\Cu"...
0x14075981c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140759820  call    RtlInitUnicodeString
0x140759825  mov     ebx, 20019h
0x14075982a  mov     byte ptr [rsp+0F0h+UserData], r12b
0x14075982f  mov     r9d, ebx
0x140759832  lea     r8, [rbp+57h+DestinationString]
0x140759836  xor     edx, edx
0x140759838  lea     rcx, [rbp+57h+Handle]
0x14075983c  call    IopOpenRegistryKey
0x140759841  test    eax, eax
0x140759843  jns     short loc_14075988A
0x140759845  lea     rdx, aRegistryMachin_20; "\\Registry\\Machine\\OSBOOT\\System\\Cu"...
0x14075984c  jmp     short loc_14075985A
0x14075984e  mov     ebx, 20019h
0x140759853  lea     rdx, aRegistryMachin_79; "\\Registry\\Machine\\System\\CurrentCon"...
0x14075985a  lea     rdi, [rbp+57h+DestinationString]
0x14075985e  mov     r15d, ebx
0x140759861  mov     rcx, rdi; DestinationString
0x140759864  lea     rsi, [rbp+57h+Handle]
0x140759868  mov     r14, r12
0x14075986b  call    RtlInitUnicodeString
0x140759870  mov     r9d, ebx
0x140759873  mov     byte ptr [rsp+0F0h+UserData], r12b
0x140759878  mov     r8, rdi
0x14075987b  mov     rdx, r12
0x14075987e  mov     rcx, rsi
0x140759881  call    IopOpenRegistryKey
0x140759886  test    eax, eax
0x140759888  js      short loc_1407598D8
0x14075988a  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x14075988e  lea     r9, [rbp+57h+P]
0x140759892  mov     r8d, 4
0x140759898  lea     rdx, aAllowcrashdump; "AllowCrashDump"
0x14075989f  call    IopGetRegistryValue
0x1407598a4  test    eax, eax
0x1407598a6  js      short loc_1407598CD
0x1407598a8  mov     rcx, [rbp+57h+P]; P
0x1407598ac  cmp     dword ptr [rcx+4], 4
0x1407598b0  jnz     short loc_1407598C6
0x1407598b2  cmp     dword ptr [rcx+0Ch], 4
0x1407598b6  jnz     short loc_1407598C6
0x1407598b8  mov     eax, [rcx+8]
0x1407598bb  cmp     [rax+rcx], r12d
0x1407598bf  setnz   cs:AllowCrashDump
0x1407598c6  xor     edx, edx; Tag
0x1407598c8  call    ExFreePoolWithTag
0x1407598cd  mov     rcx, [rbp+57h+Handle]; Handle
0x1407598d1  xor     edx, edx; PreviousMode
0x1407598d3  call    ObCloseHandle
0x1407598d8  call    CmIsStateSeparationEnabled
0x1407598dd  test    al, al
0x1407598df  jz      short loc_140759919
0x1407598e1  lea     rdx, aRegistryMachin_238; "\\Registry\\Machine\\OSDATA\\System\\Cu"...
0x1407598e8  lea     rcx, [rbp+57h+var_A0]; DestinationString
0x1407598ec  call    RtlInitUnicodeString
0x1407598f1  mov     r9d, ebx
0x1407598f4  mov     byte ptr [rsp+0F0h+UserData], r12b
0x1407598f9  lea     r8, [rbp+57h+var_A0]
0x1407598fd  xor     edx, edx
0x1407598ff  lea     rcx, [rbp+57h+Handle]
0x140759903  call    IopOpenRegistryKey
0x140759908  test    eax, eax
0x14075990a  jns     short loc_140759950
0x14075990c  lea     rdi, [rbp+57h+var_A0]
0x140759910  lea     rdx, aRegistryMachin_40; "\\Registry\\Machine\\OSBOOT\\System\\Cu"...
0x140759917  jmp     short loc_140759924
0x140759919  lea     rdi, [rbp+57h+DestinationString]
0x14075991d  lea     rdx, aRegistryMachin_99; "\\Registry\\Machine\\System\\CurrentCon"...
0x140759924  mov     rcx, rdi; DestinationString
0x140759927  lea     rsi, [rbp+57h+Handle]
0x14075992b  mov     r15b, r12b
0x14075992e  mov     r14, r12
0x140759931  call    RtlInitUnicodeString
0x140759936  mov     r9d, ebx
0x140759939  mov     byte ptr [rsp+0F0h+UserData], r12b
0x14075993e  mov     r8, rdi
0x140759941  mov     rdx, r12
0x140759944  mov     rcx, rsi
0x140759947  call    IopOpenRegistryKey
0x14075994c  test    eax, eax
0x14075994e  js      short loc_14075999E
0x140759950  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x140759954  lea     r9, [rbp+57h+P]
0x140759958  mov     r8d, 4
0x14075995e  lea     rdx, aAllowlivedump_0; "AllowLiveDump"
0x140759965  call    IopGetRegistryValue
0x14075996a  test    eax, eax
0x14075996c  js      short loc_140759993
0x14075996e  mov     rcx, [rbp+57h+P]; P
0x140759972  cmp     dword ptr [rcx+4], 4
0x140759976  jnz     short loc_14075998C
0x140759978  cmp     dword ptr [rcx+0Ch], 4
0x14075997c  jnz     short loc_14075998C
0x14075997e  mov     eax, [rcx+8]
0x140759981  cmp     [rax+rcx], r12d
0x140759985  setnz   cs:AllowLiveDump
0x14075998c  xor     edx, edx; Tag
0x14075998e  call    ExFreePoolWithTag
0x140759993  mov     rcx, [rbp+57h+Handle]; Handle
0x140759997  xor     edx, edx; PreviousMode
0x140759999  call    ObCloseHandle
0x14075999e  test    r13b, r13b
0x1407599a1  jz      loc_140759A84
0x1407599a7  xor     r9d, r9d
0x1407599aa  mov     [rsp+0F0h+var_C8], r12
0x1407599af  lea     rax, IopCrashDumpPolicyChangeWnfCallback
0x1407599b6  lea     rdx, WNF_DUMP_ALLOW_CRASHDUMP_POLICY_VALUE_CHANGED
0x1407599bd  mov     [rsp+0F0h+UserData], rax
0x1407599c2  lea     rcx, [rbp+57h+P]
0x1407599c6  lea     ebx, [r9+1]
0x1407599ca  mov     r8d, ebx
0x1407599cd  call    ExSubscribeWnfStateChange
0x1407599d2  test    eax, eax
0x1407599d4  jns     loc_140759A7F
0x1407599da  call    IopDumpIsTracingEnabled
0x1407599df  test    al, al
0x1407599e1  jz      short loc_140759A18
0x1407599e3  mov     rcx, cs:IopDumpEtwRegHandle; RegHandle
0x1407599ea  lea     rax, aFailedToSubscr; "Failed to subscribe for policy value ch"...
0x1407599f1  mov     [rbp-39h], rax
0x1407599f5  lea     rdx, DUMP_EVENT_CRASHDUMP_POLICY_OPERATION_FAILURE; EventDescriptor
0x1407599fc  lea     rax, [rbp+57h+var_90]
0x140759a00  mov     qword ptr [rbp+57h+var_90.Size], 38h ; '8'
0x140759a08  mov     r9d, ebx; UserDataCount
0x140759a0b  mov     [rsp+0F0h+UserData], rax; UserData
0x140759a10  xor     r8d, r8d; ActivityId
0x140759a13  call    EtwWrite
0x140759a18  mov     eax, cs:dword_140E0A2F8
0x140759a1e  cmp     eax, 5
0x140759a21  jbe     short loc_140759A7F
0x140759a23  mov     rdx, 400000000000h
0x140759a2d  lea     rcx, dword_140E0A2F8
0x140759a34  call    _tlgKeywordOn
0x140759a39  test    al, al
0x140759a3b  jz      short loc_140759A7F
0x140759a3d  lea     rax, [rbp+57h+P]
0x140759a41  mov     [rbp+57h+P], 1000000h
0x140759a49  mov     [rbp+57h+var_60], rax
0x140759a4d  lea     rdx, byte_1400468AD
0x140759a54  lea     rax, [rbp+57h+var_80]
0x140759a58  mov     [rbp+57h+var_58], 8
0x140759a60  mov     [rsp+0F0h+var_C8], rax
0x140759a65  lea     rcx, dword_140E0A2F8
0x140759a6c  xor     r9d, r9d
0x140759a6f  mov     dword ptr [rsp+0F0h+UserData], 3
0x140759a77  xor     r8d, r8d
0x140759a7a  call    _tlgWriteTransfer_EtwWriteTransfer
0x140759a7f  call    IopLiveDumpRegisterWnfNotificationCallback
0x140759a84  mov     rcx, [rbp+57h+var_50]
0x140759a88  xor     rcx, rsp; StackCookie
0x140759a8b  call    __security_check_cookie
0x140759a90  add     rsp, 0B8h
0x140759a97  pop     r15
0x140759a99  pop     r14
0x140759a9b  pop     r13
0x140759a9d  pop     r12
0x140759a9f  pop     rdi
0x140759aa0  pop     rsi
0x140759aa1  pop     rbx
0x140759aa2  pop     rbp
0x140759aa3  retn
```
