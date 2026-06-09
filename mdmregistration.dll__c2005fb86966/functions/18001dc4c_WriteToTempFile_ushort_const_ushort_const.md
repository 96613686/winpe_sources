# WriteToTempFile(ushort const *,ushort const *)

- ea: `0x18001dc4c`
- end: `0x18001de56`
- name: `?WriteToTempFile@@YAJPEBG0@Z`
- size: `522`
- prototype: `__int64 __fastcall(LPCVOID lpBuffer, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001436c`
- `0x1800284a0`
- `0x18002f1c4`
- `0x18002f6bc`

## callees

- `0x1800026d0`
- `0x1800031a0`
- `0x18000bc44`
- `0x1800141b0`
- `0x18001dc4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dcdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dd50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dcdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dd50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001de17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001de17`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001dde6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001dde6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001dd3b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001dd3b`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18001dccb`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18001dccb`

## string_xrefs

- `0x18001dcab`: `WriteToTempFile`

## pseudocode

```c
__int64 __fastcall WriteToTempFile(_WORD *lpBuffer, const unsigned __int16 *a2)
{
  signed int LastError; // eax
  HANDLE v6; // rbx
  signed int v7; // eax
  _WORD *v8; // rax
  __int64 v9; // rdx
  unsigned int v10; // ecx
  unsigned __int64 v11; // r8
  unsigned __int64 v12; // r8
  unsigned int v13; // ebx
  signed int v14; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-BCh] BYREF
  _QWORD v16[3]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR FileName; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v18[526]; // [rsp+62h] [rbp-9Eh] BYREF

  if ( !byte_180070EC0 )
    return 0;
  v14 = 0;
  NumberOfBytesWritten = 0;
  FileName = 0;
  memset_0(v18, 0, 0x206u);
  v16[0] = "WriteToTempFile";
  v16[1] = &v14;
  if ( !(unsigned int)GetTempPath2W(260, &FileName) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v14 = LastError;
    goto LABEL_26;
  }
  v14 = StringCchCatW(&FileName, 0x104u, a2);
  if ( v14 < 0 )
    goto LABEL_26;
  v6 = CreateFileW(&FileName, 0xC0000000, 0, 0, 2u, 0, 0);
  if ( v6 == (HANDLE)-1LL )
  {
    v7 = GetLastError();
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    v14 = v7;
    goto LABEL_25;
  }
  if ( !lpBuffer )
  {
    v10 = -2147024809;
LABEL_23:
    v14 = v10;
    goto LABEL_24;
  }
  v8 = lpBuffer;
  v9 = 0x7FFFFFFF;
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v9;
  }
  while ( v9 );
  v10 = v9 == 0 ? 0x80070057 : 0;
  v11 = (0x7FFFFFFF - v9) & -(__int64)(v9 != 0);
  if ( !v9 )
    goto LABEL_23;
  v14 = v9 == 0 ? 0x80070057 : 0;
  if ( v11 > 0xFFFFFFFF || (v12 = 2LL * (unsigned int)v11, v12 > 0xFFFFFFFF) )
  {
    v14 = -2147024362;
  }
  else
  {
    v14 = 0;
    if ( !WriteFile(v6, lpBuffer, v12, &NumberOfBytesWritten, 0) )
      v14 = 0;
  }
LABEL_24:
  if ( v6 )
LABEL_25:
    CloseHandle(v6);
LABEL_26:
  v13 = v14;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v16);
  return v13;
}

```

## disassembly

```asm
0x18001dc4c  mov     [rsp-8+arg_10], rbx
0x18001dc51  push    rbp
0x18001dc52  push    rsi
0x18001dc53  push    rdi
0x18001dc54  lea     rbp, [rsp-180h]
0x18001dc5c  sub     rsp, 280h
0x18001dc63  mov     rax, cs:__security_cookie
0x18001dc6a  xor     rax, rsp
0x18001dc6d  mov     [rbp+190h+var_20], rax
0x18001dc74  xor     esi, esi
0x18001dc76  mov     rbx, rdx
0x18001dc79  cmp     cs:byte_180070EC0, sil
0x18001dc80  mov     rdi, rcx
0x18001dc83  jnz     short loc_18001DC8C
0x18001dc85  xor     eax, eax
0x18001dc87  jmp     loc_18001DE33
0x18001dc8c  xor     edx, edx; Val
0x18001dc8e  mov     [rsp+290h+var_250], esi
0x18001dc92  mov     r8d, 206h; Size
0x18001dc98  mov     [rsp+290h+NumberOfBytesWritten], esi
0x18001dc9c  lea     rcx, [rsp+290h+var_22E]; void *
0x18001dca1  mov     [rsp+290h+FileName], si
0x18001dca6  call    memset_0
0x18001dcab  lea     rax, aWritetotempfil; "WriteToTempFile"
0x18001dcb2  mov     ecx, 104h
0x18001dcb7  mov     [rsp+290h+var_248], rax
0x18001dcbc  lea     rdx, [rsp+290h+FileName]
0x18001dcc1  lea     rax, [rsp+290h+var_250]
0x18001dcc6  mov     [rsp+290h+var_240], rax
0x18001dccb  call    cs:__imp_GetTempPath2W
0x18001dcd2  nop     dword ptr [rax+rax+00h]
0x18001dcd7  test    eax, eax
0x18001dcd9  jnz     short loc_18001DCFC
0x18001dcdb  call    cs:__imp_GetLastError
0x18001dce2  nop     dword ptr [rax+rax+00h]
0x18001dce7  test    eax, eax
0x18001dce9  jle     short loc_18001DCF3
0x18001dceb  movzx   eax, ax
0x18001dcee  or      eax, 80070000h
0x18001dcf3  mov     [rsp+290h+var_250], eax
0x18001dcf7  jmp     loc_18001DE23
0x18001dcfc  mov     r8, rbx; unsigned __int16 *
0x18001dcff  lea     rcx, [rsp+290h+FileName]; unsigned __int16 *
0x18001dd04  mov     edx, 104h; unsigned __int64
0x18001dd09  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001dd0e  mov     [rsp+290h+var_250], eax
0x18001dd12  test    eax, eax
0x18001dd14  js      loc_18001DE23
0x18001dd1a  mov     [rsp+290h+hTemplateFile], rsi; hTemplateFile
0x18001dd1f  lea     rcx, [rsp+290h+FileName]; lpFileName
0x18001dd24  mov     [rsp+290h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18001dd28  xor     r9d, r9d; lpSecurityAttributes
0x18001dd2b  xor     r8d, r8d; dwShareMode
0x18001dd2e  mov     [rsp+290h+dwCreationDisposition], 2; dwCreationDisposition
0x18001dd36  mov     edx, 0C0000000h; dwDesiredAccess
0x18001dd3b  call    cs:__imp_CreateFileW
0x18001dd42  nop     dword ptr [rax+rax+00h]
0x18001dd47  mov     rbx, rax
0x18001dd4a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001dd4e  jnz     short loc_18001DD71
0x18001dd50  call    cs:__imp_GetLastError
0x18001dd57  nop     dword ptr [rax+rax+00h]
0x18001dd5c  test    eax, eax
0x18001dd5e  jle     short loc_18001DD68
0x18001dd60  movzx   eax, ax
0x18001dd63  or      eax, 80070000h
0x18001dd68  mov     [rsp+290h+var_250], eax
0x18001dd6c  jmp     loc_18001DE14
0x18001dd71  test    rdi, rdi
0x18001dd74  jz      loc_18001DE06
0x18001dd7a  mov     r9d, 7FFFFFFFh
0x18001dd80  mov     rax, rdi
0x18001dd83  mov     edx, r9d
0x18001dd86  cmp     [rax], si
0x18001dd89  jz      short loc_18001DD95
0x18001dd8b  add     rax, 2
0x18001dd8f  sub     rdx, 1
0x18001dd93  jnz     short loc_18001DD86
0x18001dd95  mov     rax, rdx
0x18001dd98  neg     rax
0x18001dd9b  mov     rax, rdx
0x18001dd9e  sbb     ecx, ecx
0x18001dda0  sub     r9, rdx
0x18001dda3  not     ecx
0x18001dda5  and     ecx, 80070057h
0x18001ddab  neg     rax
0x18001ddae  sbb     r8, r8
0x18001ddb1  and     r8, r9
0x18001ddb4  test    rdx, rdx
0x18001ddb7  jz      short loc_18001DE0B
0x18001ddb9  mov     eax, 0FFFFFFFFh
0x18001ddbe  mov     [rsp+290h+var_250], ecx
0x18001ddc2  cmp     r8, rax
0x18001ddc5  ja      short loc_18001DDFC
0x18001ddc7  mov     r8d, r8d
0x18001ddca  add     r8, r8; nNumberOfBytesToWrite
0x18001ddcd  cmp     r8, rax
0x18001ddd0  ja      short loc_18001DDFC
0x18001ddd2  lea     r9, [rsp+290h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001ddd7  mov     [rsp+290h+var_250], esi
0x18001dddb  mov     rdx, rdi; lpBuffer
0x18001ddde  mov     qword ptr [rsp+290h+dwCreationDisposition], rsi; lpOverlapped
0x18001dde3  mov     rcx, rbx; hFile
0x18001dde6  call    cs:__imp_WriteFile
0x18001dded  nop     dword ptr [rax+rax+00h]
0x18001ddf2  test    eax, eax
0x18001ddf4  jnz     short loc_18001DE0F
0x18001ddf6  mov     [rsp+290h+var_250], esi
0x18001ddfa  jmp     short loc_18001DE0F
0x18001ddfc  mov     [rsp+290h+var_250], 80070216h
0x18001de04  jmp     short loc_18001DE0F
0x18001de06  mov     ecx, 80070057h
0x18001de0b  mov     [rsp+290h+var_250], ecx
0x18001de0f  test    rbx, rbx
0x18001de12  jz      short loc_18001DE23
0x18001de14  mov     rcx, rbx; hObject
0x18001de17  call    cs:__imp_CloseHandle
0x18001de1e  nop     dword ptr [rax+rax+00h]
0x18001de23  mov     ebx, [rsp+290h+var_250]
0x18001de27  lea     rcx, [rsp+290h+var_248]; this
0x18001de2c  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18001de31  mov     eax, ebx
0x18001de33  mov     rcx, [rbp+190h+var_20]
0x18001de3a  xor     rcx, rsp; StackCookie
0x18001de3d  call    __security_check_cookie
0x18001de42  mov     rbx, [rsp+290h+arg_10]
0x18001de4a  add     rsp, 280h
0x18001de51  pop     rdi
0x18001de52  pop     rsi
0x18001de53  pop     rbp
0x18001de54  retn
```
