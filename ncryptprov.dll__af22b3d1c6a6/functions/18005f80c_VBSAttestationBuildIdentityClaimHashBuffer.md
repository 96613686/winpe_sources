# VBSAttestationBuildIdentityClaimHashBuffer

- ea: `0x18005f80c`
- end: `0x18005faaf`
- name: `VBSAttestationBuildIdentityClaimHashBuffer`
- size: `675`
- prototype: `__int64 __fastcall(BCRYPT_HANDLE hObject, UCHAR **, UCHAR *, __int64, PUCHAR, PUCHAR, PUCHAR, PUCHAR, PUCHAR pbInput)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004fb48`

## callees

- `0x18000af80`
- `0x18000d3d0`
- `0x18000def0`
- `0x18005f4d8`
- `0x18005f80c`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18005f869`
- `bcrypt!BCryptCreateHash` at `0x18005f869`
- `bcrypt!BCryptHashData` at `0x18005f909`
- `bcrypt!BCryptHashData` at `0x18005f934`
- `bcrypt!BCryptHashData` at `0x18005f95f`
- `bcrypt!BCryptHashData` at `0x18005f98a`
- `bcrypt!BCryptHashData` at `0x18005f909`
- `bcrypt!BCryptHashData` at `0x18005f934`
- `bcrypt!BCryptHashData` at `0x18005f95f`
- `bcrypt!BCryptHashData` at `0x18005f98a`
- `bcrypt!BCryptDestroyHash` at `0x18005fa8f`
- `bcrypt!BCryptDestroyHash` at `0x18005fa8f`
- `bcrypt!BCryptFinishHash` at `0x18005fa1e`
- `bcrypt!BCryptFinishHash` at `0x18005fa1e`
- `bcrypt!BCryptGetProperty` at `0x18005f9c5`
- `bcrypt!BCryptGetProperty` at `0x18005f9c5`

## string_xrefs

- `0x18005f883`: `onecore\ds\security\cryptoapi\ncrypt\common\vbsattestation\vbsattesthelper.cxx`
- `0x18005fa66`: `onecore\ds\security\cryptoapi\ncrypt\common\vbsattestation\vbsattesthelper.cxx`

## pseudocode

```c
__int64 __fastcall VBSAttestationBuildIdentityClaimHashBuffer(
        BCRYPT_HANDLE hObject,
        UCHAR **a2,
        UCHAR *a3,
        __int64 a4,
        PUCHAR a5,
        PUCHAR a6,
        PUCHAR a7,
        PUCHAR a8,
        PUCHAR pbInput)
{
  PUCHAR v12; // rdi
  NTSTATUS Property; // eax
  unsigned int v14; // ebx
  __int64 v15; // r9
  __int64 v16; // rcx
  UCHAR *v17; // rax
  UCHAR *v18; // rdi
  NTSTATUS v19; // eax
  __int64 v20; // rcx
  __int64 v21; // r9
  BCRYPT_HASH_HANDLE phHash; // [rsp+60h] [rbp-18h] BYREF
  ULONG pcbResult; // [rsp+D0h] [rbp+58h] BYREF

  phHash = 0;
  pcbResult = 0;
  if ( a3 && (v12 = pbInput) != 0 )
  {
    Property = BCryptCreateHash(hObject, &phHash, 0, 0, 0, 0, 0);
    v14 = Property;
    if ( Property < 0 )
    {
      v15 = 449;
LABEL_5:
      v16 = (unsigned int)Property;
LABEL_6:
      DebugTraceError(
        v16,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\vbsattestation\\vbsattesthelper.cxx",
        v15);
      goto LABEL_30;
    }
    Property = VBSAttestationHashClaimGeneralParams(
                 phHash,
                 a5,
                 *((_DWORD *)v12 + 3),
                 a6,
                 *((_DWORD *)v12 + 4),
                 a7,
                 *((_DWORD *)v12 + 6),
                 a8);
    v14 = Property;
    if ( Property < 0 )
    {
      v15 = 467;
      goto LABEL_5;
    }
    Property = BCryptHashData(phHash, v12, 4u, 0);
    v14 = Property;
    if ( Property < 0 )
    {
      v15 = 478;
      goto LABEL_5;
    }
    Property = BCryptHashData(phHash, v12 + 4, 4u, 0);
    v14 = Property;
    if ( Property < 0 )
    {
      v15 = 489;
      goto LABEL_5;
    }
    Property = BCryptHashData(phHash, v12 + 16, 4u, 0);
    v14 = Property;
    if ( Property < 0 )
    {
      v15 = 500;
      goto LABEL_5;
    }
    Property = BCryptHashData(phHash, v12 + 20, 4u, 0);
    v14 = Property;
    if ( Property < 0 )
    {
      v15 = 511;
      goto LABEL_5;
    }
    Property = BCryptGetProperty(hObject, L"HashDigestLength", a3, 4u, &pcbResult, 0);
    v14 = Property;
    if ( Property < 0 )
    {
      v15 = 525;
      goto LABEL_5;
    }
    if ( !pcbResult || !*(_DWORD *)a3 )
    {
      v14 = -1073741595;
      v15 = 533;
      v16 = 3221225701LL;
      goto LABEL_6;
    }
    v17 = (UCHAR *)SafeAllocaAllocateFromHeap(*(unsigned int *)a3);
    v18 = v17;
    if ( !v17 )
    {
      v14 = -1073741801;
      v15 = 542;
      v16 = 3221225495LL;
      goto LABEL_6;
    }
    v19 = BCryptFinishHash(phHash, v17, *(_DWORD *)a3, 0);
    v14 = v19;
    if ( v19 >= 0 )
    {
      *a2 = v18;
      goto LABEL_30;
    }
    v20 = (unsigned int)v19;
    v21 = 554;
  }
  else
  {
    v18 = 0;
    v14 = -1073741595;
    v20 = 3221225701LL;
    v21 = 434;
  }
  DebugTraceError(
    v20,
    "Status",
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\vbsattestation\\vbsattesthelper.cxx",
    v21);
  if ( v18 )
    MSCryptFree(v18);
LABEL_30:
  if ( phHash )
    BCryptDestroyHash(phHash);
  return v14;
}

```

## disassembly

```asm
0x18005f80c  push    rbp
0x18005f80e  push    rbx
0x18005f80f  push    rsi
0x18005f810  push    rdi
0x18005f811  push    r12
0x18005f813  push    r13
0x18005f815  push    r14
0x18005f817  push    r15
0x18005f819  mov     rbp, rsp
0x18005f81c  sub     rsp, 78h
0x18005f820  xor     r13d, r13d
0x18005f823  mov     r12, r9
0x18005f826  mov     [rbp+phHash], r13
0x18005f82a  mov     rsi, r8
0x18005f82d  mov     [rbp+pcbResult], r13d
0x18005f831  mov     r15, rdx
0x18005f834  mov     r14, rcx
0x18005f837  test    r8, r8
0x18005f83a  jz      loc_18005FA54
0x18005f840  mov     rdi, [rbp+pbInput]
0x18005f847  test    rdi, rdi
0x18005f84a  jz      loc_18005FA54
0x18005f850  mov     [rsp+78h+dwFlags], r13d; dwFlags
0x18005f855  lea     rdx, [rbp+phHash]; phHash
0x18005f859  mov     [rsp+78h+cbSecret], r13d; cbSecret
0x18005f85e  xor     r9d, r9d; cbHashObject
0x18005f861  xor     r8d, r8d; pbHashObject
0x18005f864  mov     [rsp+78h+pbSecret], r13; pbSecret
0x18005f869  call    cs:__imp_BCryptCreateHash
0x18005f870  nop     dword ptr [rax+rax+00h]
0x18005f875  mov     ebx, eax
0x18005f877  test    eax, eax
0x18005f879  jns     short loc_18005F89B
0x18005f87b  mov     r9d, 1C1h
0x18005f881  mov     ecx, eax
0x18005f883  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005f88a  lea     rdx, aStatus; "Status"
0x18005f891  call    DebugTraceError
0x18005f896  jmp     loc_18005FA86
0x18005f89b  mov     rax, [rbp+arg_38]
0x18005f8a2  mov     r8, r12
0x18005f8a5  mov     r9d, [rdi+8]
0x18005f8a9  mov     edx, [rdi+1Ch]
0x18005f8ac  mov     rcx, [rbp+phHash]; hHash
0x18005f8b0  mov     [rsp+78h+var_28], rax; PUCHAR
0x18005f8b5  mov     eax, [rdi+18h]
0x18005f8b8  mov     [rsp+78h+var_30], eax; ULONG
0x18005f8bc  mov     rax, [rbp+arg_30]
0x18005f8c0  mov     [rsp+78h+var_38], rax; PUCHAR
0x18005f8c5  mov     eax, [rdi+10h]
0x18005f8c8  mov     [rsp+78h+var_40], eax; ULONG
0x18005f8cc  mov     rax, [rbp+arg_28]
0x18005f8d0  mov     qword ptr [rsp+78h+dwFlags], rax; PUCHAR
0x18005f8d5  mov     eax, [rdi+0Ch]
0x18005f8d8  mov     [rsp+78h+cbSecret], eax; cbInput
0x18005f8dc  mov     rax, [rbp+arg_20]
0x18005f8e0  mov     [rsp+78h+pbSecret], rax; PUCHAR
0x18005f8e5  call    VBSAttestationHashClaimGeneralParams
0x18005f8ea  mov     ebx, eax
0x18005f8ec  test    eax, eax
0x18005f8ee  jns     short loc_18005F8F8
0x18005f8f0  mov     r9d, 1D3h
0x18005f8f6  jmp     short loc_18005F881
0x18005f8f8  mov     rcx, [rbp+phHash]; hHash
0x18005f8fc  xor     r9d, r9d; dwFlags
0x18005f8ff  mov     rdx, rdi; pbInput
0x18005f902  lea     r12d, [r9+4]
0x18005f906  mov     r8d, r12d; cbInput
0x18005f909  call    cs:__imp_BCryptHashData
0x18005f910  nop     dword ptr [rax+rax+00h]
0x18005f915  mov     ebx, eax
0x18005f917  test    eax, eax
0x18005f919  jns     short loc_18005F926
0x18005f91b  mov     r9d, 1DEh
0x18005f921  jmp     loc_18005F881
0x18005f926  mov     rcx, [rbp+phHash]; hHash
0x18005f92a  lea     rdx, [rdi+4]; pbInput
0x18005f92e  xor     r9d, r9d; dwFlags
0x18005f931  mov     r8d, r12d; cbInput
0x18005f934  call    cs:__imp_BCryptHashData
0x18005f93b  nop     dword ptr [rax+rax+00h]
0x18005f940  mov     ebx, eax
0x18005f942  test    eax, eax
0x18005f944  jns     short loc_18005F951
0x18005f946  mov     r9d, 1E9h
0x18005f94c  jmp     loc_18005F881
0x18005f951  mov     rcx, [rbp+phHash]; hHash
0x18005f955  lea     rdx, [rdi+10h]; pbInput
0x18005f959  xor     r9d, r9d; dwFlags
0x18005f95c  mov     r8d, r12d; cbInput
0x18005f95f  call    cs:__imp_BCryptHashData
0x18005f966  nop     dword ptr [rax+rax+00h]
0x18005f96b  mov     ebx, eax
0x18005f96d  test    eax, eax
0x18005f96f  jns     short loc_18005F97C
0x18005f971  mov     r9d, 1F4h
0x18005f977  jmp     loc_18005F881
0x18005f97c  mov     rcx, [rbp+phHash]; hHash
0x18005f980  lea     rdx, [rdi+14h]; pbInput
0x18005f984  xor     r9d, r9d; dwFlags
0x18005f987  mov     r8d, r12d; cbInput
0x18005f98a  call    cs:__imp_BCryptHashData
0x18005f991  nop     dword ptr [rax+rax+00h]
0x18005f996  mov     ebx, eax
0x18005f998  test    eax, eax
0x18005f99a  jns     short loc_18005F9A7
0x18005f99c  mov     r9d, 1FFh
0x18005f9a2  jmp     loc_18005F881
0x18005f9a7  lea     rax, [rbp+pcbResult]
0x18005f9ab  mov     [rsp+78h+cbSecret], r13d; dwFlags
0x18005f9b0  mov     r9d, r12d; cbOutput
0x18005f9b3  mov     [rsp+78h+pbSecret], rax; pcbResult
0x18005f9b8  mov     r8, rsi; pbOutput
0x18005f9bb  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18005f9c2  mov     rcx, r14; hObject
0x18005f9c5  call    cs:__imp_BCryptGetProperty
0x18005f9cc  nop     dword ptr [rax+rax+00h]
0x18005f9d1  mov     ebx, eax
0x18005f9d3  test    eax, eax
0x18005f9d5  jns     short loc_18005F9E2
0x18005f9d7  mov     r9d, 20Dh
0x18005f9dd  jmp     loc_18005F881
0x18005f9e2  cmp     [rbp+pcbResult], r13d
0x18005f9e6  jz      short loc_18005FA3F
0x18005f9e8  cmp     [rsi], r13d
0x18005f9eb  jz      short loc_18005FA3F
0x18005f9ed  mov     ecx, [rsi]
0x18005f9ef  call    SafeAllocaAllocateFromHeap
0x18005f9f4  mov     rdi, rax
0x18005f9f7  test    rax, rax
0x18005f9fa  jnz     short loc_18005FA11
0x18005f9fc  mov     ebx, 0C0000017h
0x18005fa01  mov     r9d, 21Eh
0x18005fa07  mov     ecx, 0C0000017h
0x18005fa0c  jmp     loc_18005F883
0x18005fa11  mov     r8d, [rsi]; cbOutput
0x18005fa14  xor     r9d, r9d; dwFlags
0x18005fa17  mov     rcx, [rbp+phHash]; hHash
0x18005fa1b  mov     rdx, rdi; pbOutput
0x18005fa1e  call    cs:__imp_BCryptFinishHash
0x18005fa25  nop     dword ptr [rax+rax+00h]
0x18005fa2a  mov     ebx, eax
0x18005fa2c  test    eax, eax
0x18005fa2e  jns     short loc_18005FA3A
0x18005fa30  mov     ecx, eax
0x18005fa32  mov     r9d, 22Ah
0x18005fa38  jmp     short loc_18005FA66
0x18005fa3a  mov     [r15], rdi
0x18005fa3d  jmp     short loc_18005FA86
0x18005fa3f  mov     ebx, 0C00000E5h
0x18005fa44  mov     r9d, 215h
0x18005fa4a  mov     ecx, 0C00000E5h
0x18005fa4f  jmp     loc_18005F883
0x18005fa54  xor     edi, edi
0x18005fa56  mov     ebx, 0C00000E5h
0x18005fa5b  mov     ecx, 0C00000E5h
0x18005fa60  mov     r9d, 1B2h
0x18005fa66  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005fa6d  lea     rdx, aStatus; "Status"
0x18005fa74  call    DebugTraceError
0x18005fa79  test    rdi, rdi
0x18005fa7c  jz      short loc_18005FA86
0x18005fa7e  mov     rcx, rdi
0x18005fa81  call    MSCryptFree
0x18005fa86  mov     rcx, [rbp+phHash]; hHash
0x18005fa8a  test    rcx, rcx
0x18005fa8d  jz      short loc_18005FA9B
0x18005fa8f  call    cs:__imp_BCryptDestroyHash
0x18005fa96  nop     dword ptr [rax+rax+00h]
0x18005fa9b  mov     eax, ebx
0x18005fa9d  add     rsp, 78h
0x18005faa1  pop     r15
0x18005faa3  pop     r14
0x18005faa5  pop     r13
0x18005faa7  pop     r12
0x18005faa9  pop     rdi
0x18005faaa  pop     rsi
0x18005faab  pop     rbx
0x18005faac  pop     rbp
0x18005faad  retn
```
