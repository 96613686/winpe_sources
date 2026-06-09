# cdp::ActivityStoreManagementlet::GetActivityPermissionScopePolicy(CDPActivityType,char const *,bool &,CDPActivityPolicySource *,ushort,uchar &)

- ea: `0x1800da710`
- end: `0x1800da9b9`
- name: `?GetActivityPermissionScopePolicy@ActivityStoreManagementlet@cdp@@UEAAJW4CDPActivityType@@PEBDAEA_NPEAW4CDPActivityPolicySource@@GAEAE@Z`
- size: `681`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18001ce80`
- `0x1800da710`
- `0x18012d5cc`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da7f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da83c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da8f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da958`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da7f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da83c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da8f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800da958`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall cdp::ActivityStoreManagementlet::GetActivityPermissionScopePolicy(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        bool *a4,
        _WORD *a5,
        unsigned __int16 a6,
        _BYTE *a7)
{
  _WORD *v11; // rbx
  _BYTE *v12; // rdi
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rax
  void *v16; // rcx
  int v17; // r14d
  void *v18; // rcx
  _QWORD *v19; // rcx
  _QWORD *v21; // rcx
  unsigned int v22; // ecx
  __int64 v23; // rax
  void *v24; // rcx
  char *v25; // r8
  char *v26; // rdx
  _QWORD *v27; // rcx
  void *v28; // rcx
  unsigned int v29; // [rsp+40h] [rbp-41h] BYREF
  int v30; // [rsp+44h] [rbp-3Dh] BYREF
  int v31; // [rsp+48h] [rbp-39h] BYREF
  _QWORD *v32; // [rsp+50h] [rbp-31h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-29h] BYREF
  LPVOID *p_pv; // [rsp+60h] [rbp-21h]
  void *v35; // [rsp+68h] [rbp-19h] BYREF
  char v36; // [rsp+70h] [rbp-11h]

  v11 = a5;
  if ( !a5 )
  {
    v29 = -2147467261;
    v31 = 1238;
    Log<long &,char const (&)[36],int>(
      a1,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
      (unsigned int)&v29,
      (unsigned int)".\\activitystorelet.cpp",
      (__int64)&v31);
    return v29;
  }
  *a4 = 0;
  v12 = a7;
  *a7 = 0;
  v32 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
  v13 = *(_QWORD *)(a1 + 296);
  v32 = 0;
  if ( !v13 )
  {
    v14 = -2147024809;
LABEL_14:
    v29 = v14;
    v31 = 1244;
    Log<long &,char const (&)[36],int>(
      v13,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
      (unsigned int)&v29,
      (unsigned int)".\\activitystorelet.cpp",
      (__int64)&v31);
    v21 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v21 + 16LL))(v21);
    }
    return v29;
  }
  v14 = (*(__int64 (__fastcall **)(__int64, GUID *, _QWORD **))(*(_QWORD *)v13 + 24LL))(
          v13,
          &GUID_cf134f41_b0ed_422f_8ee4_6202a3603e84,
          &v32);
  if ( v14 < 0 )
    goto LABEL_14;
  v30 = 0;
  pv = 0;
  LOBYTE(a5) = 0;
  v15 = *v32;
  p_pv = &pv;
  v35 = 0;
  v36 = 1;
  v17 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, __int64, int *, void **, _WORD **))(v15 + 56))(
          v32,
          a2,
          a3,
          &v30,
          &v35,
          &a5);
  if ( v36 )
  {
    v16 = *p_pv;
    *p_pv = v35;
    if ( v16 )
      CoTaskMemFree(v16);
  }
  if ( v17 < 0 )
  {
    v29 = v17;
    v31 = 1251;
    Log<long &,char const (&)[36],int>(
      (_DWORD)v16,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
      (unsigned int)&v29,
      (unsigned int)".\\activitystorelet.cpp",
      (__int64)&v31);
    v18 = pv;
    pv = 0;
    if ( v18 )
      CoTaskMemFree(v18);
    v19 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
    }
    return v29;
  }
  v22 = (unsigned __int8)a5;
  *v12 = (_BYTE)a5;
  if ( (unsigned __int16)v22 > a6 )
  {
    v29 = -2147221235;
    v31 = 1254;
    Log<long &,char const (&)[36],int>(
      v22,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
      (unsigned int)&v29,
      (unsigned int)".\\activitystorelet.cpp",
      (__int64)&v31);
    v28 = pv;
    pv = 0;
    if ( v28 )
      CoTaskMemFree(v28);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v32);
    return v29;
  }
  *a4 = v30 != 0;
  v23 = v22;
  v24 = pv;
  v25 = (char *)pv + 4 * v23;
  v26 = (char *)pv;
  if ( pv != v25 )
  {
    do
    {
      *v11++ = *(_WORD *)v26;
      v26 += 4;
    }
    while ( v26 != v25 );
  }
  pv = 0;
  if ( v24 )
    CoTaskMemFree(v24);
  v27 = v32;
  if ( v32 )
  {
    v32 = 0;
    (*(void (__fastcall **)(_QWORD *, char *))(*v27 + 16LL))(v27, v26);
  }
  return 0;
}

```

## disassembly

```asm
0x1800da710  push    rbp
0x1800da712  push    rbx
0x1800da713  push    rsi
0x1800da714  push    rdi
0x1800da715  push    r12
0x1800da717  push    r13
0x1800da719  push    r14
0x1800da71b  push    r15
0x1800da71d  lea     rbp, [rsp-7]
0x1800da722  sub     rsp, 88h
0x1800da729  mov     rsi, r9
0x1800da72c  mov     r15, r8
0x1800da72f  mov     r12d, edx
0x1800da732  mov     r14, rcx
0x1800da735  mov     rbx, [rbp+3Fh+arg_20]
0x1800da739  xor     r13d, r13d
0x1800da73c  test    rbx, rbx
0x1800da73f  jz      loc_1800DA96D
0x1800da745  mov     [r9], r13b
0x1800da748  mov     rdi, [rbp+3Fh+arg_30]
0x1800da74c  mov     [rdi], r13b
0x1800da74f  mov     [rbp+3Fh+var_70], r13
0x1800da753  lea     rcx, [rbp+3Fh+var_70]
0x1800da757  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800da75c  mov     rcx, [r14+128h]
0x1800da763  mov     [rbp+3Fh+var_70], r13
0x1800da767  test    rcx, rcx
0x1800da76a  jz      loc_1800DA874
0x1800da770  mov     rax, [rcx]
0x1800da773  lea     r8, [rbp+3Fh+var_70]
0x1800da777  lea     rdx, _GUID_cf134f41_b0ed_422f_8ee4_6202a3603e84
0x1800da77e  mov     rax, [rax+18h]
0x1800da782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da787  nop
0x1800da788  test    eax, eax
0x1800da78a  js      loc_1800DA879
0x1800da790  mov     [rbp+3Fh+var_7C], r13d
0x1800da794  mov     [rbp+3Fh+pv], r13
0x1800da798  mov     byte ptr [rbp+3Fh+arg_20], r13b
0x1800da79c  mov     rcx, [rbp+3Fh+var_70]
0x1800da7a0  mov     rax, [rcx]
0x1800da7a3  lea     rdx, [rbp+3Fh+pv]
0x1800da7a7  mov     [rbp+3Fh+var_60], rdx
0x1800da7ab  mov     [rbp+3Fh+var_58], r13
0x1800da7af  mov     [rbp+3Fh+var_50], 1
0x1800da7b3  lea     rdx, [rbp+3Fh+arg_20]
0x1800da7b7  mov     [rsp+0C0h+var_98], rdx
0x1800da7bc  lea     rdx, [rbp+3Fh+var_58]
0x1800da7c0  mov     [rsp+0C0h+var_A0], rdx
0x1800da7c5  lea     r9, [rbp+3Fh+var_7C]
0x1800da7c9  mov     r8, r15
0x1800da7cc  mov     edx, r12d
0x1800da7cf  mov     rax, [rax+38h]
0x1800da7d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da7d8  mov     r14d, eax
0x1800da7db  cmp     [rbp+3Fh+var_50], r13b
0x1800da7df  jz      short loc_1800DA7FA
0x1800da7e1  mov     r8, [rbp+3Fh+var_60]
0x1800da7e5  mov     rcx, [r8]; pv
0x1800da7e8  mov     rdx, [rbp+3Fh+var_58]
0x1800da7ec  mov     [r8], rdx
0x1800da7ef  test    rcx, rcx
0x1800da7f2  jz      short loc_1800DA7FA
0x1800da7f4  call    cs:__imp_CoTaskMemFree
0x1800da7fa  test    r14d, r14d
0x1800da7fd  jns     loc_1800DA8C0
0x1800da803  mov     [rbp+3Fh+var_80], r14d
0x1800da807  mov     [rbp+3Fh+var_78], 4E3h
0x1800da80e  lea     rax, [rbp+3Fh+var_78]
0x1800da812  mov     [rsp+0C0h+var_A0], rax
0x1800da817  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x1800da81e  lea     r8, [rbp+3Fh+var_80]
0x1800da822  lea     rdx, aHr0x08xFileSLi_93; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800da829  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x1800da82e  nop
0x1800da82f  mov     rcx, [rbp+3Fh+pv]; pv
0x1800da833  mov     [rbp+3Fh+pv], r13
0x1800da837  test    rcx, rcx
0x1800da83a  jz      short loc_1800DA843
0x1800da83c  call    cs:__imp_CoTaskMemFree
0x1800da842  nop
0x1800da843  mov     rcx, [rbp+3Fh+var_70]
0x1800da847  test    rcx, rcx
0x1800da84a  jz      short loc_1800DA85D
0x1800da84c  mov     [rbp+3Fh+var_70], r13
0x1800da850  mov     rdx, [rcx]
0x1800da853  mov     rax, [rdx+10h]
0x1800da857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da85c  nop
0x1800da85d  mov     eax, [rbp+3Fh+var_80]
0x1800da860  add     rsp, 88h
0x1800da867  pop     r15
0x1800da869  pop     r14
0x1800da86b  pop     r13
0x1800da86d  pop     r12
0x1800da86f  pop     rdi
0x1800da870  pop     rsi
0x1800da871  pop     rbx
0x1800da872  pop     rbp
0x1800da873  retn
0x1800da874  mov     eax, 80070057h
0x1800da879  mov     [rbp+3Fh+var_80], eax
0x1800da87c  mov     [rbp+3Fh+var_78], 4DCh
0x1800da883  lea     rax, [rbp+3Fh+var_78]
0x1800da887  mov     [rsp+0C0h+var_A0], rax
0x1800da88c  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x1800da893  lea     r8, [rbp+3Fh+var_80]
0x1800da897  lea     rdx, aHr0x08xFileSLi_93; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800da89e  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x1800da8a3  nop
0x1800da8a4  mov     rcx, [rbp+3Fh+var_70]
0x1800da8a8  test    rcx, rcx
0x1800da8ab  jz      short loc_1800DA8BE
0x1800da8ad  mov     [rbp+3Fh+var_70], r13
0x1800da8b1  mov     rdx, [rcx]
0x1800da8b4  mov     rax, [rdx+10h]
0x1800da8b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da8bd  nop
0x1800da8be  jmp     short loc_1800DA85D
0x1800da8c0  movzx   ecx, byte ptr [rbp+3Fh+arg_20]
0x1800da8c4  mov     [rdi], cl
0x1800da8c6  cmp     cx, [rbp+3Fh+arg_28]
0x1800da8ca  ja      short loc_1800DA91C
0x1800da8cc  cmp     [rbp+3Fh+var_7C], r13d
0x1800da8d0  setnz   al
0x1800da8d3  mov     [rsi], al
0x1800da8d5  mov     eax, ecx
0x1800da8d7  mov     rcx, [rbp+3Fh+pv]; pv
0x1800da8db  lea     r8, [rcx+rax*4]
0x1800da8df  mov     rdx, rcx
0x1800da8e2  cmp     rcx, r8
0x1800da8e5  jnz     loc_1800DA9A0
0x1800da8eb  mov     [rbp+3Fh+pv], r13
0x1800da8ef  test    rcx, rcx
0x1800da8f2  jz      short loc_1800DA8FB
0x1800da8f4  call    cs:__imp_CoTaskMemFree
0x1800da8fa  nop
0x1800da8fb  mov     rcx, [rbp+3Fh+var_70]
0x1800da8ff  test    rcx, rcx
0x1800da902  jz      short loc_1800DA915
0x1800da904  mov     [rbp+3Fh+var_70], r13
0x1800da908  mov     rax, [rcx]
0x1800da90b  mov     rax, [rax+10h]
0x1800da90f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da914  nop
0x1800da915  xor     eax, eax
0x1800da917  jmp     loc_1800DA860
0x1800da91c  mov     [rbp+3Fh+var_80], 8004010Dh
0x1800da923  mov     [rbp+3Fh+var_78], 4E6h
0x1800da92a  lea     rax, [rbp+3Fh+var_78]
0x1800da92e  mov     [rsp+0C0h+var_A0], rax
0x1800da933  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x1800da93a  lea     r8, [rbp+3Fh+var_80]
0x1800da93e  lea     rdx, aHr0x08xFileSLi_93; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800da945  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x1800da94a  nop
0x1800da94b  mov     rcx, [rbp+3Fh+pv]; pv
0x1800da94f  mov     [rbp+3Fh+pv], r13
0x1800da953  test    rcx, rcx
0x1800da956  jz      short loc_1800DA95F
0x1800da958  call    cs:__imp_CoTaskMemFree
0x1800da95e  nop
0x1800da95f  lea     rcx, [rbp+3Fh+var_70]
0x1800da963  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800da968  jmp     loc_1800DA85D
0x1800da96d  mov     [rbp+3Fh+var_80], 80004003h
0x1800da974  mov     [rbp+3Fh+var_78], 4D6h
0x1800da97b  lea     rax, [rbp+3Fh+var_78]
0x1800da97f  mov     [rsp+0C0h+var_A0], rax
0x1800da984  lea     r9, aActivitystorel; ".\\activitystorelet.cpp"
0x1800da98b  lea     r8, [rbp+3Fh+var_80]
0x1800da98f  lea     rdx, aHr0x08xFileSLi_93; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800da996  call    ??$Log@AEAJAEAY0CE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CE@$$CBD$$QEAH@Z; Log<long &,char const (&)[36],int>(CDPLogLevel,char const *,long &,char const (&)[36],int &&)
0x1800da99b  jmp     loc_1800DA85D
0x1800da9a0  movzx   eax, word ptr [rdx]
0x1800da9a3  mov     [rbx], ax
0x1800da9a6  lea     rbx, [rbx+2]
0x1800da9aa  add     rdx, 4
0x1800da9ae  cmp     rdx, r8
0x1800da9b1  jnz     short loc_1800DA9A0
0x1800da9b3  jmp     loc_1800DA8EB
```
