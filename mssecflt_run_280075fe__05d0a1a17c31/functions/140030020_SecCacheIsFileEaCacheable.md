# SecCacheIsFileEaCacheable

- ea: `0x140030020`
- end: `0x1400300d3`
- name: `SecCacheIsFileEaCacheable`
- size: `179`
- prototype: `__int64 __fastcall(PFILE_OBJECT FileObject)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x14000736c`
- `0x140007418`
- `0x140022f00`
- `0x140022fe4`
- `0x14002314c`
- `0x140023224`
- `0x140031c88`

## callees

- `0x140011650`
- `0x1400289ec`
- `0x140030020`

## import_xrefs

- `ntoskrnl!IoQueryVolumeInformation` at `0x14003006b`
- `ntoskrnl!IoQueryVolumeInformation` at `0x14003006b`

## pseudocode

```c
char __fastcall SecCacheIsFileEaCacheable(PFILE_OBJECT FileObject)
{
  bool v3; // bl
  enum _FLT_FILESYSTEM_TYPE FileSystemType; // [rsp+30h] [rbp-28h] BYREF
  ULONG v5; // [rsp+34h] [rbp-24h] BYREF
  __int64 v6; // [rsp+38h] [rbp-20h] BYREF

  v6 = 0;
  v5 = 0;
  FileSystemType = FLT_FSTYPE_UNKNOWN;
  if ( IoQueryVolumeInformation(FileObject, FileFsDeviceInformation, 8u, &v6, &v5) < 0 )
    return 0;
  v3 = (v6 & 0x1300000000LL) == 0;
  if ( (v6 & 0x1300000000LL) != 0 )
  {
    _mm_lfence();
    if ( (int)SecGetFsTypeFromFileObject(FileObject, &FileSystemType) >= 0
      && (FileSystemType == (FLT_FSTYPE_REFS|FLT_FSTYPE_NTFS) || FileSystemType == FLT_FSTYPE_NTFS) )
    {
      return 1;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x140030020  mov     r11, rsp
0x140030023  mov     [r11+10h], rbx
0x140030027  push    rdi
0x140030028  sub     rsp, 50h
0x14003002c  mov     rax, cs:__security_cookie
0x140030033  xor     rax, rsp
0x140030036  mov     [rsp+58h+var_18], rax
0x14003003b  mov     edx, 4; FsInformationClass
0x140030040  mov     qword ptr [r11-20h], 0
0x140030048  lea     rax, [r11-24h]
0x14003004c  mov     [rsp+58h+var_24], 0
0x140030054  lea     r9, [r11-20h]; FsInformation
0x140030058  mov     [rsp+58h+FileSystemType], 0
0x140030060  mov     rdi, rcx
0x140030063  mov     [r11-38h], rax
0x140030067  lea     r8d, [rdx+4]; Length
0x14003006b  call    cs:__imp_IoQueryVolumeInformation
0x140030072  nop     dword ptr [rax+rax+00h]
0x140030077  test    eax, eax
0x140030079  jns     short loc_14003007F
0x14003007b  xor     al, al
0x14003007d  jmp     short loc_1400300BA
0x14003007f  test    [rsp+58h+var_1C], 13h
0x140030087  setz    bl
0x14003008a  test    [rsp+58h+var_1C], 13h
0x140030092  jz      short loc_1400300B8
0x140030094  lfence
0x140030097  lea     rdx, [rsp+58h+FileSystemType]; FileSystemType
0x14003009c  mov     rcx, rdi; FileObject
0x14003009f  call    SecGetFsTypeFromFileObject
0x1400300a4  test    eax, eax
0x1400300a6  js      short loc_1400300B8
0x1400300a8  cmp     [rsp+58h+FileSystemType], 1Eh
0x1400300ad  jz      short loc_1400300B6
0x1400300af  cmp     [rsp+58h+FileSystemType], 2
0x1400300b4  jnz     short loc_1400300B8
0x1400300b6  mov     bl, 1
0x1400300b8  mov     al, bl
0x1400300ba  mov     rcx, [rsp+58h+var_18]
0x1400300bf  xor     rcx, rsp; StackCookie
0x1400300c2  call    __security_check_cookie
0x1400300c7  mov     rbx, [rsp+58h+arg_8]
0x1400300cc  add     rsp, 50h
0x1400300d0  pop     rdi
0x1400300d1  retn
```
