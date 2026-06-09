# FwhcAreAllEventsPresent

- ea: `0x18000b108`
- end: `0x18000b233`
- name: `FwhcAreAllEventsPresent`
- size: `299`
- prototype: `__int64 __fastcall(FILETIME *lpFileTime2)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008d7c`

## callees

- `0x18000b108`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000b1e0`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000b1e0`
- `fwpuclnt!FwpmEngineClose0` at `0x18000b20e`
- `fwpuclnt!FwpmEngineClose0` at `0x18000b20e`
- `fwpuclnt!FwpmFreeMemory0` at `0x18000b21e`
- `fwpuclnt!FwpmFreeMemory0` at `0x18000b21e`
- `fwpuclnt!FwpmNetEventCreateEnumHandle0` at `0x18000b186`
- `fwpuclnt!FwpmNetEventCreateEnumHandle0` at `0x18000b186`
- `fwpuclnt!FwpmNetEventDestroyEnumHandle0` at `0x18000b1ff`
- `fwpuclnt!FwpmNetEventDestroyEnumHandle0` at `0x18000b1ff`
- `fwpuclnt!FwpmEngineOpen0` at `0x18000b15c`
- `fwpuclnt!FwpmEngineOpen0` at `0x18000b15c`
- `fwpuclnt!FwpmNetEventEnum5` at `0x18000b1b7`
- `fwpuclnt!FwpmNetEventEnum5` at `0x18000b1b7`

## pseudocode

```c
__int64 __fastcall FwhcAreAllEventsPresent(FILETIME *lpFileTime2, _BYTE *a2)
{
  signed int v4; // eax
  signed int v5; // ebx
  char v6; // di
  signed int v7; // eax
  int v8; // eax
  FWPM_NET_EVENT_ENUM_TEMPLATE0 enumTemplate; // [rsp+30h] [rbp-28h] BYREF
  int v11; // [rsp+90h] [rbp+38h] BYREF
  HANDLE engineHandle; // [rsp+98h] [rbp+40h] BYREF
  void *p; // [rsp+A0h] [rbp+48h] BYREF
  HANDLE enumHandle; // [rsp+A8h] [rbp+50h] BYREF

  enumTemplate.endTime = *lpFileTime2;
  *a2 = 0;
  *(_QWORD *)&enumTemplate.numFilterConditions = 0;
  p = 0;
  engineHandle = 0;
  enumHandle = 0;
  v11 = 0;
  enumTemplate.startTime = 0;
  enumTemplate.filterCondition = 0;
  v4 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 < 0 )
  {
    v6 = 0;
  }
  else
  {
    v6 = 1;
    v7 = FwpmNetEventCreateEnumHandle0(engineHandle, &enumTemplate, &enumHandle);
    v5 = v7;
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0x80070000;
    if ( v5 >= 0 )
    {
      v8 = FwpmNetEventEnum5(engineHandle, enumHandle, 1, &p, &v11);
      v5 = v8;
      if ( v8 > 0 )
        v5 = (unsigned __int16)v8 | 0x80070000;
      if ( v5 >= 0 && v11 && CompareFileTime(*(const FILETIME **)p, lpFileTime2) < 0 )
        *a2 = 1;
    }
  }
  if ( enumHandle )
    FwpmNetEventDestroyEnumHandle0(engineHandle, enumHandle);
  if ( v6 )
    FwpmEngineClose0(engineHandle);
  if ( p )
    FwpmFreeMemory0(&p);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000b108  push    rbp
0x18000b10a  push    rbx
0x18000b10b  push    rsi
0x18000b10c  push    rdi
0x18000b10d  push    r14
0x18000b10f  push    r15
0x18000b111  mov     rbp, rsp
0x18000b114  sub     rsp, 58h
0x18000b118  mov     rax, [rcx]
0x18000b11b  xor     r15d, r15d
0x18000b11e  mov     qword ptr [rbp+enumTemplate.endTime.dwLowDateTime], rax
0x18000b122  mov     rsi, rdx
0x18000b125  mov     r14, rcx
0x18000b128  mov     [rdx], r15b
0x18000b12b  lea     rax, [rbp+arg_8]
0x18000b12f  mov     qword ptr [rbp+enumTemplate.numFilterConditions], r15
0x18000b133  lea     edx, [r15+0Ah]; authnService
0x18000b137  mov     [rbp+p], r15
0x18000b13b  xor     r9d, r9d; session
0x18000b13e  mov     [rbp+arg_8], r15
0x18000b142  xor     r8d, r8d; authIdentity
0x18000b145  mov     [rbp+enumHandle], r15
0x18000b149  xor     ecx, ecx; serverName
0x18000b14b  mov     [rbp+arg_0], r15d
0x18000b14f  mov     qword ptr [rbp+enumTemplate.startTime.dwLowDateTime], r15
0x18000b153  mov     [rbp+enumTemplate.filterCondition], r15
0x18000b157  mov     [rsp+58h+engineHandle], rax; engineHandle
0x18000b15c  call    cs:__imp_FwpmEngineOpen0
0x18000b162  mov     ebx, eax
0x18000b164  test    eax, eax
0x18000b166  jle     short loc_18000B171
0x18000b168  movzx   ebx, ax
0x18000b16b  or      ebx, 80070000h
0x18000b171  test    ebx, ebx
0x18000b173  js      short loc_18000B1EF
0x18000b175  mov     rcx, [rbp+arg_8]; engineHandle
0x18000b179  lea     r8, [rbp+enumHandle]; enumHandle
0x18000b17d  lea     rdx, [rbp+enumTemplate]; enumTemplate
0x18000b181  mov     edi, 1
0x18000b186  call    cs:__imp_FwpmNetEventCreateEnumHandle0
0x18000b18c  mov     ebx, eax
0x18000b18e  test    eax, eax
0x18000b190  jle     short loc_18000B19B
0x18000b192  movzx   ebx, ax
0x18000b195  or      ebx, 80070000h
0x18000b19b  test    ebx, ebx
0x18000b19d  js      short loc_18000B1F2
0x18000b19f  mov     rdx, [rbp+enumHandle]
0x18000b1a3  lea     rax, [rbp+arg_0]
0x18000b1a7  mov     rcx, [rbp+arg_8]
0x18000b1ab  lea     r9, [rbp+p]
0x18000b1af  mov     r8d, edi
0x18000b1b2  mov     [rsp+58h+engineHandle], rax
0x18000b1b7  call    cs:__imp_FwpmNetEventEnum5
0x18000b1bd  mov     ebx, eax
0x18000b1bf  test    eax, eax
0x18000b1c1  jle     short loc_18000B1CC
0x18000b1c3  movzx   ebx, ax
0x18000b1c6  or      ebx, 80070000h
0x18000b1cc  test    ebx, ebx
0x18000b1ce  js      short loc_18000B1F2
0x18000b1d0  cmp     [rbp+arg_0], r15d
0x18000b1d4  jbe     short loc_18000B1F2
0x18000b1d6  mov     rcx, [rbp+p]
0x18000b1da  mov     rdx, r14; lpFileTime2
0x18000b1dd  mov     rcx, [rcx]; lpFileTime1
0x18000b1e0  call    cs:__imp_CompareFileTime
0x18000b1e6  test    eax, eax
0x18000b1e8  jns     short loc_18000B1F2
0x18000b1ea  mov     [rsi], dil
0x18000b1ed  jmp     short loc_18000B1F2
0x18000b1ef  mov     dil, r15b
0x18000b1f2  mov     rdx, [rbp+enumHandle]; enumHandle
0x18000b1f6  test    rdx, rdx
0x18000b1f9  jz      short loc_18000B205
0x18000b1fb  mov     rcx, [rbp+arg_8]; engineHandle
0x18000b1ff  call    cs:__imp_FwpmNetEventDestroyEnumHandle0
0x18000b205  test    dil, dil
0x18000b208  jz      short loc_18000B214
0x18000b20a  mov     rcx, [rbp+arg_8]; engineHandle
0x18000b20e  call    cs:__imp_FwpmEngineClose0
0x18000b214  cmp     [rbp+p], r15
0x18000b218  jz      short loc_18000B224
0x18000b21a  lea     rcx, [rbp+p]; p
0x18000b21e  call    cs:__imp_FwpmFreeMemory0
0x18000b224  mov     eax, ebx
0x18000b226  add     rsp, 58h
0x18000b22a  pop     r15
0x18000b22c  pop     r14
0x18000b22e  pop     rdi
0x18000b22f  pop     rsi
0x18000b230  pop     rbx
0x18000b231  pop     rbp
0x18000b232  retn
```
