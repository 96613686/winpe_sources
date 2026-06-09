# CSystemWriter::AddCoreCLRFiles(IVssCreateWriterMetadata *,void *)

- ea: `0x18001df9c`
- end: `0x18001e11e`
- name: `?AddCoreCLRFiles@CSystemWriter@@AEAA_NPEAVIVssCreateWriterMetadata@@PEAX@Z`
- size: `386`
- prototype: `bool(CSystemWriter *__hidden this, struct IVssCreateWriterMetadata *, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001e1d4`

## callees

- `0x1800051e0`
- `0x180006e54`
- `0x180007188`
- `0x18000be40`
- `0x18001df9c`
- `0x18001e470`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dfdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e0c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dfdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e0c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18001dfd2`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18001e095`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18001dfd2`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18001e095`

## string_xrefs

- `0x18001dfe2`: `AddCoreCLRFiles : GetWindowsDirectory failed.`
- `0x18001e001`: `AddCoreCLRFiles : GetWindowsDirectory needs more buffer.`
- `0x18001e028`: `AddCoreCLRFiles : unable to concat Windows directory and assembly.`
- `0x18001e0c9`: `AddCoreCLRFiles : unable to concat Windows directory and Microsoft.Net.`

## pseudocode

```c
bool __fastcall CSystemWriter::AddCoreCLRFiles(CSystemWriter *this, struct IVssCreateWriterMetadata *a2, void *a3)
{
  UINT WindowsDirectoryW; // eax
  const unsigned __int16 *v6; // rdx
  CSystemWriter *v8; // rcx
  char v9; // [rsp+28h] [rbp-250h]
  WCHAR Buffer[264]; // [rsp+50h] [rbp-228h] BYREF

  WindowsDirectoryW = GetWindowsDirectoryW(Buffer, 0x104u);
  if ( !WindowsDirectoryW )
  {
LABEL_2:
    WindowsDirectoryW = GetLastError();
    v6 = L"AddCoreCLRFiles : GetWindowsDirectory failed.";
LABEL_3:
    CSystemWriter::LogSystemErrorEvent(0x201u, v6, WindowsDirectoryW);
    return 0;
  }
  if ( WindowsDirectoryW > 0x104 )
    goto LABEL_5;
  if ( !(unsigned int)pSetupConcatenatePaths(Buffer, L"assembly", 260) )
  {
    WindowsDirectoryW = GetLastError();
    v6 = L"AddCoreCLRFiles : unable to concat Windows directory and assembly.";
    goto LABEL_3;
  }
  if ( CSystemWriter::DirExists(Buffer) )
  {
    v9 = 1;
    WindowsDirectoryW = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, _QWORD, const wchar_t *, WCHAR *, const wchar_t *, char, _QWORD, int))(*(_QWORD *)a2 + 40LL))(
                          a2,
                          0,
                          L"System Files",
                          Buffer,
                          L"*",
                          v9,
                          0,
                          3855);
    if ( WindowsDirectoryW )
    {
      v6 = L"AddCoreCLRFiles : AddFilesToFileGroup failed for %systemroot%\\assembly.";
      goto LABEL_3;
    }
  }
  WindowsDirectoryW = GetWindowsDirectoryW(Buffer, 0x104u);
  if ( !WindowsDirectoryW )
    goto LABEL_2;
  if ( WindowsDirectoryW > 0x104 )
  {
LABEL_5:
    v6 = L"AddCoreCLRFiles : GetWindowsDirectory needs more buffer.";
    goto LABEL_3;
  }
  if ( !(unsigned int)pSetupConcatenatePaths(Buffer, L"Microsoft.Net", 260) )
  {
    WindowsDirectoryW = GetLastError();
    v6 = L"AddCoreCLRFiles : unable to concat Windows directory and Microsoft.Net.";
    goto LABEL_3;
  }
  return !CSystemWriter::DirExists(Buffer) || CSystemWriter::TraverseDir(v8, Buffer, a3);
}

```

## disassembly

```asm
0x18001df9c  mov     [rsp+arg_0], rbx
0x18001dfa1  mov     [rsp+arg_18], rsi
0x18001dfa6  push    rdi
0x18001dfa7  sub     rsp, 270h
0x18001dfae  mov     rax, cs:__security_cookie
0x18001dfb5  xor     rax, rsp
0x18001dfb8  mov     [rsp+278h+var_18], rax
0x18001dfc0  mov     rbx, rdx
0x18001dfc3  lea     rcx, [rsp+278h+Buffer]; lpBuffer
0x18001dfc8  mov     esi, 104h
0x18001dfcd  mov     rdi, r8
0x18001dfd0  mov     edx, esi; uSize
0x18001dfd2  call    cs:__imp_GetWindowsDirectoryW
0x18001dfd8  test    eax, eax
0x18001dfda  jnz     short loc_18001DFFD
0x18001dfdc  call    cs:__imp_GetLastError
0x18001dfe2  lea     rdx, aAddcoreclrfile_2; "AddCoreCLRFiles : GetWindowsDirectory f"...
0x18001dfe9  mov     r8d, eax; unsigned int
0x18001dfec  mov     ecx, 201h; unsigned int
0x18001dff1  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x18001dff6  xor     al, al
0x18001dff8  jmp     loc_18001E0F9
0x18001dffd  cmp     eax, esi
0x18001dfff  jbe     short loc_18001E00A
0x18001e001  lea     rdx, aAddcoreclrfile_3; "AddCoreCLRFiles : GetWindowsDirectory n"...
0x18001e008  jmp     short loc_18001DFE9
0x18001e00a  mov     r8d, esi
0x18001e00d  lea     rdx, aAssembly; "assembly"
0x18001e014  lea     rcx, [rsp+278h+Buffer]
0x18001e019  call    pSetupConcatenatePaths
0x18001e01e  test    eax, eax
0x18001e020  jnz     short loc_18001E031
0x18001e022  call    cs:__imp_GetLastError
0x18001e028  lea     rdx, aAddcoreclrfile; "AddCoreCLRFiles : unable to concat Wind"...
0x18001e02f  jmp     short loc_18001DFE9
0x18001e031  lea     rcx, [rsp+278h+Buffer]; unsigned __int16 *
0x18001e036  call    ?DirExists@CSystemWriter@@CA_NPEAG@Z; CSystemWriter::DirExists(ushort *)
0x18001e03b  test    al, al
0x18001e03d  jz      short loc_18001E08E
0x18001e03f  mov     rax, [rbx]
0x18001e042  lea     rcx, asc_180026F2C; "*"
0x18001e049  mov     [rsp+278h+var_240], 0F0Fh
0x18001e051  lea     r9, [rsp+278h+Buffer]
0x18001e056  mov     [rsp+278h+var_248], 0
0x18001e05f  lea     r8, aSystemFiles; "System Files"
0x18001e066  mov     [rsp+278h+var_250], 1
0x18001e06b  xor     edx, edx
0x18001e06d  mov     rax, [rax+28h]
0x18001e071  mov     [rsp+278h+var_258], rcx
0x18001e076  mov     rcx, rbx
0x18001e079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e07e  test    eax, eax
0x18001e080  jz      short loc_18001E08E
0x18001e082  lea     rdx, aAddcoreclrfile_1; "AddCoreCLRFiles : AddFilesToFileGroup f"...
0x18001e089  jmp     loc_18001DFE9
0x18001e08e  mov     edx, esi; uSize
0x18001e090  lea     rcx, [rsp+278h+Buffer]; lpBuffer
0x18001e095  call    cs:__imp_GetWindowsDirectoryW
0x18001e09b  test    eax, eax
0x18001e09d  jz      loc_18001DFDC
0x18001e0a3  cmp     eax, esi
0x18001e0a5  ja      loc_18001E001
0x18001e0ab  mov     r8d, esi
0x18001e0ae  lea     rdx, aMicrosoftNet; "Microsoft.Net"
0x18001e0b5  lea     rcx, [rsp+278h+Buffer]
0x18001e0ba  call    pSetupConcatenatePaths
0x18001e0bf  test    eax, eax
0x18001e0c1  jnz     short loc_18001E0D5
0x18001e0c3  call    cs:__imp_GetLastError
0x18001e0c9  lea     rdx, aAddcoreclrfile_0; "AddCoreCLRFiles : unable to concat Wind"...
0x18001e0d0  jmp     loc_18001DFE9
0x18001e0d5  lea     rcx, [rsp+278h+Buffer]; unsigned __int16 *
0x18001e0da  call    ?DirExists@CSystemWriter@@CA_NPEAG@Z; CSystemWriter::DirExists(ushort *)
0x18001e0df  test    al, al
0x18001e0e1  jz      short loc_18001E0F7
0x18001e0e3  mov     r8, rdi; void *
0x18001e0e6  lea     rdx, [rsp+278h+Buffer]; unsigned __int16 *
0x18001e0eb  call    ?TraverseDir@CSystemWriter@@AEAA_NPEAGPEAX@Z; CSystemWriter::TraverseDir(ushort *,void *)
0x18001e0f0  test    al, al
0x18001e0f2  setnz   al
0x18001e0f5  jmp     short loc_18001E0F9
0x18001e0f7  mov     al, 1
0x18001e0f9  mov     rcx, [rsp+278h+var_18]
0x18001e101  xor     rcx, rsp; StackCookie
0x18001e104  call    __security_check_cookie
0x18001e109  lea     r11, [rsp+278h+var_8]
0x18001e111  mov     rbx, [r11+10h]
0x18001e115  mov     rsi, [r11+28h]
0x18001e119  mov     rsp, r11
0x18001e11c  pop     rdi
0x18001e11d  retn
```
