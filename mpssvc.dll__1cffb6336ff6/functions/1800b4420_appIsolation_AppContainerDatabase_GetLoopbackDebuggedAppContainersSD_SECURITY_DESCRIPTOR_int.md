# appIsolation::AppContainerDatabase::GetLoopbackDebuggedAppContainersSD(_SECURITY_DESCRIPTOR * *,int)

- ea: `0x1800b4420`
- end: `0x1800b4876`
- name: `?GetLoopbackDebuggedAppContainersSD@AppContainerDatabase@appIsolation@@QEAAJPEAPEAU_SECURITY_DESCRIPTOR@@H@Z`
- size: `1110`
- prototype: `__int64 __fastcall(appIsolation::AppContainerDatabase *__hidden this, struct _SECURITY_DESCRIPTOR **, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180025ae4`

## callees

- `0x18000af3c`
- `0x180051bec`
- `0x18006f520`
- `0x1800b4420`

## import_xrefs

- `ntdll!RtlIsCapabilitySid` at `0x1800b465c`
- `ntdll!RtlIsCapabilitySid` at `0x1800b465c`
- `ntdll!RtlEqualSid` at `0x1800b4646`
- `ntdll!RtlEqualSid` at `0x1800b4646`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b44ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4524`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b44ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4524`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b4827`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b4832`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b4827`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b4832`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800b44c4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800b451a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800b44c4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800b451a`
- `api-ms-win-security-trustee-l1-1-0!BuildSecurityDescriptorW` at `0x1800b4771`
- `api-ms-win-security-trustee-l1-1-0!BuildSecurityDescriptorW` at `0x1800b4771`
- `fwbase!FwAlloc` at `0x1800b457a`
- `fwbase!FwAlloc` at `0x1800b457a`
- `fwbase!FwCriticalSectionEnter` at `0x1800b446b`
- `fwbase!FwCriticalSectionEnter` at `0x1800b446b`
- `fwbase!FwCriticalSectionLeave` at `0x1800b481c`
- `fwbase!FwCriticalSectionLeave` at `0x1800b481c`
- `fwbase!FwFree` at `0x1800b4805`
- `fwbase!FwFree` at `0x1800b483b`
- `fwbase!FwFree` at `0x1800b4805`
- `fwbase!FwFree` at `0x1800b483b`

## pseudocode

```c
__int64 __fastcall appIsolation::AppContainerDatabase::GetLoopbackDebuggedAppContainersSD(
        appIsolation::AppContainerDatabase *this,
        struct _SECURITY_DESCRIPTOR **a2,
        int a3)
{
  struct _EXPLICIT_ACCESS_W *v3; // rbp
  struct _SECURITY_DESCRIPTOR **v5; // rdi
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
  PSECURITY_DESCRIPTOR pNewSD; // [rsp+58h] [rbp-60h] BYREF
  PSID Sid; // [rsp+60h] [rbp-58h] BYREF
  PSID hMem; // [rsp+68h] [rbp-50h] BYREF
  ULONG pSizeNewSD; // [rsp+70h] [rbp-48h] BYREF

  pSizeNewSD = 0;
  v3 = 0;
  pNewSD = 0;
  Sid = 0;
  v5 = a2;
  hMem = 0;
  *a2 = 0;
  FwCriticalSectionEnter(this);
  if ( !*((_DWORD *)this + 30) )
  {
    v7 = 0;
    v8 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v9 = 23;
      v10 = 0;
LABEL_5:
      WPP_SF_d(*(_QWORD *)(v8 + 16), v9, WPP_0cc1b8e921193136af39b3da6a1b6f83_Traceguids, v10);
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
        v9 = 25;
        v10 = v7;
        goto LABEL_5;
      }
      goto LABEL_53;
    }
    v3 = (struct _EXPLICIT_ACCESS_W *)FwAlloc(48LL * (unsigned int)(2 * *((_DWORD *)this + 30) + 2));
    if ( !v3 )
    {
      v7 = -2147024882;
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v9 = 26;
        v10 = 2147942414LL;
        goto LABEL_5;
      }
      goto LABEL_53;
    }
    LODWORD(v13) = 0;
    v7 = 0;
    v14 = 0;
    if ( *((_DWORD *)this + 30) == -2 )
    {
LABEL_37:
      v3->Trustee.ptstrName = (LPWCH)Sid;
      v3[1].Trustee.ptstrName = (LPWCH)hMem;
      if ( !a3 || (unsigned int)v13 > 2 )
      {
        v20 = BuildSecurityDescriptorW(0, 0, v13, v3, 0, 0, 0, &pSizeNewSD, &pNewSD);
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
            v22 = 28;
            goto LABEL_48;
          }
        }
      }
LABEL_49:
      for ( i = 0; i < (unsigned int)v13; ++i )
      {
        ptstrName = v3[i].Trustee.ptstrName;
        if ( *((_DWORD *)ptstrName + 2) == 3 )
          FwFree(ptstrName);
      }
      goto LABEL_53;
    }
    while ( 1 )
    {
      v15 = (unsigned int)v13;
      v3[v15].grfAccessMode = GRANT_ACCESS;
      v16 = (unsigned int)v13;
      v3[v16].grfAccessPermissions = 1;
      v3[v15].grfInheritance = 4;
      v3[v15].Trustee.pMultipleTrustee = 0;
      *(_QWORD *)&v3[v15].Trustee.MultipleTrusteeOperation = 0;
      v3[v15].Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
      if ( v14 >= 2 )
      {
        if ( RtlEqualSid(*gSidManager, *(PSID *)(*((_QWORD *)this + 14) + 16LL * (v14 - 2))) == 1
          || (unsigned __int8)RtlIsCapabilitySid(*(_QWORD *)(*((_QWORD *)this + 14) + 16LL * (v14 - 2))) == 1
          || a3 && (*(_BYTE *)(*((_QWORD *)this + 14) + 16LL * (v14 - 2) + 8) & 1) == 0 )
        {
          goto LABEL_35;
        }
        v17 = *(_DWORD **)(*((_QWORD *)this + 14) + 16LL * (v14 - 2));
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
              v22 = 27;
LABEL_48:
              WPP_SF_d(*(_QWORD *)(v21 + 16), v22, WPP_0cc1b8e921193136af39b3da6a1b6f83_Traceguids, v7);
            }
            goto LABEL_49;
          }
          v13 = (unsigned int)(v13 + 1);
          *((_DWORD *)v3[v16].Trustee.ptstrName + 2) = 3;
          v19 = v13;
          v3[v19].grfAccessPermissions = 1;
          v3[v19].grfAccessMode = GRANT_ACCESS;
          v3[v19].grfInheritance = 4;
          v3[v19].Trustee.pMultipleTrustee = 0;
          *(_QWORD *)&v3[v19].Trustee.MultipleTrusteeOperation = 0;
          v3[v19].Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
        }
        v3[(unsigned int)v13].Trustee.ptstrName = *(LPWCH *)(*((_QWORD *)this + 14) + 16LL * (v14 - 2));
      }
      LODWORD(v13) = v13 + 1;
LABEL_35:
      if ( ++v14 >= *((_DWORD *)this + 30) + 2 )
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
    v9 = 24;
    v10 = v7;
    goto LABEL_5;
  }
LABEL_53:
  FwCriticalSectionLeave(this);
  LocalFree(Sid);
  LocalFree(hMem);
  FwFree(v3);
  return v7;
}

```

## disassembly

```asm
0x1800b4420  push    rbx
0x1800b4422  push    rbp
0x1800b4423  push    rdi
0x1800b4424  push    r12
0x1800b4426  push    r13
0x1800b4428  push    r14
0x1800b442a  sub     rsp, 88h
0x1800b4431  mov     rax, cs:__security_cookie
0x1800b4438  xor     rax, rsp
0x1800b443b  mov     [rsp+0B8h+var_40], rax
0x1800b4440  xor     r12d, r12d
0x1800b4443  mov     [rsp+0B8h+var_68], rdx
0x1800b4448  mov     [rsp+0B8h+var_48], r12d
0x1800b444d  mov     ebp, r12d
0x1800b4450  mov     [rsp+0B8h+var_60], r12
0x1800b4455  mov     r13d, r8d
0x1800b4458  mov     [rsp+0B8h+Sid], r12
0x1800b445d  mov     rdi, rdx
0x1800b4460  mov     [rsp+0B8h+hMem], r12
0x1800b4465  mov     r14, rcx
0x1800b4468  mov     [rdx], r12
0x1800b446b  call    cs:__imp_FwCriticalSectionEnter
0x1800b4471  cmp     [r14+78h], r12d
0x1800b4475  jnz     short loc_1800B44B8
0x1800b4477  mov     ebx, r12d
0x1800b447a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4481  lea     rax, WPP_GLOBAL_Control
0x1800b4488  cmp     rcx, rax
0x1800b448b  jz      loc_1800B4819
0x1800b4491  test    byte ptr [rcx+1Ch], 1
0x1800b4495  jz      loc_1800B4819
0x1800b449b  mov     edx, 17h
0x1800b44a0  xor     r9d, r9d
0x1800b44a3  mov     rcx, [rcx+10h]
0x1800b44a7  lea     r8, WPP_0cc1b8e921193136af39b3da6a1b6f83_Traceguids
0x1800b44ae  call    WPP_SF_d
0x1800b44b3  jmp     loc_1800B4819
0x1800b44b8  lea     rdx, [rsp+0B8h+Sid]; Sid
0x1800b44bd  lea     rcx, aWd; "WD"
0x1800b44c4  call    cs:__imp_ConvertStringSidToSidW
0x1800b44ca  test    eax, eax
0x1800b44cc  jnz     short loc_1800B450E
0x1800b44ce  call    cs:__imp_GetLastError
0x1800b44d4  mov     ebx, eax
0x1800b44d6  test    eax, eax
0x1800b44d8  jle     short loc_1800B44E3
0x1800b44da  movzx   ebx, ax
0x1800b44dd  or      ebx, 80070000h
0x1800b44e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b44ea  lea     rax, WPP_GLOBAL_Control
0x1800b44f1  cmp     rcx, rax
0x1800b44f4  jz      loc_1800B4819
0x1800b44fa  test    byte ptr [rcx+1Ch], 1
0x1800b44fe  jz      loc_1800B4819
0x1800b4504  mov     edx, 18h
0x1800b4509  mov     r9d, ebx
0x1800b450c  jmp     short loc_1800B44A3
0x1800b450e  lea     rdx, [rsp+0B8h+hMem]; Sid
0x1800b4513  lea     rcx, aAn; "AN"
0x1800b451a  call    cs:__imp_ConvertStringSidToSidW
0x1800b4520  test    eax, eax
0x1800b4522  jnz     short loc_1800B4567
0x1800b4524  call    cs:__imp_GetLastError
0x1800b452a  mov     ebx, eax
0x1800b452c  test    eax, eax
0x1800b452e  jle     short loc_1800B4539
0x1800b4530  movzx   ebx, ax
0x1800b4533  or      ebx, 80070000h
0x1800b4539  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4540  lea     rax, WPP_GLOBAL_Control
0x1800b4547  cmp     rcx, rax
0x1800b454a  jz      loc_1800B4819
0x1800b4550  test    byte ptr [rcx+1Ch], 1
0x1800b4554  jz      loc_1800B4819
0x1800b455a  mov     edx, 19h
0x1800b455f  mov     r9d, ebx
0x1800b4562  jmp     loc_1800B44A3
0x1800b4567  mov     eax, [r14+78h]
0x1800b456b  lea     eax, ds:2[rax*2]
0x1800b4572  lea     rcx, [rax+rax*2]
0x1800b4576  shl     rcx, 4
0x1800b457a  call    cs:__imp_FwAlloc
0x1800b4580  mov     rbp, rax
0x1800b4583  test    rax, rax
0x1800b4586  jnz     short loc_1800B45BB
0x1800b4588  mov     ebx, 8007000Eh
0x1800b458d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4594  lea     rax, WPP_GLOBAL_Control
0x1800b459b  cmp     rcx, rax
0x1800b459e  jz      loc_1800B4819
0x1800b45a4  test    byte ptr [rcx+1Ch], 1
0x1800b45a8  jz      loc_1800B4819
0x1800b45ae  mov     edx, 1Ah
0x1800b45b3  mov     r9d, ebx
0x1800b45b6  jmp     loc_1800B44A3
0x1800b45bb  mov     eax, [r14+78h]
0x1800b45bf  xor     r8d, r8d
0x1800b45c2  mov     [rsp+0B8h+arg_10], rsi
0x1800b45ca  mov     esi, r8d
0x1800b45cd  mov     [rsp+0B8h+var_38], r15
0x1800b45d5  mov     ebx, r8d
0x1800b45d8  mov     r15d, r8d
0x1800b45db  add     eax, 2
0x1800b45de  jz      loc_1800B4724
0x1800b45e4  mov     eax, esi
0x1800b45e6  lea     rcx, [rax+rax*2]
0x1800b45ea  add     rcx, rcx
0x1800b45ed  mov     dword ptr [rbp+rcx*8+4], 1
0x1800b45f5  lea     r12, ds:0[rcx*8]
0x1800b45fd  mov     dword ptr [r12+rbp], 1
0x1800b4605  mov     dword ptr [rbp+rcx*8+8], 4
0x1800b460d  mov     [rbp+rcx*8+10h], r8
0x1800b4612  mov     qword ptr [rbp+rcx*8+18h], 0
0x1800b461b  mov     dword ptr [rbp+rcx*8+20h], 5
0x1800b4623  cmp     r15d, 2
0x1800b4627  jb      loc_1800B4707
0x1800b462d  mov     rdx, [r14+70h]
0x1800b4631  lea     edi, [r15-2]
0x1800b4635  mov     rcx, cs:?gSidManager@@3V?$unique_ptr@VSidManagement@appIsolation@@U?$default_delete@VSidManagement@appIsolation@@@wistd@@@wistd@@A; wistd::unique_ptr<appIsolation::SidManagement,wistd::default_delete<appIsolation::SidManagement>> gSidManager
0x1800b463c  add     rdi, rdi
0x1800b463f  mov     rdx, [rdx+rdi*8]; Sid2
0x1800b4643  mov     rcx, [rcx]; Sid1
0x1800b4646  call    cs:__imp_RtlEqualSid
0x1800b464c  cmp     al, 1
0x1800b464e  jz      loc_1800B4709
0x1800b4654  mov     rcx, [r14+70h]
0x1800b4658  mov     rcx, [rcx+rdi*8]
0x1800b465c  call    cs:__imp_RtlIsCapabilitySid
0x1800b4662  cmp     al, 1
0x1800b4664  jz      loc_1800B4709
0x1800b466a  test    r13d, r13d
0x1800b466d  jz      short loc_1800B467E
0x1800b466f  mov     rax, [r14+70h]
0x1800b4673  test    byte ptr [rax+rdi*8+8], 1
0x1800b4678  jz      loc_1800B4709
0x1800b467e  mov     rax, [r14+70h]
0x1800b4682  mov     rcx, [rax+rdi*8]; SourceSid
0x1800b4686  cmp     dword ptr [rcx+8], 2
0x1800b468a  jnz     short loc_1800B46F1
0x1800b468c  lea     rdx, [rbp+28h]
0x1800b4690  add     rdx, r12
0x1800b4693  call    FwSidCopy
0x1800b4698  mov     ebx, eax
0x1800b469a  test    eax, eax
0x1800b469c  jle     short loc_1800B46A7
0x1800b469e  movzx   ebx, ax
0x1800b46a1  or      ebx, 80070000h
0x1800b46a7  test    ebx, ebx
0x1800b46a9  js      loc_1800B47AE
0x1800b46af  mov     rax, [r12+rbp+28h]
0x1800b46b4  inc     esi
0x1800b46b6  mov     dword ptr [rax+8], 3
0x1800b46bd  lea     rcx, [rsi+rsi*2]
0x1800b46c1  add     rcx, rcx
0x1800b46c4  xor     r12d, r12d
0x1800b46c7  mov     dword ptr [rbp+rcx*8+0], 1
0x1800b46cf  mov     dword ptr [rbp+rcx*8+4], 1
0x1800b46d7  mov     dword ptr [rbp+rcx*8+8], 4
0x1800b46df  mov     [rbp+rcx*8+10h], r12
0x1800b46e4  mov     [rbp+rcx*8+18h], r12
0x1800b46e9  mov     dword ptr [rbp+rcx*8+20h], 5
0x1800b46f1  mov     rdx, [r14+70h]
0x1800b46f5  mov     eax, esi
0x1800b46f7  lea     rcx, [rax+rax*2]
0x1800b46fb  mov     rax, [rdx+rdi*8]
0x1800b46ff  add     rcx, rcx
0x1800b4702  mov     [rbp+rcx*8+28h], rax
0x1800b4707  inc     esi
0x1800b4709  mov     eax, [r14+78h]
0x1800b470d  inc     r15d
0x1800b4710  add     eax, 2
0x1800b4713  xor     r8d, r8d
0x1800b4716  cmp     r15d, eax
0x1800b4719  jb      loc_1800B45E4
0x1800b471f  mov     rdi, [rsp+0B8h+var_68]
0x1800b4724  mov     rax, [rsp+0B8h+Sid]
0x1800b4729  mov     [rbp+28h], rax
0x1800b472d  mov     rax, [rsp+0B8h+hMem]
0x1800b4732  mov     [rbp+58h], rax
0x1800b4736  test    r13d, r13d
0x1800b4739  jz      short loc_1800B4744
0x1800b473b  cmp     esi, 2
0x1800b473e  jbe     loc_1800B47DF
0x1800b4744  lea     rax, [rsp+0B8h+var_60]
0x1800b4749  mov     r9, rbp; pListOfAccessEntries
0x1800b474c  mov     [rsp+0B8h+pNewSD], rax; pNewSD
0x1800b4751  xor     edx, edx; pGroup
0x1800b4753  lea     rax, [rsp+0B8h+var_48]
0x1800b4758  xor     ecx, ecx; pOwner
0x1800b475a  mov     [rsp+0B8h+pSizeNewSD], rax; pSizeNewSD
0x1800b475f  mov     [rsp+0B8h+pOldSD], r8; pOldSD
0x1800b4764  mov     [rsp+0B8h+pListOfAuditEntries], r8; pListOfAuditEntries
0x1800b4769  mov     [rsp+0B8h+cCountOfAuditEntries], r8d; cCountOfAuditEntries
0x1800b476e  mov     r8d, esi; cCountOfAccessEntries
0x1800b4771  call    cs:__imp_BuildSecurityDescriptorW
0x1800b4777  mov     ebx, eax
0x1800b4779  test    eax, eax
0x1800b477b  jle     short loc_1800B4786
0x1800b477d  movzx   ebx, ax
0x1800b4780  or      ebx, 80070000h
0x1800b4786  test    ebx, ebx
0x1800b4788  jns     loc_1800B4861
0x1800b478e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4795  lea     rax, WPP_GLOBAL_Control
0x1800b479c  cmp     rcx, rax
0x1800b479f  jz      short loc_1800B47DF
0x1800b47a1  test    byte ptr [rcx+1Ch], 1
0x1800b47a5  jz      short loc_1800B47DF
0x1800b47a7  mov     edx, 1Ch
0x1800b47ac  jmp     short loc_1800B47CC
0x1800b47ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b47b5  lea     rax, WPP_GLOBAL_Control
0x1800b47bc  cmp     rcx, rax
0x1800b47bf  jz      short loc_1800B47DF
0x1800b47c1  test    byte ptr [rcx+1Ch], 1
0x1800b47c5  jz      short loc_1800B47DF
0x1800b47c7  mov     edx, 1Bh
0x1800b47cc  mov     rcx, [rcx+10h]
0x1800b47d0  lea     r8, WPP_0cc1b8e921193136af39b3da6a1b6f83_Traceguids
0x1800b47d7  mov     r9d, ebx
0x1800b47da  call    WPP_SF_d
0x1800b47df  xor     r12d, r12d
0x1800b47e2  mov     r15, [rsp+0B8h+var_38]
0x1800b47ea  mov     edi, r12d
0x1800b47ed  test    esi, esi
0x1800b47ef  jz      short loc_1800B4811
0x1800b47f1  mov     eax, edi
0x1800b47f3  lea     rdx, [rax+rax*2]
0x1800b47f7  add     rdx, rdx
0x1800b47fa  mov     rcx, [rbp+rdx*8+28h]
0x1800b47ff  cmp     dword ptr [rcx+8], 3
0x1800b4803  jnz     short loc_1800B480B
0x1800b4805  call    cs:__imp_FwFree
0x1800b480b  inc     edi
0x1800b480d  cmp     edi, esi
0x1800b480f  jb      short loc_1800B47F1
0x1800b4811  mov     rsi, [rsp+0B8h+arg_10]
0x1800b4819  mov     rcx, r14
0x1800b481c  call    cs:__imp_FwCriticalSectionLeave
0x1800b4822  mov     rcx, [rsp+0B8h+Sid]; hMem
0x1800b4827  call    cs:__imp_LocalFree
0x1800b482d  mov     rcx, [rsp+0B8h+hMem]; hMem
0x1800b4832  call    cs:__imp_LocalFree
0x1800b4838  mov     rcx, rbp
0x1800b483b  call    cs:__imp_FwFree
0x1800b4841  mov     eax, ebx
0x1800b4843  mov     rcx, [rsp+0B8h+var_40]
0x1800b4848  xor     rcx, rsp; StackCookie
0x1800b484b  call    __security_check_cookie
0x1800b4850  add     rsp, 88h
0x1800b4857  pop     r14
0x1800b4859  pop     r13
0x1800b485b  pop     r12
0x1800b485d  pop     rdi
0x1800b485e  pop     rbp
0x1800b485f  pop     rbx
0x1800b4860  retn
0x1800b4861  mov     rax, [rsp+0B8h+var_60]
0x1800b4866  xor     r12d, r12d
0x1800b4869  mov     [rdi], rax
0x1800b486c  mov     [rsp+0B8h+var_60], r12
0x1800b4871  jmp     loc_1800B47E2
```
