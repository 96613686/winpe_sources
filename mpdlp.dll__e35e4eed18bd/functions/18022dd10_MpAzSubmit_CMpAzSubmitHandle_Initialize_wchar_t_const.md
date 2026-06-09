# MpAzSubmit::CMpAzSubmitHandle::Initialize(wchar_t const *)

- ea: `0x18022dd10`
- end: `0x18022de34`
- name: `?Initialize@CMpAzSubmitHandle@MpAzSubmit@@QEAAJPEB_W@Z`
- size: `292`
- prototype: `int(MpAzSubmit::CMpAzSubmitHandle *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18022d6f4`

## callees

- `0x18022dd10`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18022dd3e`
- `KERNEL32!GetLastError` at `0x18022dd3e`
- `KERNEL32!LoadLibraryExW` at `0x18022dd2c`
- `KERNEL32!LoadLibraryExW` at `0x18022dd2c`
- `KERNEL32!GetProcAddress` at `0x18022dd63`
- `KERNEL32!GetProcAddress` at `0x18022dd83`
- `KERNEL32!GetProcAddress` at `0x18022dda3`
- `KERNEL32!GetProcAddress` at `0x18022ddc3`
- `KERNEL32!GetProcAddress` at `0x18022dde7`
- `KERNEL32!GetProcAddress` at `0x18022de0b`
- `KERNEL32!GetProcAddress` at `0x18022dd63`
- `KERNEL32!GetProcAddress` at `0x18022dd83`
- `KERNEL32!GetProcAddress` at `0x18022dda3`
- `KERNEL32!GetProcAddress` at `0x18022ddc3`
- `KERNEL32!GetProcAddress` at `0x18022dde7`
- `KERNEL32!GetProcAddress` at `0x18022de0b`

## string_xrefs

- `0x18022ddbc`: `MpAzStorageLibraryCreate`

## pseudocode

```c
int __fastcall MpAzSubmit::CMpAzSubmitHandle::Initialize(MpAzSubmit::CMpAzSubmitHandle *this, const wchar_t *a2)
{
  HMODULE Library; // rax
  int result; // eax

  if ( byte_180314740 )
    return 0;
  Library = LoadLibraryExW(a2, 0, 0);
  qword_180314748 = Library;
  if ( Library )
  {
    *(_QWORD *)&xmmword_180314750 = GetProcAddress(Library, "MpAzSubmitBlobInitialize");
    if ( (_QWORD)xmmword_180314750 )
    {
      *((_QWORD *)&xmmword_180314750 + 1) = GetProcAddress(qword_180314748, "MpAzSubmitBlobUpload");
      if ( *((_QWORD *)&xmmword_180314750 + 1) )
      {
        qword_180314760 = (__int64)GetProcAddress(qword_180314748, "MpAzSubmitBlobUninitialize");
        if ( qword_180314760 )
        {
          qword_180314768 = (__int64)GetProcAddress(qword_180314748, "MpAzStorageLibraryCreate");
          if ( qword_180314768 )
          {
            qword_180314770 = (__int64)GetProcAddress(qword_180314748, "MpAzStorageLibraryOperation");
            if ( qword_180314770 )
            {
              qword_180314778 = (__int64)GetProcAddress(qword_180314748, "MpAzStorageLibraryRelease");
              if ( qword_180314768 )
              {
                byte_180314740 = 1;
                return 0;
              }
            }
          }
        }
      }
    }
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18022dd10  sub     rsp, 28h
0x18022dd14  cmp     cs:byte_180314740, 0
0x18022dd1b  mov     rax, rdx
0x18022dd1e  jnz     loc_18022DE2D
0x18022dd24  xor     r8d, r8d; dwFlags
0x18022dd27  xor     edx, edx; hFile
0x18022dd29  mov     rcx, rax; lpLibFileName
0x18022dd2c  call    cs:__imp_LoadLibraryExW
0x18022dd32  mov     cs:qword_180314748, rax
0x18022dd39  test    rax, rax
0x18022dd3c  jnz     short loc_18022DD59
0x18022dd3e  call    cs:__imp_GetLastError
0x18022dd44  test    eax, eax
0x18022dd46  jle     loc_18022DE2F
0x18022dd4c  movzx   eax, ax
0x18022dd4f  or      eax, 80070000h
0x18022dd54  jmp     loc_18022DE2F
0x18022dd59  lea     rdx, aMpazsubmitblob; "MpAzSubmitBlobInitialize"
0x18022dd60  mov     rcx, rax; hModule
0x18022dd63  call    cs:__imp_GetProcAddress
0x18022dd69  mov     qword ptr cs:xmmword_180314750, rax
0x18022dd70  test    rax, rax
0x18022dd73  jz      short loc_18022DD3E
0x18022dd75  mov     rcx, cs:qword_180314748; hModule
0x18022dd7c  lea     rdx, aMpazsubmitblob_0; "MpAzSubmitBlobUpload"
0x18022dd83  call    cs:__imp_GetProcAddress
0x18022dd89  mov     qword ptr cs:xmmword_180314750+8, rax
0x18022dd90  test    rax, rax
0x18022dd93  jz      short loc_18022DD3E
0x18022dd95  mov     rcx, cs:qword_180314748; hModule
0x18022dd9c  lea     rdx, aMpazsubmitblob_1; "MpAzSubmitBlobUninitialize"
0x18022dda3  call    cs:__imp_GetProcAddress
0x18022dda9  mov     cs:qword_180314760, rax
0x18022ddb0  test    rax, rax
0x18022ddb3  jz      short loc_18022DD3E
0x18022ddb5  mov     rcx, cs:qword_180314748; hModule
0x18022ddbc  lea     rdx, aMpazstoragelib_0; "MpAzStorageLibraryCreate"
0x18022ddc3  call    cs:__imp_GetProcAddress
0x18022ddc9  mov     cs:qword_180314768, rax
0x18022ddd0  test    rax, rax
0x18022ddd3  jz      loc_18022DD3E
0x18022ddd9  mov     rcx, cs:qword_180314748; hModule
0x18022dde0  lea     rdx, aMpazstoragelib; "MpAzStorageLibraryOperation"
0x18022dde7  call    cs:__imp_GetProcAddress
0x18022dded  mov     cs:qword_180314770, rax
0x18022ddf4  test    rax, rax
0x18022ddf7  jz      loc_18022DD3E
0x18022ddfd  mov     rcx, cs:qword_180314748; hModule
0x18022de04  lea     rdx, aMpazstoragelib_1; "MpAzStorageLibraryRelease"
0x18022de0b  call    cs:__imp_GetProcAddress
0x18022de11  cmp     cs:qword_180314768, 0
0x18022de19  mov     cs:qword_180314778, rax
0x18022de20  jz      loc_18022DD3E
0x18022de26  mov     cs:byte_180314740, 1
0x18022de2d  xor     eax, eax
0x18022de2f  add     rsp, 28h
0x18022de33  retn
```
