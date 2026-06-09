# GenerateDownLevelInf(_WPNP_INFO *)

- ea: `0x18002c77c`
- end: `0x18002c896`
- name: `?GenerateDownLevelInf@@YAJPEAU_WPNP_INFO@@@Z`
- size: `282`
- prototype: `__int64 __fastcall(struct _WPNP_INFO *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x18002cf10`

## callees

- `0x18002c77c`
- `0x18002d6f4`
- `0x18002d804`
- `0x18002da50`
- `0x18002dc90`
- `0x18002deb8`
- `0x18002e060`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c7d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c7d8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c7c5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002c7c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c870`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c87e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c870`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c87e`

## pseudocode

```c
__int64 __fastcall GenerateDownLevelInf(struct _WPNP_INFO *a1)
{
  int valid; // ebx
  char *FileW; // rax
  unsigned __int16 *v4; // rdi
  HLOCAL hMem; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int16 *v7; // [rsp+60h] [rbp+18h] BYREF

  valid = ValidWPNPInfo(a1);
  if ( valid >= 0 )
  {
    FileW = (char *)CreateFileW(*((LPCWSTR *)a1 + 1), 0x40000000u, 0, 0, 2u, 0x80u, 0);
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileW);
    v4 = 0;
    hMem = 0;
    v7 = 0;
    valid = ProcessVersionSection(a1);
    if ( valid >= 0 )
    {
      valid = ProcessManufacturerSection(a1, (unsigned __int16 **)&hMem);
      if ( valid >= 0 )
      {
        valid = ProcessModelsSection(a1, (const unsigned __int16 *)hMem, &v7);
        if ( valid < 0 || (valid = ProcessSection(a1, L"DestinationDirs", L"DefaultDestDir", 0), valid < 0) )
        {
          v4 = v7;
        }
        else
        {
          v4 = v7;
          valid = ProcessDDInstallSection(a1, v7);
        }
      }
      if ( hMem )
        LocalFree(hMem);
      if ( v4 )
        LocalFree(v4);
    }
  }
  return (unsigned int)valid;
}

```

## disassembly

```asm
0x18002c77c  mov     [rsp+arg_0], rbx
0x18002c781  mov     [rsp+arg_18], rsi
0x18002c786  push    rdi
0x18002c787  sub     rsp, 40h
0x18002c78b  mov     rsi, rcx
0x18002c78e  call    ?ValidWPNPInfo@@YAJPEAU_WPNP_INFO@@@Z; ValidWPNPInfo(_WPNP_INFO *)
0x18002c793  mov     ebx, eax
0x18002c795  test    eax, eax
0x18002c797  js      loc_18002C884
0x18002c79d  mov     rcx, [rsi+8]; lpFileName
0x18002c7a1  xor     r9d, r9d; lpSecurityAttributes
0x18002c7a4  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18002c7ad  xor     r8d, r8d; dwShareMode
0x18002c7b0  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002c7b8  mov     edx, 40000000h; dwDesiredAccess
0x18002c7bd  mov     [rsp+48h+dwCreationDisposition], 2; dwCreationDisposition
0x18002c7c5  call    cs:__imp_CreateFileW
0x18002c7cb  lea     rcx, [rax-1]
0x18002c7cf  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002c7d3  ja      short loc_18002C7DE
0x18002c7d5  mov     rcx, rax; hObject
0x18002c7d8  call    cs:__imp_CloseHandle
0x18002c7de  xor     edi, edi
0x18002c7e0  mov     [rsp+48h+hMem], 0
0x18002c7e9  mov     rcx, rsi; struct _WPNP_INFO *
0x18002c7ec  mov     [rsp+48h+arg_10], rdi
0x18002c7f1  call    ?ProcessVersionSection@@YAJPEAU_WPNP_INFO@@@Z; ProcessVersionSection(_WPNP_INFO *)
0x18002c7f6  mov     ebx, eax
0x18002c7f8  test    eax, eax
0x18002c7fa  js      loc_18002C884
0x18002c800  lea     rdx, [rsp+48h+hMem]; unsigned __int16 **
0x18002c805  mov     rcx, rsi; struct _WPNP_INFO *
0x18002c808  call    ?ProcessManufacturerSection@@YAJPEAU_WPNP_INFO@@PEAPEAG@Z; ProcessManufacturerSection(_WPNP_INFO *,ushort * *)
0x18002c80d  mov     ebx, eax
0x18002c80f  test    eax, eax
0x18002c811  js      short loc_18002C863
0x18002c813  mov     rdx, [rsp+48h+hMem]; unsigned __int16 *
0x18002c818  lea     r8, [rsp+48h+arg_10]; unsigned __int16 **
0x18002c81d  mov     rcx, rsi; struct _WPNP_INFO *
0x18002c820  call    ?ProcessModelsSection@@YAJPEAU_WPNP_INFO@@PEBGPEAPEAG@Z; ProcessModelsSection(_WPNP_INFO *,ushort const *,ushort * *)
0x18002c825  mov     ebx, eax
0x18002c827  test    eax, eax
0x18002c829  js      short loc_18002C85E
0x18002c82b  xor     r9d, r9d; int
0x18002c82e  lea     r8, aDefaultdestdir; "DefaultDestDir"
0x18002c835  lea     rdx, cszDestinationDirs; "DestinationDirs"
0x18002c83c  mov     rcx, rsi; struct _WPNP_INFO *
0x18002c83f  call    ?ProcessSection@@YAJPEAU_WPNP_INFO@@PEBG1H@Z; ProcessSection(_WPNP_INFO *,ushort const *,ushort const *,int)
0x18002c844  mov     ebx, eax
0x18002c846  test    eax, eax
0x18002c848  js      short loc_18002C85E
0x18002c84a  mov     rdi, [rsp+48h+arg_10]
0x18002c84f  mov     rcx, rsi; struct _WPNP_INFO *
0x18002c852  mov     rdx, rdi; unsigned __int16 *
0x18002c855  call    ?ProcessDDInstallSection@@YAJPEAU_WPNP_INFO@@PEBG@Z; ProcessDDInstallSection(_WPNP_INFO *,ushort const *)
0x18002c85a  mov     ebx, eax
0x18002c85c  jmp     short loc_18002C863
0x18002c85e  mov     rdi, [rsp+48h+arg_10]
0x18002c863  cmp     [rsp+48h+hMem], 0
0x18002c869  jz      short loc_18002C876
0x18002c86b  mov     rcx, [rsp+48h+hMem]; hMem
0x18002c870  call    cs:__imp_LocalFree
0x18002c876  test    rdi, rdi
0x18002c879  jz      short loc_18002C884
0x18002c87b  mov     rcx, rdi; hMem
0x18002c87e  call    cs:__imp_LocalFree
0x18002c884  mov     rsi, [rsp+48h+arg_18]
0x18002c889  mov     eax, ebx
0x18002c88b  mov     rbx, [rsp+48h+arg_0]
0x18002c890  add     rsp, 40h
0x18002c894  pop     rdi
0x18002c895  retn
```
