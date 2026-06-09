# CLocalDumpGenerator::CreateUniqueDumpFile(wchar_t const *,wchar_t const *,ulong,int,tlx::unique_any<tlx::file_handle_traits> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x1800196bc`
- end: `0x1800199f2`
- name: `?CreateUniqueDumpFile@CLocalDumpGenerator@@CAJPEB_W0KHPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `822`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800199f8`

## callees

- `0x180002890`
- `0x1800028b4`
- `0x180003474`
- `0x180006b50`
- `0x180009ed8`
- `0x180009f00`
- `0x18000a074`
- `0x1800196bc`
- `0x18001aaf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800198c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800198e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800198c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800198e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019779`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019920`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019779`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019920`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800198af`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800198af`

## pseudocode

```c
__int64 __fastcall CLocalDumpGenerator::CreateUniqueDumpFile(
        __int64 a1,
        wchar_t *a2,
        DWORD a3,
        int a4,
        void **a5,
        __int64 a6)
{
  const wchar_t *v10; // r15
  void *v11; // rcx
  _WORD *v12; // rcx
  __int64 v13; // rax
  wchar_t *v14; // r8
  wchar_t *v15; // rcx
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  unsigned int v18; // ebx
  DWORD v19; // edi
  int v20; // eax
  HANDLE FileW; // rbx
  signed int LastError; // eax
  void *v23; // rcx
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-D8h]
  LPCWSTR lpFileName[2]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v28[8]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v29; // [rsp+60h] [rbp-A0h]
  wchar_t v30[264]; // [rsp+70h] [rbp-90h] BYREF

  v29 = a2;
  memset_0(v30, 0, 0x208u);
  lpFileName[0] = v28;
  v10 = L"protected.dmp";
  v28[0] = 0;
  lpFileName[1] = v28;
  if ( !a4 )
    v10 = L"dmp";
  if ( a1 && a5 && a6 )
  {
    v11 = *a5;
    *a5 = 0;
    if ( (unsigned __int64)v11 + 1 > 1 )
      CloseHandle(v11);
    v12 = *(_WORD **)a6;
    *(_QWORD *)(a6 + 8) = *(_QWORD *)a6;
    *v12 = 0;
    if ( a2 )
    {
      v13 = 2147483646;
      v14 = v30;
      v15 = a2;
      v16 = 260;
      do
      {
        if ( !v13 )
          break;
        if ( !*v15 )
          break;
        *v14++ = *v15++;
        --v13;
        --v16;
      }
      while ( v16 );
      v17 = v14 - 1;
      v18 = v16 == 0 ? 0x8007007A : 0;
      if ( v16 )
        v17 = v14;
      *v17 = 0;
      if ( !v16 )
      {
LABEL_41:
        if ( lpFileName[0] != v28 )
          operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
        return v18;
      }
      CLocalDumpGenerator::SanitizeFileNameComponent(v30);
    }
    v19 = 0;
    while ( 1 )
    {
      if ( v29 )
      {
        if ( v19 )
        {
          dwFlagsAndAttributes[0] = a3;
          dwCreationDisposition[0] = v19;
          v20 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                  lpFileName,
                  L"%s\\%s(%u).%u.%s",
                  a1,
                  v30,
                  *(_QWORD *)dwCreationDisposition,
                  *(_QWORD *)dwFlagsAndAttributes,
                  v10);
        }
        else
        {
          dwCreationDisposition[0] = a3;
          v20 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                  lpFileName,
                  L"%s\\%s.%u.%s",
                  a1,
                  v30,
                  *(_QWORD *)dwCreationDisposition,
                  v10);
        }
      }
      else if ( v19 )
      {
        dwCreationDisposition[0] = a3;
        v20 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                lpFileName,
                L"%s\\(%u).%u.%s",
                a1,
                v19,
                *(_QWORD *)dwCreationDisposition,
                v10);
      }
      else
      {
        v20 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                lpFileName,
                L"%s\\%u.%s",
                a1,
                a3,
                v10);
      }
      v18 = v20;
      if ( v20 < 0 )
        break;
      FileW = CreateFileW(lpFileName[0], 0x10002u, 0, 0, 1u, 0x80u, 0);
      if ( (unsigned __int64)FileW + 1 > 1 )
      {
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a6, lpFileName);
        v23 = *a5;
        *a5 = FileW;
        if ( (unsigned __int64)v23 + 1 > 1 )
          CloseHandle(v23);
        v18 = 0;
        goto LABEL_41;
      }
      if ( GetLastError() != 80 )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        if ( LastError >= 0 )
          LastError = -2147467259;
        v18 = LastError;
        goto LABEL_41;
      }
      if ( ++v19 == -1 )
      {
        v18 = -2147467259;
        goto LABEL_41;
      }
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        &WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids,
        (unsigned int)v20);
    goto LABEL_41;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids);
    if ( lpFileName[0] != v28 )
      operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800196bc  mov     [rsp-8+arg_8], rbx
0x1800196c1  push    rbp
0x1800196c2  push    rsi
0x1800196c3  push    rdi
0x1800196c4  push    r12
0x1800196c6  push    r13
0x1800196c8  push    r14
0x1800196ca  push    r15
0x1800196cc  lea     rbp, [rsp-190h]
0x1800196d4  sub     rsp, 290h
0x1800196db  mov     rax, cs:__security_cookie
0x1800196e2  xor     rax, rsp
0x1800196e5  mov     [rbp+1C0h+var_40], rax
0x1800196ec  mov     r14, [rbp+1C0h+arg_28]
0x1800196f3  mov     r13d, r8d
0x1800196f6  mov     rsi, [rbp+1C0h+arg_20]
0x1800196fd  mov     rdi, rdx
0x180019700  mov     [rsp+2C0h+var_260], rdx
0x180019705  mov     r12, rcx
0x180019708  xor     edx, edx; Val
0x18001970a  lea     rcx, [rsp+2C0h+var_250]; void *
0x18001970f  mov     r8d, 208h; Size
0x180019715  mov     ebx, r9d
0x180019718  call    memset_0
0x18001971d  xor     r10d, r10d
0x180019720  lea     rax, [rsp+2C0h+var_270]
0x180019725  mov     [rsp+2C0h+lpFileName], rax
0x18001972a  lea     r15, aProtectedDmp; "protected.dmp"
0x180019731  lea     rax, [rsp+2C0h+var_270]
0x180019736  mov     [rsp+2C0h+var_270], r10w
0x18001973c  test    ebx, ebx
0x18001973e  mov     [rsp+2C0h+var_278], rax
0x180019743  lea     rax, aDmp; "dmp"
0x18001974a  cmovz   r15, rax
0x18001974e  test    r12, r12
0x180019751  jz      loc_18001997A
0x180019757  test    rsi, rsi
0x18001975a  jz      loc_18001997A
0x180019760  test    r14, r14
0x180019763  jz      loc_18001997A
0x180019769  mov     rcx, [rsi]; hObject
0x18001976c  mov     [rsi], r10
0x18001976f  lea     rax, [rcx+1]
0x180019773  cmp     rax, 1
0x180019777  jbe     short loc_180019782
0x180019779  call    cs:__imp_CloseHandle
0x18001977f  xor     r10d, r10d
0x180019782  mov     rcx, [r14]
0x180019785  mov     [r14+8], rcx
0x180019789  mov     [rcx], r10w
0x18001978d  test    rdi, rdi
0x180019790  jz      short loc_1800197FA
0x180019792  mov     eax, 7FFFFFFEh
0x180019797  lea     r8, [rsp+2C0h+var_250]
0x18001979c  mov     rcx, rdi
0x18001979f  mov     edx, 104h
0x1800197a4  test    rax, rax
0x1800197a7  jz      short loc_1800197C8
0x1800197a9  movzx   r9d, word ptr [rcx]
0x1800197ad  test    r9w, r9w
0x1800197b1  jz      short loc_1800197C8
0x1800197b3  mov     [r8], r9w
0x1800197b7  add     rcx, 2
0x1800197bb  add     r8, 2
0x1800197bf  dec     rax
0x1800197c2  sub     rdx, 1
0x1800197c6  jnz     short loc_1800197A4
0x1800197c8  mov     rax, rdx
0x1800197cb  lea     rcx, [r8-2]
0x1800197cf  neg     rax
0x1800197d2  sbb     ebx, ebx
0x1800197d4  not     ebx
0x1800197d6  and     ebx, 8007007Ah
0x1800197dc  test    rdx, rdx
0x1800197df  cmovnz  rcx, r8
0x1800197e3  mov     [rcx], r10w
0x1800197e7  jz      loc_18001995B
0x1800197ed  lea     rcx, [rsp+2C0h+var_250]; wchar_t *
0x1800197f2  call    ?SanitizeFileNameComponent@CLocalDumpGenerator@@CAXPEA_W@Z; CLocalDumpGenerator::SanitizeFileNameComponent(wchar_t *)
0x1800197f7  xor     r10d, r10d
0x1800197fa  mov     edi, r10d
0x1800197fd  lea     rcx, [rsp+2C0h+lpFileName]
0x180019802  mov     r8, r12
0x180019805  cmp     [rsp+2C0h+var_260], r10
0x18001980a  jz      short loc_180019849
0x18001980c  lea     r9, [rsp+2C0h+var_250]
0x180019811  test    edi, edi
0x180019813  jnz     short loc_18001982D
0x180019815  mov     qword ptr [rsp+2C0h+dwFlagsAndAttributes], r15
0x18001981a  lea     rdx, aSSUS; "%s\\%s.%u.%s"
0x180019821  mov     [rsp+2C0h+dwCreationDisposition], r13d
0x180019826  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18001982b  jmp     short loc_18001987C
0x18001982d  mov     [rsp+2C0h+hTemplateFile], r15
0x180019832  lea     rdx, aSSUUS; "%s\\%s(%u).%u.%s"
0x180019839  mov     [rsp+2C0h+dwFlagsAndAttributes], r13d
0x18001983e  mov     [rsp+2C0h+dwCreationDisposition], edi
0x180019842  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180019847  jmp     short loc_18001987C
0x180019849  test    edi, edi
0x18001984b  jnz     short loc_180019863
0x18001984d  mov     r9d, r13d
0x180019850  mov     qword ptr [rsp+2C0h+dwCreationDisposition], r15
0x180019855  lea     rdx, aSUS; "%s\\%u.%s"
0x18001985c  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180019861  jmp     short loc_18001987C
0x180019863  mov     qword ptr [rsp+2C0h+dwFlagsAndAttributes], r15
0x180019868  lea     rdx, aSUUS; "%s\\(%u).%u.%s"
0x18001986f  mov     r9d, edi
0x180019872  mov     [rsp+2C0h+dwCreationDisposition], r13d
0x180019877  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18001987c  mov     ebx, eax
0x18001987e  test    eax, eax
0x180019880  js      loc_18001992A
0x180019886  mov     rcx, [rsp+2C0h+lpFileName]; lpFileName
0x18001988b  xor     r9d, r9d; lpSecurityAttributes
0x18001988e  mov     [rsp+2C0h+hTemplateFile], 0; hTemplateFile
0x180019897  xor     r8d, r8d; dwShareMode
0x18001989a  mov     [rsp+2C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800198a2  mov     edx, 10002h; dwDesiredAccess
0x1800198a7  mov     [rsp+2C0h+dwCreationDisposition], 1; dwCreationDisposition
0x1800198af  call    cs:__imp_CreateFileW
0x1800198b5  mov     rbx, rax
0x1800198b8  lea     rcx, [rax+1]
0x1800198bc  cmp     rcx, 1
0x1800198c0  ja      short loc_180019903
0x1800198c2  call    cs:__imp_GetLastError
0x1800198c8  cmp     eax, 50h ; 'P'
0x1800198cb  jnz     short loc_1800198E3
0x1800198cd  inc     edi
0x1800198cf  lea     r10d, [rax-50h]
0x1800198d3  cmp     edi, 0FFFFFFFFh
0x1800198d6  jb      loc_1800197FD
0x1800198dc  mov     ebx, 80004005h
0x1800198e1  jmp     short loc_18001995B
0x1800198e3  call    cs:__imp_GetLastError
0x1800198e9  test    eax, eax
0x1800198eb  jle     short loc_1800198F5
0x1800198ed  movzx   eax, ax
0x1800198f0  or      eax, 80070000h
0x1800198f5  mov     ebx, 80004005h
0x1800198fa  test    eax, eax
0x1800198fc  cmovns  eax, ebx
0x1800198ff  mov     ebx, eax
0x180019901  jmp     short loc_18001995B
0x180019903  lea     rdx, [rsp+2C0h+lpFileName]
0x180019908  mov     rcx, r14
0x18001990b  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x180019910  mov     rcx, [rsi]; hObject
0x180019913  mov     [rsi], rbx
0x180019916  lea     rax, [rcx+1]
0x18001991a  cmp     rax, 1
0x18001991e  jbe     short loc_180019926
0x180019920  call    cs:__imp_CloseHandle
0x180019926  xor     ebx, ebx
0x180019928  jmp     short loc_18001995B
0x18001992a  mov     rcx, cs:WPP_GLOBAL_Control
0x180019931  lea     rax, WPP_GLOBAL_Control
0x180019938  cmp     rcx, rax
0x18001993b  jz      short loc_18001995B
0x18001993d  test    byte ptr [rcx+1Ch], 1
0x180019941  jz      short loc_18001995B
0x180019943  mov     rcx, [rcx+10h]
0x180019947  lea     r8, WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids
0x18001994e  mov     edx, 2Ah ; '*'
0x180019953  mov     r9d, ebx
0x180019956  call    WPP_SF_d
0x18001995b  mov     rcx, [rsp+2C0h+lpFileName]; void *
0x180019960  lea     rax, [rsp+2C0h+var_270]
0x180019965  cmp     rcx, rax
0x180019968  jz      short loc_180019976
0x18001996a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180019971  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180019976  mov     eax, ebx
0x180019978  jmp     short loc_1800199C8
0x18001997a  mov     rcx, cs:WPP_GLOBAL_Control
0x180019981  lea     rax, WPP_GLOBAL_Control
0x180019988  cmp     rcx, rax
0x18001998b  jz      short loc_1800199C3
0x18001998d  test    byte ptr [rcx+1Ch], 1
0x180019991  jz      short loc_1800199C3
0x180019993  mov     rcx, [rcx+10h]
0x180019997  lea     r8, WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids
0x18001999e  mov     edx, 29h ; ')'
0x1800199a3  call    WPP_SF_
0x1800199a8  mov     rcx, [rsp+2C0h+lpFileName]; void *
0x1800199ad  lea     rax, [rsp+2C0h+var_270]
0x1800199b2  cmp     rcx, rax
0x1800199b5  jz      short loc_1800199C3
0x1800199b7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800199be  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800199c3  mov     eax, 80070057h
0x1800199c8  mov     rcx, [rbp+1C0h+var_40]
0x1800199cf  xor     rcx, rsp; StackCookie
0x1800199d2  call    __security_check_cookie
0x1800199d7  mov     rbx, [rsp+2C0h+arg_8]
0x1800199df  add     rsp, 290h
0x1800199e6  pop     r15
0x1800199e8  pop     r14
0x1800199ea  pop     r13
0x1800199ec  pop     r12
0x1800199ee  pop     rdi
0x1800199ef  pop     rsi
0x1800199f0  pop     rbp
0x1800199f1  retn
```
