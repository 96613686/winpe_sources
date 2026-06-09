# appIsolation::AppContainerDatabase::GetLoopbackDebuggedAppContainersSD(_SECURITY_DESCRIPTOR * *,int)

- ea: `0x1800baf00`
- end: `0x1800bb3ba`
- name: `?GetLoopbackDebuggedAppContainersSD@AppContainerDatabase@appIsolation@@QEAAJPEAPEAU_SECURITY_DESCRIPTOR@@H@Z`
- size: `1210`
- prototype: `__int64 __fastcall(appIsolation::AppContainerDatabase *__hidden this, struct _SECURITY_DESCRIPTOR **, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180028084`

## callees

- `0x18000a710`
- `0x180056008`
- `0x1800729c0`
- `0x1800baf00`

## import_xrefs

- `ntdll!RtlIsCapabilitySid` at `0x1800bb170`
- `ntdll!RtlIsCapabilitySid` at `0x1800bb170`
- `ntdll!RtlEqualSid` at `0x1800bb154`
- `ntdll!RtlEqualSid` at `0x1800bb154`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bafc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb02b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bafc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bb02b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bb355`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bb366`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bb355`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bb366`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800bafb9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800bb01b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800bafb9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800bb01b`
- `api-ms-win-security-trustee-l1-1-0!BuildSecurityDescriptorW` at `0x1800bb28b`
- `api-ms-win-security-trustee-l1-1-0!BuildSecurityDescriptorW` at `0x1800bb28b`
- `fwbase!FwAlloc` at `0x1800bb086`
- `fwbase!FwAlloc` at `0x1800bb086`
- `fwbase!FwCriticalSectionEnter` at `0x1800baf5a`
- `fwbase!FwCriticalSectionEnter` at `0x1800baf5a`
- `fwbase!FwCriticalSectionLeave` at `0x1800bb344`
- `fwbase!FwCriticalSectionLeave` at `0x1800bb344`
- `fwbase!FwFree` at `0x1800bb325`
- `fwbase!FwFree` at `0x1800bb375`
- `fwbase!FwFree` at `0x1800bb325`
- `fwbase!FwFree` at `0x1800bb375`

## pseudocode

```c
__int64 __fastcall appIsolation::AppContainerDatabase::GetLoopbackDebuggedAppContainersSD(
        appIsolation::AppContainerDatabase *this,
        struct _SECURITY_DESCRIPTOR **a2,
        int a3)
{
  struct _SECURITY_DESCRIPTOR **v5; // r14
  struct _EXPLICIT_ACCESS_W *v6; // rbp
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  signed int v11; // eax
  signed int LastError; // eax
  __int64 v13; // rsi
  unsigned int v14; // r15d
  __int64 v15; // rcx
  __int64 v16; // r12
  _DWORD *v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  signed int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rdx
  unsigned int i; // edi
  LPWCH ptstrName; // rcx
  char *v27; // [rsp+58h] [rbp-70h]
  PSECURITY_DESCRIPTOR pNewSD; // [rsp+60h] [rbp-68h] BYREF
  PSID Sid; // [rsp+68h] [rbp-60h] BYREF
  PSID hMem; // [rsp+70h] [rbp-58h] BYREF
  ULONG pSizeNewSD; // [rsp+78h] [rbp-50h] BYREF

  pSizeNewSD = 0;
  pNewSD = 0;
  Sid = 0;
  hMem = 0;
  v5 = a2;
  *a2 = 0;
  v6 = 0;
  v27 = (char *)this + 24;
  FwCriticalSectionEnter((char *)this + 24);
  if ( !*((_DWORD *)this + 2) )
  {
    v7 = 0;
    v8 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v9 = 19;
      v10 = 0;
LABEL_5:
      WPP_SF_d(*(_QWORD *)(v8 + 16), v9, WPP_202f566a5b6b3eebbc58311978cd75bc_Traceguids, v10);
      goto LABEL_53;
    }
    goto LABEL_53;
  }
  if ( ConvertStringSidToSidW(L"WD", &Sid) )
  {
    if ( !ConvertStringSidToSidW(L"AN", &hMem) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v9 = 21;
        v10 = v7;
        goto LABEL_5;
      }
      goto LABEL_53;
    }
    v6 = (struct _EXPLICIT_ACCESS_W *)FwAlloc(48LL * (unsigned int)(2 * *((_DWORD *)this + 2) + 2));
    if ( !v6 )
    {
      v7 = -2147024882;
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v9 = 22;
        v10 = 2147942414LL;
        goto LABEL_5;
      }
      goto LABEL_53;
    }
    LODWORD(v13) = 0;
    v7 = 0;
    v14 = 0;
    if ( *((_DWORD *)this + 2) == -2 )
    {
LABEL_37:
      v6->Trustee.ptstrName = (LPWCH)Sid;
      v6[1].Trustee.ptstrName = (LPWCH)hMem;
      if ( !a3 || (unsigned int)v13 > 2 )
      {
        v20 = BuildSecurityDescriptorW(0, 0, v13, v6, 0, 0, 0, &pSizeNewSD, &pNewSD);
        v7 = v20;
        if ( v20 > 0 )
          v7 = (unsigned __int16)v20 | 0x80070000;
        if ( (v7 & 0x80000000) == 0 )
        {
          *v5 = (struct _SECURITY_DESCRIPTOR *)pNewSD;
          pNewSD = 0;
        }
        else
        {
          v21 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v22 = 24;
            goto LABEL_48;
          }
        }
      }
LABEL_49:
      for ( i = 0; i < (unsigned int)v13; ++i )
      {
        ptstrName = v6[i].Trustee.ptstrName;
        if ( *((_DWORD *)ptstrName + 2) == 3 )
          FwFree(ptstrName);
      }
      goto LABEL_53;
    }
    while ( 1 )
    {
      v15 = (unsigned int)v13;
      v6[v15].grfAccessMode = GRANT_ACCESS;
      v16 = (unsigned int)v13;
      v6[v16].grfAccessPermissions = 1;
      v6[v15].grfInheritance = 4;
      v6[v15].Trustee.pMultipleTrustee = 0;
      *(_QWORD *)&v6[v15].Trustee.MultipleTrusteeOperation = 0;
      v6[v15].Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
      if ( v14 >= 2 )
      {
        if ( RtlEqualSid(::Sid, *(PSID *)(*((_QWORD *)this + 2) + 16LL * (v14 - 2))) == 1
          || (unsigned __int8)RtlIsCapabilitySid(*(_QWORD *)(*((_QWORD *)this + 2) + 16LL * (v14 - 2))) == 1
          || a3 && (*(_BYTE *)(*((_QWORD *)this + 2) + 16LL * (v14 - 2) + 8) & 1) == 0 )
        {
          goto LABEL_35;
        }
        v17 = *(_DWORD **)(*((_QWORD *)this + 2) + 16LL * (v14 - 2));
        if ( v17[2] == 2 )
        {
          v18 = FwSidCopy(v17);
          v7 = v18;
          if ( v18 > 0 )
            v7 = (unsigned __int16)v18 | 0x80070000;
          if ( (v7 & 0x80000000) != 0 )
          {
            v21 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v22 = 23;
LABEL_48:
              WPP_SF_d(*(_QWORD *)(v21 + 16), v22, WPP_202f566a5b6b3eebbc58311978cd75bc_Traceguids, v7);
            }
            goto LABEL_49;
          }
          v13 = (unsigned int)(v13 + 1);
          *((_DWORD *)v6[v16].Trustee.ptstrName + 2) = 3;
          v19 = v13;
          v6[v19].grfAccessPermissions = 1;
          v6[v19].grfAccessMode = GRANT_ACCESS;
          v6[v19].grfInheritance = 4;
          v6[v19].Trustee.pMultipleTrustee = 0;
          *(_QWORD *)&v6[v19].Trustee.MultipleTrusteeOperation = 0;
          v6[v19].Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
        }
        v6[(unsigned int)v13].Trustee.ptstrName = *(LPWCH *)(*((_QWORD *)this + 2) + 16LL * (v14 - 2));
      }
      LODWORD(v13) = v13 + 1;
LABEL_35:
      if ( ++v14 >= *((_DWORD *)this + 2) + 2 )
      {
        v5 = a2;
        goto LABEL_37;
      }
    }
  }
  v11 = GetLastError();
  v7 = v11;
  if ( v11 > 0 )
    v7 = (unsigned __int16)v11 | 0x80070000;
  v8 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v9 = 20;
    v10 = v7;
    goto LABEL_5;
  }
LABEL_53:
  FwCriticalSectionLeave(v27);
  LocalFree(Sid);
  LocalFree(hMem);
  FwFree(v6);
  return v7;
}

```

## disassembly

```asm
0x1800baf00  push    rbx
0x1800baf02  push    rbp
0x1800baf03  push    rdi
0x1800baf04  push    r12
0x1800baf06  push    r13
0x1800baf08  push    r14
0x1800baf0a  sub     rsp, 98h
0x1800baf11  mov     rax, cs:__security_cookie
0x1800baf18  xor     rax, rsp
0x1800baf1b  mov     [rsp+0C8h+var_48], rax
0x1800baf23  xor     r12d, r12d
0x1800baf26  mov     [rsp+0C8h+var_78], rdx
0x1800baf2b  lea     rax, [rcx+18h]
0x1800baf2f  mov     [rsp+0C8h+var_50], r12d
0x1800baf34  mov     rdi, rcx
0x1800baf37  mov     [rsp+0C8h+var_68], r12
0x1800baf3c  mov     rcx, rax
0x1800baf3f  mov     [rsp+0C8h+Sid], r12
0x1800baf44  mov     r13d, r8d
0x1800baf47  mov     [rsp+0C8h+hMem], r12
0x1800baf4c  mov     r14, rdx
0x1800baf4f  mov     [rdx], r12
0x1800baf52  mov     ebp, r12d
0x1800baf55  mov     [rsp+0C8h+var_70], rax
0x1800baf5a  call    cs:__imp_FwCriticalSectionEnter
0x1800baf61  nop     dword ptr [rax+rax+00h]
0x1800baf66  cmp     [rdi+8], r12d
0x1800baf6a  jnz     short loc_1800BAFAD
0x1800baf6c  mov     ebx, r12d
0x1800baf6f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800baf76  lea     rax, WPP_GLOBAL_Control
0x1800baf7d  cmp     rcx, rax
0x1800baf80  jz      loc_1800BB33F
0x1800baf86  test    byte ptr [rcx+1Ch], 1
0x1800baf8a  jz      loc_1800BB33F
0x1800baf90  mov     edx, 13h
0x1800baf95  xor     r9d, r9d
0x1800baf98  mov     rcx, [rcx+10h]
0x1800baf9c  lea     r8, WPP_202f566a5b6b3eebbc58311978cd75bc_Traceguids
0x1800bafa3  call    WPP_SF_d
0x1800bafa8  jmp     loc_1800BB33F
0x1800bafad  lea     rdx, [rsp+0C8h+Sid]; Sid
0x1800bafb2  lea     rcx, aWd; "WD"
0x1800bafb9  call    cs:__imp_ConvertStringSidToSidW
0x1800bafc0  nop     dword ptr [rax+rax+00h]
0x1800bafc5  test    eax, eax
0x1800bafc7  jnz     short loc_1800BB00F
0x1800bafc9  call    cs:__imp_GetLastError
0x1800bafd0  nop     dword ptr [rax+rax+00h]
0x1800bafd5  mov     ebx, eax
0x1800bafd7  test    eax, eax
0x1800bafd9  jle     short loc_1800BAFE4
0x1800bafdb  movzx   ebx, ax
0x1800bafde  or      ebx, 80070000h
0x1800bafe4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bafeb  lea     rax, WPP_GLOBAL_Control
0x1800baff2  cmp     rcx, rax
0x1800baff5  jz      loc_1800BB33F
0x1800baffb  test    byte ptr [rcx+1Ch], 1
0x1800bafff  jz      loc_1800BB33F
0x1800bb005  mov     edx, 14h
0x1800bb00a  mov     r9d, ebx
0x1800bb00d  jmp     short loc_1800BAF98
0x1800bb00f  lea     rdx, [rsp+0C8h+hMem]; Sid
0x1800bb014  lea     rcx, aAn; "AN"
0x1800bb01b  call    cs:__imp_ConvertStringSidToSidW
0x1800bb022  nop     dword ptr [rax+rax+00h]
0x1800bb027  test    eax, eax
0x1800bb029  jnz     short loc_1800BB074
0x1800bb02b  call    cs:__imp_GetLastError
0x1800bb032  nop     dword ptr [rax+rax+00h]
0x1800bb037  mov     ebx, eax
0x1800bb039  test    eax, eax
0x1800bb03b  jle     short loc_1800BB046
0x1800bb03d  movzx   ebx, ax
0x1800bb040  or      ebx, 80070000h
0x1800bb046  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bb04d  lea     rax, WPP_GLOBAL_Control
0x1800bb054  cmp     rcx, rax
0x1800bb057  jz      loc_1800BB33F
0x1800bb05d  test    byte ptr [rcx+1Ch], 1
0x1800bb061  jz      loc_1800BB33F
0x1800bb067  mov     edx, 15h
0x1800bb06c  mov     r9d, ebx
0x1800bb06f  jmp     loc_1800BAF98
0x1800bb074  mov     eax, [rdi+8]
0x1800bb077  lea     eax, ds:2[rax*2]
0x1800bb07e  lea     rcx, [rax+rax*2]
0x1800bb082  shl     rcx, 4
0x1800bb086  call    cs:__imp_FwAlloc
0x1800bb08d  nop     dword ptr [rax+rax+00h]
0x1800bb092  mov     rbp, rax
0x1800bb095  test    rax, rax
0x1800bb098  jnz     short loc_1800BB0CD
0x1800bb09a  mov     ebx, 8007000Eh
0x1800bb09f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bb0a6  lea     rax, WPP_GLOBAL_Control
0x1800bb0ad  cmp     rcx, rax
0x1800bb0b0  jz      loc_1800BB33F
0x1800bb0b6  test    byte ptr [rcx+1Ch], 1
0x1800bb0ba  jz      loc_1800BB33F
0x1800bb0c0  mov     edx, 16h
0x1800bb0c5  mov     r9d, ebx
0x1800bb0c8  jmp     loc_1800BAF98
0x1800bb0cd  mov     eax, [rdi+8]
0x1800bb0d0  xor     r8d, r8d
0x1800bb0d3  mov     [rsp+0C8h+arg_10], rsi
0x1800bb0db  mov     esi, r8d
0x1800bb0de  mov     [rsp+0C8h+var_38], r15
0x1800bb0e6  mov     ebx, r8d
0x1800bb0e9  mov     r15d, r8d
0x1800bb0ec  add     eax, 2
0x1800bb0ef  jz      loc_1800BB23E
0x1800bb0f5  mov     eax, esi
0x1800bb0f7  lea     rcx, [rax+rax*2]
0x1800bb0fb  add     rcx, rcx
0x1800bb0fe  mov     dword ptr [rbp+rcx*8+4], 1
0x1800bb106  lea     r12, ds:0[rcx*8]
0x1800bb10e  mov     dword ptr [r12+rbp], 1
0x1800bb116  mov     dword ptr [rbp+rcx*8+8], 4
0x1800bb11e  mov     [rbp+rcx*8+10h], r8
0x1800bb123  mov     qword ptr [rbp+rcx*8+18h], 0
0x1800bb12c  mov     dword ptr [rbp+rcx*8+20h], 5
0x1800bb134  cmp     r15d, 2
0x1800bb138  jb      loc_1800BB222
0x1800bb13e  mov     rdx, [rdi+10h]
0x1800bb142  lea     r14d, [r15-2]
0x1800bb146  mov     rcx, cs:Sid; Sid1
0x1800bb14d  add     r14, r14
0x1800bb150  mov     rdx, [rdx+r14*8]; Sid2
0x1800bb154  call    cs:__imp_RtlEqualSid
0x1800bb15b  nop     dword ptr [rax+rax+00h]
0x1800bb160  cmp     al, 1
0x1800bb162  jz      loc_1800BB224
0x1800bb168  mov     rcx, [rdi+10h]
0x1800bb16c  mov     rcx, [rcx+r14*8]
0x1800bb170  call    cs:__imp_RtlIsCapabilitySid
0x1800bb177  nop     dword ptr [rax+rax+00h]
0x1800bb17c  cmp     al, 1
0x1800bb17e  jz      loc_1800BB224
0x1800bb184  test    r13d, r13d
0x1800bb187  jz      short loc_1800BB199
0x1800bb189  mov     rax, [rdi+10h]
0x1800bb18d  test    byte ptr [rax+r14*8+8], 1
0x1800bb193  jz      loc_1800BB224
0x1800bb199  mov     rax, [rdi+10h]
0x1800bb19d  mov     rcx, [rax+r14*8]; SourceSid
0x1800bb1a1  cmp     dword ptr [rcx+8], 2
0x1800bb1a5  jnz     short loc_1800BB20C
0x1800bb1a7  lea     rdx, [rbp+28h]
0x1800bb1ab  add     rdx, r12
0x1800bb1ae  call    FwSidCopy
0x1800bb1b3  mov     ebx, eax
0x1800bb1b5  test    eax, eax
0x1800bb1b7  jle     short loc_1800BB1C2
0x1800bb1b9  movzx   ebx, ax
0x1800bb1bc  or      ebx, 80070000h
0x1800bb1c2  test    ebx, ebx
0x1800bb1c4  js      loc_1800BB2CE
0x1800bb1ca  mov     rax, [r12+rbp+28h]
0x1800bb1cf  inc     esi
0x1800bb1d1  mov     dword ptr [rax+8], 3
0x1800bb1d8  lea     rcx, [rsi+rsi*2]
0x1800bb1dc  add     rcx, rcx
0x1800bb1df  xor     r12d, r12d
0x1800bb1e2  mov     dword ptr [rbp+rcx*8+0], 1
0x1800bb1ea  mov     dword ptr [rbp+rcx*8+4], 1
0x1800bb1f2  mov     dword ptr [rbp+rcx*8+8], 4
0x1800bb1fa  mov     [rbp+rcx*8+10h], r12
0x1800bb1ff  mov     [rbp+rcx*8+18h], r12
0x1800bb204  mov     dword ptr [rbp+rcx*8+20h], 5
0x1800bb20c  mov     rdx, [rdi+10h]
0x1800bb210  mov     eax, esi
0x1800bb212  lea     rcx, [rax+rax*2]
0x1800bb216  mov     rax, [rdx+r14*8]
0x1800bb21a  add     rcx, rcx
0x1800bb21d  mov     [rbp+rcx*8+28h], rax
0x1800bb222  inc     esi
0x1800bb224  mov     eax, [rdi+8]
0x1800bb227  inc     r15d
0x1800bb22a  add     eax, 2
0x1800bb22d  xor     r8d, r8d
0x1800bb230  cmp     r15d, eax
0x1800bb233  jb      loc_1800BB0F5
0x1800bb239  mov     r14, [rsp+0C8h+var_78]
0x1800bb23e  mov     rax, [rsp+0C8h+Sid]
0x1800bb243  mov     [rbp+28h], rax
0x1800bb247  mov     rax, [rsp+0C8h+hMem]
0x1800bb24c  mov     [rbp+58h], rax
0x1800bb250  test    r13d, r13d
0x1800bb253  jz      short loc_1800BB25E
0x1800bb255  cmp     esi, 2
0x1800bb258  jbe     loc_1800BB2FF
0x1800bb25e  lea     rax, [rsp+0C8h+var_68]
0x1800bb263  mov     r9, rbp; pListOfAccessEntries
0x1800bb266  mov     [rsp+0C8h+pNewSD], rax; pNewSD
0x1800bb26b  xor     edx, edx; pGroup
0x1800bb26d  lea     rax, [rsp+0C8h+var_50]
0x1800bb272  xor     ecx, ecx; pOwner
0x1800bb274  mov     [rsp+0C8h+pSizeNewSD], rax; pSizeNewSD
0x1800bb279  mov     [rsp+0C8h+pOldSD], r8; pOldSD
0x1800bb27e  mov     [rsp+0C8h+pListOfAuditEntries], r8; pListOfAuditEntries
0x1800bb283  mov     [rsp+0C8h+cCountOfAuditEntries], r8d; cCountOfAuditEntries
0x1800bb288  mov     r8d, esi; cCountOfAccessEntries
0x1800bb28b  call    cs:__imp_BuildSecurityDescriptorW
0x1800bb292  nop     dword ptr [rax+rax+00h]
0x1800bb297  mov     ebx, eax
0x1800bb299  test    eax, eax
0x1800bb29b  jle     short loc_1800BB2A6
0x1800bb29d  movzx   ebx, ax
0x1800bb2a0  or      ebx, 80070000h
0x1800bb2a6  test    ebx, ebx
0x1800bb2a8  jns     loc_1800BB3A5
0x1800bb2ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bb2b5  lea     rax, WPP_GLOBAL_Control
0x1800bb2bc  cmp     rcx, rax
0x1800bb2bf  jz      short loc_1800BB2FF
0x1800bb2c1  test    byte ptr [rcx+1Ch], 1
0x1800bb2c5  jz      short loc_1800BB2FF
0x1800bb2c7  mov     edx, 18h
0x1800bb2cc  jmp     short loc_1800BB2EC
0x1800bb2ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bb2d5  lea     rax, WPP_GLOBAL_Control
0x1800bb2dc  cmp     rcx, rax
0x1800bb2df  jz      short loc_1800BB2FF
0x1800bb2e1  test    byte ptr [rcx+1Ch], 1
0x1800bb2e5  jz      short loc_1800BB2FF
0x1800bb2e7  mov     edx, 17h
0x1800bb2ec  mov     rcx, [rcx+10h]
0x1800bb2f0  lea     r8, WPP_202f566a5b6b3eebbc58311978cd75bc_Traceguids
0x1800bb2f7  mov     r9d, ebx
0x1800bb2fa  call    WPP_SF_d
0x1800bb2ff  xor     r12d, r12d
0x1800bb302  mov     r15, [rsp+0C8h+var_38]
0x1800bb30a  mov     edi, r12d
0x1800bb30d  test    esi, esi
0x1800bb30f  jz      short loc_1800BB337
0x1800bb311  mov     eax, edi
0x1800bb313  lea     rdx, [rax+rax*2]
0x1800bb317  add     rdx, rdx
0x1800bb31a  mov     rcx, [rbp+rdx*8+28h]
0x1800bb31f  cmp     dword ptr [rcx+8], 3
0x1800bb323  jnz     short loc_1800BB331
0x1800bb325  call    cs:__imp_FwFree
0x1800bb32c  nop     dword ptr [rax+rax+00h]
0x1800bb331  inc     edi
0x1800bb333  cmp     edi, esi
0x1800bb335  jb      short loc_1800BB311
0x1800bb337  mov     rsi, [rsp+0C8h+arg_10]
0x1800bb33f  mov     rcx, [rsp+0C8h+var_70]
0x1800bb344  call    cs:__imp_FwCriticalSectionLeave
0x1800bb34b  nop     dword ptr [rax+rax+00h]
0x1800bb350  mov     rcx, [rsp+0C8h+Sid]; hMem
0x1800bb355  call    cs:__imp_LocalFree
0x1800bb35c  nop     dword ptr [rax+rax+00h]
0x1800bb361  mov     rcx, [rsp+0C8h+hMem]; hMem
0x1800bb366  call    cs:__imp_LocalFree
0x1800bb36d  nop     dword ptr [rax+rax+00h]
0x1800bb372  mov     rcx, rbp
0x1800bb375  call    cs:__imp_FwFree
0x1800bb37c  nop     dword ptr [rax+rax+00h]
0x1800bb381  mov     eax, ebx
0x1800bb383  mov     rcx, [rsp+0C8h+var_48]
0x1800bb38b  xor     rcx, rsp; StackCookie
0x1800bb38e  call    __security_check_cookie
0x1800bb393  add     rsp, 98h
0x1800bb39a  pop     r14
0x1800bb39c  pop     r13
0x1800bb39e  pop     r12
0x1800bb3a0  pop     rdi
0x1800bb3a1  pop     rbp
0x1800bb3a2  pop     rbx
0x1800bb3a3  retn
0x1800bb3a5  mov     rax, [rsp+0C8h+var_68]
0x1800bb3aa  xor     r12d, r12d
0x1800bb3ad  mov     [r14], rax
0x1800bb3b0  mov     [rsp+0C8h+var_68], r12
0x1800bb3b5  jmp     loc_1800BB302
```
