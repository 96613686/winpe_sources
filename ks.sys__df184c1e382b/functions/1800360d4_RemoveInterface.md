# RemoveInterface

- ea: `0x1800360d4`
- end: `0x1800365b9`
- name: `RemoveInterface`
- size: `1253`
- prototype: `__int64 __fastcall(GUID *Guid, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180035dc0`

## callees

- `0x18000b7bc`
- `0x18000c630`
- `0x180019bd0`
- `0x1800360d4`
- `0x180063e6c`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1800362a2`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18003652e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18003653e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800362a2`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18003652e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18003653e`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003634f`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003634f`
- `ntoskrnl!RtlStringFromGUID` at `0x1800361f4`
- `ntoskrnl!RtlStringFromGUID` at `0x180036258`
- `ntoskrnl!RtlStringFromGUID` at `0x1800361f4`
- `ntoskrnl!RtlStringFromGUID` at `0x180036258`
- `ntoskrnl!ZwClose` at `0x18003623f`
- `ntoskrnl!ZwClose` at `0x1800364f2`
- `ntoskrnl!ZwClose` at `0x180036508`
- `ntoskrnl!ZwClose` at `0x18003651e`
- `ntoskrnl!ZwClose` at `0x18003654f`
- `ntoskrnl!ZwClose` at `0x18003623f`
- `ntoskrnl!ZwClose` at `0x1800364f2`
- `ntoskrnl!ZwClose` at `0x180036508`
- `ntoskrnl!ZwClose` at `0x18003651e`
- `ntoskrnl!ZwClose` at `0x18003654f`
- `ntoskrnl!ZwOpenKey` at `0x1800362f7`
- `ntoskrnl!ZwOpenKey` at `0x180036392`
- `ntoskrnl!ZwOpenKey` at `0x18003640d`
- `ntoskrnl!ZwOpenKey` at `0x1800362f7`
- `ntoskrnl!ZwOpenKey` at `0x180036392`
- `ntoskrnl!ZwOpenKey` at `0x18003640d`
- `ntoskrnl!ZwQueryKey` at `0x18003647e`
- `ntoskrnl!ZwQueryKey` at `0x1800364c0`
- `ntoskrnl!ZwQueryKey` at `0x18003647e`
- `ntoskrnl!ZwQueryKey` at `0x1800364c0`
- `ntoskrnl!ZwDeleteKey` at `0x180036457`
- `ntoskrnl!ZwDeleteKey` at `0x180036499`
- `ntoskrnl!ZwDeleteKey` at `0x1800364dd`
- `ntoskrnl!ZwDeleteKey` at `0x180036457`
- `ntoskrnl!ZwDeleteKey` at `0x180036499`
- `ntoskrnl!ZwDeleteKey` at `0x1800364dd`

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
  __int64 v20; // [rsp+28h] [rbp-A1h]
  HANDLE v21; // [rsp+30h] [rbp-99h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-91h] BYREF
  __int64 ResultLength; // [rsp+40h] [rbp-89h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-81h] BYREF
  HANDLE v25; // [rsp+50h] [rbp-79h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-71h] BYREF
  UNICODE_STRING GuidString; // [rsp+88h] [rbp-41h] BYREF
  UNICODE_STRING UnicodeString; // [rsp+98h] [rbp-31h] BYREF
  UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-21h] BYREF
  __int128 KeyInformation; // [rsp+B8h] [rbp-11h] BYREF
  __int128 v31; // [rsp+C8h] [rbp-1h]
  __int128 v32; // [rsp+D8h] [rbp+Fh]

  KeyHandle = 0;
  v2 = a2;
  Handle = 0;
  v25 = 0;
  v21 = 0;
  memset(&ObjectAttributes, 0, 44);
  LODWORD(ResultLength) = 0;
  GuidString = 0;
  UnicodeString = 0;
  DestinationString = 0;
  KeyInformation = 0;
  v31 = 0;
  v32 = 0;
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
        v25 = (HANDLE)-1LL;
        ObjectAttributes.ObjectName = &GuidString;
        v21 = (HANDLE)-1LL;
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
          v15 = ZwOpenKey(&v21, 0x20006u, &ObjectAttributes);
          if ( v15 >= 0 )
          {
            ObjectAttributes.RootDirectory = v21;
            ObjectAttributes.Length = 48;
            ObjectAttributes.ObjectName = &UnicodeString;
            ObjectAttributes.Attributes = 576;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            v17 = ZwOpenKey(&v25, 0x20006u, &ObjectAttributes);
            if ( v17 >= 0 )
            {
              ZwDeleteKey(v25);
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
            if ( ZwQueryKey(v21, KeyFullInformation, &KeyInformation, 0x30u, (PULONG)&ResultLength) >= 0 && !DWORD1(v31) )
              ZwDeleteKey(v21);
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
          v10 = ZwQueryKey(KeyHandle, KeyFullInformation, &KeyInformation, 0x30u, (PULONG)&ResultLength);
          if ( v10 >= 0 && !DWORD1(v31) )
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
        if ( v25 != (HANDLE)-1LL )
          ZwClose(v25);
        if ( v21 != (HANDLE)-1LL )
          ZwClose(v21);
        if ( KeyHandle != (void *)-1LL )
          ZwClose(KeyHandle);
        RtlFreeUnicodeString(&GuidString);
        RtlFreeUnicodeString(&UnicodeString);
        ZwClose(Handle);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LODWORD(v20) = v10;
          LOBYTE(v19) = 5;
          WPP_RECORDER_SF_D(
            WPP_GLOBAL_Control->DeviceExtension,
            v19,
            1,
            108,
            (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
            v20);
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
          v11,
          v21,
          KeyHandle,
          ResultLength);
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
        v8,
        v21,
        KeyHandle,
        ResultLength);
    }
    ZwClose(Handle);
    return (unsigned int)v10;
  }
  return result;
}

```

## disassembly

```asm
0x1800360d4  mov     [rsp-8+arg_10], rbx
0x1800360d9  push    rbp
0x1800360da  push    rsi
0x1800360db  push    rdi
0x1800360dc  push    r12
0x1800360de  push    r13
0x1800360e0  push    r14
0x1800360e2  push    r15
0x1800360e4  lea     rbp, [rsp-27h]
0x1800360e9  sub     rsp, 0F0h
0x1800360f0  mov     rax, cs:__security_cookie
0x1800360f7  xor     rax, rsp
0x1800360fa  mov     [rbp+57h+var_38], rax
0x1800360fe  xor     r14d, r14d
0x180036101  xorps   xmm0, xmm0
0x180036104  xorps   xmm1, xmm1
0x180036107  mov     [rsp+120h+KeyHandle], r14
0x18003610c  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180036110  mov     rbx, rdx
0x180036113  mov     rdi, rcx
0x180036116  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18003611a  mov     [rsp+120h+Handle], r14
0x18003611f  xor     eax, eax
0x180036121  mov     [rbp+57h+var_D0], r14
0x180036125  mov     [rsp+120h+var_F0], r14
0x18003612a  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18003612e  mov     dword ptr [rsp+120h+var_E0], r14d
0x180036133  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm0
0x180036137  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm1
0x18003613b  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18003613f  movups  [rbp+57h+KeyInformation], xmm1
0x180036143  movups  [rbp+57h+var_58], xmm1
0x180036147  movups  [rbp+57h+var_48], xmm1
0x18003614b  lea     r15, WPP_RECORDER_INITIALIZED
0x180036152  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180036159  lea     r13, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180036160  lea     r12d, [r14+1]
0x180036164  jz      short loc_18003618B
0x180036166  mov     rcx, cs:WPP_GLOBAL_Control
0x18003616d  cmp     [rcx+48h], r14w
0x180036172  jz      short loc_18003618B
0x180036174  mov     rcx, [rcx+40h]
0x180036178  lea     r9d, [r14+66h]
0x18003617c  mov     r8d, r12d
0x18003617f  mov     [rsp+120h+ResultLength], r13
0x180036184  mov     dl, 5
0x180036186  call    WPP_RECORDER_SF_
0x18003618b  lea     rsi, [rdi+20h]
0x18003618f  mov     r8d, 30h ; '0'
0x180036195  mov     rdx, rsi
0x180036198  test    rsi, rsi
0x18003619b  jz      short loc_1800361D8
0x18003619d  movzx   ecx, word ptr [rdx]
0x1800361a0  test    cx, cx
0x1800361a3  jz      short loc_1800361D8
0x1800361a5  lea     eax, [rcx-21h]
0x1800361a8  cmp     ax, 5Eh ; '^'
0x1800361ac  ja      short loc_1800361CE
0x1800361ae  sub     cx, 2Ch ; ','
0x1800361b2  cmp     cx, r8w
0x1800361b6  ja      short loc_1800361C8
0x1800361b8  mov     rax, 1000000000009h
0x1800361c2  bt      rax, rcx
0x1800361c6  jb      short loc_1800361CE
0x1800361c8  add     rdx, 2
0x1800361cc  jmp     short loc_18003619D
0x1800361ce  mov     eax, 0C000000Dh
0x1800361d3  jmp     loc_180036591
0x1800361d8  mov     rdx, rbx
0x1800361db  lea     rcx, [rsp+120h+Handle]
0x1800361e0  call    OpenDeviceInterfacesKey
0x1800361e5  test    eax, eax
0x1800361e7  js      loc_180036591
0x1800361ed  lea     rdx, [rbp+57h+GuidString]; GuidString
0x1800361f1  mov     rcx, rdi; Guid
0x1800361f4  call    cs:__imp_RtlStringFromGUID
0x1800361fb  nop     dword ptr [rax+rax+00h]
0x180036200  mov     ebx, eax
0x180036202  test    eax, eax
0x180036204  jns     short loc_180036250
0x180036206  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18003620d  jz      short loc_18003623A
0x18003620f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036216  cmp     [rcx+48h], r14w
0x18003621b  jz      short loc_18003623A
0x18003621d  mov     rcx, [rcx+40h]
0x180036221  mov     r9d, 67h ; 'g'
0x180036227  mov     dword ptr [rsp+120h+var_F8], eax
0x18003622b  mov     r8d, r12d
0x18003622e  mov     dl, 5
0x180036230  mov     [rsp+120h+ResultLength], r13
0x180036235  call    WPP_RECORDER_SF_D
0x18003623a  mov     rcx, [rsp+120h+Handle]; Handle
0x18003623f  call    cs:__imp_ZwClose
0x180036246  nop     dword ptr [rax+rax+00h]
0x18003624b  jmp     loc_18003658F
0x180036250  lea     rcx, [rdi+10h]; Guid
0x180036254  lea     rdx, [rbp+57h+UnicodeString]; GuidString
0x180036258  call    cs:__imp_RtlStringFromGUID
0x18003625f  nop     dword ptr [rax+rax+00h]
0x180036264  mov     ebx, eax
0x180036266  test    eax, eax
0x180036268  jns     short loc_1800362B0
0x18003626a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180036271  jz      short loc_18003629E
0x180036273  mov     rcx, cs:WPP_GLOBAL_Control
0x18003627a  cmp     [rcx+48h], r14w
0x18003627f  jz      short loc_18003629E
0x180036281  mov     rcx, [rcx+40h]
0x180036285  mov     r9d, 68h ; 'h'
0x18003628b  mov     dword ptr [rsp+120h+var_F8], eax
0x18003628f  mov     r8d, r12d
0x180036292  mov     dl, 5
0x180036294  mov     [rsp+120h+ResultLength], r13
0x180036299  call    WPP_RECORDER_SF_D
0x18003629e  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x1800362a2  call    cs:__imp_RtlFreeUnicodeString
0x1800362a9  nop     dword ptr [rax+rax+00h]
0x1800362ae  jmp     short loc_18003623A
0x1800362b0  mov     rax, [rsp+120h+Handle]
0x1800362b5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800362b9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800362bd  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800362c1  lea     rax, [rbp+57h+GuidString]
0x1800362c5  mov     [rbp+57h+var_D0], rdi
0x1800362c9  xorps   xmm0, xmm0
0x1800362cc  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800362d0  mov     edx, 20006h; DesiredAccess
0x1800362d5  mov     [rsp+120h+var_F0], rdi
0x1800362da  lea     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x1800362df  mov     [rsp+120h+KeyHandle], rdi
0x1800362e4  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800362eb  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1800362f2  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800362f7  call    cs:__imp_ZwOpenKey
0x1800362fe  nop     dword ptr [rax+rax+00h]
0x180036303  mov     ebx, eax
0x180036305  test    eax, eax
0x180036307  jns     short loc_180036348
0x180036309  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180036310  jz      loc_1800364E9
0x180036316  mov     rcx, cs:WPP_GLOBAL_Control
0x18003631d  cmp     [rcx+48h], r14w
0x180036322  jz      loc_1800364E9
0x180036328  mov     rcx, [rcx+40h]
0x18003632c  lea     r9d, [rdi+6Ah]
0x180036330  mov     dword ptr [rsp+120h+var_F8], eax
0x180036334  mov     r8d, r12d
0x180036337  mov     dl, 5
0x180036339  mov     [rsp+120h+ResultLength], r13
0x18003633e  call    WPP_RECORDER_SF_D
0x180036343  jmp     loc_1800364E9
0x180036348  mov     rdx, rsi; SourceString
0x18003634b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18003634f  call    cs:__imp_RtlInitUnicodeString
0x180036356  nop     dword ptr [rax+rax+00h]
0x18003635b  mov     rax, [rsp+120h+KeyHandle]
0x180036360  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180036364  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180036368  lea     rcx, [rsp+120h+var_F0]; KeyHandle
0x18003636d  lea     rax, [rbp+57h+DestinationString]
0x180036371  xorps   xmm0, xmm0
0x180036374  mov     ebx, 30h ; '0'
0x180036379  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18003637d  mov     esi, 240h
0x180036382  mov     [rbp+57h+ObjectAttributes.Length], ebx
0x180036385  mov     edx, 20006h; DesiredAccess
0x18003638a  mov     [rbp+57h+ObjectAttributes.Attributes], esi
0x18003638d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180036392  call    cs:__imp_ZwOpenKey
0x180036399  nop     dword ptr [rax+rax+00h]
0x18003639e  test    eax, eax
0x1800363a0  jns     short loc_1800363E1
0x1800363a2  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800363a9  jz      loc_1800364A5
0x1800363af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800363b6  cmp     [rcx+48h], r14w
0x1800363bb  jz      loc_1800364A5
0x1800363c1  mov     rcx, [rcx+40h]
0x1800363c5  lea     r9d, [rbx+3Ah]
0x1800363c9  mov     dword ptr [rsp+120h+var_F8], eax
0x1800363cd  mov     r8d, r12d
0x1800363d0  mov     dl, 5
0x1800363d2  mov     [rsp+120h+ResultLength], r13
0x1800363d7  call    WPP_RECORDER_SF_D
0x1800363dc  jmp     loc_1800364A5
0x1800363e1  mov     rax, [rsp+120h+var_F0]
0x1800363e6  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800363ea  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800363ee  lea     rcx, [rbp+57h+var_D0]; KeyHandle
0x1800363f2  lea     rax, [rbp+57h+UnicodeString]
0x1800363f6  mov     [rbp+57h+ObjectAttributes.Length], ebx
0x1800363f9  xorps   xmm0, xmm0
0x1800363fc  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180036400  mov     edx, 20006h; DesiredAccess
0x180036405  mov     [rbp+57h+ObjectAttributes.Attributes], esi
0x180036408  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003640d  call    cs:__imp_ZwOpenKey
0x180036414  nop     dword ptr [rax+rax+00h]
0x180036419  test    eax, eax
0x18003641b  jns     short loc_180036453
0x18003641d  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180036424  jz      short loc_180036463
0x180036426  mov     rcx, cs:WPP_GLOBAL_Control
0x18003642d  cmp     [rcx+48h], r14w
0x180036432  jz      short loc_180036463
0x180036434  mov     rcx, [rcx+40h]
0x180036438  mov     r9d, 6Bh ; 'k'
0x18003643e  mov     dword ptr [rsp+120h+var_F8], eax
0x180036442  mov     r8d, r12d
0x180036445  mov     dl, 5
0x180036447  mov     [rsp+120h+ResultLength], r13
0x18003644c  call    WPP_RECORDER_SF_D
0x180036451  jmp     short loc_180036463
0x180036453  mov     rcx, [rbp+57h+var_D0]; KeyHandle
0x180036457  call    cs:__imp_ZwDeleteKey
0x18003645e  nop     dword ptr [rax+rax+00h]
0x180036463  mov     rcx, [rsp+120h+var_F0]; KeyHandle
0x180036468  lea     rax, [rsp+120h+var_E0]
0x18003646d  mov     r9d, ebx; Length
0x180036470  mov     [rsp+120h+ResultLength], rax; ResultLength
0x180036475  lea     r8, [rbp+57h+KeyInformation]; KeyInformation
0x180036479  mov     edx, 2; KeyInformationClass
0x18003647e  call    cs:__imp_ZwQueryKey
0x180036485  nop     dword ptr [rax+rax+00h]
0x18003648a  test    eax, eax
0x18003648c  js      short loc_1800364A5
0x18003648e  cmp     dword ptr [rbp+57h+var_58+4], r14d
0x180036492  jnz     short loc_1800364A5
0x180036494  mov     rcx, [rsp+120h+var_F0]; KeyHandle
0x180036499  call    cs:__imp_ZwDeleteKey
0x1800364a0  nop     dword ptr [rax+rax+00h]
0x1800364a5  mov     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x1800364aa  lea     rax, [rsp+120h+var_E0]
0x1800364af  mov     r9d, ebx; Length
0x1800364b2  mov     [rsp+120h+ResultLength], rax; ResultLength
0x1800364b7  lea     r8, [rbp+57h+KeyInformation]; KeyInformation
0x1800364bb  mov     edx, 2; KeyInformationClass
0x1800364c0  call    cs:__imp_ZwQueryKey
0x1800364c7  nop     dword ptr [rax+rax+00h]
0x1800364cc  mov     ebx, eax
0x1800364ce  test    eax, eax
0x1800364d0  js      short loc_1800364E9
0x1800364d2  cmp     dword ptr [rbp+57h+var_58+4], r14d
0x1800364d6  jnz     short loc_1800364E9
0x1800364d8  mov     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x1800364dd  call    cs:__imp_ZwDeleteKey
0x1800364e4  nop     dword ptr [rax+rax+00h]
0x1800364e9  mov     rcx, [rbp+57h+var_D0]; Handle
0x1800364ed  cmp     rcx, rdi
0x1800364f0  jz      short loc_1800364FE
0x1800364f2  call    cs:__imp_ZwClose
0x1800364f9  nop     dword ptr [rax+rax+00h]
0x1800364fe  mov     rcx, [rsp+120h+var_F0]; Handle
0x180036503  cmp     rcx, rdi
0x180036506  jz      short loc_180036514
0x180036508  call    cs:__imp_ZwClose
0x18003650f  nop     dword ptr [rax+rax+00h]
0x180036514  mov     rcx, [rsp+120h+KeyHandle]; Handle
0x180036519  cmp     rcx, rdi
0x18003651c  jz      short loc_18003652A
0x18003651e  call    cs:__imp_ZwClose
0x180036525  nop     dword ptr [rax+rax+00h]
0x18003652a  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x18003652e  call    cs:__imp_RtlFreeUnicodeString
0x180036535  nop     dword ptr [rax+rax+00h]
0x18003653a  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x18003653e  call    cs:__imp_RtlFreeUnicodeString
0x180036545  nop     dword ptr [rax+rax+00h]
0x18003654a  mov     rcx, [rsp+120h+Handle]; Handle
0x18003654f  call    cs:__imp_ZwClose
0x180036556  nop     dword ptr [rax+rax+00h]
0x18003655b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180036562  jz      short loc_18003658F
0x180036564  mov     rcx, cs:WPP_GLOBAL_Control
0x18003656b  cmp     [rcx+48h], r14w
0x180036570  jz      short loc_18003658F
0x180036572  mov     rcx, [rcx+40h]
0x180036576  mov     r9d, 6Ch ; 'l'
0x18003657c  mov     dword ptr [rsp+120h+var_F8], ebx
0x180036580  mov     r8d, r12d
0x180036583  mov     dl, 5
0x180036585  mov     [rsp+120h+ResultLength], r13
0x18003658a  call    WPP_RECORDER_SF_D
0x18003658f  mov     eax, ebx
0x180036591  mov     rcx, [rbp+57h+var_38]
0x180036595  xor     rcx, rsp; StackCookie
0x180036598  call    __security_check_cookie
0x18003659d  mov     rbx, [rsp+120h+arg_10]
0x1800365a5  add     rsp, 0F0h
0x1800365ac  pop     r15
0x1800365ae  pop     r14
0x1800365b0  pop     r13
0x1800365b2  pop     r12
0x1800365b4  pop     rdi
0x1800365b5  pop     rsi
0x1800365b6  pop     rbp
0x1800365b7  retn
```
