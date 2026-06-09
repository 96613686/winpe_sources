# GetDumpSecurityDescriptor

- ea: `0x18004704c`
- end: `0x18004730c`
- name: `GetDumpSecurityDescriptor`
- size: `704`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, PSECURITY_DESCRIPTOR *SecurityDescriptor)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180047adc`

## callees

- `0x1800028b4`
- `0x180006b50`
- `0x180009f00`
- `0x18003a9e8`
- `0x18003ab24`
- `0x18004704c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800470fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047281`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800470fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047281`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800470e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047263`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800472ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800470e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047263`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800472ce`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180047277`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180047277`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800470f2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800470f2`

## pseudocode

```c
__int64 __fastcall GetDumpSecurityDescriptor(HANDLE ProcessHandle, PSECURITY_DESCRIPTOR *SecurityDescriptor)
{
  signed int ProcessUserSid; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  HLOCAL v7; // rcx
  signed int v8; // eax
  PSECURITY_DESCRIPTOR v9; // rcx
  signed int LastError; // eax
  LPCWSTR StringSecurityDescriptor[2]; // [rsp+28h] [rbp-28h] BYREF
  _WORD v13[12]; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v14; // [rsp+80h] [rbp+30h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp+38h] BYREF

  StringSecurityDescriptor[0] = v13;
  StringSecurityDescriptor[1] = v13;
  v13[0] = 0;
  hMem = 0;
  v14 = 0;
  ProcessUserSid = UtilGetProcessUserSid(ProcessHandle);
  if ( ProcessUserSid >= 0 )
  {
    v7 = hMem;
    hMem = 0;
    if ( v7 )
      LocalFree(v7);
    if ( ConvertSidToStringSidW(0, (LPWSTR *)&hMem) )
    {
      ProcessUserSid = UtilGetProcessIntegrityRid(ProcessHandle, &v14);
      if ( ProcessUserSid >= 0 )
      {
        if ( v14 < 0x3000 )
        {
          if ( v14 < 0x2000 )
          {
            ProcessUserSid = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                               StringSecurityDescriptor,
                               L"D:P(A;;GA;;;BA)(A;;GA;;;SY)(A;;GA;;;%s)",
                               hMem);
            if ( ProcessUserSid < 0 )
            {
              v5 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v6 = 25;
                goto LABEL_5;
              }
              goto LABEL_45;
            }
          }
          else
          {
            ProcessUserSid = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                               StringSecurityDescriptor,
                               L"D:P(A;;GA;;;BA)(A;;GA;;;SY)(A;;GA;;;%s)S:(ML;;NR;;;ME)",
                               hMem);
            if ( ProcessUserSid < 0 )
            {
              v5 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v6 = 24;
                goto LABEL_5;
              }
              goto LABEL_45;
            }
          }
        }
        else
        {
          ProcessUserSid = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                             StringSecurityDescriptor,
                             L"D:P(A;;GA;;;BA)(A;;GA;;;SY)(A;;GA;;;%s)S:(ML;;NR;;;HI)",
                             hMem);
          if ( ProcessUserSid < 0 )
          {
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v6 = 23;
              goto LABEL_5;
            }
            goto LABEL_45;
          }
        }
        v9 = *SecurityDescriptor;
        *SecurityDescriptor = 0;
        if ( v9 )
          LocalFree(v9);
        if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
               StringSecurityDescriptor[0],
               1u,
               SecurityDescriptor,
               0) )
        {
          ProcessUserSid = 0;
        }
        else
        {
          LastError = GetLastError();
          ProcessUserSid = LastError;
          if ( LastError > 0 )
            ProcessUserSid = (unsigned __int16)LastError | 0x80070000;
          if ( ProcessUserSid >= 0 )
            ProcessUserSid = -2147467259;
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v6 = 26;
            goto LABEL_5;
          }
        }
        goto LABEL_45;
      }
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 22;
        goto LABEL_5;
      }
    }
    else
    {
      v8 = GetLastError();
      ProcessUserSid = v8;
      if ( v8 > 0 )
        ProcessUserSid = (unsigned __int16)v8 | 0x80070000;
      if ( ProcessUserSid >= 0 )
        ProcessUserSid = -2147467259;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 21;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 20;
LABEL_5:
      WPP_SF_d(v5[2], v6, &WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids, (unsigned int)ProcessUserSid);
    }
  }
LABEL_45:
  if ( hMem )
    LocalFree(hMem);
  if ( StringSecurityDescriptor[0] != v13 )
    operator delete((void *)StringSecurityDescriptor[0], (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)ProcessUserSid;
}

```

## disassembly

```asm
0x18004704c  mov     [rsp-18h+arg_0], rbx
0x180047051  push    rbp
0x180047052  push    rsi
0x180047053  push    rdi
0x180047054  mov     rbp, rsp
0x180047057  sub     rsp, 50h
0x18004705b  lea     rax, [rbp+var_18]
0x18004705f  mov     [rbp+Sid], 0
0x180047067  mov     [rbp+StringSecurityDescriptor], rax
0x18004706b  mov     rdi, rdx
0x18004706e  lea     rax, [rbp+var_18]
0x180047072  mov     rsi, rcx
0x180047075  mov     [rbp+var_20], rax
0x180047079  lea     rdx, [rbp+Sid]
0x18004707d  xor     eax, eax
0x18004707f  mov     [rbp+var_18], ax
0x180047083  mov     [rbp+hMem], rax
0x180047087  mov     [rbp+arg_10], eax
0x18004708a  call    ?UtilGetProcessUserSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; UtilGetProcessUserSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)
0x18004708f  mov     ebx, eax
0x180047091  test    eax, eax
0x180047093  jns     short loc_1800470D3
0x180047095  mov     rcx, cs:WPP_GLOBAL_Control
0x18004709c  lea     rax, WPP_GLOBAL_Control
0x1800470a3  cmp     rcx, rax
0x1800470a6  jz      loc_1800472C5
0x1800470ac  test    byte ptr [rcx+1Ch], 1
0x1800470b0  jz      loc_1800472C5
0x1800470b6  mov     edx, 14h
0x1800470bb  mov     rcx, [rcx+10h]
0x1800470bf  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x1800470c6  mov     r9d, ebx
0x1800470c9  call    WPP_SF_d
0x1800470ce  jmp     loc_1800472C5
0x1800470d3  mov     rcx, [rbp+hMem]; hMem
0x1800470d7  mov     [rbp+hMem], 0
0x1800470df  test    rcx, rcx
0x1800470e2  jz      short loc_1800470EA
0x1800470e4  call    cs:__imp_LocalFree
0x1800470ea  mov     rcx, [rbp+Sid]; Sid
0x1800470ee  lea     rdx, [rbp+hMem]; StringSid
0x1800470f2  call    cs:__imp_ConvertSidToStringSidW
0x1800470f8  test    eax, eax
0x1800470fa  jnz     short loc_180047146
0x1800470fc  call    cs:__imp_GetLastError
0x180047102  mov     ebx, eax
0x180047104  test    eax, eax
0x180047106  jle     short loc_180047111
0x180047108  movzx   ebx, ax
0x18004710b  or      ebx, 80070000h
0x180047111  test    ebx, ebx
0x180047113  mov     eax, 80004005h
0x180047118  cmovns  ebx, eax
0x18004711b  mov     rcx, cs:WPP_GLOBAL_Control
0x180047122  lea     rax, WPP_GLOBAL_Control
0x180047129  cmp     rcx, rax
0x18004712c  jz      loc_1800472C5
0x180047132  test    byte ptr [rcx+1Ch], 1
0x180047136  jz      loc_1800472C5
0x18004713c  mov     edx, 15h
0x180047141  jmp     loc_1800470BB
0x180047146  lea     rdx, [rbp+arg_10]; unsigned int *
0x18004714a  mov     rcx, rsi; ProcessHandle
0x18004714d  call    ?UtilGetProcessIntegrityRid@@YAJPEAXPEAK@Z; UtilGetProcessIntegrityRid(void *,ulong *)
0x180047152  mov     ebx, eax
0x180047154  test    eax, eax
0x180047156  jns     short loc_180047183
0x180047158  mov     rcx, cs:WPP_GLOBAL_Control
0x18004715f  lea     rax, WPP_GLOBAL_Control
0x180047166  cmp     rcx, rax
0x180047169  jz      loc_1800472C5
0x18004716f  test    byte ptr [rcx+1Ch], 1
0x180047173  jz      loc_1800472C5
0x180047179  mov     edx, 16h
0x18004717e  jmp     loc_1800470BB
0x180047183  cmp     [rbp+arg_10], 3000h
0x18004718a  lea     rcx, [rbp+StringSecurityDescriptor]
0x18004718e  mov     r8, [rbp+hMem]
0x180047192  jb      short loc_1800471D5
0x180047194  lea     rdx, aDPAGaBaAGaSyAG_1; "D:P(A;;GA;;;BA)(A;;GA;;;SY)(A;;GA;;;%s)"...
0x18004719b  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800471a0  mov     ebx, eax
0x1800471a2  test    eax, eax
0x1800471a4  jns     loc_180047254
0x1800471aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800471b1  lea     rax, WPP_GLOBAL_Control
0x1800471b8  cmp     rcx, rax
0x1800471bb  jz      loc_1800472C5
0x1800471c1  test    byte ptr [rcx+1Ch], 1
0x1800471c5  jz      loc_1800472C5
0x1800471cb  mov     edx, 17h
0x1800471d0  jmp     loc_1800470BB
0x1800471d5  cmp     [rbp+arg_10], 2000h
0x1800471dc  jb      short loc_18004721B
0x1800471de  lea     rdx, aDPAGaBaAGaSyAG_0; "D:P(A;;GA;;;BA)(A;;GA;;;SY)(A;;GA;;;%s)"...
0x1800471e5  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800471ea  mov     ebx, eax
0x1800471ec  test    eax, eax
0x1800471ee  jns     short loc_180047254
0x1800471f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800471f7  lea     rax, WPP_GLOBAL_Control
0x1800471fe  cmp     rcx, rax
0x180047201  jz      loc_1800472C5
0x180047207  test    byte ptr [rcx+1Ch], 1
0x18004720b  jz      loc_1800472C5
0x180047211  mov     edx, 18h
0x180047216  jmp     loc_1800470BB
0x18004721b  lea     rdx, aDPAGaBaAGaSyAG; "D:P(A;;GA;;;BA)(A;;GA;;;SY)(A;;GA;;;%s)"
0x180047222  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180047227  mov     ebx, eax
0x180047229  test    eax, eax
0x18004722b  jns     short loc_180047254
0x18004722d  mov     rcx, cs:WPP_GLOBAL_Control
0x180047234  lea     rax, WPP_GLOBAL_Control
0x18004723b  cmp     rcx, rax
0x18004723e  jz      loc_1800472C5
0x180047244  test    byte ptr [rcx+1Ch], 1
0x180047248  jz      short loc_1800472C5
0x18004724a  mov     edx, 19h
0x18004724f  jmp     loc_1800470BB
0x180047254  mov     rcx, [rdi]; hMem
0x180047257  mov     qword ptr [rdi], 0
0x18004725e  test    rcx, rcx
0x180047261  jz      short loc_180047269
0x180047263  call    cs:__imp_LocalFree
0x180047269  mov     rcx, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x18004726d  xor     r9d, r9d; SecurityDescriptorSize
0x180047270  mov     r8, rdi; SecurityDescriptor
0x180047273  lea     edx, [r9+1]; StringSDRevision
0x180047277  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004727d  test    eax, eax
0x18004727f  jnz     short loc_1800472C3
0x180047281  call    cs:__imp_GetLastError
0x180047287  mov     ebx, eax
0x180047289  test    eax, eax
0x18004728b  jle     short loc_180047296
0x18004728d  movzx   ebx, ax
0x180047290  or      ebx, 80070000h
0x180047296  test    ebx, ebx
0x180047298  mov     eax, 80004005h
0x18004729d  cmovns  ebx, eax
0x1800472a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800472a7  lea     rax, WPP_GLOBAL_Control
0x1800472ae  cmp     rcx, rax
0x1800472b1  jz      short loc_1800472C5
0x1800472b3  test    byte ptr [rcx+1Ch], 1
0x1800472b7  jz      short loc_1800472C5
0x1800472b9  mov     edx, 1Ah
0x1800472be  jmp     loc_1800470BB
0x1800472c3  xor     ebx, ebx
0x1800472c5  mov     rcx, [rbp+hMem]; hMem
0x1800472c9  test    rcx, rcx
0x1800472cc  jz      short loc_1800472D4
0x1800472ce  call    cs:__imp_LocalFree
0x1800472d4  mov     rcx, [rbp+StringSecurityDescriptor]; void *
0x1800472d8  lea     rax, [rbp+var_18]
0x1800472dc  cmp     rcx, rax
0x1800472df  jz      short loc_1800472ED
0x1800472e1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800472e8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800472ed  cmp     [rbp+Sid], 0
0x1800472f2  jz      short loc_1800472FD
0x1800472f4  mov     rcx, [rbp+Sid]; void *
0x1800472f8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800472fd  mov     eax, ebx
0x1800472ff  mov     rbx, [rsp+50h+arg_0]
0x180047304  add     rsp, 50h
0x180047308  pop     rdi
0x180047309  pop     rsi
0x18004730a  pop     rbp
0x18004730b  retn
```
