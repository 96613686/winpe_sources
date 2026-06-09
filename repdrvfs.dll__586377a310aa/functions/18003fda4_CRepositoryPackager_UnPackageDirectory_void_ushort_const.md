# CRepositoryPackager::UnPackageDirectory(void *,ushort const *)

- ea: `0x18003fda4`
- end: `0x18003ffcc`
- name: `?UnPackageDirectory@CRepositoryPackager@@AEAAJPEAXPEBG@Z`
- size: `552`
- prototype: `__int64 __fastcall(CRepositoryPackager *__hidden this, void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003fcac`

## callees

- `0x1800012b8`
- `0x180013880`
- `0x180013f90`
- `0x180023bf0`
- `0x18003fcac`
- `0x18003fda4`
- `0x1800443df`
- `0x180044420`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003fe84`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003ff32`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003ff4e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003fe84`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003ff32`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003ff4e`
- `wbemcomn!GetMemLogObject` at `0x18003fe33`
- `wbemcomn!GetMemLogObject` at `0x18003fede`
- `wbemcomn!GetMemLogObject` at `0x18003ff57`
- `wbemcomn!GetMemLogObject` at `0x18003fe33`
- `wbemcomn!GetMemLogObject` at `0x18003fede`
- `wbemcomn!GetMemLogObject` at `0x18003ff57`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003fe43`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003feee`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ff67`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003fe43`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003feee`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ff67`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003fe06`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003fe06`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003fec7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18003fec7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fed1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fed1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRepositoryPackager::UnPackageDirectory(
        CRepositoryPackager *this,
        void *a2,
        const unsigned __int16 *a3)
{
  unsigned __int16 *v6; // rdi
  CMemoryLog *v7; // rax
  unsigned int v8; // ebx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v10; // rax
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-248h] BYREF
  LPCWSTR lpPathName; // [rsp+38h] [rbp-240h] BYREF
  _BYTE v14[4]; // [rsp+40h] [rbp-238h] BYREF
  unsigned __int16 Buffer[262]; // [rsp+44h] [rbp-234h] BYREF

  memset_0(v14, 0, 0x210u);
  NumberOfBytesRead = 0;
  if ( ReadFile(a2, Buffer, 0x20Cu, &NumberOfBytesRead, 0) && NumberOfBytesRead == 524 )
  {
    CFileName::CFileName((CFileName *)&lpPathName);
    v6 = (unsigned __int16 *)lpPathName;
    if ( lpPathName )
    {
      StringCchCopyW((unsigned __int16 *)lpPathName, 0x173u, a3);
      StringCchCatW(v6, 0x173u, L"\\");
      StringCchCatW(v6, 0x173u, Buffer);
      if ( CreateDirectoryW(v6, 0) || GetLastError() == 183 )
      {
        v8 = CRepositoryPackager::UnPackageContentsOfDirectory(this, a2, v6);
        CWin32DefaultArena::WbemMemFree(v6);
      }
      else
      {
        MemLogObject = GetMemLogObject();
        v8 = -2147217407;
        CMemoryLog::Write(MemLogObject, -2147217407);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            28,
            WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids,
            2147749889LL);
        }
        CWin32DefaultArena::WbemMemFree(v6);
      }
    }
    else
    {
      v7 = GetMemLogObject();
      v8 = -2147217402;
      CMemoryLog::Write(v7, -2147217402);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids, 2147749894LL);
      }
      CWin32DefaultArena::WbemMemFree(0);
    }
  }
  else
  {
    v10 = GetMemLogObject();
    v8 = -2147217407;
    CMemoryLog::Write(v10, -2147217407);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids, 2147749889LL);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18003fda4  mov     [rsp+arg_18], rbx
0x18003fda9  push    rbp
0x18003fdaa  push    rsi
0x18003fdab  push    rdi
0x18003fdac  sub     rsp, 260h
0x18003fdb3  mov     rax, cs:__security_cookie
0x18003fdba  xor     rax, rsp
0x18003fdbd  mov     [rsp+278h+var_28], rax
0x18003fdc5  mov     rbp, r8
0x18003fdc8  mov     rbx, rdx
0x18003fdcb  mov     rsi, rcx
0x18003fdce  xor     edx, edx; Val
0x18003fdd0  mov     r8d, 210h; Size
0x18003fdd6  lea     rcx, [rsp+278h+var_238]; void *
0x18003fddb  call    memset_0
0x18003fde0  mov     [rsp+278h+NumberOfBytesRead], 0
0x18003fde8  mov     [rsp+278h+lpOverlapped], 0; lpOverlapped
0x18003fdf1  lea     r9, [rsp+278h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18003fdf6  mov     edi, 20Ch
0x18003fdfb  mov     r8d, edi; nNumberOfBytesToRead
0x18003fdfe  lea     rdx, [rsp+278h+Buffer]; lpBuffer
0x18003fe03  mov     rcx, rbx; hFile
0x18003fe06  call    cs:__imp_ReadFile
0x18003fe0c  test    eax, eax
0x18003fe0e  jz      loc_18003FF57
0x18003fe14  cmp     [rsp+278h+NumberOfBytesRead], edi
0x18003fe18  jnz     loc_18003FF57
0x18003fe1e  lea     rcx, [rsp+278h+lpPathName]; this
0x18003fe23  call    ??0CFileName@@QEAA@XZ; CFileName::CFileName(void)
0x18003fe28  nop
0x18003fe29  mov     rdi, [rsp+278h+lpPathName]
0x18003fe2e  test    rdi, rdi
0x18003fe31  jnz     short loc_18003FE90
0x18003fe33  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003fe39  mov     ebx, 80041006h
0x18003fe3e  mov     edx, ebx
0x18003fe40  mov     rcx, rax
0x18003fe43  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003fe49  lea     rax, WPP_GLOBAL_Control
0x18003fe50  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fe57  cmp     rcx, rax
0x18003fe5a  jz      short loc_18003FE82
0x18003fe5c  test    byte ptr [rcx+1Ch], 1
0x18003fe60  jz      short loc_18003FE82
0x18003fe62  cmp     byte ptr [rcx+19h], 2
0x18003fe66  jb      short loc_18003FE82
0x18003fe68  lea     edx, [rdi+1Bh]
0x18003fe6b  mov     r9d, 80041006h
0x18003fe71  lea     r8, WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids
0x18003fe78  mov     rcx, [rcx+10h]
0x18003fe7c  call    WPP_SF_d
0x18003fe81  nop
0x18003fe82  xor     ecx, ecx
0x18003fe84  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003fe8a  nop
0x18003fe8b  jmp     loc_18003FFA7
0x18003fe90  mov     r8, rbp; unsigned __int16 *
0x18003fe93  mov     ebp, 173h
0x18003fe98  mov     edx, ebp; unsigned __int64
0x18003fe9a  mov     rcx, rdi; unsigned __int16 *
0x18003fe9d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003fea2  lea     r8, asc_18004B0E0; "\\"
0x18003fea9  mov     edx, ebp; unsigned __int64
0x18003feab  mov     rcx, rdi; unsigned __int16 *
0x18003feae  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003feb3  lea     r8, [rsp+278h+Buffer]; unsigned __int16 *
0x18003feb8  mov     edx, ebp; unsigned __int64
0x18003feba  mov     rcx, rdi; unsigned __int16 *
0x18003febd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003fec2  xor     edx, edx; lpSecurityAttributes
0x18003fec4  mov     rcx, rdi; lpPathName
0x18003fec7  call    cs:__imp_CreateDirectoryW
0x18003fecd  test    eax, eax
0x18003fecf  jnz     short loc_18003FF3B
0x18003fed1  call    cs:__imp_GetLastError
0x18003fed7  cmp     eax, 0B7h
0x18003fedc  jz      short loc_18003FF3B
0x18003fede  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003fee4  mov     ebx, 80041001h
0x18003fee9  mov     edx, ebx
0x18003feeb  mov     rcx, rax
0x18003feee  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003fef4  lea     rax, WPP_GLOBAL_Control
0x18003fefb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ff02  cmp     rcx, rax
0x18003ff05  jz      short loc_18003FF2F
0x18003ff07  test    byte ptr [rcx+1Ch], 1
0x18003ff0b  jz      short loc_18003FF2F
0x18003ff0d  cmp     byte ptr [rcx+19h], 2
0x18003ff11  jb      short loc_18003FF2F
0x18003ff13  mov     edx, 1Ch
0x18003ff18  mov     r9d, 80041001h
0x18003ff1e  lea     r8, WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids
0x18003ff25  mov     rcx, [rcx+10h]
0x18003ff29  call    WPP_SF_d
0x18003ff2e  nop
0x18003ff2f  mov     rcx, rdi
0x18003ff32  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003ff38  nop
0x18003ff39  jmp     short loc_18003FFA7
0x18003ff3b  mov     r8, rdi; unsigned __int16 *
0x18003ff3e  mov     rdx, rbx; void *
0x18003ff41  mov     rcx, rsi; this
0x18003ff44  call    ?UnPackageContentsOfDirectory@CRepositoryPackager@@AEAAJPEAXPEBG@Z; CRepositoryPackager::UnPackageContentsOfDirectory(void *,ushort const *)
0x18003ff49  mov     ebx, eax
0x18003ff4b  mov     rcx, rdi
0x18003ff4e  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003ff54  nop
0x18003ff55  jmp     short loc_18003FFA7
0x18003ff57  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003ff5d  mov     ebx, 80041001h
0x18003ff62  mov     edx, ebx
0x18003ff64  mov     rcx, rax
0x18003ff67  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003ff6d  lea     rax, WPP_GLOBAL_Control
0x18003ff74  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ff7b  cmp     rcx, rax
0x18003ff7e  jz      short loc_18003FFA7
0x18003ff80  test    byte ptr [rcx+1Ch], 1
0x18003ff84  jz      short loc_18003FFA7
0x18003ff86  cmp     byte ptr [rcx+19h], 2
0x18003ff8a  jb      short loc_18003FFA7
0x18003ff8c  mov     edx, 1Ah
0x18003ff91  mov     r9d, 80041001h
0x18003ff97  lea     r8, WPP_b554bc6150a33b8ad3dfed538f333758_Traceguids
0x18003ff9e  mov     rcx, [rcx+10h]
0x18003ffa2  call    WPP_SF_d
0x18003ffa7  mov     eax, ebx
0x18003ffa9  mov     rcx, [rsp+278h+var_28]
0x18003ffb1  xor     rcx, rsp; StackCookie
0x18003ffb4  call    __security_check_cookie
0x18003ffb9  mov     rbx, [rsp+278h+arg_18]
0x18003ffc1  add     rsp, 260h
0x18003ffc8  pop     rdi
0x18003ffc9  pop     rsi
0x18003ffca  pop     rbp
0x18003ffcb  retn
```
