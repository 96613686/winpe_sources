# CScriptHostContext::GetNamespaceChildren(ushort const *,ulong *,IUnknown * * *,ulong *,ushort * * *,int * *)

- ea: `0x18059cc10`
- end: `0x18059d216`
- name: `?GetNamespaceChildren@CScriptHostContext@@UEAAJPEBGPEAKPEAPEAPEAUIUnknown@@1PEAPEAPEAGPEAPEAH@Z`
- size: `1542`
- prototype: `__int64 __fastcall(CScriptHostContext *__hidden this, const unsigned __int16 *, unsigned int *, struct IUnknown ***, unsigned int *, unsigned __int16 ***, int **)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180401df0`
- `0x18059bf58`
- `0x18059bf84`
- `0x18059c024`
- `0x18059c398`
- `0x18059c5f0`
- `0x18059c774`
- `0x18059cc10`
- `0x18059dfb4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18059d0fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18059d0fa`
- `api-ms-win-ro-typeresolution-l1-1-0!RoResolveNamespace` at `0x18059cea0`
- `api-ms-win-ro-typeresolution-l1-1-0!RoResolveNamespace` at `0x18059cea0`

## pseudocode

```c
__int64 __fastcall CScriptHostContext::GetNamespaceChildren(
        CScriptHostContext *this,
        wchar_t *a2,
        unsigned int *a3,
        struct IUnknown ***a4,
        unsigned int *a5,
        unsigned __int16 ***a6,
        int **a7)
{
  unsigned int v8; // edi
  unsigned int *v9; // rbx
  struct IUnknown ***v10; // r15
  unsigned __int16 ***v11; // r13
  int **v12; // r14
  int v13; // eax
  unsigned int mm; // esi
  __int64 v15; // rbx
  unsigned int v16; // esi
  __int64 v17; // rbx
  int v18; // eax
  unsigned int kk; // esi
  __int64 v20; // rbx
  unsigned int v21; // esi
  __int64 v22; // rbx
  int v23; // eax
  unsigned int jj; // esi
  __int64 v25; // rbx
  unsigned int v26; // esi
  __int64 v27; // rbx
  int v28; // eax
  enum WinRTHostUtilities::WinRTType *v29; // r8
  unsigned int ii; // esi
  __int64 v31; // rbx
  unsigned int v32; // esi
  __int64 v33; // rbx
  int WinRTType; // eax
  unsigned int n; // esi
  __int64 v36; // rbx
  unsigned int v37; // esi
  __int64 v38; // rbx
  int *v39; // rax
  unsigned int m; // edi
  __int64 v41; // rbx
  unsigned int v42; // edi
  __int64 v43; // rbx
  unsigned int i; // r8d
  __int64 v45; // rcx
  unsigned int j; // esi
  __int64 v47; // rbx
  unsigned int v48; // esi
  __int64 v49; // rbx
  int v51; // [rsp+20h] [rbp-50h]
  int v52; // [rsp+20h] [rbp-50h]
  unsigned __int16 v53[4]; // [rsp+40h] [rbp-30h] BYREF
  HSTRING v54; // [rsp+48h] [rbp-28h] BYREF
  unsigned int v55; // [rsp+50h] [rbp-20h] BYREF
  HSTRING *v56; // [rsp+58h] [rbp-18h]
  unsigned int v57; // [rsp+60h] [rbp-10h]
  HSTRING *k; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  wchar_t *String1; // [rsp+B8h] [rbp+48h] BYREF
  unsigned int *v62; // [rsp+C0h] [rbp+50h]
  struct IUnknown ***v63; // [rsp+C8h] [rbp+58h]

  v63 = a4;
  v62 = a3;
  String1 = a2;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  k = 0;
  *(_DWORD *)v53 = 0;
  if ( a2 )
  {
    v9 = v62;
    if ( v62 && (v10 = v63) != 0 && a5 && (v11 = a6) != 0 && (v12 = a7) != 0 )
    {
      v13 = Windows::Internal::String::Initialize<unsigned short const *>(&v54, (__int64 *)&String1);
      v8 = v13;
      if ( v13 >= 0 )
      {
        v18 = RoResolveNamespace(v54, 0, 0, 0);
        v8 = v18;
        if ( v18 >= 0 )
        {
          v23 = CScriptHostContext::ConvertMetaDataFilePathsToMetaDataImports(this, v55, v56, v9, v10);
          v8 = v23;
          if ( v23 >= 0 )
          {
            v28 = CScriptHostContext::ConvertSubNamespacesAsHStringToCString(v57, k, a5, v11);
            v8 = v28;
            if ( v28 >= 0 )
            {
              WinRTType = WinRTHostUtilities::GetWinRTType(a2, v53, v29);
              v8 = WinRTType;
              if ( WinRTType >= 0 )
              {
                v39 = (int *)CoTaskMemAlloc(4LL * *v9);
                *v12 = v39;
                if ( v39 )
                {
                  for ( i = 0; i < *v9; (*v12)[v45] = *(_DWORD *)v53 == 1 )
                    v45 = i++;
                  for ( j = 0; j < v57; k[v47] = 0 )
                  {
                    v47 = j;
                    WindowsDeleteStringDeallocate<HSTRING__ *>(k[j++]);
                  }
                  CoTaskMemFreeDeallocate<unsigned short * *>(k);
                  v48 = 0;
                  for ( k = 0; v48 < v55; v56[v49] = 0 )
                  {
                    v49 = v48;
                    WindowsDeleteStringDeallocate<HSTRING__ *>(v56[v48++]);
                  }
                }
                else
                {
                  for ( m = 0; m < v57; k[v41] = 0 )
                  {
                    v41 = m;
                    WindowsDeleteStringDeallocate<HSTRING__ *>(k[m++]);
                  }
                  CoTaskMemFreeDeallocate<unsigned short * *>(k);
                  v42 = 0;
                  for ( k = 0; v42 < v55; v56[v43] = 0 )
                  {
                    v43 = v42;
                    WindowsDeleteStringDeallocate<HSTRING__ *>(v56[v42++]);
                  }
                  v8 = -2147024882;
                }
              }
              else
              {
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x20C,
                  (unsigned int)"onecoreuap\\inetcore\\lib\\scriptprojectionhost\\scripthostcontext.cxx",
                  (const char *)(unsigned int)WinRTType,
                  v52);
                for ( n = 0; n < v57; k[v36] = 0 )
                {
                  v36 = n;
                  WindowsDeleteStringDeallocate<HSTRING__ *>(k[n++]);
                }
                CoTaskMemFreeDeallocate<unsigned short * *>(k);
                v37 = 0;
                for ( k = 0; v37 < v55; v56[v38] = 0 )
                {
                  v38 = v37;
                  WindowsDeleteStringDeallocate<HSTRING__ *>(v56[v37++]);
                }
              }
            }
            else
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x20A,
                (unsigned int)"onecoreuap\\inetcore\\lib\\scriptprojectionhost\\scripthostcontext.cxx",
                (const char *)(unsigned int)v28,
                v52);
              for ( ii = 0; ii < v57; k[v31] = 0 )
              {
                v31 = ii;
                WindowsDeleteStringDeallocate<HSTRING__ *>(k[ii++]);
              }
              CoTaskMemFreeDeallocate<unsigned short * *>(k);
              v32 = 0;
              for ( k = 0; v32 < v55; v56[v33] = 0 )
              {
                v33 = v32;
                WindowsDeleteStringDeallocate<HSTRING__ *>(v56[v32++]);
              }
            }
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x204,
              (unsigned int)"onecoreuap\\inetcore\\lib\\scriptprojectionhost\\scripthostcontext.cxx",
              (const char *)(unsigned int)v23,
              v52);
            for ( jj = 0; jj < v57; k[v25] = 0 )
            {
              v25 = jj;
              WindowsDeleteStringDeallocate<HSTRING__ *>(k[jj++]);
            }
            CoTaskMemFreeDeallocate<unsigned short * *>(k);
            v26 = 0;
            for ( k = 0; v26 < v55; v56[v27] = 0 )
            {
              v27 = v26;
              WindowsDeleteStringDeallocate<HSTRING__ *>(v56[v26++]);
            }
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1FE,
            (unsigned int)"onecoreuap\\inetcore\\lib\\scriptprojectionhost\\scripthostcontext.cxx",
            (const char *)(unsigned int)v18,
            (int)&v55);
          for ( kk = 0; kk < v57; k[v20] = 0 )
          {
            v20 = kk;
            WindowsDeleteStringDeallocate<HSTRING__ *>(k[kk++]);
          }
          CoTaskMemFreeDeallocate<unsigned short * *>(k);
          v21 = 0;
          for ( k = 0; v21 < v55; v56[v22] = 0 )
          {
            v22 = v21;
            WindowsDeleteStringDeallocate<HSTRING__ *>(v56[v21++]);
          }
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1F4,
          (unsigned int)"onecoreuap\\inetcore\\lib\\scriptprojectionhost\\scripthostcontext.cxx",
          (const char *)(unsigned int)v13,
          v51);
        for ( mm = 0; mm < v57; k[v15] = 0 )
        {
          v15 = mm;
          WindowsDeleteStringDeallocate<HSTRING__ *>(k[mm++]);
        }
        CoTaskMemFreeDeallocate<unsigned short * *>(k);
        v16 = 0;
        for ( k = 0; v16 < v55; v56[v17] = 0 )
        {
          v17 = v16;
          WindowsDeleteStringDeallocate<HSTRING__ *>(v56[v16++]);
        }
      }
    }
    else
    {
      CoTaskMemFreeDeallocate<unsigned short * *>(0);
      k = 0;
      v8 = -2147467261;
    }
  }
  else
  {
    CoTaskMemFreeDeallocate<unsigned short * *>(0);
    k = 0;
    v8 = -2147024809;
  }
  CoTaskMemFreeDeallocate<unsigned short * *>(v56);
  v56 = 0;
  Windows::Internal::String::~String((Windows::Internal::String *)&v54);
  return v8;
}

```

## disassembly

```asm
0x18059cc10  mov     rax, rsp
0x18059cc13  mov     [rax+20h], r9
0x18059cc17  mov     [rax+18h], r8
0x18059cc1b  mov     [rax+10h], rdx
0x18059cc1f  mov     [rax+8], rcx
0x18059cc23  push    rbp
0x18059cc24  push    rbx
0x18059cc25  push    rsi
0x18059cc26  push    rdi
0x18059cc27  push    r13
0x18059cc29  push    r14
0x18059cc2b  push    r15
0x18059cc2d  mov     rbp, rsp
0x18059cc30  sub     rsp, 70h
0x18059cc34  mov     rsi, [rbp+String1]
0x18059cc38  xor     r13d, r13d
0x18059cc3b  mov     [rbp+var_28], r13
0x18059cc3f  mov     [rbp+var_20], r13d
0x18059cc43  mov     [rbp+var_18], r13
0x18059cc47  mov     [rbp+var_10], r13d
0x18059cc4b  mov     [rbp+var_8], r13
0x18059cc4f  mov     dword ptr [rbp+var_30], r13d
0x18059cc53  test    rsi, rsi
0x18059cc56  jnz     short loc_18059CC94
0x18059cc58  xor     ecx, ecx
0x18059cc5a  call    ??$CoTaskMemFreeDeallocate@PEAPEAG@@YAXPEAPEAG@Z; CoTaskMemFreeDeallocate<ushort * *>(ushort * *)
0x18059cc5f  mov     edi, r13d
0x18059cc62  mov     [rbp+var_8], r13
0x18059cc66  cmp     [rbp+var_20], r13d
0x18059cc6a  jbe     short loc_18059CC8A
0x18059cc6c  mov     rcx, [rbp+var_18]
0x18059cc70  mov     ebx, edi
0x18059cc72  mov     rcx, [rcx+rbx*8]
0x18059cc76  call    ??$WindowsDeleteStringDeallocate@PEAUHSTRING__@@@@YAXPEAUHSTRING__@@@Z; WindowsDeleteStringDeallocate<HSTRING__ *>(HSTRING__ *)
0x18059cc7b  mov     rax, [rbp+var_18]
0x18059cc7f  inc     edi
0x18059cc81  mov     [rax+rbx*8], r13
0x18059cc85  cmp     edi, [rbp+var_20]
0x18059cc88  jb      short loc_18059CC6C
0x18059cc8a  mov     edi, 80070057h
0x18059cc8f  jmp     loc_18059D1EE
0x18059cc94  mov     rbx, [rbp+arg_10]
0x18059cc98  test    rbx, rbx
0x18059cc9b  jnz     short loc_18059CCD9
0x18059cc9d  xor     ecx, ecx
0x18059cc9f  call    ??$CoTaskMemFreeDeallocate@PEAPEAG@@YAXPEAPEAG@Z; CoTaskMemFreeDeallocate<ushort * *>(ushort * *)
0x18059cca4  mov     edi, r13d
0x18059cca7  mov     [rbp+var_8], r13
0x18059ccab  cmp     [rbp+var_20], r13d
0x18059ccaf  jbe     short loc_18059CCCF
0x18059ccb1  mov     rcx, [rbp+var_18]
0x18059ccb5  mov     ebx, edi
0x18059ccb7  mov     rcx, [rcx+rbx*8]
0x18059ccbb  call    ??$WindowsDeleteStringDeallocate@PEAUHSTRING__@@@@YAXPEAUHSTRING__@@@Z; WindowsDeleteStringDeallocate<HSTRING__ *>(HSTRING__ *)
0x18059ccc0  mov     rax, [rbp+var_18]
0x18059ccc4  inc     edi
0x18059ccc6  mov     [rax+rbx*8], r13
0x18059ccca  cmp     edi, [rbp+var_20]
0x18059cccd  jb      short loc_18059CCB1
0x18059cccf  mov     edi, 80004003h
0x18059ccd4  jmp     loc_18059D1EE
0x18059ccd9  mov     r15, [rbp+arg_18]
0x18059ccdd  test    r15, r15
0x18059cce0  jnz     short loc_18059CD16
0x18059cce2  xor     ecx, ecx
0x18059cce4  call    ??$CoTaskMemFreeDeallocate@PEAPEAG@@YAXPEAPEAG@Z; CoTaskMemFreeDeallocate<ushort * *>(ushort * *)
0x18059cce9  mov     edi, r13d
0x18059ccec  mov     [rbp+var_8], r13
0x18059ccf0  cmp     [rbp+var_20], r13d
0x18059ccf4  jbe     short loc_18059CCCF
0x18059ccf6  mov     rcx, [rbp+var_18]
0x18059ccfa  mov     ebx, edi
0x18059ccfc  mov     rcx, [rcx+rbx*8]
0x18059cd00  call    ??$WindowsDeleteStringDeallocate@PEAUHSTRING__@@@@YAXPEAUHSTRING__@@@Z; WindowsDeleteStringDeallocate<HSTRING__ *>(HSTRING__ *)
0x18059cd05  mov     rax, [rbp+var_18]
0x18059cd09  inc     edi
0x18059cd0b  mov     [rax+rbx*8], r13
0x18059cd0f  cmp     edi, [rbp+var_20]
0x18059cd12  jb      short loc_18059CCF6
0x18059cd14  jmp     short loc_18059CCCF
0x18059cd16  cmp     [rbp+arg_20], r13
0x18059cd1a  jnz     short loc_18059CD53
0x18059cd1c  xor     ecx, ecx
0x18059cd1e  call    ??$CoTaskMemFreeDeallocate@PEAPEAG@@YAXPEAPEAG@Z; CoTaskMemFreeDeallocate<ushort * *>(ushort * *)
0x18059cd23  mov     edi, r13d
0x18059cd26  mov     [rbp+var_8], r13
0x18059cd2a  cmp     [rbp+var_20], r13d
0x18059cd2e  jbe     short loc_18059CCCF
0x18059cd30  mov     rcx, [rbp+var_18]
0x18059cd34  mov     ebx, edi
0x18059cd36  mov     rcx, [rcx+rbx*8]
0x18059cd3a  call    ??$WindowsDeleteStringDeallocate@PEAUHSTRING__@@@@YAXPEAUHSTRING__@@@Z; WindowsDeleteStringDeallocate<HSTRING__ *>(HSTRING__ *)
0x18059cd3f  mov     rax, [rbp+var_18]
0x18059cd43  inc     edi
0x18059cd45  mov     [rax+rbx*8], r13
0x18059cd49  cmp     edi, [rbp+var_20]
0x18059cd4c  jb      short loc_18059CD30
0x18059cd4e  jmp     loc_18059CCCF
0x18059cd53  mov     r13, [rbp+arg_28]
0x18059cd57  test    r13, r13
0x18059cd5a  jnz     short loc_18059CD97
0x18059cd5c  xor     ecx, ecx
0x18059cd5e  call    ??$CoTaskMemFreeDeallocate@PEAPEAG@@YAXPEAPEAG@Z; CoTaskMemFreeDeallocate<ushort * *>(ushort * *)
0x18059cd63  mov     edi, r13d
0x18059cd66  mov     [rbp+var_8], r13
0x18059cd6a  cmp     [rbp+var_20], r13d
0x18059cd6e  jbe     loc_18059CCCF
0x18059cd74  mov     rcx, [rbp+var_18]
0x18059cd78  mov     ebx, edi
0x18059cd7a  mov     rcx, [rcx+rbx*8]
0x18059cd7e  call    ??$WindowsDeleteStringDeallocate@PEAUHSTRING__@@@@YAXPEAUHSTRING__@@@Z; WindowsDeleteStringDeallocate<HSTRING__ *>(HSTRING__ *)
0x18059cd83  mov     rax, [rbp+var_18]
0x18059cd87  inc     edi
0x18059cd89  mov     [rax+rbx*8], r13
0x18059cd8d  cmp     edi, [rbp+var_20]
0x18059cd90  jb      short loc_18059CD74
0x18059cd92  jmp     loc_18059CCCF
0x18059cd97  mov     r14, [rbp+arg_30]
0x18059cd9b  test    r14, r14
0x18059cd9e  jnz     short loc_18059CDDE
0x18059cda0  xor     ecx, ecx
0x18059cda2  call    ??$CoTaskMemFreeDeallocate@PEAPEAG@@YAXPEAPEAG@Z; CoTaskMemFreeDeallocate<ushort * *>(ushort * *)
0x18059cda7  xor     r13d, r13d
0x18059cdaa  mov     edi, r13d
0x18059cdad  mov     [rbp+var_8], r13
0x18059cdb1  cmp     [rbp+var_20], r13d
0x18059cdb5  jbe     loc_18059CCCF
0x18059cdbb  mov     rcx, [rbp+var_18]
0x18059cdbf  mov     ebx, edi
0x18059cdc1  mov     rcx, [rcx+rbx*8]
0x18059cdc5  call    ??$WindowsDeleteStringDeallocate@PEAUHSTRING__@@@@YAXPEAUHSTRING__@@@Z; WindowsDeleteStringDeallocate<HSTRING__ *>(HSTRING__ *)
0x18059cdca  mov     rax, [rbp+var_18]
0x18059cdce  inc     edi
0x18059cdd0  mov     [rax+rbx*8], r13
0x18059cdd4  cmp     edi, [rbp+var_20]
0x18059cdd7  jb      short loc_18059CDBB
0x18059cdd9  jmp     loc_18059CCCF
0x18059cdde  lea     rdx, [rbp+String1]
0x18059cde2  lea     rcx, [rbp+var_28]
0x18059cde6  call    ??$Initialize@PEBG@String@Internal@Windows@@QEAAJAEBQEBGUdummy_t@_StringDetail@12@@Z; Windows::Internal::String::Initialize<ushort const *>(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)
0x18059cdeb  mov     edi, eax
0x18059cded  test    eax, eax
0x18059cdef  jns     short loc_18059CE70
0x18059cdf1  mov     rcx, [rbp+38h]; this
0x18059cdf5  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\lib\\scriptprojec"...
0x18059cdfc  mov     r9d, eax; char *
0x18059cdff  mov     edx, 1F4h; void *
0x18059ce04  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18059ce09  xor     r13d, r13d
0x18059ce0c  mov     esi, r13d
0x18059ce0f  cmp     [rbp+var_10], r13d
0x18059ce13  jbe     short loc_18059CE33
0x18059ce15  mov     rcx, [rbp+var_8]
0x18059ce19  mov     ebx, esi
0x18059ce1b  mov     rcx, [rcx+rbx*8]
0x18059ce1f  call    ??$WindowsDeleteStringDeallocate@PEAUHSTRING__@@@@YAXPEAUHSTRING__@@@Z; WindowsDeleteStringDeallocate<HSTRING__ *>(HSTRING__ *)
0x18059ce24  mov     rax, [rbp+var_8]
0x18059ce28  inc     esi
0x18059ce2a  mov     [rax+rbx*8], r13
0x18059ce2e  cmp     esi, [rbp+var_10]
0x18059ce31  jb      short loc_18059CE15
0x18059ce33  mov     rcx, [rbp+var_8]
0x18059ce37  call    ??$CoTaskMemFreeDeallocate@PEAPEAG@@YAXPEAPEAG@Z; CoTaskMemFreeDeallocate<ushort * *>(ushort * *)
0x18059ce3c  mov     esi, r13d
0x18059ce3f  mov     [rbp+var_8], r13
0x18059ce43  cmp     [rbp+var_20], r13d
0x18059ce47  jbe     loc_18059D1EE
0x18059ce4d  mov     rcx, [rbp+var_18]
0x18059ce51  mov     ebx, esi
0x18059ce53  mov     rcx, [rcx+rbx*8]
0x18059ce57  call    ??$WindowsDeleteStringDeallocate@PEAUHSTRING__@@@@YAXPEAUHSTRING__@@@Z; WindowsDeleteStringDeallocate<HSTRING__ *>(HSTRING__ *)
0x18059ce5c  mov     rax, [rbp+var_18]
0x18059ce60  inc     esi
0x18059ce62  mov     [rax+rbx*8], r13
0x18059ce66  cmp     esi, [rbp+var_20]
0x18059ce69  jb      short loc_18059CE4D
0x18059ce6b  jmp     loc_18059D1EE
0x18059ce70  mov     rcx, [rbp+var_28]
0x18059ce74  lea     rax, [rbp+var_8]
0x18059ce78  mov     [rsp+70h+var_38], rax
0x18059ce7d  xor     r9d, r9d
0x18059ce80  lea     rax, [rbp+var_10]
0x18059ce84  xor     r8d, r8d
0x18059ce87  mov     [rsp+70h+var_40], rax
0x18059ce8c  xor     edx, edx
0x18059ce8e  lea     rax, [rbp+var_18]
0x18059ce92  mov     [rsp+70h+var_48], rax
0x18059ce97  lea     rax, [rbp+var_20]
0x18059ce9b  mov     [rsp+70h+var_50], rax; int
0x18059cea0  call    cs:__imp_RoResolveNamespace
0x18059cea7  nop     dword ptr [rax+rax+00h]
0x18059ceac  mov     edi, eax
0x18059ceae  test    eax, eax
0x18059ceb0  jns     short loc_18059CF31
0x18059ceb2  mov     rcx, [rbp+38h]; this
0x18059ceb6  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\lib\\scriptprojec"...
0x18059cebd  mov     r9d, eax; char *
0x18059cec0  mov     edx, 1FEh; void *
0x18059cec5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18059ceca  xor     r13d, r13d
0x18059cecd  mov     esi, r13d
0x18059ced0  cmp     [rbp+var_10], r13d
0x18059ced4  jbe     short loc_18059CEF4
0x18059ced6  mov     rcx, [rbp+var_8]
0x18059ceda  mov     ebx, esi
0x18059cedc  mov     rcx, [rcx+rbx*8]
0x18059cee0  call    ??$WindowsDeleteStringDeallocate@PEAUHSTRING__@@@@YAXPEAUHSTRING__@@@Z; WindowsDeleteStringDeallocate<HSTRING__ *>(HSTRING__ *)
0x18059cee5  mov     rax, [rbp+var_8]
0x18059cee9  inc     esi
0x18059ceeb  mov     [rax+rbx*8], r13
0x18059ceef  cmp     esi, [rbp+var_10]
0x18059cef2  jb      short loc_18059CED6
0x18059cef4  mov     rcx, [rbp+var_8]
0x18059cef8  call    ??$CoTaskMemFreeDeallocate@PEAPEAG@@YAXPEAPEAG@Z; CoTaskMemFreeDeallocate<ushort * *>(ushort * *)
0x18059cefd  mov     esi, r13d
0x18059cf00  mov     [rbp+var_8], r13
0x18059cf04  cmp     [rbp+var_20], r13d
0x18059cf08  jbe     loc_18059D1EE
0x18059cf0e  mov     rcx, [rbp+var_18]
0x18059cf12  mov     ebx, esi
0x18059cf14  mov     rcx, [rcx+rbx*8]
0x18059cf18  call    ??$WindowsDeleteStringDeallocate@PEAUHSTRING__@@@@YAXPEAUHSTRING__@@@Z; WindowsDeleteStringDeallocate<HSTRING__ *>(HSTRING__ *)
0x18059cf1d  mov     rax, [rbp+var_18]
0x18059cf21  inc     esi
0x18059cf23  mov     [rax+rbx*8], r13
0x18059cf27  cmp     esi, [rbp+var_20]
0x18059cf2a  jb      short loc_18059CF0E
0x18059cf2c  jmp     loc_18059D1EE
0x18059cf31  mov     r8, [rbp+var_18]; HSTRING *
0x18059cf35  mov     r9, rbx; unsigned int *
0x18059cf38  mov     edx, [rbp+var_20]; unsigned int
0x18059cf3b  mov     rcx, [rbp+arg_0]; this
0x18059cf3f  mov     [rsp+70h+var_50], r15; int
0x18059cf44  call    ?ConvertMetaDataFilePathsToMetaDataImports@CScriptHostContext@@AEAAJKPEBQEAUHSTRING__@@PEAKPEAPEAPEAUIUnknown@@@Z; CScriptHostContext::ConvertMetaDataFilePathsToMetaDataImports(ulong,HSTRING__ * const *,ulong *,IUnknown * * *)
0x18059cf49  mov     edi, eax
0x18059cf4b  test    eax, eax
0x18059cf4d  jns     short loc_18059CFCE
0x18059cf4f  mov     rcx, [rbp+38h]; this
0x18059cf53  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\lib\\scriptprojec"...
0x18059cf5a  mov     r9d, eax; char *
0x18059cf5d  mov     edx, 204h; void *
0x18059cf62  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18059cf67  xor     r13d, r13d
0x18059cf6a  mov     esi, r13d
0x18059cf6d  cmp     [rbp+var_10], r13d
0x18059cf71  jbe     short loc_18059CF91
0x18059cf73  mov     rcx, [rbp+var_8]
0x18059cf77  mov     ebx, esi
0x18059cf79  mov     rcx, [rcx+rbx*8]
0x18059cf7d  call    ??$WindowsDeleteStringDeallocate@PEAUHSTRING__@@@@YAXPEAUHSTRING__@@@Z; WindowsDeleteStringDeallocate<HSTRING__ *>(HSTRING__ *)
0x18059cf82  mov     rax, [rbp+var_8]
0x18059cf86  inc     esi
0x18059cf88  mov     [rax+rbx*8], r13
0x18059cf8c  cmp     esi, [rbp+var_10]
0x18059cf8f  jb      short loc_18059CF73
0x18059cf91  mov     rcx, [rbp+var_8]
0x18059cf95  call    ??$CoTaskMemFreeDeallocate@PEAPEAG@@YAXPEAPEAG@Z; CoTaskMemFreeDeallocate<ushort * *>(ushort * *)
0x18059cf9a  mov     esi, r13d
0x18059cf9d  mov     [rbp+var_8], r13
0x18059cfa1  cmp     [rbp+var_20], r13d
0x18059cfa5  jbe     loc_18059D1EE
0x18059cfab  mov     rcx, [rbp+var_18]
0x18059cfaf  mov     ebx, esi
0x18059cfb1  mov     rcx, [rcx+rbx*8]
0x18059cfb5  call    ??$WindowsDeleteStringDeallocate@PEAUHSTRING__@@@@YAXPEAUHSTRING__@@@Z; WindowsDeleteStringDeallocate<HSTRING__ *>(HSTRING__ *)
0x18059cfba  mov     rax, [rbp+var_18]
0x18059cfbe  inc     esi
0x18059cfc0  mov     [rax+rbx*8], r13
0x18059cfc4  cmp     esi, [rbp+var_20]
0x18059cfc7  jb      short loc_18059CFAB
0x18059cfc9  jmp     loc_18059D1EE
0x18059cfce  mov     r8, [rbp+arg_20]; unsigned int *
0x18059cfd2  mov     r9, r13; unsigned __int16 ***
0x18059cfd5  mov     rdx, [rbp+var_8]; HSTRING *
0x18059cfd9  mov     ecx, [rbp+var_10]; unsigned int
0x18059cfdc  call    ?ConvertSubNamespacesAsHStringToCString@CScriptHostContext@@CAJKPEBQEAUHSTRING__@@PEAKPEAPEAPEAG@Z; CScriptHostContext::ConvertSubNamespacesAsHStringToCString(ulong,HSTRING__ * const *,ulong *,ushort * * *)
0x18059cfe1  xor     r13d, r13d
0x18059cfe4  mov     edi, eax
0x18059cfe6  test    eax, eax
0x18059cfe8  jns     short loc_18059D066
0x18059cfea  mov     rcx, [rbp+38h]; this
0x18059cfee  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\lib\\scriptprojec"...
0x18059cff5  mov     r9d, eax; char *
0x18059cff8  mov     edx, 20Ah; void *
0x18059cffd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18059d002  mov     esi, r13d
0x18059d005  cmp     [rbp+var_10], r13d
0x18059d009  jbe     short loc_18059D029
0x18059d00b  mov     rcx, [rbp+var_8]
0x18059d00f  mov     ebx, esi
0x18059d011  mov     rcx, [rcx+rbx*8]
0x18059d015  call    ??$WindowsDeleteStringDeallocate@PEAUHSTRING__@@@@YAXPEAUHSTRING__@@@Z; WindowsDeleteStringDeallocate<HSTRING__ *>(HSTRING__ *)
0x18059d01a  mov     rax, [rbp+var_8]
0x18059d01e  inc     esi
0x18059d020  mov     [rax+rbx*8], r13
0x18059d024  cmp     esi, [rbp+var_10]
0x18059d027  jb      short loc_18059D00B
0x18059d029  mov     rcx, [rbp+var_8]
0x18059d02d  call    ??$CoTaskMemFreeDeallocate@PEAPEAG@@YAXPEAPEAG@Z; CoTaskMemFreeDeallocate<ushort * *>(ushort * *)
0x18059d032  mov     esi, r13d
  ... truncated ...
```
