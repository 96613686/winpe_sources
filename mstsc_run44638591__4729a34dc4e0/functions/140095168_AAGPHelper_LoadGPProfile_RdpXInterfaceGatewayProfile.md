# AAGPHelper::LoadGPProfile(RdpXInterfaceGatewayProfile * *)

- ea: `0x140095168`
- end: `0x140095696`
- name: `?LoadGPProfile@AAGPHelper@@SAJPEAPEAURdpXInterfaceGatewayProfile@@@Z`
- size: `1326`
- prototype: `__int64 __fastcall(struct RdpXInterfaceGatewayProfile **)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140094978`
- `0x140095810`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x140042d04`
- `0x140063d40`
- `0x140064258`
- `0x140094ab8`
- `0x140094cd4`
- `0x140094f44`
- `0x140095168`
- `0x14009569c`
- `0x140113390`
- `0x140114010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1400952dc`
- `ADVAPI32!RegOpenKeyExW` at `0x1400952dc`
- `ADVAPI32!RegCloseKey` at `0x140095661`
- `ADVAPI32!RegCloseKey` at `0x140095661`
- `ADVAPI32!RegQueryValueExW` at `0x140095583`
- `ADVAPI32!RegQueryValueExW` at `0x140095583`

## string_xrefs

- `0x1400952ce`: `Software\Policies\Microsoft\Windows NT\Terminal Services`

## pseudocode

```c
__int64 __fastcall AAGPHelper::LoadGPProfile(struct RdpXInterfaceGatewayProfile **a1, __int64 a2)
{
  PVOID *v3; // rcx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int DefaultProxyHostName; // edi
  int Object; // ebx
  unsigned int v7; // eax
  struct RdpXInterfaceGatewayProfile *v8; // rbx
  LSTATUS v9; // edi
  unsigned int v10; // eax
  int DefaultProxyUsage; // esi
  int v12; // eax
  unsigned int v13; // r8d
  _QWORD *v14; // rcx
  int v15; // edx
  const wchar_t *v16; // r9
  BOOL v17; // esi
  int v18; // r8d
  LSTATUS v19; // r15d
  unsigned int v20; // eax
  int v22; // [rsp+30h] [rbp-D0h] BYREF
  int v23; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v24; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData; // [rsp+4Ch] [rbp-B4h] BYREF
  struct RdpXInterfaceGatewayProfile *v28; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[528]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  v28 = 0;
  *(_WORD *)Data = 0;
  v23 = 0;
  v22 = 0;
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      &WPP_4be363d4c2c33cc86d8cd0b2db161955_Traceguids,
      CurrentThreadActivityIdPrefix);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 8) != 0 && *((_BYTE *)v3 + 25) >= 2u )
      WPP_SF_S(v3[2], 22, &WPP_4be363d4c2c33cc86d8cd0b2db161955_Traceguids, L"ppProfile");
    DefaultProxyHostName = -2147024809;
    goto LABEL_71;
  }
  *a1 = 0;
  Object = RdpX_CreateObject(v3, a2, 88);
  if ( Object )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_4be363d4c2c33cc86d8cd0b2db161955_Traceguids, v7, Object);
    }
    DefaultProxyHostName = -2147467259;
    goto LABEL_71;
  }
  (**(void (__fastcall ***)(struct RdpXInterfaceGatewayProfile *))v28)(v28);
  v8 = v28;
  v9 = RegOpenKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
         0,
         0x20019u,
         &hKey);
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_4be363d4c2c33cc86d8cd0b2db161955_Traceguids, v10, v9);
    }
LABEL_22:
    DefaultProxyHostName = 1;
    goto LABEL_68;
  }
  v24 = 0;
  DefaultProxyUsage = InternalGetDefaultProxyUsage(hKey, (enum _XRdpGatewayProxyUsage *)&v24, &v23, &v22);
  v12 = (*(__int64 (__fastcall **)(struct RdpXInterfaceGatewayProfile *, _QWORD))(*(_QWORD *)v8 + 104LL))(v8, v24);
  DefaultProxyHostName = v12;
  if ( v12 >= 0 )
  {
    if ( v22 )
    {
      (*(void (__fastcall **)(struct RdpXInterfaceGatewayProfile *, __int64))(*(_QWORD *)v8 + 216LL))(v8, 1);
      if ( v23 )
        (*(void (__fastcall **)(struct RdpXInterfaceGatewayProfile *, __int64))(*(_QWORD *)v8 + 208LL))(v8, 1);
    }
    DefaultProxyHostName = InternalGetDefaultProxyHostName(hKey, Data, v13, &v23, &v22);
    v17 = DefaultProxyHostName >= 0 || DefaultProxyUsage >= 0;
    if ( v22 )
    {
      (*(void (__fastcall **)(struct RdpXInterfaceGatewayProfile *, BYTE *))(*(_QWORD *)v8 + 64LL))(v8, Data);
      if ( DefaultProxyHostName < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            26,
            v18,
            (unsigned int)L"SetProxyHostNameAndPort",
            DefaultProxyHostName);
        }
        goto LABEL_68;
      }
      (*(void (__fastcall **)(struct RdpXInterfaceGatewayProfile *, __int64))(*(_QWORD *)v8 + 216LL))(v8, 2);
      if ( v23 )
        (*(void (__fastcall **)(struct RdpXInterfaceGatewayProfile *, __int64))(*(_QWORD *)v8 + 208LL))(v8, 2);
    }
    v24 = 0;
    if ( (int)InternalGetDefaultAuthMode(hKey, (enum _XRdpGatewayAuthSchemes *)&v24, &v23, &v22) >= 0 )
      v17 = 1;
    v12 = (*(__int64 (__fastcall **)(struct RdpXInterfaceGatewayProfile *, _QWORD))(*(_QWORD *)v8 + 72LL))(v8, v24);
    DefaultProxyHostName = v12;
    if ( v12 >= 0 )
    {
      if ( v22 )
      {
        (*(void (__fastcall **)(struct RdpXInterfaceGatewayProfile *, __int64))(*(_QWORD *)v8 + 216LL))(v8, 4);
        if ( v23 )
          (*(void (__fastcall **)(struct RdpXInterfaceGatewayProfile *, __int64))(*(_QWORD *)v8 + 208LL))(v8, 4);
      }
      cbData = 520;
      Type = 0;
      v19 = RegQueryValueExW(hKey, L"AlternateSPN", 0, &Type, Data, &cbData);
      if ( !v19 && Type == 1 && cbData )
      {
        v12 = (*(__int64 (__fastcall **)(struct RdpXInterfaceGatewayProfile *, BYTE *))(*(_QWORD *)v8 + 184LL))(
                v8,
                Data);
        DefaultProxyHostName = v12;
        if ( v12 < 0 )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v15 = v19 + 28;
            v16 = L"SetAlternateSPN";
            goto LABEL_28;
          }
          goto LABEL_68;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v20 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_4be363d4c2c33cc86d8cd0b2db161955_Traceguids, v20, v19);
        }
        if ( !v17 )
          goto LABEL_22;
      }
      if ( !DefaultProxyHostName )
      {
        *a1 = v8;
        goto LABEL_71;
      }
      goto LABEL_68;
    }
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 27;
      v16 = L"InternalSetAuthScheme";
      goto LABEL_28;
    }
  }
  else
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 25;
      v16 = L"SetProxyUsage";
LABEL_28:
      WPP_SF_Sd(v14[2], v15, v13, (_DWORD)v16, v12);
    }
  }
LABEL_68:
  if ( v8 )
    (*(void (__fastcall **)(struct RdpXInterfaceGatewayProfile *))(*(_QWORD *)v8 + 8LL))(v8);
LABEL_71:
  if ( hKey )
    RegCloseKey(hKey);
  RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(&v28);
  return (unsigned int)DefaultProxyHostName;
}

```

## disassembly

```asm
0x140095168  push    rbp
0x14009516a  push    rbx
0x14009516b  push    rsi
0x14009516c  push    rdi
0x14009516d  push    r12
0x14009516f  push    r13
0x140095171  push    r14
0x140095173  push    r15
0x140095175  lea     rbp, [rsp-188h]
0x14009517d  sub     rsp, 288h
0x140095184  mov     rax, cs:__security_cookie
0x14009518b  xor     rax, rsp
0x14009518e  mov     [rbp+1C0h+var_50], rax
0x140095195  xor     r12d, r12d
0x140095198  mov     r14, rcx
0x14009519b  mov     [rsp+2C0h+hKey], r12
0x1400951a0  mov     [rsp+2C0h+var_270], r12
0x1400951a5  mov     word ptr [rsp+2C0h+Data], r12w
0x1400951ab  mov     [rsp+2C0h+var_28C], r12d
0x1400951b0  mov     [rsp+2C0h+var_290], r12d
0x1400951b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400951bc  lea     r15, WPP_GLOBAL_Control
0x1400951c3  lea     rsi, WPP_4be363d4c2c33cc86d8cd0b2db161955_Traceguids
0x1400951ca  lea     r13d, [r12+1]
0x1400951cf  cmp     rcx, r15
0x1400951d2  jz      short loc_140095207
0x1400951d4  test    [rcx+1Ch], r13b
0x1400951d8  jz      short loc_140095207
0x1400951da  cmp     byte ptr [rcx+19h], 5
0x1400951de  jb      short loc_140095207
0x1400951e0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400951e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400951ec  lea     edx, [r12+15h]
0x1400951f1  mov     r9d, eax
0x1400951f4  mov     r8, rsi
0x1400951f7  mov     rcx, [rcx+10h]
0x1400951fb  call    WPP_SF_d
0x140095200  mov     rcx, cs:WPP_GLOBAL_Control
0x140095207  test    r14, r14
0x14009520a  jnz     short loc_14009523E
0x14009520c  cmp     rcx, r15
0x14009520f  jz      short loc_140095234
0x140095211  test    byte ptr [rcx+1Ch], 8
0x140095215  jz      short loc_140095234
0x140095217  cmp     byte ptr [rcx+19h], 2
0x14009521b  jb      short loc_140095234
0x14009521d  mov     rcx, [rcx+10h]
0x140095221  lea     edx, [r14+16h]
0x140095225  lea     r9, aPpprofile; "ppProfile"
0x14009522c  mov     r8, rsi
0x14009522f  call    WPP_SF_S
0x140095234  mov     edi, 80070057h
0x140095239  jmp     loc_140095657
0x14009523e  mov     r9d, 7Dh ; '}'
0x140095244  mov     [r14], r12
0x140095247  lea     rax, [rsp+2C0h+var_270]
0x14009524c  mov     [rsp+2C0h+phkResult], rax
0x140095251  lea     r8d, [r9-25h]
0x140095255  call    ?RdpX_CreateObject@@YA?AW4_XResult32@@PEAURdpXInterface@@IW4_XObjectId32@@W4_XInterfaceId32@@PEAPEAX@Z; RdpX_CreateObject(RdpXInterface *,uint,_XObjectId32,_XInterfaceId32,void * *)
0x14009525a  mov     ebx, eax
0x14009525c  test    eax, eax
0x14009525e  jz      short loc_1400952A6
0x140095260  mov     rcx, cs:WPP_GLOBAL_Control
0x140095267  cmp     rcx, r15
0x14009526a  jz      short loc_14009529C
0x14009526c  test    [rcx+1Ch], r13b
0x140095270  jz      short loc_14009529C
0x140095272  cmp     byte ptr [rcx+19h], 2
0x140095276  jb      short loc_14009529C
0x140095278  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14009527d  mov     rcx, cs:WPP_GLOBAL_Control
0x140095284  mov     edx, 17h
0x140095289  mov     r9d, eax
0x14009528c  mov     dword ptr [rsp+2C0h+phkResult], ebx
0x140095290  mov     r8, rsi
0x140095293  mov     rcx, [rcx+10h]
0x140095297  call    WPP_SF_Dd
0x14009529c  mov     edi, 80004005h
0x1400952a1  jmp     loc_140095657
0x1400952a6  mov     rcx, [rsp+2C0h+var_270]
0x1400952ab  mov     rax, [rcx]
0x1400952ae  mov     rax, [rax]
0x1400952b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400952b6  mov     rbx, [rsp+2C0h+var_270]
0x1400952bb  lea     rax, [rsp+2C0h+hKey]
0x1400952c0  mov     r9d, 20019h; samDesired
0x1400952c6  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1400952cb  xor     r8d, r8d; ulOptions
0x1400952ce  lea     rdx, aSoftwarePolici_1; "Software\\Policies\\Microsoft\\Windows "...
0x1400952d5  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400952dc  call    cs:__imp_RegOpenKeyExW
0x1400952e2  mov     edi, eax
0x1400952e4  test    eax, eax
0x1400952e6  jz      short loc_14009532C
0x1400952e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400952ef  cmp     rcx, r15
0x1400952f2  jz      short loc_140095324
0x1400952f4  test    [rcx+1Ch], r13b
0x1400952f8  jz      short loc_140095324
0x1400952fa  cmp     byte ptr [rcx+19h], 3
0x1400952fe  jb      short loc_140095324
0x140095300  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140095305  mov     rcx, cs:WPP_GLOBAL_Control
0x14009530c  mov     edx, 18h
0x140095311  mov     r9d, eax
0x140095314  mov     dword ptr [rsp+2C0h+phkResult], edi
0x140095318  mov     r8, rsi
0x14009531b  mov     rcx, [rcx+10h]
0x14009531f  call    WPP_SF_Dd
0x140095324  mov     edi, r13d
0x140095327  jmp     loc_14009563E
0x14009532c  mov     rcx, [rsp+2C0h+hKey]; hKey
0x140095331  lea     r9, [rsp+2C0h+var_290]; int *
0x140095336  lea     r8, [rsp+2C0h+var_28C]; int *
0x14009533b  mov     [rsp+2C0h+var_288], r12d
0x140095340  lea     rdx, [rsp+2C0h+var_288]; enum _XRdpGatewayProxyUsage *
0x140095345  call    ?InternalGetDefaultProxyUsage@@YAJPEAUHKEY__@@PEAW4_XRdpGatewayProxyUsage@@PEAH2@Z; InternalGetDefaultProxyUsage(HKEY__ *,_XRdpGatewayProxyUsage *,int *,int *)
0x14009534a  mov     rcx, [rbx]
0x14009534d  mov     esi, eax
0x14009534f  mov     edx, [rsp+2C0h+var_288]
0x140095353  mov     rax, [rcx+68h]
0x140095357  mov     rcx, rbx
0x14009535a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009535f  mov     edi, eax
0x140095361  test    eax, eax
0x140095363  jns     short loc_1400953A7
0x140095365  mov     rcx, cs:WPP_GLOBAL_Control
0x14009536c  cmp     rcx, r15
0x14009536f  jz      loc_14009563E
0x140095375  test    byte ptr [rcx+1Ch], 8
0x140095379  jz      loc_14009563E
0x14009537f  cmp     byte ptr [rcx+19h], 2
0x140095383  jb      loc_14009563E
0x140095389  mov     edx, 19h
0x14009538e  lea     r9, aSetproxyusage; "SetProxyUsage"
0x140095395  mov     dword ptr [rsp+2C0h+phkResult], eax
0x140095399  mov     rcx, [rcx+10h]
0x14009539d  call    WPP_SF_Sd
0x1400953a2  jmp     loc_14009563E
0x1400953a7  cmp     [rsp+2C0h+var_290], r12d
0x1400953ac  jz      short loc_1400953DF
0x1400953ae  mov     rax, [rbx]
0x1400953b1  mov     edx, r13d
0x1400953b4  mov     rcx, rbx
0x1400953b7  mov     rax, [rax+0D8h]
0x1400953be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400953c3  cmp     [rsp+2C0h+var_28C], r12d
0x1400953c8  jz      short loc_1400953DF
0x1400953ca  mov     rax, [rbx]
0x1400953cd  mov     edx, r13d
0x1400953d0  mov     rcx, rbx
0x1400953d3  mov     rax, [rax+0D0h]
0x1400953da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400953df  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1400953e4  lea     rax, [rsp+2C0h+var_290]
0x1400953e9  lea     r9, [rsp+2C0h+var_28C]; int *
0x1400953ee  mov     [rsp+2C0h+phkResult], rax; int *
0x1400953f3  lea     rdx, [rsp+2C0h+Data]; lpData
0x1400953f8  call    ?InternalGetDefaultProxyHostName@@YAJPEAUHKEY__@@PEAGKPEAH2@Z; InternalGetDefaultProxyHostName(HKEY__ *,ushort *,ulong,int *,int *)
0x1400953fd  mov     edi, eax
0x1400953ff  test    eax, eax
0x140095401  js      short loc_140095408
0x140095403  mov     esi, r13d
0x140095406  jmp     short loc_14009540D
0x140095408  not     esi
0x14009540a  shr     esi, 1Fh
0x14009540d  cmp     [rsp+2C0h+var_290], r12d
0x140095412  jz      loc_14009549E
0x140095418  mov     rax, [rbx]
0x14009541b  lea     rdx, [rsp+2C0h+Data]
0x140095420  mov     rcx, rbx
0x140095423  mov     rax, [rax+40h]
0x140095427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009542c  test    edi, edi
0x14009542e  jns     short loc_140095469
0x140095430  mov     rcx, cs:WPP_GLOBAL_Control
0x140095437  cmp     rcx, r15
0x14009543a  jz      loc_14009563E
0x140095440  test    byte ptr [rcx+1Ch], 8
0x140095444  jz      loc_14009563E
0x14009544a  cmp     byte ptr [rcx+19h], 2
0x14009544e  jb      loc_14009563E
0x140095454  mov     edx, 1Ah
0x140095459  mov     dword ptr [rsp+2C0h+phkResult], edi
0x14009545d  lea     r9, aSetproxyhostna; "SetProxyHostNameAndPort"
0x140095464  jmp     loc_140095399
0x140095469  mov     rax, [rbx]
0x14009546c  mov     edx, 2
0x140095471  mov     rcx, rbx
0x140095474  mov     rax, [rax+0D8h]
0x14009547b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140095480  cmp     [rsp+2C0h+var_28C], r12d
0x140095485  jz      short loc_14009549E
0x140095487  mov     rax, [rbx]
0x14009548a  mov     edx, 2
0x14009548f  mov     rcx, rbx
0x140095492  mov     rax, [rax+0D0h]
0x140095499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009549e  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1400954a3  lea     r9, [rsp+2C0h+var_290]; int *
0x1400954a8  lea     r8, [rsp+2C0h+var_28C]; int *
0x1400954ad  mov     [rsp+2C0h+var_288], r12d
0x1400954b2  lea     rdx, [rsp+2C0h+var_288]; enum _XRdpGatewayAuthSchemes *
0x1400954b7  call    ?InternalGetDefaultAuthMode@@YAJPEAUHKEY__@@PEAW4_XRdpGatewayAuthSchemes@@PEAH2@Z; InternalGetDefaultAuthMode(HKEY__ *,_XRdpGatewayAuthSchemes *,int *,int *)
0x1400954bc  mov     edx, [rsp+2C0h+var_288]
0x1400954c0  test    eax, eax
0x1400954c2  mov     rax, [rbx]
0x1400954c5  mov     rcx, rbx
0x1400954c8  cmovns  esi, r13d
0x1400954cc  mov     rax, [rax+48h]
0x1400954d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400954d5  mov     edi, eax
0x1400954d7  test    eax, eax
0x1400954d9  jns     short loc_140095510
0x1400954db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400954e2  cmp     rcx, r15
0x1400954e5  jz      loc_14009563E
0x1400954eb  test    byte ptr [rcx+1Ch], 8
0x1400954ef  jz      loc_14009563E
0x1400954f5  cmp     byte ptr [rcx+19h], 2
0x1400954f9  jb      loc_14009563E
0x1400954ff  mov     edx, 1Bh
0x140095504  lea     r9, aInternalsetaut; "InternalSetAuthScheme"
0x14009550b  jmp     loc_140095395
0x140095510  cmp     [rsp+2C0h+var_290], r12d
0x140095515  jz      short loc_14009554E
0x140095517  mov     rax, [rbx]
0x14009551a  mov     r15d, 4
0x140095520  mov     edx, r15d
0x140095523  mov     rcx, rbx
0x140095526  mov     rax, [rax+0D8h]
0x14009552d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140095532  cmp     [rsp+2C0h+var_28C], r12d
0x140095537  jz      short loc_14009554E
0x140095539  mov     rax, [rbx]
0x14009553c  mov     edx, r15d
0x14009553f  mov     rcx, rbx
0x140095542  mov     rax, [rax+0D0h]
0x140095549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009554e  mov     rcx, [rsp+2C0h+hKey]; hKey
0x140095553  lea     rax, [rsp+2C0h+cbData]
0x140095558  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x14009555d  lea     r9, [rsp+2C0h+Type]; lpType
0x140095562  lea     rax, [rsp+2C0h+Data]
0x140095567  mov     [rsp+2C0h+cbData], 208h
0x14009556f  xor     r8d, r8d; lpReserved
0x140095572  mov     [rsp+2C0h+phkResult], rax; lpData
0x140095577  lea     rdx, aAlternatespn; "AlternateSPN"
0x14009557e  mov     [rsp+2C0h+Type], r12d
0x140095583  call    cs:__imp_RegQueryValueExW
0x140095589  mov     r15d, eax
0x14009558c  test    eax, eax
0x14009558e  jnz     short loc_1400955EA
0x140095590  cmp     [rsp+2C0h+Type], r13d
0x140095595  jnz     short loc_1400955EA
0x140095597  cmp     [rsp+2C0h+cbData], r12d
0x14009559c  jbe     short loc_1400955EA
0x14009559e  mov     rax, [rbx]
0x1400955a1  lea     rdx, [rsp+2C0h+Data]
0x1400955a6  mov     rcx, rbx
0x1400955a9  mov     rax, [rax+0B8h]
0x1400955b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400955b5  mov     edi, eax
0x1400955b7  test    eax, eax
0x1400955b9  jns     short loc_14009563A
0x1400955bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400955c2  lea     rdx, WPP_GLOBAL_Control
0x1400955c9  cmp     rcx, rdx
0x1400955cc  jz      short loc_14009563E
0x1400955ce  test    byte ptr [rcx+1Ch], 8
0x1400955d2  jz      short loc_14009563E
0x1400955d4  cmp     byte ptr [rcx+19h], 2
0x1400955d8  jb      short loc_14009563E
0x1400955da  lea     edx, [r15+1Ch]
0x1400955de  lea     r9, aSetalternatesp; "SetAlternateSPN"
0x1400955e5  jmp     loc_140095395
0x1400955ea  mov     rax, cs:WPP_GLOBAL_Control
0x1400955f1  lea     rdx, WPP_GLOBAL_Control
0x1400955f8  cmp     rax, rdx
0x1400955fb  jz      short loc_140095632
0x1400955fd  test    [rax+1Ch], r13b
0x140095601  jz      short loc_140095632
0x140095603  cmp     byte ptr [rax+19h], 5
0x140095607  jb      short loc_140095632
0x140095609  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14009560e  mov     rcx, cs:WPP_GLOBAL_Control
0x140095615  lea     r8, WPP_4be363d4c2c33cc86d8cd0b2db161955_Traceguids
0x14009561c  mov     edx, 1Dh
0x140095621  mov     dword ptr [rsp+2C0h+phkResult], r15d
0x140095626  mov     r9d, eax
0x140095629  mov     rcx, [rcx+10h]
0x14009562d  call    WPP_SF_Dd
0x140095632  test    esi, esi
0x140095634  jz      loc_140095324
0x14009563a  test    edi, edi
0x14009563c  jz      short loc_140095654
0x14009563e  test    rbx, rbx
0x140095641  jz      short loc_140095657
0x140095643  mov     rax, [rbx]
0x140095646  mov     rcx, rbx
  ... truncated ...
```
