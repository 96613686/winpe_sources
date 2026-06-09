# BsCreateSpacesOnPool(BS_CONVERT_DRIVE_INFO *,BS_POOL *,SDB_POOL *,unsigned __int64,_GUID *)

- ea: `0x1801c105c`
- end: `0x1801c13dc`
- name: `?BsCreateSpacesOnPool@@YAJPEAVBS_CONVERT_DRIVE_INFO@@PEAVBS_POOL@@PEAVSDB_POOL@@_KPEAU_GUID@@@Z`
- size: `896`
- prototype: `int(struct BS_CONVERT_DRIVE_INFO *, struct BS_POOL *, struct SDB_POOL *, unsigned __int64, struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1801c1f64`

## callees

- `0x1800014ec`
- `0x1800057d8`
- `0x180006290`
- `0x180006cf4`
- `0x1800b1e00`
- `0x1801c0fa0`
- `0x1801c105c`
- `0x1801c1ef8`
- `0x1801c5a70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c1228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c135d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c1228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c135d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801c11c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801c12fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801c11c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801c12fe`
- `RPCRT4!UuidCreate` at `0x1801c1148`
- `RPCRT4!UuidCreate` at `0x1801c12b3`
- `RPCRT4!UuidCreate` at `0x1801c1148`
- `RPCRT4!UuidCreate` at `0x1801c12b3`
- `ntdll!RtlNtStatusToDosError` at `0x1801c11bd`
- `ntdll!RtlNtStatusToDosError` at `0x1801c12f6`
- `ntdll!RtlNtStatusToDosError` at `0x1801c11bd`
- `ntdll!RtlNtStatusToDosError` at `0x1801c12f6`

## string_xrefs

- `0x1801c11cb`: `Failed to create space on Pool`
- `0x1801c1208`: `BsCreateSpacesOnPool`
- `0x1801c133d`: `BsCreateSpacesOnPool`
- `0x1801c1304`: `Failed to create fixed-provisioned space on Pool`

## pseudocode

```c
__int64 __fastcall BsCreateSpacesOnPool(
        struct BS_CONVERT_DRIVE_INFO *a1,
        struct BS_POOL *a2,
        struct SDB_POOL *a3,
        __int64 a4,
        struct _GUID *a5)
{
  __int64 v5; // r15
  __int64 v10; // rax
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  NTSTATUS Space; // eax
  unsigned int v14; // ebx
  DWORD v15; // eax
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  NTSTATUS v19; // eax
  DWORD v20; // eax
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  DWORD LastError; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v26; // [rsp+54h] [rbp-ACh] BYREF
  wchar_t *v27; // [rsp+58h] [rbp-A8h] BYREF
  const char *v28; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *v29; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v30[16]; // [rsp+70h] [rbp-90h] BYREF
  UUID v31; // [rsp+80h] [rbp-80h] BYREF
  char v32; // [rsp+290h] [rbp+190h]
  __int64 v33; // [rsp+298h] [rbp+198h]
  UUID v34; // [rsp+2D0h] [rbp+1D0h]
  int *v35; // [rsp+2E0h] [rbp+1E0h]
  _OWORD *v36; // [rsp+2E8h] [rbp+1E8h]
  UUID Uuid; // [rsp+2F0h] [rbp+1F0h] BYREF
  int v38; // [rsp+300h] [rbp+200h] BYREF
  __int64 v39; // [rsp+304h] [rbp+204h]
  int v40; // [rsp+30Ch] [rbp+20Ch]
  __int64 v41; // [rsp+310h] [rbp+210h]
  _OWORD v42[2]; // [rsp+318h] [rbp+218h] BYREF
  wchar_t pszDest[512]; // [rsp+340h] [rbp+240h] BYREF

  v5 = *((int *)a1 + 261);
  Uuid = 0;
  BS_SPACE_INFO::BS_SPACE_INFO((BS_SPACE_INFO *)v30);
  memset_0(v30, 0, 0x280u);
  v10 = *((_QWORD *)a1 + 131);
  v11 = *((_OWORD *)a3 + 7);
  v42[0] = *((_OWORD *)a3 + 6);
  LODWORD(v42[0]) = 1;
  v12 = *(_OWORD *)((char *)a3 + 24 * v5 + 108);
  *((_QWORD *)&v42[0] + 1) = v10;
  v42[1] = v11;
  v38 = v12;
  v39 = 0x100000000LL;
  v40 = 1;
  v41 = 0x4000000000001LL;
  UuidCreate(&Uuid);
  BS_SPACE_INFO::SetName((BS_SPACE_INFO *)v30, (const unsigned __int16 *)a1 + 264);
  v33 = a4 + 2LL * *((_QWORD *)a1 + 131);
  v35 = &v38;
  v32 = 2;
  v36 = v42;
  v31 = Uuid;
  Space = BS_POOL::CreateSpace(a2, (struct BS_SPACE_INFO *)v30);
  v14 = Space;
  if ( Space >= 0 )
  {
    if ( (_DWORD)v5 != 2 )
      goto LABEL_11;
    *((_QWORD *)&v42[0] + 1) = *((_QWORD *)a1 + 65);
    LODWORD(v42[0]) = 2;
    BS_SPACE_INFO::SetName((BS_SPACE_INFO *)v30, &word_1802BF87C);
    UuidCreate(&v31);
    v33 = *((_QWORD *)a1 + 65);
    v34 = Uuid;
    v32 = 6;
    v19 = BS_POOL::CreateSpace(a2, (struct BS_SPACE_INFO *)v30);
    v14 = v19;
    if ( v19 < 0 )
    {
      v20 = RtlNtStatusToDosError(v19);
      SetLastError(v20);
      StringCbPrintfW(pszDest, 0x400u, L"Failed to create fixed-provisioned space on Pool");
      if ( (unsigned int)dword_180397C48 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180397C48, 1) )
      {
        v26 = 2140;
        v29 = (wchar_t *)"BsCreateSpacesOnPool";
        v28 = "minkernel\\storage\\spaces\\back\\back.cpp";
        LastError = GetLastError();
        v27 = pszDest;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v21,
          (__int64)&byte_180369297,
          v22,
          v23,
          &v27,
          (__int64)&LastError,
          (__int64)&v26,
          &v28,
          &v29);
      }
    }
    else
    {
LABEL_11:
      *a5 = Uuid;
    }
  }
  else
  {
    v15 = RtlNtStatusToDosError(Space);
    SetLastError(v15);
    StringCbPrintfW(pszDest, 0x400u, L"Failed to create space on Pool");
    if ( (unsigned int)dword_180397C48 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180397C48, 1) )
    {
      LastError = 2110;
      v27 = (wchar_t *)"BsCreateSpacesOnPool";
      v28 = "minkernel\\storage\\spaces\\back\\back.cpp";
      v26 = GetLastError();
      v29 = pszDest;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v16,
        (__int64)&unk_180369A38,
        v17,
        v18,
        &v29,
        (__int64)&v26,
        (__int64)&LastError,
        &v28,
        &v27);
    }
  }
  return v14;
}

```

## disassembly

```asm
0x1801c105c  push    rbp
0x1801c105e  push    rbx
0x1801c105f  push    rsi
0x1801c1060  push    rdi
0x1801c1061  push    r12
0x1801c1063  push    r13
0x1801c1065  push    r14
0x1801c1067  push    r15
0x1801c1069  lea     rbp, [rsp-658h]
0x1801c1071  sub     rsp, 758h
0x1801c1078  mov     rax, cs:__security_cookie
0x1801c107f  xor     rax, rsp
0x1801c1082  mov     [rbp+690h+var_50], rax
0x1801c1089  movsxd  r15, dword ptr [rcx+414h]
0x1801c1090  mov     r14, rcx
0x1801c1093  mov     rsi, [rbp+690h+arg_20]
0x1801c109a  lea     rcx, [rsp+790h+var_720]; this
0x1801c109f  xorps   xmm0, xmm0
0x1801c10a2  mov     rdi, r9
0x1801c10a5  movups  xmmword ptr [rbp+690h+Uuid.Data1], xmm0
0x1801c10ac  mov     rbx, r8
0x1801c10af  mov     r12, rdx
0x1801c10b2  call    ??0BS_SPACE_INFO@@QEAA@XZ; BS_SPACE_INFO::BS_SPACE_INFO(void)
0x1801c10b7  xor     edx, edx; Val
0x1801c10b9  lea     rcx, [rsp+790h+var_720]; void *
0x1801c10be  mov     r8d, 280h; Size
0x1801c10c4  call    memset_0
0x1801c10c9  movups  xmm0, xmmword ptr [rbx+60h]
0x1801c10cd  mov     rax, [r14+418h]
0x1801c10d4  mov     r13d, 1
0x1801c10da  movups  xmm1, xmmword ptr [rbx+70h]
0x1801c10de  lea     rcx, [r15+r15*2]
0x1801c10e2  movups  [rbp+690h+var_478], xmm0
0x1801c10e9  mov     dword ptr [rbp+690h+var_478], r13d
0x1801c10f0  movups  xmm0, xmmword ptr [rbx+rcx*8+6Ch]
0x1801c10f5  mov     qword ptr [rbp+690h+var_478+8], rax
0x1801c10fc  movups  [rbp+690h+var_468], xmm1
0x1801c1103  movsd   xmm1, qword ptr [rbx+rcx*8+7Ch]
0x1801c1109  lea     rcx, [rbp+690h+Uuid]; Uuid
0x1801c1110  movups  [rbp+690h+var_490], xmm0
0x1801c1117  mov     dword ptr [rbp+690h+var_490+8], r13d
0x1801c111e  movsd   [rbp+690h+var_480], xmm1
0x1801c1126  mov     dword ptr [rbp+690h+var_490+4], 0
0x1801c1130  mov     dword ptr [rbp+690h+var_490+0Ch], r13d
0x1801c1137  mov     dword ptr [rbp+690h+var_480], r13d
0x1801c113e  mov     dword ptr [rbp+690h+var_480+4], 40000h
0x1801c1148  call    cs:__imp_UuidCreate
0x1801c114e  lea     rdx, [r14+210h]; unsigned __int16 *
0x1801c1155  lea     rcx, [rsp+790h+var_720]; this
0x1801c115a  call    ?SetName@BS_SPACE_INFO@@QEAAHPEBG@Z; BS_SPACE_INFO::SetName(ushort const *)
0x1801c115f  mov     rax, [r14+418h]
0x1801c1166  lea     rdx, [rsp+790h+var_720]; struct BS_SPACE_INFO *
0x1801c116b  movups  xmm0, xmmword ptr [rbp+690h+Uuid.Data1]
0x1801c1172  lea     rcx, [rdi+rax*2]
0x1801c1176  lea     rax, [rbp+690h+var_490]
0x1801c117d  mov     [rbp+690h+var_4F8], rcx
0x1801c1184  mov     [rbp+690h+var_4B0], rax
0x1801c118b  lea     edi, [r13+1]
0x1801c118f  lea     rax, [rbp+690h+var_478]
0x1801c1196  mov     [rbp+690h+var_500], dil
0x1801c119d  mov     rcx, r12; this
0x1801c11a0  mov     [rbp+690h+var_4A8], rax
0x1801c11a7  movdqu  xmmword ptr [rbp+690h+var_710.Data1], xmm0
0x1801c11ac  call    ?CreateSpace@BS_POOL@@QEAAJPEAVBS_SPACE_INFO@@@Z; BS_POOL::CreateSpace(BS_SPACE_INFO *)
0x1801c11b1  mov     ebx, eax
0x1801c11b3  test    eax, eax
0x1801c11b5  jns     loc_1801C1281
0x1801c11bb  mov     ecx, eax; Status
0x1801c11bd  call    cs:__imp_RtlNtStatusToDosError
0x1801c11c3  mov     ecx, eax; dwErrCode
0x1801c11c5  call    cs:__imp_SetLastError
0x1801c11cb  lea     r8, aFailedToCreate_0; "Failed to create space on Pool"
0x1801c11d2  mov     edx, 400h; cbDest
0x1801c11d7  lea     rcx, [rbp+690h+pszDest]; pszDest
0x1801c11de  call    StringCbPrintfW
0x1801c11e3  mov     ecx, cs:dword_180397C48
0x1801c11e9  cmp     ecx, edi
0x1801c11eb  jbe     loc_1801C13B7
0x1801c11f1  mov     edx, r13d
0x1801c11f4  lea     rcx, dword_180397C48
0x1801c11fb  call    _tlgKeywordOn
0x1801c1200  test    al, al
0x1801c1202  jz      loc_1801C13B7
0x1801c1208  lea     rax, aBscreatespaces_0; "BsCreateSpacesOnPool"
0x1801c120f  mov     [rsp+790h+var_740], 83Eh
0x1801c1217  mov     [rsp+790h+var_738], rax
0x1801c121c  lea     rax, aMinkernelStora; "minkernel\\storage\\spaces\\back\\back."...
0x1801c1223  mov     [rsp+790h+var_730], rax
0x1801c1228  call    cs:__imp_GetLastError
0x1801c122e  mov     [rsp+790h+var_73C], eax
0x1801c1232  lea     rdx, unk_180369A38
0x1801c1239  lea     rax, [rbp+690h+pszDest]
0x1801c1240  mov     [rsp+790h+var_728], rax
0x1801c1245  lea     rax, [rsp+790h+var_738]
0x1801c124a  mov     [rsp+790h+var_750], rax
0x1801c124f  lea     rax, [rsp+790h+var_730]
0x1801c1254  mov     [rsp+790h+var_758], rax
0x1801c1259  lea     rax, [rsp+790h+var_740]
0x1801c125e  mov     [rsp+790h+var_760], rax
0x1801c1263  lea     rax, [rsp+790h+var_73C]
0x1801c1268  mov     [rsp+790h+var_768], rax
0x1801c126d  lea     rax, [rsp+790h+var_728]
0x1801c1272  mov     [rsp+790h+var_770], rax
0x1801c1277  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1801c127c  jmp     loc_1801C13B7
0x1801c1281  cmp     r15d, edi
0x1801c1284  jnz     loc_1801C13AC
0x1801c128a  mov     rax, [r14+208h]
0x1801c1291  lea     rdx, word_1802BF87C; unsigned __int16 *
0x1801c1298  lea     rcx, [rsp+790h+var_720]; this
0x1801c129d  mov     qword ptr [rbp+690h+var_478+8], rax
0x1801c12a4  mov     dword ptr [rbp+690h+var_478], edi
0x1801c12aa  call    ?SetName@BS_SPACE_INFO@@QEAAHPEBG@Z; BS_SPACE_INFO::SetName(ushort const *)
0x1801c12af  lea     rcx, [rbp+690h+var_710]; Uuid
0x1801c12b3  call    cs:__imp_UuidCreate
0x1801c12b9  movups  xmm0, xmmword ptr [rbp+690h+Uuid.Data1]
0x1801c12c0  mov     rax, [r14+208h]
0x1801c12c7  lea     rdx, [rsp+790h+var_720]; struct BS_SPACE_INFO *
0x1801c12cc  mov     rcx, r12; this
0x1801c12cf  mov     [rbp+690h+var_4F8], rax
0x1801c12d6  movdqu  [rbp+690h+var_4C0], xmm0
0x1801c12de  mov     [rbp+690h+var_500], 6
0x1801c12e5  call    ?CreateSpace@BS_POOL@@QEAAJPEAVBS_SPACE_INFO@@@Z; BS_POOL::CreateSpace(BS_SPACE_INFO *)
0x1801c12ea  mov     ebx, eax
0x1801c12ec  test    eax, eax
0x1801c12ee  jns     loc_1801C13AC
0x1801c12f4  mov     ecx, eax; Status
0x1801c12f6  call    cs:__imp_RtlNtStatusToDosError
0x1801c12fc  mov     ecx, eax; dwErrCode
0x1801c12fe  call    cs:__imp_SetLastError
0x1801c1304  lea     r8, aFailedToCreate; "Failed to create fixed-provisioned spac"...
0x1801c130b  mov     edx, 400h; cbDest
0x1801c1310  lea     rcx, [rbp+690h+pszDest]; pszDest
0x1801c1317  call    StringCbPrintfW
0x1801c131c  mov     eax, cs:dword_180397C48
0x1801c1322  cmp     eax, edi
0x1801c1324  jbe     loc_1801C13B7
0x1801c132a  mov     rdx, r13
0x1801c132d  lea     rcx, dword_180397C48
0x1801c1334  call    _tlgKeywordOn
0x1801c1339  test    al, al
0x1801c133b  jz      short loc_1801C13B7
0x1801c133d  lea     rax, aBscreatespaces_0; "BsCreateSpacesOnPool"
0x1801c1344  mov     [rsp+790h+var_73C], 85Ch
0x1801c134c  mov     [rsp+790h+var_728], rax
0x1801c1351  lea     rax, aMinkernelStora; "minkernel\\storage\\spaces\\back\\back."...
0x1801c1358  mov     [rsp+790h+var_730], rax
0x1801c135d  call    cs:__imp_GetLastError
0x1801c1363  mov     [rsp+790h+var_740], eax
0x1801c1367  lea     rdx, byte_180369297
0x1801c136e  lea     rax, [rbp+690h+pszDest]
0x1801c1375  mov     [rsp+790h+var_738], rax
0x1801c137a  lea     rax, [rsp+790h+var_728]
0x1801c137f  mov     [rsp+790h+var_750], rax
0x1801c1384  lea     rax, [rsp+790h+var_730]
0x1801c1389  mov     [rsp+790h+var_758], rax
0x1801c138e  lea     rax, [rsp+790h+var_73C]
0x1801c1393  mov     [rsp+790h+var_760], rax
0x1801c1398  lea     rax, [rsp+790h+var_740]
0x1801c139d  mov     [rsp+790h+var_768], rax
0x1801c13a2  lea     rax, [rsp+790h+var_738]
0x1801c13a7  jmp     loc_1801C1272
0x1801c13ac  movups  xmm0, xmmword ptr [rbp+690h+Uuid.Data1]
0x1801c13b3  movdqu  xmmword ptr [rsi], xmm0
0x1801c13b7  mov     eax, ebx
0x1801c13b9  mov     rcx, [rbp+690h+var_50]
0x1801c13c0  xor     rcx, rsp; StackCookie
0x1801c13c3  call    __security_check_cookie
0x1801c13c8  add     rsp, 758h
0x1801c13cf  pop     r15
0x1801c13d1  pop     r14
0x1801c13d3  pop     r13
0x1801c13d5  pop     r12
0x1801c13d7  pop     rdi
0x1801c13d8  pop     rsi
0x1801c13d9  pop     rbx
0x1801c13da  pop     rbp
0x1801c13db  retn
```
