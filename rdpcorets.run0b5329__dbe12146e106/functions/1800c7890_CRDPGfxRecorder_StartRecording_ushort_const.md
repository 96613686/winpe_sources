# CRDPGfxRecorder::StartRecording(ushort const *)

- ea: `0x1800c7890`
- end: `0x1800c7b2d`
- name: `?StartRecording@CRDPGfxRecorder@@UEAAJPEBG@Z`
- size: `669`
- prototype: `__int64 __fastcall(CRDPGfxRecorder *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180009088`
- `0x1800091a8`
- `0x18002e600`
- `0x180033da0`
- `0x180034970`
- `0x1800c7890`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c79b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7a82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c79b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7a82`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c7afb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800c7afb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c7a78`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c7a78`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c799c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c799c`

## string_xrefs

- `0x1800c7aef`: `failed to open file`

## pseudocode

```c
__int64 __fastcall CRDPGfxRecorder::StartRecording(CRDPGfxRecorder *this, const unsigned __int16 *a2)
{
  signed int v4; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v6; // edx
  const char *v7; // rcx
  int v8; // esi
  HANDLE FileW; // rax
  signed int LastError; // eax
  void *v11; // rcx
  signed int v12; // eax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  int Buffer; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v18; // [rsp+4Ch] [rbp-B4h]
  WCHAR FileName[264]; // [rsp+60h] [rbp-A0h] BYREF

  Buffer = 0;
  NumberOfBytesWritten = 0;
  v18 = 0;
  memset_0(FileName, 0, 0x208u);
  v4 = StringCchPrintfW(FileName, 0x104u, L"%s", a2);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v6 = 12;
LABEL_6:
      v7 = "Failed to print file name";
LABEL_7:
      LODWORD(dwFlagsAndAttributes) = v4;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        (unsigned int)WPP_00f57cbcba22367f230f2d13c3b6dfe1_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v7,
        dwFlagsAndAttributes);
    }
    return (unsigned int)v4;
  }
  v8 = 0;
  while ( 1 )
  {
    FileW = CreateFileW(FileName, 0x40000000u, 0, 0, 1u, 0x80u, 0);
    *((_QWORD *)this + 6) = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError == 80 )
      {
        dwCreationDisposition[0] = ++v8;
        v4 = StringCchPrintfW(FileName, 0x104u, L"%s-%d", a2, *(_QWORD *)dwCreationDisposition);
        if ( v4 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v6 = 13;
            goto LABEL_6;
          }
          return (unsigned int)v4;
        }
        goto LABEL_19;
      }
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( v4 < 0 )
        break;
    }
LABEL_19:
    v11 = (void *)*((_QWORD *)this + 6);
    if ( v11 != (void *)-1LL )
    {
      Buffer = 1651856467;
      WORD4(v18) = 0;
      *(_QWORD *)&v18 = 0x1400000001LL;
      HIDWORD(v18) = 1;
      if ( WriteFile(v11, &Buffer, 0x14u, &NumberOfBytesWritten, 0) )
        goto LABEL_33;
      v12 = GetLastError();
      v4 = v12;
      if ( v12 > 0 )
        v4 = (unsigned __int16)v12 | 0x80070000;
      if ( v4 >= 0 )
      {
LABEL_33:
        *((_DWORD *)this + 16) = GetTickCount();
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v6 = 15;
LABEL_32:
        v7 = "failed to open file";
        goto LABEL_7;
      }
      return (unsigned int)v4;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 14;
    goto LABEL_32;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800c7890  mov     [rsp-8+arg_10], rbx
0x1800c7895  mov     [rsp-8+arg_18], rsi
0x1800c789a  push    rbp
0x1800c789b  push    rdi
0x1800c789c  push    r14
0x1800c789e  lea     rbp, [rsp-180h]
0x1800c78a6  sub     rsp, 280h
0x1800c78ad  mov     rax, cs:__security_cookie
0x1800c78b4  xor     rax, rsp
0x1800c78b7  mov     [rbp+190h+var_20], rax
0x1800c78be  mov     r14, rdx
0x1800c78c1  mov     [rsp+290h+Buffer], 0
0x1800c78c9  mov     rdi, rcx
0x1800c78cc  mov     [rsp+290h+NumberOfBytesWritten], 0
0x1800c78d4  xorps   xmm0, xmm0
0x1800c78d7  lea     rcx, [rsp+290h+FileName]; void *
0x1800c78dc  xor     edx, edx; Val
0x1800c78de  mov     r8d, 208h; Size
0x1800c78e4  movups  [rsp+290h+var_244], xmm0
0x1800c78e9  call    memset_0
0x1800c78ee  mov     r9, r14
0x1800c78f1  lea     r8, aS_0; "%s"
0x1800c78f8  mov     edx, 104h; unsigned __int64
0x1800c78fd  lea     rcx, [rsp+290h+FileName]; unsigned __int16 *
0x1800c7902  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c7907  mov     ebx, eax
0x1800c7909  test    eax, eax
0x1800c790b  jns     short loc_1800C7971
0x1800c790d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7914  lea     rax, WPP_GLOBAL_Control
0x1800c791b  cmp     rcx, rax
0x1800c791e  jz      loc_1800C7B04
0x1800c7924  test    byte ptr [rcx+1Ch], 8
0x1800c7928  jz      loc_1800C7B04
0x1800c792e  cmp     byte ptr [rcx+19h], 2
0x1800c7932  jb      loc_1800C7B04
0x1800c7938  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800c793d  mov     edx, 0Ch
0x1800c7942  lea     rcx, aFailedToPrintF; "Failed to print file name"
0x1800c7949  mov     dword ptr [rsp+290h+dwFlagsAndAttributes], ebx
0x1800c794d  lea     r8, WPP_00f57cbcba22367f230f2d13c3b6dfe1_Traceguids
0x1800c7954  mov     qword ptr [rsp+290h+dwCreationDisposition], rcx
0x1800c7959  mov     r9d, eax
0x1800c795c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7963  mov     rcx, [rcx+10h]
0x1800c7967  call    WPP_SF_DsD
0x1800c796c  jmp     loc_1800C7B04
0x1800c7971  xor     esi, esi
0x1800c7973  mov     [rsp+290h+hTemplateFile], 0; hTemplateFile
0x1800c797c  lea     rcx, [rsp+290h+FileName]; lpFileName
0x1800c7981  mov     dword ptr [rsp+290h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800c7989  xor     r9d, r9d; lpSecurityAttributes
0x1800c798c  xor     r8d, r8d; dwShareMode
0x1800c798f  mov     [rsp+290h+dwCreationDisposition], 1; dwCreationDisposition
0x1800c7997  mov     edx, 40000000h; dwDesiredAccess
0x1800c799c  call    cs:__imp_CreateFileW
0x1800c79a2  mov     [rdi+30h], rax
0x1800c79a6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800c79aa  jnz     loc_1800C7A31
0x1800c79b0  call    cs:__imp_GetLastError
0x1800c79b6  mov     ebx, eax
0x1800c79b8  cmp     eax, 50h ; 'P'
0x1800c79bb  jnz     short loc_1800C7A1C
0x1800c79bd  inc     esi
0x1800c79bf  lea     r8, aSD_0; "%s-%d"
0x1800c79c6  mov     r9, r14
0x1800c79c9  mov     [rsp+290h+dwCreationDisposition], esi
0x1800c79cd  mov     edx, 104h; unsigned __int64
0x1800c79d2  lea     rcx, [rsp+290h+FileName]; unsigned __int16 *
0x1800c79d7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800c79dc  mov     ebx, eax
0x1800c79de  test    eax, eax
0x1800c79e0  jns     short loc_1800C7A31
0x1800c79e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c79e9  lea     rax, WPP_GLOBAL_Control
0x1800c79f0  cmp     rcx, rax
0x1800c79f3  jz      loc_1800C7B04
0x1800c79f9  test    byte ptr [rcx+1Ch], 8
0x1800c79fd  jz      loc_1800C7B04
0x1800c7a03  cmp     byte ptr [rcx+19h], 2
0x1800c7a07  jb      loc_1800C7B04
0x1800c7a0d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800c7a12  mov     edx, 0Dh
0x1800c7a17  jmp     loc_1800C7942
0x1800c7a1c  test    eax, eax
0x1800c7a1e  jle     short loc_1800C7A29
0x1800c7a20  movzx   ebx, ax
0x1800c7a23  or      ebx, 80070000h
0x1800c7a29  test    ebx, ebx
0x1800c7a2b  js      loc_1800C7AC6
0x1800c7a31  mov     rcx, [rdi+30h]; hFile
0x1800c7a35  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800c7a39  jz      loc_1800C7973
0x1800c7a3f  xor     eax, eax
0x1800c7a41  mov     [rsp+290h+Buffer], 62755453h
0x1800c7a49  mov     r8d, 14h; nNumberOfBytesToWrite
0x1800c7a4f  mov     word ptr [rsp+290h+var_244+8], ax
0x1800c7a54  lea     r9, [rsp+290h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800c7a59  mov     dword ptr [rsp+290h+var_244+4], r8d
0x1800c7a5e  lea     rdx, [rsp+290h+Buffer]; lpBuffer
0x1800c7a63  mov     qword ptr [rsp+290h+dwCreationDisposition], rax; lpOverlapped
0x1800c7a68  mov     dword ptr [rsp+290h+var_244], 1
0x1800c7a70  mov     dword ptr [rsp+290h+var_244+0Ch], 1
0x1800c7a78  call    cs:__imp_WriteFile
0x1800c7a7e  test    eax, eax
0x1800c7a80  jnz     short loc_1800C7AFB
0x1800c7a82  call    cs:__imp_GetLastError
0x1800c7a88  mov     ebx, eax
0x1800c7a8a  test    eax, eax
0x1800c7a8c  jle     short loc_1800C7A97
0x1800c7a8e  movzx   ebx, ax
0x1800c7a91  or      ebx, 80070000h
0x1800c7a97  test    ebx, ebx
0x1800c7a99  jns     short loc_1800C7AFB
0x1800c7a9b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7aa2  lea     rax, WPP_GLOBAL_Control
0x1800c7aa9  cmp     rcx, rax
0x1800c7aac  jz      short loc_1800C7B04
0x1800c7aae  test    byte ptr [rcx+1Ch], 8
0x1800c7ab2  jz      short loc_1800C7B04
0x1800c7ab4  cmp     byte ptr [rcx+19h], 2
0x1800c7ab8  jb      short loc_1800C7B04
0x1800c7aba  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800c7abf  mov     edx, 0Fh
0x1800c7ac4  jmp     short loc_1800C7AEF
0x1800c7ac6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c7acd  lea     rax, WPP_GLOBAL_Control
0x1800c7ad4  cmp     rcx, rax
0x1800c7ad7  jz      short loc_1800C7B04
0x1800c7ad9  test    byte ptr [rcx+1Ch], 8
0x1800c7add  jz      short loc_1800C7B04
0x1800c7adf  cmp     byte ptr [rcx+19h], 2
0x1800c7ae3  jb      short loc_1800C7B04
0x1800c7ae5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800c7aea  mov     edx, 0Eh
0x1800c7aef  lea     rcx, aFailedToOpenFi; "failed to open file"
0x1800c7af6  jmp     loc_1800C7949
0x1800c7afb  call    cs:__imp_GetTickCount
0x1800c7b01  mov     [rdi+40h], eax
0x1800c7b04  mov     eax, ebx
0x1800c7b06  mov     rcx, [rbp+190h+var_20]
0x1800c7b0d  xor     rcx, rsp; StackCookie
0x1800c7b10  call    __security_check_cookie
0x1800c7b15  lea     r11, [rsp+290h+var_10]
0x1800c7b1d  mov     rbx, [r11+30h]
0x1800c7b21  mov     rsi, [r11+38h]
0x1800c7b25  mov     rsp, r11
0x1800c7b28  pop     r14
0x1800c7b2a  pop     rdi
0x1800c7b2b  pop     rbp
0x1800c7b2c  retn
```
