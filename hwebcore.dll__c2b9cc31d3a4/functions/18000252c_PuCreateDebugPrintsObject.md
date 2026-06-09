# PuCreateDebugPrintsObject

- ea: `0x18000252c`
- end: `0x1800025fa`
- name: `PuCreateDebugPrintsObject`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001948`

## callees

- `0x18000252c`
- `0x180002da2`

## import_xrefs

- `msvcrt!strcpy_s` at `0x180002563`
- `msvcrt!strcpy_s` at `0x180002563`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x1800025ae`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x1800025ae`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000253c`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000253c`

## pseudocode

```c
char *PuCreateDebugPrintsObject()
{
  char *v0; // rax
  char *v1; // rbx
  HANDLE StdHandle; // rax

  v0 = (char *)GlobalAlloc(0x40u, 0x298u);
  v1 = v0;
  if ( v0 )
  {
    strcpy_s(v0, 0x64u, "HWEBCORE");
    memset_0(v1 + 100, 0, 0x104u);
    memset_0(v1 + 360, 0, 0x104u);
    *((_QWORD *)v1 + 78) = -1;
    *((_DWORD *)v1 + 162) = 1;
    StdHandle = GetStdHandle(0xFFFFFFF4);
    *((_QWORD *)v1 + 79) = StdHandle;
    if ( !StdHandle )
      *((_QWORD *)v1 + 79) = -1;
    *((_DWORD *)v1 + 160) = 1;
    *((_DWORD *)v1 + 161) = 1;
    *((_QWORD *)v1 + 82) = 0;
  }
  return v1;
}

```

## disassembly

```asm
0x18000252c  push    rbx
0x18000252e  sub     rsp, 20h
0x180002532  mov     edx, 298h; dwBytes
0x180002537  mov     ecx, 40h ; '@'; uFlags
0x18000253c  call    cs:__imp_GlobalAlloc
0x180002543  nop     dword ptr [rax+rax+00h]
0x180002548  mov     rbx, rax
0x18000254b  test    rax, rax
0x18000254e  jz      loc_1800025F0
0x180002554  lea     r8, Source; "HWEBCORE"
0x18000255b  mov     edx, 64h ; 'd'; SizeInBytes
0x180002560  mov     rcx, rax; Destination
0x180002563  call    cs:__imp_strcpy_s
0x18000256a  nop     dword ptr [rax+rax+00h]
0x18000256f  lea     rcx, [rbx+64h]; void *
0x180002573  xor     edx, edx; Val
0x180002575  mov     r8d, 104h; Size
0x18000257b  call    memset_0
0x180002580  lea     rcx, [rbx+168h]; void *
0x180002587  xor     edx, edx; Val
0x180002589  mov     r8d, 104h; Size
0x18000258f  call    memset_0
0x180002594  mov     ecx, 0FFFFFFF4h; nStdHandle
0x180002599  mov     qword ptr [rbx+270h], 0FFFFFFFFFFFFFFFFh
0x1800025a4  mov     dword ptr [rbx+288h], 1
0x1800025ae  call    cs:__imp_GetStdHandle
0x1800025b5  nop     dword ptr [rax+rax+00h]
0x1800025ba  mov     [rbx+278h], rax
0x1800025c1  test    rax, rax
0x1800025c4  jnz     short loc_1800025D1
0x1800025c6  mov     qword ptr [rbx+278h], 0FFFFFFFFFFFFFFFFh
0x1800025d1  mov     dword ptr [rbx+280h], 1
0x1800025db  mov     dword ptr [rbx+284h], 1
0x1800025e5  mov     qword ptr [rbx+290h], 0
0x1800025f0  mov     rax, rbx
0x1800025f3  add     rsp, 20h
0x1800025f7  pop     rbx
0x1800025f8  retn
```
