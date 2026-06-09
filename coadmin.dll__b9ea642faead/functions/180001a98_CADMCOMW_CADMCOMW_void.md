# CADMCOMW::CADMCOMW(void)

- ea: `0x180001a98`
- end: `0x180001bcb`
- name: `??0CADMCOMW@@QEAA@XZ`
- size: `307`
- prototype: `CADMCOMW *__fastcall(CADMCOMW *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180009dd0`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180001bb7`
- `KERNEL32!InitializeCriticalSection` at `0x180001bb7`
- `IisRTL!??0STRU@@QEAA@XZ` at `0x180001afa`
- `IisRTL!??0STRU@@QEAA@XZ` at `0x180001afa`

## pseudocode

```c
CADMCOMW *__fastcall CADMCOMW::CADMCOMW(CADMCOMW *this)
{
  *((_DWORD *)this + 10) = 1;
  *(_QWORD *)((char *)this + 12) = 0;
  *(_QWORD *)this = &CADMCOMW::`vftable';
  *((_DWORD *)this + 2) = 1;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 24) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_DWORD *)this + 42) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_DWORD *)this + 48) = 0;
  STRU::STRU((CADMCOMW *)((char *)this + 200));
  *(_QWORD *)((char *)this + 772) = 1;
  *((_QWORD *)this + 98) = &CADMCOMW::CImpExpHelp::`vftable';
  *((_DWORD *)this + 200) = 0;
  *((_DWORD *)this + 201) = 0;
  *((_QWORD *)this + 101) = CADMCOMW::s_pAboWrapper;
  *((_QWORD *)this + 102) = &CADMCOMW::CImpIConnectionPointContainer::`vftable';
  *((_QWORD *)this + 105) = &COConnectionPoint::`vftable';
  *((_DWORD *)this + 212) = 0;
  *((_DWORD *)this + 213) = 0;
  *((_QWORD *)this + 107) = 0;
  *((_QWORD *)this + 108) = 0;
  *((_QWORD *)this + 109) = 0;
  *((_DWORD *)this + 220) = 0;
  *((_DWORD *)this + 221) = 1;
  *((_QWORD *)this + 111) = 0;
  *((_DWORD *)this + 224) = 0;
  *((_OWORD *)this + 3) = 0;
  *((_OWORD *)this + 4) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 19) = (char *)this + 144;
  *((_QWORD *)this + 18) = (char *)this + 144;
  *((_WORD *)this + 128) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  return this;
}

```

## disassembly

```asm
0x180001a98  mov     [rsp+arg_0], rbx
0x180001a9d  push    rsi
0x180001a9e  sub     rsp, 20h
0x180001aa2  xor     esi, esi
0x180001aa4  mov     dword ptr [rcx+28h], 1
0x180001aab  lea     rax, ??_7CADMCOMW@@6B@; const CADMCOMW::`vftable'
0x180001ab2  mov     [rcx+0Ch], rsi
0x180001ab6  mov     [rcx], rax
0x180001ab9  mov     rbx, rcx
0x180001abc  mov     dword ptr [rcx+8], 1
0x180001ac3  mov     [rcx+18h], rsi
0x180001ac7  mov     [rcx+20h], rsi
0x180001acb  mov     [rcx+58h], rsi
0x180001acf  mov     [rcx+60h], esi
0x180001ad2  mov     [rcx+0A0h], rsi
0x180001ad9  mov     [rcx+0A8h], esi
0x180001adf  mov     [rcx+0B0h], rsi
0x180001ae6  mov     [rcx+0B8h], rsi
0x180001aed  mov     [rcx+0C0h], esi
0x180001af3  add     rcx, 0C8h
0x180001afa  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180001b00  mov     qword ptr [rbx+304h], 1
0x180001b0b  lea     rax, ??_7CImpExpHelp@CADMCOMW@@6B@; const CADMCOMW::CImpExpHelp::`vftable'
0x180001b12  mov     [rbx+310h], rax
0x180001b19  lea     rcx, [rbx+68h]; lpCriticalSection
0x180001b1d  mov     [rbx+320h], esi
0x180001b23  xorps   xmm0, xmm0
0x180001b26  mov     [rbx+324h], esi
0x180001b2c  mov     rax, cs:?s_pAboWrapper@CADMCOMW@@0PEAVIAboWrapper@@EA; IAboWrapper * CADMCOMW::s_pAboWrapper
0x180001b33  mov     [rbx+328h], rax
0x180001b3a  lea     rax, ??_7CImpIConnectionPointContainer@CADMCOMW@@6B@; const CADMCOMW::CImpIConnectionPointContainer::`vftable'
0x180001b41  mov     [rbx+330h], rax
0x180001b48  lea     rax, ??_7COConnectionPoint@@6B@; const COConnectionPoint::`vftable'
0x180001b4f  mov     [rbx+348h], rax
0x180001b56  xor     eax, eax
0x180001b58  mov     [rbx+350h], esi
0x180001b5e  mov     [rbx+354h], esi
0x180001b64  mov     [rbx+358h], rsi
0x180001b6b  mov     [rbx+360h], rsi
0x180001b72  mov     [rbx+368h], rsi
0x180001b79  mov     [rbx+370h], esi
0x180001b7f  mov     dword ptr [rbx+374h], 1
0x180001b89  mov     [rbx+378h], rsi
0x180001b90  mov     [rbx+380h], esi
0x180001b96  movups  xmmword ptr [rbx+30h], xmm0
0x180001b9a  movups  xmmword ptr [rbx+40h], xmm0
0x180001b9e  mov     [rbx+50h], rax
0x180001ba2  lea     rax, [rbx+90h]
0x180001ba9  mov     [rax+8], rax
0x180001bad  mov     [rax], rax
0x180001bb0  mov     [rbx+100h], si
0x180001bb7  call    cs:__imp_InitializeCriticalSection
0x180001bbd  mov     rax, rbx
0x180001bc0  mov     rbx, [rsp+28h+arg_0]
0x180001bc5  add     rsp, 20h
0x180001bc9  pop     rsi
0x180001bca  retn
```
