# DoAutoDatabaseRestore(void)

- ea: `0x1800393e4`
- end: `0x180039559`
- name: `?DoAutoDatabaseRestore@@YAJXZ`
- size: `373`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003db10`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x180013f90`
- `0x180023bf0`
- `0x1800393e4`
- `0x18003c16c`
- `0x18003d2d0`
- `0x18004025c`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180039484`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180039542`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180039484`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180039542`
- `wbemcomn!GetMemLogObject` at `0x18003943a`
- `wbemcomn!GetMemLogObject` at `0x1800394f6`
- `wbemcomn!GetMemLogObject` at `0x18003943a`
- `wbemcomn!GetMemLogObject` at `0x1800394f6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003944a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180039501`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003944a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180039501`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800394d1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800394d1`

## pseudocode

```c
__int64 DoAutoDatabaseRestore(void)
{
  unsigned __int16 *v0; // rdi
  CMemoryLog *v1; // rax
  int v3; // esi
  __int64 v4; // rbx
  DWORD FileAttributesW; // eax
  const unsigned __int16 *v6; // r8
  CMemoryLog *MemLogObject; // rax
  char v8; // [rsp+40h] [rbp+8h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids);
  }
  CFileName::CFileName((CFileName *)&lpFileName);
  v0 = (unsigned __int16 *)lpFileName;
  if ( lpFileName )
  {
    v3 = 0;
    v4 = dword_1800597A0;
    StringCchCopyNW((unsigned __int16 *)lpFileName, 0x173u, &FileName, dword_1800597A0);
    v0[v4] = 0;
    StringCchCatW(v0, 0x173u, L"\\repdrvfs.rec");
    FileAttributesW = GetFileAttributesW(v0);
    if ( FileAttributesW == -1
      || (FileAttributesW & 0x1650) != 0
      || (v3 = CRepositoryPackager::UnpackageRepository((CRepositoryPackager *)&v8, v0, v6), v3 >= 0) )
    {
      ReportFutureCorruption();
    }
    else
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v3);
    }
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        WPP_53e1474670223052d7bc731b72ed24d6_Traceguids,
        (unsigned int)v3);
    }
    CWin32DefaultArena::WbemMemFree(v0);
    return (unsigned int)v3;
  }
  else
  {
    v1 = GetMemLogObject();
    CMemoryLog::Write(v1, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids, 2147749894LL);
    }
    CWin32DefaultArena::WbemMemFree(0);
    return 2147749894LL;
  }
}

```

## disassembly

```asm
0x1800393e4  mov     [rsp+arg_10], rbx
0x1800393e9  push    rsi
0x1800393ea  push    rdi
0x1800393eb  push    r15
0x1800393ed  sub     rsp, 20h
0x1800393f1  lea     r15, WPP_GLOBAL_Control
0x1800393f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800393ff  cmp     rcx, r15
0x180039402  jz      short loc_180039425
0x180039404  test    byte ptr [rcx+1Ch], 1
0x180039408  jz      short loc_180039425
0x18003940a  cmp     byte ptr [rcx+19h], 5
0x18003940e  jb      short loc_180039425
0x180039410  mov     edx, 3Ah ; ':'
0x180039415  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x18003941c  mov     rcx, [rcx+10h]
0x180039420  call    WPP_SF_
0x180039425  lea     rcx, [rsp+38h+lpFileName]; this
0x18003942a  call    ??0CFileName@@QEAA@XZ; CFileName::CFileName(void)
0x18003942f  nop
0x180039430  mov     rdi, [rsp+38h+lpFileName]
0x180039435  test    rdi, rdi
0x180039438  jnz     short loc_180039492
0x18003943a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180039440  mov     ebx, 80041006h
0x180039445  mov     edx, ebx
0x180039447  mov     rcx, rax
0x18003944a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180039450  mov     rcx, cs:WPP_GLOBAL_Control
0x180039457  cmp     rcx, r15
0x18003945a  jz      short loc_180039482
0x18003945c  test    byte ptr [rcx+1Ch], 1
0x180039460  jz      short loc_180039482
0x180039462  cmp     byte ptr [rcx+19h], 2
0x180039466  jb      short loc_180039482
0x180039468  lea     edx, [rdi+3Bh]
0x18003946b  mov     r9d, 80041006h
0x180039471  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x180039478  mov     rcx, [rcx+10h]
0x18003947c  call    WPP_SF_d
0x180039481  nop
0x180039482  xor     ecx, ecx
0x180039484  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003948a  nop
0x18003948b  mov     eax, ebx
0x18003948d  jmp     loc_18003954B
0x180039492  xor     esi, esi
0x180039494  movsxd  rbx, cs:dword_1800597A0
0x18003949b  mov     r9, rbx; unsigned __int64
0x18003949e  lea     r8, FileName; unsigned __int16 *
0x1800394a5  mov     edx, 173h; unsigned __int64
0x1800394aa  mov     rcx, rdi; unsigned __int16 *
0x1800394ad  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800394b2  xor     r11d, r11d
0x1800394b5  mov     [rdi+rbx*2], r11w
0x1800394ba  lea     r8, aRepdrvfsRec; "\\repdrvfs.rec"
0x1800394c1  mov     edx, 173h; unsigned __int64
0x1800394c6  mov     rcx, rdi; unsigned __int16 *
0x1800394c9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800394ce  mov     rcx, rdi; lpFileName
0x1800394d1  call    cs:__imp_GetFileAttributesW
0x1800394d7  cmp     eax, 0FFFFFFFFh
0x1800394da  jz      short loc_180039509
0x1800394dc  test    eax, 1650h
0x1800394e1  jnz     short loc_180039509
0x1800394e3  mov     rdx, rdi; lpFileName
0x1800394e6  lea     rcx, [rsp+38h+arg_0]; this
0x1800394eb  call    ?UnpackageRepository@CRepositoryPackager@@QEAAJPEBG0@Z; CRepositoryPackager::UnpackageRepository(ushort const *,ushort const *)
0x1800394f0  mov     esi, eax
0x1800394f2  test    eax, eax
0x1800394f4  jns     short loc_180039509
0x1800394f6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800394fc  mov     edx, esi
0x1800394fe  mov     rcx, rax
0x180039501  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180039507  jmp     short loc_18003950E
0x180039509  call    ?ReportFutureCorruption@@YAJXZ; ReportFutureCorruption(void)
0x18003950e  mov     rcx, cs:WPP_GLOBAL_Control
0x180039515  cmp     rcx, r15
0x180039518  jz      short loc_18003953F
0x18003951a  test    byte ptr [rcx+1Ch], 1
0x18003951e  jz      short loc_18003953F
0x180039520  cmp     byte ptr [rcx+19h], 2
0x180039524  jb      short loc_18003953F
0x180039526  mov     edx, 3Ch ; '<'
0x18003952b  mov     r9d, esi
0x18003952e  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x180039535  mov     rcx, [rcx+10h]
0x180039539  call    WPP_SF_d
0x18003953e  nop
0x18003953f  mov     rcx, rdi
0x180039542  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180039548  nop
0x180039549  mov     eax, esi
0x18003954b  mov     rbx, [rsp+38h+arg_10]
0x180039550  add     rsp, 20h
0x180039554  pop     r15
0x180039556  pop     rdi
0x180039557  pop     rsi
0x180039558  retn
```
