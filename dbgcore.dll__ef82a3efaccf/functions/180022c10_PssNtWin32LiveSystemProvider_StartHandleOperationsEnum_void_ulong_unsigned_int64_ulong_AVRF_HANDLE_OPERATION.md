# PssNtWin32LiveSystemProvider::StartHandleOperationsEnum(void *,ulong,unsigned __int64 *,ulong *,_AVRF_HANDLE_OPERATION * *)

- ea: `0x180022c10`
- end: `0x180022d58`
- name: `?StartHandleOperationsEnum@PssNtWin32LiveSystemProvider@@UEAAJPEAXKPEA_KPEAKPEAPEAU_AVRF_HANDLE_OPERATION@@@Z`
- size: `328`
- prototype: `__int64 __usercall@<rax>(PssNtWin32LiveSystemProvider *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, unsigned __int64 *@<r9>, unsigned int *, struct _AVRF_HANDLE_OPERATION **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180020634`
- `0x180022c10`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c95`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180022c7d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180022c7d`

## pseudocode

```c
signed int __fastcall PssNtWin32LiveSystemProvider::StartHandleOperationsEnum(
        PssNtWin32LiveSystemProvider *this,
        void *a2,
        __int64 a3,
        unsigned __int64 *a4,
        unsigned int *a5,
        struct _AVRF_HANDLE_OPERATION **a6)
{
  __int64 v7; // rcx
  signed int result; // eax
  bool v10; // cc
  struct _PROCESS_HANDLE_TRACING_QUERY *v11; // rax
  struct _PROCESS_HANDLE_TRACING_QUERY *v12; // rdi
  __int64 v13; // rax
  unsigned int (*v14)(struct _AVRF_HANDLE_OPERATION *, void *, unsigned int *); // rdx
  unsigned __int64 v15; // rdx
  __int128 hFileMappingObject; // [rsp+30h] [rbp-18h] BYREF

  v7 = *((_QWORD *)this + 153);
  hFileMappingObject = 0;
  result = (*((__int64 (__fastcall **)(__int64, __int64, __int128 *))this + 142))(v7, 6, &hFileMappingObject);
  v10 = result <= 0;
  if ( result )
  {
LABEL_2:
    if ( !v10 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v11 = (struct _PROCESS_HANDLE_TRACING_QUERY *)MapViewOfFile((HANDLE)hFileMappingObject, 4u, 0, 0, 0);
  v12 = v11;
  if ( !v11 )
  {
    if ( !GetLastError() )
      return -2147467259;
    result = GetLastError();
    v10 = result <= 0;
    goto LABEL_2;
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 6) + 8LL))(
          *((_QWORD *)this + 6),
          (unsigned int)(288 * *((_DWORD *)v11 + 2)));
  *((_QWORD *)this + 90) = v13;
  if ( !v13 )
    return -2147024882;
  *((_QWORD *)this + 89) = *((unsigned int *)v12 + 2);
  *((_DWORD *)this + 182) = 0;
  PssNtWin32LiveSystemProvider::AVrfpCopyHandleTraceInformation(v12, v14, this);
  v15 = *((_QWORD *)this + 90);
  if ( *((_DWORD *)this + 182) )
  {
    if ( v15 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 24LL))(*((_QWORD *)this + 6));
    return *((_DWORD *)this + 182);
  }
  else
  {
    *a4 = v15;
    *a5 = *((_DWORD *)v12 + 2);
    *a6 = (struct _AVRF_HANDLE_OPERATION *)*((_QWORD *)this + 90);
    return 0;
  }
}

```

## disassembly

```asm
0x180022c10  mov     rax, rsp
0x180022c13  mov     [rax+8], rbx
0x180022c17  mov     [rax+10h], rsi
0x180022c1b  push    rdi
0x180022c1c  sub     rsp, 40h
0x180022c20  mov     rbx, rcx
0x180022c23  lea     r8, [rax-18h]
0x180022c27  mov     rcx, [rcx+4C8h]
0x180022c2e  mov     rsi, r9
0x180022c31  mov     r9d, 10h
0x180022c37  xorps   xmm0, xmm0
0x180022c3a  movups  xmmword ptr [rax-18h], xmm0
0x180022c3e  mov     rax, [rbx+470h]
0x180022c45  lea     edx, [r9-0Ah]
0x180022c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c4e  test    eax, eax
0x180022c50  jz      short loc_180022C65
0x180022c52  jle     loc_180022D48
0x180022c58  movzx   eax, ax
0x180022c5b  or      eax, 80070000h
0x180022c60  jmp     loc_180022D48
0x180022c65  mov     rcx, qword ptr [rsp+48h+hFileMappingObject]; hFileMappingObject
0x180022c6a  xor     r9d, r9d; dwFileOffsetLow
0x180022c6d  xor     r8d, r8d; dwFileOffsetHigh
0x180022c70  mov     [rsp+48h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x180022c79  lea     edx, [r9+4]; dwDesiredAccess
0x180022c7d  call    cs:__imp_MapViewOfFile
0x180022c83  mov     rdi, rax
0x180022c86  test    rax, rax
0x180022c89  jnz     short loc_180022CA9
0x180022c8b  call    cs:__imp_GetLastError
0x180022c91  test    eax, eax
0x180022c93  jz      short loc_180022C9F
0x180022c95  call    cs:__imp_GetLastError
0x180022c9b  test    eax, eax
0x180022c9d  jmp     short loc_180022C52
0x180022c9f  mov     eax, 80004005h
0x180022ca4  jmp     loc_180022D48
0x180022ca9  mov     eax, [rax+8]
0x180022cac  mov     rcx, [rbx+30h]
0x180022cb0  lea     edx, [rax+rax*8]
0x180022cb3  mov     r8, [rcx]
0x180022cb6  shl     edx, 5
0x180022cb9  mov     rax, [r8+8]
0x180022cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022cc2  mov     [rbx+2D0h], rax
0x180022cc9  test    rax, rax
0x180022ccc  jnz     short loc_180022CD5
0x180022cce  mov     eax, 8007000Eh
0x180022cd3  jmp     short loc_180022D48
0x180022cd5  mov     eax, [rdi+8]
0x180022cd8  mov     r8, rbx; void *
0x180022cdb  mov     rcx, rdi; struct _PROCESS_HANDLE_TRACING_QUERY *
0x180022cde  mov     [rbx+2C8h], eax
0x180022ce4  mov     dword ptr [rbx+2CCh], 0
0x180022cee  mov     dword ptr [rbx+2D8h], 0
0x180022cf8  call    ?AVrfpCopyHandleTraceInformation@PssNtWin32LiveSystemProvider@@SAXPEAU_PROCESS_HANDLE_TRACING_QUERY@@P6AKPEAU_AVRF_HANDLE_OPERATION@@PEAXPEAK@Z2@Z; PssNtWin32LiveSystemProvider::AVrfpCopyHandleTraceInformation(_PROCESS_HANDLE_TRACING_QUERY *,ulong (*)(_AVRF_HANDLE_OPERATION *,void *,ulong *),void *)
0x180022cfd  cmp     dword ptr [rbx+2D8h], 0
0x180022d04  mov     rdx, [rbx+2D0h]
0x180022d0b  jz      short loc_180022D2A
0x180022d0d  test    rdx, rdx
0x180022d10  jz      short loc_180022D22
0x180022d12  mov     rcx, [rbx+30h]
0x180022d16  mov     rax, [rcx]
0x180022d19  mov     rax, [rax+18h]
0x180022d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d22  mov     eax, [rbx+2D8h]
0x180022d28  jmp     short loc_180022D48
0x180022d2a  mov     rax, [rsp+48h+arg_20]
0x180022d2f  mov     [rsi], rdx
0x180022d32  mov     ecx, [rdi+8]
0x180022d35  mov     [rax], ecx
0x180022d37  mov     rax, [rsp+48h+arg_28]
0x180022d3c  mov     rcx, [rbx+2D0h]
0x180022d43  mov     [rax], rcx
0x180022d46  xor     eax, eax
0x180022d48  mov     rbx, [rsp+48h+arg_0]
0x180022d4d  mov     rsi, [rsp+48h+arg_8]
0x180022d52  add     rsp, 40h
0x180022d56  pop     rdi
0x180022d57  retn
```
