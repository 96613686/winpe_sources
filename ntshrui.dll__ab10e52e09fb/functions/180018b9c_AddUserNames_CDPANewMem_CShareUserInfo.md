# AddUserNames(CDPANewMem<CShareUserInfo> &)

- ea: `0x180018b9c`
- end: `0x180018f44`
- name: `?AddUserNames@@YAJAEAV?$CDPANewMem@VCShareUserInfo@@@@@Z`
- size: `936`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180072570`

## callees

- `0x1800120e0`
- `0x180018b9c`
- `0x180018f4c`
- `0x180018fdc`
- `0x180019454`
- `0x180019550`
- `0x180022a70`
- `0x1800259bc`
- `0x18003c01c`
- `0x180078010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018d94`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018d94`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018bd5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018c06`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018bd5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018c06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018cf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018d13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018d54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018e3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018e60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018e8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018ecb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018ed5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018ee0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018cf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018d13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018d54`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018e3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018e60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018e8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018ecb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018ed5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018ee0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180018cb4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180018cb4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180018d86`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180018d86`
- `PROPSYS!PropVariantToUInt32` at `0x180018ca1`
- `PROPSYS!PropVariantToUInt32` at `0x180018ca1`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall AddUserNames(__int64 a1)
{
  HRESULT String; // edi
  unsigned int i; // esi
  HRESULT v4; // ebx
  void *v5; // rcx
  __int64 v6; // rdx
  bool v7; // bl
  DWORD LengthSid; // eax
  CShareUserInfo *v9; // rcx
  CShareUserInfo *v10; // rax
  CShareUserInfo *v11; // rbx
  LPVOID v12; // rdi
  LPCWSTR v13; // rdi
  void *v14; // rcx
  LPVOID v15; // rdi
  void *v16; // rcx
  unsigned int v17; // edx
  CShareUserInfo *v18; // rcx
  LPVOID pv; // [rsp+30h] [rbp-40h] BYREF
  LPCWSTR StringSid; // [rsp+38h] [rbp-38h] BYREF
  LPVOID v22; // [rsp+40h] [rbp-30h] BYREF
  LPVOID v23; // [rsp+48h] [rbp-28h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-20h] BYREF
  PROPVARIANT propvarIn[2]; // [rsp+58h] [rbp-18h] BYREF
  __int64 v26; // [rsp+68h] [rbp-8h]
  unsigned int v27; // [rsp+B8h] [rbp+48h] BYREF
  CShareUserInfo *pulRet; // [rsp+C0h] [rbp+50h] BYREF
  __int64 v29; // [rsp+C8h] [rbp+58h] BYREF

  ppv = 0;
  String = CoCreateInstance(&CLSID_LocalUserAccounts, 0, 1u, &GUID_3c708557_c99d_4fa3_9231_56518418b4e4, &ppv);
  if ( String >= 0 )
  {
    v23 = 0;
    CoCreateInstance(
      &GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e,
      0,
      1u,
      &GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1,
      &v23);
    v27 = 0;
    String = (*(__int64 (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)ppv + 32LL))(ppv, &v27);
    for ( i = 0; String >= 0; ++i )
    {
      if ( i >= v27 )
        break;
      v29 = 0;
      String = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)ppv + 40LL))(ppv, i, &v29);
      if ( String >= 0 )
      {
        LODWORD(pulRet) = 0;
        *(_OWORD *)propvarIn = 0;
        v26 = 0;
        if ( (*(int (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v29 + 40LL))(
               v29,
               PKEY_SAM_ResidualID,
               propvarIn) < 0
          || (!LOWORD(propvarIn[0]) ? (v4 = -2147023728) : (v4 = PropVariantToUInt32(propvarIn, (ULONG *)&pulRet)),
              (PropVariantClear(propvarIn), v4 < 0) || (_DWORD)pulRet != 501) )
        {
          if ( !(unsigned __int8)s_DontShowInLogonUI(v29) && !(unsigned __int8)s_UserAccountDisabled(v29) )
          {
            v22 = 0;
            CoTaskMemFree(0);
            IPropertyStore_GetString(v29, PKEY_SAM_FullName, &v22);
            pv = 0;
            CoTaskMemFree(0);
            String = IPropertyStore_GetString(v29, &PKEY_SAM_Name, &pv);
            v5 = pv;
            if ( String >= 0 && pv && *(_WORD *)pv )
            {
              StringSid = 0;
              CoTaskMemFree(0);
              String = IPropertyStore_GetSecurityIDString(v29, v6, &StringSid);
              if ( String >= 0 )
              {
                if ( !v23 )
                  goto LABEL_21;
                v7 = 0;
                pulRet = 0;
                if ( ConvertStringSidToSidW(StringSid, (PSID *)&pulRet) )
                {
                  LengthSid = GetLengthSid(pulRet);
                  v7 = (*(int (__fastcall **)(LPVOID, CShareUserInfo *, _QWORD, _QWORD))(*(_QWORD *)v23 + 56LL))(
                         v23,
                         pulRet,
                         LengthSid,
                         0) >= 0;
                }
                v9 = pulRet;
                pulRet = 0;
                CTContainer_PolicyLocalMem::DestroyMem(v9);
                if ( !v7 )
                {
LABEL_21:
                  v10 = (CShareUserInfo *)operator new(0x68u, (const struct std::nothrow_t *)std::nothrow);
                  v11 = v10;
                  pulRet = v10;
                  if ( v10 )
                  {
                    *(_QWORD *)v10 = 0;
                    *((_QWORD *)v10 + 1) = 0;
                    *((_QWORD *)v10 + 2) = 0;
                    *((_QWORD *)v10 + 3) = 0;
                    *((_QWORD *)v10 + 4) = 0;
                    *((_QWORD *)v10 + 5) = 0;
                    *((_QWORD *)v10 + 6) = 0;
                    *((_QWORD *)v10 + 7) = 0;
                    *((_QWORD *)v10 + 8) = 0;
                    *((_QWORD *)v10 + 9) = 0;
                    *((_QWORD *)v10 + 10) = 0;
                    *((_QWORD *)v10 + 11) = 0;
                    *((_BYTE *)v10 + 96) = 0;
                    v12 = pv;
                    pv = 0;
                    if ( *(_QWORD *)v10 )
                      CoTaskMemFree(*(LPVOID *)v10);
                    *(_QWORD *)v11 = v12;
                    *((_QWORD *)v11 + 2) = -1;
                    *((_QWORD *)v11 + 1) = -1;
                    v13 = StringSid;
                    StringSid = 0;
                    v14 = (void *)*((_QWORD *)v11 + 9);
                    if ( v14 )
                      CoTaskMemFree(v14);
                    *((_QWORD *)v11 + 9) = v13;
                    *((_QWORD *)v11 + 11) = -1;
                    *((_QWORD *)v11 + 10) = -1;
                    v15 = v22;
                    if ( v22 && *(_WORD *)v22 )
                    {
                      v22 = 0;
                      v16 = (void *)*((_QWORD *)v11 + 3);
                      if ( v16 )
                        CoTaskMemFree(v16);
                      *((_QWORD *)v11 + 3) = v15;
                      *((_QWORD *)v11 + 5) = -1;
                      *((_QWORD *)v11 + 4) = -1;
                    }
                    String = CDPA_Base<CShareUserInfo,CTContainer_PolicyNewMem>::AppendPtr(a1, v11);
                    v18 = 0;
                    if ( String < 0 )
                      v18 = v11;
                    if ( v18 )
                      CShareUserInfo::`scalar deleting destructor'(v18, v17);
                  }
                  else
                  {
                    String = -2147024882;
                  }
                }
              }
              CoTaskMemFree((LPVOID)StringSid);
              v5 = pv;
            }
            CoTaskMemFree(v5);
            CoTaskMemFree(v22);
          }
        }
      }
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    if ( v23 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v23 + 16LL))(v23);
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x180018b9c  push    rbp
0x180018b9e  push    rbx
0x180018b9f  push    rsi
0x180018ba0  push    rdi
0x180018ba1  push    r12
0x180018ba3  push    r14
0x180018ba5  push    r15
0x180018ba7  mov     rbp, rsp
0x180018baa  sub     rsp, 70h
0x180018bae  mov     r14, rcx
0x180018bb1  xor     r15d, r15d
0x180018bb4  mov     [rbp+var_20], r15
0x180018bb8  lea     rax, [rbp+var_20]
0x180018bbc  mov     [rsp+70h+ppv], rax; ppv
0x180018bc1  lea     r9, _GUID_3c708557_c99d_4fa3_9231_56518418b4e4; riid
0x180018bc8  xor     edx, edx; pUnkOuter
0x180018bca  lea     r8d, [r15+1]; dwClsContext
0x180018bce  lea     rcx, CLSID_LocalUserAccounts; rclsid
0x180018bd5  call    cs:__imp_CoCreateInstance
0x180018bdb  mov     edi, eax
0x180018bdd  test    eax, eax
0x180018bdf  js      loc_180018F1D
0x180018be5  mov     [rbp+var_28], r15
0x180018be9  lea     rax, [rbp+var_28]
0x180018bed  mov     [rsp+70h+ppv], rax; ppv
0x180018bf2  lea     r9, _GUID_9ec044bc_b01d_4c18_8634_59bd3ff5dcc1; riid
0x180018bf9  xor     edx, edx; pUnkOuter
0x180018bfb  lea     r8d, [r15+1]; dwClsContext
0x180018bff  lea     rcx, _GUID_40afa0b6_3b2f_4654_8c3f_161de85cf80e; rclsid
0x180018c06  call    cs:__imp_CoCreateInstance
0x180018c0c  mov     [rbp+arg_8], r15d
0x180018c10  mov     rcx, [rbp+var_20]
0x180018c14  mov     rax, [rcx]
0x180018c17  lea     rdx, [rbp+arg_8]
0x180018c1b  mov     rax, [rax+20h]
0x180018c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c24  mov     edi, eax
0x180018c26  mov     esi, r15d
0x180018c29  test    eax, eax
0x180018c2b  js      loc_180018F07
0x180018c31  or      r12, 0FFFFFFFFFFFFFFFFh
0x180018c35  cmp     esi, [rbp+arg_8]
0x180018c38  jnb     loc_180018F07
0x180018c3e  mov     [rbp+arg_18], r15
0x180018c42  mov     rcx, [rbp+var_20]
0x180018c46  mov     rax, [rcx]
0x180018c49  lea     r8, [rbp+arg_18]
0x180018c4d  mov     edx, esi
0x180018c4f  mov     rax, [rax+28h]
0x180018c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c58  mov     edi, eax
0x180018c5a  test    eax, eax
0x180018c5c  js      loc_180018EE7
0x180018c62  mov     rcx, [rbp+arg_18]
0x180018c66  mov     dword ptr [rbp+pulRet], r15d
0x180018c6a  xorps   xmm0, xmm0
0x180018c6d  xor     eax, eax
0x180018c6f  movups  xmmword ptr [rbp+propvarIn], xmm0
0x180018c73  mov     [rbp+var_8], rax
0x180018c77  mov     rax, [rcx]
0x180018c7a  lea     r8, [rbp+propvarIn]
0x180018c7e  lea     rdx, PKEY_SAM_ResidualID
0x180018c85  mov     rax, [rax+28h]
0x180018c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c8e  test    eax, eax
0x180018c90  js      short loc_180018CCB
0x180018c92  cmp     r15w, word ptr [rbp+propvarIn]
0x180018c97  jz      short loc_180018CAB
0x180018c99  lea     rdx, [rbp+pulRet]; pulRet
0x180018c9d  lea     rcx, [rbp+propvarIn]; propvarIn
0x180018ca1  call    cs:__imp_PropVariantToUInt32
0x180018ca7  mov     ebx, eax
0x180018ca9  jmp     short loc_180018CB0
0x180018cab  mov     ebx, 80070490h
0x180018cb0  lea     rcx, [rbp+propvarIn]; pvar
0x180018cb4  call    cs:__imp_PropVariantClear
0x180018cba  test    ebx, ebx
0x180018cbc  js      short loc_180018CCB
0x180018cbe  cmp     dword ptr [rbp+pulRet], 1F5h
0x180018cc5  jz      loc_180018EE7
0x180018ccb  mov     rcx, [rbp+arg_18]
0x180018ccf  call    s_DontShowInLogonUI
0x180018cd4  test    al, al
0x180018cd6  jnz     loc_180018EE7
0x180018cdc  mov     rcx, [rbp+arg_18]
0x180018ce0  call    s_UserAccountDisabled
0x180018ce5  test    al, al
0x180018ce7  jnz     loc_180018EE7
0x180018ced  mov     [rbp+var_30], r15
0x180018cf1  xor     ecx, ecx; pv
0x180018cf3  call    cs:__imp_CoTaskMemFree
0x180018cf9  lea     r8, [rbp+var_30]
0x180018cfd  lea     rdx, PKEY_SAM_FullName
0x180018d04  mov     rcx, [rbp+arg_18]
0x180018d08  call    IPropertyStore_GetString
0x180018d0d  mov     [rbp+pv], r15
0x180018d11  xor     ecx, ecx; pv
0x180018d13  call    cs:__imp_CoTaskMemFree
0x180018d19  lea     r8, [rbp+pv]
0x180018d1d  lea     rdx, PKEY_SAM_Name
0x180018d24  mov     rcx, [rbp+arg_18]
0x180018d28  call    IPropertyStore_GetString
0x180018d2d  mov     edi, eax
0x180018d2f  mov     rcx, [rbp+pv]
0x180018d33  test    eax, eax
0x180018d35  js      loc_180018ED5
0x180018d3b  test    rcx, rcx
0x180018d3e  jz      loc_180018ED5
0x180018d44  cmp     [rcx], r15w
0x180018d48  jz      loc_180018ED5
0x180018d4e  mov     [rbp+StringSid], r15
0x180018d52  xor     ecx, ecx; pv
0x180018d54  call    cs:__imp_CoTaskMemFree
0x180018d5a  lea     r8, [rbp+StringSid]
0x180018d5e  mov     rcx, [rbp+arg_18]
0x180018d62  call    IPropertyStore_GetSecurityIDString
0x180018d67  mov     edi, eax
0x180018d69  test    eax, eax
0x180018d6b  js      loc_180018EC7
0x180018d71  cmp     [rbp+var_28], r15
0x180018d75  jz      short loc_180018DD1
0x180018d77  mov     bl, r15b
0x180018d7a  mov     [rbp+pulRet], r15
0x180018d7e  lea     rdx, [rbp+pulRet]; Sid
0x180018d82  mov     rcx, [rbp+StringSid]; StringSid
0x180018d86  call    cs:__imp_ConvertStringSidToSidW
0x180018d8c  test    eax, eax
0x180018d8e  jz      short loc_180018DBB
0x180018d90  mov     rcx, [rbp+pulRet]; pSid
0x180018d94  call    cs:__imp_GetLengthSid
0x180018d9a  mov     edx, eax
0x180018d9c  mov     rcx, [rbp+var_28]
0x180018da0  mov     r8, [rcx]
0x180018da3  mov     rax, [r8+38h]
0x180018da7  xor     r9d, r9d
0x180018daa  mov     r8d, edx
0x180018dad  mov     rdx, [rbp+pulRet]
0x180018db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018db6  test    eax, eax
0x180018db8  setns   bl
0x180018dbb  mov     rcx, [rbp+pulRet]; void *
0x180018dbf  mov     [rbp+pulRet], r15
0x180018dc3  call    ?DestroyMem@CTContainer_PolicyLocalMem@@SAHPEAX@Z; CTContainer_PolicyLocalMem::DestroyMem(void *)
0x180018dc8  nop
0x180018dc9  test    bl, bl
0x180018dcb  jnz     loc_180018EC7
0x180018dd1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018dd8  mov     ecx, 68h ; 'h'; unsigned __int64
0x180018ddd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180018de2  mov     rbx, rax
0x180018de5  mov     [rbp+pulRet], rax
0x180018de9  test    rax, rax
0x180018dec  jz      loc_180018EC2
0x180018df2  mov     [rax], r15
0x180018df5  mov     [rax+8], r15
0x180018df9  mov     [rax+10h], r15
0x180018dfd  mov     [rax+18h], r15
0x180018e01  mov     [rax+20h], r15
0x180018e05  mov     [rax+28h], r15
0x180018e09  mov     [rax+30h], r15
0x180018e0d  mov     [rax+38h], r15
0x180018e11  mov     [rax+40h], r15
0x180018e15  mov     [rax+48h], r15
0x180018e19  mov     [rax+50h], r15
0x180018e1d  mov     [rax+58h], r15
0x180018e21  mov     [rax+60h], r15b
0x180018e25  test    rax, rax
0x180018e28  jz      loc_180018EC2
0x180018e2e  mov     rdi, [rbp+pv]
0x180018e32  mov     [rbp+pv], r15
0x180018e36  mov     rcx, [rax]; pv
0x180018e39  test    rcx, rcx
0x180018e3c  jz      short loc_180018E44
0x180018e3e  call    cs:__imp_CoTaskMemFree
0x180018e44  mov     [rbx], rdi
0x180018e47  mov     [rbx+10h], r12
0x180018e4b  mov     [rbx+8], r12
0x180018e4f  mov     rdi, [rbp+StringSid]
0x180018e53  mov     [rbp+StringSid], r15
0x180018e57  mov     rcx, [rbx+48h]; pv
0x180018e5b  test    rcx, rcx
0x180018e5e  jz      short loc_180018E66
0x180018e60  call    cs:__imp_CoTaskMemFree
0x180018e66  mov     [rbx+48h], rdi
0x180018e6a  mov     [rbx+58h], r12
0x180018e6e  mov     [rbx+50h], r12
0x180018e72  mov     rdi, [rbp+var_30]
0x180018e76  test    rdi, rdi
0x180018e79  jz      short loc_180018EA0
0x180018e7b  cmp     [rdi], r15w
0x180018e7f  jz      short loc_180018EA0
0x180018e81  mov     [rbp+var_30], r15
0x180018e85  mov     rcx, [rbx+18h]; pv
0x180018e89  test    rcx, rcx
0x180018e8c  jz      short loc_180018E94
0x180018e8e  call    cs:__imp_CoTaskMemFree
0x180018e94  mov     [rbx+18h], rdi
0x180018e98  mov     [rbx+28h], r12
0x180018e9c  mov     [rbx+20h], r12
0x180018ea0  mov     rdx, rbx
0x180018ea3  mov     rcx, r14
0x180018ea6  call    ?AppendPtr@?$CDPA_Base@VCShareUserInfo@@VCTContainer_PolicyNewMem@@@@QEAAJPEAVCShareUserInfo@@PEAH@Z; CDPA_Base<CShareUserInfo,CTContainer_PolicyNewMem>::AppendPtr(CShareUserInfo *,int *)
0x180018eab  mov     edi, eax
0x180018ead  mov     rcx, r15
0x180018eb0  test    eax, eax
0x180018eb2  cmovs   rcx, rbx; this
0x180018eb6  test    rcx, rcx
0x180018eb9  jz      short loc_180018EC7
0x180018ebb  call    ??_GCShareUserInfo@@QEAAPEAXI@Z; CShareUserInfo::`scalar deleting destructor'(uint)
0x180018ec0  jmp     short loc_180018EC7
0x180018ec2  mov     edi, 8007000Eh
0x180018ec7  mov     rcx, [rbp+StringSid]; pv
0x180018ecb  call    cs:__imp_CoTaskMemFree
0x180018ed1  mov     rcx, [rbp+pv]; pv
0x180018ed5  call    cs:__imp_CoTaskMemFree
0x180018edb  nop
0x180018edc  mov     rcx, [rbp+var_30]; pv
0x180018ee0  call    cs:__imp_CoTaskMemFree
0x180018ee6  nop
0x180018ee7  mov     rcx, [rbp+arg_18]
0x180018eeb  test    rcx, rcx
0x180018eee  jz      short loc_180018EFD
0x180018ef0  mov     rax, [rcx]
0x180018ef3  mov     rax, [rax+10h]
0x180018ef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018efc  nop
0x180018efd  inc     esi
0x180018eff  test    edi, edi
0x180018f01  jns     loc_180018C35
0x180018f07  mov     rcx, [rbp+var_28]
0x180018f0b  test    rcx, rcx
0x180018f0e  jz      short loc_180018F1D
0x180018f10  mov     rax, [rcx]
0x180018f13  mov     rax, [rax+10h]
0x180018f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f1c  nop
0x180018f1d  mov     rcx, [rbp+var_20]
0x180018f21  test    rcx, rcx
0x180018f24  jz      short loc_180018F33
0x180018f26  mov     rax, [rcx]
0x180018f29  mov     rax, [rax+10h]
0x180018f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f32  nop
0x180018f33  mov     eax, edi
0x180018f35  add     rsp, 70h
0x180018f39  pop     r15
0x180018f3b  pop     r14
0x180018f3d  pop     r12
0x180018f3f  pop     rdi
0x180018f40  pop     rsi
0x180018f41  pop     rbx
0x180018f42  pop     rbp
0x180018f43  retn
```
