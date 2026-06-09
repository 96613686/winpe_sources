# CFileStream::DupFileHandleToOthers(void)

- ea: `0x18004bc24`
- end: `0x18004bd26`
- name: `?DupFileHandleToOthers@CFileStream@@AEAAJXZ`
- size: `258`
- prototype: `__int64 __fastcall(CFileStream *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001defc`

## callees

- `0x180026bc4`
- `0x180035d08`
- `0x18004bc24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bc9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bce4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bc9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bce4`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004bcda`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004bcda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004bcfd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004bcfd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004bcb0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004bcb0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004bc8d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18004bc8d`

## pseudocode

```c
__int64 __fastcall CFileStream::DupFileHandleToOthers(CFileStream *this)
{
  unsigned int v1; // esi
  __int64 v3; // r8
  __int64 v4; // rdx
  struct CFileStream *i; // rdi
  HANDLE v6; // rbp
  DWORD v7; // eax
  void *v8; // rbx
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax

  v1 = 0;
  v3 = **((_QWORD **)this + 6);
  if ( v3 )
    v4 = v3 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
  else
    v4 = 0;
  for ( i = (struct CFileStream *)((v4 - 32) & -(__int64)(v4 != 0)); i; i = CFileStream::GetNext(i) )
  {
    if ( *((_QWORD *)i + 8) == -1 && *((_QWORD *)i + 9) == -1 )
    {
      v6 = OpenProcess(0x40u, 0, *((_DWORD *)i + 8));
      if ( v6 )
      {
        v8 = (void *)*((_QWORD *)this + 8);
        CurrentProcess = GetCurrentProcess();
        if ( !DuplicateHandle(CurrentProcess, v8, v6, (LPHANDLE)i + 9, 0, 0, 2u) )
        {
          LastError = GetLastError();
          v1 = Win32ErrorToScode(LastError);
          *((_QWORD *)i + 9) = -1;
        }
        CloseHandle(v6);
      }
      else
      {
        v7 = GetLastError();
        v1 = Win32ErrorToScode(v7);
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18004bc24  push    rbx
0x18004bc26  push    rbp
0x18004bc27  push    rsi
0x18004bc28  push    rdi
0x18004bc29  push    r14
0x18004bc2b  push    r15
0x18004bc2d  sub     rsp, 48h
0x18004bc31  mov     rax, [rcx+30h]
0x18004bc35  xor     esi, esi
0x18004bc37  mov     r15, rcx
0x18004bc3a  mov     r8, [rax]
0x18004bc3d  test    r8, r8
0x18004bc40  jz      short loc_18004BC5A
0x18004bc42  mov     rax, gs:30h
0x18004bc4b  mov     rdx, [rax+1758h]
0x18004bc52  mov     rdx, [rdx]
0x18004bc55  add     rdx, r8
0x18004bc58  jmp     short loc_18004BC5C
0x18004bc5a  xor     edx, edx
0x18004bc5c  lea     rax, [rdx-20h]
0x18004bc60  neg     rdx
0x18004bc63  sbb     rdi, rdi
0x18004bc66  and     rdi, rax
0x18004bc69  jz      loc_18004BD17
0x18004bc6f  cmp     qword ptr [rdi+40h], 0FFFFFFFFFFFFFFFFh
0x18004bc74  jnz     loc_18004BD03
0x18004bc7a  lea     r14, [rdi+48h]
0x18004bc7e  cmp     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x18004bc82  jnz     short loc_18004BD03
0x18004bc84  mov     r8d, [rdi+20h]; dwProcessId
0x18004bc88  xor     edx, edx; bInheritHandle
0x18004bc8a  lea     ecx, [rdx+40h]; dwDesiredAccess
0x18004bc8d  call    cs:__imp_OpenProcess
0x18004bc93  mov     rbp, rax
0x18004bc96  test    rax, rax
0x18004bc99  jnz     short loc_18004BCAC
0x18004bc9b  call    cs:__imp_GetLastError
0x18004bca1  mov     ecx, eax; unsigned int
0x18004bca3  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x18004bca8  mov     esi, eax
0x18004bcaa  jmp     short loc_18004BD03
0x18004bcac  mov     rbx, [r15+40h]
0x18004bcb0  call    cs:__imp_GetCurrentProcess
0x18004bcb6  mov     [rsp+78h+dwOptions], 2; dwOptions
0x18004bcbe  mov     r9, r14; lpTargetHandle
0x18004bcc1  mov     rcx, rax; hSourceProcessHandle
0x18004bcc4  mov     [rsp+78h+bInheritHandle], 0; bInheritHandle
0x18004bccc  mov     r8, rbp; hTargetProcessHandle
0x18004bccf  mov     [rsp+78h+dwDesiredAccess], 0; dwDesiredAccess
0x18004bcd7  mov     rdx, rbx; hSourceHandle
0x18004bcda  call    cs:__imp_DuplicateHandle
0x18004bce0  test    eax, eax
0x18004bce2  jnz     short loc_18004BCFA
0x18004bce4  call    cs:__imp_GetLastError
0x18004bcea  mov     ecx, eax; unsigned int
0x18004bcec  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x18004bcf1  mov     esi, eax
0x18004bcf3  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x18004bcfa  mov     rcx, rbp; hObject
0x18004bcfd  call    cs:__imp_CloseHandle
0x18004bd03  mov     rcx, rdi; this
0x18004bd06  call    ?GetNext@CFileStream@@QEBAPEAU1@XZ; CFileStream::GetNext(void)
0x18004bd0b  mov     rdi, rax
0x18004bd0e  test    rax, rax
0x18004bd11  jnz     loc_18004BC6F
0x18004bd17  mov     eax, esi
0x18004bd19  add     rsp, 48h
0x18004bd1d  pop     r15
0x18004bd1f  pop     r14
0x18004bd21  pop     rdi
0x18004bd22  pop     rsi
0x18004bd23  pop     rbp
0x18004bd24  pop     rbx
0x18004bd25  retn
```
