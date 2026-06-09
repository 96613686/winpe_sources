# REQUEST_FILTER_CONFIG::Reset(void)

- ea: `0x180005520`
- end: `0x180005697`
- name: `?Reset@REQUEST_FILTER_CONFIG@@AEAAXXZ`
- size: `375`
- prototype: `void __fastcall(REQUEST_FILTER_CONFIG *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180002ab0`
- `0x180005460`
- `0x180007130`

## callees

- `0x180005520`
- `0x1800058a0`
- `0x1800070ec`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800055ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005672`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800055ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005672`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x180005531`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x18000553b`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x180005562`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x18000556f`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x18000557c`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x180005589`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x180005596`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x180005531`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x18000553b`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x180005562`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x18000556f`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x18000557c`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x180005589`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x180005596`
- `iisutil!?Reset@MULTISZA@@QEAAXXZ` at `0x180005548`
- `iisutil!?Reset@MULTISZA@@QEAAXXZ` at `0x180005555`
- `iisutil!?Reset@MULTISZA@@QEAAXXZ` at `0x180005548`
- `iisutil!?Reset@MULTISZA@@QEAAXXZ` at `0x180005555`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800055cc`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800055cc`

## pseudocode

```c
void __fastcall REQUEST_FILTER_CONFIG::Reset(REQUEST_FILTER_CONFIG *this)
{
  __int64 v2; // rsi
  __int64 v3; // rax
  __int64 v4; // r14
  void *v5; // rbp
  __int64 v6; // rdi
  __int64 v7; // rax
  __int64 v8; // r14
  void *v9; // rsi

  MULTISZ::Reset((REQUEST_FILTER_CONFIG *)((char *)this + 56));
  MULTISZ::Reset((REQUEST_FILTER_CONFIG *)((char *)this + 112));
  MULTISZA::Reset((REQUEST_FILTER_CONFIG *)((char *)this + 168));
  MULTISZA::Reset((REQUEST_FILTER_CONFIG *)((char *)this + 224));
  MULTISZ::Reset((REQUEST_FILTER_CONFIG *)((char *)this + 392));
  MULTISZ::Reset((REQUEST_FILTER_CONFIG *)((char *)this + 504));
  MULTISZ::Reset((REQUEST_FILTER_CONFIG *)((char *)this + 280));
  MULTISZ::Reset((REQUEST_FILTER_CONFIG *)((char *)this + 336));
  MULTISZ::Reset((REQUEST_FILTER_CONFIG *)((char *)this + 448));
  if ( *((_DWORD *)this + 142) )
  {
    v2 = 0;
    do
    {
      v3 = *((_QWORD *)this + 70);
      v4 = 8 * v2;
      v5 = *(void **)(8 * v2 + v3);
      if ( v5 )
      {
        STRA::~STRA(*(STRA **)(8 * v2 + v3));
        operator delete(v5);
      }
      v2 = (unsigned int)(v2 + 1);
      *(_QWORD *)(v4 + *((_QWORD *)this + 70)) = 0;
    }
    while ( (unsigned int)v2 < *((_DWORD *)this + 142) );
    LocalFree(*((HLOCAL *)this + 70));
    *((_QWORD *)this + 70) = 0;
    *((_DWORD *)this + 142) = 0;
  }
  if ( *((_DWORD *)this + 146) )
  {
    v6 = 0;
    do
    {
      v7 = *((_QWORD *)this + 72);
      v8 = 8 * v6;
      v9 = *(void **)(8 * v6 + v7);
      if ( v9 )
      {
        FILTERING_RULE::~FILTERING_RULE(*(FILTERING_RULE **)(8 * v6 + v7));
        operator delete(v9);
      }
      v6 = (unsigned int)(v6 + 1);
      *(_QWORD *)(v8 + *((_QWORD *)this + 72)) = 0;
    }
    while ( (unsigned int)v6 < *((_DWORD *)this + 146) );
    LocalFree(*((HLOCAL *)this + 72));
    *((_QWORD *)this + 72) = 0;
    *((_DWORD *)this + 146) = 0;
  }
}

```

## disassembly

```asm
0x180005520  push    rbx
0x180005522  push    rsi
0x180005523  push    rdi
0x180005524  push    r14
0x180005526  sub     rsp, 28h
0x18000552a  mov     rbx, rcx
0x18000552d  add     rcx, 38h ; '8'
0x180005531  call    cs:__imp_?Reset@MULTISZ@@QEAAXXZ; MULTISZ::Reset(void)
0x180005537  lea     rcx, [rbx+70h]
0x18000553b  call    cs:__imp_?Reset@MULTISZ@@QEAAXXZ; MULTISZ::Reset(void)
0x180005541  lea     rcx, [rbx+0A8h]
0x180005548  call    cs:__imp_?Reset@MULTISZA@@QEAAXXZ; MULTISZA::Reset(void)
0x18000554e  lea     rcx, [rbx+0E0h]
0x180005555  call    cs:__imp_?Reset@MULTISZA@@QEAAXXZ; MULTISZA::Reset(void)
0x18000555b  lea     rcx, [rbx+188h]
0x180005562  call    cs:__imp_?Reset@MULTISZ@@QEAAXXZ; MULTISZ::Reset(void)
0x180005568  lea     rcx, [rbx+1F8h]
0x18000556f  call    cs:__imp_?Reset@MULTISZ@@QEAAXXZ; MULTISZ::Reset(void)
0x180005575  lea     rcx, [rbx+118h]
0x18000557c  call    cs:__imp_?Reset@MULTISZ@@QEAAXXZ; MULTISZ::Reset(void)
0x180005582  lea     rcx, [rbx+150h]
0x180005589  call    cs:__imp_?Reset@MULTISZ@@QEAAXXZ; MULTISZ::Reset(void)
0x18000558f  lea     rcx, [rbx+1C0h]
0x180005596  call    cs:__imp_?Reset@MULTISZ@@QEAAXXZ; MULTISZ::Reset(void)
0x18000559c  mov     eax, [rbx+238h]
0x1800055a2  test    eax, eax
0x1800055a4  jz      short loc_18000561A
0x1800055a6  xor     esi, esi
0x1800055a8  test    eax, eax
0x1800055aa  jz      short loc_1800055F8
0x1800055ac  mov     [rsp+48h+arg_0], rbp
0x1800055b1  mov     rax, [rbx+230h]
0x1800055b8  lea     r14, ds:0[rsi*8]
0x1800055c0  mov     rbp, [r14+rax]
0x1800055c4  test    rbp, rbp
0x1800055c7  jz      short loc_1800055DA
0x1800055c9  mov     rcx, rbp
0x1800055cc  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800055d2  mov     rcx, rbp; Block
0x1800055d5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800055da  mov     rax, [rbx+230h]
0x1800055e1  inc     esi
0x1800055e3  mov     qword ptr [r14+rax], 0
0x1800055eb  cmp     esi, [rbx+238h]
0x1800055f1  jb      short loc_1800055B1
0x1800055f3  mov     rbp, [rsp+48h+arg_0]
0x1800055f8  mov     rcx, [rbx+230h]; hMem
0x1800055ff  call    cs:__imp_LocalFree
0x180005605  mov     qword ptr [rbx+230h], 0
0x180005610  mov     dword ptr [rbx+238h], 0
0x18000561a  mov     eax, [rbx+248h]
0x180005620  test    eax, eax
0x180005622  jz      short loc_18000568D
0x180005624  xor     edi, edi
0x180005626  test    eax, eax
0x180005628  jz      short loc_18000566B
0x18000562a  mov     rax, [rbx+240h]
0x180005631  lea     r14, ds:0[rdi*8]
0x180005639  mov     rsi, [r14+rax]
0x18000563d  test    rsi, rsi
0x180005640  jz      short loc_180005652
0x180005642  mov     rcx, rsi; this
0x180005645  call    ??1FILTERING_RULE@@QEAA@XZ; FILTERING_RULE::~FILTERING_RULE(void)
0x18000564a  mov     rcx, rsi; Block
0x18000564d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005652  mov     rax, [rbx+240h]
0x180005659  inc     edi
0x18000565b  mov     qword ptr [r14+rax], 0
0x180005663  cmp     edi, [rbx+248h]
0x180005669  jb      short loc_18000562A
0x18000566b  mov     rcx, [rbx+240h]; hMem
0x180005672  call    cs:__imp_LocalFree
0x180005678  mov     qword ptr [rbx+240h], 0
0x180005683  mov     dword ptr [rbx+248h], 0
0x18000568d  add     rsp, 28h
0x180005691  pop     r14
0x180005693  pop     rdi
0x180005694  pop     rsi
0x180005695  pop     rbx
0x180005696  retn
```
