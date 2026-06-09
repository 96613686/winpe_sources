# PERF_SM_MANAGER::PERF_SM_READER::ConnectToActiveMemory(void)

- ea: `0x18005c268`
- end: `0x18005c4cf`
- name: `?ConnectToActiveMemory@PERF_SM_READER@PERF_SM_MANAGER@@AEAAXXZ`
- size: `615`
- prototype: `void __fastcall(PERF_SM_MANAGER::PERF_SM_READER *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18005d834`

## callees

- `0x18005c268`
- `0x18005daf8`
- `0x180061060`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c44e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c47b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c44e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c47b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18005c439`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18005c464`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18005c439`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18005c464`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005c4a3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005c4ad`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005c4a3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18005c4ad`
- `iisutil!PuDbgPrintError` at `0x18005c327`
- `iisutil!PuDbgPrintError` at `0x18005c37d`
- `iisutil!PuDbgPrintError` at `0x18005c42b`
- `iisutil!PuDbgPrintError` at `0x18005c327`
- `iisutil!PuDbgPrintError` at `0x18005c37d`
- `iisutil!PuDbgPrintError` at `0x18005c42b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18005c292`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18005c29c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18005c292`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18005c29c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18005c2e9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18005c33f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18005c2e9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18005c33f`

## string_xrefs

- `0x18005c316`: `servercommon\inetsrv\iis\iisrearc\core\prfshmem\perf_sm.cxx`
- `0x18005c372`: `servercommon\inetsrv\iis\iisrearc\core\prfshmem\perf_sm.cxx`
- `0x18005c419`: `servercommon\inetsrv\iis\iisrearc\core\prfshmem\perf_sm.cxx`
- `0x18005c2ef`: `Copying in the shared memory name failed, ignoring we will try to open an non-existent memory file\n`
- `0x18005c352`: `Copying in the shared memory name failed, ignoring we will try to open an non-existent memory file\n`
- `0x18005c400`: `PERF_SM_MANAGER::PERF_SM_READER::ConnectToActiveMemory`

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
  signed int v11; // eax
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
    v11 = OpenMemoryFile(lpName, (void **)this + 5, (void **)this + 6);
    if ( !v11 )
    {
      v11 = OpenMemoryFile(v15, (void **)this + 7, (void **)this + 8);
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
0x18005c268  push    rbp
0x18005c26a  push    rbx
0x18005c26b  push    rsi
0x18005c26c  push    rdi
0x18005c26d  push    r14
0x18005c26f  push    r15
0x18005c271  lea     rbp, [rsp-2Fh]
0x18005c276  sub     rsp, 0C8h
0x18005c27d  mov     rax, cs:__security_cookie
0x18005c284  xor     rax, rsp
0x18005c287  mov     [rbp+57h+var_40], rax
0x18005c28b  mov     rbx, rcx
0x18005c28e  lea     rcx, [rbp+57h+var_78]
0x18005c292  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18005c298  lea     rcx, [rbp+57h+var_B0]
0x18005c29c  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18005c2a2  movsxd  rdx, dword ptr [rbx+18h]
0x18005c2a6  xor     ecx, ecx
0x18005c2a8  mov     rax, [rbp+57h+lpName]
0x18005c2ac  mov     rsi, [rbx+10h]
0x18005c2b0  imul    rdi, rdx, 1008h
0x18005c2b7  mov     [rax], cx
0x18005c2ba  mov     rax, [rbp+57h+var_90]
0x18005c2be  mov     [rbp+57h+var_48], ecx
0x18005c2c1  mov     [rax], cx
0x18005c2c4  mov     [rbp+57h+var_80], ecx
0x18005c2c7  lea     rcx, [rbp+57h+var_78]
0x18005c2cb  mov     rax, [rsi+10h]
0x18005c2cf  mov     r14d, [rax+rdi+100Ch]
0x18005c2d7  lea     rdx, [rax+1014h]
0x18005c2de  mov     r15d, [rax+rdi+1010h]
0x18005c2e6  add     rdx, rdi
0x18005c2e9  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18005c2ef  lea     rcx, aCopyingInTheSh; "Copying in the shared memory name faile"...
0x18005c2f6  test    eax, eax
0x18005c2f8  jns     short loc_18005C32D
0x18005c2fa  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005c301  jz      short loc_18005C32D
0x18005c303  mov     [rsp+0F0h+var_C8], rcx
0x18005c308  lea     r9, aPerfSmManagerG; "PERF_SM_MANAGER::GetActiveInformation"
0x18005c30f  mov     rcx, cs:g_pDebug
0x18005c316  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18005c31d  mov     r8d, 2B6h
0x18005c323  mov     [rsp+0F0h+var_D0], eax
0x18005c327  call    cs:__imp_PuDbgPrintError
0x18005c32d  mov     rdx, [rsi+10h]
0x18005c331  lea     rcx, [rbp+57h+var_B0]
0x18005c335  add     rdx, 1814h
0x18005c33c  add     rdx, rdi
0x18005c33f  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18005c345  test    eax, eax
0x18005c347  jns     short loc_18005C383
0x18005c349  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005c350  jz      short loc_18005C383
0x18005c352  lea     rcx, aCopyingInTheSh; "Copying in the shared memory name faile"...
0x18005c359  mov     r8d, 2C0h
0x18005c35f  mov     [rsp+0F0h+var_C8], rcx
0x18005c364  lea     r9, aPerfSmManagerG; "PERF_SM_MANAGER::GetActiveInformation"
0x18005c36b  mov     rcx, cs:g_pDebug
0x18005c372  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18005c379  mov     [rsp+0F0h+var_D0], eax
0x18005c37d  call    cs:__imp_PuDbgPrintError
0x18005c383  test    r14d, r14d
0x18005c386  jz      short loc_18005C3D7
0x18005c388  cmp     [rbp+57h+var_48], 0
0x18005c38c  jz      short loc_18005C3D7
0x18005c38e  cmp     [rbp+57h+var_80], 0
0x18005c392  jz      short loc_18005C3D7
0x18005c394  cmp     r14d, [rbx+20h]
0x18005c398  jz      loc_18005C496
0x18005c39e  mov     rcx, [rbp+57h+lpName]; lpName
0x18005c3a2  lea     rsi, [rbx+30h]
0x18005c3a6  lea     rdi, [rbx+28h]
0x18005c3aa  mov     r8, rsi; void **
0x18005c3ad  mov     rdx, rdi; void **
0x18005c3b0  call    ?OpenMemoryFile@@YAKPEBGPEAPEAX1@Z; OpenMemoryFile(ushort const *,void * *,void * *)
0x18005c3b5  test    eax, eax
0x18005c3b7  jnz     short loc_18005C3E4
0x18005c3b9  mov     rcx, [rbp+57h+var_90]; lpName
0x18005c3bd  lea     r8, [rbx+40h]; void **
0x18005c3c1  lea     rdx, [rbx+38h]; void **
0x18005c3c5  call    ?OpenMemoryFile@@YAKPEBGPEAPEAX1@Z; OpenMemoryFile(ushort const *,void * *,void * *)
0x18005c3ca  test    eax, eax
0x18005c3cc  jnz     short loc_18005C3E4
0x18005c3ce  mov     [rbx+20h], r14d
0x18005c3d2  jmp     loc_18005C496
0x18005c3d7  mov     eax, 2
0x18005c3dc  lea     rsi, [rbx+30h]
0x18005c3e0  lea     rdi, [rbx+28h]
0x18005c3e4  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18005c3eb  jz      short loc_18005C431
0x18005c3ed  mov     ecx, [rbx+18h]
0x18005c3f0  test    eax, eax
0x18005c3f2  jle     short loc_18005C3FC
0x18005c3f4  movzx   eax, ax
0x18005c3f7  or      eax, 80070000h
0x18005c3fc  mov     [rsp+0F0h+var_C0], ecx
0x18005c400  lea     r9, aPerfSmManagerP_0; "PERF_SM_MANAGER::PERF_SM_READER::Connec"...
0x18005c407  lea     rcx, aCouldNotConnec; "Could not connect to counter informatio"...
0x18005c40e  mov     r8d, 0DF7h
0x18005c414  mov     [rsp+0F0h+var_C8], rcx
0x18005c419  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18005c420  mov     rcx, cs:g_pDebug
0x18005c427  mov     [rsp+0F0h+var_D0], eax
0x18005c42b  call    cs:__imp_PuDbgPrintError
0x18005c431  mov     rcx, [rsi]; lpBaseAddress
0x18005c434  test    rcx, rcx
0x18005c437  jz      short loc_18005C446
0x18005c439  call    cs:__imp_UnmapViewOfFile
0x18005c43f  mov     qword ptr [rsi], 0
0x18005c446  mov     rcx, [rdi]; hObject
0x18005c449  test    rcx, rcx
0x18005c44c  jz      short loc_18005C45B
0x18005c44e  call    cs:__imp_CloseHandle
0x18005c454  mov     qword ptr [rdi], 0
0x18005c45b  mov     rcx, [rbx+40h]; lpBaseAddress
0x18005c45f  test    rcx, rcx
0x18005c462  jz      short loc_18005C472
0x18005c464  call    cs:__imp_UnmapViewOfFile
0x18005c46a  mov     qword ptr [rbx+40h], 0
0x18005c472  mov     rcx, [rbx+38h]; hObject
0x18005c476  test    rcx, rcx
0x18005c479  jz      short loc_18005C489
0x18005c47b  call    cs:__imp_CloseHandle
0x18005c481  mov     qword ptr [rbx+38h], 0
0x18005c489  mov     dword ptr [rbx+20h], 0
0x18005c490  mov     r15d, 1
0x18005c496  mov     eax, 1Ch
0x18005c49b  lea     rcx, [rbp+57h+var_B0]
0x18005c49f  mov     [rbx+rax], r15d
0x18005c4a3  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18005c4a9  lea     rcx, [rbp+57h+var_78]
0x18005c4ad  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18005c4b3  mov     rcx, [rbp+57h+var_40]
0x18005c4b7  xor     rcx, rsp; StackCookie
0x18005c4ba  call    __security_check_cookie
0x18005c4bf  add     rsp, 0C8h
0x18005c4c6  pop     r15
0x18005c4c8  pop     r14
0x18005c4ca  pop     rdi
0x18005c4cb  pop     rsi
0x18005c4cc  pop     rbx
0x18005c4cd  pop     rbp
0x18005c4ce  retn
```
