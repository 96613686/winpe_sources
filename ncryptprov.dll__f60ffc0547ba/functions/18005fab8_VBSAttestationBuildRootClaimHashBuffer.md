# VBSAttestationBuildRootClaimHashBuffer

- ea: `0x18005fab8`
- end: `0x18005fd4c`
- name: `VBSAttestationBuildRootClaimHashBuffer`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004ff08`

## callees

- `0x18000af80`
- `0x18000d3d0`
- `0x18000def0`
- `0x18005f4d8`
- `0x18005fab8`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18005fb16`
- `bcrypt!BCryptCreateHash` at `0x18005fb16`
- `bcrypt!BCryptHashData` at `0x18005fbb3`
- `bcrypt!BCryptHashData` at `0x18005fbe2`
- `bcrypt!BCryptHashData` at `0x18005fc11`
- `bcrypt!BCryptHashData` at `0x18005fbb3`
- `bcrypt!BCryptHashData` at `0x18005fbe2`
- `bcrypt!BCryptHashData` at `0x18005fc11`
- `bcrypt!BCryptDestroyHash` at `0x18005fd29`
- `bcrypt!BCryptDestroyHash` at `0x18005fd29`
- `bcrypt!BCryptFinishHash` at `0x18005fcb3`
- `bcrypt!BCryptFinishHash` at `0x18005fcb3`
- `bcrypt!BCryptGetProperty` at `0x18005fc52`
- `bcrypt!BCryptGetProperty` at `0x18005fc52`

## string_xrefs

- `0x18005fb30`: `onecore\ds\security\cryptoapi\ncrypt\common\vbsattestation\vbsattesthelper.cxx`
- `0x18005fcfc`: `onecore\ds\security\cryptoapi\ncrypt\common\vbsattestation\vbsattesthelper.cxx`

## pseudocode

```c
__int64 __fastcall VBSAttestationBuildRootClaimHashBuffer(
        __int64 a1,
        UCHAR **a2,
        UCHAR *a3,
        __int64 a4,
        PUCHAR a5,
        ULONG cbInput,
        PUCHAR pbInput)
{
  PUCHAR v9; // rdi
  NTSTATUS Property; // eax
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rcx
  UCHAR *v14; // rax
  UCHAR *v15; // rdi
  NTSTATUS v16; // eax
  __int64 v17; // rcx
  __int64 v18; // r9
  ULONG pcbResult; // [rsp+90h] [rbp+8h] BYREF
  int v21; // [rsp+94h] [rbp+Ch]
  BCRYPT_HASH_HANDLE hHash; // [rsp+A0h] [rbp+18h] BYREF

  v21 = HIDWORD(a1);
  hHash = 0;
  pcbResult = 0;
  if ( a3 && (v9 = pbInput) != 0 )
  {
    Property = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &hHash, 0, 0, 0, 0, 0);
    v11 = Property;
    if ( Property < 0 )
    {
      v12 = 297;
LABEL_5:
      v13 = (unsigned int)Property;
LABEL_6:
      DebugTraceError(
        v13,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\vbsattestation\\vbsattesthelper.cxx",
        v12);
      goto LABEL_28;
    }
    Property = VBSAttestationHashClaimGeneralParams(hHash, a5, cbInput, 0, 0, 0, 0, 0);
    v11 = Property;
    if ( Property < 0 )
    {
      v12 = 315;
      goto LABEL_5;
    }
    Property = BCryptHashData(hHash, v9, 4u, 0);
    v11 = Property;
    if ( Property < 0 )
    {
      v12 = 326;
      goto LABEL_5;
    }
    Property = BCryptHashData(hHash, v9 + 4, 4u, 0);
    v11 = Property;
    if ( Property < 0 )
    {
      v12 = 337;
      goto LABEL_5;
    }
    Property = BCryptHashData(hHash, v9 + 16, 4u, 0);
    v11 = Property;
    if ( Property < 0 )
    {
      v12 = 349;
      goto LABEL_5;
    }
    Property = BCryptGetProperty((BCRYPT_HANDLE)0x41, L"HashDigestLength", a3, 4u, &pcbResult, 0);
    v11 = Property;
    if ( Property < 0 )
    {
      v12 = 363;
      goto LABEL_5;
    }
    if ( !pcbResult || !*(_DWORD *)a3 )
    {
      v11 = -1073741595;
      v12 = 371;
      v13 = 3221225701LL;
      goto LABEL_6;
    }
    v14 = (UCHAR *)SafeAllocaAllocateFromHeap(*(unsigned int *)a3);
    v15 = v14;
    if ( !v14 )
    {
      v11 = -1073741801;
      v12 = 380;
      v13 = 3221225495LL;
      goto LABEL_6;
    }
    v16 = BCryptFinishHash(hHash, v14, *(_DWORD *)a3, 0);
    v11 = v16;
    if ( v16 >= 0 )
    {
      *a2 = v15;
      goto LABEL_28;
    }
    v17 = (unsigned int)v16;
    v18 = 392;
  }
  else
  {
    v15 = 0;
    v11 = -1073741595;
    v17 = 3221225701LL;
    v18 = 282;
  }
  DebugTraceError(
    v17,
    "Status",
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\vbsattestation\\vbsattesthelper.cxx",
    v18);
  if ( v15 )
    MSCryptFree(v15);
LABEL_28:
  if ( hHash )
    BCryptDestroyHash(hHash);
  return v11;
}

```

## disassembly

```asm
0x18005fab8  mov     rax, rsp
0x18005fabb  mov     [rax+10h], rbx
0x18005fabf  mov     [rax+8], rcx
0x18005fac3  push    rbp
0x18005fac4  push    rsi
0x18005fac5  push    rdi
0x18005fac6  push    r14
0x18005fac8  push    r15
0x18005faca  sub     rsp, 60h
0x18005face  xor     r15d, r15d
0x18005fad1  mov     rbp, r9
0x18005fad4  mov     [rax+18h], r15
0x18005fad8  mov     rsi, r8
0x18005fadb  mov     [rax+8], r15d
0x18005fadf  mov     r14, rdx
0x18005fae2  test    r8, r8
0x18005fae5  jz      loc_18005FCE9
0x18005faeb  mov     rdi, [rsp+88h+pbInput]
0x18005faf3  test    rdi, rdi
0x18005faf6  jz      loc_18005FCE9
0x18005fafc  mov     [rax-58h], r15d
0x18005fb00  lea     rdx, [rax+18h]; phHash
0x18005fb04  mov     [rax-60h], r15d
0x18005fb08  lea     ecx, [r15+41h]; hAlgorithm
0x18005fb0c  xor     r9d, r9d; cbHashObject
0x18005fb0f  mov     [rax-68h], r15
0x18005fb13  xor     r8d, r8d; pbHashObject
0x18005fb16  call    cs:__imp_BCryptCreateHash
0x18005fb1d  nop     dword ptr [rax+rax+00h]
0x18005fb22  mov     ebx, eax
0x18005fb24  test    eax, eax
0x18005fb26  jns     short loc_18005FB48
0x18005fb28  mov     r9d, 129h
0x18005fb2e  mov     ecx, eax
0x18005fb30  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005fb37  lea     rdx, aStatus; "Status"
0x18005fb3e  call    DebugTraceError
0x18005fb43  jmp     loc_18005FD1C
0x18005fb48  mov     eax, [rsp+88h+cbInput]
0x18005fb4f  mov     r8, rbp
0x18005fb52  mov     r9d, [rdi+8]
0x18005fb56  mov     edx, [rdi+14h]
0x18005fb59  mov     rcx, [rsp+88h+hHash]; hHash
0x18005fb61  mov     [rsp+88h+var_38], r15; PUCHAR
0x18005fb66  mov     [rsp+88h+var_40], r15d; ULONG
0x18005fb6b  mov     [rsp+88h+var_48], r15; PUCHAR
0x18005fb70  mov     [rsp+88h+var_50], r15d; ULONG
0x18005fb75  mov     [rsp+88h+var_58], r15; PUCHAR
0x18005fb7a  mov     [rsp+88h+dwFlags], eax; cbInput
0x18005fb7e  mov     rax, [rsp+88h+arg_20]
0x18005fb86  mov     [rsp+88h+pcbResult], rax; PUCHAR
0x18005fb8b  call    VBSAttestationHashClaimGeneralParams
0x18005fb90  mov     ebx, eax
0x18005fb92  test    eax, eax
0x18005fb94  jns     short loc_18005FB9E
0x18005fb96  mov     r9d, 13Bh
0x18005fb9c  jmp     short loc_18005FB2E
0x18005fb9e  mov     rcx, [rsp+88h+hHash]; hHash
0x18005fba6  xor     r9d, r9d; dwFlags
0x18005fba9  mov     rdx, rdi; pbInput
0x18005fbac  lea     ebp, [r9+4]
0x18005fbb0  mov     r8d, ebp; cbInput
0x18005fbb3  call    cs:__imp_BCryptHashData
0x18005fbba  nop     dword ptr [rax+rax+00h]
0x18005fbbf  mov     ebx, eax
0x18005fbc1  test    eax, eax
0x18005fbc3  jns     short loc_18005FBD0
0x18005fbc5  mov     r9d, 146h
0x18005fbcb  jmp     loc_18005FB2E
0x18005fbd0  mov     rcx, [rsp+88h+hHash]; hHash
0x18005fbd8  lea     rdx, [rdi+4]; pbInput
0x18005fbdc  xor     r9d, r9d; dwFlags
0x18005fbdf  mov     r8d, ebp; cbInput
0x18005fbe2  call    cs:__imp_BCryptHashData
0x18005fbe9  nop     dword ptr [rax+rax+00h]
0x18005fbee  mov     ebx, eax
0x18005fbf0  test    eax, eax
0x18005fbf2  jns     short loc_18005FBFF
0x18005fbf4  mov     r9d, 151h
0x18005fbfa  jmp     loc_18005FB2E
0x18005fbff  mov     rcx, [rsp+88h+hHash]; hHash
0x18005fc07  lea     rdx, [rdi+10h]; pbInput
0x18005fc0b  xor     r9d, r9d; dwFlags
0x18005fc0e  mov     r8d, ebp; cbInput
0x18005fc11  call    cs:__imp_BCryptHashData
0x18005fc18  nop     dword ptr [rax+rax+00h]
0x18005fc1d  mov     ebx, eax
0x18005fc1f  test    eax, eax
0x18005fc21  jns     short loc_18005FC2E
0x18005fc23  mov     r9d, 15Dh
0x18005fc29  jmp     loc_18005FB2E
0x18005fc2e  lea     rax, [rsp+88h+arg_0]
0x18005fc36  mov     [rsp+88h+dwFlags], r15d; dwFlags
0x18005fc3b  mov     r9d, ebp; cbOutput
0x18005fc3e  mov     [rsp+88h+pcbResult], rax; pcbResult
0x18005fc43  mov     r8, rsi; pbOutput
0x18005fc46  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18005fc4d  mov     ecx, 41h ; 'A'; hObject
0x18005fc52  call    cs:__imp_BCryptGetProperty
0x18005fc59  nop     dword ptr [rax+rax+00h]
0x18005fc5e  mov     ebx, eax
0x18005fc60  test    eax, eax
0x18005fc62  jns     short loc_18005FC6F
0x18005fc64  mov     r9d, 16Bh
0x18005fc6a  jmp     loc_18005FB2E
0x18005fc6f  cmp     [rsp+88h+arg_0], r15d
0x18005fc77  jz      short loc_18005FCD4
0x18005fc79  cmp     [rsi], r15d
0x18005fc7c  jz      short loc_18005FCD4
0x18005fc7e  mov     ecx, [rsi]
0x18005fc80  call    SafeAllocaAllocateFromHeap
0x18005fc85  mov     rdi, rax
0x18005fc88  test    rax, rax
0x18005fc8b  jnz     short loc_18005FCA2
0x18005fc8d  mov     ebx, 0C0000017h
0x18005fc92  mov     r9d, 17Ch
0x18005fc98  mov     ecx, 0C0000017h
0x18005fc9d  jmp     loc_18005FB30
0x18005fca2  mov     r8d, [rsi]; cbOutput
0x18005fca5  xor     r9d, r9d; dwFlags
0x18005fca8  mov     rcx, [rsp+88h+hHash]; hHash
0x18005fcb0  mov     rdx, rdi; pbOutput
0x18005fcb3  call    cs:__imp_BCryptFinishHash
0x18005fcba  nop     dword ptr [rax+rax+00h]
0x18005fcbf  mov     ebx, eax
0x18005fcc1  test    eax, eax
0x18005fcc3  jns     short loc_18005FCCF
0x18005fcc5  mov     ecx, eax
0x18005fcc7  mov     r9d, 188h
0x18005fccd  jmp     short loc_18005FCFC
0x18005fccf  mov     [r14], rdi
0x18005fcd2  jmp     short loc_18005FD1C
0x18005fcd4  mov     ebx, 0C00000E5h
0x18005fcd9  mov     r9d, 173h
0x18005fcdf  mov     ecx, 0C00000E5h
0x18005fce4  jmp     loc_18005FB30
0x18005fce9  mov     rdi, r15
0x18005fcec  mov     ebx, 0C00000E5h
0x18005fcf1  mov     ecx, 0C00000E5h
0x18005fcf6  mov     r9d, 11Ah
0x18005fcfc  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005fd03  lea     rdx, aStatus; "Status"
0x18005fd0a  call    DebugTraceError
0x18005fd0f  test    rdi, rdi
0x18005fd12  jz      short loc_18005FD1C
0x18005fd14  mov     rcx, rdi
0x18005fd17  call    MSCryptFree
0x18005fd1c  mov     rcx, [rsp+88h+hHash]; hHash
0x18005fd24  test    rcx, rcx
0x18005fd27  jz      short loc_18005FD35
0x18005fd29  call    cs:__imp_BCryptDestroyHash
0x18005fd30  nop     dword ptr [rax+rax+00h]
0x18005fd35  mov     eax, ebx
0x18005fd37  mov     rbx, [rsp+88h+arg_8]
0x18005fd3f  add     rsp, 60h
0x18005fd43  pop     r15
0x18005fd45  pop     r14
0x18005fd47  pop     rdi
0x18005fd48  pop     rsi
0x18005fd49  pop     rbp
0x18005fd4a  retn
```
