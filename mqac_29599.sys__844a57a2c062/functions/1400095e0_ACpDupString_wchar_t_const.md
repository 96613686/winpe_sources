# ACpDupString(wchar_t const *)

- ea: `0x1400095e0`
- end: `0x140009685`
- name: `?ACpDupString@@YAPEA_WPEB_W@Z`
- size: `165`
- prototype: `wchar_t *__fastcall(const wchar_t *Src)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x140004314`
- `0x1400058fc`
- `0x140007e3c`
- `0x1400085f4`
- `0x14000bb00`
- `0x14000d8a0`

## callees

- `0x140001128`
- `0x1400095e0`
- `0x14000b730`
- `0x140024cc0`

## pseudocode

```c
wchar_t *__fastcall ACpDupString(const wchar_t *Src)
{
  __int64 v2; // rax
  __int64 v3; // rsi
  __int64 v4; // rax
  unsigned __int64 v5; // kr00_8
  void *v6; // rax
  void *v7; // rdi

  v2 = -1;
  do
    ++v2;
  while ( Src[v2] );
  v3 = v2 + 1;
  v5 = v2 + 1;
  v4 = 2 * (v2 + 1);
  if ( !is_mul_ok(v5, 2u) )
    v4 = -1;
  v6 = (void *)operator new(v4, 256, 1128354125, NormalPoolPriority);
  v7 = v6;
  if ( v6 )
  {
    memmove(v6, Src, 2 * v3);
    return (wchar_t *)v7;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_PS(
        WPP_GLOBAL_Control->Queue.ListEntry.Blink,
        16,
        (unsigned int)&WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids,
        2 * v3,
        (__int64)Src);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1400095e0  push    rbx
0x1400095e2  push    rbp
0x1400095e3  push    rsi
0x1400095e4  push    rdi
0x1400095e5  sub     rsp, 38h
0x1400095e9  mov     rbx, rcx
0x1400095ec  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400095f0  mov     rax, rcx
0x1400095f3  xor     ebp, ebp
0x1400095f5  inc     rax
0x1400095f8  cmp     [rbx+rax*2], bp
0x1400095fc  jnz     short loc_1400095F5
0x1400095fe  lea     rsi, [rax+1]
0x140009602  mov     r9d, 10h; enum _EX_POOL_PRIORITY
0x140009608  mov     eax, 2
0x14000960d  mov     r8d, 4341514Dh; unsigned int
0x140009613  mul     rsi
0x140009616  mov     edx, 100h; unsigned __int64
0x14000961b  cmovb   rax, rcx
0x14000961f  mov     rcx, rax; unsigned __int64
0x140009622  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x140009627  mov     rdi, rax
0x14000962a  test    rax, rax
0x14000962d  jnz     short loc_140009669
0x14000962f  mov     rcx, cs:WPP_GLOBAL_Control
0x140009636  lea     rax, WPP_GLOBAL_Control
0x14000963d  cmp     rcx, rax
0x140009640  jz      short loc_140009665
0x140009642  mov     eax, [rcx+6Ch]
0x140009645  test    al, 1
0x140009647  jz      short loc_140009665
0x140009649  mov     rcx, [rcx+58h]
0x14000964d  lea     r9, [rsi+rsi]
0x140009651  lea     edx, [rdi+10h]
0x140009654  mov     [rsp+58h+var_38], rbx
0x140009659  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140009660  call    WPP_SF_PS
0x140009665  xor     eax, eax
0x140009667  jmp     short loc_14000967B
0x140009669  lea     r8, [rsi+rsi]; Size
0x14000966d  mov     rdx, rbx; Src
0x140009670  mov     rcx, rdi; void *
0x140009673  call    memmove
0x140009678  mov     rax, rdi
0x14000967b  add     rsp, 38h
0x14000967f  pop     rdi
0x140009680  pop     rsi
0x140009681  pop     rbp
0x140009682  pop     rbx
0x140009683  retn
```
