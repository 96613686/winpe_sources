# SSI_REQUEST::SSISendError(ulong,char * * const)

- ea: `0x18000395c`
- end: `0x180003a2b`
- name: `?SSISendError@SSI_REQUEST@@QEAAJKQEAPEAD@Z`
- size: `207`
- prototype: `int(SSI_REQUEST *__hidden this, unsigned int, char **const)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800042fc`
- `0x180004afc`

## callees

- `0x18000395c`
- `0x180005620`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x1800039d2`
- `api-ms-win-core-localization-l1-2-0!FormatMessageA` at `0x1800039d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800039a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800039a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003a13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003a13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039f4`

## string_xrefs

- `0x180003997`: `iisres.dll`

## pseudocode

```c
unsigned int __fastcall SSI_REQUEST::SSISendError(SSI_REQUEST *this, DWORD a2, char **const a3)
{
  unsigned int v5; // r8d
  HMODULE ModuleHandleW; // rax
  DWORD v9; // eax
  unsigned int v10; // ebx
  signed int LastError; // eax
  char *Buffer; // [rsp+50h] [rbp+8h] BYREF

  v5 = *((_DWORD *)this + 176);
  if ( v5 )
    return SSI_VECTOR_BUFFER::CopyToVector((SSI_REQUEST *)((char *)this + 800), *((char **)this + 86), v5);
  Buffer = 0;
  ModuleHandleW = GetModuleHandleW(L"iisres.dll");
  v9 = FormatMessageA(0x2900u, ModuleHandleW, a2, 0, (LPSTR)&Buffer, 0, a3);
  if ( v9 )
  {
    v10 = SSI_VECTOR_BUFFER::CopyToVector((SSI_REQUEST *)((char *)this + 800), Buffer, v9);
  }
  else
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( Buffer )
    LocalFree(Buffer);
  return v10;
}

```

## disassembly

```asm
0x18000395c  mov     [rsp+arg_8], rbx
0x180003961  mov     [rsp+arg_10], rsi
0x180003966  push    rdi
0x180003967  sub     rsp, 40h
0x18000396b  mov     rdi, r8
0x18000396e  mov     esi, edx
0x180003970  mov     r8d, [rcx+2C0h]; unsigned int
0x180003977  mov     rbx, rcx
0x18000397a  test    r8d, r8d
0x18000397d  jz      short loc_180003997
0x18000397f  mov     rdx, [rbx+2B0h]; Src
0x180003986  add     rcx, 320h; this
0x18000398d  call    ?CopyToVector@SSI_VECTOR_BUFFER@@QEAAJPEADK@Z; SSI_VECTOR_BUFFER::CopyToVector(char *,ulong)
0x180003992  jmp     loc_180003A1B
0x180003997  lea     rcx, ModuleName; "iisres.dll"
0x18000399e  mov     [rsp+48h+Buffer], 0
0x1800039a7  call    cs:__imp_GetModuleHandleW
0x1800039ad  mov     [rsp+48h+Arguments], rdi; Arguments
0x1800039b2  xor     r9d, r9d; dwLanguageId
0x1800039b5  mov     rdx, rax; lpSource
0x1800039b8  mov     [rsp+48h+nSize], 0; nSize
0x1800039c0  lea     rax, [rsp+48h+Buffer]
0x1800039c5  mov     r8d, esi; dwMessageId
0x1800039c8  mov     ecx, 2900h; dwFlags
0x1800039cd  mov     [rsp+48h+lpBuffer], rax; lpBuffer
0x1800039d2  call    cs:__imp_FormatMessageA
0x1800039d8  test    eax, eax
0x1800039da  jz      short loc_1800039F4
0x1800039dc  mov     rdx, [rsp+48h+Buffer]; Src
0x1800039e1  lea     rcx, [rbx+320h]; this
0x1800039e8  mov     r8d, eax; unsigned int
0x1800039eb  call    ?CopyToVector@SSI_VECTOR_BUFFER@@QEAAJPEADK@Z; SSI_VECTOR_BUFFER::CopyToVector(char *,ulong)
0x1800039f0  mov     ebx, eax
0x1800039f2  jmp     short loc_180003A09
0x1800039f4  call    cs:__imp_GetLastError
0x1800039fa  mov     ebx, eax
0x1800039fc  test    eax, eax
0x1800039fe  jle     short loc_180003A09
0x180003a00  movzx   ebx, ax
0x180003a03  or      ebx, 80070000h
0x180003a09  mov     rcx, [rsp+48h+Buffer]; hMem
0x180003a0e  test    rcx, rcx
0x180003a11  jz      short loc_180003A19
0x180003a13  call    cs:__imp_LocalFree
0x180003a19  mov     eax, ebx
0x180003a1b  mov     rbx, [rsp+48h+arg_8]
0x180003a20  mov     rsi, [rsp+48h+arg_10]
0x180003a25  add     rsp, 40h
0x180003a29  pop     rdi
0x180003a2a  retn
```
