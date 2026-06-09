# RemoveInterface

- ea: `0x180035fc4`
- end: `0x1800364a9`
- name: `RemoveInterface`
- size: `1253`
- prototype: `__int64 __fastcall(GUID *Guid)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180035cb0`

## callees

- `0x18000b7bc`
- `0x18000c630`
- `0x180019b80`
- `0x180035fc4`
- `0x180063ccc`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x180036192`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18003641e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18003642e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180036192`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18003641e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18003642e`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003623f`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003623f`
- `ntoskrnl!RtlStringFromGUID` at `0x1800360e4`
- `ntoskrnl!RtlStringFromGUID` at `0x180036148`
- `ntoskrnl!RtlStringFromGUID` at `0x1800360e4`
- `ntoskrnl!RtlStringFromGUID` at `0x180036148`
- `ntoskrnl!ZwClose` at `0x18003612f`
- `ntoskrnl!ZwClose` at `0x1800363e2`
- `ntoskrnl!ZwClose` at `0x1800363f8`
- `ntoskrnl!ZwClose` at `0x18003640e`
- `ntoskrnl!ZwClose` at `0x18003643f`
- `ntoskrnl!ZwClose` at `0x18003612f`
- `ntoskrnl!ZwClose` at `0x1800363e2`
- `ntoskrnl!ZwClose` at `0x1800363f8`
- `ntoskrnl!ZwClose` at `0x18003640e`
- `ntoskrnl!ZwClose` at `0x18003643f`
- `ntoskrnl!ZwOpenKey` at `0x1800361e7`
- `ntoskrnl!ZwOpenKey` at `0x180036282`
- `ntoskrnl!ZwOpenKey` at `0x1800362fd`
- `ntoskrnl!ZwOpenKey` at `0x1800361e7`
- `ntoskrnl!ZwOpenKey` at `0x180036282`
- `ntoskrnl!ZwOpenKey` at `0x1800362fd`
- `ntoskrnl!ZwQueryKey` at `0x18003636e`
- `ntoskrnl!ZwQueryKey` at `0x1800363b0`
- `ntoskrnl!ZwQueryKey` at `0x18003636e`
- `ntoskrnl!ZwQueryKey` at `0x1800363b0`
- `ntoskrnl!ZwDeleteKey` at `0x180036347`
- `ntoskrnl!ZwDeleteKey` at `0x180036389`
- `ntoskrnl!ZwDeleteKey` at `0x1800363cd`
- `ntoskrnl!ZwDeleteKey` at `0x180036347`
- `ntoskrnl!ZwDeleteKey` at `0x180036389`
- `ntoskrnl!ZwDeleteKey` at `0x1800363cd`

## pseudocode

```c
__int64 __fastcall RemoveInterface(GUID *Guid, __int64 a2)
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
  NTSTATUS v13; // eax
  int v14; // edx
  NTSTATUS v15; // eax
  int v16; // edx
  NTSTATUS v17; // eax
  int v18; // edx
  int v19; // edx
  HANDLE v20; // [rsp+30h] [rbp-99h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-91h] BYREF
  ULONG ResultLength; // [rsp+40h] [rbp-89h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-81h] BYREF
  HANDLE v24; // [rsp+50h] [rbp-79h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-71h] BYREF
  UNICODE_STRING GuidString; // [rsp+88h] [rbp-41h] BYREF
  UNICODE_STRING UnicodeString; // [rsp+98h] [rbp-31h] BYREF
  UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-21h] BYREF
  __int128 KeyInformation; // [rsp+B8h] [rbp-11h] BYREF
  __int128 v30; // [rsp+C8h] [rbp-1h]
  __int128 v31; // [rsp+D8h] [rbp+Fh]

  KeyHandle = 0;
  v2 = a2;
  Handle = 0;
  v24 = 0;
  v20 = 0;
  memset(&ObjectAttributes, 0, 44);
  ResultLength = 0;
  GuidString = 0;
  UnicodeString = 0;
  DestinationString = 0;
  KeyInformation = 0;
  v30 = 0;
  v31 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      102,
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
        v24 = (HANDLE)-1LL;
        ObjectAttributes.ObjectName = &GuidString;
        v20 = (HANDLE)-1LL;
        KeyHandle = (void *)-1LL;
        ObjectAttributes.Length = 48;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v13 = ZwOpenKey(&KeyHandle, 0x20006u, &ObjectAttributes);
        v10 = v13;
        if ( v13 >= 0 )
        {
          RtlInitUnicodeString(&DestinationString, (PCWSTR)&Guid[2]);
          ObjectAttributes.RootDirectory = KeyHandle;
          ObjectAttributes.ObjectName = &DestinationString;
          ObjectAttributes.Length = 48;
          ObjectAttributes.Attributes = 576;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v15 = ZwOpenKey(&v20, 0x20006u, &ObjectAttributes);
          if ( v15 >= 0 )
          {
            ObjectAttributes.RootDirectory = v20;
            ObjectAttributes.Length = 48;
            ObjectAttributes.ObjectName = &UnicodeString;
            ObjectAttributes.Attributes = 576;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            v17 = ZwOpenKey(&v24, 0x20006u, &ObjectAttributes);
            if ( v17 >= 0 )
            {
              ZwDeleteKey(v24);
            }
            else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                   && LOWORD(WPP_GLOBAL_Control->DeviceType) )
            {
              LOBYTE(v18) = 5;
              WPP_RECORDER_SF_D(
                WPP_GLOBAL_Control->DeviceExtension,
                v18,
                1,
                107,
                (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
                v17);
            }
            if ( ZwQueryKey(v20, KeyFullInformation, &KeyInformation, 0x30u, &ResultLength) >= 0 && !DWORD1(v30) )
              ZwDeleteKey(v20);
          }
          else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                 && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            LOBYTE(v16) = 5;
            WPP_RECORDER_SF_D(
              WPP_GLOBAL_Control->DeviceExtension,
              v16,
              1,
              106,
              (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
              v15);
          }
          v10 = ZwQueryKey(KeyHandle, KeyFullInformation, &KeyInformation, 0x30u, &ResultLength);
          if ( v10 >= 0 && !DWORD1(v30) )
            ZwDeleteKey(KeyHandle);
        }
        else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
               && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(v14) = 5;
          WPP_RECORDER_SF_D(
            WPP_GLOBAL_Control->DeviceExtension,
            v14,
            1,
            105,
            (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
            v13);
        }
        if ( v24 != (HANDLE)-1LL )
          ZwClose(v24);
        if ( v20 != (HANDLE)-1LL )
          ZwClose(v20);
        if ( KeyHandle != (void *)-1LL )
          ZwClose(KeyHandle);
        RtlFreeUnicodeString(&GuidString);
        RtlFreeUnicodeString(&UnicodeString);
        ZwClose(Handle);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(v19) = 5;
          WPP_RECORDER_SF_D(
            WPP_GLOBAL_Control->DeviceExtension,
            v19,
            1,
            108,
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
          104,
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
        103,
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
0x180035fc4  mov     [rsp-8+arg_10], rbx
0x180035fc9  push    rbp
0x180035fca  push    rsi
0x180035fcb  push    rdi
0x180035fcc  push    r12
0x180035fce  push    r13
0x180035fd0  push    r14
0x180035fd2  push    r15
0x180035fd4  lea     rbp, [rsp-27h]
0x180035fd9  sub     rsp, 0F0h
0x180035fe0  mov     rax, cs:__security_cookie
0x180035fe7  xor     rax, rsp
0x180035fea  mov     [rbp+57h+var_38], rax
0x180035fee  xor     r14d, r14d
0x180035ff1  xorps   xmm0, xmm0
0x180035ff4  xorps   xmm1, xmm1
0x180035ff7  mov     [rsp+120h+KeyHandle], r14
0x180035ffc  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180036000  mov     rbx, rdx
0x180036003  mov     rdi, rcx
0x180036006  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18003600a  mov     [rsp+120h+Handle], r14
0x18003600f  xor     eax, eax
0x180036011  mov     [rbp+57h+var_D0], r14
0x180036015  mov     [rsp+120h+var_F0], r14
0x18003601a  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18003601e  mov     [rsp+120h+var_E0], r14d
0x180036023  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm0
0x180036027  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm1
0x18003602b  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18003602f  movups  [rbp+57h+KeyInformation], xmm1
0x180036033  movups  [rbp+57h+var_58], xmm1
0x180036037  movups  [rbp+57h+var_48], xmm1
0x18003603b  lea     r15, WPP_RECORDER_INITIALIZED
0x180036042  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180036049  lea     r13, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180036050  lea     r12d, [r14+1]
0x180036054  jz      short loc_18003607B
0x180036056  mov     rcx, cs:WPP_GLOBAL_Control
0x18003605d  cmp     [rcx+48h], r14w
0x180036062  jz      short loc_18003607B
0x180036064  mov     rcx, [rcx+40h]
0x180036068  lea     r9d, [r14+66h]
0x18003606c  mov     r8d, r12d
0x18003606f  mov     [rsp+120h+ResultLength], r13
0x180036074  mov     dl, 5
0x180036076  call    WPP_RECORDER_SF_
0x18003607b  lea     rsi, [rdi+20h]
0x18003607f  mov     r8d, 30h ; '0'
0x180036085  mov     rdx, rsi
0x180036088  test    rsi, rsi
0x18003608b  jz      short loc_1800360C8
0x18003608d  movzx   ecx, word ptr [rdx]
0x180036090  test    cx, cx
0x180036093  jz      short loc_1800360C8
0x180036095  lea     eax, [rcx-21h]
0x180036098  cmp     ax, 5Eh ; '^'
0x18003609c  ja      short loc_1800360BE
0x18003609e  sub     cx, 2Ch ; ','
0x1800360a2  cmp     cx, r8w
0x1800360a6  ja      short loc_1800360B8
0x1800360a8  mov     rax, 1000000000009h
0x1800360b2  bt      rax, rcx
0x1800360b6  jb      short loc_1800360BE
0x1800360b8  add     rdx, 2
0x1800360bc  jmp     short loc_18003608D
0x1800360be  mov     eax, 0C000000Dh
0x1800360c3  jmp     loc_180036481
0x1800360c8  mov     rdx, rbx
0x1800360cb  lea     rcx, [rsp+120h+Handle]
0x1800360d0  call    OpenDeviceInterfacesKey
0x1800360d5  test    eax, eax
0x1800360d7  js      loc_180036481
0x1800360dd  lea     rdx, [rbp+57h+GuidString]; GuidString
0x1800360e1  mov     rcx, rdi; Guid
0x1800360e4  call    cs:__imp_RtlStringFromGUID
0x1800360eb  nop     dword ptr [rax+rax+00h]
0x1800360f0  mov     ebx, eax
0x1800360f2  test    eax, eax
0x1800360f4  jns     short loc_180036140
0x1800360f6  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800360fd  jz      short loc_18003612A
0x1800360ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180036106  cmp     [rcx+48h], r14w
0x18003610b  jz      short loc_18003612A
0x18003610d  mov     rcx, [rcx+40h]
0x180036111  mov     r9d, 67h ; 'g'
0x180036117  mov     [rsp+120h+var_F8], eax
0x18003611b  mov     r8d, r12d
0x18003611e  mov     dl, 5
0x180036120  mov     [rsp+120h+ResultLength], r13
0x180036125  call    WPP_RECORDER_SF_D
0x18003612a  mov     rcx, [rsp+120h+Handle]; Handle
0x18003612f  call    cs:__imp_ZwClose
0x180036136  nop     dword ptr [rax+rax+00h]
0x18003613b  jmp     loc_18003647F
0x180036140  lea     rcx, [rdi+10h]; Guid
0x180036144  lea     rdx, [rbp+57h+UnicodeString]; GuidString
0x180036148  call    cs:__imp_RtlStringFromGUID
0x18003614f  nop     dword ptr [rax+rax+00h]
0x180036154  mov     ebx, eax
0x180036156  test    eax, eax
0x180036158  jns     short loc_1800361A0
0x18003615a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180036161  jz      short loc_18003618E
0x180036163  mov     rcx, cs:WPP_GLOBAL_Control
0x18003616a  cmp     [rcx+48h], r14w
0x18003616f  jz      short loc_18003618E
0x180036171  mov     rcx, [rcx+40h]
0x180036175  mov     r9d, 68h ; 'h'
0x18003617b  mov     [rsp+120h+var_F8], eax
0x18003617f  mov     r8d, r12d
0x180036182  mov     dl, 5
0x180036184  mov     [rsp+120h+ResultLength], r13
0x180036189  call    WPP_RECORDER_SF_D
0x18003618e  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x180036192  call    cs:__imp_RtlFreeUnicodeString
0x180036199  nop     dword ptr [rax+rax+00h]
0x18003619e  jmp     short loc_18003612A
0x1800361a0  mov     rax, [rsp+120h+Handle]
0x1800361a5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800361a9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800361ad  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800361b1  lea     rax, [rbp+57h+GuidString]
0x1800361b5  mov     [rbp+57h+var_D0], rdi
0x1800361b9  xorps   xmm0, xmm0
0x1800361bc  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800361c0  mov     edx, 20006h; DesiredAccess
0x1800361c5  mov     [rsp+120h+var_F0], rdi
0x1800361ca  lea     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x1800361cf  mov     [rsp+120h+KeyHandle], rdi
0x1800361d4  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800361db  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1800361e2  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800361e7  call    cs:__imp_ZwOpenKey
0x1800361ee  nop     dword ptr [rax+rax+00h]
0x1800361f3  mov     ebx, eax
0x1800361f5  test    eax, eax
0x1800361f7  jns     short loc_180036238
0x1800361f9  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180036200  jz      loc_1800363D9
0x180036206  mov     rcx, cs:WPP_GLOBAL_Control
0x18003620d  cmp     [rcx+48h], r14w
0x180036212  jz      loc_1800363D9
0x180036218  mov     rcx, [rcx+40h]
0x18003621c  lea     r9d, [rdi+6Ah]
0x180036220  mov     [rsp+120h+var_F8], eax
0x180036224  mov     r8d, r12d
0x180036227  mov     dl, 5
0x180036229  mov     [rsp+120h+ResultLength], r13
0x18003622e  call    WPP_RECORDER_SF_D
0x180036233  jmp     loc_1800363D9
0x180036238  mov     rdx, rsi; SourceString
0x18003623b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003623f  call    cs:__imp_RtlInitUnicodeString
0x180036246  nop     dword ptr [rax+rax+00h]
0x18003624b  mov     rax, [rsp+120h+KeyHandle]
0x180036250  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180036254  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180036258  lea     rcx, [rsp+120h+var_F0]; KeyHandle
0x18003625d  lea     rax, [rbp+57h+DestinationString]
0x180036261  xorps   xmm0, xmm0
0x180036264  mov     ebx, 30h ; '0'
0x180036269  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18003626d  mov     esi, 240h
0x180036272  mov     [rbp+57h+ObjectAttributes.Length], ebx
0x180036275  mov     edx, 20006h; DesiredAccess
0x18003627a  mov     [rbp+57h+ObjectAttributes.Attributes], esi
0x18003627d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180036282  call    cs:__imp_ZwOpenKey
0x180036289  nop     dword ptr [rax+rax+00h]
0x18003628e  test    eax, eax
0x180036290  jns     short loc_1800362D1
0x180036292  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180036299  jz      loc_180036395
0x18003629f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800362a6  cmp     [rcx+48h], r14w
0x1800362ab  jz      loc_180036395
0x1800362b1  mov     rcx, [rcx+40h]
0x1800362b5  lea     r9d, [rbx+3Ah]
0x1800362b9  mov     [rsp+120h+var_F8], eax
0x1800362bd  mov     r8d, r12d
0x1800362c0  mov     dl, 5
0x1800362c2  mov     [rsp+120h+ResultLength], r13
0x1800362c7  call    WPP_RECORDER_SF_D
0x1800362cc  jmp     loc_180036395
0x1800362d1  mov     rax, [rsp+120h+var_F0]
0x1800362d6  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800362da  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800362de  lea     rcx, [rbp+57h+var_D0]; KeyHandle
0x1800362e2  lea     rax, [rbp+57h+UnicodeString]
0x1800362e6  mov     [rbp+57h+ObjectAttributes.Length], ebx
0x1800362e9  xorps   xmm0, xmm0
0x1800362ec  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800362f0  mov     edx, 20006h; DesiredAccess
0x1800362f5  mov     [rbp+57h+ObjectAttributes.Attributes], esi
0x1800362f8  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800362fd  call    cs:__imp_ZwOpenKey
0x180036304  nop     dword ptr [rax+rax+00h]
0x180036309  test    eax, eax
0x18003630b  jns     short loc_180036343
0x18003630d  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180036314  jz      short loc_180036353
0x180036316  mov     rcx, cs:WPP_GLOBAL_Control
0x18003631d  cmp     [rcx+48h], r14w
0x180036322  jz      short loc_180036353
0x180036324  mov     rcx, [rcx+40h]
0x180036328  mov     r9d, 6Bh ; 'k'
0x18003632e  mov     [rsp+120h+var_F8], eax
0x180036332  mov     r8d, r12d
0x180036335  mov     dl, 5
0x180036337  mov     [rsp+120h+ResultLength], r13
0x18003633c  call    WPP_RECORDER_SF_D
0x180036341  jmp     short loc_180036353
0x180036343  mov     rcx, [rbp+57h+var_D0]; KeyHandle
0x180036347  call    cs:__imp_ZwDeleteKey
0x18003634e  nop     dword ptr [rax+rax+00h]
0x180036353  mov     rcx, [rsp+120h+var_F0]; KeyHandle
0x180036358  lea     rax, [rsp+120h+var_E0]
0x18003635d  mov     r9d, ebx; Length
0x180036360  mov     [rsp+120h+ResultLength], rax; ResultLength
0x180036365  lea     r8, [rbp+57h+KeyInformation]; KeyInformation
0x180036369  mov     edx, 2; KeyInformationClass
0x18003636e  call    cs:__imp_ZwQueryKey
0x180036375  nop     dword ptr [rax+rax+00h]
0x18003637a  test    eax, eax
0x18003637c  js      short loc_180036395
0x18003637e  cmp     dword ptr [rbp+57h+var_58+4], r14d
0x180036382  jnz     short loc_180036395
0x180036384  mov     rcx, [rsp+120h+var_F0]; KeyHandle
0x180036389  call    cs:__imp_ZwDeleteKey
0x180036390  nop     dword ptr [rax+rax+00h]
0x180036395  mov     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x18003639a  lea     rax, [rsp+120h+var_E0]
0x18003639f  mov     r9d, ebx; Length
0x1800363a2  mov     [rsp+120h+ResultLength], rax; ResultLength
0x1800363a7  lea     r8, [rbp+57h+KeyInformation]; KeyInformation
0x1800363ab  mov     edx, 2; KeyInformationClass
0x1800363b0  call    cs:__imp_ZwQueryKey
0x1800363b7  nop     dword ptr [rax+rax+00h]
0x1800363bc  mov     ebx, eax
0x1800363be  test    eax, eax
0x1800363c0  js      short loc_1800363D9
0x1800363c2  cmp     dword ptr [rbp+57h+var_58+4], r14d
0x1800363c6  jnz     short loc_1800363D9
0x1800363c8  mov     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x1800363cd  call    cs:__imp_ZwDeleteKey
0x1800363d4  nop     dword ptr [rax+rax+00h]
0x1800363d9  mov     rcx, [rbp+57h+var_D0]; Handle
0x1800363dd  cmp     rcx, rdi
0x1800363e0  jz      short loc_1800363EE
0x1800363e2  call    cs:__imp_ZwClose
0x1800363e9  nop     dword ptr [rax+rax+00h]
0x1800363ee  mov     rcx, [rsp+120h+var_F0]; Handle
0x1800363f3  cmp     rcx, rdi
0x1800363f6  jz      short loc_180036404
0x1800363f8  call    cs:__imp_ZwClose
0x1800363ff  nop     dword ptr [rax+rax+00h]
0x180036404  mov     rcx, [rsp+120h+KeyHandle]; Handle
0x180036409  cmp     rcx, rdi
0x18003640c  jz      short loc_18003641A
0x18003640e  call    cs:__imp_ZwClose
0x180036415  nop     dword ptr [rax+rax+00h]
0x18003641a  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x18003641e  call    cs:__imp_RtlFreeUnicodeString
0x180036425  nop     dword ptr [rax+rax+00h]
0x18003642a  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x18003642e  call    cs:__imp_RtlFreeUnicodeString
0x180036435  nop     dword ptr [rax+rax+00h]
0x18003643a  mov     rcx, [rsp+120h+Handle]; Handle
0x18003643f  call    cs:__imp_ZwClose
0x180036446  nop     dword ptr [rax+rax+00h]
0x18003644b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180036452  jz      short loc_18003647F
0x180036454  mov     rcx, cs:WPP_GLOBAL_Control
0x18003645b  cmp     [rcx+48h], r14w
0x180036460  jz      short loc_18003647F
0x180036462  mov     rcx, [rcx+40h]
0x180036466  mov     r9d, 6Ch ; 'l'
0x18003646c  mov     [rsp+120h+var_F8], ebx
0x180036470  mov     r8d, r12d
0x180036473  mov     dl, 5
0x180036475  mov     [rsp+120h+ResultLength], r13
0x18003647a  call    WPP_RECORDER_SF_D
0x18003647f  mov     eax, ebx
0x180036481  mov     rcx, [rbp+57h+var_38]
0x180036485  xor     rcx, rsp; StackCookie
0x180036488  call    __security_check_cookie
0x18003648d  mov     rbx, [rsp+120h+arg_10]
0x180036495  add     rsp, 0F0h
0x18003649c  pop     r15
0x18003649e  pop     r14
0x1800364a0  pop     r13
0x1800364a2  pop     r12
0x1800364a4  pop     rdi
0x1800364a5  pop     rsi
0x1800364a6  pop     rbp
0x1800364a7  retn
```
