# AAGPHelper::LoadGPProfile(RdpXInterfaceGatewayProfile * *)

- ea: `0x140092ff8`
- end: `0x140093526`
- name: `?LoadGPProfile@AAGPHelper@@SAJPEAPEAURdpXInterfaceGatewayProfile@@@Z`
- size: `1326`
- prototype: `__int64 __fastcall(struct RdpXInterfaceGatewayProfile **)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140092808`
- `0x1400936a0`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x140040b9c`
- `0x140061bd0`
- `0x1400620e8`
- `0x140092948`
- `0x140092b64`
- `0x140092dd4`
- `0x140092ff8`
- `0x14009352c`
- `0x140111220`
- `0x140112010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14009316c`
- `ADVAPI32!RegOpenKeyExW` at `0x14009316c`
- `ADVAPI32!RegCloseKey` at `0x1400934f1`
- `ADVAPI32!RegCloseKey` at `0x1400934f1`
- `ADVAPI32!RegQueryValueExW` at `0x140093413`
- `ADVAPI32!RegQueryValueExW` at `0x140093413`

## string_xrefs

- `0x14009315e`: `Software\Policies\Microsoft\Windows NT\Terminal Services`

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
  _QWORD v28[2]; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[528]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  v28[0] = 0;
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
  Object = RdpX_CreateObject(v3, a2, 88, 125, v28);
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
  (**(void (__fastcall ***)(_QWORD))v28[0])(v28[0]);
  v8 = (struct RdpXInterfaceGatewayProfile *)v28[0];
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
  RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(v28);
  return (unsigned int)DefaultProxyHostName;
}

```

## disassembly

```asm
0x140092ff8  push    rbp
0x140092ffa  push    rbx
0x140092ffb  push    rsi
0x140092ffc  push    rdi
0x140092ffd  push    r12
0x140092fff  push    r13
0x140093001  push    r14
0x140093003  push    r15
0x140093005  lea     rbp, [rsp-188h]
0x14009300d  sub     rsp, 288h
0x140093014  mov     rax, cs:__security_cookie
0x14009301b  xor     rax, rsp
0x14009301e  mov     [rbp+1C0h+var_50], rax
0x140093025  xor     r12d, r12d
0x140093028  mov     r14, rcx
0x14009302b  mov     [rsp+2C0h+hKey], r12
0x140093030  mov     [rsp+2C0h+var_270], r12
0x140093035  mov     word ptr [rsp+2C0h+Data], r12w
0x14009303b  mov     [rsp+2C0h+var_28C], r12d
0x140093040  mov     [rsp+2C0h+var_290], r12d
0x140093045  mov     rcx, cs:WPP_GLOBAL_Control
0x14009304c  lea     r15, WPP_GLOBAL_Control
0x140093053  lea     rsi, WPP_4be363d4c2c33cc86d8cd0b2db161955_Traceguids
0x14009305a  lea     r13d, [r12+1]
0x14009305f  cmp     rcx, r15
0x140093062  jz      short loc_140093097
0x140093064  test    [rcx+1Ch], r13b
0x140093068  jz      short loc_140093097
0x14009306a  cmp     byte ptr [rcx+19h], 5
0x14009306e  jb      short loc_140093097
0x140093070  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140093075  mov     rcx, cs:WPP_GLOBAL_Control
0x14009307c  lea     edx, [r12+15h]
0x140093081  mov     r9d, eax
0x140093084  mov     r8, rsi
0x140093087  mov     rcx, [rcx+10h]
0x14009308b  call    WPP_SF_d
0x140093090  mov     rcx, cs:WPP_GLOBAL_Control
0x140093097  test    r14, r14
0x14009309a  jnz     short loc_1400930CE
0x14009309c  cmp     rcx, r15
0x14009309f  jz      short loc_1400930C4
0x1400930a1  test    byte ptr [rcx+1Ch], 8
0x1400930a5  jz      short loc_1400930C4
0x1400930a7  cmp     byte ptr [rcx+19h], 2
0x1400930ab  jb      short loc_1400930C4
0x1400930ad  mov     rcx, [rcx+10h]
0x1400930b1  lea     edx, [r14+16h]
0x1400930b5  lea     r9, aPpprofile; "ppProfile"
0x1400930bc  mov     r8, rsi
0x1400930bf  call    WPP_SF_S
0x1400930c4  mov     edi, 80070057h
0x1400930c9  jmp     loc_1400934E7
0x1400930ce  mov     r9d, 7Dh ; '}'
0x1400930d4  mov     [r14], r12
0x1400930d7  lea     rax, [rsp+2C0h+var_270]
0x1400930dc  mov     [rsp+2C0h+phkResult], rax
0x1400930e1  lea     r8d, [r9-25h]
0x1400930e5  call    ?RdpX_CreateObject@@YA?AW4_XResult32@@PEAURdpXInterface@@IW4_XObjectId32@@W4_XInterfaceId32@@PEAPEAX@Z; RdpX_CreateObject(RdpXInterface *,uint,_XObjectId32,_XInterfaceId32,void * *)
0x1400930ea  mov     ebx, eax
0x1400930ec  test    eax, eax
0x1400930ee  jz      short loc_140093136
0x1400930f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400930f7  cmp     rcx, r15
0x1400930fa  jz      short loc_14009312C
0x1400930fc  test    [rcx+1Ch], r13b
0x140093100  jz      short loc_14009312C
0x140093102  cmp     byte ptr [rcx+19h], 2
0x140093106  jb      short loc_14009312C
0x140093108  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14009310d  mov     rcx, cs:WPP_GLOBAL_Control
0x140093114  mov     edx, 17h
0x140093119  mov     r9d, eax
0x14009311c  mov     dword ptr [rsp+2C0h+phkResult], ebx
0x140093120  mov     r8, rsi
0x140093123  mov     rcx, [rcx+10h]
0x140093127  call    WPP_SF_Dd
0x14009312c  mov     edi, 80004005h
0x140093131  jmp     loc_1400934E7
0x140093136  mov     rcx, [rsp+2C0h+var_270]
0x14009313b  mov     rax, [rcx]
0x14009313e  mov     rax, [rax]
0x140093141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140093146  mov     rbx, [rsp+2C0h+var_270]
0x14009314b  lea     rax, [rsp+2C0h+hKey]
0x140093150  mov     r9d, 20019h; samDesired
0x140093156  mov     [rsp+2C0h+phkResult], rax; phkResult
0x14009315b  xor     r8d, r8d; ulOptions
0x14009315e  lea     rdx, aSoftwarePolici_1; "Software\\Policies\\Microsoft\\Windows "...
0x140093165  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14009316c  call    cs:__imp_RegOpenKeyExW
0x140093172  mov     edi, eax
0x140093174  test    eax, eax
0x140093176  jz      short loc_1400931BC
0x140093178  mov     rcx, cs:WPP_GLOBAL_Control
0x14009317f  cmp     rcx, r15
0x140093182  jz      short loc_1400931B4
0x140093184  test    [rcx+1Ch], r13b
0x140093188  jz      short loc_1400931B4
0x14009318a  cmp     byte ptr [rcx+19h], 3
0x14009318e  jb      short loc_1400931B4
0x140093190  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140093195  mov     rcx, cs:WPP_GLOBAL_Control
0x14009319c  mov     edx, 18h
0x1400931a1  mov     r9d, eax
0x1400931a4  mov     dword ptr [rsp+2C0h+phkResult], edi
0x1400931a8  mov     r8, rsi
0x1400931ab  mov     rcx, [rcx+10h]
0x1400931af  call    WPP_SF_Dd
0x1400931b4  mov     edi, r13d
0x1400931b7  jmp     loc_1400934CE
0x1400931bc  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1400931c1  lea     r9, [rsp+2C0h+var_290]; int *
0x1400931c6  lea     r8, [rsp+2C0h+var_28C]; int *
0x1400931cb  mov     [rsp+2C0h+var_288], r12d
0x1400931d0  lea     rdx, [rsp+2C0h+var_288]; enum _XRdpGatewayProxyUsage *
0x1400931d5  call    ?InternalGetDefaultProxyUsage@@YAJPEAUHKEY__@@PEAW4_XRdpGatewayProxyUsage@@PEAH2@Z; InternalGetDefaultProxyUsage(HKEY__ *,_XRdpGatewayProxyUsage *,int *,int *)
0x1400931da  mov     rcx, [rbx]
0x1400931dd  mov     esi, eax
0x1400931df  mov     edx, [rsp+2C0h+var_288]
0x1400931e3  mov     rax, [rcx+68h]
0x1400931e7  mov     rcx, rbx
0x1400931ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400931ef  mov     edi, eax
0x1400931f1  test    eax, eax
0x1400931f3  jns     short loc_140093237
0x1400931f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400931fc  cmp     rcx, r15
0x1400931ff  jz      loc_1400934CE
0x140093205  test    byte ptr [rcx+1Ch], 8
0x140093209  jz      loc_1400934CE
0x14009320f  cmp     byte ptr [rcx+19h], 2
0x140093213  jb      loc_1400934CE
0x140093219  mov     edx, 19h
0x14009321e  lea     r9, aSetproxyusage; "SetProxyUsage"
0x140093225  mov     dword ptr [rsp+2C0h+phkResult], eax
0x140093229  mov     rcx, [rcx+10h]
0x14009322d  call    WPP_SF_Sd
0x140093232  jmp     loc_1400934CE
0x140093237  cmp     [rsp+2C0h+var_290], r12d
0x14009323c  jz      short loc_14009326F
0x14009323e  mov     rax, [rbx]
0x140093241  mov     edx, r13d
0x140093244  mov     rcx, rbx
0x140093247  mov     rax, [rax+0D8h]
0x14009324e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140093253  cmp     [rsp+2C0h+var_28C], r12d
0x140093258  jz      short loc_14009326F
0x14009325a  mov     rax, [rbx]
0x14009325d  mov     edx, r13d
0x140093260  mov     rcx, rbx
0x140093263  mov     rax, [rax+0D0h]
0x14009326a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009326f  mov     rcx, [rsp+2C0h+hKey]; hKey
0x140093274  lea     rax, [rsp+2C0h+var_290]
0x140093279  lea     r9, [rsp+2C0h+var_28C]; int *
0x14009327e  mov     [rsp+2C0h+phkResult], rax; int *
0x140093283  lea     rdx, [rsp+2C0h+Data]; lpData
0x140093288  call    ?InternalGetDefaultProxyHostName@@YAJPEAUHKEY__@@PEAGKPEAH2@Z; InternalGetDefaultProxyHostName(HKEY__ *,ushort *,ulong,int *,int *)
0x14009328d  mov     edi, eax
0x14009328f  test    eax, eax
0x140093291  js      short loc_140093298
0x140093293  mov     esi, r13d
0x140093296  jmp     short loc_14009329D
0x140093298  not     esi
0x14009329a  shr     esi, 1Fh
0x14009329d  cmp     [rsp+2C0h+var_290], r12d
0x1400932a2  jz      loc_14009332E
0x1400932a8  mov     rax, [rbx]
0x1400932ab  lea     rdx, [rsp+2C0h+Data]
0x1400932b0  mov     rcx, rbx
0x1400932b3  mov     rax, [rax+40h]
0x1400932b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400932bc  test    edi, edi
0x1400932be  jns     short loc_1400932F9
0x1400932c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400932c7  cmp     rcx, r15
0x1400932ca  jz      loc_1400934CE
0x1400932d0  test    byte ptr [rcx+1Ch], 8
0x1400932d4  jz      loc_1400934CE
0x1400932da  cmp     byte ptr [rcx+19h], 2
0x1400932de  jb      loc_1400934CE
0x1400932e4  mov     edx, 1Ah
0x1400932e9  mov     dword ptr [rsp+2C0h+phkResult], edi
0x1400932ed  lea     r9, aSetproxyhostna; "SetProxyHostNameAndPort"
0x1400932f4  jmp     loc_140093229
0x1400932f9  mov     rax, [rbx]
0x1400932fc  mov     edx, 2
0x140093301  mov     rcx, rbx
0x140093304  mov     rax, [rax+0D8h]
0x14009330b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140093310  cmp     [rsp+2C0h+var_28C], r12d
0x140093315  jz      short loc_14009332E
0x140093317  mov     rax, [rbx]
0x14009331a  mov     edx, 2
0x14009331f  mov     rcx, rbx
0x140093322  mov     rax, [rax+0D0h]
0x140093329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009332e  mov     rcx, [rsp+2C0h+hKey]; hKey
0x140093333  lea     r9, [rsp+2C0h+var_290]; int *
0x140093338  lea     r8, [rsp+2C0h+var_28C]; int *
0x14009333d  mov     [rsp+2C0h+var_288], r12d
0x140093342  lea     rdx, [rsp+2C0h+var_288]; enum _XRdpGatewayAuthSchemes *
0x140093347  call    ?InternalGetDefaultAuthMode@@YAJPEAUHKEY__@@PEAW4_XRdpGatewayAuthSchemes@@PEAH2@Z; InternalGetDefaultAuthMode(HKEY__ *,_XRdpGatewayAuthSchemes *,int *,int *)
0x14009334c  mov     edx, [rsp+2C0h+var_288]
0x140093350  test    eax, eax
0x140093352  mov     rax, [rbx]
0x140093355  mov     rcx, rbx
0x140093358  cmovns  esi, r13d
0x14009335c  mov     rax, [rax+48h]
0x140093360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140093365  mov     edi, eax
0x140093367  test    eax, eax
0x140093369  jns     short loc_1400933A0
0x14009336b  mov     rcx, cs:WPP_GLOBAL_Control
0x140093372  cmp     rcx, r15
0x140093375  jz      loc_1400934CE
0x14009337b  test    byte ptr [rcx+1Ch], 8
0x14009337f  jz      loc_1400934CE
0x140093385  cmp     byte ptr [rcx+19h], 2
0x140093389  jb      loc_1400934CE
0x14009338f  mov     edx, 1Bh
0x140093394  lea     r9, aInternalsetaut; "InternalSetAuthScheme"
0x14009339b  jmp     loc_140093225
0x1400933a0  cmp     [rsp+2C0h+var_290], r12d
0x1400933a5  jz      short loc_1400933DE
0x1400933a7  mov     rax, [rbx]
0x1400933aa  mov     r15d, 4
0x1400933b0  mov     edx, r15d
0x1400933b3  mov     rcx, rbx
0x1400933b6  mov     rax, [rax+0D8h]
0x1400933bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400933c2  cmp     [rsp+2C0h+var_28C], r12d
0x1400933c7  jz      short loc_1400933DE
0x1400933c9  mov     rax, [rbx]
0x1400933cc  mov     edx, r15d
0x1400933cf  mov     rcx, rbx
0x1400933d2  mov     rax, [rax+0D0h]
0x1400933d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400933de  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1400933e3  lea     rax, [rsp+2C0h+cbData]
0x1400933e8  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x1400933ed  lea     r9, [rsp+2C0h+Type]; lpType
0x1400933f2  lea     rax, [rsp+2C0h+Data]
0x1400933f7  mov     [rsp+2C0h+cbData], 208h
0x1400933ff  xor     r8d, r8d; lpReserved
0x140093402  mov     [rsp+2C0h+phkResult], rax; lpData
0x140093407  lea     rdx, aAlternatespn; "AlternateSPN"
0x14009340e  mov     [rsp+2C0h+Type], r12d
0x140093413  call    cs:__imp_RegQueryValueExW
0x140093419  mov     r15d, eax
0x14009341c  test    eax, eax
0x14009341e  jnz     short loc_14009347A
0x140093420  cmp     [rsp+2C0h+Type], r13d
0x140093425  jnz     short loc_14009347A
0x140093427  cmp     [rsp+2C0h+cbData], r12d
0x14009342c  jbe     short loc_14009347A
0x14009342e  mov     rax, [rbx]
0x140093431  lea     rdx, [rsp+2C0h+Data]
0x140093436  mov     rcx, rbx
0x140093439  mov     rax, [rax+0B8h]
0x140093440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140093445  mov     edi, eax
0x140093447  test    eax, eax
0x140093449  jns     short loc_1400934CA
0x14009344b  mov     rcx, cs:WPP_GLOBAL_Control
0x140093452  lea     rdx, WPP_GLOBAL_Control
0x140093459  cmp     rcx, rdx
0x14009345c  jz      short loc_1400934CE
0x14009345e  test    byte ptr [rcx+1Ch], 8
0x140093462  jz      short loc_1400934CE
0x140093464  cmp     byte ptr [rcx+19h], 2
0x140093468  jb      short loc_1400934CE
0x14009346a  lea     edx, [r15+1Ch]
0x14009346e  lea     r9, aSetalternatesp; "SetAlternateSPN"
0x140093475  jmp     loc_140093225
0x14009347a  mov     rax, cs:WPP_GLOBAL_Control
0x140093481  lea     rdx, WPP_GLOBAL_Control
0x140093488  cmp     rax, rdx
0x14009348b  jz      short loc_1400934C2
0x14009348d  test    [rax+1Ch], r13b
0x140093491  jz      short loc_1400934C2
0x140093493  cmp     byte ptr [rax+19h], 5
0x140093497  jb      short loc_1400934C2
0x140093499  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14009349e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400934a5  lea     r8, WPP_4be363d4c2c33cc86d8cd0b2db161955_Traceguids
0x1400934ac  mov     edx, 1Dh
0x1400934b1  mov     dword ptr [rsp+2C0h+phkResult], r15d
0x1400934b6  mov     r9d, eax
0x1400934b9  mov     rcx, [rcx+10h]
0x1400934bd  call    WPP_SF_Dd
0x1400934c2  test    esi, esi
0x1400934c4  jz      loc_1400931B4
0x1400934ca  test    edi, edi
0x1400934cc  jz      short loc_1400934E4
0x1400934ce  test    rbx, rbx
0x1400934d1  jz      short loc_1400934E7
0x1400934d3  mov     rax, [rbx]
0x1400934d6  mov     rcx, rbx
  ... truncated ...
```
