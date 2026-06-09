# CMFSourceResolver::GetURLExtension(CResolverResult *)

- ea: `0x180019a40`
- end: `0x180019dea`
- name: `?GetURLExtension@CMFSourceResolver@@IEAAJPEAVCResolverResult@@@Z`
- size: `938`
- prototype: `__int64 __fastcall(CMFSourceResolver *__hidden this, struct CResolverResult *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000628c`

## callees

- `0x180004870`
- `0x180016bec`
- `0x180016ec4`
- `0x180018220`
- `0x180018278`
- `0x180019124`
- `0x180019a40`
- `0x180019df0`
- `0x18001b4c8`
- `0x1800214fc`
- `0x18007ba8c`
- `0x18009fc54`
- `0x180120ecc`
- `0x180174668`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180019b36`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180019b36`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180019c4d`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180019d91`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180019c4d`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180019d91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019b84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019c66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019b84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019c66`

## string_xrefs

- `0x180019caa`: `.directory`

## pseudocode

```c
__int64 __fastcall CMFSourceResolver::GetURLExtension(CMFSourceResolver *this, struct CResolverResult *a2)
{
  char *v4; // rsi
  char *v5; // rbx
  const unsigned __int16 *v6; // rax
  int v7; // r8d
  __int64 v8; // rax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  int v12; // eax
  __int64 v13; // rdx
  wchar_t *Ext; // rax
  __int64 (__fastcall ***v15)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v16)(_QWORD, GUID *, __int64 *); // rbx
  wchar_t *Buffer; // rax
  __int64 v18; // [rsp+50h] [rbp-39h] BYREF
  int v19; // [rsp+58h] [rbp-31h]
  int v20; // [rsp+5Ch] [rbp-2Dh]
  __int64 v21; // [rsp+60h] [rbp-29h]
  __int64 v22; // [rsp+68h] [rbp-21h] BYREF
  unsigned int v23; // [rsp+70h] [rbp-19h]
  int v24; // [rsp+A8h] [rbp+1Fh]
  int v25; // [rsp+F8h] [rbp+6Fh] BYREF
  LPVOID pv; // [rsp+100h] [rbp+77h] BYREF
  __int64 v27; // [rsp+108h] [rbp+7Fh] BYREF

  v27 = 0;
  pv = 0;
  v25 = 0;
  if ( !a2 )
  {
    v12 = -2147467261;
    v9 = -2147467261;
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_16;
    v13 = 166;
    goto LABEL_21;
  }
  if ( !*((_QWORD *)a2 + 24) )
  {
    v12 = -2147467261;
    v9 = -2147467261;
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_16;
    v13 = 167;
    goto LABEL_21;
  }
  v4 = (char *)a2 + 144;
  *(_QWORD *)((char *)a2 + 148) = 0;
  v5 = (char *)a2 + 120;
  if ( (unsigned int)CMFBaseStringT<unsigned short>::IsEmpty((char *)a2 + 120) )
  {
LABEL_13:
    v9 = 0;
    if ( (unsigned int)CMFBaseStringT<unsigned short>::IsEmpty(v4) && *((char *)a2 + 232) < 0 )
      CMFBaseStringT<unsigned short>::operator=(v4, ".directory");
    if ( !(unsigned int)CMFBaseStringT<unsigned short>::IsEmpty(v4) )
      goto LABEL_15;
    v15 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)a2 + 24);
    v16 = **v15;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
    v12 = v16(v15, &GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3, &v27);
    v9 = v12;
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, const IID *, LPVOID *, int *))(*(_QWORD *)v27 + 104LL))(
              v27,
              &MF_BYTESTREAM_ORIGIN_NAME,
              &pv,
              &v25);
      v9 = v12;
      if ( v12 >= 0 )
      {
        Buffer = (wchar_t *)CMFBaseStringT<unsigned short>::GetBuffer(v4, 256);
        if ( Buffer )
        {
          if ( !_wsplitpath_s((const wchar_t *)pv, 0, 0, 0, 0, 0, 0, Buffer, 0x100u) )
            CMFBaseStringT<unsigned short>::ReleaseBuffer(v4, 0xFFFFFFFFLL);
LABEL_15:
          if ( (unsigned int)CMFBaseStringT<unsigned short>::IsEmpty(v4) )
          {
            v9 = -2147467259;
            if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                172,
                &WPP_ef38ce74783430fcef771c0ef296c5cd_Traceguids,
                this,
                -2147467259);
          }
          goto LABEL_16;
        }
        v12 = -2147024882;
        v9 = -2147024882;
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_16;
        v13 = 171;
      }
      else
      {
        if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
          goto LABEL_16;
        v13 = 170;
      }
    }
    else
    {
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_16;
      v13 = 169;
    }
LABEL_21:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_ef38ce74783430fcef771c0ef296c5cd_Traceguids, this, v12);
    goto LABEL_16;
  }
  v19 = 0;
  v18 = (unsigned int)v18 & 0xFFFFFFF8;
  v21 = 0;
  v20 = 0;
  v24 = 1;
  memset_0(&v22, 0, 0x40u);
  v6 = (const unsigned __int16 *)CMFBaseStringT<unsigned short>::PContents(v5);
  if ( (int)CUri::Parse((CUri *)&v18, v6, v7) >= 0 )
  {
    if ( (unsigned int)_o__wcsnicmp(v22, L"ms-winsoundevent", v23) )
      CUri::GetExtension(&v18, v4);
    goto LABEL_12;
  }
  v8 = CMFBaseStringT<unsigned short>::PContents(v5);
  if ( (unsigned int)MFCreatePathFromURL(v8, (__int64)&pv) )
  {
LABEL_12:
    CMFBaseStringT<unsigned short>::~CMFBaseStringT<unsigned short>(&v18);
    goto LABEL_13;
  }
  if ( *((int *)v4 + 1) >= 0 && (int)CMFBaseStringT<unsigned short>::_EnsureSpace(v4, 256) >= 0 )
  {
    Ext = (wchar_t *)*((_QWORD *)v4 + 2);
    if ( Ext )
    {
      if ( !_wsplitpath_s((const wchar_t *)pv, 0, 0, 0, 0, 0, 0, Ext, 0x100u) )
        CMFBaseStringT<unsigned short>::ReleaseBuffer(v4, 0xFFFFFFFFLL);
      CoTaskMemFree(pv);
      pv = 0;
      goto LABEL_12;
    }
  }
  v9 = -2147024882;
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      168,
      &WPP_ef38ce74783430fcef771c0ef296c5cd_Traceguids,
      this,
      -2147024882);
  CMFBaseStringT<unsigned short>::~CMFBaseStringT<unsigned short>(&v18);
LABEL_16:
  CoTaskMemFree(pv);
  pv = 0;
  v10 = v27;
  if ( v27 )
  {
    v27 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  return v9;
}

```

## disassembly

```asm
0x180019a40  push    rbp
0x180019a42  push    rbx
0x180019a43  push    rsi
0x180019a44  push    rdi
0x180019a45  push    r12
0x180019a47  push    r14
0x180019a49  push    r15
0x180019a4b  lea     rbp, [rsp-27h]
0x180019a50  sub     rsp, 0B0h
0x180019a57  mov     rdi, rdx
0x180019a5a  mov     r14, rcx
0x180019a5d  xor     r15d, r15d
0x180019a60  mov     [rbp+57h+arg_18], r15
0x180019a64  mov     [rbp+57h+pv], r15
0x180019a68  mov     [rbp+57h+arg_8], r15d
0x180019a6c  test    rdx, rdx
0x180019a6f  jz      loc_180019BBB
0x180019a75  cmp     [rdx+0C0h], r15
0x180019a7c  jz      loc_180019BE0
0x180019a82  lea     rsi, [rdx+90h]
0x180019a89  mov     [rsi+4], r15
0x180019a8d  lea     rbx, [rdx+78h]
0x180019a91  mov     rcx, rbx
0x180019a94  call    ?IsEmpty@?$CMFBaseStringT@G@@QEBAHXZ; CMFBaseStringT<ushort>::IsEmpty(void)
0x180019a99  mov     r12d, 100h
0x180019a9f  test    eax, eax
0x180019aa1  jnz     loc_180019B4D
0x180019aa7  mov     [rbp+57h+var_8C], r15
0x180019aab  and     [rbp+57h+var_90], 0FFFFFFF8h
0x180019aaf  mov     [rbp+57h+var_80], r15
0x180019ab3  mov     [rbp+57h+var_84], r15d
0x180019ab7  mov     [rbp+57h+var_38], 1
0x180019abe  xor     edx, edx; Val
0x180019ac0  lea     r8d, [r15+40h]; Size
0x180019ac4  lea     rcx, [rbp+57h+var_78]; void *
0x180019ac8  call    memset_0
0x180019acd  nop
0x180019ace  mov     rcx, rbx
0x180019ad1  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x180019ad6  mov     rdx, rax; unsigned __int16 *
0x180019ad9  lea     rcx, [rbp+57h+var_90]; this
0x180019add  call    ?Parse@CUri@@QEAAJPEBGJ@Z; CUri::Parse(ushort const *,long)
0x180019ae2  test    eax, eax
0x180019ae4  jns     short loc_180019B27
0x180019ae6  mov     rcx, rbx
0x180019ae9  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x180019aee  mov     rcx, rax
0x180019af1  lea     rdx, [rbp+57h+pv]
0x180019af5  call    MFCreatePathFromURL
0x180019afa  test    eax, eax
0x180019afc  jnz     short loc_180019B44
0x180019afe  cmp     [rsi+4], r15d
0x180019b02  jge     loc_180019C08
0x180019b08  mov     eax, 8007000Eh
0x180019b0d  mov     ebx, eax
0x180019b0f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180019b16  jnb     loc_180019C75
0x180019b1c  lea     rcx, [rbp+57h+var_90]
0x180019b20  call    ??1?$CMFBaseStringT@G@@QEAA@XZ; CMFBaseStringT<ushort>::~CMFBaseStringT<ushort>(void)
0x180019b25  jmp     short loc_180019B80
0x180019b27  mov     r8d, [rbp+57h+var_70]
0x180019b2b  lea     rdx, aMsWinsoundeven; "ms-winsoundevent"
0x180019b32  mov     rcx, [rbp+57h+var_78]
0x180019b36  call    cs:__imp__o__wcsnicmp
0x180019b3c  test    eax, eax
0x180019b3e  jnz     loc_180019BF7
0x180019b44  lea     rcx, [rbp+57h+var_90]
0x180019b48  call    ??1?$CMFBaseStringT@G@@QEAA@XZ; CMFBaseStringT<ushort>::~CMFBaseStringT<ushort>(void)
0x180019b4d  mov     ebx, r15d
0x180019b50  mov     rcx, rsi
0x180019b53  call    ?IsEmpty@?$CMFBaseStringT@G@@QEBAHXZ; CMFBaseStringT<ushort>::IsEmpty(void)
0x180019b58  test    eax, eax
0x180019b5a  jnz     loc_180019C9D
0x180019b60  mov     rcx, rsi
0x180019b63  call    ?IsEmpty@?$CMFBaseStringT@G@@QEBAHXZ; CMFBaseStringT<ushort>::IsEmpty(void)
0x180019b68  test    eax, eax
0x180019b6a  jnz     loc_180019CBE
0x180019b70  mov     rcx, rsi
0x180019b73  call    ?IsEmpty@?$CMFBaseStringT@G@@QEBAHXZ; CMFBaseStringT<ushort>::IsEmpty(void)
0x180019b78  test    eax, eax
0x180019b7a  jnz     loc_180019DAF
0x180019b80  mov     rcx, [rbp+57h+pv]; pv
0x180019b84  call    cs:__imp_CoTaskMemFree
0x180019b8a  mov     [rbp+57h+pv], r15
0x180019b8e  mov     rcx, [rbp+57h+arg_18]
0x180019b92  test    rcx, rcx
0x180019b95  jz      short loc_180019BA7
0x180019b97  mov     [rbp+57h+arg_18], r15
0x180019b9b  mov     rax, [rcx]
0x180019b9e  mov     rax, [rax+10h]
0x180019ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ba7  mov     eax, ebx
0x180019ba9  add     rsp, 0B0h
0x180019bb0  pop     r15
0x180019bb2  pop     r14
0x180019bb4  pop     r12
0x180019bb6  pop     rdi
0x180019bb7  pop     rsi
0x180019bb8  pop     rbx
0x180019bb9  pop     rbp
0x180019bba  retn
0x180019bbb  mov     eax, 80004003h
0x180019bc0  mov     ebx, eax
0x180019bc2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180019bc9  jb      short loc_180019B80
0x180019bcb  mov     edx, 0A6h
0x180019bd0  jmp     short loc_180019BD7
0x180019bd2  mov     edx, 0ABh
0x180019bd7  mov     dword ptr [rsp+0E0h+DirCount], eax
0x180019bdb  jmp     loc_180019DCA
0x180019be0  mov     eax, 80004003h
0x180019be5  mov     ebx, eax
0x180019be7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180019bee  jb      short loc_180019B80
0x180019bf0  mov     edx, 0A7h
0x180019bf5  jmp     short loc_180019BD7
0x180019bf7  mov     rdx, rsi
0x180019bfa  lea     rcx, [rbp+57h+var_90]
0x180019bfe  call    ?GetExtension@CUri@@QEAAJAEAV?$CMFBaseStringT@G@@@Z; CUri::GetExtension(CMFBaseStringT<ushort> &)
0x180019c03  jmp     loc_180019B44
0x180019c08  mov     edx, r12d
0x180019c0b  mov     rcx, rsi
0x180019c0e  call    ?_EnsureSpace@?$CMFBaseStringT@G@@IEAAJJ@Z; CMFBaseStringT<ushort>::_EnsureSpace(long)
0x180019c13  test    eax, eax
0x180019c15  js      loc_180019B08
0x180019c1b  mov     rax, [rsi+10h]
0x180019c1f  test    rax, rax
0x180019c22  jz      loc_180019B08
0x180019c28  mov     [rsp+0E0h+ExtCount], r12; ExtCount
0x180019c2d  mov     [rsp+0E0h+Ext], rax; Ext
0x180019c32  mov     [rsp+0E0h+FilenameCount], r15; FilenameCount
0x180019c37  mov     [rsp+0E0h+Filename], r15; Filename
0x180019c3c  mov     [rsp+0E0h+DirCount], r15; DirCount
0x180019c41  xor     r9d, r9d; Dir
0x180019c44  xor     r8d, r8d; DriveCount
0x180019c47  xor     edx, edx; Drive
0x180019c49  mov     rcx, [rbp+57h+pv]; FullPath
0x180019c4d  call    cs:__imp__wsplitpath_s
0x180019c53  test    eax, eax
0x180019c55  jnz     short loc_180019C62
0x180019c57  or      edx, 0FFFFFFFFh
0x180019c5a  mov     rcx, rsi
0x180019c5d  call    ?ReleaseBuffer@?$CMFBaseStringT@G@@QEAAJJ@Z; CMFBaseStringT<ushort>::ReleaseBuffer(long)
0x180019c62  mov     rcx, [rbp+57h+pv]; pv
0x180019c66  call    cs:__imp_CoTaskMemFree
0x180019c6c  mov     [rbp+57h+pv], r15
0x180019c70  jmp     loc_180019B44
0x180019c75  mov     edx, 0A8h
0x180019c7a  mov     dword ptr [rsp+0E0h+DirCount], eax
0x180019c7e  mov     r9, r14
0x180019c81  lea     r8, WPP_ef38ce74783430fcef771c0ef296c5cd_Traceguids
0x180019c88  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c8f  mov     rcx, [rcx+10h]
0x180019c93  call    WPP_SF_qD
0x180019c98  jmp     loc_180019B1C
0x180019c9d  test    byte ptr [rdi+0E8h], 80h
0x180019ca4  jz      loc_180019B60
0x180019caa  lea     rdx, aDirectory; ".directory"
0x180019cb1  mov     rcx, rsi
0x180019cb4  call    ??4?$CMFBaseStringT@G@@QEAAAEBV0@PEBD@Z; CMFBaseStringT<ushort>::operator=(char const *)
0x180019cb9  jmp     loc_180019B60
0x180019cbe  mov     rdi, [rdi+0C0h]
0x180019cc5  mov     rax, [rdi]
0x180019cc8  mov     rbx, [rax]
0x180019ccb  lea     rcx, [rbp+57h+arg_18]
0x180019ccf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180019cd4  lea     r8, [rbp+57h+arg_18]
0x180019cd8  lea     rdx, _GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3
0x180019cdf  mov     rcx, rdi
0x180019ce2  mov     rax, rbx
0x180019ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019cea  mov     ebx, eax
0x180019cec  test    eax, eax
0x180019cee  jns     short loc_180019D07
0x180019cf0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180019cf7  jb      loc_180019B80
0x180019cfd  mov     edx, 0A9h
0x180019d02  jmp     loc_180019BD7
0x180019d07  mov     rcx, [rbp+57h+arg_18]
0x180019d0b  mov     rax, [rcx]
0x180019d0e  lea     r9, [rbp+57h+arg_8]
0x180019d12  lea     r8, [rbp+57h+pv]
0x180019d16  lea     rdx, MF_BYTESTREAM_ORIGIN_NAME
0x180019d1d  mov     rax, [rax+68h]
0x180019d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019d26  mov     ebx, eax
0x180019d28  test    eax, eax
0x180019d2a  jns     short loc_180019D43
0x180019d2c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180019d33  jb      loc_180019B80
0x180019d39  mov     edx, 0AAh
0x180019d3e  jmp     loc_180019BD7
0x180019d43  mov     edx, r12d
0x180019d46  mov     rcx, rsi
0x180019d49  call    ?GetBuffer@?$CMFBaseStringT@G@@QEAAPEAGJ@Z; CMFBaseStringT<ushort>::GetBuffer(long)
0x180019d4e  test    rax, rax
0x180019d51  jnz     short loc_180019D6C
0x180019d53  mov     eax, 8007000Eh
0x180019d58  mov     ebx, eax
0x180019d5a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180019d61  jb      loc_180019B80
0x180019d67  jmp     loc_180019BD2
0x180019d6c  mov     [rsp+0E0h+ExtCount], r12; ExtCount
0x180019d71  mov     [rsp+0E0h+Ext], rax; Ext
0x180019d76  mov     [rsp+0E0h+FilenameCount], r15; FilenameCount
0x180019d7b  mov     [rsp+0E0h+Filename], r15; Filename
0x180019d80  mov     [rsp+0E0h+DirCount], r15; DirCount
0x180019d85  xor     r9d, r9d; Dir
0x180019d88  xor     r8d, r8d; DriveCount
0x180019d8b  xor     edx, edx; Drive
0x180019d8d  mov     rcx, [rbp+57h+pv]; FullPath
0x180019d91  call    cs:__imp__wsplitpath_s
0x180019d97  test    eax, eax
0x180019d99  jnz     loc_180019B70
0x180019d9f  or      edx, 0FFFFFFFFh
0x180019da2  mov     rcx, rsi
0x180019da5  call    ?ReleaseBuffer@?$CMFBaseStringT@G@@QEAAJJ@Z; CMFBaseStringT<ushort>::ReleaseBuffer(long)
0x180019daa  jmp     loc_180019B70
0x180019daf  mov     ebx, 80004005h
0x180019db4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180019dbb  jb      loc_180019B80
0x180019dc1  mov     edx, 0ACh
0x180019dc6  mov     dword ptr [rsp+0E0h+DirCount], ebx
0x180019dca  mov     rcx, cs:WPP_GLOBAL_Control
0x180019dd1  mov     r9, r14
0x180019dd4  lea     r8, WPP_ef38ce74783430fcef771c0ef296c5cd_Traceguids
0x180019ddb  mov     rcx, [rcx+10h]
0x180019ddf  call    WPP_SF_qD
0x180019de4  jmp     loc_180019B80
```
