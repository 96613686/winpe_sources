# CACHED_FILE_INFO::GetModuleContextContainer(void)

- ea: `0x1800024a0`
- end: `0x180002504`
- name: `?GetModuleContextContainer@CACHED_FILE_INFO@@UEAAPEAVIHttpModuleContextContainer@@XZ`
- size: `100`
- prototype: `struct IHttpModuleContextContainer *__fastcall(CACHED_FILE_INFO *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800024a0`
- `0x180004010`

## pseudocode

```c
struct IHttpModuleContextContainer *__fastcall CACHED_FILE_INFO::GetModuleContextContainer(CACHED_FILE_INFO *this)
{
  signed __int64 v3; // rdx

  if ( *((_QWORD *)this + 103) )
    return (struct IHttpModuleContextContainer *)*((_QWORD *)this + 103);
  v3 = (*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 128LL))(g_pGlobalInfo);
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 103, v3, 0) )
    (*(void (__fastcall **)(signed __int64))(*(_QWORD *)v3 + 16LL))(v3);
  return (struct IHttpModuleContextContainer *)*((_QWORD *)this + 103);
}

```

## disassembly

```asm
0x1800024a0  push    rbx
0x1800024a2  sub     rsp, 20h
0x1800024a6  cmp     qword ptr [rcx+338h], 0
0x1800024ae  mov     rbx, rcx
0x1800024b1  jz      short loc_1800024C0
0x1800024b3  mov     rax, [rcx+338h]
0x1800024ba  add     rsp, 20h
0x1800024be  pop     rbx
0x1800024bf  retn
0x1800024c0  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800024c7  mov     rax, [rcx]
0x1800024ca  mov     rax, [rax+80h]
0x1800024d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024d6  mov     rdx, rax
0x1800024d9  xor     eax, eax
0x1800024db  lock cmpxchg [rbx+338h], rdx
0x1800024e4  jnz     short loc_1800024F3
0x1800024e6  mov     rax, [rbx+338h]
0x1800024ed  add     rsp, 20h
0x1800024f1  pop     rbx
0x1800024f2  retn
0x1800024f3  mov     rcx, [rdx]
0x1800024f6  mov     rax, [rcx+10h]
0x1800024fa  mov     rcx, rdx
0x1800024fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002502  jmp     short loc_1800024E6
```
