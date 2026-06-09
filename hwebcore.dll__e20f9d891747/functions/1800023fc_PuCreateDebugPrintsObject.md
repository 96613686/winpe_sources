# PuCreateDebugPrintsObject

- ea: `0x1800023fc`
- end: `0x1800024b7`
- name: `PuCreateDebugPrintsObject`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001948`

## callees

- `0x1800023fc`
- `0x180002ba2`

## import_xrefs

- `msvcrt!strcpy_s` at `0x18000242d`
- `msvcrt!strcpy_s` at `0x18000242d`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x180002472`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x180002472`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000240c`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000240c`

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
0x1800023fc  push    rbx
0x1800023fe  sub     rsp, 20h
0x180002402  mov     edx, 298h; dwBytes
0x180002407  mov     ecx, 40h ; '@'; uFlags
0x18000240c  call    cs:__imp_GlobalAlloc
0x180002412  mov     rbx, rax
0x180002415  test    rax, rax
0x180002418  jz      loc_1800024AE
0x18000241e  lea     r8, Source; "HWEBCORE"
0x180002425  mov     edx, 64h ; 'd'; SizeInBytes
0x18000242a  mov     rcx, rax; Destination
0x18000242d  call    cs:__imp_strcpy_s
0x180002433  lea     rcx, [rbx+64h]; void *
0x180002437  xor     edx, edx; Val
0x180002439  mov     r8d, 104h; Size
0x18000243f  call    memset_0
0x180002444  lea     rcx, [rbx+168h]; void *
0x18000244b  xor     edx, edx; Val
0x18000244d  mov     r8d, 104h; Size
0x180002453  call    memset_0
0x180002458  mov     ecx, 0FFFFFFF4h; nStdHandle
0x18000245d  mov     qword ptr [rbx+270h], 0FFFFFFFFFFFFFFFFh
0x180002468  mov     dword ptr [rbx+288h], 1
0x180002472  call    cs:__imp_GetStdHandle
0x180002478  mov     [rbx+278h], rax
0x18000247f  test    rax, rax
0x180002482  jnz     short loc_18000248F
0x180002484  mov     qword ptr [rbx+278h], 0FFFFFFFFFFFFFFFFh
0x18000248f  mov     dword ptr [rbx+280h], 1
0x180002499  mov     dword ptr [rbx+284h], 1
0x1800024a3  mov     qword ptr [rbx+290h], 0
0x1800024ae  mov     rax, rbx
0x1800024b1  add     rsp, 20h
0x1800024b5  pop     rbx
0x1800024b6  retn
```
