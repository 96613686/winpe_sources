# NlCreateShare(ushort *,ushort *,uchar,int,int,ulong)

- ea: `0x180034fa8`
- end: `0x180035360`
- name: `?NlCreateShare@@YAKPEAG0EHHK@Z`
- size: `952`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, char, __int64, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18006e0ec`

## callees

- `0x180003670`
- `0x180007278`
- `0x180007b50`
- `0x18000d710`
- `0x18000e270`
- `0x18000ed34`
- `0x180034fa8`
- `0x18008733c`
- `0x180087cbc`
- `0x180088008`

## import_xrefs

- `netutils!NetApiBufferFree` at `0x18003532d`
- `netutils!NetApiBufferFree` at `0x18003532d`
- `netutils!NetpwPathCompare` at `0x18003519f`
- `netutils!NetpwPathCompare` at `0x18003519f`
- `srvcli!NetShareDel` at `0x1800351b1`
- `srvcli!NetShareDel` at `0x1800351b1`
- `srvcli!NetShareSetInfo` at `0x1800352d5`
- `srvcli!NetShareSetInfo` at `0x1800352d5`
- `srvcli!NetShareGetInfo` at `0x180035166`
- `srvcli!NetShareGetInfo` at `0x18003525d`
- `srvcli!NetShareGetInfo` at `0x180035166`
- `srvcli!NetShareGetInfo` at `0x18003525d`
- `srvcli!NetShareAdd` at `0x18003512c`
- `srvcli!NetShareAdd` at `0x1800351c9`
- `srvcli!NetShareAdd` at `0x18003512c`
- `srvcli!NetShareAdd` at `0x1800351c9`

## string_xrefs

- `0x18003520c`: `onecore\ds\netapi\svcdlls\logonsrv\server\lsrvutil.cxx`
- `0x1800350fa`: `'%ws' share: Cannot create security descriptor 0x%lx\n`
- `0x180035147`: `'%ws' share already exists. \n`
- `0x180035177`: `'%ws' share current path is %ws\n`
- `0x1800351d8`: `'%ws' share was recreated with new path %ws\n`
- `0x18003522f`: `'%ws' share: Error attempting to create-share: %ld\n`
- `0x18003526c`: `NlCreateShare: NetShareGetInfo (1005) failed for share '%ws': %lu\n`
- `0x1800352f5`: `NlCreateShare: Share '%ws' updated successfully flags 0x%lx 0x%lx\n`
- `0x180035307`: `NlCreateShare: Failed to update share '%ws' flags 0x%lx 0x%lx: 0x%lx\n`

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
      5527,
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
0x180034fa8  mov     [rsp-8+arg_10], rbx
0x180034fad  mov     [rsp-8+arg_18], rsi
0x180034fb2  push    rbp
0x180034fb3  push    rdi
0x180034fb4  push    r12
0x180034fb6  push    r14
0x180034fb8  push    r15
0x180034fba  lea     rbp, [rsp-100h]
0x180034fc2  sub     rsp, 200h
0x180034fc9  mov     rax, cs:__security_cookie
0x180034fd0  xor     rax, rsp
0x180034fd3  mov     [rbp+120h+var_30], rax
0x180034fda  mov     rdi, rdx
0x180034fdd  mov     bl, r8b
0x180034fe0  xor     edx, edx; Val
0x180034fe2  mov     rsi, rcx
0x180034fe5  lea     rcx, [rbp+120h+buf]; void *
0x180034fe9  lea     r8d, [rdx+48h]; Size
0x180034fed  call    memset_0
0x180034ff2  xor     r14d, r14d
0x180034ff5  mov     [rsp+220h+var_1C4], 0A0000000h
0x180034ffd  mov     ecx, 10000000h
0x180035002  mov     [rsp+220h+var_1E0], r14
0x180035007  lea     rax, WorldSid
0x18003500e  mov     [rsp+220h+var_1B4], ecx
0x180035012  mov     [rsp+220h+var_1C0], rax
0x180035017  lea     rdx, aWsShareIsToWs; "'%ws' share is to '%ws'\n"
0x18003501e  lea     rax, AliasAdminsSid
0x180035025  mov     [rsp+220h+var_1A4], ecx
0x180035029  neg     bl
0x18003502b  mov     [rsp+220h+var_1B0], rax
0x180035030  lea     rax, AuthenticatedUserSid
0x180035037  mov     [rsp+220h+var_1D8], r14w
0x18003503d  sbb     ebx, ebx
0x18003503f  mov     [rbp+120h+var_1A0], rax
0x180035043  lea     r15d, [r14+1]
0x180035047  mov     [rsp+220h+var_1C8], r14w
0x18003504d  mov     r9, rsi
0x180035050  mov     [rsp+220h+var_1C6], r14b
0x180035055  mov     r8, rdi
0x180035058  mov     [rsp+220h+var_1B8], r14w
0x18003505e  mov     ecx, r15d; unsigned int
0x180035061  mov     [rsp+220h+var_1B6], r14b
0x180035066  mov     [rsp+220h+var_1A8], r14w
0x18003506c  neg     ebx
0x18003506e  mov     [rsp+220h+var_1A6], r14b
0x180035073  mov     [rbp+120h+var_168], rsi
0x180035077  mov     [rbp+120h+var_150], r14
0x18003507b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180035080  lea     rax, [rsp+220h+var_1D8]
0x180035085  lea     r8, [rbp+120h+var_140]
0x180035089  mov     [rsp+220h+var_1F0], rax
0x18003508e  call    DosGetMessage
0x180035093  lea     r12, LocaleName
0x18003509a  test    ax, ax
0x18003509d  jnz     short loc_1800350BA
0x18003509f  lea     r8, [rbp+120h+var_140]
0x1800350a3  lea     edx, [r14+51h]
0x1800350a7  lea     rcx, [rbp+120h+SourceString]; SourceString
0x1800350ab  call    NetpCopyStrToWStr
0x1800350b0  lea     rax, [rbp+120h+SourceString]
0x1800350b4  mov     [rbp+120h+var_180], rax
0x1800350b8  jmp     short loc_1800350BE
0x1800350ba  mov     [rbp+120h+var_180], r12
0x1800350be  lea     rax, [rbp+120h+var_150]
0x1800350c2  mov     qword ptr [rbp+120h+buf], rdi
0x1800350c6  xor     r9d, r9d
0x1800350c9  mov     [rsp+220h+parm_err], rax
0x1800350ce  xor     r8d, r8d
0x1800350d1  mov     [rbp+120h+var_188], r14d
0x1800350d5  lea     edx, [rbx+2]
0x1800350d8  mov     [rbp+120h+var_178], r15d
0x1800350dc  lea     rcx, [rsp+220h+var_1C8]
0x1800350e1  mov     [rbp+120h+var_174], 0FFFFFFFFh
0x1800350e8  mov     [rbp+120h+var_160], r12
0x1800350ec  call    NetpCreateSecurityDescriptor
0x1800350f1  mov     ebx, eax
0x1800350f3  test    eax, eax
0x1800350f5  jns     short loc_18003511A
0x1800350f7  mov     r9d, eax
0x1800350fa  lea     rdx, aWsShareCannotC; "'%ws' share: Cannot create security des"...
0x180035101  mov     r8, rsi
0x180035104  mov     ecx, 100h; unsigned int
0x180035109  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003510e  mov     ecx, ebx; Status
0x180035110  call    NetpNtStatusToApiStatus
0x180035115  jmp     loc_180035335
0x18003511a  mov     r12d, 1F6h
0x180035120  lea     r8, [rbp+120h+buf]; buf
0x180035124  mov     edx, r12d; level
0x180035127  xor     r9d, r9d; parm_err
0x18003512a  xor     ecx, ecx; servername
0x18003512c  call    cs:__imp_NetShareAdd
0x180035132  mov     ebx, eax
0x180035134  cmp     eax, 846h
0x180035139  jnz     loc_1800351F9
0x18003513f  mov     r8, rdi
0x180035142  mov     [rsp+220h+bufptr], r14
0x180035147  lea     rdx, aWsShareAlready; "'%ws' share already exists. \n"
0x18003514e  mov     ecx, r15d; unsigned int
0x180035151  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180035156  lea     r9, [rsp+220h+bufptr]; bufptr
0x18003515b  mov     r8d, 2; level
0x180035161  mov     rdx, rdi; netname
0x180035164  xor     ecx, ecx; servername
0x180035166  call    cs:__imp_NetShareGetInfo
0x18003516c  mov     ebx, eax
0x18003516e  test    eax, eax
0x180035170  jnz     short loc_1800351EA
0x180035172  mov     r9, [rsp+220h+bufptr]
0x180035177  lea     rdx, aWsShareCurrent; "'%ws' share current path is %ws\n"
0x18003517e  mov     r8, rdi
0x180035181  mov     ecx, r15d; unsigned int
0x180035184  mov     r9, [r9+28h]
0x180035188  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18003518d  mov     rdx, [rsp+220h+bufptr]
0x180035192  xor     r9d, r9d
0x180035195  xor     r8d, r8d
0x180035198  mov     rcx, rsi
0x18003519b  mov     rdx, [rdx+28h]
0x18003519f  call    cs:__imp_NetpwPathCompare
0x1800351a5  test    eax, eax
0x1800351a7  jz      short loc_1800351EA
0x1800351a9  xor     r8d, r8d; reserved
0x1800351ac  mov     rdx, rdi; netname
0x1800351af  xor     ecx, ecx; servername
0x1800351b1  call    cs:__imp_NetShareDel
0x1800351b7  mov     ebx, eax
0x1800351b9  test    eax, eax
0x1800351bb  jnz     short loc_1800351EA
0x1800351bd  xor     r9d, r9d; parm_err
0x1800351c0  lea     r8, [rbp+120h+buf]; buf
0x1800351c4  mov     edx, r12d; level
0x1800351c7  xor     ecx, ecx; servername
0x1800351c9  call    cs:__imp_NetShareAdd
0x1800351cf  mov     ebx, eax
0x1800351d1  test    eax, eax
0x1800351d3  jnz     short loc_1800351EA
0x1800351d5  mov     r9, rsi
0x1800351d8  lea     rdx, aWsShareWasRecr; "'%ws' share was recreated with new path"...
0x1800351df  mov     r8, rdi
0x1800351e2  mov     ecx, r15d; unsigned int
0x1800351e5  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800351ea  mov     rcx, [rsp+220h+bufptr]
0x1800351ef  test    rcx, rcx
0x1800351f2  jz      short loc_1800351F9
0x1800351f4  call    NetpMemoryFree
0x1800351f9  cmp     cs:?NlGlobalMemberWorkstation@@3HA, r14d; int NlGlobalMemberWorkstation
0x180035200  jnz     short loc_18003521F
0x180035202  test    ebx, ebx
0x180035204  jz      short loc_18003521F
0x180035206  mov     r8d, 1597h; unsigned int
0x18003520c  lea     rdx, aOnecoreDsNetap_13; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180035213  lea     rcx, aNetstatusNerrS; "NetStatus == NERR_Success"
0x18003521a  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18003521f  mov     rcx, [rbp+120h+var_150]
0x180035223  call    NetpMemoryFree
0x180035228  test    ebx, ebx
0x18003522a  jz      short loc_18003524A
0x18003522c  mov     r9d, ebx
0x18003522f  lea     rdx, aWsShareErrorAt; "'%ws' share: Error attempting to create"...
0x180035236  mov     r8, rdi
0x180035239  mov     ecx, 100h; unsigned int
0x18003523e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180035243  mov     eax, ebx
0x180035245  jmp     loc_180035335
0x18003524a  mov     r12d, 3EDh
0x180035250  lea     r9, [rsp+220h+var_1E0]; bufptr
0x180035255  mov     r8d, r12d; level
0x180035258  mov     rdx, rdi; netname
0x18003525b  xor     ecx, ecx; servername
0x18003525d  call    cs:__imp_NetShareGetInfo
0x180035263  mov     esi, eax
0x180035265  test    eax, eax
0x180035267  jz      short loc_180035285
0x180035269  mov     r9d, eax
0x18003526c  lea     rdx, aNlcreateshareN; "NlCreateShare: NetShareGetInfo (1005) f"...
0x180035273  mov     r8, rdi
0x180035276  mov     ecx, 100h; unsigned int
0x18003527b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180035280  jmp     loc_180035333
0x180035285  mov     rcx, [rsp+220h+var_1E0]
0x18003528a  mov     ebx, [rcx]
0x18003528c  mov     eax, ebx
0x18003528e  and     eax, 100h
0x180035293  cmp     [rbp+120h+arg_20], r14d
0x18003529a  jz      short loc_1800352A8
0x18003529c  test    eax, eax
0x18003529e  mov     eax, ebx
0x1800352a0  jz      short loc_1800352B9
0x1800352a2  btr     eax, 8
0x1800352a6  jmp     short loc_1800352B2
0x1800352a8  test    eax, eax
0x1800352aa  mov     eax, ebx
0x1800352ac  jnz     short loc_1800352B9
0x1800352ae  bts     eax, 8
0x1800352b2  mov     [rcx], eax
0x1800352b4  mov     rcx, [rsp+220h+var_1E0]
0x1800352b9  bts     eax, 0Ch
0x1800352bd  mov     [rcx], eax
0x1800352bf  cmp     ebx, eax
0x1800352c1  jz      short loc_180035323
0x1800352c3  mov     r9, [rsp+220h+var_1E0]; buf
0x1800352c8  mov     r8d, r12d; level
0x1800352cb  mov     rdx, rdi; netname
0x1800352ce  mov     [rsp+220h+parm_err], r14; parm_err
0x1800352d3  xor     ecx, ecx; servername
0x1800352d5  call    cs:__imp_NetShareSetInfo
0x1800352db  mov     r9d, ebx
0x1800352de  mov     r8, rdi
0x1800352e1  mov     esi, eax
0x1800352e3  test    eax, eax
0x1800352e5  jnz     short loc_180035303
0x1800352e7  mov     rax, [rsp+220h+var_1E0]
0x1800352ec  mov     ecx, r15d; unsigned int
0x1800352ef  mov     edx, [rax]
0x1800352f1  mov     dword ptr [rsp+220h+parm_err], edx
0x1800352f5  lea     rdx, aNlcreateshareS; "NlCreateShare: Share '%ws' updated succ"...
0x1800352fc  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180035301  jmp     short loc_180035323
0x180035303  mov     [rsp+220h+var_1F8], eax
0x180035307  lea     rdx, aNlcreateshareF; "NlCreateShare: Failed to update share '"...
0x18003530e  mov     rax, [rsp+220h+var_1E0]
0x180035313  mov     ecx, [rax]
0x180035315  mov     dword ptr [rsp+220h+parm_err], ecx
0x180035319  mov     ecx, 100h; unsigned int
0x18003531e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180035323  mov     rcx, [rsp+220h+var_1E0]; Buffer
0x180035328  test    rcx, rcx
0x18003532b  jz      short loc_180035333
0x18003532d  call    cs:__imp_NetApiBufferFree
0x180035333  mov     eax, esi
0x180035335  mov     rcx, [rbp+120h+var_30]
0x18003533c  xor     rcx, rsp; StackCookie
0x18003533f  call    __security_check_cookie
0x180035344  lea     r11, [rsp+220h+var_20]
0x18003534c  mov     rbx, [r11+40h]
0x180035350  mov     rsi, [r11+48h]
0x180035354  mov     rsp, r11
0x180035357  pop     r15
0x180035359  pop     r14
0x18003535b  pop     r12
0x18003535d  pop     rdi
0x18003535e  pop     rbp
0x18003535f  retn
```
