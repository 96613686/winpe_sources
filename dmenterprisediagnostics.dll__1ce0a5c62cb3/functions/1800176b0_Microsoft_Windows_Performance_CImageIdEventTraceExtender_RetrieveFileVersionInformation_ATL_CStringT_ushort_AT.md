# Microsoft::Windows::Performance::CImageIdEventTraceExtender::RetrieveFileVersionInformation(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,XPerfCore::CFileMapping *)

- ea: `0x1800176b0`
- end: `0x1800179a2`
- name: `?RetrieveFileVersionInformation@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEAVCFileMapping@XPerfCore@@@Z`
- size: `754`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180011fec`

## callees

- `0x1800017e0`
- `0x180001804`
- `0x180009838`
- `0x180009994`
- `0x1800099b8`
- `0x180013adc`
- `0x180013b90`
- `0x1800149f0`
- `0x180014b00`
- `0x18001529c`
- `0x180017364`
- `0x1800176b0`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800177ad`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800177ad`

## string_xrefs

- `0x180017871`: `CompanyName`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::RetrieveFileVersionInformation(
        __int64 (__fastcall **a1)(_QWORD, _QWORD, _QWORD),
        __int64 a2,
        const unsigned __int16 *a3,
        struct XPerfCore::CFileMapping *a4)
{
  void *v8; // rcx
  int VersionInfo; // edi
  unsigned __int64 v10; // r8
  __int64 result; // rax
  unsigned __int64 v12; // r8
  void *v13; // rdi
  signed int Error; // ebx
  unsigned __int64 v15; // r8
  unsigned __int64 v16; // r8
  unsigned __int64 v17; // r8
  int v18; // eax
  __int64 *v19; // rax
  __int64 v20; // rdx
  unsigned int puLen[2]; // [rsp+30h] [rbp-278h] BYREF
  LPCVOID pBlock; // [rsp+38h] [rbp-270h] BYREF
  unsigned __int16 v23; // [rsp+40h] [rbp-268h]
  LPVOID lpBuffer[2]; // [rsp+48h] [rbp-260h] BYREF
  ATL::CAtlException *v25; // [rsp+58h] [rbp-250h] BYREF
  unsigned __int16 v26[264]; // [rsp+60h] [rbp-248h] BYREF

  lpBuffer[1] = a1;
  operator delete(0);
  v8 = 0;
  pBlock = 0;
  if ( !a4 )
  {
    VersionInfo = -2147467261;
LABEL_5:
    operator delete(v8);
    return (unsigned int)VersionInfo;
  }
  VersionInfo = XPerfCore::CFileVersionInfo::GetVersionInfo((XPerfCore::CFileVersionInfo *)&pBlock, a3, a4);
  if ( VersionInfo < 0 )
  {
    v8 = (void *)pBlock;
    goto LABEL_5;
  }
  XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v26, v10, L"FileDescription");
  try
  {
    ATL::CSimpleStringT<unsigned short,0>::Append(a2, (__int64)v26);
    ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
    XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v26, v12, L"FileVersion");
    ATL::CSimpleStringT<unsigned short,0>::Append(a2, (__int64)v26);
    ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
    lpBuffer[0] = 0;
    v13 = (void *)pBlock;
    if ( !pBlock )
    {
      Error = -2147418113;
LABEL_11:
      operator delete(v13);
      return (unsigned int)Error;
    }
    puLen[0] = 0;
    if ( VerQueryValueW(pBlock, L"\\", lpBuffer, puLen) )
    {
      if ( puLen[0] >= 0xC )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          a2,
          L"%u.%u.%u.%u",
          *((unsigned __int16 *)lpBuffer[0] + 5),
          *((unsigned __int16 *)lpBuffer[0] + 4),
          *((unsigned __int16 *)lpBuffer[0] + 7),
          *((unsigned __int16 *)lpBuffer[0] + 6));
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          a2,
          L"%u",
          v23);
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
        XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v26, v15, L"ProductName");
        ATL::CSimpleStringT<unsigned short,0>::Append(a2, (__int64)v26);
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
        XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v26, v16, L"CompanyName");
        ATL::CSimpleStringT<unsigned short,0>::Append(a2, (__int64)v26);
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
        XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v26, v17, L"ProductVersion");
        ATL::CSimpleStringT<unsigned short,0>::Append(a2, (__int64)v26);
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
        *(_QWORD *)puLen = 0;
        try
        {
          if ( Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable((Microsoft::Windows::Performance::CAeDelayLoad *)(a1 + 37)) )
            v18 = ((__int64 (__fastcall **)(const unsigned __int16 *, __int64, unsigned int *))a1)[39](a3, 1, puLen);
          else
            v18 = ATL::AtlHresultFromWin32(127);
          if ( v18 >= 0 )
          {
            v19 = *(__int64 **)puLen;
          }
          else
          {
            v19 = 0;
            *(_QWORD *)puLen = 0;
          }
          if ( v19 && *v19 )
            ATL::CSimpleStringT<unsigned short,0>::Append(a2, *v19);
          ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
          if ( *(_QWORD *)puLen )
          {
            v20 = *(_QWORD *)(*(_QWORD *)puLen + 8LL);
            if ( v20 )
              ATL::CSimpleStringT<unsigned short,0>::Append(a2, v20);
          }
          ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
          if ( *(_QWORD *)puLen )
          {
            Microsoft::Windows::Performance::CAeDelayLoad::PicFreeFileInfo(
              (Microsoft::Windows::Performance::CAeDelayLoad *)(a1 + 37),
              *(struct _FILE_INFO **)puLen);
            *(_QWORD *)puLen = 0;
          }
        }
        catch ( ... )
        {
          throw;
        }
        operator delete((void *)pBlock);
        return 0;
      }
    }
    else
    {
      lpBuffer[0] = 0;
      Error = ATL::AtlHresultFromLastError();
      if ( Error < 0 )
        goto LABEL_11;
    }
    operator delete(v13);
    result = 2147549183LL;
  }
  catch ( ATL::CAtlException *v25 )
  {
    return *(unsigned int *)v25;
  }
  return result;
}

```

## disassembly

```asm
0x1800176b0  push    rbx
0x1800176b2  push    rsi
0x1800176b3  push    rdi
0x1800176b4  push    r14
0x1800176b6  sub     rsp, 288h
0x1800176bd  mov     rax, cs:__security_cookie
0x1800176c4  xor     rax, rsp
0x1800176c7  mov     [rsp+2A8h+var_38], rax
0x1800176cf  mov     rdi, r9
0x1800176d2  mov     r14, r8
0x1800176d5  mov     rbx, rdx
0x1800176d8  mov     rsi, rcx
0x1800176db  mov     [rsp+2A8h+var_258], rcx
0x1800176e0  xor     ecx, ecx; void *
0x1800176e2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800176e7  xor     ecx, ecx
0x1800176e9  mov     [rsp+2A8h+pBlock], rcx
0x1800176ee  test    rdi, rdi
0x1800176f1  jnz     short loc_1800176FA
0x1800176f3  mov     edi, 80004003h
0x1800176f8  jmp     short loc_180017715
0x1800176fa  mov     r8, rdi; struct XPerfCore::CFileMapping *
0x1800176fd  mov     rdx, r14; unsigned __int16 *
0x180017700  lea     rcx, [rsp+2A8h+pBlock]; this
0x180017705  call    ?GetVersionInfo@CFileVersionInfo@XPerfCore@@QEAAJPEBGPEAVCFileMapping@2@@Z; XPerfCore::CFileVersionInfo::GetVersionInfo(ushort const *,XPerfCore::CFileMapping *)
0x18001770a  mov     edi, eax
0x18001770c  test    eax, eax
0x18001770e  jns     short loc_180017721
0x180017710  mov     rcx, [rsp+2A8h+pBlock]; void *
0x180017715  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001771a  mov     eax, edi
0x18001771c  jmp     loc_180017984
0x180017721  lea     r9, aFiledescriptio; "FileDescription"
0x180017728  lea     rdx, [rsp+2A8h+var_248]; unsigned __int16 *
0x18001772d  lea     rcx, [rsp+2A8h+pBlock]; this
0x180017732  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x180017737  lea     rdx, [rsp+2A8h+var_248]
0x18001773c  mov     rcx, rbx
0x18001773f  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x180017744  mov     rcx, rbx
0x180017747  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18001774c  lea     r9, aFileversion; "FileVersion"
0x180017753  lea     rdx, [rsp+2A8h+var_248]; unsigned __int16 *
0x180017758  lea     rcx, [rsp+2A8h+pBlock]; this
0x18001775d  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x180017762  lea     rdx, [rsp+2A8h+var_248]
0x180017767  mov     rcx, rbx
0x18001776a  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18001776f  mov     rcx, rbx
0x180017772  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x180017777  mov     [rsp+2A8h+lpBuffer], 0
0x180017780  mov     rdi, [rsp+2A8h+pBlock]
0x180017785  test    rdi, rdi
0x180017788  jnz     short loc_180017791
0x18001778a  mov     ebx, 8000FFFFh
0x18001778f  jmp     short loc_1800177CB
0x180017791  mov     [rsp+2A8h+puLen], 0
0x180017799  lea     r9, [rsp+2A8h+puLen]; puLen
0x18001779e  lea     r8, [rsp+2A8h+lpBuffer]; lplpBuffer
0x1800177a3  lea     rdx, asc_180029930; "\\"
0x1800177aa  mov     rcx, rdi; pBlock
0x1800177ad  call    cs:__imp_VerQueryValueW
0x1800177b3  test    eax, eax
0x1800177b5  jnz     short loc_1800177DA
0x1800177b7  mov     [rsp+2A8h+lpBuffer], 0
0x1800177c0  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800177c5  mov     ebx, eax
0x1800177c7  test    eax, eax
0x1800177c9  jns     short loc_1800177E1
0x1800177cb  mov     rcx, rdi; void *
0x1800177ce  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800177d3  mov     eax, ebx
0x1800177d5  jmp     loc_180017984
0x1800177da  cmp     [rsp+2A8h+puLen], 0Ch
0x1800177df  jnb     short loc_1800177F3
0x1800177e1  mov     rcx, rdi; void *
0x1800177e4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800177e9  mov     eax, 8000FFFFh
0x1800177ee  jmp     loc_180017984
0x1800177f3  mov     rdx, [rsp+2A8h+lpBuffer]
0x1800177f8  movzx   eax, word ptr [rdx+0Ch]
0x1800177fc  movzx   ecx, word ptr [rdx+0Eh]
0x180017800  movzx   r9d, word ptr [rdx+8]
0x180017805  movzx   r8d, word ptr [rdx+0Ah]
0x18001780a  mov     [rsp+2A8h+var_280], eax
0x18001780e  mov     [rsp+2A8h+var_288], ecx
0x180017812  lea     rdx, aUUUU; "%u.%u.%u.%u"
0x180017819  mov     rcx, rbx
0x18001781c  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180017821  mov     rcx, rbx
0x180017824  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x180017829  movzx   r8d, [rsp+2A8h+var_268]
0x18001782f  lea     rdx, aU; "%u"
0x180017836  mov     rcx, rbx
0x180017839  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18001783e  mov     rcx, rbx
0x180017841  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x180017846  lea     r9, aProductname; "ProductName"
0x18001784d  lea     rdx, [rsp+2A8h+var_248]; unsigned __int16 *
0x180017852  lea     rcx, [rsp+2A8h+pBlock]; this
0x180017857  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x18001785c  lea     rdx, [rsp+2A8h+var_248]
0x180017861  mov     rcx, rbx
0x180017864  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x180017869  mov     rcx, rbx
0x18001786c  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x180017871  lea     r9, aCompanyname; "CompanyName"
0x180017878  lea     rdx, [rsp+2A8h+var_248]; unsigned __int16 *
0x18001787d  lea     rcx, [rsp+2A8h+pBlock]; this
0x180017882  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x180017887  lea     rdx, [rsp+2A8h+var_248]
0x18001788c  mov     rcx, rbx
0x18001788f  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x180017894  mov     rcx, rbx
0x180017897  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18001789c  lea     r9, aProductversion; "ProductVersion"
0x1800178a3  lea     rdx, [rsp+2A8h+var_248]; unsigned __int16 *
0x1800178a8  lea     rcx, [rsp+2A8h+pBlock]; this
0x1800178ad  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x1800178b2  lea     rdx, [rsp+2A8h+var_248]
0x1800178b7  mov     rcx, rbx
0x1800178ba  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x1800178bf  mov     rcx, rbx
0x1800178c2  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x1800178c7  mov     qword ptr [rsp+2A8h+puLen], 0
0x1800178d0  lea     rdi, [rsi+128h]
0x1800178d7  mov     rcx, rdi; this
0x1800178da  call    ?IsLibraryAvailable@CAeDelayLoad@Performance@Windows@Microsoft@@QEAA_NXZ; Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable(void)
0x1800178df  test    al, al
0x1800178e1  jz      short loc_1800178FB
0x1800178e3  lea     r8, [rsp+2A8h+puLen]
0x1800178e8  mov     edx, 1
0x1800178ed  mov     rcx, r14
0x1800178f0  mov     rax, [rdi+10h]
0x1800178f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178f9  jmp     short loc_180017905
0x1800178fb  mov     ecx, 7Fh; unsigned int
0x180017900  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180017905  test    eax, eax
0x180017907  jns     short loc_180017912
0x180017909  xor     eax, eax
0x18001790b  mov     qword ptr [rsp+2A8h+puLen], rax
0x180017910  jmp     short loc_180017917
0x180017912  mov     rax, qword ptr [rsp+2A8h+puLen]
0x180017917  test    rax, rax
0x18001791a  jz      short loc_18001792C
0x18001791c  mov     rdx, [rax]
0x18001791f  test    rdx, rdx
0x180017922  jz      short loc_18001792C
0x180017924  mov     rcx, rbx
0x180017927  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18001792c  mov     rcx, rbx
0x18001792f  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x180017934  mov     rax, qword ptr [rsp+2A8h+puLen]
0x180017939  test    rax, rax
0x18001793c  jz      short loc_18001794F
0x18001793e  mov     rdx, [rax+8]
0x180017942  test    rdx, rdx
0x180017945  jz      short loc_18001794F
0x180017947  mov     rcx, rbx
0x18001794a  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18001794f  mov     rcx, rbx
0x180017952  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x180017957  mov     rdx, qword ptr [rsp+2A8h+puLen]; struct _FILE_INFO *
0x18001795c  test    rdx, rdx
0x18001795f  jz      short loc_180017972
0x180017961  mov     rcx, rdi; this
0x180017964  call    ?PicFreeFileInfo@CAeDelayLoad@Performance@Windows@Microsoft@@QEAAJPEAU_FILE_INFO@@@Z; Microsoft::Windows::Performance::CAeDelayLoad::PicFreeFileInfo(_FILE_INFO *)
0x180017969  mov     qword ptr [rsp+2A8h+puLen], 0
0x180017972  mov     rcx, [rsp+2A8h+pBlock]; void *
0x180017977  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001797c  xor     eax, eax
0x18001797e  jmp     short loc_180017984
0x180017980  mov     eax, [rsp+2A8h+puLen]
0x180017984  mov     rcx, [rsp+2A8h+var_38]
0x18001798c  xor     rcx, rsp; StackCookie
0x18001798f  call    __security_check_cookie
0x180017994  add     rsp, 288h
0x18001799b  pop     r14
0x18001799d  pop     rdi
0x18001799e  pop     rsi
0x18001799f  pop     rbx
0x1800179a0  retn
```
