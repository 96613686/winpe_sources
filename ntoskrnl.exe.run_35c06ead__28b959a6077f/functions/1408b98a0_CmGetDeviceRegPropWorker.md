# _CmGetDeviceRegPropWorker

- ea: `0x1408b98a0`
- end: `0x1408b9fc0`
- name: `_CmGetDeviceRegPropWorker`
- size: `1824`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1408b9700`

## callees

- `0x140414d30`
- `0x140466d5c`
- `0x140478b58`
- `0x14053e920`
- `0x1406d9d70`
- `0x1406daa70`
- `0x1406e8590`
- `0x1408b9700`
- `0x1408b98a0`
- `0x1408ba060`
- `0x1408be7f0`
- `0x14095f710`

## string_xrefs

- `0x1408b9c7b`: `Service`
- `0x1408b9c93`: `CompatibleIDs`
- `0x1408b9ec0`: `ConfigFlags`
- `0x1408b9dc1`: `Security`

## pseudocode

```c
__int64 __fastcall CmGetDeviceRegPropWorker(
        __int64 a1,
        const wchar_t *a2,
        void *a3,
        unsigned int a4,
        _DWORD *a5,
        NTSTRSAFE_PWSTR pszDest,
        unsigned int *a7,
        __int16 a8)
{
  __int64 v8; // r10
  const wchar_t *v11; // r11
  unsigned int v12; // edx
  wchar_t *v13; // r15
  NTSTATUS inited; // edi
  const wchar_t *v15; // r8
  int v17; // r8d
  NTSTATUS DeviceRegProp; // eax
  int v19; // ecx
  int InstallerClassRegProp; // eax
  unsigned int v21; // r12d
  int v22; // eax
  HANDLE v23; // rdx
  NTSTATUS v24; // eax
  NTSTATUS v25; // edx
  int v26; // eax
  wchar_t *v27; // rax
  const wchar_t *v28; // r8
  __int64 v29; // rax
  int v30; // r9d
  NTSTRSAFE_PWSTR *ppszDestEnd; // [rsp+20h] [rbp-E0h]
  size_t *pcbRemaining; // [rsp+28h] [rbp-D8h]
  ULONG dwFlags; // [rsp+30h] [rbp-D0h]
  unsigned int cbDest; // [rsp+60h] [rbp-A0h]
  unsigned int cbDest_4; // [rsp+64h] [rbp-9Ch] BYREF
  int v36; // [rsp+68h] [rbp-98h] BYREF
  HANDLE Handle; // [rsp+70h] [rbp-90h] BYREF
  int v38; // [rsp+78h] [rbp-88h] BYREF
  __int64 v39; // [rsp+80h] [rbp-80h]
  STRSAFE_PCNZWCH pszSrc; // [rsp+88h] [rbp-78h]
  UNICODE_STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v42[76]; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v43; // [rsp+ECh] [rbp-14h]

  v8 = a1;
  v11 = a2;
  v39 = a1;
  pszSrc = a2;
  Handle = 0;
  v36 = 0;
  cbDest_4 = 0;
  v38 = 0;
  DestinationString = 0;
  if ( a8 )
    return 3221225485LL;
  if ( !a7 )
    return 3221225485LL;
  if ( !a5 )
    return 3221225485LL;
  v12 = *a7;
  if ( *a7 )
  {
    if ( !pszDest )
      return 3221225485LL;
  }
  v13 = 0;
  *a7 = 0;
  if ( v12 )
    v13 = pszDest;
  cbDest = v12;
  *a5 = 0;
  if ( a4 - 1 > 0x24 )
    return 3221226032LL;
  if ( a4 != 37 )
  {
    if ( a4 != 25 )
    {
      switch ( a4 )
      {
        case 1u:
        case 2u:
        case 3u:
        case 5u:
        case 8u:
        case 9u:
        case 0xAu:
        case 0xBu:
        case 0xCu:
        case 0xDu:
        case 0xEu:
        case 0xFu:
        case 0x10u:
        case 0x11u:
        case 0x12u:
        case 0x13u:
        case 0x14u:
        case 0x15u:
        case 0x16u:
        case 0x17u:
        case 0x18u:
        case 0x1Au:
        case 0x1Bu:
        case 0x1Cu:
        case 0x1Du:
        case 0x1Eu:
        case 0x1Fu:
        case 0x20u:
        case 0x21u:
        case 0x22u:
        case 0x23u:
        case 0x24u:
          goto LABEL_10;
        default:
          return 3221226032LL;
      }
    }
    return 3221226032LL;
  }
LABEL_10:
  inited = 0;
  if ( !a3 )
  {
    inited = CmOpenDeviceRegKey(a1, (_DWORD)v11, 16, 0, 33554433, 0, (__int64)&Handle, 0);
    if ( inited < 0 )
      goto LABEL_25;
    v12 = cbDest;
    v8 = v39;
    v11 = pszSrc;
  }
  switch ( a4 )
  {
    case 0x1Du:
LABEL_14:
      switch ( a4 )
      {
        case 1u:
          v15 = L"DeviceDesc";
          goto LABEL_40;
        case 2u:
        case 4u:
        case 6u:
        case 7u:
        case 0xAu:
        case 0xBu:
        case 0xFu:
        case 0x14u:
        case 0x15u:
        case 0x16u:
        case 0x17u:
        case 0x19u:
        case 0x1Fu:
        case 0x20u:
        case 0x21u:
        case 0x23u:
        case 0x24u:
          inited = -1073741264;
          goto LABEL_25;
        case 3u:
          v15 = L"CompatibleIDs";
          goto LABEL_40;
        case 5u:
          v15 = L"Service";
          goto LABEL_40;
        case 8u:
          v15 = L"Class";
          goto LABEL_40;
        case 9u:
          v15 = L"ClassGUID";
          goto LABEL_40;
        case 0xCu:
          v15 = L"Mfg";
          goto LABEL_40;
        case 0xDu:
          v15 = L"FriendlyName";
          goto LABEL_40;
        case 0xEu:
          v15 = L"LocationInformation";
          goto LABEL_40;
        case 0x10u:
          v15 = L"Capabilities";
          goto LABEL_40;
        case 0x11u:
          v15 = L"UINumber";
          goto LABEL_40;
        case 0x12u:
          v15 = L"UpperFilters";
          goto LABEL_40;
        case 0x13u:
          v15 = L"LowerFilters";
          goto LABEL_40;
        case 0x18u:
          v15 = L"Security";
          goto LABEL_40;
        case 0x1Au:
          v15 = L"DeviceType";
          goto LABEL_40;
        case 0x1Bu:
          v15 = L"Exclusive";
          goto LABEL_40;
        case 0x1Cu:
          v15 = L"DeviceCharacteristics";
          goto LABEL_40;
        case 0x1Du:
          v15 = L"Address";
          goto LABEL_40;
        case 0x1Eu:
          v15 = L"UINumberDescFormat";
          goto LABEL_40;
        case 0x22u:
          v15 = L"RemovalPolicy";
          goto LABEL_40;
        case 0x25u:
          v15 = L"ContainerID";
          goto LABEL_40;
        default:
          return 3221226032LL;
      }
    case 8u:
      v17 = (int)Handle;
      v36 = 0;
      if ( a3 )
        v17 = (int)a3;
      cbDest_4 = 78;
      DeviceRegProp = CmGetDeviceRegProp(v8, (_DWORD)v11, v17, 9, (__int64)&v36, (__int64)v42, (__int64)&cbDest_4, 0);
      inited = DeviceRegProp;
      if ( DeviceRegProp == -1073741789 )
      {
        inited = -1073741595;
        goto LABEL_25;
      }
      if ( DeviceRegProp )
        goto LABEL_25;
      v19 = v39;
      v43 = 0;
      *a7 = cbDest;
      InstallerClassRegProp = CmGetInstallerClassRegProp(
                                v19,
                                (unsigned int)v42,
                                0,
                                8,
                                (__int64)a5,
                                (__int64)v13,
                                (__int64)a7);
      inited = InstallerClassRegProp;
LABEL_23:
      if ( InstallerClassRegProp == -1073741772 )
LABEL_24:
        inited = -1073741275;
      goto LABEL_25;
    case 0x17u:
      v27 = wcschr(v11, 0x5Cu);
      if ( v27 )
      {
        v28 = pszSrc;
        *a7 = (_DWORD)v27 - (_DWORD)pszSrc + 2;
        *a5 = 1;
        v29 = *a7;
        if ( cbDest < (unsigned int)v29 )
          inited = -1073741789;
        else
          inited = RtlStringCbCopyNExW(v13, cbDest, v28, v29 - 2, ppszDestEnd, pcbRemaining, dwFlags);
      }
      else
      {
        inited = -1073741811;
      }
      goto LABEL_25;
  }
  if ( a4 != 36 )
  {
    switch ( a4 )
    {
      case 0xFu:
        v21 = 1;
        goto LABEL_33;
      case 0x14u:
        v21 = 2;
        goto LABEL_33;
      case 0x15u:
        v21 = 3;
        goto LABEL_33;
      case 0x16u:
        v21 = 4;
        goto LABEL_33;
      case 0x1Fu:
        v21 = 5;
        goto LABEL_33;
      case 0x20u:
        v21 = 6;
        goto LABEL_33;
      case 0x21u:
        v21 = 10;
        goto LABEL_33;
      case 0x23u:
        v21 = 11;
LABEL_33:
        inited = RtlInitUnicodeStringEx(&DestinationString, v11);
        if ( inited < 0 )
          goto LABEL_25;
        if ( !*(_QWORD *)(v39 + 256) )
        {
          inited = -1073741822;
          goto LABEL_25;
        }
        v22 = guard_dispatch_icall_no_overrides(v39, &DestinationString, v21, v13);
        inited = v22;
        if ( v22 == -2147483643 )
        {
          inited = -1073741789;
LABEL_37:
          *a7 = cbDest;
          *a5 = MapCmDevicePropertyToRegType(a4);
          goto LABEL_25;
        }
        if ( v22 == -1073741772 )
          goto LABEL_24;
        if ( v22 >= 0 || v22 == -1073741789 )
          goto LABEL_37;
        break;
      default:
        switch ( a4 )
        {
          case 2u:
            v15 = L"HardwareID";
            break;
          case 0xAu:
            v15 = L"Driver";
            break;
          case 0xBu:
            v15 = L"ConfigFlags";
            break;
          default:
            goto LABEL_14;
        }
LABEL_40:
        cbDest_4 = v12;
        v23 = Handle;
        if ( a3 )
          v23 = a3;
        v24 = guard_dispatch_icall_no_overrides(v8, v23, v15, &v36);
        v25 = v24;
        if ( v24 == -1073741772 || v24 == -1073741444 )
          goto LABEL_24;
        if ( (int)(v24 + 0x80000000) >= 0 && v24 != -1073741789 )
        {
          inited = v24;
          goto LABEL_25;
        }
        v26 = v36;
        if ( v36 == 1 )
        {
          if ( cbDest_4 < 2 )
            goto LABEL_24;
        }
        else if ( v36 == 7 )
        {
          if ( cbDest_4 < 2 )
            goto LABEL_24;
        }
        else if ( cbDest_4 != 4 && v36 == 4 )
        {
          goto LABEL_24;
        }
        *a7 = cbDest_4;
        *a5 = v26;
        if ( v25 || !cbDest )
          inited = -1073741789;
        goto LABEL_25;
    }
    goto LABEL_25;
  }
  v30 = (int)Handle;
  if ( a3 )
    v30 = (int)a3;
  InstallerClassRegProp = PnpGetObjectProperty(
                            v8,
                            (_DWORD)v11,
                            1,
                            v30,
                            0,
                            (__int64)&DEVPKEY_Device_LocationPaths,
                            (__int64)&v38,
                            (__int64)v13,
                            v12,
                            (__int64)a7,
                            0);
  *a5 = 7;
  inited = InstallerClassRegProp;
  if ( InstallerClassRegProp < 0 )
    goto LABEL_23;
LABEL_25:
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1408b98a0  push    rbp
0x1408b98a2  push    rbx
0x1408b98a3  push    rsi
0x1408b98a4  push    r13
0x1408b98a6  push    r14
0x1408b98a8  lea     rbp, [rsp-10h]
0x1408b98ad  sub     rsp, 110h
0x1408b98b4  mov     rax, cs:__security_cookie
0x1408b98bb  xor     rax, rsp
0x1408b98be  mov     [rbp+30h+var_40], rax
0x1408b98c2  movzx   eax, [rbp+30h+arg_38]
0x1408b98c6  xorps   xmm0, xmm0
0x1408b98c9  mov     r14, [rbp+30h+arg_20]
0x1408b98cd  mov     r10, rcx
0x1408b98d0  mov     rsi, [rbp+30h+arg_30]
0x1408b98d4  mov     r13, r8
0x1408b98d7  movsxd  rbx, r9d
0x1408b98da  mov     r11, rdx
0x1408b98dd  xor     r9d, r9d
0x1408b98e0  mov     [rbp+30h+var_B0], rcx
0x1408b98e4  mov     rcx, [rbp+30h+pszDest]
0x1408b98e8  mov     [rbp+30h+pszSrc], rdx
0x1408b98ec  mov     [rsp+130h+Handle], r9
0x1408b98f1  mov     [rsp+130h+var_C8], r9d
0x1408b98f6  mov     dword ptr [rsp+130h+cbDest+4], r9d
0x1408b98fb  mov     [rsp+130h+var_B8], r9d
0x1408b9900  movups  xmmword ptr [rbp+30h+DestinationString.Length], xmm0
0x1408b9904  test    eax, eax
0x1408b9906  jnz     loc_1408B9E9C
0x1408b990c  test    rsi, rsi
0x1408b990f  jz      loc_1408B9E9C
0x1408b9915  test    r14, r14
0x1408b9918  jz      loc_1408B9E9C
0x1408b991e  mov     edx, [rsi]
0x1408b9920  test    edx, edx
0x1408b9922  jz      short loc_1408B992D
0x1408b9924  test    rcx, rcx
0x1408b9927  jz      loc_1408B9E9C
0x1408b992d  mov     [rsp+130h+var_28], r12
0x1408b9935  test    edx, edx
0x1408b9937  mov     [rsp+130h+var_30], r15
0x1408b993f  lea     r12d, [rbx-1]; switch 37 cases
0x1408b9943  mov     r15, r9
0x1408b9946  mov     [rsi], r9d
0x1408b9949  cmovnz  r15, rcx
0x1408b994d  mov     dword ptr [rsp+130h+cbDest], edx
0x1408b9951  mov     [r14], r9d
0x1408b9954  cmp     r12d, 24h ; '$'
0x1408b9958  ja      def_1408B99E2; jumptable 00000001408B99E2 default case
0x1408b995e  lea     r8, cs:140000000h
0x1408b9965  cmp     ebx, 25h ; '%'
0x1408b9968  jnz     loc_1408B99F4
0x1408b996e  mov     [rsp+130h+arg_18], rdi; jumptable 0000000140B51AFB cases 1-3,5,8-24,26-36
0x1408b9976  mov     edi, r9d
0x1408b9979  test    r13, r13
0x1408b997c  jnz     short loc_1408B99CB
0x1408b997e  mov     [rsp+130h+var_F8], r9
0x1408b9983  lea     rax, [rsp+130h+Handle]
0x1408b9988  mov     qword ptr [rsp+130h+dwFlags], rax; dwFlags
0x1408b998d  mov     r8d, 10h
0x1408b9993  mov     byte ptr [rsp+130h+pcbRemaining], dil; pcbRemaining
0x1408b9998  mov     rdx, r11
0x1408b999b  mov     rcx, r10
0x1408b999e  mov     dword ptr [rsp+130h+ppszDestEnd], 2000001h; ppszDestEnd
0x1408b99a6  call    _CmOpenDeviceRegKey
0x1408b99ab  mov     edi, eax
0x1408b99ad  test    eax, eax
0x1408b99af  js      loc_1408B9AA1
0x1408b99b5  mov     edx, dword ptr [rsp+130h+cbDest]
0x1408b99b9  lea     r8, cs:140000000h
0x1408b99c0  mov     r10, [rbp+30h+var_B0]
0x1408b99c4  xor     r9d, r9d
0x1408b99c7  mov     r11, [rbp+30h+pszSrc]
0x1408b99cb  cmp     ebx, 1Dh
0x1408b99ce  jnz     loc_1408B9AE6
0x1408b99d4  movsxd  rax, r12d
0x1408b99d7  mov     ecx, ds:(jpt_1408B99E2 - 140000000h)[r8+rax*4]
0x1408b99df  add     rcx, r8
0x1408b99e2  jmp     rcx; switch jump
0x1408b99e8  lea     r8, aDevicedesc; jumptable 00000001408B99E2 case 1
0x1408b99ef  jmp     loc_1408B9BB1
0x1408b99f4  cmp     ebx, 19h
0x1408b99f7  jnz     loc_140B51ADE
0x1408b99fd  mov     eax, 0C0000230h; jumptable 00000001408B99E2 default case
0x1408b9a02  jmp     loc_1408B9ABA
0x1408b9a07  mov     r8, [rsp+130h+Handle]
0x1408b9a0c  lea     rax, [rsp+130h+cbDest+4]
0x1408b9a11  mov     dword ptr [rsp+130h+var_F8], r9d
0x1408b9a16  test    r13, r13
0x1408b9a19  mov     qword ptr [rsp+130h+dwFlags], rax
0x1408b9a1e  mov     rdx, r11
0x1408b9a21  lea     rax, [rbp+30h+var_90]
0x1408b9a25  mov     [rsp+130h+var_C8], r9d
0x1408b9a2a  mov     [rsp+130h+pcbRemaining], rax
0x1408b9a2f  cmovnz  r8, r13
0x1408b9a33  lea     rax, [rsp+130h+var_C8]
0x1408b9a38  mov     dword ptr [rsp+130h+cbDest+4], 4Eh ; 'N'
0x1408b9a40  mov     r9d, 9
0x1408b9a46  mov     [rsp+130h+ppszDestEnd], rax
0x1408b9a4b  mov     rcx, r10
0x1408b9a4e  call    _CmGetDeviceRegProp
0x1408b9a53  mov     edi, eax
0x1408b9a55  cmp     eax, 0C0000023h
0x1408b9a5a  jz      loc_1408B9E59
0x1408b9a60  test    eax, eax
0x1408b9a62  jnz     short loc_1408B9AA1
0x1408b9a64  mov     rcx, [rbp+30h+var_B0]
0x1408b9a68  lea     rdx, [rbp+30h+var_90]
0x1408b9a6c  mov     [rbp+30h+var_44], ax
0x1408b9a70  mov     r9d, 8
0x1408b9a76  mov     eax, dword ptr [rsp+130h+cbDest]
0x1408b9a7a  xor     r8d, r8d
0x1408b9a7d  mov     qword ptr [rsp+130h+dwFlags], rsi
0x1408b9a82  mov     [rsp+130h+pcbRemaining], r15
0x1408b9a87  mov     [rsi], eax
0x1408b9a89  mov     [rsp+130h+ppszDestEnd], r14
0x1408b9a8e  call    _CmGetInstallerClassRegProp
0x1408b9a93  mov     edi, eax
0x1408b9a95  cmp     eax, 0C0000034h
0x1408b9a9a  jnz     short loc_1408B9AA1
0x1408b9a9c  mov     edi, 0C0000225h
0x1408b9aa1  mov     rcx, [rsp+130h+Handle]; Handle
0x1408b9aa6  test    rcx, rcx
0x1408b9aa9  jz      short loc_1408B9AB0
0x1408b9aab  call    ZwClose
0x1408b9ab0  mov     eax, edi
0x1408b9ab2  mov     rdi, [rsp+130h+arg_18]
0x1408b9aba  mov     r12, [rsp+130h+var_28]
0x1408b9ac2  mov     r15, [rsp+130h+var_30]
0x1408b9aca  mov     rcx, [rbp+30h+var_40]
0x1408b9ace  xor     rcx, rsp; StackCookie
0x1408b9ad1  call    __security_check_cookie
0x1408b9ad6  add     rsp, 110h
0x1408b9add  pop     r14
0x1408b9adf  pop     r13
0x1408b9ae1  pop     rsi
0x1408b9ae2  pop     rbx
0x1408b9ae3  pop     rbp
0x1408b9ae4  retn
0x1408b9ae6  cmp     ebx, 8
0x1408b9ae9  jz      loc_1408B9A07
0x1408b9aef  cmp     ebx, 17h
0x1408b9af2  jz      loc_1408B9CAB
0x1408b9af8  cmp     ebx, 24h ; '$'
0x1408b9afb  jz      loc_1408B9DF1
0x1408b9b01  lea     eax, [rbx-0Fh]; switch 21 cases
0x1408b9b04  cmp     eax, 14h
0x1408b9b07  ja      def_1408B9B1A; jumptable 00000001408B9B1A default case, cases 16-19,23-30,34
0x1408b9b0d  cdqe
0x1408b9b0f  mov     ecx, ds:(jpt_1408B9B1A - 140000000h)[r8+rax*4]
0x1408b9b17  add     rcx, r8
0x1408b9b1a  jmp     rcx; switch jump
0x1408b9b20  mov     r12d, 1; jumptable 00000001408B9B1A case 15
0x1408b9b26  mov     rdx, r11; SourceString
0x1408b9b29  lea     rcx, [rbp+30h+DestinationString]; DestinationString
0x1408b9b2d  call    RtlInitUnicodeStringEx
0x1408b9b32  mov     edi, eax
0x1408b9b34  test    eax, eax
0x1408b9b36  js      loc_1408B9AA1
0x1408b9b3c  mov     rcx, [rbp+30h+var_B0]
0x1408b9b40  mov     rax, [rcx+100h]
0x1408b9b47  test    rax, rax
0x1408b9b4a  jz      loc_1408B9E86
0x1408b9b50  mov     edx, dword ptr [rsp+130h+cbDest]
0x1408b9b54  lea     r8, [rsp+130h+cbDest]
0x1408b9b59  mov     [rsp+130h+dwFlags], 0
0x1408b9b61  mov     r9, r15
0x1408b9b64  mov     [rsp+130h+pcbRemaining], r8
0x1408b9b69  mov     r8d, r12d
0x1408b9b6c  mov     dword ptr [rsp+130h+ppszDestEnd], edx
0x1408b9b70  lea     rdx, [rbp+30h+DestinationString]
0x1408b9b74  call    _guard_dispatch_icall_no_overrides
0x1408b9b79  mov     rdi, rax
0x1408b9b7c  cmp     eax, 80000005h
0x1408b9b81  jnz     loc_1408B9CE3
0x1408b9b87  mov     edi, 0C0000023h
0x1408b9b8c  mov     eax, dword ptr [rsp+130h+cbDest]
0x1408b9b90  mov     ecx, ebx
0x1408b9b92  mov     [rsi], eax
0x1408b9b94  call    _MapCmDevicePropertyToRegType
0x1408b9b99  mov     [r14], eax
0x1408b9b9c  jmp     loc_1408B9AA1
0x1408b9ba1  cmp     ebx, 2; jumptable 00000001408B9B1A default case, cases 16-19,23-30,34
0x1408b9ba4  jnz     loc_1408B9EA6
0x1408b9baa  lea     r8, aHardwareid; "HardwareID"
0x1408b9bb1  mov     rax, [r10+208h]
0x1408b9bb8  lea     rcx, _PnpRegQueryValueIndirect
0x1408b9bbf  mov     qword ptr [rsp+130h+dwFlags], r9
0x1408b9bc4  test    r13, r13
0x1408b9bc7  mov     dword ptr [rsp+130h+cbDest+4], edx
0x1408b9bcb  lea     r9, [rsp+130h+var_C8]
0x1408b9bd0  mov     rdx, [rsp+130h+Handle]
0x1408b9bd5  cmovnz  rdx, r13
0x1408b9bd9  test    rax, rax
0x1408b9bdc  cmovz   rax, rcx
0x1408b9be0  lea     rcx, [rsp+130h+cbDest+4]
0x1408b9be5  mov     [rsp+130h+pcbRemaining], rcx
0x1408b9bea  mov     rcx, r10
0x1408b9bed  mov     [rsp+130h+ppszDestEnd], r15
0x1408b9bf2  call    _guard_dispatch_icall_no_overrides
0x1408b9bf7  mov     edx, eax
0x1408b9bf9  cmp     eax, 0C0000034h
0x1408b9bfe  jz      loc_1408B9A9C
0x1408b9c04  cmp     eax, 0C000017Ch
0x1408b9c09  jz      loc_1408B9A9C
0x1408b9c0f  mov     eax, 80000000h
0x1408b9c14  lea     ecx, [rdx+rax]
0x1408b9c17  test    eax, ecx
0x1408b9c19  jz      short loc_1408B9C53
0x1408b9c1b  mov     eax, [rsp+130h+var_C8]
0x1408b9c1f  mov     ecx, dword ptr [rsp+130h+cbDest+4]
0x1408b9c23  cmp     eax, 1
0x1408b9c26  jz      short loc_1408B9C62
0x1408b9c28  cmp     eax, 7
0x1408b9c2b  jnz     short loc_1408B9C6C
0x1408b9c2d  cmp     ecx, 2
0x1408b9c30  jb      loc_1408B9A9C
0x1408b9c36  mov     [rsi], ecx
0x1408b9c38  mov     [r14], eax
0x1408b9c3b  test    edx, edx
0x1408b9c3d  jnz     short loc_1408B9C49
0x1408b9c3f  cmp     dword ptr [rsp+130h+cbDest], edx
0x1408b9c43  jnz     loc_1408B9AA1
0x1408b9c49  mov     edi, 0C0000023h
0x1408b9c4e  jmp     loc_1408B9AA1
0x1408b9c53  cmp     edx, 0C0000023h
0x1408b9c59  jz      short loc_1408B9C1B
0x1408b9c5b  mov     edi, edx
0x1408b9c5d  jmp     loc_1408B9AA1
0x1408b9c62  cmp     ecx, 2
0x1408b9c65  jnb     short loc_1408B9C36
0x1408b9c67  jmp     loc_1408B9A9C
0x1408b9c6c  cmp     ecx, 4
0x1408b9c6f  jz      short loc_1408B9C36
0x1408b9c71  cmp     eax, 4
0x1408b9c74  jnz     short loc_1408B9C36
0x1408b9c76  jmp     loc_1408B9A9C
0x1408b9c7b  lea     r8, aService; jumptable 00000001408B99E2 case 5
0x1408b9c82  jmp     loc_1408B9BB1
0x1408b9c87  lea     r8, aFriendlyname_0; jumptable 00000001408B99E2 case 13
0x1408b9c8e  jmp     loc_1408B9BB1
0x1408b9c93  lea     r8, aCompatibleids; jumptable 00000001408B99E2 case 3
0x1408b9c9a  jmp     loc_1408B9BB1
0x1408b9c9f  lea     r8, aUpperfilters; jumptable 00000001408B99E2 case 18
0x1408b9ca6  jmp     loc_1408B9BB1
0x1408b9cab  mov     edx, 5Ch ; '\'; Ch
0x1408b9cb0  mov     rcx, r11; Str
0x1408b9cb3  call    wcschr
0x1408b9cb8  test    rax, rax
0x1408b9cbb  jnz     loc_1408B9D41
0x1408b9cc1  mov     edi, 0C000000Dh
0x1408b9cc6  jmp     loc_1408B9AA1
0x1408b9ccb  lea     r8, aLowerfilters_0; jumptable 00000001408B99E2 case 19
0x1408b9cd2  jmp     loc_1408B9BB1
0x1408b9cd7  lea     r8, aMfg; jumptable 00000001408B99E2 case 12
0x1408b9cde  jmp     loc_1408B9BB1
0x1408b9ce3  cmp     eax, 0C0000034h
0x1408b9ce8  jz      loc_1408B9A9C
0x1408b9cee  test    eax, eax
0x1408b9cf0  jns     loc_1408B9B8C
0x1408b9cf6  cmp     eax, 0C0000023h
0x1408b9cfb  jz      loc_1408B9B8C
0x1408b9d01  jmp     loc_1408B9AA1
0x1408b9d06  lea     r8, aContainerid_0; jumptable 00000001408B99E2 case 37
0x1408b9d0d  jmp     loc_1408B9BB1
0x1408b9d12  mov     r12d, 4; jumptable 00000001408B9B1A case 22
0x1408b9d18  jmp     loc_1408B9B26
0x1408b9d1d  lea     r8, aUinumber; jumptable 00000001408B99E2 case 17
0x1408b9d24  jmp     loc_1408B9BB1
0x1408b9d29  lea     r8, aCapabilities_0; jumptable 00000001408B99E2 case 16
0x1408b9d30  jmp     loc_1408B9BB1
0x1408b9d35  lea     r8, aAddress; jumptable 00000001408B99E2 case 29
0x1408b9d3c  jmp     loc_1408B9BB1
0x1408b9d41  mov     r8, [rbp+30h+pszSrc]; pszSrc
0x1408b9d45  mov     ecx, dword ptr [rsp+130h+cbDest]
0x1408b9d49  sub     eax, r8d
0x1408b9d4c  add     eax, 2
0x1408b9d4f  mov     [rsi], eax
0x1408b9d51  mov     dword ptr [r14], 1
0x1408b9d58  mov     eax, [rsi]
0x1408b9d5a  cmp     ecx, eax
0x1408b9d5c  jb      short loc_1408B9D95
0x1408b9d5e  mov     edx, ecx; cbDest
0x1408b9d60  lea     r9, [rax-2]; cbToCopy
0x1408b9d64  mov     rcx, r15; pszDest
0x1408b9d67  call    RtlStringCbCopyNExW
0x1408b9d6c  mov     edi, eax
0x1408b9d6e  jmp     loc_1408B9AA1
0x1408b9d73  mov     r12d, 6; jumptable 00000001408B9B1A case 32
0x1408b9d79  jmp     loc_1408B9B26
0x1408b9d7e  mov     r12d, 3; jumptable 00000001408B9B1A case 21
0x1408b9d84  jmp     loc_1408B9B26
0x1408b9d89  lea     r8, aLocationinform; jumptable 00000001408B99E2 case 14
0x1408b9d90  jmp     loc_1408B9BB1
0x1408b9d95  mov     edi, 0C0000023h
0x1408b9d9a  jmp     loc_1408B9AA1
0x1408b9d9f  mov     r12d, 0Bh; jumptable 00000001408B9B1A case 35
0x1408b9da5  jmp     loc_1408B9B26
0x1408b9daa  mov     r12d, 0Ah; jumptable 00000001408B9B1A case 33
0x1408b9db0  jmp     loc_1408B9B26
  ... truncated ...
```
