# FrameBufferClientChannel::OpenGlobalObjects(ushort const *,ushort const *,ushort const *)

- ea: `0x1802c0120`
- end: `0x1802c04c5`
- name: `?OpenGlobalObjects@FrameBufferClientChannel@@AEAAJPEBG00@Z`
- size: `933`
- prototype: `__int64 __fastcall(FrameBufferClientChannel *__hidden this, LPCWSTR lpName, LPCWSTR, LPCWSTR)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18010a020`

## callees

- `0x180039c98`
- `0x180039ce4`
- `0x1800e9b1c`
- `0x1802beba8`
- `0x1802c0120`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1802c0274`
- `KERNEL32!GetLastError` at `0x1802c02fb`
- `KERNEL32!GetLastError` at `0x1802c034b`
- `KERNEL32!GetLastError` at `0x1802c03b5`
- `KERNEL32!GetLastError` at `0x1802c0274`
- `KERNEL32!GetLastError` at `0x1802c02fb`
- `KERNEL32!GetLastError` at `0x1802c034b`
- `KERNEL32!GetLastError` at `0x1802c03b5`
- `KERNEL32!MapViewOfFile` at `0x1802c03a3`
- `KERNEL32!MapViewOfFile` at `0x1802c03a3`
- `KERNEL32!OpenEventW` at `0x1802c0262`
- `KERNEL32!OpenEventW` at `0x1802c0262`
- `KERNEL32!OpenMutexW` at `0x1802c02e9`
- `KERNEL32!OpenMutexW` at `0x1802c02e9`
- `KERNEL32!OpenFileMappingW` at `0x1802c0339`
- `KERNEL32!OpenFileMappingW` at `0x1802c0339`
- `KERNEL32!GetSystemInfo` at `0x1802c03fa`
- `KERNEL32!GetSystemInfo` at `0x1802c03fa`

## string_xrefs

- `0x1802c0484`: `CreateBitmap failed!`

## pseudocode

```c
__int64 __fastcall FrameBufferClientChannel::OpenGlobalObjects(
        FrameBufferClientChannel *this,
        LPCWSTR lpName,
        LPCWSTR a3,
        LPCWSTR a4)
{
  bool v4; // zf
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v9; // rdx
  signed int LastError; // ebx
  HANDLE v11; // rax
  unsigned int v12; // eax
  __int64 v13; // rdx
  HANDLE v14; // rax
  HANDLE v15; // rax
  LPVOID v16; // rax
  __int64 v17; // r10
  int v18; // ecx
  unsigned int v19; // eax
  __int64 v21; // [rsp+28h] [rbp-40h]
  _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-38h] BYREF

  v4 = *((_QWORD *)this + 34) == 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147418113;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 89;
LABEL_6:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      WPP_d4d15e93c04c3e8f14016103dc3e75c5_Traceguids,
      CurrentThreadActivityIdPrefix,
      -2147418113);
    return (unsigned int)-2147418113;
  }
  if ( *((_QWORD *)this + 35) )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147418113;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 90;
    goto LABEL_6;
  }
  if ( *((_QWORD *)this + 36) )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147418113;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 91;
    goto LABEL_6;
  }
  if ( *((_QWORD *)this + 25) )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147418113;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 92;
    goto LABEL_6;
  }
  v11 = OpenEventW(0x100000u, 0, a4);
  *((_QWORD *)this + 34) = v11;
  if ( !v11 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_29;
    }
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 93;
LABEL_28:
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, WPP_d4d15e93c04c3e8f14016103dc3e75c5_Traceguids, v12, LastError);
LABEL_29:
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      return (unsigned int)-2147467259;
    return (unsigned int)LastError;
  }
  v14 = OpenMutexW(0x100000u, 0, a3);
  *((_QWORD *)this + 35) = v14;
  if ( !v14 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_29;
    }
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 94;
    goto LABEL_28;
  }
  v15 = OpenFileMappingW(6u, 0, lpName);
  *((_QWORD *)this + 36) = v15;
  if ( !v15 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_29;
    }
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 95;
    goto LABEL_28;
  }
  v16 = MapViewOfFile(v15, 2u, 0, 0, 0x38u);
  *((_QWORD *)this + 25) = v16;
  if ( !v16 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_29;
    }
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 96;
    goto LABEL_28;
  }
  GetSystemInfo(&SystemInfo);
  v17 = *((_QWORD *)this + 25);
  *((_DWORD *)this + 52) = *(_DWORD *)(v17 + 20);
  v18 = -*(_DWORD *)(v17 + 24);
  if ( *(int *)(v17 + 24) > 0 )
    v18 = *(_DWORD *)(v17 + 24);
  *((_DWORD *)this + 53) = v18;
  LastError = FrameBufferClientChannel::CreateBitmap(
                this,
                *(_DWORD *)(v17 + 20),
                *(_DWORD *)(v17 + 24),
                *(unsigned __int16 *)(v17 + 30),
                *((void **)this + 36),
                SystemInfo.dwAllocationGranularity * (0x38 / SystemInfo.dwAllocationGranularity + 1));
  if ( LastError < 0
    && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v19 = RdpWppGetCurrentThreadActivityIdPrefix();
    LODWORD(v21) = LastError;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      97,
      (unsigned int)WPP_d4d15e93c04c3e8f14016103dc3e75c5_Traceguids,
      v19,
      (__int64)"CreateBitmap failed!",
      v21,
      *(_QWORD *)&SystemInfo.dwOemId,
      SystemInfo.lpMinimumApplicationAddress,
      SystemInfo.lpMaximumApplicationAddress,
      SystemInfo.dwActiveProcessorMask,
      *(_QWORD *)&SystemInfo.dwNumberOfProcessors);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1802c0120  mov     rax, rsp
0x1802c0123  mov     [rax+8], rbx
0x1802c0127  mov     [rax+10h], rsi
0x1802c012b  push    rdi
0x1802c012c  sub     rsp, 60h
0x1802c0130  cmp     qword ptr [rcx+110h], 0
0x1802c0138  xorps   xmm0, xmm0
0x1802c013b  movups  xmmword ptr [rax-38h], xmm0
0x1802c013f  mov     rsi, r8
0x1802c0142  mov     rdi, rdx
0x1802c0145  movups  xmmword ptr [rax-28h], xmm0
0x1802c0149  mov     rbx, rcx
0x1802c014c  movups  xmmword ptr [rax-18h], xmm0
0x1802c0150  jz      short loc_1802C01A7
0x1802c0152  mov     rcx, cs:WPP_GLOBAL_Control
0x1802c0159  lea     rax, WPP_GLOBAL_Control
0x1802c0160  cmp     rcx, rax
0x1802c0163  jz      short loc_1802C019D
0x1802c0165  test    byte ptr [rcx+1Ch], 8
0x1802c0169  jz      short loc_1802C019D
0x1802c016b  cmp     byte ptr [rcx+19h], 2
0x1802c016f  jb      short loc_1802C019D
0x1802c0171  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1802c0176  mov     edx, 59h ; 'Y'
0x1802c017b  mov     rcx, cs:WPP_GLOBAL_Control
0x1802c0182  lea     r8, WPP_d4d15e93c04c3e8f14016103dc3e75c5_Traceguids
0x1802c0189  mov     r9d, eax
0x1802c018c  mov     dword ptr [rsp+68h+dwNumberOfBytesToMap], 8000FFFFh
0x1802c0194  mov     rcx, [rcx+10h]
0x1802c0198  call    WPP_SF_Dd
0x1802c019d  mov     ebx, 8000FFFFh
0x1802c01a2  jmp     loc_1802C04B3
0x1802c01a7  cmp     qword ptr [rcx+118h], 0
0x1802c01af  jz      short loc_1802C01DC
0x1802c01b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1802c01b8  lea     rax, WPP_GLOBAL_Control
0x1802c01bf  cmp     rcx, rax
0x1802c01c2  jz      short loc_1802C019D
0x1802c01c4  test    byte ptr [rcx+1Ch], 8
0x1802c01c8  jz      short loc_1802C019D
0x1802c01ca  cmp     byte ptr [rcx+19h], 2
0x1802c01ce  jb      short loc_1802C019D
0x1802c01d0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1802c01d5  mov     edx, 5Ah ; 'Z'
0x1802c01da  jmp     short loc_1802C017B
0x1802c01dc  cmp     qword ptr [rcx+120h], 0
0x1802c01e4  jz      short loc_1802C0214
0x1802c01e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1802c01ed  lea     rax, WPP_GLOBAL_Control
0x1802c01f4  cmp     rcx, rax
0x1802c01f7  jz      short loc_1802C019D
0x1802c01f9  test    byte ptr [rcx+1Ch], 8
0x1802c01fd  jz      short loc_1802C019D
0x1802c01ff  cmp     byte ptr [rcx+19h], 2
0x1802c0203  jb      short loc_1802C019D
0x1802c0205  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1802c020a  mov     edx, 5Bh ; '['
0x1802c020f  jmp     loc_1802C017B
0x1802c0214  cmp     qword ptr [rcx+0C8h], 0
0x1802c021c  jz      short loc_1802C0258
0x1802c021e  mov     rcx, cs:WPP_GLOBAL_Control
0x1802c0225  lea     rax, WPP_GLOBAL_Control
0x1802c022c  cmp     rcx, rax
0x1802c022f  jz      loc_1802C019D
0x1802c0235  test    byte ptr [rcx+1Ch], 8
0x1802c0239  jz      loc_1802C019D
0x1802c023f  cmp     byte ptr [rcx+19h], 2
0x1802c0243  jb      loc_1802C019D
0x1802c0249  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1802c024e  mov     edx, 5Ch ; '\'
0x1802c0253  jmp     loc_1802C017B
0x1802c0258  mov     r8, r9; lpName
0x1802c025b  xor     edx, edx; bInheritHandle
0x1802c025d  mov     ecx, 100000h; dwDesiredAccess
0x1802c0262  call    cs:__imp_OpenEventW
0x1802c0268  mov     [rbx+110h], rax
0x1802c026f  test    rax, rax
0x1802c0272  jnz     short loc_1802C02DF
0x1802c0274  call    cs:__imp_GetLastError
0x1802c027a  mov     ebx, eax
0x1802c027c  mov     rcx, cs:WPP_GLOBAL_Control
0x1802c0283  lea     rax, WPP_GLOBAL_Control
0x1802c028a  cmp     rcx, rax
0x1802c028d  jz      short loc_1802C02C3
0x1802c028f  test    byte ptr [rcx+1Ch], 8
0x1802c0293  jz      short loc_1802C02C3
0x1802c0295  cmp     byte ptr [rcx+19h], 2
0x1802c0299  jb      short loc_1802C02C3
0x1802c029b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1802c02a0  mov     edx, 5Dh ; ']'
0x1802c02a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1802c02ac  lea     r8, WPP_d4d15e93c04c3e8f14016103dc3e75c5_Traceguids
0x1802c02b3  mov     r9d, eax
0x1802c02b6  mov     dword ptr [rsp+68h+dwNumberOfBytesToMap], ebx
0x1802c02ba  mov     rcx, [rcx+10h]
0x1802c02be  call    WPP_SF_Dd
0x1802c02c3  test    ebx, ebx
0x1802c02c5  jle     short loc_1802C02D0
0x1802c02c7  movzx   ebx, bx
0x1802c02ca  or      ebx, 80070000h
0x1802c02d0  test    ebx, ebx
0x1802c02d2  mov     eax, 80004005h
0x1802c02d7  cmovns  ebx, eax
0x1802c02da  jmp     loc_1802C04B3
0x1802c02df  mov     r8, rsi; lpName
0x1802c02e2  xor     edx, edx; bInheritHandle
0x1802c02e4  mov     ecx, 100000h; dwDesiredAccess
0x1802c02e9  call    cs:__imp_OpenMutexW
0x1802c02ef  mov     [rbx+118h], rax
0x1802c02f6  test    rax, rax
0x1802c02f9  jnz     short loc_1802C0331
0x1802c02fb  call    cs:__imp_GetLastError
0x1802c0301  mov     ebx, eax
0x1802c0303  mov     rcx, cs:WPP_GLOBAL_Control
0x1802c030a  lea     rax, WPP_GLOBAL_Control
0x1802c0311  cmp     rcx, rax
0x1802c0314  jz      short loc_1802C02C3
0x1802c0316  test    byte ptr [rcx+1Ch], 8
0x1802c031a  jz      short loc_1802C02C3
0x1802c031c  cmp     byte ptr [rcx+19h], 2
0x1802c0320  jb      short loc_1802C02C3
0x1802c0322  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1802c0327  mov     edx, 5Eh ; '^'
0x1802c032c  jmp     loc_1802C02A5
0x1802c0331  xor     edx, edx; bInheritHandle
0x1802c0333  mov     r8, rdi; lpName
0x1802c0336  lea     ecx, [rdx+6]; dwDesiredAccess
0x1802c0339  call    cs:__imp_OpenFileMappingW
0x1802c033f  mov     [rbx+120h], rax
0x1802c0346  test    rax, rax
0x1802c0349  jnz     short loc_1802C038D
0x1802c034b  call    cs:__imp_GetLastError
0x1802c0351  mov     ebx, eax
0x1802c0353  mov     rcx, cs:WPP_GLOBAL_Control
0x1802c035a  lea     rax, WPP_GLOBAL_Control
0x1802c0361  cmp     rcx, rax
0x1802c0364  jz      loc_1802C02C3
0x1802c036a  test    byte ptr [rcx+1Ch], 8
0x1802c036e  jz      loc_1802C02C3
0x1802c0374  cmp     byte ptr [rcx+19h], 2
0x1802c0378  jb      loc_1802C02C3
0x1802c037e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1802c0383  mov     edx, 5Fh ; '_'
0x1802c0388  jmp     loc_1802C02A5
0x1802c038d  mov     edi, 38h ; '8'
0x1802c0392  xor     r9d, r9d; dwFileOffsetLow
0x1802c0395  xor     r8d, r8d; dwFileOffsetHigh
0x1802c0398  mov     [rsp+68h+dwNumberOfBytesToMap], rdi; dwNumberOfBytesToMap
0x1802c039d  mov     rcx, rax; hFileMappingObject
0x1802c03a0  lea     edx, [rdi-36h]; dwDesiredAccess
0x1802c03a3  call    cs:__imp_MapViewOfFile
0x1802c03a9  mov     [rbx+0C8h], rax
0x1802c03b0  test    rax, rax
0x1802c03b3  jnz     short loc_1802C03F5
0x1802c03b5  call    cs:__imp_GetLastError
0x1802c03bb  mov     ebx, eax
0x1802c03bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1802c03c4  lea     rax, WPP_GLOBAL_Control
0x1802c03cb  cmp     rcx, rax
0x1802c03ce  jz      loc_1802C02C3
0x1802c03d4  test    byte ptr [rcx+1Ch], 8
0x1802c03d8  jz      loc_1802C02C3
0x1802c03de  cmp     byte ptr [rcx+19h], 2
0x1802c03e2  jb      loc_1802C02C3
0x1802c03e8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1802c03ed  lea     edx, [rdi+28h]
0x1802c03f0  jmp     loc_1802C02A5
0x1802c03f5  lea     rcx, [rsp+68h+SystemInfo]; lpSystemInfo
0x1802c03fa  call    cs:__imp_GetSystemInfo
0x1802c0400  mov     r10, [rbx+0C8h]
0x1802c0407  mov     rax, rdi
0x1802c040a  mov     ecx, [r10+14h]
0x1802c040e  mov     [rbx+0D0h], ecx
0x1802c0414  mov     ecx, [r10+18h]
0x1802c0418  neg     ecx
0x1802c041a  cmovs   ecx, [r10+18h]
0x1802c041f  xor     edx, edx
0x1802c0421  mov     [rbx+0D4h], ecx
0x1802c0427  mov     ecx, [rsp+68h+SystemInfo.dwAllocationGranularity]
0x1802c042b  movzx   r9d, word ptr [r10+1Eh]; unsigned int
0x1802c0430  mov     r8d, [r10+18h]; int
0x1802c0434  div     rcx
0x1802c0437  mov     edx, [r10+14h]; int
0x1802c043b  mov     rcx, rbx; this
0x1802c043e  inc     eax
0x1802c0440  imul    eax, [rsp+68h+SystemInfo.dwAllocationGranularity]
0x1802c0445  mov     dword ptr [rsp+68h+var_40], eax; unsigned int
0x1802c0449  mov     rax, [rbx+120h]
0x1802c0450  mov     [rsp+68h+dwNumberOfBytesToMap], rax; void *
0x1802c0455  call    ?CreateBitmap@FrameBufferClientChannel@@AEAAJJJIPEAXK@Z; FrameBufferClientChannel::CreateBitmap(long,long,uint,void *,ulong)
0x1802c045a  mov     ebx, eax
0x1802c045c  test    eax, eax
0x1802c045e  jns     short loc_1802C04B3
0x1802c0460  mov     rcx, cs:WPP_GLOBAL_Control
0x1802c0467  lea     rax, WPP_GLOBAL_Control
0x1802c046e  cmp     rcx, rax
0x1802c0471  jz      short loc_1802C04B3
0x1802c0473  test    byte ptr [rcx+1Ch], 8
0x1802c0477  jz      short loc_1802C04B3
0x1802c0479  cmp     byte ptr [rcx+19h], 2
0x1802c047d  jb      short loc_1802C04B3
0x1802c047f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1802c0484  lea     rcx, aCreatebitmapFa_1; "CreateBitmap failed!"
0x1802c048b  mov     dword ptr [rsp+68h+var_40], ebx
0x1802c048f  mov     [rsp+68h+dwNumberOfBytesToMap], rcx
0x1802c0494  lea     r8, WPP_d4d15e93c04c3e8f14016103dc3e75c5_Traceguids
0x1802c049b  mov     rcx, cs:WPP_GLOBAL_Control
0x1802c04a2  mov     edx, 61h ; 'a'
0x1802c04a7  mov     r9d, eax
0x1802c04aa  mov     rcx, [rcx+10h]
0x1802c04ae  call    WPP_SF_DsD
0x1802c04b3  mov     rsi, [rsp+68h+arg_8]
0x1802c04b8  mov     eax, ebx
0x1802c04ba  mov     rbx, [rsp+68h+arg_0]
0x1802c04bf  add     rsp, 60h
0x1802c04c3  pop     rdi
0x1802c04c4  retn
```
