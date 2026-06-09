# CTSScpRegister::TryUpdateScpAttributes(void)

- ea: `0x18007c4cc`
- end: `0x18007c91a`
- name: `?TryUpdateScpAttributes@CTSScpRegister@@AEAAJXZ`
- size: `1102`
- prototype: `__int64 __fastcall(CTSScpRegister *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18007bb18`

## callees

- `0x180005665`
- `0x18001ad74`
- `0x18001ae3c`
- `0x18001aea4`
- `0x180078bbc`
- `0x18007ab8c`
- `0x18007b2a8`
- `0x18007c0e0`
- `0x18007c368`
- `0x18007c4cc`
- `0x1800a0fb0`
- `0x1800a5010`

## import_xrefs

- `ACTIVEDS!__imp_ADsGetObject` at `0x18007c559`
- `ACTIVEDS!__imp_ADsGetObject` at `0x18007c559`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18007c5bd`
- `ACTIVEDS!__imp_FreeADsMem` at `0x18007c5bd`
- `KERNEL32!GetLastError` at `0x18007c657`
- `KERNEL32!GetLastError` at `0x18007c657`
- `KERNEL32!LocalAlloc` at `0x18007c735`
- `KERNEL32!LocalAlloc` at `0x18007c7d3`
- `KERNEL32!LocalAlloc` at `0x18007c735`
- `KERNEL32!LocalAlloc` at `0x18007c7d3`
- `KERNEL32!LocalFree` at `0x18007c5d4`
- `KERNEL32!LocalFree` at `0x18007c5e8`
- `KERNEL32!LocalFree` at `0x18007c5d4`
- `KERNEL32!LocalFree` at `0x18007c5e8`

## string_xrefs

- `0x18007c51f`: `serviceBindingInformation`
- `0x18007c871`: `serviceBindingInformation`
- `0x18007c514`: `serviceDnsName`
- `0x18007c84f`: `serviceDnsName`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTSScpRegister::TryUpdateScpAttributes(CTSScpRegister *this)
{
  BOOL v2; // r12d
  _DWORD *v3; // r15
  int Object; // eax
  _QWORD *v5; // r10
  __int64 v6; // rdx
  int v7; // edi
  LPVOID v9; // r14
  _DWORD *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 i; // r8
  __int64 v14; // rdx
  HLOCAL v15; // rdi
  __int64 v16; // r8
  unsigned int v17; // ecx
  __int64 v18; // rdx
  int v19; // [rsp+38h] [rbp-79h] BYREF
  LPCWSTR lpszPathName; // [rsp+40h] [rbp-71h] BYREF
  void *ppObject; // [rsp+48h] [rbp-69h] BYREF
  LPVOID pMem; // [rsp+50h] [rbp-61h] BYREF
  _DWORD v23[2]; // [rsp+58h] [rbp-59h] BYREF
  __int64 v24; // [rsp+60h] [rbp-51h]
  __int64 v25; // [rsp+68h] [rbp-49h]
  _QWORD v26[3]; // [rsp+70h] [rbp-41h] BYREF
  const wchar_t *v27; // [rsp+88h] [rbp-29h] BYREF
  int v28; // [rsp+90h] [rbp-21h]
  int v29; // [rsp+94h] [rbp-1Dh]
  _DWORD *v30; // [rsp+98h] [rbp-19h]
  int v31; // [rsp+A0h] [rbp-11h]
  const wchar_t *v32; // [rsp+A8h] [rbp-9h]
  int v33; // [rsp+B0h] [rbp-1h]
  int v34; // [rsp+B4h] [rbp+3h]
  _DWORD *v35; // [rsp+B8h] [rbp+7h]
  int v36; // [rsp+C0h] [rbp+Fh]
  const wchar_t *v37; // [rsp+C8h] [rbp+17h]
  int v38; // [rsp+D0h] [rbp+1Fh]
  int v39; // [rsp+D4h] [rbp+23h]
  HLOCAL v40; // [rsp+D8h] [rbp+27h]
  unsigned int v41; // [rsp+E0h] [rbp+2Fh]

  v2 = 1;
  ppObject = 0;
  lpszPathName = 0;
  pMem = 0;
  v3 = 0;
  v26[0] = L"serviceDnsName";
  v26[1] = L"serviceBindingInformation";
  v26[2] = L"keywords";
  v19 = 0;
  if ( (int)GetScpLdapBindPathFromRegistry(*((_QWORD *)this + 12), (LPBYTE *)&lpszPathName) < 0 )
    goto LABEL_7;
  Object = ADsGetObject(lpszPathName, &IID_IDirectoryObject, &ppObject);
  if ( Object < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_7;
    v6 = 60;
LABEL_6:
    WPP_SF_D(v5[2], v6, WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids, (unsigned int)Object);
LABEL_7:
    CTSScpRegister::TryUnRegisterSCP(this);
    v7 = CTSScpRegister::TryRegisterSCP(this);
    goto LABEL_8;
  }
  v7 = (*(__int64 (__fastcall **)(void *, _QWORD *, __int64, LPVOID *, int *))(*(_QWORD *)ppObject + 32LL))(
         ppObject,
         v26,
         3,
         &pMem,
         &v19);
  if ( v7 < 0 )
  {
    Object = GetLastError();
    if ( Object > 0 )
      Object = (unsigned __int16)Object | 0x80070000;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_7;
    v6 = 61;
    goto LABEL_6;
  }
  v9 = pMem;
  if ( !(unsigned int)IsAttributeValueChanged(3, 1, (int)this + 144, v19, (__int64)pMem)
    && !(unsigned int)IsAttributeValueChanged(6, *((_DWORD *)this + 30), *((_QWORD *)this + 16), v19, (__int64)v9) )
  {
    v2 = IsAttributeValueChanged(2, *((_DWORD *)this + 26), *((_QWORD *)this + 14), v19, (__int64)v9) != 0;
  }
  if ( v2 )
  {
    v23[1] = 0;
    v25 = 0;
    v23[0] = 3;
    v24 = *((_QWORD *)this + 18);
    v10 = LocalAlloc(0, 24LL * *((unsigned int *)this + 30));
    v3 = v10;
    if ( !v10 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_30;
      v11 = 62;
      v12 = *((_QWORD *)WPP_GLOBAL_Control + 2);
LABEL_29:
      WPP_SF_S(v12, v11, WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids, L"_T(\"LocalAlloc\")");
LABEL_30:
      v7 = -2147024882;
      goto LABEL_8;
    }
    memset_0(v10, 0, 24LL * *((unsigned int *)this + 30));
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 30); i = (unsigned int)(i + 1) )
    {
      v14 = 3 * i;
      v3[2 * v14] = 3;
      *(_QWORD *)&v3[2 * v14 + 2] = *(_QWORD *)(*((_QWORD *)this + 16) + 8 * i);
    }
    v15 = LocalAlloc(0, 24LL * *((unsigned int *)this + 26));
    if ( !v15 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_30;
      v11 = 63;
      v12 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      goto LABEL_29;
    }
    memset_0(v15, 0, 24LL * *((unsigned int *)this + 26));
    v16 = 0;
    v17 = *((_DWORD *)this + 26);
    if ( v17 )
    {
      do
      {
        v18 = 3 * v16;
        *((_DWORD *)v15 + 2 * v18) = 3;
        *((_QWORD *)v15 + v18 + 1) = *(_QWORD *)(*((_QWORD *)this + 14) + 8 * v16);
        v16 = (unsigned int)(v16 + 1);
        v17 = *((_DWORD *)this + 26);
      }
      while ( (unsigned int)v16 < v17 );
    }
    v27 = L"serviceDnsName";
    v28 = 2;
    v29 = 3;
    v30 = v23;
    v31 = 1;
    v32 = L"serviceBindingInformation";
    v33 = 2;
    v34 = 3;
    v35 = v3;
    v36 = *((_DWORD *)this + 30);
    v37 = L"keywords";
    v38 = 2;
    v39 = 3;
    v40 = v15;
    v41 = v17;
    v7 = (*(__int64 (__fastcall **)(void *, const wchar_t **, __int64, int *))(*(_QWORD *)ppObject + 40LL))(
           ppObject,
           &v27,
           3,
           &v19);
    if ( v7 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        64,
        (unsigned int)WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids,
        (unsigned int)L"\"SetObjectAttributes\"",
        v7);
  }
LABEL_8:
  if ( pMem )
    FreeADsMem(pMem);
  if ( lpszPathName )
    LocalFree((HLOCAL)lpszPathName);
  if ( v3 )
    LocalFree(v3);
  ATL::CComPtrBase<IADs>::~CComPtrBase<IADs>(&ppObject);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18007c4cc  mov     rax, rsp
0x18007c4cf  mov     [rax+10h], rbx
0x18007c4d3  mov     [rax+18h], rdi
0x18007c4d7  mov     [rax+20h], r12
0x18007c4db  push    rbp
0x18007c4dc  push    r14
0x18007c4de  push    r15
0x18007c4e0  lea     rbp, [rax-5Fh]
0x18007c4e4  sub     rsp, 0F0h
0x18007c4eb  mov     rax, cs:__security_cookie
0x18007c4f2  xor     rax, rsp
0x18007c4f5  mov     [rbp+57h+var_20], rax
0x18007c4f9  mov     rbx, rcx
0x18007c4fc  mov     r12d, 1
0x18007c502  and     [rbp+57h+ppObject], 0
0x18007c507  and     [rbp+57h+lpszPathName], 0
0x18007c50c  and     [rbp+57h+pMem], 0
0x18007c511  xor     r15d, r15d
0x18007c514  lea     rax, aServicednsname_1; "serviceDnsName"
0x18007c51b  mov     [rbp+57h+var_98], rax
0x18007c51f  lea     rax, aServicebinding; "serviceBindingInformation"
0x18007c526  mov     [rbp+57h+var_90], rax
0x18007c52a  lea     rax, aKeywords; "keywords"
0x18007c531  mov     [rbp+57h+var_88], rax
0x18007c535  and     [rbp+57h+var_D0], r15d
0x18007c539  lea     rdx, [rbp+57h+lpszPathName]
0x18007c53d  mov     rcx, [rcx+60h]
0x18007c541  call    GetScpLdapBindPathFromRegistry
0x18007c546  test    eax, eax
0x18007c548  js      short loc_18007C59F
0x18007c54a  lea     r8, [rbp+57h+ppObject]; ppObject
0x18007c54e  lea     rdx, IID_IDirectoryObject; riid
0x18007c555  mov     rcx, [rbp+57h+lpszPathName]; lpszPathName
0x18007c559  call    cs:__imp_ADsGetObject
0x18007c560  nop     dword ptr [rax+rax+00h]
0x18007c565  test    eax, eax
0x18007c567  jns     loc_18007C62A
0x18007c56d  lea     rcx, WPP_GLOBAL_Control
0x18007c574  mov     r10, cs:WPP_GLOBAL_Control
0x18007c57b  cmp     r10, rcx
0x18007c57e  jz      short loc_18007C59F
0x18007c580  cmp     byte ptr [r10+19h], 2
0x18007c585  jb      short loc_18007C59F
0x18007c587  lea     edx, [r12+3Bh]
0x18007c58c  mov     r9d, eax
0x18007c58f  lea     r8, WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids
0x18007c596  mov     rcx, [r10+10h]
0x18007c59a  call    WPP_SF_D
0x18007c59f  mov     rcx, rbx; this
0x18007c5a2  call    ?TryUnRegisterSCP@CTSScpRegister@@AEAAJXZ; CTSScpRegister::TryUnRegisterSCP(void)
0x18007c5a7  mov     rcx, rbx; this
0x18007c5aa  call    ?TryRegisterSCP@CTSScpRegister@@AEAAJXZ; CTSScpRegister::TryRegisterSCP(void)
0x18007c5af  mov     edi, eax
0x18007c5b1  mov     r14, [rbp+57h+pMem]
0x18007c5b5  test    r14, r14
0x18007c5b8  jz      short loc_18007C5C9
0x18007c5ba  mov     rcx, r14; pMem
0x18007c5bd  call    cs:__imp_FreeADsMem
0x18007c5c4  nop     dword ptr [rax+rax+00h]
0x18007c5c9  cmp     [rbp+57h+lpszPathName], 0
0x18007c5ce  jz      short loc_18007C5E0
0x18007c5d0  mov     rcx, [rbp+57h+lpszPathName]; hMem
0x18007c5d4  call    cs:__imp_LocalFree
0x18007c5db  nop     dword ptr [rax+rax+00h]
0x18007c5e0  test    r15, r15
0x18007c5e3  jz      short loc_18007C5F5
0x18007c5e5  mov     rcx, r15; hMem
0x18007c5e8  call    cs:__imp_LocalFree
0x18007c5ef  nop     dword ptr [rax+rax+00h]
0x18007c5f4  nop
0x18007c5f5  lea     rcx, [rbp+57h+ppObject]
0x18007c5f9  call    ??1?$CComPtrBase@UIADs@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IADs>::~CComPtrBase<IADs>(void)
0x18007c5fe  mov     eax, edi
0x18007c600  mov     rcx, [rbp+57h+var_20]
0x18007c604  xor     rcx, rsp; StackCookie
0x18007c607  call    __security_check_cookie
0x18007c60c  lea     r11, [rsp+100h+var_10]
0x18007c614  mov     rbx, [r11+28h]
0x18007c618  mov     rdi, [r11+30h]
0x18007c61c  mov     r12, [r11+38h]
0x18007c620  mov     rsp, r11
0x18007c623  pop     r15
0x18007c625  pop     r14
0x18007c627  pop     rbp
0x18007c628  retn
0x18007c62a  mov     rcx, [rbp+57h+ppObject]
0x18007c62e  mov     rax, [rcx]
0x18007c631  lea     rdx, [rbp+57h+var_D0]
0x18007c635  mov     [rsp+100h+var_E0], rdx
0x18007c63a  lea     r9, [rbp+57h+pMem]
0x18007c63e  mov     r8d, 3
0x18007c644  lea     rdx, [rbp+57h+var_98]
0x18007c648  mov     rax, [rax+20h]
0x18007c64c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c651  mov     edi, eax
0x18007c653  test    eax, eax
0x18007c655  jns     short loc_18007C69B
0x18007c657  call    cs:__imp_GetLastError
0x18007c65e  nop     dword ptr [rax+rax+00h]
0x18007c663  test    eax, eax
0x18007c665  jle     short loc_18007C66F
0x18007c667  movzx   eax, ax
0x18007c66a  or      eax, 80070000h
0x18007c66f  lea     rcx, WPP_GLOBAL_Control
0x18007c676  mov     r10, cs:WPP_GLOBAL_Control
0x18007c67d  cmp     r10, rcx
0x18007c680  jz      loc_18007C59F
0x18007c686  cmp     byte ptr [r10+19h], 2
0x18007c68b  jb      loc_18007C59F
0x18007c691  mov     edx, 3Dh ; '='
0x18007c696  jmp     loc_18007C58C
0x18007c69b  lea     r8, [rbx+90h]
0x18007c6a2  mov     r14, [rbp+57h+pMem]
0x18007c6a6  mov     [rsp+100h+var_E0], r14
0x18007c6ab  mov     r9d, [rbp+57h+var_D0]
0x18007c6af  mov     edx, 1
0x18007c6b4  lea     ecx, [rdx+2]
0x18007c6b7  call    IsAttributeValueChanged
0x18007c6bc  test    eax, eax
0x18007c6be  jnz     short loc_18007C6FE
0x18007c6c0  mov     [rsp+100h+var_E0], r14
0x18007c6c5  mov     r9d, [rbp+57h+var_D0]
0x18007c6c9  mov     r8, [rbx+80h]
0x18007c6d0  mov     edx, [rbx+78h]
0x18007c6d3  lea     ecx, [rax+6]
0x18007c6d6  call    IsAttributeValueChanged
0x18007c6db  test    eax, eax
0x18007c6dd  jnz     short loc_18007C6FE
0x18007c6df  mov     [rsp+100h+var_E0], r14
0x18007c6e4  mov     r9d, [rbp+57h+var_D0]
0x18007c6e8  mov     r8, [rbx+70h]
0x18007c6ec  mov     edx, [rbx+68h]
0x18007c6ef  lea     ecx, [rax+2]
0x18007c6f2  call    IsAttributeValueChanged
0x18007c6f7  neg     eax
0x18007c6f9  sbb     ecx, ecx
0x18007c6fb  and     r12d, ecx
0x18007c6fe  mov     r14d, 1
0x18007c704  cmp     r12d, r14d
0x18007c707  jnz     loc_18007C5B1
0x18007c70d  and     [rbp+57h+var_AC], r15d
0x18007c711  and     [rbp+57h+var_A0], r15
0x18007c715  lea     r12d, [r14+2]
0x18007c719  mov     [rbp+57h+var_B0], r12d
0x18007c71d  mov     rax, [rbx+90h]
0x18007c724  mov     [rbp+57h+var_A8], rax
0x18007c728  mov     eax, [rbx+78h]
0x18007c72b  lea     rdx, [rax+rax*2]
0x18007c72f  shl     rdx, 3; uBytes
0x18007c733  xor     ecx, ecx; uFlags
0x18007c735  call    cs:__imp_LocalAlloc
0x18007c73c  nop     dword ptr [rax+rax+00h]
0x18007c741  mov     r15, rax
0x18007c744  test    rax, rax
0x18007c747  jnz     short loc_18007C787
0x18007c749  lea     rcx, WPP_GLOBAL_Control
0x18007c750  mov     r10, cs:WPP_GLOBAL_Control
0x18007c757  cmp     r10, rcx
0x18007c75a  jz      short loc_18007C77D
0x18007c75c  cmp     byte ptr [r10+19h], 2
0x18007c761  jb      short loc_18007C77D
0x18007c763  lea     edx, [rax+3Eh]
0x18007c766  mov     rcx, [r10+10h]
0x18007c76a  lea     r8, WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids
0x18007c771  lea     r9, aTLocalalloc; "_T(\"LocalAlloc\")"
0x18007c778  call    WPP_SF_S
0x18007c77d  mov     edi, 8007000Eh
0x18007c782  jmp     loc_18007C5B1
0x18007c787  mov     eax, [rbx+78h]
0x18007c78a  lea     r8, [rax+rax*2]
0x18007c78e  shl     r8, 3; Size
0x18007c792  xor     edx, edx; Val
0x18007c794  mov     rcx, r15; void *
0x18007c797  call    memset_0
0x18007c79c  xor     r8d, r8d
0x18007c79f  cmp     [rbx+78h], r8d
0x18007c7a3  jbe     short loc_18007C7C6
0x18007c7a5  lea     rdx, [r8+r8*2]
0x18007c7a9  mov     [r15+rdx*8], r12d
0x18007c7ad  mov     rax, [rbx+80h]
0x18007c7b4  mov     rcx, [rax+r8*8]
0x18007c7b8  mov     [r15+rdx*8+8], rcx
0x18007c7bd  add     r8d, r14d
0x18007c7c0  cmp     r8d, [rbx+78h]
0x18007c7c4  jb      short loc_18007C7A5
0x18007c7c6  mov     eax, [rbx+68h]
0x18007c7c9  lea     rdx, [rax+rax*2]
0x18007c7cd  shl     rdx, 3; uBytes
0x18007c7d1  xor     ecx, ecx; uFlags
0x18007c7d3  call    cs:__imp_LocalAlloc
0x18007c7da  nop     dword ptr [rax+rax+00h]
0x18007c7df  mov     rdi, rax
0x18007c7e2  test    rax, rax
0x18007c7e5  jnz     short loc_18007C810
0x18007c7e7  lea     rcx, WPP_GLOBAL_Control
0x18007c7ee  mov     rax, cs:WPP_GLOBAL_Control
0x18007c7f5  cmp     rax, rcx
0x18007c7f8  jz      short loc_18007C77D
0x18007c7fa  cmp     byte ptr [rax+19h], 2
0x18007c7fe  jb      loc_18007C77D
0x18007c804  lea     edx, [rdi+3Fh]
0x18007c807  mov     rcx, [rax+10h]
0x18007c80b  jmp     loc_18007C76A
0x18007c810  mov     eax, [rbx+68h]
0x18007c813  lea     r8, [rax+rax*2]
0x18007c817  shl     r8, 3; Size
0x18007c81b  xor     edx, edx; Val
0x18007c81d  mov     rcx, rdi; void *
0x18007c820  call    memset_0
0x18007c825  xor     r8d, r8d
0x18007c828  mov     ecx, [rbx+68h]
0x18007c82b  test    ecx, ecx
0x18007c82d  jz      short loc_18007C84F
0x18007c82f  lea     rdx, [r8+r8*2]
0x18007c833  mov     [rdi+rdx*8], r12d
0x18007c837  mov     rax, [rbx+70h]
0x18007c83b  mov     rcx, [rax+r8*8]
0x18007c83f  mov     [rdi+rdx*8+8], rcx
0x18007c844  add     r8d, r14d
0x18007c847  mov     ecx, [rbx+68h]
0x18007c84a  cmp     r8d, ecx
0x18007c84d  jb      short loc_18007C82F
0x18007c84f  lea     rax, aServicednsname_1; "serviceDnsName"
0x18007c856  mov     [rbp+57h+var_80], rax
0x18007c85a  mov     [rbp+57h+var_78], 2
0x18007c861  mov     [rbp+57h+var_74], r12d
0x18007c865  lea     rax, [rbp+57h+var_B0]
0x18007c869  mov     [rbp+57h+var_70], rax
0x18007c86d  mov     [rbp+57h+var_68], r14d
0x18007c871  lea     rax, aServicebinding; "serviceBindingInformation"
0x18007c878  mov     [rbp+57h+var_60], rax
0x18007c87c  mov     [rbp+57h+var_58], 2
0x18007c883  mov     [rbp+57h+var_54], r12d
0x18007c887  mov     [rbp+57h+var_50], r15
0x18007c88b  mov     eax, [rbx+78h]
0x18007c88e  mov     [rbp+57h+var_48], eax
0x18007c891  lea     rax, aKeywords; "keywords"
0x18007c898  mov     [rbp+57h+var_40], rax
0x18007c89c  mov     [rbp+57h+var_38], 2
0x18007c8a3  mov     [rbp+57h+var_34], r12d
0x18007c8a7  mov     [rbp+57h+var_30], rdi
0x18007c8ab  mov     [rbp+57h+var_28], ecx
0x18007c8ae  mov     rcx, [rbp+57h+ppObject]
0x18007c8b2  mov     rax, [rcx]
0x18007c8b5  lea     r9, [rbp+57h+var_D0]
0x18007c8b9  mov     r8d, r12d
0x18007c8bc  lea     rdx, [rbp+57h+var_80]
0x18007c8c0  mov     rax, [rax+28h]
0x18007c8c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c8c9  mov     edi, eax
0x18007c8cb  test    eax, eax
0x18007c8cd  jns     loc_18007C5B1
0x18007c8d3  lea     rcx, WPP_GLOBAL_Control
0x18007c8da  mov     rax, cs:WPP_GLOBAL_Control
0x18007c8e1  cmp     rax, rcx
0x18007c8e4  jz      loc_18007C5B1
0x18007c8ea  cmp     byte ptr [rax+19h], 2
0x18007c8ee  jb      loc_18007C5B1
0x18007c8f4  mov     edx, 40h ; '@'
0x18007c8f9  mov     dword ptr [rsp+100h+var_E0], edi
0x18007c8fd  lea     r9, aSetobjectattri; "\"SetObjectAttributes\""
0x18007c904  lea     r8, WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids
0x18007c90b  mov     rcx, [rax+10h]
0x18007c90f  call    WPP_SF_SD
0x18007c914  jmp     loc_18007C5B1
```
