# STBUFF::STBUFF(int)

- ea: `0x180001948`
- end: `0x1800019b1`
- name: `??0STBUFF@@QEAA@H@Z`
- size: `105`
- prototype: `STBUFF *__fastcall(STBUFF *this)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x180001af4`
- `0x180001cd4`
- `0x180001dc8`
- `0x180002604`
- `0x180002dd0`
- `0x180003ec0`
- `0x1800047a4`
- `0x180004f8c`
- `0x180005168`
- `0x1800055f0`
- `0x1800057cc`
- `0x180005ab8`
- `0x180005d74`
- `0x1800061c0`

## callees

- `0x180001948`
- `0x18000678e`

## pseudocode

```c
STBUFF *__fastcall STBUFF::STBUFF(STBUFF *this)
{
  char *v1; // rbx
  char *v3; // rcx
  STBUFF *result; // rax

  v1 = (char *)this + 28;
  *((_DWORD *)this + 4) = 0;
  *((_QWORD *)this + 1) = (char *)this + 28;
  *(_QWORD *)this = &STBUFF::`vftable';
  *((_DWORD *)this + 5) = 64;
  *((_DWORD *)this + 6) = 0x4000;
  memset_0((char *)this + 28, 0, 0x40u);
  v3 = (char *)*((_QWORD *)this + 1);
  if ( v3 != v1 )
    memset_0(v3, 0, *((unsigned int *)this + 5));
  result = this;
  *((_WORD *)this + 46) = 0;
  return result;
}

```

## disassembly

```asm
0x180001948  mov     [rsp+arg_0], rbx
0x18000194d  push    rdi
0x18000194e  sub     rsp, 20h
0x180001952  lea     rbx, [rcx+1Ch]
0x180001956  mov     dword ptr [rcx+10h], 0
0x18000195d  lea     rax, ??_7STBUFF@@6B@; const STBUFF::`vftable'
0x180001964  mov     [rcx+8], rbx
0x180001968  mov     r8d, 40h ; '@'; Size
0x18000196e  mov     [rcx], rax
0x180001971  mov     [rcx+14h], r8d
0x180001975  mov     rdi, rcx
0x180001978  mov     dword ptr [rcx+18h], 4000h
0x18000197f  xor     edx, edx; Val
0x180001981  mov     rcx, rbx; void *
0x180001984  call    memset_0
0x180001989  mov     rcx, [rdi+8]; void *
0x18000198d  cmp     rcx, rbx
0x180001990  jz      short loc_18000199D
0x180001992  mov     r8d, [rdi+14h]; Size
0x180001996  xor     edx, edx; Val
0x180001998  call    memset_0
0x18000199d  mov     rbx, [rsp+28h+arg_0]
0x1800019a2  mov     rax, rdi
0x1800019a5  mov     word ptr [rdi+5Ch], 0
0x1800019ab  add     rsp, 20h
0x1800019af  pop     rdi
0x1800019b0  retn
```
