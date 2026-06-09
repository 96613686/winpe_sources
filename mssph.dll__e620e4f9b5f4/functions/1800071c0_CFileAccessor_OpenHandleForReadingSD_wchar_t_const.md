# CFileAccessor::OpenHandleForReadingSD(wchar_t const *)

- ea: `0x1800071c0`
- end: `0x1800075d4`
- name: `?OpenHandleForReadingSD@CFileAccessor@@AEAAJPEB_W@Z`
- size: `1044`
- prototype: `__int64 __fastcall(CFileAccessor *this, wchar_t *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003970`

## callees

- `0x180002d80`
- `0x180004ec4`
- `0x1800055b0`
- `0x180005720`
- `0x180005d40`
- `0x1800071c0`
- `0x18000a1d0`
- `0x18000b324`
- `0x18000c680`
- `0x18000e7fc`
- `0x18000e878`
- `0x18000e9cc`
- `0x18000fcd0`
- `0x180011135`
- `0x18001e194`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000737e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000737e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007338`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007338`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007308`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007308`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180007407`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180007407`
- `ntdll!RtlNtStatusToDosError` at `0x180007317`
- `ntdll!RtlNtStatusToDosError` at `0x180007317`
- `ntdll!RtlInitUnicodeString` at `0x180007278`
- `ntdll!RtlInitUnicodeString` at `0x180007278`
- `ntdll!NtCreateFile` at `0x1800072ed`
- `ntdll!NtCreateFile` at `0x1800072ed`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180007540`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180007540`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x1800074f2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x1800074f2`

## string_xrefs

- `0x180007569`: `[SrchPHFile] Could not open file for oplock %ls - 0x%08x`
- `0x180007449`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`
- `0x180007520`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`

## pseudocode

```c
__int64 __fastcall CFileAccessor::OpenHandleForReadingSD(CFileAccessor *this, wchar_t *a2)
{
  _BOOL8 is_extended_length_path; // rbx
  NTSTATUS v5; // eax
  NTSTATUS v6; // edi
  __int64 v7; // rbx
  DWORD v8; // ecx
  ULONG v9; // eax
  char *v10; // rdi
  char *v11; // rcx
  signed int v12; // edi
  DWORD LastError; // eax
  DWORD v14; // eax
  DWORD v15; // eax
  DWORD v16; // eax
  DWORD v17; // eax
  _WORD *v18; // rdi
  void *v19; // rcx
  unsigned __int64 v20; // rax
  __int64 v21; // rsi
  unsigned __int64 v22; // rax
  unsigned int *v23; // rax
  PLARGE_INTEGER AllocationSize; // [rsp+20h] [rbp-E0h]
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  int v27; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp-50h] BYREF
  void **v31; // [rsp+C0h] [rbp-40h] BYREF
  PCWSTR SourceString; // [rsp+C8h] [rbp-38h]
  __int64 v33; // [rsp+D0h] [rbp-30h]
  wchar_t v34[68]; // [rsp+D8h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  *((_DWORD *)this + 36) = 0;
  *((_DWORD *)this + 235) = 1;
  is_extended_length_path = wil::is_extended_length_path((wil *)a2, a2);
  SourceString = v34;
  v33 = 65;
  v34[0] = 0;
  v31 = &TLMString<64,64,32767>::`vftable';
  CLMString::Assign((CLMString *)&v31, L"\\??\\", 0, 0xFFFFFFFF);
  ((void (__fastcall *)(void ***, const wchar_t *, _QWORD, __int64))v31[4])(
    &v31,
    &a2[4 * is_extended_length_path],
    HIDWORD(v33),
    0xFFFFFFFFLL);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  FileHandle = 0;
  v5 = NtCreateFile(&FileHandle, 0x20080u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x204000u, 0, 0);
  v6 = v5;
  v7 = -1;
  if ( v5 == 264 )
  {
    CloseHandle(FileHandle);
    v8 = 32;
  }
  else
  {
    v9 = RtlNtStatusToDosError(v5);
    v8 = v9;
    if ( !v9 )
      goto LABEL_8;
    if ( v6 == -1073739511 )
      v9 = 32;
    v8 = v9;
  }
  FileHandle = (void *)-1LL;
LABEL_8:
  SetLastError(v8);
  v10 = (char *)FileHandle;
  v31 = &TLMString<64,64,32767>::`vftable';
  CLMString::DeleteBuf((CLMString *)&v31, v34);
  v11 = (char *)*((_QWORD *)this + 13);
  if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(v11);
  *((_QWORD *)this + 13) = v10;
  if ( (unsigned __int64)(v10 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError != 3 )
    {
      if ( LastError > 0x56 )
      {
        v14 = LastError - 148;
        if ( v14 )
        {
          v15 = v14 - 22;
          if ( v15 )
          {
            v16 = v15 - 1081;
            if ( v16 )
            {
              v17 = v16 - 75;
              if ( !v17 )
                goto LABEL_20;
              if ( v17 != 3024 )
                goto LABEL_26;
            }
            goto LABEL_51;
          }
        }
LABEL_28:
        v12 = -2147216896;
        goto LABEL_48;
      }
      if ( LastError == 86 )
      {
LABEL_20:
        v12 = -2147216891;
LABEL_48:
        LODWORD(AllocationSize) = v12;
        SearchIndexerTrace::Warning(
          (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssph\\\\file\\\\fileacc.cxx\"",
          (const wchar_t *)0x56E,
          (unsigned int)L"[SrchPHFile] Could not open file for oplock %ls - 0x%08x",
          a2,
          AllocationSize);
        return (unsigned int)v12;
      }
      if ( LastError != 2 )
      {
        if ( LastError != 5 )
        {
          if ( LastError != 54 )
          {
            if ( LastError != 58 )
            {
              if ( LastError == 65 )
                goto LABEL_20;
LABEL_26:
              if ( v12 > 0 )
                v12 = (unsigned __int16)v12 | 0x80070000;
              goto LABEL_48;
            }
LABEL_51:
            v12 = -2147216890;
            goto LABEL_48;
          }
          goto LABEL_28;
        }
        goto LABEL_20;
      }
    }
    if ( GetDriveTypeW(*((LPCWSTR *)this + 88)) != 4 )
    {
      v18 = (_WORD *)*((_QWORD *)this + 88);
      v31 = &CLMString::`vftable';
      v19 = v34;
      SourceString = v34;
      LODWORD(v33) = 65;
      if ( !v18 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x91,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
          (const char *)0x80070057LL,
          (int)AllocationSize);
      v20 = -1;
      do
        ++v20;
      while ( v18[v20] );
      if ( v20 > 0xFFFFFFFF )
        goto LABEL_53;
      v21 = (unsigned int)v20;
      v27 = v20;
      v22 = (unsigned int)v20 + 1LL;
      if ( v22 > 0xFFFFFFFF )
        goto LABEL_53;
      if ( (unsigned int)v22 > 0x41 )
      {
        v23 = (unsigned int *)SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(
                                &v27,
                                &FileHandle);
        CLMString::GrowInConstructor((CLMString *)&v31, *v23);
        v19 = (void *)SourceString;
      }
      if ( !is_mul_ok(2u, v21) )
LABEL_53:
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
      memcpy_0(v19, v18, (unsigned int)(2 * v21));
      HIDWORD(v33) = v21;
      SourceString[v21] = 0;
      v31 = &TLMString<64,64,32767>::`vftable';
      if ( (unsigned int)v33 < 0x104 )
        TLMString<192,64,32767>::GrowString(&v31, 260);
      if ( PathStripToRootW((LPWSTR)SourceString) )
      {
        do
          ++v7;
        while ( SourceString[v7] );
        if ( (unsigned int)v7 >= (unsigned int)v33 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0xFE,
            (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
            (const char *)0xCE,
            (unsigned int)AllocationSize);
        HIDWORD(v33) = v7;
        SourceString[(unsigned int)v7] = 0;
        if ( !PathFileExistsW(SourceString) )
        {
          v31 = &TLMString<64,64,32767>::`vftable';
          CLMString::DeleteBuf((CLMString *)&v31, v34);
          goto LABEL_51;
        }
        v31 = &TLMString<64,64,32767>::`vftable';
        CLMString::DeleteBuf((CLMString *)&v31, v34);
      }
      else
      {
        TLMString<64,64,32767>::~TLMString<64,64,32767>(&v31);
      }
    }
    v12 = -2147216895;
    goto LABEL_48;
  }
  return 0;
}

```

## disassembly

```asm
0x1800071c0  mov     [rsp-8+arg_10], rbx
0x1800071c5  push    rbp
0x1800071c6  push    rsi
0x1800071c7  push    rdi
0x1800071c8  push    r12
0x1800071ca  push    r13
0x1800071cc  push    r14
0x1800071ce  push    r15
0x1800071d0  lea     rbp, [rsp-70h]
0x1800071d5  sub     rsp, 170h
0x1800071dc  mov     rax, cs:__security_cookie
0x1800071e3  xor     rax, rsp
0x1800071e6  mov     [rbp+0A0h+var_40], rax
0x1800071ea  mov     r14, rdx
0x1800071ed  mov     rsi, rcx
0x1800071f0  xor     r15d, r15d
0x1800071f3  mov     [rcx+90h], r15d
0x1800071fa  mov     dword ptr [rcx+3ACh], 1
0x180007204  mov     rcx, rdx; this
0x180007207  call    ?is_extended_length_path@wil@@YA_NPEB_W@Z; wil::is_extended_length_path(wchar_t const *)
0x18000720c  movzx   ebx, al
0x18000720f  lea     rax, [rbp+0A0h+var_C8]
0x180007213  mov     [rbp+0A0h+SourceString], rax
0x180007217  mov     [rbp+0A0h+var_D0], 41h ; 'A'
0x18000721f  mov     [rbp+0A0h+var_C8], r15w
0x180007224  lea     r13, ??_7?$TLMString@$0EA@$0EA@$0HPPP@@@6B@; const TLMString<64,64,32767>::`vftable'
0x18000722b  mov     [rbp+0A0h+var_E0], r13
0x18000722f  mov     r12d, 0FFFFFFFFh
0x180007235  mov     r9d, r12d; unsigned int
0x180007238  xor     r8d, r8d; unsigned int
0x18000723b  lea     rdx, asc_18002A8A8; "\\??\\"
0x180007242  lea     rcx, [rbp+0A0h+var_E0]; this
0x180007246  call    ?Assign@CLMString@@UEAAHPEB_WII@Z; CLMString::Assign(wchar_t const *,uint,uint)
0x18000724b  lea     rdx, [r14+rbx*8]
0x18000724f  mov     rax, [rbp+0A0h+var_E0]
0x180007253  mov     r9d, r12d
0x180007256  mov     r8d, dword ptr [rbp+0A0h+var_D0+4]
0x18000725a  lea     rcx, [rbp+0A0h+var_E0]
0x18000725e  mov     rax, [rax+20h]
0x180007262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007267  xorps   xmm0, xmm0
0x18000726a  movups  xmmword ptr [rsp+1A0h+DestinationString.Length], xmm0
0x18000726f  mov     rdx, [rbp+0A0h+SourceString]; SourceString
0x180007273  lea     rcx, [rsp+1A0h+DestinationString]; DestinationString
0x180007278  call    cs:__imp_RtlInitUnicodeString
0x18000727e  mov     qword ptr [rbp+0A0h+ObjectAttributes.Length], 30h ; '0'
0x180007286  mov     qword ptr [rbp+0A0h+ObjectAttributes.Attributes], 40h ; '@'
0x18000728e  mov     [rbp+0A0h+ObjectAttributes.RootDirectory], r15
0x180007292  lea     rax, [rsp+1A0h+DestinationString]
0x180007297  mov     [rbp+0A0h+ObjectAttributes.ObjectName], rax
0x18000729b  xorps   xmm0, xmm0
0x18000729e  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800072a3  movups  xmmword ptr [rbp+0A0h+IoStatusBlock], xmm0
0x1800072a7  mov     [rsp+1A0h+FileHandle], r15
0x1800072ac  mov     [rsp+1A0h+EaLength], r15d; EaLength
0x1800072b1  mov     [rsp+1A0h+EaBuffer], r15; EaBuffer
0x1800072b6  mov     [rsp+1A0h+CreateOptions], 204000h; CreateOptions
0x1800072be  mov     [rsp+1A0h+CreateDisposition], 1; CreateDisposition
0x1800072c6  mov     [rsp+1A0h+ShareAccess], 7; ShareAccess
0x1800072ce  mov     [rsp+1A0h+FileAttributes], 80h; FileAttributes
0x1800072d6  mov     [rsp+1A0h+AllocationSize], r15; unsigned int
0x1800072db  lea     r9, [rbp+0A0h+IoStatusBlock]; IoStatusBlock
0x1800072df  lea     r8, [rbp+0A0h+ObjectAttributes]; ObjectAttributes
0x1800072e3  mov     edx, 20080h; DesiredAccess
0x1800072e8  lea     rcx, [rsp+1A0h+FileHandle]; FileHandle
0x1800072ed  call    cs:__imp_NtCreateFile
0x1800072f3  mov     edi, eax
0x1800072f5  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800072fc  cmp     eax, 108h
0x180007301  jnz     short loc_180007315
0x180007303  mov     rcx, [rsp+1A0h+FileHandle]; hObject
0x180007308  call    cs:__imp_CloseHandle
0x18000730e  mov     ecx, 20h ; ' '
0x180007313  jmp     short loc_180007333
0x180007315  mov     ecx, edi; Status
0x180007317  call    cs:__imp_RtlNtStatusToDosError
0x18000731d  mov     ecx, eax
0x18000731f  test    eax, eax
0x180007321  jz      short loc_180007338
0x180007323  mov     ecx, 20h ; ' '
0x180007328  cmp     edi, 0C0000909h
0x18000732e  cmovz   eax, ecx
0x180007331  mov     ecx, eax; dwErrCode
0x180007333  mov     [rsp+1A0h+FileHandle], rbx
0x180007338  call    cs:__imp_SetLastError
0x18000733e  mov     rdi, [rsp+1A0h+FileHandle]
0x180007343  mov     [rbp+0A0h+var_E0], r13
0x180007347  lea     rdx, [rbp+0A0h+var_C8]; wchar_t *
0x18000734b  lea     rcx, [rbp+0A0h+var_E0]; this
0x18000734f  call    ?DeleteBuf@CLMString@@IEAAXPEB_W@Z; CLMString::DeleteBuf(wchar_t const *)
0x180007354  nop
0x180007355  mov     rcx, [rsi+68h]; hObject
0x180007359  lea     rax, [rcx-1]
0x18000735d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007361  ja      short loc_180007368
0x180007363  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x180007368  mov     [rsi+68h], rdi
0x18000736c  lea     rax, [rdi-1]
0x180007370  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007374  ja      short loc_18000737E
0x180007376  mov     edi, r15d
0x180007379  jmp     loc_180007581
0x18000737e  call    cs:__imp_GetLastError
0x180007384  mov     edi, eax
0x180007386  cmp     eax, 3
0x180007389  jz      short loc_180007400
0x18000738b  cmp     eax, 56h ; 'V'
0x18000738e  ja      short loc_1800073B9
0x180007390  jz      short loc_1800073AF
0x180007392  cmp     eax, 2
0x180007395  jz      short loc_180007400
0x180007397  cmp     eax, 5
0x18000739a  jz      short loc_1800073AF
0x18000739c  cmp     eax, 36h ; '6'
0x18000739f  jz      short loc_1800073F6
0x1800073a1  cmp     eax, 3Ah ; ':'
0x1800073a4  jz      loc_1800075BC
0x1800073aa  cmp     eax, 41h ; 'A'
0x1800073ad  jnz     short loc_1800073E0
0x1800073af  mov     edi, 80041205h
0x1800073b4  jmp     loc_180007562
0x1800073b9  sub     eax, 94h
0x1800073be  jz      short loc_1800073F6
0x1800073c0  sub     eax, 16h
0x1800073c3  jz      short loc_1800073F6
0x1800073c5  sub     eax, 439h
0x1800073ca  jz      loc_1800075BC
0x1800073d0  sub     eax, 4Bh ; 'K'
0x1800073d3  jz      short loc_1800073AF
0x1800073d5  cmp     eax, 0BD0h
0x1800073da  jz      loc_1800075BC
0x1800073e0  test    edi, edi
0x1800073e2  jle     loc_180007562
0x1800073e8  movzx   edi, di
0x1800073eb  or      edi, 80070000h
0x1800073f1  jmp     loc_180007562
0x1800073f6  mov     edi, 80041200h
0x1800073fb  jmp     loc_180007562
0x180007400  mov     rcx, [rsi+2C0h]; lpRootPathName
0x180007407  call    cs:__imp_GetDriveTypeW
0x18000740d  cmp     eax, 4
0x180007410  jz      loc_18000755D
0x180007416  mov     rdi, [rsi+2C0h]
0x18000741d  lea     rax, ??_7CLMString@@6B@; const CLMString::`vftable'
0x180007424  mov     [rbp+0A0h+var_E0], rax
0x180007428  lea     rcx, [rbp+0A0h+var_C8]
0x18000742c  mov     [rbp+0A0h+SourceString], rcx
0x180007430  mov     dword ptr [rbp+0A0h+var_D0], 41h ; 'A'
0x180007437  test    rdi, rdi
0x18000743a  jnz     short loc_18000745B
0x18000743c  mov     rcx, [rbp+0A8h]; this
0x180007443  mov     r9d, 80070057h; char *
0x180007449  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\search\\com"...
0x180007450  mov     edx, 91h; void *
0x180007455  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000745b  mov     rax, rbx
0x18000745e  xchg    ax, ax
0x180007460  inc     rax
0x180007463  cmp     word ptr [rdi+rax*2], 0
0x180007468  jnz     short loc_180007460
0x18000746a  cmp     rax, r12
0x18000746d  ja      loc_1800075CE
0x180007473  mov     esi, eax
0x180007475  mov     [rsp+1A0h+var_138], esi
0x180007479  lea     rax, [rsi+1]
0x18000747d  cmp     rax, r12
0x180007480  ja      loc_1800075CE
0x180007486  cmp     eax, 41h ; 'A'
0x180007489  jbe     short loc_1800074A9
0x18000748b  lea     rdx, [rsp+1A0h+FileHandle]
0x180007490  lea     rcx, [rsp+1A0h+var_138]
0x180007495  call    ??$?HH@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@H@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(int)
0x18000749a  mov     edx, [rax]; unsigned int
0x18000749c  lea     rcx, [rbp+0A0h+var_E0]; this
0x1800074a0  call    ?GrowInConstructor@CLMString@@IEAAXI@Z; CLMString::GrowInConstructor(uint)
0x1800074a5  mov     rcx, [rbp+0A0h+SourceString]; void *
0x1800074a9  lea     rdx, [rsi+rsi]
0x1800074ad  mov     rax, rdx
0x1800074b0  shr     rax, 20h
0x1800074b4  test    eax, eax
0x1800074b6  jnz     loc_1800075CE
0x1800074bc  mov     r8d, edx; Size
0x1800074bf  mov     rdx, rdi; Src
0x1800074c2  call    memcpy_0
0x1800074c7  mov     dword ptr [rbp+0A0h+var_D0+4], esi
0x1800074ca  mov     rax, [rbp+0A0h+SourceString]
0x1800074ce  mov     [rax+rsi*2], r15w
0x1800074d3  mov     [rbp+0A0h+var_E0], r13
0x1800074d7  cmp     dword ptr [rbp+0A0h+var_D0], 104h
0x1800074de  jnb     short loc_1800074EE
0x1800074e0  mov     edx, 104h
0x1800074e5  lea     rcx, [rbp+0A0h+var_E0]
0x1800074e9  call    ?GrowString@?$TLMString@$0MA@$0EA@$0HPPP@@@EEAAXI@Z; TLMString<192,64,32767>::GrowString(uint)
0x1800074ee  mov     rcx, [rbp+0A0h+SourceString]; pszPath
0x1800074f2  call    cs:__imp_PathStripToRootW
0x1800074f8  test    eax, eax
0x1800074fa  jz      loc_1800075C3
0x180007500  mov     rdx, [rbp+0A0h+SourceString]
0x180007504  inc     rbx
0x180007507  cmp     word ptr [rdx+rbx*2], 0
0x18000750c  jnz     short loc_180007504
0x18000750e  cmp     ebx, dword ptr [rbp+0A0h+var_D0]
0x180007511  jb      short loc_180007532
0x180007513  mov     rcx, [rbp+0A8h]; this
0x18000751a  mov     r9d, 0CEh; char *
0x180007520  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180007527  mov     edx, 0FEh; void *
0x18000752c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180007532  mov     dword ptr [rbp+0A0h+var_D0+4], ebx
0x180007535  mov     ecx, ebx
0x180007537  mov     [rdx+rcx*2], r15w
0x18000753c  mov     rcx, [rbp+0A0h+SourceString]; pszPath
0x180007540  call    cs:__imp_PathFileExistsW
0x180007546  nop
0x180007547  test    eax, eax
0x180007549  jz      short loc_1800075AA
0x18000754b  mov     [rbp+0A0h+var_E0], r13
0x18000754f  lea     rdx, [rbp+0A0h+var_C8]; wchar_t *
0x180007553  lea     rcx, [rbp+0A0h+var_E0]; this
0x180007557  call    ?DeleteBuf@CLMString@@IEAAXPEB_W@Z; CLMString::DeleteBuf(wchar_t const *)
0x18000755c  nop
0x18000755d  mov     edi, 80041201h
0x180007562  mov     dword ptr [rsp+1A0h+AllocationSize], edi
0x180007566  mov     r9, r14; wchar_t *
0x180007569  lea     r8, aSrchphfileCoul; "[SrchPHFile] Could not open file for op"...
0x180007570  mov     edx, 56Eh; wchar_t *
0x180007575  lea     rcx, aOnecoreuapBase_11; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000757c  call    ?Warning@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Warning(wchar_t const *,uint,wchar_t const *,...)
0x180007581  mov     eax, edi
0x180007583  mov     rcx, [rbp+0A0h+var_40]
0x180007587  xor     rcx, rsp; StackCookie
0x18000758a  call    __security_check_cookie
0x18000758f  mov     rbx, [rsp+1A0h+arg_10]
0x180007597  add     rsp, 170h
0x18000759e  pop     r15
0x1800075a0  pop     r14
0x1800075a2  pop     r13
0x1800075a4  pop     r12
0x1800075a6  pop     rdi
0x1800075a7  pop     rsi
0x1800075a8  pop     rbp
0x1800075a9  retn
0x1800075aa  mov     [rbp+0A0h+var_E0], r13
0x1800075ae  lea     rdx, [rbp+0A0h+var_C8]; wchar_t *
0x1800075b2  lea     rcx, [rbp+0A0h+var_E0]; this
0x1800075b6  call    ?DeleteBuf@CLMString@@IEAAXPEB_W@Z; CLMString::DeleteBuf(wchar_t const *)
0x1800075bb  nop
0x1800075bc  mov     edi, 80041206h
0x1800075c1  jmp     short loc_180007562
0x1800075c3  lea     rcx, [rbp+0A0h+var_E0]
0x1800075c7  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1800075cc  jmp     short loc_18000755D
0x1800075ce  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
```
