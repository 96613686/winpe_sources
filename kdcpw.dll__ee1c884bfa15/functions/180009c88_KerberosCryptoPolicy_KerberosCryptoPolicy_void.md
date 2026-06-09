# KerberosCryptoPolicy::~KerberosCryptoPolicy(void)

- ea: `0x180009c88`
- end: `0x180009d1a`
- name: `??1KerberosCryptoPolicy@@QEAA@XZ`
- size: `146`
- prototype: `void __fastcall(KerberosCryptoPolicy *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009d20`
- `0x180009d50`
- `0x18000af04`
- `0x18000bd80`

## callees

- `0x180009c88`
- `0x180009d20`
- `0x18000c964`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009cb4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009cc9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009cb4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009cc9`

## pseudocode

```c
void __fastcall KerberosCryptoPolicy::~KerberosCryptoPolicy(KerberosCryptoPolicy *this)
{
  void *v2; // rcx
  void *v3; // rcx
  KerberosCryptoPolicy *v4; // rdx

  if ( *((_QWORD *)this + 14) && *((_BYTE *)this + 104) )
    KerbFreeKey();
  v2 = (void *)*((_QWORD *)this + 12);
  if ( v2 && *((_BYTE *)this + 88) )
    LocalFree(v2);
  v3 = (void *)*((_QWORD *)this + 9);
  if ( v3 && *((_BYTE *)this + 64) )
    LocalFree(v3);
  v4 = (KerberosCryptoPolicy *)*((_QWORD *)this + 6);
  if ( v4 )
    utl::default_delete<KerberosCryptoPolicy>::operator()((__int64)this + 48, v4);
  if ( *((_QWORD *)this + 5) )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 64LL))(*((_QWORD *)this + 4));
  if ( *((_QWORD *)this + 3) )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 64LL))(*((_QWORD *)this + 2));
}

```

## disassembly

```asm
0x180009c88  push    rbx
0x180009c8a  sub     rsp, 20h
0x180009c8e  mov     rbx, rcx
0x180009c91  mov     rcx, [rcx+70h]
0x180009c95  test    rcx, rcx
0x180009c98  jz      short loc_180009CA5
0x180009c9a  cmp     byte ptr [rbx+68h], 0
0x180009c9e  jz      short loc_180009CA5
0x180009ca0  call    KerbFreeKey
0x180009ca5  mov     rcx, [rbx+60h]; hMem
0x180009ca9  test    rcx, rcx
0x180009cac  jz      short loc_180009CBA
0x180009cae  cmp     byte ptr [rbx+58h], 0
0x180009cb2  jz      short loc_180009CBA
0x180009cb4  call    cs:__imp_LocalFree
0x180009cba  mov     rcx, [rbx+48h]; hMem
0x180009cbe  test    rcx, rcx
0x180009cc1  jz      short loc_180009CCF
0x180009cc3  cmp     byte ptr [rbx+40h], 0
0x180009cc7  jz      short loc_180009CCF
0x180009cc9  call    cs:__imp_LocalFree
0x180009ccf  lea     rcx, [rbx+30h]
0x180009cd3  mov     rdx, [rcx]
0x180009cd6  test    rdx, rdx
0x180009cd9  jz      short loc_180009CE0
0x180009cdb  call    ??R?$default_delete@VKerberosCryptoPolicy@@@utl@@QEBAXPEAVKerberosCryptoPolicy@@@Z; utl::default_delete<KerberosCryptoPolicy>::operator()(KerberosCryptoPolicy *)
0x180009ce0  lea     rdx, [rbx+20h]
0x180009ce4  cmp     qword ptr [rdx+8], 0
0x180009ce9  jz      short loc_180009CFA
0x180009ceb  mov     rcx, [rdx]
0x180009cee  mov     rax, [rcx]
0x180009cf1  mov     rax, [rax+40h]
0x180009cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cfa  lea     rdx, [rbx+10h]
0x180009cfe  cmp     qword ptr [rdx+8], 0
0x180009d03  jz      short loc_180009D14
0x180009d05  mov     rcx, [rdx]
0x180009d08  mov     rax, [rcx]
0x180009d0b  mov     rax, [rax+40h]
0x180009d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d14  add     rsp, 20h
0x180009d18  pop     rbx
0x180009d19  retn
```
