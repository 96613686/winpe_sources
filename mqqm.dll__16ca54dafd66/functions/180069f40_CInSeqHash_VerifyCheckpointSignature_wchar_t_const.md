# CInSeqHash::VerifyCheckpointSignature(wchar_t const *)

- ea: `0x180069f40`
- end: `0x18006a14e`
- name: `?VerifyCheckpointSignature@CInSeqHash@@AEAAHPEB_W@Z`
- size: `526`
- prototype: `int(CInSeqHash *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18006a154`

## callees

- `0x18000f35c`
- `0x18000fa48`
- `0x18002c4dc`
- `0x18002c574`
- `0x180069f40`
- `0x18009b5ec`

## import_xrefs

- `KERNEL32!DebugBreak` at `0x18006a12e`
- `KERNEL32!DebugBreak` at `0x18006a12e`
- `KERNEL32!GetLastError` at `0x180069fd9`
- `KERNEL32!GetLastError` at `0x18006a06b`
- `KERNEL32!GetLastError` at `0x18006a0c7`
- `KERNEL32!GetLastError` at `0x180069fd9`
- `KERNEL32!GetLastError` at `0x18006a06b`
- `KERNEL32!GetLastError` at `0x18006a0c7`
- `KERNEL32!CloseHandle` at `0x18006a0f2`
- `KERNEL32!CloseHandle` at `0x18006a0f2`
- `KERNEL32!CreateFileW` at `0x180069f9b`
- `KERNEL32!CreateFileW` at `0x180069f9b`
- `KERNEL32!ReadFile` at `0x18006a095`
- `KERNEL32!ReadFile` at `0x18006a095`
- `KERNEL32!SetFilePointer` at `0x18006a024`
- `KERNEL32!SetFilePointer` at `0x18006a024`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInSeqHash::VerifyCheckpointSignature(CInSeqHash *this, const wchar_t *a2)
{
  HANDLE FileW; // rax
  void *v5; // rsi
  DWORD LastError; // eax
  unsigned int v7; // ebx
  DWORD v8; // eax
  __int64 v9; // rdx
  unsigned __int16 v10; // r8
  char *v12; // [rsp+40h] [rbp-28h] BYREF
  DWORD NumberOfBytesRead; // [rsp+70h] [rbp+8h] BYREF
  int Buffer; // [rsp+80h] [rbp+18h] BYREF
  __int64 DistanceToMoveHigh; // [rsp+88h] [rbp+20h] BYREF

  v12 = (char *)this + 8;
  CReadWriteLock::LockWrite((CInSeqHash *)((char *)this + 8));
  NumberOfBytesRead = 0;
  Buffer = 0;
  FileW = CreateFileW(a2, 0x80000000, 0, 0, 3u, 0x80u, 0);
  v5 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LogIllegalPoint((wchar_t *)L"xactin", 0x7EBDu);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 42), 55, &WPP_d47abf12d2c63181d11479d5f9b3f4aa_Traceguids, LastError);
    }
    v7 = 0;
    goto LABEL_21;
  }
  DistanceToMoveHigh = -4;
  v7 = 1;
  if ( SetFilePointer(FileW, -4, (PLONG)&DistanceToMoveHigh + 1, 2u) == -1 )
  {
    LogIllegalPoint((wchar_t *)L"xactin", 0x7EBBu);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 348) & 1) == 0 )
      goto LABEL_15;
    v8 = GetLastError();
    v9 = 56;
  }
  else
  {
    if ( ReadFile(v5, &Buffer, 4u, &NumberOfBytesRead, 0) )
      goto LABEL_15;
    LogIllegalPoint((wchar_t *)L"xactin", 0x7EBCu);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 348) & 1) == 0 )
      goto LABEL_15;
    v8 = GetLastError();
    v9 = 57;
  }
  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 42), v9, &WPP_d47abf12d2c63181d11479d5f9b3f4aa_Traceguids, v8);
LABEL_15:
  CloseHandle(v5);
  if ( NumberOfBytesRead == 4 )
  {
    if ( Buffer == 4660 )
      goto LABEL_21;
    v10 = 32441;
  }
  else
  {
    v10 = 32440;
  }
  LogMsgBOOL(0, (wchar_t *)L"xactin", v10);
  v7 = 0;
  if ( *((_DWORD *)this + 705) )
    DebugBreak();
LABEL_21:
  CSW::~CSW((CSW *)&v12);
  return v7;
}

```

## disassembly

```asm
0x180069f40  mov     [rsp+arg_8], rbx
0x180069f45  push    rbp
0x180069f46  push    rsi
0x180069f47  push    rdi
0x180069f48  sub     rsp, 50h
0x180069f4c  mov     rbx, rdx
0x180069f4f  mov     rbp, rcx
0x180069f52  add     rcx, 8; this
0x180069f56  mov     [rsp+68h+var_28], rcx
0x180069f5b  call    ?LockWrite@CReadWriteLock@@QEAAXXZ; CReadWriteLock::LockWrite(void)
0x180069f60  nop
0x180069f61  mov     [rsp+68h+NumberOfBytesRead], 0
0x180069f69  mov     [rsp+68h+Buffer], 0
0x180069f74  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180069f7d  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180069f85  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180069f8d  xor     r9d, r9d; lpSecurityAttributes
0x180069f90  xor     r8d, r8d; dwShareMode
0x180069f93  mov     edx, 80000000h; dwDesiredAccess
0x180069f98  mov     rcx, rbx; lpFileName
0x180069f9b  call    cs:__imp_CreateFileW
0x180069fa1  mov     rsi, rax
0x180069fa4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180069fa8  jnz     short loc_18006A006
0x180069faa  mov     edx, 7EBDh; unsigned __int16
0x180069faf  lea     rcx, aXactin; "xactin"
0x180069fb6  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x180069fbb  lea     rax, WPP_GLOBAL_Control
0x180069fc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180069fc9  cmp     rcx, rax
0x180069fcc  jz      short loc_180069FFF
0x180069fce  lea     ebx, [rsi+2]
0x180069fd1  test    [rcx+15Ch], bl
0x180069fd7  jz      short loc_180069FFF
0x180069fd9  call    cs:__imp_GetLastError
0x180069fdf  lea     edx, [rsi+38h]
0x180069fe2  mov     r9d, eax
0x180069fe5  lea     r8, WPP_d47abf12d2c63181d11479d5f9b3f4aa_Traceguids
0x180069fec  mov     rcx, cs:WPP_GLOBAL_Control
0x180069ff3  mov     rcx, [rcx+150h]
0x180069ffa  call    WPP_SF_d
0x180069fff  xor     ebx, ebx
0x18006a001  jmp     loc_18006A135
0x18006a006  mov     rdx, 0FFFFFFFFFFFFFFFCh; lDistanceToMove
0x18006a00d  mov     [rsp+68h+DistanceToMoveHigh], rdx
0x18006a015  lea     r9d, [rdx+6]; dwMoveMethod
0x18006a019  lea     r8, [rsp+68h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x18006a021  mov     rcx, rsi; hFile
0x18006a024  call    cs:__imp_SetFilePointer
0x18006a02a  mov     ebx, 1
0x18006a02f  lea     rdi, aXactin; "xactin"
0x18006a036  cmp     eax, 0FFFFFFFFh
0x18006a039  jnz     short loc_18006A076
0x18006a03b  mov     edx, 7EBBh; unsigned __int16
0x18006a040  mov     rcx, rdi; wchar_t *
0x18006a043  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x18006a048  lea     rax, WPP_GLOBAL_Control
0x18006a04f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a056  cmp     rcx, rax
0x18006a059  jz      loc_18006A0EF
0x18006a05f  test    [rcx+15Ch], bl
0x18006a065  jz      loc_18006A0EF
0x18006a06b  call    cs:__imp_GetLastError
0x18006a071  lea     edx, [rbx+37h]
0x18006a074  jmp     short loc_18006A0D2
0x18006a076  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOverlapped
0x18006a07f  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18006a084  mov     r8d, 4; nNumberOfBytesToRead
0x18006a08a  lea     rdx, [rsp+68h+Buffer]; lpBuffer
0x18006a092  mov     rcx, rsi; hFile
0x18006a095  call    cs:__imp_ReadFile
0x18006a09b  test    eax, eax
0x18006a09d  jnz     short loc_18006A0EF
0x18006a09f  mov     edx, 7EBCh; unsigned __int16
0x18006a0a4  mov     rcx, rdi; wchar_t *
0x18006a0a7  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x18006a0ac  lea     rax, WPP_GLOBAL_Control
0x18006a0b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a0ba  cmp     rcx, rax
0x18006a0bd  jz      short loc_18006A0EF
0x18006a0bf  test    [rcx+15Ch], bl
0x18006a0c5  jz      short loc_18006A0EF
0x18006a0c7  call    cs:__imp_GetLastError
0x18006a0cd  mov     edx, 39h ; '9'
0x18006a0d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a0d9  mov     r9d, eax
0x18006a0dc  lea     r8, WPP_d47abf12d2c63181d11479d5f9b3f4aa_Traceguids
0x18006a0e3  mov     rcx, [rcx+150h]
0x18006a0ea  call    WPP_SF_d
0x18006a0ef  mov     rcx, rsi; hObject
0x18006a0f2  call    cs:__imp_CloseHandle
0x18006a0f8  cmp     [rsp+68h+NumberOfBytesRead], 4
0x18006a0fd  jz      short loc_18006A107
0x18006a0ff  mov     r8d, 7EB8h
0x18006a105  jmp     short loc_18006A11A
0x18006a107  cmp     [rsp+68h+Buffer], 1234h
0x18006a112  jz      short loc_18006A135
0x18006a114  mov     r8d, 7EB9h; unsigned __int16
0x18006a11a  xor     ecx, ecx; int
0x18006a11c  mov     rdx, rdi; wchar_t *
0x18006a11f  call    ?LogMsgBOOL@@YAXHPEA_WG@Z; LogMsgBOOL(int,wchar_t *,ushort)
0x18006a124  xor     ebx, ebx
0x18006a126  cmp     [rbp+0B04h], ebx
0x18006a12c  jz      short loc_18006A135
0x18006a12e  call    cs:__imp_DebugBreak
0x18006a134  nop
0x18006a135  lea     rcx, [rsp+68h+var_28]; this
0x18006a13a  call    ??1CSW@@QEAA@XZ; CSW::~CSW(void)
0x18006a13f  mov     eax, ebx
0x18006a141  mov     rbx, [rsp+68h+arg_8]
0x18006a146  add     rsp, 50h
0x18006a14a  pop     rdi
0x18006a14b  pop     rsi
0x18006a14c  pop     rbp
0x18006a14d  retn
```
