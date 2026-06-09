# CFveApiBase::FsVolumeOpen(void * *)

- ea: `0x1800052d0`
- end: `0x18000540a`
- name: `?FsVolumeOpen@CFveApiBase@@UEAAJPEAPEAX@Z`
- size: `314`
- prototype: `__int64 __fastcall(CFveApiBase *__hidden this, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x1800052d0`
- `0x180005410`
- `0x180009468`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800052fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800052fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800053e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800053e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18011f1c9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180005376`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180005376`

## pseudocode

```c
__int64 __fastcall CFveApiBase::FsVolumeOpen(CFveApiBase *this, void **a2)
{
  int LastHresultError; // edi
  HANDLE FileW; // rax

  LastHresultError = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 24);
  if ( !a2 )
  {
    LastHresultError = -2147024809;
    goto LABEL_13;
  }
  *a2 = (void *)-1LL;
  if ( !*((_QWORD *)this + 47) )
  {
    LastHresultError = -2147024809;
    goto LABEL_13;
  }
  if ( _InterlockedIncrement((volatile signed __int32 *)this + 238) == 1 )
  {
    LastHresultError = CFveApiBase::ResolveVolumeMountName(this);
    if ( LastHresultError < 0 )
    {
      _InterlockedDecrement((volatile signed __int32 *)this + 238);
      goto LABEL_13;
    }
    FileW = CreateFileW(*((LPCWSTR *)this + 49), *((_DWORD *)this + 250), 3u, 0, 3u, 0, 0);
    *((_QWORD *)this + 118) = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      _InterlockedDecrement((volatile signed __int32 *)this + 238);
      LastHresultError = GetLastHresultError();
      goto LABEL_13;
    }
  }
  else
  {
    FileW = (HANDLE)*((_QWORD *)this + 118);
    if ( FileW == (HANDLE)-1LL )
    {
      LastHresultError = -2147024890;
      goto LABEL_13;
    }
  }
  *a2 = FileW;
LABEL_13:
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 24);
  return (unsigned int)LastHresultError;
}

```

## disassembly

```asm
0x1800052d0  mov     [rsp+arg_8], rbx
0x1800052d5  mov     [rsp+arg_10], rsi
0x1800052da  mov     [rsp+arg_0], rcx
0x1800052df  push    rdi
0x1800052e0  push    r14
0x1800052e2  push    r15
0x1800052e4  sub     rsp, 50h
0x1800052e8  mov     rsi, rdx
0x1800052eb  mov     rbx, rcx
0x1800052ee  xor     r15d, r15d
0x1800052f1  mov     edi, r15d
0x1800052f4  add     rcx, 3C0h; lpCriticalSection
0x1800052fb  call    cs:__imp_EnterCriticalSection
0x180005302  nop     dword ptr [rax+rax+00h]
0x180005307  test    rsi, rsi
0x18000530a  jz      loc_1800053C0
0x180005310  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180005317  cmp     [rbx+178h], r15
0x18000531e  jz      loc_1800053CB
0x180005324  mov     eax, 1
0x180005329  lock xadd [rbx+3B8h], eax
0x180005331  inc     eax
0x180005333  cmp     eax, 1
0x180005336  jnz     short loc_180005394
0x180005338  mov     rcx, rbx; this
0x18000533b  call    ?ResolveVolumeMountName@CFveApiBase@@QEAAJXZ; CFveApiBase::ResolveVolumeMountName(void)
0x180005340  mov     edi, eax
0x180005342  mov     [rsp+68h+var_28], eax
0x180005346  test    eax, eax
0x180005348  js      loc_1800053D6
0x18000534e  mov     [rsp+68h+hTemplateFile], r15; hTemplateFile
0x180005353  mov     [rsp+68h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x180005358  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180005360  xor     r9d, r9d; lpSecurityAttributes
0x180005363  mov     r8d, 3; dwShareMode
0x180005369  mov     edx, [rbx+3E8h]; dwDesiredAccess
0x18000536f  mov     rcx, [rbx+188h]; lpFileName
0x180005376  call    cs:__imp_CreateFileW
0x18000537d  nop     dword ptr [rax+rax+00h]
0x180005382  mov     [rbx+3B0h], rax
0x180005389  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000538d  jz      short loc_1800053AC
0x18000538f  mov     [rsi], rax
0x180005392  jmp     short loc_1800053DD
0x180005394  mov     rax, [rbx+3B0h]
0x18000539b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000539f  jnz     short loc_18000538F
0x1800053a1  mov     edi, 80070006h
0x1800053a6  mov     [rsp+68h+var_28], edi
0x1800053aa  jmp     short loc_1800053DD
0x1800053ac  lock dec dword ptr [rbx+3B8h]
0x1800053b3  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x1800053b8  mov     edi, eax
0x1800053ba  mov     [rsp+68h+var_28], eax
0x1800053be  jmp     short loc_1800053DD
0x1800053c0  mov     edi, 80070057h
0x1800053c5  mov     [rsp+68h+var_28], edi
0x1800053c9  jmp     short loc_1800053DD
0x1800053cb  mov     edi, 80070057h
0x1800053d0  mov     [rsp+68h+var_28], edi
0x1800053d4  jmp     short loc_1800053DD
0x1800053d6  lock dec dword ptr [rbx+3B8h]
0x1800053dd  lea     rcx, [rbx+3C0h]; lpCriticalSection
0x1800053e4  call    cs:__imp_LeaveCriticalSection
0x1800053eb  nop     dword ptr [rax+rax+00h]
0x1800053f0  mov     eax, edi
0x1800053f2  mov     rbx, [rsp+68h+arg_8]
0x1800053f7  mov     rsi, [rsp+68h+arg_10]
0x1800053ff  add     rsp, 50h
0x180005403  pop     r15
0x180005405  pop     r14
0x180005407  pop     rdi
0x180005408  retn
0x18011f1b0  push    rbp
0x18011f1b2  sub     rsp, 40h
0x18011f1b6  mov     rbp, rdx
0x18011f1b9  mov     rcx, [rbp+70h]
0x18011f1bd  add     rcx, 3C0h
0x18011f1c4  add     rsp, 40h
0x18011f1c8  pop     rbp
0x18011f1c9  jmp     cs:__imp_LeaveCriticalSection
```
