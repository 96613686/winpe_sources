# CFileStream::ReadAt(_ULARGE_INTEGER,void *,ulong,ulong *)

- ea: `0x180025460`
- end: `0x1800256a2`
- name: `?ReadAt@CFileStream@@UEAAJT_ULARGE_INTEGER@@PEAXKPEAK@Z`
- size: `578`
- prototype: `__int64 __usercall@<rax>(CFileStream *__hidden this@<rcx>, union _ULARGE_INTEGER@<rdx>, void *@<r8>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180025460`
- `0x180025768`
- `0x180025840`
- `0x180025a10`
- `0x180026bc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025681`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025690`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025681`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025690`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180025555`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800255cf`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002561a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180025555`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800255cf`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002561a`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180025676`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180025676`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800254e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800254e2`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800254cf`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800254cf`
- `api-ms-win-core-memory-l1-1-0!FlushViewOfFile` at `0x1800254c5`
- `api-ms-win-core-memory-l1-1-0!FlushViewOfFile` at `0x1800254c5`

## pseudocode

```c
__int64 __fastcall CFileStream::ReadAt(
        CFileStream *this,
        union _ULARGE_INTEGER a2,
        void *a3,
        DWORD a4,
        unsigned int *lpNumberOfBytesRead)
{
  __int64 v9; // rcx
  int v10; // eax
  void *v11; // rcx
  __int64 v12; // r9
  __int64 v13; // rax
  int v14; // ecx
  bool v15; // zf
  void *v16; // rcx
  DWORD *v17; // r9
  DWORD v18; // r8d
  void *v19; // rdx
  __int64 result; // rax
  __int64 v21; // rax
  int v22; // ecx
  __int64 v23; // rax
  __int64 v24; // rcx
  union _ULARGE_INTEGER v25; // rax
  DWORD LastError; // eax
  struct _OVERLAPPED Overlapped; // [rsp+30h] [rbp-58h] BYREF
  DWORD HighPart; // [rsp+9Ch] [rbp+14h]

  HighPart = a2.HighPart;
  *lpNumberOfBytesRead = 0;
  v9 = *((_QWORD *)this + 6);
  v10 = *(_DWORD *)(v9 + 596);
  if ( v10 == 2 )
    return 2147680769LL;
  if ( v10 != 1 )
  {
    v25 = *(union _ULARGE_INTEGER *)(v9 + 600);
    if ( a2.QuadPart > v25.QuadPart || a4 > v25.QuadPart - a2.QuadPart )
    {
      *(_QWORD *)(*((_QWORD *)this + 6) + 608LL) = a2.QuadPart + a4;
      return 2147483658LL;
    }
  }
  if ( !*((_QWORD *)this + 13) )
  {
LABEL_13:
    if ( a4 )
    {
      v13 = *((_QWORD *)this + 6);
      v14 = 0;
      if ( v13 )
        LOBYTE(v14) = a2.QuadPart == *(_QWORD *)(v13 + 48);
      v15 = v14 == 0;
      v16 = (void *)*((_QWORD *)this + 8);
      v17 = lpNumberOfBytesRead;
      v18 = a4;
      v19 = a3;
      if ( !v15 )
      {
        if ( !ReadFile(v16, a3, a4, lpNumberOfBytesRead, 0) )
        {
LABEL_38:
          LastError = GetLastError();
          return Win32ErrorToScode(LastError);
        }
        goto LABEL_25;
      }
      goto LABEL_24;
    }
LABEL_33:
    *lpNumberOfBytesRead = 0;
    return 0;
  }
  if ( (*(_BYTE *)(v9 + 68) & 1) == 0 )
  {
    if ( *((_QWORD *)this + 12) )
    {
      FlushViewOfFile(*((LPCVOID *)this + 13), 0);
      UnmapViewOfFile(*((LPCVOID *)this + 13));
      v11 = (void *)*((_QWORD *)this + 12);
      *((_QWORD *)this + 13) = 0;
      if ( v11 )
      {
        CloseHandle(v11);
        *((_QWORD *)this + 12) = 0;
      }
      if ( CContextList::CountContexts(*((CContextList **)this + 6)) == 1
        && *(char *)(v12 + 32) < 0
        && (*(_BYTE *)(v12 + 68) & 8) != 0
        && CFileStream::SeekTo(this, *(unsigned int *)(v12 + 60)) != -1 )
      {
        SetEndOfFile(*((HANDLE *)this + 8));
      }
    }
    goto LABEL_13;
  }
  result = CFileStream::ReadAt_FromMap(this, a2.LowPart, a3, a4, lpNumberOfBytesRead);
  if ( (int)result >= 0 )
    return result;
  if ( !a4 )
    goto LABEL_33;
  v21 = *((_QWORD *)this + 6);
  v22 = 0;
  if ( v21 )
    LOBYTE(v22) = a2.QuadPart == *(_QWORD *)(v21 + 48);
  v15 = v22 == 0;
  v16 = (void *)*((_QWORD *)this + 8);
  v17 = lpNumberOfBytesRead;
  v18 = a4;
  v19 = a3;
  if ( !v15 )
  {
    if ( !ReadFile(v16, a3, a4, lpNumberOfBytesRead, 0) )
      goto LABEL_38;
    goto LABEL_25;
  }
LABEL_24:
  Overlapped.Internal = 0;
  Overlapped.InternalHigh = 0;
  Overlapped.Pointer = (PVOID)__PAIR64__(HighPart, a2.LowPart);
  Overlapped.hEvent = 0;
  if ( !ReadFile(v16, v19, v18, v17, &Overlapped) && GetLastError() != 38 )
    goto LABEL_38;
LABEL_25:
  v23 = *lpNumberOfBytesRead;
  if ( (_DWORD)v23 )
  {
    v24 = *((_QWORD *)this + 6);
    if ( v24 )
      *(_QWORD *)(v24 + 48) = a2.QuadPart + v23;
  }
  return 0;
}

```

## disassembly

```asm
0x180025460  mov     [rsp+arg_8], rdx
0x180025465  push    rbx
0x180025466  push    rbp
0x180025467  push    rsi
0x180025468  push    rdi
0x180025469  push    r14
0x18002546b  push    r15
0x18002546d  sub     rsp, 58h
0x180025471  mov     rsi, [rsp+88h+lpNumberOfBytesRead]
0x180025479  xor     r15d, r15d
0x18002547c  mov     rdi, rcx
0x18002547f  mov     ebp, r9d
0x180025482  mov     r14, r8
0x180025485  mov     rbx, rdx
0x180025488  mov     [rsi], r15d
0x18002548b  mov     rcx, [rcx+30h]
0x18002548f  mov     eax, [rcx+254h]
0x180025495  cmp     eax, 2
0x180025498  jz      loc_180025603
0x18002549e  cmp     eax, 1
0x1800254a1  jnz     loc_180025639
0x1800254a7  mov     rax, [rdi+68h]
0x1800254ab  test    rax, rax
0x1800254ae  jz      short loc_180025521
0x1800254b0  test    byte ptr [rcx+44h], 1
0x1800254b4  jnz     loc_180025564
0x1800254ba  cmp     [rdi+60h], r15
0x1800254be  jz      short loc_180025521
0x1800254c0  xor     edx, edx; dwNumberOfBytesToFlush
0x1800254c2  mov     rcx, rax; lpBaseAddress
0x1800254c5  call    cs:__imp_FlushViewOfFile
0x1800254cb  mov     rcx, [rdi+68h]; lpBaseAddress
0x1800254cf  call    cs:__imp_UnmapViewOfFile
0x1800254d5  mov     rcx, [rdi+60h]; hObject
0x1800254d9  mov     [rdi+68h], r15
0x1800254dd  test    rcx, rcx
0x1800254e0  jz      short loc_1800254EC
0x1800254e2  call    cs:__imp_CloseHandle
0x1800254e8  mov     [rdi+60h], r15
0x1800254ec  mov     r9, [rdi+30h]
0x1800254f0  mov     rcx, r9; this
0x1800254f3  call    ?CountContexts@CContextList@@QEAAKXZ; CContextList::CountContexts(void)
0x1800254f8  cmp     eax, 1
0x1800254fb  jnz     short loc_180025521
0x1800254fd  test    byte ptr [r9+20h], 80h
0x180025502  jz      short loc_180025521
0x180025504  test    byte ptr [r9+44h], 8
0x180025509  jz      short loc_180025521
0x18002550b  mov     edx, [r9+3Ch]; unsigned __int64
0x18002550f  mov     rcx, rdi; this
0x180025512  call    ?SeekTo@CFileStream@@AEAA_K_K@Z; CFileStream::SeekTo(unsigned __int64)
0x180025517  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002551b  jnz     loc_180025672
0x180025521  test    ebp, ebp
0x180025523  jz      loc_180025626
0x180025529  mov     rax, [rdi+30h]
0x18002552d  mov     ecx, r15d
0x180025530  test    rax, rax
0x180025533  jz      short loc_18002553C
0x180025535  cmp     rbx, [rax+30h]
0x180025539  setz    cl
0x18002553c  mov     r10, [rdi+40h]
0x180025540  test    ecx, ecx
0x180025542  mov     rcx, r10; hFile
0x180025545  mov     r9, rsi; lpNumberOfBytesRead
0x180025548  mov     r8d, ebp; nNumberOfBytesToRead
0x18002554b  mov     rdx, r14; lpBuffer
0x18002554e  jz      short loc_1800255A7
0x180025550  mov     [rsp+88h+lpOverlapped], r15; lpOverlapped
0x180025555  call    cs:__imp_ReadFile
0x18002555b  test    eax, eax
0x18002555d  jnz     short loc_1800255DD
0x18002555f  jmp     loc_180025690
0x180025564  mov     r9d, ebp; unsigned int
0x180025567  mov     [rsp+88h+lpOverlapped], rsi; unsigned int *
0x18002556c  mov     rcx, rdi; this
0x18002556f  call    ?ReadAt_FromMap@CFileStream@@AEAAJKPEAXKPEAK@Z; CFileStream::ReadAt_FromMap(ulong,void *,ulong,ulong *)
0x180025574  test    eax, eax
0x180025576  jns     short loc_1800255F6
0x180025578  test    ebp, ebp
0x18002557a  jz      loc_180025626
0x180025580  mov     rax, [rdi+30h]
0x180025584  mov     ecx, r15d
0x180025587  test    rax, rax
0x18002558a  jz      short loc_180025593
0x18002558c  cmp     rbx, [rax+30h]
0x180025590  setz    cl
0x180025593  mov     r10, [rdi+40h]
0x180025597  test    ecx, ecx
0x180025599  mov     rcx, r10; hFile
0x18002559c  mov     r9, rsi; lpNumberOfBytesRead
0x18002559f  mov     r8d, ebp; nNumberOfBytesToRead
0x1800255a2  mov     rdx, r14; lpBuffer
0x1800255a5  jnz     short loc_180025615
0x1800255a7  mov     eax, dword ptr [rsp+88h+arg_8+4]
0x1800255ae  mov     dword ptr [rsp+88h+Overlapped.10h+4], eax
0x1800255b2  lea     rax, [rsp+88h+Overlapped]
0x1800255b7  mov     [rsp+88h+lpOverlapped], rax; lpOverlapped
0x1800255bc  mov     [rsp+88h+Overlapped.Internal], r15
0x1800255c1  mov     [rsp+88h+Overlapped.InternalHigh], r15
0x1800255c6  mov     dword ptr [rsp+88h+Overlapped.10h], ebx
0x1800255ca  mov     [rsp+88h+Overlapped.hEvent], r15
0x1800255cf  call    cs:__imp_ReadFile
0x1800255d5  test    eax, eax
0x1800255d7  jz      loc_180025681
0x1800255dd  mov     eax, [rsi]
0x1800255df  test    eax, eax
0x1800255e1  jz      short loc_1800255F3
0x1800255e3  mov     rcx, [rdi+30h]
0x1800255e7  test    rcx, rcx
0x1800255ea  jz      short loc_1800255F3
0x1800255ec  add     rax, rbx
0x1800255ef  mov     [rcx+30h], rax
0x1800255f3  mov     eax, r15d
0x1800255f6  add     rsp, 58h
0x1800255fa  pop     r15
0x1800255fc  pop     r14
0x1800255fe  pop     rdi
0x1800255ff  pop     rsi
0x180025600  pop     rbp
0x180025601  pop     rbx
0x180025602  retn
0x180025603  mov     eax, 80030201h
0x180025608  add     rsp, 58h
0x18002560c  pop     r15
0x18002560e  pop     r14
0x180025610  pop     rdi
0x180025611  pop     rsi
0x180025612  pop     rbp
0x180025613  pop     rbx
0x180025614  retn
0x180025615  mov     [rsp+88h+lpOverlapped], r15; lpOverlapped
0x18002561a  call    cs:__imp_ReadFile
0x180025620  test    eax, eax
0x180025622  jnz     short loc_1800255DD
0x180025624  jmp     short loc_180025690
0x180025626  mov     [rsi], r15d
0x180025629  mov     eax, r15d
0x18002562c  add     rsp, 58h
0x180025630  pop     r15
0x180025632  pop     r14
0x180025634  pop     rdi
0x180025635  pop     rsi
0x180025636  pop     rbp
0x180025637  pop     rbx
0x180025638  retn
0x180025639  mov     rax, [rcx+258h]
0x180025640  cmp     rbx, rax
0x180025643  ja      short loc_180025651
0x180025645  sub     rax, rbx
0x180025648  cmp     rbp, rax
0x18002564b  jbe     loc_1800254A7
0x180025651  mov     rax, [rdi+30h]
0x180025655  lea     rcx, [rdx+rbp]
0x180025659  mov     [rax+260h], rcx
0x180025660  mov     eax, 8000000Ah
0x180025665  add     rsp, 58h
0x180025669  pop     r15
0x18002566b  pop     r14
0x18002566d  pop     rdi
0x18002566e  pop     rsi
0x18002566f  pop     rbp
0x180025670  pop     rbx
0x180025671  retn
0x180025672  mov     rcx, [rdi+40h]; hFile
0x180025676  call    cs:__imp_SetEndOfFile
0x18002567c  jmp     loc_180025521
0x180025681  call    cs:__imp_GetLastError
0x180025687  cmp     eax, 26h ; '&'
0x18002568a  jz      loc_1800255DD
0x180025690  call    cs:__imp_GetLastError
0x180025696  mov     ecx, eax; unsigned int
0x180025698  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x18002569d  jmp     loc_1800255F6
```
