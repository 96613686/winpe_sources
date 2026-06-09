# TSPI_lineGetExtensionID

- ea: `0x180005d00`
- end: `0x180005da4`
- name: `TSPI_lineGetExtensionID`
- size: `164`
- prototype: `LONG __stdcall(DWORD dwDeviceID, DWORD dwTSPIVersion, LPLINEEXTENSIONID lpExtensionID)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18000298c`
- `0x180003af0`
- `0x180004184`
- `0x180005d00`
- `0x180007df8`

## string_xrefs

- `0x180005d1d`: `lineGetExtensionID(%d): deviceID(%x), TSPIV(%x)`

## pseudocode

```c
LONG __stdcall TSPI_lineGetExtensionID(DWORD dwDeviceID, DWORD dwTSPIVersion, LPLINEEXTENSIONID lpExtensionID)
{
  LONG result; // eax
  char *v6; // rbx
  _DWORD *v7; // rdx
  void *lpInBuffer; // [rsp+58h] [rbp+20h] BYREF

  lpInBuffer = 0;
  TspLog(8, "lineGetExtensionID(%d): deviceID(%x), TSPIV(%x)", ++dword_18000E284, dwDeviceID, dwTSPIVersion);
  result = PrepareSyncRequest(117637394, dwDeviceID, 0x18u, &lpInBuffer);
  if ( !result )
  {
    v6 = (char *)lpInBuffer;
    v7 = lpInBuffer;
    *((_DWORD *)lpInBuffer + 5) = dwDeviceID;
    if ( (unsigned int)SyncDriverRequest(0x8FFF23C8, v7) )
      *lpExtensionID = 0;
    else
      *lpExtensionID = *(LPLINEEXTENSIONID)(v6 + 24);
    FreeRequest(v6);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180005d00  mov     rax, rsp
0x180005d03  mov     [rax+8], rbx
0x180005d07  mov     [rax+10h], rsi
0x180005d0b  push    rdi
0x180005d0c  sub     rsp, 30h
0x180005d10  mov     rdi, r8
0x180005d13  mov     [rax-18h], edx
0x180005d16  mov     r8d, cs:dword_18000E284
0x180005d1d  lea     rdx, aLinegetextensi; "lineGetExtensionID(%d): deviceID(%x), T"...
0x180005d24  inc     r8d
0x180005d27  mov     qword ptr [rax+20h], 0
0x180005d2f  mov     esi, ecx
0x180005d31  mov     cs:dword_18000E284, r8d
0x180005d38  mov     r9d, ecx
0x180005d3b  mov     ecx, 8
0x180005d40  call    TspLog
0x180005d45  lea     r9, [rsp+38h+lpInBuffer]
0x180005d4a  mov     r8d, 18h
0x180005d50  mov     edx, esi
0x180005d52  mov     ecx, 7030112h
0x180005d57  call    PrepareSyncRequest
0x180005d5c  test    eax, eax
0x180005d5e  jnz     short loc_180005D93
0x180005d60  mov     rbx, [rsp+38h+lpInBuffer]
0x180005d65  mov     ecx, 8FFF23C8h; dwIoControlCode
0x180005d6a  mov     rdx, rbx; lpInBuffer
0x180005d6d  mov     [rbx+14h], esi
0x180005d70  call    SyncDriverRequest
0x180005d75  test    eax, eax
0x180005d77  jnz     short loc_180005D83
0x180005d79  movups  xmm0, xmmword ptr [rbx+18h]
0x180005d7d  movdqu  xmmword ptr [rdi], xmm0
0x180005d81  jmp     short loc_180005D89
0x180005d83  xorps   xmm0, xmm0
0x180005d86  movups  xmmword ptr [rdi], xmm0
0x180005d89  mov     rcx, rbx; void *
0x180005d8c  call    FreeRequest
0x180005d91  xor     eax, eax
0x180005d93  mov     rbx, [rsp+38h+arg_0]
0x180005d98  mov     rsi, [rsp+38h+arg_8]
0x180005d9d  add     rsp, 30h
0x180005da1  pop     rdi
0x180005da2  retn
```
