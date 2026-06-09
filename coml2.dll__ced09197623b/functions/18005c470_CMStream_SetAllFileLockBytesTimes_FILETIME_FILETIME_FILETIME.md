# CMStream::SetAllFileLockBytesTimes(_FILETIME,_FILETIME,_FILETIME)

- ea: `0x18005c470`
- end: `0x18005c532`
- name: `?SetAllFileLockBytesTimes@CMStream@@QEAAJU_FILETIME@@00@Z`
- size: `194`
- prototype: `__int64 __fastcall(CMStream *__hidden this, struct _FILETIME, struct _FILETIME, struct _FILETIME)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180041e7c`

## callees

- `0x180026bc4`
- `0x18005c470`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c507`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c507`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18005c4fd`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18005c4fd`

## pseudocode

```c
__int64 __fastcall CMStream::SetAllFileLockBytesTimes(CMStream *this, FILETIME a2, FILETIME a3, FILETIME a4)
{
  unsigned int v5; // ebp
  int (__fastcall ****v8)(_QWORD, GUID *, __int64 *); // rcx
  int (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v10; // rcx
  void *v11; // rcx
  DWORD LastError; // eax
  FILETIME LastWriteTime; // [rsp+20h] [rbp-48h] BYREF
  FILETIME LastAccessTime; // [rsp+28h] [rbp-40h] BYREF
  FILETIME CreationTime; // [rsp+30h] [rbp-38h] BYREF
  __int64 v17; // [rsp+70h] [rbp+8h] BYREF

  v5 = 0;
  if ( *(_QWORD *)this )
    v8 = (int (__fastcall ****)(_QWORD, GUID *, __int64 *))(*(_QWORD *)this + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
  else
    v8 = 0;
  v9 = *v8;
  v17 = 0;
  if ( (**v9)(v9, &IID_IDfReserved1, &v17) >= 0 )
  {
    if ( v17 )
      v10 = v17 - 8;
    else
      v10 = 0;
    v11 = *(void **)(v10 + 64);
    CreationTime = a4;
    LastWriteTime = a3;
    LastAccessTime = a2;
    if ( !SetFileTime(v11, &CreationTime, &LastAccessTime, &LastWriteTime) )
    {
      LastError = GetLastError();
      v5 = Win32ErrorToScode(LastError);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return v5;
}

```

## disassembly

```asm
0x18005c470  push    rbx
0x18005c472  push    rbp
0x18005c473  push    rsi
0x18005c474  push    rdi
0x18005c475  sub     rsp, 48h
0x18005c479  mov     rsi, rdx
0x18005c47c  xor     ebp, ebp
0x18005c47e  mov     rdx, [rcx]
0x18005c481  mov     rbx, r9
0x18005c484  mov     rdi, r8
0x18005c487  test    rdx, rdx
0x18005c48a  jz      short loc_18005C4A4
0x18005c48c  mov     rax, gs:30h
0x18005c495  mov     rcx, [rax+1758h]
0x18005c49c  mov     rcx, [rcx]
0x18005c49f  add     rcx, rdx
0x18005c4a2  jmp     short loc_18005C4A6
0x18005c4a4  xor     ecx, ecx
0x18005c4a6  mov     rcx, [rcx]
0x18005c4a9  lea     r8, [rsp+68h+arg_0]
0x18005c4ae  mov     [rsp+68h+arg_0], rbp
0x18005c4b3  lea     rdx, IID_IDfReserved1
0x18005c4ba  mov     rax, [rcx]
0x18005c4bd  mov     rax, [rax]
0x18005c4c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c4c5  test    eax, eax
0x18005c4c7  js      short loc_18005C527
0x18005c4c9  mov     rax, [rsp+68h+arg_0]
0x18005c4ce  test    rax, rax
0x18005c4d1  jz      short loc_18005C4D9
0x18005c4d3  lea     rcx, [rax-8]
0x18005c4d7  jmp     short loc_18005C4DB
0x18005c4d9  xor     ecx, ecx
0x18005c4db  mov     rcx, [rcx+40h]; hFile
0x18005c4df  lea     r9, [rsp+68h+LastWriteTime]; lpLastWriteTime
0x18005c4e4  lea     r8, [rsp+68h+LastAccessTime]; lpLastAccessTime
0x18005c4e9  mov     qword ptr [rsp+68h+CreationTime.dwLowDateTime], rbx
0x18005c4ee  lea     rdx, [rsp+68h+CreationTime]; lpCreationTime
0x18005c4f3  mov     qword ptr [rsp+68h+LastWriteTime.dwLowDateTime], rdi
0x18005c4f8  mov     qword ptr [rsp+68h+LastAccessTime.dwLowDateTime], rsi
0x18005c4fd  call    cs:__imp_SetFileTime
0x18005c503  test    eax, eax
0x18005c505  jnz     short loc_18005C516
0x18005c507  call    cs:__imp_GetLastError
0x18005c50d  mov     ecx, eax; unsigned int
0x18005c50f  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x18005c514  mov     ebp, eax
0x18005c516  mov     rcx, [rsp+68h+arg_0]
0x18005c51b  mov     rdx, [rcx]
0x18005c51e  mov     rax, [rdx+10h]
0x18005c522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c527  mov     eax, ebp
0x18005c529  add     rsp, 48h
0x18005c52d  pop     rdi
0x18005c52e  pop     rsi
0x18005c52f  pop     rbp
0x18005c530  pop     rbx
0x18005c531  retn
```
