# Debugger::TargetComposition::Services::MappedFile::RuntimeClassInitialize(ushort const *)

- ea: `0x1804c18ec`
- end: `0x1804c1a2c`
- name: `?RuntimeClassInitialize@MappedFile@Services@TargetComposition@Debugger@@QEAAJPEBG@Z`
- size: `320`
- prototype: `__int64 __fastcall(Debugger::TargetComposition::Services::MappedFile *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1804be754`

## callees

- `0x18019ae5c`
- `0x1804be6f4`
- `0x1804c18ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804c1a03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804c1a03`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1804c1980`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1804c1980`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1804c194f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1804c194f`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1804c19ba`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1804c19ba`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1804c19ea`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1804c19ea`

## pseudocode

```c
signed int __fastcall Debugger::TargetComposition::Services::MappedFile::RuntimeClassInitialize(
        Debugger::TargetComposition::Services::MappedFile *this,
        const unsigned __int16 *a2)
{
  _lambda_df994f46f8d10f2f7c700efdae03d4e0_ *v3; // rax
  signed int result; // eax
  signed int v5; // edi
  char *FileW; // rax
  void *v7; // rsi
  DWORD FileSize; // eax
  char *FileMappingW; // rax
  LPVOID v10; // rax
  __int64 v11; // [rsp+40h] [rbp-18h] BYREF
  LPCWSTR lpFileName; // [rsp+68h] [rbp+10h] BYREF
  DWORD FileSizeHigh; // [rsp+70h] [rbp+18h] BYREF

  lpFileName = a2;
  v3 = _lambda_df994f46f8d10f2f7c700efdae03d4e0_::_lambda_df994f46f8d10f2f7c700efdae03d4e0_(
         (_lambda_df994f46f8d10f2f7c700efdae03d4e0_ *)&v11,
         this,
         (struct IDebugServiceManager **)&lpFileName);
  result = Debugger::TargetComposition::ConvertException<_lambda_b5bc8cfefade0c415f7ae202c3d2d6c2_>(v3);
  v5 = result;
  if ( result >= 0 )
  {
    FileW = (char *)CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    v7 = FileW;
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL
      && (*((_QWORD *)this + 8) = FileW,
          FileSizeHigh = 0,
          FileSize = GetFileSize(FileW, &FileSizeHigh),
          *((_QWORD *)this + 11) = FileSize | ((unsigned __int64)FileSizeHigh << 32),
          FileMappingW = (char *)CreateFileMappingW(v7, 0, 2u, 0, 0, 0),
          (unsigned __int64)(FileMappingW - 1) <= 0xFFFFFFFFFFFFFFFDuLL)
      && (*((_QWORD *)this + 9) = FileMappingW, (v10 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0)) != 0) )
    {
      *((_QWORD *)this + 10) = v10;
      return v5;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1804c18ec  mov     rax, rsp
0x1804c18ef  mov     [rax+8], rbx
0x1804c18f3  mov     [rax+20h], rsi
0x1804c18f7  mov     [rax+10h], rdx
0x1804c18fb  push    rdi
0x1804c18fc  sub     rsp, 50h
0x1804c1900  mov     rdx, rcx; struct Debugger::TargetComposition::Services::OS::Windows::WindowsKernelInfrastructure *
0x1804c1903  lea     r8, [rax+10h]; struct IDebugServiceManager **
0x1804c1907  mov     rbx, rcx
0x1804c190a  lea     rcx, [rax-18h]; this
0x1804c190e  call    ??0_lambda_df994f46f8d10f2f7c700efdae03d4e0_@@QEAA@PEAVWindowsKernelInfrastructure@Windows@OS@Services@TargetComposition@Debugger@@AEAPEAUIDebugServiceManager@@@Z; _lambda_df994f46f8d10f2f7c700efdae03d4e0_::_lambda_df994f46f8d10f2f7c700efdae03d4e0_(Debugger::TargetComposition::Services::OS::Windows::WindowsKernelInfrastructure *,IDebugServiceManager * &)
0x1804c1913  mov     rcx, rax
0x1804c1916  call    ??$ConvertException@V_lambda_b5bc8cfefade0c415f7ae202c3d2d6c2_@@@TargetComposition@Debugger@@YAJAEBV_lambda_b5bc8cfefade0c415f7ae202c3d2d6c2_@@@Z; Debugger::TargetComposition::ConvertException<_lambda_b5bc8cfefade0c415f7ae202c3d2d6c2_>(_lambda_b5bc8cfefade0c415f7ae202c3d2d6c2_ const &)
0x1804c191b  mov     edi, eax
0x1804c191d  test    eax, eax
0x1804c191f  js      loc_1804C1A1B
0x1804c1925  mov     rcx, [rsp+58h+lpFileName]; lpFileName
0x1804c192a  xor     r9d, r9d; lpSecurityAttributes
0x1804c192d  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x1804c1936  mov     edx, 80000000h; dwDesiredAccess
0x1804c193b  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1804c1943  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x1804c194b  lea     r8d, [r9+1]; dwShareMode
0x1804c194f  call    cs:__imp_CreateFileW
0x1804c1956  nop     dword ptr [rax+rax+00h]
0x1804c195b  mov     rsi, rax
0x1804c195e  lea     rcx, [rax-1]
0x1804c1962  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1804c1966  ja      loc_1804C1A03
0x1804c196c  lea     rdx, [rsp+58h+FileSizeHigh]; lpFileSizeHigh
0x1804c1971  mov     [rbx+40h], rax
0x1804c1975  mov     rcx, rax; hFile
0x1804c1978  mov     [rsp+58h+FileSizeHigh], 0
0x1804c1980  call    cs:__imp_GetFileSize
0x1804c1987  nop     dword ptr [rax+rax+00h]
0x1804c198c  mov     edx, [rsp+58h+FileSizeHigh]
0x1804c1990  xor     r9d, r9d; dwMaximumSizeHigh
0x1804c1993  shl     rdx, 20h
0x1804c1997  mov     ecx, eax
0x1804c1999  or      rdx, rcx
0x1804c199c  mov     qword ptr [rsp+58h+dwFlagsAndAttributes], 0; lpName
0x1804c19a5  mov     [rbx+58h], rdx
0x1804c19a9  lea     r8d, [r9+2]; flProtect
0x1804c19ad  xor     edx, edx; lpFileMappingAttributes
0x1804c19af  mov     [rsp+58h+dwCreationDisposition], 0; dwMaximumSizeLow
0x1804c19b7  mov     rcx, rsi; hFile
0x1804c19ba  call    cs:__imp_CreateFileMappingW
0x1804c19c1  nop     dword ptr [rax+rax+00h]
0x1804c19c6  lea     rcx, [rax-1]
0x1804c19ca  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1804c19ce  ja      short loc_1804C1A03
0x1804c19d0  xor     r9d, r9d; dwFileOffsetLow
0x1804c19d3  mov     [rbx+48h], rax
0x1804c19d7  xor     r8d, r8d; dwFileOffsetHigh
0x1804c19da  mov     qword ptr [rsp+58h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x1804c19e3  mov     rcx, rax; hFileMappingObject
0x1804c19e6  lea     edx, [r9+4]; dwDesiredAccess
0x1804c19ea  call    cs:__imp_MapViewOfFile
0x1804c19f1  nop     dword ptr [rax+rax+00h]
0x1804c19f6  test    rax, rax
0x1804c19f9  jz      short loc_1804C1A03
0x1804c19fb  mov     [rbx+50h], rax
0x1804c19ff  mov     eax, edi
0x1804c1a01  jmp     short loc_1804C1A1B
0x1804c1a03  call    cs:__imp_GetLastError
0x1804c1a0a  nop     dword ptr [rax+rax+00h]
0x1804c1a0f  test    eax, eax
0x1804c1a11  jle     short loc_1804C1A1B
0x1804c1a13  movzx   eax, ax
0x1804c1a16  or      eax, 80070000h
0x1804c1a1b  mov     rbx, [rsp+58h+arg_0]
0x1804c1a20  mov     rsi, [rsp+58h+arg_18]
0x1804c1a25  add     rsp, 50h
0x1804c1a29  pop     rdi
0x1804c1a2a  retn
```
