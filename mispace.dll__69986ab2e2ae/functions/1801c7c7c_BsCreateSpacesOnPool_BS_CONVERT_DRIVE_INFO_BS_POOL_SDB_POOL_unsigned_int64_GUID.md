# BsCreateSpacesOnPool(BS_CONVERT_DRIVE_INFO *,BS_POOL *,SDB_POOL *,unsigned __int64,_GUID *)

- ea: `0x1801c7c7c`
- end: `0x1801c8031`
- name: `?BsCreateSpacesOnPool@@YAJPEAVBS_CONVERT_DRIVE_INFO@@PEAVBS_POOL@@PEAVSDB_POOL@@_KPEAU_GUID@@@Z`
- size: `949`
- prototype: `int(struct BS_CONVERT_DRIVE_INFO *, struct BS_POOL *, struct SDB_POOL *, unsigned __int64, struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1801c8c7c`

## callees

- `0x180001504`
- `0x180005820`
- `0x180006350`
- `0x180006dd4`
- `0x1800b4ac0`
- `0x1801c7bc0`
- `0x1801c7c7c`
- `0x1801c8c04`
- `0x1801ccad4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c7e5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c7fab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c7e5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c7fab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801c7df1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801c7f42`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801c7df1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801c7f42`
- `RPCRT4!UuidCreate` at `0x1801c7d68`
- `RPCRT4!UuidCreate` at `0x1801c7eeb`
- `RPCRT4!UuidCreate` at `0x1801c7d68`
- `RPCRT4!UuidCreate` at `0x1801c7eeb`
- `ntdll!RtlNtStatusToDosError` at `0x1801c7de3`
- `ntdll!RtlNtStatusToDosError` at `0x1801c7f34`
- `ntdll!RtlNtStatusToDosError` at `0x1801c7de3`
- `ntdll!RtlNtStatusToDosError` at `0x1801c7f34`

## string_xrefs

- `0x1801c7dfd`: `Failed to create space on Pool`
- `0x1801c7e3a`: `BsCreateSpacesOnPool`
- `0x1801c7f8b`: `BsCreateSpacesOnPool`
- `0x1801c7f4e`: `Failed to create fixed-provisioned space on Pool`

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
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  NTSTATUS v19; // eax
  DWORD v20; // eax
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
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
    BS_SPACE_INFO::SetName((BS_SPACE_INFO *)v30, &word_1802C67CC);
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
      if ( (unsigned int)dword_18039EC48 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18039EC48, 1) )
      {
        v26 = 2140;
        v29 = (wchar_t *)"BsCreateSpacesOnPool";
        v28 = "minkernel\\storage\\spaces\\back\\back.cpp";
        LastError = GetLastError();
        v27 = pszDest;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v21,
          (unsigned int)byte_180370273,
          v22,
          v23,
          (__int64)&v27,
          (__int64)&LastError,
          (__int64)&v26,
          (__int64)&v28,
          (__int64)&v29);
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
    if ( (unsigned int)dword_18039EC48 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18039EC48, 1) )
    {
      LastError = 2110;
      v27 = (wchar_t *)"BsCreateSpacesOnPool";
      v28 = "minkernel\\storage\\spaces\\back\\back.cpp";
      v26 = GetLastError();
      v29 = pszDest;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v16,
        (unsigned int)byte_180370919,
        v17,
        v18,
        (__int64)&v29,
        (__int64)&v26,
        (__int64)&LastError,
        (__int64)&v28,
        (__int64)&v27);
    }
  }
  return v14;
}

```

## disassembly

```asm
0x1801c7c7c  push    rbp
0x1801c7c7e  push    rbx
0x1801c7c7f  push    rsi
0x1801c7c80  push    rdi
0x1801c7c81  push    r12
0x1801c7c83  push    r13
0x1801c7c85  push    r14
0x1801c7c87  push    r15
0x1801c7c89  lea     rbp, [rsp-658h]
0x1801c7c91  sub     rsp, 758h
0x1801c7c98  mov     rax, cs:__security_cookie
0x1801c7c9f  xor     rax, rsp
0x1801c7ca2  mov     [rbp+690h+var_50], rax
0x1801c7ca9  movsxd  r15, dword ptr [rcx+414h]
0x1801c7cb0  mov     r14, rcx
0x1801c7cb3  mov     rsi, [rbp+690h+arg_20]
0x1801c7cba  lea     rcx, [rsp+790h+var_720]; this
0x1801c7cbf  xorps   xmm0, xmm0
0x1801c7cc2  mov     rdi, r9
0x1801c7cc5  movups  xmmword ptr [rbp+690h+Uuid.Data1], xmm0
0x1801c7ccc  mov     rbx, r8
0x1801c7ccf  mov     r12, rdx
0x1801c7cd2  call    ??0BS_SPACE_INFO@@QEAA@XZ; BS_SPACE_INFO::BS_SPACE_INFO(void)
0x1801c7cd7  xor     edx, edx; Val
0x1801c7cd9  lea     rcx, [rsp+790h+var_720]; void *
0x1801c7cde  mov     r8d, 280h; Size
0x1801c7ce4  call    memset_0
0x1801c7ce9  movups  xmm0, xmmword ptr [rbx+60h]
0x1801c7ced  mov     rax, [r14+418h]
0x1801c7cf4  mov     r13d, 1
0x1801c7cfa  movups  xmm1, xmmword ptr [rbx+70h]
0x1801c7cfe  lea     rcx, [r15+r15*2]
0x1801c7d02  movups  [rbp+690h+var_478], xmm0
0x1801c7d09  mov     dword ptr [rbp+690h+var_478], r13d
0x1801c7d10  movups  xmm0, xmmword ptr [rbx+rcx*8+6Ch]
0x1801c7d15  mov     qword ptr [rbp+690h+var_478+8], rax
0x1801c7d1c  movups  [rbp+690h+var_468], xmm1
0x1801c7d23  movsd   xmm1, qword ptr [rbx+rcx*8+7Ch]
0x1801c7d29  lea     rcx, [rbp+690h+Uuid]; Uuid
0x1801c7d30  movups  [rbp+690h+var_490], xmm0
0x1801c7d37  mov     dword ptr [rbp+690h+var_490+8], r13d
0x1801c7d3e  movsd   [rbp+690h+var_480], xmm1
0x1801c7d46  mov     dword ptr [rbp+690h+var_490+4], 0
0x1801c7d50  mov     dword ptr [rbp+690h+var_490+0Ch], r13d
0x1801c7d57  mov     dword ptr [rbp+690h+var_480], r13d
0x1801c7d5e  mov     dword ptr [rbp+690h+var_480+4], 40000h
0x1801c7d68  call    cs:__imp_UuidCreate
0x1801c7d6f  nop     dword ptr [rax+rax+00h]
0x1801c7d74  lea     rdx, [r14+210h]; unsigned __int16 *
0x1801c7d7b  lea     rcx, [rsp+790h+var_720]; this
0x1801c7d80  call    ?SetName@BS_SPACE_INFO@@QEAAHPEBG@Z; BS_SPACE_INFO::SetName(ushort const *)
0x1801c7d85  mov     rax, [r14+418h]
0x1801c7d8c  lea     rdx, [rsp+790h+var_720]; struct BS_SPACE_INFO *
0x1801c7d91  movups  xmm0, xmmword ptr [rbp+690h+Uuid.Data1]
0x1801c7d98  lea     rcx, [rdi+rax*2]
0x1801c7d9c  lea     rax, [rbp+690h+var_490]
0x1801c7da3  mov     [rbp+690h+var_4F8], rcx
0x1801c7daa  mov     [rbp+690h+var_4B0], rax
0x1801c7db1  lea     edi, [r13+1]
0x1801c7db5  lea     rax, [rbp+690h+var_478]
0x1801c7dbc  mov     [rbp+690h+var_500], dil
0x1801c7dc3  mov     rcx, r12; this
0x1801c7dc6  mov     [rbp+690h+var_4A8], rax
0x1801c7dcd  movdqu  xmmword ptr [rbp+690h+var_710.Data1], xmm0
0x1801c7dd2  call    ?CreateSpace@BS_POOL@@QEAAJPEAVBS_SPACE_INFO@@@Z; BS_POOL::CreateSpace(BS_SPACE_INFO *)
0x1801c7dd7  mov     ebx, eax
0x1801c7dd9  test    eax, eax
0x1801c7ddb  jns     loc_1801C7EB9
0x1801c7de1  mov     ecx, eax; Status
0x1801c7de3  call    cs:__imp_RtlNtStatusToDosError
0x1801c7dea  nop     dword ptr [rax+rax+00h]
0x1801c7def  mov     ecx, eax; dwErrCode
0x1801c7df1  call    cs:__imp_SetLastError
0x1801c7df8  nop     dword ptr [rax+rax+00h]
0x1801c7dfd  lea     r8, aFailedToCreate_0; "Failed to create space on Pool"
0x1801c7e04  mov     edx, 400h; cbDest
0x1801c7e09  lea     rcx, [rbp+690h+pszDest]; pszDest
0x1801c7e10  call    StringCbPrintfW
0x1801c7e15  mov     ecx, cs:dword_18039EC48
0x1801c7e1b  cmp     ecx, edi
0x1801c7e1d  jbe     loc_1801C800B
0x1801c7e23  mov     edx, r13d
0x1801c7e26  lea     rcx, dword_18039EC48
0x1801c7e2d  call    _tlgKeywordOn
0x1801c7e32  test    al, al
0x1801c7e34  jz      loc_1801C800B
0x1801c7e3a  lea     rax, aBscreatespaces_0; "BsCreateSpacesOnPool"
0x1801c7e41  mov     [rsp+790h+var_740], 83Eh
0x1801c7e49  mov     [rsp+790h+var_738], rax
0x1801c7e4e  lea     rax, aMinkernelStora; "minkernel\\storage\\spaces\\back\\back."...
0x1801c7e55  mov     [rsp+790h+var_730], rax
0x1801c7e5a  call    cs:__imp_GetLastError
0x1801c7e61  nop     dword ptr [rax+rax+00h]
0x1801c7e66  mov     [rsp+790h+var_73C], eax
0x1801c7e6a  lea     rdx, byte_180370919
0x1801c7e71  lea     rax, [rbp+690h+pszDest]
0x1801c7e78  mov     [rsp+790h+var_728], rax
0x1801c7e7d  lea     rax, [rsp+790h+var_738]
0x1801c7e82  mov     [rsp+790h+var_750], rax
0x1801c7e87  lea     rax, [rsp+790h+var_730]
0x1801c7e8c  mov     [rsp+790h+var_758], rax
0x1801c7e91  lea     rax, [rsp+790h+var_740]
0x1801c7e96  mov     [rsp+790h+var_760], rax
0x1801c7e9b  lea     rax, [rsp+790h+var_73C]
0x1801c7ea0  mov     [rsp+790h+var_768], rax
0x1801c7ea5  lea     rax, [rsp+790h+var_728]
0x1801c7eaa  mov     [rsp+790h+var_770], rax
0x1801c7eaf  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1801c7eb4  jmp     loc_1801C800B
0x1801c7eb9  cmp     r15d, edi
0x1801c7ebc  jnz     loc_1801C8000
0x1801c7ec2  mov     rax, [r14+208h]
0x1801c7ec9  lea     rdx, word_1802C67CC; unsigned __int16 *
0x1801c7ed0  lea     rcx, [rsp+790h+var_720]; this
0x1801c7ed5  mov     qword ptr [rbp+690h+var_478+8], rax
0x1801c7edc  mov     dword ptr [rbp+690h+var_478], edi
0x1801c7ee2  call    ?SetName@BS_SPACE_INFO@@QEAAHPEBG@Z; BS_SPACE_INFO::SetName(ushort const *)
0x1801c7ee7  lea     rcx, [rbp+690h+var_710]; Uuid
0x1801c7eeb  call    cs:__imp_UuidCreate
0x1801c7ef2  nop     dword ptr [rax+rax+00h]
0x1801c7ef7  movups  xmm0, xmmword ptr [rbp+690h+Uuid.Data1]
0x1801c7efe  mov     rax, [r14+208h]
0x1801c7f05  lea     rdx, [rsp+790h+var_720]; struct BS_SPACE_INFO *
0x1801c7f0a  mov     rcx, r12; this
0x1801c7f0d  mov     [rbp+690h+var_4F8], rax
0x1801c7f14  movdqu  [rbp+690h+var_4C0], xmm0
0x1801c7f1c  mov     [rbp+690h+var_500], 6
0x1801c7f23  call    ?CreateSpace@BS_POOL@@QEAAJPEAVBS_SPACE_INFO@@@Z; BS_POOL::CreateSpace(BS_SPACE_INFO *)
0x1801c7f28  mov     ebx, eax
0x1801c7f2a  test    eax, eax
0x1801c7f2c  jns     loc_1801C8000
0x1801c7f32  mov     ecx, eax; Status
0x1801c7f34  call    cs:__imp_RtlNtStatusToDosError
0x1801c7f3b  nop     dword ptr [rax+rax+00h]
0x1801c7f40  mov     ecx, eax; dwErrCode
0x1801c7f42  call    cs:__imp_SetLastError
0x1801c7f49  nop     dword ptr [rax+rax+00h]
0x1801c7f4e  lea     r8, aFailedToCreate; "Failed to create fixed-provisioned spac"...
0x1801c7f55  mov     edx, 400h; cbDest
0x1801c7f5a  lea     rcx, [rbp+690h+pszDest]; pszDest
0x1801c7f61  call    StringCbPrintfW
0x1801c7f66  mov     eax, cs:dword_18039EC48
0x1801c7f6c  cmp     eax, edi
0x1801c7f6e  jbe     loc_1801C800B
0x1801c7f74  mov     rdx, r13
0x1801c7f77  lea     rcx, dword_18039EC48
0x1801c7f7e  call    _tlgKeywordOn
0x1801c7f83  test    al, al
0x1801c7f85  jz      loc_1801C800B
0x1801c7f8b  lea     rax, aBscreatespaces_0; "BsCreateSpacesOnPool"
0x1801c7f92  mov     [rsp+790h+var_73C], 85Ch
0x1801c7f9a  mov     [rsp+790h+var_728], rax
0x1801c7f9f  lea     rax, aMinkernelStora; "minkernel\\storage\\spaces\\back\\back."...
0x1801c7fa6  mov     [rsp+790h+var_730], rax
0x1801c7fab  call    cs:__imp_GetLastError
0x1801c7fb2  nop     dword ptr [rax+rax+00h]
0x1801c7fb7  mov     [rsp+790h+var_740], eax
0x1801c7fbb  lea     rdx, byte_180370273
0x1801c7fc2  lea     rax, [rbp+690h+pszDest]
0x1801c7fc9  mov     [rsp+790h+var_738], rax
0x1801c7fce  lea     rax, [rsp+790h+var_728]
0x1801c7fd3  mov     [rsp+790h+var_750], rax
0x1801c7fd8  lea     rax, [rsp+790h+var_730]
0x1801c7fdd  mov     [rsp+790h+var_758], rax
0x1801c7fe2  lea     rax, [rsp+790h+var_73C]
0x1801c7fe7  mov     [rsp+790h+var_760], rax
0x1801c7fec  lea     rax, [rsp+790h+var_740]
0x1801c7ff1  mov     [rsp+790h+var_768], rax
0x1801c7ff6  lea     rax, [rsp+790h+var_738]
0x1801c7ffb  jmp     loc_1801C7EAA
0x1801c8000  movups  xmm0, xmmword ptr [rbp+690h+Uuid.Data1]
0x1801c8007  movdqu  xmmword ptr [rsi], xmm0
0x1801c800b  mov     eax, ebx
0x1801c800d  mov     rcx, [rbp+690h+var_50]
0x1801c8014  xor     rcx, rsp; StackCookie
0x1801c8017  call    __security_check_cookie
0x1801c801c  add     rsp, 758h
0x1801c8023  pop     r15
0x1801c8025  pop     r14
0x1801c8027  pop     r13
0x1801c8029  pop     r12
0x1801c802b  pop     rdi
0x1801c802c  pop     rsi
0x1801c802d  pop     rbx
0x1801c802e  pop     rbp
0x1801c802f  retn
```
