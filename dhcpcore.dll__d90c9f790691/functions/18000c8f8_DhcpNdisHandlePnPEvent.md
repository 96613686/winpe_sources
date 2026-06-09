# DhcpNdisHandlePnPEvent

- ea: `0x18000c8f8`
- end: `0x18000cc6a`
- name: `DhcpNdisHandlePnPEvent`
- size: `882`
- prototype: `__int64 __fastcall(__int64, DWORD, const void **, const void **, const void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000c7dc`

## callees

- `0x18000c8f8`
- `0x18001d826`
- `0x180047e3c`
- `0x18004d1e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc5d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cba9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cba9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cb79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cb79`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000cba1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000cba1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000c9ca`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000c9ca`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000cb0d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000cb0d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000cb65`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000cb65`

## pseudocode

```c
__int64 __fastcall DhcpNdisHandlePnPEvent(__int64 a1, DWORD a2, const void **a3, const void **a4, const void **a5)
{
  unsigned int v6; // ebx
  unsigned int v8; // r13d
  __int64 v9; // rax
  int v10; // eax
  unsigned int v11; // ecx
  __int64 v12; // rax
  const void **v13; // rdi
  int v14; // eax
  unsigned int v15; // ecx
  unsigned int v16; // eax
  DWORD v17; // r12d
  _OWORD *v18; // rax
  _WORD *v19; // rbx
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  char *v23; // r15
  size_t v24; // rax
  char *v25; // rsi
  size_t v26; // rax
  char *v27; // rsi
  size_t v28; // rax
  __int64 v29; // rax
  HANDLE FileW; // rsi
  DWORD LastError; // edi
  _OWORD v33[2]; // [rsp+40h] [rbp-51h] BYREF
  __int128 v34; // [rsp+60h] [rbp-31h]
  __int128 v35; // [rsp+70h] [rbp-21h]
  __int64 v36; // [rsp+80h] [rbp-11h]
  DWORD BytesReturned; // [rsp+E8h] [rbp+57h] BYREF

  BytesReturned = a2;
  v6 = 72;
  memset_0(v33, 0, 0x48u);
  v8 = 0;
  BytesReturned = 0;
  if ( (BYTE2(xmmword_1800616A0) & 8) != 0 )
    WPP_SF_(1043, 11, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids);
  *(_QWORD *)&v34 = 72;
  if ( !a3 )
  {
    v9 = 74;
LABEL_6:
    v6 = v9;
    *(_QWORD *)&v35 = v9;
    goto LABEL_7;
  }
  v9 = (unsigned int)*(unsigned __int16 *)a3 + 74;
  if ( (unsigned int)v9 >= 0x48 && (unsigned int)v9 >= (unsigned int)*(unsigned __int16 *)a3 + 2 )
    goto LABEL_6;
LABEL_7:
  v10 = 0;
  if ( a4 )
    v10 = *(unsigned __int16 *)a4;
  v11 = v10 + 2;
  v12 = v10 + 2 + v6;
  if ( (unsigned int)v12 >= v6 && (unsigned int)v12 >= v11 )
  {
    v6 = v12;
    v36 = v12;
  }
  v13 = a5;
  v14 = 0;
  if ( a5 )
    v14 = *(unsigned __int16 *)a5;
  v15 = v14 + 2;
  v16 = v14 + 2 + v6;
  if ( v16 >= v6 && v16 >= v15 )
    v6 = v16;
  *((_QWORD *)&v33[0] + 1) = v6 + (-v6 & 7);
  v17 = DWORD2(v33[0]) + 1;
  v18 = LocalAlloc(0x40u, (unsigned int)(DWORD2(v33[0]) + 1));
  v19 = v18;
  if ( v18 )
  {
    v20 = v33[1];
    *v18 = v33[0];
    v21 = v34;
    v18[1] = v20;
    v22 = v35;
    v18[2] = v21;
    *(_QWORD *)&v21 = v36;
    v18[3] = v22;
    *((_QWORD *)v18 + 8) = v21;
    *(_DWORD *)v18 = 2;
    *((_DWORD *)v18 + 1) = 3;
    v23 = (char *)v18 + *((_QWORD *)v18 + 4);
    if ( a3 && (v24 = *(unsigned __int16 *)a3, (_WORD)v24) )
    {
      v19[12] = v24;
      memcpy_0(v23, a3[1], v24);
    }
    else
    {
      v19[12] = 0;
    }
    *(_WORD *)&v23[v19[12] & 0xFFFE] = 0;
    v19[13] = v19[12] + 2;
    v25 = (char *)v19 + *((_QWORD *)v19 + 6);
    if ( a4 && (v26 = *(unsigned __int16 *)a4, (_WORD)v26) )
    {
      v19[20] = v26;
      memcpy_0(v25, a4[1], v26);
    }
    else
    {
      v19[20] = 0;
    }
    *(_WORD *)&v25[v19[20] & 0xFFFE] = 0;
    v19[21] = v19[20] + 2;
    v27 = (char *)v19 + *((_QWORD *)v19 + 8);
    if ( v13 && (v28 = *(unsigned __int16 *)v13, (_WORD)v28) )
    {
      v19[28] = v28;
      memcpy_0(v27, v13[1], v28);
    }
    else
    {
      v19[28] = 0;
    }
    *(_WORD *)&v27[v19[28] & 0xFFFE] = 0;
    v19[29] = v19[28] + 2;
    v29 = *((_QWORD *)v19 + 1);
    *((_DWORD *)v19 + 4) = 0;
    *((_BYTE *)v19 + v29) = 0;
    if ( (BYTE2(xmmword_1800616A0) & 8) != 0 )
      WPP_SF_(1043, 12, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids);
    FileW = CreateFileW(L"\\\\.\\NDIS", 0, 0, 0, 3u, 0, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
    }
    else
    {
      if ( (BYTE2(xmmword_1800616A0) & 8) != 0 )
        WPP_SF_(1043, 13, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids);
      v8 = DeviceIoControl(FileW, 0x170008u, v19, v17, 0, 0, &BytesReturned, 0);
      LastError = GetLastError();
      CloseHandle(FileW);
      if ( (BYTE2(xmmword_1800616A0) & 8) != 0 )
        WPP_SF_(1043, 14, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids);
    }
    LocalFree(v19);
  }
  else
  {
    LastError = 8;
  }
  SetLastError(LastError);
  if ( (BYTE2(xmmword_1800616A0) & 8) != 0 )
    WPP_SF_(1043, 15, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids);
  return v8;
}

```

## disassembly

```asm
0x18000c8f8  mov     [rsp-8+BytesReturned], edx
0x18000c8fc  push    rbp
0x18000c8fd  push    rbx
0x18000c8fe  push    rsi
0x18000c8ff  push    rdi
0x18000c900  push    r12
0x18000c902  push    r13
0x18000c904  push    r14
0x18000c906  push    r15
0x18000c908  lea     rbp, [rsp-7]
0x18000c90d  sub     rsp, 98h
0x18000c914  mov     rsi, r8
0x18000c917  lea     rcx, [rbp+3Fh+var_90]; void *
0x18000c91b  mov     ebx, 48h ; 'H'
0x18000c920  xor     edx, edx; Val
0x18000c922  mov     r8d, ebx; Size
0x18000c925  mov     r14, r9
0x18000c928  call    memset_0
0x18000c92d  xor     r15d, r15d
0x18000c930  mov     r13d, r15d
0x18000c933  mov     [rbp+3Fh+BytesReturned], r15d
0x18000c937  test    byte ptr cs:xmmword_1800616A0+2, 8
0x18000c93e  jz      short loc_18000C954
0x18000c940  lea     edx, [rbx-3Dh]
0x18000c943  mov     ecx, 413h
0x18000c948  lea     r8, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids
0x18000c94f  call    WPP_SF_
0x18000c954  mov     qword ptr [rbp+3Fh+var_70], rbx
0x18000c958  test    rsi, rsi
0x18000c95b  jz      loc_18000CC04
0x18000c961  movzx   ecx, word ptr [rsi]
0x18000c964  add     ecx, 2
0x18000c967  lea     eax, [rcx+48h]
0x18000c96a  cmp     eax, ebx
0x18000c96c  jb      short loc_18000C978
0x18000c96e  cmp     eax, ecx
0x18000c970  jb      short loc_18000C978
0x18000c972  mov     ebx, eax
0x18000c974  mov     qword ptr [rbp+3Fh+var_60], rax
0x18000c978  mov     eax, r15d
0x18000c97b  test    r14, r14
0x18000c97e  jz      short loc_18000C984
0x18000c980  movzx   eax, word ptr [r14]
0x18000c984  lea     ecx, [rax+2]
0x18000c987  lea     eax, [rcx+rbx]
0x18000c98a  cmp     eax, ebx
0x18000c98c  jnb     loc_18000CBCF
0x18000c992  mov     rdi, [rbp+3Fh+arg_20]
0x18000c996  mov     eax, r15d
0x18000c999  test    rdi, rdi
0x18000c99c  jz      short loc_18000C9A1
0x18000c99e  movzx   eax, word ptr [rdi]
0x18000c9a1  lea     ecx, [rax+2]
0x18000c9a4  lea     eax, [rcx+rbx]
0x18000c9a7  cmp     eax, ebx
0x18000c9a9  jnb     loc_18000CBE2
0x18000c9af  mov     ecx, ebx
0x18000c9b1  neg     ecx
0x18000c9b3  and     ecx, 7
0x18000c9b6  add     ecx, ebx
0x18000c9b8  mov     eax, ecx
0x18000c9ba  mov     qword ptr [rbp+3Fh+var_90+8], rax
0x18000c9be  lea     r12d, [rcx+1]
0x18000c9c2  mov     ecx, 40h ; '@'; uFlags
0x18000c9c7  mov     edx, r12d; uBytes
0x18000c9ca  call    cs:__imp_LocalAlloc
0x18000c9d0  mov     rbx, rax
0x18000c9d3  test    rax, rax
0x18000c9d6  jz      loc_18000CC0E
0x18000c9dc  movaps  xmm0, [rbp+3Fh+var_90]
0x18000c9e0  xor     ecx, ecx
0x18000c9e2  movaps  xmm1, [rbp+3Fh+var_80]
0x18000c9e6  movups  xmmword ptr [rax], xmm0
0x18000c9e9  movaps  xmm0, [rbp+3Fh+var_70]
0x18000c9ed  movups  xmmword ptr [rax+10h], xmm1
0x18000c9f1  movaps  xmm1, [rbp+3Fh+var_60]
0x18000c9f5  movups  xmmword ptr [rax+20h], xmm0
0x18000c9f9  movsd   xmm0, [rbp+3Fh+var_50]
0x18000c9fe  movups  xmmword ptr [rax+30h], xmm1
0x18000ca02  movsd   qword ptr [rax+40h], xmm0
0x18000ca07  mov     dword ptr [rax], 2
0x18000ca0d  mov     dword ptr [rax+4], 3
0x18000ca14  mov     r15, [rax+20h]
0x18000ca18  add     r15, rax
0x18000ca1b  test    rsi, rsi
0x18000ca1e  jz      short loc_18000CA2C
0x18000ca20  movzx   eax, word ptr [rsi]
0x18000ca23  test    ax, ax
0x18000ca26  jnz     loc_18000CC15
0x18000ca2c  mov     [rbx+18h], cx
0x18000ca30  movzx   ecx, word ptr [rbx+18h]
0x18000ca34  xor     eax, eax
0x18000ca36  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000ca3a  mov     [rcx+r15], ax
0x18000ca3f  xor     r15d, r15d
0x18000ca42  movzx   eax, word ptr [rbx+18h]
0x18000ca46  add     ax, 2
0x18000ca4a  mov     [rbx+1Ah], ax
0x18000ca4e  mov     rsi, [rbx+30h]
0x18000ca52  add     rsi, rbx
0x18000ca55  test    r14, r14
0x18000ca58  jz      short loc_18000CA67
0x18000ca5a  movzx   eax, word ptr [r14]
0x18000ca5e  test    ax, ax
0x18000ca61  jnz     loc_18000CC2D
0x18000ca67  mov     [rbx+28h], r15w
0x18000ca6c  movzx   ecx, word ptr [rbx+28h]
0x18000ca70  mov     r14d, 2
0x18000ca76  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000ca7a  mov     [rcx+rsi], r15w
0x18000ca7f  movzx   eax, word ptr [rbx+28h]
0x18000ca83  add     ax, r14w
0x18000ca87  mov     [rbx+2Ah], ax
0x18000ca8b  mov     rsi, [rbx+40h]
0x18000ca8f  add     rsi, rbx
0x18000ca92  test    rdi, rdi
0x18000ca95  jz      short loc_18000CAA3
0x18000ca97  movzx   eax, word ptr [rdi]
0x18000ca9a  test    ax, ax
0x18000ca9d  jnz     loc_18000CC45
0x18000caa3  mov     [rbx+38h], r15w
0x18000caa8  movzx   ecx, word ptr [rbx+38h]
0x18000caac  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000cab0  mov     [rcx+rsi], r15w
0x18000cab5  movzx   eax, word ptr [rbx+38h]
0x18000cab9  add     ax, r14w
0x18000cabd  mov     [rbx+3Ah], ax
0x18000cac1  mov     rax, [rbx+8]
0x18000cac5  mov     [rbx+10h], r15d
0x18000cac9  mov     [rbx+rax], r15b
0x18000cacd  test    byte ptr cs:xmmword_1800616A0+2, 8
0x18000cad4  jz      short loc_18000CAEC
0x18000cad6  mov     edx, 0Ch
0x18000cadb  lea     r8, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids
0x18000cae2  mov     ecx, 413h
0x18000cae7  call    WPP_SF_
0x18000caec  mov     [rsp+0D0h+hTemplateFile], r15; hTemplateFile
0x18000caf1  lea     rcx, FileName; "\\\\.\\NDIS"
0x18000caf8  mov     [rsp+0D0h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x18000cafd  xor     r9d, r9d; lpSecurityAttributes
0x18000cb00  xor     r8d, r8d; dwShareMode
0x18000cb03  mov     [rsp+0D0h+dwCreationDisposition], 3; dwCreationDisposition
0x18000cb0b  xor     edx, edx; dwDesiredAccess
0x18000cb0d  call    cs:__imp_CreateFileW
0x18000cb13  mov     rsi, rax
0x18000cb16  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000cb1a  jz      loc_18000CC5D
0x18000cb20  test    byte ptr cs:xmmword_1800616A0+2, 8
0x18000cb27  jz      short loc_18000CB3F
0x18000cb29  mov     edx, 0Dh
0x18000cb2e  lea     r8, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids
0x18000cb35  mov     ecx, 413h
0x18000cb3a  call    WPP_SF_
0x18000cb3f  mov     [rsp+0D0h+lpOverlapped], r15; lpOverlapped
0x18000cb44  lea     rax, [rbp+3Fh+BytesReturned]
0x18000cb48  mov     [rsp+0D0h+hTemplateFile], rax; lpBytesReturned
0x18000cb4d  mov     r9d, r12d; nInBufferSize
0x18000cb50  mov     [rsp+0D0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x18000cb55  mov     r8, rbx; lpInBuffer
0x18000cb58  mov     edx, 170008h; dwIoControlCode
0x18000cb5d  mov     qword ptr [rsp+0D0h+dwCreationDisposition], r15; lpOutBuffer
0x18000cb62  mov     rcx, rsi; hDevice
0x18000cb65  call    cs:__imp_DeviceIoControl
0x18000cb6b  mov     r13d, eax
0x18000cb6e  call    cs:__imp_GetLastError
0x18000cb74  mov     rcx, rsi; hObject
0x18000cb77  mov     edi, eax
0x18000cb79  call    cs:__imp_CloseHandle
0x18000cb7f  test    byte ptr cs:xmmword_1800616A0+2, 8
0x18000cb86  jz      short loc_18000CB9E
0x18000cb88  mov     edx, 0Eh
0x18000cb8d  lea     r8, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids
0x18000cb94  mov     ecx, 413h
0x18000cb99  call    WPP_SF_
0x18000cb9e  mov     rcx, rbx; hMem
0x18000cba1  call    cs:__imp_LocalFree
0x18000cba7  mov     ecx, edi; dwErrCode
0x18000cba9  call    cs:__imp_SetLastError
0x18000cbaf  test    byte ptr cs:xmmword_1800616A0+2, 8
0x18000cbb6  jnz     short loc_18000CBEC
0x18000cbb8  mov     eax, r13d
0x18000cbbb  add     rsp, 98h
0x18000cbc2  pop     r15
0x18000cbc4  pop     r14
0x18000cbc6  pop     r13
0x18000cbc8  pop     r12
0x18000cbca  pop     rdi
0x18000cbcb  pop     rsi
0x18000cbcc  pop     rbx
0x18000cbcd  pop     rbp
0x18000cbce  retn
0x18000cbcf  cmp     eax, ecx
0x18000cbd1  jb      loc_18000C992
0x18000cbd7  mov     ebx, eax
0x18000cbd9  mov     [rbp+3Fh+var_50], rax
0x18000cbdd  jmp     loc_18000C992
0x18000cbe2  cmp     eax, ecx
0x18000cbe4  cmovnb  ebx, eax
0x18000cbe7  jmp     loc_18000C9AF
0x18000cbec  mov     edx, 0Fh
0x18000cbf1  lea     r8, WPP_73943e8cee903d0019b1148a57b13c50_Traceguids
0x18000cbf8  mov     ecx, 413h
0x18000cbfd  call    WPP_SF_
0x18000cc02  jmp     short loc_18000CBB8
0x18000cc04  mov     eax, 4Ah ; 'J'
0x18000cc09  jmp     loc_18000C972
0x18000cc0e  mov     edi, 8
0x18000cc13  jmp     short loc_18000CBA7
0x18000cc15  mov     [rbx+18h], ax
0x18000cc19  mov     r8, rax; Size
0x18000cc1c  mov     rdx, [rsi+8]; Src
0x18000cc20  mov     rcx, r15; void *
0x18000cc23  call    memcpy_0
0x18000cc28  jmp     loc_18000CA30
0x18000cc2d  mov     [rbx+28h], ax
0x18000cc31  mov     r8, rax; Size
0x18000cc34  mov     rdx, [r14+8]; Src
0x18000cc38  mov     rcx, rsi; void *
0x18000cc3b  call    memcpy_0
0x18000cc40  jmp     loc_18000CA6C
0x18000cc45  mov     [rbx+38h], ax
0x18000cc49  mov     r8, rax; Size
0x18000cc4c  mov     rdx, [rdi+8]; Src
0x18000cc50  mov     rcx, rsi; void *
0x18000cc53  call    memcpy_0
0x18000cc58  jmp     loc_18000CAA8
0x18000cc5d  call    cs:__imp_GetLastError
0x18000cc63  mov     edi, eax
0x18000cc65  jmp     loc_18000CB9E
```
