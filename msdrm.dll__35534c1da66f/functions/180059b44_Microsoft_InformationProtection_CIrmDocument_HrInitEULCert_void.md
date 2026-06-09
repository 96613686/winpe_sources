# Microsoft::InformationProtection::CIrmDocument::HrInitEULCert(void)

- ea: `0x180059b44`
- end: `0x180059ce6`
- name: `?HrInitEULCert@CIrmDocument@InformationProtection@Microsoft@@AEAAJXZ`
- size: `418`
- prototype: `__int64 __fastcall(Microsoft::InformationProtection::CIrmDocument *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180059920`
- `0x18005a4f0`

## callees

- `0x180001284`
- `0x18001a680`
- `0x180058f64`
- `0x180059b44`
- `0x18005a9cc`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180059c31`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180059c31`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180059bb0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180059bb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059c91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059c91`

## pseudocode

```c
__int64 __fastcall Microsoft::InformationProtection::CIrmDocument::HrInitEULCert(
        Microsoft::InformationProtection::CIrmDocument *this)
{
  int EULCert; // eax
  unsigned int v3; // ebx
  HANDLE EventW; // rax
  void *v5; // rbp
  __int64 v6; // rcx
  WCHAR *v7; // rax
  HRESULT v8; // eax
  __int64 v9; // r8
  void *v10; // rcx
  __int128 pvContext; // [rsp+40h] [rbp-28h] BYREF
  __int64 v13; // [rsp+50h] [rbp-18h]

  v13 = 0;
  pvContext = 0;
  if ( !*((_DWORD *)this + 28) || !*((_QWORD *)this + 17) )
  {
    v3 = -2147418113;
    Microsoft::InformationProtection::DebugLog(
      (Microsoft::InformationProtection *)L"%S Exited with hr = 0x%x",
      "Microsoft::InformationProtection::CIrmDocument::HrInitEULCert",
      2147549183LL);
    return v3;
  }
  EULCert = Microsoft::InformationProtection::CIrmDocument::HrFetchEULCert(this);
  v3 = EULCert;
  if ( EULCert < 0 )
  {
    Microsoft::InformationProtection::DebugLog(
      (Microsoft::InformationProtection *)L"%S FAILED at Line %d with hr = 0x%x",
      "Microsoft::InformationProtection::CIrmDocument::HrInitEULCert",
      792,
      (unsigned int)EULCert);
    EventW = CreateEventW(0, 0, 0, 0);
    v5 = EventW;
    if ( !EventW )
    {
LABEL_5:
      v3 = -2147467259;
      goto LABEL_13;
    }
    v6 = *((_QWORD *)this + 17);
    *(_QWORD *)&pvContext = this;
    *((_QWORD *)&pvContext + 1) = EventW;
    LODWORD(v13) = 0;
    v7 = (WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 40LL))(v6);
    v8 = DRMAcquireLicense(*((_DWORD *)this + 28), 2u, v7, 0, 0, 0, &pvContext);
    v3 = v8;
    if ( v8 >= 0 )
    {
      if ( WaitForSingleObject(v5, 0xEA60u) )
        goto LABEL_5;
      v3 = v13;
      if ( (int)v13 < 0 )
      {
LABEL_13:
        v10 = (void *)*((_QWORD *)this + 15);
        if ( v10 )
        {
          operator delete(v10);
          *((_QWORD *)this + 15) = 0;
        }
        if ( !v5 )
          goto LABEL_18;
        goto LABEL_16;
      }
      v8 = Microsoft::InformationProtection::CIrmDocument::HrFetchEULCert(this);
      v3 = v8;
      if ( v8 >= 0 )
      {
LABEL_16:
        if ( v5 != (void *)-1LL )
          CloseHandle(v5);
LABEL_18:
        if ( (v3 & 0x80000000) != 0 )
          Microsoft::InformationProtection::DebugLog(
            (Microsoft::InformationProtection *)L"%S FAILED at Line %d with hr = 0x%x",
            "Microsoft::InformationProtection::CIrmDocument::HrInitEULCert",
            831,
            v3);
        return v3;
      }
      v9 = 823;
    }
    else
    {
      v9 = 810;
    }
    Microsoft::InformationProtection::DebugLog(
      (Microsoft::InformationProtection *)L"%S FAILED at Line %d with hr = 0x%x",
      "Microsoft::InformationProtection::CIrmDocument::HrInitEULCert",
      v9,
      (unsigned int)v8);
    goto LABEL_13;
  }
  return v3;
}

```

## disassembly

```asm
0x180059b44  mov     [rsp+arg_0], rbx
0x180059b49  mov     [rsp+arg_8], rbp
0x180059b4e  push    rdi
0x180059b4f  sub     rsp, 60h
0x180059b53  xor     eax, eax
0x180059b55  xorps   xmm0, xmm0
0x180059b58  mov     rdi, rcx
0x180059b5b  mov     [rsp+68h+var_18], rax
0x180059b60  movups  [rsp+68h+var_28], xmm0
0x180059b65  cmp     [rcx+70h], eax
0x180059b68  jz      loc_180059CB9
0x180059b6e  cmp     [rcx+88h], rax
0x180059b75  jz      loc_180059CB9
0x180059b7b  call    ?HrFetchEULCert@CIrmDocument@InformationProtection@Microsoft@@AEAAJXZ; Microsoft::InformationProtection::CIrmDocument::HrFetchEULCert(void)
0x180059b80  mov     ebx, eax
0x180059b82  test    eax, eax
0x180059b84  jns     loc_180059CD4
0x180059b8a  mov     r9d, eax
0x180059b8d  lea     rdx, aMicrosoftInfor_11; "Microsoft::InformationProtection::CIrmD"...
0x180059b94  mov     r8d, 318h
0x180059b9a  lea     rcx, aSFailedAtLineD; "%S FAILED at Line %d with hr = 0x%x"
0x180059ba1  call    ?DebugLog@InformationProtection@Microsoft@@YAXPEBGZZ; Microsoft::InformationProtection::DebugLog(ushort const *,...)
0x180059ba6  xor     r9d, r9d; lpName
0x180059ba9  xor     r8d, r8d; bInitialState
0x180059bac  xor     edx, edx; bManualReset
0x180059bae  xor     ecx, ecx; lpEventAttributes
0x180059bb0  call    cs:__imp_CreateEventW
0x180059bb6  mov     rbp, rax
0x180059bb9  test    rax, rax
0x180059bbc  jnz     short loc_180059BC8
0x180059bbe  mov     ebx, 80004005h
0x180059bc3  jmp     loc_180059C6D
0x180059bc8  mov     rcx, [rdi+88h]
0x180059bcf  mov     qword ptr [rsp+68h+var_28], rdi
0x180059bd4  mov     qword ptr [rsp+68h+var_28+8], rbp
0x180059bd9  mov     dword ptr [rsp+68h+var_18], 0
0x180059be1  mov     rax, [rcx]
0x180059be4  mov     rax, [rax+28h]
0x180059be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059bed  lea     rcx, [rsp+68h+var_28]
0x180059bf2  xor     r9d, r9d; wszRequestedRights
0x180059bf5  mov     [rsp+68h+pvContext], rcx; pvContext
0x180059bfa  mov     r8, rax; wszGroupIdentityCredential
0x180059bfd  mov     ecx, [rdi+70h]; hSession
0x180059c00  mov     [rsp+68h+wszURL], 0; wszURL
0x180059c09  lea     edx, [r9+2]; uFlags
0x180059c0d  mov     [rsp+68h+wszCustomData], 0; wszCustomData
0x180059c16  call    DRMAcquireLicense
0x180059c1b  mov     ebx, eax
0x180059c1d  test    eax, eax
0x180059c1f  jns     short loc_180059C29
0x180059c21  mov     r8d, 32Ah
0x180059c27  jmp     short loc_180059C57
0x180059c29  mov     edx, 0EA60h; dwMilliseconds
0x180059c2e  mov     rcx, rbp; hHandle
0x180059c31  call    cs:__imp_WaitForSingleObject
0x180059c37  test    eax, eax
0x180059c39  jnz     short loc_180059BBE
0x180059c3b  mov     ebx, dword ptr [rsp+68h+var_18]
0x180059c3f  test    ebx, ebx
0x180059c41  js      short loc_180059C6D
0x180059c43  mov     rcx, rdi; this
0x180059c46  call    ?HrFetchEULCert@CIrmDocument@InformationProtection@Microsoft@@AEAAJXZ; Microsoft::InformationProtection::CIrmDocument::HrFetchEULCert(void)
0x180059c4b  mov     ebx, eax
0x180059c4d  test    eax, eax
0x180059c4f  jns     short loc_180059C88
0x180059c51  mov     r8d, 337h
0x180059c57  mov     r9d, eax
0x180059c5a  lea     rdx, aMicrosoftInfor_11; "Microsoft::InformationProtection::CIrmD"...
0x180059c61  lea     rcx, aSFailedAtLineD; "%S FAILED at Line %d with hr = 0x%x"
0x180059c68  call    ?DebugLog@InformationProtection@Microsoft@@YAXPEBGZZ; Microsoft::InformationProtection::DebugLog(ushort const *,...)
0x180059c6d  mov     rcx, [rdi+78h]; Block
0x180059c71  test    rcx, rcx
0x180059c74  jz      short loc_180059C83
0x180059c76  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180059c7b  mov     qword ptr [rdi+78h], 0
0x180059c83  test    rbp, rbp
0x180059c86  jz      short loc_180059C97
0x180059c88  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x180059c8c  jz      short loc_180059C97
0x180059c8e  mov     rcx, rbp; hObject
0x180059c91  call    cs:__imp_CloseHandle
0x180059c97  test    ebx, ebx
0x180059c99  jns     short loc_180059CD4
0x180059c9b  mov     r9d, ebx
0x180059c9e  lea     rdx, aMicrosoftInfor_11; "Microsoft::InformationProtection::CIrmD"...
0x180059ca5  mov     r8d, 33Fh
0x180059cab  lea     rcx, aSFailedAtLineD; "%S FAILED at Line %d with hr = 0x%x"
0x180059cb2  call    ?DebugLog@InformationProtection@Microsoft@@YAXPEBGZZ; Microsoft::InformationProtection::DebugLog(ushort const *,...)
0x180059cb7  jmp     short loc_180059CD4
0x180059cb9  mov     ebx, 8000FFFFh
0x180059cbe  lea     rdx, aMicrosoftInfor_11; "Microsoft::InformationProtection::CIrmD"...
0x180059cc5  mov     r8d, ebx
0x180059cc8  lea     rcx, aSExitedWithHr0; "%S Exited with hr = 0x%x"
0x180059ccf  call    ?DebugLog@InformationProtection@Microsoft@@YAXPEBGZZ; Microsoft::InformationProtection::DebugLog(ushort const *,...)
0x180059cd4  mov     rbp, [rsp+68h+arg_8]
0x180059cd9  mov     eax, ebx
0x180059cdb  mov     rbx, [rsp+68h+arg_0]
0x180059ce0  add     rsp, 60h
0x180059ce4  pop     rdi
0x180059ce5  retn
```
