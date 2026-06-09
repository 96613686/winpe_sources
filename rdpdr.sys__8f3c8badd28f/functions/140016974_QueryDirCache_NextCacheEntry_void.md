# QueryDirCache::NextCacheEntry(void)

- ea: `0x140016974`
- end: `0x1400169e7`
- name: `?NextCacheEntry@QueryDirCache@@QEAAPEAUtagRDPDR_QUERYDIR_CACHE_ENTRY@@XZ`
- size: `115`
- prototype: `struct tagRDPDR_QUERYDIR_CACHE_ENTRY *__fastcall(QueryDirCache *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400168f0`

## callees

- `0x1400032c0`
- `0x140016974`

## pseudocode

```c
struct tagRDPDR_QUERYDIR_CACHE_ENTRY *__fastcall QueryDirCache::NextCacheEntry(QueryDirCache *this)
{
  unsigned int *v1; // rbx
  unsigned int v2; // eax

  if ( *((_QWORD *)this + 1)
    && (v1 = (unsigned int *)*((_QWORD *)this + 3)) != 0
    && (v2 = *((_DWORD *)this + 9), v2 < *((_DWORD *)this + 8)) )
  {
    *((_DWORD *)this + 9) = v2 + 1;
    *((_QWORD *)this + 3) = (char *)v1 + *v1;
  }
  else
  {
    v1 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        23,
        WPP_857ee275c9d63dc09dd0836f7968c8e8_Traceguids,
        *((unsigned int *)this + 9),
        *((_DWORD *)this + 8));
  }
  return (struct tagRDPDR_QUERYDIR_CACHE_ENTRY *)v1;
}

```

## disassembly

```asm
0x140016974  push    rbx
0x140016976  sub     rsp, 30h
0x14001697a  cmp     qword ptr [rcx+8], 0
0x14001697f  jz      short loc_1400169A2
0x140016981  mov     rbx, [rcx+18h]
0x140016985  test    rbx, rbx
0x140016988  jz      short loc_1400169A2
0x14001698a  mov     eax, [rcx+24h]
0x14001698d  cmp     eax, [rcx+20h]
0x140016990  jnb     short loc_1400169A2
0x140016992  inc     eax
0x140016994  mov     [rcx+24h], eax
0x140016997  mov     eax, [rbx]
0x140016999  add     rax, rbx
0x14001699c  mov     [rcx+18h], rax
0x1400169a0  jmp     short loc_1400169DD
0x1400169a2  mov     rax, cs:WPP_GLOBAL_Control
0x1400169a9  lea     rdx, WPP_GLOBAL_Control
0x1400169b0  xor     ebx, ebx
0x1400169b2  cmp     rax, rdx
0x1400169b5  jz      short loc_1400169DD
0x1400169b7  cmp     byte ptr [rax+29h], 5
0x1400169bb  jb      short loc_1400169DD
0x1400169bd  mov     r8d, [rcx+20h]
0x1400169c1  lea     edx, [rbx+17h]
0x1400169c4  mov     r9d, [rcx+24h]
0x1400169c8  mov     rcx, [rax+18h]
0x1400169cc  mov     [rsp+38h+var_18], r8d
0x1400169d1  lea     r8, WPP_857ee275c9d63dc09dd0836f7968c8e8_Traceguids
0x1400169d8  call    WPP_SF_dd
0x1400169dd  mov     rax, rbx
0x1400169e0  add     rsp, 30h
0x1400169e4  pop     rbx
0x1400169e5  retn
```
