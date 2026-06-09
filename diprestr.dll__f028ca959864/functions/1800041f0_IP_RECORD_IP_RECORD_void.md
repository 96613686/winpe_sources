# IP_RECORD::~IP_RECORD(void)

- ea: `0x1800041f0`
- end: `0x1800042b3`
- name: `??1IP_RECORD@@UEAA@XZ`
- size: `195`
- prototype: `void __fastcall(IP_RECORD *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800043d0`

## callees

- `0x1800041f0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000424e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000428a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000424e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000428a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000421d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000421d`

## pseudocode

```c
void __fastcall IP_RECORD::~IP_RECORD(IP_RECORD *this)
{
  bool v1; // zf
  char *v3; // rcx
  char *v4; // rcx

  v1 = *((_DWORD *)this + 72) == 0;
  *(_QWORD *)this = &IP_RECORD::`vftable';
  if ( !v1 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 248));
    *((_DWORD *)this + 72) = 0;
  }
  v3 = (char *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 16) = &STBUFF::`vftable';
  if ( v3 != (char *)this + 156 )
  {
    LocalFree(v3);
    *((_QWORD *)this + 17) = (char *)this + 156;
    *((_DWORD *)this + 37) = 64;
  }
  *((_DWORD *)this + 36) = 0;
  *(_QWORD *)this = &STTABLE_ITEM::`vftable';
  v4 = (char *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 4) = &STBUFF::`vftable';
  if ( v4 != (char *)this + 60 )
  {
    LocalFree(v4);
    *((_QWORD *)this + 5) = (char *)this + 60;
    *((_DWORD *)this + 13) = 64;
  }
  *((_DWORD *)this + 12) = 0;
}

```

## disassembly

```asm
0x1800041f0  mov     [rsp+arg_0], rbx
0x1800041f5  mov     [rsp+arg_8], rdi
0x1800041fa  push    r14
0x1800041fc  sub     rsp, 20h
0x180004200  cmp     dword ptr [rcx+120h], 0
0x180004207  lea     rax, ??_7IP_RECORD@@6B@; const IP_RECORD::`vftable'
0x18000420e  mov     [rcx], rax
0x180004211  mov     rbx, rcx
0x180004214  jz      short loc_18000422D
0x180004216  add     rcx, 0F8h; lpCriticalSection
0x18000421d  call    cs:__imp_DeleteCriticalSection
0x180004223  mov     dword ptr [rbx+120h], 0
0x18000422d  mov     rcx, [rbx+88h]; hMem
0x180004234  lea     rdi, [rbx+9Ch]
0x18000423b  lea     r14, ??_7STBUFF@@6B@; const STBUFF::`vftable'
0x180004242  mov     [rbx+80h], r14
0x180004249  cmp     rcx, rdi
0x18000424c  jz      short loc_180004265
0x18000424e  call    cs:__imp_LocalFree
0x180004254  mov     [rbx+88h], rdi
0x18000425b  mov     dword ptr [rbx+94h], 40h ; '@'
0x180004265  mov     dword ptr [rbx+90h], 0
0x18000426f  lea     rax, ??_7STTABLE_ITEM@@6B@; const STTABLE_ITEM::`vftable'
0x180004276  mov     [rbx], rax
0x180004279  lea     rdi, [rbx+3Ch]
0x18000427d  mov     rcx, [rbx+28h]; hMem
0x180004281  mov     [rbx+20h], r14
0x180004285  cmp     rcx, rdi
0x180004288  jz      short loc_18000429B
0x18000428a  call    cs:__imp_LocalFree
0x180004290  mov     [rbx+28h], rdi
0x180004294  mov     dword ptr [rbx+34h], 40h ; '@'
0x18000429b  mov     rdi, [rsp+28h+arg_8]
0x1800042a0  mov     dword ptr [rbx+30h], 0
0x1800042a7  mov     rbx, [rsp+28h+arg_0]
0x1800042ac  add     rsp, 20h
0x1800042b0  pop     r14
0x1800042b2  retn
```
