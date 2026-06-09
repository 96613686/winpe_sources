# W3_URL_INFO::W3_URL_INFO(void)

- ea: `0x18000e220`
- end: `0x18000e3b8`
- name: `??0W3_URL_INFO@@QEAA@XZ`
- size: `408`
- prototype: `W3_URL_INFO *__fastcall(W3_URL_INFO *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002db0`
- `0x180009e50`
- `0x18000d260`
- `0x180022a10`

## callees

- `0x18000e3c0`
- `0x18003773a`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000e299`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000e299`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000e355`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000e355`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18000e30a`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18000e30a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000e2cd`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000e2cd`

## pseudocode

```c
W3_URL_INFO *__fastcall W3_URL_INFO::W3_URL_INFO(W3_URL_INFO *this)
{
  DWORD TickCount; // eax

  *(_QWORD *)this = &IHttpUrlInfo::`vftable';
  *((_QWORD *)this + 1) = &IHttpCacheSpecificData::`vftable';
  W3_URL_INFO_KEY::W3_URL_INFO_KEY((W3_URL_INFO *)((char *)this + 16));
  *((_DWORD *)this + 128) = 1229738581;
  *(_QWORD *)this = &W3_URL_INFO::`vftable'{for `IHttpUrlInfo'};
  *(_QWORD *)((char *)this + 516) = 1;
  *((_QWORD *)this + 1) = &W3_URL_INFO::`vftable'{for `IHttpCacheSpecificData'};
  *((_QWORD *)this + 2) = &W3_URL_INFO::`vftable'{for `W3_URL_INFO_KEY'};
  *((_DWORD *)this + 131) = 2;
  *((_QWORD *)this + 72) = 0;
  *((_DWORD *)this + 146) = 0;
  TickCount = GetTickCount();
  *((_QWORD *)this + 74) = 0;
  *((_DWORD *)this + 147) = TickCount;
  *((_QWORD *)this + 75) = 0;
  STRU::STRU((W3_URL_INFO *)((char *)this + 608), (unsigned __int16 *)this + 332, 0x94u);
  *((_QWORD *)this + 151) = &CONTEXT_CONTAINER::`vftable'{for `IDispensedHttpModuleContextContainer'};
  *((_QWORD *)this + 152) = &CONTEXT_CONTAINER::`vftable'{for `IHttpConnectionModuleContextContainer'};
  *((_QWORD *)this + 153) = &CONTEXT_CONTAINER::`vftable'{for `INamedContextContainer'};
  CReaderWriterLock3::CReaderWriterLock3((W3_URL_INFO *)((char *)this + 1232));
  *((_QWORD *)this + 155) = 0;
  *((_QWORD *)this + 156) = 0;
  *((_DWORD *)this + 314) = 0;
  *((_WORD *)this + 630) = 1;
  *((_BYTE *)this + 1262) = 0;
  *((_QWORD *)this + 158) = 0;
  *((_QWORD *)this + 159) = 0;
  *((_QWORD *)this + 160) = 0;
  InitializeSRWLock((PSRWLOCK)this + 120);
  *(_OWORD *)((char *)this + 968) = 0;
  *((_DWORD *)this + 246) = 0;
  *(_OWORD *)((char *)this + 988) = 0;
  *((_DWORD *)this + 251) = 0;
  *((_OWORD *)this + 63) = 0;
  *((_OWORD *)this + 64) = 0;
  *((_QWORD *)this + 130) = 0;
  memset_0((char *)this + 1048, 0, 0xA0u);
  return this;
}

```

## disassembly

```asm
0x18000e220  mov     [rsp+arg_0], rbx
0x18000e225  push    rdi
0x18000e226  sub     rsp, 20h
0x18000e22a  lea     rax, ??_7IHttpUrlInfo@@6B@; const IHttpUrlInfo::`vftable'
0x18000e231  mov     rdi, rcx
0x18000e234  mov     [rcx], rax
0x18000e237  lea     rax, ??_7IHttpCacheSpecificData@@6B@; const IHttpCacheSpecificData::`vftable'
0x18000e23e  mov     [rcx+8], rax
0x18000e242  add     rcx, 10h; this
0x18000e246  call    ??0W3_URL_INFO_KEY@@QEAA@XZ; W3_URL_INFO_KEY::W3_URL_INFO_KEY(void)
0x18000e24b  lea     rax, ??_7W3_URL_INFO@@6BIHttpUrlInfo@@@; const W3_URL_INFO::`vftable'{for `IHttpUrlInfo'}
0x18000e252  mov     dword ptr [rdi+200h], 494C5255h
0x18000e25c  mov     [rdi], rax
0x18000e25f  xor     ebx, ebx
0x18000e261  lea     rax, ??_7W3_URL_INFO@@6BIHttpCacheSpecificData@@@; const W3_URL_INFO::`vftable'{for `IHttpCacheSpecificData'}
0x18000e268  mov     qword ptr [rdi+204h], 1
0x18000e273  mov     [rdi+8], rax
0x18000e277  lea     rax, ??_7W3_URL_INFO@@6BW3_URL_INFO_KEY@@@; const W3_URL_INFO::`vftable'{for `W3_URL_INFO_KEY'}
0x18000e27e  mov     [rdi+10h], rax
0x18000e282  mov     dword ptr [rdi+20Ch], 2
0x18000e28c  mov     [rdi+240h], rbx
0x18000e293  mov     [rdi+248h], ebx
0x18000e299  call    cs:__imp_GetTickCount
0x18000e2a0  nop     dword ptr [rax+rax+00h]
0x18000e2a5  lea     rdx, [rdi+298h]
0x18000e2ac  mov     [rdi+250h], rbx
0x18000e2b3  lea     rcx, [rdi+260h]
0x18000e2ba  mov     [rdi+24Ch], eax
0x18000e2c0  mov     r8d, 94h
0x18000e2c6  mov     [rdi+258h], rbx
0x18000e2cd  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000e2d4  nop     dword ptr [rax+rax+00h]
0x18000e2d9  lea     rax, ??_7CONTEXT_CONTAINER@@6BIDispensedHttpModuleContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `IDispensedHttpModuleContextContainer'}
0x18000e2e0  mov     [rdi+4B8h], rax
0x18000e2e7  lea     rcx, [rdi+4D0h]
0x18000e2ee  lea     rax, ??_7CONTEXT_CONTAINER@@6BIHttpConnectionModuleContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `IHttpConnectionModuleContextContainer'}
0x18000e2f5  mov     [rdi+4C0h], rax
0x18000e2fc  lea     rax, ??_7CONTEXT_CONTAINER@@6BINamedContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `INamedContextContainer'}
0x18000e303  mov     [rdi+4C8h], rax
0x18000e30a  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x18000e311  nop     dword ptr [rax+rax+00h]
0x18000e316  mov     [rdi+4D8h], rbx
0x18000e31d  lea     rcx, [rdi+3C0h]; SRWLock
0x18000e324  mov     [rdi+4E0h], rbx
0x18000e32b  mov     [rdi+4E8h], ebx
0x18000e331  mov     word ptr [rdi+4ECh], 1
0x18000e33a  mov     [rdi+4EEh], bl
0x18000e340  mov     [rdi+4F0h], rbx
0x18000e347  mov     [rdi+4F8h], rbx
0x18000e34e  mov     [rdi+500h], rbx
0x18000e355  call    cs:__imp_InitializeSRWLock
0x18000e35c  nop     dword ptr [rax+rax+00h]
0x18000e361  xorps   xmm0, xmm0
0x18000e364  lea     rcx, [rdi+418h]; void *
0x18000e36b  movups  xmmword ptr [rdi+3C8h], xmm0
0x18000e372  xor     eax, eax
0x18000e374  xor     edx, edx; Val
0x18000e376  mov     [rdi+3D8h], eax
0x18000e37c  mov     r8d, 0A0h; Size
0x18000e382  movups  xmmword ptr [rdi+3DCh], xmm0
0x18000e389  mov     [rdi+3ECh], eax
0x18000e38f  movups  xmmword ptr [rdi+3F0h], xmm0
0x18000e396  movups  xmmword ptr [rdi+400h], xmm0
0x18000e39d  mov     [rdi+410h], rax
0x18000e3a4  call    memset_0
0x18000e3a9  mov     rbx, [rsp+28h+arg_0]
0x18000e3ae  mov     rax, rdi
0x18000e3b1  add     rsp, 20h
0x18000e3b5  pop     rdi
0x18000e3b6  retn
```
