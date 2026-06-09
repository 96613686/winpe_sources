# CDSLink::CDSLink(void)

- ea: `0x18000eea0`
- end: `0x18000ef7c`
- name: `??0CDSLink@@QEAA@XZ`
- size: `220`
- prototype: `CDSLink *__fastcall(CDSLink *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000e7c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000ef00`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000ef00`

## pseudocode

```c
CDSLink *__fastcall CDSLink::CDSLink(CDSLink *this)
{
  CDSLink *result; // rax

  *((_DWORD *)this + 10) = 1;
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &CDSLink::`vftable'{for `IDirectMusicSynthSink'};
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 1) = &CDSLink::`vftable'{for `IKsControl'};
  *((_QWORD *)this + 4) = &CClock::`vftable';
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = 0;
  *((_DWORD *)this + 19) = 22050;
  _InterlockedIncrement(&g_cComponent);
  *((_DWORD *)this + 44) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  *((_DWORD *)this + 44) = 1;
  *(_OWORD *)((char *)this + 84) = 0;
  *((_WORD *)this + 50) = 0;
  result = this;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 20) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 27) = 1000;
  *((_QWORD *)this + 23) = 0;
  *((_DWORD *)this + 48) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_DWORD *)this + 10) = 1;
  *((_DWORD *)this + 56) = 0;
  return result;
}

```

## disassembly

```asm
0x18000eea0  mov     [rsp+arg_0], rbx
0x18000eea5  push    rdi
0x18000eea6  sub     rsp, 20h
0x18000eeaa  xor     edi, edi
0x18000eeac  mov     dword ptr [rcx+28h], 1
0x18000eeb3  lea     rax, ??_7CDSLink@@6BIDirectMusicSynthSink@@@; const CDSLink::`vftable'{for `IDirectMusicSynthSink'}
0x18000eeba  mov     [rcx+10h], rdi
0x18000eebe  mov     [rcx], rax
0x18000eec1  mov     rbx, rcx
0x18000eec4  lea     rax, ??_7CDSLink@@6BIKsControl@@@; const CDSLink::`vftable'{for `IKsControl'}
0x18000eecb  mov     [rcx+30h], rdi
0x18000eecf  mov     [rcx+8], rax
0x18000eed3  lea     rax, ??_7CClock@@6B@; const CClock::`vftable'
0x18000eeda  mov     [rcx+20h], rax
0x18000eede  mov     [rcx+40h], rdi
0x18000eee2  mov     [rcx+48h], edi
0x18000eee5  mov     dword ptr [rcx+4Ch], 5622h
0x18000eeec  lock inc cs:?g_cComponent@@3JA; long g_cComponent
0x18000eef3  mov     [rcx+0B0h], edi
0x18000eef9  add     rcx, 88h; lpCriticalSection
0x18000ef00  call    cs:__imp_InitializeCriticalSection
0x18000ef06  mov     dword ptr [rbx+0B0h], 1
0x18000ef10  xor     eax, eax
0x18000ef12  xorps   xmm0, xmm0
0x18000ef15  movups  xmmword ptr [rbx+54h], xmm0
0x18000ef19  mov     [rbx+64h], ax
0x18000ef1d  mov     rax, rbx
0x18000ef20  mov     [rbx+38h], rdi
0x18000ef24  mov     [rbx+50h], edi
0x18000ef27  mov     [rbx+18h], rdi
0x18000ef2b  mov     [rbx+68h], rdi
0x18000ef2f  mov     [rbx+70h], rdi
0x18000ef33  mov     [rbx+78h], rdi
0x18000ef37  mov     [rbx+80h], rdi
0x18000ef3e  mov     qword ptr [rbx+0D8h], 3E8h
0x18000ef49  mov     [rbx+0B8h], rdi
0x18000ef50  mov     [rbx+0C0h], edi
0x18000ef56  mov     [rbx+0C8h], rdi
0x18000ef5d  mov     [rbx+0D0h], rdi
0x18000ef64  mov     dword ptr [rbx+28h], 1
0x18000ef6b  mov     [rbx+0E0h], edi
0x18000ef71  mov     rbx, [rsp+28h+arg_0]
0x18000ef76  add     rsp, 20h
0x18000ef7a  pop     rdi
0x18000ef7b  retn
```
