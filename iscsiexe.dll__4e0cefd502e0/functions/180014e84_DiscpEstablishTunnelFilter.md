# DiscpEstablishTunnelFilter

- ea: `0x180014e84`
- end: `0x1800151a7`
- name: `DiscpEstablishTunnelFilter`
- size: `803`
- prototype: `__int64 __fastcall(__int64, int *, int *, int, int, __int16, char, GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800151b0`

## callees

- `0x180001410`
- `0x180001cfe`
- `0x180014960`
- `0x180014b74`
- `0x180014e84`

## import_xrefs

- `ISCSIUM!DiscpFreeMemory` at `0x18001516c`
- `ISCSIUM!DiscpFreeMemory` at `0x180015175`
- `ISCSIUM!DiscpFreeMemory` at `0x18001516c`
- `ISCSIUM!DiscpFreeMemory` at `0x180015175`
- `RPCRT4!UuidCreate` at `0x180014f89`
- `RPCRT4!UuidCreate` at `0x180015007`
- `RPCRT4!UuidCreate` at `0x180014f89`
- `RPCRT4!UuidCreate` at `0x180015007`
- `WS2_32!__imp_htonl` at `0x180015066`
- `WS2_32!__imp_htonl` at `0x180015091`
- `WS2_32!__imp_htonl` at `0x180015066`
- `WS2_32!__imp_htonl` at `0x180015091`
- `fwpuclnt!FwpmIPsecTunnelAdd0` at `0x180015161`
- `fwpuclnt!FwpmIPsecTunnelAdd0` at `0x180015161`

## pseudocode

```c
__int64 __fastcall DiscpEstablishTunnelFilter(
        __int64 a1,
        int *a2,
        int *a3,
        int a4,
        int a5,
        __int16 a6,
        char a7,
        GUID *a8)
{
  int v12; // r12d
  unsigned int v13; // ebx
  IPSEC_KEYING_POLICY0 *v14; // r14
  int v15; // ecx
  __int64 v16; // rdi
  u_long v17; // ecx
  u_long v18; // eax
  u_long v19; // ecx
  __int128 v20; // xmm0
  __int128 v21; // xmm0
  STRSAFE_LPWSTR v23; // [rsp+40h] [rbp-C0h] BYREF
  IPSEC_KEYING_POLICY0 *v24; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v26[4]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v27; // [rsp+A0h] [rbp-60h] BYREF
  char v28; // [rsp+B0h] [rbp-50h]
  __int128 v29; // [rsp+B8h] [rbp-48h] BYREF
  char v30; // [rsp+C8h] [rbp-38h]
  FWPM_PROVIDER_CONTEXT0 Uuid; // [rsp+D0h] [rbp-30h] BYREF
  FWPM_PROVIDER_CONTEXT0 v32; // [rsp+130h] [rbp+30h] BYREF
  FWPM_FILTER_CONDITION0 filterConditions; // [rsp+190h] [rbp+90h] BYREF
  GUID v34; // [rsp+1B8h] [rbp+B8h]
  int v35; // [rsp+1C8h] [rbp+C8h]
  int v36; // [rsp+1D0h] [rbp+D0h]
  __int128 *v37; // [rsp+1D8h] [rbp+D8h]
  GUID v38; // [rsp+1E0h] [rbp+E0h]
  int v39; // [rsp+1F0h] [rbp+F0h]
  int v40; // [rsp+1F8h] [rbp+F8h]
  __int128 *v41; // [rsp+200h] [rbp+100h]
  GUID v42; // [rsp+208h] [rbp+108h]
  int v43; // [rsp+218h] [rbp+118h]
  int v44; // [rsp+220h] [rbp+120h]
  __int16 v45; // [rsp+228h] [rbp+128h]

  v24 = 0;
  memset_0(&Uuid, 0, sizeof(Uuid));
  memset_0(&v32, 0, sizeof(v32));
  v12 = *a3;
  v25 = 0;
  v28 = 0;
  v30 = 0;
  v23 = 0;
  v27 = 0;
  v29 = 0;
  memset(v26, 0, 60);
  v13 = DiscpBuildTunnelPolicyTemplate(a1, a2, (a7 & 0x10) != 0 ? 6 : 0, &v23, &v24);
  if ( !v13 )
  {
    memset_0(&Uuid, 0, sizeof(Uuid));
    v14 = v24;
    Uuid.displayData.name = v23;
    Uuid.displayData.description = v23;
    Uuid.type = FWPM_IPSEC_IKE_QM_TUNNEL_CONTEXT;
    Uuid.keyingPolicy = v24;
    v13 = UuidCreate(&Uuid.providerContextKey);
    if ( !v13 )
    {
      *a8 = Uuid.providerContextKey;
      v13 = DiscpBuildMMPolicy(v15, a4, a5, (int)a3, (__int64)&v25, v26);
      if ( !v13 )
      {
        memset_0(&v32, 0, sizeof(v32));
        v16 = v25;
        v32.keyingPolicy = (IPSEC_KEYING_POLICY0 *)DiscpMMPolicyTemplate;
        v32.displayData.name = (wchar_t *)v25;
        v32.displayData.description = (wchar_t *)v25;
        v32.type = FWPM_IPSEC_IKE_MM_CONTEXT;
        v13 = UuidCreate(&v32.providerContextKey);
        if ( !v13 )
        {
          filterConditions.matchType = FWP_MATCH_EQUAL;
          filterConditions.conditionValue.type = FWP_UINT8;
          filterConditions.conditionValue.uint8 = 6;
          v35 = 0;
          filterConditions.fieldKey = FWPM_CONDITION_IP_PROTOCOL;
          if ( v12 )
          {
            v20 = *(_OWORD *)(a1 + 12);
            v37 = &v27;
            v27 = v20;
            v28 = 0;
            v21 = *(_OWORD *)(a3 + 3);
            v36 = 257;
            v34 = FWPM_CONDITION_IP_LOCAL_ADDRESS;
            v30 = 0;
            v39 = 0;
            v29 = v21;
            v40 = 257;
            v38 = FWPM_CONDITION_IP_REMOTE_ADDRESS;
            v41 = &v29;
          }
          else
          {
            v17 = *(_DWORD *)(a1 + 4);
            v36 = 3;
            v34 = FWPM_CONDITION_IP_LOCAL_ADDRESS;
            v18 = htonl(v17);
            v19 = a3[1];
            LODWORD(v37) = v18;
            v38 = FWPM_CONDITION_IP_REMOTE_ADDRESS;
            v39 = 0;
            v40 = 3;
            LODWORD(v41) = htonl(v19);
          }
          v45 = a6;
          v42 = FWPM_CONDITION_IP_REMOTE_PORT;
          v43 = 0;
          v44 = 2;
          v13 = FwpmIPsecTunnelAdd0(DiscpEngineHandle, 1u, &v32, &Uuid, 4u, &filterConditions, 0);
        }
        DiscpFreeMemory(v16);
      }
    }
    DiscpFreeMemory(v14);
  }
  return v13;
}

```

## disassembly

```asm
0x180014e84  mov     [rsp-8+arg_18], rbx
0x180014e89  push    rbp
0x180014e8a  push    rsi
0x180014e8b  push    rdi
0x180014e8c  push    r12
0x180014e8e  push    r13
0x180014e90  push    r14
0x180014e92  push    r15
0x180014e94  lea     rbp, [rsp-140h]
0x180014e9c  sub     rsp, 240h
0x180014ea3  mov     rax, cs:__security_cookie
0x180014eaa  xor     rax, rsp
0x180014ead  mov     [rbp+170h+var_40], rax
0x180014eb4  mov     r13, [rbp+170h+arg_38]
0x180014ebb  xor     r14d, r14d
0x180014ebe  mov     rsi, r8
0x180014ec1  mov     [rsp+270h+var_228], r14
0x180014ec6  mov     rbx, rdx
0x180014ec9  mov     r15, rcx
0x180014ecc  xor     edx, edx; Val
0x180014ece  lea     rcx, [rbp+170h+Uuid]; void *
0x180014ed2  lea     r12d, [r14+58h]
0x180014ed6  mov     edi, r9d
0x180014ed9  mov     r8d, r12d; Size
0x180014edc  call    memset_0
0x180014ee1  mov     r8d, r12d; Size
0x180014ee4  lea     rcx, [rbp+170h+var_140]; void *
0x180014ee8  xor     edx, edx; Val
0x180014eea  call    memset_0
0x180014eef  mov     r12d, [rsi]
0x180014ef2  lea     r9, [rsp+270h+var_230]
0x180014ef7  xor     eax, eax
0x180014ef9  mov     [rsp+270h+var_220], r14
0x180014efe  xorps   xmm0, xmm0
0x180014f01  mov     [rbp+170h+var_1C0], al
0x180014f04  mov     [rbp+170h+var_1A8], al
0x180014f07  xorps   xmm1, xmm1
0x180014f0a  mov     al, [rbp+170h+arg_30]
0x180014f10  mov     rdx, rbx
0x180014f13  and     al, 10h
0x180014f15  mov     [rsp+270h+var_230], r14
0x180014f1a  neg     al
0x180014f1c  mov     rcx, r15
0x180014f1f  lea     rax, [rsp+270h+var_228]
0x180014f24  sbb     r8d, r8d
0x180014f27  mov     qword ptr [rsp+270h+numFilterConditions], rax
0x180014f2c  movups  xmmword ptr [rbp+170h+var_1F0], xmm0
0x180014f30  and     r8d, 6
0x180014f34  movups  [rbp+170h+var_1D0], xmm0
0x180014f38  movups  [rbp+170h+var_1B8], xmm1
0x180014f3c  movups  [rsp+270h+var_210], xmm0
0x180014f41  movups  [rsp+270h+var_200], xmm0
0x180014f46  movups  xmmword ptr [rbp+170h+var_1F0+0Ch], xmm0
0x180014f4a  call    DiscpBuildTunnelPolicyTemplate
0x180014f4f  mov     ebx, eax
0x180014f51  test    eax, eax
0x180014f53  jnz     loc_18001517B
0x180014f59  xor     edx, edx; Val
0x180014f5b  lea     r8d, [r14+58h]; Size
0x180014f5f  lea     rcx, [rbp+170h+Uuid]; void *
0x180014f63  call    memset_0
0x180014f68  mov     rax, [rsp+270h+var_230]
0x180014f6d  lea     rcx, [rbp+170h+Uuid]; Uuid
0x180014f71  mov     r14, [rsp+270h+var_228]
0x180014f76  mov     [rbp+170h+var_190], rax
0x180014f7a  mov     [rbp+170h+var_188], rax
0x180014f7e  mov     [rbp+170h+var_160], 2
0x180014f85  mov     [rbp+170h+var_158], r14
0x180014f89  call    cs:__imp_UuidCreate
0x180014f8f  mov     ebx, eax
0x180014f91  test    eax, eax
0x180014f93  jnz     loc_180015172
0x180014f99  movaps  xmm0, xmmword ptr [rbp+170h+Uuid.Data1]
0x180014f9d  lea     rax, [rsp+270h+var_210]
0x180014fa2  mov     r8, qword ptr [rbp+170h+arg_20]; int
0x180014fa9  mov     r9, rsi; int
0x180014fac  mov     [rsp+270h+filterConditions], rax; void *
0x180014fb1  mov     edx, edi; int
0x180014fb3  lea     rax, [rsp+270h+var_220]
0x180014fb8  mov     qword ptr [rsp+270h+numFilterConditions], rax; __int64
0x180014fbd  movdqu  xmmword ptr [r13+0], xmm0
0x180014fc3  call    DiscpBuildMMPolicy
0x180014fc8  xor     r13d, r13d
0x180014fcb  mov     ebx, eax
0x180014fcd  test    eax, eax
0x180014fcf  jnz     loc_180015172
0x180014fd5  xor     edx, edx; Val
0x180014fd7  lea     r8d, [rax+58h]; Size
0x180014fdb  lea     rcx, [rbp+170h+var_140]; void *
0x180014fdf  call    memset_0
0x180014fe4  mov     rax, cs:DiscpMMPolicyTemplate
0x180014feb  lea     rcx, [rbp+170h+var_140]; Uuid
0x180014fef  mov     rdi, [rsp+270h+var_220]
0x180014ff4  mov     [rbp+170h+var_F8], rax
0x180014ff8  mov     [rbp+170h+var_130], rdi
0x180014ffc  mov     [rbp+170h+var_128], rdi
0x180015000  mov     [rbp+170h+var_100], 5
0x180015007  call    cs:__imp_UuidCreate
0x18001500d  mov     ebx, eax
0x18001500f  test    eax, eax
0x180015011  jnz     loc_180015169
0x180015017  mov     [rbp+170h+var_E0.matchType], r13d
0x18001501e  mov     [rbp+170h+var_E0.conditionValue.type], 1
0x180015028  mov     byte ptr [rbp+170h+var_E0.conditionValue.8], 6
0x18001502f  mov     [rbp+170h+var_A8], r13d
0x180015036  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_PROTOCOL.Data1
0x18001503d  movdqu  xmmword ptr [rbp+170h+var_E0.fieldKey.Data1], xmm0
0x180015045  test    r12d, r12d
0x180015048  jnz     short loc_18001509F
0x18001504a  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_ADDRESS.Data1
0x180015051  mov     ecx, [r15+4]; hostlong
0x180015055  lea     ebx, [rax+3]
0x180015058  mov     [rbp+170h+var_A0], ebx
0x18001505e  movdqu  [rbp+170h+var_B8], xmm0
0x180015066  call    cs:__imp_htonl
0x18001506c  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_REMOTE_ADDRESS.Data1
0x180015073  mov     ecx, [rsi+4]; hostlong
0x180015076  mov     dword ptr [rbp+170h+var_98], eax
0x18001507c  movdqu  [rbp+170h+var_90], xmm0
0x180015084  mov     [rbp+170h+var_80], r13d
0x18001508b  mov     [rbp+170h+var_78], ebx
0x180015091  call    cs:__imp_htonl
0x180015097  mov     dword ptr [rbp+170h+var_70], eax
0x18001509d  jmp     short loc_180015106
0x18001509f  movups  xmm0, xmmword ptr [r15+0Ch]
0x1800150a4  lea     rax, [rbp+170h+var_1D0]
0x1800150a8  mov     ecx, 101h
0x1800150ad  movups  xmm1, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_ADDRESS.Data1
0x1800150b4  mov     [rbp+170h+var_98], rax
0x1800150bb  lea     rax, [rbp+170h+var_1B8]
0x1800150bf  movdqu  [rbp+170h+var_1D0], xmm0
0x1800150c4  mov     [rbp+170h+var_1C0], r13b
0x1800150c8  movups  xmm0, xmmword ptr [rsi+0Ch]
0x1800150cc  mov     [rbp+170h+var_A0], ecx
0x1800150d2  movdqu  [rbp+170h+var_B8], xmm1
0x1800150da  mov     [rbp+170h+var_1A8], r13b
0x1800150de  movups  xmm1, xmmword ptr cs:FWPM_CONDITION_IP_REMOTE_ADDRESS.Data1
0x1800150e5  mov     [rbp+170h+var_80], r13d
0x1800150ec  movdqu  [rbp+170h+var_1B8], xmm0
0x1800150f1  mov     [rbp+170h+var_78], ecx
0x1800150f7  movdqu  [rbp+170h+var_90], xmm1
0x1800150ff  mov     [rbp+170h+var_70], rax
0x180015106  movzx   eax, [rbp+170h+arg_28]
0x18001510d  lea     r9, [rbp+170h+Uuid]; tunnelPolicy
0x180015111  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data1
0x180015118  mov     rcx, cs:DiscpEngineHandle; engineHandle
0x18001511f  lea     r8, [rbp+170h+var_140]; mainModePolicy
0x180015123  mov     [rbp+170h+var_48], ax
0x18001512a  mov     edx, 1; flags
0x18001512f  lea     rax, [rbp+170h+var_E0]
0x180015136  mov     [rsp+270h+sd], r13; sd
0x18001513b  mov     [rsp+270h+filterConditions], rax; filterConditions
0x180015140  mov     [rsp+270h+numFilterConditions], 4; numFilterConditions
0x180015148  movdqu  [rbp+170h+var_68], xmm0
0x180015150  mov     [rbp+170h+var_58], r13d
0x180015157  mov     [rbp+170h+var_50], 2
0x180015161  call    cs:__imp_FwpmIPsecTunnelAdd0
0x180015167  mov     ebx, eax
0x180015169  mov     rcx, rdi
0x18001516c  call    cs:__imp_DiscpFreeMemory
0x180015172  mov     rcx, r14
0x180015175  call    cs:__imp_DiscpFreeMemory
0x18001517b  mov     eax, ebx
0x18001517d  mov     rcx, [rbp+170h+var_40]
0x180015184  xor     rcx, rsp; StackCookie
0x180015187  call    __security_check_cookie
0x18001518c  mov     rbx, [rsp+270h+arg_18]
0x180015194  add     rsp, 240h
0x18001519b  pop     r15
0x18001519d  pop     r14
0x18001519f  pop     r13
0x1800151a1  pop     r12
0x1800151a3  pop     rdi
0x1800151a4  pop     rsi
0x1800151a5  pop     rbp
0x1800151a6  retn
```
