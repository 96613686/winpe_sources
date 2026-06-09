# ATL::CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>::GrowBuffer(unsigned __int64)

- ea: `0x180026a7c`
- end: `0x180026b44`
- name: `?GrowBuffer@?$CAtlArray@PEBUImageData@IProcessInfoSource@XPerfAddIn@@V?$CElementTraits@PEBUImageData@IProcessInfoSource@XPerfAddIn@@@ATL@@@ATL@@AEAA_N_K@Z`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180026a14`

## callees

- `0x180026a7c`
- `0x180040af8`

## import_xrefs

- `msvcrt!calloc` at `0x180026ab7`
- `msvcrt!calloc` at `0x180026af2`
- `msvcrt!calloc` at `0x180026ab7`
- `msvcrt!calloc` at `0x180026af2`
- `msvcrt!memmove_s` at `0x180026b15`
- `msvcrt!memmove_s` at `0x180026b15`
- `msvcrt!free` at `0x180026b25`
- `msvcrt!free` at `0x180026b25`

## pseudocode

```c
char __fastcall ATL::CAtlArray<XPerfAddIn::IProcessInfoSource::ImageData const *,ATL::CElementTraits<XPerfAddIn::IProcessInfoSource::ImageData const *>>::GrowBuffer(
        __int64 a1,
        size_t a2)
{
  unsigned __int64 v4; // rdx
  size_t v5; // rcx
  void *v6; // rax
  void *v7; // rax
  void *v8; // rsi
  errno_t v10; // eax

  v4 = *(_QWORD *)(a1 + 16);
  if ( a2 > v4 )
  {
    v5 = *(int *)(a1 + 24);
    if ( *(_QWORD *)a1 )
    {
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
    }
    else
    {
      if ( v5 > a2 )
        a2 = v5;
      v6 = calloc(a2, 8u);
      *(_QWORD *)a1 = v6;
      if ( !v6 )
        return 0;
    }
    *(_QWORD *)(a1 + 16) = a2;
  }
  return 1;
}

```

## disassembly

```asm
0x180026a7c  mov     [rsp+arg_0], rbx
0x180026a81  mov     [rsp+arg_8], rsi
0x180026a86  push    rdi
0x180026a87  sub     rsp, 20h
0x180026a8b  mov     rbx, rdx
0x180026a8e  mov     rdi, rcx
0x180026a91  mov     rdx, [rcx+10h]
0x180026a95  cmp     rbx, rdx
0x180026a98  jbe     loc_180026B32
0x180026a9e  cmp     qword ptr [rdi], 0
0x180026aa2  movsxd  rcx, dword ptr [rcx+18h]
0x180026aa6  jnz     short loc_180026AC7
0x180026aa8  cmp     rcx, rbx
0x180026aab  mov     edx, 8; Size
0x180026ab0  cmova   rbx, rcx
0x180026ab4  mov     rcx, rbx; Count
0x180026ab7  call    cs:__imp_calloc
0x180026abd  mov     [rdi], rax
0x180026ac0  test    rax, rax
0x180026ac3  jnz     short loc_180026B2E
0x180026ac5  jmp     short loc_180026B00
0x180026ac7  test    rcx, rcx
0x180026aca  jnz     short loc_180026ADF
0x180026acc  mov     rcx, rdx
0x180026acf  mov     rax, rbx
0x180026ad2  shr     rcx, 1
0x180026ad5  sub     rax, rdx
0x180026ad8  cmp     rax, rcx
0x180026adb  cmova   rcx, rax
0x180026adf  lea     rax, [rdx+rcx]
0x180026ae3  mov     edx, 8; Size
0x180026ae8  cmp     rbx, rax
0x180026aeb  cmovb   rbx, rax
0x180026aef  mov     rcx, rbx; Count
0x180026af2  call    cs:__imp_calloc
0x180026af8  mov     rsi, rax
0x180026afb  test    rax, rax
0x180026afe  jnz     short loc_180026B04
0x180026b00  xor     al, al
0x180026b02  jmp     short loc_180026B34
0x180026b04  mov     rdx, [rdi+8]
0x180026b08  mov     rcx, rsi; Destination
0x180026b0b  mov     r8, [rdi]; Source
0x180026b0e  shl     rdx, 3; DestinationSize
0x180026b12  mov     r9, rdx; SourceSize
0x180026b15  call    cs:__imp_memmove_s
0x180026b1b  mov     ecx, eax; int
0x180026b1d  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180026b22  mov     rcx, [rdi]; Block
0x180026b25  call    cs:__imp_free
0x180026b2b  mov     [rdi], rsi
0x180026b2e  mov     [rdi+10h], rbx
0x180026b32  mov     al, 1
0x180026b34  mov     rbx, [rsp+28h+arg_0]
0x180026b39  mov     rsi, [rsp+28h+arg_8]
0x180026b3e  add     rsp, 20h
0x180026b42  pop     rdi
0x180026b43  retn
```
