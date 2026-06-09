# CSharePageProgress::_s_GetStopSharingSids(CUserObjectList *,CUserObjectList *,CDPA<ushort,CTContainer_PolicyUnOwned<ushort>> &)

- ea: `0x18006e4d0`
- end: `0x18006e5a8`
- name: `?_s_GetStopSharingSids@CSharePageProgress@@CAJPEAVCUserObjectList@@0AEAV?$CDPA@GV?$CTContainer_PolicyUnOwned@G@@@@@Z`
- size: `216`
- prototype: `__int64 __fastcall(CUserObjectList *this, CUserObjectList *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006e6f4`

## callees

- `0x1800098dc`
- `0x1800120e0`
- `0x18006e4d0`
- `0x1800707b0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18006e50e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18006e50e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e573`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e573`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006e546`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006e546`

## pseudocode

```c
__int64 __fastcall CSharePageProgress::_s_GetStopSharingSids(PSID **this, PSID **a2, __int64 a3)
{
  PSID *v3; // rdi
  int appended; // ebx
  PSID *Next; // r14
  int v9; // esi
  PSID v10; // rcx
  LPWSTR StringSid; // [rsp+50h] [rbp+8h] BYREF

  v3 = *this;
  appended = 0;
  do
  {
    if ( !v3 )
      break;
    Next = *a2;
    v9 = 0;
    if ( !*a2 )
      goto LABEL_8;
    do
    {
      if ( EqualSid(*v3, *Next) )
        v9 = 1;
      Next = (PSID *)CUserObjectList::GetNext((CUserObjectList *)a2, (struct CUserObject *)Next);
    }
    while ( Next );
    if ( !v9 )
    {
LABEL_8:
      v10 = *v3;
      StringSid = 0;
      if ( ConvertSidToStringSidW(v10, &StringSid) || (appended = ResultFromKnownLastError(), appended >= 0) )
      {
        appended = CDPA_Base<CShareUserInfo,CTContainer_PolicyNewMem>::AppendPtr(a3, StringSid);
        if ( appended < 0 )
          LocalFree(StringSid);
      }
    }
    v3 = (PSID *)CUserObjectList::GetNext((CUserObjectList *)this, (struct CUserObject *)v3);
  }
  while ( appended >= 0 );
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18006e4d0  mov     [rsp+arg_8], rbx
0x18006e4d5  mov     [rsp+arg_10], rbp
0x18006e4da  push    rsi
0x18006e4db  push    rdi
0x18006e4dc  push    r12
0x18006e4de  push    r14
0x18006e4e0  push    r15
0x18006e4e2  sub     rsp, 20h
0x18006e4e6  mov     rdi, [rcx]
0x18006e4e9  mov     r12, r8
0x18006e4ec  mov     rbp, rdx
0x18006e4ef  mov     r15, rcx
0x18006e4f2  xor     ebx, ebx
0x18006e4f4  test    rdi, rdi
0x18006e4f7  jz      loc_18006E58F
0x18006e4fd  mov     r14, [rbp+0]
0x18006e501  xor     esi, esi
0x18006e503  test    r14, r14
0x18006e506  jz      short loc_18006E535
0x18006e508  mov     rdx, [r14]; pSid2
0x18006e50b  mov     rcx, [rdi]; pSid1
0x18006e50e  call    cs:__imp_EqualSid
0x18006e514  mov     ecx, 1
0x18006e519  mov     rdx, r14; struct CUserObject *
0x18006e51c  test    eax, eax
0x18006e51e  cmovnz  esi, ecx
0x18006e521  mov     rcx, rbp; this
0x18006e524  call    ?GetNext@CUserObjectList@@QEAAPEAVCUserObject@@PEAV2@@Z; CUserObjectList::GetNext(CUserObject *)
0x18006e529  mov     r14, rax
0x18006e52c  test    rax, rax
0x18006e52f  jnz     short loc_18006E508
0x18006e531  test    esi, esi
0x18006e533  jnz     short loc_18006E579
0x18006e535  mov     rcx, [rdi]; Sid
0x18006e538  lea     rdx, [rsp+48h+StringSid]; StringSid
0x18006e53d  mov     [rsp+48h+StringSid], 0
0x18006e546  call    cs:__imp_ConvertSidToStringSidW
0x18006e54c  test    eax, eax
0x18006e54e  jnz     short loc_18006E55B
0x18006e550  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006e555  mov     ebx, eax
0x18006e557  test    eax, eax
0x18006e559  js      short loc_18006E579
0x18006e55b  mov     rdx, [rsp+48h+StringSid]
0x18006e560  mov     rcx, r12
0x18006e563  call    ?AppendPtr@?$CDPA_Base@VCShareUserInfo@@VCTContainer_PolicyNewMem@@@@QEAAJPEAVCShareUserInfo@@PEAH@Z; CDPA_Base<CShareUserInfo,CTContainer_PolicyNewMem>::AppendPtr(CShareUserInfo *,int *)
0x18006e568  mov     ebx, eax
0x18006e56a  test    eax, eax
0x18006e56c  jns     short loc_18006E579
0x18006e56e  mov     rcx, [rsp+48h+StringSid]; hMem
0x18006e573  call    cs:__imp_LocalFree
0x18006e579  mov     rdx, rdi; struct CUserObject *
0x18006e57c  mov     rcx, r15; this
0x18006e57f  call    ?GetNext@CUserObjectList@@QEAAPEAVCUserObject@@PEAV2@@Z; CUserObjectList::GetNext(CUserObject *)
0x18006e584  mov     rdi, rax
0x18006e587  test    ebx, ebx
0x18006e589  jns     loc_18006E4F4
0x18006e58f  mov     rbp, [rsp+48h+arg_10]
0x18006e594  mov     eax, ebx
0x18006e596  mov     rbx, [rsp+48h+arg_8]
0x18006e59b  add     rsp, 20h
0x18006e59f  pop     r15
0x18006e5a1  pop     r14
0x18006e5a3  pop     r12
0x18006e5a5  pop     rdi
0x18006e5a6  pop     rsi
0x18006e5a7  retn
```
