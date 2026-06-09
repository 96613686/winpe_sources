# CFindQueuedApp::IsMatch(tagTSC_QUEUED_APP const *)

- ea: `0x140010210`
- end: `0x1400105d3`
- name: `?IsMatch@CFindQueuedApp@@UEAAHPEBUtagTSC_QUEUED_APP@@@Z`
- size: `963`
- prototype: `__int64 __fastcall(CFindQueuedApp *__hidden this, const struct tagTSC_QUEUED_APP *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x140010210`
- `0x1400b3ef0`
- `0x140113322`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x140010253`
- `msvcrt!_wcsicmp` at `0x140010253`
- `KERNEL32!LocalFree` at `0x1400105a4`
- `KERNEL32!LocalFree` at `0x1400105b2`
- `KERNEL32!LocalFree` at `0x1400105a4`
- `KERNEL32!LocalFree` at `0x1400105b2`
- `KERNEL32!ReadFile` at `0x1400104b5`
- `KERNEL32!ReadFile` at `0x140010517`
- `KERNEL32!ReadFile` at `0x1400104b5`
- `KERNEL32!ReadFile` at `0x140010517`
- `KERNEL32!GetFileSize` at `0x1400103d6`
- `KERNEL32!GetFileSize` at `0x1400103e3`
- `KERNEL32!GetFileSize` at `0x1400103d6`
- `KERNEL32!GetFileSize` at `0x1400103e3`
- `KERNEL32!CreateFileW` at `0x1400102bc`
- `KERNEL32!CreateFileW` at `0x14001035e`
- `KERNEL32!CreateFileW` at `0x1400102bc`
- `KERNEL32!CreateFileW` at `0x14001035e`
- `KERNEL32!CloseHandle` at `0x140010587`
- `KERNEL32!CloseHandle` at `0x140010596`
- `KERNEL32!CloseHandle` at `0x140010587`
- `KERNEL32!CloseHandle` at `0x140010596`
- `KERNEL32!GetLastError` at `0x1400102d0`
- `KERNEL32!GetLastError` at `0x14001036d`
- `KERNEL32!GetLastError` at `0x1400104bf`
- `KERNEL32!GetLastError` at `0x140010521`
- `KERNEL32!GetLastError` at `0x1400102d0`
- `KERNEL32!GetLastError` at `0x14001036d`
- `KERNEL32!GetLastError` at `0x1400104bf`
- `KERNEL32!GetLastError` at `0x140010521`

## pseudocode

```c
_BOOL8 __fastcall CFindQueuedApp::IsMatch(CFindQueuedApp *this, const struct tagTSC_QUEUED_APP *a2)
{
  __int64 v3; // rcx
  const wchar_t *v5; // rcx
  __int64 v6; // rax
  BOOL v7; // r14d
  const WCHAR *v8; // rcx
  DWORD LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  void *v11; // rbp
  void *v12; // rsi
  HANDLE FileW; // r13
  DWORD v14; // ebx
  unsigned int v15; // eax
  __int64 v16; // rdx
  size_t FileSize; // rdi
  DWORD v18; // eax
  size_t v19; // r15
  unsigned int v20; // eax
  __int64 v21; // rdx
  DWORD NumberOfBytesRead; // [rsp+88h] [rbp+10h] BYREF
  DWORD v24; // [rsp+90h] [rbp+18h] BYREF
  HANDLE hFile; // [rsp+98h] [rbp+20h]

  v3 = *(_QWORD *)a2;
  NumberOfBytesRead = 0;
  v24 = 0;
  v5 = (const wchar_t *)(v3 + 2092);
  if ( v5 )
  {
    v6 = *((_QWORD *)this + 1);
    if ( *(_QWORD *)v6 != -2092 && !_wcsicmp(v5, (const wchar_t *)(*(_QWORD *)v6 + 2092LL)) )
      return 1;
  }
  v7 = 0;
  v8 = (const WCHAR *)(*(_QWORD *)a2 + 4196LL);
  if ( *v8 && *(_WORD *)(**((_QWORD **)this + 1) + 4196LL) )
  {
    hFile = CreateFileW(v8, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    if ( hFile == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          WPP_1db77516aed63344bd47a7ea602c3b99_Traceguids,
          CurrentThreadActivityIdPrefix,
          LastError);
      }
      return v7;
    }
    v11 = 0;
    v12 = 0;
    FileW = CreateFileW((LPCWSTR)(**((_QWORD **)this + 1) + 4196LL), 0x80000000, 1u, 0, 3u, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      v14 = GetLastError();
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_43;
      }
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 30;
      goto LABEL_17;
    }
    FileSize = GetFileSize(hFile, 0);
    v18 = GetFileSize(FileW, 0);
    v19 = v18;
    if ( (_DWORD)FileSize != v18 )
      goto LABEL_43;
    v11 = MIDL_user_allocate((unsigned int)FileSize);
    if ( v11 )
    {
      v12 = MIDL_user_allocate(v19);
      if ( v12 )
      {
        if ( ReadFile(hFile, v11, FileSize, &NumberOfBytesRead, 0) )
        {
          if ( ReadFile(FileW, v12, v19, &v24, 0) )
          {
            if ( NumberOfBytesRead == v24 && NumberOfBytesRead == (_DWORD)FileSize )
              v7 = memcmp_0(v11, v12, FileSize) == 0;
            goto LABEL_43;
          }
          v14 = GetLastError();
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
LABEL_43:
            CloseHandle(hFile);
            if ( FileW != (HANDLE)-1LL )
              CloseHandle(FileW);
            if ( v11 )
              LocalFree(v11);
            if ( v12 )
              LocalFree(v12);
            return v7;
          }
          v15 = RdpWppGetCurrentThreadActivityIdPrefix();
          v16 = 34;
        }
        else
        {
          v14 = GetLastError();
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_43;
          }
          v15 = RdpWppGetCurrentThreadActivityIdPrefix();
          v16 = 33;
        }
LABEL_17:
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, WPP_1db77516aed63344bd47a7ea602c3b99_Traceguids, v15, v14);
        goto LABEL_43;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_43;
      }
      v20 = RdpWppGetCurrentThreadActivityIdPrefix();
      v21 = 32;
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_43;
      }
      v20 = RdpWppGetCurrentThreadActivityIdPrefix();
      v21 = 31;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, WPP_1db77516aed63344bd47a7ea602c3b99_Traceguids, v20);
    goto LABEL_43;
  }
  return v7;
}

```

## disassembly

```asm
0x140010210  mov     rax, rsp
0x140010213  mov     [rax+8], rbx
0x140010217  push    rbp
0x140010218  push    rsi
0x140010219  push    rdi
0x14001021a  push    r12
0x14001021c  push    r13
0x14001021e  push    r14
0x140010220  push    r15
0x140010222  sub     rsp, 40h
0x140010226  xor     r15d, r15d
0x140010229  mov     rdi, rcx
0x14001022c  mov     rcx, [rdx]
0x14001022f  mov     rbx, rdx
0x140010232  mov     [rax+10h], r15d
0x140010236  mov     [rax+18h], r15d
0x14001023a  add     rcx, 82Ch; String1
0x140010241  jz      short loc_140010266
0x140010243  mov     rax, [rdi+8]
0x140010247  mov     rdx, [rax]
0x14001024a  add     rdx, 82Ch; String2
0x140010251  jz      short loc_140010266
0x140010253  call    cs:__imp__wcsicmp
0x140010259  test    eax, eax
0x14001025b  jnz     short loc_140010266
0x14001025d  lea     r14d, [r15+1]
0x140010261  jmp     loc_1400105B8
0x140010266  mov     rcx, [rbx]
0x140010269  mov     r14d, r15d
0x14001026c  add     rcx, 1064h; lpFileName
0x140010273  cmp     [rcx], r15w
0x140010277  jz      loc_1400105B8
0x14001027d  mov     rax, [rdi+8]
0x140010281  mov     rdx, [rax]
0x140010284  cmp     [rdx+1064h], r15w
0x14001028c  jz      loc_1400105B8
0x140010292  mov     r12d, 80h
0x140010298  mov     [rsp+78h+hTemplateFile], r15; hTemplateFile
0x14001029d  mov     [rsp+78h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x1400102a2  xor     r9d, r9d; lpSecurityAttributes
0x1400102a5  mov     edx, 80000000h; dwDesiredAccess
0x1400102aa  lea     ebx, [r12-7Fh]
0x1400102af  lea     r13d, [r12-7Dh]
0x1400102b4  mov     r8d, ebx; dwShareMode
0x1400102b7  mov     [rsp+78h+dwCreationDisposition], r13d; dwCreationDisposition
0x1400102bc  call    cs:__imp_CreateFileW
0x1400102c2  mov     [rsp+78h+hFile], rax
0x1400102ca  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400102ce  jnz     short loc_140010330
0x1400102d0  call    cs:__imp_GetLastError
0x1400102d6  mov     ebx, eax
0x1400102d8  mov     rdx, cs:WPP_GLOBAL_Control
0x1400102df  lea     rcx, WPP_GLOBAL_Control
0x1400102e6  cmp     rdx, rcx
0x1400102e9  jz      loc_1400105B8
0x1400102ef  test    byte ptr [rdx+1Ch], 8
0x1400102f3  jz      loc_1400105B8
0x1400102f9  cmp     byte ptr [rdx+19h], 2
0x1400102fd  jb      loc_1400105B8
0x140010303  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140010308  mov     rcx, cs:WPP_GLOBAL_Control
0x14001030f  lea     edx, [r12-63h]
0x140010314  mov     r9d, eax
0x140010317  mov     [rsp+78h+dwCreationDisposition], ebx
0x14001031b  lea     r8, WPP_1db77516aed63344bd47a7ea602c3b99_Traceguids
0x140010322  mov     rcx, [rcx+10h]
0x140010326  call    WPP_SF_Dd
0x14001032b  jmp     loc_1400105B8
0x140010330  mov     rax, [rdi+8]
0x140010334  xor     r9d, r9d; lpSecurityAttributes
0x140010337  mov     [rsp+78h+hTemplateFile], r15; hTemplateFile
0x14001033c  mov     r8d, ebx; dwShareMode
0x14001033f  mov     [rsp+78h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x140010344  mov     edx, 80000000h; dwDesiredAccess
0x140010349  mov     rbp, r15
0x14001034c  mov     [rsp+78h+dwCreationDisposition], r13d; dwCreationDisposition
0x140010351  mov     rcx, [rax]
0x140010354  mov     rsi, r15
0x140010357  add     rcx, 1064h; lpFileName
0x14001035e  call    cs:__imp_CreateFileW
0x140010364  mov     r13, rax
0x140010367  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001036b  jnz     short loc_1400103CC
0x14001036d  call    cs:__imp_GetLastError
0x140010373  mov     ebx, eax
0x140010375  mov     rdx, cs:WPP_GLOBAL_Control
0x14001037c  lea     rcx, WPP_GLOBAL_Control
0x140010383  cmp     rdx, rcx
0x140010386  jz      loc_14001057F
0x14001038c  test    byte ptr [rdx+1Ch], 8
0x140010390  jz      loc_14001057F
0x140010396  cmp     byte ptr [rdx+19h], 2
0x14001039a  jb      loc_14001057F
0x1400103a0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400103a5  lea     edx, [r13+1Fh]
0x1400103a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400103b0  lea     r8, WPP_1db77516aed63344bd47a7ea602c3b99_Traceguids
0x1400103b7  mov     r9d, eax
0x1400103ba  mov     [rsp+78h+dwCreationDisposition], ebx
0x1400103be  mov     rcx, [rcx+10h]
0x1400103c2  call    WPP_SF_Dd
0x1400103c7  jmp     loc_14001057F
0x1400103cc  mov     rcx, [rsp+78h+hFile]; hFile
0x1400103d4  xor     edx, edx; lpFileSizeHigh
0x1400103d6  call    cs:__imp_GetFileSize
0x1400103dc  xor     edx, edx; lpFileSizeHigh
0x1400103de  mov     rcx, r13; hFile
0x1400103e1  mov     edi, eax
0x1400103e3  call    cs:__imp_GetFileSize
0x1400103e9  mov     r15d, eax
0x1400103ec  cmp     edi, eax
0x1400103ee  jnz     loc_14001057F
0x1400103f4  mov     ecx, edi; size
0x1400103f6  call    MIDL_user_allocate
0x1400103fb  mov     rbp, rax
0x1400103fe  test    rax, rax
0x140010401  jnz     short loc_140010455
0x140010403  mov     rdx, cs:WPP_GLOBAL_Control
0x14001040a  lea     rcx, WPP_GLOBAL_Control
0x140010411  cmp     rdx, rcx
0x140010414  jz      loc_14001057F
0x14001041a  test    byte ptr [rdx+1Ch], 8
0x14001041e  jz      loc_14001057F
0x140010424  cmp     byte ptr [rdx+19h], 2
0x140010428  jb      loc_14001057F
0x14001042e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140010433  lea     edx, [rbp+1Fh]
0x140010436  mov     rcx, cs:WPP_GLOBAL_Control
0x14001043d  lea     r8, WPP_1db77516aed63344bd47a7ea602c3b99_Traceguids
0x140010444  mov     r9d, eax
0x140010447  mov     rcx, [rcx+10h]
0x14001044b  call    WPP_SF_d
0x140010450  jmp     loc_14001057F
0x140010455  mov     rcx, r15; size
0x140010458  call    MIDL_user_allocate
0x14001045d  mov     rsi, rax
0x140010460  test    rax, rax
0x140010463  jnz     short loc_14001049A
0x140010465  mov     rdx, cs:WPP_GLOBAL_Control
0x14001046c  lea     rcx, WPP_GLOBAL_Control
0x140010473  cmp     rdx, rcx
0x140010476  jz      loc_14001057F
0x14001047c  test    byte ptr [rdx+1Ch], 8
0x140010480  jz      loc_14001057F
0x140010486  cmp     byte ptr [rdx+19h], 2
0x14001048a  jb      loc_14001057F
0x140010490  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140010495  lea     edx, [rsi+20h]
0x140010498  jmp     short loc_140010436
0x14001049a  mov     rcx, [rsp+78h+hFile]; hFile
0x1400104a2  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1400104aa  mov     r8d, edi; nNumberOfBytesToRead
0x1400104ad  mov     qword ptr [rsp+78h+dwCreationDisposition], r14; lpOverlapped
0x1400104b2  mov     rdx, rbp; lpBuffer
0x1400104b5  call    cs:__imp_ReadFile
0x1400104bb  test    eax, eax
0x1400104bd  jnz     short loc_140010501
0x1400104bf  call    cs:__imp_GetLastError
0x1400104c5  mov     ebx, eax
0x1400104c7  mov     rdx, cs:WPP_GLOBAL_Control
0x1400104ce  lea     rcx, WPP_GLOBAL_Control
0x1400104d5  cmp     rdx, rcx
0x1400104d8  jz      loc_14001057F
0x1400104de  test    byte ptr [rdx+1Ch], 8
0x1400104e2  jz      loc_14001057F
0x1400104e8  cmp     byte ptr [rdx+19h], 2
0x1400104ec  jb      loc_14001057F
0x1400104f2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400104f7  mov     edx, 21h ; '!'
0x1400104fc  jmp     loc_1400103A9
0x140010501  lea     r9, [rsp+78h+arg_10]; lpNumberOfBytesRead
0x140010509  mov     qword ptr [rsp+78h+dwCreationDisposition], r14; lpOverlapped
0x14001050e  mov     r8d, r15d; nNumberOfBytesToRead
0x140010511  mov     rdx, rsi; lpBuffer
0x140010514  mov     rcx, r13; hFile
0x140010517  call    cs:__imp_ReadFile
0x14001051d  test    eax, eax
0x14001051f  jnz     short loc_140010557
0x140010521  call    cs:__imp_GetLastError
0x140010527  mov     ebx, eax
0x140010529  mov     rdx, cs:WPP_GLOBAL_Control
0x140010530  lea     rcx, WPP_GLOBAL_Control
0x140010537  cmp     rdx, rcx
0x14001053a  jz      short loc_14001057F
0x14001053c  test    byte ptr [rdx+1Ch], 8
0x140010540  jz      short loc_14001057F
0x140010542  cmp     byte ptr [rdx+19h], 2
0x140010546  jb      short loc_14001057F
0x140010548  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14001054d  mov     edx, 22h ; '"'
0x140010552  jmp     loc_1400103A9
0x140010557  mov     eax, [rsp+78h+NumberOfBytesRead]
0x14001055e  cmp     eax, [rsp+78h+arg_10]
0x140010565  jnz     short loc_14001057F
0x140010567  cmp     eax, edi
0x140010569  jnz     short loc_14001057F
0x14001056b  mov     r8, rdi; Size
0x14001056e  mov     rdx, rsi; Buf2
0x140010571  mov     rcx, rbp; Buf1
0x140010574  call    memcmp_0
0x140010579  test    eax, eax
0x14001057b  cmovz   r14d, ebx
0x14001057f  mov     rcx, [rsp+78h+hFile]; hObject
0x140010587  call    cs:__imp_CloseHandle
0x14001058d  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x140010591  jz      short loc_14001059C
0x140010593  mov     rcx, r13; hObject
0x140010596  call    cs:__imp_CloseHandle
0x14001059c  test    rbp, rbp
0x14001059f  jz      short loc_1400105AA
0x1400105a1  mov     rcx, rbp; hMem
0x1400105a4  call    cs:__imp_LocalFree
0x1400105aa  test    rsi, rsi
0x1400105ad  jz      short loc_1400105B8
0x1400105af  mov     rcx, rsi; hMem
0x1400105b2  call    cs:__imp_LocalFree
0x1400105b8  mov     rbx, [rsp+78h+arg_0]
0x1400105c0  mov     eax, r14d
0x1400105c3  add     rsp, 40h
0x1400105c7  pop     r15
0x1400105c9  pop     r14
0x1400105cb  pop     r13
0x1400105cd  pop     r12
0x1400105cf  pop     rdi
0x1400105d0  pop     rsi
0x1400105d1  pop     rbp
0x1400105d2  retn
```
