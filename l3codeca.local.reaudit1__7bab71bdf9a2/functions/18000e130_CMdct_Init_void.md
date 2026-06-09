# CMdct::Init(void)

- ea: `0x18000e130`
- end: `0x18000e1fa`
- name: `?Init@CMdct@@QEAAXXZ`
- size: `202`
- prototype: `void __fastcall(CMdct *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003fa0`
- `0x180005000`

## callees

- `0x18000e130`

## pseudocode

```c
void __fastcall CMdct::Init(CMdct *this)
{
  __int64 v1; // rdx
  __int64 v2; // rax
  __int64 v3; // r8
  __int64 v4; // rax

  v1 = 0;
  v2 = 0;
  do
  {
    *(_QWORD *)((char *)this + v2 + 224) = 0;
    ++v1;
    *(_QWORD *)((char *)this + v2 + 232) = 0;
    *(_QWORD *)((char *)this + v2 + 240) = 0;
    *(_QWORD *)((char *)this + v2 + 248) = 0;
    *(_QWORD *)((char *)this + v2 + 256) = 0;
    *(_QWORD *)((char *)this + v2 + 264) = 0;
    *(_QWORD *)((char *)this + v2 + 272) = 0;
    *(_QWORD *)((char *)this + v2 + 280) = 0;
    *(_QWORD *)((char *)this + v2 + 288) = 0;
    v2 += 72;
  }
  while ( v1 != 32 );
  v3 = 0;
  do
  {
    v4 = 9 * v1;
    ++v3;
    *((_QWORD *)this + v4 + 28) = 0;
    ++v1;
    *((_QWORD *)this + v4 + 29) = 0;
    *((_QWORD *)this + v4 + 30) = 0;
    *((_QWORD *)this + v4 + 31) = 0;
    *((_QWORD *)this + v4 + 32) = 0;
    *((_QWORD *)this + v4 + 33) = 0;
    *((_QWORD *)this + v4 + 34) = 0;
    *((_QWORD *)this + v4 + 35) = 0;
    *((_QWORD *)this + v4 + 36) = 0;
  }
  while ( v3 != 32 );
}

```

## disassembly

```asm
0x18000e130  xor     r9d, r9d
0x18000e133  mov     edx, r9d
0x18000e136  mov     eax, r9d
0x18000e139  nop     dword ptr [rax+00000000h]
0x18000e140  mov     [rcx+rax+0E0h], r9
0x18000e148  inc     rdx
0x18000e14b  mov     [rcx+rax+0E8h], r9
0x18000e153  mov     [rcx+rax+0F0h], r9
0x18000e15b  mov     [rcx+rax+0F8h], r9
0x18000e163  mov     [rcx+rax+100h], r9
0x18000e16b  mov     [rcx+rax+108h], r9
0x18000e173  mov     [rcx+rax+110h], r9
0x18000e17b  mov     [rcx+rax+118h], r9
0x18000e183  mov     [rcx+rax+120h], r9
0x18000e18b  lea     rax, [rax+48h]
0x18000e18f  cmp     rdx, 20h ; ' '
0x18000e193  jnz     short loc_18000E140
0x18000e195  mov     r8, r9
0x18000e198  nop     dword ptr [rax+rax+00000000h]
0x18000e1a0  lea     rax, [rdx+rdx*8]
0x18000e1a4  inc     r8
0x18000e1a7  mov     [rcx+rax*8+0E0h], r9
0x18000e1af  lea     rdx, [rdx+1]
0x18000e1b3  mov     [rcx+rax*8+0E8h], r9
0x18000e1bb  mov     [rcx+rax*8+0F0h], r9
0x18000e1c3  mov     [rcx+rax*8+0F8h], r9
0x18000e1cb  mov     [rcx+rax*8+100h], r9
0x18000e1d3  mov     [rcx+rax*8+108h], r9
0x18000e1db  mov     [rcx+rax*8+110h], r9
0x18000e1e3  mov     [rcx+rax*8+118h], r9
0x18000e1eb  mov     [rcx+rax*8+120h], r9
0x18000e1f3  cmp     r8, 20h ; ' '
0x18000e1f7  jnz     short loc_18000E1A0
0x18000e1f9  retn
```
