# CSecurityAdmin2::AddRole(_GUID const &,ushort *)

- ea: `0x180035e38`
- end: `0x1800360a8`
- name: `?AddRole@CSecurityAdmin2@@QEAAJAEBU_GUID@@PEAG@Z`
- size: `624`
- prototype: `signed int __fastcall(CSecurityAdmin2 *this, const struct _GUID *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180033f20`

## callees

- `0x180033d68`
- `0x180033eb4`
- `0x180035e38`
- `0x180058010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180035f0c`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180035f0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035f3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003607f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035f3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003607f`
- `api-ms-win-security-trustee-l1-1-0!BuildSecurityDescriptorW` at `0x180035eda`
- `api-ms-win-security-trustee-l1-1-0!BuildSecurityDescriptorW` at `0x180035eda`
- `api-ms-win-security-trustee-l1-1-1!BuildTrusteeWithNameW` at `0x180035e82`
- `api-ms-win-security-trustee-l1-1-1!BuildTrusteeWithNameW` at `0x180035e93`
- `api-ms-win-security-trustee-l1-1-1!BuildTrusteeWithNameW` at `0x180035e82`
- `api-ms-win-security-trustee-l1-1-1!BuildTrusteeWithNameW` at `0x180035e93`

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
0x180035e38  push    rbp
0x180035e3a  push    rbx
0x180035e3b  push    rsi
0x180035e3c  push    rdi
0x180035e3d  lea     rbp, [rsp-3Fh]
0x180035e42  sub     rsp, 0B8h
0x180035e49  xorps   xmm0, xmm0
0x180035e4c  mov     [rbp+57h+hMem], 0
0x180035e54  xorps   xmm1, xmm1
0x180035e57  mov     [rbp+57h+arg_18], 0
0x180035e5e  mov     rdi, rdx
0x180035e61  mov     rbx, rcx
0x180035e64  lea     rdx, pName; "CURRENT_USER"
0x180035e6b  mov     rsi, r8
0x180035e6e  lea     rcx, [rbp+57h+pTrustee]; pTrustee
0x180035e72  movups  xmmword ptr [rbp+57h+pTrustee.pMultipleTrustee], xmm0
0x180035e76  movups  xmmword ptr [rbp+57h+pTrustee.TrusteeType], xmm0
0x180035e7a  movups  xmmword ptr [rbp+57h+pGroup.pMultipleTrustee], xmm1
0x180035e7e  movups  xmmword ptr [rbp+57h+pGroup.TrusteeType], xmm1
0x180035e82  call    cs:__imp_BuildTrusteeWithNameW
0x180035e88  lea     rdx, pName; "CURRENT_USER"
0x180035e8f  lea     rcx, [rbp+57h+pGroup]; pTrustee
0x180035e93  call    cs:__imp_BuildTrusteeWithNameW
0x180035e99  lea     rax, [rbp+57h+hMem]
0x180035e9d  mov     [rbp+57h+pGroup.TrusteeType], 2
0x180035ea4  mov     [rsp+0D0h+pNewSD], rax; pNewSD
0x180035ea9  lea     rdx, [rbp+57h+pGroup]; pGroup
0x180035ead  lea     rax, [rbp+57h+arg_18]
0x180035eb1  xor     r9d, r9d; pListOfAccessEntries
0x180035eb4  mov     [rsp+0D0h+pSizeNewSD], rax; pSizeNewSD
0x180035eb9  lea     rcx, [rbp+57h+pTrustee]; pOwner
0x180035ebd  mov     [rsp+0D0h+pOldSD], 0; unsigned int
0x180035ec6  xor     r8d, r8d; cCountOfAccessEntries
0x180035ec9  mov     [rsp+0D0h+pListOfAuditEntries], 0; pListOfAuditEntries
0x180035ed2  mov     [rsp+0D0h+cCountOfAuditEntries], 0; cCountOfAuditEntries
0x180035eda  call    cs:__imp_BuildSecurityDescriptorW
0x180035ee0  test    eax, eax
0x180035ee2  jz      short loc_180035EF7
0x180035ee4  jle     loc_18003609C
0x180035eea  movzx   eax, ax
0x180035eed  or      eax, 80070000h
0x180035ef2  jmp     loc_18003609C
0x180035ef7  mov     edx, 8; nAclLength
0x180035efc  mov     qword ptr [rbp+57h+pAcl.AclRevision], 0
0x180035f04  lea     rcx, [rbp+57h+pAcl]; pAcl
0x180035f08  lea     r8d, [rdx-4]; dwAclRevision
0x180035f0c  call    cs:__imp_InitializeAcl
0x180035f12  mov     eax, [rbp+57h+arg_18]
0x180035f15  lea     edx, [rax+8]; uBytes
0x180035f18  cmp     edx, eax
0x180035f1a  jnb     short loc_180035F26
0x180035f1c  mov     eax, 80070216h
0x180035f21  jmp     loc_18003609C
0x180035f26  mov     rcx, [rbp+57h+hMem]; Src
0x180035f2a  call    ?SmartLocalReAlloc@@YAPEAXPEAXII@Z; SmartLocalReAlloc(void *,uint,uint)
0x180035f2f  mov     rdx, rax
0x180035f32  test    rax, rax
0x180035f35  jnz     short loc_180035F4B
0x180035f37  mov     rcx, [rbp+57h+hMem]; hMem
0x180035f3b  call    cs:__imp_LocalFree
0x180035f41  mov     eax, 8007000Eh
0x180035f46  jmp     loc_18003609C
0x180035f4b  mov     ecx, [rbp+57h+arg_18]
0x180035f4e  lea     r9, tidCOMSERVICES_ROLESDCACHE; struct _GUID *
0x180035f55  mov     rax, qword ptr [rbp+57h+pAcl.AclRevision]
0x180035f59  mov     [rbp+57h+hMem], rdx
0x180035f5d  mov     [rcx+rdx], rax
0x180035f61  mov     eax, [rbp+57h+arg_18]
0x180035f64  mov     rcx, [rbp+57h+hMem]; this
0x180035f68  mov     [rcx+10h], eax
0x180035f6b  lea     rax, [rbp+57h+var_80]
0x180035f6f  mov     rdx, [rbx+18h]; struct ISimpleTableDispenser *
0x180035f73  add     [rbp+57h+arg_18], 8
0x180035f77  mov     [rsp+0D0h+pNewSD], rax; void **
0x180035f7c  mov     dword ptr [rsp+0D0h+pSizeNewSD], 20000h; unsigned int
0x180035f84  mov     [rsp+0D0h+pListOfAuditEntries], 0; void *
0x180035f8d  mov     qword ptr [rsp+0D0h+cCountOfAuditEntries], 0; void *
0x180035f96  mov     [rbp+57h+var_80], 0
0x180035f9e  call    ?GetTable@CSecurityAdmin2@@QEAAJPEAUISimpleTableDispenser@@AEBU_GUID@@1PEAX2KKPEAPEAX@Z; CSecurityAdmin2::GetTable(ISimpleTableDispenser *,_GUID const &,_GUID const &,void *,void *,ulong,ulong,void * *)
0x180035fa3  mov     ebx, eax
0x180035fa5  test    eax, eax
0x180035fa7  js      loc_180036076
0x180035fad  mov     rcx, [rbp+57h+var_80]
0x180035fb1  mov     rax, [rcx]
0x180035fb4  mov     rax, [rax+18h]
0x180035fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035fbd  mov     ebx, eax
0x180035fbf  test    eax, eax
0x180035fc1  js      loc_180036076
0x180035fc7  mov     rcx, [rbp+57h+var_80]
0x180035fcb  mov     rax, [rcx]
0x180035fce  mov     rax, [rax+78h]
0x180035fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035fd7  mov     ebx, eax
0x180035fd9  test    eax, eax
0x180035fdb  js      loc_180036076
0x180035fe1  mov     rcx, [rbp+57h+var_80]
0x180035fe5  mov     r9, rdi
0x180035fe8  xor     r8d, r8d
0x180035feb  xor     edx, edx
0x180035fed  mov     rax, [rcx]
0x180035ff0  mov     rax, [rax+0A0h]
0x180035ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ffc  mov     ebx, eax
0x180035ffe  test    eax, eax
0x180036000  js      short loc_180036076
0x180036002  mov     rcx, [rbp+57h+var_80]
0x180036006  xor     r8d, r8d
0x180036009  mov     r9, rsi
0x18003600c  mov     rax, [rcx]
0x18003600f  lea     edx, [r8+1]
0x180036013  mov     rax, [rax+0A0h]
0x18003601a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003601f  mov     ebx, eax
0x180036021  test    eax, eax
0x180036023  js      short loc_180036076
0x180036025  mov     rcx, [rbp+57h+var_80]
0x180036029  mov     edx, 2
0x18003602e  mov     r9, [rbp+57h+hMem]
0x180036032  mov     r8d, [rbp+57h+arg_18]
0x180036036  mov     rax, [rcx]
0x180036039  mov     rax, [rax+0A0h]
0x180036040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036045  mov     ebx, eax
0x180036047  test    eax, eax
0x180036049  js      short loc_180036076
0x18003604b  mov     rcx, [rbp+57h+var_80]
0x18003604f  mov     rax, [rcx]
0x180036052  mov     rax, [rax+90h]
0x180036059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003605e  mov     ebx, eax
0x180036060  test    eax, eax
0x180036062  js      short loc_180036076
0x180036064  mov     rcx, [rbp+57h+var_80]
0x180036068  mov     rax, [rcx]
0x18003606b  mov     rax, [rax+60h]
0x18003606f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036074  mov     ebx, eax
0x180036076  mov     rcx, [rbp+57h+hMem]; hMem
0x18003607a  test    rcx, rcx
0x18003607d  jz      short loc_180036085
0x18003607f  call    cs:__imp_LocalFree
0x180036085  mov     rcx, [rbp+57h+var_80]
0x180036089  test    rcx, rcx
0x18003608c  jz      short loc_18003609A
0x18003608e  mov     rax, [rcx]
0x180036091  mov     rax, [rax+10h]
0x180036095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003609a  mov     eax, ebx
0x18003609c  add     rsp, 0B8h
0x1800360a3  pop     rdi
0x1800360a4  pop     rsi
0x1800360a5  pop     rbx
0x1800360a6  pop     rbp
0x1800360a7  retn
```
