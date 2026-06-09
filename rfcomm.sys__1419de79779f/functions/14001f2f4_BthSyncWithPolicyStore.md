# BthSyncWithPolicyStore

- ea: `0x14001f2f4`
- end: `0x14001f7d2`
- name: `BthSyncWithPolicyStore`
- size: `1246`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14001f7e0`
- `0x140037080`

## callees

- `0x14001ee8c`
- `0x14001f2f4`
- `0x14001fd40`
- `0x140034118`
- `0x140034290`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001f6fb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001f6fb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001f797`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001f797`
- `ntoskrnl!ZwClose` at `0x14001f7ac`
- `ntoskrnl!ZwClose` at `0x14001f7ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f546`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f5b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f622`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f717`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f731`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f74b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f546`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f5b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f622`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f717`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f731`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001f74b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f365`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f3af`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f3f2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f42f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f46c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f4a9`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f4e7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f564`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f5d2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f640`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f67e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f6bc`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f365`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f3af`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f3f2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f42f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f46c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f4a9`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f4e7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f564`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f5d2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f640`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f67e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001f6bc`

## string_xrefs

- `0x14001f49e`: `PM_LinkSecurityLevel`
- `0x14001f5c7`: `PM_ServicesAllowedList`
- `0x14001f673`: `PM_AllowPrepairing`

## pseudocode

```c
__int64 BthSyncWithPolicyStore()
{
  NTSTATUS v1; // edi
  KIRQL v2; // bl
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-29h] BYREF
  _OWORD v4[7]; // [rsp+40h] [rbp-19h] BYREF
  __int64 v5; // [rsp+C0h] [rbp+67h] BYREF
  HANDLE Handle; // [rsp+C8h] [rbp+6Fh] BYREF

  Handle = 0;
  LODWORD(v5) = 0;
  DestinationString = 0;
  memset(v4, 0, 0x50u);
  if ( !g_PolicyStorePath.Buffer )
    return 3221225473LL;
  v1 = BthOpenKeyEx(0, &g_PolicyStorePath, &Handle);
  if ( v1 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"PM_AllowBluetooth");
    if ( (int)BthQueryKeyValueEx(Handle, &DestinationString, v4, 0) >= 0 && (v4[0] & 0xFFFFFFFD) == 0 )
      DWORD1(v4[4]) |= 1u;
    RtlInitUnicodeString(&DestinationString, L"PM_AllowDiscoverableMode");
    if ( (int)BthQueryKeyValueEx(Handle, &DestinationString, (char *)v4 + 4, 0) >= 0 && DWORD1(v4[0]) <= 1 )
      DWORD1(v4[4]) |= 2u;
    RtlInitUnicodeString(&DestinationString, L"PM_AllowConnectableMode");
    if ( (int)BthQueryKeyValueEx(Handle, &DestinationString, (char *)v4 + 8, 0) >= 0 && DWORD2(v4[0]) <= 1 )
      DWORD1(v4[4]) |= 4u;
    RtlInitUnicodeString(&DestinationString, L"PM_AllowAdvertising");
    if ( (int)BthQueryKeyValueEx(Handle, &DestinationString, (char *)v4 + 12, 0) >= 0 && HIDWORD(v4[0]) <= 1 )
      DWORD1(v4[4]) |= 8u;
    RtlInitUnicodeString(&DestinationString, L"PM_AllowOutOfBandPairing");
    if ( (int)BthQueryKeyValueEx(Handle, &DestinationString, &v4[1], 0) >= 0 && LODWORD(v4[1]) <= 1 )
      DWORD1(v4[4]) |= 0x10u;
    RtlInitUnicodeString(&DestinationString, L"PM_LinkSecurityLevel");
    if ( (int)BthQueryKeyValueEx(Handle, &DestinationString, (char *)&v4[1] + 4, 0) >= 0 && DWORD1(v4[1]) <= 2 )
      DWORD1(v4[4]) |= 0x20u;
    RtlInitUnicodeString(&DestinationString, L"PM_LocalDeviceName");
    if ( (int)ReadVariableLengthPolicy(Handle, &DestinationString, (__int64)&v4[2], (__int64)&v5) < 0
      || (unsigned int)v5 > 0xFFFF )
    {
      if ( *(_QWORD *)&v4[2] )
      {
        ExFreePoolWithTag(*(PVOID *)&v4[2], 0);
        *(_OWORD *)((char *)&v4[1] + 8) = 0;
      }
    }
    else
    {
      WORD5(v4[1]) = v5;
      if ( (unsigned __int16)v5 >= 2u )
      {
        DWORD1(v4[4]) |= 0x40u;
        WORD4(v4[1]) = v5 - 2;
      }
    }
    RtlInitUnicodeString(&DestinationString, L"PM_DevicesAllowedList");
    if ( (int)ReadVariableLengthPolicy(Handle, &DestinationString, (__int64)&v4[2] + 8, (__int64)&v5) < 0 )
    {
      if ( *((_QWORD *)&v4[2] + 1) )
      {
        ExFreePoolWithTag(*((PVOID *)&v4[2] + 1), 0);
        *((_QWORD *)&v4[2] + 1) = 0;
        DWORD2(v4[4]) = 0;
      }
    }
    else
    {
      DWORD1(v4[4]) |= 0x80u;
      DWORD2(v4[4]) = (unsigned int)v5 >> 3;
    }
    RtlInitUnicodeString(&DestinationString, L"PM_ServicesAllowedList");
    if ( (int)ReadVariableLengthPolicy(Handle, &DestinationString, (__int64)&v4[3], (__int64)&v5) < 0 )
    {
      if ( *(_QWORD *)&v4[3] )
      {
        ExFreePoolWithTag(*(PVOID *)&v4[3], 0);
        *(_QWORD *)&v4[3] = 0;
        HIDWORD(v4[4]) = 0;
      }
    }
    else
    {
      DWORD1(v4[4]) |= 0x100u;
      HIDWORD(v4[4]) = (unsigned int)v5 >> 4;
    }
    RtlInitUnicodeString(&DestinationString, L"PM_RequireRestrictedMode");
    if ( (int)BthQueryKeyValueEx(Handle, &DestinationString, (char *)&v4[3] + 8, 0) >= 0 && DWORD2(v4[3]) <= 1 )
      DWORD1(v4[4]) |= 0x200u;
    RtlInitUnicodeString(&DestinationString, L"PM_AllowPrepairing");
    if ( (int)BthQueryKeyValueEx(Handle, &DestinationString, (char *)&v4[3] + 12, 0) >= 0 && HIDWORD(v4[3]) <= 1 )
      DWORD1(v4[4]) |= 0x400u;
    RtlInitUnicodeString(&DestinationString, L"PM_SetMinimumEncryptionKeySize");
    if ( (int)BthQueryKeyValueEx(Handle, &DestinationString, &v4[4], 0) >= 0
      && (unsigned int)(LODWORD(v4[4]) - 1) <= 0xF )
    {
      DWORD1(v4[4]) |= 0x800u;
    }
    v2 = KeAcquireSpinLockRaiseToDpc(&g_PolicyLock);
    if ( P )
      ExFreePoolWithTag(P, 0);
    if ( *(&P + 1) )
      ExFreePoolWithTag(*(&P + 1), 0);
    if ( xmmword_14002D230 )
      ExFreePoolWithTag(xmmword_14002D230, 0);
    g_Policies = v4[0];
    *(_OWORD *)&P = v4[2];
    xmmword_14002D210 = v4[1];
    *(_OWORD *)byte_14002D240 = v4[4];
    *(_OWORD *)&xmmword_14002D230 = v4[3];
    KeReleaseSpinLock(&g_PolicyLock, v2);
  }
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x14001f2f4  mov     [rsp-8+arg_10], rbx
0x14001f2f9  push    rbp
0x14001f2fa  push    rsi
0x14001f2fb  push    rdi
0x14001f2fc  push    r14
0x14001f2fe  push    r15
0x14001f300  lea     rbp, [rsp-37h]
0x14001f305  sub     rsp, 90h
0x14001f30c  xor     esi, esi
0x14001f30e  lea     rcx, [rbp+57h+var_70]; void *
0x14001f312  xorps   xmm0, xmm0
0x14001f315  mov     [rbp+57h+Handle], rsi
0x14001f319  xor     edx, edx; Val
0x14001f31b  mov     dword ptr [rbp+57h+arg_0], esi
0x14001f31e  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14001f322  lea     r8d, [rsi+50h]; Size
0x14001f326  call    memset
0x14001f32b  cmp     cs:?g_PolicyStorePath@@3U_UNICODE_STRING@@A.Buffer, rsi; _UNICODE_STRING g_PolicyStorePath ...
0x14001f332  jnz     short loc_14001F33E
0x14001f334  mov     eax, 0C0000001h
0x14001f339  jmp     loc_14001F7BA
0x14001f33e  lea     r8, [rbp+57h+Handle]
0x14001f342  xor     ecx, ecx
0x14001f344  lea     rdx, ?g_PolicyStorePath@@3U_UNICODE_STRING@@A; _UNICODE_STRING g_PolicyStorePath
0x14001f34b  call    BthOpenKeyEx
0x14001f350  mov     edi, eax
0x14001f352  test    eax, eax
0x14001f354  js      loc_14001F7A3
0x14001f35a  lea     rdx, aPmAllowbluetoo; "PM_AllowBluetooth"
0x14001f361  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001f365  call    cs:__imp_RtlInitUnicodeString
0x14001f36c  nop     dword ptr [rax+rax+00h]
0x14001f371  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x14001f375  lea     r8, [rbp+57h+var_70]; void *
0x14001f379  mov     r14d, 4
0x14001f37f  mov     [rsp+0B0h+var_90], rsi; __int64
0x14001f384  mov     r9d, r14d
0x14001f387  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14001f38b  call    BthQueryKeyValueEx
0x14001f390  lea     ebx, [r14-3]
0x14001f394  test    eax, eax
0x14001f396  js      short loc_14001F3A4
0x14001f398  test    dword ptr [rbp+57h+var_70], 0FFFFFFFDh
0x14001f39f  jnz     short loc_14001F3A4
0x14001f3a1  or      dword ptr [rbp+57h+var_30+4], ebx
0x14001f3a4  lea     rdx, aPmAllowdiscove; "PM_AllowDiscoverableMode"
0x14001f3ab  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001f3af  call    cs:__imp_RtlInitUnicodeString
0x14001f3b6  nop     dword ptr [rax+rax+00h]
0x14001f3bb  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x14001f3bf  lea     r8, [rbp+57h+var_70+4]; void *
0x14001f3c3  mov     r9d, r14d
0x14001f3c6  mov     [rsp+0B0h+var_90], rsi; __int64
0x14001f3cb  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14001f3cf  call    BthQueryKeyValueEx
0x14001f3d4  mov     r15d, 2
0x14001f3da  test    eax, eax
0x14001f3dc  js      short loc_14001F3E7
0x14001f3de  cmp     dword ptr [rbp+57h+var_70+4], ebx
0x14001f3e1  ja      short loc_14001F3E7
0x14001f3e3  or      dword ptr [rbp+57h+var_30+4], r15d
0x14001f3e7  lea     rdx, aPmAllowconnect; "PM_AllowConnectableMode"
0x14001f3ee  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001f3f2  call    cs:__imp_RtlInitUnicodeString
0x14001f3f9  nop     dword ptr [rax+rax+00h]
0x14001f3fe  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x14001f402  lea     r8, [rbp+57h+var_70+8]; void *
0x14001f406  mov     r9d, r14d
0x14001f409  mov     [rsp+0B0h+var_90], rsi; __int64
0x14001f40e  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14001f412  call    BthQueryKeyValueEx
0x14001f417  test    eax, eax
0x14001f419  js      short loc_14001F424
0x14001f41b  cmp     dword ptr [rbp+57h+var_70+8], ebx
0x14001f41e  ja      short loc_14001F424
0x14001f420  or      dword ptr [rbp+57h+var_30+4], r14d
0x14001f424  lea     rdx, aPmAllowadverti; "PM_AllowAdvertising"
0x14001f42b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001f42f  call    cs:__imp_RtlInitUnicodeString
0x14001f436  nop     dword ptr [rax+rax+00h]
0x14001f43b  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x14001f43f  lea     r8, [rbp+57h+var_70+0Ch]; void *
0x14001f443  mov     r9d, r14d
0x14001f446  mov     [rsp+0B0h+var_90], rsi; __int64
0x14001f44b  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14001f44f  call    BthQueryKeyValueEx
0x14001f454  test    eax, eax
0x14001f456  js      short loc_14001F461
0x14001f458  cmp     dword ptr [rbp+57h+var_70+0Ch], ebx
0x14001f45b  ja      short loc_14001F461
0x14001f45d  or      dword ptr [rbp+57h+var_30+4], 8
0x14001f461  lea     rdx, aPmAllowoutofba; "PM_AllowOutOfBandPairing"
0x14001f468  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001f46c  call    cs:__imp_RtlInitUnicodeString
0x14001f473  nop     dword ptr [rax+rax+00h]
0x14001f478  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x14001f47c  lea     r8, [rbp+57h+var_60]; void *
0x14001f480  mov     r9d, r14d
0x14001f483  mov     [rsp+0B0h+var_90], rsi; __int64
0x14001f488  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14001f48c  call    BthQueryKeyValueEx
0x14001f491  test    eax, eax
0x14001f493  js      short loc_14001F49E
0x14001f495  cmp     dword ptr [rbp+57h+var_60], ebx
0x14001f498  ja      short loc_14001F49E
0x14001f49a  or      dword ptr [rbp+57h+var_30+4], 10h
0x14001f49e  lea     rdx, aPmLinksecurity; "PM_LinkSecurityLevel"
0x14001f4a5  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001f4a9  call    cs:__imp_RtlInitUnicodeString
0x14001f4b0  nop     dword ptr [rax+rax+00h]
0x14001f4b5  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x14001f4b9  lea     r8, [rbp+57h+var_60+4]; void *
0x14001f4bd  mov     r9d, r14d
0x14001f4c0  mov     [rsp+0B0h+var_90], rsi; __int64
0x14001f4c5  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14001f4c9  call    BthQueryKeyValueEx
0x14001f4ce  test    eax, eax
0x14001f4d0  js      short loc_14001F4DC
0x14001f4d2  cmp     dword ptr [rbp+57h+var_60+4], r15d
0x14001f4d6  ja      short loc_14001F4DC
0x14001f4d8  or      dword ptr [rbp+57h+var_30+4], 20h
0x14001f4dc  lea     rdx, aPmLocaldevicen; "PM_LocalDeviceName"
0x14001f4e3  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001f4e7  call    cs:__imp_RtlInitUnicodeString
0x14001f4ee  nop     dword ptr [rax+rax+00h]
0x14001f4f3  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x14001f4f7  lea     rax, [rbp+57h+arg_0]
0x14001f4fb  mov     [rsp+0B0h+var_88], rax; __int64
0x14001f500  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14001f504  lea     rax, [rbp+57h+var_50]
0x14001f508  mov     r8d, r15d
0x14001f50b  mov     [rsp+0B0h+var_90], rax; __int64
0x14001f510  call    ReadVariableLengthPolicy
0x14001f515  test    eax, eax
0x14001f517  js      short loc_14001F53B
0x14001f519  mov     eax, dword ptr [rbp+57h+arg_0]
0x14001f51c  cmp     eax, 0FFFFh
0x14001f521  ja      short loc_14001F53B
0x14001f523  mov     word ptr [rbp+57h+var_60+0Ah], ax
0x14001f527  cmp     ax, r15w
0x14001f52b  jb      short loc_14001F559
0x14001f52d  sub     ax, r15w
0x14001f531  or      dword ptr [rbp+57h+var_30+4], 40h
0x14001f535  mov     word ptr [rbp+57h+var_60+8], ax
0x14001f539  jmp     short loc_14001F559
0x14001f53b  mov     rcx, [rbp+57h+var_50]; P
0x14001f53f  test    rcx, rcx
0x14001f542  jz      short loc_14001F559
0x14001f544  xor     edx, edx; Tag
0x14001f546  call    cs:__imp_ExFreePoolWithTag
0x14001f54d  nop     dword ptr [rax+rax+00h]
0x14001f552  xorps   xmm0, xmm0
0x14001f555  movups  [rbp+57h+var_60+8], xmm0
0x14001f559  lea     rdx, aPmDevicesallow; "PM_DevicesAllowedList"
0x14001f560  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001f564  call    cs:__imp_RtlInitUnicodeString
0x14001f56b  nop     dword ptr [rax+rax+00h]
0x14001f570  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x14001f574  lea     rax, [rbp+57h+arg_0]
0x14001f578  mov     [rsp+0B0h+var_88], rax; __int64
0x14001f57d  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14001f581  lea     rax, [rbp+57h+P]
0x14001f585  mov     r8d, 8
0x14001f58b  mov     [rsp+0B0h+var_90], rax; __int64
0x14001f590  call    ReadVariableLengthPolicy
0x14001f595  test    eax, eax
0x14001f597  js      short loc_14001F5A9
0x14001f599  mov     eax, dword ptr [rbp+57h+arg_0]
0x14001f59c  shr     eax, 3
0x14001f59f  bts     dword ptr [rbp+57h+var_30+4], 7
0x14001f5a4  mov     dword ptr [rbp+57h+var_30+8], eax
0x14001f5a7  jmp     short loc_14001F5C7
0x14001f5a9  mov     rcx, [rbp+57h+P]; P
0x14001f5ad  test    rcx, rcx
0x14001f5b0  jz      short loc_14001F5C7
0x14001f5b2  xor     edx, edx; Tag
0x14001f5b4  call    cs:__imp_ExFreePoolWithTag
0x14001f5bb  nop     dword ptr [rax+rax+00h]
0x14001f5c0  mov     [rbp+57h+P], rsi
0x14001f5c4  mov     dword ptr [rbp+57h+var_30+8], esi
0x14001f5c7  lea     rdx, aPmServicesallo; "PM_ServicesAllowedList"
0x14001f5ce  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001f5d2  call    cs:__imp_RtlInitUnicodeString
0x14001f5d9  nop     dword ptr [rax+rax+00h]
0x14001f5de  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x14001f5e2  lea     rax, [rbp+57h+arg_0]
0x14001f5e6  mov     [rsp+0B0h+var_88], rax; __int64
0x14001f5eb  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14001f5ef  lea     rax, [rbp+57h+var_40]
0x14001f5f3  mov     r8d, 10h
0x14001f5f9  mov     [rsp+0B0h+var_90], rax; __int64
0x14001f5fe  call    ReadVariableLengthPolicy
0x14001f603  test    eax, eax
0x14001f605  js      short loc_14001F617
0x14001f607  mov     eax, dword ptr [rbp+57h+arg_0]
0x14001f60a  shr     eax, 4
0x14001f60d  bts     dword ptr [rbp+57h+var_30+4], 8
0x14001f612  mov     dword ptr [rbp+57h+var_30+0Ch], eax
0x14001f615  jmp     short loc_14001F635
0x14001f617  mov     rcx, [rbp+57h+var_40]; P
0x14001f61b  test    rcx, rcx
0x14001f61e  jz      short loc_14001F635
0x14001f620  xor     edx, edx; Tag
0x14001f622  call    cs:__imp_ExFreePoolWithTag
0x14001f629  nop     dword ptr [rax+rax+00h]
0x14001f62e  mov     [rbp+57h+var_40], rsi
0x14001f632  mov     dword ptr [rbp+57h+var_30+0Ch], esi
0x14001f635  lea     rdx, aPmRequirerestr; "PM_RequireRestrictedMode"
0x14001f63c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001f640  call    cs:__imp_RtlInitUnicodeString
0x14001f647  nop     dword ptr [rax+rax+00h]
0x14001f64c  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x14001f650  lea     r8, [rbp+57h+var_40+8]; void *
0x14001f654  mov     r9d, r14d
0x14001f657  mov     [rsp+0B0h+var_90], rsi; __int64
0x14001f65c  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14001f660  call    BthQueryKeyValueEx
0x14001f665  test    eax, eax
0x14001f667  js      short loc_14001F673
0x14001f669  cmp     dword ptr [rbp+57h+var_40+8], ebx
0x14001f66c  ja      short loc_14001F673
0x14001f66e  bts     dword ptr [rbp+57h+var_30+4], 9
0x14001f673  lea     rdx, aPmAllowprepair; "PM_AllowPrepairing"
0x14001f67a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001f67e  call    cs:__imp_RtlInitUnicodeString
0x14001f685  nop     dword ptr [rax+rax+00h]
0x14001f68a  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x14001f68e  lea     r8, [rbp+57h+var_40+0Ch]; void *
0x14001f692  mov     r9d, r14d
0x14001f695  mov     [rsp+0B0h+var_90], rsi; __int64
0x14001f69a  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14001f69e  call    BthQueryKeyValueEx
0x14001f6a3  test    eax, eax
0x14001f6a5  js      short loc_14001F6B1
0x14001f6a7  cmp     dword ptr [rbp+57h+var_40+0Ch], ebx
0x14001f6aa  ja      short loc_14001F6B1
0x14001f6ac  bts     dword ptr [rbp+57h+var_30+4], 0Ah
0x14001f6b1  lea     rdx, aPmSetminimumen; "PM_SetMinimumEncryptionKeySize"
0x14001f6b8  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001f6bc  call    cs:__imp_RtlInitUnicodeString
0x14001f6c3  nop     dword ptr [rax+rax+00h]
0x14001f6c8  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x14001f6cc  lea     r8, [rbp+57h+var_30]; void *
0x14001f6d0  mov     r9d, r14d
0x14001f6d3  mov     [rsp+0B0h+var_90], rsi; __int64
0x14001f6d8  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x14001f6dc  call    BthQueryKeyValueEx
0x14001f6e1  test    eax, eax
0x14001f6e3  js      short loc_14001F6F4
0x14001f6e5  mov     eax, dword ptr [rbp+57h+var_30]
0x14001f6e8  dec     eax
0x14001f6ea  cmp     eax, 0Fh
0x14001f6ed  ja      short loc_14001F6F4
0x14001f6ef  bts     dword ptr [rbp+57h+var_30+4], 0Bh
0x14001f6f4  lea     rcx, ?g_PolicyLock@@3_KA; SpinLock
0x14001f6fb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001f702  nop     dword ptr [rax+rax+00h]
0x14001f707  mov     rcx, qword ptr cs:P; P
0x14001f70e  mov     bl, al
0x14001f710  test    rcx, rcx
0x14001f713  jz      short loc_14001F723
0x14001f715  xor     edx, edx; Tag
0x14001f717  call    cs:__imp_ExFreePoolWithTag
0x14001f71e  nop     dword ptr [rax+rax+00h]
0x14001f723  mov     rcx, qword ptr cs:P+8; P
0x14001f72a  test    rcx, rcx
0x14001f72d  jz      short loc_14001F73D
0x14001f72f  xor     edx, edx; Tag
0x14001f731  call    cs:__imp_ExFreePoolWithTag
0x14001f738  nop     dword ptr [rax+rax+00h]
0x14001f73d  mov     rcx, qword ptr cs:xmmword_14002D230; P
0x14001f744  test    rcx, rcx
0x14001f747  jz      short loc_14001F757
0x14001f749  xor     edx, edx; Tag
0x14001f74b  call    cs:__imp_ExFreePoolWithTag
0x14001f752  nop     dword ptr [rax+rax+00h]
0x14001f757  movaps  xmm0, [rbp+57h+var_70]
0x14001f75b  lea     rcx, ?g_PolicyLock@@3_KA; SpinLock
0x14001f762  movaps  xmm1, [rbp+57h+var_60]
0x14001f766  mov     dl, bl; NewIrql
0x14001f768  movaps  cs:?g_Policies@@3UPolicies@@A, xmm0; Policies g_Policies
0x14001f76f  movaps  xmm0, xmmword ptr [rbp+7]
0x14001f773  movaps  cs:P, xmm0
0x14001f77a  movaps  xmm0, [rbp+57h+var_30]
0x14001f77e  movaps  cs:xmmword_14002D210, xmm1
0x14001f785  movaps  xmm1, xmmword ptr [rbp+57h+var_40]
0x14001f789  movaps  xmmword ptr cs:byte_14002D240, xmm0
0x14001f790  movaps  cs:xmmword_14002D230, xmm1
0x14001f797  call    cs:__imp_KeReleaseSpinLock
0x14001f79e  nop     dword ptr [rax+rax+00h]
0x14001f7a3  mov     rcx, [rbp+57h+Handle]; Handle
0x14001f7a7  test    rcx, rcx
0x14001f7aa  jz      short loc_14001F7B8
0x14001f7ac  call    cs:__imp_ZwClose
0x14001f7b3  nop     dword ptr [rax+rax+00h]
0x14001f7b8  mov     eax, edi
0x14001f7ba  mov     rbx, [rsp+0B0h+arg_10]
0x14001f7c2  add     rsp, 90h
0x14001f7c9  pop     r15
0x14001f7cb  pop     r14
  ... truncated ...
```
