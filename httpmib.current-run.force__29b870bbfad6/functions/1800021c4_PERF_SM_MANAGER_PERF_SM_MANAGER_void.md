# PERF_SM_MANAGER::~PERF_SM_MANAGER(void)

- ea: `0x1800021c4`
- end: `0x18000228a`
- name: `??1PERF_SM_MANAGER@@UEAA@XZ`
- size: `198`
- prototype: `void __fastcall(PERF_SM_MANAGER *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002024`
- `0x1800023a0`

## callees

- `0x180001928`
- `0x1800021c4`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180002248`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180002248`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800021e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800021fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000225f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002276`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800021e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800021fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000225f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002276`

## pseudocode

```c
void __fastcall PERF_SM_MANAGER::~PERF_SM_MANAGER(PERF_SM_MANAGER *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  const void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx

  *((_DWORD *)this + 2) = 1483566451;
  *(_QWORD *)this = &PERF_SM_MANAGER::`vftable';
  v2 = (void *)*((_QWORD *)this + 6);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 6) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 7);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 7) = 0;
  }
  v4 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 4);
  if ( v4 )
  {
    if ( *(v4 - 1) )
      (**v4)(v4, 3);
    else
      operator delete(v4 - 1);
    *((_QWORD *)this + 4) = 0;
  }
  v5 = (const void *)*((_QWORD *)this + 2);
  if ( v5 )
  {
    UnmapViewOfFile(v5);
    *((_QWORD *)this + 2) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 3);
  if ( v6 )
  {
    CloseHandle(v6);
    *((_QWORD *)this + 3) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 8);
  if ( v7 )
  {
    CloseHandle(v7);
    *((_QWORD *)this + 8) = 0;
  }
}

```

## disassembly

```asm
0x1800021c4  push    rbx
0x1800021c6  sub     rsp, 20h
0x1800021ca  lea     rax, ??_7PERF_SM_MANAGER@@6B@; const PERF_SM_MANAGER::`vftable'
0x1800021d1  mov     dword ptr [rcx+8], 586D6D73h
0x1800021d8  mov     [rcx], rax
0x1800021db  mov     rbx, rcx
0x1800021de  mov     rcx, [rcx+30h]; hObject
0x1800021e2  test    rcx, rcx
0x1800021e5  jz      short loc_1800021F5
0x1800021e7  call    cs:__imp_CloseHandle
0x1800021ed  mov     qword ptr [rbx+30h], 0
0x1800021f5  mov     rcx, [rbx+38h]; hObject
0x1800021f9  test    rcx, rcx
0x1800021fc  jz      short loc_18000220C
0x1800021fe  call    cs:__imp_CloseHandle
0x180002204  mov     qword ptr [rbx+38h], 0
0x18000220c  mov     rcx, [rbx+20h]
0x180002210  test    rcx, rcx
0x180002213  jz      short loc_18000223F
0x180002215  cmp     qword ptr [rcx-8], 0
0x18000221a  jz      short loc_18000222E
0x18000221c  mov     rax, [rcx]
0x18000221f  mov     edx, 3
0x180002224  mov     rax, [rax]
0x180002227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000222c  jmp     short loc_180002237
0x18000222e  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x180002232  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002237  mov     qword ptr [rbx+20h], 0
0x18000223f  mov     rcx, [rbx+10h]; lpBaseAddress
0x180002243  test    rcx, rcx
0x180002246  jz      short loc_180002256
0x180002248  call    cs:__imp_UnmapViewOfFile
0x18000224e  mov     qword ptr [rbx+10h], 0
0x180002256  mov     rcx, [rbx+18h]; hObject
0x18000225a  test    rcx, rcx
0x18000225d  jz      short loc_18000226D
0x18000225f  call    cs:__imp_CloseHandle
0x180002265  mov     qword ptr [rbx+18h], 0
0x18000226d  mov     rcx, [rbx+40h]; hObject
0x180002271  test    rcx, rcx
0x180002274  jz      short loc_180002284
0x180002276  call    cs:__imp_CloseHandle
0x18000227c  mov     qword ptr [rbx+40h], 0
0x180002284  add     rsp, 20h
0x180002288  pop     rbx
0x180002289  retn
```
