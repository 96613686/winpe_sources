# CMmcssTask::LoadRuntime(void)

- ea: `0x18015b1dc`
- end: `0x18015b348`
- name: `?LoadRuntime@CMmcssTask@@AEAAJXZ`
- size: `364`
- prototype: `__int64 __fastcall(CMmcssTask *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x18015a210`

## callees

- `0x180050270`
- `0x18015b1dc`
- `0x180231c54`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18015b27a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18015b29c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18015b2be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18015b27a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18015b29c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18015b2be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18015b1f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18015b269`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18015b28b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18015b2ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18015b1f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18015b269`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18015b28b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18015b2ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015b20e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015b2cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015b2f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015b31f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015b20e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015b2cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015b2f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015b31f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18015b1ff`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18015b1ff`

## string_xrefs

- `0x18015b1f8`: `avrt.dll`
- `0x18015b273`: `AvRevertMmThreadCharacteristics`
- `0x18015b2b7`: `AvSetMmThreadPriority`
- `0x18015b295`: `AvSetMmThreadCharacteristicsW`

## pseudocode

```c
__int64 __fastcall CMmcssTask::LoadRuntime(CMmcssTask *this)
{
  HMODULE LibraryW; // rax
  signed int v3; // eax
  signed int v4; // ebx
  unsigned int v5; // eax
  FARPROC ProcAddress; // rax
  FARPROC v8; // rax
  FARPROC v9; // rax
  signed int v10; // eax
  signed int LastError; // eax
  signed int v12; // eax

  if ( *((_QWORD *)this + 6) )
    return 0;
  SetLastError(0);
  LibraryW = LoadLibraryW(L"avrt.dll");
  *((_QWORD *)this + 6) = LibraryW;
  if ( LibraryW )
  {
    SetLastError(0);
    ProcAddress = GetProcAddress(*((HMODULE *)this + 6), "AvRevertMmThreadCharacteristics");
    *((_QWORD *)this + 8) = ProcAddress;
    if ( !ProcAddress )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( v4 >= 0 )
        v4 = -2003304445;
      v5 = 333;
      goto LABEL_8;
    }
    SetLastError(0);
    v8 = GetProcAddress(*((HMODULE *)this + 6), "AvSetMmThreadCharacteristicsW");
    *((_QWORD *)this + 7) = v8;
    if ( !v8 )
    {
      v12 = GetLastError();
      v4 = v12;
      if ( v12 > 0 )
        v4 = (unsigned __int16)v12 | 0x80070000;
      if ( v4 >= 0 )
        v4 = -2003304445;
      v5 = 335;
      goto LABEL_8;
    }
    SetLastError(0);
    v9 = GetProcAddress(*((HMODULE *)this + 6), "AvSetMmThreadPriority");
    *((_QWORD *)this + 9) = v9;
    if ( !v9 )
    {
      v10 = GetLastError();
      v4 = v10;
      if ( v10 > 0 )
        v4 = (unsigned __int16)v10 | 0x80070000;
      if ( v4 >= 0 )
        v4 = -2003304445;
      v5 = 337;
      goto LABEL_8;
    }
    return 0;
  }
  v3 = GetLastError();
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 >= 0 )
    v4 = -2003304445;
  v5 = 330;
LABEL_8:
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v4, v5, 0);
  CMmcssTask::UnloadRuntime(this);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18015b1dc  mov     [rsp+arg_0], rbx
0x18015b1e1  push    rdi
0x18015b1e2  sub     rsp, 30h
0x18015b1e6  cmp     qword ptr [rcx+30h], 0
0x18015b1eb  mov     rdi, rcx
0x18015b1ee  jnz     short loc_18015B258
0x18015b1f0  xor     ecx, ecx; dwErrCode
0x18015b1f2  call    cs:__imp_SetLastError
0x18015b1f8  lea     rcx, LibFileName; "avrt.dll"
0x18015b1ff  call    cs:__imp_LoadLibraryW
0x18015b205  mov     [rdi+30h], rax
0x18015b209  test    rax, rax
0x18015b20c  jnz     short loc_18015B267
0x18015b20e  call    cs:__imp_GetLastError
0x18015b214  mov     ebx, eax
0x18015b216  test    eax, eax
0x18015b218  jle     short loc_18015B223
0x18015b21a  movzx   ebx, ax
0x18015b21d  or      ebx, 80070000h
0x18015b223  mov     eax, 88980003h
0x18015b228  test    ebx, ebx
0x18015b22a  cmovns  ebx, eax
0x18015b22d  mov     eax, 14Ah
0x18015b232  xor     edx, edx; int *
0x18015b234  xor     r10d, r10d
0x18015b237  mov     [rsp+38h+var_10], r10; void *
0x18015b23c  xor     r8d, r8d; unsigned int
0x18015b23f  mov     r9d, ebx; int
0x18015b242  mov     [rsp+38h+var_18], eax; unsigned int
0x18015b246  lea     ecx, [rdx+14h]; unsigned int
0x18015b249  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18015b24e  mov     rcx, rdi; this
0x18015b251  call    ?UnloadRuntime@CMmcssTask@@AEAAXXZ; CMmcssTask::UnloadRuntime(void)
0x18015b256  jmp     short loc_18015B25A
0x18015b258  xor     ebx, ebx
0x18015b25a  mov     eax, ebx
0x18015b25c  mov     rbx, [rsp+38h+arg_0]
0x18015b261  add     rsp, 30h
0x18015b265  pop     rdi
0x18015b266  retn
0x18015b267  xor     ecx, ecx; dwErrCode
0x18015b269  call    cs:__imp_SetLastError
0x18015b26f  mov     rcx, [rdi+30h]; hModule
0x18015b273  lea     rdx, aAvrevertmmthre; "AvRevertMmThreadCharacteristics"
0x18015b27a  call    cs:__imp_GetProcAddress
0x18015b280  mov     [rdi+40h], rax
0x18015b284  test    rax, rax
0x18015b287  jz      short loc_18015B2F6
0x18015b289  xor     ecx, ecx; dwErrCode
0x18015b28b  call    cs:__imp_SetLastError
0x18015b291  mov     rcx, [rdi+30h]; hModule
0x18015b295  lea     rdx, aAvsetmmthreadc; "AvSetMmThreadCharacteristicsW"
0x18015b29c  call    cs:__imp_GetProcAddress
0x18015b2a2  mov     [rdi+38h], rax
0x18015b2a6  test    rax, rax
0x18015b2a9  jz      short loc_18015B31F
0x18015b2ab  xor     ecx, ecx; dwErrCode
0x18015b2ad  call    cs:__imp_SetLastError
0x18015b2b3  mov     rcx, [rdi+30h]; hModule
0x18015b2b7  lea     rdx, aAvsetmmthreadp; "AvSetMmThreadPriority"
0x18015b2be  call    cs:__imp_GetProcAddress
0x18015b2c4  mov     [rdi+48h], rax
0x18015b2c8  test    rax, rax
0x18015b2cb  jnz     short loc_18015B258
0x18015b2cd  call    cs:__imp_GetLastError
0x18015b2d3  mov     ebx, eax
0x18015b2d5  test    eax, eax
0x18015b2d7  jle     short loc_18015B2E2
0x18015b2d9  movzx   ebx, ax
0x18015b2dc  or      ebx, 80070000h
0x18015b2e2  mov     eax, 88980003h
0x18015b2e7  test    ebx, ebx
0x18015b2e9  cmovns  ebx, eax
0x18015b2ec  mov     eax, 151h
0x18015b2f1  jmp     loc_18015B232
0x18015b2f6  call    cs:__imp_GetLastError
0x18015b2fc  mov     ebx, eax
0x18015b2fe  test    eax, eax
0x18015b300  jle     short loc_18015B30B
0x18015b302  movzx   ebx, ax
0x18015b305  or      ebx, 80070000h
0x18015b30b  mov     eax, 88980003h
0x18015b310  test    ebx, ebx
0x18015b312  cmovns  ebx, eax
0x18015b315  mov     eax, 14Dh
0x18015b31a  jmp     loc_18015B232
0x18015b31f  call    cs:__imp_GetLastError
0x18015b325  mov     ebx, eax
0x18015b327  test    eax, eax
0x18015b329  jle     short loc_18015B334
0x18015b32b  movzx   ebx, ax
0x18015b32e  or      ebx, 80070000h
0x18015b334  mov     eax, 88980003h
0x18015b339  test    ebx, ebx
0x18015b33b  cmovns  ebx, eax
0x18015b33e  mov     eax, 14Fh
0x18015b343  jmp     loc_18015B232
```
