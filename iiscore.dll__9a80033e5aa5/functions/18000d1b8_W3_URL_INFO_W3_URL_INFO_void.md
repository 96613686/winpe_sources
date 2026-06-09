# W3_URL_INFO::W3_URL_INFO(void)

- ea: `0x18000d1b8`
- end: `0x18000d337`
- name: `??0W3_URL_INFO@@QEAA@XZ`
- size: `383`
- prototype: `W3_URL_INFO *__fastcall(W3_URL_INFO *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002bf0`
- `0x1800095d0`
- `0x18000c2e0`
- `0x180020e20`

## callees

- `0x18000d848`
- `0x18003439a`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000d231`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000d231`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000d2db`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000d2db`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18000d296`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18000d296`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000d25f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000d25f`

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
0x18000d1b8  mov     [rsp+arg_0], rbx
0x18000d1bd  push    rdi
0x18000d1be  sub     rsp, 20h
0x18000d1c2  lea     rax, ??_7IHttpUrlInfo@@6B@; const IHttpUrlInfo::`vftable'
0x18000d1c9  mov     rdi, rcx
0x18000d1cc  mov     [rcx], rax
0x18000d1cf  lea     rax, ??_7IHttpCacheSpecificData@@6B@; const IHttpCacheSpecificData::`vftable'
0x18000d1d6  mov     [rcx+8], rax
0x18000d1da  add     rcx, 10h; this
0x18000d1de  call    ??0W3_URL_INFO_KEY@@QEAA@XZ; W3_URL_INFO_KEY::W3_URL_INFO_KEY(void)
0x18000d1e3  lea     rax, ??_7W3_URL_INFO@@6BIHttpUrlInfo@@@; const W3_URL_INFO::`vftable'{for `IHttpUrlInfo'}
0x18000d1ea  mov     dword ptr [rdi+200h], 494C5255h
0x18000d1f4  mov     [rdi], rax
0x18000d1f7  xor     ebx, ebx
0x18000d1f9  lea     rax, ??_7W3_URL_INFO@@6BIHttpCacheSpecificData@@@; const W3_URL_INFO::`vftable'{for `IHttpCacheSpecificData'}
0x18000d200  mov     qword ptr [rdi+204h], 1
0x18000d20b  mov     [rdi+8], rax
0x18000d20f  lea     rax, ??_7W3_URL_INFO@@6BW3_URL_INFO_KEY@@@; const W3_URL_INFO::`vftable'{for `W3_URL_INFO_KEY'}
0x18000d216  mov     [rdi+10h], rax
0x18000d21a  mov     dword ptr [rdi+20Ch], 2
0x18000d224  mov     [rdi+240h], rbx
0x18000d22b  mov     [rdi+248h], ebx
0x18000d231  call    cs:__imp_GetTickCount
0x18000d237  lea     rdx, [rdi+298h]
0x18000d23e  mov     [rdi+250h], rbx
0x18000d245  lea     rcx, [rdi+260h]
0x18000d24c  mov     [rdi+24Ch], eax
0x18000d252  mov     r8d, 94h
0x18000d258  mov     [rdi+258h], rbx
0x18000d25f  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000d265  lea     rax, ??_7CONTEXT_CONTAINER@@6BIDispensedHttpModuleContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `IDispensedHttpModuleContextContainer'}
0x18000d26c  mov     [rdi+4B8h], rax
0x18000d273  lea     rcx, [rdi+4D0h]
0x18000d27a  lea     rax, ??_7CONTEXT_CONTAINER@@6BIHttpConnectionModuleContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `IHttpConnectionModuleContextContainer'}
0x18000d281  mov     [rdi+4C0h], rax
0x18000d288  lea     rax, ??_7CONTEXT_CONTAINER@@6BINamedContextContainer@@@; const CONTEXT_CONTAINER::`vftable'{for `INamedContextContainer'}
0x18000d28f  mov     [rdi+4C8h], rax
0x18000d296  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x18000d29c  mov     [rdi+4D8h], rbx
0x18000d2a3  lea     rcx, [rdi+3C0h]; SRWLock
0x18000d2aa  mov     [rdi+4E0h], rbx
0x18000d2b1  mov     [rdi+4E8h], ebx
0x18000d2b7  mov     word ptr [rdi+4ECh], 1
0x18000d2c0  mov     [rdi+4EEh], bl
0x18000d2c6  mov     [rdi+4F0h], rbx
0x18000d2cd  mov     [rdi+4F8h], rbx
0x18000d2d4  mov     [rdi+500h], rbx
0x18000d2db  call    cs:__imp_InitializeSRWLock
0x18000d2e1  xorps   xmm0, xmm0
0x18000d2e4  lea     rcx, [rdi+418h]; void *
0x18000d2eb  movups  xmmword ptr [rdi+3C8h], xmm0
0x18000d2f2  xor     eax, eax
0x18000d2f4  xor     edx, edx; Val
0x18000d2f6  mov     [rdi+3D8h], eax
0x18000d2fc  mov     r8d, 0A0h; Size
0x18000d302  movups  xmmword ptr [rdi+3DCh], xmm0
0x18000d309  mov     [rdi+3ECh], eax
0x18000d30f  movups  xmmword ptr [rdi+3F0h], xmm0
0x18000d316  movups  xmmword ptr [rdi+400h], xmm0
0x18000d31d  mov     [rdi+410h], rax
0x18000d324  call    memset_0
0x18000d329  mov     rbx, [rsp+28h+arg_0]
0x18000d32e  mov     rax, rdi
0x18000d331  add     rsp, 20h
0x18000d335  pop     rdi
0x18000d336  retn
```
