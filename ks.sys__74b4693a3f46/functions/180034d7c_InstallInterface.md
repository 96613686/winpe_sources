# InstallInterface

- ea: `0x180034d7c`
- end: `0x18003510e`
- name: `InstallInterface`
- size: `914`
- prototype: `__int64 __fastcall(GUID *Guid)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180035ad0`

## callees

- `0x18000b7bc`
- `0x18000c630`
- `0x180034d7c`
- `0x180063ccc`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x180034f24`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180035098`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800350a8`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180034f24`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180035098`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800350a8`
- `ntoskrnl!RtlInitUnicodeString` at `0x180034fa4`
- `ntoskrnl!RtlInitUnicodeString` at `0x180034fa4`
- `ntoskrnl!ZwCreateKey` at `0x180034f87`
- `ntoskrnl!ZwCreateKey` at `0x180034ff4`
- `ntoskrnl!ZwCreateKey` at `0x180035047`
- `ntoskrnl!ZwCreateKey` at `0x180034f87`
- `ntoskrnl!ZwCreateKey` at `0x180034ff4`
- `ntoskrnl!ZwCreateKey` at `0x180035047`
- `ntoskrnl!RtlStringFromGUID` at `0x180034e75`
- `ntoskrnl!RtlStringFromGUID` at `0x180034ed9`
- `ntoskrnl!RtlStringFromGUID` at `0x180034e75`
- `ntoskrnl!RtlStringFromGUID` at `0x180034ed9`
- `ntoskrnl!ZwClose` at `0x180034ec0`
- `ntoskrnl!ZwClose` at `0x18003505e`
- `ntoskrnl!ZwClose` at `0x180035073`
- `ntoskrnl!ZwClose` at `0x180035088`
- `ntoskrnl!ZwClose` at `0x1800350b8`
- `ntoskrnl!ZwClose` at `0x180034ec0`
- `ntoskrnl!ZwClose` at `0x18003505e`
- `ntoskrnl!ZwClose` at `0x180035073`
- `ntoskrnl!ZwClose` at `0x180035088`
- `ntoskrnl!ZwClose` at `0x1800350b8`

## pseudocode

```c
__int64 __fastcall InstallInterface(GUID *Guid, __int64 a2)
{
  __int64 v2; // rbx
  GUID *v4; // rdx
  unsigned __int64 Data1_low; // rcx
  __int64 v6; // rax
  __int64 result; // rax
  NTSTATUS v8; // eax
  int v9; // edx
  NTSTATUS v10; // ebx
  NTSTATUS v11; // eax
  int v12; // edx
  int v13; // edx
  HANDLE v14; // [rsp+40h] [rbp-49h] BYREF
  UNICODE_STRING GuidString; // [rsp+48h] [rbp-41h] BYREF
  UNICODE_STRING UnicodeString; // [rsp+58h] [rbp-31h] BYREF
  UNICODE_STRING DestinationString; // [rsp+68h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-11h] BYREF
  HANDLE Handle; // [rsp+F0h] [rbp+67h] BYREF
  HANDLE v20; // [rsp+100h] [rbp+77h] BYREF
  void *KeyHandle; // [rsp+108h] [rbp+7Fh] BYREF

  KeyHandle = 0;
  v2 = a2;
  Handle = 0;
  v14 = 0;
  v20 = 0;
  memset(&ObjectAttributes, 0, 44);
  GuidString = 0;
  UnicodeString = 0;
  DestinationString = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      91,
      (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids);
  }
  v4 = Guid + 2;
  if ( Guid != (GUID *)-32LL )
  {
    while ( 1 )
    {
      Data1_low = LOWORD(v4->Data1);
      if ( !(_WORD)Data1_low )
        break;
      if ( (unsigned __int16)(Data1_low - 33) > 0x5Eu )
        return 3221225485LL;
      LOWORD(Data1_low) = Data1_low - 44;
      if ( (unsigned __int16)Data1_low <= 0x30u )
      {
        v6 = 0x1000000000009LL;
        if ( _bittest64(&v6, Data1_low) )
          return 3221225485LL;
      }
      v4 = (GUID *)((char *)v4 + 2);
    }
  }
  result = OpenDeviceInterfacesKey(&Handle, v2, 48);
  if ( (int)result >= 0 )
  {
    v8 = RtlStringFromGUID(Guid, &GuidString);
    v10 = v8;
    if ( v8 >= 0 )
    {
      v11 = RtlStringFromGUID(Guid + 1, &UnicodeString);
      v10 = v11;
      if ( v11 >= 0 )
      {
        ObjectAttributes.RootDirectory = Handle;
        ObjectAttributes.ObjectName = &GuidString;
        v14 = (HANDLE)-1LL;
        v20 = (HANDLE)-1LL;
        KeyHandle = (void *)-1LL;
        ObjectAttributes.Length = 48;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v10 = ZwCreateKey(&KeyHandle, 0x20006u, &ObjectAttributes, 0, 0, 0, 0);
        if ( v10 >= 0 )
        {
          RtlInitUnicodeString(&DestinationString, (PCWSTR)&Guid[2]);
          ObjectAttributes.RootDirectory = KeyHandle;
          ObjectAttributes.ObjectName = &DestinationString;
          ObjectAttributes.Length = 48;
          ObjectAttributes.Attributes = 576;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v10 = ZwCreateKey(&v20, 0x20006u, &ObjectAttributes, 0, 0, 0, 0);
          if ( v10 >= 0 )
          {
            ObjectAttributes.RootDirectory = v20;
            ObjectAttributes.ObjectName = &UnicodeString;
            ObjectAttributes.Length = 48;
            ObjectAttributes.Attributes = 576;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            v10 = ZwCreateKey(&v14, 0x20006u, &ObjectAttributes, 0, 0, 0, 0);
          }
        }
        if ( v14 != (HANDLE)-1LL )
          ZwClose(v14);
        if ( v20 != (HANDLE)-1LL )
          ZwClose(v20);
        if ( KeyHandle != (void *)-1LL )
          ZwClose(KeyHandle);
        RtlFreeUnicodeString(&GuidString);
        RtlFreeUnicodeString(&UnicodeString);
        ZwClose(Handle);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(v13) = 5;
          WPP_RECORDER_SF_D(
            WPP_GLOBAL_Control->DeviceExtension,
            v13,
            1,
            94,
            (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
            v10);
        }
        return (unsigned int)v10;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v12) = 5;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v12,
          1,
          93,
          (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
          v11);
      }
      RtlFreeUnicodeString(&GuidString);
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
           && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v9) = 5;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        1,
        92,
        (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
        v8);
    }
    ZwClose(Handle);
    return (unsigned int)v10;
  }
  return result;
}

```

## disassembly

```asm
0x180034d7c  push    rbp
0x180034d7e  push    rbx
0x180034d7f  push    rsi
0x180034d80  push    rdi
0x180034d81  push    r13
0x180034d83  push    r14
0x180034d85  push    r15
0x180034d87  lea     rbp, [rsp-27h]
0x180034d8c  sub     rsp, 0B0h
0x180034d93  xorps   xmm0, xmm0
0x180034d96  xor     r14d, r14d
0x180034d99  xorps   xmm1, xmm1
0x180034d9c  mov     [rbp+57h+KeyHandle], r14
0x180034da0  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180034da4  mov     rbx, rdx
0x180034da7  mov     rdi, rcx
0x180034daa  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180034dae  mov     [rbp+57h+Handle], r14
0x180034db2  xor     eax, eax
0x180034db4  mov     [rbp+57h+var_A0], r14
0x180034db8  mov     [rbp+57h+arg_10], r14
0x180034dbc  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180034dc0  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm0
0x180034dc4  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm1
0x180034dc8  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180034dcc  lea     r15, WPP_RECORDER_INITIALIZED
0x180034dd3  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180034dda  lea     r13, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180034de1  jz      short loc_180034E09
0x180034de3  mov     rcx, cs:WPP_GLOBAL_Control
0x180034dea  cmp     [rcx+48h], r14w
0x180034def  jz      short loc_180034E09
0x180034df1  mov     rcx, [rcx+40h]
0x180034df5  lea     r9d, [r14+5Bh]
0x180034df9  lea     r8d, [r14+1]
0x180034dfd  mov     [rsp+0E0h+Class], r13
0x180034e02  mov     dl, 5
0x180034e04  call    WPP_RECORDER_SF_
0x180034e09  lea     rsi, [rdi+20h]
0x180034e0d  mov     r9d, 5Eh ; '^'
0x180034e13  mov     rdx, rsi
0x180034e16  lea     r8d, [r9-2Eh]
0x180034e1a  test    rsi, rsi
0x180034e1d  jz      short loc_180034E5A
0x180034e1f  movzx   ecx, word ptr [rdx]
0x180034e22  test    cx, cx
0x180034e25  jz      short loc_180034E5A
0x180034e27  lea     eax, [rcx-21h]
0x180034e2a  cmp     ax, r9w
0x180034e2e  ja      short loc_180034E50
0x180034e30  sub     cx, 2Ch ; ','
0x180034e34  cmp     cx, r8w
0x180034e38  ja      short loc_180034E4A
0x180034e3a  mov     rax, 1000000000009h
0x180034e44  bt      rax, rcx
0x180034e48  jb      short loc_180034E50
0x180034e4a  add     rdx, 2
0x180034e4e  jmp     short loc_180034E1F
0x180034e50  mov     eax, 0C000000Dh
0x180034e55  jmp     loc_1800350FB
0x180034e5a  mov     rdx, rbx
0x180034e5d  lea     rcx, [rbp+57h+Handle]
0x180034e61  call    OpenDeviceInterfacesKey
0x180034e66  test    eax, eax
0x180034e68  js      loc_1800350FB
0x180034e6e  lea     rdx, [rbp+57h+GuidString]; GuidString
0x180034e72  mov     rcx, rdi; Guid
0x180034e75  call    cs:__imp_RtlStringFromGUID
0x180034e7c  nop     dword ptr [rax+rax+00h]
0x180034e81  mov     ebx, eax
0x180034e83  test    eax, eax
0x180034e85  jns     short loc_180034ED1
0x180034e87  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180034e8e  jz      short loc_180034EBC
0x180034e90  mov     rcx, cs:WPP_GLOBAL_Control
0x180034e97  cmp     [rcx+48h], r14w
0x180034e9c  jz      short loc_180034EBC
0x180034e9e  mov     rcx, [rcx+40h]
0x180034ea2  mov     r9d, 5Ch ; '\'
0x180034ea8  mov     [rsp+0E0h+CreateOptions], eax
0x180034eac  mov     dl, 5
0x180034eae  mov     [rsp+0E0h+Class], r13
0x180034eb3  lea     r8d, [r9-5Bh]
0x180034eb7  call    WPP_RECORDER_SF_D
0x180034ebc  mov     rcx, [rbp+57h+Handle]; Handle
0x180034ec0  call    cs:__imp_ZwClose
0x180034ec7  nop     dword ptr [rax+rax+00h]
0x180034ecc  jmp     loc_1800350F9
0x180034ed1  lea     rcx, [rdi+10h]; Guid
0x180034ed5  lea     rdx, [rbp+57h+UnicodeString]; GuidString
0x180034ed9  call    cs:__imp_RtlStringFromGUID
0x180034ee0  nop     dword ptr [rax+rax+00h]
0x180034ee5  mov     ebx, eax
0x180034ee7  test    eax, eax
0x180034ee9  jns     short loc_180034F32
0x180034eeb  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180034ef2  jz      short loc_180034F20
0x180034ef4  mov     rcx, cs:WPP_GLOBAL_Control
0x180034efb  cmp     [rcx+48h], r14w
0x180034f00  jz      short loc_180034F20
0x180034f02  mov     rcx, [rcx+40h]
0x180034f06  mov     r9d, 5Dh ; ']'
0x180034f0c  mov     [rsp+0E0h+CreateOptions], eax
0x180034f10  mov     dl, 5
0x180034f12  mov     [rsp+0E0h+Class], r13
0x180034f17  lea     r8d, [r9-5Ch]
0x180034f1b  call    WPP_RECORDER_SF_D
0x180034f20  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x180034f24  call    cs:__imp_RtlFreeUnicodeString
0x180034f2b  nop     dword ptr [rax+rax+00h]
0x180034f30  jmp     short loc_180034EBC
0x180034f32  mov     rax, [rbp+57h+Handle]
0x180034f36  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180034f3a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180034f3e  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180034f42  lea     rax, [rbp+57h+GuidString]
0x180034f46  mov     [rsp+0E0h+Disposition], r14; Disposition
0x180034f4b  xorps   xmm0, xmm0
0x180034f4e  mov     [rsp+0E0h+CreateOptions], r14d; CreateOptions
0x180034f53  xor     r9d, r9d; TitleIndex
0x180034f56  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180034f5a  mov     edx, 20006h; DesiredAccess
0x180034f5f  mov     [rbp+57h+var_A0], rdi
0x180034f63  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180034f67  mov     [rbp+57h+arg_10], rdi
0x180034f6b  mov     [rbp+57h+KeyHandle], rdi
0x180034f6f  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180034f76  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180034f7d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180034f82  mov     [rsp+0E0h+Class], r14; Class
0x180034f87  call    cs:__imp_ZwCreateKey
0x180034f8e  nop     dword ptr [rax+rax+00h]
0x180034f93  mov     ebx, eax
0x180034f95  test    eax, eax
0x180034f97  js      loc_180035055
0x180034f9d  mov     rdx, rsi; SourceString
0x180034fa0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180034fa4  call    cs:__imp_RtlInitUnicodeString
0x180034fab  nop     dword ptr [rax+rax+00h]
0x180034fb0  mov     rax, [rbp+57h+KeyHandle]
0x180034fb4  lea     esi, [rdi+31h]
0x180034fb7  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180034fbb  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180034fbf  lea     rax, [rbp+57h+DestinationString]
0x180034fc3  mov     [rsp+0E0h+Disposition], r14; Disposition
0x180034fc8  xorps   xmm0, xmm0
0x180034fcb  mov     [rsp+0E0h+CreateOptions], r14d; CreateOptions
0x180034fd0  xor     r9d, r9d; TitleIndex
0x180034fd3  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180034fd7  mov     edx, 20006h; DesiredAccess
0x180034fdc  mov     [rbp+57h+ObjectAttributes.Length], esi
0x180034fdf  lea     rcx, [rbp+57h+arg_10]; KeyHandle
0x180034fe3  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180034fea  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180034fef  mov     [rsp+0E0h+Class], r14; Class
0x180034ff4  call    cs:__imp_ZwCreateKey
0x180034ffb  nop     dword ptr [rax+rax+00h]
0x180035000  mov     ebx, eax
0x180035002  test    eax, eax
0x180035004  js      short loc_180035055
0x180035006  mov     rax, [rbp+57h+arg_10]
0x18003500a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18003500e  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180035012  lea     rcx, [rbp+57h+var_A0]; KeyHandle
0x180035016  lea     rax, [rbp+57h+UnicodeString]
0x18003501a  mov     [rsp+0E0h+Disposition], r14; Disposition
0x18003501f  xorps   xmm0, xmm0
0x180035022  mov     [rsp+0E0h+CreateOptions], r14d; CreateOptions
0x180035027  xor     r9d, r9d; TitleIndex
0x18003502a  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18003502e  mov     edx, 20006h; DesiredAccess
0x180035033  mov     [rbp+57h+ObjectAttributes.Length], esi
0x180035036  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18003503d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180035042  mov     [rsp+0E0h+Class], r14; Class
0x180035047  call    cs:__imp_ZwCreateKey
0x18003504e  nop     dword ptr [rax+rax+00h]
0x180035053  mov     ebx, eax
0x180035055  mov     rcx, [rbp+57h+var_A0]; Handle
0x180035059  cmp     rcx, rdi
0x18003505c  jz      short loc_18003506A
0x18003505e  call    cs:__imp_ZwClose
0x180035065  nop     dword ptr [rax+rax+00h]
0x18003506a  mov     rcx, [rbp+57h+arg_10]; Handle
0x18003506e  cmp     rcx, rdi
0x180035071  jz      short loc_18003507F
0x180035073  call    cs:__imp_ZwClose
0x18003507a  nop     dword ptr [rax+rax+00h]
0x18003507f  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180035083  cmp     rcx, rdi
0x180035086  jz      short loc_180035094
0x180035088  call    cs:__imp_ZwClose
0x18003508f  nop     dword ptr [rax+rax+00h]
0x180035094  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x180035098  call    cs:__imp_RtlFreeUnicodeString
0x18003509f  nop     dword ptr [rax+rax+00h]
0x1800350a4  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x1800350a8  call    cs:__imp_RtlFreeUnicodeString
0x1800350af  nop     dword ptr [rax+rax+00h]
0x1800350b4  mov     rcx, [rbp+57h+Handle]; Handle
0x1800350b8  call    cs:__imp_ZwClose
0x1800350bf  nop     dword ptr [rax+rax+00h]
0x1800350c4  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800350cb  jz      short loc_1800350F9
0x1800350cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800350d4  cmp     [rcx+48h], r14w
0x1800350d9  jz      short loc_1800350F9
0x1800350db  mov     rcx, [rcx+40h]
0x1800350df  mov     r9d, 5Eh ; '^'
0x1800350e5  mov     [rsp+0E0h+CreateOptions], ebx
0x1800350e9  mov     dl, 5
0x1800350eb  mov     [rsp+0E0h+Class], r13
0x1800350f0  lea     r8d, [r9-5Dh]
0x1800350f4  call    WPP_RECORDER_SF_D
0x1800350f9  mov     eax, ebx
0x1800350fb  add     rsp, 0B0h
0x180035102  pop     r15
0x180035104  pop     r14
0x180035106  pop     r13
0x180035108  pop     rdi
0x180035109  pop     rsi
0x18003510a  pop     rbx
0x18003510b  pop     rbp
0x18003510c  retn
```
