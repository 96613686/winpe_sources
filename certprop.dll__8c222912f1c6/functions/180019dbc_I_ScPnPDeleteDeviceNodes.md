# I_ScPnPDeleteDeviceNodes

- ea: `0x180019dbc`
- end: `0x180019e4a`
- name: `I_ScPnPDeleteDeviceNodes`
- size: `142`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180006a40`
- `0x180015398`

## callees

- `0x180004600`
- `0x180018d78`
- `0x180019dbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e02`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180019df0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180019df0`

## pseudocode

```c
__int64 __fastcall I_ScPnPDeleteDeviceNodes(__int64 a1)
{
  void *v1; // rcx
  DWORD LastError; // ebx
  __int64 v3; // rcx
  int v4; // r9d
  DWORD v6; // [rsp+50h] [rbp+8h] BYREF

  v1 = *(void **)(a1 + 192);
  LastError = 0;
  v6 = 0;
  if ( !DeviceIoControl(v1, 0x310FB0u, 0, 0, 0, 0, &v6, 0) )
  {
    WppTraceIndent(v3, 2);
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        53,
        (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
        v4,
        LastError);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180019dbc  mov     r11, rsp
0x180019dbf  push    rbx
0x180019dc0  sub     rsp, 40h
0x180019dc4  mov     rcx, [rcx+0C0h]; hDevice
0x180019dcb  lea     rax, [r11+8]
0x180019dcf  xor     ebx, ebx
0x180019dd1  xor     r9d, r9d; nInBufferSize
0x180019dd4  mov     [r11-10h], rbx
0x180019dd8  xor     r8d, r8d; lpInBuffer
0x180019ddb  mov     [r11-18h], rax
0x180019ddf  mov     edx, 310FB0h; dwIoControlCode
0x180019de4  mov     [rsp+48h+nOutBufferSize], ebx; nOutBufferSize
0x180019de8  mov     [r11-28h], rbx
0x180019dec  mov     [rsp+48h+arg_0], ebx
0x180019df0  call    cs:__imp_DeviceIoControl
0x180019df6  test    eax, eax
0x180019df8  jnz     short loc_180019E42
0x180019dfa  lea     edx, [rbx+2]
0x180019dfd  call    WppTraceIndent
0x180019e02  call    cs:__imp_GetLastError
0x180019e08  mov     ebx, eax
0x180019e0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180019e11  lea     rax, WPP_GLOBAL_Control
0x180019e18  cmp     rcx, rax
0x180019e1b  jz      short loc_180019E42
0x180019e1d  test    byte ptr [rcx+1Ch], 1
0x180019e21  jz      short loc_180019E42
0x180019e23  cmp     byte ptr [rcx+19h], 2
0x180019e27  jb      short loc_180019E42
0x180019e29  mov     rcx, [rcx+10h]
0x180019e2d  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x180019e34  mov     edx, 35h ; '5'
0x180019e39  mov     [rsp+48h+var_28], ebx
0x180019e3d  call    WPP_SF_sd
0x180019e42  mov     eax, ebx
0x180019e44  add     rsp, 40h
0x180019e48  pop     rbx
0x180019e49  retn
```
