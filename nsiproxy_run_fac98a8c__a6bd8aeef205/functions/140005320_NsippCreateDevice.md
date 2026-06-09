# NsippCreateDevice

- ea: `0x140005320`
- end: `0x1400055ac`
- name: `NsippCreateDevice`
- size: `652`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x14000f078`

## callees

- `0x140005320`
- `0x1400055c0`
- `0x1400058c0`
- `0x140006530`
- `0x14000d010`

## import_xrefs

- `ntoskrnl!SeConvertStringSecurityDescriptorToSecurityDescriptor` at `0x1400054c7`
- `ntoskrnl!SeConvertStringSecurityDescriptorToSecurityDescriptor` at `0x1400054c7`
- `ntoskrnl!RtlInitUnicodeString` at `0x140005479`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400054f3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140005479`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400054f3`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140005508`
- `ntoskrnl!IoCreateSymbolicLink` at `0x140005508`
- `ntoskrnl!IoDeleteDevice` at `0x14000554b`
- `ntoskrnl!IoDeleteDevice` at `0x14000554b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005573`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005573`

## pseudocode

```c
__int64 __fastcall NsippCreateDevice(PDRIVER_OBJECT DriverObject)
{
  PDRIVER_OBJECT v1; // rdi
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  ULONG v5; // edx
  ULONG v6; // r9d
  int v7; // ebx
  __int64 v8; // rcx
  int v9; // r8d
  int v10; // r9d
  __int64 i; // rdi
  void *v12; // rcx
  ULONG v14; // [rsp+20h] [rbp-E0h]
  BOOLEAN v15; // [rsp+28h] [rbp-D8h]
  const GUID *v16; // [rsp+38h] [rbp-C8h]
  PDEVICE_OBJECT *v17; // [rsp+40h] [rbp-C0h]
  int v18; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD v19[4]; // [rsp+58h] [rbp-A8h] BYREF
  UNICODE_STRING DefaultSDDLString; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  PVOID P; // [rsp+88h] [rbp-78h] BYREF
  __int128 v23; // [rsp+90h] [rbp-70h]
  __int64 CapabilitySid; // [rsp+A0h] [rbp-60h]
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+A8h] [rbp-58h] BYREF
  _OWORD v26[8]; // [rsp+C0h] [rbp-40h] BYREF

  *(_QWORD *)&DefaultSDDLString.Length = 8388734;
  DestinationString = 0;
  v1 = DriverObject;
  v26[0] = *(_OWORD *)L"D:P(A;;GX;;;WD)(A;;GA;;;SY)(A;;GA;;;BA)(A;;GX;;;RC)(A;;GX;;;AC)";
  LOBYTE(DriverObject) = 1;
  SymbolicLinkName = 0;
  DefaultSDDLString.Buffer = (wchar_t *)v26;
  v26[2] = *(_OWORD *)L"A;;GA;;;SY)(A;;GA;;;BA)(A;;GX;;;RC)(A;;GX;;;AC)";
  v26[1] = *(_OWORD *)L"X;;;WD)(A;;GA;;;SY)(A;;GA;;;BA)(A;;GX;;;RC)(A;;GX;;;AC)";
  v26[4] = *(_OWORD *)L"A;;;BA)(A;;GX;;;RC)(A;;GX;;;AC)";
  v26[3] = *(_OWORD *)L"SY)(A;;GA;;;BA)(A;;GX;;;RC)(A;;GX;;;AC)";
  v26[6] = *(_OWORD *)L"RC)(A;;GX;;;AC)";
  v26[5] = *(_OWORD *)L"A;;GX;;;RC)(A;;GX;;;AC)";
  v23 = 0;
  CapabilitySid = 0;
  v26[7] = *(_OWORD *)L"X;;;AC)";
  v18 = 1;
  P = (PVOID)AllocateCapabilitySid(DriverObject, &v18);
  if ( !P )
    goto LABEL_10;
  v18 = 2;
  LOBYTE(v2) = 1;
  *(_QWORD *)&v23 = AllocateCapabilitySid(v2, &v18);
  if ( !(_QWORD)v23 )
    goto LABEL_10;
  v18 = 3;
  LOBYTE(v3) = 1;
  *((_QWORD *)&v23 + 1) = AllocateCapabilitySid(v3, &v18);
  if ( !*((_QWORD *)&v23 + 1) )
    goto LABEL_10;
  v19[0] = -80198963;
  LOBYTE(v4) = 4;
  v19[1] = 1334025770;
  v19[2] = 122408079;
  v19[3] = -375778463;
  CapabilitySid = AllocateCapabilitySid(v4, v19);
  if ( CapabilitySid )
  {
    RtlInitUnicodeString(&DestinationString, L"\\Device\\Nsi");
    v7 = WdmlibIoCreateDeviceSecure(v1, v5, &DestinationString, v6, v14, v15, &DefaultSDDLString, v16, v17);
    if ( v7 < 0 )
      goto LABEL_13;
    NsiServiceSecurityDescriptor = 0;
    v7 = SeConvertStringSecurityDescriptorToSecurityDescriptor(
           L"D:P(A;;FA;;;S-1-5-80-2310782386-4237065203-3688974353-390202159-3511571085)",
           1,
           &NsiServiceSecurityDescriptor,
           0);
    if ( v7 >= 0 )
    {
      v7 = ApplySecurityToDeviceObject(v8, (__int64)&P, v9, v10);
      if ( v7 >= 0 )
      {
        RtlInitUnicodeString(&SymbolicLinkName, L"\\??\\Nsi");
        v7 = IoCreateSymbolicLink(&SymbolicLinkName, &DestinationString);
        if ( v7 >= 0 )
        {
          NsiProxyDeviceObject->Flags |= 0x10u;
          memset64(v1->MajorFunction, (unsigned __int64)&NsippDispatch, 0x1Cu);
          goto LABEL_13;
        }
      }
    }
  }
  else
  {
LABEL_10:
    v7 = -1073741670;
  }
  if ( NsiProxyDeviceObject )
  {
    IoDeleteDevice(NsiProxyDeviceObject);
    NsiProxyDeviceObject = 0;
  }
LABEL_13:
  for ( i = 0; i != 4; ++i )
  {
    v12 = *(&P + i);
    if ( v12 )
      ExFreePoolWithTag(v12, 0x6770534Eu);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140005320  mov     [rsp-8+arg_8], rbx
0x140005325  mov     [rsp-8+arg_10], rdi
0x14000532a  push    rbp
0x14000532b  lea     rbp, [rsp-50h]
0x140005330  sub     rsp, 150h
0x140005337  mov     rax, cs:__security_cookie
0x14000533e  xor     rax, rsp
0x140005341  mov     [rbp+50h+var_10], rax
0x140005345  xorps   xmm0, xmm0
0x140005348  mov     qword ptr [rsp+150h+var_E8.Length], 80007Eh
0x140005351  movups  xmmword ptr [rsp+150h+DestinationString.Length], xmm0
0x140005356  lea     rax, [rbp+50h+var_90]
0x14000535a  mov     rdi, rcx
0x14000535d  movaps  xmm0, xmmword ptr cs:aDPAGxWdAGaSyAG; "D:P(A;;GX;;;WD)(A;;GA;;;SY)(A;;GA;;;BA)"...
0x140005364  lea     rdx, [rsp+150h+var_100]
0x140005369  xorps   xmm1, xmm1
0x14000536c  movaps  [rbp+50h+var_90], xmm0
0x140005370  movaps  xmm0, xmmword ptr cs:aDPAGxWdAGaSyAG+20h; "A;;GA;;;SY)(A;;GA;;;BA)(A;;GX;;;RC)(A;;"...
0x140005377  mov     cl, 1
0x140005379  movups  xmmword ptr [rbp+50h+SymbolicLinkName.Length], xmm1
0x14000537d  mov     [rsp+150h+var_E8.Buffer], rax
0x140005382  movaps  xmm1, xmmword ptr cs:aDPAGxWdAGaSyAG+10h; "X;;;WD)(A;;GA;;;SY)(A;;GA;;;BA)(A;;GX;;"...
0x140005389  movaps  [rbp+50h+var_70], xmm0
0x14000538d  movaps  xmm0, xmmword ptr cs:aDPAGxWdAGaSyAG+40h; "A;;;BA)(A;;GX;;;RC)(A;;GX;;;AC)"
0x140005394  movaps  [rbp+50h+var_80], xmm1
0x140005398  movaps  xmm1, xmmword ptr cs:aDPAGxWdAGaSyAG+30h; "SY)(A;;GA;;;BA)(A;;GX;;;RC)(A;;GX;;;AC)"
0x14000539f  movaps  [rbp+50h+var_50], xmm0
0x1400053a3  movaps  xmm0, xmmword ptr cs:aDPAGxWdAGaSyAG+60h; "RC)(A;;GX;;;AC)"
0x1400053aa  movaps  [rbp+50h+var_60], xmm1
0x1400053ae  movaps  xmm1, xmmword ptr cs:aDPAGxWdAGaSyAG+50h; "A;;GX;;;RC)(A;;GX;;;AC)"
0x1400053b5  movaps  [rbp+50h+var_30], xmm0
0x1400053b9  xorps   xmm0, xmm0
0x1400053bc  movaps  [rbp+50h+var_40], xmm1
0x1400053c0  movaps  xmm1, xmmword ptr cs:aDPAGxWdAGaSyAG+70h; "X;;;AC)"
0x1400053c7  movdqu  [rbp+50h+var_C0], xmm0
0x1400053cc  mov     [rbp+50h+var_B0], 0
0x1400053d4  movaps  [rbp+50h+var_20], xmm1
0x1400053d8  mov     [rsp+150h+var_100], 1
0x1400053e0  call    AllocateCapabilitySid
0x1400053e5  mov     [rbp+50h+P], rax
0x1400053e9  test    rax, rax
0x1400053ec  jz      loc_14000553A
0x1400053f2  lea     rdx, [rsp+150h+var_100]
0x1400053f7  mov     [rsp+150h+var_100], 2
0x1400053ff  mov     cl, 1
0x140005401  call    AllocateCapabilitySid
0x140005406  mov     qword ptr [rbp+50h+var_C0], rax
0x14000540a  test    rax, rax
0x14000540d  jz      loc_14000553A
0x140005413  lea     rdx, [rsp+150h+var_100]
0x140005418  mov     [rsp+150h+var_100], 3
0x140005420  mov     cl, 1
0x140005422  call    AllocateCapabilitySid
0x140005427  mov     qword ptr [rbp+50h+var_C0+8], rax
0x14000542b  test    rax, rax
0x14000542e  jz      loc_14000553A
0x140005434  lea     rdx, [rsp+150h+var_F8]
0x140005439  mov     [rsp+150h+var_F8], 0FB3842CDh
0x140005441  mov     cl, 4
0x140005443  mov     [rsp+150h+var_F4], 4F839E2Ah
0x14000544b  mov     [rsp+150h+var_F0], 74BCC8Fh
0x140005453  mov     [rsp+150h+var_EC], 0E99A1361h
0x14000545b  call    AllocateCapabilitySid
0x140005460  mov     [rbp+50h+var_B0], rax
0x140005464  test    rax, rax
0x140005467  jz      loc_14000553A
0x14000546d  lea     rdx, SourceString; "\\Device\\Nsi"
0x140005474  lea     rcx, [rsp+150h+DestinationString]; DestinationString
0x140005479  call    cs:__imp_RtlInitUnicodeString
0x140005480  nop     dword ptr [rax+rax+00h]
0x140005485  lea     rax, [rsp+150h+var_E8]
0x14000548a  mov     rcx, rdi; DriverObject
0x14000548d  lea     r8, [rsp+150h+DestinationString]; DeviceName
0x140005492  mov     [rsp+150h+DefaultSDDLString], rax; DefaultSDDLString
0x140005497  call    WdmlibIoCreateDeviceSecure
0x14000549c  mov     ebx, eax
0x14000549e  test    eax, eax
0x1400054a0  js      loc_140005562
0x1400054a6  xor     r9d, r9d
0x1400054a9  mov     cs:NsiServiceSecurityDescriptor, 0
0x1400054b4  lea     r8, NsiServiceSecurityDescriptor
0x1400054bb  mov     edx, 1
0x1400054c0  lea     rcx, aDPAFaS15802310; "D:P(A;;FA;;;S-1-5-80-2310782386-4237065"...
0x1400054c7  call    cs:__imp_SeConvertStringSecurityDescriptorToSecurityDescriptor
0x1400054ce  nop     dword ptr [rax+rax+00h]
0x1400054d3  mov     ebx, eax
0x1400054d5  test    eax, eax
0x1400054d7  js      short loc_14000553F
0x1400054d9  lea     rdx, [rbp+50h+P]
0x1400054dd  call    ApplySecurityToDeviceObject
0x1400054e2  mov     ebx, eax
0x1400054e4  test    eax, eax
0x1400054e6  js      short loc_14000553F
0x1400054e8  lea     rdx, aNsi; "\\??\\Nsi"
0x1400054ef  lea     rcx, [rbp+50h+SymbolicLinkName]; DestinationString
0x1400054f3  call    cs:__imp_RtlInitUnicodeString
0x1400054fa  nop     dword ptr [rax+rax+00h]
0x1400054ff  lea     rdx, [rsp+150h+DestinationString]; DeviceName
0x140005504  lea     rcx, [rbp+50h+SymbolicLinkName]; SymbolicLinkName
0x140005508  call    cs:__imp_IoCreateSymbolicLink
0x14000550f  nop     dword ptr [rax+rax+00h]
0x140005514  mov     ebx, eax
0x140005516  test    eax, eax
0x140005518  js      short loc_14000553F
0x14000551a  mov     rax, cs:NsiProxyDeviceObject
0x140005521  mov     ecx, 1Ch
0x140005526  or      dword ptr [rax+30h], 10h
0x14000552a  lea     rax, NsippDispatch
0x140005531  add     rdi, 70h ; 'p'
0x140005535  rep stosq
0x140005538  jmp     short loc_140005562
0x14000553a  mov     ebx, 0C000009Ah
0x14000553f  mov     rcx, cs:NsiProxyDeviceObject; DeviceObject
0x140005546  test    rcx, rcx
0x140005549  jz      short loc_140005562
0x14000554b  call    cs:__imp_IoDeleteDevice
0x140005552  nop     dword ptr [rax+rax+00h]
0x140005557  mov     cs:NsiProxyDeviceObject, 0
0x140005562  xor     edi, edi
0x140005564  mov     rcx, [rbp+rdi*8+50h+P]; P
0x140005569  test    rcx, rcx
0x14000556c  jz      short loc_14000557F
0x14000556e  mov     edx, 6770534Eh; Tag
0x140005573  call    cs:__imp_ExFreePoolWithTag
0x14000557a  nop     dword ptr [rax+rax+00h]
0x14000557f  inc     rdi
0x140005582  cmp     rdi, 4
0x140005586  jnz     short loc_140005564
0x140005588  mov     eax, ebx
0x14000558a  mov     rcx, [rbp+50h+var_10]
0x14000558e  xor     rcx, rsp; StackCookie
0x140005591  call    __security_check_cookie
0x140005596  lea     r11, [rsp+150h+var_s0]
0x14000559e  mov     rbx, [r11+18h]
0x1400055a2  mov     rdi, [r11+20h]
0x1400055a6  mov     rsp, r11
0x1400055a9  pop     rbp
0x1400055aa  retn
```
