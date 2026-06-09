# CaptureBitsResponse::CreateSectionBitmap(void)

- ea: `0x1801dd8dc`
- end: `0x1801dd991`
- name: `?CreateSectionBitmap@CaptureBitsResponse@@IEAAJXZ`
- size: `181`
- prototype: `__int64 __fastcall(CaptureBitsResponse *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x1801dd810`

## callees

- `0x18001dd04`
- `0x180050270`
- `0x1801dd8dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801dd8f6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801dd8f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dd92e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801dd92e`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1801dd91c`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1801dd91c`

## pseudocode

```c
__int64 __fastcall CaptureBitsResponse::CreateSectionBitmap(DWORD *this)
{
  int v2; // eax
  unsigned int v3; // ebx
  HANDLE FileMappingW; // rax
  signed int LastError; // eax
  int v6; // r9d
  DWORD dwMaximumSizeLow; // [rsp+20h] [rbp-18h]

  v2 = CaptureBitsResponse::CalcSectionBitmapSize((CaptureBitsResponse *)this);
  v3 = v2;
  if ( v2 < 0 )
  {
    v6 = v2;
    dwMaximumSizeLow = 228;
LABEL_9:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v6, dwMaximumSizeLow, 0);
    return v3;
  }
  SetLastError(0);
  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, this[376], 0);
  *((_QWORD *)this + 186) = FileMappingW;
  if ( !FileMappingW )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    dwMaximumSizeLow = 236;
    if ( (v3 & 0x80000000) == 0 )
      v3 = -2003304445;
    v6 = v3;
    goto LABEL_9;
  }
  return v3;
}

```

## disassembly

```asm
0x1801dd8dc  mov     [rsp+arg_0], rbx
0x1801dd8e1  push    rdi
0x1801dd8e2  sub     rsp, 30h
0x1801dd8e6  mov     rdi, rcx
0x1801dd8e9  call    ?CalcSectionBitmapSize@CaptureBitsResponse@@IEAAJXZ; CaptureBitsResponse::CalcSectionBitmapSize(void)
0x1801dd8ee  mov     ebx, eax
0x1801dd8f0  test    eax, eax
0x1801dd8f2  js      short loc_1801DD963
0x1801dd8f4  xor     ecx, ecx; dwErrCode
0x1801dd8f6  call    cs:__imp_SetLastError
0x1801dd8fc  mov     edx, [rdi+5E0h]
0x1801dd902  xor     r9d, r9d; dwMaximumSizeHigh
0x1801dd905  mov     [rsp+38h+lpName], 0; lpName
0x1801dd90e  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1801dd912  mov     [rsp+38h+dwMaximumSizeLow], edx; dwMaximumSizeLow
0x1801dd916  xor     edx, edx; lpFileMappingAttributes
0x1801dd918  lea     r8d, [r9+4]; flProtect
0x1801dd91c  call    cs:__imp_CreateFileMappingW
0x1801dd922  mov     [rdi+5D0h], rax
0x1801dd929  test    rax, rax
0x1801dd92c  jnz     short loc_1801DD984
0x1801dd92e  call    cs:__imp_GetLastError
0x1801dd934  mov     ebx, eax
0x1801dd936  test    eax, eax
0x1801dd938  jle     short loc_1801DD943
0x1801dd93a  movzx   ebx, ax
0x1801dd93d  or      ebx, 80070000h
0x1801dd943  test    ebx, ebx
0x1801dd945  mov     [rsp+38h+lpName], 0
0x1801dd94e  mov     eax, 88980003h
0x1801dd953  mov     [rsp+38h+dwMaximumSizeLow], 0ECh
0x1801dd95b  cmovns  ebx, eax
0x1801dd95e  mov     r9d, ebx
0x1801dd961  jmp     short loc_1801DD977
0x1801dd963  mov     [rsp+38h+lpName], 0; void *
0x1801dd96c  mov     r9d, eax; int
0x1801dd96f  mov     [rsp+38h+dwMaximumSizeLow], 0E4h; unsigned int
0x1801dd977  xor     edx, edx; int *
0x1801dd979  xor     r8d, r8d; unsigned int
0x1801dd97c  lea     ecx, [rdx+14h]; unsigned int
0x1801dd97f  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801dd984  mov     eax, ebx
0x1801dd986  mov     rbx, [rsp+38h+arg_0]
0x1801dd98b  add     rsp, 30h
0x1801dd98f  pop     rdi
0x1801dd990  retn
```
