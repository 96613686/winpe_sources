# FAX_SetSecurityEx2

- ea: `0x140046610`
- end: `0x140046a73`
- name: `FAX_SetSecurityEx2`
- size: `1123`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x14000c5ac`
- `0x1400452ac`
- `0x140045c88`
- `0x140046610`
- `0x14005549c`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x140046840`
- `ADVAPI32!OpenThreadToken` at `0x140046840`
- `ADVAPI32!SetPrivateObjectSecurity` at `0x140046911`
- `ADVAPI32!SetPrivateObjectSecurity` at `0x140046911`
- `KERNEL32!GetLastError` at `0x14004684a`
- `KERNEL32!GetLastError` at `0x14004691b`
- `KERNEL32!GetLastError` at `0x140046a0a`
- `KERNEL32!GetLastError` at `0x14004684a`
- `KERNEL32!GetLastError` at `0x14004691b`
- `KERNEL32!GetLastError` at `0x140046a0a`
- `KERNEL32!CloseHandle` at `0x1400469e8`
- `KERNEL32!CloseHandle` at `0x1400469e8`
- `KERNEL32!EnterCriticalSection` at `0x140046746`
- `KERNEL32!EnterCriticalSection` at `0x140046746`
- `KERNEL32!LeaveCriticalSection` at `0x1400469d8`
- `KERNEL32!LeaveCriticalSection` at `0x1400469d8`
- `KERNEL32!GetCurrentThread` at `0x14004682b`
- `KERNEL32!GetCurrentThread` at `0x14004682b`
- `RPCRT4!RpcRevertToSelf` at `0x14004687e`
- `RPCRT4!RpcRevertToSelf` at `0x1400468ba`
- `RPCRT4!RpcRevertToSelf` at `0x14004687e`
- `RPCRT4!RpcRevertToSelf` at `0x1400468ba`
- `RPCRT4!RpcImpersonateClient` at `0x1400467f1`
- `RPCRT4!RpcImpersonateClient` at `0x1400467f1`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x1400466ed`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x1400466ed`

## pseudocode

```c
__int64 __fastcall FAX_SetSecurityEx2(__int64 a1, SECURITY_INFORMATION a2, void *a3, ULONG a4)
{
  CMapDeviceId *v7; // rcx
  __int64 v8; // rdx
  int v10; // ebx
  unsigned int v11; // ecx
  unsigned int v12; // eax
  unsigned int v13; // ebx
  CMapDeviceId *v14; // rcx
  __int64 v15; // rdx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  unsigned int v18; // eax
  int ConfigEvent; // eax
  DWORD v20; // eax
  void *TokenHandle; // [rsp+30h] [rbp-48h] BYREF
  int v22; // [rsp+90h] [rbp+18h] BYREF

  v22 = 0;
  TokenHandle = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( !a3 || !a4 )
  {
    if ( v7 == (CMapDeviceId *)&WPP_GLOBAL_Control || (*((_BYTE *)v7 + 28) & 4) == 0 || *((_BYTE *)v7 + 25) < 2u )
      return 87;
    v8 = 56;
    goto LABEL_89;
  }
  if ( (a2 & 0xF) == 0 )
  {
    if ( v7 == (CMapDeviceId *)&WPP_GLOBAL_Control || (*((_BYTE *)v7 + 28) & 4) == 0 || *((_BYTE *)v7 + 25) < 2u )
      return 87;
    v8 = 57;
LABEL_89:
    WPP_SF_(*((_QWORD *)v7 + 2), v8, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
    return 87;
  }
  if ( (a2 & 0xFFFFFFF0) != 0 )
  {
    if ( v7 == (CMapDeviceId *)&WPP_GLOBAL_Control || (*((_BYTE *)v7 + 28) & 4) == 0 || *((_BYTE *)v7 + 25) < 2u )
      return 87;
    v8 = 58;
    goto LABEL_89;
  }
  if ( !RtlValidRelativeSecurityDescriptor(a3, a4, a2) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
    }
    return 13;
  }
  v10 = ((a2 & 1) << 19) | 0x40000;
  if ( (a2 & 6) == 0 )
    v10 = (a2 & 1) << 19;
  EnterCriticalSection(&g_CsSecurity);
  v11 = v10 | 0x1000000;
  if ( (a2 & 8) == 0 )
    v11 = v10;
  v12 = FaxSvcAccessCheck(v11, &v22, 0, 1);
  v13 = v12;
  if ( v12 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_75;
    }
    v15 = 60;
    goto LABEL_32;
  }
  if ( !v22 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
    }
    v13 = 5;
    goto LABEL_75;
  }
  v12 = RpcImpersonateClient(0);
  v13 = v12;
  if ( v12 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_75;
    }
    v15 = 62;
    goto LABEL_32;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, LastError);
    }
    v12 = RpcRevertToSelf();
    if ( !v12 )
      goto LABEL_75;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_75;
    }
    v15 = 64;
    goto LABEL_32;
  }
  v12 = RpcRevertToSelf();
  v13 = v12;
  if ( v12 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_75;
    }
    v15 = 65;
    goto LABEL_32;
  }
  if ( SetPrivateObjectSecurity(a2, a3, &g_pFaxSD, (PGENERIC_MAPPING)&GenericMapping, TokenHandle) )
  {
    v18 = SaveSecurityDescriptor(g_pFaxSD);
    v13 = v18;
    if ( v18 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, v18);
      }
      v13 = 1015;
    }
    else
    {
      ConfigEvent = CreateConfigEvent(5);
      if ( ConfigEvent
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_h(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          68,
          WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids,
          (unsigned __int16)ConfigEvent);
      }
    }
    goto LABEL_75;
  }
  v12 = GetLastError();
  v13 = v12;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = 66;
LABEL_32:
    WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, v12);
  }
LABEL_75:
  LeaveCriticalSection(&g_CsSecurity);
  if ( TokenHandle
    && !CloseHandle(TokenHandle)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v20 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, v20);
  }
  if ( v13 == 8 || v13 == 14 )
    return 7001;
  return v13;
}

```

## disassembly

```asm
0x140046610  mov     rax, rsp
0x140046613  push    rbx
0x140046614  push    rbp
0x140046615  push    rsi
0x140046616  push    r12
0x140046618  push    r13
0x14004661a  push    r14
0x14004661c  sub     rsp, 48h
0x140046620  mov     ebx, r9d
0x140046623  mov     dword ptr [rax+18h], 0
0x14004662a  mov     rbp, r8
0x14004662d  mov     qword ptr [rax-48h], 0
0x140046635  mov     esi, edx
0x140046637  mov     rcx, cs:WPP_GLOBAL_Control
0x14004663e  lea     r12, WPP_GLOBAL_Control
0x140046645  lea     r13, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x14004664c  mov     r14b, 4
0x14004664f  cmp     rcx, r12
0x140046652  jz      short loc_140046678
0x140046654  test    [rcx+1Ch], r14b
0x140046658  jz      short loc_140046678
0x14004665a  cmp     byte ptr [rcx+19h], 5
0x14004665e  jb      short loc_140046678
0x140046660  mov     rcx, [rcx+10h]
0x140046664  mov     edx, 37h ; '7'
0x140046669  mov     r8, r13
0x14004666c  call    WPP_SF_
0x140046671  mov     rcx, cs:WPP_GLOBAL_Control
0x140046678  test    rbp, rbp
0x14004667b  jz      loc_140046A3E
0x140046681  test    ebx, ebx
0x140046683  jz      loc_140046A3E
0x140046689  test    sil, 0Fh
0x14004668d  jnz     short loc_1400466B6
0x14004668f  cmp     rcx, r12
0x140046692  jz      loc_140046A60
0x140046698  test    [rcx+1Ch], r14b
0x14004669c  jz      loc_140046A60
0x1400466a2  cmp     byte ptr [rcx+19h], 2
0x1400466a6  jb      loc_140046A60
0x1400466ac  mov     edx, 39h ; '9'
0x1400466b1  jmp     loc_140046A54
0x1400466b6  test    esi, 0FFFFFFF0h
0x1400466bc  jz      short loc_1400466E5
0x1400466be  cmp     rcx, r12
0x1400466c1  jz      loc_140046A60
0x1400466c7  test    [rcx+1Ch], r14b
0x1400466cb  jz      loc_140046A60
0x1400466d1  cmp     byte ptr [rcx+19h], 2
0x1400466d5  jb      loc_140046A60
0x1400466db  mov     edx, 3Ah ; ':'
0x1400466e0  jmp     loc_140046A54
0x1400466e5  mov     r8d, esi; RequiredInformation
0x1400466e8  mov     edx, ebx; SecurityDescriptorLength
0x1400466ea  mov     rcx, rbp; SecurityDescriptorInput
0x1400466ed  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x1400466f3  test    al, al
0x1400466f5  jnz     short loc_14004672A
0x1400466f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400466fe  cmp     rcx, r12
0x140046701  jz      short loc_140046720
0x140046703  test    [rcx+1Ch], r14b
0x140046707  jz      short loc_140046720
0x140046709  cmp     byte ptr [rcx+19h], 2
0x14004670d  jb      short loc_140046720
0x14004670f  mov     rcx, [rcx+10h]
0x140046713  mov     edx, 3Bh ; ';'
0x140046718  mov     r8, r13
0x14004671b  call    WPP_SF_
0x140046720  mov     eax, 0Dh
0x140046725  jmp     loc_140046A65
0x14004672a  mov     ecx, esi
0x14004672c  and     ecx, 1
0x14004672f  shl     ecx, 13h
0x140046732  mov     ebx, ecx
0x140046734  bts     ebx, 12h
0x140046738  test    sil, 6
0x14004673c  cmovz   ebx, ecx
0x14004673f  lea     rcx, ?g_CsSecurity@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140046746  call    cs:__imp_EnterCriticalSection
0x14004674c  mov     ecx, ebx
0x14004674e  lea     rdx, [rsp+78h+arg_10]; int *
0x140046756  bts     ecx, 18h
0x14004675a  mov     r9d, 1; int
0x140046760  test    sil, 8
0x140046764  cmovz   ecx, ebx; unsigned int
0x140046767  xor     r8d, r8d; unsigned int *
0x14004676a  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x14004676f  mov     ebx, eax
0x140046771  test    eax, eax
0x140046773  jz      short loc_1400467B2
0x140046775  mov     rcx, cs:WPP_GLOBAL_Control
0x14004677c  cmp     rcx, r12
0x14004677f  jz      loc_1400469D1
0x140046785  test    [rcx+1Ch], r14b
0x140046789  jz      loc_1400469D1
0x14004678f  cmp     byte ptr [rcx+19h], 2
0x140046793  jb      loc_1400469D1
0x140046799  mov     edx, 3Ch ; '<'
0x14004679e  mov     rcx, [rcx+10h]
0x1400467a2  mov     r9d, eax
0x1400467a5  mov     r8, r13
0x1400467a8  call    WPP_SF_d
0x1400467ad  jmp     loc_1400469D1
0x1400467b2  cmp     [rsp+78h+arg_10], 0
0x1400467ba  jnz     short loc_1400467EF
0x1400467bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400467c3  cmp     rcx, r12
0x1400467c6  jz      short loc_1400467E5
0x1400467c8  test    [rcx+1Ch], r14b
0x1400467cc  jz      short loc_1400467E5
0x1400467ce  cmp     byte ptr [rcx+19h], 2
0x1400467d2  jb      short loc_1400467E5
0x1400467d4  mov     rcx, [rcx+10h]
0x1400467d8  mov     edx, 3Dh ; '='
0x1400467dd  mov     r8, r13
0x1400467e0  call    WPP_SF_
0x1400467e5  mov     ebx, 5
0x1400467ea  jmp     loc_1400469D1
0x1400467ef  xor     ecx, ecx; BindingHandle
0x1400467f1  call    cs:__imp_RpcImpersonateClient
0x1400467f7  mov     ebx, eax
0x1400467f9  test    eax, eax
0x1400467fb  jz      short loc_14004682B
0x1400467fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140046804  cmp     rcx, r12
0x140046807  jz      loc_1400469D1
0x14004680d  test    [rcx+1Ch], r14b
0x140046811  jz      loc_1400469D1
0x140046817  cmp     byte ptr [rcx+19h], 2
0x14004681b  jb      loc_1400469D1
0x140046821  mov     edx, 3Eh ; '>'
0x140046826  jmp     loc_14004679E
0x14004682b  call    cs:__imp_GetCurrentThread
0x140046831  xor     r8d, r8d; OpenAsSelf
0x140046834  lea     r9, [rsp+78h+TokenHandle]; TokenHandle
0x140046839  mov     rcx, rax; ThreadHandle
0x14004683c  lea     edx, [r8+8]; DesiredAccess
0x140046840  call    cs:__imp_OpenThreadToken
0x140046846  test    eax, eax
0x140046848  jnz     short loc_1400468BA
0x14004684a  call    cs:__imp_GetLastError
0x140046850  mov     ebx, eax
0x140046852  mov     rcx, cs:WPP_GLOBAL_Control
0x140046859  cmp     rcx, r12
0x14004685c  jz      short loc_14004687E
0x14004685e  test    [rcx+1Ch], r14b
0x140046862  jz      short loc_14004687E
0x140046864  cmp     byte ptr [rcx+19h], 2
0x140046868  jb      short loc_14004687E
0x14004686a  mov     rcx, [rcx+10h]
0x14004686e  mov     edx, 3Fh ; '?'
0x140046873  mov     r9d, eax
0x140046876  mov     r8, r13
0x140046879  call    WPP_SF_d
0x14004687e  call    cs:__imp_RpcRevertToSelf
0x140046884  test    eax, eax
0x140046886  jz      loc_1400469D1
0x14004688c  mov     rcx, cs:WPP_GLOBAL_Control
0x140046893  cmp     rcx, r12
0x140046896  jz      loc_1400469D1
0x14004689c  test    [rcx+1Ch], r14b
0x1400468a0  jz      loc_1400469D1
0x1400468a6  cmp     byte ptr [rcx+19h], 2
0x1400468aa  jb      loc_1400469D1
0x1400468b0  mov     edx, 40h ; '@'
0x1400468b5  jmp     loc_14004679E
0x1400468ba  call    cs:__imp_RpcRevertToSelf
0x1400468c0  mov     ebx, eax
0x1400468c2  test    eax, eax
0x1400468c4  jz      short loc_1400468F4
0x1400468c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400468cd  cmp     rcx, r12
0x1400468d0  jz      loc_1400469D1
0x1400468d6  test    [rcx+1Ch], r14b
0x1400468da  jz      loc_1400469D1
0x1400468e0  cmp     byte ptr [rcx+19h], 2
0x1400468e4  jb      loc_1400469D1
0x1400468ea  mov     edx, 41h ; 'A'
0x1400468ef  jmp     loc_14004679E
0x1400468f4  mov     rax, [rsp+78h+TokenHandle]
0x1400468f9  lea     r9, GenericMapping; GenericMapping
0x140046900  lea     r8, ?g_pFaxSD@@3PEAXEA; ObjectsSecurityDescriptor
0x140046907  mov     [rsp+78h+Token], rax; Token
0x14004690c  mov     rdx, rbp; ModificationDescriptor
0x14004690f  mov     ecx, esi; SecurityInformation
0x140046911  call    cs:__imp_SetPrivateObjectSecurity
0x140046917  test    eax, eax
0x140046919  jnz     short loc_140046951
0x14004691b  call    cs:__imp_GetLastError
0x140046921  mov     ebx, eax
0x140046923  mov     rcx, cs:WPP_GLOBAL_Control
0x14004692a  cmp     rcx, r12
0x14004692d  jz      loc_1400469D1
0x140046933  test    [rcx+1Ch], r14b
0x140046937  jz      loc_1400469D1
0x14004693d  cmp     byte ptr [rcx+19h], 2
0x140046941  jb      loc_1400469D1
0x140046947  mov     edx, 42h ; 'B'
0x14004694c  jmp     loc_14004679E
0x140046951  mov     rcx, cs:?g_pFaxSD@@3PEAXEA; pAbsoluteSecurityDescriptor
0x140046958  call    ?SaveSecurityDescriptor@@YAKPEAX@Z; SaveSecurityDescriptor(void *)
0x14004695d  mov     ebx, eax
0x14004695f  test    eax, eax
0x140046961  jz      short loc_140046996
0x140046963  mov     rcx, cs:WPP_GLOBAL_Control
0x14004696a  cmp     rcx, r12
0x14004696d  jz      short loc_14004698F
0x14004696f  test    [rcx+1Ch], r14b
0x140046973  jz      short loc_14004698F
0x140046975  cmp     byte ptr [rcx+19h], 2
0x140046979  jb      short loc_14004698F
0x14004697b  mov     rcx, [rcx+10h]
0x14004697f  mov     edx, 43h ; 'C'
0x140046984  mov     r9d, eax
0x140046987  mov     r8, r13
0x14004698a  call    WPP_SF_d
0x14004698f  mov     ebx, 3F7h
0x140046994  jmp     short loc_1400469D1
0x140046996  mov     ecx, 5
0x14004699b  call    ?CreateConfigEvent@@YAKW4FAX_ENUM_CONFIG_TYPE@@@Z; CreateConfigEvent(FAX_ENUM_CONFIG_TYPE)
0x1400469a0  test    eax, eax
0x1400469a2  jz      short loc_1400469D1
0x1400469a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400469ab  cmp     rcx, r12
0x1400469ae  jz      short loc_1400469D1
0x1400469b0  test    [rcx+1Ch], r14b
0x1400469b4  jz      short loc_1400469D1
0x1400469b6  cmp     byte ptr [rcx+19h], 2
0x1400469ba  jb      short loc_1400469D1
0x1400469bc  mov     rcx, [rcx+10h]
0x1400469c0  movzx   r9d, ax
0x1400469c4  mov     edx, 44h ; 'D'
0x1400469c9  mov     r8, r13
0x1400469cc  call    WPP_SF_h
0x1400469d1  lea     rcx, ?g_CsSecurity@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400469d8  call    cs:__imp_LeaveCriticalSection
0x1400469de  mov     rcx, [rsp+78h+TokenHandle]; hObject
0x1400469e3  test    rcx, rcx
0x1400469e6  jz      short loc_140046A2B
0x1400469e8  call    cs:__imp_CloseHandle
0x1400469ee  test    eax, eax
0x1400469f0  jnz     short loc_140046A2B
0x1400469f2  mov     rax, cs:WPP_GLOBAL_Control
0x1400469f9  cmp     rax, r12
0x1400469fc  jz      short loc_140046A2B
0x1400469fe  test    [rax+1Ch], r14b
0x140046a02  jz      short loc_140046A2B
0x140046a04  cmp     byte ptr [rax+19h], 2
0x140046a08  jb      short loc_140046A2B
0x140046a0a  call    cs:__imp_GetLastError
0x140046a10  mov     rcx, cs:WPP_GLOBAL_Control
0x140046a17  mov     edx, 45h ; 'E'
0x140046a1c  mov     r9d, eax
0x140046a1f  mov     r8, r13
0x140046a22  mov     rcx, [rcx+10h]
0x140046a26  call    WPP_SF_d
0x140046a2b  cmp     ebx, 8
0x140046a2e  jz      short loc_140046A35
0x140046a30  cmp     ebx, 0Eh
0x140046a33  jnz     short loc_140046A3A
0x140046a35  mov     ebx, 1B59h
0x140046a3a  mov     eax, ebx
0x140046a3c  jmp     short loc_140046A65
0x140046a3e  cmp     rcx, r12
0x140046a41  jz      short loc_140046A60
0x140046a43  test    [rcx+1Ch], r14b
0x140046a47  jz      short loc_140046A60
0x140046a49  cmp     byte ptr [rcx+19h], 2
0x140046a4d  jb      short loc_140046A60
0x140046a4f  mov     edx, 38h ; '8'
0x140046a54  mov     rcx, [rcx+10h]
0x140046a58  mov     r8, r13
0x140046a5b  call    WPP_SF_
0x140046a60  mov     eax, 57h ; 'W'
0x140046a65  add     rsp, 48h
0x140046a69  pop     r14
0x140046a6b  pop     r13
0x140046a6d  pop     r12
0x140046a6f  pop     rsi
0x140046a70  pop     rbp
0x140046a71  pop     rbx
0x140046a72  retn
```
