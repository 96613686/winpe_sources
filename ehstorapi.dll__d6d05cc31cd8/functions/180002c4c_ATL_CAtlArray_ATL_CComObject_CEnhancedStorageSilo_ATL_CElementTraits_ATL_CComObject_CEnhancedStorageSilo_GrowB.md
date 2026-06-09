# ATL::CAtlArray<ATL::CComObject<CEnhancedStorageSilo> *,ATL::CElementTraits<ATL::CComObject<CEnhancedStorageSilo> *>>::GrowBuffer(unsigned __int64)

- ea: `0x180002c4c`
- end: `0x180002d14`
- name: `?GrowBuffer@?$CAtlArray@PEAV?$CComObject@VCEnhancedStorageSilo@@@ATL@@V?$CElementTraits@PEAV?$CComObject@VCEnhancedStorageSilo@@@ATL@@@2@@ATL@@AEAA_N_K@Z`
- size: `200`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002d68`

## callees

- `0x180002210`
- `0x180002c4c`

## import_xrefs

- `msvcrt!calloc` at `0x180002c87`
- `msvcrt!calloc` at `0x180002cc2`
- `msvcrt!calloc` at `0x180002c87`
- `msvcrt!calloc` at `0x180002cc2`
- `msvcrt!free` at `0x180002cf5`
- `msvcrt!free` at `0x180002cf5`
- `msvcrt!memmove_s` at `0x180002ce5`
- `msvcrt!memmove_s` at `0x180002ce5`

## pseudocode

```c
char __fastcall ATL::CAtlArray<ATL::CComObject<CEnhancedStorageSilo> *,ATL::CElementTraits<ATL::CComObject<CEnhancedStorageSilo> *>>::GrowBuffer(
        __int64 a1,
        size_t a2)
{
  size_t v4; // rdx
  size_t v5; // rcx
  void *v6; // rax
  void *v7; // rax
  void *v8; // rsi
  errno_t v10; // eax

  v4 = *(_QWORD *)(a1 + 16);
  if ( a2 <= v4 )
    return 1;
  v5 = *(int *)(a1 + 24);
  if ( !*(_QWORD *)a1 )
  {
    if ( v5 > a2 )
      a2 = v5;
    v6 = calloc(a2, 8u);
    *(_QWORD *)a1 = v6;
    if ( v6 )
      goto LABEL_15;
    return 0;
  }
  if ( !v5 )
  {
    v5 = v4 >> 1;
    if ( a2 - v4 > v4 >> 1 )
      v5 = a2 - v4;
  }
  if ( a2 < v4 + v5 )
    a2 = v4 + v5;
  v7 = calloc(a2, 8u);
  v8 = v7;
  if ( !v7 )
    return 0;
  v10 = memmove_s(v7, 8LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 8LL * *(_QWORD *)(a1 + 8));
  ATL::AtlCrtErrorCheck(v10);
  free(*(void **)a1);
  *(_QWORD *)a1 = v8;
LABEL_15:
  *(_QWORD *)(a1 + 16) = a2;
  return 1;
}

```

## disassembly

```asm
0x180002c4c  mov     [rsp+arg_0], rbx
0x180002c51  mov     [rsp+arg_8], rsi
0x180002c56  push    rdi
0x180002c57  sub     rsp, 20h
0x180002c5b  mov     rbx, rdx
0x180002c5e  mov     rdi, rcx
0x180002c61  mov     rdx, [rcx+10h]
0x180002c65  cmp     rbx, rdx
0x180002c68  jbe     loc_180002D02
0x180002c6e  cmp     qword ptr [rdi], 0
0x180002c72  movsxd  rcx, dword ptr [rcx+18h]
0x180002c76  jnz     short loc_180002C97
0x180002c78  cmp     rcx, rbx
0x180002c7b  mov     edx, 8; Size
0x180002c80  cmova   rbx, rcx
0x180002c84  mov     rcx, rbx; Count
0x180002c87  call    cs:__imp_calloc
0x180002c8d  mov     [rdi], rax
0x180002c90  test    rax, rax
0x180002c93  jz      short loc_180002CD0
0x180002c95  jmp     short loc_180002CFE
0x180002c97  test    rcx, rcx
0x180002c9a  jnz     short loc_180002CAF
0x180002c9c  mov     rcx, rdx
0x180002c9f  mov     rax, rbx
0x180002ca2  shr     rcx, 1
0x180002ca5  sub     rax, rdx
0x180002ca8  cmp     rax, rcx
0x180002cab  cmova   rcx, rax
0x180002caf  lea     rax, [rdx+rcx]
0x180002cb3  mov     edx, 8; Size
0x180002cb8  cmp     rbx, rax
0x180002cbb  cmovb   rbx, rax
0x180002cbf  mov     rcx, rbx; Count
0x180002cc2  call    cs:__imp_calloc
0x180002cc8  mov     rsi, rax
0x180002ccb  test    rax, rax
0x180002cce  jnz     short loc_180002CD4
0x180002cd0  xor     al, al
0x180002cd2  jmp     short loc_180002D04
0x180002cd4  mov     rdx, [rdi+8]
0x180002cd8  mov     rcx, rsi; Destination
0x180002cdb  mov     r8, [rdi]; Source
0x180002cde  shl     rdx, 3; DestinationSize
0x180002ce2  mov     r9, rdx; SourceSize
0x180002ce5  call    cs:__imp_memmove_s
0x180002ceb  mov     ecx, eax; int
0x180002ced  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180002cf2  mov     rcx, [rdi]; Block
0x180002cf5  call    cs:__imp_free
0x180002cfb  mov     [rdi], rsi
0x180002cfe  mov     [rdi+10h], rbx
0x180002d02  mov     al, 1
0x180002d04  mov     rbx, [rsp+28h+arg_0]
0x180002d09  mov     rsi, [rsp+28h+arg_8]
0x180002d0e  add     rsp, 20h
0x180002d12  pop     rdi
0x180002d13  retn
```
