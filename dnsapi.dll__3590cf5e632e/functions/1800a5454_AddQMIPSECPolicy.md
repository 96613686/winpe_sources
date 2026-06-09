# AddQMIPSECPolicy

- ea: `0x1800a5454`
- end: `0x1800a56da`
- name: `AddQMIPSECPolicy`
- size: `646`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800a5890`

## callees

- `0x1800889b8`
- `0x180088c48`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800a5454`
- `0x1800a56e0`
- `0x1800dc9e0`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800a5630`
- `RPCRT4!UuidCreate` at `0x1800a5630`
- `fwpuclnt!FwpmProviderContextAdd1` at `0x1800a5677`
- `fwpuclnt!FwpmProviderContextAdd1` at `0x1800a5677`

## pseudocode

```c
__int64 __fastcall AddQMIPSECPolicy(int a1, GUID *a2, __int64 a3)
{
  DWORD CertConfig; // eax
  void *v7; // rdi
  DWORD v8; // ebx
  int v9; // esi
  __int64 v10; // rdx
  int v12; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v14; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v15; // [rsp+50h] [rbp-B0h]
  __int128 *v16; // [rsp+60h] [rbp-A0h]
  __int128 v17; // [rsp+68h] [rbp-98h] BYREF
  __int64 v18; // [rsp+78h] [rbp-88h]
  FWPM_PROVIDER_CONTEXT1 Uuid; // [rsp+80h] [rbp-80h] BYREF
  int v20; // [rsp+E0h] [rbp-20h] BYREF
  int v21; // [rsp+E8h] [rbp-18h]
  __int64 v22; // [rsp+F0h] [rbp-10h]
  void *v23; // [rsp+F8h] [rbp-8h]
  int v24; // [rsp+100h] [rbp+0h]
  __int64 v25; // [rsp+108h] [rbp+8h]
  int v26; // [rsp+118h] [rbp+18h]
  int v27; // [rsp+130h] [rbp+30h] BYREF
  __int64 v28; // [rsp+138h] [rbp+38h]
  __int128 v29; // [rsp+140h] [rbp+40h]
  __int128 v30; // [rsp+150h] [rbp+50h]
  __int128 v31; // [rsp+160h] [rbp+60h]
  _BYTE v32[128]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v33[128]; // [rsp+1F0h] [rbp+F0h] BYREF

  v16 = 0;
  v18 = 0;
  v14 = 0;
  v15 = 0;
  v17 = 0;
  memset_0(&v20, 0, 0x50u);
  memset_0(&Uuid, 0, sizeof(Uuid));
  memset_0(v33, 0, sizeof(v33));
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  memset_0(v32, 0, sizeof(v32));
  lpMem = 0;
  v12 = 0;
  CertConfig = GetCertConfig(&lpMem, &v12, a3);
  v7 = lpMem;
  v8 = CertConfig;
  v9 = v12;
  if ( CertConfig )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
      goto LABEL_18;
    v10 = 12;
    goto LABEL_4;
  }
  CertConfig = BuildQmProposals(a1, (unsigned int)&v14, (unsigned int)v33, (unsigned int)&v27, (__int64)v32);
  v8 = CertConfig;
  if ( CertConfig )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    {
      v10 = 13;
LABEL_4:
      WPP_SF_d(1035, v10, WPP_254dea594a8e3819874328e26b99b3ad_Traceguids, CertConfig);
    }
  }
  else
  {
    v20 = 4;
    v26 = 10;
    v24 = 2;
    v25 = 0;
    if ( v9 )
    {
      v21 = 0;
      v23 = v7;
      LODWORD(v22) = v9;
    }
    else
    {
      v21 = 2;
      v22 = 0;
    }
    DWORD1(v15) = 10;
    *((_QWORD *)&v17 + 1) = &v20;
    LODWORD(v17) = 1;
    v16 = &v17;
    Uuid.displayData.name = L"DNS  QM IPSEC Policy";
    Uuid.displayData.description = L"DNS  QM IPSEC Policy";
    Uuid.keyingPolicy = (IPSEC_KEYING_POLICY0 *)&v14;
    *((_QWORD *)&v15 + 1) = 0x3C0000012CLL;
    Uuid.type = FWPM_IPSEC_AUTHIP_QM_TRANSPORT_CONTEXT;
    CertConfig = UuidCreate(&Uuid.providerContextKey);
    v8 = CertConfig;
    if ( CertConfig )
    {
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      {
        v10 = 14;
        goto LABEL_4;
      }
    }
    else
    {
      CertConfig = FwpmProviderContextAdd1(engineHandle, &Uuid, 0, 0);
      v8 = CertConfig;
      if ( CertConfig )
      {
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        {
          v10 = 15;
          goto LABEL_4;
        }
      }
      else
      {
        *a2 = Uuid.providerContextKey;
      }
    }
  }
LABEL_18:
  if ( v7 )
    FreeCertConfig(v7);
  return v8;
}

```

## disassembly

```asm
0x1800a5454  mov     [rsp-8+arg_18], rbx
0x1800a5459  push    rbp
0x1800a545a  push    rsi
0x1800a545b  push    rdi
0x1800a545c  push    r14
0x1800a545e  push    r15
0x1800a5460  lea     rbp, [rsp-180h]
0x1800a5468  sub     rsp, 280h
0x1800a546f  mov     rax, cs:__security_cookie
0x1800a5476  xor     rax, rsp
0x1800a5479  mov     [rbp+1A0h+var_30], rax
0x1800a5480  xor     eax, eax
0x1800a5482  xorps   xmm0, xmm0
0x1800a5485  mov     rbx, r8
0x1800a5488  mov     [rsp+2A0h+var_240], rax
0x1800a548d  mov     r15, rdx
0x1800a5490  mov     [rsp+2A0h+var_228], rax
0x1800a5495  mov     r14d, ecx
0x1800a5498  xor     edx, edx; Val
0x1800a549a  lea     r8d, [rax+50h]; Size
0x1800a549e  lea     rcx, [rbp+1A0h+var_1C0]; void *
0x1800a54a2  movups  [rsp+2A0h+var_260], xmm0
0x1800a54a7  movups  [rsp+2A0h+var_250], xmm0
0x1800a54ac  movups  [rsp+2A0h+var_238], xmm0
0x1800a54b1  call    memset_0
0x1800a54b6  xor     edx, edx; Val
0x1800a54b8  lea     rcx, [rbp+1A0h+Uuid]; void *
0x1800a54bc  lea     r8d, [rdx+58h]; Size
0x1800a54c0  call    memset_0
0x1800a54c5  mov     edi, 80h
0x1800a54ca  lea     rcx, [rbp+1A0h+var_B0]; void *
0x1800a54d1  mov     r8d, edi; Size
0x1800a54d4  xor     edx, edx; Val
0x1800a54d6  call    memset_0
0x1800a54db  xorps   xmm0, xmm0
0x1800a54de  mov     [rbp+1A0h+var_170], 0
0x1800a54e5  xor     eax, eax
0x1800a54e7  lea     rcx, [rbp+1A0h+var_130]; void *
0x1800a54eb  mov     r8d, edi; Size
0x1800a54ee  mov     [rbp+1A0h+var_168], rax
0x1800a54f2  xor     edx, edx; Val
0x1800a54f4  movups  [rbp+1A0h+var_160], xmm0
0x1800a54f8  movups  [rbp+1A0h+var_150], xmm0
0x1800a54fc  movups  [rbp+1A0h+var_140], xmm0
0x1800a5500  call    memset_0
0x1800a5505  mov     r8, rbx
0x1800a5508  mov     [rsp+2A0h+lpMem], 0
0x1800a5511  lea     rdx, [rsp+2A0h+var_270]
0x1800a5516  mov     [rsp+2A0h+var_270], 0
0x1800a551e  lea     rcx, [rsp+2A0h+lpMem]
0x1800a5523  call    GetCertConfig
0x1800a5528  mov     rdi, [rsp+2A0h+lpMem]
0x1800a552d  mov     ebx, eax
0x1800a552f  mov     esi, [rsp+2A0h+var_270]
0x1800a5533  test    eax, eax
0x1800a5535  jz      short loc_1800A5562
0x1800a5537  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800a553e  jz      loc_1800A56A2
0x1800a5544  mov     edx, 0Ch
0x1800a5549  mov     ecx, 40Bh
0x1800a554e  lea     r8, WPP_254dea594a8e3819874328e26b99b3ad_Traceguids
0x1800a5555  mov     r9d, eax
0x1800a5558  call    WPP_SF_d
0x1800a555d  jmp     loc_1800A56A2
0x1800a5562  lea     rax, [rbp+1A0h+var_130]
0x1800a5566  mov     ecx, r14d
0x1800a5569  lea     r9, [rbp+1A0h+var_170]
0x1800a556d  mov     [rsp+2A0h+var_280], rax
0x1800a5572  lea     r8, [rbp+1A0h+var_B0]
0x1800a5579  lea     rdx, [rsp+2A0h+var_260]
0x1800a557e  call    BuildQmProposals
0x1800a5583  mov     ebx, eax
0x1800a5585  test    eax, eax
0x1800a5587  jz      short loc_1800A559D
0x1800a5589  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800a5590  jz      loc_1800A56A2
0x1800a5596  mov     edx, 0Dh
0x1800a559b  jmp     short loc_1800A5549
0x1800a559d  mov     [rbp+1A0h+var_1C0], 4
0x1800a55a4  mov     ecx, 0Ah
0x1800a55a9  mov     [rbp+1A0h+var_188], ecx
0x1800a55ac  mov     [rbp+1A0h+var_1A0], 2
0x1800a55b3  mov     [rbp+1A0h+var_198], 0
0x1800a55bb  test    esi, esi
0x1800a55bd  jnz     short loc_1800A55D0
0x1800a55bf  mov     [rbp+1A0h+var_1B8], 2
0x1800a55c6  mov     [rbp+1A0h+var_1B0], 0
0x1800a55ce  jmp     short loc_1800A55DE
0x1800a55d0  mov     [rbp+1A0h+var_1B8], 0
0x1800a55d7  mov     [rbp+1A0h+var_1A8], rdi
0x1800a55db  mov     dword ptr [rbp+1A0h+var_1B0], esi
0x1800a55de  lea     rax, [rbp+1A0h+var_1C0]
0x1800a55e2  mov     dword ptr [rsp+2A0h+var_250+4], ecx
0x1800a55e6  mov     qword ptr [rsp+2A0h+var_238+8], rax
0x1800a55eb  lea     rcx, [rbp+1A0h+Uuid]; Uuid
0x1800a55ef  lea     rax, [rsp+2A0h+var_238]
0x1800a55f4  mov     dword ptr [rsp+2A0h+var_238], 1
0x1800a55fc  mov     [rsp+2A0h+var_240], rax
0x1800a5601  lea     rax, aDnsQmIpsecPoli; "DNS  QM IPSEC Policy"
0x1800a5608  mov     [rbp+1A0h+var_210], rax
0x1800a560c  mov     [rbp+1A0h+var_208], rax
0x1800a5610  lea     rax, [rsp+2A0h+var_260]
0x1800a5615  mov     [rbp+1A0h+var_1D8], rax
0x1800a5619  mov     dword ptr [rsp+2A0h+var_250+8], 12Ch
0x1800a5621  mov     dword ptr [rsp+2A0h+var_250+0Ch], 3Ch ; '<'
0x1800a5629  mov     [rbp+1A0h+var_1E0], 3
0x1800a5630  call    cs:__imp_UuidCreate
0x1800a5637  nop     dword ptr [rax+rax+00h]
0x1800a563c  mov     ebx, eax
0x1800a563e  test    eax, eax
0x1800a5640  jz      short loc_1800A5666
0x1800a5642  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800a5649  jz      short loc_1800A56A2
0x1800a564b  mov     edx, 0Eh
0x1800a5650  mov     ecx, 40Bh
0x1800a5655  lea     r8, WPP_254dea594a8e3819874328e26b99b3ad_Traceguids
0x1800a565c  mov     r9d, eax
0x1800a565f  call    WPP_SF_d
0x1800a5664  jmp     short loc_1800A56A2
0x1800a5666  mov     rcx, cs:engineHandle; engineHandle
0x1800a566d  lea     rdx, [rbp+1A0h+Uuid]; providerContext
0x1800a5671  xor     r9d, r9d; id
0x1800a5674  xor     r8d, r8d; sd
0x1800a5677  call    cs:__imp_FwpmProviderContextAdd1
0x1800a567e  nop     dword ptr [rax+rax+00h]
0x1800a5683  mov     ebx, eax
0x1800a5685  test    eax, eax
0x1800a5687  jz      short loc_1800A5699
0x1800a5689  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800a5690  jz      short loc_1800A56A2
0x1800a5692  mov     edx, 0Fh
0x1800a5697  jmp     short loc_1800A5650
0x1800a5699  movaps  xmm0, xmmword ptr [rbp+1A0h+Uuid.Data1]
0x1800a569d  movdqu  xmmword ptr [r15], xmm0
0x1800a56a2  test    rdi, rdi
0x1800a56a5  jz      short loc_1800A56B1
0x1800a56a7  mov     edx, esi
0x1800a56a9  mov     rcx, rdi; lpMem
0x1800a56ac  call    FreeCertConfig
0x1800a56b1  mov     eax, ebx
0x1800a56b3  mov     rcx, [rbp+1A0h+var_30]
0x1800a56ba  xor     rcx, rsp; StackCookie
0x1800a56bd  call    __security_check_cookie
0x1800a56c2  mov     rbx, [rsp+2A0h+arg_18]
0x1800a56ca  add     rsp, 280h
0x1800a56d1  pop     r15
0x1800a56d3  pop     r14
0x1800a56d5  pop     rdi
0x1800a56d6  pop     rsi
0x1800a56d7  pop     rbp
0x1800a56d8  retn
```
