# _drr_ReadStateFile

- ea: `0x1800036c8`
- end: `0x180003ac9`
- name: `_drr_ReadStateFile`
- size: `1025`
- prototype: `__int64 __fastcall(const WCHAR *, _OWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180006230`

## callees

- `0x1800035cc`
- `0x1800035f4`
- `0x1800036c8`
- `0x180003d84`
- `0x18000cde8`
- `0x18000d1f0`
- `0x18000d2c8`
- `0x18000d384`
- `0x18000d89e`
- `0x18000d8d0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003884`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003884`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003a9d`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180003806`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180003806`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003719`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003719`

## pseudocode

```c
__int64 __fastcall drr_ReadStateFile(const WCHAR *a1, _OWORD *a2)
{
  HANDLE FileW; // rsi
  unsigned int File; // edi
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  DWORD LastError; // eax
  __int128 Buffer; // [rsp+50h] [rbp-69h] BYREF

  FileW = CreateFileW(a1, 1u, 1u, 0, 3u, 0x8000006u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    memset_0(&Buffer, 0, 0x84u);
    File = DRR_ReadFile(FileW, a2, 0x70u);
    if ( !File )
      File = 30;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_13;
    v7 = 10;
    v8 = File;
    goto LABEL_12;
  }
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError - 2 <= 1 )
  {
    File = 0;
    if ( a1 == Src )
      return File;
  }
  File = LastError;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v7 = 18;
LABEL_12:
    WPP_SF_D(v6[2], v7, WPP_fefedfb84db73ff4a9615eb38da9dc9d_Traceguids, v8);
  }
LABEL_13:
  memset_0(a2, 0, 0x70u);
  DRR_UninitRoamingTokenSet(a2 + 7);
  a2[7] = 0;
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  return File;
}

```

## disassembly

```asm
0x1800036c8  mov     [rsp-8+arg_10], rbx
0x1800036cd  mov     [rsp-8+arg_18], rsi
0x1800036d2  push    rbp
0x1800036d3  push    rdi
0x1800036d4  push    r14
0x1800036d6  lea     rbp, [rsp-47h]
0x1800036db  sub     rsp, 100h
0x1800036e2  mov     rax, cs:__security_cookie
0x1800036e9  xor     rax, rsp
0x1800036ec  mov     [rbp+57h+var_20], rax
0x1800036f0  xor     r9d, r9d; lpSecurityAttributes
0x1800036f3  mov     [rsp+110h+hTemplateFile], 0; hTemplateFile
0x1800036fc  mov     rbx, rdx
0x1800036ff  mov     [rsp+110h+dwFlagsAndAttributes], 8000006h; dwFlagsAndAttributes
0x180003707  mov     r14, rcx
0x18000370a  mov     [rsp+110h+dwCreationDisposition], 3; dwCreationDisposition
0x180003712  lea     edx, [r9+1]; dwDesiredAccess
0x180003716  mov     r8d, edx; dwShareMode
0x180003719  call    cs:__imp_CreateFileW
0x18000371f  mov     rsi, rax
0x180003722  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180003726  jz      loc_180003A29
0x18000372c  xor     edx, edx; Val
0x18000372e  lea     rcx, [rbp+57h+Buffer]; void *
0x180003732  mov     r8d, 84h; Size
0x180003738  call    memset_0
0x18000373d  lea     r9, [rbp+57h+var_D0]
0x180003741  mov     [rbp+57h+var_D0], 0
0x180003748  mov     r8d, 70h ; 'p'; nNumberOfBytesToRead
0x18000374e  mov     rdx, rbx; lpBuffer
0x180003751  mov     rcx, rsi; hFile
0x180003754  call    DRR_ReadFile
0x180003759  mov     edi, eax
0x18000375b  test    eax, eax
0x18000375d  jnz     short loc_180003768
0x18000375f  cmp     [rbp+57h+var_D0], 70h ; 'p'
0x180003763  jnb     short loc_180003793
0x180003765  lea     edi, [rax+1Eh]
0x180003768  mov     rcx, cs:WPP_GLOBAL_Control
0x18000376f  lea     rax, WPP_GLOBAL_Control
0x180003776  cmp     rcx, rax
0x180003779  jz      loc_180003A76
0x18000377f  test    byte ptr [rcx+1Ch], 2
0x180003783  jz      loc_180003A76
0x180003789  mov     edx, 0Ah
0x18000378e  jmp     loc_18000383F
0x180003793  cmp     byte ptr [rbx], 4Bh ; 'K'
0x180003796  jnz     loc_1800039F6
0x18000379c  cmp     byte ptr [rbx+1], 52h ; 'R'
0x1800037a0  jnz     loc_1800039F6
0x1800037a6  cmp     byte ptr [rbx+2], 53h ; 'S'
0x1800037aa  jnz     loc_1800039F6
0x1800037b0  cmp     byte ptr [rbx+3], 54h ; 'T'
0x1800037b4  jnz     loc_1800039F6
0x1800037ba  cmp     dword ptr [rbx+4], 10000h
0x1800037c1  jnz     loc_1800039F6
0x1800037c7  lea     rcx, [rbx+18h]; lpFileTime1
0x1800037cb  call    DRR_IsValidPastTime
0x1800037d0  test    eax, eax
0x1800037d2  jz      loc_1800039F6
0x1800037d8  lea     rcx, [rbx+20h]; lpFileTime1
0x1800037dc  call    DRR_IsValidPastTime
0x1800037e1  test    eax, eax
0x1800037e3  jz      loc_1800039F6
0x1800037e9  test    dword ptr [rbx+5Ch], 0FFFFFFFEh
0x1800037f0  jnz     loc_1800039F6
0x1800037f6  mov     r9d, 1; dwMoveMethod
0x1800037fc  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800037ff  mov     rcx, rsi; hFile
0x180003802  lea     edx, [r9+0Fh]; lDistanceToMove
0x180003806  call    cs:__imp_SetFilePointer
0x18000380c  cmp     eax, 0FFFFFFFFh
0x18000380f  jnz     short loc_180003847
0x180003811  call    cs:__imp_GetLastError
0x180003817  mov     edi, eax
0x180003819  mov     rcx, cs:WPP_GLOBAL_Control
0x180003820  lea     rax, WPP_GLOBAL_Control
0x180003827  cmp     rcx, rax
0x18000382a  jz      loc_180003A76
0x180003830  test    byte ptr [rcx+1Ch], 2
0x180003834  jz      loc_180003A76
0x18000383a  mov     edx, 0Ch
0x18000383f  mov     r9d, edi
0x180003842  jmp     loc_180003A66
0x180003847  mov     r14d, 80h
0x18000384d  lea     r9, [rbp+57h+var_D0]
0x180003851  mov     [rbp+57h+var_40], 0
0x180003858  mov     r8d, r14d; nNumberOfBytesToRead
0x18000385b  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x18000385f  mov     rcx, rsi; hFile
0x180003862  call    DRR_ReadFile
0x180003867  mov     edi, eax
0x180003869  test    eax, eax
0x18000386b  jnz     loc_1800039CB
0x180003871  mov     eax, [rbp+57h+var_D0]
0x180003874  cmp     eax, r14d
0x180003877  jnz     loc_180003920
0x18000387d  mov     edx, 84h; uBytes
0x180003882  xor     ecx, ecx; uFlags
0x180003884  call    cs:__imp_LocalAlloc
0x18000388a  mov     rdx, rax
0x18000388d  test    rax, rax
0x180003890  jz      loc_180003976
0x180003896  movups  xmm0, [rbp+57h+Buffer]
0x18000389a  lea     rcx, [rbx+70h]
0x18000389e  lea     r8d, [rdi+1]
0x1800038a2  movups  xmmword ptr [rax], xmm0
0x1800038a5  movups  xmm1, [rbp+57h+var_B0]
0x1800038a9  movups  xmmword ptr [rax+10h], xmm1
0x1800038ad  movups  xmm0, [rbp+57h+var_A0]
0x1800038b1  movups  xmmword ptr [rax+20h], xmm0
0x1800038b5  movups  xmm1, [rbp+57h+var_90]
0x1800038b9  movups  xmmword ptr [rax+30h], xmm1
0x1800038bd  movups  xmm0, [rbp+57h+var_80]
0x1800038c1  movups  xmmword ptr [rax+40h], xmm0
0x1800038c5  movups  xmm1, [rbp+57h+var_70]
0x1800038c9  movups  xmmword ptr [rax+50h], xmm1
0x1800038cd  movups  xmm0, [rbp+57h+var_60]
0x1800038d1  movups  xmmword ptr [rax+60h], xmm0
0x1800038d5  movups  xmm1, [rbp+57h+var_50]
0x1800038d9  movups  xmmword ptr [rax+70h], xmm1
0x1800038dd  mov     eax, [rbp+57h+var_40]
0x1800038e0  mov     [rdx+80h], eax
0x1800038e6  call    DRR_AddRoamingTokenToSet
0x1800038eb  mov     edi, eax
0x1800038ed  test    eax, eax
0x1800038ef  jz      loc_18000384D
0x1800038f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038fc  lea     rax, WPP_GLOBAL_Control
0x180003903  cmp     rcx, rax
0x180003906  jz      loc_180003A76
0x18000390c  test    byte ptr [rcx+1Ch], 2
0x180003910  jz      loc_180003A76
0x180003916  mov     edx, 0Fh
0x18000391b  jmp     loc_18000383F
0x180003920  test    eax, eax
0x180003922  jnz     short loc_1800039A0
0x180003924  lea     rdx, [rbp+57h+var_30]
0x180003928  mov     rcx, rbx
0x18000392b  call    DRR_HashState
0x180003930  mov     rax, [rbx+8]
0x180003934  cmp     rax, [rbp+57h+var_30]
0x180003938  jnz     short loc_180003948
0x18000393a  mov     rax, [rbx+10h]
0x18000393e  cmp     rax, [rbp+57h+var_28]
0x180003942  jz      loc_180003A9A
0x180003948  mov     edi, 0Dh
0x18000394d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003954  lea     rax, WPP_GLOBAL_Control
0x18000395b  cmp     rcx, rax
0x18000395e  jz      loc_180003A76
0x180003964  test    byte ptr [rcx+1Ch], 2
0x180003968  jz      loc_180003A76
0x18000396e  lea     edx, [rdi+4]
0x180003971  jmp     loc_180003A17
0x180003976  mov     edi, 0Eh
0x18000397b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003982  lea     rax, WPP_GLOBAL_Control
0x180003989  cmp     rcx, rax
0x18000398c  jz      loc_180003A76
0x180003992  test    byte ptr [rcx+1Ch], 2
0x180003996  jz      loc_180003A76
0x18000399c  mov     edx, edi
0x18000399e  jmp     short loc_180003A17
0x1800039a0  mov     edi, 0Dh
0x1800039a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800039ac  lea     rax, WPP_GLOBAL_Control
0x1800039b3  cmp     rcx, rax
0x1800039b6  jz      loc_180003A76
0x1800039bc  test    byte ptr [rcx+1Ch], 2
0x1800039c0  jz      loc_180003A76
0x1800039c6  lea     edx, [rdi+3]
0x1800039c9  jmp     short loc_180003A17
0x1800039cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800039d2  lea     rax, WPP_GLOBAL_Control
0x1800039d9  cmp     rcx, rax
0x1800039dc  jz      loc_180003A76
0x1800039e2  test    byte ptr [rcx+1Ch], 2
0x1800039e6  jz      loc_180003A76
0x1800039ec  mov     edx, 0Dh
0x1800039f1  jmp     loc_18000383F
0x1800039f6  mov     edi, 0Dh
0x1800039fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a02  lea     rax, WPP_GLOBAL_Control
0x180003a09  cmp     rcx, rax
0x180003a0c  jz      short loc_180003A76
0x180003a0e  test    byte ptr [rcx+1Ch], 2
0x180003a12  jz      short loc_180003A76
0x180003a14  lea     edx, [rdi-2]
0x180003a17  mov     rcx, [rcx+10h]
0x180003a1b  lea     r8, WPP_fefedfb84db73ff4a9615eb38da9dc9d_Traceguids
0x180003a22  call    WPP_SF_
0x180003a27  jmp     short loc_180003A76
0x180003a29  call    cs:__imp_GetLastError
0x180003a2f  mov     r9d, eax
0x180003a32  lea     ecx, [rax-2]
0x180003a35  cmp     ecx, 1
0x180003a38  ja      short loc_180003A45
0x180003a3a  xor     edi, edi
0x180003a3c  cmp     r14, cs:Src
0x180003a43  jz      short loc_180003AA3
0x180003a45  mov     edi, r9d
0x180003a48  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a4f  lea     rax, WPP_GLOBAL_Control
0x180003a56  cmp     rcx, rax
0x180003a59  jz      short loc_180003A76
0x180003a5b  test    byte ptr [rcx+1Ch], 2
0x180003a5f  jz      short loc_180003A76
0x180003a61  mov     edx, 12h
0x180003a66  mov     rcx, [rcx+10h]
0x180003a6a  lea     r8, WPP_fefedfb84db73ff4a9615eb38da9dc9d_Traceguids
0x180003a71  call    WPP_SF_D
0x180003a76  xor     edx, edx; Val
0x180003a78  mov     rcx, rbx; void *
0x180003a7b  lea     r8d, [rdx+70h]; Size
0x180003a7f  call    memset_0
0x180003a84  lea     rcx, [rbx+70h]
0x180003a88  call    DRR_UninitRoamingTokenSet
0x180003a8d  xorps   xmm0, xmm0
0x180003a90  movups  xmmword ptr [rbx+70h], xmm0
0x180003a94  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180003a98  jz      short loc_180003AA3
0x180003a9a  mov     rcx, rsi; hObject
0x180003a9d  call    cs:__imp_CloseHandle
0x180003aa3  mov     eax, edi
0x180003aa5  mov     rcx, [rbp+57h+var_20]
0x180003aa9  xor     rcx, rsp; StackCookie
0x180003aac  call    __security_check_cookie
0x180003ab1  lea     r11, [rsp+110h+var_10]
0x180003ab9  mov     rbx, [r11+30h]
0x180003abd  mov     rsi, [r11+38h]
0x180003ac1  mov     rsp, r11
0x180003ac4  pop     r14
0x180003ac6  pop     rdi
0x180003ac7  pop     rbp
0x180003ac8  retn
```
