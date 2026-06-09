# DhcpNdisHandlePnPEvent

- ea: `0x18000ed88`
- end: `0x18000f017`
- name: `DhcpNdisHandlePnPEvent`
- size: `655`
- prototype: `__int64 __fastcall(__int64, DWORD, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000f2a0`

## callees

- `0x180005162`
- `0x18000ed88`
- `0x18000f020`
- `0x180012b80`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!SetLastError` at `0x18000efd3`
- `api-ms-win-downlevel-kernel32-l1-1-0!SetLastError` at `0x18000efd3`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetLastError` at `0x18000ef8e`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetLastError` at `0x18000efc0`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetLastError` at `0x18000ef8e`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetLastError` at `0x18000efc0`
- `api-ms-win-downlevel-kernel32-l1-1-0!CloseHandle` at `0x18000ef99`
- `api-ms-win-downlevel-kernel32-l1-1-0!CloseHandle` at `0x18000ef99`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ef2d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ef2d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000ef85`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000ef85`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000ee68`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000ee68`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000efcb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000efcb`

## pseudocode

```c
__int64 __fastcall DhcpNdisHandlePnPEvent(
        __int64 a1,
        DWORD a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  unsigned int v6; // ebx
  unsigned int v8; // r12d
  __int64 v9; // rax
  int v10; // eax
  unsigned int v11; // ecx
  __int64 v12; // rax
  unsigned __int16 *v13; // rdi
  int v14; // eax
  unsigned int v15; // ecx
  unsigned int v16; // eax
  DWORD v17; // r15d
  _OWORD *v18; // rax
  _QWORD *v19; // rbx
  DWORD LastError; // edi
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int64 v24; // rax
  HANDLE FileW; // rsi
  _OWORD v27[2]; // [rsp+48h] [rbp-31h] BYREF
  __int128 v28; // [rsp+68h] [rbp-11h]
  __int128 v29; // [rsp+78h] [rbp-1h]
  __int64 v30; // [rsp+88h] [rbp+Fh]
  DWORD BytesReturned; // [rsp+D0h] [rbp+57h] BYREF

  BytesReturned = a2;
  v6 = 72;
  memset_0(v27, 0, 0x48u);
  v8 = 0;
  BytesReturned = 0;
  if ( (BYTE2(xmmword_18001E1E0) & 8) != 0 )
    WPP_SF_(1043, 11, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids);
  *(_QWORD *)&v28 = 72;
  if ( a3 )
  {
    v9 = (unsigned int)*a3 + 74;
    if ( (unsigned int)v9 < 0x48 || (unsigned int)v9 < (unsigned int)*a3 + 2 )
      goto LABEL_8;
  }
  else
  {
    v9 = 74;
  }
  v6 = v9;
  *(_QWORD *)&v29 = v9;
LABEL_8:
  if ( a4 )
    v10 = *a4;
  else
    v10 = 0;
  v11 = v10 + 2;
  v12 = v10 + 2 + v6;
  if ( (unsigned int)v12 >= v6 && (unsigned int)v12 >= v11 )
  {
    v6 = v12;
    v30 = v12;
  }
  v13 = a5;
  if ( a5 )
    v14 = *a5;
  else
    v14 = 0;
  v15 = v14 + 2;
  v16 = v14 + 2 + v6;
  if ( v16 >= v6 && v16 >= v15 )
    v6 = v16;
  *((_QWORD *)&v27[0] + 1) = v6 + (-v6 & 7);
  v17 = DWORD2(v27[0]) + 1;
  v18 = LocalAlloc(0x40u, (unsigned int)(DWORD2(v27[0]) + 1));
  v19 = v18;
  if ( v18 )
  {
    v21 = v27[1];
    *v18 = v27[0];
    v22 = v28;
    v18[1] = v21;
    v23 = v29;
    v18[2] = v22;
    *(_QWORD *)&v22 = v30;
    v18[3] = v23;
    *((_QWORD *)v18 + 8) = v22;
    *(_DWORD *)v18 = 2;
    *((_DWORD *)v18 + 1) = 3;
    DhcpNdispUnicodeStringToVar(v18, a3, (char *)v18 + 24);
    DhcpNdispUnicodeStringToVar(v19, a4, v19 + 5);
    DhcpNdispUnicodeStringToVar(v19, v13, v19 + 7);
    v24 = v19[1];
    *((_DWORD *)v19 + 4) = 0;
    *((_BYTE *)v19 + v24) = 0;
    if ( (BYTE2(xmmword_18001E1E0) & 8) != 0 )
      WPP_SF_(1043, 12, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids);
    FileW = CreateFileW(L"\\\\.\\NDIS", 0, 0, 0, 3u, 0, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
    }
    else
    {
      if ( (BYTE2(xmmword_18001E1E0) & 8) != 0 )
        WPP_SF_(1043, 13, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids);
      v8 = DeviceIoControl(FileW, 0x170008u, v19, v17, 0, 0, &BytesReturned, 0);
      LastError = GetLastError();
      CloseHandle(FileW);
      if ( (BYTE2(xmmword_18001E1E0) & 8) != 0 )
        WPP_SF_(1043, 14, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids);
    }
    LocalFree(v19);
  }
  else
  {
    LastError = 8;
  }
  SetLastError(LastError);
  if ( (BYTE2(xmmword_18001E1E0) & 8) != 0 )
    WPP_SF_(1043, 15, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids);
  return v8;
}

```

## disassembly

```asm
0x18000ed88  mov     rax, rsp
0x18000ed8b  mov     [rax+8], rbx
0x18000ed8f  mov     [rax+18h], rsi
0x18000ed93  mov     [rax+10h], edx
0x18000ed96  push    rbp
0x18000ed97  push    rdi
0x18000ed98  push    r12
0x18000ed9a  push    r14
0x18000ed9c  push    r15
0x18000ed9e  lea     rbp, [rax-47h]
0x18000eda2  sub     rsp, 90h
0x18000eda9  mov     r14, r8
0x18000edac  lea     rcx, [rbp+3Fh+var_70]; void *
0x18000edb0  mov     ebx, 48h ; 'H'
0x18000edb5  xor     edx, edx; Val
0x18000edb7  mov     r8d, ebx; Size
0x18000edba  mov     rsi, r9
0x18000edbd  call    memset_0
0x18000edc2  xor     r12d, r12d
0x18000edc5  mov     [rbp+3Fh+BytesReturned], r12d
0x18000edc9  test    byte ptr cs:xmmword_18001E1E0+2, 8
0x18000edd0  jz      short loc_18000EDE6
0x18000edd2  lea     edx, [rbx-3Dh]
0x18000edd5  mov     ecx, 413h
0x18000edda  lea     r8, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids
0x18000ede1  call    WPP_SF_
0x18000ede6  mov     qword ptr [rbp+3Fh+var_50], rbx
0x18000edea  test    r14, r14
0x18000eded  jnz     short loc_18000EDF6
0x18000edef  mov     eax, 4Ah ; 'J'
0x18000edf4  jmp     short loc_18000EE08
0x18000edf6  movzx   ecx, word ptr [r14]
0x18000edfa  add     ecx, 2
0x18000edfd  lea     eax, [rcx+48h]
0x18000ee00  cmp     eax, ebx
0x18000ee02  jb      short loc_18000EE0E
0x18000ee04  cmp     eax, ecx
0x18000ee06  jb      short loc_18000EE0E
0x18000ee08  mov     ebx, eax
0x18000ee0a  mov     qword ptr [rbp+3Fh+var_40], rax
0x18000ee0e  test    rsi, rsi
0x18000ee11  jnz     short loc_18000EE17
0x18000ee13  xor     eax, eax
0x18000ee15  jmp     short loc_18000EE1A
0x18000ee17  movzx   eax, word ptr [rsi]
0x18000ee1a  lea     ecx, [rax+2]
0x18000ee1d  lea     eax, [rcx+rbx]
0x18000ee20  cmp     eax, ebx
0x18000ee22  jb      short loc_18000EE2E
0x18000ee24  cmp     eax, ecx
0x18000ee26  jb      short loc_18000EE2E
0x18000ee28  mov     ebx, eax
0x18000ee2a  mov     [rbp+3Fh+var_30], rax
0x18000ee2e  mov     rdi, [rbp+3Fh+arg_20]
0x18000ee32  test    rdi, rdi
0x18000ee35  jnz     short loc_18000EE3B
0x18000ee37  xor     eax, eax
0x18000ee39  jmp     short loc_18000EE3E
0x18000ee3b  movzx   eax, word ptr [rdi]
0x18000ee3e  lea     ecx, [rax+2]
0x18000ee41  lea     eax, [rcx+rbx]
0x18000ee44  cmp     eax, ebx
0x18000ee46  jb      short loc_18000EE4D
0x18000ee48  cmp     eax, ecx
0x18000ee4a  cmovnb  ebx, eax
0x18000ee4d  mov     ecx, ebx
0x18000ee4f  neg     ecx
0x18000ee51  and     ecx, 7
0x18000ee54  add     ecx, ebx
0x18000ee56  mov     eax, ecx
0x18000ee58  mov     qword ptr [rbp+3Fh+var_70+8], rax
0x18000ee5c  lea     r15d, [rcx+1]
0x18000ee60  mov     ecx, 40h ; '@'; uFlags
0x18000ee65  mov     edx, r15d; uBytes
0x18000ee68  call    cs:__imp_LocalAlloc
0x18000ee6e  mov     rbx, rax
0x18000ee71  test    rax, rax
0x18000ee74  jnz     short loc_18000EE7E
0x18000ee76  lea     edi, [rax+8]
0x18000ee79  jmp     loc_18000EFD1
0x18000ee7e  movaps  xmm0, [rbp+3Fh+var_70]
0x18000ee82  lea     r8, [rax+18h]
0x18000ee86  movaps  xmm1, [rbp+3Fh+var_60]
0x18000ee8a  mov     rdx, r14
0x18000ee8d  movups  xmmword ptr [rax], xmm0
0x18000ee90  mov     rcx, rbx
0x18000ee93  movaps  xmm0, [rbp+3Fh+var_50]
0x18000ee97  movups  xmmword ptr [rax+10h], xmm1
0x18000ee9b  movaps  xmm1, [rbp+3Fh+var_40]
0x18000ee9f  movups  xmmword ptr [rax+20h], xmm0
0x18000eea3  movsd   xmm0, [rbp+3Fh+var_30]
0x18000eea8  movups  xmmword ptr [rax+30h], xmm1
0x18000eeac  movsd   qword ptr [rax+40h], xmm0
0x18000eeb1  mov     dword ptr [rax], 2
0x18000eeb7  mov     dword ptr [rax+4], 3
0x18000eebe  call    DhcpNdispUnicodeStringToVar
0x18000eec3  lea     r8, [rbx+28h]
0x18000eec7  mov     rdx, rsi
0x18000eeca  mov     rcx, rbx
0x18000eecd  call    DhcpNdispUnicodeStringToVar
0x18000eed2  lea     r8, [rbx+38h]
0x18000eed6  mov     rdx, rdi
0x18000eed9  mov     rcx, rbx
0x18000eedc  call    DhcpNdispUnicodeStringToVar
0x18000eee1  mov     rax, [rbx+8]
0x18000eee5  mov     [rbx+10h], r12d
0x18000eee9  mov     [rbx+rax], r12b
0x18000eeed  test    byte ptr cs:xmmword_18001E1E0+2, 8
0x18000eef4  jz      short loc_18000EF0C
0x18000eef6  mov     edx, 0Ch
0x18000eefb  lea     r8, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids
0x18000ef02  mov     ecx, 413h
0x18000ef07  call    WPP_SF_
0x18000ef0c  mov     [rsp+0B0h+hTemplateFile], r12; hTemplateFile
0x18000ef11  lea     rcx, FileName; "\\\\.\\NDIS"
0x18000ef18  mov     [rsp+0B0h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x18000ef1d  xor     r9d, r9d; lpSecurityAttributes
0x18000ef20  xor     r8d, r8d; dwShareMode
0x18000ef23  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x18000ef2b  xor     edx, edx; dwDesiredAccess
0x18000ef2d  call    cs:__imp_CreateFileW
0x18000ef33  mov     rsi, rax
0x18000ef36  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ef3a  jz      loc_18000EFC0
0x18000ef40  test    byte ptr cs:xmmword_18001E1E0+2, 8
0x18000ef47  jz      short loc_18000EF5F
0x18000ef49  mov     edx, 0Dh
0x18000ef4e  lea     r8, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids
0x18000ef55  mov     ecx, 413h
0x18000ef5a  call    WPP_SF_
0x18000ef5f  mov     [rsp+0B0h+lpOverlapped], r12; lpOverlapped
0x18000ef64  lea     rax, [rbp+3Fh+BytesReturned]
0x18000ef68  mov     [rsp+0B0h+hTemplateFile], rax; lpBytesReturned
0x18000ef6d  mov     r9d, r15d; nInBufferSize
0x18000ef70  mov     [rsp+0B0h+dwFlagsAndAttributes], r12d; nOutBufferSize
0x18000ef75  mov     r8, rbx; lpInBuffer
0x18000ef78  mov     edx, 170008h; dwIoControlCode
0x18000ef7d  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r12; lpOutBuffer
0x18000ef82  mov     rcx, rsi; hDevice
0x18000ef85  call    cs:__imp_DeviceIoControl
0x18000ef8b  mov     r12d, eax
0x18000ef8e  call    cs:__imp_GetLastError
0x18000ef94  mov     rcx, rsi; hObject
0x18000ef97  mov     edi, eax
0x18000ef99  call    cs:__imp_CloseHandle
0x18000ef9f  test    byte ptr cs:xmmword_18001E1E0+2, 8
0x18000efa6  jz      short loc_18000EFC8
0x18000efa8  mov     edx, 0Eh
0x18000efad  lea     r8, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids
0x18000efb4  mov     ecx, 413h
0x18000efb9  call    WPP_SF_
0x18000efbe  jmp     short loc_18000EFC8
0x18000efc0  call    cs:__imp_GetLastError
0x18000efc6  mov     edi, eax
0x18000efc8  mov     rcx, rbx; hMem
0x18000efcb  call    cs:__imp_LocalFree
0x18000efd1  mov     ecx, edi; dwErrCode
0x18000efd3  call    cs:__imp_SetLastError
0x18000efd9  test    byte ptr cs:xmmword_18001E1E0+2, 8
0x18000efe0  jz      short loc_18000EFF8
0x18000efe2  mov     edx, 0Fh
0x18000efe7  lea     r8, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids
0x18000efee  mov     ecx, 413h
0x18000eff3  call    WPP_SF_
0x18000eff8  lea     r11, [rsp+0B0h+var_20]
0x18000f000  mov     eax, r12d
0x18000f003  mov     rbx, [r11+30h]
0x18000f007  mov     rsi, [r11+40h]
0x18000f00b  mov     rsp, r11
0x18000f00e  pop     r15
0x18000f010  pop     r14
0x18000f012  pop     r12
0x18000f014  pop     rdi
0x18000f015  pop     rbp
0x18000f016  retn
```
