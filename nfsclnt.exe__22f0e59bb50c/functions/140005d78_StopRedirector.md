# StopRedirector

- ea: `0x140005d78`
- end: `0x140005f22`
- name: `StopRedirector`
- size: `426`
- prototype: `ULONG()`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000664c`

## callees

- `0x140002bd8`
- `0x140002c00`
- `0x140005d78`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140005df8`
- `KERNEL32!GetLastError` at `0x140005df8`
- `KERNEL32!CreateEventW` at `0x140005dea`
- `KERNEL32!CreateEventW` at `0x140005dea`
- `KERNEL32!WaitForSingleObject` at `0x140005e4c`
- `KERNEL32!WaitForSingleObject` at `0x140005e4c`
- `KERNEL32!CloseHandle` at `0x140005e6d`
- `KERNEL32!CloseHandle` at `0x140005e6d`
- `ntdll!NtFsControlFile` at `0x140005e39`
- `ntdll!NtFsControlFile` at `0x140005e39`
- `ntdll!NtClose` at `0x140005ec3`
- `ntdll!NtClose` at `0x140005ec3`
- `ntdll!RtlNtStatusToDosError` at `0x140005f0c`
- `ntdll!RtlNtStatusToDosError` at `0x140005f0c`

## pseudocode

```c
ULONG StopRedirector()
{
  _QWORD *v0; // rcx
  HANDLE EventW; // rsi
  DWORD v3; // ebx
  unsigned int Status; // edi
  _QWORD *v5; // rcx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-38h] BYREF

  IoStatusBlock = 0;
  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_e7926938627732e63f903c41c3c41751_Traceguids);
      v0 = WPP_GLOBAL_Control;
    }
    if ( v0 != &WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 8) != 0 )
      WPP_SF_(v0[2], 26, WPP_e7926938627732e63f903c41c3c41751_Traceguids);
  }
  EventW = CreateEventW(0, 0, 0, 0);
  if ( !EventW )
    return GetLastError();
  v3 = 0;
  if ( NtFsControlFile(hDevice, EventW, 0, 0, &IoStatusBlock, 0x148944u, 0, 0, 0, 0) != 259
    || (v3 = WaitForSingleObject(EventW, 0xFFFFFFFF), Status = -1073741823, v3 != -1) )
  {
    Status = IoStatusBlock.Status;
  }
  if ( v3 != -1 )
    v3 = 0;
  CloseHandle(EventW);
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_e7926938627732e63f903c41c3c41751_Traceguids);
      v5 = WPP_GLOBAL_Control;
    }
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
      WPP_SF_d(v5[2], 28, WPP_e7926938627732e63f903c41c3c41751_Traceguids, Status);
  }
  NtClose(hDevice);
  hDevice = 0;
  if ( Status == -2147483613 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_e7926938627732e63f903c41c3c41751_Traceguids);
    return 1794;
  }
  else
  {
    if ( !v3 )
      return RtlNtStatusToDosError(Status);
    return v3;
  }
}

```

## disassembly

```asm
0x140005d78  push    rbx
0x140005d7a  push    rsi
0x140005d7b  push    rdi
0x140005d7c  push    r14
0x140005d7e  push    r15
0x140005d80  sub     rsp, 60h
0x140005d84  xorps   xmm0, xmm0
0x140005d87  movups  xmmword ptr [rsp+88h+var_38], xmm0
0x140005d8c  mov     rcx, cs:WPP_GLOBAL_Control
0x140005d93  lea     r14, WPP_GLOBAL_Control
0x140005d9a  lea     r15, WPP_e7926938627732e63f903c41c3c41751_Traceguids
0x140005da1  cmp     rcx, r14
0x140005da4  jz      short loc_140005DE0
0x140005da6  test    byte ptr [rcx+1Ch], 1
0x140005daa  jz      short loc_140005DC4
0x140005dac  mov     rcx, [rcx+10h]
0x140005db0  mov     edx, 19h
0x140005db5  mov     r8, r15
0x140005db8  call    WPP_SF_
0x140005dbd  mov     rcx, cs:WPP_GLOBAL_Control
0x140005dc4  cmp     rcx, r14
0x140005dc7  jz      short loc_140005DE0
0x140005dc9  test    byte ptr [rcx+1Ch], 8
0x140005dcd  jz      short loc_140005DE0
0x140005dcf  mov     rcx, [rcx+10h]
0x140005dd3  mov     edx, 1Ah
0x140005dd8  mov     r8, r15
0x140005ddb  call    WPP_SF_
0x140005de0  xor     r9d, r9d; lpName
0x140005de3  xor     r8d, r8d; bInitialState
0x140005de6  xor     edx, edx; bManualReset
0x140005de8  xor     ecx, ecx; lpEventAttributes
0x140005dea  call    cs:__imp_CreateEventW
0x140005df0  mov     rsi, rax
0x140005df3  test    rax, rax
0x140005df6  jnz     short loc_140005E03
0x140005df8  call    cs:__imp_GetLastError
0x140005dfe  jmp     loc_140005F16
0x140005e03  mov     rcx, cs:hDevice; FileHandle
0x140005e0a  lea     rax, [rsp+88h+var_38]
0x140005e0f  xor     ebx, ebx
0x140005e11  xor     r9d, r9d; ApcContext
0x140005e14  mov     [rsp+88h+OutputBufferLength], ebx; OutputBufferLength
0x140005e18  xor     r8d, r8d; ApcRoutine
0x140005e1b  mov     [rsp+88h+OutputBuffer], rbx; OutputBuffer
0x140005e20  mov     rdx, rsi; Event
0x140005e23  mov     [rsp+88h+InputBufferLength], ebx; InputBufferLength
0x140005e27  mov     [rsp+88h+InputBuffer], rbx; InputBuffer
0x140005e2c  mov     [rsp+88h+FsControlCode], 148944h; FsControlCode
0x140005e34  mov     [rsp+88h+IoStatusBlock], rax; IoStatusBlock
0x140005e39  call    cs:__imp_NtFsControlFile
0x140005e3f  cmp     eax, 103h
0x140005e44  jnz     short loc_140005E5E
0x140005e46  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140005e49  mov     rcx, rsi; hHandle
0x140005e4c  call    cs:__imp_WaitForSingleObject
0x140005e52  mov     ebx, eax
0x140005e54  mov     edi, 0C0000001h
0x140005e59  cmp     eax, 0FFFFFFFFh
0x140005e5c  jz      short loc_140005E62
0x140005e5e  mov     edi, dword ptr [rsp+88h+var_38]
0x140005e62  xor     eax, eax
0x140005e64  mov     rcx, rsi; hObject
0x140005e67  cmp     ebx, 0FFFFFFFFh
0x140005e6a  cmovnz  ebx, eax
0x140005e6d  call    cs:__imp_CloseHandle
0x140005e73  mov     rcx, cs:WPP_GLOBAL_Control
0x140005e7a  cmp     rcx, r14
0x140005e7d  jz      short loc_140005EBC
0x140005e7f  test    byte ptr [rcx+1Ch], 8
0x140005e83  jz      short loc_140005E9D
0x140005e85  mov     rcx, [rcx+10h]
0x140005e89  mov     edx, 1Bh
0x140005e8e  mov     r8, r15
0x140005e91  call    WPP_SF_
0x140005e96  mov     rcx, cs:WPP_GLOBAL_Control
0x140005e9d  cmp     rcx, r14
0x140005ea0  jz      short loc_140005EBC
0x140005ea2  test    byte ptr [rcx+1Ch], 8
0x140005ea6  jz      short loc_140005EBC
0x140005ea8  mov     rcx, [rcx+10h]
0x140005eac  mov     edx, 1Ch
0x140005eb1  mov     r9d, edi
0x140005eb4  mov     r8, r15
0x140005eb7  call    WPP_SF_d
0x140005ebc  mov     rcx, cs:hDevice; Handle
0x140005ec3  call    cs:__imp_NtClose
0x140005ec9  mov     cs:hDevice, 0
0x140005ed4  cmp     edi, 80000023h
0x140005eda  jnz     short loc_140005F06
0x140005edc  mov     rcx, cs:WPP_GLOBAL_Control
0x140005ee3  cmp     rcx, r14
0x140005ee6  jz      short loc_140005EFF
0x140005ee8  test    byte ptr [rcx+1Ch], 2
0x140005eec  jz      short loc_140005EFF
0x140005eee  mov     rcx, [rcx+10h]
0x140005ef2  mov     edx, 1Dh
0x140005ef7  mov     r8, r15
0x140005efa  call    WPP_SF_
0x140005eff  mov     eax, 702h
0x140005f04  jmp     short loc_140005F16
0x140005f06  test    ebx, ebx
0x140005f08  jnz     short loc_140005F14
0x140005f0a  mov     ecx, edi; Status
0x140005f0c  call    cs:__imp_RtlNtStatusToDosError
0x140005f12  mov     ebx, eax
0x140005f14  mov     eax, ebx
0x140005f16  add     rsp, 60h
0x140005f1a  pop     r15
0x140005f1c  pop     r14
0x140005f1e  pop     rdi
0x140005f1f  pop     rsi
0x140005f20  pop     rbx
0x140005f21  retn
```
