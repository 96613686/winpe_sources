# EaLibCreateAndSetLimitTimer

- ea: `0x180003ca0`
- end: `0x180003d2c`
- name: `EaLibCreateAndSetLimitTimer`
- size: `140`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005cc0`

## callees

- `0x180003ca0`

## import_xrefs

- `ntdll!TpAllocTimer` at `0x180003cdf`
- `ntdll!TpAllocTimer` at `0x180003cdf`
- `ntdll!TpSetTimer` at `0x180003d14`
- `ntdll!TpSetTimer` at `0x180003d14`

## pseudocode

```c
__int64 __fastcall EaLibCreateAndSetLimitTimer(__int64 a1)
{
  __int64 v1; // rax
  __int64 result; // rax
  unsigned int v4; // edi
  __int64 v5; // rcx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 56);
  v6 = 0;
  if ( !*(_DWORD *)(v1 + 32) )
    return 0;
  result = TpAllocTimer(a1 + 128, EaLibTimeLimitCallback, a1, 0);
  v4 = result;
  if ( (int)result >= 0 )
  {
    v5 = *(_QWORD *)(a1 + 128);
    v6 = -10000000LL * *(unsigned int *)(*(_QWORD *)(a1 + 56) + 32LL);
    TpSetTimer(v5, &v6, 0, 1000);
    result = v4;
    *(_BYTE *)(a1 + 120) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x180003ca0  push    rbx
0x180003ca2  sub     rsp, 20h
0x180003ca6  mov     rax, [rcx+38h]
0x180003caa  mov     rbx, rcx
0x180003cad  mov     [rsp+28h+arg_0], 0
0x180003cb6  cmp     dword ptr [rax+20h], 0
0x180003cba  jnz     short loc_180003CC4
0x180003cbc  xor     eax, eax
0x180003cbe  add     rsp, 20h
0x180003cc2  pop     rbx
0x180003cc3  retn
0x180003cc4  mov     [rsp+28h+arg_8], rsi
0x180003cc9  lea     rdx, EaLibTimeLimitCallback
0x180003cd0  xor     r9d, r9d
0x180003cd3  mov     [rsp+28h+arg_10], rdi
0x180003cd8  mov     r8, rbx
0x180003cdb  sub     rcx, 0FFFFFFFFFFFFFF80h
0x180003cdf  call    cs:__imp_TpAllocTimer
0x180003ce5  mov     edi, eax
0x180003ce7  test    eax, eax
0x180003ce9  js      short loc_180003D20
0x180003ceb  mov     rdx, [rbx+38h]
0x180003cef  mov     r9d, 3E8h
0x180003cf5  mov     rcx, [rbx+80h]
0x180003cfc  mov     r8d, [rdx+20h]
0x180003d00  imul    rdx, r8, 0FFFFFFFFFF676980h
0x180003d07  xor     r8d, r8d
0x180003d0a  mov     [rsp+28h+arg_0], rdx
0x180003d0f  lea     rdx, [rsp+28h+arg_0]
0x180003d14  call    cs:__imp_TpSetTimer
0x180003d1a  mov     eax, edi
0x180003d1c  mov     byte ptr [rbx+78h], 1
0x180003d20  mov     rsi, [rsp+28h+arg_8]
0x180003d25  mov     rdi, [rsp+28h+arg_10]
0x180003d2a  jmp     short loc_180003CBE
```
