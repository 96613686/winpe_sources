# CMsiOpExecute::CreateFolder(IMsiPath &,Bool,Bool,IMsiStream *,Bool,Bool,Bool)

- ea: `0x1800a55e0`
- end: `0x1800a5cd4`
- name: `?CreateFolder@CMsiOpExecute@@IEAA?AW4iesEnum@@AEAVIMsiPath@@W4Bool@@1PEAVIMsiStream@@111@Z`
- size: `1780`
- prototype: ``
- caller_count: `10`
- callee_count: `21`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180068848`
- `0x1800694d0`
- `0x1800a2b9c`
- `0x1800e519c`
- `0x180146828`
- `0x1801de630`
- `0x1801f4530`
- `0x1801f7020`
- `0x1801f7ac0`
- `0x1801f89f0`

## callees

- `0x180012620`
- `0x180025904`
- `0x180025a18`
- `0x180035a8c`
- `0x1800620e4`
- `0x180066074`
- `0x180068680`
- `0x180076e28`
- `0x18007ccec`
- `0x18007d8cc`
- `0x1800a55e0`
- `0x18011d2c4`
- `0x1801382a0`
- `0x18014471c`
- `0x180146548`
- `0x18014a65c`
- `0x180154ed4`
- `0x18016d71c`
- `0x18025ab2a`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!IsValidSecurityDescriptor` at `0x1800a56df`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x1800a56df`
- `ADVAPI32!SetFileSecurityW` at `0x1800a5ace`
- `ADVAPI32!SetFileSecurityW` at `0x1800a5c1b`
- `ADVAPI32!SetFileSecurityW` at `0x1800a5ace`
- `ADVAPI32!SetFileSecurityW` at `0x1800a5c1b`
- `KERNEL32!GetLastError` at `0x1800a5c4d`
- `KERNEL32!GetLastError` at `0x1800a5c4d`
- `KERNEL32!CreateFileW` at `0x1800a595f`
- `KERNEL32!CreateFileW` at `0x1800a5b2b`
- `KERNEL32!CreateFileW` at `0x1800a595f`
- `KERNEL32!CreateFileW` at `0x1800a5b2b`

## string_xrefs

- `0x1800a59a3`: `Folder is not accessible: %s`
- `0x1800a5b73`: `Folder is not accessible: %s`
- `0x1800a5a23`: `Folder has Junction: %s`

## pseudocode

```c
__int64 __fastcall CMsiOpExecute::CreateFolder(
        __int64 a1,
        __int64 *a2,
        int a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        int a7,
        int a8)
{
  unsigned int v8; // r12d
  __int64 v11; // rbx
  __int128 *v12; // rcx
  unsigned int v13; // esi
  int v14; // eax
  unsigned int v15; // edi
  PSECURITY_DESCRIPTOR v16; // rdx
  PSECURITY_DESCRIPTOR v17; // rcx
  int v18; // edi
  __int64 v19; // rsi
  int v20; // eax
  int v22; // eax
  __int64 v23; // rax
  __int64 (__fastcall *v24)(__int64 *, __int64); // rbx
  __int64 v25; // rax
  __int64 v26; // rax
  int v27; // ebx
  unsigned int v28; // esi
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rbx
  const WCHAR *v32; // rax
  HANDLE FileW; // rax
  const unsigned __int16 *v34; // rax
  const unsigned __int16 *v35; // rax
  SECURITY_INFORMATION SecurityInformation; // r14d
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rdx
  PSECURITY_DESCRIPTOR v40; // rdi
  const WCHAR *v41; // rax
  BOOL v42; // edi
  const WCHAR *v43; // rax
  HANDLE v44; // rax
  const unsigned __int16 *v45; // rax
  __int64 v46; // rdx
  PSECURITY_DESCRIPTOR v47; // rdi
  const WCHAR *v48; // rax
  __int64 v49; // rdi
  DWORD LastError; // eax
  __int64 v51; // rdx
  __int64 v52; // [rsp+60h] [rbp-A0h] BYREF
  int v53; // [rsp+68h] [rbp-98h] BYREF
  int v54; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v55; // [rsp+70h] [rbp-90h] BYREF
  __int64 v56; // [rsp+78h] [rbp-88h] BYREF
  char v57[8]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v58; // [rsp+88h] [rbp-78h] BYREF
  __int64 v59; // [rsp+98h] [rbp-68h]
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+A0h] [rbp-60h] BYREF
  int v61; // [rsp+A8h] [rbp-58h]
  _BYTE v62[512]; // [rsp+B0h] [rbp-50h] BYREF

  v8 = 0;
  v54 = a3;
  v55 = a4;
  v53 = 0;
  v11 = 0;
  v56 = 0;
  memset_0(v62, 0, sizeof(v62));
  v61 = 512;
  pSecurityDescriptor = v62;
  v12 = 0;
  v59 = 0;
  v52 = 0;
  v58 = 0;
  v13 = 3;
  if ( a5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a5 + 112LL))(a5);
    v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a5 + 32LL))(a5);
    v15 = v14;
    if ( v14 <= 512 )
    {
      v16 = pSecurityDescriptor;
    }
    else
    {
      CTempBuffer<char,512>::SetSize(&pSecurityDescriptor, (unsigned int)v14);
      v16 = pSecurityDescriptor;
      if ( !pSecurityDescriptor )
      {
        if ( v61 <= 512 )
        {
LABEL_70:
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v56);
          return v13;
        }
        v17 = 0;
LABEL_60:
        operator delete(v17);
        goto LABEL_70;
      }
    }
    (*(void (__fastcall **)(__int64, PSECURITY_DESCRIPTOR, _QWORD))(*(_QWORD *)a5 + 64LL))(a5, v16, v15);
    IsValidSecurityDescriptor(pSecurityDescriptor);
    v12 = &v58;
    *((_QWORD *)&v58 + 1) = pSecurityDescriptor;
    v52 = (__int64)&v58;
    LODWORD(v58) = 24;
    LODWORD(v59) = 0;
  }
  v18 = 2;
  if ( a7 || *(_DWORD *)(a1 + 40) == 2 )
    v8 = 1;
  while ( 1 )
  {
    v19 = (*(__int64 (__fastcall **)(__int64 *, int *, __int128 *, _QWORD))(*a2 + 200))(a2, &v53, v12, v8);
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = v19;
    v56 = v19;
    if ( !v19 )
      break;
    v20 = CMsiOpExecute::DispatchMessageW(a1, 16777221, v19);
    if ( v20 == 2 )
    {
      if ( v61 > 512 )
        operator delete(pSecurityDescriptor);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      return 2;
    }
    v12 = (__int128 *)v52;
    if ( v20 != 4 )
      goto LABEL_22;
  }
  v22 = v53;
  if ( a6 )
  {
    if ( !v53 )
      goto LABEL_39;
  }
  else if ( !v53 )
  {
LABEL_22:
    if ( v61 > 512 )
      operator delete(pSecurityDescriptor);
    v13 = 3;
    goto LABEL_70;
  }
  if ( v54 || a8 != 1 && *(_DWORD *)(a1 + 500) == 5 )
  {
LABEL_39:
    if ( a5 && !v22 )
    {
      v30 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 56))(a2);
      v52 = -1;
      v31 = v30;
      if ( v8 )
      {
        CElevate::CElevate((CElevate *)&v55, 1);
        v32 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 80LL))(v31);
        v13 = 3;
        FileW = CreateFileW(v32, 0x80000000, 3u, 0, 3u, 0x2200000u, 0);
        CHandle::operator=(&v52, FileW);
        if ( v52 == -1 )
        {
          if ( g_dmDiagnosticMode )
          {
            v34 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 80LL))(v31);
            DebugString(
              9,
              0,
              0,
              L"Folder is not accessible: %s",
              v34,
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          }
          CElevate::~CElevate((CElevate *)&v55);
          goto LABEL_58;
        }
        if ( (*(unsigned __int8 (__fastcall **)(__int64 *))(*a2 + 584))(a2) )
        {
          if ( g_dmDiagnosticMode )
          {
            v35 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 80LL))(v31);
            DebugString(
              9,
              0,
              0,
              L"Folder has Junction: %s",
              v35,
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          }
          v8 = 0;
        }
        CElevate::~CElevate((CElevate *)&v55);
      }
      else
      {
        v43 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 80LL))(v30);
        v13 = 3;
        v44 = CreateFileW(v43, 0x80000000, 3u, 0, 3u, 0x2200000u, 0);
        CHandle::operator=(&v52, v44);
        if ( v52 == -1 )
        {
          if ( g_dmDiagnosticMode )
          {
            v45 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 80LL))(v31);
            DebugString(
              9,
              0,
              0,
              L"Folder is not accessible: %s",
              v45,
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          }
          goto LABEL_58;
        }
      }
      SecurityInformation = GetSecurityInformation(pSecurityDescriptor);
      LOBYTE(v37) = 1;
      if ( v8 )
      {
        CElevate::CElevate((CElevate *)v57, 1);
        LOBYTE(v38) = 1;
        if ( (unsigned __int8)RefCountedTokenPrivilegesCore(1, v38) )
          v18 = 1;
        v54 = v18;
        CRefCountedTokenPrivileges::CRefCountedTokenPrivileges(&v55, v39, (SecurityInformation >> 3) & 1);
        v40 = pSecurityDescriptor;
        v41 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 80LL))(v31);
        v42 = SetFileSecurityW(v41, SecurityInformation, v40);
        CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges((CRefCountedTokenPrivileges *)&v55);
        CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges((CRefCountedTokenPrivileges *)&v54);
        CElevate::~CElevate((CElevate *)v57);
      }
      else
      {
        if ( (unsigned __int8)RefCountedTokenPrivilegesCore(1, v37) )
          v18 = 1;
        v54 = v18;
        CRefCountedTokenPrivileges::CRefCountedTokenPrivileges(&v55, v46, (SecurityInformation >> 3) & 1);
        v47 = pSecurityDescriptor;
        v48 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 80LL))(v31);
        v42 = SetFileSecurityW(v48, SecurityInformation, v47);
        CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges((CRefCountedTokenPrivileges *)&v55);
        CRefCountedTokenPrivileges::~CRefCountedTokenPrivileges((CRefCountedTokenPrivileges *)&v54);
      }
      if ( !v42 )
      {
        v49 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 80LL))(v31);
        LastError = GetLastError();
        CMsiOpExecute::DispatchError(a1, v51, 1926, LastError, v49);
LABEL_58:
        CHandle::~CHandle((CHandle *)&v52);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        if ( v61 <= 512 )
          goto LABEL_70;
        v17 = pSecurityDescriptor;
        goto LABEL_60;
      }
      CHandle::~CHandle((CHandle *)&v52);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    if ( v61 > 512 )
      operator delete(pSecurityDescriptor);
    v13 = 1;
    goto LABEL_70;
  }
  v23 = *a2;
  v52 = 0;
  v24 = *(__int64 (__fastcall **)(__int64 *, __int64))(v23 + 88);
  v25 = CComPointer<IEnumMsiRecord>::operator=(&v52);
  v26 = v24(a2, v25);
  CComPointer<IMsiDatabase>::operator=(&v56, v26);
  if ( !v56 )
  {
    v27 = 0;
    if ( v53 > 0 )
    {
      v28 = v55;
      do
      {
        v29 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(a1 + 8) + 256LL))(
                *(_QWORD *)(a1 + 8),
                v52,
                v28);
        CComPointer<IMsiDatabase>::operator=(&v56, v29);
        if ( v56 )
          CMsiOpExecute::Message(a1, 0x4000000, v56);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 112LL))(v52);
        ++v27;
      }
      while ( v27 < v53 );
    }
    CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v52);
    v22 = v53;
    goto LABEL_39;
  }
  CMsiOpExecute::Message(a1, 0x1000000, v56);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v52);
  if ( v61 > 512 )
    operator delete(pSecurityDescriptor);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v56);
  return 3;
}

```

## disassembly

```asm
0x1800a55e0  mov     [rsp-8+arg_10], rbx
0x1800a55e5  push    rbp
0x1800a55e6  push    rsi
0x1800a55e7  push    rdi
0x1800a55e8  push    r12
0x1800a55ea  push    r13
0x1800a55ec  push    r14
0x1800a55ee  push    r15
0x1800a55f0  lea     rbp, [rsp-1C0h]
0x1800a55f8  sub     rsp, 2C0h
0x1800a55ff  mov     rax, cs:__security_cookie
0x1800a5606  xor     rax, rsp
0x1800a5609  mov     [rbp+1F0h+var_40], rax
0x1800a5610  mov     r14, [rbp+1F0h+arg_20]
0x1800a5617  xor     r12d, r12d
0x1800a561a  mov     [rsp+2F0h+var_284], r8d
0x1800a561f  mov     r15, rdx
0x1800a5622  mov     r13, rcx
0x1800a5625  mov     [rsp+2F0h+var_280], r9d
0x1800a562a  mov     edi, 200h
0x1800a562f  mov     [rsp+2F0h+var_288], r12d
0x1800a5634  mov     ebx, r12d
0x1800a5637  lea     rcx, [rbp+1F0h+var_240]; void *
0x1800a563b  mov     r8d, edi; Size
0x1800a563e  mov     [rsp+2F0h+var_278], rbx
0x1800a5643  xor     edx, edx; Val
0x1800a5645  call    memset_0
0x1800a564a  lea     rax, [rbp+1F0h+var_240]
0x1800a564e  mov     [rbp+1F0h+var_248], edi
0x1800a5651  mov     [rbp+1F0h+pSecurityDescriptor], rax
0x1800a5655  xorps   xmm0, xmm0
0x1800a5658  xor     eax, eax
0x1800a565a  mov     ecx, r12d
0x1800a565d  mov     [rbp+1F0h+var_258], rax
0x1800a5661  mov     [rsp+2F0h+var_290], rcx
0x1800a5666  movups  [rbp+1F0h+var_268], xmm0
0x1800a566a  lea     esi, [rax+3]
0x1800a566d  test    r14, r14
0x1800a5670  jz      loc_1800A5701
0x1800a5676  mov     rax, [r14]
0x1800a5679  mov     rcx, r14
0x1800a567c  mov     rax, [rax+70h]
0x1800a5680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5685  mov     rax, [r14]
0x1800a5688  mov     rcx, r14
0x1800a568b  mov     rax, [rax+20h]
0x1800a568f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5694  mov     edi, eax
0x1800a5696  cmp     eax, 200h
0x1800a569b  jle     short loc_1800A56C5
0x1800a569d  mov     edx, eax
0x1800a569f  lea     rcx, [rbp+1F0h+pSecurityDescriptor]
0x1800a56a3  call    ?SetSize@?$CTempBuffer@D$0CAA@@@QEAAXH@Z; CTempBuffer<char,512>::SetSize(int)
0x1800a56a8  mov     rdx, [rbp+1F0h+pSecurityDescriptor]
0x1800a56ac  test    rdx, rdx
0x1800a56af  jnz     short loc_1800A56C9
0x1800a56b1  cmp     [rbp+1F0h+var_248], 200h
0x1800a56b8  jle     loc_1800A5C9E
0x1800a56be  xor     ecx, ecx
0x1800a56c0  jmp     loc_1800A5BCF
0x1800a56c5  mov     rdx, [rbp+1F0h+pSecurityDescriptor]
0x1800a56c9  mov     rax, [r14]
0x1800a56cc  mov     r8d, edi
0x1800a56cf  mov     rcx, r14
0x1800a56d2  mov     rax, [rax+40h]
0x1800a56d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a56db  mov     rcx, [rbp+1F0h+pSecurityDescriptor]; pSecurityDescriptor
0x1800a56df  call    cs:__imp_IsValidSecurityDescriptor
0x1800a56e5  mov     rax, [rbp+1F0h+pSecurityDescriptor]
0x1800a56e9  lea     rcx, [rbp+1F0h+var_268]
0x1800a56ed  mov     qword ptr [rbp+1F0h+var_268+8], rax
0x1800a56f1  mov     [rsp+2F0h+var_290], rcx
0x1800a56f6  mov     dword ptr [rbp+1F0h+var_268], 18h
0x1800a56fd  mov     dword ptr [rbp+1F0h+var_258], r12d
0x1800a5701  mov     edi, 2
0x1800a5706  cmp     [rbp+1F0h+arg_30], r12d
0x1800a570d  jnz     short loc_1800A5715
0x1800a570f  cmp     [r13+28h], edi
0x1800a5713  jnz     short loc_1800A571B
0x1800a5715  mov     r12d, 1
0x1800a571b  mov     rax, [r15]
0x1800a571e  lea     rdx, [rsp+2F0h+var_288]
0x1800a5723  mov     r8, rcx
0x1800a5726  mov     r9d, r12d
0x1800a5729  mov     rcx, r15
0x1800a572c  mov     rax, [rax+0C8h]
0x1800a5733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5738  mov     rsi, rax
0x1800a573b  test    rbx, rbx
0x1800a573e  jz      short loc_1800A574F
0x1800a5740  mov     rcx, [rbx]
0x1800a5743  mov     rax, [rcx+10h]
0x1800a5747  mov     rcx, rbx
0x1800a574a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a574f  mov     rbx, rsi
0x1800a5752  mov     [rsp+2F0h+var_278], rbx
0x1800a5757  test    rsi, rsi
0x1800a575a  jz      short loc_1800A57A4
0x1800a575c  mov     r8, rsi
0x1800a575f  mov     edx, 1000005h
0x1800a5764  mov     rcx, r13
0x1800a5767  call    ?DispatchMessageW@CMsiOpExecute@@IEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@W4Bool@@@Z; CMsiOpExecute::DispatchMessageW(imtEnum,IMsiRecord &,Bool)
0x1800a576c  cmp     eax, edi
0x1800a576e  jz      short loc_1800A577C
0x1800a5770  mov     rcx, [rsp+2F0h+var_290]
0x1800a5775  cmp     eax, 4
0x1800a5778  jz      short loc_1800A571B
0x1800a577a  jmp     short loc_1800A57B5
0x1800a577c  cmp     [rbp+1F0h+var_248], 200h
0x1800a5783  jle     short loc_1800A578E
0x1800a5785  mov     rcx, [rbp+1F0h+pSecurityDescriptor]; void *
0x1800a5789  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a578e  mov     rax, [rsi]
0x1800a5791  mov     rcx, rsi
0x1800a5794  mov     rax, [rax+10h]
0x1800a5798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a579d  mov     eax, edi
0x1800a579f  jmp     loc_1800A5CAA
0x1800a57a4  cmp     [rbp+1F0h+arg_28], 0
0x1800a57ab  mov     eax, [rsp+2F0h+var_288]
0x1800a57af  jnz     short loc_1800A57D1
0x1800a57b1  test    eax, eax
0x1800a57b3  jnz     short loc_1800A57D9
0x1800a57b5  cmp     [rbp+1F0h+var_248], 200h
0x1800a57bc  jle     short loc_1800A57C7
0x1800a57be  mov     rcx, [rbp+1F0h+pSecurityDescriptor]; void *
0x1800a57c2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a57c7  mov     esi, 3
0x1800a57cc  jmp     loc_1800A5C9E
0x1800a57d1  test    eax, eax
0x1800a57d3  jz      loc_1800A58E9
0x1800a57d9  cmp     [rsp+2F0h+var_284], 0
0x1800a57de  jnz     loc_1800A58E9
0x1800a57e4  cmp     [rbp+1F0h+arg_38], 1
0x1800a57eb  jz      short loc_1800A57FB
0x1800a57ed  cmp     dword ptr [r13+1F4h], 5
0x1800a57f5  jz      loc_1800A58E9
0x1800a57fb  mov     rax, [r15]
0x1800a57fe  lea     rcx, [rsp+2F0h+var_290]
0x1800a5803  mov     [rsp+2F0h+var_290], 0
0x1800a580c  mov     rbx, [rax+58h]
0x1800a5810  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x1800a5815  mov     rdx, rax
0x1800a5818  mov     rcx, r15
0x1800a581b  mov     rax, rbx
0x1800a581e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5823  mov     rdx, rax
0x1800a5826  lea     rcx, [rsp+2F0h+var_278]
0x1800a582b  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x1800a5830  mov     r8, [rsp+2F0h+var_278]
0x1800a5835  test    r8, r8
0x1800a5838  jz      short loc_1800A5877
0x1800a583a  mov     edx, 1000000h
0x1800a583f  mov     rcx, r13
0x1800a5842  call    ?Message@CMsiOpExecute@@IEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiOpExecute::Message(imtEnum,IMsiRecord &)
0x1800a5847  lea     rcx, [rsp+2F0h+var_290]
0x1800a584c  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800a5851  cmp     [rbp+1F0h+var_248], 200h
0x1800a5858  jle     short loc_1800A5863
0x1800a585a  mov     rcx, [rbp+1F0h+pSecurityDescriptor]; void *
0x1800a585e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a5863  lea     rcx, [rsp+2F0h+var_278]
0x1800a5868  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800a586d  mov     eax, 3
0x1800a5872  jmp     loc_1800A5CAA
0x1800a5877  xor     ebx, ebx
0x1800a5879  cmp     [rsp+2F0h+var_288], ebx
0x1800a587d  jle     short loc_1800A58DB
0x1800a587f  mov     esi, [rsp+2F0h+var_280]
0x1800a5883  mov     rcx, [r13+8]
0x1800a5887  mov     r8d, esi
0x1800a588a  mov     rdx, [rsp+2F0h+var_290]
0x1800a588f  mov     rax, [rcx]
0x1800a5892  mov     rax, [rax+100h]
0x1800a5899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a589e  mov     rdx, rax
0x1800a58a1  lea     rcx, [rsp+2F0h+var_278]
0x1800a58a6  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x1800a58ab  mov     r8, [rsp+2F0h+var_278]
0x1800a58b0  test    r8, r8
0x1800a58b3  jz      short loc_1800A58C2
0x1800a58b5  mov     edx, 4000000h
0x1800a58ba  mov     rcx, r13
0x1800a58bd  call    ?Message@CMsiOpExecute@@IEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiOpExecute::Message(imtEnum,IMsiRecord &)
0x1800a58c2  mov     rcx, [rsp+2F0h+var_290]
0x1800a58c7  mov     rax, [rcx]
0x1800a58ca  mov     rax, [rax+70h]
0x1800a58ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a58d3  inc     ebx
0x1800a58d5  cmp     ebx, [rsp+2F0h+var_288]
0x1800a58d9  jl      short loc_1800A5883
0x1800a58db  lea     rcx, [rsp+2F0h+var_290]
0x1800a58e0  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800a58e5  mov     eax, [rsp+2F0h+var_288]
0x1800a58e9  test    r14, r14
0x1800a58ec  jz      loc_1800A5C87
0x1800a58f2  xor     r14d, r14d
0x1800a58f5  test    eax, eax
0x1800a58f7  jnz     loc_1800A5C87
0x1800a58fd  mov     rax, [r15]
0x1800a5900  mov     rcx, r15
0x1800a5903  mov     rax, [rax+38h]
0x1800a5907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a590c  mov     [rsp+2F0h+var_290], 0FFFFFFFFFFFFFFFFh
0x1800a5915  mov     rbx, rax
0x1800a5918  test    r12d, r12d
0x1800a591b  jz      loc_1800A5AF8
0x1800a5921  mov     dl, 1; bool
0x1800a5923  lea     rcx, [rsp+2F0h+var_280]; this
0x1800a5928  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x1800a592d  mov     rax, [rbx]
0x1800a5930  mov     rcx, rbx
0x1800a5933  mov     rax, [rax+50h]
0x1800a5937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a593c  lea     esi, [r14+3]
0x1800a5940  mov     [rsp+2F0h+hTemplateFile], r14; hTemplateFile
0x1800a5945  mov     r8d, esi; dwShareMode
0x1800a5948  mov     [rsp+2F0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1800a5950  xor     r9d, r9d; lpSecurityAttributes
0x1800a5953  mov     [rsp+2F0h+dwCreationDisposition], esi; dwCreationDisposition
0x1800a5957  mov     edx, 80000000h; dwDesiredAccess
0x1800a595c  mov     rcx, rax; lpFileName
0x1800a595f  call    cs:__imp_CreateFileW
0x1800a5965  mov     rdx, rax
0x1800a5968  lea     rcx, [rsp+2F0h+var_290]
0x1800a596d  call    ??4CHandle@@QEAAXPEAX@Z; CHandle::operator=(void *)
0x1800a5972  cmp     [rsp+2F0h+var_290], 0FFFFFFFFFFFFFFFFh
0x1800a5978  jnz     short loc_1800A59E4
0x1800a597a  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x1800a5981  jz      short loc_1800A59D5
0x1800a5983  mov     rax, [rbx]
0x1800a5986  mov     rcx, rbx
0x1800a5989  mov     rax, [rax+50h]
0x1800a598d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5992  lea     rcx, aNull; "(NULL)"
0x1800a5999  mov     [rsp+2F0h+var_298], r14; void *
0x1800a599e  mov     [rsp+2F0h+var_2A0], r14d; unsigned int
0x1800a59a3  lea     r9, aFolderIsNotAcc; "Folder is not accessible: %s"
0x1800a59aa  mov     [rsp+2F0h+var_2A8], rcx; unsigned __int16 *
0x1800a59af  xor     edx, edx; unsigned __int16
0x1800a59b1  mov     [rsp+2F0h+var_2B0], rcx; unsigned __int16 *
0x1800a59b6  xor     r8d, r8d; int
0x1800a59b9  mov     [rsp+2F0h+var_2B8], rcx; unsigned __int16 *
0x1800a59be  mov     [rsp+2F0h+hTemplateFile], rcx; unsigned __int16 *
0x1800a59c3  mov     qword ptr [rsp+2F0h+dwFlagsAndAttributes], rcx; unsigned __int16 *
0x1800a59c8  lea     ecx, [rsi+6]; int
0x1800a59cb  mov     qword ptr [rsp+2F0h+dwCreationDisposition], rax; unsigned __int16 *
0x1800a59d0  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800a59d5  lea     rcx, [rsp+2F0h+var_280]; this
0x1800a59da  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x1800a59df  jmp     loc_1800A5BA5
0x1800a59e4  mov     rax, [r15]
0x1800a59e7  mov     rcx, r15
0x1800a59ea  mov     rax, [rax+248h]
0x1800a59f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a59f6  test    al, al
0x1800a59f8  jz      short loc_1800A5A58
0x1800a59fa  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x1800a5a01  jz      short loc_1800A5A55
0x1800a5a03  mov     rax, [rbx]
0x1800a5a06  mov     rcx, rbx
0x1800a5a09  mov     rax, [rax+50h]
0x1800a5a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5a12  lea     rcx, aNull; "(NULL)"
0x1800a5a19  mov     [rsp+2F0h+var_298], r14; void *
0x1800a5a1e  mov     [rsp+2F0h+var_2A0], r14d; unsigned int
0x1800a5a23  lea     r9, aFolderHasJunct; "Folder has Junction: %s"
0x1800a5a2a  mov     [rsp+2F0h+var_2A8], rcx; unsigned __int16 *
0x1800a5a2f  xor     edx, edx; unsigned __int16
0x1800a5a31  mov     [rsp+2F0h+var_2B0], rcx; unsigned __int16 *
0x1800a5a36  xor     r8d, r8d; int
0x1800a5a39  mov     [rsp+2F0h+var_2B8], rcx; unsigned __int16 *
0x1800a5a3e  mov     [rsp+2F0h+hTemplateFile], rcx; unsigned __int16 *
0x1800a5a43  mov     qword ptr [rsp+2F0h+dwFlagsAndAttributes], rcx; unsigned __int16 *
0x1800a5a48  lea     ecx, [rdx+9]; int
0x1800a5a4b  mov     qword ptr [rsp+2F0h+dwCreationDisposition], rax; unsigned __int16 *
0x1800a5a50  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800a5a55  mov     r12d, r14d
0x1800a5a58  lea     rcx, [rsp+2F0h+var_280]; this
0x1800a5a5d  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x1800a5a62  mov     rcx, [rbp+1F0h+pSecurityDescriptor]; pSecurityDescriptor
0x1800a5a66  call    ?GetSecurityInformation@@YAKPEAX@Z; GetSecurityInformation(void *)
0x1800a5a6b  mov     r15d, 1
0x1800a5a71  mov     r14d, eax
0x1800a5a74  mov     dl, r15b; bool
0x1800a5a77  test    r12d, r12d
0x1800a5a7a  jz      loc_1800A5BD9
0x1800a5a80  lea     rcx, [rbp+1F0h+var_270]; this
0x1800a5a84  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x1800a5a89  mov     dl, r15b
0x1800a5a8c  mov     ecx, r15d
0x1800a5a8f  call    ?RefCountedTokenPrivilegesCore@@YA_NW4itkpEnum@@_N@Z; RefCountedTokenPrivilegesCore(itkpEnum,bool)
0x1800a5a94  test    al, al
0x1800a5a96  lea     rcx, [rsp+2F0h+var_280]
0x1800a5a9b  mov     r8d, r14d
0x1800a5a9e  cmovnz  edi, r15d
0x1800a5aa2  shr     r8d, 3
0x1800a5aa6  and     r8d, r15d
0x1800a5aa9  mov     [rsp+2F0h+var_284], edi
0x1800a5aad  call    ??0CRefCountedTokenPrivileges@@QEAA@W4itkpEnum@@W4Bool@@@Z; CRefCountedTokenPrivileges::CRefCountedTokenPrivileges(itkpEnum,Bool)
  ... truncated ...
```
