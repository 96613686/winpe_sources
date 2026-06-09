# CPoolAllocator::CreatePath(wchar_t const *)

- ea: `0x14000fbbc`
- end: `0x14000fc9a`
- name: `?CreatePath@CPoolAllocator@@SAPEA_WPEB_W@Z`
- size: `222`
- prototype: `wchar_t *__fastcall(const wchar_t *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x14000ecd0`
- `0x14000ed80`
- `0x140010984`

## callees

- `0x140001128`
- `0x140002f2c`
- `0x14000b730`
- `0x14000fbbc`

## pseudocode

```c
wchar_t *__fastcall CPoolAllocator::CreatePath(const wchar_t *a1)
{
  __int64 v1; // rdx
  __int64 v2; // rsi
  const wchar_t *v3; // rdi
  const wchar_t *v4; // rbp
  unsigned __int64 v5; // rax
  wchar_t *v6; // rax
  wchar_t *v7; // rbx

  v1 = -1;
  do
    ++v1;
  while ( a1[v1] );
  v2 = v1 + 2;
  v3 = a1 + 2;
  if ( a1[1] != 92 )
    v2 = v1;
  v4 = L"UNC\\";
  if ( a1[1] != 92 )
  {
    v3 = a1;
    v4 = &qword_140027730;
  }
  v5 = 2 * (v2 + 11);
  if ( !is_mul_ok(v2 + 11, 2u) )
    v5 = -1;
  v6 = (wchar_t *)operator new(v5, 0x100u, 0x4841514Du, LowPoolPriority);
  v7 = v6;
  if ( v6 )
  {
    StringCchPrintfW(v6, v2 + 11, L"\\Global??\\%s%s", v4, v3);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
  {
    WPP_SF_PS(
      WPP_GLOBAL_Control->Queue.ListEntry.Blink,
      37,
      (unsigned int)WPP_664e97eed756311217f592c2f10907d7_Traceguids,
      2 * v2 + 22,
      (__int64)v3);
  }
  return v7;
}

```

## disassembly

```asm
0x14000fbbc  push    rbx
0x14000fbbe  push    rbp
0x14000fbbf  push    rsi
0x14000fbc0  push    rdi
0x14000fbc1  push    r14
0x14000fbc3  push    r15
0x14000fbc5  sub     rsp, 38h
0x14000fbc9  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000fbcd  mov     rdx, r8
0x14000fbd0  xor     r15d, r15d
0x14000fbd3  inc     rdx
0x14000fbd6  cmp     [rcx+rdx*2], r15w
0x14000fbdb  jnz     short loc_14000FBD3
0x14000fbdd  cmp     word ptr [rcx+2], 5Ch ; '\'
0x14000fbe2  lea     rsi, [rdx+2]
0x14000fbe6  lea     rdi, [rcx+4]
0x14000fbea  mov     eax, 2
0x14000fbef  cmovnz  rsi, rdx
0x14000fbf3  lea     rbp, aUnc; "UNC\\"
0x14000fbfa  cmovnz  rdi, rcx
0x14000fbfe  lea     rcx, qword_140027730
0x14000fc05  cmovnz  rbp, rcx
0x14000fc09  lea     r14, [rsi+0Bh]
0x14000fc0d  mul     r14
0x14000fc10  mov     edx, 100h; unsigned __int64
0x14000fc15  cmovb   rax, r8
0x14000fc19  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x14000fc1c  mov     rcx, rax; unsigned __int64
0x14000fc1f  mov     r8d, 4841514Dh; unsigned int
0x14000fc25  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x14000fc2a  mov     rbx, rax
0x14000fc2d  test    rax, rax
0x14000fc30  jnz     short loc_14000FC6F
0x14000fc32  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fc39  lea     rax, WPP_GLOBAL_Control
0x14000fc40  cmp     rcx, rax
0x14000fc43  jz      short loc_14000FC89
0x14000fc45  mov     edx, [rcx+6Ch]
0x14000fc48  test    dl, 1
0x14000fc4b  jz      short loc_14000FC89
0x14000fc4d  mov     rcx, [rcx+58h]
0x14000fc51  lea     r9, ds:16h[rsi*2]
0x14000fc59  lea     edx, [rbx+25h]
0x14000fc5c  mov     [rsp+68h+var_48], rdi
0x14000fc61  lea     r8, WPP_664e97eed756311217f592c2f10907d7_Traceguids
0x14000fc68  call    WPP_SF_PS
0x14000fc6d  jmp     short loc_14000FC89
0x14000fc6f  mov     r9, rbp
0x14000fc72  mov     [rsp+68h+var_48], rdi
0x14000fc77  lea     r8, aGlobalSS; "\\Global??\\%s%s"
0x14000fc7e  mov     rdx, r14; unsigned __int64
0x14000fc81  mov     rcx, rbx; wchar_t *
0x14000fc84  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x14000fc89  mov     rax, rbx
0x14000fc8c  add     rsp, 38h
0x14000fc90  pop     r15
0x14000fc92  pop     r14
0x14000fc94  pop     rdi
0x14000fc95  pop     rsi
0x14000fc96  pop     rbp
0x14000fc97  pop     rbx
0x14000fc98  retn
```
