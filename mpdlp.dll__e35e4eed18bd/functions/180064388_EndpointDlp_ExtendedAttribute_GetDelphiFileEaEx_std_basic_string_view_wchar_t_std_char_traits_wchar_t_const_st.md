# EndpointDlp::ExtendedAttribute::GetDelphiFileEaEx(std::basic_string_view<wchar_t,std::char_traits<wchar_t>> const &,std::basic_string_view<char,std::char_traits<char>> const &)

- ea: `0x180064388`
- end: `0x180064772`
- name: `?GetDelphiFileEaEx@ExtendedAttribute@EndpointDlp@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@4@AEBV?$basic_string_view@DU?$char_traits@D@std@@@4@@Z`
- size: `1002`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, loader_planting`

## callers

- `0x1800642a4`
- `0x18016b5a0`

## callees

- `0x180004f3c`
- `0x180024ac0`
- `0x1800301a0`
- `0x1800323d0`
- `0x1800572a0`
- `0x180062c38`
- `0x180064388`
- `0x180064774`
- `0x1800647d4`
- `0x180065438`
- `0x18010cb40`
- `0x18010d700`
- `0x18011d880`
- `0x18023a310`
- `0x18023a6d0`

## import_xrefs

- `ntdll!ZwQueryEaFile` at `0x180064490`
- `ntdll!ZwQueryEaFile` at `0x18006469b`
- `ntdll!ZwQueryEaFile` at `0x180064490`
- `ntdll!ZwQueryEaFile` at `0x18006469b`
- `KERNEL32!CreateFileW` at `0x180064412`
- `KERNEL32!CreateFileW` at `0x180064412`
- `KERNEL32!CloseHandle` at `0x180064766`
- `KERNEL32!CloseHandle` at `0x180064766`

## string_xrefs

- `0x18006442e`: `failed to open a file for getting EA`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EndpointDlp::ExtendedAttribute::GetDelphiFileEaEx(__int64 a1, __int64 a2, __int64 a3)
{
  char *FileW; // r15
  NTSTATUS v7; // eax
  const char *v8; // rbx
  unsigned int Information; // edi
  size_t v10; // r8
  __int64 v11; // rax
  struct EndpointDlp::TraceLoggingProvider *v12; // rax
  int v13; // r8d
  int v14; // r9d
  _DWORD *v15; // rcx
  char v17; // dl
  char *v18; // rbx
  PVOID v19; // r8
  NTSTATUS v20; // eax
  const char *v21; // r9
  __int64 v22; // rax
  const char *dwFlagsAndAttributesa; // [rsp+28h] [rbp-D8h]
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  const char *hTemplateFile; // [rsp+30h] [rbp-D0h]
  const char *hTemplateFilea; // [rsp+30h] [rbp-D0h]
  LPCWSTR v27; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v28[2]; // [rsp+58h] [rbp-A8h] BYREF
  PVOID v29[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v30; // [rsp+78h] [rbp-88h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-80h] BYREF
  _BYTE Buffer[4096]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+10D8h] [rbp+FD8h]

  v28[0] = a1;
  LODWORD(v27) = 1;
  *(_OWORD *)v29 = 0;
  v30 = 0;
  if ( !*(_QWORD *)(a2 + 8) )
    di::TelemetryAssert::AssertTriggeredNoArgs();
  FileW = (char *)CreateFileW(*(LPCWSTR *)a2, 8u, 0, 0, 3u, 0x80u, 0);
  v28[1] = FileW;
  wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(
    retaddr,
    (void *)0x50,
    (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\WindowsDelphiEa\\src\\windowsDelphiEa.cpp",
    (const char *)(FileW + 1 != 0),
    (bool)"failed to open a file for getting EA",
    dwFlagsAndAttributesa);
  IoStatusBlock = 0;
  memset(Buffer, 0, sizeof(Buffer));
  v7 = ZwQueryEaFile(FileW, &IoStatusBlock, Buffer, 0x1000u, 0, 0, 0, 0, 1u);
  if ( v7 < 0 )
  {
    _mm_lfence();
    if ( v7 == -1073741789 || (v17 = 1, v7 == -2147483643) )
      v17 = 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x6C,
      (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\WindowsDelphiEa\\src\\windowsDelphiEa.cpp",
      (const char *)(v7 | 0x10000000u),
      v17,
      (bool)"ZwQueryEaFile failed",
      hTemplateFile);
    LODWORD(v18) = v29[1];
    v19 = v29[0];
    if ( (PVOID)((char *)v29[1] - (char *)v29[0]) > (PVOID)0x4000 )
    {
      v18 = (char *)v29[0] + 0x4000;
LABEL_29:
      v29[1] = v18;
      goto LABEL_30;
    }
    if ( (PVOID)((char *)v29[1] - (char *)v29[0]) < (PVOID)0x4000 )
    {
      if ( v30 - (unsigned __int64)v29[0] >= 0x4000 )
      {
        memset(v29[1], 0, 0x4000 - (unsigned __int64)((char *)v29[1] - (char *)v29[0]));
        v18 = (char *)v29[0] + 0x4000;
        v19 = v29[0];
        goto LABEL_29;
      }
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v29, 0x4000);
      LODWORD(v18) = v29[1];
      v19 = v29[0];
    }
LABEL_30:
    v20 = ZwQueryEaFile(FileW, &IoStatusBlock, v19, (_DWORD)v18 - (_DWORD)v19, 0, 0, 0, 0, 1u);
    v21 = (const char *)(unsigned int)v20;
    LODWORD(v21) = v20 | 0x10000000;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x7B,
      (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\WindowsDelphiEa\\src\\windowsDelphiEa.cpp",
      v21,
      v20 < 0,
      (bool)"ZwQueryEaFile failed",
      hTemplateFilea);
    v8 = (const char *)v29[0];
    goto LABEL_5;
  }
  v8 = Buffer;
LABEL_5:
  Information = IoStatusBlock.Information;
  while ( 1 )
  {
    if ( Information < 0xC )
      goto LABEL_7;
    v10 = *(_QWORD *)(a3 + 8);
    v11 = *((unsigned __int8 *)v8 + 5);
    if ( v11 == v10 && Information >= (unsigned __int64)(v11 + 8) && !strnicmp(v8 + 8, *(const char **)a3, v10) )
      break;
    if ( !*(_DWORD *)v8 )
      goto LABEL_7;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xA4,
      (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\WindowsDelphiEa\\src\\windowsDelphiEa.cpp",
      (const char *)0x90000014LL,
      *(_DWORD *)v8 >= Information,
      (bool)"The extended attribute (EA) list is inconsistent",
      hTemplateFile);
    v22 = *(unsigned int *)v8;
    Information -= v22;
    v8 += v22;
  }
  if ( !*((_WORD *)v8 + 3)
    || Information < *((unsigned __int8 *)v8 + 5) + (unsigned __int64)*((unsigned __int16 *)v8 + 3) + 9 )
  {
LABEL_7:
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0xAB,
      (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\WindowsDelphiEa\\src\\windowsDelphiEa.cpp",
      (const char *)0xD0000034LL,
      (int)"Failed to find EA",
      dwFlagsAndAttributes);
  }
  v12 = EndpointDlp::TraceLoggingProvider::Instance();
  v15 = *(_DWORD **)v12;
  if ( **(_DWORD **)v12 > 5u )
  {
    v27 = *(LPCWSTR *)a2;
    v28[0] = L"Found EA for the file";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
      (_DWORD)v15,
      (unsigned int)byte_1802BDCAD,
      v13,
      v14,
      (__int64)v28,
      (__int64)&v27);
  }
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  std::vector<unsigned char>::vector<unsigned char>(a1, *((unsigned __int16 *)v8 + 3));
  memmove(*(void **)a1, &v8[*((unsigned __int8 *)v8 + 5) + 9], *((unsigned __int16 *)v8 + 3));
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  if ( v29[0] )
    std::_Deallocate<16>(v29[0], v30 - (unsigned __int64)v29[0]);
  return a1;
}

```

## disassembly

```asm
0x180064388  mov     [rsp-8+arg_18], rbx
0x18006438d  push    rbp
0x18006438e  push    rsi
0x18006438f  push    rdi
0x180064390  push    r12
0x180064392  push    r13
0x180064394  push    r14
0x180064396  push    r15
0x180064398  lea     rbp, [rsp-0FA0h]
0x1800643a0  mov     eax, 10A0h
0x1800643a5  call    _alloca_probe
0x1800643aa  sub     rsp, rax
0x1800643ad  mov     rax, cs:__security_cookie
0x1800643b4  xor     rax, rsp
0x1800643b7  mov     [rbp+0FD0h+var_40], rax
0x1800643be  mov     r13, r8
0x1800643c1  mov     r12, rdx
0x1800643c4  mov     rsi, rcx
0x1800643c7  mov     [rsp+10D0h+var_1078], rcx
0x1800643cc  mov     dword ptr [rsp+10D0h+var_1080], 1
0x1800643d4  xorps   xmm1, xmm1
0x1800643d7  movdqu  xmmword ptr [rsp+10D0h+var_1068], xmm1
0x1800643dd  xor     r14d, r14d
0x1800643e0  mov     [rsp+10D0h+var_1058], r14
0x1800643e5  cmp     [rdx+8], r14
0x1800643e9  jz      loc_1800645BD
0x1800643ef  mov     [rsp+10D0h+hTemplateFile], r14; hTemplateFile
0x1800643f4  mov     [rsp+10D0h+dwFlagsAndAttributes], 80h; char *
0x1800643fc  mov     [rsp+10D0h+dwCreationDisposition], 3; dwCreationDisposition
0x180064404  xor     r9d, r9d; lpSecurityAttributes
0x180064407  xor     r8d, r8d; dwShareMode
0x18006440a  lea     edx, [r9+8]; dwDesiredAccess
0x18006440e  mov     rcx, [r12]; lpFileName
0x180064412  call    cs:__imp_CreateFileW
0x180064418  mov     r15, rax
0x18006441b  mov     [rsp+10D0h+var_1070], rax
0x180064420  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180064424  setnz   al
0x180064427  mov     rcx, [rbp+0FD8h]; this
0x18006442e  lea     rdx, aFailedToOpenAF; "failed to open a file for getting EA"
0x180064435  mov     qword ptr [rsp+10D0h+dwCreationDisposition], rdx; bool
0x18006443a  movzx   r9d, al; char *
0x18006443e  lea     r8, aSrcEppDlpEndpo_16; "src\\epp\\Dlp\\EndpointDlp\\WindowsDelp"...
0x180064445  mov     edx, 50h ; 'P'; void *
0x18006444a  call    ?Throw_GetLastErrorIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x18006444f  xorps   xmm0, xmm0
0x180064452  movups  xmmword ptr [rbp+0FD0h+IoStatusBlock], xmm0
0x180064456  mov     ebx, 1000h
0x18006445b  mov     r8d, ebx; Size
0x18006445e  xor     edx, edx; Val
0x180064460  lea     rcx, [rbp+0FD0h+Buffer]; void *
0x180064464  call    memset
0x180064469  mov     [rsp+10D0h+RestartScan], 1; RestartScan
0x18006446e  mov     [rsp+10D0h+EaIndex], r14; EaIndex
0x180064473  mov     dword ptr [rsp+10D0h+hTemplateFile], r14d; char *
0x180064478  mov     qword ptr [rsp+10D0h+dwFlagsAndAttributes], r14; char *
0x18006447d  mov     byte ptr [rsp+10D0h+dwCreationDisposition], r14b; ReturnSingleEntry
0x180064482  mov     r9d, ebx; Length
0x180064485  lea     r8, [rbp+0FD0h+Buffer]; Buffer
0x180064489  lea     rdx, [rbp+0FD0h+IoStatusBlock]; IoStatusBlock
0x18006448d  mov     rcx, r15; FileHandle
0x180064490  call    cs:__imp_ZwQueryEaFile
0x180064496  test    eax, eax
0x180064498  js      loc_1800645C8
0x18006449e  lea     rbx, [rbp+0FD0h+Buffer]
0x1800644a2  mov     edi, dword ptr [rbp+0FD0h+IoStatusBlock.Information]
0x1800644a5  cmp     edi, 0Ch
0x1800644a8  jnb     short loc_1800644D5
0x1800644aa  mov     rcx, [rbp+0FD8h]; this
0x1800644b1  lea     rax, aFailedToFindEa; "Failed to find EA"
0x1800644b8  mov     qword ptr [rsp+10D0h+dwCreationDisposition], rax; int
0x1800644bd  mov     r9d, 0D0000034h; char *
0x1800644c3  lea     r8, aSrcEppDlpEndpo_16; "src\\epp\\Dlp\\EndpointDlp\\WindowsDelp"...
0x1800644ca  mov     edx, 0ABh; void *
0x1800644cf  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800644d5  mov     r8, [r13+8]; MaxCount
0x1800644d9  movzx   eax, byte ptr [rbx+5]
0x1800644dd  cmp     rax, r8
0x1800644e0  jnz     loc_1800646E1
0x1800644e6  mov     r14d, edi
0x1800644e9  add     rax, 8
0x1800644ed  cmp     r14, rax
0x1800644f0  jb      loc_1800646DE
0x1800644f6  lea     rcx, [rbx+8]; String1
0x1800644fa  mov     rdx, [r13+0]; String2
0x1800644fe  call    _strnicmp
0x180064503  xor     ecx, ecx
0x180064505  test    eax, eax
0x180064507  jnz     loc_1800646DE
0x18006450d  cmp     [rbx+6], cx
0x180064511  jbe     short loc_1800644AA
0x180064513  movzx   ecx, word ptr [rbx+6]
0x180064517  movzx   eax, byte ptr [rbx+5]
0x18006451b  add     rcx, 9
0x18006451f  add     rcx, rax
0x180064522  cmp     r14, rcx
0x180064525  jb      short loc_1800644AA
0x180064527  call    ?Instance@TraceLoggingProvider@EndpointDlp@@SAAEAV12@XZ; EndpointDlp::TraceLoggingProvider::Instance(void)
0x18006452c  mov     rcx, [rax]
0x18006452f  cmp     dword ptr [rcx], 5
0x180064532  ja      loc_180064729
0x180064538  xorps   xmm0, xmm0
0x18006453b  xor     eax, eax
0x18006453d  movups  xmmword ptr [rsi], xmm0
0x180064540  mov     [rsi+10h], rax
0x180064544  movzx   edx, word ptr [rbx+6]
0x180064548  mov     rcx, rsi
0x18006454b  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180064550  movzx   r8d, word ptr [rbx+6]; Size
0x180064555  movzx   edx, byte ptr [rbx+5]
0x180064559  add     rdx, 9
0x18006455d  add     rdx, rbx; Src
0x180064560  mov     rcx, [rsi]; void *
0x180064563  call    memmove
0x180064568  nop
0x180064569  lea     rax, [r15-1]
0x18006456d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180064571  jbe     loc_180064763
0x180064577  mov     rcx, [rsp+10D0h+var_1068]
0x18006457c  test    rcx, rcx
0x18006457f  jnz     short loc_1800645AE
0x180064581  mov     rax, rsi
0x180064584  mov     rcx, [rbp+0FD0h+var_40]
0x18006458b  xor     rcx, rsp; StackCookie
0x18006458e  call    __security_check_cookie
0x180064593  mov     rbx, [rsp+10D0h+arg_18]
0x18006459b  add     rsp, 10A0h
0x1800645a2  pop     r15
0x1800645a4  pop     r14
0x1800645a6  pop     r13
0x1800645a8  pop     r12
0x1800645aa  pop     rdi
0x1800645ab  pop     rsi
0x1800645ac  pop     rbp
0x1800645ad  retn
0x1800645ae  mov     rdx, [rsp+10D0h+var_1058]
0x1800645b3  sub     rdx, rcx
0x1800645b6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800645bb  jmp     short loc_180064581
0x1800645bd  call    ?AssertTriggeredNoArgs@TelemetryAssert@di@@SAXXZ; di::TelemetryAssert::AssertTriggeredNoArgs(void)
0x1800645c2  nop
0x1800645c3  jmp     loc_1800643EF
0x1800645c8  lfence
0x1800645cb  cmp     eax, 0C0000023h
0x1800645d0  jz      short loc_1800645DB
0x1800645d2  cmp     eax, 80000005h
0x1800645d7  mov     dl, 1
0x1800645d9  jnz     short loc_1800645DE
0x1800645db  mov     dl, r14b
0x1800645de  bts     eax, 1Ch
0x1800645e2  mov     rcx, [rbp+0FD8h]; this
0x1800645e9  lea     r8, aZwqueryeafileF; "ZwQueryEaFile failed"
0x1800645f0  mov     qword ptr [rsp+10D0h+dwFlagsAndAttributes], r8; bool
0x1800645f5  mov     byte ptr [rsp+10D0h+dwCreationDisposition], dl; char
0x1800645f9  mov     r9d, eax; char *
0x1800645fc  lea     r8, aSrcEppDlpEndpo_16; "src\\epp\\Dlp\\EndpointDlp\\WindowsDelp"...
0x180064603  mov     edx, 6Ch ; 'l'; void *
0x180064608  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18006460d  mov     rbx, [rsp+10D0h+var_1068+8]
0x180064612  mov     rcx, rbx
0x180064615  mov     r8, [rsp+10D0h+var_1068]
0x18006461a  sub     rcx, r8
0x18006461d  mov     edi, 4000h
0x180064622  cmp     rcx, rdi
0x180064625  jbe     short loc_180064630
0x180064627  lea     rbx, [r8+4000h]
0x18006462e  jmp     short loc_180064670
0x180064630  jnb     short loc_180064675
0x180064632  mov     rax, [rsp+10D0h+var_1058]
0x180064637  sub     rax, r8
0x18006463a  cmp     rax, rdi
0x18006463d  jnb     short loc_180064658
0x18006463f  mov     rdx, rdi
0x180064642  lea     rcx, [rsp+10D0h+var_1068]
0x180064647  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18006464c  mov     rbx, [rsp+10D0h+var_1068+8]
0x180064651  mov     r8, [rsp+10D0h+var_1068]
0x180064656  jmp     short loc_180064675
0x180064658  sub     rdi, rcx
0x18006465b  mov     r8, rdi; Size
0x18006465e  xor     edx, edx; Val
0x180064660  mov     rcx, rbx; void *
0x180064663  call    memset
0x180064668  add     rbx, rdi
0x18006466b  mov     r8, [rsp+10D0h+var_1068]; Buffer
0x180064670  mov     [rsp+10D0h+var_1068+8], rbx
0x180064675  sub     ebx, r8d
0x180064678  mov     [rsp+10D0h+RestartScan], 1; RestartScan
0x18006467d  mov     [rsp+10D0h+EaIndex], r14; EaIndex
0x180064682  mov     dword ptr [rsp+10D0h+hTemplateFile], r14d; char *
0x180064687  mov     qword ptr [rsp+10D0h+dwFlagsAndAttributes], r14; EaList
0x18006468c  mov     byte ptr [rsp+10D0h+dwCreationDisposition], r14b; ReturnSingleEntry
0x180064691  mov     r9d, ebx; Length
0x180064694  lea     rdx, [rbp+0FD0h+IoStatusBlock]; IoStatusBlock
0x180064698  mov     rcx, r15; FileHandle
0x18006469b  call    cs:__imp_ZwQueryEaFile
0x1800646a1  mov     r9d, eax
0x1800646a4  shr     eax, 1Fh
0x1800646a7  bts     r9d, 1Ch; char *
0x1800646ac  mov     rcx, [rbp+0FD8h]; this
0x1800646b3  lea     rdx, aZwqueryeafileF; "ZwQueryEaFile failed"
0x1800646ba  mov     qword ptr [rsp+10D0h+dwFlagsAndAttributes], rdx; bool
0x1800646bf  mov     byte ptr [rsp+10D0h+dwCreationDisposition], al; char
0x1800646c3  lea     r8, aSrcEppDlpEndpo_16; "src\\epp\\Dlp\\EndpointDlp\\WindowsDelp"...
0x1800646ca  mov     edx, 7Bh ; '{'; void *
0x1800646cf  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800646d4  mov     rbx, [rsp+10D0h+var_1068]
0x1800646d9  jmp     loc_1800644A2
0x1800646de  xor     r14d, r14d
0x1800646e1  cmp     [rbx], r14d
0x1800646e4  jz      loc_1800644AA
0x1800646ea  cmp     [rbx], edi
0x1800646ec  setnb   al
0x1800646ef  mov     rcx, [rbp+0FD8h]; this
0x1800646f6  lea     rdx, aTheExtendedAtt; "The extended attribute (EA) list is inc"...
0x1800646fd  mov     qword ptr [rsp+10D0h+dwFlagsAndAttributes], rdx; bool
0x180064702  mov     byte ptr [rsp+10D0h+dwCreationDisposition], al; char
0x180064706  mov     r9d, 90000014h; char *
0x18006470c  lea     r8, aSrcEppDlpEndpo_16; "src\\epp\\Dlp\\EndpointDlp\\WindowsDelp"...
0x180064713  mov     edx, 0A4h; void *
0x180064718  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18006471d  mov     eax, [rbx]
0x18006471f  sub     edi, eax
0x180064721  add     rbx, rax
0x180064724  jmp     loc_1800644A5
0x180064729  mov     rax, [r12]
0x18006472d  mov     [rsp+10D0h+var_1080], rax
0x180064732  lea     rax, aFoundEaForTheF; "Found EA for the file"
0x180064739  mov     [rsp+10D0h+var_1078], rax
0x18006473e  lea     rax, [rsp+10D0h+var_1080]
0x180064743  mov     qword ptr [rsp+10D0h+dwFlagsAndAttributes], rax
0x180064748  lea     rax, [rsp+10D0h+var_1078]
0x18006474d  mov     qword ptr [rsp+10D0h+dwCreationDisposition], rax
0x180064752  lea     rdx, byte_1802BDCAD
0x180064759  call    ??$Write@U?$_tlgWrapSz@_W@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x18006475e  jmp     loc_180064538
0x180064763  mov     rcx, r15; hObject
0x180064766  call    cs:__imp_CloseHandle
0x18006476c  jmp     loc_180064577
```
