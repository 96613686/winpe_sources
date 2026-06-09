# YUVConversion(uchar const *,uchar *,long,long,long,long,long,long,long,long)

- ea: `0x1800145b4`
- end: `0x1800146b2`
- name: `?YUVConversion@@YAXPEBEPEAEJJJJJJJJ@Z`
- size: `254`
- prototype: `void __fastcall(const unsigned __int8 *Src, unsigned __int8 *, int, int, int, int, int, int, int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180020eb0`
- `0x180027fe0`
- `0x180028740`

## callees

- `0x1800145b4`
- `0x180029fc0`

## pseudocode

```c
void __fastcall YUVConversion(
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
  int v14; // ebx
  __int64 v15; // r15
  int v16; // ecx
  __int64 v17; // r15
  const unsigned __int8 *v18; // rdx
  unsigned __int8 *v19; // r8
  int i; // r9d

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
      v14 = 0;
      if ( a7 == 1 )
      {
        if ( a9 > 0 )
        {
          v15 = a4;
          do
          {
            memcpy_0(a2, Src, a8);
            Src += v15;
            a2 += a5;
            ++v14;
          }
          while ( v14 < a9 );
        }
      }
      else
      {
        v16 = 0;
        if ( a9 > 0 )
        {
          v17 = a4;
          do
          {
            v18 = Src;
            v19 = a2;
            for ( i = 0; i < a8; v19 += a7 )
            {
              ++i;
              *v19 = *v18++;
            }
            a2 += a5;
            ++v16;
            Src += v17;
          }
          while ( v16 < a9 );
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800145b4  push    rbx
0x1800145b6  push    rsi
0x1800145b7  push    rdi
0x1800145b8  push    r12
0x1800145ba  push    r14
0x1800145bc  push    r15
0x1800145be  sub     rsp, 28h
0x1800145c2  movsxd  r11, [rsp+58h+arg_38]
0x1800145ca  mov     r10d, r8d
0x1800145cd  neg     r10d
0x1800145d0  mov     rdi, rdx
0x1800145d3  mov     rsi, rcx
0x1800145d6  cmovs   r10d, r8d
0x1800145da  mov     r8d, r11d
0x1800145dd  imul    r8d, [rsp+58h+arg_40]
0x1800145e6  mov     eax, r8d
0x1800145e9  neg     eax
0x1800145eb  cmovs   eax, r8d
0x1800145ef  cmp     eax, r10d
0x1800145f2  jg      loc_1800146A4
0x1800145f8  movsxd  rdx, [rsp+58h+arg_20]
0x180014600  mov     ecx, edx
0x180014602  imul    ecx, [rsp+58h+arg_40]
0x18001460a  mov     eax, ecx
0x18001460c  neg     eax
0x18001460e  cmovs   eax, ecx
0x180014611  cmp     eax, r10d
0x180014614  jg      loc_1800146A4
0x18001461a  xor     ebx, ebx
0x18001461c  cmp     [rsp+58h+arg_30], 1
0x180014624  jnz     short loc_180014659
0x180014626  cmp     [rsp+58h+arg_40], ebx
0x18001462d  jle     short loc_1800146A4
0x18001462f  mov     r14, r11
0x180014632  movsxd  r15, r9d
0x180014635  mov     r12, rdx
0x180014638  mov     r8, r14; Size
0x18001463b  mov     rdx, rsi; Src
0x18001463e  mov     rcx, rdi; void *
0x180014641  call    memcpy_0
0x180014646  add     rsi, r15
0x180014649  add     rdi, r12
0x18001464c  inc     ebx
0x18001464e  cmp     ebx, [rsp+58h+arg_40]
0x180014655  jl      short loc_180014638
0x180014657  jmp     short loc_1800146A4
0x180014659  mov     ecx, ebx
0x18001465b  cmp     [rsp+58h+arg_40], ebx
0x180014662  jle     short loc_1800146A4
0x180014664  mov     r14, rdx
0x180014667  movsxd  r15, r9d
0x18001466a  mov     rdx, rsi
0x18001466d  mov     r8, rdi
0x180014670  mov     r9d, ebx
0x180014673  test    r11d, r11d
0x180014676  jle     short loc_180014693
0x180014678  movsxd  r10, [rsp+58h+arg_30]
0x180014680  mov     al, [rdx]
0x180014682  inc     r9d
0x180014685  mov     [r8], al
0x180014688  inc     rdx
0x18001468b  add     r8, r10
0x18001468e  cmp     r9d, r11d
0x180014691  jl      short loc_180014680
0x180014693  add     rdi, r14
0x180014696  inc     ecx
0x180014698  add     rsi, r15
0x18001469b  cmp     ecx, [rsp+58h+arg_40]
0x1800146a2  jl      short loc_18001466A
0x1800146a4  add     rsp, 28h
0x1800146a8  pop     r15
0x1800146aa  pop     r14
0x1800146ac  pop     r12
0x1800146ae  pop     rdi
0x1800146af  pop     rsi
0x1800146b0  pop     rbx
0x1800146b1  retn
```
