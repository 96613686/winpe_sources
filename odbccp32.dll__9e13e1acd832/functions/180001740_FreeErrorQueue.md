# FreeErrorQueue

- ea: `0x180001740`
- end: `0x1800017b9`
- name: `FreeErrorQueue`
- size: `121`
- prototype: `void *()`
- caller_count: `24`
- callee_count: `2`
- tags: ``

## callers

- `0x180002ce0`
- `0x180002d20`
- `0x1800084c0`
- `0x180008570`
- `0x180008bf0`
- `0x180008d10`
- `0x180008d50`
- `0x180008dc0`
- `0x180008fc0`
- `0x180009160`
- `0x1800091f0`
- `0x180009280`
- `0x180009660`
- `0x1800096f0`
- `0x180009750`
- `0x180009960`
- `0x1800099a0`
- `0x180009b80`
- `0x180009bd0`
- `0x180009cf0`
- `0x180009d40`
- `0x18000a100`
- `0x18000a150`
- `0x18000a320`

## callees

- `0x180001740`
- `0x180014aae`

## import_xrefs

- `msvcrt!free` at `0x180001781`
- `msvcrt!free` at `0x180001781`

## pseudocode

```c
void *FreeErrorQueue()
{
  int v0; // edi
  __int16 v1; // bx
  void *v2; // rcx

  v0 = (unsigned __int16)word_18001CA40;
  v1 = 0;
  if ( word_18001CA40 )
  {
    do
    {
      v2 = (void *)qword_18001C9C0[2 * v1 + 1];
      if ( v2 )
        free(v2);
      ++v1;
    }
    while ( v1 < v0 );
  }
  word_18001CA40 = 0;
  return memset_0(qword_18001C9C0, 0, sizeof(qword_18001C9C0));
}

```

## disassembly

```asm
0x180001740  mov     [rsp+arg_0], rbx
0x180001745  mov     [rsp+arg_8], rsi
0x18000174a  push    rdi
0x18000174b  sub     rsp, 20h
0x18000174f  movzx   edi, cs:word_18001CA40
0x180001756  lea     rsi, qword_18001C9C0
0x18000175d  xor     ebx, ebx
0x18000175f  test    edi, edi
0x180001761  jz      short loc_180001791
0x180001763  nop     dword ptr [rax+00h]
0x180001767  nop     word ptr [rax+rax+00000000h]
0x180001770  movsx   rax, bx
0x180001774  add     rax, rax
0x180001777  mov     rcx, [rsi+rax*8+8]; Block
0x18000177c  test    rcx, rcx
0x18000177f  jz      short loc_180001787
0x180001781  call    cs:__imp_free
0x180001787  inc     bx
0x18000178a  movsx   eax, bx
0x18000178d  cmp     eax, edi
0x18000178f  jl      short loc_180001770
0x180001791  xor     eax, eax
0x180001793  xor     edx, edx; Val
0x180001795  mov     r8d, 80h; Size
0x18000179b  mov     cs:word_18001CA40, ax
0x1800017a2  mov     rcx, rsi; void *
0x1800017a5  mov     rbx, [rsp+28h+arg_0]
0x1800017aa  mov     rsi, [rsp+28h+arg_8]
0x1800017af  add     rsp, 20h
0x1800017b3  pop     rdi
0x1800017b4  jmp     memset_0
```
