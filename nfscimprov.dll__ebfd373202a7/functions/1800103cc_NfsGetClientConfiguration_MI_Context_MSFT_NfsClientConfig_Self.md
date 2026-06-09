# NfsGetClientConfiguration(_MI_Context *,_MSFT_NfsClientConfig_Self *)

- ea: `0x1800103cc`
- end: `0x1800109b9`
- name: `?NfsGetClientConfiguration@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_MSFT_NfsClientConfig_Self@@@Z`
- size: `1517`
- prototype: `enum _MI_Result __fastcall(MI_Instance *self, struct _MSFT_NfsClientConfig_Self *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008e30`

## callees

- `0x18000be78`
- `0x18000bff0`
- `0x18000f544`
- `0x180010184`
- `0x1800103cc`
- `0x180013a40`
- `0x18002143c`
- `0x180021598`
- `0x180021744`
- `0x180023384`
- `0x180023484`
- `0x1800234d0`
- `0x180035b02`
- `0x180035b40`
- `0x180037010`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x18001056f`
- `ADVAPI32!RegGetValueW` at `0x18001056f`

## string_xrefs

- `0x1800107d9`: `MountType`
- `0x1800108d4`: `Access`
- `0x180010634`: `SOFTWARE\Microsoft\ClientForNFS\CurrentVersion\Users\Default\Mount`
- `0x18001068f`: `SOFTWARE\Microsoft\ClientForNFS\CurrentVersion\Users\Default\Mount`
- `0x1800107e0`: `SOFTWARE\Microsoft\ClientForNFS\CurrentVersion\Users\Default\Mount`
- `0x18001055a`: `Protocols`
- `0x18001062d`: `ReadBuffer`
- `0x180010688`: `WriteBuffer`
- `0x18001087a`: `NFSReadDir`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NfsGetClientConfiguration(MI_Instance *self, struct _MSFT_NfsClientConfig_Self *a2)
{
  enum _MI_Result CimProperty; // ebx
  LSTATUS ValueW; // eax
  int v6; // ecx
  unsigned int Value; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  char v10; // dl
  __int64 v11; // rcx
  unsigned int v12; // eax
  const wchar_t *v13; // rcx
  unsigned int v14; // eax
  unsigned int v15; // eax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  int pvData; // [rsp+44h] [rbp-BCh] BYREF
  int v19; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v20; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v21; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v22; // [rsp+54h] [rbp-ACh] BYREF
  int v23; // [rsp+58h] [rbp-A8h] BYREF
  int v24; // [rsp+5Ch] [rbp-A4h] BYREF
  int v25; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v26; // [rsp+68h] [rbp-98h] BYREF
  int v27; // [rsp+70h] [rbp-90h]
  int v28; // [rsp+74h] [rbp-8Ch]
  struct _MSFT_NfsClientConfig_Self *v29; // [rsp+78h] [rbp-88h] BYREF
  int v30; // [rsp+80h] [rbp-80h]
  _BYTE v31[56]; // [rsp+88h] [rbp-78h] BYREF
  MI_Instance selfa; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v33; // [rsp+110h] [rbp+10h]
  char v34; // [rsp+114h] [rbp+14h]
  bool v35; // [rsp+130h] [rbp+30h]
  char v36; // [rsp+131h] [rbp+31h]
  int v37; // [rsp+134h] [rbp+34h]
  char v38; // [rsp+138h] [rbp+38h]
  unsigned int v39; // [rsp+158h] [rbp+58h]
  char v40; // [rsp+15Ch] [rbp+5Ch]
  unsigned int v41; // [rsp+184h] [rbp+84h]
  char v42; // [rsp+188h] [rbp+88h]
  WCHAR ServiceName[528]; // [rsp+190h] [rbp+90h] BYREF
  _OWORD v44[2]; // [rsp+5B0h] [rbp+4B0h] BYREF
  __int128 v45; // [rsp+5D0h] [rbp+4D0h] BYREF
  __int64 v46; // [rsp+5E0h] [rbp+4E0h]

  pvData = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v19 = 0;
  v24 = 0;
  v25 = 0;
  pcbData = 0;
  v20 = 0;
  CNfsRegHive::CNfsRegHive((CNfsRegHive *)v31, 1);
  memset(v44, 0, sizeof(v44));
  v45 = 0;
  v46 = 0;
  memset_0(&selfa, 0, 0xD0u);
  NfsService::NfsService(ServiceName, L"NfsClnt", L"NfsRdr");
  v29 = a2;
  v30 = 0;
  CLock::AcquireLock((CLock *)&v29);
  if ( !self || !self->ft )
  {
    CimProperty = MI_RESULT_INVALID_PARAMETER;
LABEL_38:
    if ( !self )
      goto LABEL_41;
    goto LABEL_39;
  }
  CimProperty = ((unsigned int (__fastcall *)(MI_Instance *, void *, MI_Instance *))self->ft->IsA)(
                  self,
                  &MSFT_NfsClientConfig_rtti,
                  &selfa);
  if ( CimProperty )
    goto LABEL_38;
  v26 = L"nfsclnt";
  CimProperty = ((unsigned int (__fastcall *)(MI_Instance *, _QWORD, const wchar_t **, __int64, _DWORD))selfa.ft->SetElementAt)(
                  &selfa,
                  0,
                  &v26,
                  13,
                  0);
  if ( CimProperty == MI_RESULT_OK )
  {
    if ( !NfsService::GetServiceState((NfsService *)ServiceName, &v20) )
    {
      v33 = v20;
      v34 = 1;
      if ( !v20 )
        goto LABEL_35;
    }
    pcbData = 4;
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Default",
               L"Protocols",
               0x10u,
               0,
               &pvData,
               &pcbData);
    CimProperty = MapWinErrorToMIResult(ValueW);
    if ( CimProperty == MI_RESULT_OK )
    {
      if ( (pvData & 0x455455) != 0 )
        *(_QWORD *)&v45 = L"TCP";
      v6 = (pvData & 0x455455) != 0;
      if ( (pvData & 0x8AA8AA) != 0 )
      {
        *((_QWORD *)&v45 + ((pvData & 0x455455) != 0)) = L"UDP";
        ++v6;
      }
      v28 = 0;
      v26 = (const wchar_t *)&v45;
      v27 = v6;
      CimProperty = ((unsigned int (__fastcall *)(MI_Instance *, __int64, const wchar_t **))selfa.ft->SetElementAt)(
                      &selfa,
                      9,
                      &v26);
      if ( CimProperty == MI_RESULT_OK )
      {
        pcbData = 4;
        Value = CNfsRegHive::GetValue(
                  (CNfsRegHive *)v31,
                  L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Mount",
                  L"ReadBuffer",
                  0,
                  0x10u,
                  0,
                  &v21,
                  &pcbData);
        CimProperty = MapWinErrorToMIResult(Value);
        if ( CimProperty == MI_RESULT_OK )
        {
          v39 = v21 >> 10;
          v40 = 1;
          pcbData = 4;
          v8 = CNfsRegHive::GetValue(
                 (CNfsRegHive *)v31,
                 L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Mount",
                 L"WriteBuffer",
                 0,
                 0x10u,
                 0,
                 &v22,
                 &pcbData);
          CimProperty = MapWinErrorToMIResult(v8);
          if ( CimProperty == MI_RESULT_OK )
          {
            v41 = v22 >> 10;
            v42 = 1;
            pcbData = 4;
            v9 = CNfsRegHive::GetValue(
                   (CNfsRegHive *)v31,
                   L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Auth",
                   L"SecFlavors",
                   0,
                   0x10u,
                   0,
                   &v23,
                   &pcbData);
            CimProperty = MapWinErrorToMIResult(v9);
            if ( CimProperty == MI_RESULT_OK )
            {
              v10 = v23;
              v11 = v23 & 1;
              if ( (v23 & 1) != 0 )
                *(_QWORD *)&v44[0] = L"sys";
              if ( (v23 & 2) != 0 )
              {
                *((_QWORD *)v44 + v11) = L"Krb5";
                v11 = (unsigned int)(v11 + 1);
              }
              if ( (v10 & 4) != 0 )
              {
                *((_QWORD *)v44 + v11) = L"Krb5i";
                v11 = (unsigned int)(v11 + 1);
              }
              if ( (v10 & 8) != 0 )
              {
                *((_QWORD *)v44 + v11) = L"Krb5p";
                LODWORD(v11) = v11 + 1;
              }
              if ( !(_DWORD)v11
                || (v28 = 0,
                    v26 = (const wchar_t *)v44,
                    v27 = v11,
                    (CimProperty = ((unsigned int (__fastcall *)(MI_Instance *, __int64, const wchar_t **))selfa.ft->SetElementAt)(
                                     &selfa,
                                     2,
                                     &v26)) == MI_RESULT_OK) )
              {
                pcbData = 4;
                v12 = CNfsRegHive::GetValue(
                        (CNfsRegHive *)v31,
                        L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Mount",
                        L"MountType",
                        0,
                        0x10u,
                        0,
                        &v19,
                        &pcbData);
                CimProperty = MapWinErrorToMIResult(v12);
                if ( CimProperty == MI_RESULT_OK )
                {
                  if ( v19 == 1 )
                  {
                    v13 = L"soft";
                  }
                  else
                  {
                    v13 = L"hard";
                    if ( v19 != 2 )
                      v13 = 0;
                  }
                  v26 = v13;
                  CimProperty = ((unsigned int (__fastcall *)(MI_Instance *, __int64, const wchar_t **))selfa.ft->SetElementAt)(
                                  &selfa,
                                  5,
                                  &v26);
                  if ( CimProperty == MI_RESULT_OK )
                  {
                    pcbData = 4;
                    v14 = CNfsRegHive::GetValue(
                            (CNfsRegHive *)v31,
                            L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Defaults",
                            L"NFSReadDir",
                            0,
                            0x10u,
                            0,
                            &v24,
                            &pcbData);
                    CimProperty = MapWinErrorToMIResult(v14);
                    if ( CimProperty == MI_RESULT_OK )
                    {
                      v35 = v24 == 0;
                      v36 = 1;
                      pcbData = 4;
                      v15 = CNfsRegHive::GetValue(
                              (CNfsRegHive *)v31,
                              L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\Default\\Defaults",
                              L"Access",
                              0,
                              0x10u,
                              0,
                              &v25,
                              &pcbData);
                      CimProperty = MapWinErrorToMIResult(v15);
                      if ( CimProperty == MI_RESULT_OK )
                      {
                        v37 = v25 + 2 * (v25 / 8 + 10 * (v25 / 64));
                        v38 = 1;
                        CimProperty = NfsGetCimProperty(
                                        &selfa,
                                        (struct _NFS_CIMPROPERTY_REGKEY_PAIR *)off_180054E50,
                                        3u);
                        if ( CimProperty == MI_RESULT_OK )
LABEL_35:
                          CimProperty = MI_Instance_Destruct(self);
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  MI_Instance_Destruct(&selfa);
LABEL_39:
  if ( self->ft )
    ((void (__fastcall *)(MI_Instance *, _QWORD))self->ft->Clone)(self, (unsigned int)CimProperty);
LABEL_41:
  CLock::ReleaseLock((CLock *)&v29);
  NfsService::~NfsService((NfsService *)ServiceName);
  CNfsRegHive::~CNfsRegHive((CNfsRegHive *)v31);
  return (unsigned int)CimProperty;
}

```

## disassembly

```asm
0x1800103cc  push    rbp
0x1800103ce  push    rbx
0x1800103cf  push    rsi
0x1800103d0  push    rdi
0x1800103d1  push    r12
0x1800103d3  push    r14
0x1800103d5  lea     rbp, [rsp-4F8h]
0x1800103dd  sub     rsp, 5F8h
0x1800103e4  mov     rax, cs:__security_cookie
0x1800103eb  xor     rax, rsp
0x1800103ee  mov     [rbp+520h+var_38], rax
0x1800103f5  mov     rbx, rdx
0x1800103f8  mov     rsi, rcx
0x1800103fb  xor     r14d, r14d
0x1800103fe  mov     [rsp+620h+var_5DC], r14d
0x180010403  mov     [rsp+620h+var_5D0], r14d
0x180010408  mov     [rsp+620h+var_5CC], r14d
0x18001040d  mov     [rsp+620h+var_5C8], r14d
0x180010412  mov     [rsp+620h+var_5D8], r14d
0x180010417  mov     [rsp+620h+var_5C4], r14d
0x18001041c  mov     [rsp+620h+var_5C0], r14d
0x180010421  mov     [rsp+620h+var_5E0], r14d
0x180010426  mov     [rsp+620h+var_5D4], r14d
0x18001042b  lea     edx, [r14+1]; int
0x18001042f  lea     rcx, [rbp+520h+var_598]; this
0x180010433  call    ??0CNfsRegHive@@QEAA@H@Z; CNfsRegHive::CNfsRegHive(int)
0x180010438  nop
0x180010439  xorps   xmm0, xmm0
0x18001043c  movups  [rbp+520h+var_70], xmm0
0x180010443  movups  [rbp+520h+var_60], xmm0
0x18001044a  xorps   xmm1, xmm1
0x18001044d  xor     eax, eax
0x18001044f  movups  [rbp+520h+var_50], xmm1
0x180010456  mov     [rbp+520h+var_40], rax
0x18001045d  xor     edx, edx; Val
0x18001045f  mov     r8d, 0D0h; Size
0x180010465  lea     rcx, [rbp+520h+self]; void *
0x180010469  call    memset_0
0x18001046e  lea     r8, aNfsrdr_0; "NfsRdr"
0x180010475  lea     rdx, aNfsclnt_0; "NfsClnt"
0x18001047c  lea     rcx, [rbp+520h+ServiceName]; lpServiceName
0x180010483  call    ??0NfsService@@QEAA@PEBG0@Z; NfsService::NfsService(ushort const *,ushort const *)
0x180010488  nop
0x180010489  mov     [rsp+620h+var_5A8], rbx
0x18001048e  mov     [rbp+520h+var_5A0], r14d
0x180010492  lea     rcx, [rsp+620h+var_5A8]; this
0x180010497  call    ?AcquireLock@CLock@@QEAAXXZ; CLock::AcquireLock(void)
0x18001049c  test    rsi, rsi
0x18001049f  jz      loc_180010957
0x1800104a5  mov     rax, [rsi]
0x1800104a8  test    rax, rax
0x1800104ab  jz      loc_180010957
0x1800104b1  lea     r8, [rbp+520h+self]
0x1800104b5  lea     rdx, MSFT_NfsClientConfig_rtti
0x1800104bc  mov     rcx, rsi
0x1800104bf  mov     rax, [rax+18h]
0x1800104c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104c8  mov     ebx, eax
0x1800104ca  test    eax, eax
0x1800104cc  jnz     loc_18001095C
0x1800104d2  lea     rax, aNfsclnt; "nfsclnt"
0x1800104d9  mov     [rsp+620h+var_5B8], rax
0x1800104de  mov     rax, [rbp+520h+self.ft]
0x1800104e2  mov     dword ptr [rsp+620h+pdwType], r14d
0x1800104e7  lea     r9d, [r14+0Dh]
0x1800104eb  lea     r8, [rsp+620h+var_5B8]
0x1800104f0  xor     edx, edx
0x1800104f2  lea     rcx, [rbp+520h+self]
0x1800104f6  mov     rax, [rax+50h]
0x1800104fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104ff  mov     ebx, eax
0x180010501  test    eax, eax
0x180010503  jnz     loc_18001094C
0x180010509  lea     rdx, [rsp+620h+var_5D4]; unsigned int *
0x18001050e  lea     rcx, [rbp+520h+ServiceName]; this
0x180010515  call    ?GetServiceState@NfsService@@QEAAKPEAK@Z; NfsService::GetServiceState(ulong *)
0x18001051a  test    eax, eax
0x18001051c  jnz     short loc_180010531
0x18001051e  mov     eax, [rsp+620h+var_5D4]
0x180010522  mov     [rbp+520h+var_510], eax
0x180010525  mov     [rbp+520h+var_50C], 1
0x180010529  test    eax, eax
0x18001052b  jz      loc_18001093E
0x180010531  mov     edi, 4
0x180010536  mov     [rsp+620h+var_5E0], edi
0x18001053a  lea     rax, [rsp+620h+var_5E0]
0x18001053f  mov     [rsp+620h+pcbData], rax; pcbData
0x180010544  lea     rax, [rsp+620h+var_5DC]
0x180010549  mov     [rsp+620h+pvData], rax; pvData
0x18001054e  mov     [rsp+620h+pdwType], r14; pdwType
0x180010553  lea     r12d, [rdi+0Ch]
0x180010557  mov     r9d, r12d; dwFlags
0x18001055a  lea     r8, ValueName; "Protocols"
0x180010561  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x180010568  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001056f  call    cs:__imp_RegGetValueW
0x180010575  mov     ecx, eax; unsigned int
0x180010577  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x18001057c  mov     ebx, eax
0x18001057e  test    eax, eax
0x180010580  jnz     loc_18001094C
0x180010586  mov     eax, [rsp+620h+var_5DC]
0x18001058a  and     eax, 455455h
0x18001058f  jz      short loc_18001059F
0x180010591  lea     rcx, aTcp; "TCP"
0x180010598  mov     qword ptr [rbp+520h+var_50], rcx
0x18001059f  mov     ecx, r14d
0x1800105a2  test    eax, eax
0x1800105a4  setnz   cl
0x1800105a7  test    [rsp+620h+var_5DC], 8AA8AAh
0x1800105af  jz      short loc_1800105C4
0x1800105b1  mov     eax, ecx
0x1800105b3  lea     rdx, aUdp; "UDP"
0x1800105ba  mov     qword ptr [rbp+rax*8+520h+var_50], rdx
0x1800105c2  inc     ecx
0x1800105c4  mov     [rsp+620h+var_5AC], r14d
0x1800105c9  lea     rax, [rbp+520h+var_50]
0x1800105d0  mov     [rsp+620h+var_5B8], rax
0x1800105d5  mov     [rsp+620h+var_5B0], ecx
0x1800105d9  mov     rax, [rbp+520h+self.ft]
0x1800105dd  mov     dword ptr [rsp+620h+pdwType], r14d
0x1800105e2  mov     r9d, 1Dh
0x1800105e8  lea     r8, [rsp+620h+var_5B8]
0x1800105ed  lea     edx, [r9-14h]
0x1800105f1  lea     rcx, [rbp+520h+self]
0x1800105f5  mov     rax, [rax+50h]
0x1800105f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105fe  mov     ebx, eax
0x180010600  test    eax, eax
0x180010602  jnz     loc_18001094C
0x180010608  mov     [rsp+620h+var_5E0], edi
0x18001060c  lea     rax, [rsp+620h+var_5E0]
0x180010611  mov     [rsp+620h+var_5E8], rax; unsigned int *
0x180010616  lea     rax, [rsp+620h+var_5D0]
0x18001061b  mov     [rsp+620h+pcbData], rax; void *
0x180010620  mov     [rsp+620h+pvData], r14; unsigned int *
0x180010625  mov     dword ptr [rsp+620h+pdwType], r12d; unsigned int
0x18001062a  xor     r9d, r9d; unsigned __int16 *
0x18001062d  lea     r8, aReadbuffer; "ReadBuffer"
0x180010634  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x18001063b  lea     rcx, [rbp+520h+var_598]; this
0x18001063f  call    ?GetValue@CNfsRegHive@@QEAAJPEBG00KPEAKPEAX1@Z; CNfsRegHive::GetValue(ushort const *,ushort const *,ushort const *,ulong,ulong *,void *,ulong *)
0x180010644  mov     ecx, eax; unsigned int
0x180010646  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x18001064b  mov     ebx, eax
0x18001064d  test    eax, eax
0x18001064f  jnz     loc_18001094C
0x180010655  mov     eax, [rsp+620h+var_5D0]
0x180010659  shr     eax, 0Ah
0x18001065c  mov     [rbp+520h+var_4C8], eax
0x18001065f  mov     [rbp+520h+var_4C4], 1
0x180010663  mov     [rsp+620h+var_5E0], edi
0x180010667  lea     rax, [rsp+620h+var_5E0]
0x18001066c  mov     [rsp+620h+var_5E8], rax; unsigned int *
0x180010671  lea     rax, [rsp+620h+var_5CC]
0x180010676  mov     [rsp+620h+pcbData], rax; void *
0x18001067b  mov     [rsp+620h+pvData], r14; unsigned int *
0x180010680  mov     dword ptr [rsp+620h+pdwType], r12d; unsigned int
0x180010685  xor     r9d, r9d; unsigned __int16 *
0x180010688  lea     r8, aWritebuffer; "WriteBuffer"
0x18001068f  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x180010696  lea     rcx, [rbp+520h+var_598]; this
0x18001069a  call    ?GetValue@CNfsRegHive@@QEAAJPEBG00KPEAKPEAX1@Z; CNfsRegHive::GetValue(ushort const *,ushort const *,ushort const *,ulong,ulong *,void *,ulong *)
0x18001069f  mov     ecx, eax; unsigned int
0x1800106a1  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x1800106a6  mov     ebx, eax
0x1800106a8  test    eax, eax
0x1800106aa  jnz     loc_18001094C
0x1800106b0  mov     eax, [rsp+620h+var_5CC]
0x1800106b4  shr     eax, 0Ah
0x1800106b7  mov     [rbp+520h+var_49C], eax
0x1800106bd  mov     [rbp+520h+var_498], 1
0x1800106c4  mov     [rsp+620h+var_5E0], edi
0x1800106c8  lea     rax, [rsp+620h+var_5E0]
0x1800106cd  mov     [rsp+620h+var_5E8], rax; unsigned int *
0x1800106d2  lea     rax, [rsp+620h+var_5C8]
0x1800106d7  mov     [rsp+620h+pcbData], rax; void *
0x1800106dc  mov     [rsp+620h+pvData], r14; unsigned int *
0x1800106e1  mov     dword ptr [rsp+620h+pdwType], r12d; unsigned int
0x1800106e6  xor     r9d, r9d; unsigned __int16 *
0x1800106e9  lea     r8, aSecflavors; "SecFlavors"
0x1800106f0  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x1800106f7  lea     rcx, [rbp+520h+var_598]; this
0x1800106fb  call    ?GetValue@CNfsRegHive@@QEAAJPEBG00KPEAKPEAX1@Z; CNfsRegHive::GetValue(ushort const *,ushort const *,ushort const *,ulong,ulong *,void *,ulong *)
0x180010700  mov     ecx, eax; unsigned int
0x180010702  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x180010707  mov     ebx, eax
0x180010709  test    eax, eax
0x18001070b  jnz     loc_18001094C
0x180010711  mov     edx, [rsp+620h+var_5C8]
0x180010715  mov     ecx, edx
0x180010717  and     ecx, 1
0x18001071a  jz      short loc_18001072A
0x18001071c  lea     rax, aSys; "sys"
0x180010723  mov     qword ptr [rbp+520h+var_70], rax
0x18001072a  test    dl, 2
0x18001072d  jz      short loc_180010740
0x18001072f  lea     r8, aKrb5; "Krb5"
0x180010736  mov     qword ptr [rbp+rcx*8+520h+var_70], r8
0x18001073e  inc     ecx
0x180010740  test    dil, dl
0x180010743  jz      short loc_180010756
0x180010745  lea     r8, aKrb5i; "Krb5i"
0x18001074c  mov     qword ptr [rbp+rcx*8+520h+var_70], r8
0x180010754  inc     ecx
0x180010756  test    dl, 8
0x180010759  jz      short loc_18001076C
0x18001075b  lea     rdx, aKrb5p; "Krb5p"
0x180010762  mov     qword ptr [rbp+rcx*8+520h+var_70], rdx
0x18001076a  inc     ecx
0x18001076c  test    ecx, ecx
0x18001076e  jz      short loc_1800107B4
0x180010770  mov     [rsp+620h+var_5AC], r14d
0x180010775  lea     rax, [rbp+520h+var_70]
0x18001077c  mov     [rsp+620h+var_5B8], rax
0x180010781  mov     [rsp+620h+var_5B0], ecx
0x180010785  mov     rax, [rbp+520h+self.ft]
0x180010789  mov     dword ptr [rsp+620h+pdwType], r14d
0x18001078e  mov     r9d, 1Dh
0x180010794  lea     r8, [rsp+620h+var_5B8]
0x180010799  lea     edx, [r9-1Bh]
0x18001079d  lea     rcx, [rbp+520h+self]
0x1800107a1  mov     rax, [rax+50h]
0x1800107a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107aa  mov     ebx, eax
0x1800107ac  test    eax, eax
0x1800107ae  jnz     loc_18001094C
0x1800107b4  mov     [rsp+620h+var_5E0], edi
0x1800107b8  lea     rax, [rsp+620h+var_5E0]
0x1800107bd  mov     [rsp+620h+var_5E8], rax; unsigned int *
0x1800107c2  lea     rax, [rsp+620h+var_5D8]
0x1800107c7  mov     [rsp+620h+pcbData], rax; void *
0x1800107cc  mov     [rsp+620h+pvData], r14; unsigned int *
0x1800107d1  mov     dword ptr [rsp+620h+pdwType], r12d; unsigned int
0x1800107d6  xor     r9d, r9d; unsigned __int16 *
0x1800107d9  lea     r8, aMounttype; "MountType"
0x1800107e0  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x1800107e7  lea     rcx, [rbp+520h+var_598]; this
0x1800107eb  call    ?GetValue@CNfsRegHive@@QEAAJPEBG00KPEAKPEAX1@Z; CNfsRegHive::GetValue(ushort const *,ushort const *,ushort const *,ulong,ulong *,void *,ulong *)
0x1800107f0  mov     ecx, eax; unsigned int
0x1800107f2  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x1800107f7  mov     ebx, eax
0x1800107f9  test    eax, eax
0x1800107fb  jnz     loc_18001094C
0x180010801  cmp     [rsp+620h+var_5D8], 1
0x180010806  jnz     short loc_180010811
0x180010808  lea     rcx, aSoft; "soft"
0x18001080f  jmp     short loc_180010821
0x180010811  lea     rcx, aHard; "hard"
0x180010818  cmp     [rsp+620h+var_5D8], 2
0x18001081d  cmovnz  rcx, r14
0x180010821  mov     [rsp+620h+var_5B8], rcx
0x180010826  mov     rax, [rbp+520h+self.ft]
0x18001082a  mov     dword ptr [rsp+620h+pdwType], r14d
0x18001082f  mov     r9d, 0Dh
0x180010835  lea     r8, [rsp+620h+var_5B8]
0x18001083a  lea     edx, [r9-8]
0x18001083e  lea     rcx, [rbp+520h+self]
0x180010842  mov     rax, [rax+50h]
0x180010846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001084b  mov     ebx, eax
0x18001084d  test    eax, eax
0x18001084f  jnz     loc_18001094C
0x180010855  mov     [rsp+620h+var_5E0], edi
0x180010859  lea     rax, [rsp+620h+var_5E0]
0x18001085e  mov     [rsp+620h+var_5E8], rax; unsigned int *
0x180010863  lea     rax, [rsp+620h+var_5C4]
0x180010868  mov     [rsp+620h+pcbData], rax; void *
0x18001086d  mov     [rsp+620h+pvData], r14; unsigned int *
0x180010872  mov     dword ptr [rsp+620h+pdwType], r12d; unsigned int
0x180010877  xor     r9d, r9d; unsigned __int16 *
0x18001087a  lea     r8, aNfsreaddir; "NFSReadDir"
0x180010881  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x180010888  lea     rcx, [rbp+520h+var_598]; this
0x18001088c  call    ?GetValue@CNfsRegHive@@QEAAJPEBG00KPEAKPEAX1@Z; CNfsRegHive::GetValue(ushort const *,ushort const *,ushort const *,ulong,ulong *,void *,ulong *)
0x180010891  mov     ecx, eax; unsigned int
0x180010893  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x180010898  mov     ebx, eax
0x18001089a  test    eax, eax
0x18001089c  jnz     loc_18001094C
0x1800108a2  cmp     [rsp+620h+var_5C4], r14d
0x1800108a7  setz    [rbp+520h+var_4F0]
0x1800108ab  mov     [rbp+520h+var_4EF], 1
0x1800108af  mov     [rsp+620h+var_5E0], edi
0x1800108b3  lea     rax, [rsp+620h+var_5E0]
0x1800108b8  mov     [rsp+620h+var_5E8], rax; unsigned int *
0x1800108bd  lea     rax, [rsp+620h+var_5C0]
0x1800108c2  mov     [rsp+620h+pcbData], rax; void *
0x1800108c7  mov     [rsp+620h+pvData], r14; unsigned int *
0x1800108cc  mov     dword ptr [rsp+620h+pdwType], r12d; unsigned int
0x1800108d1  xor     r9d, r9d; unsigned __int16 *
0x1800108d4  lea     r8, aAccess; "Access"
0x1800108db  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x1800108e2  lea     rcx, [rbp+520h+var_598]; this
0x1800108e6  call    ?GetValue@CNfsRegHive@@QEAAJPEBG00KPEAKPEAX1@Z; CNfsRegHive::GetValue(ushort const *,ushort const *,ushort const *,ulong,ulong *,void *,ulong *)
0x1800108eb  mov     ecx, eax; unsigned int
0x1800108ed  call    ?MapWinErrorToMIResult@@YA?AW4_MI_Result@@K@Z; MapWinErrorToMIResult(ulong)
0x1800108f2  mov     ebx, eax
0x1800108f4  test    eax, eax
0x1800108f6  jnz     short loc_18001094C
  ... truncated ...
```
