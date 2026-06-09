# FheFileOperations::ReadCurrentUsn(void *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,__int64 &)

- ea: `0x18003122c`
- end: `0x18003141b`
- name: `?ReadCurrentUsn@FheFileOperations@@YAJPEAXV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEA_J@Z`
- size: `495`
- prototype: `__int64 __fastcall(HANDLE hObject, LPCWSTR *, _QWORD *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000fde8`
- `0x18002f430`
- `0x18002f970`

## callees

- `0x1800062d0`
- `0x180007818`
- `0x180009258`
- `0x18003122c`
- `0x180031642`
- `0x180031680`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800312b2`
- `KERNEL32!GetLastError` at `0x180031350`
- `KERNEL32!GetLastError` at `0x1800312b2`
- `KERNEL32!GetLastError` at `0x180031350`
- `KERNEL32!CloseHandle` at `0x1800313e9`
- `KERNEL32!CloseHandle` at `0x1800313e9`
- `KERNEL32!CreateFileW` at `0x1800312a3`
- `KERNEL32!CreateFileW` at `0x1800312a3`
- `KERNEL32!DeviceIoControl` at `0x180031346`
- `KERNEL32!DeviceIoControl` at `0x180031346`

## pseudocode

```c
__int64 __fastcall FheFileOperations::ReadCurrentUsn(HANDLE hObject, LPCWSTR *a2, _QWORD *a3)
{
  int v6; // ebp
  signed int LastError; // eax
  unsigned int v8; // ebx
  signed int v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  int InBuffer; // [rsp+40h] [rbp-298h] BYREF
  DWORD BytesReturned[3]; // [rsp+44h] [rbp-294h] BYREF
  unsigned int OutBuffer; // [rsp+50h] [rbp-288h] BYREF
  __int16 v16; // [rsp+54h] [rbp-284h]
  __int64 v17; // [rsp+68h] [rbp-270h]

  v6 = 0;
  BytesReturned[0] = 0;
  memset_0(&OutBuffer, 0, 0x248u);
  InBuffer = 131074;
  if ( hObject == (HANDLE)-1LL )
  {
    hObject = CreateFileW(*a2, 0, 7u, 0, 3u, 0x2200080u, 0);
    if ( hObject == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          (unsigned int)&WPP_15a774469b7338d2f0041947fb32ba59_Traceguids,
          (unsigned int)*a2,
          v8);
      goto LABEL_25;
    }
    v6 = 1;
  }
  if ( !DeviceIoControl(hObject, 0x900EBu, &InBuffer, 4u, &OutBuffer, 0x248u, BytesReturned, 0) )
  {
    v9 = GetLastError();
    v8 = v9;
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_23;
    v11 = 11;
    goto LABEL_22;
  }
  if ( BytesReturned[0] >= 0x20 && OutBuffer >= 0x20 && v16 == 2 )
  {
    v8 = 0;
    *a3 = v17;
    goto LABEL_23;
  }
  v8 = -2147418113;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = 12;
LABEL_22:
    WPP_SF_d(v10[2], v11, &WPP_15a774469b7338d2f0041947fb32ba59_Traceguids, v8);
  }
LABEL_23:
  if ( v6 )
    CloseHandle(hObject);
LABEL_25:
  ATL::CStringData::Release((ATL::CStringData *)(*a2 - 12));
  return v8;
}

```

## disassembly

```asm
0x18003122c  push    rbx
0x18003122e  push    rbp
0x18003122f  push    rsi
0x180031230  push    rdi
0x180031231  push    r14
0x180031233  sub     rsp, 2B0h
0x18003123a  mov     rax, cs:__security_cookie
0x180031241  xor     rax, rsp
0x180031244  mov     [rsp+2D8h+var_38], rax
0x18003124c  mov     r14, r8
0x18003124f  mov     rsi, rdx
0x180031252  mov     rdi, rcx
0x180031255  xor     ebp, ebp
0x180031257  xor     edx, edx; Val
0x180031259  mov     [rsp+2D8h+BytesReturned], ebp
0x18003125d  mov     r8d, 248h; Size
0x180031263  lea     rcx, [rsp+2D8h+OutBuffer]; void *
0x180031268  call    memset_0
0x18003126d  mov     [rsp+2D8h+InBuffer], 20002h
0x180031275  lea     ebx, [rbp+2]
0x180031278  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18003127c  jnz     loc_18003130E
0x180031282  mov     rcx, [rsi]; lpFileName
0x180031285  lea     r8d, [rbp+7]; dwShareMode
0x180031289  mov     [rsp+2D8h+hTemplateFile], rbp; hTemplateFile
0x18003128e  xor     r9d, r9d; lpSecurityAttributes
0x180031291  mov     [rsp+2D8h+dwFlagsAndAttributes], 2200080h; dwFlagsAndAttributes
0x180031299  xor     edx, edx; dwDesiredAccess
0x18003129b  mov     [rsp+2D8h+dwCreationDisposition], 3; dwCreationDisposition
0x1800312a3  call    cs:__imp_CreateFileW
0x1800312a9  mov     rdi, rax
0x1800312ac  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800312b0  jnz     short loc_180031309
0x1800312b2  call    cs:__imp_GetLastError
0x1800312b8  mov     ebx, eax
0x1800312ba  test    eax, eax
0x1800312bc  jle     short loc_1800312C7
0x1800312be  movzx   ebx, ax
0x1800312c1  or      ebx, 80070000h
0x1800312c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800312ce  lea     rax, WPP_GLOBAL_Control
0x1800312d5  cmp     rcx, rax
0x1800312d8  jz      loc_1800313EF
0x1800312de  test    byte ptr [rcx+1Ch], 1
0x1800312e2  jz      loc_1800313EF
0x1800312e8  mov     r9, [rsi]
0x1800312eb  lea     r8, WPP_15a774469b7338d2f0041947fb32ba59_Traceguids
0x1800312f2  mov     rcx, [rcx+10h]
0x1800312f6  mov     edx, 0Ah
0x1800312fb  mov     [rsp+2D8h+dwCreationDisposition], ebx
0x1800312ff  call    WPP_SF_Sd
0x180031304  jmp     loc_1800313EF
0x180031309  mov     ebp, 1
0x18003130e  mov     [rsp+2D8h+lpOverlapped], 0; lpOverlapped
0x180031317  lea     rax, [rsp+2D8h+BytesReturned]
0x18003131c  mov     [rsp+2D8h+hTemplateFile], rax; lpBytesReturned
0x180031321  lea     r8, [rsp+2D8h+InBuffer]; lpInBuffer
0x180031326  lea     rax, [rsp+2D8h+OutBuffer]
0x18003132b  mov     [rsp+2D8h+dwFlagsAndAttributes], 248h; nOutBufferSize
0x180031333  mov     r9d, 4; nInBufferSize
0x180031339  mov     qword ptr [rsp+2D8h+dwCreationDisposition], rax; lpOutBuffer
0x18003133e  mov     edx, 900EBh; dwIoControlCode
0x180031343  mov     rcx, rdi; hDevice
0x180031346  call    cs:__imp_DeviceIoControl
0x18003134c  test    eax, eax
0x18003134e  jnz     short loc_180031385
0x180031350  call    cs:__imp_GetLastError
0x180031356  mov     ebx, eax
0x180031358  test    eax, eax
0x18003135a  jle     short loc_180031365
0x18003135c  movzx   ebx, ax
0x18003135f  or      ebx, 80070000h
0x180031365  mov     rcx, cs:WPP_GLOBAL_Control
0x18003136c  lea     rax, WPP_GLOBAL_Control
0x180031373  cmp     rcx, rax
0x180031376  jz      short loc_1800313DC
0x180031378  test    byte ptr [rcx+1Ch], 1
0x18003137c  jz      short loc_1800313DC
0x18003137e  mov     edx, 0Bh
0x180031383  jmp     short loc_1800313C9
0x180031385  cmp     [rsp+2D8h+BytesReturned], 20h ; ' '
0x18003138a  jb      short loc_1800313A6
0x18003138c  cmp     [rsp+2D8h+OutBuffer], 20h ; ' '
0x180031391  jb      short loc_1800313A6
0x180031393  cmp     [rsp+2D8h+var_284], bx
0x180031398  jnz     short loc_1800313A6
0x18003139a  mov     rax, [rsp+2D8h+var_270]
0x18003139f  xor     ebx, ebx
0x1800313a1  mov     [r14], rax
0x1800313a4  jmp     short loc_1800313DC
0x1800313a6  mov     ebx, 8000FFFFh
0x1800313ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800313b2  lea     rax, WPP_GLOBAL_Control
0x1800313b9  cmp     rcx, rax
0x1800313bc  jz      short loc_1800313DC
0x1800313be  test    byte ptr [rcx+1Ch], 1
0x1800313c2  jz      short loc_1800313DC
0x1800313c4  mov     edx, 0Ch
0x1800313c9  mov     rcx, [rcx+10h]
0x1800313cd  lea     r8, WPP_15a774469b7338d2f0041947fb32ba59_Traceguids
0x1800313d4  mov     r9d, ebx
0x1800313d7  call    WPP_SF_d
0x1800313dc  test    ebp, ebp
0x1800313de  jz      short loc_1800313EF
0x1800313e0  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800313e4  jz      short loc_1800313EF
0x1800313e6  mov     rcx, rdi; hObject
0x1800313e9  call    cs:__imp_CloseHandle
0x1800313ef  mov     rcx, [rsi]
0x1800313f2  sub     rcx, 18h; this
0x1800313f6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800313fb  mov     eax, ebx
0x1800313fd  mov     rcx, [rsp+2D8h+var_38]
0x180031405  xor     rcx, rsp; StackCookie
0x180031408  call    __security_check_cookie
0x18003140d  add     rsp, 2B0h
0x180031414  pop     r14
0x180031416  pop     rdi
0x180031417  pop     rsi
0x180031418  pop     rbp
0x180031419  pop     rbx
0x18003141a  retn
```
