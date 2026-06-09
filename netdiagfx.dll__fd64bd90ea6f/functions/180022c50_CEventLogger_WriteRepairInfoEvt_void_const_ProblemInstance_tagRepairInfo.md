# CEventLogger::WriteRepairInfoEvt(void const *,ProblemInstance *,tagRepairInfo *)

- ea: `0x180022c50`
- end: `0x180022f50`
- name: `?WriteRepairInfoEvt@CEventLogger@@EEAAJPEBXPEAVProblemInstance@@PEAUtagRepairInfo@@@Z`
- size: `768`
- prototype: `int(CEventLogger *__hidden this, const void *, struct ProblemInstance *, struct tagRepairInfo *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800218e8`
- `0x180022c50`
- `0x18002b928`
- `0x18002ba00`
- `0x18002bc48`
- `0x18002c2fc`
- `0x18002c802`
- `0x18002c840`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x180022efd`
- `ADVAPI32!EventWrite` at `0x180022efd`
- `ADVAPI32!EventEnabled` at `0x180022c94`
- `ADVAPI32!EventEnabled` at `0x180022c94`
- `IPHLPAPI!ConvertInterfaceLuidToAlias` at `0x180022ead`
- `IPHLPAPI!ConvertInterfaceLuidToAlias` at `0x180022ead`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180022e94`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180022e94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022f08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022f11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022f08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022f11`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CEventLogger::WriteRepairInfoEvt(
        CEventLogger *this,
        const EVENT_DESCRIPTOR *a2,
        struct ProblemInstance *a3,
        struct tagRepairInfo *a4)
{
  signed int v6; // ebx
  __int64 v7; // rcx
  const unsigned __int16 *v8; // rbx
  void *Value; // r12
  int v10; // r14d
  __int64 v11; // rdi
  int ReplacedText; // eax
  __int64 v13; // rax
  ULONG v14; // eax
  const unsigned __int16 *pwszDescription; // rbx
  void *v16; // r15
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  const unsigned __int16 *v20; // rax
  __int64 v21; // rcx
  NET_LUID InterfaceLuid; // [rsp+20h] [rbp-E0h] BYREF
  DiagnosisTextParserImpl *v24; // [rsp+28h] [rbp-D8h] BYREF
  int cost; // [rsp+30h] [rbp-D0h] BYREF
  DWORD sidType; // [rsp+34h] [rbp-CCh] BYREF
  PCEVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-C8h]
  GUID InterfaceGuid; // [rsp+40h] [rbp-C0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-B0h] BYREF
  char *v30; // [rsp+60h] [rbp-A0h]
  __int64 v31; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v32; // [rsp+70h] [rbp-90h]
  int v33; // [rsp+78h] [rbp-88h]
  int v34; // [rsp+7Ch] [rbp-84h]
  struct tagRepairInfo *v35; // [rsp+80h] [rbp-80h]
  __int64 v36; // [rsp+88h] [rbp-78h]
  int *p_cost; // [rsp+90h] [rbp-70h]
  __int64 v38; // [rsp+98h] [rbp-68h]
  DWORD *p_sidType; // [rsp+A0h] [rbp-60h]
  __int64 v40; // [rsp+A8h] [rbp-58h]
  const unsigned __int16 *v41; // [rsp+B0h] [rbp-50h]
  int v42; // [rsp+B8h] [rbp-48h]
  int v43; // [rsp+BCh] [rbp-44h]
  WCHAR *v44; // [rsp+C0h] [rbp-40h]
  int v45; // [rsp+C8h] [rbp-38h]
  int v46; // [rsp+CCh] [rbp-34h]
  GUID *p_InterfaceGuid; // [rsp+D0h] [rbp-30h]
  __int64 v48; // [rsp+D8h] [rbp-28h]
  WCHAR InterfaceAlias[264]; // [rsp+E0h] [rbp-20h] BYREF

  EventDescriptor = a2;
  v6 = 0;
  if ( EventEnabled(NETDIAG_EVT_GUID_Context, a2) )
  {
    v7 = 80;
    if ( *((_DWORD *)a3 + 24) < *((_DWORD *)a3 + 25) )
      v7 = 88;
    v8 = *(const unsigned __int16 **)((char *)a3 + v7);
    Value = 0;
    InterfaceLuid.Value = 0;
    v10 = 2;
    v11 = -1;
    if ( !v8 )
      goto LABEL_12;
    DiagnosisTextParser::DiagnosisTextParser((DiagnosisTextParser *)&v24);
    if ( !(unsigned int)DiagnosisTextParser::SetXML((DiagnosisTextParser *)&v24, v8) )
    {
      ReplacedText = DiagnosisTextParser::GetReplacedText(&v24, (unsigned __int16 **)&InterfaceLuid);
      Value = (void *)InterfaceLuid.Value;
      if ( ReplacedText >= 0 )
        v8 = (const unsigned __int16 *)InterfaceLuid.Value;
    }
    DiagnosisTextParser::~DiagnosisTextParser((DiagnosisTextParser *)&v24);
    if ( v8 )
    {
      v13 = -1;
      do
        ++v13;
      while ( v8[v13] );
      v14 = 2 * v13 + 2;
    }
    else
    {
LABEL_12:
      v8 = &dword_180033E1C;
      v14 = 2;
    }
    UserData.Ptr = (ULONGLONG)v8;
    UserData.Size = v14;
    UserData.Reserved = 0;
    v30 = (char *)a3 + 256;
    v31 = 16;
    pwszDescription = a4->pwszDescription;
    v16 = 0;
    InterfaceLuid.Value = 0;
    if ( !pwszDescription )
      goto LABEL_21;
    DiagnosisTextParser::DiagnosisTextParser((DiagnosisTextParser *)&v24);
    if ( !(unsigned int)DiagnosisTextParser::SetXML((DiagnosisTextParser *)&v24, pwszDescription) )
    {
      v17 = DiagnosisTextParser::GetReplacedText(&v24, (unsigned __int16 **)&InterfaceLuid);
      v16 = (void *)InterfaceLuid.Value;
      if ( v17 >= 0 )
        pwszDescription = (const unsigned __int16 *)InterfaceLuid.Value;
    }
    DiagnosisTextParser::~DiagnosisTextParser((DiagnosisTextParser *)&v24);
    if ( pwszDescription )
    {
      v18 = -1;
      do
        ++v18;
      while ( pwszDescription[v18] );
      v19 = 2 * v18 + 2;
    }
    else
    {
LABEL_21:
      pwszDescription = &dword_180033E1C;
      v19 = 2;
    }
    v32 = pwszDescription;
    v33 = v19;
    v34 = 0;
    v35 = a4;
    v36 = 16;
    cost = a4->cost;
    p_cost = &cost;
    v38 = 4;
    sidType = a4->sidType;
    p_sidType = &sidType;
    v40 = 4;
    v20 = (const unsigned __int16 *)*((_QWORD *)a3 + 2);
    if ( !*((_DWORD *)v20 - 4) )
      v20 = *(const unsigned __int16 **)a3;
    if ( v20 )
    {
      v21 = -1;
      do
        ++v21;
      while ( v20[v21] );
      v10 = 2 * v21 + 2;
    }
    else
    {
      v20 = &dword_180033E1C;
    }
    v41 = v20;
    v42 = v10;
    v43 = 0;
    InterfaceGuid = 0;
    memset_0(InterfaceAlias, 0, 0x202u);
    if ( GetAdapterGUID(a3, &InterfaceGuid) )
    {
      InterfaceLuid.Value = 0;
      if ( !ConvertInterfaceGuidToLuid(&InterfaceGuid, &InterfaceLuid) )
        ConvertInterfaceLuidToAlias(&InterfaceLuid, InterfaceAlias, 0x101u);
    }
    v44 = InterfaceAlias;
    do
      ++v11;
    while ( InterfaceAlias[v11] );
    v45 = 2 * v11 + 2;
    v46 = 0;
    p_InterfaceGuid = &InterfaceGuid;
    v48 = 16;
    v6 = EventWrite(NETDIAG_EVT_GUID_Context, EventDescriptor, 9u, &UserData);
    CoTaskMemFree(Value);
    CoTaskMemFree(v16);
    if ( v6 > 0 )
      return (unsigned __int16)v6 | 0x80070000;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180022c50  mov     [rsp-8+arg_0], rbx
0x180022c55  push    rbp
0x180022c56  push    rsi
0x180022c57  push    rdi
0x180022c58  push    r12
0x180022c5a  push    r13
0x180022c5c  push    r14
0x180022c5e  push    r15
0x180022c60  lea     rbp, [rsp-200h]
0x180022c68  sub     rsp, 300h
0x180022c6f  mov     rax, cs:__security_cookie
0x180022c76  xor     rax, rsp
0x180022c79  mov     [rbp+230h+var_40], rax
0x180022c80  mov     r13, r9
0x180022c83  mov     rsi, r8
0x180022c86  mov     [rsp+330h+EventDescriptor], rdx
0x180022c8b  xor     ebx, ebx
0x180022c8d  mov     rcx, cs:NETDIAG_EVT_GUID_Context; RegHandle
0x180022c94  call    cs:__imp_EventEnabled
0x180022c9a  xor     r8d, r8d
0x180022c9d  test    al, al
0x180022c9f  jz      loc_180022F24
0x180022ca5  lea     ecx, [rbx+50h]
0x180022ca8  lea     edx, [rbx+58h]
0x180022cab  mov     eax, [rsi+64h]
0x180022cae  cmp     [rsi+60h], eax
0x180022cb1  cmovl   ecx, edx
0x180022cb4  mov     rbx, [rcx+rsi]
0x180022cb8  mov     r12d, r8d
0x180022cbb  mov     qword ptr [rsp+330h+InterfaceLuid], r8
0x180022cc0  lea     r14d, [r8+2]
0x180022cc4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180022cc8  test    rbx, rbx
0x180022ccb  jz      short loc_180022D2B
0x180022ccd  lea     rcx, [rsp+330h+var_308]; this
0x180022cd2  call    ??0DiagnosisTextParser@@QEAA@XZ; DiagnosisTextParser::DiagnosisTextParser(void)
0x180022cd7  nop
0x180022cd8  mov     rdx, rbx; unsigned __int16 *
0x180022cdb  lea     rcx, [rsp+330h+var_308]; this
0x180022ce0  call    ?SetXML@DiagnosisTextParser@@QEAAJPEBG@Z; DiagnosisTextParser::SetXML(ushort const *)
0x180022ce5  test    eax, eax
0x180022ce7  jnz     short loc_180022D03
0x180022ce9  lea     rdx, [rsp+330h+InterfaceLuid]; unsigned __int16 **
0x180022cee  lea     rcx, [rsp+330h+var_308]; this
0x180022cf3  call    ?GetReplacedText@DiagnosisTextParser@@QEAAJPEAPEAG@Z; DiagnosisTextParser::GetReplacedText(ushort * *)
0x180022cf8  mov     r12, qword ptr [rsp+330h+InterfaceLuid]
0x180022cfd  test    eax, eax
0x180022cff  cmovns  rbx, r12
0x180022d03  lea     rcx, [rsp+330h+var_308]; this
0x180022d08  call    ??1DiagnosisTextParser@@QEAA@XZ; DiagnosisTextParser::~DiagnosisTextParser(void)
0x180022d0d  xor     r8d, r8d
0x180022d10  test    rbx, rbx
0x180022d13  jz      short loc_180022D2B
0x180022d15  mov     rax, rdi
0x180022d18  inc     rax
0x180022d1b  cmp     [rbx+rax*2], r8w
0x180022d20  jnz     short loc_180022D18
0x180022d22  lea     eax, ds:2[rax*2]
0x180022d29  jmp     short loc_180022D35
0x180022d2b  lea     rbx, dword_180033E1C
0x180022d32  mov     eax, r14d
0x180022d35  mov     [rsp+330h+UserData.Ptr], rbx
0x180022d3a  mov     [rsp+330h+UserData.Size], eax
0x180022d3e  mov     dword ptr [rsp+330h+UserData.0Ch], r8d
0x180022d43  lea     rax, [rsi+100h]
0x180022d4a  mov     [rsp+330h+var_2D0], rax
0x180022d4f  mov     [rsp+330h+var_2C8], 10h
0x180022d58  mov     rbx, [r13+18h]
0x180022d5c  mov     r15, r8
0x180022d5f  mov     qword ptr [rsp+330h+InterfaceLuid], r8
0x180022d64  test    rbx, rbx
0x180022d67  jz      short loc_180022DC7
0x180022d69  lea     rcx, [rsp+330h+var_308]; this
0x180022d6e  call    ??0DiagnosisTextParser@@QEAA@XZ; DiagnosisTextParser::DiagnosisTextParser(void)
0x180022d73  nop
0x180022d74  mov     rdx, rbx; unsigned __int16 *
0x180022d77  lea     rcx, [rsp+330h+var_308]; this
0x180022d7c  call    ?SetXML@DiagnosisTextParser@@QEAAJPEBG@Z; DiagnosisTextParser::SetXML(ushort const *)
0x180022d81  test    eax, eax
0x180022d83  jnz     short loc_180022D9F
0x180022d85  lea     rdx, [rsp+330h+InterfaceLuid]; unsigned __int16 **
0x180022d8a  lea     rcx, [rsp+330h+var_308]; this
0x180022d8f  call    ?GetReplacedText@DiagnosisTextParser@@QEAAJPEAPEAG@Z; DiagnosisTextParser::GetReplacedText(ushort * *)
0x180022d94  mov     r15, qword ptr [rsp+330h+InterfaceLuid]
0x180022d99  test    eax, eax
0x180022d9b  cmovns  rbx, r15
0x180022d9f  lea     rcx, [rsp+330h+var_308]; this
0x180022da4  call    ??1DiagnosisTextParser@@QEAA@XZ; DiagnosisTextParser::~DiagnosisTextParser(void)
0x180022da9  xor     r8d, r8d
0x180022dac  test    rbx, rbx
0x180022daf  jz      short loc_180022DC7
0x180022db1  mov     rax, rdi
0x180022db4  inc     rax
0x180022db7  cmp     [rbx+rax*2], r8w
0x180022dbc  jnz     short loc_180022DB4
0x180022dbe  lea     eax, ds:2[rax*2]
0x180022dc5  jmp     short loc_180022DD1
0x180022dc7  lea     rbx, dword_180033E1C
0x180022dce  mov     eax, r14d
0x180022dd1  mov     [rsp+330h+var_2C0], rbx
0x180022dd6  mov     [rsp+330h+var_2B8], eax
0x180022dda  mov     [rsp+330h+var_2B4], r8d
0x180022ddf  mov     [rbp+230h+var_2B0], r13
0x180022de3  mov     [rbp+230h+var_2A8], 10h
0x180022deb  mov     eax, [r13+24h]
0x180022def  mov     [rsp+330h+var_300], eax
0x180022df3  lea     rax, [rsp+330h+var_300]
0x180022df8  mov     [rbp+230h+var_2A0], rax
0x180022dfc  mov     [rbp+230h+var_298], 4
0x180022e04  mov     eax, [r13+20h]
0x180022e08  mov     [rsp+330h+var_2FC], eax
0x180022e0c  lea     rax, [rsp+330h+var_2FC]
0x180022e11  mov     [rbp+230h+var_290], rax
0x180022e15  mov     [rbp+230h+var_288], 4
0x180022e1d  mov     rax, [rsi+10h]
0x180022e21  cmp     [rax-10h], r8d
0x180022e25  jnz     short loc_180022E2A
0x180022e27  mov     rax, [rsi]
0x180022e2a  test    rax, rax
0x180022e2d  jz      short loc_180022E46
0x180022e2f  mov     rcx, rdi
0x180022e32  inc     rcx
0x180022e35  cmp     [rax+rcx*2], r8w
0x180022e3a  jnz     short loc_180022E32
0x180022e3c  lea     r14d, ds:2[rcx*2]
0x180022e44  jmp     short loc_180022E4D
0x180022e46  lea     rax, dword_180033E1C
0x180022e4d  mov     [rbp+230h+var_280], rax
0x180022e51  mov     [rbp+230h+var_278], r14d
0x180022e55  mov     [rbp+230h+var_274], r8d
0x180022e59  xorps   xmm0, xmm0
0x180022e5c  movups  xmmword ptr [rsp+330h+InterfaceGuid.Data1], xmm0
0x180022e61  xor     edx, edx; Val
0x180022e63  mov     r8d, 202h; Size
0x180022e69  lea     rcx, [rbp+230h+InterfaceAlias]; void *
0x180022e6d  call    memset_0
0x180022e72  lea     rdx, [rsp+330h+InterfaceGuid]; struct _GUID *
0x180022e77  mov     rcx, rsi; struct ProblemInstance *
0x180022e7a  call    ?GetAdapterGUID@@YAHPEAVProblemInstance@@PEAU_GUID@@@Z; GetAdapterGUID(ProblemInstance *,_GUID *)
0x180022e7f  xor     esi, esi
0x180022e81  test    eax, eax
0x180022e83  jz      short loc_180022EB3
0x180022e85  mov     qword ptr [rsp+330h+InterfaceLuid], rsi
0x180022e8a  lea     rdx, [rsp+330h+InterfaceLuid]; InterfaceLuid
0x180022e8f  lea     rcx, [rsp+330h+InterfaceGuid]; InterfaceGuid
0x180022e94  call    cs:__imp_ConvertInterfaceGuidToLuid
0x180022e9a  test    eax, eax
0x180022e9c  jnz     short loc_180022EB3
0x180022e9e  mov     r8d, 101h; Length
0x180022ea4  lea     rdx, [rbp+230h+InterfaceAlias]; InterfaceAlias
0x180022ea8  lea     rcx, [rsp+330h+InterfaceLuid]; InterfaceLuid
0x180022ead  call    cs:__imp_ConvertInterfaceLuidToAlias
0x180022eb3  lea     rax, [rbp+230h+InterfaceAlias]
0x180022eb7  mov     [rbp+230h+var_270], rax
0x180022ebb  lea     rax, [rbp+230h+InterfaceAlias]
0x180022ebf  inc     rdi
0x180022ec2  cmp     [rax+rdi*2], si
0x180022ec6  jnz     short loc_180022EBF
0x180022ec8  lea     eax, ds:2[rdi*2]
0x180022ecf  mov     [rbp+230h+var_268], eax
0x180022ed2  mov     [rbp+230h+var_264], esi
0x180022ed5  lea     rax, [rsp+330h+InterfaceGuid]
0x180022eda  mov     [rbp+230h+var_260], rax
0x180022ede  mov     [rbp+230h+var_258], 10h
0x180022ee6  lea     r9, [rsp+330h+UserData]; UserData
0x180022eeb  mov     r8d, 9; UserDataCount
0x180022ef1  mov     rdx, [rsp+330h+EventDescriptor]; EventDescriptor
0x180022ef6  mov     rcx, cs:NETDIAG_EVT_GUID_Context; RegHandle
0x180022efd  call    cs:__imp_EventWrite
0x180022f03  mov     ebx, eax
0x180022f05  mov     rcx, r12; pv
0x180022f08  call    cs:__imp_CoTaskMemFree
0x180022f0e  mov     rcx, r15; pv
0x180022f11  call    cs:__imp_CoTaskMemFree
0x180022f17  test    ebx, ebx
0x180022f19  jle     short loc_180022F24
0x180022f1b  movzx   ebx, bx
0x180022f1e  or      ebx, 80070000h
0x180022f24  mov     eax, ebx
0x180022f26  mov     rcx, [rbp+230h+var_40]
0x180022f2d  xor     rcx, rsp; StackCookie
0x180022f30  call    __security_check_cookie
0x180022f35  mov     rbx, [rsp+330h+arg_0]
0x180022f3d  add     rsp, 300h
0x180022f44  pop     r15
0x180022f46  pop     r14
0x180022f48  pop     r13
0x180022f4a  pop     r12
0x180022f4c  pop     rdi
0x180022f4d  pop     rsi
0x180022f4e  pop     rbp
0x180022f4f  retn
```
