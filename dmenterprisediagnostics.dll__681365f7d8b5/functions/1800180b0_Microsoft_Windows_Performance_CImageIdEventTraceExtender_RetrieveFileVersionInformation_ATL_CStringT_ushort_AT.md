# Microsoft::Windows::Performance::CImageIdEventTraceExtender::RetrieveFileVersionInformation(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,XPerfCore::CFileMapping *)

- ea: `0x1800180b0`
- end: `0x1800183a8`
- name: `?RetrieveFileVersionInformation@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEAVCFileMapping@XPerfCore@@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800127c4`

## callees

- `0x180001800`
- `0x180001824`
- `0x180009d08`
- `0x180009e70`
- `0x180009e98`
- `0x1800142d0`
- `0x180014380`
- `0x180015290`
- `0x1800153a8`
- `0x180015bc0`
- `0x180017d64`
- `0x1800180b0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800181ad`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800181ad`

## string_xrefs

- `0x180018277`: `CompanyName`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::RetrieveFileVersionInformation(
        __int64 (__fastcall **a1)(_QWORD, _QWORD, _QWORD),
        unsigned __int64 a2,
        const unsigned __int16 *a3,
        struct XPerfCore::CFileMapping *a4)
{
  unsigned __int64 v8; // rdx
  void *v9; // rcx
  int VersionInfo; // edi
  unsigned __int64 v11; // r8
  __int64 result; // rax
  unsigned __int64 v13; // r8
  unsigned __int64 v14; // rdx
  void *v15; // rdi
  int Error; // ebx
  unsigned __int64 v17; // r8
  unsigned __int64 v18; // r8
  unsigned __int64 v19; // r8
  int v20; // eax
  _QWORD *v21; // rax
  __int64 v22; // rdx
  unsigned __int64 v23; // rdx
  unsigned int puLen[2]; // [rsp+30h] [rbp-278h] BYREF
  LPCVOID pBlock; // [rsp+38h] [rbp-270h] BYREF
  unsigned __int16 v26; // [rsp+40h] [rbp-268h]
  LPVOID lpBuffer[2]; // [rsp+48h] [rbp-260h] BYREF
  ATL::CAtlException *v28; // [rsp+58h] [rbp-250h] BYREF
  unsigned __int16 v29[264]; // [rsp+60h] [rbp-248h] BYREF

  lpBuffer[1] = a1;
  operator delete(0, a2);
  v9 = 0;
  pBlock = 0;
  if ( !a4 )
  {
    VersionInfo = -2147467261;
LABEL_5:
    operator delete(v9, v8);
    return (unsigned int)VersionInfo;
  }
  VersionInfo = XPerfCore::CFileVersionInfo::GetVersionInfo((XPerfCore::CFileVersionInfo *)&pBlock, a3, a4);
  if ( VersionInfo < 0 )
  {
    v9 = (void *)pBlock;
    goto LABEL_5;
  }
  XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v29, v11, L"FileDescription");
  try
  {
    ATL::CSimpleStringT<unsigned short,0>::Append(a2, v29);
    ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
    XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v29, v13, L"FileVersion");
    ATL::CSimpleStringT<unsigned short,0>::Append(a2, v29);
    ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
    lpBuffer[0] = 0;
    v15 = (void *)pBlock;
    if ( !pBlock )
    {
      Error = -2147418113;
LABEL_11:
      operator delete(v15, v14);
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
          v26);
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
        XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v29, v17, L"ProductName");
        ATL::CSimpleStringT<unsigned short,0>::Append(a2, v29);
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
        XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v29, v18, L"CompanyName");
        ATL::CSimpleStringT<unsigned short,0>::Append(a2, v29);
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
        XPerfCore::CFileVersionInfo::GetValue((XPerfCore::CFileVersionInfo *)&pBlock, v29, v19, L"ProductVersion");
        ATL::CSimpleStringT<unsigned short,0>::Append(a2, v29);
        ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
        *(_QWORD *)puLen = 0;
        try
        {
          if ( Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable((Microsoft::Windows::Performance::CAeDelayLoad *)(a1 + 37)) )
            v20 = ((__int64 (__fastcall **)(const unsigned __int16 *, __int64, unsigned int *))a1)[39](a3, 1, puLen);
          else
            v20 = ATL::AtlHresultFromWin32(0x7Fu);
          if ( v20 >= 0 )
          {
            v21 = *(_QWORD **)puLen;
          }
          else
          {
            v21 = 0;
            *(_QWORD *)puLen = 0;
          }
          if ( v21 && *v21 )
            ATL::CSimpleStringT<unsigned short,0>::Append(a2, *v21);
          ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
          if ( *(_QWORD *)puLen )
          {
            v22 = *(_QWORD *)(*(_QWORD *)puLen + 8LL);
            if ( v22 )
              ATL::CSimpleStringT<unsigned short,0>::Append(a2, v22);
          }
          ATL::CSimpleStringT<unsigned short,0>::AppendChar(a2);
          v23 = *(_QWORD *)puLen;
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
        operator delete((void *)pBlock, v23);
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
    operator delete(v15, v14);
    result = 2147549183LL;
  }
  catch ( ATL::CAtlException *v28 )
  {
    return *(unsigned int *)v28;
  }
  return result;
}

```

## disassembly

```asm
0x1800180b0  push    rbx
0x1800180b2  push    rsi
0x1800180b3  push    rdi
0x1800180b4  push    r14
0x1800180b6  sub     rsp, 288h
0x1800180bd  mov     rax, cs:__security_cookie
0x1800180c4  xor     rax, rsp
0x1800180c7  mov     [rsp+2A8h+var_38], rax
0x1800180cf  mov     rdi, r9
0x1800180d2  mov     r14, r8
0x1800180d5  mov     rbx, rdx
0x1800180d8  mov     rsi, rcx
0x1800180db  mov     [rsp+2A8h+var_258], rcx
0x1800180e0  xor     ecx, ecx; void *
0x1800180e2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800180e7  xor     ecx, ecx
0x1800180e9  mov     [rsp+2A8h+pBlock], rcx
0x1800180ee  test    rdi, rdi
0x1800180f1  jnz     short loc_1800180FA
0x1800180f3  mov     edi, 80004003h
0x1800180f8  jmp     short loc_180018115
0x1800180fa  mov     r8, rdi; struct XPerfCore::CFileMapping *
0x1800180fd  mov     rdx, r14; unsigned __int16 *
0x180018100  lea     rcx, [rsp+2A8h+pBlock]; this
0x180018105  call    ?GetVersionInfo@CFileVersionInfo@XPerfCore@@QEAAJPEBGPEAVCFileMapping@2@@Z; XPerfCore::CFileVersionInfo::GetVersionInfo(ushort const *,XPerfCore::CFileMapping *)
0x18001810a  mov     edi, eax
0x18001810c  test    eax, eax
0x18001810e  jns     short loc_180018121
0x180018110  mov     rcx, [rsp+2A8h+pBlock]; void *
0x180018115  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001811a  mov     eax, edi
0x18001811c  jmp     loc_18001838A
0x180018121  lea     r9, aFiledescriptio; "FileDescription"
0x180018128  lea     rdx, [rsp+2A8h+var_248]; unsigned __int16 *
0x18001812d  lea     rcx, [rsp+2A8h+pBlock]; this
0x180018132  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x180018137  lea     rdx, [rsp+2A8h+var_248]
0x18001813c  mov     rcx, rbx
0x18001813f  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x180018144  mov     rcx, rbx
0x180018147  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18001814c  lea     r9, aFileversion; "FileVersion"
0x180018153  lea     rdx, [rsp+2A8h+var_248]; unsigned __int16 *
0x180018158  lea     rcx, [rsp+2A8h+pBlock]; this
0x18001815d  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x180018162  lea     rdx, [rsp+2A8h+var_248]
0x180018167  mov     rcx, rbx
0x18001816a  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18001816f  mov     rcx, rbx
0x180018172  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x180018177  mov     [rsp+2A8h+lpBuffer], 0
0x180018180  mov     rdi, [rsp+2A8h+pBlock]
0x180018185  test    rdi, rdi
0x180018188  jnz     short loc_180018191
0x18001818a  mov     ebx, 8000FFFFh
0x18001818f  jmp     short loc_1800181D1
0x180018191  mov     [rsp+2A8h+puLen], 0
0x180018199  lea     r9, [rsp+2A8h+puLen]; puLen
0x18001819e  lea     r8, [rsp+2A8h+lpBuffer]; lplpBuffer
0x1800181a3  lea     rdx, asc_18002A930; "\\"
0x1800181aa  mov     rcx, rdi; pBlock
0x1800181ad  call    cs:__imp_VerQueryValueW
0x1800181b4  nop     dword ptr [rax+rax+00h]
0x1800181b9  test    eax, eax
0x1800181bb  jnz     short loc_1800181E0
0x1800181bd  mov     [rsp+2A8h+lpBuffer], 0
0x1800181c6  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800181cb  mov     ebx, eax
0x1800181cd  test    eax, eax
0x1800181cf  jns     short loc_1800181E7
0x1800181d1  mov     rcx, rdi; void *
0x1800181d4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800181d9  mov     eax, ebx
0x1800181db  jmp     loc_18001838A
0x1800181e0  cmp     [rsp+2A8h+puLen], 0Ch
0x1800181e5  jnb     short loc_1800181F9
0x1800181e7  mov     rcx, rdi; void *
0x1800181ea  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800181ef  mov     eax, 8000FFFFh
0x1800181f4  jmp     loc_18001838A
0x1800181f9  mov     rdx, [rsp+2A8h+lpBuffer]
0x1800181fe  movzx   eax, word ptr [rdx+0Ch]
0x180018202  movzx   ecx, word ptr [rdx+0Eh]
0x180018206  movzx   r9d, word ptr [rdx+8]
0x18001820b  movzx   r8d, word ptr [rdx+0Ah]
0x180018210  mov     [rsp+2A8h+var_280], eax
0x180018214  mov     [rsp+2A8h+var_288], ecx
0x180018218  lea     rdx, aUUUU; "%u.%u.%u.%u"
0x18001821f  mov     rcx, rbx
0x180018222  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180018227  mov     rcx, rbx
0x18001822a  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18001822f  movzx   r8d, [rsp+2A8h+var_268]
0x180018235  lea     rdx, aU; "%u"
0x18001823c  mov     rcx, rbx
0x18001823f  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180018244  mov     rcx, rbx
0x180018247  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18001824c  lea     r9, aProductname; "ProductName"
0x180018253  lea     rdx, [rsp+2A8h+var_248]; unsigned __int16 *
0x180018258  lea     rcx, [rsp+2A8h+pBlock]; this
0x18001825d  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x180018262  lea     rdx, [rsp+2A8h+var_248]
0x180018267  mov     rcx, rbx
0x18001826a  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18001826f  mov     rcx, rbx
0x180018272  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x180018277  lea     r9, aCompanyname; "CompanyName"
0x18001827e  lea     rdx, [rsp+2A8h+var_248]; unsigned __int16 *
0x180018283  lea     rcx, [rsp+2A8h+pBlock]; this
0x180018288  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x18001828d  lea     rdx, [rsp+2A8h+var_248]
0x180018292  mov     rcx, rbx
0x180018295  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18001829a  mov     rcx, rbx
0x18001829d  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x1800182a2  lea     r9, aProductversion; "ProductVersion"
0x1800182a9  lea     rdx, [rsp+2A8h+var_248]; unsigned __int16 *
0x1800182ae  lea     rcx, [rsp+2A8h+pBlock]; this
0x1800182b3  call    ?GetValue@CFileVersionInfo@XPerfCore@@QEAAJPEAG_KPEBG@Z; XPerfCore::CFileVersionInfo::GetValue(ushort *,unsigned __int64,ushort const *)
0x1800182b8  lea     rdx, [rsp+2A8h+var_248]
0x1800182bd  mov     rcx, rbx
0x1800182c0  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x1800182c5  mov     rcx, rbx
0x1800182c8  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x1800182cd  mov     qword ptr [rsp+2A8h+puLen], 0
0x1800182d6  lea     rdi, [rsi+128h]
0x1800182dd  mov     rcx, rdi; this
0x1800182e0  call    ?IsLibraryAvailable@CAeDelayLoad@Performance@Windows@Microsoft@@QEAA_NXZ; Microsoft::Windows::Performance::CAeDelayLoad::IsLibraryAvailable(void)
0x1800182e5  test    al, al
0x1800182e7  jz      short loc_180018301
0x1800182e9  lea     r8, [rsp+2A8h+puLen]
0x1800182ee  mov     edx, 1
0x1800182f3  mov     rcx, r14
0x1800182f6  mov     rax, [rdi+10h]
0x1800182fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182ff  jmp     short loc_18001830B
0x180018301  mov     ecx, 7Fh; unsigned int
0x180018306  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18001830b  test    eax, eax
0x18001830d  jns     short loc_180018318
0x18001830f  xor     eax, eax
0x180018311  mov     qword ptr [rsp+2A8h+puLen], rax
0x180018316  jmp     short loc_18001831D
0x180018318  mov     rax, qword ptr [rsp+2A8h+puLen]
0x18001831d  test    rax, rax
0x180018320  jz      short loc_180018332
0x180018322  mov     rdx, [rax]
0x180018325  test    rdx, rdx
0x180018328  jz      short loc_180018332
0x18001832a  mov     rcx, rbx
0x18001832d  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x180018332  mov     rcx, rbx
0x180018335  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18001833a  mov     rax, qword ptr [rsp+2A8h+puLen]
0x18001833f  test    rax, rax
0x180018342  jz      short loc_180018355
0x180018344  mov     rdx, [rax+8]
0x180018348  test    rdx, rdx
0x18001834b  jz      short loc_180018355
0x18001834d  mov     rcx, rbx
0x180018350  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x180018355  mov     rcx, rbx
0x180018358  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18001835d  mov     rdx, qword ptr [rsp+2A8h+puLen]; struct _FILE_INFO *
0x180018362  test    rdx, rdx
0x180018365  jz      short loc_180018378
0x180018367  mov     rcx, rdi; this
0x18001836a  call    ?PicFreeFileInfo@CAeDelayLoad@Performance@Windows@Microsoft@@QEAAJPEAU_FILE_INFO@@@Z; Microsoft::Windows::Performance::CAeDelayLoad::PicFreeFileInfo(_FILE_INFO *)
0x18001836f  mov     qword ptr [rsp+2A8h+puLen], 0
0x180018378  mov     rcx, [rsp+2A8h+pBlock]; void *
0x18001837d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018382  xor     eax, eax
0x180018384  jmp     short loc_18001838A
0x180018386  mov     eax, [rsp+2A8h+puLen]
0x18001838a  mov     rcx, [rsp+2A8h+var_38]
0x180018392  xor     rcx, rsp; StackCookie
0x180018395  call    __security_check_cookie
0x18001839a  add     rsp, 288h
0x1800183a1  pop     r14
0x1800183a3  pop     rdi
0x1800183a4  pop     rsi
0x1800183a5  pop     rbx
0x1800183a6  retn
```
