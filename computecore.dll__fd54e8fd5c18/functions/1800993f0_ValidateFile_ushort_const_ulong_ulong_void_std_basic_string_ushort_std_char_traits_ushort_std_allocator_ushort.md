# ValidateFile(ushort const *,ulong,ulong,void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800993f0`
- end: `0x1800995f9`
- name: `?ValidateFile@@YAHPEBGKKPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `521`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18005e930`

## callees

- `0x1800067c0`
- `0x180009e8c`
- `0x18001e220`
- `0x180020c90`
- `0x1800993f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800995cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800995cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009949c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099507`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099534`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009949c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099507`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099534`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800995a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800995a6`
- `ntdll!RtlFreeHeap` at `0x1800995c3`
- `ntdll!RtlFreeHeap` at `0x1800995c3`
- `ntdll!RtlAllocateHeap` at `0x1800994be`
- `ntdll!RtlAllocateHeap` at `0x1800994be`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800994ef`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800994ef`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18009952a`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18009952a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180099488`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180099488`

## pseudocode

```c
__int64 __fastcall ValidateFile(const WCHAR *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v5; // r14d
  HANDLE FileW; // rsi
  DWORD LastError; // ebx
  WCHAR *Heap; // rdi
  int v9; // ebx
  DWORD dwFlags[4]; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v12; // [rsp+58h] [rbp-B0h]
  HANDLE v13; // [rsp+68h] [rbp-A0h]
  WCHAR *v14; // [rsp+70h] [rbp-98h]
  __int128 v15; // [rsp+78h] [rbp-90h]
  __int64 v16; // [rsp+88h] [rbp-80h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+90h] [rbp-78h] BYREF

  v5 = 0;
  memset(&FileInformation, 0, sizeof(FileInformation));
  v15 = 0;
  v16 = 0;
  dwFlags[0] = 0;
  dwFlags[1] = 1;
  dwFlags[2] = 8;
  dwFlags[3] = 9;
  LODWORD(v12) = 10;
  FileW = CreateFileW(a1, 0x80u, 7u, 0, 3u, 0x100080u, 0);
  v13 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
  }
  else
  {
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xFFFEu);
    v14 = Heap;
    if ( Heap )
    {
      v9 = 0;
      while ( !GetFinalPathNameByHandleW(FileW, Heap, 0x7FFFu, dwFlags[v9]) )
      {
        if ( (unsigned int)++v9 >= 5 )
        {
          LastError = GetLastError();
          if ( !LastError )
            LastError = 2;
          goto LABEL_14;
        }
      }
      if ( GetFileInformationByHandle(FileW, &FileInformation) )
      {
        if ( (FileInformation.dwFileAttributes & 0x10) != 0 )
        {
          LastError = 267;
        }
        else
        {
          try
          {
            *(_OWORD *)dwFlags = 0;
            v12 = 0;
            std::wstring::_Construct<1,unsigned short const *>(dwFlags, Heap);
            std::wstring::operator=(a5, dwFlags);
            std::wstring::~wstring(dwFlags);
            LastError = 0;
            v5 = 1;
          }
          catch ( std::bad_alloc )
          {
            LastError = 14;
            v5 = 0;
            FileW = v13;
            Heap = v14;
          }
        }
      }
      else
      {
        LastError = GetLastError();
      }
    }
    else
    {
      LastError = 14;
    }
LABEL_14:
    CloseHandle(FileW);
    if ( Heap )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  }
  if ( LastError )
    SetLastError(LastError);
  return v5;
}

```

## disassembly

```asm
0x1800993f0  mov     r11, rsp
0x1800993f3  push    rbx
0x1800993f4  push    rsi
0x1800993f5  push    rdi
0x1800993f6  push    r12
0x1800993f8  push    r14
0x1800993fa  push    r15
0x1800993fc  sub     rsp, 0D8h
0x180099403  mov     rax, cs:__security_cookie
0x18009940a  xor     rax, rsp
0x18009940d  mov     [rsp+108h+var_40], rax
0x180099415  mov     r12, [rsp+108h+arg_20]
0x18009941d  xor     r14d, r14d
0x180099420  mov     [rsp+108h+var_C4], r14d
0x180099425  xorps   xmm0, xmm0
0x180099428  xor     eax, eax
0x18009942a  movups  xmmword ptr [r11-78h], xmm0
0x18009942f  movups  xmmword ptr [r11-68h], xmm0
0x180099434  movups  xmmword ptr [r11-58h], xmm0
0x180099439  mov     [r11-48h], eax
0x18009943d  movups  [rsp+108h+var_90], xmm0
0x180099442  mov     [r11-80h], rax
0x180099446  mov     [rsp+108h+dwFlags], eax
0x18009944a  mov     [rsp+108h+dwFlags+4], 1
0x180099452  lea     ebx, [rax+8]
0x180099455  mov     [rsp+108h+dwFlags+8], ebx
0x180099459  mov     [rsp+108h+dwFlags+0Ch], 9
0x180099461  mov     dword ptr [rsp+108h+var_B0], 0Ah
0x180099469  mov     [rsp+108h+hTemplateFile], rax; hTemplateFile
0x18009946e  mov     [rsp+108h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180099476  mov     [rsp+108h+dwCreationDisposition], 3; dwCreationDisposition
0x18009947e  xor     r9d, r9d; lpSecurityAttributes
0x180099481  lea     edx, [rbx+78h]; dwDesiredAccess
0x180099484  lea     r8d, [r14+7]; dwShareMode
0x180099488  call    cs:__imp_CreateFileW
0x18009948e  mov     rsi, rax
0x180099491  mov     [rsp+108h+var_A0], rax
0x180099496  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009949a  jnz     short loc_1800994A9
0x18009949c  call    cs:__imp_GetLastError
0x1800994a2  mov     ebx, eax
0x1800994a4  jmp     loc_1800995C9
0x1800994a9  mov     rcx, gs:60h
0x1800994b2  mov     r8d, 0FFFEh; Size
0x1800994b8  mov     edx, ebx; Flags
0x1800994ba  mov     rcx, [rcx+30h]; HeapHandle
0x1800994be  call    cs:__imp_RtlAllocateHeap
0x1800994c4  mov     rdi, rax
0x1800994c7  mov     [rsp+108h+var_98], rax
0x1800994cc  test    rax, rax
0x1800994cf  jnz     short loc_1800994D9
0x1800994d1  lea     ebx, [rax+0Eh]
0x1800994d4  jmp     loc_1800995A3
0x1800994d9  xor     ebx, ebx
0x1800994db  movsxd  r9, ebx
0x1800994de  mov     r9d, [rsp+r9*4+108h+dwFlags]; dwFlags
0x1800994e3  mov     r8d, 7FFFh; cchFilePath
0x1800994e9  mov     rdx, rdi; lpszFilePath
0x1800994ec  mov     rcx, rsi; hFile
0x1800994ef  call    cs:__imp_GetFinalPathNameByHandleW
0x1800994f5  mov     r15d, eax
0x1800994f8  test    eax, eax
0x1800994fa  jnz     short loc_18009951F
0x1800994fc  inc     ebx
0x1800994fe  cmp     ebx, 5
0x180099501  jb      short loc_1800994DB
0x180099503  test    eax, eax
0x180099505  jnz     short loc_18009951F
0x180099507  call    cs:__imp_GetLastError
0x18009950d  mov     ebx, eax
0x18009950f  test    eax, eax
0x180099511  jnz     loc_1800995A3
0x180099517  lea     ebx, [rax+2]
0x18009951a  jmp     loc_1800995A3
0x18009951f  lea     rdx, [rsp+108h+FileInformation]; lpFileInformation
0x180099527  mov     rcx, rsi; hFile
0x18009952a  call    cs:__imp_GetFileInformationByHandle
0x180099530  test    eax, eax
0x180099532  jnz     short loc_18009953E
0x180099534  call    cs:__imp_GetLastError
0x18009953a  mov     ebx, eax
0x18009953c  jmp     short loc_1800995A3
0x18009953e  test    byte ptr [rsp+108h+FileInformation.dwFileAttributes], 10h
0x180099546  jz      short loc_18009954F
0x180099548  mov     ebx, 10Bh
0x18009954d  jmp     short loc_1800995A3
0x18009954f  xorps   xmm0, xmm0
0x180099552  movups  xmmword ptr [rsp+108h+dwFlags], xmm0
0x180099557  xorps   xmm1, xmm1
0x18009955a  movdqu  [rsp+108h+var_B0], xmm1
0x180099560  mov     r8, r15
0x180099563  mov     rdx, rdi
0x180099566  lea     rcx, [rsp+108h+dwFlags]
0x18009956b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180099570  lea     rdx, [rsp+108h+dwFlags]
0x180099575  mov     rcx, r12
0x180099578  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18009957d  lea     rcx, [rsp+108h+dwFlags]
0x180099582  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180099587  nop
0x180099588  xor     ebx, ebx
0x18009958a  lea     r14d, [rbx+1]
0x18009958e  jmp     short loc_1800995A3
0x180099590  mov     ebx, [rsp+108h+var_C8]
0x180099594  mov     r14d, [rsp+108h+var_C4]
0x180099599  mov     rsi, [rsp+108h+var_A0]
0x18009959e  mov     rdi, [rsp+108h+var_98]
0x1800995a3  mov     rcx, rsi; hObject
0x1800995a6  call    cs:__imp_CloseHandle
0x1800995ac  test    rdi, rdi
0x1800995af  jz      short loc_1800995C9
0x1800995b1  mov     rcx, gs:60h
0x1800995ba  mov     r8, rdi; P
0x1800995bd  xor     edx, edx; Flags
0x1800995bf  mov     rcx, [rcx+30h]; HeapHandle
0x1800995c3  call    cs:__imp_RtlFreeHeap
0x1800995c9  test    ebx, ebx
0x1800995cb  jz      short loc_1800995D5
0x1800995cd  mov     ecx, ebx; dwErrCode
0x1800995cf  call    cs:__imp_SetLastError
0x1800995d5  mov     eax, r14d
0x1800995d8  mov     rcx, [rsp+108h+var_40]
0x1800995e0  xor     rcx, rsp; StackCookie
0x1800995e3  call    __security_check_cookie
0x1800995e8  add     rsp, 0D8h
0x1800995ef  pop     r15
0x1800995f1  pop     r14
0x1800995f3  pop     r12
0x1800995f5  pop     rdi
0x1800995f6  pop     rsi
0x1800995f7  pop     rbx
0x1800995f8  retn
```
