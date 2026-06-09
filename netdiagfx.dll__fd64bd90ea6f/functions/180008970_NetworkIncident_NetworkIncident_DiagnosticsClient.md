# NetworkIncident::NetworkIncident(DiagnosticsClient *)

- ea: `0x180008970`
- end: `0x180008ae1`
- name: `??0NetworkIncident@@QEAA@PEAVDiagnosticsClient@@@Z`
- size: `369`
- prototype: `NetworkIncident *__fastcall(NetworkIncident *__hidden this, struct DiagnosticsClient *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001b898`

## callees

- `0x180005350`
- `0x18000579c`
- `0x1800083e0`
- `0x18000844c`
- `0x180008970`
- `0x18001b3a8`
- `0x18002c840`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180008a57`
- `KERNEL32!InitializeCriticalSection` at `0x180008a57`
- `KERNEL32!CreateEventW` at `0x180008a69`
- `KERNEL32!CreateEventW` at `0x180008a69`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
NetworkIncident *__fastcall NetworkIncident::NetworkIncident(NetworkIncident *this, struct DiagnosticsClient *a2)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  struct NetworkDiagnosticsEngine *v6; // rax
  _BYTE v8[16]; // [rsp+38h] [rbp-20h] BYREF

  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 8) = 0;
  *(_QWORD *)((char *)this + 100) = 0;
  *((_QWORD *)this + 16) = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 136);
  *((_QWORD *)this + 18) = 0;
  *((_DWORD *)this + 38) = -2147467259;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_OWORD *)this + 11) = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 224);
  std::queue<int>::queue<int,std::deque<int>>((char *)this + 240);
  std::list<ProblemNode *>::list<ProblemNode *>((char *)this + 280);
  std::list<ProblemNode *>::list<ProblemNode *>((char *)this + 296);
  if ( (byte_180041BC1 & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(v4, StartNDFIncident, v5, 1, v8);
  *((_QWORD *)this + 10) = a2;
  *((_DWORD *)this + 6) = 0;
  *((_DWORD *)this + 22) = 0;
  *((_QWORD *)this + 2) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 312));
  *((_QWORD *)this + 9) = CreateEventW(0, 1, 0, 0);
  *((_WORD *)this + 46) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 88) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 28) = 0;
  *((_QWORD *)this + 27) = 0;
  v6 = NetworkDiagnosticsEngine::Instance();
  if ( v6 )
    *((_QWORD *)this + 27) = *(_QWORD *)v6;
  *((_QWORD *)this + 15) = 0;
  *((_DWORD *)this + 58) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_DWORD *)this + 52) = 0;
  *((_QWORD *)this + 24) = 0;
  return this;
}

```

## disassembly

```asm
0x180008970  mov     [rsp+arg_8], rbx
0x180008975  mov     [rsp+arg_10], rsi
0x18000897a  push    rdi
0x18000897b  sub     rsp, 50h
0x18000897f  mov     rax, cs:__security_cookie
0x180008986  xor     rax, rsp
0x180008989  mov     [rsp+58h+var_10], rax
0x18000898e  mov     rdi, rdx
0x180008991  mov     rbx, rcx
0x180008994  mov     [rsp+58h+var_28], rcx
0x180008999  xor     esi, esi
0x18000899b  mov     [rcx+20h], rsi
0x18000899f  mov     [rcx+28h], rsi
0x1800089a3  mov     [rcx+30h], rsi
0x1800089a7  mov     [rcx+40h], rsi
0x1800089ab  mov     [rcx+64h], rsi
0x1800089af  mov     [rcx+80h], rsi
0x1800089b6  add     rcx, 88h
0x1800089bd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800089c2  mov     [rbx+90h], rsi
0x1800089c9  mov     dword ptr [rbx+98h], 80004005h
0x1800089d3  mov     [rbx+0A0h], rsi
0x1800089da  mov     [rbx+0A8h], rsi
0x1800089e1  xorps   xmm0, xmm0
0x1800089e4  movups  xmmword ptr [rbx+0B0h], xmm0
0x1800089eb  lea     rcx, [rbx+0E0h]
0x1800089f2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800089f7  nop
0x1800089f8  lea     rcx, [rbx+0F0h]
0x1800089ff  call    ??0?$queue@HV?$deque@HV?$allocator@H@std@@@std@@@std@@QEAA@XZ; std::queue<int>::queue<int,std::deque<int>>(void)
0x180008a04  nop
0x180008a05  lea     rcx, [rbx+118h]
0x180008a0c  call    ??0?$list@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAA@XZ; std::list<ProblemNode *>::list<ProblemNode *>(void)
0x180008a11  nop
0x180008a12  lea     rcx, [rbx+128h]
0x180008a19  call    ??0?$list@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAA@XZ; std::list<ProblemNode *>::list<ProblemNode *>(void)
0x180008a1e  nop
0x180008a1f  test    cs:byte_180041BC1, 2
0x180008a26  jz      short loc_180008A42
0x180008a28  lea     rax, [rsp+58h+var_20]
0x180008a2d  mov     [rsp+58h+var_38], rax
0x180008a32  lea     r9d, [rsi+1]
0x180008a36  lea     rdx, StartNDFIncident
0x180008a3d  call    McGenEventWrite_EventWriteTransfer
0x180008a42  mov     [rbx+50h], rdi
0x180008a46  mov     [rbx+18h], esi
0x180008a49  mov     [rbx+58h], esi
0x180008a4c  mov     [rbx+10h], rsi
0x180008a50  lea     rcx, [rbx+138h]; lpCriticalSection
0x180008a57  call    cs:__imp_InitializeCriticalSection
0x180008a5d  xor     r9d, r9d; lpName
0x180008a60  xor     r8d, r8d; bInitialState
0x180008a63  lea     edx, [r9+1]; bManualReset
0x180008a67  xor     ecx, ecx; lpEventAttributes
0x180008a69  call    cs:__imp_CreateEventW
0x180008a6f  mov     [rbx+48h], rax
0x180008a73  mov     [rbx+5Ch], si
0x180008a77  mov     [rbx+60h], rsi
0x180008a7b  mov     [rbx+160h], esi
0x180008a81  mov     [rbx+68h], rsi
0x180008a85  mov     [rbx+70h], esi
0x180008a88  mov     [rbx+0D8h], rsi
0x180008a8f  call    ?Instance@NetworkDiagnosticsEngine@@SAPEAV1@XZ; NetworkDiagnosticsEngine::Instance(void)
0x180008a94  test    rax, rax
0x180008a97  jz      short loc_180008AA3
0x180008a99  mov     rcx, [rax]
0x180008a9c  mov     [rbx+0D8h], rcx
0x180008aa3  mov     [rbx+78h], rsi
0x180008aa7  mov     [rbx+0E8h], esi
0x180008aad  mov     [rbx+0C8h], rsi
0x180008ab4  mov     [rbx+0D0h], esi
0x180008aba  mov     [rbx+0C0h], rsi
0x180008ac1  mov     rax, rbx
0x180008ac4  mov     rcx, [rsp+58h+var_10]
0x180008ac9  xor     rcx, rsp; StackCookie
0x180008acc  call    __security_check_cookie
0x180008ad1  mov     rbx, [rsp+58h+arg_8]
0x180008ad6  mov     rsi, [rsp+58h+arg_10]
0x180008adb  add     rsp, 50h
0x180008adf  pop     rdi
0x180008ae0  retn
```
