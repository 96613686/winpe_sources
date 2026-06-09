# LookupPrincipalName

- ea: `0x180038734`
- end: `0x1800389e1`
- name: `LookupPrincipalName`
- size: `685`
- prototype: ``
- caller_count: `11`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180098e60`
- `0x1800a504c`
- `0x1800c6430`
- `0x1801260a4`
- `0x180159df4`
- `0x18015d404`
- `0x180194070`
- `0x18023e6e0`
- `0x18031faac`
- `0x180327ba4`
- `0x18037c294`

## callees

- `0x180006360`
- `0x1800067d0`
- `0x180021aa3`
- `0x180038734`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800387ec`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800387ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800387f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800387f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038876`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038876`
- `ntdll!RtlNtStatusToDosError` at `0x1800389c6`
- `ntdll!RtlNtStatusToDosError` at `0x1800389c6`
- `ADVAPI32!LsaOpenPolicy` at `0x180038787`
- `ADVAPI32!LsaOpenPolicy` at `0x180038787`
- `ADVAPI32!LsaLookupSids` at `0x1800387bc`
- `ADVAPI32!LsaLookupSids` at `0x1800387bc`
- `ADVAPI32!LsaClose` at `0x1800389ba`
- `ADVAPI32!LsaClose` at `0x1804546ca`
- `ADVAPI32!LsaClose` at `0x1800389ba`
- `ADVAPI32!LsaClose` at `0x1804546ca`
- `ADVAPI32!LsaFreeMemory` at `0x18003899a`
- `ADVAPI32!LsaFreeMemory` at `0x1800389aa`
- `ADVAPI32!LsaFreeMemory` at `0x1804546aa`
- `ADVAPI32!LsaFreeMemory` at `0x1804546ba`
- `ADVAPI32!LsaFreeMemory` at `0x18003899a`
- `ADVAPI32!LsaFreeMemory` at `0x1800389aa`
- `ADVAPI32!LsaFreeMemory` at `0x1804546aa`
- `ADVAPI32!LsaFreeMemory` at `0x1804546ba`

## pseudocode

```c
__int64 __fastcall LookupPrincipalName(__int64 a1, void *a2, _QWORD *a3, unsigned int *a4)
{
  DWORD LastError; // edi
  int v8; // ebx
  NTSTATUS v9; // eax
  __int64 v10; // rax
  void *v11; // rax
  unsigned int v12; // eax
  void *v13; // rax
  PLSA_TRANSLATED_NAME Names; // [rsp+38h] [rbp-90h] BYREF
  PLSA_REFERENCED_DOMAIN_LIST ReferencedDomains; // [rsp+40h] [rbp-88h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-80h] BYREF
  LSA_HANDLE PolicyHandle; // [rsp+50h] [rbp-78h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES v19[2]; // [rsp+58h] [rbp-70h] BYREF
  PSID Sids; // [rsp+D8h] [rbp+10h] BYREF

  Sids = a2;
  PolicyHandle = 0;
  memset(v19, 0, 48);
  ReferencedDomains = 0;
  Names = 0;
  LastError = 0;
  v8 = LsaOpenPolicy(0, v19, 0x800u, &PolicyHandle);
  if ( v8 >= 0 )
  {
    v9 = LsaLookupSids(PolicyHandle, 1u, &Sids, &ReferencedDomains, &Names);
    v8 = v9;
    if ( v9 == -1073741709 )
    {
      StringSid = 0;
      v8 = 0;
      if ( ConvertSidToStringSidW(Sids, &StringSid) )
      {
        v10 = -1;
        do
          ++v10;
        while ( StringSid[v10] );
        *a4 = v10;
        if ( a1 )
          v11 = (void *)THAlloc_(a1, 1, 2 * ((int)v10 + 1), 0, 0, 50468041);
        else
          v11 = (void *)DSAllocAux(2LL * (unsigned int)(v10 + 1), 50468044);
        *a3 = v11;
        if ( v11 )
          memcpy_0(v11, StringSid, 2LL * *a4);
        else
          LastError = 14;
        LocalFree(StringSid);
      }
      else
      {
        LastError = GetLastError();
      }
    }
    else if ( v9 >= 0 )
    {
      v12 = ((ReferencedDomains->Domains[Names->DomainIndex].Name.Length + (unsigned int)Names->Name.Length) >> 1) + 1;
      *a4 = v12;
      if ( a1 )
        v13 = (void *)THAlloc_(a1, 1, 2 * (v12 + 1), 0, 0, 50468069);
      else
        v13 = (void *)DSAllocAux(2LL * (v12 + 1), 50468072);
      *a3 = v13;
      if ( v13 )
      {
        memcpy_0(
          v13,
          ReferencedDomains->Domains[Names->DomainIndex].Name.Buffer,
          ReferencedDomains->Domains[Names->DomainIndex].Name.Length);
        *(_WORD *)(*a3 + 2 * ((unsigned __int64)ReferencedDomains->Domains[Names->DomainIndex].Name.Length >> 1)) = 92;
        memcpy_0(
          (void *)(*a3 + 2LL + 2 * ((unsigned __int64)ReferencedDomains->Domains[Names->DomainIndex].Name.Length >> 1)),
          Names->Name.Buffer,
          Names->Name.Length);
        *(_WORD *)(*a3 + 2LL * *a4) = 0;
      }
      else
      {
        LastError = 14;
      }
    }
  }
  if ( Names )
    LsaFreeMemory(Names);
  if ( ReferencedDomains )
    LsaFreeMemory(ReferencedDomains);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  if ( v8 )
    return RtlNtStatusToDosError(v8);
  return LastError;
}

```

## disassembly

```asm
0x180038734  mov     rax, rsp
0x180038737  mov     [rax+10h], rdx
0x18003873b  push    rbx
0x18003873c  push    rsi
0x18003873d  push    rdi
0x18003873e  push    r12
0x180038740  push    r14
0x180038742  push    r15
0x180038744  sub     rsp, 98h
0x18003874b  mov     r15, r9
0x18003874e  mov     rsi, r8
0x180038751  mov     r14, rcx
0x180038754  xor     r12d, r12d
0x180038757  mov     [rax-78h], r12
0x18003875b  xorps   xmm0, xmm0
0x18003875e  movups  xmmword ptr [rax-70h], xmm0
0x180038762  movups  xmmword ptr [rax-60h], xmm0
0x180038766  movups  xmmword ptr [rax-50h], xmm0
0x18003876a  mov     [rsp+0C8h+ReferencedDomains], r12
0x18003876f  mov     [rsp+0C8h+var_90], r12
0x180038774  mov     edi, r12d
0x180038777  lea     r9, [rax-78h]; PolicyHandle
0x18003877b  mov     r8d, 800h; DesiredAccess
0x180038781  lea     rdx, [rax-70h]; ObjectAttributes
0x180038785  xor     ecx, ecx; SystemName
0x180038787  call    cs:__imp_LsaOpenPolicy
0x18003878d  mov     ebx, eax
0x18003878f  mov     [rsp+0C8h+var_98], eax
0x180038793  test    eax, eax
0x180038795  js      loc_180038990
0x18003879b  lea     rax, [rsp+0C8h+var_90]
0x1800387a0  mov     [rsp+0C8h+Names], rax; Names
0x1800387a5  lea     r9, [rsp+0C8h+ReferencedDomains]; ReferencedDomains
0x1800387aa  lea     r8, [rsp+0C8h+Sids]; Sids
0x1800387b2  lea     edx, [r12+1]; Count
0x1800387b7  mov     rcx, [rsp+0C8h+PolicyHandle]; PolicyHandle
0x1800387bc  call    cs:__imp_LsaLookupSids
0x1800387c2  mov     ebx, eax
0x1800387c4  mov     [rsp+0C8h+var_98], eax
0x1800387c8  cmp     eax, 0C0000073h
0x1800387cd  jnz     loc_180038881
0x1800387d3  mov     [rsp+0C8h+StringSid], r12
0x1800387d8  mov     ebx, r12d
0x1800387db  mov     [rsp+0C8h+var_98], ebx
0x1800387df  lea     rdx, [rsp+0C8h+StringSid]; StringSid
0x1800387e4  mov     rcx, [rsp+0C8h+Sids]; Sid
0x1800387ec  call    cs:__imp_ConvertSidToStringSidW
0x1800387f2  test    eax, eax
0x1800387f4  jnz     short loc_180038803
0x1800387f6  call    cs:__imp_GetLastError
0x1800387fc  mov     edi, eax
0x1800387fe  jmp     loc_180038990
0x180038803  mov     rcx, [rsp+0C8h+StringSid]
0x180038808  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003880c  inc     rax
0x18003880f  cmp     [rcx+rax*2], r12w
0x180038814  jnz     short loc_18003880C
0x180038816  mov     [r15], eax
0x180038819  lea     ecx, [rax+1]
0x18003881c  add     rcx, rcx
0x18003881f  test    r14, r14
0x180038822  jz      short loc_180038845
0x180038824  mov     [rsp+0C8h+var_A0], 30214C9h
0x18003882c  mov     dword ptr [rsp+0C8h+Names], r12d
0x180038831  xor     r9d, r9d
0x180038834  mov     r8, rcx
0x180038837  lea     edx, [r9+1]
0x18003883b  mov     rcx, r14
0x18003883e  call    THAlloc_
0x180038843  jmp     short loc_18003884F
0x180038845  mov     edx, 30214CCh
0x18003884a  call    DSAllocAux
0x18003884f  mov     [rsi], rax
0x180038852  test    rax, rax
0x180038855  jz      short loc_18003886C
0x180038857  mov     r8d, [r15]
0x18003885a  add     r8, r8; Size
0x18003885d  mov     rdx, [rsp+0C8h+StringSid]; Src
0x180038862  mov     rcx, rax; void *
0x180038865  call    memcpy_0
0x18003886a  jmp     short loc_180038871
0x18003886c  mov     edi, 0Eh
0x180038871  mov     rcx, [rsp+0C8h+StringSid]; hMem
0x180038876  call    cs:__imp_LocalFree
0x18003887c  jmp     loc_180038990
0x180038881  test    eax, eax
0x180038883  js      loc_180038990
0x180038889  mov     r9, [rsp+0C8h+var_90]
0x18003888e  movsxd  rax, dword ptr [r9+18h]
0x180038892  lea     rdx, [rax+rax*2]
0x180038896  mov     rax, [rsp+0C8h+ReferencedDomains]
0x18003889b  mov     rcx, [rax+8]
0x18003889f  movzx   r8d, word ptr [rcx+rdx*8]
0x1800388a4  movzx   eax, word ptr [r9+8]
0x1800388a9  add     eax, r8d
0x1800388ac  shr     eax, 1
0x1800388ae  inc     eax
0x1800388b0  mov     [r15], eax
0x1800388b3  lea     ecx, [rax+1]
0x1800388b6  add     rcx, rcx
0x1800388b9  test    r14, r14
0x1800388bc  jz      short loc_1800388DF
0x1800388be  mov     [rsp+0C8h+var_A0], 30214E5h
0x1800388c6  mov     dword ptr [rsp+0C8h+Names], r12d
0x1800388cb  xor     r9d, r9d
0x1800388ce  mov     r8, rcx
0x1800388d1  lea     edx, [r9+1]
0x1800388d5  mov     rcx, r14
0x1800388d8  call    THAlloc_
0x1800388dd  jmp     short loc_1800388E9
0x1800388df  mov     edx, 30214E8h
0x1800388e4  call    DSAllocAux
0x1800388e9  mov     [rsi], rax
0x1800388ec  mov     rcx, rax; void *
0x1800388ef  test    rax, rax
0x1800388f2  jnz     short loc_1800388FC
0x1800388f4  lea     edi, [rax+0Eh]
0x1800388f7  jmp     loc_180038990
0x1800388fc  mov     rax, [rsp+0C8h+var_90]
0x180038901  movsxd  rdx, dword ptr [rax+18h]
0x180038905  lea     r9, [rdx+rdx*2]
0x180038909  mov     rax, [rsp+0C8h+ReferencedDomains]
0x18003890e  mov     rdx, [rax+8]
0x180038912  movzx   r8d, word ptr [rdx+r9*8]; Size
0x180038917  mov     rdx, [rdx+r9*8+8]; Src
0x18003891c  call    memcpy_0
0x180038921  mov     rax, [rsp+0C8h+var_90]
0x180038926  movsxd  rcx, dword ptr [rax+18h]
0x18003892a  lea     rdx, [rcx+rcx*2]
0x18003892e  mov     rax, [rsp+0C8h+ReferencedDomains]
0x180038933  mov     rcx, [rax+8]
0x180038937  movzx   r8d, word ptr [rcx+rdx*8]
0x18003893c  shr     r8, 1
0x18003893f  mov     rax, [rsi]
0x180038942  mov     ecx, 5Ch ; '\'
0x180038947  mov     [rax+r8*2], cx
0x18003894c  mov     rdx, [rsp+0C8h+var_90]
0x180038951  movzx   r8d, word ptr [rdx+8]; Size
0x180038956  movsxd  rax, dword ptr [rdx+18h]
0x18003895a  lea     r9, [rax+rax*2]
0x18003895e  mov     rax, [rsp+0C8h+ReferencedDomains]
0x180038963  mov     rcx, [rax+8]
0x180038967  movzx   r10d, word ptr [rcx+r9*8]
0x18003896c  shr     r10, 1
0x18003896f  mov     rax, [rsi]
0x180038972  add     rax, 2
0x180038976  lea     rcx, [rax+r10*2]; void *
0x18003897a  mov     rdx, [rdx+10h]; Src
0x18003897e  call    memcpy_0
0x180038983  mov     edx, [r15]
0x180038986  mov     rcx, [rsi]
0x180038989  mov     eax, r12d
0x18003898c  mov     [rcx+rdx*2], ax
0x180038990  mov     rcx, [rsp+0C8h+var_90]; Buffer
0x180038995  test    rcx, rcx
0x180038998  jz      short loc_1800389A0
0x18003899a  call    cs:__imp_LsaFreeMemory
0x1800389a0  mov     rcx, [rsp+0C8h+ReferencedDomains]; Buffer
0x1800389a5  test    rcx, rcx
0x1800389a8  jz      short loc_1800389B0
0x1800389aa  call    cs:__imp_LsaFreeMemory
0x1800389b0  mov     rcx, [rsp+0C8h+PolicyHandle]; ObjectHandle
0x1800389b5  test    rcx, rcx
0x1800389b8  jz      short loc_1800389C0
0x1800389ba  call    cs:__imp_LsaClose
0x1800389c0  test    ebx, ebx
0x1800389c2  jz      short loc_1800389CE
0x1800389c4  mov     ecx, ebx; Status
0x1800389c6  call    cs:__imp_RtlNtStatusToDosError
0x1800389cc  mov     edi, eax
0x1800389ce  mov     eax, edi
0x1800389d0  add     rsp, 98h
0x1800389d7  pop     r15
0x1800389d9  pop     r14
0x1800389db  pop     r12
0x1800389dd  pop     rdi
0x1800389de  pop     rsi
0x1800389df  pop     rbx
0x1800389e0  retn
0x180454698  push    rbp
0x18045469a  sub     rsp, 30h
0x18045469e  mov     rbp, rdx
0x1804546a1  mov     rcx, [rbp+38h]; Buffer
0x1804546a5  test    rcx, rcx
0x1804546a8  jz      short loc_1804546B1
0x1804546aa  call    cs:__imp_LsaFreeMemory
0x1804546b0  nop
0x1804546b1  mov     rcx, [rbp+40h]; Buffer
0x1804546b5  test    rcx, rcx
0x1804546b8  jz      short loc_1804546C1
0x1804546ba  call    cs:__imp_LsaFreeMemory
0x1804546c0  nop
0x1804546c1  mov     rcx, [rbp+50h]; ObjectHandle
0x1804546c5  test    rcx, rcx
0x1804546c8  jz      short loc_1804546D1
0x1804546ca  call    cs:__imp_LsaClose
0x1804546d0  nop
0x1804546d1  add     rsp, 30h
0x1804546d5  pop     rbp
0x1804546d6  retn
```
