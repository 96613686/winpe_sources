# PERF_SM_MANAGER::PERF_SM_READER::ConnectToActiveMemory(void)

- ea: `0x1800023d8`
- end: `0x18000263f`
- name: `?ConnectToActiveMemory@PERF_SM_READER@PERF_SM_MANAGER@@AEAAXXZ`
- size: `615`
- prototype: `void __fastcall(PERF_SM_MANAGER::PERF_SM_READER *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002024`

## callees

- `0x1800023d8`
- `0x180002a64`
- `0x180002da0`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002459`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800024af`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002459`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800024af`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002402`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000240c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002402`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000240c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002613`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000261d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002613`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000261d`
- `iisutil!PuDbgPrintError` at `0x180002497`
- `iisutil!PuDbgPrintError` at `0x1800024ed`
- `iisutil!PuDbgPrintError` at `0x18000259b`
- `iisutil!PuDbgPrintError` at `0x180002497`
- `iisutil!PuDbgPrintError` at `0x1800024ed`
- `iisutil!PuDbgPrintError` at `0x18000259b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800025a9`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800025d4`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800025a9`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800025d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800025be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800025eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800025be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800025eb`

## string_xrefs

- `0x180002486`: `servercommon\inetsrv\iis\iisrearc\core\prfshmem\perf_sm.cxx`
- `0x1800024e2`: `servercommon\inetsrv\iis\iisrearc\core\prfshmem\perf_sm.cxx`
- `0x180002589`: `servercommon\inetsrv\iis\iisrearc\core\prfshmem\perf_sm.cxx`
- `0x18000245f`: `Copying in the shared memory name failed, ignoring we will try to open an non-existent memory file\n`
- `0x1800024c2`: `Copying in the shared memory name failed, ignoring we will try to open an non-existent memory file\n`
- `0x180002570`: `PERF_SM_MANAGER::PERF_SM_READER::ConnectToActiveMemory`

## pseudocode

```c
void __fastcall PERF_SM_MANAGER::PERF_SM_READER::ConnectToActiveMemory(PERF_SM_MANAGER::PERF_SM_READER *this)
{
  __int64 v2; // rsi
  __int64 v3; // rdi
  __int64 v4; // rax
  int v5; // r14d
  int v6; // r15d
  int v7; // eax
  int v8; // eax
  LPCVOID *v9; // rsi
  HANDLE *v10; // rdi
  int v11; // eax
  const void *v12; // rcx
  void *v13; // rcx
  _BYTE v14[32]; // [rsp+40h] [rbp-59h] BYREF
  LPCWSTR v15; // [rsp+60h] [rbp-39h]
  int v16; // [rsp+70h] [rbp-29h]
  _BYTE v17[32]; // [rsp+78h] [rbp-21h] BYREF
  LPCWSTR lpName; // [rsp+98h] [rbp-1h]
  int v19; // [rsp+A8h] [rbp+Fh]

  STRU::STRU((STRU *)v17);
  STRU::STRU((STRU *)v14);
  v2 = *((_QWORD *)this + 2);
  v3 = 4104LL * *((int *)this + 6);
  *lpName = 0;
  v19 = 0;
  *v15 = 0;
  v16 = 0;
  v4 = *(_QWORD *)(v2 + 16);
  v5 = *(_DWORD *)(v4 + v3 + 4108);
  v6 = *(_DWORD *)(v4 + v3 + 4112);
  v7 = STRU::Copy((STRU *)v17, (const unsigned __int16 *)(v3 + v4 + 4116));
  if ( v7 < 0 && (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
      694,
      "PERF_SM_MANAGER::GetActiveInformation",
      v7,
      "Copying in the shared memory name failed, ignoring we will try to open an non-existent memory file\n");
  v8 = STRU::Copy((STRU *)v14, (const unsigned __int16 *)(v3 + *(_QWORD *)(v2 + 16) + 6164LL));
  if ( v8 < 0 && (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
      704,
      "PERF_SM_MANAGER::GetActiveInformation",
      v8,
      "Copying in the shared memory name failed, ignoring we will try to open an non-existent memory file\n");
  if ( v5 && v19 && v16 )
  {
    if ( v5 == *((_DWORD *)this + 8) )
      goto LABEL_28;
    v9 = (LPCVOID *)((char *)this + 48);
    v10 = (HANDLE *)((char *)this + 40);
    v11 = OpenMemoryFile(lpName, (void **)this + 5, (LPCVOID *)this + 6);
    if ( !v11 )
    {
      v11 = OpenMemoryFile(v15, (void **)this + 7, (LPCVOID *)this + 8);
      if ( !v11 )
      {
        *((_DWORD *)this + 8) = v5;
        goto LABEL_28;
      }
    }
  }
  else
  {
    v11 = 2;
    v9 = (LPCVOID *)((char *)this + 48);
    v10 = (HANDLE *)((char *)this + 40);
  }
  if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
      3575,
      "PERF_SM_MANAGER::PERF_SM_READER::ConnectToActiveMemory",
      v11,
      "Could not connect to counter information for counter set %d\n",
      *((_DWORD *)this + 6));
  }
  if ( *v9 )
  {
    UnmapViewOfFile(*v9);
    *v9 = 0;
  }
  if ( *v10 )
  {
    CloseHandle(*v10);
    *v10 = 0;
  }
  v12 = (const void *)*((_QWORD *)this + 8);
  if ( v12 )
  {
    UnmapViewOfFile(v12);
    *((_QWORD *)this + 8) = 0;
  }
  v13 = (void *)*((_QWORD *)this + 7);
  if ( v13 )
  {
    CloseHandle(v13);
    *((_QWORD *)this + 7) = 0;
  }
  *((_DWORD *)this + 8) = 0;
  v6 = 1;
LABEL_28:
  *((_DWORD *)this + 7) = v6;
  STRU::~STRU((STRU *)v14);
  STRU::~STRU((STRU *)v17);
}

```

## disassembly

```asm
0x1800023d8  push    rbp
0x1800023da  push    rbx
0x1800023db  push    rsi
0x1800023dc  push    rdi
0x1800023dd  push    r14
0x1800023df  push    r15
0x1800023e1  lea     rbp, [rsp-2Fh]
0x1800023e6  sub     rsp, 0C8h
0x1800023ed  mov     rax, cs:__security_cookie
0x1800023f4  xor     rax, rsp
0x1800023f7  mov     [rbp+57h+var_40], rax
0x1800023fb  mov     rbx, rcx
0x1800023fe  lea     rcx, [rbp+57h+var_78]
0x180002402  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002408  lea     rcx, [rbp+57h+var_B0]
0x18000240c  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180002412  movsxd  rdx, dword ptr [rbx+18h]
0x180002416  xor     ecx, ecx
0x180002418  mov     rax, [rbp+57h+lpName]
0x18000241c  mov     rsi, [rbx+10h]
0x180002420  imul    rdi, rdx, 1008h
0x180002427  mov     [rax], cx
0x18000242a  mov     rax, [rbp+57h+var_90]
0x18000242e  mov     [rbp+57h+var_48], ecx
0x180002431  mov     [rax], cx
0x180002434  mov     [rbp+57h+var_80], ecx
0x180002437  lea     rcx, [rbp+57h+var_78]
0x18000243b  mov     rax, [rsi+10h]
0x18000243f  mov     r14d, [rax+rdi+100Ch]
0x180002447  lea     rdx, [rax+1014h]
0x18000244e  mov     r15d, [rax+rdi+1010h]
0x180002456  add     rdx, rdi
0x180002459  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000245f  lea     rcx, aCopyingInTheSh; "Copying in the shared memory name faile"...
0x180002466  test    eax, eax
0x180002468  jns     short loc_18000249D
0x18000246a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180002471  jz      short loc_18000249D
0x180002473  mov     [rsp+0F0h+var_C8], rcx
0x180002478  lea     r9, aPerfSmManagerG; "PERF_SM_MANAGER::GetActiveInformation"
0x18000247f  mov     rcx, cs:g_pDebug
0x180002486  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000248d  mov     r8d, 2B6h
0x180002493  mov     [rsp+0F0h+var_D0], eax
0x180002497  call    cs:__imp_PuDbgPrintError
0x18000249d  mov     rdx, [rsi+10h]
0x1800024a1  lea     rcx, [rbp+57h+var_B0]
0x1800024a5  add     rdx, 1814h
0x1800024ac  add     rdx, rdi
0x1800024af  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800024b5  test    eax, eax
0x1800024b7  jns     short loc_1800024F3
0x1800024b9  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800024c0  jz      short loc_1800024F3
0x1800024c2  lea     rcx, aCopyingInTheSh; "Copying in the shared memory name faile"...
0x1800024c9  mov     r8d, 2C0h
0x1800024cf  mov     [rsp+0F0h+var_C8], rcx
0x1800024d4  lea     r9, aPerfSmManagerG; "PERF_SM_MANAGER::GetActiveInformation"
0x1800024db  mov     rcx, cs:g_pDebug
0x1800024e2  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800024e9  mov     [rsp+0F0h+var_D0], eax
0x1800024ed  call    cs:__imp_PuDbgPrintError
0x1800024f3  test    r14d, r14d
0x1800024f6  jz      short loc_180002547
0x1800024f8  cmp     [rbp+57h+var_48], 0
0x1800024fc  jz      short loc_180002547
0x1800024fe  cmp     [rbp+57h+var_80], 0
0x180002502  jz      short loc_180002547
0x180002504  cmp     r14d, [rbx+20h]
0x180002508  jz      loc_180002606
0x18000250e  mov     rcx, [rbp+57h+lpName]; lpName
0x180002512  lea     rsi, [rbx+30h]
0x180002516  lea     rdi, [rbx+28h]
0x18000251a  mov     r8, rsi; void **
0x18000251d  mov     rdx, rdi; void **
0x180002520  call    ?OpenMemoryFile@@YAKPEBGPEAPEAX1@Z; OpenMemoryFile(ushort const *,void * *,void * *)
0x180002525  test    eax, eax
0x180002527  jnz     short loc_180002554
0x180002529  mov     rcx, [rbp+57h+var_90]; lpName
0x18000252d  lea     r8, [rbx+40h]; void **
0x180002531  lea     rdx, [rbx+38h]; void **
0x180002535  call    ?OpenMemoryFile@@YAKPEBGPEAPEAX1@Z; OpenMemoryFile(ushort const *,void * *,void * *)
0x18000253a  test    eax, eax
0x18000253c  jnz     short loc_180002554
0x18000253e  mov     [rbx+20h], r14d
0x180002542  jmp     loc_180002606
0x180002547  mov     eax, 2
0x18000254c  lea     rsi, [rbx+30h]
0x180002550  lea     rdi, [rbx+28h]
0x180002554  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000255b  jz      short loc_1800025A1
0x18000255d  mov     ecx, [rbx+18h]
0x180002560  test    eax, eax
0x180002562  jle     short loc_18000256C
0x180002564  movzx   eax, ax
0x180002567  or      eax, 80070000h
0x18000256c  mov     [rsp+0F0h+var_C0], ecx
0x180002570  lea     r9, aPerfSmManagerP; "PERF_SM_MANAGER::PERF_SM_READER::Connec"...
0x180002577  lea     rcx, aCouldNotConnec; "Could not connect to counter informatio"...
0x18000257e  mov     r8d, 0DF7h
0x180002584  mov     [rsp+0F0h+var_C8], rcx
0x180002589  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180002590  mov     rcx, cs:g_pDebug
0x180002597  mov     [rsp+0F0h+var_D0], eax
0x18000259b  call    cs:__imp_PuDbgPrintError
0x1800025a1  mov     rcx, [rsi]; lpBaseAddress
0x1800025a4  test    rcx, rcx
0x1800025a7  jz      short loc_1800025B6
0x1800025a9  call    cs:__imp_UnmapViewOfFile
0x1800025af  mov     qword ptr [rsi], 0
0x1800025b6  mov     rcx, [rdi]; hObject
0x1800025b9  test    rcx, rcx
0x1800025bc  jz      short loc_1800025CB
0x1800025be  call    cs:__imp_CloseHandle
0x1800025c4  mov     qword ptr [rdi], 0
0x1800025cb  mov     rcx, [rbx+40h]; lpBaseAddress
0x1800025cf  test    rcx, rcx
0x1800025d2  jz      short loc_1800025E2
0x1800025d4  call    cs:__imp_UnmapViewOfFile
0x1800025da  mov     qword ptr [rbx+40h], 0
0x1800025e2  mov     rcx, [rbx+38h]; hObject
0x1800025e6  test    rcx, rcx
0x1800025e9  jz      short loc_1800025F9
0x1800025eb  call    cs:__imp_CloseHandle
0x1800025f1  mov     qword ptr [rbx+38h], 0
0x1800025f9  mov     dword ptr [rbx+20h], 0
0x180002600  mov     r15d, 1
0x180002606  mov     eax, 1Ch
0x18000260b  lea     rcx, [rbp+57h+var_B0]
0x18000260f  mov     [rbx+rax], r15d
0x180002613  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002619  lea     rcx, [rbp+57h+var_78]
0x18000261d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002623  mov     rcx, [rbp+57h+var_40]
0x180002627  xor     rcx, rsp; StackCookie
0x18000262a  call    __security_check_cookie
0x18000262f  add     rsp, 0C8h
0x180002636  pop     r15
0x180002638  pop     r14
0x18000263a  pop     rdi
0x18000263b  pop     rsi
0x18000263c  pop     rbx
0x18000263d  pop     rbp
0x18000263e  retn
```
