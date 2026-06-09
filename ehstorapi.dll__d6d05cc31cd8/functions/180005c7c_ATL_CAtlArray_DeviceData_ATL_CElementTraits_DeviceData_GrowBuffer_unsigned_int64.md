# ATL::CAtlArray<DeviceData,ATL::CElementTraits<DeviceData>>::GrowBuffer(unsigned __int64)

- ea: `0x180005c7c`
- end: `0x180005d48`
- name: `?GrowBuffer@?$CAtlArray@VDeviceData@@V?$CElementTraits@VDeviceData@@@ATL@@@ATL@@AEAA_N_K@Z`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000408c`

## callees

- `0x180002210`
- `0x180005c7c`

## import_xrefs

- `msvcrt!calloc` at `0x180005cb7`
- `msvcrt!calloc` at `0x180005cf2`
- `msvcrt!calloc` at `0x180005cb7`
- `msvcrt!calloc` at `0x180005cf2`
- `msvcrt!free` at `0x180005d29`
- `msvcrt!free` at `0x180005d29`
- `msvcrt!memmove_s` at `0x180005d19`
- `msvcrt!memmove_s` at `0x180005d19`

## pseudocode

```c
char __fastcall ATL::CAtlArray<DeviceData,ATL::CElementTraits<DeviceData>>::GrowBuffer(__int64 a1, size_t a2)
{
  size_t v4; // rdx
  size_t v5; // rcx
  void *v6; // rax
  void *v7; // rsi
  errno_t v9; // eax

  v4 = *(_QWORD *)(a1 + 16);
  if ( a2 <= v4 )
    return 1;
  v5 = *(int *)(a1 + 24);
  if ( !*(_QWORD *)a1 )
  {
    if ( v5 > a2 )
      a2 = v5;
    v6 = calloc(a2, 0x28u);
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
  v7 = calloc(a2, 0x28u);
  if ( !v7 )
    return 0;
  v9 = memmove_s(v7, 40LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 40LL * *(_QWORD *)(a1 + 8));
  ATL::AtlCrtErrorCheck(v9);
  free(*(void **)a1);
  *(_QWORD *)a1 = v7;
LABEL_15:
  *(_QWORD *)(a1 + 16) = a2;
  return 1;
}

```

## disassembly

```asm
0x180005c7c  mov     [rsp+arg_0], rbx
0x180005c81  mov     [rsp+arg_8], rsi
0x180005c86  push    rdi
0x180005c87  sub     rsp, 20h
0x180005c8b  mov     rbx, rdx
0x180005c8e  mov     rdi, rcx
0x180005c91  mov     rdx, [rcx+10h]
0x180005c95  cmp     rbx, rdx
0x180005c98  jbe     loc_180005D36
0x180005c9e  cmp     qword ptr [rdi], 0
0x180005ca2  movsxd  rcx, dword ptr [rcx+18h]
0x180005ca6  jnz     short loc_180005CC7
0x180005ca8  cmp     rcx, rbx
0x180005cab  mov     edx, 28h ; '('; Size
0x180005cb0  cmova   rbx, rcx
0x180005cb4  mov     rcx, rbx; Count
0x180005cb7  call    cs:__imp_calloc
0x180005cbd  mov     [rdi], rax
0x180005cc0  test    rax, rax
0x180005cc3  jz      short loc_180005D00
0x180005cc5  jmp     short loc_180005D32
0x180005cc7  test    rcx, rcx
0x180005cca  jnz     short loc_180005CDF
0x180005ccc  mov     rcx, rdx
0x180005ccf  mov     rax, rbx
0x180005cd2  shr     rcx, 1
0x180005cd5  sub     rax, rdx
0x180005cd8  cmp     rax, rcx
0x180005cdb  cmova   rcx, rax
0x180005cdf  lea     rax, [rdx+rcx]
0x180005ce3  mov     edx, 28h ; '('; Size
0x180005ce8  cmp     rbx, rax
0x180005ceb  cmovb   rbx, rax
0x180005cef  mov     rcx, rbx; Count
0x180005cf2  call    cs:__imp_calloc
0x180005cf8  mov     rsi, rax
0x180005cfb  test    rax, rax
0x180005cfe  jnz     short loc_180005D04
0x180005d00  xor     al, al
0x180005d02  jmp     short loc_180005D38
0x180005d04  mov     rax, [rdi+8]
0x180005d08  mov     rcx, rsi; Destination
0x180005d0b  mov     r8, [rdi]; Source
0x180005d0e  lea     rdx, [rax+rax*4]
0x180005d12  shl     rdx, 3; DestinationSize
0x180005d16  mov     r9, rdx; SourceSize
0x180005d19  call    cs:__imp_memmove_s
0x180005d1f  mov     ecx, eax; int
0x180005d21  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180005d26  mov     rcx, [rdi]; Block
0x180005d29  call    cs:__imp_free
0x180005d2f  mov     [rdi], rsi
0x180005d32  mov     [rdi+10h], rbx
0x180005d36  mov     al, 1
0x180005d38  mov     rbx, [rsp+28h+arg_0]
0x180005d3d  mov     rsi, [rsp+28h+arg_8]
0x180005d42  add     rsp, 20h
0x180005d46  pop     rdi
0x180005d47  retn
```
