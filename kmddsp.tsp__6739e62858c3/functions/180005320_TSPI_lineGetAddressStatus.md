# TSPI_lineGetAddressStatus

- ea: `0x180005320`
- end: `0x180005436`
- name: `TSPI_lineGetAddressStatus`
- size: `278`
- prototype: `LONG __stdcall(HDRVLINE hdLine, DWORD dwAddressID, LPLINEADDRESSSTATUS lpAddressStatus)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x180002494`
- `0x18000298c`
- `0x1800037a8`
- `0x180003af0`
- `0x180004184`
- `0x180005320`
- `0x180007df8`
- `0x180008091`

## string_xrefs

- `0x180005362`: `lineGetAddressStatus(%d): line(%p), addressID(%x)`

## pseudocode

```c
LONG __stdcall TSPI_lineGetAddressStatus(HDRVLINE hdLine, DWORD dwAddressID, LPLINEADDRESSSTATUS lpAddressStatus)
{
  LONG result; // eax
  __int64 v7; // rsi
  __int64 v8; // rdx
  LONG v9; // ebx
  unsigned int *v10; // rbx
  _DWORD *v11; // rdx
  LONG v12; // ebp
  __int64 v13; // rdx
  void *lpInBuffer; // [rsp+30h] [rbp-28h] BYREF
  __int64 v15; // [rsp+78h] [rbp+20h] BYREF

  v15 = 0;
  ++dword_18000E290;
  lpInBuffer = 0;
  TspLog(8, "lineGetAddressStatus(%d): line(%p), addressID(%x)", dword_18000E290, hdLine, dwAddressID);
  result = GetLineObjWithReadLock(hdLine, &v15);
  if ( !result )
  {
    v7 = v15;
    v9 = PrepareSyncRequest(117637388, *(_DWORD *)(v15 + 4), lpAddressStatus->dwTotalSize + 24, &lpInBuffer);
    if ( v9 )
    {
      ReleaseObjReadLock(hdLine, v8);
      return v9;
    }
    else
    {
      v10 = (unsigned int *)lpInBuffer;
      v11 = lpInBuffer;
      *((_QWORD *)lpInBuffer + 3) = *(_QWORD *)(v7 + 16);
      v11[8] = dwAddressID;
      v11[9] = lpAddressStatus->dwTotalSize;
      v11[11] = 64;
      v11[10] = 64;
      *((_OWORD *)v11 + 3) = 0;
      *((_OWORD *)v11 + 4) = 0;
      *((_OWORD *)v11 + 5) = 0;
      v11[24] = 0;
      v12 = SyncDriverRequest(0x8FFF23C8, v11);
      if ( !v12 )
        memcpy_0(lpAddressStatus, v10 + 9, v10[11]);
      FreeRequest(v10);
      ReleaseObjReadLock(hdLine, v13);
      return v12;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005320  mov     rax, rsp
0x180005323  mov     [rax+8], rbx
0x180005327  mov     [rax+10h], rbp
0x18000532b  push    rsi
0x18000532c  push    rdi
0x18000532d  push    r14
0x18000532f  sub     rsp, 40h
0x180005333  mov     r14, r8
0x180005336  mov     [rax-38h], edx
0x180005339  mov     r8d, cs:dword_18000E290
0x180005340  mov     ebp, edx
0x180005342  inc     r8d
0x180005345  mov     qword ptr [rax+20h], 0
0x18000534d  mov     rdi, rcx
0x180005350  mov     cs:dword_18000E290, r8d
0x180005357  mov     r9, rcx
0x18000535a  mov     qword ptr [rax-28h], 0
0x180005362  lea     rdx, aLinegetaddress_1; "lineGetAddressStatus(%d): line(%p), add"...
0x180005369  mov     ecx, 8
0x18000536e  call    TspLog
0x180005373  lea     rdx, [rsp+58h+arg_18]
0x180005378  mov     rcx, rdi
0x18000537b  call    GetLineObjWithReadLock
0x180005380  test    eax, eax
0x180005382  jnz     loc_180005422
0x180005388  mov     r8d, [r14]
0x18000538b  lea     r9, [rsp+58h+lpInBuffer]
0x180005390  mov     rsi, [rsp+58h+arg_18]
0x180005395  add     r8d, 18h
0x180005399  mov     ecx, 703010Ch
0x18000539e  mov     edx, [rsi+4]
0x1800053a1  call    PrepareSyncRequest
0x1800053a6  mov     ebx, eax
0x1800053a8  test    eax, eax
0x1800053aa  jz      short loc_1800053B8
0x1800053ac  mov     rcx, rdi
0x1800053af  call    ReleaseObjReadLock
0x1800053b4  mov     eax, ebx
0x1800053b6  jmp     short loc_180005422
0x1800053b8  mov     rax, [rsi+10h]
0x1800053bc  xorps   xmm0, xmm0
0x1800053bf  mov     rbx, [rsp+58h+lpInBuffer]
0x1800053c4  mov     ecx, 8FFF23C8h; dwIoControlCode
0x1800053c9  mov     rdx, rbx; lpInBuffer
0x1800053cc  mov     [rbx+18h], rax
0x1800053d0  mov     [rbx+20h], ebp
0x1800053d3  mov     eax, [r14]
0x1800053d6  mov     [rbx+24h], eax
0x1800053d9  mov     eax, 40h ; '@'
0x1800053de  mov     [rbx+2Ch], eax
0x1800053e1  mov     [rbx+28h], eax
0x1800053e4  xor     eax, eax
0x1800053e6  movups  xmmword ptr [rbx+30h], xmm0
0x1800053ea  movups  xmmword ptr [rbx+40h], xmm0
0x1800053ee  movups  xmmword ptr [rbx+50h], xmm0
0x1800053f2  mov     [rbx+60h], eax
0x1800053f5  call    SyncDriverRequest
0x1800053fa  mov     ebp, eax
0x1800053fc  test    eax, eax
0x1800053fe  jnz     short loc_180005410
0x180005400  mov     r8d, [rbx+2Ch]; Size
0x180005404  lea     rdx, [rbx+24h]; Src
0x180005408  mov     rcx, r14; void *
0x18000540b  call    memcpy_0
0x180005410  mov     rcx, rbx; void *
0x180005413  call    FreeRequest
0x180005418  mov     rcx, rdi
0x18000541b  call    ReleaseObjReadLock
0x180005420  mov     eax, ebp
0x180005422  mov     rbx, [rsp+58h+arg_0]
0x180005427  mov     rbp, [rsp+58h+arg_8]
0x18000542c  add     rsp, 40h
0x180005430  pop     r14
0x180005432  pop     rdi
0x180005433  pop     rsi
0x180005434  retn
```
