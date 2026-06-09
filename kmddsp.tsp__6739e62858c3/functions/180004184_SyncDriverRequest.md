# SyncDriverRequest

- ea: `0x180004184`
- end: `0x180004300`
- name: `SyncDriverRequest`
- size: `380`
- prototype: `__int64 __fastcall(DWORD dwIoControlCode, _DWORD *lpInBuffer)`
- caller_count: `23`
- callee_count: `3`
- tags: ``

## callers

- `0x180003488`
- `0x180003ba8`
- `0x180004520`
- `0x180004670`
- `0x180004880`
- `0x180004fe0`
- `0x1800051d0`
- `0x180005320`
- `0x180005440`
- `0x180005550`
- `0x1800058b0`
- `0x180005bc0`
- `0x180005d00`
- `0x180005db0`
- `0x180006140`
- `0x180006820`
- `0x180006a20`
- `0x180006e30`
- `0x1800070c0`
- `0x1800072e0`
- `0x1800073b0`
- `0x1800074c0`
- `0x1800075b0`

## callees

- `0x180004184`
- `0x180007d9c`
- `0x180007df8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180004295`
- `KERNEL32!GetLastError` at `0x180004295`
- `KERNEL32!DeviceIoControl` at `0x18000427a`
- `KERNEL32!DeviceIoControl` at `0x18000427a`

## pseudocode

```c
__int64 __fastcall SyncDriverRequest(DWORD dwIoControlCode, _DWORD *lpInBuffer)
{
  __int64 v2; // rax
  const char *v5; // rdx
  HANDLE v6; // rcx
  BOOL v7; // eax
  int v8; // ebx
  DWORD LastError; // eax
  DWORD nOutBufferSize[2]; // [rsp+28h] [rbp-20h]
  DWORD BytesReturned; // [rsp+58h] [rbp+10h] BYREF

  v2 = (unsigned int)(lpInBuffer[1] - 117637377);
  BytesReturned = 0;
  if ( dword_18000C720[v2] == 1 )
  {
    TspLog(
      4,
      "SyncDriverRequest: oid(%s), devID(%x), reqID(%x)",
      off_18000A000[(unsigned int)v2],
      lpInBuffer[2],
      lpInBuffer[4]);
  }
  else
  {
    switch ( dword_18000C720[v2] )
    {
      case 2:
        v5 = "SyncDriverRequest: oid(%s), devID(%x), reqID(%x), hdCall(%p)";
        *(_QWORD *)nOutBufferSize = *((_QWORD *)lpInBuffer + 3);
        break;
      case 3:
        v5 = "SyncDriverRequest: oid(%s), devID(%x), reqID(%x), hdLine(%p)";
        *(_QWORD *)nOutBufferSize = *((_QWORD *)lpInBuffer + 3);
        break;
      case 4:
        v5 = "SyncDriverRequest: oid(%s), devID(%x), reqID(%x), deviceID(%x)";
        nOutBufferSize[0] = lpInBuffer[5];
        break;
      default:
        goto LABEL_10;
    }
    TspLog(
      4,
      v5,
      off_18000A000[(unsigned int)v2],
      (unsigned int)lpInBuffer[2],
      lpInBuffer[4],
      *(_QWORD *)nOutBufferSize);
  }
LABEL_10:
  v6 = ghDriverSync;
  *(lpInBuffer - 4) = 1;
  v7 = DeviceIoControl(
         v6,
         dwIoControlCode,
         lpInBuffer,
         lpInBuffer[3] + 20,
         lpInBuffer,
         lpInBuffer[3] + 20,
         &BytesReturned,
         0);
  *(lpInBuffer - 4) = 0;
  if ( v7 )
  {
    if ( *lpInBuffer )
      TspLog(
        2,
        "SyncDriverRequest: (Oid %s) returns with NDIS status (%x)",
        off_18000A000[lpInBuffer[1] - 117637377],
        *lpInBuffer);
    return TranslateDriverResult((unsigned int)*lpInBuffer);
  }
  else
  {
    v8 = lpInBuffer[1];
    LastError = GetLastError();
    TspLog(1, "SyncDriverRequest: IoCtl(Oid %x) failed(%d)", v8, LastError);
    return 2147483720LL;
  }
}

```

## disassembly

```asm
0x180004184  mov     [rsp+arg_0], rbx
0x180004189  mov     [rsp+arg_10], rsi
0x18000418e  push    rdi
0x18000418f  sub     rsp, 40h
0x180004193  mov     eax, [rdx+4]
0x180004196  lea     rsi, cs:180000000h
0x18000419d  sub     eax, 7030101h
0x1800041a2  mov     [rsp+48h+BytesReturned], 0
0x1800041aa  mov     rbx, rdx
0x1800041ad  mov     r8d, eax
0x1800041b0  mov     edi, ecx
0x1800041b2  mov     edx, ds:rva dword_18000C720[rsi+rax*4]
0x1800041b9  sub     edx, 1
0x1800041bc  jz      short loc_18000421E
0x1800041be  sub     edx, 1
0x1800041c1  jz      short loc_18000420C
0x1800041c3  sub     edx, 1
0x1800041c6  jz      short loc_1800041FA
0x1800041c8  cmp     edx, 1
0x1800041cb  jnz     short loc_180004242
0x1800041cd  mov     eax, [rbx+14h]
0x1800041d0  lea     rdx, aSyncdriverrequ_4; "SyncDriverRequest: oid(%s), devID(%x), "...
0x1800041d7  mov     [rsp+48h+nOutBufferSize], eax
0x1800041db  mov     eax, [rbx+10h]
0x1800041de  mov     ecx, 4
0x1800041e3  mov     r9d, [rbx+8]
0x1800041e7  mov     r8, ds:rva off_18000A000[rsi+r8*8]; "Accept" ...
0x1800041ef  mov     dword ptr [rsp+48h+lpOutBuffer], eax
0x1800041f3  call    TspLog
0x1800041f8  jmp     short loc_180004242
0x1800041fa  mov     rax, [rbx+18h]
0x1800041fe  lea     rdx, aSyncdriverrequ; "SyncDriverRequest: oid(%s), devID(%x), "...
0x180004205  mov     qword ptr [rsp+48h+nOutBufferSize], rax
0x18000420a  jmp     short loc_1800041DB
0x18000420c  mov     rax, [rbx+18h]
0x180004210  lea     rdx, aSyncdriverrequ_3; "SyncDriverRequest: oid(%s), devID(%x), "...
0x180004217  mov     qword ptr [rsp+48h+nOutBufferSize], rax
0x18000421c  jmp     short loc_1800041DB
0x18000421e  mov     eax, [rbx+10h]
0x180004221  lea     rdx, aSyncdriverrequ_0; "SyncDriverRequest: oid(%s), devID(%x), "...
0x180004228  mov     r9d, [rbx+8]
0x18000422c  mov     ecx, 4
0x180004231  mov     r8, ds:rva off_18000A000[rsi+r8*8]; "Accept" ...
0x180004239  mov     dword ptr [rsp+48h+lpOutBuffer], eax
0x18000423d  call    TspLog
0x180004242  mov     rcx, cs:ghDriverSync; hDevice
0x180004249  lea     rax, [rsp+48h+BytesReturned]
0x18000424e  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x180004257  mov     r8, rbx; lpInBuffer
0x18000425a  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x18000425f  mov     edx, edi; dwIoControlCode
0x180004261  mov     dword ptr [rbx-10h], 1
0x180004268  mov     r9d, [rbx+0Ch]
0x18000426c  add     r9d, 14h; nInBufferSize
0x180004270  mov     [rsp+48h+nOutBufferSize], r9d; nOutBufferSize
0x180004275  mov     [rsp+48h+lpOutBuffer], rbx; lpOutBuffer
0x18000427a  call    cs:__imp_DeviceIoControl
0x180004281  nop     dword ptr [rax+rax+00h]
0x180004286  mov     dword ptr [rbx-10h], 0
0x18000428d  cmp     eax, 1
0x180004290  jz      short loc_1800042BF
0x180004292  mov     ebx, [rbx+4]
0x180004295  call    cs:__imp_GetLastError
0x18000429c  nop     dword ptr [rax+rax+00h]
0x1800042a1  mov     r8d, ebx
0x1800042a4  lea     rdx, aSyncdriverrequ_2; "SyncDriverRequest: IoCtl(Oid %x) failed"...
0x1800042ab  mov     r9d, eax
0x1800042ae  mov     ecx, 1
0x1800042b3  call    TspLog
0x1800042b8  mov     eax, 80000048h
0x1800042bd  jmp     short loc_1800042EF
0x1800042bf  mov     r9d, [rbx]
0x1800042c2  test    r9d, r9d
0x1800042c5  jz      short loc_1800042E8
0x1800042c7  mov     eax, [rbx+4]
0x1800042ca  lea     rdx, aSyncdriverrequ_1; "SyncDriverRequest: (Oid %s) returns wit"...
0x1800042d1  sub     eax, 7030101h
0x1800042d6  mov     ecx, 2
0x1800042db  mov     r8, ds:rva off_18000A000[rsi+rax*8]; "Accept" ...
0x1800042e3  call    TspLog
0x1800042e8  mov     ecx, [rbx]
0x1800042ea  call    TranslateDriverResult
0x1800042ef  mov     rbx, [rsp+48h+arg_0]
0x1800042f4  mov     rsi, [rsp+48h+arg_10]
0x1800042f9  add     rsp, 40h
0x1800042fd  pop     rdi
0x1800042fe  retn
```
