# CNtfsStream::Init(void *,ulong,ushort const *,CNtfsStream *)

- ea: `0x180057e80`
- end: `0x180057f6b`
- name: `?Init@CNtfsStream@@UEAAJPEAXKPEBGPEAV1@@Z`
- size: `235`
- prototype: `int(CNtfsStream *__hidden this, void *, unsigned int, const unsigned __int16 *, struct CNtfsStream *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004fc90`
- `0x180053a64`

## callees

- `0x18001e2f0`
- `0x180057e80`
- `0x180059d28`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180057ec9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180057ec9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057ea2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057ea2`

## pseudocode

```c
int __fastcall CNtfsStream::Init(
        CNtfsStream *this,
        void *a2,
        int a3,
        const unsigned __int16 *a4,
        struct CNtfsStream *a5)
{
  void *v6; // rcx
  __int64 v8; // rax
  SIZE_T v9; // rsi
  unsigned __int16 *v10; // rax
  __int64 v12; // rax

  *((_QWORD *)this + 12) = a2;
  *((_DWORD *)this + 22) = a3;
  v6 = (void *)*((_QWORD *)this + 2);
  if ( v6 )
  {
    CoTaskMemFree(v6);
    *((_QWORD *)this + 2) = 0;
  }
  if ( a4 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a4[v8] );
    v9 = (unsigned int)(2 * v8 + 2);
    v10 = (unsigned __int16 *)CoTaskMemAlloc(v9);
    *((_QWORD *)this + 2) = v10;
    if ( !v10 )
      return -2147287032;
    StringCbCopyW(v10, v9, a4);
  }
  if ( a5 && !*((_QWORD *)this + 18) )
  {
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 13) + 24LL))(*((_QWORD *)this + 13), 0xFFFFFFFFLL);
    *((_QWORD *)this + 17) = a5;
    *((_QWORD *)this + 18) = *((_QWORD *)a5 + 18);
    *((_QWORD *)a5 + 18) = this;
    v12 = *((_QWORD *)this + 18);
    if ( v12 )
      *(_QWORD *)(v12 + 136) = this;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 32LL))(*((_QWORD *)this + 13));
  }
  return CNFFMappedStream::Init((CNtfsStream *)((char *)this + 24), *((void **)this + 12));
}

```

## disassembly

```asm
0x180057e80  push    rbx
0x180057e82  push    rbp
0x180057e83  push    rsi
0x180057e84  push    rdi
0x180057e85  sub     rsp, 28h
0x180057e89  mov     rbx, rcx
0x180057e8c  mov     [rcx+60h], rdx
0x180057e90  mov     [rcx+58h], r8d
0x180057e94  xor     ebp, ebp
0x180057e96  mov     rcx, [rcx+10h]; pv
0x180057e9a  mov     rdi, r9
0x180057e9d  test    rcx, rcx
0x180057ea0  jz      short loc_180057EAC
0x180057ea2  call    cs:__imp_CoTaskMemFree
0x180057ea8  mov     [rbx+10h], rbp
0x180057eac  test    rdi, rdi
0x180057eaf  jz      short loc_180057EF0
0x180057eb1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180057eb5  inc     rax
0x180057eb8  cmp     [rdi+rax*2], bp
0x180057ebc  jnz     short loc_180057EB5
0x180057ebe  lea     eax, ds:2[rax*2]
0x180057ec5  mov     ecx, eax; cb
0x180057ec7  mov     esi, eax
0x180057ec9  call    cs:__imp_CoTaskMemAlloc
0x180057ecf  mov     [rbx+10h], rax
0x180057ed3  test    rax, rax
0x180057ed6  jnz     short loc_180057EE2
0x180057ed8  mov     eax, 80030008h
0x180057edd  jmp     loc_180057F62
0x180057ee2  mov     r8, rdi; unsigned __int16 *
0x180057ee5  mov     rdx, rsi; unsigned __int64
0x180057ee8  mov     rcx, rax; unsigned __int16 *
0x180057eeb  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180057ef0  mov     rdi, [rsp+48h+arg_20]
0x180057ef5  test    rdi, rdi
0x180057ef8  jz      short loc_180057F55
0x180057efa  cmp     [rbx+90h], rbp
0x180057f01  jnz     short loc_180057F55
0x180057f03  mov     rcx, [rbx+68h]
0x180057f07  or      edx, 0FFFFFFFFh
0x180057f0a  mov     rax, [rcx]
0x180057f0d  mov     rax, [rax+18h]
0x180057f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057f16  mov     [rbx+88h], rdi
0x180057f1d  mov     rax, [rdi+90h]
0x180057f24  mov     [rbx+90h], rax
0x180057f2b  mov     [rdi+90h], rbx
0x180057f32  mov     rax, [rbx+90h]
0x180057f39  test    rax, rax
0x180057f3c  jz      short loc_180057F45
0x180057f3e  mov     [rax+88h], rbx
0x180057f45  mov     rcx, [rbx+68h]
0x180057f49  mov     rax, [rcx]
0x180057f4c  mov     rax, [rax+20h]
0x180057f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057f55  mov     rdx, [rbx+60h]; void *
0x180057f59  lea     rcx, [rbx+18h]; this
0x180057f5d  call    ?Init@CNFFMappedStream@@QEAAJPEAX@Z; CNFFMappedStream::Init(void *)
0x180057f62  add     rsp, 28h
0x180057f66  pop     rdi
0x180057f67  pop     rsi
0x180057f68  pop     rbp
0x180057f69  pop     rbx
0x180057f6a  retn
```
