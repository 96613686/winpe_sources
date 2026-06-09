# CONFIG_CACHE::CONFIG_CACHE(void)

- ea: `0x18004cdfc`
- end: `0x18004cf4d`
- name: `??0CONFIG_CACHE@@QEAA@XZ`
- size: `337`
- prototype: `CONFIG_CACHE *__fastcall(CONFIG_CACHE *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18001e1c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18004cea6`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18004cea6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004cf14`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004cf14`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18004ce71`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18004cec1`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18004ce71`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18004cec1`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18004ce34`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18004ce41`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18004ce34`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18004ce41`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18004ce2a`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18004ce2a`

## pseudocode

```c
CONFIG_CACHE *__fastcall CONFIG_CACHE::CONFIG_CACHE(CONFIG_CACHE *this)
{
  CONFIG_CACHE *result; // rax

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 10) = 0;
  MULTISZ::MULTISZ((CONFIG_CACHE *)((char *)this + 64));
  STRU::STRU((CONFIG_CACHE *)((char *)this + 120));
  STRU::STRU((CONFIG_CACHE *)((char *)this + 176));
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  CReaderWriterLock3::CReaderWriterLock3((CONFIG_CACHE *)((char *)this + 272));
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 41) = 0;
  *((_DWORD *)this + 84) = 0;
  *((_DWORD *)this + 85) = 0;
  InitializeSRWLock((PSRWLOCK)this + 36);
  *((_QWORD *)this + 38) = (char *)this + 296;
  *((_QWORD *)this + 37) = (char *)this + 296;
  CReaderWriterLock3::CReaderWriterLock3((CONFIG_CACHE *)((char *)this + 344));
  *((_DWORD *)this + 96) &= 0xFFFFFFF0;
  *((_QWORD *)this + 44) = (char *)this + 388;
  *((_DWORD *)this + 94) = -1;
  *((_DWORD *)this + 95) = -1;
  *((_QWORD *)this + 45) = 0;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 97) = 0;
  *((_QWORD *)this + 98) = 0;
  *((_QWORD *)this + 99) = 0;
  *((_DWORD *)this + 200) = 0;
  *((_DWORD *)this + 202) = GetTickCount();
  result = this;
  *(_QWORD *)((char *)this + 812) = 0;
  *((_DWORD *)this + 205) = 0;
  *((_QWORD *)this + 103) = 0;
  *((_DWORD *)this + 208) = 0;
  return result;
}

```

## disassembly

```asm
0x18004cdfc  mov     [rsp+arg_0], rbx
0x18004ce01  mov     [rsp+arg_8], rsi
0x18004ce06  push    rdi
0x18004ce07  sub     rsp, 20h
0x18004ce0b  xor     esi, esi
0x18004ce0d  mov     rdi, rcx
0x18004ce10  mov     [rcx], rsi
0x18004ce13  mov     [rcx+8], rsi
0x18004ce17  mov     [rcx+10h], rsi
0x18004ce1b  mov     [rcx+18h], rsi
0x18004ce1f  mov     [rcx+20h], rsi
0x18004ce23  mov     [rcx+28h], esi
0x18004ce26  add     rcx, 40h ; '@'
0x18004ce2a  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x18004ce30  lea     rcx, [rdi+78h]
0x18004ce34  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18004ce3a  lea     rcx, [rdi+0B0h]
0x18004ce41  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18004ce47  lea     rcx, [rdi+110h]
0x18004ce4e  mov     [rdi+0E8h], rsi
0x18004ce55  mov     [rdi+0F0h], rsi
0x18004ce5c  mov     [rdi+0F8h], rsi
0x18004ce63  mov     [rdi+100h], rsi
0x18004ce6a  mov     [rdi+108h], rsi
0x18004ce71  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x18004ce77  mov     [rdi+118h], rsi
0x18004ce7e  lea     rcx, [rdi+120h]; SRWLock
0x18004ce85  mov     [rdi+138h], rsi
0x18004ce8c  mov     [rdi+140h], rsi
0x18004ce93  mov     [rdi+148h], rsi
0x18004ce9a  mov     [rdi+150h], esi
0x18004cea0  mov     [rdi+154h], esi
0x18004cea6  call    cs:__imp_InitializeSRWLock
0x18004ceac  lea     rax, [rdi+128h]
0x18004ceb3  lea     rcx, [rdi+158h]
0x18004ceba  mov     [rax+8], rax
0x18004cebe  mov     [rax], rax
0x18004cec1  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x18004cec7  and     dword ptr [rdi+180h], 0FFFFFFF0h
0x18004cece  lea     rax, [rdi+184h]
0x18004ced5  mov     [rdi+160h], rax
0x18004cedc  or      eax, 0FFFFFFFFh
0x18004cedf  mov     [rdi+178h], eax
0x18004cee5  mov     [rdi+17Ch], eax
0x18004ceeb  mov     [rdi+168h], rsi
0x18004cef2  mov     [rdi+170h], rsi
0x18004cef9  mov     [rdi+308h], rsi
0x18004cf00  mov     [rdi+310h], rsi
0x18004cf07  mov     [rdi+318h], rsi
0x18004cf0e  mov     [rdi+320h], esi
0x18004cf14  call    cs:__imp_GetTickCount
0x18004cf1a  mov     rbx, [rsp+28h+arg_0]
0x18004cf1f  mov     [rdi+328h], eax
0x18004cf25  mov     rax, rdi
0x18004cf28  mov     [rdi+32Ch], rsi
0x18004cf2f  mov     [rdi+334h], esi
0x18004cf35  mov     [rdi+338h], rsi
0x18004cf3c  mov     [rdi+340h], esi
0x18004cf42  mov     rsi, [rsp+28h+arg_8]
0x18004cf47  add     rsp, 20h
0x18004cf4b  pop     rdi
0x18004cf4c  retn
```
