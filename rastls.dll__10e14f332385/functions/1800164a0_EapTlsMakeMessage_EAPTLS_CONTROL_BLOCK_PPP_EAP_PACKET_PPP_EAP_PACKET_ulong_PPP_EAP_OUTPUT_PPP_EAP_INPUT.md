# EapTlsMakeMessage(_EAPTLS_CONTROL_BLOCK *,_PPP_EAP_PACKET *,_PPP_EAP_PACKET *,ulong,_PPP_EAP_OUTPUT *,_PPP_EAP_INPUT *)

- ea: `0x1800164a0`
- end: `0x18001685e`
- name: `?EapTlsMakeMessage@@YAKPEAU_EAPTLS_CONTROL_BLOCK@@PEAU_PPP_EAP_PACKET@@1KPEAU_PPP_EAP_OUTPUT@@PEAU_PPP_EAP_INPUT@@@Z`
- size: `958`
- prototype: `__int64 __fastcall(struct _EAPTLS_CONTROL_BLOCK *, struct _PPP_EAP_PACKET *, struct _PPP_EAP_PACKET *, unsigned int, struct _PPP_EAP_OUTPUT *, struct _PPP_EAP_INPUT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180059b50`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18000f350`
- `0x1800164a0`
- `0x180016870`
- `0x180016a00`
- `0x18004f508`
- `0x180050ef0`
- `0x18005aa28`
- `0x18006e508`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800166d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016701`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001678e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001681c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800166d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016701`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001678e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001681c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800166f7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001677b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800166f7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001677b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180016801`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180016801`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800166c6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800166c6`
- `eapputil!EapConvertWireToHostFormat32` at `0x1800165bb`
- `eapputil!EapConvertWireToHostFormat32` at `0x1800165bb`
- `eapputil!EapConvertWireToHostFormat16` at `0x180016556`
- `eapputil!EapConvertWireToHostFormat16` at `0x180016556`

## pseudocode

```c
__int64 __fastcall EapTlsMakeMessage(
        struct _EAPTLS_CONTROL_BLOCK *a1,
        struct _PPP_EAP_PACKET *a2,
        struct _PPP_EAP_PACKET *a3,
        unsigned int a4,
        struct _PPP_EAP_OUTPUT *a5,
        struct _PPP_EAP_INPUT *a6)
{
  const WCHAR *v10; // r9
  BYTE Code; // r15
  BYTE v12; // al
  int v13; // edx
  int v14; // r8d
  int v15; // eax
  char v16; // al
  const char *v17; // rdi
  const char *v18; // r11
  const char *v19; // rax
  int v21; // eax
  int v22; // r15d
  int v23; // edi
  void *v24; // rcx
  DWORD LastError; // edi
  __int64 v26; // r8
  struct _EAPTLS_CONTROL_BLOCK *v27; // rcx
  __int64 v28; // rdx
  DWORD v29; // eax
  __int64 v30; // rdx
  struct _PPP_EAP_INPUT *v31; // [rsp+28h] [rbp-90h]
  int v32; // [rsp+70h] [rbp-48h]
  char v33; // [rsp+74h] [rbp-44h]
  char v34; // [rsp+78h] [rbp-40h]
  char v35; // [rsp+C0h] [rbp+8h]
  int v36; // [rsp+C8h] [rbp+10h]
  int v37; // [rsp+D0h] [rbp+18h]

  if ( a1 && a5 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v10 = &String;
      if ( a1 != (struct _EAPTLS_CONTROL_BLOCK *)-16LL )
        v10 = (const WCHAR *)((char *)a1 + 16);
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v10);
    }
    if ( a2 )
    {
      Code = 0;
      v34 = 0;
      v33 = 0;
      if ( a2->Code <= 4u )
        Code = a2->Code;
      v35 = EapConvertWireToHostFormat16(a2->Length);
      if ( (unsigned int)FValidPacket((struct _EAPTLS_PACKET *)a2)
        && (unsigned __int8)(a2->Code - 1) <= 1u
        && a2->Data[0] == 13 )
      {
        v12 = a2[1].Code;
        v34 = 13;
        v13 = v12 & 0x80;
        v14 = v12 & 0x40;
        v37 = v13;
        v15 = v12 & 0x20;
        v32 = v14;
        v36 = a2[1].Code & 0x20;
        if ( v13 )
        {
          v16 = EapConvertWireToHostFormat32(&a2[1].Id);
          v13 = v37;
          v14 = v32;
          v33 = v16;
          v15 = v36;
        }
      }
      else
      {
        v15 = 0;
        v13 = 0;
        v14 = 0;
      }
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v17 = "S";
        if ( !v15 )
          v17 = (const char *)&dword_180081A9C;
        v18 = "M";
        v19 = "L";
        if ( !v14 )
          v18 = (const char *)&dword_180081A9C;
        if ( !v13 )
          v19 = (const char *)&dword_180081A9C;
        WPP_SF_ssdddddsss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (__int64)off_18007E2B0[Code],
          a2->Code,
          a2->Id,
          v35,
          v34,
          v33,
          (__int64)v19,
          (__int64)v18,
          (__int64)v17);
      }
    }
    if ( !(unsigned int)FValidPacket((struct _EAPTLS_PACKET *)a2) )
    {
      a5->Action = EAPACTION_NoAction;
      return 722;
    }
    v21 = *((_DWORD *)a1 + 1);
    v22 = v21 & 2;
    v23 = v21 & 1;
    if ( (v21 & 1) == 0 && (v21 & 2) == 0 && (v21 & 0x4C04) == 0 )
    {
      v24 = (void *)*((_QWORD *)a1 + 1);
      if ( v24 )
      {
        if ( !ImpersonateLoggedOnUser(v24) )
        {
          LastError = GetLastError();
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          {
            v28 = 67;
LABEL_37:
            WPP_SF_qD(*((_QWORD *)v27 + 2), v28, v26, *((_QWORD *)a1 + 1), LastError);
            goto LABEL_38;
          }
          goto LABEL_38;
        }
      }
    }
    if ( (*((_BYTE *)a1 + 4) & 4) != 0 && !SetThreadToken(0, *((HANDLE *)a1 + 1)) )
    {
      LastError = GetLastError();
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v28 = 68;
        goto LABEL_37;
      }
LABEL_38:
      a5->Action = EAPACTION_NoAction;
      return LastError;
    }
    if ( v23 )
    {
      LastError = EapTlsSMakeMessage(a1, (struct _EAPTLS_PACKET *)a2, (struct _EAPTLS_PACKET *)a3, a4, a5, v31);
    }
    else
    {
      LastError = EapTlsCMakeMessage(a1, (struct _EAPTLS_PACKET *)a2, (struct _EAPTLS_PACKET *)a3, a4, a5, a6);
      if ( *(_QWORD *)&a5->Action == 2 && (*((_DWORD *)a1 + 1) & 0x2000) == 0 )
        SetCachedCredentials(a1);
      if ( !v22 )
      {
        if ( (*((_BYTE *)a1 + 4) & 4) != 0 )
        {
LABEL_43:
          if ( SetThreadToken(0, 0) || WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            return LastError;
          v29 = GetLastError();
          v30 = 70;
LABEL_46:
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v29);
          return LastError;
        }
        if ( !RevertToSelf() )
        {
          if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            return LastError;
          v29 = GetLastError();
          v30 = 69;
          goto LABEL_46;
        }
      }
    }
    if ( (*((_BYTE *)a1 + 4) & 4) == 0 )
      return LastError;
    goto LABEL_43;
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
  return 87;
}

```

## disassembly

```asm
0x1800164a0  push    rbx
0x1800164a2  push    rbp
0x1800164a3  push    rsi
0x1800164a4  push    r12
0x1800164a6  push    r13
0x1800164a8  push    r14
0x1800164aa  sub     rsp, 88h
0x1800164b1  mov     r12d, r9d
0x1800164b4  mov     r13, r8
0x1800164b7  mov     r14, rdx
0x1800164ba  mov     rbx, rcx
0x1800164bd  test    rcx, rcx
0x1800164c0  jz      loc_18001682C
0x1800164c6  mov     rsi, [rsp+0B8h+arg_20]
0x1800164ce  test    rsi, rsi
0x1800164d1  jz      loc_18001682C
0x1800164d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800164de  lea     rbp, WPP_GLOBAL_Control
0x1800164e5  cmp     rcx, rbp
0x1800164e8  jz      short loc_180016511
0x1800164ea  mov     rcx, [rcx+10h]
0x1800164ee  lea     rax, [rbx+10h]
0x1800164f2  test    rax, rax
0x1800164f5  lea     r9, String
0x1800164fc  mov     edx, 42h ; 'B'
0x180016501  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180016508  cmovnz  r9, rax
0x18001650c  call    WPP_SF_S
0x180016511  mov     [rsp+0B8h+arg_18], rdi
0x180016519  mov     [rsp+0B8h+var_38], r15
0x180016521  test    r14, r14
0x180016524  jz      loc_180016687
0x18001652a  movzx   eax, byte ptr [r14]
0x18001652e  lea     rcx, [r14+2]
0x180016532  xor     r15d, r15d
0x180016535  mov     [rsp+0B8h+arg_8], 0
0x180016540  cmp     al, 4
0x180016542  mov     dword ptr [rsp+0B8h+var_40], 0
0x18001654a  mov     dword ptr [rsp+0B8h+var_44], 0
0x180016552  cmovbe  r15d, eax
0x180016556  call    cs:__imp_EapConvertWireToHostFormat16
0x18001655c  mov     rcx, r14; struct _EAPTLS_PACKET *
0x18001655f  mov     [rsp+0B8h+arg_0], ax
0x180016567  call    ?FValidPacket@@YAHPEAU_EAPTLS_PACKET@@@Z; FValidPacket(_EAPTLS_PACKET *)
0x18001656c  test    eax, eax
0x18001656e  jz      short loc_1800165DA
0x180016570  movzx   eax, byte ptr [r14]
0x180016574  dec     al
0x180016576  cmp     al, 1
0x180016578  ja      short loc_1800165DA
0x18001657a  cmp     byte ptr [r14+4], 0Dh
0x18001657f  jnz     short loc_1800165DA
0x180016581  movzx   eax, byte ptr [r14+5]
0x180016586  mov     edx, eax
0x180016588  mov     dword ptr [rsp+0B8h+var_40], 0Dh
0x180016590  mov     r8d, eax
0x180016593  and     edx, 80h
0x180016599  and     r8d, 40h
0x18001659d  mov     [rsp+0B8h+arg_10], edx
0x1800165a4  and     eax, 20h
0x1800165a7  mov     [rsp+0B8h+var_48], r8d
0x1800165ac  mov     [rsp+0B8h+arg_8], eax
0x1800165b3  test    edx, edx
0x1800165b5  jz      short loc_1800165E6
0x1800165b7  lea     rcx, [r14+6]
0x1800165bb  call    cs:__imp_EapConvertWireToHostFormat32
0x1800165c1  mov     edx, [rsp+0B8h+arg_10]
0x1800165c8  mov     r8d, [rsp+0B8h+var_48]
0x1800165cd  mov     dword ptr [rsp+0B8h+var_44], eax
0x1800165d1  mov     eax, [rsp+0B8h+arg_8]
0x1800165d8  jmp     short loc_1800165E6
0x1800165da  mov     eax, [rsp+0B8h+arg_8]
0x1800165e1  mov     edx, eax
0x1800165e3  mov     r8d, eax
0x1800165e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800165ed  cmp     rcx, rbp
0x1800165f0  jz      loc_180016687
0x1800165f6  mov     rcx, [rcx+10h]; LoggerHandle
0x1800165fa  lea     r9, dword_180081A9C
0x180016601  test    eax, eax
0x180016603  movzx   r10d, r15b
0x180016607  lea     rdi, aS; "S"
0x18001660e  cmovz   rdi, r9
0x180016612  lea     r11, aM; "M"
0x180016619  mov     [rsp+0B8h+var_58], rdi; __int64
0x18001661e  lea     rax, asc_180081A88; "L"
0x180016625  test    r8d, r8d
0x180016628  lea     r15, off_18007E2B0; "Unknown"
0x18001662f  movzx   r8d, byte ptr [r14+1]
0x180016634  cmovz   r11, r9
0x180016638  test    edx, edx
0x18001663a  movzx   edx, [rsp+0B8h+arg_0]
0x180016642  mov     [rsp+0B8h+var_60], r11; __int64
0x180016647  cmovz   rax, r9
0x18001664b  movzx   r9d, byte ptr [r14]
0x18001664f  mov     [rsp+0B8h+var_68], rax; __int64
0x180016654  mov     eax, dword ptr [rsp+0B8h+var_44]
0x180016658  mov     dword ptr [rsp+0B8h+var_70], eax; char
0x18001665c  mov     eax, dword ptr [rsp+0B8h+var_40]
0x180016660  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x180016664  mov     rax, [r15+r10*8]
0x180016668  mov     dword ptr [rsp+0B8h+var_80], edx; char
0x18001666c  mov     dword ptr [rsp+0B8h+var_88], r8d; char
0x180016671  mov     dword ptr [rsp+0B8h+var_90], r9d; struct _PPP_EAP_INPUT *
0x180016676  lea     r9, aReceived; ">> Received"
0x18001667d  mov     [rsp+0B8h+var_98], rax; __int64
0x180016682  call    WPP_SF_ssdddddsss
0x180016687  mov     rcx, r14; struct _EAPTLS_PACKET *
0x18001668a  call    ?FValidPacket@@YAHPEAU_EAPTLS_PACKET@@@Z; FValidPacket(_EAPTLS_PACKET *)
0x18001668f  test    eax, eax
0x180016691  jnz     short loc_1800166A0
0x180016693  mov     [rsi+4], eax
0x180016696  mov     eax, 2D2h
0x18001669b  jmp     loc_180016734
0x1800166a0  mov     eax, [rbx+4]
0x1800166a3  mov     r15d, eax
0x1800166a6  and     r15d, 2
0x1800166aa  mov     edi, eax
0x1800166ac  and     edi, 1
0x1800166af  jnz     short loc_1800166EB
0x1800166b1  test    r15d, r15d
0x1800166b4  jnz     short loc_1800166EB
0x1800166b6  test    eax, 4C04h
0x1800166bb  jnz     short loc_1800166EB
0x1800166bd  mov     rcx, [rbx+8]; hToken
0x1800166c1  test    rcx, rcx
0x1800166c4  jz      short loc_1800166EB
0x1800166c6  call    cs:__imp_ImpersonateLoggedOnUser
0x1800166cc  test    eax, eax
0x1800166ce  jnz     short loc_1800166EB
0x1800166d0  call    cs:__imp_GetLastError
0x1800166d6  mov     edi, eax
0x1800166d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800166df  cmp     rcx, rbp
0x1800166e2  jz      short loc_18001672B
0x1800166e4  mov     edx, 43h ; 'C'
0x1800166e9  jmp     short loc_18001671A
0x1800166eb  test    byte ptr [rbx+4], 4
0x1800166ef  jz      short loc_180016755
0x1800166f1  mov     rdx, [rbx+8]; Token
0x1800166f5  xor     ecx, ecx; Thread
0x1800166f7  call    cs:__imp_SetThreadToken
0x1800166fd  test    eax, eax
0x1800166ff  jnz     short loc_180016755
0x180016701  call    cs:__imp_GetLastError
0x180016707  mov     edi, eax
0x180016709  mov     rcx, cs:WPP_GLOBAL_Control
0x180016710  cmp     rcx, rbp
0x180016713  jz      short loc_18001672B
0x180016715  mov     edx, 44h ; 'D'
0x18001671a  mov     r9, [rbx+8]
0x18001671e  mov     rcx, [rcx+10h]
0x180016722  mov     dword ptr [rsp+0B8h+var_98], edi
0x180016726  call    WPP_SF_qD
0x18001672b  mov     dword ptr [rsi+4], 0
0x180016732  mov     eax, edi
0x180016734  mov     rdi, [rsp+0B8h+arg_18]
0x18001673c  mov     r15, [rsp+0B8h+var_38]
0x180016744  add     rsp, 88h
0x18001674b  pop     r14
0x18001674d  pop     r13
0x18001674f  pop     r12
0x180016751  pop     rsi
0x180016752  pop     rbp
0x180016753  pop     rbx
0x180016754  retn
0x180016755  mov     r9d, r12d; unsigned int
0x180016758  mov     r8, r13; struct _EAPTLS_PACKET *
0x18001675b  mov     rdx, r14; struct _EAPTLS_PACKET *
0x18001675e  mov     rcx, rbx; struct _EAPTLS_CONTROL_BLOCK *
0x180016761  test    edi, edi
0x180016763  jz      short loc_1800167B8
0x180016765  mov     [rsp+0B8h+var_98], rsi; struct _PPP_EAP_OUTPUT *
0x18001676a  call    ?EapTlsSMakeMessage@@YAKPEAU_EAPTLS_CONTROL_BLOCK@@PEAU_EAPTLS_PACKET@@1KPEAU_PPP_EAP_OUTPUT@@PEAU_PPP_EAP_INPUT@@@Z; EapTlsSMakeMessage(_EAPTLS_CONTROL_BLOCK *,_EAPTLS_PACKET *,_EAPTLS_PACKET *,ulong,_PPP_EAP_OUTPUT *,_PPP_EAP_INPUT *)
0x18001676f  mov     edi, eax
0x180016771  test    byte ptr [rbx+4], 4
0x180016775  jz      short loc_180016732
0x180016777  xor     edx, edx; Token
0x180016779  xor     ecx, ecx; Thread
0x18001677b  call    cs:__imp_SetThreadToken
0x180016781  test    eax, eax
0x180016783  jnz     short loc_180016732
0x180016785  cmp     cs:WPP_GLOBAL_Control, rbp
0x18001678c  jz      short loc_180016732
0x18001678e  call    cs:__imp_GetLastError
0x180016794  mov     edx, 46h ; 'F'
0x180016799  mov     rcx, cs:WPP_GLOBAL_Control
0x1800167a0  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x1800167a7  mov     r9d, eax
0x1800167aa  mov     rcx, [rcx+10h]
0x1800167ae  call    WPP_SF_d
0x1800167b3  jmp     loc_180016732
0x1800167b8  mov     rax, [rsp+0B8h+arg_28]
0x1800167c0  mov     [rsp+0B8h+var_90], rax; struct _PPP_EAP_INPUT *
0x1800167c5  mov     [rsp+0B8h+var_98], rsi; struct _PPP_EAP_OUTPUT *
0x1800167ca  call    ?EapTlsCMakeMessage@@YAKPEAU_EAPTLS_CONTROL_BLOCK@@PEAU_EAPTLS_PACKET@@1KPEAU_PPP_EAP_OUTPUT@@PEAU_PPP_EAP_INPUT@@@Z; EapTlsCMakeMessage(_EAPTLS_CONTROL_BLOCK *,_EAPTLS_PACKET *,_EAPTLS_PACKET *,ulong,_PPP_EAP_OUTPUT *,_PPP_EAP_INPUT *)
0x1800167cf  cmp     dword ptr [rsi+4], 2
0x1800167d3  mov     edi, eax
0x1800167d5  jnz     short loc_1800167EE
0x1800167d7  cmp     dword ptr [rsi+8], 0
0x1800167db  jnz     short loc_1800167EE
0x1800167dd  test    dword ptr [rbx+4], 2000h
0x1800167e4  jnz     short loc_1800167EE
0x1800167e6  mov     rcx, rbx; struct _EAPTLS_CONTROL_BLOCK *
0x1800167e9  call    ?SetCachedCredentials@@YAXPEAU_EAPTLS_CONTROL_BLOCK@@@Z; SetCachedCredentials(_EAPTLS_CONTROL_BLOCK *)
0x1800167ee  test    r15d, r15d
0x1800167f1  jnz     loc_180016771
0x1800167f7  test    byte ptr [rbx+4], 4
0x1800167fb  jnz     loc_180016777
0x180016801  call    cs:__imp_RevertToSelf
0x180016807  test    eax, eax
0x180016809  jnz     loc_180016771
0x18001680f  cmp     cs:WPP_GLOBAL_Control, rbp
0x180016816  jz      loc_180016732
0x18001681c  call    cs:__imp_GetLastError
0x180016822  mov     edx, 45h ; 'E'
0x180016827  jmp     loc_180016799
0x18001682c  mov     rcx, cs:WPP_GLOBAL_Control
0x180016833  lea     rbp, WPP_GLOBAL_Control
0x18001683a  cmp     rcx, rbp
0x18001683d  jz      short loc_180016854
0x18001683f  mov     rcx, [rcx+10h]
0x180016843  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18001684a  mov     edx, 41h ; 'A'
0x18001684f  call    WPP_SF_
0x180016854  mov     eax, 57h ; 'W'
0x180016859  jmp     loc_180016744
```
