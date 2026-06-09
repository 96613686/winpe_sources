# NdfCreateIncident

- ea: `0x18000a9e0`
- end: `0x18000acdb`
- name: `NdfCreateIncident`
- size: `763`
- prototype: `HRESULT __stdcall(LPCWSTR helperClassName, ULONG celt, HELPER_ATTRIBUTE *attributes, NDFHANDLE *handle)`
- caller_count: `12`
- callee_count: `15`
- tags: `file_ops, service_task`

## callers

- `0x18000a200`
- `0x18000a310`
- `0x18000a470`
- `0x18000a730`
- `0x18000acf0`
- `0x18000adc0`
- `0x18000afb0`
- `0x18000b0e0`
- `0x18000b240`
- `0x18000b3c0`
- `0x180010054`
- `0x180011e20`

## callees

- `0x18000264c`
- `0x18000721c`
- `0x180007f1c`
- `0x180008304`
- `0x180008580`
- `0x1800087f8`
- `0x1800089b4`
- `0x180008a60`
- `0x1800098b0`
- `0x18000a9e0`
- `0x18000c0a0`
- `0x18000f800`
- `0x18001f652`
- `0x18001f65e`
- `0x18001f690`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000aca5`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000aca5`
- `KERNEL32!GetModuleFileNameW` at `0x18000ab55`
- `KERNEL32!GetModuleFileNameW` at `0x18000ab55`
- `ole32!CoTaskMemAlloc` at `0x18000abb5`
- `ole32!CoTaskMemAlloc` at `0x18000abb5`
- `ole32!CoTaskMemFree` at `0x18000ac36`
- `ole32!CoTaskMemFree` at `0x18000ac64`
- `ole32!CoTaskMemFree` at `0x18000ac87`
- `ole32!CoTaskMemFree` at `0x18000ac36`
- `ole32!CoTaskMemFree` at `0x18000ac64`
- `ole32!CoTaskMemFree` at `0x18000ac87`
- `wdi!WdiCancel` at `0x18000aa59`
- `wdi!WdiCancel` at `0x18000aa59`

## string_xrefs

- `0x18000aa39`: `NdfCreateIncident`

## pseudocode

```c
HRESULT __stdcall NdfCreateIncident(
        LPCWSTR helperClassName,
        ULONG celt,
        HELPER_ATTRIBUTE *attributes,
        NDFHANDLE *handle)
{
  CNetDiagClient *v9; // rax
  CNetDiagClient *v10; // rdi
  ULONG v11; // r12d
  const wchar_t ***i; // rbx
  SIZE_T v13; // rbx
  struct tagHELPER_ATTRIBUTE *v14; // rax
  struct tagHELPER_ATTRIBUTE *v15; // r14
  unsigned int v16; // ebx
  const struct tagHELPER_ATTRIBUTE **v17; // rsi
  struct tagHELPER_ATTRIBUTE **v18; // rsi
  struct tagHELPER_ATTRIBUTE *v19; // rcx
  struct tagHELPER_ATTRIBUTE **v20; // rbx
  HRESULT v21; // ebx
  void *v22; // rcx
  void *v23; // rcx
  LPVOID pv[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v25; // [rsp+30h] [rbp-D0h]
  __int64 v26; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v27; // [rsp+40h] [rbp-C0h]
  NDFHANDLE *v28; // [rsp+48h] [rbp-B8h]
  struct tagHELPER_ATTRIBUTE v29; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Filename[3]; // [rsp+E0h] [rbp-20h] BYREF
  char v31; // [rsp+E6h] [rbp-1Ah] BYREF

  v27 = (unsigned __int16 *)helperClassName;
  v28 = handle;
  v26 = 15;
  v25 = 0;
  LOBYTE(pv[0]) = 0;
  std::string::assign((size_t *)pv, "NdfCreateIncident", 0x11u);
  TelemeterAPICall(pv);
  if ( (unsigned int)WdiCancel(0) == -2147023611 )
    return -2147467260;
  if ( !helperClassName )
    return -2146895615;
  if ( celt )
  {
    if ( !attributes )
      return -2146895611;
  }
  else if ( attributes )
  {
    return -2146895611;
  }
  if ( !handle )
    return -2146895611;
  v9 = (CNetDiagClient *)operator new(0xCD8u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v9 )
    return -2147024882;
  v10 = CNetDiagClient::CNetDiagClient(v9);
  if ( !v10 )
    return -2147024882;
  LODWORD(v25) = 0;
  v11 = celt;
  *(_OWORD *)pv = 0;
  if ( (int)HelperAttributeList::Add((struct tagHELPER_ATTRIBUTE ***)pv, attributes, celt) >= 0 )
  {
    for ( i = (const wchar_t ***)pv[0]; i; i = (const wchar_t ***)i[1] )
    {
      if ( !wcscmp_0(**i, L"NDFSQMCallerApplication") )
        goto LABEL_26;
    }
    memset_0(Filename, 0, 0x208u);
    if ( GetModuleFileNameW(0, Filename, 0x104u) )
    {
      memset_0(&v29, 0, sizeof(v29));
      v29.pwszName = (LPWSTR)L"NDFSQMCallerApplication";
      v29.Int64 = (LONGLONG)&v31;
      v29.type = AT_STRING;
      if ( (int)HelperAttributeList::Add((struct tagHELPER_ATTRIBUTE ***)pv, &v29, 1u) >= 0 )
      {
        if ( (_DWORD)v25 )
        {
          v13 = 144LL * (unsigned int)v25;
          v14 = (struct tagHELPER_ATTRIBUTE *)CoTaskMemAlloc(v13);
          v15 = v14;
          if ( v14 )
          {
            memset_0(v14, 0, v13);
            v16 = 0;
            v17 = (const struct tagHELPER_ATTRIBUTE **)pv[0];
            while ( 1 )
            {
              if ( !v17 )
              {
                attributes = v15;
                v11 = v16;
                goto LABEL_26;
              }
              if ( (int)CopyHelperAttribute(&v15[v16], *v17) < 0 )
                break;
              v17 = (const struct tagHELPER_ATTRIBUTE **)v17[1];
              ++v16;
            }
            FreeHelperAttributes(v15, v16, 1);
          }
        }
      }
    }
  }
LABEL_26:
  v18 = (struct tagHELPER_ATTRIBUTE **)pv[0];
  while ( v18 )
  {
    v19 = *v18;
    v20 = v18;
    v18 = (struct tagHELPER_ATTRIBUTE **)v18[1];
    FreeHelperAttributes(v19, 1u, 1);
    CoTaskMemFree(v20);
  }
  if ( v11 )
  {
    v21 = _attributes_array_t::Copy((CNetDiagClient *)((char *)v10 + 32), v11, attributes);
    if ( v21 < 0 )
      goto LABEL_35;
  }
  v22 = (void *)*((_QWORD *)v10 + 3);
  if ( v22 )
    CoTaskMemFree(v22);
  v21 = StringCopyWithAlloc((unsigned __int16 **)v10 + 3, v27);
  if ( v21 < 0 )
  {
LABEL_35:
    v23 = (void *)*((_QWORD *)v10 + 3);
    if ( v23 )
      CoTaskMemFree(v23);
    _attributes_array_t::FreeAll((CNetDiagClient *)((char *)v10 + 32));
    CNetDiagClient::~CNetDiagClient((void **)v10);
    operator delete(v10);
  }
  else
  {
    v21 = 0;
    *v28 = v10;
  }
  if ( v11 != celt )
    FreeHelperAttributes(attributes, v11, 1);
  return v21;
}

```

## disassembly

```asm
0x18000a9e0  push    rbp
0x18000a9e2  push    rbx
0x18000a9e3  push    rsi
0x18000a9e4  push    rdi
0x18000a9e5  push    r12
0x18000a9e7  push    r13
0x18000a9e9  push    r14
0x18000a9eb  push    r15
0x18000a9ed  lea     rbp, [rsp-208h]
0x18000a9f5  sub     rsp, 308h
0x18000a9fc  mov     rax, cs:__security_cookie
0x18000aa03  xor     rax, rsp
0x18000aa06  mov     [rbp+240h+var_50], rax
0x18000aa0d  xor     esi, esi
0x18000aa0f  mov     [rsp+340h+var_300], rcx
0x18000aa14  mov     r15, r8
0x18000aa17  mov     [rsp+340h+var_2F8], r9
0x18000aa1c  mov     r13d, edx
0x18000aa1f  mov     [rsp+340h+var_308], 0Fh
0x18000aa28  mov     rbx, rcx
0x18000aa2b  mov     [rsp+340h+var_310], rsi
0x18000aa30  lea     r8d, [rsi+11h]; Size
0x18000aa34  mov     byte ptr [rsp+340h+pv], sil
0x18000aa39  lea     rdx, aNdfcreateincid_0; "NdfCreateIncident"
0x18000aa40  mov     rdi, r9
0x18000aa43  lea     rcx, [rsp+340h+pv]; void *
0x18000aa48  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z; std::string::assign(char const *,unsigned __int64)
0x18000aa4d  lea     rcx, [rsp+340h+pv]
0x18000aa52  call    ?TelemeterAPICall@@YAXV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; TelemeterAPICall(std::string)
0x18000aa57  xor     ecx, ecx
0x18000aa59  call    cs:__imp_WdiCancel
0x18000aa5f  cmp     eax, 80070505h
0x18000aa64  jnz     short loc_18000AA6D
0x18000aa66  mov     eax, 80004004h
0x18000aa6b  jmp     short loc_18000AA88
0x18000aa6d  test    rbx, rbx
0x18000aa70  jnz     short loc_18000AA79
0x18000aa72  mov     eax, 8008F901h
0x18000aa77  jmp     short loc_18000AA88
0x18000aa79  test    r13d, r13d
0x18000aa7c  jz      short loc_18000AAAB
0x18000aa7e  test    r15, r15
0x18000aa81  jnz     short loc_18000AAB0
0x18000aa83  mov     eax, 8008F905h
0x18000aa88  mov     rcx, [rbp+240h+var_50]
0x18000aa8f  xor     rcx, rsp; StackCookie
0x18000aa92  call    __security_check_cookie
0x18000aa97  add     rsp, 308h
0x18000aa9e  pop     r15
0x18000aaa0  pop     r14
0x18000aaa2  pop     r13
0x18000aaa4  pop     r12
0x18000aaa6  pop     rdi
0x18000aaa7  pop     rsi
0x18000aaa8  pop     rbx
0x18000aaa9  pop     rbp
0x18000aaaa  retn
0x18000aaab  test    r15, r15
0x18000aaae  jnz     short loc_18000AA83
0x18000aab0  test    rdi, rdi
0x18000aab3  jz      short loc_18000AA83
0x18000aab5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000aabc  mov     ecx, 0CD8h; unsigned __int64
0x18000aac1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000aac6  test    rax, rax
0x18000aac9  jz      loc_18000ACCF
0x18000aacf  mov     rcx, rax; this
0x18000aad2  call    ??0CNetDiagClient@@QEAA@XZ; CNetDiagClient::CNetDiagClient(void)
0x18000aad7  mov     rdi, rax
0x18000aada  test    rax, rax
0x18000aadd  jz      loc_18000ACCF
0x18000aae3  xorps   xmm0, xmm0
0x18000aae6  mov     dword ptr [rsp+340h+var_310], esi
0x18000aaea  mov     r8d, r13d; unsigned int
0x18000aaed  lea     rcx, [rsp+340h+pv]; this
0x18000aaf2  mov     rdx, r15; struct tagHELPER_ATTRIBUTE *
0x18000aaf5  mov     r12d, r13d
0x18000aaf8  movdqu  xmmword ptr [rsp+340h+pv], xmm0
0x18000aafe  call    ?Add@HelperAttributeList@@QEAAJPEBUtagHELPER_ATTRIBUTE@@K@Z; HelperAttributeList::Add(tagHELPER_ATTRIBUTE const *,ulong)
0x18000ab03  test    eax, eax
0x18000ab05  js      loc_18000AC03
0x18000ab0b  mov     rbx, [rsp+340h+pv]
0x18000ab10  lea     r14, aNdfsqmcallerap; "NDFSQMCallerApplication"
0x18000ab17  jmp     short loc_18000AB33
0x18000ab19  mov     rcx, [rbx]
0x18000ab1c  mov     rdx, r14; String2
0x18000ab1f  mov     rcx, [rcx]; String1
0x18000ab22  call    wcscmp_0
0x18000ab27  test    eax, eax
0x18000ab29  jz      loc_18000AC03
0x18000ab2f  mov     rbx, [rbx+8]
0x18000ab33  test    rbx, rbx
0x18000ab36  jnz     short loc_18000AB19
0x18000ab38  xor     edx, edx; Val
0x18000ab3a  lea     rcx, [rbp+240h+Filename]; void *
0x18000ab3e  mov     r8d, 208h; Size
0x18000ab44  call    memset_0
0x18000ab49  mov     r8d, 104h; nSize
0x18000ab4f  lea     rdx, [rbp+240h+Filename]; lpFilename
0x18000ab53  xor     ecx, ecx; hModule
0x18000ab55  call    cs:__imp_GetModuleFileNameW
0x18000ab5b  test    eax, eax
0x18000ab5d  jz      loc_18000AC03
0x18000ab63  xor     edx, edx; Val
0x18000ab65  lea     rcx, [rsp+340h+var_2F0]; void *
0x18000ab6a  mov     r8d, 90h; Size
0x18000ab70  call    memset_0
0x18000ab75  lea     rax, [rbp+240h+var_25A]
0x18000ab79  mov     [rsp+340h+var_2F0.pwszName], r14
0x18000ab7e  lea     r8d, [rbx+1]; unsigned int
0x18000ab82  mov     qword ptr [rsp+340h+var_2F0.10h], rax
0x18000ab87  lea     rdx, [rsp+340h+var_2F0]; struct tagHELPER_ATTRIBUTE *
0x18000ab8c  mov     [rsp+340h+var_2F0.type], 0Ah
0x18000ab94  lea     rcx, [rsp+340h+pv]; this
0x18000ab99  call    ?Add@HelperAttributeList@@QEAAJPEBUtagHELPER_ATTRIBUTE@@K@Z; HelperAttributeList::Add(tagHELPER_ATTRIBUTE const *,ulong)
0x18000ab9e  test    eax, eax
0x18000aba0  js      short loc_18000AC03
0x18000aba2  mov     eax, dword ptr [rsp+340h+var_310]
0x18000aba6  test    eax, eax
0x18000aba8  jz      short loc_18000AC03
0x18000abaa  lea     rbx, [rax+rax*8]
0x18000abae  shl     rbx, 4
0x18000abb2  mov     rcx, rbx; cb
0x18000abb5  call    cs:__imp_CoTaskMemAlloc
0x18000abbb  mov     r14, rax
0x18000abbe  test    rax, rax
0x18000abc1  jz      short loc_18000AC03
0x18000abc3  mov     r8, rbx; Size
0x18000abc6  xor     edx, edx; Val
0x18000abc8  mov     rcx, rax; void *
0x18000abcb  call    memset_0
0x18000abd0  mov     ebx, esi
0x18000abd2  mov     rsi, [rsp+340h+pv]
0x18000abd7  jmp     short loc_18000ABF8
0x18000abd9  mov     rdx, [rsi]; struct tagHELPER_ATTRIBUTE *
0x18000abdc  mov     eax, ebx
0x18000abde  lea     rcx, [rax+rax*8]
0x18000abe2  shl     rcx, 4
0x18000abe6  add     rcx, r14; struct tagHELPER_ATTRIBUTE *
0x18000abe9  call    ?CopyHelperAttribute@@YAJPEAUtagHELPER_ATTRIBUTE@@PEBU1@@Z; CopyHelperAttribute(tagHELPER_ATTRIBUTE *,tagHELPER_ATTRIBUTE const *)
0x18000abee  test    eax, eax
0x18000abf0  js      short loc_18000AC0A
0x18000abf2  mov     rsi, [rsi+8]
0x18000abf6  inc     ebx
0x18000abf8  test    rsi, rsi
0x18000abfb  jnz     short loc_18000ABD9
0x18000abfd  mov     r15, r14
0x18000ac00  mov     r12d, ebx
0x18000ac03  mov     rsi, [rsp+340h+pv]
0x18000ac08  jmp     short loc_18000AC3C
0x18000ac0a  mov     r8d, 1; int
0x18000ac10  mov     edx, ebx; unsigned int
0x18000ac12  mov     rcx, r14; pv
0x18000ac15  call    ?FreeHelperAttributes@@YAXPEAUtagHELPER_ATTRIBUTE@@KH@Z; FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)
0x18000ac1a  jmp     short loc_18000AC03
0x18000ac1c  mov     rcx, [rsi]; pv
0x18000ac1f  mov     edx, 1; unsigned int
0x18000ac24  mov     r8d, edx; int
0x18000ac27  mov     rbx, rsi
0x18000ac2a  mov     rsi, [rsi+8]
0x18000ac2e  call    ?FreeHelperAttributes@@YAXPEAUtagHELPER_ATTRIBUTE@@KH@Z; FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)
0x18000ac33  mov     rcx, rbx; pv
0x18000ac36  call    cs:__imp_CoTaskMemFree
0x18000ac3c  test    rsi, rsi
0x18000ac3f  jnz     short loc_18000AC1C
0x18000ac41  test    r12d, r12d
0x18000ac44  jz      short loc_18000AC5B
0x18000ac46  lea     rcx, [rdi+20h]; this
0x18000ac4a  mov     r8, r15; struct tagHELPER_ATTRIBUTE *
0x18000ac4d  mov     edx, r12d; unsigned int
0x18000ac50  call    ?Copy@_attributes_array_t@@QEAAJKPEAUtagHELPER_ATTRIBUTE@@@Z; _attributes_array_t::Copy(ulong,tagHELPER_ATTRIBUTE *)
0x18000ac55  mov     ebx, eax
0x18000ac57  test    eax, eax
0x18000ac59  js      short loc_18000AC7E
0x18000ac5b  mov     rcx, [rdi+18h]; pv
0x18000ac5f  test    rcx, rcx
0x18000ac62  jz      short loc_18000AC6A
0x18000ac64  call    cs:__imp_CoTaskMemFree
0x18000ac6a  mov     rdx, [rsp+340h+var_300]; unsigned __int16 *
0x18000ac6f  lea     rcx, [rdi+18h]; unsigned __int16 **
0x18000ac73  call    ?StringCopyWithAlloc@@YAJPEAPEAGPEBG@Z; StringCopyWithAlloc(ushort * *,ushort const *)
0x18000ac78  mov     ebx, eax
0x18000ac7a  test    eax, eax
0x18000ac7c  jns     short loc_18000ACAD
0x18000ac7e  mov     rcx, [rdi+18h]; pv
0x18000ac82  test    rcx, rcx
0x18000ac85  jz      short loc_18000AC8D
0x18000ac87  call    cs:__imp_CoTaskMemFree
0x18000ac8d  lea     rcx, [rdi+20h]; this
0x18000ac91  call    ?FreeAll@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeAll(void)
0x18000ac96  test    ebx, ebx
0x18000ac98  jns     short loc_18000ACAF
0x18000ac9a  mov     rcx, rdi; this
0x18000ac9d  call    ??1CNetDiagClient@@QEAA@XZ; CNetDiagClient::~CNetDiagClient(void)
0x18000aca2  mov     rcx, rdi
0x18000aca5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000acab  jmp     short loc_18000ACB7
0x18000acad  xor     ebx, ebx
0x18000acaf  mov     rax, [rsp+340h+var_2F8]
0x18000acb4  mov     [rax], rdi
0x18000acb7  cmp     r12d, r13d
0x18000acba  jz      short loc_18000ACD4
0x18000acbc  mov     r8d, 1; int
0x18000acc2  mov     edx, r12d; unsigned int
0x18000acc5  mov     rcx, r15; pv
0x18000acc8  call    ?FreeHelperAttributes@@YAXPEAUtagHELPER_ATTRIBUTE@@KH@Z; FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)
0x18000accd  jmp     short loc_18000ACD4
0x18000accf  mov     ebx, 8007000Eh
0x18000acd4  mov     eax, ebx
0x18000acd6  jmp     loc_18000AA88
```
