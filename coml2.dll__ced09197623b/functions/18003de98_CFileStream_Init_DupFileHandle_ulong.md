# CFileStream::Init_DupFileHandle(ulong)

- ea: `0x18003de98`
- end: `0x18003dfe5`
- name: `?Init_DupFileHandle@CFileStream@@AEAAJK@Z`
- size: `333`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001defc`

## callees

- `0x18001f708`
- `0x180035d08`
- `0x18003de98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003df53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003df93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003df53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003df93`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003df89`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18003df89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ded0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003df9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003dfb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003dfc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ded0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003df9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003dfb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003dfc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003df5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003df5f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003df45`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003df45`

## pseudocode

```c
__int64 __fastcall CFileStream::Init_DupFileHandle(CFileStream *this)
{
  void *v2; // rcx
  int v3; // ebx
  __int64 v5; // rdx
  unsigned __int64 v6; // rcx
  struct CFileStream *i; // rbx
  void *v8; // rbp
  HANDLE v9; // r14
  HANDLE *v10; // rsi
  HANDLE CurrentProcess; // rax

  v2 = (void *)*((_QWORD *)this + 9);
  if ( v2 != (void *)-1LL )
  {
    *((_QWORD *)this + 8) = v2;
    *((_QWORD *)this + 9) = -1;
    v3 = ProtectHandle(v2);
    if ( v3 >= 0 )
      return 0;
    CloseHandle(*((HANDLE *)this + 8));
    *((_QWORD *)this + 8) = -1;
    return (unsigned int)v3;
  }
  v5 = **((_QWORD **)this + 6);
  if ( v5 )
    v6 = v5 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
  else
    v6 = 0;
  for ( i = (struct CFileStream *)((v6 - 32) & ((unsigned __int128)-(__int128)v6 >> 64)); ; i = CFileStream::GetNext(i) )
  {
    if ( !i )
      return 2147680262LL;
    v8 = (void *)*((_QWORD *)i + 8);
    if ( v8 != (void *)-1LL )
      break;
    v8 = (void *)*((_QWORD *)i + 9);
    if ( v8 != (void *)-1LL )
      break;
LABEL_12:
    ;
  }
  v9 = OpenProcess(0x40u, 0, *((_DWORD *)i + 8));
  if ( !v9 )
  {
    GetLastError();
    goto LABEL_12;
  }
  v10 = (HANDLE *)((char *)this + 64);
  CurrentProcess = GetCurrentProcess();
  if ( !DuplicateHandle(v9, v8, CurrentProcess, (LPHANDLE)this + 8, 0, 0, 2u) )
  {
    GetLastError();
    *v10 = (HANDLE)-1LL;
    CloseHandle(v9);
    goto LABEL_12;
  }
  v3 = ProtectHandle(*v10);
  if ( v3 < 0 )
  {
    CloseHandle(*v10);
    *v10 = (HANDLE)-1LL;
    return (unsigned int)v3;
  }
  CloseHandle(v9);
  return 0;
}

```

## disassembly

```asm
0x18003de98  push    rbx
0x18003de9a  push    rbp
0x18003de9b  push    rsi
0x18003de9c  push    rdi
0x18003de9d  push    r14
0x18003de9f  push    r15
0x18003dea1  sub     rsp, 48h
0x18003dea5  mov     rdi, rcx
0x18003dea8  or      r15, 0FFFFFFFFFFFFFFFFh
0x18003deac  mov     rcx, [rcx+48h]; ObjectHandle
0x18003deb0  cmp     rcx, r15
0x18003deb3  jz      short loc_18003DEE1
0x18003deb5  mov     [rdi+40h], rcx
0x18003deb9  mov     [rdi+48h], r15
0x18003debd  call    ?ProtectHandle@@YAJPEAX@Z; ProtectHandle(void *)
0x18003dec2  mov     ebx, eax
0x18003dec4  test    eax, eax
0x18003dec6  jns     loc_18003DFCF
0x18003decc  mov     rcx, [rdi+40h]; hObject
0x18003ded0  call    cs:__imp_CloseHandle
0x18003ded6  mov     [rdi+40h], r15
0x18003deda  mov     eax, ebx
0x18003dedc  jmp     loc_18003DFD8
0x18003dee1  mov     rax, [rdi+30h]
0x18003dee5  mov     rdx, [rax]
0x18003dee8  test    rdx, rdx
0x18003deeb  jz      short loc_18003DF05
0x18003deed  mov     rax, gs:30h
0x18003def6  mov     rcx, [rax+1758h]
0x18003defd  mov     rcx, [rcx]
0x18003df00  add     rcx, rdx
0x18003df03  jmp     short loc_18003DF07
0x18003df05  xor     ecx, ecx
0x18003df07  lea     rax, [rcx-20h]
0x18003df0b  neg     rcx
0x18003df0e  sbb     rbx, rbx
0x18003df11  and     rbx, rax
0x18003df14  test    rbx, rbx
0x18003df17  jz      loc_18003DFD3
0x18003df1d  mov     rbp, [rbx+40h]
0x18003df21  cmp     rbp, r15
0x18003df24  jnz     short loc_18003DF3C
0x18003df26  mov     rbp, [rbx+48h]
0x18003df2a  cmp     rbp, r15
0x18003df2d  jnz     short loc_18003DF3C
0x18003df2f  mov     rcx, rbx; this
0x18003df32  call    ?GetNext@CFileStream@@QEBAPEAU1@XZ; CFileStream::GetNext(void)
0x18003df37  mov     rbx, rax
0x18003df3a  jmp     short loc_18003DF14
0x18003df3c  mov     r8d, [rbx+20h]; dwProcessId
0x18003df40  xor     edx, edx; bInheritHandle
0x18003df42  lea     ecx, [rdx+40h]; dwDesiredAccess
0x18003df45  call    cs:__imp_OpenProcess
0x18003df4b  mov     r14, rax
0x18003df4e  test    rax, rax
0x18003df51  jnz     short loc_18003DF5B
0x18003df53  call    cs:__imp_GetLastError
0x18003df59  jmp     short loc_18003DF2F
0x18003df5b  lea     rsi, [rdi+40h]
0x18003df5f  call    cs:__imp_GetCurrentProcess
0x18003df65  mov     [rsp+78h+dwOptions], 2; dwOptions
0x18003df6d  mov     r9, rsi; lpTargetHandle
0x18003df70  mov     r8, rax; hTargetProcessHandle
0x18003df73  mov     [rsp+78h+bInheritHandle], 0; bInheritHandle
0x18003df7b  mov     rdx, rbp; hSourceHandle
0x18003df7e  mov     [rsp+78h+dwDesiredAccess], 0; dwDesiredAccess
0x18003df86  mov     rcx, r14; hSourceProcessHandle
0x18003df89  call    cs:__imp_DuplicateHandle
0x18003df8f  test    eax, eax
0x18003df91  jnz     short loc_18003DFA7
0x18003df93  call    cs:__imp_GetLastError
0x18003df99  mov     rcx, r14; hObject
0x18003df9c  mov     [rsi], r15
0x18003df9f  call    cs:__imp_CloseHandle
0x18003dfa5  jmp     short loc_18003DF2F
0x18003dfa7  mov     rcx, [rsi]; ObjectHandle
0x18003dfaa  call    ?ProtectHandle@@YAJPEAX@Z; ProtectHandle(void *)
0x18003dfaf  mov     ebx, eax
0x18003dfb1  test    eax, eax
0x18003dfb3  jns     short loc_18003DFC6
0x18003dfb5  mov     rcx, [rsi]; hObject
0x18003dfb8  call    cs:__imp_CloseHandle
0x18003dfbe  mov     [rsi], r15
0x18003dfc1  jmp     loc_18003DEDA
0x18003dfc6  mov     rcx, r14; hObject
0x18003dfc9  call    cs:__imp_CloseHandle
0x18003dfcf  xor     eax, eax
0x18003dfd1  jmp     short loc_18003DFD8
0x18003dfd3  mov     eax, 80030006h
0x18003dfd8  add     rsp, 48h
0x18003dfdc  pop     r15
0x18003dfde  pop     r14
0x18003dfe0  pop     rdi
0x18003dfe1  pop     rsi
0x18003dfe2  pop     rbp
0x18003dfe3  pop     rbx
0x18003dfe4  retn
```
