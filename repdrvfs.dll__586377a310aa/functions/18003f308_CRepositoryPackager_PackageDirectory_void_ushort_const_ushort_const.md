# CRepositoryPackager::PackageDirectory(void *,ushort const *,ushort const *)

- ea: `0x18003f308`
- end: `0x18003f4d3`
- name: `?PackageDirectory@CRepositoryPackager@@AEAAJPEAXPEBG1@Z`
- size: `459`
- prototype: `int(CRepositoryPackager *__hidden this, void *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003f940`

## callees

- `0x1800012b8`
- `0x180013880`
- `0x180013f90`
- `0x180023bf0`
- `0x18003f160`
- `0x18003f308`
- `0x1800443df`
- `0x180044420`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003f4a3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003f4a3`
- `wbemcomn!GetMemLogObject` at `0x18003f457`
- `wbemcomn!GetMemLogObject` at `0x18003f457`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003f462`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003f462`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003f392`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003f441`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003f392`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003f441`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRepositoryPackager::PackageDirectory(
        CRepositoryPackager *this,
        void *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int v6; // ebx
  unsigned __int16 *v7; // rdi
  CRepositoryPackager *v8; // rcx
  CMemoryLog *MemLogObject; // rax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-D0h] BYREF
  int v12; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int16 *v13; // [rsp+38h] [rbp-C8h] BYREF
  int Buffer; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v15[262]; // [rsp+44h] [rbp-BCh] BYREF

  memset_0(v15, 0, sizeof(v15));
  Buffer = 1;
  StringCchCopyW(v15, 0x105u, L".");
  NumberOfBytesWritten = 0;
  if ( !WriteFile(a2, &Buffer, 0x210u, &NumberOfBytesWritten, 0) || (v6 = 0, NumberOfBytesWritten != 528) )
    v6 = -2147217407;
  CFileName::CFileName((CFileName *)&v13);
  v7 = v13;
  if ( !v13 )
  {
    v6 = -2147217402;
LABEL_11:
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v6);
    goto LABEL_12;
  }
  if ( v6 < 0 )
    goto LABEL_11;
  StringCchCopyW(v13, 0x173u, a3);
  StringCchCatW(v7, 0x173u, L"\\");
  StringCchCatW(v7, 0x173u, L".");
  v6 = CRepositoryPackager::PackageContentsOfDirectory(v8, a2, v7);
  if ( v6 < 0 )
    goto LABEL_11;
  v12 = 2;
  NumberOfBytesWritten = 0;
  if ( !WriteFile(a2, &v12, 4u, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != 4 )
  {
    v6 = -2147217407;
    goto LABEL_11;
  }
LABEL_12:
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids, (unsigned int)v6);
  }
  CWin32DefaultArena::WbemMemFree(v7);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003f308  mov     [rsp-8+arg_0], rbx
0x18003f30d  mov     [rsp-8+arg_18], rsi
0x18003f312  push    rbp
0x18003f313  push    rdi
0x18003f314  push    r14
0x18003f316  lea     rbp, [rsp-160h]
0x18003f31e  sub     rsp, 260h
0x18003f325  mov     rax, cs:__security_cookie
0x18003f32c  xor     rax, rsp
0x18003f32f  mov     [rbp+170h+var_20], rax
0x18003f336  mov     r14, r8
0x18003f339  mov     rsi, rdx
0x18003f33c  xor     edx, edx; Val
0x18003f33e  mov     r8d, 20Ch; Size
0x18003f344  lea     rcx, [rsp+270h+var_22C]; void *
0x18003f349  call    memset_0
0x18003f34e  mov     [rsp+270h+Buffer], 1
0x18003f356  lea     r8, asc_18004D06C; "."
0x18003f35d  mov     edx, 105h; unsigned __int64
0x18003f362  lea     rcx, [rsp+270h+var_22C]; unsigned __int16 *
0x18003f367  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003f36c  mov     [rsp+270h+NumberOfBytesWritten], 0
0x18003f374  mov     [rsp+270h+lpOverlapped], 0; lpOverlapped
0x18003f37d  lea     r9, [rsp+270h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003f382  mov     edi, 210h
0x18003f387  mov     r8d, edi; nNumberOfBytesToWrite
0x18003f38a  lea     rdx, [rsp+270h+Buffer]; lpBuffer
0x18003f38f  mov     rcx, rsi; hFile
0x18003f392  call    cs:__imp_WriteFile
0x18003f398  test    eax, eax
0x18003f39a  jz      short loc_18003F3A4
0x18003f39c  xor     ebx, ebx
0x18003f39e  cmp     [rsp+270h+NumberOfBytesWritten], edi
0x18003f3a2  jz      short loc_18003F3A9
0x18003f3a4  mov     ebx, 80041001h
0x18003f3a9  lea     rcx, [rsp+270h+var_238]; this
0x18003f3ae  call    ??0CFileName@@QEAA@XZ; CFileName::CFileName(void)
0x18003f3b3  nop
0x18003f3b4  mov     rdi, [rsp+270h+var_238]
0x18003f3b9  test    rdi, rdi
0x18003f3bc  jnz     short loc_18003F3C8
0x18003f3be  mov     ebx, 80041006h
0x18003f3c3  jmp     loc_18003F457
0x18003f3c8  test    ebx, ebx
0x18003f3ca  js      loc_18003F457
0x18003f3d0  mov     r8, r14; unsigned __int16 *
0x18003f3d3  mov     ebx, 173h
0x18003f3d8  mov     edx, ebx; unsigned __int64
0x18003f3da  mov     rcx, rdi; unsigned __int16 *
0x18003f3dd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003f3e2  lea     r8, asc_18004B0E0; "\\"
0x18003f3e9  mov     edx, ebx; unsigned __int64
0x18003f3eb  mov     rcx, rdi; unsigned __int16 *
0x18003f3ee  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003f3f3  lea     r8, asc_18004D06C; "."
0x18003f3fa  mov     edx, ebx; unsigned __int64
0x18003f3fc  mov     rcx, rdi; unsigned __int16 *
0x18003f3ff  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003f404  mov     r8, rdi; unsigned __int16 *
0x18003f407  mov     rdx, rsi; void *
0x18003f40a  call    ?PackageContentsOfDirectory@CRepositoryPackager@@AEAAJPEAXPEBG@Z; CRepositoryPackager::PackageContentsOfDirectory(void *,ushort const *)
0x18003f40f  mov     ebx, eax
0x18003f411  test    eax, eax
0x18003f413  js      short loc_18003F457
0x18003f415  mov     [rsp+270h+var_23C], 2
0x18003f41d  mov     [rsp+270h+NumberOfBytesWritten], 0
0x18003f425  mov     [rsp+270h+lpOverlapped], 0; lpOverlapped
0x18003f42e  lea     r9, [rsp+270h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003f433  mov     r8d, 4; nNumberOfBytesToWrite
0x18003f439  lea     rdx, [rsp+270h+var_23C]; lpBuffer
0x18003f43e  mov     rcx, rsi; hFile
0x18003f441  call    cs:__imp_WriteFile
0x18003f447  test    eax, eax
0x18003f449  jz      short loc_18003F452
0x18003f44b  cmp     [rsp+270h+NumberOfBytesWritten], 4
0x18003f450  jz      short loc_18003F468
0x18003f452  mov     ebx, 80041001h
0x18003f457  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003f45d  mov     edx, ebx
0x18003f45f  mov     rcx, rax
0x18003f462  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003f468  lea     rax, WPP_GLOBAL_Control
0x18003f46f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f476  cmp     rcx, rax
0x18003f479  jz      short loc_18003F4A0
0x18003f47b  test    byte ptr [rcx+1Ch], 1
0x18003f47f  jz      short loc_18003F4A0
0x18003f481  cmp     byte ptr [rcx+19h], 2
0x18003f485  jb      short loc_18003F4A0
0x18003f487  mov     edx, 15h
0x18003f48c  mov     r9d, ebx
0x18003f48f  lea     r8, WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids
0x18003f496  mov     rcx, [rcx+10h]
0x18003f49a  call    WPP_SF_d
0x18003f49f  nop
0x18003f4a0  mov     rcx, rdi
0x18003f4a3  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003f4a9  nop
0x18003f4aa  mov     eax, ebx
0x18003f4ac  mov     rcx, [rbp+170h+var_20]
0x18003f4b3  xor     rcx, rsp; StackCookie
0x18003f4b6  call    __security_check_cookie
0x18003f4bb  lea     r11, [rsp+270h+var_10]
0x18003f4c3  mov     rbx, [r11+20h]
0x18003f4c7  mov     rsi, [r11+38h]
0x18003f4cb  mov     rsp, r11
0x18003f4ce  pop     r14
0x18003f4d0  pop     rdi
0x18003f4d1  pop     rbp
0x18003f4d2  retn
```
