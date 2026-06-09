# CMessageContextMenu::CreateDisplayNameForPropertySearch(_tagpropertykey const &,IPropertyStore *,wchar_t * *)

- ea: `0x180019188`
- end: `0x1800193e0`
- name: `?CreateDisplayNameForPropertySearch@CMessageContextMenu@@IEAAJAEBU_tagpropertykey@@PEAUIPropertyStore@@PEAPEA_W@Z`
- size: `600`
- prototype: `__int64 __fastcall(CMessageContextMenu *__hidden this, const struct _tagpropertykey *, struct IPropertyStore *, wchar_t **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001968c`

## callees

- `0x180004080`
- `0x180005210`
- `0x18000557c`
- `0x180006270`
- `0x180008a74`
- `0x180019188`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180019277`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001936a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180019277`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001936a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001939a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001939a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019335`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019335`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001934c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001934c`
- `PROPSYS!PSGetPropertyDescription` at `0x1800192d8`
- `PROPSYS!PSGetPropertyDescription` at `0x1800192d8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMessageContextMenu::CreateDisplayNameForPropertySearch(
        CMessageContextMenu *this,
        const struct _tagpropertykey *a2,
        struct IPropertyStore *a3,
        wchar_t **a4)
{
  DWORD pid; // eax
  __int64 v7; // rax
  UINT v8; // edx
  __int64 v9; // rax
  __int64 v10; // rax
  HRESULT Error; // ebx
  __int64 v12; // rax
  unsigned __int64 v13; // rbx
  wchar_t *v14; // rax
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  void *ppv; // [rsp+38h] [rbp-C8h] BYREF
  PROPVARIANT pvar[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+50h] [rbp-B0h]
  PROPERTYKEY propkey; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t v21[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[264]; // [rsp+280h] [rbp+180h] BYREF

  propkey.fmtid = a2->fmtid;
  pid = a2->pid;
  propkey.pid = pid;
  if ( pid != 100 )
  {
    if ( pid == 14 )
    {
      v9 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_Message_FromName.fmtid.Data1;
      if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_Message_FromName.fmtid.Data1 )
        v9 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_Message_FromName.fmtid.Data4;
      if ( !v9 )
      {
        v8 = 142;
        goto LABEL_16;
      }
    }
    else if ( pid == 20 )
    {
      v10 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_Message_DateReceived.fmtid.Data1;
      if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_Message_DateReceived.fmtid.Data1 )
        v10 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_Message_DateReceived.fmtid.Data4;
      if ( !v10 )
      {
        v8 = 143;
        goto LABEL_16;
      }
    }
LABEL_24:
    if ( LoadStringW(hInstance, 0x90u, v21, 260) )
    {
LABEL_27:
      v12 = -1;
      do
        ++v12;
      while ( v21[v12] );
      v13 = (unsigned int)(v12 + 1);
      v14 = (wchar_t *)CoTaskMemAlloc(2 * v13);
      *a4 = v14;
      if ( v14 )
        return (unsigned int)StringCchCopyW(v14, v13, v21);
      else
        return (unsigned int)-2147024882;
    }
    Error = ResultFromLastError();
LABEL_26:
    if ( Error < 0 )
      return (unsigned int)Error;
    goto LABEL_27;
  }
  v7 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_Message_ConversationID.fmtid.Data1;
  if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_Message_ConversationID.fmtid.Data1 )
    v7 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_Message_ConversationID.fmtid.Data4;
  if ( v7 )
    goto LABEL_24;
  v8 = 141;
  propkey = PKEY_ItemName;
LABEL_16:
  if ( LoadStringW(hInstance, v8, Buffer, 260) || (Error = ResultFromLastError(), Error >= 0) )
  {
    *(_OWORD *)pvar = 0;
    v19 = 0;
    Error = ((__int64 (__fastcall *)(struct IPropertyStore *, PROPERTYKEY *, PROPVARIANT *))a3->lpVtbl->GetValue)(
              a3,
              &propkey,
              pvar);
    if ( Error >= 0 )
    {
      ppv = 0;
      Error = PSGetPropertyDescription(&propkey, &GUID_6f79d558_3e96_4549_a1d1_7d75d2288814, &ppv);
      if ( Error >= 0 )
      {
        pv = 0;
        Error = (*(__int64 (__fastcall **)(void *, PROPVARIANT *, __int64, LPVOID *))(*(_QWORD *)ppv + 176LL))(
                  ppv,
                  pvar,
                  64,
                  &pv);
        if ( Error >= 0 )
        {
          Error = StringCchPrintfW(v21, 0x104u, Buffer, pv);
          CoTaskMemFree(pv);
        }
      }
      ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&ppv);
    }
    PropVariantClear(pvar);
    goto LABEL_26;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180019188  push    rbp
0x18001918a  push    rbx
0x18001918b  push    rsi
0x18001918c  push    rdi
0x18001918d  push    r14
0x18001918f  lea     rbp, [rsp-3A0h]
0x180019197  sub     rsp, 4A0h
0x18001919e  mov     rax, cs:__security_cookie
0x1800191a5  xor     rax, rsp
0x1800191a8  mov     [rbp+3C0h+var_30], rax
0x1800191af  mov     rsi, r9
0x1800191b2  mov     rdi, r8
0x1800191b5  movups  xmm0, xmmword ptr [rdx]
0x1800191b8  movups  xmmword ptr [rsp+4C0h+propkey.fmtid.Data1], xmm0
0x1800191bd  mov     eax, [rdx+10h]
0x1800191c0  mov     [rsp+4C0h+propkey.pid], eax
0x1800191c4  xor     r14d, r14d
0x1800191c7  cmp     eax, 64h ; 'd'
0x1800191ca  jnz     short loc_180019209
0x1800191cc  mov     rax, [rdx]
0x1800191cf  sub     rax, qword ptr cs:PKEY_Message_ConversationID.fmtid.Data1
0x1800191d6  jnz     short loc_1800191E3
0x1800191d8  mov     rax, [rdx+8]
0x1800191dc  sub     rax, qword ptr cs:PKEY_Message_ConversationID.fmtid.Data4
0x1800191e3  test    rax, rax
0x1800191e6  jnz     loc_180019354
0x1800191ec  mov     edx, 8Dh
0x1800191f1  movups  xmm0, xmmword ptr cs:PKEY_ItemName.fmtid.Data1
0x1800191f8  movups  xmmword ptr [rsp+4C0h+propkey.fmtid.Data1], xmm0
0x1800191fd  mov     eax, cs:PKEY_ItemName.pid
0x180019203  mov     [rsp+4C0h+propkey.pid], eax
0x180019207  jmp     short loc_180019263
0x180019209  cmp     eax, 0Eh
0x18001920c  jnz     short loc_180019235
0x18001920e  mov     rax, [rdx]
0x180019211  sub     rax, qword ptr cs:PKEY_Message_FromName.fmtid.Data1
0x180019218  jnz     short loc_180019225
0x18001921a  mov     rax, [rdx+8]
0x18001921e  sub     rax, qword ptr cs:PKEY_Message_FromName.fmtid.Data4
0x180019225  test    rax, rax
0x180019228  jnz     loc_180019354
0x18001922e  mov     edx, 8Eh
0x180019233  jmp     short loc_180019263
0x180019235  cmp     eax, 14h
0x180019238  jnz     loc_180019354
0x18001923e  mov     rax, [rdx]
0x180019241  sub     rax, qword ptr cs:PKEY_Message_DateReceived.fmtid.Data1
0x180019248  jnz     short loc_180019255
0x18001924a  mov     rax, [rdx+8]
0x18001924e  sub     rax, qword ptr cs:PKEY_Message_DateReceived.fmtid.Data4
0x180019255  test    rax, rax
0x180019258  jnz     loc_180019354
0x18001925e  mov     edx, 8Fh; uID
0x180019263  mov     r9d, 104h; cchBufferMax
0x180019269  lea     r8, [rbp+3C0h+Buffer]; lpBuffer
0x180019270  mov     rcx, cs:hInstance; hInstance
0x180019277  call    cs:__imp_LoadStringW
0x18001927d  test    eax, eax
0x18001927f  jnz     short loc_180019290
0x180019281  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180019286  mov     ebx, eax
0x180019288  test    eax, eax
0x18001928a  js      loc_1800193C1
0x180019290  xorps   xmm0, xmm0
0x180019293  xor     eax, eax
0x180019295  movups  xmmword ptr [rsp+4C0h+pvar], xmm0
0x18001929a  mov     [rsp+4C0h+var_470], rax
0x18001929f  mov     rax, [rdi]
0x1800192a2  lea     r8, [rsp+4C0h+pvar]
0x1800192a7  lea     rdx, [rsp+4C0h+propkey]
0x1800192ac  mov     rcx, rdi
0x1800192af  mov     rax, [rax+28h]
0x1800192b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192b8  mov     ebx, eax
0x1800192ba  test    eax, eax
0x1800192bc  js      loc_180019347
0x1800192c2  mov     [rsp+4C0h+ppv], r14
0x1800192c7  lea     r8, [rsp+4C0h+ppv]; ppv
0x1800192cc  lea     rdx, _GUID_6f79d558_3e96_4549_a1d1_7d75d2288814; riid
0x1800192d3  lea     rcx, [rsp+4C0h+propkey]; propkey
0x1800192d8  call    cs:__imp_PSGetPropertyDescription
0x1800192de  mov     ebx, eax
0x1800192e0  test    eax, eax
0x1800192e2  js      short loc_18001933C
0x1800192e4  mov     [rsp+4C0h+pv], r14
0x1800192e9  mov     rcx, [rsp+4C0h+ppv]
0x1800192ee  mov     rax, [rcx]
0x1800192f1  lea     r9, [rsp+4C0h+pv]
0x1800192f6  mov     r8d, 40h ; '@'
0x1800192fc  lea     rdx, [rsp+4C0h+pvar]
0x180019301  mov     rax, [rax+0B0h]
0x180019308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001930d  mov     ebx, eax
0x18001930f  test    eax, eax
0x180019311  js      short loc_18001933C
0x180019313  mov     r9, [rsp+4C0h+pv]
0x180019318  lea     r8, [rbp+3C0h+Buffer]; wchar_t *
0x18001931f  mov     edx, 104h; unsigned __int64
0x180019324  lea     rcx, [rsp+4C0h+var_450]; wchar_t *
0x180019329  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18001932e  mov     ebx, eax
0x180019330  mov     rcx, [rsp+4C0h+pv]; pv
0x180019335  call    cs:__imp_CoTaskMemFree
0x18001933b  nop
0x18001933c  lea     rcx, [rsp+4C0h+ppv]
0x180019341  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x180019346  nop
0x180019347  lea     rcx, [rsp+4C0h+pvar]; pvar
0x18001934c  call    cs:__imp_PropVariantClear
0x180019352  jmp     short loc_18001937B
0x180019354  mov     r9d, 104h; cchBufferMax
0x18001935a  lea     r8, [rsp+4C0h+var_450]; lpBuffer
0x18001935f  lea     edx, [r9-74h]; uID
0x180019363  mov     rcx, cs:hInstance; hInstance
0x18001936a  call    cs:__imp_LoadStringW
0x180019370  test    eax, eax
0x180019372  jnz     short loc_18001937F
0x180019374  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180019379  mov     ebx, eax
0x18001937b  test    ebx, ebx
0x18001937d  js      short loc_1800193C1
0x18001937f  lea     rcx, [rsp+4C0h+var_450]
0x180019384  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019388  inc     rax
0x18001938b  cmp     [rcx+rax*2], r14w
0x180019390  jnz     short loc_180019388
0x180019392  inc     eax
0x180019394  mov     ebx, eax
0x180019396  lea     rcx, [rax+rax]; cb
0x18001939a  call    cs:__imp_CoTaskMemAlloc
0x1800193a0  mov     [rsi], rax
0x1800193a3  test    rax, rax
0x1800193a6  jnz     short loc_1800193AF
0x1800193a8  mov     ebx, 8007000Eh
0x1800193ad  jmp     short loc_1800193C1
0x1800193af  lea     r8, [rsp+4C0h+var_450]; wchar_t *
0x1800193b4  mov     rdx, rbx; unsigned __int64
0x1800193b7  mov     rcx, rax; wchar_t *
0x1800193ba  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800193bf  mov     ebx, eax
0x1800193c1  mov     eax, ebx
0x1800193c3  mov     rcx, [rbp+3C0h+var_30]
0x1800193ca  xor     rcx, rsp; StackCookie
0x1800193cd  call    __security_check_cookie
0x1800193d2  add     rsp, 4A0h
0x1800193d9  pop     r14
0x1800193db  pop     rdi
0x1800193dc  pop     rsi
0x1800193dd  pop     rbx
0x1800193de  pop     rbp
0x1800193df  retn
```
