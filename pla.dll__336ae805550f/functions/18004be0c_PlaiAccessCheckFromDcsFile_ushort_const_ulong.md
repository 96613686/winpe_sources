# PlaiAccessCheckFromDcsFile(ushort const *,ulong)

- ea: `0x18004be0c`
- end: `0x18004c31e`
- name: `?PlaiAccessCheckFromDcsFile@@YAJPEBGK@Z`
- size: `1298`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180067cd0`
- `0x1800fed14`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x18002b3a0`
- `0x18004be0c`
- `0x180113c60`
- `0x18013aee0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18004bf6e`
- `msvcrt!_wcsnicmp` at `0x18004bf6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004be6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c23b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c298`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004be6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c23b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c298`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c265`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c265`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004be50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004be50`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004c130`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004c130`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18004c231`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18004c231`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x18004c0fb`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x18004c0fb`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18004be5d`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18004be5d`

## string_xrefs

- `0x18004bf10`: `PlaiAccessCheckFromDcsFile`
- `0x18004c025`: `PlaiAccessCheckFromDcsFile`
- `0x18004c1e0`: `PlaiAccessCheckFromDcsFile`

## pseudocode

```c
__int64 __fastcall PlaiAccessCheckFromDcsFile(const unsigned __int16 *a1)
{
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdi
  __int64 FileW; // r15
  int v8; // eax
  __int64 v9; // rax
  int CollectorSetPath; // eax
  __int64 v11; // rax
  int v12; // r14d
  DWORD v13; // eax
  __int64 v14; // rax
  DWORD v15; // eax
  int v16; // eax
  DWORD v18; // eax
  int v19; // eax
  __int64 v20; // rax
  int v21; // [rsp+70h] [rbp-90h] BYREF
  int v22; // [rsp+78h] [rbp-88h] BYREF
  WINBOOL Wow64Process; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR lpFileName; // [rsp+88h] [rbp-78h] BYREF
  PVOID OldValue; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v26[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v27[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v28[64]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v29[64]; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int16 v30[64]; // [rsp+2A0h] [rbp+1A0h] BYREF

  Wow64Process = 0;
  lpFileName = 0;
  OldValue = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !IsWow64Process(CurrentProcess, &Wow64Process) )
  {
    LastError = GetLastError();
    v4 = PlaiHResultFromWin32(LastError);
    v5 = v4;
    if ( v4 < 0 )
    {
      v21 = 0;
      v22 = v4;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v26, 0x4000000000000800uLL);
        v6 = -1;
        do
          ++v6;
        while ( v26[v6] );
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v22, 4, byte_180147320, 1, &v21, 4);
      }
      return v5;
    }
  }
  FileW = -1;
  if ( _wcsnicmp(L"system\\", a1, 7u) )
  {
    CollectorSetPath = PlaiCreateCollectorSetPath(a1, 0, (unsigned __int16 **)&lpFileName);
    v5 = CollectorSetPath;
    if ( CollectorSetPath < 0 )
    {
      v22 = 0;
      v21 = CollectorSetPath;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_39;
      }
      PlaiWhoAmI(v28, 0x4000000000000800uLL);
      v11 = -1;
      do
        ++v11;
      while ( v28[v11] );
      goto LABEL_16;
    }
LABEL_24:
    v12 = 0;
    if ( Wow64Process )
    {
      if ( Wow64DisableWow64FsRedirection(&OldValue) )
      {
        v5 = 0;
      }
      else
      {
        v18 = GetLastError();
        v19 = PlaiHResultFromWin32(v18);
        v5 = v19;
        if ( v19 < 0 )
        {
          v22 = 0;
          v21 = v19;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_39;
          }
          PlaiWhoAmI(v29, 0x4000000000000800uLL);
          v20 = -1;
          do
            ++v20;
          while ( v29[v20] );
          goto LABEL_16;
        }
      }
      v12 = 1;
    }
    FileW = (__int64)CreateFileW(lpFileName, 1u, 0, 0, 3u, 0x80u, 0);
    if ( FileW == -1 )
    {
      v13 = GetLastError();
      v5 = PlaiHResultFromWin32(v13);
      v22 = 0;
      v21 = v5;
      if ( (_DWORD)xmmword_180169738 )
      {
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v30, 0x4000000000000800uLL);
          v14 = -1;
          do
            ++v14;
          while ( v30[v14] );
          EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v21, 4, byte_180147320, 1, &v22, 4);
        }
      }
    }
    if ( v12 )
    {
      if ( !Wow64RevertWow64FsRedirection(OldValue) )
      {
        v15 = GetLastError();
        v16 = PlaiHResultFromWin32(v15);
        if ( v16 < 0 )
          v5 = v16;
      }
    }
    goto LABEL_39;
  }
  v8 = PlaiCreateCollectorSetPath(a1 + 7, 1, (unsigned __int16 **)&lpFileName);
  v5 = v8;
  if ( v8 >= 0 )
    goto LABEL_24;
  v22 = 0;
  v21 = v8;
  if ( !(_DWORD)xmmword_180169738
    || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
    || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
  {
    goto LABEL_39;
  }
  PlaiWhoAmI(v27, 0x4000000000000800uLL);
  v9 = -1;
  do
    ++v9;
  while ( v27[v9] );
LABEL_16:
  EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v21, 4, byte_180147320, 1, &v22, 4);
LABEL_39:
  if ( lpFileName )
    PlaiFree(lpFileName, 1);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  return v5;
}

```

## disassembly

```asm
0x18004be0c  mov     [rsp-8+arg_8], rbx
0x18004be11  mov     [rsp-8+arg_10], rsi
0x18004be16  push    rbp
0x18004be17  push    rdi
0x18004be18  push    r12
0x18004be1a  push    r14
0x18004be1c  push    r15
0x18004be1e  lea     rbp, [rsp-230h]
0x18004be26  sub     rsp, 330h
0x18004be2d  mov     rax, cs:__security_cookie
0x18004be34  xor     rax, rsp
0x18004be37  mov     [rbp+250h+var_30], rax
0x18004be3e  xor     r12d, r12d
0x18004be41  mov     r14, rcx
0x18004be44  mov     [rbp+250h+Wow64Process], r12d
0x18004be48  mov     [rbp+250h+lpFileName], r12
0x18004be4c  mov     [rbp+250h+OldValue], r12
0x18004be50  call    cs:__imp_GetCurrentProcess
0x18004be56  mov     rcx, rax; hProcess
0x18004be59  lea     rdx, [rbp+250h+Wow64Process]; Wow64Process
0x18004be5d  call    cs:__imp_IsWow64Process
0x18004be63  test    eax, eax
0x18004be65  jnz     loc_18004BF59
0x18004be6b  call    cs:__imp_GetLastError
0x18004be71  mov     ecx, eax; unsigned int
0x18004be73  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18004be78  mov     ebx, eax
0x18004be7a  test    eax, eax
0x18004be7c  jns     loc_18004BF59
0x18004be82  cmp     dword ptr cs:xmmword_180169738, r12d
0x18004be89  mov     [rsp+350h+var_2E0], r12d
0x18004be8e  mov     [rsp+350h+var_2D8], eax
0x18004be92  jz      loc_18004C26B
0x18004be98  mov     rdx, 4000000000000800h; unsigned __int64
0x18004bea2  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004bea9  jz      loc_18004C26B
0x18004beaf  mov     rax, cs:qword_180169748
0x18004beb6  and     rax, rdx
0x18004beb9  cmp     cs:qword_180169748, rax
0x18004bec0  jnz     loc_18004C26B
0x18004bec6  lea     rcx, [rbp+250h+var_2B0]; unsigned __int16 *
0x18004beca  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004becf  lea     rax, [rbp+250h+var_2B0]
0x18004bed3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004bed7  inc     rdi
0x18004beda  cmp     [rax+rdi*2], r12w
0x18004bedf  jnz     short loc_18004BED7
0x18004bee1  lea     rax, [rbp+250h+var_2B0]
0x18004bee5  lea     ecx, [rdi+rdi]
0x18004bee8  add     rcx, 2
0x18004beec  lea     r9, [rsp+350h+var_2D8]
0x18004bef1  mov     [rsp+350h+var_2F0], rcx
0x18004bef6  lea     rdx, PLA_EVENT_ERROR
0x18004befd  mov     [rsp+350h+var_2F8], rax
0x18004bf02  lea     rcx, [rsp+350h+var_2E0]
0x18004bf07  mov     [rsp+350h+var_300], 1Bh
0x18004bf10  lea     rax, aPlaiaccesschec_0; "PlaiAccessCheckFromDcsFile"
0x18004bf17  mov     [rsp+350h+var_308], rax
0x18004bf1c  mov     eax, 4
0x18004bf21  mov     [rsp+350h+var_310], rax
0x18004bf26  mov     [rsp+350h+var_318], rcx
0x18004bf2b  lea     rcx, byte_180147320
0x18004bf32  lea     esi, [rax-3]
0x18004bf35  mov     [rsp+350h+hTemplateFile], rsi
0x18004bf3a  lea     r8d, [rax+1]
0x18004bf3e  mov     qword ptr [rsp+350h+dwFlagsAndAttributes], rcx
0x18004bf43  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18004bf4a  mov     qword ptr [rsp+350h+dwCreationDisposition], rax
0x18004bf4f  call    EventingWriteEvent
0x18004bf54  jmp     loc_18004C26B
0x18004bf59  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004bf5d  lea     rcx, aSystem; "system\\"
0x18004bf64  mov     rdx, r14; String2
0x18004bf67  mov     r15, rdi
0x18004bf6a  lea     r8d, [rdi+8]; MaxCount
0x18004bf6e  call    cs:__imp__wcsnicmp
0x18004bf74  lea     esi, [rdi+2]
0x18004bf77  lea     r8, [rbp+250h+lpFileName]; unsigned __int16 **
0x18004bf7b  test    eax, eax
0x18004bf7d  jnz     loc_18004C06B
0x18004bf83  lea     rcx, [r14+0Eh]; unsigned __int16 *
0x18004bf87  mov     edx, esi; int
0x18004bf89  call    ?PlaiCreateCollectorSetPath@@YAJPEBGHPEAPEAG@Z; PlaiCreateCollectorSetPath(ushort const *,int,ushort * *)
0x18004bf8e  mov     ebx, eax
0x18004bf90  test    eax, eax
0x18004bf92  jns     loc_18004C0EE
0x18004bf98  cmp     dword ptr cs:xmmword_180169738, r12d
0x18004bf9f  mov     [rsp+350h+var_2D8], r12d
0x18004bfa4  mov     [rsp+350h+var_2E0], eax
0x18004bfa8  jz      loc_18004C24D
0x18004bfae  mov     rdx, 4000000000000800h; unsigned __int64
0x18004bfb8  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004bfbf  jz      loc_18004C24D
0x18004bfc5  mov     rax, cs:qword_180169748
0x18004bfcc  and     rax, rdx
0x18004bfcf  cmp     cs:qword_180169748, rax
0x18004bfd6  jnz     loc_18004C24D
0x18004bfdc  lea     rcx, [rbp+250h+var_230]; unsigned __int16 *
0x18004bfe0  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004bfe5  lea     rcx, [rbp+250h+var_230]
0x18004bfe9  mov     rax, rdi
0x18004bfec  inc     rax
0x18004bfef  cmp     [rcx+rax*2], r12w
0x18004bff4  jnz     short loc_18004BFEC
0x18004bff6  lea     ecx, [rax+rax]
0x18004bff9  lea     rax, [rbp+250h+var_230]
0x18004bffd  add     rcx, 2
0x18004c001  lea     r9, [rsp+350h+var_2E0]
0x18004c006  mov     [rsp+350h+var_2F0], rcx
0x18004c00b  lea     rdx, PLA_EVENT_ERROR
0x18004c012  mov     [rsp+350h+var_2F8], rax
0x18004c017  lea     rcx, [rsp+350h+var_2D8]
0x18004c01c  mov     [rsp+350h+var_300], 1Bh
0x18004c025  lea     rax, aPlaiaccesschec_0; "PlaiAccessCheckFromDcsFile"
0x18004c02c  mov     [rsp+350h+var_308], rax
0x18004c031  mov     eax, 4
0x18004c036  mov     [rsp+350h+var_310], rax
0x18004c03b  mov     [rsp+350h+var_318], rcx
0x18004c040  lea     rcx, byte_180147320
0x18004c047  mov     [rsp+350h+hTemplateFile], rsi
0x18004c04c  mov     qword ptr [rsp+350h+dwFlagsAndAttributes], rcx
0x18004c051  lea     r8d, [rax+1]
0x18004c055  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18004c05c  mov     qword ptr [rsp+350h+dwCreationDisposition], rax
0x18004c061  call    EventingWriteEvent
0x18004c066  jmp     loc_18004C24D
0x18004c06b  xor     edx, edx; int
0x18004c06d  mov     rcx, r14; unsigned __int16 *
0x18004c070  call    ?PlaiCreateCollectorSetPath@@YAJPEBGHPEAPEAG@Z; PlaiCreateCollectorSetPath(ushort const *,int,ushort * *)
0x18004c075  mov     ebx, eax
0x18004c077  test    eax, eax
0x18004c079  jns     short loc_18004C0EE
0x18004c07b  cmp     dword ptr cs:xmmword_180169738, r12d
0x18004c082  mov     [rsp+350h+var_2D8], r12d
0x18004c087  mov     [rsp+350h+var_2E0], eax
0x18004c08b  jz      loc_18004C24D
0x18004c091  mov     rdx, 4000000000000800h; unsigned __int64
0x18004c09b  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004c0a2  jz      loc_18004C24D
0x18004c0a8  mov     rax, cs:qword_180169748
0x18004c0af  and     rax, rdx
0x18004c0b2  cmp     cs:qword_180169748, rax
0x18004c0b9  jnz     loc_18004C24D
0x18004c0bf  lea     rcx, [rbp+250h+var_1B0]; unsigned __int16 *
0x18004c0c6  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004c0cb  lea     rcx, [rbp+250h+var_1B0]
0x18004c0d2  mov     rax, rdi
0x18004c0d5  inc     rax
0x18004c0d8  cmp     [rcx+rax*2], r12w
0x18004c0dd  jnz     short loc_18004C0D5
0x18004c0df  lea     ecx, [rax+rax]
0x18004c0e2  lea     rax, [rbp+250h+var_1B0]
0x18004c0e9  jmp     loc_18004BFFD
0x18004c0ee  mov     r14d, r12d
0x18004c0f1  cmp     [rbp+250h+Wow64Process], r12d
0x18004c0f5  jz      short loc_18004C10F
0x18004c0f7  lea     rcx, [rbp+250h+OldValue]; OldValue
0x18004c0fb  call    cs:__imp_Wow64DisableWow64FsRedirection
0x18004c101  test    eax, eax
0x18004c103  jz      loc_18004C298
0x18004c109  mov     ebx, r12d
0x18004c10c  mov     r14d, esi
0x18004c10f  mov     rcx, [rbp+250h+lpFileName]; lpFileName
0x18004c113  xor     r9d, r9d; lpSecurityAttributes
0x18004c116  mov     [rsp+350h+hTemplateFile], r12; hTemplateFile
0x18004c11b  xor     r8d, r8d; dwShareMode
0x18004c11e  mov     [rsp+350h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18004c126  mov     edx, esi; dwDesiredAccess
0x18004c128  mov     [rsp+350h+dwCreationDisposition], 3; dwCreationDisposition
0x18004c130  call    cs:__imp_CreateFileW
0x18004c136  mov     r15, rax
0x18004c139  cmp     rax, rdi
0x18004c13c  jnz     loc_18004C228
0x18004c142  call    cs:__imp_GetLastError
0x18004c148  mov     ecx, eax; unsigned int
0x18004c14a  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18004c14f  cmp     dword ptr cs:xmmword_180169738, r12d
0x18004c156  mov     ebx, eax
0x18004c158  mov     [rsp+350h+var_2D8], r12d
0x18004c15d  mov     [rsp+350h+var_2E0], eax
0x18004c161  jz      loc_18004C228
0x18004c167  mov     rdx, 4000000000000800h; unsigned __int64
0x18004c171  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004c178  jz      loc_18004C228
0x18004c17e  mov     rax, cs:qword_180169748
0x18004c185  and     rax, rdx
0x18004c188  cmp     cs:qword_180169748, rax
0x18004c18f  jnz     loc_18004C228
0x18004c195  lea     rcx, [rbp+250h+var_B0]; unsigned __int16 *
0x18004c19c  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004c1a1  lea     rcx, [rbp+250h+var_B0]
0x18004c1a8  mov     rax, rdi
0x18004c1ab  inc     rax
0x18004c1ae  cmp     [rcx+rax*2], r12w
0x18004c1b3  jnz     short loc_18004C1AB
0x18004c1b5  lea     ecx, [rax+rax]
0x18004c1b8  add     rcx, 2
0x18004c1bc  lea     rax, [rbp+250h+var_B0]
0x18004c1c3  mov     [rsp+350h+var_2F0], rcx
0x18004c1c8  lea     r9, [rsp+350h+var_2E0]
0x18004c1cd  mov     [rsp+350h+var_2F8], rax
0x18004c1d2  lea     rcx, [rsp+350h+var_2D8]
0x18004c1d7  mov     [rsp+350h+var_300], 1Bh
0x18004c1e0  lea     rax, aPlaiaccesschec_0; "PlaiAccessCheckFromDcsFile"
0x18004c1e7  mov     [rsp+350h+var_308], rax
0x18004c1ec  lea     rdx, PLA_EVENT_ERROR
0x18004c1f3  mov     eax, 4
0x18004c1f8  mov     [rsp+350h+var_310], rax
0x18004c1fd  mov     [rsp+350h+var_318], rcx
0x18004c202  lea     rcx, byte_180147320
0x18004c209  mov     [rsp+350h+hTemplateFile], rsi
0x18004c20e  mov     qword ptr [rsp+350h+dwFlagsAndAttributes], rcx
0x18004c213  lea     r8d, [rax+1]
0x18004c217  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18004c21e  mov     qword ptr [rsp+350h+dwCreationDisposition], rax
0x18004c223  call    EventingWriteEvent
0x18004c228  test    r14d, r14d
0x18004c22b  jz      short loc_18004C24D
0x18004c22d  mov     rcx, [rbp+250h+OldValue]; OlValue
0x18004c231  call    cs:__imp_Wow64RevertWow64FsRedirection
0x18004c237  test    eax, eax
0x18004c239  jnz     short loc_18004C24D
0x18004c23b  call    cs:__imp_GetLastError
0x18004c241  mov     ecx, eax; unsigned int
0x18004c243  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18004c248  test    eax, eax
0x18004c24a  cmovs   ebx, eax
0x18004c24d  mov     rcx, [rbp+250h+lpFileName]; lpMem
0x18004c251  test    rcx, rcx
0x18004c254  jz      short loc_18004C25D
0x18004c256  mov     edx, esi; int
0x18004c258  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
0x18004c25d  cmp     r15, rdi
0x18004c260  jz      short loc_18004C26B
0x18004c262  mov     rcx, r15; hObject
0x18004c265  call    cs:__imp_CloseHandle
0x18004c26b  mov     eax, ebx
0x18004c26d  mov     rcx, [rbp+250h+var_30]
0x18004c274  xor     rcx, rsp; StackCookie
0x18004c277  call    __security_check_cookie
0x18004c27c  lea     r11, [rsp+350h+var_20]
0x18004c284  mov     rbx, [r11+38h]
0x18004c288  mov     rsi, [r11+40h]
0x18004c28c  mov     rsp, r11
0x18004c28f  pop     r15
0x18004c291  pop     r14
0x18004c293  pop     r12
0x18004c295  pop     rdi
0x18004c296  pop     rbp
0x18004c297  retn
0x18004c298  call    cs:__imp_GetLastError
0x18004c29e  mov     ecx, eax; unsigned int
0x18004c2a0  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18004c2a5  mov     ebx, eax
0x18004c2a7  test    eax, eax
0x18004c2a9  jns     loc_18004C10C
0x18004c2af  cmp     dword ptr cs:xmmword_180169738, r12d
0x18004c2b6  mov     [rsp+350h+var_2D8], r12d
0x18004c2bb  mov     [rsp+350h+var_2E0], eax
0x18004c2bf  jz      short loc_18004C24D
0x18004c2c1  mov     rdx, 4000000000000800h; unsigned __int64
0x18004c2cb  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004c2d2  jz      loc_18004C24D
0x18004c2d8  mov     rax, cs:qword_180169748
0x18004c2df  and     rax, rdx
0x18004c2e2  cmp     cs:qword_180169748, rax
0x18004c2e9  jnz     loc_18004C24D
0x18004c2ef  lea     rcx, [rbp+250h+var_130]; unsigned __int16 *
0x18004c2f6  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004c2fb  lea     rcx, [rbp+250h+var_130]
0x18004c302  mov     rax, rdi
0x18004c305  inc     rax
0x18004c308  cmp     [rcx+rax*2], r12w
0x18004c30d  jnz     short loc_18004C305
0x18004c30f  lea     ecx, [rax+rax]
0x18004c312  lea     rax, [rbp+250h+var_130]
0x18004c319  jmp     loc_18004BFFD
```
