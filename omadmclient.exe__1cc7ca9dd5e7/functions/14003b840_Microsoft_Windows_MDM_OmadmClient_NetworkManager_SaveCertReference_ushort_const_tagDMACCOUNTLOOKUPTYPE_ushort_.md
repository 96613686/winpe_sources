# Microsoft::Windows::MDM::OmadmClient::NetworkManager::SaveCertReference(ushort const *,tagDMACCOUNTLOOKUPTYPE,ushort const *)

- ea: `0x14003b840`
- end: `0x14003b9dd`
- name: `?SaveCertReference@NetworkManager@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@0@Z`
- size: `413`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14003a070`

## callees

- `0x140003450`
- `0x140003eb4`
- `0x14000b0f4`
- `0x14000e610`
- `0x140013404`
- `0x14003b840`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003b995`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003b995`
- `DMCmnUtils!CopyString` at `0x14003b8e6`
- `DMCmnUtils!CopyString` at `0x14003b8e6`
- `omadmapi!__imp_OmaDmFreeAcctInfo` at `0x14003b9a6`
- `omadmapi!__imp_OmaDmFreeAcctInfo` at `0x14003b9a6`
- `omadmapi!__imp_OmaDmSetValueInStruct` at `0x14003b93b`
- `omadmapi!__imp_OmaDmSetValueInStruct` at `0x14003b93b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::NetworkManager::SaveCertReference(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        const unsigned __int16 *a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  HLOCAL v10; // rax
  int v11; // eax
  int v13; // [rsp+20h] [rbp-E0h]
  HLOCAL v14; // [rsp+20h] [rbp-E0h]
  int v15; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v17[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+58h] [rbp-A8h]
  int *v19; // [rsp+60h] [rbp-A0h]
  int *v20; // [rsp+68h] [rbp-98h]
  char v21; // [rsp+70h] [rbp-90h]
  int v22; // [rsp+80h] [rbp-80h] BYREF
  char v23[508]; // [rsp+84h] [rbp-7Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  memset_0(v23, 0, sizeof(v23));
  v22 = 512;
  v15 = 0;
  v17[0] = 0;
  v17[1] = "SaveCertReference";
  v17[2] = COmaDmLogger::GetLogger();
  v18 = 2;
  v19 = &v15;
  v20 = &v22;
  v21 = 1;
  hMem = 0;
  v8 = CopyString(a4, 0xFFFFFFFF, (unsigned __int16 **)&hMem);
  v9 = v8;
  v15 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x758,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\networkmanager.cpp",
      (const char *)(unsigned int)v8,
      v13);
    goto LABEL_8;
  }
  v10 = hMem;
  hMem = 0;
  v14 = v10;
  v11 = OmaDmSetValueInStruct(24, &v22, 0xFFFFFFFFLL);
  v9 = v11;
  v15 = v11;
  if ( v11 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, int *, HLOCAL))(**(_QWORD **)(a1 + 104) + 48LL))(
            *(_QWORD *)(a1 + 104),
            a2,
            a3,
            &v22,
            v14);
    v9 = v11;
    v15 = v11;
    if ( v11 >= 0 )
      goto LABEL_8;
    LODWORD(v17[0]) = 18015;
  }
  else
  {
    LODWORD(v17[0]) = 18016;
  }
  HIDWORD(v17[0]) = v11;
LABEL_8:
  if ( hMem )
    LocalFree(hMem);
  OmaDmFreeAcctInfo(&v22);
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v17);
  return v9;
}

```

## disassembly

```asm
0x14003b840  push    rbp
0x14003b842  push    rbx
0x14003b843  push    rsi
0x14003b844  push    rdi
0x14003b845  push    r14
0x14003b847  lea     rbp, [rsp-190h]
0x14003b84f  sub     rsp, 290h
0x14003b856  mov     rax, cs:__security_cookie
0x14003b85d  xor     rax, rsp
0x14003b860  mov     [rbp+1B0h+var_30], rax
0x14003b867  mov     rbx, r9
0x14003b86a  mov     r14d, r8d
0x14003b86d  mov     rsi, rdx
0x14003b870  mov     rdi, rcx
0x14003b873  xor     edx, edx; Val
0x14003b875  mov     r8d, 1FCh; Size
0x14003b87b  lea     rcx, [rbp+1B0h+var_22C]; void *
0x14003b87f  call    memset_0
0x14003b884  mov     [rbp+1B0h+var_230], 200h
0x14003b88b  mov     [rsp+2B0h+var_280], 0
0x14003b893  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14003b898  mov     [rsp+2B0h+var_270], 0
0x14003b8a1  lea     rcx, aSavecertrefere; "SaveCertReference"
0x14003b8a8  mov     [rsp+2B0h+var_268], rcx
0x14003b8ad  mov     [rsp+2B0h+var_260], rax
0x14003b8b2  mov     [rsp+2B0h+var_258], 2
0x14003b8ba  lea     rax, [rsp+2B0h+var_280]
0x14003b8bf  mov     [rsp+2B0h+var_250], rax
0x14003b8c4  lea     rax, [rbp+1B0h+var_230]
0x14003b8c8  mov     [rsp+2B0h+var_248], rax
0x14003b8cd  mov     [rsp+2B0h+var_240], 1
0x14003b8d2  mov     [rsp+2B0h+hMem], 0
0x14003b8db  lea     r8, [rsp+2B0h+hMem]
0x14003b8e0  or      edx, 0FFFFFFFFh
0x14003b8e3  mov     rcx, rbx
0x14003b8e6  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x14003b8ed  nop     dword ptr [rax+rax+00h]
0x14003b8f2  mov     ebx, eax
0x14003b8f4  mov     [rsp+2B0h+var_280], eax
0x14003b8f8  test    eax, eax
0x14003b8fa  jns     short loc_14003B919
0x14003b8fc  mov     rcx, [rbp+1B8h]; this
0x14003b903  mov     r9d, eax; char *
0x14003b906  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14003b90d  mov     edx, 758h; void *
0x14003b912  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003b917  jmp     short loc_14003B98B
0x14003b919  mov     rax, [rsp+2B0h+hMem]
0x14003b91e  mov     [rsp+2B0h+hMem], 0
0x14003b927  mov     [rsp+2B0h+var_290], rax
0x14003b92c  xor     r9d, r9d
0x14003b92f  or      r8d, 0FFFFFFFFh
0x14003b933  lea     rdx, [rbp+1B0h+var_230]
0x14003b937  lea     ecx, [r9+18h]
0x14003b93b  call    cs:__imp_OmaDmSetValueInStruct
0x14003b942  nop     dword ptr [rax+rax+00h]
0x14003b947  mov     ebx, eax
0x14003b949  mov     [rsp+2B0h+var_280], eax
0x14003b94d  test    eax, eax
0x14003b94f  jns     short loc_14003B95B
0x14003b951  mov     dword ptr [rsp+2B0h+var_270], 4660h
0x14003b959  jmp     short loc_14003B987
0x14003b95b  mov     rcx, [rdi+68h]
0x14003b95f  mov     rax, [rcx]
0x14003b962  lea     r9, [rbp+1B0h+var_230]
0x14003b966  mov     r8d, r14d
0x14003b969  mov     rdx, rsi
0x14003b96c  mov     rax, [rax+30h]
0x14003b970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b975  mov     ebx, eax
0x14003b977  mov     [rsp+2B0h+var_280], eax
0x14003b97b  test    eax, eax
0x14003b97d  jns     short loc_14003B98B
0x14003b97f  mov     dword ptr [rsp+2B0h+var_270], 465Fh
0x14003b987  mov     dword ptr [rsp+2B0h+var_270+4], eax
0x14003b98b  mov     rcx, [rsp+2B0h+hMem]; hMem
0x14003b990  test    rcx, rcx
0x14003b993  jz      short loc_14003B9A2
0x14003b995  call    cs:__imp_LocalFree
0x14003b99c  nop     dword ptr [rax+rax+00h]
0x14003b9a1  nop
0x14003b9a2  lea     rcx, [rbp+1B0h+var_230]
0x14003b9a6  call    cs:__imp_OmaDmFreeAcctInfo
0x14003b9ad  nop     dword ptr [rax+rax+00h]
0x14003b9b2  nop
0x14003b9b3  lea     rcx, [rsp+2B0h+var_270]; this
0x14003b9b8  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14003b9bd  mov     eax, ebx
0x14003b9bf  mov     rcx, [rbp+1B0h+var_30]
0x14003b9c6  xor     rcx, rsp; StackCookie
0x14003b9c9  call    __security_check_cookie
0x14003b9ce  add     rsp, 290h
0x14003b9d5  pop     r14
0x14003b9d7  pop     rdi
0x14003b9d8  pop     rsi
0x14003b9d9  pop     rbx
0x14003b9da  pop     rbp
0x14003b9db  retn
```
