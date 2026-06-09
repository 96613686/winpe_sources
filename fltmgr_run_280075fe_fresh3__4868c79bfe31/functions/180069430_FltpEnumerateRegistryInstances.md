# FltpEnumerateRegistryInstances

- ea: `0x180069430`
- end: `0x1800698bb`
- name: `FltpEnumerateRegistryInstances`
- size: `1163`
- prototype: `__int64 __fastcall(PVOID FltObject)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180056ad8`
- `0x180069170`

## callees

- `0x180009f20`
- `0x1800247a0`
- `0x180069430`
- `0x1800698d0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1800697df`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006985d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800697df`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006985d`
- `ntoskrnl!ExAllocatePool2` at `0x1800696bd`
- `ntoskrnl!ExAllocatePool2` at `0x18006987a`
- `ntoskrnl!ExAllocatePool2` at `0x1800696bd`
- `ntoskrnl!ExAllocatePool2` at `0x18006987a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800695a4`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800695a4`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800695bd`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800695bd`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800694ab`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800694ab`
- `ntoskrnl!ZwClose` at `0x180069540`
- `ntoskrnl!ZwClose` at `0x180069670`
- `ntoskrnl!ZwClose` at `0x180069825`
- `ntoskrnl!ZwClose` at `0x180069540`
- `ntoskrnl!ZwClose` at `0x180069670`
- `ntoskrnl!ZwClose` at `0x180069825`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x1800694cf`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x1800694cf`
- `ntoskrnl!ZwOpenKey` at `0x18006952d`
- `ntoskrnl!ZwOpenKey` at `0x1800695fa`
- `ntoskrnl!ZwOpenKey` at `0x180069658`
- `ntoskrnl!ZwOpenKey` at `0x18006952d`
- `ntoskrnl!ZwOpenKey` at `0x1800695fa`
- `ntoskrnl!ZwOpenKey` at `0x180069658`
- `ntoskrnl!ZwEnumerateKey` at `0x1800696f1`
- `ntoskrnl!ZwEnumerateKey` at `0x1800696f1`

## string_xrefs

- `0x180069573`: `\Registry\Machine\System\ControlSet001\Services\`

## pseudocode

```c
__int64 __fastcall FltpEnumerateRegistryInstances(_QWORD *FltObject, void *a2, char a3)
{
  __int64 v3; // rbx
  ULONG v6; // r14d
  unsigned int v8; // edi
  ULONG Length; // esi
  unsigned __int16 *Pool2; // rdi
  unsigned int v11; // ebx
  unsigned int v12; // eax
  HANDLE Handle; // [rsp+68h] [rbp-A0h] BYREF
  ULONG ResultLength[2]; // [rsp+70h] [rbp-98h] BYREF
  void *KeyHandle[2]; // [rsp+78h] [rbp-90h] BYREF
  char *v17; // [rsp+88h] [rbp-80h]
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-78h] BYREF
  UNICODE_STRING SourceString; // [rsp+C0h] [rbp-48h] BYREF
  UNICODE_STRING DestinationString; // [rsp+D0h] [rbp-38h] BYREF
  OBJECT_ATTRIBUTES v21; // [rsp+E0h] [rbp-28h] BYREF
  char v22; // [rsp+118h] [rbp+10h] BYREF

  v3 = FltObject[13];
  v6 = 0;
  KeyHandle[0] = 0;
  ResultLength[0] = 0;
  SourceString = 0;
  Handle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, L"INSTANCES");
  v8 = IoOpenDriverRegistryKey(v3, 0, 131097, 0, &Handle);
  if ( (int)FltpDbgStatus(v8, "minkernel\\fs\\filtermgr\\filter\\instancesup.c", 991, 0) >= 0 )
  {
    ObjectAttributes.RootDirectory = Handle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v8 = ZwOpenKey(KeyHandle, 0x20019u, &ObjectAttributes);
    ZwClose(Handle);
    Handle = 0;
  }
  if ( (int)FltpDbgStatus(v8, "minkernel\\fs\\filtermgr\\filter\\instancesup.c", 1017, 0) < 0 )
  {
    KeyHandle[1] = (void *)20971520;
    v17 = &v22;
    memset(&v21, 0, 44);
    RtlAppendUnicodeToString((PUNICODE_STRING)&KeyHandle[1], L"\\Registry\\Machine\\System\\ControlSet001\\Services\\");
    RtlAppendUnicodeStringToString((PUNICODE_STRING)&KeyHandle[1], (PCUNICODE_STRING)(*(_QWORD *)(v3 + 48) + 24LL));
    v21.Length = 48;
    v21.ObjectName = (PUNICODE_STRING)&KeyHandle[1];
    v21.RootDirectory = 0;
    v21.Attributes = 576;
    *(_OWORD *)&v21.SecurityDescriptor = 0;
    v8 = ZwOpenKey(&Handle, 0x20019u, &v21);
    if ( (int)FltpDbgStatus(v8, "minkernel\\fs\\filtermgr\\filter\\instancesup.c", 1021, 0) >= 0 )
    {
      ObjectAttributes.RootDirectory = Handle;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v8 = ZwOpenKey(KeyHandle, 0x20019u, &ObjectAttributes);
    }
  }
  if ( Handle )
    ZwClose(Handle);
  if ( (int)FltpDbgStatus(v8, "minkernel\\fs\\filtermgr\\filter\\instancesup.c", 803, 3221225524LL) < 0 )
  {
    v11 = 0;
    if ( v8 != -1073741772 )
      v11 = v8;
  }
  else
  {
    Length = 80;
    Pool2 = (unsigned __int16 *)ExAllocatePool2(256, 80, 1920224582);
    if ( Pool2 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          v11 = ZwEnumerateKey(KeyHandle[0], v6, KeyBasicInformation, Pool2, Length, ResultLength);
          if ( (int)FltpDbgStatus(v11, "minkernel\\fs\\filtermgr\\filter\\instancesup.c", 849, 2147483674LL) < 0 )
            break;
          SourceString.Length = Pool2[6];
          SourceString.MaximumLength = SourceString.Length;
          SourceString.Buffer = Pool2 + 8;
          v12 = FltpCreateInstanceFromName(FltObject, a2, a3, KeyHandle[0], &SourceString, 0, 0);
          FltpDbgStatus(v12, "minkernel\\fs\\filtermgr\\filter\\instancesup.c", 916, 3223060495LL);
          ++v6;
        }
        if ( v11 == -2147483622 )
          break;
        if ( v11 != -1073741789 && v11 != -2147483643 )
          goto LABEL_14;
        ExFreePoolWithTag(Pool2, 0x72744D46u);
        Length = ResultLength[0];
        Pool2 = (unsigned __int16 *)ExAllocatePool2(256, ResultLength[0], 1920224582);
        if ( !Pool2 )
          goto LABEL_20;
      }
      v11 = 0;
LABEL_14:
      ExFreePoolWithTag(Pool2, 0x72744D46u);
    }
    else
    {
LABEL_20:
      v11 = -1073741670;
    }
  }
  if ( KeyHandle[0] )
    ZwClose(KeyHandle[0]);
  return v11;
}

```

## disassembly

```asm
0x180069430  mov     r11, rsp
0x180069433  push    rbp
0x180069434  push    rbx
0x180069435  lea     rbp, [r11-198h]
0x18006943c  sub     rsp, 288h
0x180069443  mov     rax, cs:__security_cookie
0x18006944a  xor     rax, rsp
0x18006944d  mov     [rbp+190h+var_40], rax
0x180069454  mov     rbx, [rcx+68h]
0x180069458  xorps   xmm0, xmm0
0x18006945b  mov     [r11-18h], rdi
0x18006945f  xor     eax, eax
0x180069461  mov     [r11-20h], r12
0x180069465  mov     r12, rdx
0x180069468  mov     [r11-28h], r13
0x18006946c  lea     rdx, FltpRegFilterInstancesSubKey; "INSTANCES"
0x180069473  mov     [r11-30h], r14
0x180069477  mov     r13d, r8d
0x18006947a  xor     r14d, r14d
0x18006947d  mov     [r11-38h], r15
0x180069481  mov     r15, rcx
0x180069484  mov     [rsp+290h+KeyHandle], r14
0x180069489  movups  xmmword ptr [rbp+190h+ObjectAttributes.ObjectName], xmm0
0x18006948d  lea     rcx, [rbp+190h+DestinationString]; DestinationString
0x180069491  mov     [rsp+290h+var_228], r14d
0x180069496  movups  xmmword ptr [rbp+190h+SourceString.Length], xmm0
0x18006949a  mov     [rsp+290h+Handle], r14
0x18006949f  movups  xmmword ptr [rbp+190h+DestinationString.Length], xmm0
0x1800694a3  movups  xmmword ptr [rbp+190h+ObjectAttributes.Length], xmm0
0x1800694a7  movups  xmmword ptr [rbp+190h+ObjectAttributes+1Ch], xmm0
0x1800694ab  call    cs:__imp_RtlInitUnicodeString
0x1800694b2  nop     dword ptr [rax+rax+00h]
0x1800694b7  lea     rax, [rsp+290h+Handle]
0x1800694bc  xor     r9d, r9d
0x1800694bf  xor     edx, edx
0x1800694c1  mov     qword ptr [rsp+290h+Length], rax
0x1800694c6  mov     r8d, 20019h
0x1800694cc  mov     rcx, rbx
0x1800694cf  call    cs:__imp_IoOpenDriverRegistryKey
0x1800694d6  nop     dword ptr [rax+rax+00h]
0x1800694db  mov     r8d, 3DFh
0x1800694e1  lea     rdx, aMinkernelFsFil_19; "minkernel\\fs\\filtermgr\\filter\\insta"...
0x1800694e8  mov     ecx, eax
0x1800694ea  xor     r9d, r9d
0x1800694ed  mov     edi, eax
0x1800694ef  call    FltpDbgStatus
0x1800694f4  test    eax, eax
0x1800694f6  js      short loc_180069551
0x1800694f8  mov     rax, [rsp+290h+Handle]
0x1800694fd  lea     r8, [rbp+190h+ObjectAttributes]; ObjectAttributes
0x180069501  mov     [rbp+190h+ObjectAttributes.RootDirectory], rax
0x180069505  lea     rcx, [rsp+290h+KeyHandle]; KeyHandle
0x18006950a  lea     rax, [rbp+190h+DestinationString]
0x18006950e  mov     [rbp+190h+ObjectAttributes.Length], 30h ; '0'
0x180069515  xorps   xmm0, xmm0
0x180069518  mov     [rbp+190h+ObjectAttributes.ObjectName], rax
0x18006951c  mov     edx, 20019h; DesiredAccess
0x180069521  mov     [rbp+190h+ObjectAttributes.Attributes], 240h
0x180069528  movdqu  xmmword ptr [rbp+190h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006952d  call    cs:__imp_ZwOpenKey
0x180069534  nop     dword ptr [rax+rax+00h]
0x180069539  mov     rcx, [rsp+290h+Handle]; Handle
0x18006953e  mov     edi, eax
0x180069540  call    cs:__imp_ZwClose
0x180069547  nop     dword ptr [rax+rax+00h]
0x18006954c  mov     [rsp+290h+Handle], r14
0x180069551  mov     r8d, 3F9h
0x180069557  lea     rdx, aMinkernelFsFil_19; "minkernel\\fs\\filtermgr\\filter\\insta"...
0x18006955e  xor     r9d, r9d
0x180069561  mov     ecx, edi
0x180069563  call    FltpDbgStatus
0x180069568  test    eax, eax
0x18006956a  jns     loc_180069666
0x180069570  xorps   xmm0, xmm0
0x180069573  lea     rdx, FltpServicesRegistryPathDesktop; "\\Registry\\Machine\\System\\ControlSet"...
0x18006957a  xor     eax, eax
0x18006957c  lea     rcx, [rsp+290h+KeyHandle+8]; Destination
0x180069581  movups  xmmword ptr [rsp+290h+KeyHandle+8], xmm0
0x180069586  mov     eax, 140h
0x18006958b  mov     word ptr [rsp+290h+KeyHandle+0Ah], ax
0x180069590  lea     rax, [rbp+190h+var_180]
0x180069594  movups  xmmword ptr [rbp+190h+var_1B8.ObjectName], xmm0
0x180069598  mov     [rbp+190h+var_210], rax
0x18006959c  movups  xmmword ptr [rbp+190h+var_1B8.Length], xmm0
0x1800695a0  movups  xmmword ptr [rbp+190h+var_1B8+1Ch], xmm0
0x1800695a4  call    cs:__imp_RtlAppendUnicodeToString
0x1800695ab  nop     dword ptr [rax+rax+00h]
0x1800695b0  mov     rdx, [rbx+30h]
0x1800695b4  lea     rcx, [rsp+290h+KeyHandle+8]; Destination
0x1800695b9  add     rdx, 18h; Source
0x1800695bd  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800695c4  nop     dword ptr [rax+rax+00h]
0x1800695c9  lea     rax, [rsp+290h+KeyHandle+8]
0x1800695ce  mov     [rbp+190h+var_1B8.Length], 30h ; '0'
0x1800695d5  xorps   xmm0, xmm0
0x1800695d8  mov     [rbp+190h+var_1B8.ObjectName], rax
0x1800695dc  lea     r8, [rbp+190h+var_1B8]; ObjectAttributes
0x1800695e0  mov     [rbp+190h+var_1B8.RootDirectory], r14
0x1800695e4  mov     edx, 20019h; DesiredAccess
0x1800695e9  mov     [rbp+190h+var_1B8.Attributes], 240h
0x1800695f0  lea     rcx, [rsp+290h+Handle]; KeyHandle
0x1800695f5  movdqu  xmmword ptr [rbp+190h+var_1B8.SecurityDescriptor], xmm0
0x1800695fa  call    cs:__imp_ZwOpenKey
0x180069601  nop     dword ptr [rax+rax+00h]
0x180069606  mov     r8d, 3FDh
0x18006960c  lea     rdx, aMinkernelFsFil_19; "minkernel\\fs\\filtermgr\\filter\\insta"...
0x180069613  mov     ecx, eax
0x180069615  xor     r9d, r9d
0x180069618  mov     edi, eax
0x18006961a  call    FltpDbgStatus
0x18006961f  test    eax, eax
0x180069621  js      short loc_180069666
0x180069623  mov     rax, [rsp+290h+Handle]
0x180069628  lea     r8, [rbp+190h+ObjectAttributes]; ObjectAttributes
0x18006962c  mov     [rbp+190h+ObjectAttributes.RootDirectory], rax
0x180069630  lea     rcx, [rsp+290h+KeyHandle]; KeyHandle
0x180069635  lea     rax, [rbp+190h+DestinationString]
0x180069639  mov     [rbp+190h+ObjectAttributes.Length], 30h ; '0'
0x180069640  xorps   xmm0, xmm0
0x180069643  mov     [rbp+190h+ObjectAttributes.ObjectName], rax
0x180069647  mov     edx, 20019h; DesiredAccess
0x18006964c  mov     [rbp+190h+ObjectAttributes.Attributes], 240h
0x180069653  movdqu  xmmword ptr [rbp+190h+ObjectAttributes.SecurityDescriptor], xmm0
0x180069658  call    cs:__imp_ZwOpenKey
0x18006965f  nop     dword ptr [rax+rax+00h]
0x180069664  mov     edi, eax
0x180069666  mov     rcx, [rsp+290h+Handle]; Handle
0x18006966b  test    rcx, rcx
0x18006966e  jz      short loc_18006967C
0x180069670  call    cs:__imp_ZwClose
0x180069677  nop     dword ptr [rax+rax+00h]
0x18006967c  mov     r8d, 323h
0x180069682  mov     qword ptr [rsp+290h+Length], r14
0x180069687  mov     r9d, 0C0000034h
0x18006968d  lea     rdx, aMinkernelFsFil_19; "minkernel\\fs\\filtermgr\\filter\\insta"...
0x180069694  mov     ecx, edi
0x180069696  call    FltpDbgStatus
0x18006969b  test    eax, eax
0x18006969d  js      loc_1800698AA
0x1800696a3  mov     [rsp+290h+arg_18], rsi
0x1800696ab  mov     r8d, 72744D46h
0x1800696b1  mov     esi, 50h ; 'P'
0x1800696b6  mov     ecx, 100h
0x1800696bb  mov     edx, esi
0x1800696bd  call    cs:__imp_ExAllocatePool2
0x1800696c4  nop     dword ptr [rax+rax+00h]
0x1800696c9  mov     rdi, rax
0x1800696cc  test    rax, rax
0x1800696cf  jz      loc_180069892
0x1800696d5  mov     rcx, [rsp+290h+KeyHandle]; KeyHandle
0x1800696da  lea     rax, [rsp+290h+var_228]
0x1800696df  mov     [rsp+290h+ResultLength], rax; ResultLength
0x1800696e4  mov     r9, rdi; KeyInformation
0x1800696e7  xor     r8d, r8d; KeyInformationClass
0x1800696ea  mov     [rsp+290h+Length], esi; Length
0x1800696ee  mov     edx, r14d; Index
0x1800696f1  call    cs:__imp_ZwEnumerateKey
0x1800696f8  nop     dword ptr [rax+rax+00h]
0x1800696fd  mov     [rsp+290h+var_260], 0
0x180069706  lea     rdx, aMinkernelFsFil_19; "minkernel\\fs\\filtermgr\\filter\\insta"...
0x18006970d  mov     ecx, eax
0x18006970f  mov     dword ptr [rsp+290h+ResultLength], 80000005h
0x180069717  mov     r9d, 8000001Ah
0x18006971d  mov     [rsp+290h+Length], 0C0000023h
0x180069725  mov     r8d, 351h
0x18006972b  mov     ebx, eax
0x18006972d  call    FltpDbgStatus
0x180069732  test    eax, eax
0x180069734  js      loc_1800697CD
0x18006973a  movzx   eax, word ptr [rdi+0Ch]
0x18006973e  xor     ebx, ebx
0x180069740  mov     r9, [rsp+290h+KeyHandle]
0x180069745  mov     r8d, r13d
0x180069748  mov     [rbp+190h+SourceString.Length], ax
0x18006974c  mov     rdx, r12
0x18006974f  mov     [rbp+190h+SourceString.MaximumLength], ax
0x180069753  mov     rcx, r15; FltObject
0x180069756  lea     rax, [rdi+10h]
0x18006975a  mov     [rsp+290h+var_260], rbx; __int64
0x18006975f  mov     [rbp+190h+SourceString.Buffer], rax
0x180069763  lea     rax, [rbp+190h+SourceString]
0x180069767  mov     [rsp+290h+ResultLength], rbx; __int64
0x18006976c  mov     qword ptr [rsp+290h+Length], rax; SourceString
0x180069771  call    FltpCreateInstanceFromName
0x180069776  mov     [rsp+50h], rbx
0x18006977b  lea     rdx, aMinkernelFsFil_19; "minkernel\\fs\\filtermgr\\filter\\insta"...
0x180069782  mov     dword ptr [rsp+290h+var_248], 0C00000BBh
0x18006978a  mov     r9d, 0C01C000Fh
0x180069790  mov     [rsp+290h+var_250], 0C0000002h
0x180069798  mov     r8d, 394h
0x18006979e  mov     [rsp+290h+var_258], 0C0000034h
0x1800697a6  mov     ecx, eax
0x1800697a8  mov     dword ptr [rsp+290h+var_260], 0C01C0011h
0x1800697b0  mov     dword ptr [rsp+290h+ResultLength], 0C01C0012h
0x1800697b8  mov     [rsp+290h+Length], 0C01C000Bh
0x1800697c0  call    FltpDbgStatus
0x1800697c5  inc     r14d
0x1800697c8  jmp     loc_1800696D5
0x1800697cd  cmp     ebx, 8000001Ah
0x1800697d3  jnz     short loc_18006984D
0x1800697d5  xor     ebx, ebx
0x1800697d7  mov     edx, 72744D46h; Tag
0x1800697dc  mov     rcx, rdi; P
0x1800697df  call    cs:__imp_ExFreePoolWithTag
0x1800697e6  nop     dword ptr [rax+rax+00h]
0x1800697eb  mov     rsi, [rsp+290h+arg_18]
0x1800697f3  mov     rcx, [rsp+290h+KeyHandle]; Handle
0x1800697f8  mov     r15, [rsp+290h+var_30]
0x180069800  mov     r14, [rsp+290h+var_28]
0x180069808  mov     r13, [rsp+290h+var_20]
0x180069810  mov     r12, [rsp+290h+var_18]
0x180069818  mov     rdi, [rsp+280h]
0x180069820  test    rcx, rcx
0x180069823  jz      short loc_180069831
0x180069825  call    cs:__imp_ZwClose
0x18006982c  nop     dword ptr [rax+rax+00h]
0x180069831  mov     eax, ebx
0x180069833  mov     rcx, [rbp+190h+var_40]
0x18006983a  xor     rcx, rsp; StackCookie
0x18006983d  call    __security_check_cookie
0x180069842  add     rsp, 288h
0x180069849  pop     rbx
0x18006984a  pop     rbp
0x18006984b  retn
0x18006984d  cmp     ebx, 0C0000023h
0x180069853  jnz     short loc_18006989C
0x180069855  mov     edx, 72744D46h; Tag
0x18006985a  mov     rcx, rdi; P
0x18006985d  call    cs:__imp_ExFreePoolWithTag
0x180069864  nop     dword ptr [rax+rax+00h]
0x180069869  mov     esi, [rsp+290h+var_228]
0x18006986d  mov     ecx, 100h
0x180069872  mov     edx, esi
0x180069874  mov     r8d, 72744D46h
0x18006987a  call    cs:__imp_ExAllocatePool2
0x180069881  nop     dword ptr [rax+rax+00h]
0x180069886  mov     rdi, rax
0x180069889  test    rax, rax
0x18006988c  jnz     loc_1800696D5
0x180069892  mov     ebx, 0C000009Ah
0x180069897  jmp     loc_1800697EB
0x18006989c  cmp     ebx, 80000005h
0x1800698a2  jnz     loc_1800697D7
0x1800698a8  jmp     short loc_180069855
0x1800698aa  cmp     edi, 0C0000034h
0x1800698b0  mov     ebx, r14d
0x1800698b3  cmovnz  ebx, edi
0x1800698b6  jmp     loc_1800697F3
```
