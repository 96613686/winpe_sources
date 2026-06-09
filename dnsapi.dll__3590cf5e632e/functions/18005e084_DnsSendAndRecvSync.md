# DnsSendAndRecvSync

- ea: `0x18005e084`
- end: `0x18005e211`
- name: `DnsSendAndRecvSync`
- size: `397`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18007b344`
- `0x18008555c`

## callees

- `0x18005e084`
- `0x18005e218`
- `0x18008b5f0`
- `0x1800dc9e0`
- `0x1800ddfa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e198`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e1c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e198`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e1c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e146`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e146`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005e0bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005e0bf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005e10e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005e10e`

## pseudocode

```c
__int64 __fastcall DnsSendAndRecvSync(_QWORD *pv)
{
  DWORD LastError; // ebx
  DWORD v3; // eax
  HANDLE hHandle[2]; // [rsp+20h] [rbp-28h] BYREF

  *(_OWORD *)hHandle = 0;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_q(1035, 464, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids, pv);
  hHandle[0] = CreateEventW(0, 0, 0, 0);
  if ( hHandle[0] )
  {
    pv[58] = hHandle;
    pv[59] = DnsUpdateCb;
    LastError = Send_AndRecv(pv);
    if ( LastError != 9506 )
      goto LABEL_7;
    v3 = WaitForSingleObject(hHandle[0], 0xFFFFFFFF);
    switch ( v3 )
    {
      case 0u:
        goto LABEL_6;
      case 0x80u:
        LastError = 735;
        break;
      case 0x102u:
        LastError = 1460;
        break;
      case 0xFFFFFFFF:
        LastError = GetLastError();
        if ( !LastError )
        {
LABEL_6:
          LastError = (DWORD)hHandle[1];
          pv[59] = 0;
          pv[58] = 0;
        }
        break;
      default:
        LastError = 14;
        break;
    }
  }
  else
  {
    LastError = GetLastError();
  }
LABEL_7:
  if ( hHandle[0] )
    CloseHandle(hHandle[0]);
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 465, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x18005e084  mov     [rsp+arg_8], rbx
0x18005e089  push    rdi
0x18005e08a  sub     rsp, 40h
0x18005e08e  mov     rax, cs:__security_cookie
0x18005e095  xor     rax, rsp
0x18005e098  mov     [rsp+48h+var_18], rax
0x18005e09d  xorps   xmm0, xmm0
0x18005e0a0  mov     rdi, rcx
0x18005e0a3  movups  xmmword ptr [rsp+48h+hHandle], xmm0
0x18005e0a8  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18005e0af  jnz     loc_18005E17A
0x18005e0b5  xor     r9d, r9d; lpName
0x18005e0b8  xor     r8d, r8d; bInitialState
0x18005e0bb  xor     edx, edx; bManualReset
0x18005e0bd  xor     ecx, ecx; lpEventAttributes
0x18005e0bf  call    cs:__imp_CreateEventW
0x18005e0c6  nop     dword ptr [rax+rax+00h]
0x18005e0cb  mov     [rsp+48h+hHandle], rax
0x18005e0d0  test    rax, rax
0x18005e0d3  jz      loc_18005E198
0x18005e0d9  lea     rax, [rsp+48h+hHandle]
0x18005e0de  mov     rcx, rdi; pv
0x18005e0e1  mov     [rdi+1D0h], rax
0x18005e0e8  lea     rax, DnsUpdateCb
0x18005e0ef  mov     [rdi+1D8h], rax
0x18005e0f6  call    Send_AndRecv
0x18005e0fb  mov     ebx, eax
0x18005e0fd  cmp     eax, 2522h
0x18005e102  jnz     short loc_18005E13C
0x18005e104  mov     rcx, [rsp+48h+hHandle]; hHandle
0x18005e109  or      ebx, 0FFFFFFFFh
0x18005e10c  mov     edx, ebx; dwMilliseconds
0x18005e10e  call    cs:__imp_WaitForSingleObject
0x18005e115  nop     dword ptr [rax+rax+00h]
0x18005e11a  test    eax, eax
0x18005e11c  jnz     loc_18005E1A8
0x18005e122  mov     ebx, dword ptr [rsp+48h+hHandle+8]
0x18005e126  mov     qword ptr [rdi+1D8h], 0
0x18005e131  mov     qword ptr [rdi+1D0h], 0
0x18005e13c  mov     rcx, [rsp+48h+hHandle]; hObject
0x18005e141  test    rcx, rcx
0x18005e144  jz      short loc_18005E152
0x18005e146  call    cs:__imp_CloseHandle
0x18005e14d  nop     dword ptr [rax+rax+00h]
0x18005e152  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18005e159  jnz     loc_18005E1F3
0x18005e15f  mov     eax, ebx
0x18005e161  mov     rcx, [rsp+48h+var_18]
0x18005e166  xor     rcx, rsp; StackCookie
0x18005e169  call    __security_check_cookie
0x18005e16e  mov     rbx, [rsp+48h+arg_8]
0x18005e173  add     rsp, 40h
0x18005e177  pop     rdi
0x18005e178  retn
0x18005e17a  mov     edx, 1D0h
0x18005e17f  lea     r8, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids
0x18005e186  mov     ecx, 40Bh
0x18005e18b  mov     r9, rdi
0x18005e18e  call    WPP_SF_q
0x18005e193  jmp     loc_18005E0B5
0x18005e198  call    cs:__imp_GetLastError
0x18005e19f  nop     dword ptr [rax+rax+00h]
0x18005e1a4  mov     ebx, eax
0x18005e1a6  jmp     short loc_18005E13C
0x18005e1a8  cmp     eax, 80h
0x18005e1ad  jz      short loc_18005E1E9
0x18005e1af  cmp     eax, 102h
0x18005e1b4  jz      short loc_18005E1DF
0x18005e1b6  cmp     eax, ebx
0x18005e1b8  jz      short loc_18005E1C4
0x18005e1ba  mov     ebx, 0Eh
0x18005e1bf  jmp     loc_18005E13C
0x18005e1c4  call    cs:__imp_GetLastError
0x18005e1cb  nop     dword ptr [rax+rax+00h]
0x18005e1d0  mov     ebx, eax
0x18005e1d2  test    eax, eax
0x18005e1d4  jnz     loc_18005E13C
0x18005e1da  jmp     loc_18005E122
0x18005e1df  mov     ebx, 5B4h
0x18005e1e4  jmp     loc_18005E13C
0x18005e1e9  mov     ebx, 2DFh
0x18005e1ee  jmp     loc_18005E13C
0x18005e1f3  mov     edx, 1D1h
0x18005e1f8  lea     r8, WPP_ba3f360b8c0d3a27e58c447a61b8ac8a_Traceguids
0x18005e1ff  mov     ecx, 40Bh
0x18005e204  mov     r9d, ebx
0x18005e207  call    WPP_SF_d
0x18005e20c  jmp     loc_18005E15F
```
