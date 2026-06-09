# TSPI_lineGetID

- ea: `0x180005db0`
- end: `0x180006130`
- name: `TSPI_lineGetID`
- size: `896`
- prototype: `LONG __stdcall(HDRVLINE hdLine, DWORD dwAddressID, HDRVCALL hdCall, DWORD dwSelect, LPVARSTRING lpDeviceID, LPCWSTR lpszDeviceClass, HANDLE hTargetProcess)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation`

## callees

- `0x180002494`
- `0x18000298c`
- `0x180003294`
- `0x1800037a8`
- `0x180003890`
- `0x180003af0`
- `0x180004184`
- `0x180005db0`
- `0x180007df8`
- `0x180008085`
- `0x180008091`
- `0x18000809d`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x1800060bd`
- `KERNEL32!WideCharToMultiByte` at `0x1800060bd`
- `KERNEL32!lstrlenW` at `0x180005df5`
- `KERNEL32!lstrlenW` at `0x180005df5`

## string_xrefs

- `0x180005e08`: `lineGetID(%d): line(%p), call(%p), addressID(%x), select(%x)`

## pseudocode

```c
LONG __stdcall TSPI_lineGetID(
        HDRVLINE hdLine,
        DWORD dwAddressID,
        HDRVCALL hdCall,
        DWORD dwSelect,
        LPVARSTRING lpDeviceID,
        LPCWSTR lpszDeviceClass,
        HANDLE hTargetProcess)
{
  __int64 v8; // r13
  __int64 v9; // r14
  int v13; // eax
  int v14; // r12d
  LONG result; // eax
  int v16; // ecx
  int *v17; // rdx
  LPVARSTRING v18; // r12
  __int64 v19; // rdx
  LONG v20; // edi
  __int64 v21; // rdx
  LPVARSTRING v22; // rcx
  LPVARSTRING v23; // rbx
  __int64 v24; // rdx
  char *v25; // rdi
  __int64 NdisTapiHandle; // rax
  __int64 v27; // rdx
  bool v28; // zf
  const WCHAR *v29; // r8
  unsigned int v30; // ecx
  __int64 v31; // rdx
  int v32; // [rsp+78h] [rbp-11h]
  void *lpInBuffer; // [rsp+80h] [rbp-9h] BYREF
  __int64 v34; // [rsp+88h] [rbp-1h] BYREF
  __int64 v35[7]; // [rsp+90h] [rbp+7h] BYREF
  LONG v38; // [rsp+F0h] [rbp+67h] BYREF

  v8 = 0;
  v9 = 0;
  v34 = 0;
  v35[0] = 0;
  lpInBuffer = 0;
  v13 = lstrlenW(lpszDeviceClass);
  ++dword_18000E29C;
  v14 = v13;
  v32 = v13;
  TspLog(
    8,
    "lineGetID(%d): line(%p), call(%p), addressID(%x), select(%x)",
    dword_18000E29C,
    hdLine,
    hdCall,
    dwAddressID,
    dwSelect);
  if ( dwSelect - 1 > 1 )
  {
    if ( dwSelect != 4 )
      return -2147024809;
LABEL_7:
    result = GetCallObjWithReadLock(hdCall, v35);
    if ( result )
      return result;
    v9 = v35[0];
    goto LABEL_9;
  }
  result = GetLineObjWithReadLock(hdLine, &v34);
  if ( result )
    return result;
  v8 = v34;
  if ( !v34 )
    return result;
  if ( dwSelect == 4 )
    goto LABEL_7;
  if ( dwSelect != 1 || wcscmp_0(lpszDeviceClass, L"LineGuid") )
  {
LABEL_9:
    v16 = v14 + 1;
    v17 = (int *)(v9 + 4);
    if ( dwSelect != 4 )
      v17 = (int *)(v8 + 4);
    v18 = lpDeviceID;
    v38 = PrepareSyncRequest(117637395, *v17, v16 + lpDeviceID->dwTotalSize + 48, &lpInBuffer);
    v20 = v38;
    if ( v38 )
    {
      if ( v9 )
        ReleaseObjReadLock(hdCall, v19);
      if ( v8 )
        ReleaseObjReadLock(hdLine, v19);
      return v20;
    }
    else
    {
      v25 = (char *)lpInBuffer + 16;
      if ( dwSelect - 1 <= 1 )
        *((_QWORD *)lpInBuffer + 3) = *(_QWORD *)(v8 + 16);
      *((_DWORD *)v25 + 4) = dwAddressID;
      if ( dwSelect != 4
        || (NdisTapiHandle = GetNdisTapiHandle(v9, &v38), v28 = v38 == 0, *((_QWORD *)v25 + 3) = NdisTapiHandle, v28) )
      {
        v29 = lpszDeviceClass;
        *((_DWORD *)v25 + 9) = v32 + 1;
        *((_DWORD *)v25 + 8) = dwSelect;
        v30 = v18->dwTotalSize + 48;
        *((_DWORD *)v25 + 10) = v30;
        *((_DWORD *)v25 + 11) = v18->dwTotalSize;
        *((_DWORD *)v25 + 13) = 24;
        *((_DWORD *)v25 + 12) = 24;
        *(_QWORD *)(v25 + 60) = 0;
        *((_DWORD *)v25 + 14) = 0;
        WideCharToMultiByte(0, 0, v29, -1, &v25[v30], v32 + 1, 0, 0);
        v38 = SyncDriverRequest(0x8FFF23C8, lpInBuffer);
        if ( !v38 )
          memcpy_0(v18, v25 + 44, *((unsigned int *)v25 + 13));
        FreeRequest(lpInBuffer);
        if ( v9 )
          ReleaseObjReadLock(hdCall, v31);
        if ( v8 )
          ReleaseObjReadLock(hdLine, v31);
        return v38;
      }
      else
      {
        if ( v8 )
          ReleaseObjReadLock(hdLine, v27);
        return v38;
      }
    }
  }
  v22 = lpDeviceID;
  lpDeviceID->dwNeededSize = 48;
  if ( v22->dwTotalSize >= 0x30 )
  {
    v22->dwUsedSize = 48;
    v23 = v22 + 1;
    v22->dwStringFormat = 1;
    v22->dwStringSize = 24;
    v22->dwStringOffset = 24;
    memmove_0(&v22[1], (const void *)(v8 + 32), 0x10u);
    v23->dwStringSize = *(_DWORD *)(v8 + 48);
    LOBYTE(v23->dwStringOffset) = 0;
    TspLog(4, "lineGetID: obj(%p)", hdLine);
    TspLog(
      4,
      "Guid %4.4x-%2.2x-%2.2x-%1.1x%1.1x-%1.1x%1.1x%1.1x%1.1x%1.1x%1.1x",
      *(_DWORD *)(v8 + 32),
      *(unsigned __int16 *)(v8 + 36),
      *(unsigned __int16 *)(v8 + 38),
      *(unsigned __int8 *)(v8 + 40),
      *(unsigned __int8 *)(v8 + 41),
      *(unsigned __int8 *)(v8 + 42),
      *(unsigned __int8 *)(v8 + 43),
      *(unsigned __int8 *)(v8 + 44),
      *(unsigned __int8 *)(v8 + 45),
      *(unsigned __int8 *)(v8 + 46),
      *(unsigned __int8 *)(v8 + 47));
    TspLog(4, "MediaType: %d", *(_DWORD *)(v8 + 48));
    ReleaseObjReadLock(hdLine, v24);
    return 0;
  }
  else
  {
    if ( v8 )
      ReleaseObjReadLock(hdLine, v21);
    return -2147483571;
  }
}

```

## disassembly

```asm
0x180005db0  mov     rax, rsp
0x180005db3  mov     [rax+18h], rbx
0x180005db7  mov     [rax+10h], edx
0x180005dba  mov     [rax+8], rcx
0x180005dbe  push    rbp
0x180005dbf  push    rsi
0x180005dc0  push    rdi
0x180005dc1  push    r12
0x180005dc3  push    r13
0x180005dc5  push    r14
0x180005dc7  push    r15
0x180005dc9  lea     rbp, [rax-47h]
0x180005dcd  sub     rsp, 90h
0x180005dd4  mov     rsi, rcx
0x180005dd7  xor     r13d, r13d
0x180005dda  mov     rcx, [rbp+3Fh+lpszDeviceClass]; lpString
0x180005dde  xor     r14d, r14d
0x180005de1  mov     [rbp+3Fh+var_40], r13
0x180005de5  mov     ebx, r9d
0x180005de8  mov     [rbp+3Fh+var_38], r14
0x180005dec  mov     r15, r8
0x180005def  mov     [rbp+3Fh+lpInBuffer], r13
0x180005df3  mov     edi, edx
0x180005df5  call    cs:__imp_lstrlenW
0x180005dfc  nop     dword ptr [rax+rax+00h]
0x180005e01  mov     r8d, cs:dword_18000E29C
0x180005e08  lea     rdx, aLinegetidDLine; "lineGetID(%d): line(%p), call(%p), addr"...
0x180005e0f  inc     r8d
0x180005e12  mov     dword ptr [rsp+0C0h+lpDefaultChar], ebx
0x180005e16  mov     [rsp+0C0h+cbMultiByte], edi
0x180005e1a  lea     ecx, [r13+8]
0x180005e1e  mov     r9, rsi
0x180005e21  mov     cs:dword_18000E29C, r8d
0x180005e28  mov     r12d, eax
0x180005e2b  mov     [rbp+3Fh+var_50], eax
0x180005e2e  mov     [rsp+0C0h+lpMultiByteStr], r15
0x180005e33  call    TspLog
0x180005e38  lea     ecx, [rbx-1]
0x180005e3b  cmp     ecx, 1
0x180005e3e  jbe     short loc_180005E4F
0x180005e40  cmp     ebx, 4
0x180005e43  jz      short loc_180005E75
0x180005e45  mov     eax, 80070057h
0x180005e4a  jmp     loc_180006114
0x180005e4f  lea     rdx, [rbp+3Fh+var_40]
0x180005e53  mov     rcx, rsi
0x180005e56  call    GetLineObjWithReadLock
0x180005e5b  test    eax, eax
0x180005e5d  jnz     loc_180006114
0x180005e63  mov     r13, [rbp+3Fh+var_40]
0x180005e67  test    r13, r13
0x180005e6a  jz      loc_180006114
0x180005e70  cmp     ebx, 4
0x180005e73  jnz     short loc_180005EEC
0x180005e75  lea     rdx, [rbp+3Fh+var_38]
0x180005e79  mov     rcx, r15
0x180005e7c  call    GetCallObjWithReadLock
0x180005e81  test    eax, eax
0x180005e83  jnz     loc_180006114
0x180005e89  mov     r14, [rbp+3Fh+var_38]
0x180005e8d  lea     ecx, [r12+1]
0x180005e92  lea     rdx, [r14+4]
0x180005e96  cmp     ebx, 4
0x180005e99  jz      short loc_180005E9F
0x180005e9b  lea     rdx, [r13+4]
0x180005e9f  mov     r12, [rbp+3Fh+lpDeviceID]
0x180005ea3  lea     r9, [rbp+3Fh+lpInBuffer]
0x180005ea7  mov     edx, [rdx]
0x180005ea9  mov     r8d, [r12]
0x180005ead  add     r8d, 30h ; '0'
0x180005eb1  add     r8d, ecx
0x180005eb4  mov     ecx, 7030113h
0x180005eb9  call    PrepareSyncRequest
0x180005ebe  mov     [rbp+3Fh+arg_18], eax
0x180005ec1  mov     edi, eax
0x180005ec3  test    eax, eax
0x180005ec5  jz      loc_18000600A
0x180005ecb  test    r14, r14
0x180005ece  jz      short loc_180005ED8
0x180005ed0  mov     rcx, r15
0x180005ed3  call    ReleaseObjReadLock
0x180005ed8  test    r13, r13
0x180005edb  jz      short loc_180005EE5
0x180005edd  mov     rcx, rsi
0x180005ee0  call    ReleaseObjReadLock
0x180005ee5  mov     eax, edi
0x180005ee7  jmp     loc_180006114
0x180005eec  cmp     ebx, 1
0x180005eef  jnz     short loc_180005E8D
0x180005ef1  mov     rcx, [rbp+3Fh+lpszDeviceClass]; String1
0x180005ef5  lea     rdx, aLineguid; "LineGuid"
0x180005efc  call    wcscmp_0
0x180005f01  test    eax, eax
0x180005f03  jnz     short loc_180005E8D
0x180005f05  mov     rcx, [rbp+3Fh+lpDeviceID]
0x180005f09  lea     eax, [rbx+2Fh]
0x180005f0c  mov     [rcx+4], eax
0x180005f0f  cmp     [rcx], eax
0x180005f11  jnb     short loc_180005F2A
0x180005f13  test    r13, r13
0x180005f16  jz      short loc_180005F20
0x180005f18  mov     rcx, rsi
0x180005f1b  call    ReleaseObjReadLock
0x180005f20  mov     eax, 8000004Dh
0x180005f25  jmp     loc_180006114
0x180005f2a  mov     [rcx+8], eax
0x180005f2d  lea     rbx, [rcx+18h]
0x180005f31  mov     eax, ebx
0x180005f33  mov     dword ptr [rcx+0Ch], 1
0x180005f3a  sub     eax, ecx
0x180005f3c  mov     dword ptr [rcx+10h], 18h
0x180005f43  mov     [rcx+14h], eax
0x180005f46  lea     rdx, [r13+20h]; Src
0x180005f4a  mov     rcx, rbx; void *
0x180005f4d  mov     r8d, 10h; Size
0x180005f53  call    memmove_0
0x180005f58  mov     eax, [r13+30h]
0x180005f5c  lea     rdx, aLinegetidObjP; "lineGetID: obj(%p)"
0x180005f63  mov     [rbx+10h], eax
0x180005f66  mov     r8, rsi
0x180005f69  mov     ecx, 4
0x180005f6e  mov     [rbx+14h], r14b
0x180005f72  call    TspLog
0x180005f77  movzx   edx, byte ptr [r13+2Eh]
0x180005f7c  movzx   ebx, byte ptr [r13+2Bh]
0x180005f81  movzx   eax, byte ptr [r13+2Fh]
0x180005f86  movzx   r10d, byte ptr [r13+2Dh]
0x180005f8b  movzx   r11d, byte ptr [r13+2Ch]
0x180005f90  movzx   edi, byte ptr [r13+2Ah]
0x180005f95  movzx   esi, byte ptr [r13+29h]
0x180005f9a  movzx   r14d, byte ptr [r13+28h]
0x180005f9f  movzx   r15d, word ptr [r13+26h]
0x180005fa4  movzx   r9d, word ptr [r13+24h]
0x180005fa9  mov     r8d, [r13+20h]
0x180005fad  mov     [rsp+60h], eax
0x180005fb1  mov     [rsp+0C0h+var_68], edx
0x180005fb5  lea     rdx, aGuid44x22x22x1; "Guid %4.4x-%2.2x-%2.2x-%1.1x%1.1x-%1.1x"...
0x180005fbc  mov     [rsp+0C0h+var_70], r10d
0x180005fc1  mov     [rsp+0C0h+var_78], r11d
0x180005fc6  mov     [rsp+0C0h+var_80], ebx
0x180005fca  mov     ebx, 4
0x180005fcf  mov     dword ptr [rsp+0C0h+lpUsedDefaultChar], edi
0x180005fd3  mov     ecx, ebx
0x180005fd5  mov     dword ptr [rsp+0C0h+lpDefaultChar], esi
0x180005fd9  mov     [rsp+0C0h+cbMultiByte], r14d
0x180005fde  mov     dword ptr [rsp+0C0h+lpMultiByteStr], r15d
0x180005fe3  call    TspLog
0x180005fe8  mov     r8d, [r13+30h]
0x180005fec  lea     rdx, aMediatypeD; "MediaType: %d"
0x180005ff3  mov     ecx, ebx
0x180005ff5  call    TspLog
0x180005ffa  mov     rcx, [rbp+3Fh+arg_0]
0x180005ffe  call    ReleaseObjReadLock
0x180006003  xor     eax, eax
0x180006005  jmp     loc_180006114
0x18000600a  mov     rdi, [rbp+3Fh+lpInBuffer]
0x18000600e  lea     eax, [rbx-1]
0x180006011  add     rdi, 10h
0x180006015  cmp     eax, 1
0x180006018  ja      short loc_180006022
0x18000601a  mov     rax, [r13+10h]
0x18000601e  mov     [rdi+8], rax
0x180006022  mov     eax, [rbp+3Fh+arg_8]
0x180006025  mov     [rdi+10h], eax
0x180006028  cmp     ebx, 4
0x18000602b  jnz     short loc_180006058
0x18000602d  lea     rdx, [rbp+3Fh+arg_18]
0x180006031  mov     rcx, r14
0x180006034  call    GetNdisTapiHandle
0x180006039  cmp     [rbp+3Fh+arg_18], 0
0x18000603d  mov     [rdi+18h], rax
0x180006041  jz      short loc_180006058
0x180006043  test    r13, r13
0x180006046  jz      short loc_180006050
0x180006048  mov     rcx, rsi
0x18000604b  call    ReleaseObjReadLock
0x180006050  mov     eax, [rbp+3Fh+arg_18]
0x180006053  jmp     loc_180006114
0x180006058  mov     edx, [rbp+3Fh+var_50]
0x18000605b  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000605f  mov     r8, [rbp+3Fh+lpszDeviceClass]; lpWideCharStr
0x180006063  inc     edx
0x180006065  mov     [rdi+24h], edx
0x180006068  mov     [rdi+20h], ebx
0x18000606b  mov     ecx, [r12]
0x18000606f  add     ecx, 30h ; '0'
0x180006072  mov     [rsp+0C0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000607b  mov     [rdi+28h], ecx
0x18000607e  mov     eax, [r12]
0x180006082  mov     [rdi+2Ch], eax
0x180006085  mov     eax, ecx
0x180006087  xor     ecx, ecx; CodePage
0x180006089  mov     [rsp+0C0h+lpDefaultChar], 0; lpDefaultChar
0x180006092  add     rax, rdi
0x180006095  mov     [rsp+0C0h+cbMultiByte], edx; cbMultiByte
0x180006099  xor     edx, edx; dwFlags
0x18000609b  mov     [rsp+0C0h+lpMultiByteStr], rax; lpMultiByteStr
0x1800060a0  mov     dword ptr [rdi+34h], 18h
0x1800060a7  mov     dword ptr [rdi+30h], 18h
0x1800060ae  mov     qword ptr [rdi+3Ch], 0
0x1800060b6  mov     dword ptr [rdi+38h], 0
0x1800060bd  call    cs:__imp_WideCharToMultiByte
0x1800060c4  nop     dword ptr [rax+rax+00h]
0x1800060c9  mov     rdx, [rbp+3Fh+lpInBuffer]; lpInBuffer
0x1800060cd  mov     ecx, 8FFF23C8h; dwIoControlCode
0x1800060d2  call    SyncDriverRequest
0x1800060d7  mov     [rbp+3Fh+arg_18], eax
0x1800060da  test    eax, eax
0x1800060dc  jnz     short loc_1800060EE
0x1800060de  mov     r8d, [rdi+34h]; Size
0x1800060e2  lea     rdx, [rdi+2Ch]; Src
0x1800060e6  mov     rcx, r12; void *
0x1800060e9  call    memcpy_0
0x1800060ee  mov     rcx, [rbp+3Fh+lpInBuffer]; void *
0x1800060f2  call    FreeRequest
0x1800060f7  test    r14, r14
0x1800060fa  jz      short loc_180006104
0x1800060fc  mov     rcx, r15
0x1800060ff  call    ReleaseObjReadLock
0x180006104  test    r13, r13
0x180006107  jz      short loc_180006111
0x180006109  mov     rcx, rsi
0x18000610c  call    ReleaseObjReadLock
0x180006111  mov     eax, [rbp+3Fh+arg_18]
0x180006114  mov     rbx, [rsp+0C0h+arg_10]
0x18000611c  add     rsp, 90h
0x180006123  pop     r15
0x180006125  pop     r14
0x180006127  pop     r13
0x180006129  pop     r12
0x18000612b  pop     rdi
0x18000612c  pop     rsi
0x18000612d  pop     rbp
0x18000612e  retn
```
