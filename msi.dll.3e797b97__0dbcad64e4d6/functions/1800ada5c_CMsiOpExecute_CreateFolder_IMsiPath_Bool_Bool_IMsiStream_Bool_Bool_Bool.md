# CMsiOpExecute::CreateFolder(IMsiPath &,Bool,Bool,IMsiStream *,Bool,Bool,Bool)

- ea: `0x1800ada5c`
- end: `0x1800ae175`
- name: `?CreateFolder@CMsiOpExecute@@IEAA?AW4iesEnum@@AEAVIMsiPath@@W4Bool@@1PEAVIMsiStream@@111@Z`
- size: `1817`
- prototype: ``
- caller_count: `10`
- callee_count: `21`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800681e4`
- `0x180068e88`
- `0x1800aaffc`
- `0x1800ebd64`
- `0x18014bc24`
- `0x1801e7568`
- `0x1801fd660`
- `0x180200180`
- `0x180200c20`
- `0x180201b50`

## callees

- `0x180003b10`
- `0x180005af8`
- `0x18000c4bc`
- `0x180014528`
- `0x180019cc0`
- `0x18002e870`
- `0x180038e70`
- `0x180067fec`
- `0x18007adb4`
- `0x18007b9e8`
- `0x18007f4c8`
- `0x1800ada5c`
- `0x18013d2f0`
- `0x180149a8c`
- `0x18014ae8c`
- `0x18014fcb8`
- `0x18015a7c0`
- `0x18017381c`
- `0x1802651ea`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!IsValidSecurityDescriptor` at `0x1800adb5b`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x1800adb5b`
- `ADVAPI32!SetFileSecurityW` at `0x1800adf56`
- `ADVAPI32!SetFileSecurityW` at `0x1800ae0af`
- `ADVAPI32!SetFileSecurityW` at `0x1800adf56`
- `ADVAPI32!SetFileSecurityW` at `0x1800ae0af`
- `KERNEL32!GetLastError` at `0x1800ae0e7`
- `KERNEL32!GetLastError` at `0x1800ae0e7`
- `KERNEL32!CreateFileW` at `0x1800adde1`
- `KERNEL32!CreateFileW` at `0x1800adfb9`
- `KERNEL32!CreateFileW` at `0x1800adde1`
- `KERNEL32!CreateFileW` at `0x1800adfb9`

## string_xrefs

- `0x1800ade2b`: `Folder is not accessible: %s`
- `0x1800ae007`: `Folder is not accessible: %s`
- `0x1800adeab`: `Folder has Junction: %s`

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
0x1800ada5c  mov     [rsp-8+arg_10], rbx
0x1800ada61  push    rbp
0x1800ada62  push    rsi
0x1800ada63  push    rdi
0x1800ada64  push    r12
0x1800ada66  push    r13
0x1800ada68  push    r14
0x1800ada6a  push    r15
0x1800ada6c  lea     rbp, [rsp-1C0h]
0x1800ada74  sub     rsp, 2C0h
0x1800ada7b  mov     rax, cs:__security_cookie
0x1800ada82  xor     rax, rsp
0x1800ada85  mov     [rbp+1F0h+var_40], rax
0x1800ada8c  mov     r14, [rbp+1F0h+arg_20]
0x1800ada93  xor     r12d, r12d
0x1800ada96  mov     [rsp+2F0h+var_284], r8d
0x1800ada9b  mov     r15, rdx
0x1800ada9e  mov     r13, rcx
0x1800adaa1  mov     [rsp+2F0h+var_280], r9d
0x1800adaa6  mov     edi, 200h
0x1800adaab  mov     [rsp+2F0h+var_288], r12d
0x1800adab0  mov     ebx, r12d
0x1800adab3  lea     rcx, [rbp+1F0h+var_240]; void *
0x1800adab7  mov     r8d, edi; Size
0x1800adaba  mov     [rsp+2F0h+var_278], rbx
0x1800adabf  xor     edx, edx; Val
0x1800adac1  call    memset_0
0x1800adac6  lea     rax, [rbp+1F0h+var_240]
0x1800adaca  mov     [rbp+1F0h+var_248], edi
0x1800adacd  mov     [rbp+1F0h+pSecurityDescriptor], rax
0x1800adad1  xorps   xmm0, xmm0
0x1800adad4  xor     eax, eax
0x1800adad6  mov     ecx, r12d
0x1800adad9  mov     [rbp+1F0h+var_258], rax
0x1800adadd  mov     [rsp+2F0h+var_290], rcx
0x1800adae2  movups  [rbp+1F0h+var_268], xmm0
0x1800adae6  lea     esi, [rax+3]
0x1800adae9  test    r14, r14
0x1800adaec  jz      loc_1800ADB83
0x1800adaf2  mov     rax, [r14]
0x1800adaf5  mov     rcx, r14
0x1800adaf8  mov     rax, [rax+70h]
0x1800adafc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adb01  mov     rax, [r14]
0x1800adb04  mov     rcx, r14
0x1800adb07  mov     rax, [rax+20h]
0x1800adb0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adb10  mov     edi, eax
0x1800adb12  cmp     eax, 200h
0x1800adb17  jle     short loc_1800ADB41
0x1800adb19  mov     edx, eax
0x1800adb1b  lea     rcx, [rbp+1F0h+pSecurityDescriptor]
0x1800adb1f  call    ?SetSize@?$CTempBuffer@D$0CAA@@@QEAAXH@Z; CTempBuffer<char,512>::SetSize(int)
0x1800adb24  mov     rdx, [rbp+1F0h+pSecurityDescriptor]
0x1800adb28  test    rdx, rdx
0x1800adb2b  jnz     short loc_1800ADB45
0x1800adb2d  cmp     [rbp+1F0h+var_248], 200h
0x1800adb34  jle     loc_1800AE13E
0x1800adb3a  xor     ecx, ecx
0x1800adb3c  jmp     loc_1800AE063
0x1800adb41  mov     rdx, [rbp+1F0h+pSecurityDescriptor]
0x1800adb45  mov     rax, [r14]
0x1800adb48  mov     r8d, edi
0x1800adb4b  mov     rcx, r14
0x1800adb4e  mov     rax, [rax+40h]
0x1800adb52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adb57  mov     rcx, [rbp+1F0h+pSecurityDescriptor]; pSecurityDescriptor
0x1800adb5b  call    cs:__imp_IsValidSecurityDescriptor
0x1800adb62  nop     dword ptr [rax+rax+00h]
0x1800adb67  mov     rax, [rbp+1F0h+pSecurityDescriptor]
0x1800adb6b  lea     rcx, [rbp+1F0h+var_268]
0x1800adb6f  mov     qword ptr [rbp+1F0h+var_268+8], rax
0x1800adb73  mov     [rsp+2F0h+var_290], rcx
0x1800adb78  mov     dword ptr [rbp+1F0h+var_268], 18h
0x1800adb7f  mov     dword ptr [rbp+1F0h+var_258], r12d
0x1800adb83  mov     edi, 2
0x1800adb88  cmp     [rbp+1F0h+arg_30], r12d
0x1800adb8f  jnz     short loc_1800ADB97
0x1800adb91  cmp     [r13+28h], edi
0x1800adb95  jnz     short loc_1800ADB9D
0x1800adb97  mov     r12d, 1
0x1800adb9d  mov     rax, [r15]
0x1800adba0  lea     rdx, [rsp+2F0h+var_288]
0x1800adba5  mov     r8, rcx
0x1800adba8  mov     r9d, r12d
0x1800adbab  mov     rcx, r15
0x1800adbae  mov     rax, [rax+0C8h]
0x1800adbb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adbba  mov     rsi, rax
0x1800adbbd  test    rbx, rbx
0x1800adbc0  jz      short loc_1800ADBD1
0x1800adbc2  mov     rcx, [rbx]
0x1800adbc5  mov     rax, [rcx+10h]
0x1800adbc9  mov     rcx, rbx
0x1800adbcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adbd1  mov     rbx, rsi
0x1800adbd4  mov     [rsp+2F0h+var_278], rbx
0x1800adbd9  test    rsi, rsi
0x1800adbdc  jz      short loc_1800ADC26
0x1800adbde  mov     r8, rsi
0x1800adbe1  mov     edx, 1000005h
0x1800adbe6  mov     rcx, r13
0x1800adbe9  call    ?DispatchMessageW@CMsiOpExecute@@IEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@W4Bool@@@Z; CMsiOpExecute::DispatchMessageW(imtEnum,IMsiRecord &,Bool)
0x1800adbee  cmp     eax, edi
0x1800adbf0  jz      short loc_1800ADBFE
0x1800adbf2  mov     rcx, [rsp+2F0h+var_290]
0x1800adbf7  cmp     eax, 4
0x1800adbfa  jz      short loc_1800ADB9D
0x1800adbfc  jmp     short loc_1800ADC37
0x1800adbfe  cmp     [rbp+1F0h+var_248], 200h
0x1800adc05  jle     short loc_1800ADC10
0x1800adc07  mov     rcx, [rbp+1F0h+pSecurityDescriptor]; void *
0x1800adc0b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800adc10  mov     rax, [rsi]
0x1800adc13  mov     rcx, rsi
0x1800adc16  mov     rax, [rax+10h]
0x1800adc1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adc1f  mov     eax, edi
0x1800adc21  jmp     loc_1800AE14A
0x1800adc26  cmp     [rbp+1F0h+arg_28], 0
0x1800adc2d  mov     eax, [rsp+2F0h+var_288]
0x1800adc31  jnz     short loc_1800ADC53
0x1800adc33  test    eax, eax
0x1800adc35  jnz     short loc_1800ADC5B
0x1800adc37  cmp     [rbp+1F0h+var_248], 200h
0x1800adc3e  jle     short loc_1800ADC49
0x1800adc40  mov     rcx, [rbp+1F0h+pSecurityDescriptor]; void *
0x1800adc44  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800adc49  mov     esi, 3
0x1800adc4e  jmp     loc_1800AE13E
0x1800adc53  test    eax, eax
0x1800adc55  jz      loc_1800ADD6B
0x1800adc5b  cmp     [rsp+2F0h+var_284], 0
0x1800adc60  jnz     loc_1800ADD6B
0x1800adc66  cmp     [rbp+1F0h+arg_38], 1
0x1800adc6d  jz      short loc_1800ADC7D
0x1800adc6f  cmp     dword ptr [r13+1F4h], 5
0x1800adc77  jz      loc_1800ADD6B
0x1800adc7d  mov     rax, [r15]
0x1800adc80  lea     rcx, [rsp+2F0h+var_290]
0x1800adc85  mov     [rsp+2F0h+var_290], 0
0x1800adc8e  mov     rbx, [rax+58h]
0x1800adc92  call    ??4?$CComPointer@VIEnumMsiRecord@@@@QEAAAEAV0@PEAVIEnumMsiRecord@@@Z; CComPointer<IEnumMsiRecord>::operator=(IEnumMsiRecord *)
0x1800adc97  mov     rdx, rax
0x1800adc9a  mov     rcx, r15
0x1800adc9d  mov     rax, rbx
0x1800adca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adca5  mov     rdx, rax
0x1800adca8  lea     rcx, [rsp+2F0h+var_278]
0x1800adcad  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x1800adcb2  mov     r8, [rsp+2F0h+var_278]
0x1800adcb7  test    r8, r8
0x1800adcba  jz      short loc_1800ADCF9
0x1800adcbc  mov     edx, 1000000h
0x1800adcc1  mov     rcx, r13
0x1800adcc4  call    ?Message@CMsiOpExecute@@IEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiOpExecute::Message(imtEnum,IMsiRecord &)
0x1800adcc9  lea     rcx, [rsp+2F0h+var_290]
0x1800adcce  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800adcd3  cmp     [rbp+1F0h+var_248], 200h
0x1800adcda  jle     short loc_1800ADCE5
0x1800adcdc  mov     rcx, [rbp+1F0h+pSecurityDescriptor]; void *
0x1800adce0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800adce5  lea     rcx, [rsp+2F0h+var_278]
0x1800adcea  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800adcef  mov     eax, 3
0x1800adcf4  jmp     loc_1800AE14A
0x1800adcf9  xor     ebx, ebx
0x1800adcfb  cmp     [rsp+2F0h+var_288], ebx
0x1800adcff  jle     short loc_1800ADD5D
0x1800add01  mov     esi, [rsp+2F0h+var_280]
0x1800add05  mov     rcx, [r13+8]
0x1800add09  mov     r8d, esi
0x1800add0c  mov     rdx, [rsp+2F0h+var_290]
0x1800add11  mov     rax, [rcx]
0x1800add14  mov     rax, [rax+100h]
0x1800add1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800add20  mov     rdx, rax
0x1800add23  lea     rcx, [rsp+2F0h+var_278]
0x1800add28  call    ??4?$CComPointer@VIMsiDatabase@@@@QEAAAEAV0@PEAVIMsiDatabase@@@Z; CComPointer<IMsiDatabase>::operator=(IMsiDatabase *)
0x1800add2d  mov     r8, [rsp+2F0h+var_278]
0x1800add32  test    r8, r8
0x1800add35  jz      short loc_1800ADD44
0x1800add37  mov     edx, 4000000h
0x1800add3c  mov     rcx, r13
0x1800add3f  call    ?Message@CMsiOpExecute@@IEAA?AW4imsEnum@@W4imtEnum@@AEAVIMsiRecord@@@Z; CMsiOpExecute::Message(imtEnum,IMsiRecord &)
0x1800add44  mov     rcx, [rsp+2F0h+var_290]
0x1800add49  mov     rax, [rcx]
0x1800add4c  mov     rax, [rax+70h]
0x1800add50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800add55  inc     ebx
0x1800add57  cmp     ebx, [rsp+2F0h+var_288]
0x1800add5b  jl      short loc_1800ADD05
0x1800add5d  lea     rcx, [rsp+2F0h+var_290]
0x1800add62  call    ??1?$CComPointer@VIMsiSelectionManager@@@@QEAA@XZ; CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(void)
0x1800add67  mov     eax, [rsp+2F0h+var_288]
0x1800add6b  test    r14, r14
0x1800add6e  jz      loc_1800AE127
0x1800add74  xor     r14d, r14d
0x1800add77  test    eax, eax
0x1800add79  jnz     loc_1800AE127
0x1800add7f  mov     rax, [r15]
0x1800add82  mov     rcx, r15
0x1800add85  mov     rax, [rax+38h]
0x1800add89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800add8e  mov     [rsp+2F0h+var_290], 0FFFFFFFFFFFFFFFFh
0x1800add97  mov     rbx, rax
0x1800add9a  test    r12d, r12d
0x1800add9d  jz      loc_1800ADF86
0x1800adda3  mov     dl, 1; bool
0x1800adda5  lea     rcx, [rsp+2F0h+var_280]; this
0x1800addaa  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x1800addaf  mov     rax, [rbx]
0x1800addb2  mov     rcx, rbx
0x1800addb5  mov     rax, [rax+50h]
0x1800addb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800addbe  lea     esi, [r14+3]
0x1800addc2  mov     [rsp+2F0h+hTemplateFile], r14; hTemplateFile
0x1800addc7  mov     r8d, esi; dwShareMode
0x1800addca  mov     [rsp+2F0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1800addd2  xor     r9d, r9d; lpSecurityAttributes
0x1800addd5  mov     [rsp+2F0h+dwCreationDisposition], esi; dwCreationDisposition
0x1800addd9  mov     edx, 80000000h; dwDesiredAccess
0x1800addde  mov     rcx, rax; lpFileName
0x1800adde1  call    cs:__imp_CreateFileW
0x1800adde8  nop     dword ptr [rax+rax+00h]
0x1800added  mov     rdx, rax
0x1800addf0  lea     rcx, [rsp+2F0h+var_290]
0x1800addf5  call    ??4CHandle@@QEAAXPEAX@Z; CHandle::operator=(void *)
0x1800addfa  cmp     [rsp+2F0h+var_290], 0FFFFFFFFFFFFFFFFh
0x1800ade00  jnz     short loc_1800ADE6C
0x1800ade02  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x1800ade09  jz      short loc_1800ADE5D
0x1800ade0b  mov     rax, [rbx]
0x1800ade0e  mov     rcx, rbx
0x1800ade11  mov     rax, [rax+50h]
0x1800ade15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ade1a  lea     rcx, aNull; "(NULL)"
0x1800ade21  mov     [rsp+2F0h+var_298], r14; void *
0x1800ade26  mov     [rsp+2F0h+var_2A0], r14d; unsigned int
0x1800ade2b  lea     r9, aFolderIsNotAcc; "Folder is not accessible: %s"
0x1800ade32  mov     [rsp+2F0h+var_2A8], rcx; unsigned __int16 *
0x1800ade37  xor     edx, edx; unsigned __int16
0x1800ade39  mov     [rsp+2F0h+var_2B0], rcx; unsigned __int16 *
0x1800ade3e  xor     r8d, r8d; int
0x1800ade41  mov     [rsp+2F0h+var_2B8], rcx; unsigned __int16 *
0x1800ade46  mov     [rsp+2F0h+hTemplateFile], rcx; unsigned __int16 *
0x1800ade4b  mov     qword ptr [rsp+2F0h+dwFlagsAndAttributes], rcx; unsigned __int16 *
0x1800ade50  lea     ecx, [rsi+6]; int
0x1800ade53  mov     qword ptr [rsp+2F0h+dwCreationDisposition], rax; unsigned __int16 *
0x1800ade58  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800ade5d  lea     rcx, [rsp+2F0h+var_280]; this
0x1800ade62  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x1800ade67  jmp     loc_1800AE039
0x1800ade6c  mov     rax, [r15]
0x1800ade6f  mov     rcx, r15
0x1800ade72  mov     rax, [rax+248h]
0x1800ade79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ade7e  test    al, al
0x1800ade80  jz      short loc_1800ADEE0
0x1800ade82  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x1800ade89  jz      short loc_1800ADEDD
0x1800ade8b  mov     rax, [rbx]
0x1800ade8e  mov     rcx, rbx
0x1800ade91  mov     rax, [rax+50h]
0x1800ade95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ade9a  lea     rcx, aNull; "(NULL)"
0x1800adea1  mov     [rsp+2F0h+var_298], r14; void *
0x1800adea6  mov     [rsp+2F0h+var_2A0], r14d; unsigned int
0x1800adeab  lea     r9, aFolderHasJunct; "Folder has Junction: %s"
0x1800adeb2  mov     [rsp+2F0h+var_2A8], rcx; unsigned __int16 *
0x1800adeb7  xor     edx, edx; unsigned __int16
0x1800adeb9  mov     [rsp+2F0h+var_2B0], rcx; unsigned __int16 *
0x1800adebe  xor     r8d, r8d; int
0x1800adec1  mov     [rsp+2F0h+var_2B8], rcx; unsigned __int16 *
0x1800adec6  mov     [rsp+2F0h+hTemplateFile], rcx; unsigned __int16 *
0x1800adecb  mov     qword ptr [rsp+2F0h+dwFlagsAndAttributes], rcx; unsigned __int16 *
0x1800aded0  lea     ecx, [rdx+9]; int
0x1800aded3  mov     qword ptr [rsp+2F0h+dwCreationDisposition], rax; unsigned __int16 *
0x1800aded8  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800adedd  mov     r12d, r14d
0x1800adee0  lea     rcx, [rsp+2F0h+var_280]; this
0x1800adee5  call    ??1CElevate@@QEAA@XZ; CElevate::~CElevate(void)
0x1800adeea  mov     rcx, [rbp+1F0h+pSecurityDescriptor]; pSecurityDescriptor
0x1800adeee  call    ?GetSecurityInformation@@YAKPEAX@Z; GetSecurityInformation(void *)
0x1800adef3  mov     r15d, 1
0x1800adef9  mov     r14d, eax
0x1800adefc  mov     dl, r15b; bool
0x1800adeff  test    r12d, r12d
0x1800adf02  jz      loc_1800AE06D
0x1800adf08  lea     rcx, [rbp+1F0h+var_270]; this
0x1800adf0c  call    ??0CElevate@@QEAA@_N@Z; CElevate::CElevate(bool)
0x1800adf11  mov     dl, r15b
0x1800adf14  mov     ecx, r15d
0x1800adf17  call    ?RefCountedTokenPrivilegesCore@@YA_NW4itkpEnum@@_N@Z; RefCountedTokenPrivilegesCore(itkpEnum,bool)
0x1800adf1c  test    al, al
0x1800adf1e  lea     rcx, [rsp+2F0h+var_280]
0x1800adf23  mov     r8d, r14d
0x1800adf26  cmovnz  edi, r15d
0x1800adf2a  shr     r8d, 3
0x1800adf2e  and     r8d, r15d
  ... truncated ...
```
