# I_ScPnPPulseReader

- ea: `0x18001a19c`
- end: `0x18001a2c2`
- name: `I_ScPnPPulseReader`
- size: `294`
- prototype: `__int64 __fastcall(HANDLE *lpInBuffer)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001a5d0`

## callees

- `0x180004600`
- `0x180018b58`
- `0x180018bb4`
- `0x180018d78`
- `0x18001a19c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a234`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a234`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001a222`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001a222`

## pseudocode

```c
__int64 __fastcall I_ScPnPPulseReader(HANDLE *lpInBuffer)
{
  DWORD v1; // ebx
  STRSAFE_LPSTR v3; // rcx
  DWORD LastError; // eax
  int v5; // r9d
  DWORD BytesReturned; // [rsp+50h] [rbp+8h] BYREF

  v1 = 0;
  BytesReturned = 0;
  WppTraceIndent(lpInBuffer, 0);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids, WPP_pszIndent);
  }
  if ( !DeviceIoControl(lpInBuffer[24], 0x310FA8u, lpInBuffer, 0xC0u, 0, 0, &BytesReturned, 0) )
  {
    WppTraceIndent(v3, 2);
    LastError = GetLastError();
    v1 = LastError;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        72,
        (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
        v5,
        LastError);
    }
  }
  WppTraceIndent(v3, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      73,
      (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
      WPP_pszIndent,
      v1);
  }
  return v1;
}

```

## disassembly

```asm
0x18001a19c  mov     [rsp+arg_8], rbx
0x18001a1a1  mov     [rsp+arg_10], rdi
0x18001a1a6  push    r15
0x18001a1a8  sub     rsp, 40h
0x18001a1ac  xor     ebx, ebx
0x18001a1ae  xor     edx, edx
0x18001a1b0  mov     [rsp+48h+BytesReturned], ebx
0x18001a1b4  mov     rdi, rcx
0x18001a1b7  call    WppTraceIndent
0x18001a1bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a1c3  lea     r15, WPP_GLOBAL_Control
0x18001a1ca  cmp     rcx, r15
0x18001a1cd  jz      short loc_18001A1F5
0x18001a1cf  test    byte ptr [rcx+1Ch], 2
0x18001a1d3  jz      short loc_18001A1F5
0x18001a1d5  cmp     byte ptr [rcx+19h], 5
0x18001a1d9  jb      short loc_18001A1F5
0x18001a1db  mov     r9, cs:WPP_pszIndent
0x18001a1e2  lea     edx, [rbx+47h]
0x18001a1e5  mov     rcx, [rcx+10h]
0x18001a1e9  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x18001a1f0  call    WPP_SF_s
0x18001a1f5  mov     rcx, [rdi+0C0h]; hDevice
0x18001a1fc  lea     rax, [rsp+48h+BytesReturned]
0x18001a201  mov     [rsp+48h+lpOverlapped], rbx; lpOverlapped
0x18001a206  mov     r9d, 0C0h; nInBufferSize
0x18001a20c  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x18001a211  mov     r8, rdi; lpInBuffer
0x18001a214  mov     [rsp+48h+nOutBufferSize], ebx; nOutBufferSize
0x18001a218  mov     edx, 310FA8h; dwIoControlCode
0x18001a21d  mov     [rsp+48h+lpOutBuffer], rbx; lpOutBuffer
0x18001a222  call    cs:__imp_DeviceIoControl
0x18001a228  test    eax, eax
0x18001a22a  jnz     short loc_18001A26D
0x18001a22c  lea     edx, [rax+2]
0x18001a22f  call    WppTraceIndent
0x18001a234  call    cs:__imp_GetLastError
0x18001a23a  mov     ebx, eax
0x18001a23c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a243  cmp     rcx, r15
0x18001a246  jz      short loc_18001A26D
0x18001a248  test    byte ptr [rcx+1Ch], 1
0x18001a24c  jz      short loc_18001A26D
0x18001a24e  cmp     byte ptr [rcx+19h], 2
0x18001a252  jb      short loc_18001A26D
0x18001a254  mov     rcx, [rcx+10h]
0x18001a258  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x18001a25f  mov     edx, 48h ; 'H'
0x18001a264  mov     dword ptr [rsp+48h+lpOutBuffer], eax
0x18001a268  call    WPP_SF_sd
0x18001a26d  mov     edx, 1
0x18001a272  call    WppTraceIndent
0x18001a277  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a27e  cmp     rcx, r15
0x18001a281  jz      short loc_18001A2AF
0x18001a283  test    byte ptr [rcx+1Ch], 2
0x18001a287  jz      short loc_18001A2AF
0x18001a289  cmp     byte ptr [rcx+19h], 5
0x18001a28d  jb      short loc_18001A2AF
0x18001a28f  mov     r9, cs:WPP_pszIndent
0x18001a296  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x18001a29d  mov     rcx, [rcx+10h]
0x18001a2a1  mov     edx, 49h ; 'I'
0x18001a2a6  mov     dword ptr [rsp+48h+lpOutBuffer], ebx
0x18001a2aa  call    WPP_SF_sD
0x18001a2af  mov     rdi, [rsp+48h+arg_10]
0x18001a2b4  mov     eax, ebx
0x18001a2b6  mov     rbx, [rsp+48h+arg_8]
0x18001a2bb  add     rsp, 40h
0x18001a2bf  pop     r15
0x18001a2c1  retn
```
