# RetrieveFormatFileAttributes(wchar_t const *,int *,_LARGE_INTEGER *)

- ea: `0x180145410`
- end: `0x1801455de`
- name: `?RetrieveFormatFileAttributes@@YAJPEB_WPEAHPEAT_LARGE_INTEGER@@@Z`
- size: `462`
- prototype: `__int64 __fastcall(const wchar_t *, int *, union _LARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1801441b0`

## callees

- `0x180003d80`
- `0x180145410`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801454bd`
- `KERNEL32!GetLastError` at `0x1801454c7`
- `KERNEL32!GetLastError` at `0x180145560`
- `KERNEL32!GetLastError` at `0x1801454bd`
- `KERNEL32!GetLastError` at `0x1801454c7`
- `KERNEL32!GetLastError` at `0x180145560`
- `KERNEL32!ReadFile` at `0x180145556`
- `KERNEL32!ReadFile` at `0x180145556`
- `KERNEL32!GetFileSize` at `0x1801454af`
- `KERNEL32!GetFileSize` at `0x1801454af`
- `KERNEL32!CreateFileW` at `0x180145498`
- `KERNEL32!CreateFileW` at `0x180145498`
- `KERNEL32!CloseHandle` at `0x18014550b`
- `KERNEL32!CloseHandle` at `0x1801455a1`
- `KERNEL32!CloseHandle` at `0x18014550b`
- `KERNEL32!CloseHandle` at `0x1801455a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RetrieveFormatFileAttributes(const wchar_t *a1, int *a2, union _LARGE_INTEGER *a3)
{
  void **v5; // rax
  HANDLE FileW; // rax
  signed int LastError; // eax
  signed int v8; // ebx
  __int64 v9; // rcx
  void (__fastcall *v10)(CFileReadStream *__hidden); // rax
  char Buffer; // [rsp+44h] [rbp-3Ch] BYREF
  char Buffer_1; // [rsp+45h] [rbp-3Bh]
  _QWORD v14[2]; // [rsp+48h] [rbp-38h] BYREF
  DWORD FileSizeHigh[4]; // [rsp+58h] [rbp-28h] BYREF
  DWORD NumberOfBytesRead; // [rsp+68h] [rbp-18h] BYREF

  v5 = &CFileReadStream::`vftable';
  v14[0] = &CFileReadStream::`vftable';
  v14[1] = 1;
  *(__m128i *)FileSizeHigh = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  NumberOfBytesRead = 0;
  if ( a1 && *a1 )
  {
    FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x8100080u, 0);
    *(_QWORD *)FileSizeHigh = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      FileSizeHigh[2] = GetFileSize(FileW, &FileSizeHigh[3]);
      if ( FileSizeHigh[2] != -1 || !GetLastError() )
      {
        v9 = *(_QWORD *)FileSizeHigh;
        goto LABEL_19;
      }
    }
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 >= 0 )
      goto LABEL_17;
    v5 = (void **)v14[0];
  }
  else
  {
    v8 = -2147221303;
  }
  v10 = (void (__fastcall *)(CFileReadStream *__hidden))v5[7];
  if ( v10 != CFileReadStream::Close )
  {
    v10((CFileReadStream *)v14);
LABEL_17:
    v9 = *(_QWORD *)FileSizeHigh;
    goto LABEL_18;
  }
  v9 = *(_QWORD *)FileSizeHigh;
  if ( *(_QWORD *)FileSizeHigh != -1 )
  {
    CloseHandle(*(HANDLE *)FileSizeHigh);
    v9 = -1;
    *(_QWORD *)FileSizeHigh = -1;
  }
  *(_QWORD *)&FileSizeHigh[2] = -1;
LABEL_18:
  if ( v8 < 0 )
    goto LABEL_31;
LABEL_19:
  if ( a2 )
  {
    if ( v9 != -1 )
    {
      if ( !ReadFile((HANDLE)v9, &Buffer, 2u, &NumberOfBytesRead, 0) )
        GetLastError();
      v9 = *(_QWORD *)FileSizeHigh;
    }
    if ( Buffer == 49 )
    {
      if ( ((Buffer_1 - 48) & 0xF6) != 0 || Buffer_1 == 57 )
      {
LABEL_27:
        *a2 = 1;
        goto LABEL_28;
      }
    }
    else if ( (unsigned __int8)(Buffer - 52) > 5u || Buffer_1 != 46 )
    {
      goto LABEL_27;
    }
    *a2 = 0;
  }
LABEL_28:
  if ( a3 )
    *a3 = *(union _LARGE_INTEGER *)&FileSizeHigh[2];
  v8 = 0;
LABEL_31:
  v14[0] = &CFileReadStream::`vftable';
  if ( v9 != -1 )
    CloseHandle((HANDLE)v9);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180145410  mov     [rsp-28h+arg_18], rbx
0x180145415  push    rbp
0x180145416  push    rsi
0x180145417  push    rdi
0x180145418  push    r14
0x18014541a  push    r15
0x18014541c  mov     rbp, rsp
0x18014541f  sub     rsp, 80h
0x180145426  mov     rax, cs:__security_cookie
0x18014542d  xor     rax, rsp
0x180145430  mov     [rbp+var_10], rax
0x180145434  mov     rsi, r8
0x180145437  mov     rdi, rdx
0x18014543a  xorps   xmm0, xmm0
0x18014543d  movups  [rbp+var_38], xmm0
0x180145441  lea     r15, ??_7CFileReadStream@@6B@; const CFileReadStream::`vftable'
0x180145448  mov     rax, r15
0x18014544b  mov     qword ptr [rbp+var_38], rax
0x18014544f  mov     dword ptr [rbp+var_38+8], 1
0x180145456  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18014545e  movdqu  xmmword ptr [rbp+FileSizeHigh], xmm0
0x180145463  xor     r14d, r14d
0x180145466  mov     [rbp+NumberOfBytesRead], r14d
0x18014546a  test    rcx, rcx
0x18014546d  jz      short loc_1801454EC
0x18014546f  cmp     [rcx], r14w
0x180145473  jz      short loc_1801454EC
0x180145475  mov     [rsp+80h+hTemplateFile], r14; hTemplateFile
0x18014547a  mov     [rsp+80h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x180145482  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x18014548a  xor     r9d, r9d; lpSecurityAttributes
0x18014548d  mov     edx, 80000000h; dwDesiredAccess
0x180145492  mov     r8d, 1; dwShareMode
0x180145498  call    cs:__imp_CreateFileW
0x18014549e  mov     qword ptr [rbp+FileSizeHigh], rax
0x1801454a2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801454a6  jz      short loc_1801454C7
0x1801454a8  lea     rdx, [rbp+FileSizeHigh+0Ch]; lpFileSizeHigh
0x1801454ac  mov     rcx, rax; hFile
0x1801454af  call    cs:__imp_GetFileSize
0x1801454b5  mov     [rbp+FileSizeHigh+8], eax
0x1801454b8  cmp     eax, 0FFFFFFFFh
0x1801454bb  jnz     short loc_1801454E6
0x1801454bd  call    cs:__imp_GetLastError
0x1801454c3  test    eax, eax
0x1801454c5  jz      short loc_1801454E6
0x1801454c7  call    cs:__imp_GetLastError
0x1801454cd  test    eax, eax
0x1801454cf  mov     ebx, eax
0x1801454d1  jle     short loc_1801454DC
0x1801454d3  movzx   ebx, ax
0x1801454d6  or      ebx, 80070000h
0x1801454dc  test    ebx, ebx
0x1801454de  jns     short loc_180145530
0x1801454e0  mov     rax, qword ptr [rbp+var_38]
0x1801454e4  jmp     short loc_1801454F1
0x1801454e6  mov     rcx, qword ptr [rbp+FileSizeHigh]
0x1801454ea  jmp     short loc_180145538
0x1801454ec  mov     ebx, 800400C9h
0x1801454f1  mov     rax, [rax+38h]
0x1801454f5  lea     rcx, ?Close@CFileReadStream@@UEAAXXZ; CFileReadStream::Close(void)
0x1801454fc  cmp     rax, rcx
0x1801454ff  jnz     short loc_180145526
0x180145501  mov     rcx, qword ptr [rbp+FileSizeHigh]; hObject
0x180145505  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180145509  jz      short loc_18014551C
0x18014550b  call    cs:__imp_CloseHandle
0x180145511  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180145518  mov     qword ptr [rbp+FileSizeHigh], rcx
0x18014551c  mov     qword ptr [rbp+FileSizeHigh+8], 0FFFFFFFFFFFFFFFFh
0x180145524  jmp     short loc_180145534
0x180145526  lea     rcx, [rbp+var_38]
0x18014552a  call    cs:__guard_dispatch_icall_fptr
0x180145530  mov     rcx, qword ptr [rbp+FileSizeHigh]; hFile
0x180145534  test    ebx, ebx
0x180145536  js      short loc_180145597
0x180145538  test    rdi, rdi
0x18014553b  jz      short loc_180145588
0x18014553d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180145541  jz      short loc_18014556A
0x180145543  mov     qword ptr [rsp+80h+dwCreationDisposition], r14; lpOverlapped
0x180145548  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18014554c  mov     r8d, 2; nNumberOfBytesToRead
0x180145552  lea     rdx, [rbp+Buffer]; lpBuffer
0x180145556  call    cs:__imp_ReadFile
0x18014555c  test    eax, eax
0x18014555e  jnz     short loc_180145566
0x180145560  call    cs:__imp_GetLastError
0x180145566  mov     rcx, qword ptr [rbp+FileSizeHigh]; hObject
0x18014556a  movzx   eax, [rbp+Buffer]
0x18014556e  cmp     al, 31h ; '1'
0x180145570  jnz     short loc_1801455CC
0x180145572  movzx   edx, byte ptr [rbp+Buffer+1]
0x180145576  lea     eax, [rdx-30h]
0x180145579  test    al, 0F6h
0x18014557b  jnz     short loc_180145582
0x18014557d  cmp     dl, 39h ; '9'
0x180145580  jnz     short loc_1801455D8
0x180145582  mov     dword ptr [rdi], 1
0x180145588  test    rsi, rsi
0x18014558b  jz      short loc_180145594
0x18014558d  mov     rax, qword ptr [rbp+FileSizeHigh+8]
0x180145591  mov     [rsi], rax
0x180145594  mov     ebx, r14d
0x180145597  mov     qword ptr [rbp+var_38], r15
0x18014559b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18014559f  jz      short loc_1801455A7
0x1801455a1  call    cs:__imp_CloseHandle
0x1801455a7  mov     eax, ebx
0x1801455a9  mov     rcx, [rbp+var_10]
0x1801455ad  xor     rcx, rsp; StackCookie
0x1801455b0  call    __security_check_cookie
0x1801455b5  mov     rbx, [rsp+80h+arg_18]
0x1801455bd  add     rsp, 80h
0x1801455c4  pop     r15
0x1801455c6  pop     r14
0x1801455c8  pop     rdi
0x1801455c9  pop     rsi
0x1801455ca  pop     rbp
0x1801455cb  retn
0x1801455cc  sub     al, 34h ; '4'
0x1801455ce  cmp     al, 5
0x1801455d0  ja      short loc_180145582
0x1801455d2  cmp     byte ptr [rbp+Buffer+1], 2Eh ; '.'
0x1801455d6  jnz     short loc_180145582
0x1801455d8  mov     [rdi], r14d
0x1801455db  jmp     short loc_180145588
```
