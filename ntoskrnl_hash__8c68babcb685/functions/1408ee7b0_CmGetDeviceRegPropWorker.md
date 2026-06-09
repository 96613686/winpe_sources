# _CmGetDeviceRegPropWorker

- ea: `0x1408ee7b0`
- end: `0x1408eeed0`
- name: `_CmGetDeviceRegPropWorker`
- size: `1824`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1408ee610`

## callees

- `0x14042bfd0`
- `0x1404759dc`
- `0x14048a3c4`
- `0x140545fe0`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x1406eb0e0`
- `0x14086eac0`
- `0x1408ee610`
- `0x1408ee7b0`
- `0x1408eef70`
- `0x1408f3700`

## string_xrefs

- `0x1408eeb8b`: `Service`
- `0x1408eeba3`: `CompatibleIDs`
- `0x1408eecd1`: `Security`
- `0x1408eedd0`: `ConfigFlags`

## pseudocode

```c
__int64 __fastcall CmGetDeviceRegPropWorker(
        __int64 a1,
        const wchar_t *a2,
        void *a3,
        unsigned int a4,
        _DWORD *a5,
        NTSTRSAFE_PWSTR pszDest,
        ULONG *a7,
        __int16 a8)
{
  __int64 v8; // r10
  const wchar_t *v11; // r11
  ULONG v12; // edx
  wchar_t *v13; // r15
  int inited; // edi
  HANDLE v16; // r8
  int DeviceRegProp; // eax
  __int64 v18; // rcx
  int ObjectProperty; // eax
  int v20; // eax
  HANDLE v21; // rdx
  int v22; // eax
  int v23; // edx
  int v24; // eax
  wchar_t *v25; // rax
  const wchar_t *v26; // r8
  __int64 v27; // rax
  HANDLE v28; // r9
  NTSTRSAFE_PWSTR *ppszDestEnd; // [rsp+20h] [rbp-E0h]
  size_t *pcbRemaining; // [rsp+28h] [rbp-D8h]
  ULONG dwFlags; // [rsp+30h] [rbp-D0h]
  unsigned int cbDest; // [rsp+60h] [rbp-A0h]
  unsigned int cbDest_4; // [rsp+64h] [rbp-9Ch] BYREF
  int v34; // [rsp+68h] [rbp-98h] BYREF
  HANDLE Handle; // [rsp+70h] [rbp-90h] BYREF
  int v36; // [rsp+78h] [rbp-88h] BYREF
  __int64 v37; // [rsp+80h] [rbp-80h]
  STRSAFE_PCNZWCH pszSrc; // [rsp+88h] [rbp-78h]
  UNICODE_STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v40[76]; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v41; // [rsp+ECh] [rbp-14h]

  v8 = a1;
  v11 = a2;
  v37 = a1;
  pszSrc = a2;
  Handle = 0;
  v34 = 0;
  cbDest_4 = 0;
  v36 = 0;
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
    inited = CmOpenDeviceRegKey(a1, (__int64)v11, 16, 0, 33554433, 0, (__int64)&Handle, 0);
    if ( inited < 0 )
      goto LABEL_24;
    v12 = cbDest;
    v8 = v37;
    v11 = pszSrc;
  }
  if ( a4 == 29 )
  {
LABEL_14:
    switch ( a4 )
    {
      case 1u:
      case 3u:
      case 5u:
      case 8u:
      case 9u:
      case 0xCu:
      case 0xDu:
      case 0xEu:
      case 0x10u:
      case 0x11u:
      case 0x12u:
      case 0x13u:
      case 0x18u:
      case 0x1Au:
      case 0x1Bu:
      case 0x1Cu:
      case 0x1Du:
      case 0x1Eu:
      case 0x22u:
      case 0x25u:
        goto LABEL_37;
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
        goto LABEL_24;
      default:
        return 3221226032LL;
    }
  }
  if ( a4 != 8 )
  {
    if ( a4 == 23 )
    {
      v25 = wcschr(v11, 0x5Cu);
      if ( v25 )
      {
        v26 = pszSrc;
        *a7 = (_DWORD)v25 - (_DWORD)pszSrc + 2;
        *a5 = 1;
        v27 = *a7;
        if ( cbDest < (unsigned int)v27 )
          inited = -1073741789;
        else
          inited = RtlStringCbCopyNExW(v13, cbDest, v26, v27 - 2, ppszDestEnd, pcbRemaining, dwFlags);
      }
      else
      {
        inited = -1073741811;
      }
      goto LABEL_24;
    }
    if ( a4 != 36 )
    {
      switch ( a4 )
      {
        case 0xFu:
        case 0x14u:
        case 0x15u:
        case 0x16u:
        case 0x1Fu:
        case 0x20u:
        case 0x21u:
        case 0x23u:
          inited = RtlInitUnicodeStringEx(&DestinationString, v11);
          if ( inited < 0 )
            goto LABEL_24;
          if ( *(_QWORD *)(v37 + 256) )
          {
            v20 = guard_dispatch_icall_no_overrides(v37, &DestinationString);
            inited = v20;
            if ( v20 == -2147483643 )
            {
              inited = -1073741789;
LABEL_35:
              *a7 = cbDest;
              *a5 = MapCmDevicePropertyToRegType(a4);
              goto LABEL_24;
            }
            if ( v20 == -1073741772 )
              goto LABEL_23;
            if ( v20 >= 0 || v20 == -1073741789 )
              goto LABEL_35;
          }
          else
          {
            inited = -1073741822;
          }
          break;
        default:
          if ( a4 != 2 && a4 != 10 && a4 != 11 )
            goto LABEL_14;
LABEL_37:
          cbDest_4 = v12;
          v21 = Handle;
          if ( a3 )
            v21 = a3;
          v22 = guard_dispatch_icall_no_overrides(v8, v21);
          v23 = v22;
          if ( v22 == -1073741772 || v22 == -1073741444 )
            goto LABEL_23;
          if ( (int)(v22 + 0x80000000) < 0 || v22 == -1073741789 )
          {
            v24 = v34;
            if ( v34 == 1 )
            {
              if ( cbDest_4 < 2 )
                goto LABEL_23;
            }
            else if ( v34 == 7 )
            {
              if ( cbDest_4 < 2 )
                goto LABEL_23;
            }
            else if ( cbDest_4 != 4 && v34 == 4 )
            {
              goto LABEL_23;
            }
            *a7 = cbDest_4;
            *a5 = v24;
            if ( v23 || !cbDest )
              inited = -1073741789;
          }
          else
          {
            inited = v22;
          }
          goto LABEL_24;
      }
      goto LABEL_24;
    }
    v28 = Handle;
    if ( a3 )
      v28 = a3;
    ObjectProperty = PnpGetObjectProperty(
                       v8,
                       (__int64)v11,
                       1u,
                       v28,
                       0,
                       (__int64)&DEVPKEY_Device_LocationPaths,
                       &v36,
                       (__int64)v13,
                       v12,
                       (__int64)a7,
                       0);
    *a5 = 7;
    inited = ObjectProperty;
    if ( ObjectProperty >= 0 )
      goto LABEL_24;
LABEL_22:
    if ( ObjectProperty == -1073741772 )
LABEL_23:
      inited = -1073741275;
    goto LABEL_24;
  }
  v16 = Handle;
  v34 = 0;
  if ( a3 )
    v16 = a3;
  cbDest_4 = 78;
  DeviceRegProp = CmGetDeviceRegProp(
                    v8,
                    (__int64)v11,
                    (__int64)v16,
                    9u,
                    (__int64)&v34,
                    (__int64)v40,
                    (__int64)&cbDest_4,
                    0);
  inited = DeviceRegProp;
  if ( DeviceRegProp == -1073741789 )
  {
    inited = -1073741595;
    goto LABEL_24;
  }
  if ( !DeviceRegProp )
  {
    v18 = v37;
    v41 = 0;
    *a7 = cbDest;
    ObjectProperty = CmGetInstallerClassRegProp(v18, (__int64)v40, 0, 8, (__int64)a5, (__int64)v13, (__int64)a7);
    inited = ObjectProperty;
    goto LABEL_22;
  }
LABEL_24:
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1408ee7b0  push    rbp
0x1408ee7b2  push    rbx
0x1408ee7b3  push    rsi
0x1408ee7b4  push    r13
0x1408ee7b6  push    r14
0x1408ee7b8  lea     rbp, [rsp-10h]
0x1408ee7bd  sub     rsp, 110h
0x1408ee7c4  mov     rax, cs:__security_cookie
0x1408ee7cb  xor     rax, rsp
0x1408ee7ce  mov     [rbp+30h+var_40], rax
0x1408ee7d2  movzx   eax, [rbp+30h+arg_38]
0x1408ee7d6  xorps   xmm0, xmm0
0x1408ee7d9  mov     r14, [rbp+30h+arg_20]
0x1408ee7dd  mov     r10, rcx
0x1408ee7e0  mov     rsi, [rbp+30h+arg_30]
0x1408ee7e4  mov     r13, r8
0x1408ee7e7  movsxd  rbx, r9d
0x1408ee7ea  mov     r11, rdx
0x1408ee7ed  xor     r9d, r9d
0x1408ee7f0  mov     [rbp+30h+var_B0], rcx
0x1408ee7f4  mov     rcx, [rbp+30h+pszDest]
0x1408ee7f8  mov     [rbp+30h+pszSrc], rdx
0x1408ee7fc  mov     [rsp+130h+Handle], r9
0x1408ee801  mov     [rsp+130h+var_C8], r9d
0x1408ee806  mov     dword ptr [rsp+130h+cbDest+4], r9d
0x1408ee80b  mov     [rsp+130h+var_B8], r9d
0x1408ee810  movups  xmmword ptr [rbp+30h+DestinationString.Length], xmm0
0x1408ee814  test    eax, eax
0x1408ee816  jnz     loc_1408EEDAC
0x1408ee81c  test    rsi, rsi
0x1408ee81f  jz      loc_1408EEDAC
0x1408ee825  test    r14, r14
0x1408ee828  jz      loc_1408EEDAC
0x1408ee82e  mov     edx, [rsi]
0x1408ee830  test    edx, edx
0x1408ee832  jz      short loc_1408EE83D
0x1408ee834  test    rcx, rcx
0x1408ee837  jz      loc_1408EEDAC
0x1408ee83d  mov     [rsp+130h+var_28], r12
0x1408ee845  test    edx, edx
0x1408ee847  mov     [rsp+130h+var_30], r15
0x1408ee84f  lea     r12d, [rbx-1]; switch 37 cases
0x1408ee853  mov     r15, r9
0x1408ee856  mov     [rsi], r9d
0x1408ee859  cmovnz  r15, rcx
0x1408ee85d  mov     dword ptr [rsp+130h+cbDest], edx
0x1408ee861  mov     [r14], r9d
0x1408ee864  cmp     r12d, 24h ; '$'
0x1408ee868  ja      def_1408EE8F2; jumptable 00000001408EE8F2 default case
0x1408ee86e  lea     r8, cs:140000000h
0x1408ee875  cmp     ebx, 25h ; '%'
0x1408ee878  jnz     loc_1408EE904
0x1408ee87e  mov     [rsp+130h+arg_18], rdi; jumptable 0000000140B56475 cases 1-3,5,8-24,26-36
0x1408ee886  mov     edi, r9d
0x1408ee889  test    r13, r13
0x1408ee88c  jnz     short loc_1408EE8DB
0x1408ee88e  mov     [rsp+130h+var_F8], r9
0x1408ee893  lea     rax, [rsp+130h+Handle]
0x1408ee898  mov     qword ptr [rsp+130h+dwFlags], rax; dwFlags
0x1408ee89d  mov     r8d, 10h
0x1408ee8a3  mov     byte ptr [rsp+130h+pcbRemaining], dil; pcbRemaining
0x1408ee8a8  mov     rdx, r11
0x1408ee8ab  mov     rcx, r10
0x1408ee8ae  mov     dword ptr [rsp+130h+ppszDestEnd], 2000001h; ppszDestEnd
0x1408ee8b6  call    _CmOpenDeviceRegKey
0x1408ee8bb  mov     edi, eax
0x1408ee8bd  test    eax, eax
0x1408ee8bf  js      loc_1408EE9B1
0x1408ee8c5  mov     edx, dword ptr [rsp+130h+cbDest]
0x1408ee8c9  lea     r8, cs:140000000h
0x1408ee8d0  mov     r10, [rbp+30h+var_B0]
0x1408ee8d4  xor     r9d, r9d
0x1408ee8d7  mov     r11, [rbp+30h+pszSrc]
0x1408ee8db  cmp     ebx, 1Dh
0x1408ee8de  jnz     loc_1408EE9F6
0x1408ee8e4  movsxd  rax, r12d
0x1408ee8e7  mov     ecx, ds:(jpt_1408EE8F2 - 140000000h)[r8+rax*4]
0x1408ee8ef  add     rcx, r8
0x1408ee8f2  jmp     rcx; switch jump
0x1408ee8f8  lea     r8, aDevicedesc; jumptable 00000001408EE8F2 case 1
0x1408ee8ff  jmp     loc_1408EEAC1
0x1408ee904  cmp     ebx, 19h
0x1408ee907  jnz     loc_140B56458
0x1408ee90d  mov     eax, 0C0000230h; jumptable 00000001408EE8F2 default case
0x1408ee912  jmp     loc_1408EE9CA
0x1408ee917  mov     r8, [rsp+130h+Handle]
0x1408ee91c  lea     rax, [rsp+130h+cbDest+4]
0x1408ee921  mov     dword ptr [rsp+130h+var_F8], r9d
0x1408ee926  test    r13, r13
0x1408ee929  mov     qword ptr [rsp+130h+dwFlags], rax
0x1408ee92e  mov     rdx, r11
0x1408ee931  lea     rax, [rbp+30h+var_90]
0x1408ee935  mov     [rsp+130h+var_C8], r9d
0x1408ee93a  mov     [rsp+130h+pcbRemaining], rax
0x1408ee93f  cmovnz  r8, r13
0x1408ee943  lea     rax, [rsp+130h+var_C8]
0x1408ee948  mov     dword ptr [rsp+130h+cbDest+4], 4Eh ; 'N'
0x1408ee950  mov     r9d, 9
0x1408ee956  mov     [rsp+130h+ppszDestEnd], rax
0x1408ee95b  mov     rcx, r10
0x1408ee95e  call    _CmGetDeviceRegProp
0x1408ee963  mov     edi, eax
0x1408ee965  cmp     eax, 0C0000023h
0x1408ee96a  jz      loc_1408EED69
0x1408ee970  test    eax, eax
0x1408ee972  jnz     short loc_1408EE9B1
0x1408ee974  mov     rcx, [rbp+30h+var_B0]
0x1408ee978  lea     rdx, [rbp+30h+var_90]
0x1408ee97c  mov     [rbp+30h+var_44], ax
0x1408ee980  mov     r9d, 8
0x1408ee986  mov     eax, dword ptr [rsp+130h+cbDest]
0x1408ee98a  xor     r8d, r8d
0x1408ee98d  mov     qword ptr [rsp+130h+dwFlags], rsi
0x1408ee992  mov     [rsp+130h+pcbRemaining], r15
0x1408ee997  mov     [rsi], eax
0x1408ee999  mov     [rsp+130h+ppszDestEnd], r14
0x1408ee99e  call    _CmGetInstallerClassRegProp
0x1408ee9a3  mov     edi, eax
0x1408ee9a5  cmp     eax, 0C0000034h
0x1408ee9aa  jnz     short loc_1408EE9B1
0x1408ee9ac  mov     edi, 0C0000225h
0x1408ee9b1  mov     rcx, [rsp+130h+Handle]; Handle
0x1408ee9b6  test    rcx, rcx
0x1408ee9b9  jz      short loc_1408EE9C0
0x1408ee9bb  call    ZwClose
0x1408ee9c0  mov     eax, edi
0x1408ee9c2  mov     rdi, [rsp+130h+arg_18]
0x1408ee9ca  mov     r12, [rsp+130h+var_28]
0x1408ee9d2  mov     r15, [rsp+130h+var_30]
0x1408ee9da  mov     rcx, [rbp+30h+var_40]
0x1408ee9de  xor     rcx, rsp; StackCookie
0x1408ee9e1  call    __security_check_cookie
0x1408ee9e6  add     rsp, 110h
0x1408ee9ed  pop     r14
0x1408ee9ef  pop     r13
0x1408ee9f1  pop     rsi
0x1408ee9f2  pop     rbx
0x1408ee9f3  pop     rbp
0x1408ee9f4  retn
0x1408ee9f6  cmp     ebx, 8
0x1408ee9f9  jz      loc_1408EE917
0x1408ee9ff  cmp     ebx, 17h
0x1408eea02  jz      loc_1408EEBBB
0x1408eea08  cmp     ebx, 24h ; '$'
0x1408eea0b  jz      loc_1408EED01
0x1408eea11  lea     eax, [rbx-0Fh]; switch 21 cases
0x1408eea14  cmp     eax, 14h
0x1408eea17  ja      def_1408EEA2A; jumptable 00000001408EEA2A default case, cases 16-19,23-30,34
0x1408eea1d  cdqe
0x1408eea1f  mov     ecx, ds:(jpt_1408EEA2A - 140000000h)[r8+rax*4]
0x1408eea27  add     rcx, r8
0x1408eea2a  jmp     rcx; switch jump
0x1408eea30  mov     r12d, 1; jumptable 00000001408EEA2A case 15
0x1408eea36  mov     rdx, r11; SourceString
0x1408eea39  lea     rcx, [rbp+30h+DestinationString]; DestinationString
0x1408eea3d  call    RtlInitUnicodeStringEx
0x1408eea42  mov     edi, eax
0x1408eea44  test    eax, eax
0x1408eea46  js      loc_1408EE9B1
0x1408eea4c  mov     rcx, [rbp+30h+var_B0]
0x1408eea50  mov     rax, [rcx+100h]
0x1408eea57  test    rax, rax
0x1408eea5a  jz      loc_1408EED96
0x1408eea60  mov     edx, dword ptr [rsp+130h+cbDest]
0x1408eea64  lea     r8, [rsp+130h+cbDest]
0x1408eea69  mov     [rsp+130h+dwFlags], 0
0x1408eea71  mov     r9, r15
0x1408eea74  mov     [rsp+130h+pcbRemaining], r8
0x1408eea79  mov     r8d, r12d
0x1408eea7c  mov     dword ptr [rsp+130h+ppszDestEnd], edx
0x1408eea80  lea     rdx, [rbp+30h+DestinationString]
0x1408eea84  call    _guard_dispatch_icall_no_overrides
0x1408eea89  mov     rdi, rax
0x1408eea8c  cmp     eax, 80000005h
0x1408eea91  jnz     loc_1408EEBF3
0x1408eea97  mov     edi, 0C0000023h
0x1408eea9c  mov     eax, dword ptr [rsp+130h+cbDest]
0x1408eeaa0  mov     ecx, ebx
0x1408eeaa2  mov     [rsi], eax
0x1408eeaa4  call    _MapCmDevicePropertyToRegType
0x1408eeaa9  mov     [r14], eax
0x1408eeaac  jmp     loc_1408EE9B1
0x1408eeab1  cmp     ebx, 2; jumptable 00000001408EEA2A default case, cases 16-19,23-30,34
0x1408eeab4  jnz     loc_1408EEDB6
0x1408eeaba  lea     r8, aHardwareid; "HardwareID"
0x1408eeac1  mov     rax, [r10+208h]
0x1408eeac8  lea     rcx, _PnpRegQueryValueIndirect
0x1408eeacf  mov     qword ptr [rsp+130h+dwFlags], r9
0x1408eead4  test    r13, r13
0x1408eead7  mov     dword ptr [rsp+130h+cbDest+4], edx
0x1408eeadb  lea     r9, [rsp+130h+var_C8]
0x1408eeae0  mov     rdx, [rsp+130h+Handle]
0x1408eeae5  cmovnz  rdx, r13
0x1408eeae9  test    rax, rax
0x1408eeaec  cmovz   rax, rcx
0x1408eeaf0  lea     rcx, [rsp+130h+cbDest+4]
0x1408eeaf5  mov     [rsp+130h+pcbRemaining], rcx
0x1408eeafa  mov     rcx, r10
0x1408eeafd  mov     [rsp+130h+ppszDestEnd], r15
0x1408eeb02  call    _guard_dispatch_icall_no_overrides
0x1408eeb07  mov     edx, eax
0x1408eeb09  cmp     eax, 0C0000034h
0x1408eeb0e  jz      loc_1408EE9AC
0x1408eeb14  cmp     eax, 0C000017Ch
0x1408eeb19  jz      loc_1408EE9AC
0x1408eeb1f  mov     eax, 80000000h
0x1408eeb24  lea     ecx, [rdx+rax]
0x1408eeb27  test    eax, ecx
0x1408eeb29  jz      short loc_1408EEB63
0x1408eeb2b  mov     eax, [rsp+130h+var_C8]
0x1408eeb2f  mov     ecx, dword ptr [rsp+130h+cbDest+4]
0x1408eeb33  cmp     eax, 1
0x1408eeb36  jz      short loc_1408EEB72
0x1408eeb38  cmp     eax, 7
0x1408eeb3b  jnz     short loc_1408EEB7C
0x1408eeb3d  cmp     ecx, 2
0x1408eeb40  jb      loc_1408EE9AC
0x1408eeb46  mov     [rsi], ecx
0x1408eeb48  mov     [r14], eax
0x1408eeb4b  test    edx, edx
0x1408eeb4d  jnz     short loc_1408EEB59
0x1408eeb4f  cmp     dword ptr [rsp+130h+cbDest], edx
0x1408eeb53  jnz     loc_1408EE9B1
0x1408eeb59  mov     edi, 0C0000023h
0x1408eeb5e  jmp     loc_1408EE9B1
0x1408eeb63  cmp     edx, 0C0000023h
0x1408eeb69  jz      short loc_1408EEB2B
0x1408eeb6b  mov     edi, edx
0x1408eeb6d  jmp     loc_1408EE9B1
0x1408eeb72  cmp     ecx, 2
0x1408eeb75  jnb     short loc_1408EEB46
0x1408eeb77  jmp     loc_1408EE9AC
0x1408eeb7c  cmp     ecx, 4
0x1408eeb7f  jz      short loc_1408EEB46
0x1408eeb81  cmp     eax, 4
0x1408eeb84  jnz     short loc_1408EEB46
0x1408eeb86  jmp     loc_1408EE9AC
0x1408eeb8b  lea     r8, aService; jumptable 00000001408EE8F2 case 5
0x1408eeb92  jmp     loc_1408EEAC1
0x1408eeb97  lea     r8, aFriendlyname_0; jumptable 00000001408EE8F2 case 13
0x1408eeb9e  jmp     loc_1408EEAC1
0x1408eeba3  lea     r8, aCompatibleids; jumptable 00000001408EE8F2 case 3
0x1408eebaa  jmp     loc_1408EEAC1
0x1408eebaf  lea     r8, aUpperfilters; jumptable 00000001408EE8F2 case 18
0x1408eebb6  jmp     loc_1408EEAC1
0x1408eebbb  mov     edx, 5Ch ; '\'; Ch
0x1408eebc0  mov     rcx, r11; Str
0x1408eebc3  call    wcschr
0x1408eebc8  test    rax, rax
0x1408eebcb  jnz     loc_1408EEC51
0x1408eebd1  mov     edi, 0C000000Dh
0x1408eebd6  jmp     loc_1408EE9B1
0x1408eebdb  lea     r8, aLowerfilters_0; jumptable 00000001408EE8F2 case 19
0x1408eebe2  jmp     loc_1408EEAC1
0x1408eebe7  lea     r8, aMfg; jumptable 00000001408EE8F2 case 12
0x1408eebee  jmp     loc_1408EEAC1
0x1408eebf3  cmp     eax, 0C0000034h
0x1408eebf8  jz      loc_1408EE9AC
0x1408eebfe  test    eax, eax
0x1408eec00  jns     loc_1408EEA9C
0x1408eec06  cmp     eax, 0C0000023h
0x1408eec0b  jz      loc_1408EEA9C
0x1408eec11  jmp     loc_1408EE9B1
0x1408eec16  lea     r8, aContainerid_0; jumptable 00000001408EE8F2 case 37
0x1408eec1d  jmp     loc_1408EEAC1
0x1408eec22  mov     r12d, 4; jumptable 00000001408EEA2A case 22
0x1408eec28  jmp     loc_1408EEA36
0x1408eec2d  lea     r8, aUinumber; jumptable 00000001408EE8F2 case 17
0x1408eec34  jmp     loc_1408EEAC1
0x1408eec39  lea     r8, aCapabilities_0; jumptable 00000001408EE8F2 case 16
0x1408eec40  jmp     loc_1408EEAC1
0x1408eec45  lea     r8, aAddress; jumptable 00000001408EE8F2 case 29
0x1408eec4c  jmp     loc_1408EEAC1
0x1408eec51  mov     r8, [rbp+30h+pszSrc]; pszSrc
0x1408eec55  mov     ecx, dword ptr [rsp+130h+cbDest]
0x1408eec59  sub     eax, r8d
0x1408eec5c  add     eax, 2
0x1408eec5f  mov     [rsi], eax
0x1408eec61  mov     dword ptr [r14], 1
0x1408eec68  mov     eax, [rsi]
0x1408eec6a  cmp     ecx, eax
0x1408eec6c  jb      short loc_1408EECA5
0x1408eec6e  mov     edx, ecx; cbDest
0x1408eec70  lea     r9, [rax-2]; cbToCopy
0x1408eec74  mov     rcx, r15; pszDest
0x1408eec77  call    RtlStringCbCopyNExW
0x1408eec7c  mov     edi, eax
0x1408eec7e  jmp     loc_1408EE9B1
0x1408eec83  mov     r12d, 6; jumptable 00000001408EEA2A case 32
0x1408eec89  jmp     loc_1408EEA36
0x1408eec8e  mov     r12d, 3; jumptable 00000001408EEA2A case 21
0x1408eec94  jmp     loc_1408EEA36
0x1408eec99  lea     r8, aLocationinform; jumptable 00000001408EE8F2 case 14
0x1408eeca0  jmp     loc_1408EEAC1
0x1408eeca5  mov     edi, 0C0000023h
0x1408eecaa  jmp     loc_1408EE9B1
0x1408eecaf  mov     r12d, 0Bh; jumptable 00000001408EEA2A case 35
0x1408eecb5  jmp     loc_1408EEA36
0x1408eecba  mov     r12d, 0Ah; jumptable 00000001408EEA2A case 33
0x1408eecc0  jmp     loc_1408EEA36
  ... truncated ...
```
