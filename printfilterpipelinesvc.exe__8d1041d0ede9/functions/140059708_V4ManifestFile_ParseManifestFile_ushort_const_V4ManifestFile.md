# V4ManifestFile::ParseManifestFile(ushort const *,V4ManifestFile * *)

- ea: `0x140059708`
- end: `0x1400597c2`
- name: `?ParseManifestFile@V4ManifestFile@@SAJPEBGPEAPEAU1@@Z`
- size: `186`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, struct V4ManifestFile **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x14005786c`

## callees

- `0x140003ecc`
- `0x140057ba8`
- `0x140059708`
- `0x1400597c8`
- `0x140059d24`
- `0x140059ea0`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x140059727`
- `KERNEL32!GetFileAttributesW` at `0x140059727`

## string_xrefs

- `0x140059775`: `DriverConfig`
- `0x14005973c`: `V4ManifestFile::ParseManifestFile`
- `0x140059735`: `Driver manifest file not found: %ws`

## pseudocode

```c
__int64 __fastcall V4ManifestFile::ParseManifestFile(LPCWSTR lpFileName, struct V4ManifestFile **a2)
{
  int v4; // edi
  V4ManifestFile *v5; // rax
  struct V4ManifestFile *v6; // rbx
  unsigned int v7; // edx

  if ( a2 )
  {
    if ( GetFileAttributesW(lpFileName) == -1 )
    {
      PrintUtilTelemetry::WriteDbgTraceWarning(
        "V4ManifestFile::ParseManifestFile",
        L"Driver manifest file not found: %ws",
        lpFileName);
      return (unsigned int)-2147024894;
    }
    else
    {
      v5 = (V4ManifestFile *)operator new(0xA0u, (const struct std::nothrow_t *)byte_14006F740);
      v6 = v5;
      if ( v5 )
      {
        V4ManifestFile::ResetManifestFileStructure(v5, 0);
        v4 = V4ManifestFile::ParseManifestSection(L"DriverConfig", lpFileName, v6);
        if ( v4 < 0 || (v4 = V4ManifestFile::ParseManifestSection(L"BidiFiles", lpFileName, v6), v4 < 0) )
          V4ManifestFile::`scalar deleting destructor'(v6, v7);
        else
          *a2 = v6;
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140059708  push    rbx
0x14005970a  push    rsi
0x14005970b  push    rdi
0x14005970c  push    r14
0x14005970e  sub     rsp, 28h
0x140059712  mov     r14, rdx
0x140059715  mov     rsi, rcx
0x140059718  test    rdx, rdx
0x14005971b  jnz     short loc_140059727
0x14005971d  mov     edi, 80070057h
0x140059722  jmp     loc_1400597B6
0x140059727  call    cs:__imp_GetFileAttributesW
0x14005972d  cmp     eax, 0FFFFFFFFh
0x140059730  jnz     short loc_14005974F
0x140059732  mov     r8, rsi
0x140059735  lea     rdx, aDriverManifest; "Driver manifest file not found: %ws"
0x14005973c  lea     rcx, aV4manifestfile; "V4ManifestFile::ParseManifestFile"
0x140059743  call    ?WriteDbgTraceWarning@PrintUtilTelemetry@@SAXPEBDPEBGZZ; PrintUtilTelemetry::WriteDbgTraceWarning(char const *,ushort const *,...)
0x140059748  mov     edi, 80070002h
0x14005974d  jmp     short loc_1400597B6
0x14005974f  lea     rdx, byte_14006F740; struct std::nothrow_t *
0x140059756  mov     ecx, 0A0h; unsigned __int64
0x14005975b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140059760  mov     rbx, rax
0x140059763  test    rax, rax
0x140059766  jz      short loc_1400597B1
0x140059768  xor     edx, edx; bool
0x14005976a  mov     rcx, rax; this
0x14005976d  call    ?ResetManifestFileStructure@V4ManifestFile@@AEAAX_N@Z; V4ManifestFile::ResetManifestFileStructure(bool)
0x140059772  mov     r8, rbx; struct V4ManifestFile *
0x140059775  lea     rcx, aDriverconfig; "DriverConfig"
0x14005977c  mov     rdx, rsi; lpFileName
0x14005977f  call    ?ParseManifestSection@V4ManifestFile@@CAJPEBG0PEAU1@@Z; V4ManifestFile::ParseManifestSection(ushort const *,ushort const *,V4ManifestFile *)
0x140059784  mov     edi, eax
0x140059786  test    eax, eax
0x140059788  js      short loc_1400597A7
0x14005978a  mov     r8, rbx; struct V4ManifestFile *
0x14005978d  lea     rcx, aBidifiles; "BidiFiles"
0x140059794  mov     rdx, rsi; lpFileName
0x140059797  call    ?ParseManifestSection@V4ManifestFile@@CAJPEBG0PEAU1@@Z; V4ManifestFile::ParseManifestSection(ushort const *,ushort const *,V4ManifestFile *)
0x14005979c  mov     edi, eax
0x14005979e  test    eax, eax
0x1400597a0  js      short loc_1400597A7
0x1400597a2  mov     [r14], rbx
0x1400597a5  jmp     short loc_1400597B6
0x1400597a7  mov     rcx, rbx; this
0x1400597aa  call    ??_GV4ManifestFile@@QEAAPEAXI@Z; V4ManifestFile::`scalar deleting destructor'(uint)
0x1400597af  jmp     short loc_1400597B6
0x1400597b1  mov     edi, 8007000Eh
0x1400597b6  mov     eax, edi
0x1400597b8  add     rsp, 28h
0x1400597bc  pop     r14
0x1400597be  pop     rdi
0x1400597bf  pop     rsi
0x1400597c0  pop     rbx
0x1400597c1  retn
```
