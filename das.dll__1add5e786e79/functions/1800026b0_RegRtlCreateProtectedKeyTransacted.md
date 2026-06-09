# _RegRtlCreateProtectedKeyTransacted

- ea: `0x1800026b0`
- end: `0x180002a78`
- name: `_RegRtlCreateProtectedKeyTransacted`
- size: `968`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180001d20`
- `0x180001f50`
- `0x180005434`

## callees

- `0x180001490`
- `0x1800026b0`
- `0x180003f50`
- `0x1800049f0`
- `0x18007c5b8`
- `0x18007c8e8`
- `0x18007c930`
- `0x18007d328`

## import_xrefs

- `ntdll!RtlGetGroupSecurityDescriptor` at `0x180002a1c`
- `ntdll!RtlGetGroupSecurityDescriptor` at `0x180002a1c`
- `ntdll!RtlGetSaclSecurityDescriptor` at `0x1800029f8`
- `ntdll!RtlGetSaclSecurityDescriptor` at `0x1800029f8`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x18000299a`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x18000299a`
- `ntdll!NtCreateKey` at `0x1800027f4`
- `ntdll!NtCreateKey` at `0x1800027f4`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1800029c9`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x1800029c9`
- `ntdll!NtClose` at `0x180002806`
- `ntdll!NtClose` at `0x180002a6d`
- `ntdll!NtClose` at `0x180002806`
- `ntdll!NtClose` at `0x180002a6d`
- `ntdll!RtlInitUnicodeStringEx` at `0x18000274d`
- `ntdll!RtlInitUnicodeStringEx` at `0x18000274d`

## pseudocode

```c
__int64 __fastcall RegRtlCreateProtectedKeyTransacted(
        __int64 a1,
        const WCHAR *a2,
        int a3,
        unsigned int a4,
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        unsigned __int8 DaclPresent,
        PHANDLE KeyHandle,
        PULONG Disposition,
        __int64 a9)
{
  int KeyTransacted_Stub; // edi
  int v13; // r9d
  HANDLE v14; // rcx
  PSECURITY_DESCRIPTOR v15; // rsi
  PULONG v16; // r12
  ACCESS_MASK v17; // edx
  PHANDLE v18; // r13
  int v20; // eax
  SECURITY_INFORMATION v21; // ebx
  unsigned __int8 DaclDefaulted; // [rsp+50h] [rbp-B8h] BYREF
  unsigned __int8 SaclDefaulted; // [rsp+51h] [rbp-B7h] BYREF
  unsigned __int8 GroupDefaulted[2]; // [rsp+52h] [rbp-B6h] BYREF
  ULONG v25; // [rsp+54h] [rbp-B4h]
  HANDLE Handle[2]; // [rsp+58h] [rbp-B0h] BYREF
  HANDLE v27; // [rsp+68h] [rbp-A0h]
  PSID Owner; // [rsp+70h] [rbp-98h] BYREF
  PSID Group; // [rsp+78h] [rbp-90h] BYREF
  PACL Dacl; // [rsp+80h] [rbp-88h] BYREF
  PACL Sacl; // [rsp+88h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp-48h] BYREF
  unsigned __int8 OwnerDefaulted; // [rsp+110h] [rbp+8h] BYREF
  int SaclPresent; // [rsp+120h] [rbp+18h] BYREF
  unsigned int v36; // [rsp+128h] [rbp+20h]

  v36 = a4;
  SaclPresent = a3;
  v27 = 0;
  v25 = 0;
  Owner = 0;
  Group = 0;
  Dacl = 0;
  Sacl = 0;
  DaclPresent = 0;
  DaclDefaulted = 0;
  LOBYTE(SaclPresent) = 0;
  SaclDefaulted = 0;
  OwnerDefaulted = 0;
  GroupDefaulted[0] = 0;
  memset(&ObjectAttributes, 0, 44);
  Handle[0] = 0;
  DestinationString = 0;
  if ( (unsigned __int64)(a1 - 0x80000000LL) <= 7
    && (KeyTransacted_Stub = RegRtlOpenPredefinedKey(a1, Handle), KeyTransacted_Stub < 0)
    || (KeyTransacted_Stub = RtlInitUnicodeStringEx(&DestinationString, a2), KeyTransacted_Stub < 0) )
  {
    v16 = Disposition;
    v18 = KeyHandle;
    v15 = SecurityDescriptor;
  }
  else
  {
    ObjectAttributes.Length = 48;
    v14 = (HANDLE)a1;
    if ( Handle[0] )
      v14 = Handle[0];
    ObjectAttributes.RootDirectory = v14;
    ObjectAttributes.Attributes = 192;
    ObjectAttributes.ObjectName = &DestinationString;
    v15 = SecurityDescriptor;
    ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
    ObjectAttributes.SecurityQualityOfService = 0;
    v16 = Disposition;
    v17 = a4;
    v18 = KeyHandle;
    if ( a9 )
    {
      KeyTransacted_Stub = NtCreateKeyTransacted_Stub((_DWORD)KeyHandle, v17, (unsigned int)&ObjectAttributes, v13);
      if ( KeyTransacted_Stub == -1073741702 )
        KeyTransacted_Stub = -1072103420;
    }
    else
    {
      KeyTransacted_Stub = NtCreateKey(KeyHandle, v17, &ObjectAttributes, 0, 0, 0, Disposition);
    }
  }
  if ( Handle[0] )
    NtClose(Handle[0]);
  if ( KeyTransacted_Stub == -1073741790 || KeyTransacted_Stub == -1073741734 )
  {
    v20 = RegRtlOpenProtectedKeyTransacted(a1, (__int64)a2, 0, v36, (__int64)v18);
    KeyTransacted_Stub = v20;
    if ( v20 == -1073741772 )
    {
      Handle[0] = (HANDLE)0x1200000011LL;
      Handle[0] = (HANDLE)RegRtlEnableThreadPrivileges((__int64)Handle, 2u);
      KeyTransacted_Stub = RegRtlCreateKeyTransacted(a1, a2, 4, 0, 0);
      if ( KeyTransacted_Stub >= 0 && v16 )
        *v16 = v25;
      RegRtlRestoreThreadPrivileges(Handle[0]);
      if ( KeyTransacted_Stub >= 0 )
      {
        if ( v25 == 1 && v15 )
        {
          v21 = 0;
          if ( RtlGetOwnerSecurityDescriptor(v15, &Owner, &OwnerDefaulted) >= 0 )
            v21 = Owner != 0;
          if ( RtlGetDaclSecurityDescriptor(v15, &DaclPresent, &Dacl, &DaclDefaulted) >= 0 && DaclPresent )
            v21 |= 4u;
          if ( RtlGetSaclSecurityDescriptor(v15, (PBOOLEAN)&SaclPresent, &Sacl, &SaclDefaulted) >= 0
            && (_BYTE)SaclPresent )
          {
            v21 |= 8u;
          }
          if ( RtlGetGroupSecurityDescriptor(v15, &Group, GroupDefaulted) >= 0 && Group )
            v21 |= 2u;
          RegRtlSetProtectedKeySecurity(v27, v21, v15);
        }
        KeyTransacted_Stub = RegRtlOpenProtectedKeyTransacted(
                               (__int64)v27,
                               (__int64)&dword_18008C97C,
                               0,
                               v36,
                               (__int64)v18);
      }
    }
    else if ( v20 >= 0 && v16 )
    {
      *v16 = 2;
    }
  }
  if ( v27 )
    NtClose(v27);
  return (unsigned int)KeyTransacted_Stub;
}

```

## disassembly

```asm
0x1800026b0  mov     r11, rsp
0x1800026b3  mov     [r11+20h], r9d
0x1800026b7  mov     [r11+18h], r8d
0x1800026bb  push    rbx
0x1800026bc  push    rsi
0x1800026bd  push    rdi
0x1800026be  push    r12
0x1800026c0  push    r13
0x1800026c2  push    r14
0x1800026c4  push    r15
0x1800026c6  sub     rsp, 0D0h
0x1800026cd  mov     r13d, r9d
0x1800026d0  mov     r15, rdx
0x1800026d3  mov     rbx, rcx
0x1800026d6  xor     r14d, r14d
0x1800026d9  mov     [rsp+108h+var_A0], r14
0x1800026de  mov     [rsp+108h+var_B4], r14d
0x1800026e3  mov     [rsp+108h+Owner], r14
0x1800026e8  mov     [rsp+108h+Group], r14
0x1800026ed  mov     [r11-88h], r14
0x1800026f4  mov     [r11-80h], r14
0x1800026f8  mov     [r11+30h], r14b
0x1800026fc  mov     [rsp+108h+DaclDefaulted], r14b
0x180002701  mov     [r11+18h], r14b
0x180002705  mov     [rsp+108h+SaclDefaulted], r14b
0x18000270a  mov     [r11+8], r14b
0x18000270e  mov     [rsp+108h+GroupDefaulted], r14b
0x180002713  xor     eax, eax
0x180002715  xorps   xmm0, xmm0
0x180002718  movups  xmmword ptr [r11-78h], xmm0
0x18000271d  movups  xmmword ptr [r11-68h], xmm0
0x180002722  movups  xmmword ptr [r11-5Ch], xmm0
0x180002727  mov     [rsp+108h+Handle], r14
0x18000272c  movups  xmmword ptr [r11-48h], xmm0
0x180002731  lea     rax, [rcx-80000000h]
0x180002738  cmp     rax, 7
0x18000273c  jbe     loc_180002847
0x180002742  mov     rdx, r15; SourceString
0x180002745  lea     rcx, [rsp+108h+DestinationString]; DestinationString
0x18000274d  call    cs:__imp_RtlInitUnicodeStringEx
0x180002753  mov     edi, eax
0x180002755  test    eax, eax
0x180002757  js      loc_18000285B
0x18000275d  mov     [rsp+108h+ObjectAttributes.Length], 30h ; '0'
0x180002768  mov     rcx, rbx
0x18000276b  mov     rax, [rsp+108h+Handle]
0x180002770  test    rax, rax
0x180002773  cmovnz  rcx, rax
0x180002777  mov     [rsp+108h+ObjectAttributes.RootDirectory], rcx
0x18000277f  mov     [rsp+108h+ObjectAttributes.Attributes], 0C0h
0x18000278a  lea     rax, [rsp+108h+DestinationString]
0x180002792  mov     [rsp+108h+ObjectAttributes.ObjectName], rax
0x18000279a  mov     rsi, [rsp+108h+SecurityDescriptor]
0x1800027a2  mov     [rsp+108h+ObjectAttributes.SecurityDescriptor], rsi
0x1800027aa  mov     [rsp+108h+ObjectAttributes.SecurityQualityOfService], r14
0x1800027b2  mov     r14, [rsp+108h+arg_40]
0x1800027ba  mov     r12, [rsp+108h+arg_38]
0x1800027c2  lea     r8, [rsp+108h+ObjectAttributes]; ObjectAttributes
0x1800027ca  mov     edx, r13d; DesiredAccess
0x1800027cd  mov     r13, [rsp+108h+KeyHandle]
0x1800027d5  mov     rcx, r13; KeyHandle
0x1800027d8  test    r14, r14
0x1800027db  jnz     loc_180002880
0x1800027e1  mov     [rsp+108h+Disposition], r12; Disposition
0x1800027e6  xor     eax, eax
0x1800027e8  mov     [rsp+108h+CreateOptions], eax; CreateOptions
0x1800027ec  mov     [rsp+108h+Class], rax; Class
0x1800027f1  xor     r9d, r9d; TitleIndex
0x1800027f4  call    cs:__imp_NtCreateKey
0x1800027fa  mov     edi, eax
0x1800027fc  mov     rcx, [rsp+108h+Handle]; Handle
0x180002801  test    rcx, rcx
0x180002804  jz      short loc_18000280C
0x180002806  call    cs:__imp_NtClose
0x18000280c  cmp     edi, 0C0000022h
0x180002812  jz      loc_1800028AE
0x180002818  cmp     edi, 0C000005Ah
0x18000281e  jz      loc_1800028AE
0x180002824  mov     rcx, [rsp+108h+var_A0]; Handle
0x180002829  test    rcx, rcx
0x18000282c  jnz     loc_180002A6D
0x180002832  mov     eax, edi
0x180002834  add     rsp, 0D0h
0x18000283b  pop     r15
0x18000283d  pop     r14
0x18000283f  pop     r13
0x180002841  pop     r12
0x180002843  pop     rdi
0x180002844  pop     rsi
0x180002845  pop     rbx
0x180002846  retn
0x180002847  lea     rdx, [rsp+108h+Handle]
0x18000284c  call    _RegRtlOpenPredefinedKey
0x180002851  mov     edi, eax
0x180002853  test    eax, eax
0x180002855  jns     loc_180002742
0x18000285b  mov     r14, [rsp+108h+arg_40]
0x180002863  mov     r12, [rsp+108h+arg_38]
0x18000286b  mov     r13, [rsp+108h+KeyHandle]
0x180002873  mov     rsi, [rsp+108h+SecurityDescriptor]
0x18000287b  jmp     loc_1800027FC
0x180002880  mov     [rsp+108h+var_D0], r12
0x180002885  mov     [rsp+108h+Disposition], r14
0x18000288a  mov     [rsp+108h+CreateOptions], 0
0x180002892  call    NtCreateKeyTransacted_Stub
0x180002897  mov     edi, eax
0x180002899  cmp     eax, 0C000007Ah
0x18000289e  jnz     loc_1800027FC
0x1800028a4  mov     edi, 0C0190004h
0x1800028a9  jmp     loc_1800027FC
0x1800028ae  mov     qword ptr [rsp+108h+CreateOptions], r14
0x1800028b3  mov     [rsp+108h+Class], r13
0x1800028b8  mov     r9d, [rsp+108h+arg_18]
0x1800028c0  xor     r8d, r8d
0x1800028c3  mov     rdx, r15
0x1800028c6  mov     rcx, rbx
0x1800028c9  call    _RegRtlOpenProtectedKeyTransacted
0x1800028ce  mov     edi, eax
0x1800028d0  cmp     eax, 0C0000034h
0x1800028d5  jz      short loc_1800028F5
0x1800028d7  test    eax, eax
0x1800028d9  js      loc_180002824
0x1800028df  test    r12, r12
0x1800028e2  jz      loc_180002824
0x1800028e8  mov     dword ptr [r12], 2
0x1800028f0  jmp     loc_180002824
0x1800028f5  mov     dword ptr [rsp+108h+Handle], 11h
0x1800028fd  mov     dword ptr [rsp+108h+Handle+4], 12h
0x180002905  mov     edx, 2
0x18000290a  lea     rcx, [rsp+108h+Handle]
0x18000290f  call    _RegRtlEnableThreadPrivileges
0x180002914  mov     [rsp+108h+Handle], rax
0x180002919  mov     [rsp+108h+var_C8], r14
0x18000291e  lea     rax, [rsp+108h+var_B4]
0x180002923  mov     [rsp+108h+var_D0], rax
0x180002928  lea     rax, [rsp+108h+var_A0]
0x18000292d  mov     [rsp+108h+Disposition], rax
0x180002932  mov     [rsp+108h+Class], 0
0x18000293b  xor     r9d, r9d
0x18000293e  mov     r8d, 4
0x180002944  mov     rdx, r15
0x180002947  mov     rcx, rbx
0x18000294a  call    _RegRtlCreateKeyTransacted
0x18000294f  mov     edi, eax
0x180002951  test    eax, eax
0x180002953  js      short loc_180002962
0x180002955  test    r12, r12
0x180002958  jz      short loc_180002962
0x18000295a  mov     eax, [rsp+108h+var_B4]
0x18000295e  mov     [r12], eax
0x180002962  mov     rcx, [rsp+108h+Handle]
0x180002967  call    _RegRtlRestoreThreadPrivileges
0x18000296c  test    edi, edi
0x18000296e  js      loc_180002824
0x180002974  cmp     [rsp+108h+var_B4], 1
0x180002979  jnz     loc_180002A40
0x18000297f  test    rsi, rsi
0x180002982  jz      loc_180002A40
0x180002988  xor     ebx, ebx
0x18000298a  lea     r8, [rsp+108h+OwnerDefaulted]; OwnerDefaulted
0x180002992  lea     rdx, [rsp+108h+Owner]; Owner
0x180002997  mov     rcx, rsi; SecurityDescriptor
0x18000299a  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x1800029a0  test    eax, eax
0x1800029a2  js      short loc_1800029B1
0x1800029a4  mov     eax, 1
0x1800029a9  cmp     [rsp+108h+Owner], rbx
0x1800029ae  cmovnz  ebx, eax
0x1800029b1  lea     r9, [rsp+108h+DaclDefaulted]; DaclDefaulted
0x1800029b6  lea     r8, [rsp+108h+Dacl]; Dacl
0x1800029be  lea     rdx, [rsp+108h+DaclPresent]; DaclPresent
0x1800029c6  mov     rcx, rsi; SecurityDescriptor
0x1800029c9  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1800029cf  test    eax, eax
0x1800029d1  js      short loc_1800029E0
0x1800029d3  cmp     [rsp+108h+DaclPresent], 0
0x1800029db  jz      short loc_1800029E0
0x1800029dd  or      ebx, 4
0x1800029e0  lea     r9, [rsp+108h+SaclDefaulted]; SaclDefaulted
0x1800029e5  lea     r8, [rsp+108h+Sacl]; Sacl
0x1800029ed  lea     rdx, [rsp+108h+SaclPresent]; SaclPresent
0x1800029f5  mov     rcx, rsi; SecurityDescriptor
0x1800029f8  call    cs:__imp_RtlGetSaclSecurityDescriptor
0x1800029fe  test    eax, eax
0x180002a00  js      short loc_180002A0F
0x180002a02  cmp     byte ptr [rsp+108h+SaclPresent], 0
0x180002a0a  jz      short loc_180002A0F
0x180002a0c  or      ebx, 8
0x180002a0f  lea     r8, [rsp+108h+GroupDefaulted]; GroupDefaulted
0x180002a14  lea     rdx, [rsp+108h+Group]; Group
0x180002a19  mov     rcx, rsi; SecurityDescriptor
0x180002a1c  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x180002a22  test    eax, eax
0x180002a24  js      short loc_180002A31
0x180002a26  cmp     [rsp+108h+Group], 0
0x180002a2c  jz      short loc_180002A31
0x180002a2e  or      ebx, 2
0x180002a31  mov     r8, rsi; SecurityDescriptor
0x180002a34  mov     edx, ebx; SecurityInformation
0x180002a36  mov     rcx, [rsp+108h+var_A0]; Handle
0x180002a3b  call    _RegRtlSetProtectedKeySecurity
0x180002a40  mov     qword ptr [rsp+108h+CreateOptions], r14
0x180002a45  mov     [rsp+108h+Class], r13
0x180002a4a  mov     r9d, [rsp+108h+arg_18]
0x180002a52  xor     r8d, r8d
0x180002a55  lea     rdx, dword_18008C97C
0x180002a5c  mov     rcx, [rsp+108h+var_A0]
0x180002a61  call    _RegRtlOpenProtectedKeyTransacted
0x180002a66  mov     edi, eax
0x180002a68  jmp     loc_180002824
0x180002a6d  call    cs:__imp_NtClose
0x180002a73  jmp     loc_180002832
0x18007ea80  push    rbp
0x18007ea82  sub     rsp, 50h
0x18007ea86  mov     rbp, rdx
0x18007ea89  mov     rcx, [rbp+58h]
0x18007ea8d  call    _RegRtlRestoreThreadPrivileges
0x18007ea92  nop
0x18007ea93  add     rsp, 50h
0x18007ea97  pop     rbp
0x18007ea98  retn
```
