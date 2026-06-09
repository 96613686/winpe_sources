# CryptSIPRetrieveSubjectGuid

- ea: `0x180024490`
- end: `0x1800248d9`
- name: `CryptSIPRetrieveSubjectGuid`
- size: `1097`
- prototype: `BOOL __stdcall(LPCWSTR FileName, HANDLE hFileIn, GUID *pgSubject)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18002ce84`

## callees

- `0x180024490`
- `0x1800248e0`
- `0x180025000`
- `0x18002c860`
- `0x1800450c0`
- `0x180115094`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024890`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800247ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002488a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800248ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800247ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002488a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800248ac`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800244f5`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800244f5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024833`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024833`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800247d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024863`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800247d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024863`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180024572`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180024798`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180024572`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180024798`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180024778`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800247c5`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180024778`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800247c5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x180024542`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x180024542`

## pseudocode

```c
BOOL __stdcall CryptSIPRetrieveSubjectGuid(LPCWSTR FileName, HANDLE hFileIn, GUID *pgSubject)
{
  char *FileW; // r15
  HANDLE FileMappingA; // r13
  _DWORD *v6; // r14
  BOOL v7; // r12d
  unsigned int MaxHeaderBytesToMapRegValue; // eax
  DWORD LowPart; // ebx
  int *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rdx
  DWORD v14; // ebx
  const CERT_CONTEXT *Context; // rbx
  DWORD v16; // r9d
  PCERT_INFO pCertInfo; // rcx
  DWORD LastError; // ecx
  int v21; // [rsp+E0h] [rbp+18h]
  union _LARGE_INTEGER FileSize; // [rsp+E8h] [rbp+20h] BYREF

  FileW = (char *)hFileIn;
  FileSize.QuadPart = 0;
  FileMappingA = 0;
  v21 = 0;
  v6 = 0;
  if ( !pgSubject )
    goto LABEL_51;
  *pgSubject = 0;
  if ( (((unsigned __int64)hFileIn + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v7 = 1;
  }
  else
  {
    if ( !FileName )
      goto LABEL_51;
    v7 = 1;
    FileW = (char *)CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    if ( FileW == (char *)-1LL )
    {
LABEL_50:
      LastError = GetLastError();
      goto LABEL_49;
    }
    v21 = 1;
  }
  if ( !GetFileSizeEx(FileW, &FileSize) || FileSize.QuadPart < 4 )
    goto LABEL_51;
  MaxHeaderBytesToMapRegValue = I_CryptGetMaxHeaderBytesToMapRegValue();
  LowPart = FileSize.LowPart;
  if ( FileSize.QuadPart >= MaxHeaderBytesToMapRegValue )
    LowPart = I_CryptGetMaxHeaderBytesToMapRegValue();
  FileMappingA = CreateFileMappingA(FileW, 0, 2u, 0, 0, 0);
  if ( !FileMappingA )
    goto LABEL_50;
  v10 = (int *)MapViewOfFile(FileMappingA, 4u, 0, 0, LowPart);
  v6 = v10;
  if ( !v10 )
    goto LABEL_50;
  if ( *(_WORD *)v10 == 23117 && LowPart >= 0x40 && (v11 = v10[15], (unsigned int)v11 <= 0x7FFFFFBE) )
  {
    v12 = (unsigned int)(v11 + 64);
    v13 = LowPart;
    if ( (unsigned int)v12 < LowPart && v12 + 264 <= (unsigned __int64)LowPart && *(_DWORD *)((char *)v6 + v11) == 17744 )
    {
      pgSubject->Data1 = -964056392;
      *(_DWORD *)&pgSubject->Data2 = 298880632;
      *(_DWORD *)pgSubject->Data4 = -1073723508;
      *(_DWORD *)&pgSubject->Data4[4] = -292175281;
      v14 = -2147418113;
      goto LABEL_34;
    }
  }
  else
  {
    v13 = LowPart;
  }
  if ( *v6 == 1178817357 )
  {
    pgSubject->Data1 = -964056390;
    *(_DWORD *)&pgSubject->Data2 = 298880632;
    *(_DWORD *)pgSubject->Data4 = -1073723508;
    *(_DWORD *)&pgSubject->Data4[4] = -292175281;
    v14 = -2147418113;
    goto LABEL_34;
  }
  if ( *(_BYTE *)v6 != 48 )
    goto LABEL_47;
  if ( FileSize.HighPart )
  {
LABEL_51:
    LastError = 87;
    goto LABEL_49;
  }
  Context = 0;
  v16 = FileSize.LowPart;
  if ( FileSize.LowPart != v13 )
  {
    UnmapViewOfFile(v6);
    v6 = MapViewOfFile(FileMappingA, 4u, 0, 0, FileSize.QuadPart);
    v16 = FileSize.LowPart;
  }
  if ( v6 )
    Context = (const CERT_CONTEXT *)CertCreateContext(3u, 0x10001u, (const BYTE *)v6, v16, 0xDu, 0);
  if ( Context )
  {
    pCertInfo = Context->pCertInfo;
    if ( pCertInfo->SerialNumber.cbData
      && !strcmp_0(*(const char **)pCertInfo->SerialNumber.pbData, "1.3.6.1.4.1.311.12.1.1") )
    {
      pgSubject->Data1 = -566945213;
      *(_DWORD *)&pgSubject->Data2 = 298880601;
      *(_DWORD *)pgSubject->Data4 = -1073723508;
      *(_DWORD *)&pgSubject->Data4[4] = -292175281;
      CertFreeCertificateContext(Context);
      v14 = -2147418113;
    }
    else
    {
      pgSubject->Data1 = -1683612353;
      *(_DWORD *)&pgSubject->Data2 = 298903354;
      *(_DWORD *)pgSubject->Data4 = -1073687924;
      *(_DWORD *)&pgSubject->Data4[4] = -292175281;
      CertFreeCertificateContext(Context);
      v14 = -2147418113;
    }
    goto LABEL_34;
  }
LABEL_47:
  if ( !(unsigned int)_QueryRegisteredIsMyFileType(FileW, FileName, pgSubject) )
  {
    LastError = -2146762749;
LABEL_49:
    SetLastError(LastError);
    v14 = GetLastError();
    v7 = 0;
    goto LABEL_34;
  }
  v14 = -2147418113;
LABEL_34:
  if ( v6 )
    UnmapViewOfFile(v6);
  if ( FileMappingA )
    CloseHandle(FileMappingA);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL && v21 )
    CloseHandle(FileW);
  if ( !v7 )
    SetLastError(v14);
  return v7;
}

```

## disassembly

```asm
0x180024490  mov     rax, rsp
0x180024493  mov     [rax+10h], rdx
0x180024497  mov     [rax+8], rcx
0x18002449b  push    rbx
0x18002449c  push    rsi
0x18002449d  push    rdi
0x18002449e  push    r12
0x1800244a0  push    r13
0x1800244a2  push    r14
0x1800244a4  push    r15
0x1800244a6  sub     rsp, 90h
0x1800244ad  mov     rsi, r8
0x1800244b0  mov     r15, rdx
0x1800244b3  xor     edi, edi
0x1800244b5  mov     [rax+20h], rdi
0x1800244b9  mov     r13d, edi
0x1800244bc  mov     [rsp+0C8h+arg_10], edi
0x1800244c3  mov     r14d, edi
0x1800244c6  test    r8, r8
0x1800244c9  jz      loc_1800248C8
0x1800244cf  xorps   xmm0, xmm0
0x1800244d2  movups  xmmword ptr [r8], xmm0
0x1800244d6  lea     rax, [rdx+1]
0x1800244da  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800244e0  jz      loc_180024806
0x1800244e6  lea     r12d, [rdi+1]
0x1800244ea  lea     rdx, [rsp+0C8h+FileSize]; lpFileSize
0x1800244f2  mov     rcx, r15; hFile
0x1800244f5  call    cs:__imp_GetFileSizeEx
0x1800244fb  test    eax, eax
0x1800244fd  jz      loc_1800248C8
0x180024503  cmp     qword ptr [rsp+0C8h+FileSize], 4
0x18002450c  jl      loc_1800248C8
0x180024512  call    I_CryptGetMaxHeaderBytesToMapRegValue
0x180024517  mov     eax, eax
0x180024519  mov     rbx, qword ptr [rsp+0C8h+FileSize]
0x180024521  cmp     rbx, rax
0x180024524  jl      short loc_18002452D
0x180024526  call    I_CryptGetMaxHeaderBytesToMapRegValue
0x18002452b  mov     ebx, eax
0x18002452d  mov     [rsp+0C8h+lpName], rdi; lpName
0x180024532  mov     [rsp+0C8h+dwMaximumSizeLow], edi; dwMaximumSizeLow
0x180024536  xor     r9d, r9d; dwMaximumSizeHigh
0x180024539  xor     edx, edx; lpFileMappingAttributes
0x18002453b  lea     r8d, [r9+2]; flProtect
0x18002453f  mov     rcx, r15; hFile
0x180024542  call    cs:__imp_CreateFileMappingA
0x180024548  mov     r13, rax
0x18002454b  mov     [rsp+0C8h+var_70], rax
0x180024550  test    rax, rax
0x180024553  jz      loc_1800248A0
0x180024559  mov     eax, ebx
0x18002455b  mov     [rsp+0C8h+var_88], rax
0x180024560  mov     qword ptr [rsp+0C8h+dwMaximumSizeLow], rax; dwNumberOfBytesToMap
0x180024565  xor     r9d, r9d; dwFileOffsetLow
0x180024568  xor     r8d, r8d; dwFileOffsetHigh
0x18002456b  lea     edx, [r9+4]; dwDesiredAccess
0x18002456f  mov     rcx, r13; hFileMappingObject
0x180024572  call    cs:__imp_MapViewOfFile
0x180024578  mov     r14, rax
0x18002457b  mov     [rsp+0C8h+var_78], rax
0x180024580  test    rax, rax
0x180024583  jz      loc_1800248A0
0x180024589  mov     edx, 5A4Dh
0x18002458e  cmp     [rax], dx
0x180024591  jnz     short loc_180024607
0x180024593  cmp     ebx, 40h ; '@'
0x180024596  jb      short loc_180024607
0x180024598  movsxd  rcx, dword ptr [rax+3Ch]
0x18002459c  cmp     ecx, 7FFFFFBEh
0x1800245a2  ja      short loc_180024607
0x1800245a4  lea     eax, [rcx+40h]
0x1800245a7  mov     rdx, [rsp+0C8h+var_88]
0x1800245ac  cmp     eax, ebx
0x1800245ae  jnb     short loc_18002460C
0x1800245b0  add     rax, 108h
0x1800245b6  cmp     rax, rdx
0x1800245b9  ja      short loc_18002460C
0x1800245bb  cmp     dword ptr [rcx+r14], 4550h
0x1800245c3  jnz     short loc_18002460C
0x1800245c5  mov     edx, 0C689AAB8h
0x1800245ca  mov     dword ptr [rsp+0C8h+var_88], edx
0x1800245ce  mov     dword ptr [rsp+0C8h+var_88+4], 11D08E78h
0x1800245d6  mov     [rsp+0C8h+var_80], 0C000478Ch
0x1800245de  mov     [rsp+0C8h+var_7C], 0EE95C24Fh
0x1800245e6  mov     [rsi], edx
0x1800245e8  mov     dword ptr [rsi+4], 11D08E78h
0x1800245ef  mov     dword ptr [rsi+8], 0C000478Ch
0x1800245f6  mov     dword ptr [rsi+0Ch], 0EE95C24Fh
0x1800245fd  mov     ebx, 8000FFFFh
0x180024602  jmp     loc_1800247BD
0x180024607  mov     rdx, [rsp+0C8h+var_88]
0x18002460c  cmp     dword ptr [r14], 4643534Dh
0x180024613  jz      short loc_180024620
0x180024615  cmp     byte ptr [r14], 30h ; '0'
0x180024619  jz      short loc_180024662
0x18002461b  jmp     loc_1800247B3
0x180024620  mov     edx, 0C689AABAh
0x180024625  mov     [rsp+0C8h+var_68], edx
0x180024629  mov     [rsp+0C8h+var_64], 11D08E78h
0x180024631  mov     [rsp+0C8h+var_60], 0C000478Ch
0x180024639  mov     [rsp+0C8h+var_5C], 0EE95C24Fh
0x180024641  mov     [rsi], edx
0x180024643  mov     dword ptr [rsi+4], 11D08E78h
0x18002464a  mov     dword ptr [rsi+8], 0C000478Ch
0x180024651  mov     dword ptr [rsi+0Ch], 0EE95C24Fh
0x180024658  mov     ebx, 8000FFFFh
0x18002465d  jmp     loc_1800247BD
0x180024662  cmp     dword ptr [rsp+0C8h+FileSize+4], edi
0x180024669  jnz     loc_180024770
0x18002466f  mov     rbx, rdi
0x180024672  mov     r9, qword ptr [rsp+0C8h+FileSize]; cbEncoded
0x18002467a  cmp     r9, rdx
0x18002467d  jnz     loc_180024775
0x180024683  test    r14, r14
0x180024686  jz      short loc_1800246AA
0x180024688  mov     [rsp+0C8h+lpName], rdi; pCreatePara
0x18002468d  mov     [rsp+0C8h+dwMaximumSizeLow], 0Dh; dwFlags
0x180024695  mov     r8, r14; pbEncoded
0x180024698  mov     edx, 10001h; dwEncodingType
0x18002469d  mov     ecx, 3; dwContextType
0x1800246a2  call    CertCreateContext
0x1800246a7  mov     rbx, rax
0x1800246aa  test    rbx, rbx
0x1800246ad  jz      loc_1800247B3
0x1800246b3  mov     rcx, [rbx+18h]
0x1800246b7  cmp     [rcx+8], edi
0x1800246ba  jz      short loc_18002471D
0x1800246bc  mov     rcx, [rcx+10h]
0x1800246c0  lea     rdx, a1361413111211; "1.3.6.1.4.1.311.12.1.1"
0x1800246c7  mov     rcx, [rcx]; Str1
0x1800246ca  call    strcmp_0
0x1800246cf  test    eax, eax
0x1800246d1  jnz     short loc_18002471D
0x1800246d3  mov     ecx, 0DE351A43h
0x1800246d8  mov     [rsp+0C8h+var_58], ecx
0x1800246dc  mov     [rsp+0C8h+var_54], 11D08E59h
0x1800246e4  mov     [rsp+0C8h+var_50], 0C000478Ch
0x1800246ec  mov     [rsp+0C8h+var_4C], 0EE95C24Fh
0x1800246f4  mov     [rsi], ecx
0x1800246f6  mov     dword ptr [rsi+4], 11D08E59h
0x1800246fd  mov     dword ptr [rsi+8], 0C000478Ch
0x180024704  mov     dword ptr [rsi+0Ch], 0EE95C24Fh
0x18002470b  mov     rcx, rbx; pCertContext
0x18002470e  call    CertFreeCertificateContext
0x180024713  mov     ebx, 8000FFFFh
0x180024718  jmp     loc_1800247BD
0x18002471d  mov     ecx, 9BA61D3Fh
0x180024722  mov     [rsp+0C8h+var_48], ecx
0x180024729  mov     [rsp+0C8h+var_44], 11D0E73Ah
0x180024734  mov     [rsp+0C8h+var_40], 0C000D28Ch
0x18002473f  mov     [rsp+0C8h+var_3C], 0EE95C24Fh
0x18002474a  mov     [rsi], ecx
0x18002474c  mov     dword ptr [rsi+4], 11D0E73Ah
0x180024753  mov     dword ptr [rsi+8], 0C000D28Ch
0x18002475a  mov     dword ptr [rsi+0Ch], 0EE95C24Fh
0x180024761  mov     rcx, rbx; pCertContext
0x180024764  call    CertFreeCertificateContext
0x180024769  mov     ebx, 8000FFFFh
0x18002476e  jmp     short loc_1800247BD
0x180024770  jmp     loc_1800248C8
0x180024775  mov     rcx, r14; lpBaseAddress
0x180024778  call    cs:__imp_UnmapViewOfFile
0x18002477e  mov     rax, qword ptr [rsp+0C8h+FileSize]
0x180024786  mov     qword ptr [rsp+0C8h+dwMaximumSizeLow], rax; dwNumberOfBytesToMap
0x18002478b  xor     r9d, r9d; dwFileOffsetLow
0x18002478e  xor     r8d, r8d; dwFileOffsetHigh
0x180024791  lea     edx, [r9+4]; dwDesiredAccess
0x180024795  mov     rcx, r13; hFileMappingObject
0x180024798  call    cs:__imp_MapViewOfFile
0x18002479e  mov     r14, rax
0x1800247a1  mov     [rsp+0C8h+var_78], rax
0x1800247a6  mov     r9, qword ptr [rsp+0C8h+FileSize]
0x1800247ae  jmp     loc_180024683
0x1800247b3  jmp     loc_18002486E
0x1800247b8  jmp     loc_1800248AA
0x1800247bd  test    r14, r14
0x1800247c0  jz      short loc_1800247CB
0x1800247c2  mov     rcx, r14; lpBaseAddress
0x1800247c5  call    cs:__imp_UnmapViewOfFile
0x1800247cb  test    r13, r13
0x1800247ce  jz      short loc_1800247D9
0x1800247d0  mov     rcx, r13; hObject
0x1800247d3  call    cs:__imp_CloseHandle
0x1800247d9  lea     rax, [r15-1]
0x1800247dd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800247e1  jbe     short loc_180024857
0x1800247e3  test    r12d, r12d
0x1800247e6  jnz     short loc_1800247F0
0x1800247e8  mov     ecx, ebx; dwErrCode
0x1800247ea  call    cs:__imp_SetLastError
0x1800247f0  mov     eax, r12d
0x1800247f3  add     rsp, 90h
0x1800247fa  pop     r15
0x1800247fc  pop     r14
0x1800247fe  pop     r13
0x180024800  pop     r12
0x180024802  pop     rdi
0x180024803  pop     rsi
0x180024804  pop     rbx
0x180024805  retn
0x180024806  test    rcx, rcx
0x180024809  jz      loc_1800248C8
0x18002480f  mov     [rsp+0C8h+hTemplateFile], rdi; hTemplateFile
0x180024814  mov     dword ptr [rsp+0C8h+lpName], 80h; dwFlagsAndAttributes
0x18002481c  mov     [rsp+0C8h+dwMaximumSizeLow], 3; dwCreationDisposition
0x180024824  xor     r9d, r9d; lpSecurityAttributes
0x180024827  lea     r12d, [r9+1]
0x18002482b  mov     r8d, r12d; dwShareMode
0x18002482e  mov     edx, 80000000h; dwDesiredAccess
0x180024833  call    cs:__imp_CreateFileW
0x180024839  mov     r15, rax
0x18002483c  mov     [rsp+0C8h+arg_8], rax
0x180024844  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180024848  jz      short loc_1800248A0
0x18002484a  mov     [rsp+0C8h+arg_10], r12d
0x180024852  jmp     loc_1800244EA
0x180024857  cmp     [rsp+0C8h+arg_10], edi
0x18002485e  jz      short loc_1800247E3
0x180024860  mov     rcx, r15; hObject
0x180024863  call    cs:__imp_CloseHandle
0x180024869  jmp     loc_1800247E3
0x18002486e  mov     r8, rsi; struct _GUID *
0x180024871  mov     rdx, [rsp+0C8h+arg_0]; unsigned __int16 *
0x180024879  mov     rcx, r15; void *
0x18002487c  call    ?_QueryRegisteredIsMyFileType@@YAHPEAXPEBGPEAU_GUID@@@Z; _QueryRegisteredIsMyFileType(void *,ushort const *,_GUID *)
0x180024881  test    eax, eax
0x180024883  jnz     short loc_1800248CF
0x180024885  mov     ecx, 800B0003h; dwErrCode
0x18002488a  call    cs:__imp_SetLastError
0x180024890  call    cs:__imp_GetLastError
0x180024896  mov     ebx, eax
0x180024898  mov     r12d, edi
0x18002489b  jmp     loc_1800247BD
0x1800248a0  call    cs:__imp_GetLastError
0x1800248a6  mov     ecx, eax
0x1800248a8  jmp     short loc_18002488A
0x1800248aa  mov     ecx, eax; dwErrCode
0x1800248ac  call    cs:__imp_SetLastError
0x1800248b2  xor     edi, edi
0x1800248b4  mov     r15, [rsp+0C8h+arg_8]
0x1800248bc  mov     r14, [rsp+0C8h+var_78]
0x1800248c1  mov     r13, [rsp+0C8h+var_70]
0x1800248c6  jmp     short loc_180024890
0x1800248c8  mov     ecx, 57h ; 'W'
0x1800248cd  jmp     short loc_18002488A
0x1800248cf  mov     ebx, 8000FFFFh
0x1800248d4  jmp     loc_1800247BD
```
