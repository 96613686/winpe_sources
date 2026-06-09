# CSystemWriter::Startup(void)

- ea: `0x18001eb28`
- end: `0x18001ec2e`
- name: `?Startup@CSystemWriter@@SA_NXZ`
- size: `262`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000ad54`

## callees

- `0x1800051b0`
- `0x180006e54`
- `0x18000be40`
- `0x18001e670`
- `0x18001eb28`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ebc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ebc1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001eba8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001eba8`

## string_xrefs

- `0x18001ebd4`: `Allocation of CSystemWriter object failed.`
- `0x18001ebba`: `Creation of CSystemWriter initialization thread failed.`

## pseudocode

```c
char CSystemWriter::Startup(void)
{
  char v0; // bl
  struct CSystemWriter *v1; // rax
  const unsigned __int16 *v2; // rbx
  DWORD LastError; // eax
  DWORD ThreadId; // [rsp+30h] [rbp-18h] BYREF

  v0 = 1;
  ThreadId = 0;
  if ( !CSystemWriter::sm_pWriter && !(unsigned int)CSystemWriter::IsSystemSetupInProgress() )
  {
    v1 = (struct CSystemWriter *)operator new(0x10u);
    if ( v1 )
    {
      *((_QWORD *)v1 + 1) = 0;
      *(_QWORD *)v1 = &CSystemWriter::`vftable';
      CSystemWriter::sm_pWriter = v1;
      g_hInitializeThread = CreateThread(0, 0, CSystemWriter::InitializeThreadFunc, 0, 0, &ThreadId);
      if ( g_hInitializeThread )
        return v0;
      v2 = L"Creation of CSystemWriter initialization thread failed.";
      LastError = GetLastError();
    }
    else
    {
      CSystemWriter::sm_pWriter = 0;
      v2 = L"Allocation of CSystemWriter object failed.";
      LastError = 14;
    }
    CSystemWriter::LogSystemErrorEvent(0x200u, v2, LastError);
    v0 = 0;
    if ( CSystemWriter::sm_pWriter )
    {
      (**(void (__fastcall ***)(struct CSystemWriter *, __int64))CSystemWriter::sm_pWriter)(
        CSystemWriter::sm_pWriter,
        1);
      CSystemWriter::sm_pWriter = 0;
    }
  }
  return v0;
}

```

## disassembly

```asm
0x18001eb28  push    rbx
0x18001eb2a  sub     rsp, 40h
0x18001eb2e  mov     rax, cs:__security_cookie
0x18001eb35  xor     rax, rsp
0x18001eb38  mov     [rsp+48h+var_10], rax
0x18001eb3d  cmp     cs:?sm_pWriter@CSystemWriter@@0PEAV1@EA, 0; CSystemWriter * CSystemWriter::sm_pWriter
0x18001eb45  mov     bl, 1
0x18001eb47  mov     [rsp+48h+ThreadId], 0
0x18001eb4f  jnz     loc_18001EC19
0x18001eb55  call    ?IsSystemSetupInProgress@CSystemWriter@@CAHXZ; CSystemWriter::IsSystemSetupInProgress(void)
0x18001eb5a  test    eax, eax
0x18001eb5c  jnz     loc_18001EC19
0x18001eb62  lea     ecx, [rax+10h]; unsigned __int64
0x18001eb65  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001eb6a  test    rax, rax
0x18001eb6d  jz      short loc_18001EBC9
0x18001eb6f  lea     rcx, ??_7CSystemWriter@@6B@; const CSystemWriter::`vftable'
0x18001eb76  mov     qword ptr [rax+8], 0
0x18001eb7e  mov     [rax], rcx
0x18001eb81  lea     r8, ?InitializeThreadFunc@CSystemWriter@@CAKPEAX@Z; lpStartAddress
0x18001eb88  mov     cs:?sm_pWriter@CSystemWriter@@0PEAV1@EA, rax; CSystemWriter * CSystemWriter::sm_pWriter
0x18001eb8f  xor     r9d, r9d; lpParameter
0x18001eb92  lea     rax, [rsp+48h+ThreadId]
0x18001eb97  xor     edx, edx; dwStackSize
0x18001eb99  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x18001eb9e  xor     ecx, ecx; lpThreadAttributes
0x18001eba0  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x18001eba8  call    cs:__imp_CreateThread
0x18001ebae  mov     cs:?g_hInitializeThread@@3PEAXEA, rax; void * g_hInitializeThread
0x18001ebb5  test    rax, rax
0x18001ebb8  jnz     short loc_18001EC19
0x18001ebba  lea     rbx, aCreationOfCsys; "Creation of CSystemWriter initializatio"...
0x18001ebc1  call    cs:__imp_GetLastError
0x18001ebc7  jmp     short loc_18001EBE0
0x18001ebc9  mov     cs:?sm_pWriter@CSystemWriter@@0PEAV1@EA, 0; CSystemWriter * CSystemWriter::sm_pWriter
0x18001ebd4  lea     rbx, aAllocationOfCs; "Allocation of CSystemWriter object fail"...
0x18001ebdb  mov     eax, 0Eh
0x18001ebe0  mov     r8d, eax; unsigned int
0x18001ebe3  mov     rdx, rbx; unsigned __int16 *
0x18001ebe6  mov     ecx, 200h; unsigned int
0x18001ebeb  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x18001ebf0  mov     rcx, cs:?sm_pWriter@CSystemWriter@@0PEAV1@EA; CSystemWriter * CSystemWriter::sm_pWriter
0x18001ebf7  xor     bl, bl
0x18001ebf9  test    rcx, rcx
0x18001ebfc  jz      short loc_18001EC19
0x18001ebfe  mov     r8, [rcx]
0x18001ec01  mov     edx, 1
0x18001ec06  mov     rax, [r8]
0x18001ec09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec0e  mov     cs:?sm_pWriter@CSystemWriter@@0PEAV1@EA, 0; CSystemWriter * CSystemWriter::sm_pWriter
0x18001ec19  mov     al, bl
0x18001ec1b  mov     rcx, [rsp+48h+var_10]
0x18001ec20  xor     rcx, rsp; StackCookie
0x18001ec23  call    __security_check_cookie
0x18001ec28  add     rsp, 40h
0x18001ec2c  pop     rbx
0x18001ec2d  retn
```
