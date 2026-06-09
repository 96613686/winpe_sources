# CSecurityAdmin2::AddRole(_GUID const &,ushort *)

- ea: `0x180028438`
- end: `0x1800286a8`
- name: `?AddRole@CSecurityAdmin2@@QEAAJAEBU_GUID@@PEAG@Z`
- size: `624`
- prototype: `signed int __fastcall(CSecurityAdmin2 *this, const struct _GUID *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180026b60`

## callees

- `0x1800269a8`
- `0x180026af4`
- `0x180028438`
- `0x180057010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18002850c`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18002850c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002853b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002867f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002853b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002867f`
- `ADVAPI32!BuildSecurityDescriptorW` at `0x1800284da`
- `ADVAPI32!BuildSecurityDescriptorW` at `0x1800284da`
- `ADVAPI32!BuildTrusteeWithNameW` at `0x180028482`
- `ADVAPI32!BuildTrusteeWithNameW` at `0x180028493`
- `ADVAPI32!BuildTrusteeWithNameW` at `0x180028482`
- `ADVAPI32!BuildTrusteeWithNameW` at `0x180028493`

## pseudocode

```c
signed int __fastcall CSecurityAdmin2::AddRole(CSecurityAdmin2 *this, const struct _GUID *a2, unsigned __int16 *a3)
{
  signed int result; // eax
  unsigned int v7; // r8d
  SIZE_T v8; // rdx
  char *v9; // rax
  const struct _GUID *v10; // r8
  CSecurityAdmin2 *v11; // rcx
  struct ISimpleTableDispenser *v12; // rdx
  int Table; // ebx
  unsigned int pOldSD; // [rsp+30h] [rbp-49h]
  void *v15; // [rsp+50h] [rbp-29h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+58h] [rbp-21h] BYREF
  struct _ACL pAcl; // [rsp+60h] [rbp-19h] BYREF
  struct _TRUSTEE_W pGroup; // [rsp+68h] [rbp-11h] BYREF
  struct _TRUSTEE_W pTrustee; // [rsp+88h] [rbp+Fh] BYREF
  ULONG pSizeNewSD; // [rsp+F8h] [rbp+7Fh] BYREF

  hMem = 0;
  pSizeNewSD = 0;
  memset(&pTrustee, 0, sizeof(pTrustee));
  memset(&pGroup, 0, sizeof(pGroup));
  BuildTrusteeWithNameW(&pTrustee, (LPWSTR)L"CURRENT_USER");
  BuildTrusteeWithNameW(&pGroup, (LPWSTR)L"CURRENT_USER");
  pGroup.TrusteeType = TRUSTEE_IS_GROUP;
  result = BuildSecurityDescriptorW(&pTrustee, &pGroup, 0, 0, 0, 0, 0, &pSizeNewSD, &hMem);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    pAcl = 0;
    InitializeAcl(&pAcl, 8u, 4u);
    v8 = pSizeNewSD + 8;
    if ( (unsigned int)v8 >= pSizeNewSD )
    {
      v9 = (char *)SmartLocalReAlloc(hMem, v8, v7);
      if ( v9 )
      {
        hMem = v9;
        *(struct _ACL *)&v9[pSizeNewSD] = pAcl;
        v11 = (CSecurityAdmin2 *)hMem;
        *((_DWORD *)hMem + 4) = pSizeNewSD;
        v12 = (struct ISimpleTableDispenser *)*((_QWORD *)this + 3);
        pSizeNewSD += 8;
        v15 = 0;
        Table = CSecurityAdmin2::GetTable(v11, v12, v10, &tidCOMSERVICES_ROLESDCACHE, 0, 0, pOldSD, 0x20000u, &v15);
        if ( Table >= 0 )
        {
          Table = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v15 + 24LL))(v15);
          if ( Table >= 0 )
          {
            Table = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v15 + 120LL))(v15);
            if ( Table >= 0 )
            {
              Table = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD, const struct _GUID *))(*(_QWORD *)v15 + 160LL))(
                        v15,
                        0,
                        0,
                        a2);
              if ( Table >= 0 )
              {
                Table = (*(__int64 (__fastcall **)(void *, __int64, _QWORD, unsigned __int16 *))(*(_QWORD *)v15 + 160LL))(
                          v15,
                          1,
                          0,
                          a3);
                if ( Table >= 0 )
                {
                  Table = (*(__int64 (__fastcall **)(void *, __int64, _QWORD, PSECURITY_DESCRIPTOR))(*(_QWORD *)v15 + 160LL))(
                            v15,
                            2,
                            pSizeNewSD,
                            hMem);
                  if ( Table >= 0 )
                  {
                    Table = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v15 + 144LL))(v15);
                    if ( Table >= 0 )
                      Table = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v15 + 96LL))(v15);
                  }
                }
              }
            }
          }
        }
        if ( hMem )
          LocalFree(hMem);
        if ( v15 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v15 + 16LL))(v15);
        return Table;
      }
      else
      {
        LocalFree(hMem);
        return -2147024882;
      }
    }
    else
    {
      return -2147024362;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180028438  push    rbp
0x18002843a  push    rbx
0x18002843b  push    rsi
0x18002843c  push    rdi
0x18002843d  lea     rbp, [rsp-3Fh]
0x180028442  sub     rsp, 0B8h
0x180028449  xorps   xmm0, xmm0
0x18002844c  mov     [rbp+57h+hMem], 0
0x180028454  xorps   xmm1, xmm1
0x180028457  mov     [rbp+57h+arg_18], 0
0x18002845e  mov     rdi, rdx
0x180028461  mov     rbx, rcx
0x180028464  lea     rdx, pName; "CURRENT_USER"
0x18002846b  mov     rsi, r8
0x18002846e  lea     rcx, [rbp+57h+pTrustee]; pTrustee
0x180028472  movups  xmmword ptr [rbp+57h+pTrustee.pMultipleTrustee], xmm0
0x180028476  movups  xmmword ptr [rbp+57h+pTrustee.TrusteeType], xmm0
0x18002847a  movups  xmmword ptr [rbp+57h+pGroup.pMultipleTrustee], xmm1
0x18002847e  movups  xmmword ptr [rbp+57h+pGroup.TrusteeType], xmm1
0x180028482  call    cs:__imp_BuildTrusteeWithNameW
0x180028488  lea     rdx, pName; "CURRENT_USER"
0x18002848f  lea     rcx, [rbp+57h+pGroup]; pTrustee
0x180028493  call    cs:__imp_BuildTrusteeWithNameW
0x180028499  lea     rax, [rbp+57h+hMem]
0x18002849d  mov     [rbp+57h+pGroup.TrusteeType], 2
0x1800284a4  mov     [rsp+0D0h+pNewSD], rax; pNewSD
0x1800284a9  lea     rdx, [rbp+57h+pGroup]; pGroup
0x1800284ad  lea     rax, [rbp+57h+arg_18]
0x1800284b1  xor     r9d, r9d; pListOfAccessEntries
0x1800284b4  mov     [rsp+0D0h+pSizeNewSD], rax; pSizeNewSD
0x1800284b9  lea     rcx, [rbp+57h+pTrustee]; pOwner
0x1800284bd  mov     [rsp+0D0h+pOldSD], 0; unsigned int
0x1800284c6  xor     r8d, r8d; cCountOfAccessEntries
0x1800284c9  mov     [rsp+0D0h+pListOfAuditEntries], 0; pListOfAuditEntries
0x1800284d2  mov     [rsp+0D0h+cCountOfAuditEntries], 0; cCountOfAuditEntries
0x1800284da  call    cs:__imp_BuildSecurityDescriptorW
0x1800284e0  test    eax, eax
0x1800284e2  jz      short loc_1800284F7
0x1800284e4  jle     loc_18002869C
0x1800284ea  movzx   eax, ax
0x1800284ed  or      eax, 80070000h
0x1800284f2  jmp     loc_18002869C
0x1800284f7  mov     edx, 8; nAclLength
0x1800284fc  mov     qword ptr [rbp+57h+pAcl.AclRevision], 0
0x180028504  lea     rcx, [rbp+57h+pAcl]; pAcl
0x180028508  lea     r8d, [rdx-4]; dwAclRevision
0x18002850c  call    cs:__imp_InitializeAcl
0x180028512  mov     eax, [rbp+57h+arg_18]
0x180028515  lea     edx, [rax+8]; uBytes
0x180028518  cmp     edx, eax
0x18002851a  jnb     short loc_180028526
0x18002851c  mov     eax, 80070216h
0x180028521  jmp     loc_18002869C
0x180028526  mov     rcx, [rbp+57h+hMem]; Src
0x18002852a  call    ?SmartLocalReAlloc@@YAPEAXPEAXII@Z; SmartLocalReAlloc(void *,uint,uint)
0x18002852f  mov     rdx, rax
0x180028532  test    rax, rax
0x180028535  jnz     short loc_18002854B
0x180028537  mov     rcx, [rbp+57h+hMem]; hMem
0x18002853b  call    cs:__imp_LocalFree
0x180028541  mov     eax, 8007000Eh
0x180028546  jmp     loc_18002869C
0x18002854b  mov     ecx, [rbp+57h+arg_18]
0x18002854e  lea     r9, tidCOMSERVICES_ROLESDCACHE; struct _GUID *
0x180028555  mov     rax, qword ptr [rbp+57h+pAcl.AclRevision]
0x180028559  mov     [rbp+57h+hMem], rdx
0x18002855d  mov     [rcx+rdx], rax
0x180028561  mov     eax, [rbp+57h+arg_18]
0x180028564  mov     rcx, [rbp+57h+hMem]; this
0x180028568  mov     [rcx+10h], eax
0x18002856b  lea     rax, [rbp+57h+var_80]
0x18002856f  mov     rdx, [rbx+18h]; struct ISimpleTableDispenser *
0x180028573  add     [rbp+57h+arg_18], 8
0x180028577  mov     [rsp+0D0h+pNewSD], rax; void **
0x18002857c  mov     dword ptr [rsp+0D0h+pSizeNewSD], 20000h; unsigned int
0x180028584  mov     [rsp+0D0h+pListOfAuditEntries], 0; void *
0x18002858d  mov     qword ptr [rsp+0D0h+cCountOfAuditEntries], 0; void *
0x180028596  mov     [rbp+57h+var_80], 0
0x18002859e  call    ?GetTable@CSecurityAdmin2@@QEAAJPEAUISimpleTableDispenser@@AEBU_GUID@@1PEAX2KKPEAPEAX@Z; CSecurityAdmin2::GetTable(ISimpleTableDispenser *,_GUID const &,_GUID const &,void *,void *,ulong,ulong,void * *)
0x1800285a3  mov     ebx, eax
0x1800285a5  test    eax, eax
0x1800285a7  js      loc_180028676
0x1800285ad  mov     rcx, [rbp+57h+var_80]
0x1800285b1  mov     rax, [rcx]
0x1800285b4  mov     rax, [rax+18h]
0x1800285b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285bd  mov     ebx, eax
0x1800285bf  test    eax, eax
0x1800285c1  js      loc_180028676
0x1800285c7  mov     rcx, [rbp+57h+var_80]
0x1800285cb  mov     rax, [rcx]
0x1800285ce  mov     rax, [rax+78h]
0x1800285d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285d7  mov     ebx, eax
0x1800285d9  test    eax, eax
0x1800285db  js      loc_180028676
0x1800285e1  mov     rcx, [rbp+57h+var_80]
0x1800285e5  mov     r9, rdi
0x1800285e8  xor     r8d, r8d
0x1800285eb  xor     edx, edx
0x1800285ed  mov     rax, [rcx]
0x1800285f0  mov     rax, [rax+0A0h]
0x1800285f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285fc  mov     ebx, eax
0x1800285fe  test    eax, eax
0x180028600  js      short loc_180028676
0x180028602  mov     rcx, [rbp+57h+var_80]
0x180028606  xor     r8d, r8d
0x180028609  mov     r9, rsi
0x18002860c  mov     rax, [rcx]
0x18002860f  lea     edx, [r8+1]
0x180028613  mov     rax, [rax+0A0h]
0x18002861a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002861f  mov     ebx, eax
0x180028621  test    eax, eax
0x180028623  js      short loc_180028676
0x180028625  mov     rcx, [rbp+57h+var_80]
0x180028629  mov     edx, 2
0x18002862e  mov     r9, [rbp+57h+hMem]
0x180028632  mov     r8d, [rbp+57h+arg_18]
0x180028636  mov     rax, [rcx]
0x180028639  mov     rax, [rax+0A0h]
0x180028640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028645  mov     ebx, eax
0x180028647  test    eax, eax
0x180028649  js      short loc_180028676
0x18002864b  mov     rcx, [rbp+57h+var_80]
0x18002864f  mov     rax, [rcx]
0x180028652  mov     rax, [rax+90h]
0x180028659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002865e  mov     ebx, eax
0x180028660  test    eax, eax
0x180028662  js      short loc_180028676
0x180028664  mov     rcx, [rbp+57h+var_80]
0x180028668  mov     rax, [rcx]
0x18002866b  mov     rax, [rax+60h]
0x18002866f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028674  mov     ebx, eax
0x180028676  mov     rcx, [rbp+57h+hMem]; hMem
0x18002867a  test    rcx, rcx
0x18002867d  jz      short loc_180028685
0x18002867f  call    cs:__imp_LocalFree
0x180028685  mov     rcx, [rbp+57h+var_80]
0x180028689  test    rcx, rcx
0x18002868c  jz      short loc_18002869A
0x18002868e  mov     rax, [rcx]
0x180028691  mov     rax, [rax+10h]
0x180028695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002869a  mov     eax, ebx
0x18002869c  add     rsp, 0B8h
0x1800286a3  pop     rdi
0x1800286a4  pop     rsi
0x1800286a5  pop     rbx
0x1800286a6  pop     rbp
0x1800286a7  retn
```
