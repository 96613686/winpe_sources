# LuafvSplitPathLeft

- ea: `0x1400219ac`
- end: `0x140021a0c`
- name: `LuafvSplitPathLeft`
- size: `96`
- prototype: `char __fastcall(unsigned __int16 *, __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14001a378`
- `0x14002194c`
- `0x140022734`
- `0x14002814c`

## callees

- `0x1400219ac`

## pseudocode

```c
char __fastcall LuafvSplitPathLeft(unsigned __int16 *a1, __int64 a2)
{
  __int16 v2; // r11
  __int64 v3; // r8
  __int64 *v4; // r9
  __int64 v5; // rax
  __int64 v6; // rcx
  char result; // al

  v2 = *a1;
  v3 = *a1 >> 1;
  if ( !(_DWORD)v3 )
    return 0;
  v4 = (__int64 *)(a1 + 4);
  do
  {
    if ( !(_DWORD)v3 )
      break;
    v4 = (__int64 *)(a1 + 4);
    v3 = (unsigned int)(v3 - 1);
  }
  while ( *(_WORD *)(*((_QWORD *)a1 + 1) + 2 * v3) != 92 );
  v5 = *v4;
  *a1 = 2 * v3;
  *(_WORD *)a2 += v2 - 2 * v3;
  v6 = v5 + 2 * v3;
  *(_WORD *)(a2 + 2) = *(_WORD *)a2;
  result = 1;
  *(_QWORD *)(a2 + 8) = v6;
  return result;
}

```

## disassembly

```asm
0x1400219ac  mov     [rsp+arg_0], rbx
0x1400219b1  movzx   r11d, word ptr [rcx]
0x1400219b5  mov     rbx, rdx
0x1400219b8  mov     r8d, r11d
0x1400219bb  shr     r8d, 1
0x1400219be  jz      short loc_140021A08
0x1400219c0  lea     r9, [rcx+8]
0x1400219c4  test    r8d, r8d
0x1400219c7  jz      short loc_1400219DB
0x1400219c9  lea     r9, [rcx+8]
0x1400219cd  dec     r8d
0x1400219d0  mov     rax, [r9]
0x1400219d3  cmp     word ptr [rax+r8*2], 5Ch ; '\'
0x1400219d9  jnz     short loc_1400219C4
0x1400219db  mov     rax, [r9]
0x1400219de  movzx   edx, r8w
0x1400219e2  add     dx, dx
0x1400219e5  mov     [rcx], dx
0x1400219e8  sub     r11w, dx
0x1400219ec  add     [rbx], r11w
0x1400219f0  lea     rcx, [rax+r8*2]
0x1400219f4  movzx   eax, word ptr [rbx]
0x1400219f7  mov     [rbx+2], ax
0x1400219fb  mov     al, 1
0x1400219fd  mov     [rbx+8], rcx
0x140021a01  mov     rbx, [rsp+arg_0]
0x140021a06  retn
0x140021a08  xor     al, al
0x140021a0a  jmp     short loc_140021A01
```
