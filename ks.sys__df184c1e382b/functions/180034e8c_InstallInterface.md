# InstallInterface

- ea: `0x180034e8c`
- end: `0x18003521e`
- name: `InstallInterface`
- size: `914`
- prototype: `__int64 __fastcall(GUID *Guid, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180035be0`

## callees

- `0x18000b7bc`
- `0x18000c630`
- `0x180034e8c`
- `0x180063e6c`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x180035034`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800351a8`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800351b8`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180035034`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800351a8`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800351b8`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800350b4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800350b4`
- `ntoskrnl!ZwCreateKey` at `0x180035097`
- `ntoskrnl!ZwCreateKey` at `0x180035104`
- `ntoskrnl!ZwCreateKey` at `0x180035157`
- `ntoskrnl!ZwCreateKey` at `0x180035097`
- `ntoskrnl!ZwCreateKey` at `0x180035104`
- `ntoskrnl!ZwCreateKey` at `0x180035157`
- `ntoskrnl!RtlStringFromGUID` at `0x180034f85`
- `ntoskrnl!RtlStringFromGUID` at `0x180034fe9`
- `ntoskrnl!RtlStringFromGUID` at `0x180034f85`
- `ntoskrnl!RtlStringFromGUID` at `0x180034fe9`
- `ntoskrnl!ZwClose` at `0x180034fd0`
- `ntoskrnl!ZwClose` at `0x18003516e`
- `ntoskrnl!ZwClose` at `0x180035183`
- `ntoskrnl!ZwClose` at `0x180035198`
- `ntoskrnl!ZwClose` at `0x1800351c8`
- `ntoskrnl!ZwClose` at `0x180034fd0`
- `ntoskrnl!ZwClose` at `0x18003516e`
- `ntoskrnl!ZwClose` at `0x180035183`
- `ntoskrnl!ZwClose` at `0x180035198`
- `ntoskrnl!ZwClose` at `0x1800351c8`

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
0x180034e8c  push    rbp
0x180034e8e  push    rbx
0x180034e8f  push    rsi
0x180034e90  push    rdi
0x180034e91  push    r13
0x180034e93  push    r14
0x180034e95  push    r15
0x180034e97  lea     rbp, [rsp-27h]
0x180034e9c  sub     rsp, 0B0h
0x180034ea3  xorps   xmm0, xmm0
0x180034ea6  xor     r14d, r14d
0x180034ea9  xorps   xmm1, xmm1
0x180034eac  mov     [rbp+57h+KeyHandle], r14
0x180034eb0  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180034eb4  mov     rbx, rdx
0x180034eb7  mov     rdi, rcx
0x180034eba  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180034ebe  mov     [rbp+57h+Handle], r14
0x180034ec2  xor     eax, eax
0x180034ec4  mov     [rbp+57h+var_A0], r14
0x180034ec8  mov     [rbp+57h+arg_10], r14
0x180034ecc  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180034ed0  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm0
0x180034ed4  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm1
0x180034ed8  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180034edc  lea     r15, WPP_RECORDER_INITIALIZED
0x180034ee3  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180034eea  lea     r13, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180034ef1  jz      short loc_180034F19
0x180034ef3  mov     rcx, cs:WPP_GLOBAL_Control
0x180034efa  cmp     [rcx+48h], r14w
0x180034eff  jz      short loc_180034F19
0x180034f01  mov     rcx, [rcx+40h]
0x180034f05  lea     r9d, [r14+5Bh]
0x180034f09  lea     r8d, [r14+1]
0x180034f0d  mov     [rsp+0E0h+Class], r13
0x180034f12  mov     dl, 5
0x180034f14  call    WPP_RECORDER_SF_
0x180034f19  lea     rsi, [rdi+20h]
0x180034f1d  mov     r9d, 5Eh ; '^'
0x180034f23  mov     rdx, rsi
0x180034f26  lea     r8d, [r9-2Eh]
0x180034f2a  test    rsi, rsi
0x180034f2d  jz      short loc_180034F6A
0x180034f2f  movzx   ecx, word ptr [rdx]
0x180034f32  test    cx, cx
0x180034f35  jz      short loc_180034F6A
0x180034f37  lea     eax, [rcx-21h]
0x180034f3a  cmp     ax, r9w
0x180034f3e  ja      short loc_180034F60
0x180034f40  sub     cx, 2Ch ; ','
0x180034f44  cmp     cx, r8w
0x180034f48  ja      short loc_180034F5A
0x180034f4a  mov     rax, 1000000000009h
0x180034f54  bt      rax, rcx
0x180034f58  jb      short loc_180034F60
0x180034f5a  add     rdx, 2
0x180034f5e  jmp     short loc_180034F2F
0x180034f60  mov     eax, 0C000000Dh
0x180034f65  jmp     loc_18003520B
0x180034f6a  mov     rdx, rbx
0x180034f6d  lea     rcx, [rbp+57h+Handle]
0x180034f71  call    OpenDeviceInterfacesKey
0x180034f76  test    eax, eax
0x180034f78  js      loc_18003520B
0x180034f7e  lea     rdx, [rbp+57h+GuidString]; GuidString
0x180034f82  mov     rcx, rdi; Guid
0x180034f85  call    cs:__imp_RtlStringFromGUID
0x180034f8c  nop     dword ptr [rax+rax+00h]
0x180034f91  mov     ebx, eax
0x180034f93  test    eax, eax
0x180034f95  jns     short loc_180034FE1
0x180034f97  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180034f9e  jz      short loc_180034FCC
0x180034fa0  mov     rcx, cs:WPP_GLOBAL_Control
0x180034fa7  cmp     [rcx+48h], r14w
0x180034fac  jz      short loc_180034FCC
0x180034fae  mov     rcx, [rcx+40h]
0x180034fb2  mov     r9d, 5Ch ; '\'
0x180034fb8  mov     [rsp+0E0h+CreateOptions], eax
0x180034fbc  mov     dl, 5
0x180034fbe  mov     [rsp+0E0h+Class], r13
0x180034fc3  lea     r8d, [r9-5Bh]
0x180034fc7  call    WPP_RECORDER_SF_D
0x180034fcc  mov     rcx, [rbp+57h+Handle]; Handle
0x180034fd0  call    cs:__imp_ZwClose
0x180034fd7  nop     dword ptr [rax+rax+00h]
0x180034fdc  jmp     loc_180035209
0x180034fe1  lea     rcx, [rdi+10h]; Guid
0x180034fe5  lea     rdx, [rbp+57h+UnicodeString]; GuidString
0x180034fe9  call    cs:__imp_RtlStringFromGUID
0x180034ff0  nop     dword ptr [rax+rax+00h]
0x180034ff5  mov     ebx, eax
0x180034ff7  test    eax, eax
0x180034ff9  jns     short loc_180035042
0x180034ffb  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180035002  jz      short loc_180035030
0x180035004  mov     rcx, cs:WPP_GLOBAL_Control
0x18003500b  cmp     [rcx+48h], r14w
0x180035010  jz      short loc_180035030
0x180035012  mov     rcx, [rcx+40h]
0x180035016  mov     r9d, 5Dh ; ']'
0x18003501c  mov     [rsp+0E0h+CreateOptions], eax
0x180035020  mov     dl, 5
0x180035022  mov     [rsp+0E0h+Class], r13
0x180035027  lea     r8d, [r9-5Ch]
0x18003502b  call    WPP_RECORDER_SF_D
0x180035030  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x180035034  call    cs:__imp_RtlFreeUnicodeString
0x18003503b  nop     dword ptr [rax+rax+00h]
0x180035040  jmp     short loc_180034FCC
0x180035042  mov     rax, [rbp+57h+Handle]
0x180035046  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18003504a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003504e  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180035052  lea     rax, [rbp+57h+GuidString]
0x180035056  mov     [rsp+0E0h+Disposition], r14; Disposition
0x18003505b  xorps   xmm0, xmm0
0x18003505e  mov     [rsp+0E0h+CreateOptions], r14d; CreateOptions
0x180035063  xor     r9d, r9d; TitleIndex
0x180035066  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18003506a  mov     edx, 20006h; DesiredAccess
0x18003506f  mov     [rbp+57h+var_A0], rdi
0x180035073  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180035077  mov     [rbp+57h+arg_10], rdi
0x18003507b  mov     [rbp+57h+KeyHandle], rdi
0x18003507f  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180035086  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18003508d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180035092  mov     [rsp+0E0h+Class], r14; Class
0x180035097  call    cs:__imp_ZwCreateKey
0x18003509e  nop     dword ptr [rax+rax+00h]
0x1800350a3  mov     ebx, eax
0x1800350a5  test    eax, eax
0x1800350a7  js      loc_180035165
0x1800350ad  mov     rdx, rsi; SourceString
0x1800350b0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800350b4  call    cs:__imp_RtlInitUnicodeString
0x1800350bb  nop     dword ptr [rax+rax+00h]
0x1800350c0  mov     rax, [rbp+57h+KeyHandle]
0x1800350c4  lea     esi, [rdi+31h]
0x1800350c7  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800350cb  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800350cf  lea     rax, [rbp+57h+DestinationString]
0x1800350d3  mov     [rsp+0E0h+Disposition], r14; Disposition
0x1800350d8  xorps   xmm0, xmm0
0x1800350db  mov     [rsp+0E0h+CreateOptions], r14d; CreateOptions
0x1800350e0  xor     r9d, r9d; TitleIndex
0x1800350e3  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800350e7  mov     edx, 20006h; DesiredAccess
0x1800350ec  mov     [rbp+57h+ObjectAttributes.Length], esi
0x1800350ef  lea     rcx, [rbp+57h+arg_10]; KeyHandle
0x1800350f3  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1800350fa  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800350ff  mov     [rsp+0E0h+Class], r14; Class
0x180035104  call    cs:__imp_ZwCreateKey
0x18003510b  nop     dword ptr [rax+rax+00h]
0x180035110  mov     ebx, eax
0x180035112  test    eax, eax
0x180035114  js      short loc_180035165
0x180035116  mov     rax, [rbp+57h+arg_10]
0x18003511a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18003511e  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180035122  lea     rcx, [rbp+57h+var_A0]; KeyHandle
0x180035126  lea     rax, [rbp+57h+UnicodeString]
0x18003512a  mov     [rsp+0E0h+Disposition], r14; Disposition
0x18003512f  xorps   xmm0, xmm0
0x180035132  mov     [rsp+0E0h+CreateOptions], r14d; CreateOptions
0x180035137  xor     r9d, r9d; TitleIndex
0x18003513a  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18003513e  mov     edx, 20006h; DesiredAccess
0x180035143  mov     [rbp+57h+ObjectAttributes.Length], esi
0x180035146  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18003514d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180035152  mov     [rsp+0E0h+Class], r14; Class
0x180035157  call    cs:__imp_ZwCreateKey
0x18003515e  nop     dword ptr [rax+rax+00h]
0x180035163  mov     ebx, eax
0x180035165  mov     rcx, [rbp+57h+var_A0]; Handle
0x180035169  cmp     rcx, rdi
0x18003516c  jz      short loc_18003517A
0x18003516e  call    cs:__imp_ZwClose
0x180035175  nop     dword ptr [rax+rax+00h]
0x18003517a  mov     rcx, [rbp+57h+arg_10]; Handle
0x18003517e  cmp     rcx, rdi
0x180035181  jz      short loc_18003518F
0x180035183  call    cs:__imp_ZwClose
0x18003518a  nop     dword ptr [rax+rax+00h]
0x18003518f  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180035193  cmp     rcx, rdi
0x180035196  jz      short loc_1800351A4
0x180035198  call    cs:__imp_ZwClose
0x18003519f  nop     dword ptr [rax+rax+00h]
0x1800351a4  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x1800351a8  call    cs:__imp_RtlFreeUnicodeString
0x1800351af  nop     dword ptr [rax+rax+00h]
0x1800351b4  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x1800351b8  call    cs:__imp_RtlFreeUnicodeString
0x1800351bf  nop     dword ptr [rax+rax+00h]
0x1800351c4  mov     rcx, [rbp+57h+Handle]; Handle
0x1800351c8  call    cs:__imp_ZwClose
0x1800351cf  nop     dword ptr [rax+rax+00h]
0x1800351d4  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800351db  jz      short loc_180035209
0x1800351dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800351e4  cmp     [rcx+48h], r14w
0x1800351e9  jz      short loc_180035209
0x1800351eb  mov     rcx, [rcx+40h]
0x1800351ef  mov     r9d, 5Eh ; '^'
0x1800351f5  mov     [rsp+0E0h+CreateOptions], ebx
0x1800351f9  mov     dl, 5
0x1800351fb  mov     [rsp+0E0h+Class], r13
0x180035200  lea     r8d, [r9-5Dh]
0x180035204  call    WPP_RECORDER_SF_D
0x180035209  mov     eax, ebx
0x18003520b  add     rsp, 0B0h
0x180035212  pop     r15
0x180035214  pop     r14
0x180035216  pop     r13
0x180035218  pop     rdi
0x180035219  pop     rsi
0x18003521a  pop     rbx
0x18003521b  pop     rbp
0x18003521c  retn
```
