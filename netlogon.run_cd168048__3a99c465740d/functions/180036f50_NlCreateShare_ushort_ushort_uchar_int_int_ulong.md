# NlCreateShare(ushort *,ushort *,uchar,int,int,ulong)

- ea: `0x180036f50`
- end: `0x18003733d`
- name: `?NlCreateShare@@YAKPEAG0EHHK@Z`
- size: `1005`
- prototype: `unsigned int(unsigned __int16 *, unsigned __int16 *, unsigned __int8, int, int, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007331c`

## callees

- `0x1800037f0`
- `0x180007518`
- `0x180007e90`
- `0x18000dd00`
- `0x18000e910`
- `0x18000f3e4`
- `0x180036f50`
- `0x18008d770`
- `0x18008e23c`
- `0x18008e5c4`

## import_xrefs

- `netutils!NetApiBufferFree` at `0x180037303`
- `netutils!NetApiBufferFree` at `0x180037303`
- `netutils!NetpwPathCompare` at `0x180037157`
- `netutils!NetpwPathCompare` at `0x180037157`
- `srvcli!NetShareDel` at `0x18003716f`
- `srvcli!NetShareDel` at `0x18003716f`
- `srvcli!NetShareSetInfo` at `0x1800372a5`
- `srvcli!NetShareSetInfo` at `0x1800372a5`
- `srvcli!NetShareGetInfo` at `0x180037114`
- `srvcli!NetShareGetInfo` at `0x180037227`
- `srvcli!NetShareGetInfo` at `0x180037114`
- `srvcli!NetShareGetInfo` at `0x180037227`
- `srvcli!NetShareAdd` at `0x1800370d4`
- `srvcli!NetShareAdd` at `0x18003718d`
- `srvcli!NetShareAdd` at `0x1800370d4`
- `srvcli!NetShareAdd` at `0x18003718d`

## string_xrefs

- `0x1800371d6`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x1800370a2`: `'%ws' share: Cannot create security descriptor 0x%lx\n`
- `0x1800370f5`: `'%ws' share already exists. \n`
- `0x18003712f`: `'%ws' share current path is %ws\n`
- `0x1800371a2`: `'%ws' share was recreated with new path %ws\n`
- `0x1800371f9`: `'%ws' share: Error attempting to create-share: %ld\n`
- `0x18003723c`: `NlCreateShare: NetShareGetInfo (1005) failed for share '%ws': %lu\n`
- `0x1800372cb`: `NlCreateShare: Share '%ws' updated successfully flags 0x%lx 0x%lx\n`
- `0x1800372dd`: `NlCreateShare: Failed to update share '%ws' flags 0x%lx 0x%lx: 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NlCreateShare(unsigned __int16 *a1, unsigned __int16 *a2, char a3, __int64 a4, int a5)
{
  BOOL v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // eax
  NTSTATUS v12; // ebx
  DWORD Info; // ebx
  char *v15; // r9
  DWORD v16; // eax
  DWORD v17; // esi
  LPBYTE v18; // rcx
  unsigned int v19; // ebx
  int v20; // eax
  bool v21; // zf
  unsigned int v22; // eax
  int v23; // eax
  DWORD v24; // eax
  LPDWORD parm_err; // [rsp+20h] [rbp-E0h]
  LPBYTE v26; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v27; // [rsp+48h] [rbp-B8h]
  LPBYTE bufptr; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v29; // [rsp+58h] [rbp-A8h] BYREF
  char v30; // [rsp+5Ah] [rbp-A6h]
  int v31; // [rsp+5Ch] [rbp-A4h]
  __int64 *v32; // [rsp+60h] [rbp-A0h]
  __int16 v33; // [rsp+68h] [rbp-98h]
  char v34; // [rsp+6Ah] [rbp-96h]
  int v35; // [rsp+6Ch] [rbp-94h]
  __int64 *v36; // [rsp+70h] [rbp-90h]
  __int16 v37; // [rsp+78h] [rbp-88h]
  char v38; // [rsp+7Ah] [rbp-86h]
  int v39; // [rsp+7Ch] [rbp-84h]
  __int64 *v40; // [rsp+80h] [rbp-80h]
  BYTE buf[8]; // [rsp+90h] [rbp-70h] BYREF
  int v42; // [rsp+98h] [rbp-68h]
  WCHAR *v43; // [rsp+A0h] [rbp-60h]
  int v44; // [rsp+A8h] [rbp-58h]
  int v45; // [rsp+ACh] [rbp-54h]
  unsigned __int16 *v46; // [rsp+B8h] [rbp-48h]
  const WCHAR *v47; // [rsp+C0h] [rbp-40h]
  struct _ACL *v48; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v49[96]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR SourceString[88]; // [rsp+140h] [rbp+40h] BYREF

  memset_0(buf, 0, 0x48u);
  v31 = -1610612736;
  v26 = 0;
  v35 = 0x10000000;
  v32 = &WorldSid;
  v39 = 0x10000000;
  v36 = &AliasAdminsSid;
  v27 = 0;
  v40 = &AuthenticatedUserSid;
  v29 = 0;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v37 = 0;
  v8 = a3 != 0;
  v38 = 0;
  v46 = a1;
  v48 = 0;
  NlPrintRoutine(1u, L"'%ws' share is to '%ws'\n", a2, a1);
  if ( (unsigned __int16)DosGetMessage(v10, v9, v49) )
  {
    v43 = (WCHAR *)&LocaleName;
  }
  else
  {
    NetpCopyStrToWStr(SourceString);
    v43 = SourceString;
  }
  *(_QWORD *)buf = a2;
  v42 = 0;
  v44 = 1;
  v45 = -1;
  v47 = &LocaleName;
  v11 = NetpCreateSecurityDescriptor((__int64)&v29, v8 + 2, 0, 0, &v48);
  v12 = v11;
  if ( v11 < 0 )
  {
    NlPrintRoutine(0x100u, L"'%ws' share: Cannot create security descriptor 0x%lx\n", a1, (unsigned int)v11);
    return NetpNtStatusToApiStatus(v12);
  }
  Info = NetShareAdd(0, 0x1F6u, buf, 0);
  if ( Info == 2118 )
  {
    bufptr = 0;
    NlPrintRoutine(1u, L"'%ws' share already exists. \n", a2);
    Info = NetShareGetInfo(0, a2, 2u, &bufptr);
    if ( !Info )
    {
      NlPrintRoutine(1u, L"'%ws' share current path is %ws\n", a2, *((_QWORD *)bufptr + 5));
      if ( (unsigned int)NetpwPathCompare(a1, *((_QWORD *)bufptr + 5), 0, 0) )
      {
        Info = NetShareDel(0, a2, 0);
        if ( !Info )
        {
          Info = NetShareAdd(0, 0x1F6u, buf, 0);
          if ( !Info )
            NlPrintRoutine(1u, L"'%ws' share was recreated with new path %ws\n", a2, a1);
        }
      }
    }
    if ( bufptr )
      NetpMemoryFree(bufptr);
  }
  if ( !NlGlobalMemberWorkstation && Info )
    NlAssertFailed(
      "NetStatus == NERR_Success",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\lsrvutil.cxx",
      0x159Eu,
      v15);
  NetpMemoryFree(v48);
  if ( Info )
  {
    NlPrintRoutine(0x100u, L"'%ws' share: Error attempting to create-share: %ld\n", a2, Info);
    return Info;
  }
  v16 = NetShareGetInfo(0, a2, 0x3EDu, &v26);
  v17 = v16;
  if ( !v16 )
  {
    v18 = v26;
    v19 = *(_DWORD *)v26;
    v20 = *(_DWORD *)v26 & 0x100;
    if ( a5 )
    {
      v21 = v20 == 0;
      v22 = *(_DWORD *)v26;
      if ( !v21 )
      {
        v22 = v19 & 0xFFFFFEFF;
LABEL_26:
        *(_DWORD *)v26 = v22;
        v18 = v26;
      }
    }
    else
    {
      v21 = v20 == 0;
      v22 = *(_DWORD *)v26;
      if ( v21 )
      {
        v22 = v19 | 0x100;
        goto LABEL_26;
      }
    }
    v23 = v22 | 0x1000;
    *(_DWORD *)v18 = v23;
    if ( v19 != v23 )
    {
      v24 = NetShareSetInfo(0, a2, 0x3EDu, v26, 0);
      v17 = v24;
      LODWORD(parm_err) = *(_DWORD *)v26;
      if ( v24 )
        NlPrintRoutine(
          0x100u,
          L"NlCreateShare: Failed to update share '%ws' flags 0x%lx 0x%lx: 0x%lx\n",
          a2,
          v19,
          parm_err,
          v24);
      else
        NlPrintRoutine(1u, L"NlCreateShare: Share '%ws' updated successfully flags 0x%lx 0x%lx\n", a2, v19, parm_err);
    }
    if ( v26 )
      NetApiBufferFree(v26);
    return v17;
  }
  NlPrintRoutine(0x100u, L"NlCreateShare: NetShareGetInfo (1005) failed for share '%ws': %lu\n", a2, v16);
  return v17;
}

```

## disassembly

```asm
0x180036f50  mov     [rsp-8+arg_10], rbx
0x180036f55  mov     [rsp-8+arg_18], rsi
0x180036f5a  push    rbp
0x180036f5b  push    rdi
0x180036f5c  push    r12
0x180036f5e  push    r14
0x180036f60  push    r15
0x180036f62  lea     rbp, [rsp-100h]
0x180036f6a  sub     rsp, 200h
0x180036f71  mov     rax, cs:__security_cookie
0x180036f78  xor     rax, rsp
0x180036f7b  mov     [rbp+120h+var_30], rax
0x180036f82  mov     rdi, rdx
0x180036f85  mov     bl, r8b
0x180036f88  xor     edx, edx; Val
0x180036f8a  mov     rsi, rcx
0x180036f8d  lea     rcx, [rbp+120h+buf]; void *
0x180036f91  lea     r8d, [rdx+48h]; Size
0x180036f95  call    memset_0
0x180036f9a  xor     r14d, r14d
0x180036f9d  mov     [rsp+220h+var_1C4], 0A0000000h
0x180036fa5  mov     ecx, 10000000h
0x180036faa  mov     [rsp+220h+var_1E0], r14
0x180036faf  lea     rax, WorldSid
0x180036fb6  mov     [rsp+220h+var_1B4], ecx
0x180036fba  mov     [rsp+220h+var_1C0], rax
0x180036fbf  lea     rdx, aWsShareIsToWs; "'%ws' share is to '%ws'\n"
0x180036fc6  lea     rax, AliasAdminsSid
0x180036fcd  mov     [rsp+220h+var_1A4], ecx
0x180036fd1  neg     bl
0x180036fd3  mov     [rsp+220h+var_1B0], rax
0x180036fd8  lea     rax, AuthenticatedUserSid
0x180036fdf  mov     [rsp+220h+var_1D8], r14w
0x180036fe5  sbb     ebx, ebx
0x180036fe7  mov     [rbp+120h+var_1A0], rax
0x180036feb  lea     r15d, [r14+1]
0x180036fef  mov     [rsp+220h+var_1C8], r14w
0x180036ff5  mov     r9, rsi
0x180036ff8  mov     [rsp+220h+var_1C6], r14b
0x180036ffd  mov     r8, rdi
0x180037000  mov     [rsp+220h+var_1B8], r14w
0x180037006  mov     ecx, r15d; unsigned int
0x180037009  mov     [rsp+220h+var_1B6], r14b
0x18003700e  mov     [rsp+220h+var_1A8], r14w
0x180037014  neg     ebx
0x180037016  mov     [rsp+220h+var_1A6], r14b
0x18003701b  mov     [rbp+120h+var_168], rsi
0x18003701f  mov     [rbp+120h+var_150], r14
0x180037023  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180037028  lea     rax, [rsp+220h+var_1D8]
0x18003702d  lea     r8, [rbp+120h+var_140]
0x180037031  mov     [rsp+220h+var_1F0], rax
0x180037036  call    DosGetMessage
0x18003703b  lea     r12, LocaleName
0x180037042  test    ax, ax
0x180037045  jnz     short loc_180037062
0x180037047  lea     r8, [rbp+120h+var_140]
0x18003704b  lea     edx, [r14+51h]
0x18003704f  lea     rcx, [rbp+120h+SourceString]; SourceString
0x180037053  call    NetpCopyStrToWStr
0x180037058  lea     rax, [rbp+120h+SourceString]
0x18003705c  mov     [rbp+120h+var_180], rax
0x180037060  jmp     short loc_180037066
0x180037062  mov     [rbp+120h+var_180], r12
0x180037066  lea     rax, [rbp+120h+var_150]
0x18003706a  mov     qword ptr [rbp+120h+buf], rdi
0x18003706e  xor     r9d, r9d
0x180037071  mov     [rsp+220h+parm_err], rax
0x180037076  xor     r8d, r8d
0x180037079  mov     [rbp+120h+var_188], r14d
0x18003707d  lea     edx, [rbx+2]
0x180037080  mov     [rbp+120h+var_178], r15d
0x180037084  lea     rcx, [rsp+220h+var_1C8]
0x180037089  mov     [rbp+120h+var_174], 0FFFFFFFFh
0x180037090  mov     [rbp+120h+var_160], r12
0x180037094  call    NetpCreateSecurityDescriptor
0x180037099  mov     ebx, eax
0x18003709b  test    eax, eax
0x18003709d  jns     short loc_1800370C2
0x18003709f  mov     r9d, eax
0x1800370a2  lea     rdx, aWsShareCannotC; "'%ws' share: Cannot create security des"...
0x1800370a9  mov     r8, rsi
0x1800370ac  mov     ecx, 100h; unsigned int
0x1800370b1  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800370b6  mov     ecx, ebx; Status
0x1800370b8  call    NetpNtStatusToApiStatus
0x1800370bd  jmp     loc_180037311
0x1800370c2  mov     r12d, 1F6h
0x1800370c8  lea     r8, [rbp+120h+buf]; buf
0x1800370cc  mov     edx, r12d; level
0x1800370cf  xor     r9d, r9d; parm_err
0x1800370d2  xor     ecx, ecx; servername
0x1800370d4  call    cs:__imp_NetShareAdd
0x1800370db  nop     dword ptr [rax+rax+00h]
0x1800370e0  mov     ebx, eax
0x1800370e2  cmp     eax, 846h
0x1800370e7  jnz     loc_1800371C3
0x1800370ed  mov     r8, rdi
0x1800370f0  mov     [rsp+220h+bufptr], r14
0x1800370f5  lea     rdx, aWsShareAlready; "'%ws' share already exists. \n"
0x1800370fc  mov     ecx, r15d; unsigned int
0x1800370ff  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180037104  lea     r9, [rsp+220h+bufptr]; bufptr
0x180037109  mov     r8d, 2; level
0x18003710f  mov     rdx, rdi; netname
0x180037112  xor     ecx, ecx; servername
0x180037114  call    cs:__imp_NetShareGetInfo
0x18003711b  nop     dword ptr [rax+rax+00h]
0x180037120  mov     ebx, eax
0x180037122  test    eax, eax
0x180037124  jnz     loc_1800371B4
0x18003712a  mov     r9, [rsp+220h+bufptr]
0x18003712f  lea     rdx, aWsShareCurrent; "'%ws' share current path is %ws\n"
0x180037136  mov     r8, rdi
0x180037139  mov     ecx, r15d; unsigned int
0x18003713c  mov     r9, [r9+28h]
0x180037140  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180037145  mov     rdx, [rsp+220h+bufptr]
0x18003714a  xor     r9d, r9d
0x18003714d  xor     r8d, r8d
0x180037150  mov     rcx, rsi
0x180037153  mov     rdx, [rdx+28h]
0x180037157  call    cs:__imp_NetpwPathCompare
0x18003715e  nop     dword ptr [rax+rax+00h]
0x180037163  test    eax, eax
0x180037165  jz      short loc_1800371B4
0x180037167  xor     r8d, r8d; reserved
0x18003716a  mov     rdx, rdi; netname
0x18003716d  xor     ecx, ecx; servername
0x18003716f  call    cs:__imp_NetShareDel
0x180037176  nop     dword ptr [rax+rax+00h]
0x18003717b  mov     ebx, eax
0x18003717d  test    eax, eax
0x18003717f  jnz     short loc_1800371B4
0x180037181  xor     r9d, r9d; parm_err
0x180037184  lea     r8, [rbp+120h+buf]; buf
0x180037188  mov     edx, r12d; level
0x18003718b  xor     ecx, ecx; servername
0x18003718d  call    cs:__imp_NetShareAdd
0x180037194  nop     dword ptr [rax+rax+00h]
0x180037199  mov     ebx, eax
0x18003719b  test    eax, eax
0x18003719d  jnz     short loc_1800371B4
0x18003719f  mov     r9, rsi
0x1800371a2  lea     rdx, aWsShareWasRecr; "'%ws' share was recreated with new path"...
0x1800371a9  mov     r8, rdi
0x1800371ac  mov     ecx, r15d; unsigned int
0x1800371af  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800371b4  mov     rcx, [rsp+220h+bufptr]
0x1800371b9  test    rcx, rcx
0x1800371bc  jz      short loc_1800371C3
0x1800371be  call    NetpMemoryFree
0x1800371c3  cmp     cs:?NlGlobalMemberWorkstation@@3HA, r14d; int NlGlobalMemberWorkstation
0x1800371ca  jnz     short loc_1800371E9
0x1800371cc  test    ebx, ebx
0x1800371ce  jz      short loc_1800371E9
0x1800371d0  mov     r8d, 159Eh; unsigned int
0x1800371d6  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800371dd  lea     rcx, aNetstatusNerrS; "NetStatus == NERR_Success"
0x1800371e4  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800371e9  mov     rcx, [rbp+120h+var_150]
0x1800371ed  call    NetpMemoryFree
0x1800371f2  test    ebx, ebx
0x1800371f4  jz      short loc_180037214
0x1800371f6  mov     r9d, ebx
0x1800371f9  lea     rdx, aWsShareErrorAt; "'%ws' share: Error attempting to create"...
0x180037200  mov     r8, rdi
0x180037203  mov     ecx, 100h; unsigned int
0x180037208  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003720d  mov     eax, ebx
0x18003720f  jmp     loc_180037311
0x180037214  mov     r12d, 3EDh
0x18003721a  lea     r9, [rsp+220h+var_1E0]; bufptr
0x18003721f  mov     r8d, r12d; level
0x180037222  mov     rdx, rdi; netname
0x180037225  xor     ecx, ecx; servername
0x180037227  call    cs:__imp_NetShareGetInfo
0x18003722e  nop     dword ptr [rax+rax+00h]
0x180037233  mov     esi, eax
0x180037235  test    eax, eax
0x180037237  jz      short loc_180037255
0x180037239  mov     r9d, eax
0x18003723c  lea     rdx, aNlcreateshareN; "NlCreateShare: NetShareGetInfo (1005) f"...
0x180037243  mov     r8, rdi
0x180037246  mov     ecx, 100h; unsigned int
0x18003724b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180037250  jmp     loc_18003730F
0x180037255  mov     rcx, [rsp+220h+var_1E0]
0x18003725a  mov     ebx, [rcx]
0x18003725c  mov     eax, ebx
0x18003725e  and     eax, 100h
0x180037263  cmp     [rbp+120h+arg_20], r14d
0x18003726a  jz      short loc_180037278
0x18003726c  test    eax, eax
0x18003726e  mov     eax, ebx
0x180037270  jz      short loc_180037289
0x180037272  btr     eax, 8
0x180037276  jmp     short loc_180037282
0x180037278  test    eax, eax
0x18003727a  mov     eax, ebx
0x18003727c  jnz     short loc_180037289
0x18003727e  bts     eax, 8
0x180037282  mov     [rcx], eax
0x180037284  mov     rcx, [rsp+220h+var_1E0]
0x180037289  bts     eax, 0Ch
0x18003728d  mov     [rcx], eax
0x18003728f  cmp     ebx, eax
0x180037291  jz      short loc_1800372F9
0x180037293  mov     r9, [rsp+220h+var_1E0]; buf
0x180037298  mov     r8d, r12d; level
0x18003729b  mov     rdx, rdi; netname
0x18003729e  mov     [rsp+220h+parm_err], r14; parm_err
0x1800372a3  xor     ecx, ecx; servername
0x1800372a5  call    cs:__imp_NetShareSetInfo
0x1800372ac  nop     dword ptr [rax+rax+00h]
0x1800372b1  mov     r9d, ebx
0x1800372b4  mov     r8, rdi
0x1800372b7  mov     esi, eax
0x1800372b9  test    eax, eax
0x1800372bb  jnz     short loc_1800372D9
0x1800372bd  mov     rax, [rsp+220h+var_1E0]
0x1800372c2  mov     ecx, r15d; unsigned int
0x1800372c5  mov     edx, [rax]
0x1800372c7  mov     dword ptr [rsp+220h+parm_err], edx
0x1800372cb  lea     rdx, aNlcreateshareS; "NlCreateShare: Share '%ws' updated succ"...
0x1800372d2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800372d7  jmp     short loc_1800372F9
0x1800372d9  mov     [rsp+220h+var_1F8], eax
0x1800372dd  lea     rdx, aNlcreateshareF; "NlCreateShare: Failed to update share '"...
0x1800372e4  mov     rax, [rsp+220h+var_1E0]
0x1800372e9  mov     ecx, [rax]
0x1800372eb  mov     dword ptr [rsp+220h+parm_err], ecx
0x1800372ef  mov     ecx, 100h; unsigned int
0x1800372f4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800372f9  mov     rcx, [rsp+220h+var_1E0]; Buffer
0x1800372fe  test    rcx, rcx
0x180037301  jz      short loc_18003730F
0x180037303  call    cs:__imp_NetApiBufferFree
0x18003730a  nop     dword ptr [rax+rax+00h]
0x18003730f  mov     eax, esi
0x180037311  mov     rcx, [rbp+120h+var_30]
0x180037318  xor     rcx, rsp; StackCookie
0x18003731b  call    __security_check_cookie
0x180037320  lea     r11, [rsp+220h+var_20]
0x180037328  mov     rbx, [r11+40h]
0x18003732c  mov     rsi, [r11+48h]
0x180037330  mov     rsp, r11
0x180037333  pop     r15
0x180037335  pop     r14
0x180037337  pop     r12
0x180037339  pop     rdi
0x18003733a  pop     rbp
0x18003733b  retn
```
