# YUVCopy(uchar const *,uchar *,long,long,long,long,long,long,long,long)

- ea: `0x180002c88`
- end: `0x180002d9b`
- name: `?YUVCopy@@YAXPEBEPEAEJJJJJJJJ@Z`
- size: `275`
- prototype: `void __fastcall(const unsigned __int8 *Src, unsigned __int8 *, int, int, int, int, int, int, int)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x180002a10`
- `0x180012120`
- `0x180016810`
- `0x18001de30`
- `0x18001e110`
- `0x18001e5b0`
- `0x18001f120`
- `0x18001f390`
- `0x18001ffa0`
- `0x180020bb0`
- `0x180027c50`
- `0x1800283c0`

## callees

- `0x180002c88`
- `0x180029fc0`

## pseudocode

```c
void __fastcall YUVCopy(
        const unsigned __int8 *Src,
        unsigned __int8 *a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9)
{
  int v9; // r10d
  int v12; // eax
  int v13; // eax
  int v14; // ecx
  __int64 v15; // r10
  const unsigned __int8 *v16; // rdx
  unsigned __int8 *v17; // r8
  int i; // r9d
  int v19; // ebx
  __int64 v20; // r15

  v9 = -a3;
  if ( a3 > 0 )
    v9 = a3;
  v12 = -(a9 * a8);
  if ( a9 * a8 > 0 )
    v12 = a9 * a8;
  if ( v12 <= v9 )
  {
    v13 = -(a9 * a5);
    if ( a9 * a5 > 0 )
      v13 = a9 * a5;
    if ( v13 <= v9 )
    {
      if ( a6 == 1 && a7 == 1 )
      {
        v19 = 0;
        if ( a9 > 0 )
        {
          v20 = a4;
          do
          {
            memcpy_0(a2, Src, a8);
            Src += v20;
            a2 += a5;
            ++v19;
          }
          while ( v19 < a9 );
        }
      }
      else
      {
        v14 = 0;
        if ( a9 > 0 )
        {
          v15 = a4;
          do
          {
            v16 = Src;
            v17 = a2;
            for ( i = 0; i < a8; v17 += a7 )
            {
              ++i;
              *v17 = *v16;
              v16 += a6;
            }
            Src += v15;
            a2 += a5;
            ++v14;
          }
          while ( v14 < a9 );
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180002c88  push    rbx
0x180002c8a  push    rsi
0x180002c8b  push    rdi
0x180002c8c  push    r12
0x180002c8e  push    r14
0x180002c90  push    r15
0x180002c92  sub     rsp, 28h
0x180002c96  movsxd  r11, [rsp+58h+arg_38]
0x180002c9e  mov     r10d, r8d
0x180002ca1  neg     r10d
0x180002ca4  mov     rdi, rdx
0x180002ca7  mov     rsi, rcx
0x180002caa  cmovs   r10d, r8d
0x180002cae  mov     r8d, r11d
0x180002cb1  imul    r8d, [rsp+58h+arg_40]
0x180002cba  mov     eax, r8d
0x180002cbd  neg     eax
0x180002cbf  cmovs   eax, r8d
0x180002cc3  cmp     eax, r10d
0x180002cc6  jg      short loc_180002CE6
0x180002cc8  movsxd  rdx, [rsp+58h+arg_20]
0x180002cd0  mov     ecx, edx
0x180002cd2  imul    ecx, [rsp+58h+arg_40]
0x180002cda  mov     eax, ecx
0x180002cdc  neg     eax
0x180002cde  cmovs   eax, ecx
0x180002ce1  cmp     eax, r10d
0x180002ce4  jle     short loc_180002CF4
0x180002ce6  add     rsp, 28h
0x180002cea  pop     r15
0x180002cec  pop     r14
0x180002cee  pop     r12
0x180002cf0  pop     rdi
0x180002cf1  pop     rsi
0x180002cf2  pop     rbx
0x180002cf3  retn
0x180002cf4  cmp     [rsp+58h+arg_28], 1
0x180002cfc  jz      short loc_180002D55
0x180002cfe  xor     ebx, ebx
0x180002d00  mov     ecx, ebx
0x180002d02  cmp     [rsp+58h+arg_40], ebx
0x180002d09  jle     short loc_180002CE6
0x180002d0b  movsxd  r10, r9d
0x180002d0e  mov     r14, rdx
0x180002d11  mov     rdx, rsi
0x180002d14  mov     r8, rdi
0x180002d17  mov     r9d, ebx
0x180002d1a  test    r11d, r11d
0x180002d1d  jle     short loc_180002D42
0x180002d1f  movsxd  r15, [rsp+58h+arg_28]
0x180002d27  movsxd  r12, [rsp+58h+arg_30]
0x180002d2f  mov     al, [rdx]
0x180002d31  inc     r9d
0x180002d34  mov     [r8], al
0x180002d37  add     rdx, r15
0x180002d3a  add     r8, r12
0x180002d3d  cmp     r9d, r11d
0x180002d40  jl      short loc_180002D2F
0x180002d42  add     rsi, r10
0x180002d45  add     rdi, r14
0x180002d48  inc     ecx
0x180002d4a  cmp     ecx, [rsp+58h+arg_40]
0x180002d51  jl      short loc_180002D11
0x180002d53  jmp     short loc_180002CE6
0x180002d55  cmp     [rsp+58h+arg_30], 1
0x180002d5d  jnz     short loc_180002CFE
0x180002d5f  xor     ebx, ebx
0x180002d61  cmp     [rsp+58h+arg_40], ebx
0x180002d68  jle     loc_180002CE6
0x180002d6e  mov     r14, r11
0x180002d71  movsxd  r15, r9d
0x180002d74  mov     r12, rdx
0x180002d77  mov     r8, r14; Size
0x180002d7a  mov     rdx, rsi; Src
0x180002d7d  mov     rcx, rdi; void *
0x180002d80  call    memcpy_0
0x180002d85  add     rsi, r15
0x180002d88  add     rdi, r12
0x180002d8b  inc     ebx
0x180002d8d  cmp     ebx, [rsp+58h+arg_40]
0x180002d94  jl      short loc_180002D77
0x180002d96  jmp     loc_180002CE6
```
