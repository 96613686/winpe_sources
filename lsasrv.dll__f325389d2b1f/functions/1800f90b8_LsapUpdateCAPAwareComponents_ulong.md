# LsapUpdateCAPAwareComponents(ulong)

- ea: `0x1800f90b8`
- end: `0x1800f93e5`
- name: `?LsapUpdateCAPAwareComponents@@YAJK@Z`
- size: `813`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800f268c`

## callees

- `0x1800b86d0`
- `0x1800f90b8`

## import_xrefs

- `ntdll!NtOpenKey` at `0x1800f9131`
- `ntdll!NtOpenKey` at `0x1800f91de`
- `ntdll!NtOpenKey` at `0x1800f92a5`
- `ntdll!NtOpenKey` at `0x1800f9131`
- `ntdll!NtOpenKey` at `0x1800f91de`
- `ntdll!NtOpenKey` at `0x1800f92a5`
- `ntdll!NtQueryValueKey` at `0x1800f916b`
- `ntdll!NtQueryValueKey` at `0x1800f916b`
- `ntdll!NtSetValueKey` at `0x1800f9213`
- `ntdll!NtSetValueKey` at `0x1800f925d`
- `ntdll!NtSetValueKey` at `0x1800f9319`
- `ntdll!NtSetValueKey` at `0x1800f935e`
- `ntdll!NtSetValueKey` at `0x1800f9213`
- `ntdll!NtSetValueKey` at `0x1800f925d`
- `ntdll!NtSetValueKey` at `0x1800f9319`
- `ntdll!NtSetValueKey` at `0x1800f935e`
- `ntdll!NtCreateKey` at `0x1800f92dd`
- `ntdll!NtCreateKey` at `0x1800f92dd`
- `ntdll!NtDeleteValueKey` at `0x1800f936c`
- `ntdll!NtDeleteValueKey` at `0x1800f936c`
- `ntdll!NtClose` at `0x1800f9383`
- `ntdll!NtClose` at `0x1800f939d`
- `ntdll!NtClose` at `0x1800f93b7`
- `ntdll!NtClose` at `0x1800f9383`
- `ntdll!NtClose` at `0x1800f939d`
- `ntdll!NtClose` at `0x1800f93b7`

## pseudocode

```c
__int64 __fastcall LsapUpdateCAPAwareComponents(char a1)
{
  NTSTATUS v2; // ebx
  int v3; // eax
  NTSTATUS v4; // eax
  NTSTATUS v5; // eax
  NTSTATUS v6; // eax
  NTSTATUS v7; // eax
  NTSTATUS v8; // eax
  int v10; // [rsp+40h] [rbp-49h] BYREF
  int v11; // [rsp+44h] [rbp-45h] BYREF
  ULONG ResultLength; // [rsp+48h] [rbp-41h] BYREF
  HANDLE v13; // [rsp+50h] [rbp-39h] BYREF
  void *KeyHandle; // [rsp+58h] [rbp-31h] BYREF
  int Data; // [rsp+60h] [rbp-29h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-19h] BYREF
  __int128 KeyValueInformation; // [rsp+A0h] [rbp+17h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  KeyHandle = 0;
  Handle = 0;
  v13 = 0;
  ResultLength = 0;
  v10 = 0;
  v11 = 0;
  KeyValueInformation = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &LanManServerKey;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  Data = 1;
  v2 = NtOpenKey(&KeyHandle, 0x2001Fu, &ObjectAttributes);
  if ( v2 < 0 )
    goto LABEL_25;
  if ( NtQueryValueKey(KeyHandle, &CAPS4UKey, KeyValuePartialInformation, &KeyValueInformation, 0x10u, &ResultLength) < 0 )
  {
    v3 = v10;
  }
  else
  {
    ResultLength -= 12;
    if ( ResultLength > 4 )
    {
      v2 = -1073741811;
      goto LABEL_25;
    }
    v3 = HIDWORD(KeyValueInformation);
    v10 = HIDWORD(KeyValueInformation);
  }
  if ( (a1 & 1) != 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &KerbEnableCbacKey;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v2 = NtOpenKey(&Handle, 0x20006u, &ObjectAttributes);
    if ( v2 < 0 )
      goto LABEL_25;
    v2 = NtSetValueKey(Handle, &EnableCbacAndArmor, 0, 4u, &Data, 4u);
    if ( v2 < 0 )
      goto LABEL_25;
    if ( v10 )
      goto LABEL_15;
    v10 = 1;
    goto LABEL_14;
  }
  if ( v3 )
  {
    v10 = 0;
LABEL_14:
    v2 = NtSetValueKey(KeyHandle, &CAPS4UKey, 0, 4u, &v10, 4u);
    if ( v2 < 0 )
      goto LABEL_25;
  }
LABEL_15:
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &CompoundIdentityKey;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = NtOpenKey(&v13, 0x2001Fu, &ObjectAttributes);
  v2 = v4;
  if ( v4 == -1073741772 )
  {
    if ( (a1 & 4) == 0
      || (v2 = NtCreateKey(&v13, 0x2001Fu, &ObjectAttributes, 0, 0, 0, 0), v2 >= 0)
      && (v11 = 1, v2 = NtSetValueKey(v13, &CAPCompoundIdValue, 0, 4u, &v11, 4u), v2 >= 0) )
    {
      v2 = 0;
    }
  }
  else if ( v4 >= 0 )
  {
    if ( (a1 & 4) != 0 )
    {
      v11 = 1;
      v5 = NtSetValueKey(v13, &CAPCompoundIdValue, 0, 4u, &v11, 4u);
    }
    else
    {
      v5 = NtDeleteValueKey(v13, &CAPCompoundIdValue);
    }
    v2 = v5;
  }
LABEL_25:
  if ( Handle )
  {
    v6 = NtClose(Handle);
    if ( v6 < 0 )
      v2 = v6;
  }
  if ( KeyHandle )
  {
    v7 = NtClose(KeyHandle);
    if ( v7 < 0 )
      v2 = v7;
  }
  if ( v13 )
  {
    v8 = NtClose(v13);
    if ( v8 < 0 )
      return (unsigned int)v8;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800f90b8  push    rbp
0x1800f90ba  push    rbx
0x1800f90bb  push    rsi
0x1800f90bc  push    rdi
0x1800f90bd  push    r14
0x1800f90bf  lea     rbp, [rsp-37h]
0x1800f90c4  sub     rsp, 0C0h
0x1800f90cb  mov     rax, cs:__security_cookie
0x1800f90d2  xor     rax, rsp
0x1800f90d5  mov     [rbp+57h+var_30], rax
0x1800f90d9  xor     esi, esi
0x1800f90db  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800f90e3  xorps   xmm0, xmm0
0x1800f90e6  mov     [rbp+57h+KeyHandle], rsi
0x1800f90ea  mov     edi, ecx
0x1800f90ec  mov     [rbp+57h+Handle], rsi
0x1800f90f0  lea     rax, ?LanManServerKey@@3U_UNICODE_STRING@@A; _UNICODE_STRING LanManServerKey
0x1800f90f7  mov     [rbp+57h+var_90], rsi
0x1800f90fb  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800f90ff  mov     [rbp+57h+var_98], esi
0x1800f9102  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800f9106  mov     [rbp+57h+var_A0], esi
0x1800f9109  mov     edx, 2001Fh; DesiredAccess
0x1800f910e  mov     [rbp+57h+var_9C], esi
0x1800f9111  movups  [rbp+57h+KeyValueInformation], xmm0
0x1800f9115  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x1800f9119  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800f911d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800f9122  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x1800f912a  mov     [rbp+57h+Data], 1
0x1800f9131  call    cs:__imp_NtOpenKey
0x1800f9138  nop     dword ptr [rax+rax+00h]
0x1800f913d  mov     ebx, eax
0x1800f913f  test    eax, eax
0x1800f9141  js      loc_1800F937A
0x1800f9147  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800f914b  lea     rax, [rbp+57h+var_98]
0x1800f914f  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1800f9154  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1800f9158  lea     r8d, [rsi+2]; KeyValueInformationClass
0x1800f915c  mov     [rsp+0E0h+Length], 10h; Length
0x1800f9164  lea     rdx, ?CAPS4UKey@@3U_UNICODE_STRING@@A; ValueName
0x1800f916b  call    cs:__imp_NtQueryValueKey
0x1800f9172  nop     dword ptr [rax+rax+00h]
0x1800f9177  lea     r14d, [rsi+4]
0x1800f917b  test    eax, eax
0x1800f917d  js      short loc_1800F919F
0x1800f917f  mov     eax, [rbp+57h+var_98]
0x1800f9182  add     eax, 0FFFFFFF4h
0x1800f9185  mov     [rbp+57h+var_98], eax
0x1800f9188  cmp     eax, r14d
0x1800f918b  jbe     short loc_1800F9197
0x1800f918d  mov     ebx, 0C000000Dh
0x1800f9192  jmp     loc_1800F937A
0x1800f9197  mov     eax, dword ptr [rbp+57h+KeyValueInformation+0Ch]
0x1800f919a  mov     [rbp+57h+var_A0], eax
0x1800f919d  jmp     short loc_1800F91A2
0x1800f919f  mov     eax, [rbp+57h+var_A0]
0x1800f91a2  test    dil, 1
0x1800f91a6  jz      loc_1800F9237
0x1800f91ac  lea     rax, ?KerbEnableCbacKey@@3U_UNICODE_STRING@@A; _UNICODE_STRING KerbEnableCbacKey
0x1800f91b3  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800f91ba  xorps   xmm0, xmm0
0x1800f91bd  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800f91c1  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800f91c5  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x1800f91c9  mov     edx, 20006h; DesiredAccess
0x1800f91ce  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1800f91d5  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x1800f91d9  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800f91de  call    cs:__imp_NtOpenKey
0x1800f91e5  nop     dword ptr [rax+rax+00h]
0x1800f91ea  mov     ebx, eax
0x1800f91ec  test    eax, eax
0x1800f91ee  js      loc_1800F937A
0x1800f91f4  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x1800f91f8  lea     rax, [rbp+57h+Data]
0x1800f91fc  mov     dword ptr [rsp+0E0h+ResultLength], r14d; DataSize
0x1800f9201  lea     rdx, ?EnableCbacAndArmor@@3U_UNICODE_STRING@@A; ValueName
0x1800f9208  mov     r9d, r14d; Type
0x1800f920b  mov     qword ptr [rsp+0E0h+Length], rax; Data
0x1800f9210  xor     r8d, r8d; TitleIndex
0x1800f9213  call    cs:__imp_NtSetValueKey
0x1800f921a  nop     dword ptr [rax+rax+00h]
0x1800f921f  mov     ebx, eax
0x1800f9221  test    eax, eax
0x1800f9223  js      loc_1800F937A
0x1800f9229  cmp     [rbp+57h+var_A0], esi
0x1800f922c  jnz     short loc_1800F9273
0x1800f922e  mov     [rbp+57h+var_A0], 1
0x1800f9235  jmp     short loc_1800F923E
0x1800f9237  test    eax, eax
0x1800f9239  jz      short loc_1800F9273
0x1800f923b  mov     [rbp+57h+var_A0], esi
0x1800f923e  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800f9242  lea     rax, [rbp+57h+var_A0]
0x1800f9246  mov     dword ptr [rsp+0E0h+ResultLength], r14d; DataSize
0x1800f924b  lea     rdx, ?CAPS4UKey@@3U_UNICODE_STRING@@A; ValueName
0x1800f9252  mov     r9d, r14d; Type
0x1800f9255  mov     qword ptr [rsp+0E0h+Length], rax; Data
0x1800f925a  xor     r8d, r8d; TitleIndex
0x1800f925d  call    cs:__imp_NtSetValueKey
0x1800f9264  nop     dword ptr [rax+rax+00h]
0x1800f9269  mov     ebx, eax
0x1800f926b  test    eax, eax
0x1800f926d  js      loc_1800F937A
0x1800f9273  lea     rax, ?CompoundIdentityKey@@3U_UNICODE_STRING@@A; _UNICODE_STRING CompoundIdentityKey
0x1800f927a  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800f9281  xorps   xmm0, xmm0
0x1800f9284  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800f9288  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800f928c  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x1800f9290  mov     edx, 2001Fh; DesiredAccess
0x1800f9295  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1800f929c  lea     rcx, [rbp+57h+var_90]; KeyHandle
0x1800f92a0  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800f92a5  call    cs:__imp_NtOpenKey
0x1800f92ac  nop     dword ptr [rax+rax+00h]
0x1800f92b1  mov     ebx, eax
0x1800f92b3  cmp     eax, 0C0000034h
0x1800f92b8  jnz     short loc_1800F932F
0x1800f92ba  test    r14b, dil
0x1800f92bd  jz      short loc_1800F932B
0x1800f92bf  mov     [rsp+0E0h+Disposition], rsi; Disposition
0x1800f92c4  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800f92c8  mov     dword ptr [rsp+0E0h+ResultLength], esi; CreateOptions
0x1800f92cc  lea     rcx, [rbp+57h+var_90]; KeyHandle
0x1800f92d0  xor     r9d, r9d; TitleIndex
0x1800f92d3  mov     qword ptr [rsp+0E0h+Length], rsi; Class
0x1800f92d8  mov     edx, 2001Fh; DesiredAccess
0x1800f92dd  call    cs:__imp_NtCreateKey
0x1800f92e4  nop     dword ptr [rax+rax+00h]
0x1800f92e9  mov     ebx, eax
0x1800f92eb  test    eax, eax
0x1800f92ed  js      loc_1800F937A
0x1800f92f3  mov     rcx, [rbp+57h+var_90]; KeyHandle
0x1800f92f7  lea     rax, [rbp+57h+var_9C]
0x1800f92fb  mov     dword ptr [rsp+0E0h+ResultLength], r14d; DataSize
0x1800f9300  lea     rdx, ?CAPCompoundIdValue@@3U_UNICODE_STRING@@A; ValueName
0x1800f9307  mov     r9d, r14d; Type
0x1800f930a  mov     qword ptr [rsp+0E0h+Length], rax; Data
0x1800f930f  xor     r8d, r8d; TitleIndex
0x1800f9312  mov     [rbp+57h+var_9C], 1
0x1800f9319  call    cs:__imp_NtSetValueKey
0x1800f9320  nop     dword ptr [rax+rax+00h]
0x1800f9325  mov     ebx, eax
0x1800f9327  test    eax, eax
0x1800f9329  js      short loc_1800F937A
0x1800f932b  mov     ebx, esi
0x1800f932d  jmp     short loc_1800F937A
0x1800f932f  test    eax, eax
0x1800f9331  js      short loc_1800F937A
0x1800f9333  mov     rcx, [rbp+57h+var_90]; KeyHandle
0x1800f9337  lea     rdx, ?CAPCompoundIdValue@@3U_UNICODE_STRING@@A; ValueName
0x1800f933e  test    r14b, dil
0x1800f9341  jz      short loc_1800F936C
0x1800f9343  lea     rax, [rbp+57h+var_9C]
0x1800f9347  mov     dword ptr [rsp+0E0h+ResultLength], r14d; DataSize
0x1800f934c  mov     r9d, r14d; Type
0x1800f934f  mov     qword ptr [rsp+0E0h+Length], rax; Data
0x1800f9354  xor     r8d, r8d; TitleIndex
0x1800f9357  mov     [rbp+57h+var_9C], 1
0x1800f935e  call    cs:__imp_NtSetValueKey
0x1800f9365  nop     dword ptr [rax+rax+00h]
0x1800f936a  jmp     short loc_1800F9378
0x1800f936c  call    cs:__imp_NtDeleteValueKey
0x1800f9373  nop     dword ptr [rax+rax+00h]
0x1800f9378  mov     ebx, eax
0x1800f937a  mov     rcx, [rbp+57h+Handle]; Handle
0x1800f937e  test    rcx, rcx
0x1800f9381  jz      short loc_1800F9394
0x1800f9383  call    cs:__imp_NtClose
0x1800f938a  nop     dword ptr [rax+rax+00h]
0x1800f938f  test    eax, eax
0x1800f9391  cmovs   ebx, eax
0x1800f9394  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800f9398  test    rcx, rcx
0x1800f939b  jz      short loc_1800F93AE
0x1800f939d  call    cs:__imp_NtClose
0x1800f93a4  nop     dword ptr [rax+rax+00h]
0x1800f93a9  test    eax, eax
0x1800f93ab  cmovs   ebx, eax
0x1800f93ae  mov     rcx, [rbp+57h+var_90]; Handle
0x1800f93b2  test    rcx, rcx
0x1800f93b5  jz      short loc_1800F93C8
0x1800f93b7  call    cs:__imp_NtClose
0x1800f93be  nop     dword ptr [rax+rax+00h]
0x1800f93c3  test    eax, eax
0x1800f93c5  cmovs   ebx, eax
0x1800f93c8  mov     eax, ebx
0x1800f93ca  mov     rcx, [rbp+57h+var_30]
0x1800f93ce  xor     rcx, rsp; StackCookie
0x1800f93d1  call    __security_check_cookie
0x1800f93d6  add     rsp, 0C0h
0x1800f93dd  pop     r14
0x1800f93df  pop     rdi
0x1800f93e0  pop     rsi
0x1800f93e1  pop     rbx
0x1800f93e2  pop     rbp
0x1800f93e3  retn
```
