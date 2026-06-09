# TSPI_lineGetAddressID

- ea: `0x1800051d0`
- end: `0x18000530e`
- name: `TSPI_lineGetAddressID`
- size: `318`
- prototype: `LONG __stdcall(HDRVLINE hdLine, LPDWORD lpdwAddressID, DWORD dwAddressMode, LPCWSTR lpsAddress, DWORD dwSize)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x180002494`
- `0x18000298c`
- `0x1800037a8`
- `0x180003af0`
- `0x180004184`
- `0x1800051d0`
- `0x180007df8`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x1800052b7`
- `KERNEL32!WideCharToMultiByte` at `0x1800052b7`

## string_xrefs

- `0x180005216`: `lineGetAddressID(%d): line(%p), addressMode(%x)`
- `0x1800052da`: `lineGetAddressID: addressID(%x)`

## pseudocode

```c
LONG __stdcall TSPI_lineGetAddressID(
        HDRVLINE hdLine,
        LPDWORD lpdwAddressID,
        DWORD dwAddressMode,
        LPCWSTR lpsAddress,
        DWORD dwSize)
{
  LONG result; // eax
  __int64 v10; // rbp
  DWORD cbMultiByte; // esi
  LONG v12; // ebx
  CHAR *v13; // rbx
  LONG v14; // esi
  DWORD v15; // r8d
  __int64 v16; // [rsp+40h] [rbp-48h] BYREF
  void *lpInBuffer; // [rsp+48h] [rbp-40h] BYREF

  v16 = 0;
  lpInBuffer = 0;
  TspLog(8, "lineGetAddressID(%d): line(%p), addressMode(%x)", ++dword_18000E280, hdLine, dwAddressMode);
  result = GetLineObjWithReadLock(hdLine, &v16);
  if ( !result )
  {
    v10 = v16;
    cbMultiByte = dwSize >> 1;
    v12 = PrepareSyncRequest(117637387, *(_DWORD *)(v16 + 4), (dwSize >> 1) + 31, &lpInBuffer);
    if ( v12 )
    {
      ReleaseObjReadLock(hdLine);
      return v12;
    }
    else
    {
      v13 = (CHAR *)lpInBuffer;
      *((_QWORD *)lpInBuffer + 3) = *(_QWORD *)(v10 + 16);
      *((_DWORD *)v13 + 9) = dwAddressMode;
      *((_DWORD *)v13 + 10) = cbMultiByte;
      WideCharToMultiByte(0, 0, lpsAddress, dwSize, v13 + 44, cbMultiByte, 0, 0);
      v14 = SyncDriverRequest(0x8FFF23C8, v13);
      if ( !v14 )
      {
        v15 = *((_DWORD *)v13 + 8);
        *lpdwAddressID = v15;
        TspLog(4, "lineGetAddressID: addressID(%x)", v15);
      }
      FreeRequest(v13);
      ReleaseObjReadLock(hdLine);
      return v14;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800051d0  push    rbx
0x1800051d2  push    rbp
0x1800051d3  push    rsi
0x1800051d4  push    rdi
0x1800051d5  push    r12
0x1800051d7  push    r14
0x1800051d9  push    r15
0x1800051db  sub     rsp, 50h
0x1800051df  mov     r15d, r8d
0x1800051e2  mov     [rsp+88h+var_48], 0
0x1800051eb  mov     r8d, cs:dword_18000E280
0x1800051f2  mov     r12, r9
0x1800051f5  inc     r8d
0x1800051f8  mov     [rsp+88h+lpInBuffer], 0
0x180005201  mov     r14, rdx
0x180005204  mov     cs:dword_18000E280, r8d
0x18000520b  mov     rdi, rcx
0x18000520e  mov     dword ptr [rsp+88h+lpMultiByteStr], r15d
0x180005213  mov     r9, rcx
0x180005216  lea     rdx, aLinegetaddress; "lineGetAddressID(%d): line(%p), address"...
0x18000521d  mov     ecx, 8
0x180005222  call    TspLog
0x180005227  lea     rdx, [rsp+88h+var_48]
0x18000522c  mov     rcx, rdi
0x18000522f  call    GetLineObjWithReadLock
0x180005234  test    eax, eax
0x180005236  jnz     loc_1800052FE
0x18000523c  mov     esi, [rsp+88h+dwSize]
0x180005243  lea     r9, [rsp+88h+lpInBuffer]
0x180005248  mov     rbp, [rsp+88h+var_48]
0x18000524d  mov     ecx, 703010Bh
0x180005252  shr     esi, 1
0x180005254  mov     edx, [rbp+4]
0x180005257  lea     r8d, [rsi+1Fh]
0x18000525b  call    PrepareSyncRequest
0x180005260  mov     ebx, eax
0x180005262  test    eax, eax
0x180005264  jz      short loc_180005275
0x180005266  mov     rcx, rdi
0x180005269  call    ReleaseObjReadLock
0x18000526e  mov     eax, ebx
0x180005270  jmp     loc_1800052FE
0x180005275  mov     rax, [rbp+10h]
0x180005279  mov     r8, r12; lpWideCharStr
0x18000527c  mov     rbx, [rsp+88h+lpInBuffer]
0x180005281  xor     edx, edx; dwFlags
0x180005283  mov     r9d, [rsp+88h+dwSize]; cchWideChar
0x18000528b  xor     ecx, ecx; CodePage
0x18000528d  mov     [rsp+88h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180005296  mov     [rsp+88h+lpDefaultChar], 0; lpDefaultChar
0x18000529f  mov     [rbx+18h], rax
0x1800052a3  lea     rax, [rbx+2Ch]
0x1800052a7  mov     [rsp+88h+cbMultiByte], esi; cbMultiByte
0x1800052ab  mov     [rsp+88h+lpMultiByteStr], rax; lpMultiByteStr
0x1800052b0  mov     [rbx+24h], r15d
0x1800052b4  mov     [rbx+28h], esi
0x1800052b7  call    cs:__imp_WideCharToMultiByte
0x1800052be  nop     dword ptr [rax+rax+00h]
0x1800052c3  mov     rdx, rbx; lpInBuffer
0x1800052c6  mov     ecx, 8FFF23C8h; dwIoControlCode
0x1800052cb  call    SyncDriverRequest
0x1800052d0  mov     esi, eax
0x1800052d2  test    eax, eax
0x1800052d4  jnz     short loc_1800052EC
0x1800052d6  mov     r8d, [rbx+20h]
0x1800052da  lea     rdx, aLinegetaddress_0; "lineGetAddressID: addressID(%x)"
0x1800052e1  lea     ecx, [rax+4]
0x1800052e4  mov     [r14], r8d
0x1800052e7  call    TspLog
0x1800052ec  mov     rcx, rbx; void *
0x1800052ef  call    FreeRequest
0x1800052f4  mov     rcx, rdi
0x1800052f7  call    ReleaseObjReadLock
0x1800052fc  mov     eax, esi
0x1800052fe  add     rsp, 50h
0x180005302  pop     r15
0x180005304  pop     r14
0x180005306  pop     r12
0x180005308  pop     rdi
0x180005309  pop     rsi
0x18000530a  pop     rbp
0x18000530b  pop     rbx
0x18000530c  retn
```
