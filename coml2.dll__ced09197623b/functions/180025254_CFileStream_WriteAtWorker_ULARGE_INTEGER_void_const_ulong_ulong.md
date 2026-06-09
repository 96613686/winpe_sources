# CFileStream::WriteAtWorker(_ULARGE_INTEGER,void const *,ulong,ulong *)

- ea: `0x180025254`
- end: `0x18002539a`
- name: `?WriteAtWorker@CFileStream@@AEAAJT_ULARGE_INTEGER@@PEBXKPEAK@Z`
- size: `326`
- prototype: `__int64 __usercall@<rax>(CFileStream *__hidden this@<rcx>, union _ULARGE_INTEGER@<rdx>, const void *@<r8>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180025010`
- `0x1800251f0`
- `0x18004bd30`

## callees

- `0x180025154`
- `0x180025254`
- `0x1800253a0`
- `0x1800256b0`
- `0x180026bc4`
- `0x18004c000`
- `0x18006141c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025388`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025388`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002537e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002537e`

## pseudocode

```c
__int64 __fastcall CFileStream::WriteAtWorker(
        CFileStream *this,
        union _ULARGE_INTEGER a2,
        const void *a3,
        unsigned int a4,
        unsigned int *lpNumberOfBytesWritten)
{
  size_t v5; // rsi
  __int64 v9; // rcx
  DWORD v10; // eax
  __int64 v12; // rcx
  int v13; // eax
  void *v14; // rcx
  BOOL v15; // eax
  __int64 v16; // rcx
  DWORD LastError; // eax
  struct _OVERLAPPED lpOverlapped; // [rsp+30h] [rbp-58h] BYREF
  DWORD HighPart; // [rsp+9Ch] [rbp+14h]

  HighPart = a2.HighPart;
  v5 = a4;
  *lpNumberOfBytesWritten = 0;
  if ( a2.QuadPart >= 0x7FFFFFFF || a4 >= 0x7FFFFFFF - a2.QuadPart )
    CFileStream::TurnOffMapping(this, 1);
  else
    CFileStream::MakeFileMapAddressValid(this, a4 + a2.LowPart);
  if ( (unsigned int)CFileStream::IsFileMapped(this) )
  {
    memcpy_0((void *)(*((_QWORD *)this + 13) + a2.LowPart), a3, v5);
    *lpNumberOfBytesWritten = v5;
    *(_DWORD *)(*((_QWORD *)this + 6) + 68LL) |= 8u;
    v9 = *((_QWORD *)this + 6);
    v10 = *(_DWORD *)(v9 + 60);
    if ( a2.LowPart > v10 || (unsigned int)v5 > v10 - a2.LowPart )
      *(_DWORD *)(v9 + 60) = a2.LowPart + v5;
    return 0;
  }
  v12 = *((_QWORD *)this + 6);
  v13 = 0;
  if ( v12 )
    LOBYTE(v13) = a2.QuadPart == *(_QWORD *)(v12 + 48);
  v14 = (void *)*((_QWORD *)this + 8);
  if ( v13 )
  {
    v15 = WriteFile(v14, a3, v5, lpNumberOfBytesWritten, 0);
  }
  else
  {
    lpOverlapped.Internal = 0;
    lpOverlapped.InternalHigh = 0;
    lpOverlapped.Pointer = (PVOID)__PAIR64__(HighPart, a2.LowPart);
    lpOverlapped.hEvent = 0;
    v15 = WriteFile(v14, a3, v5, lpNumberOfBytesWritten, &lpOverlapped);
  }
  if ( v15 )
  {
    v16 = *((_QWORD *)this + 6);
    if ( v16 )
      *(_QWORD *)(v16 + 48) = a2.QuadPart + *lpNumberOfBytesWritten;
    return 0;
  }
  LastError = GetLastError();
  return Win32ErrorToScode(LastError);
}

```

## disassembly

```asm
0x180025254  mov     [rsp+arg_8], rdx
0x180025259  push    rbx
0x18002525a  push    rsi
0x18002525b  push    rdi
0x18002525c  push    r12
0x18002525e  push    r14
0x180025260  push    r15
0x180025262  sub     rsp, 58h
0x180025266  mov     esi, r9d
0x180025269  mov     r12, r8
0x18002526c  mov     rbx, rdx
0x18002526f  mov     rdi, rcx
0x180025272  mov     r14, [rsp+88h+lpNumberOfBytesWritten]
0x18002527a  mov     dword ptr [r14], 0
0x180025281  mov     eax, 7FFFFFFFh
0x180025286  cmp     rdx, rax
0x180025289  jnb     short loc_1800252EC
0x18002528b  sub     rax, rdx
0x18002528e  cmp     rsi, rax
0x180025291  jnb     short loc_1800252EC
0x180025293  add     edx, esi; unsigned int
0x180025295  call    ?MakeFileMapAddressValid@CFileStream@@AEAAJK@Z; CFileStream::MakeFileMapAddressValid(ulong)
0x18002529a  mov     rcx, rdi; this
0x18002529d  call    ?IsFileMapped@CFileStream@@AEAAHXZ; CFileStream::IsFileMapped(void)
0x1800252a2  test    eax, eax
0x1800252a4  jz      short loc_180025300
0x1800252a6  mov     ecx, ebx
0x1800252a8  add     rcx, [rdi+68h]; void *
0x1800252ac  mov     r8, rsi; Size
0x1800252af  mov     rdx, r12; Src
0x1800252b2  call    memcpy_0
0x1800252b7  jmp     short loc_1800252C0
0x1800252b9  mov     eax, 8003001Dh
0x1800252be  jmp     short loc_1800252DE
0x1800252c0  mov     [r14], esi
0x1800252c3  mov     rax, [rdi+30h]
0x1800252c7  or      dword ptr [rax+44h], 8
0x1800252cb  mov     rcx, [rdi+30h]; this
0x1800252cf  mov     eax, [rcx+3Ch]
0x1800252d2  cmp     ebx, eax
0x1800252d4  ja      short loc_1800252F8
0x1800252d6  sub     eax, ebx
0x1800252d8  cmp     esi, eax
0x1800252da  ja      short loc_1800252F8
0x1800252dc  xor     eax, eax
0x1800252de  add     rsp, 58h
0x1800252e2  pop     r15
0x1800252e4  pop     r14
0x1800252e6  pop     r12
0x1800252e8  pop     rdi
0x1800252e9  pop     rsi
0x1800252ea  pop     rbx
0x1800252eb  retn
0x1800252ec  mov     edx, 1; int
0x1800252f1  call    ?TurnOffMapping@CFileStream@@AEAAJH@Z; CFileStream::TurnOffMapping(int)
0x1800252f6  jmp     short loc_18002529A
0x1800252f8  lea     eax, [rbx+rsi]
0x1800252fb  mov     [rcx+3Ch], eax
0x1800252fe  jmp     short loc_1800252DC
0x180025300  mov     rcx, [rdi+30h]
0x180025304  xor     eax, eax
0x180025306  test    rcx, rcx
0x180025309  jz      short loc_180025312
0x18002530b  cmp     rbx, [rcx+30h]
0x18002530f  setz    al
0x180025312  mov     rcx, [rdi+40h]; hFile
0x180025316  mov     r9, r14; lpNumberOfBytesWritten
0x180025319  mov     r8d, esi; nNumberOfBytesToWrite
0x18002531c  mov     rdx, r12; lpBuffer
0x18002531f  test    eax, eax
0x180025321  jnz     short loc_180025375
0x180025323  mov     [rsp+88h+var_58], 0
0x18002532c  mov     [rsp+88h+var_50], 0
0x180025335  mov     [rsp+88h+var_48], ebx
0x180025339  mov     eax, dword ptr [rsp+88h+arg_8+4]
0x180025340  mov     [rsp+88h+var_44], eax
0x180025344  mov     [rsp+88h+var_40], 0
0x18002534d  lea     rax, [rsp+88h+var_58]
0x180025352  mov     [rsp+88h+lpOverlapped], rax
0x180025357  jmp     short loc_18002537E
0x180025359  mov     rcx, [rdi+30h]
0x18002535d  test    rcx, rcx
0x180025360  jz      loc_1800252DC
0x180025366  mov     eax, [r14]
0x180025369  add     rax, rbx
0x18002536c  mov     [rcx+30h], rax
0x180025370  jmp     loc_1800252DC
0x180025375  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x18002537e  call    cs:__imp_WriteFile
0x180025384  test    eax, eax
0x180025386  jnz     short loc_180025359
0x180025388  call    cs:__imp_GetLastError
0x18002538e  mov     ecx, eax; unsigned int
0x180025390  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x180025395  jmp     loc_1800252DE
0x1800614ff  push    rbp
0x180061501  sub     rsp, 30h
0x180061505  mov     rbp, rdx
0x180061508  call    ?InPageExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z; InPageExceptionFilter(_EXCEPTION_POINTERS *)
0x18006150d  nop
0x18006150e  add     rsp, 30h
0x180061512  pop     rbp
0x180061513  retn
```
