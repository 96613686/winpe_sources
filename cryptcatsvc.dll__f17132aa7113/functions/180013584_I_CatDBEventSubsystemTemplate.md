# I_CatDBEventSubsystemTemplate

- ea: `0x180013584`
- end: `0x180013621`
- name: `I_CatDBEventSubsystemTemplate`
- size: `157`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001c03c`
- `0x18001cca0`

## callees

- `0x18000be40`
- `0x180013584`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800135fe`
- `ntdll!EtwEventWrite` at `0x1800135fe`
- `ntdll!EtwEventEnabled` at `0x1800135be`
- `ntdll!EtwEventEnabled` at `0x1800135be`

## pseudocode

```c
void __fastcall I_CatDBEventSubsystemTemplate(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  __int128 v5; // [rsp+20h] [rbp-28h] BYREF

  v5 = 0;
  if ( qword_180032A08 && (unsigned __int8)EtwEventEnabled(qword_180032A08, a2) )
  {
    *(_QWORD *)&v5 = a1;
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)(a1 + 2 * v4) );
    *((_QWORD *)&v5 + 1) = (unsigned int)(2 * v4 + 2);
    EtwEventWrite(qword_180032A08, a2, 1, &v5);
  }
}

```

## disassembly

```asm
0x180013584  mov     [rsp+arg_0], rbx
0x180013589  mov     [rsp+arg_10], rsi
0x18001358e  push    rdi
0x18001358f  sub     rsp, 40h
0x180013593  mov     rax, cs:__security_cookie
0x18001359a  xor     rax, rsp
0x18001359d  mov     [rsp+48h+var_18], rax
0x1800135a2  mov     rbx, rcx
0x1800135a5  xor     esi, esi
0x1800135a7  mov     rcx, cs:qword_180032A08
0x1800135ae  xorps   xmm0, xmm0
0x1800135b1  mov     rdi, rdx
0x1800135b4  movups  [rsp+48h+var_28], xmm0
0x1800135b9  test    rcx, rcx
0x1800135bc  jz      short loc_180013604
0x1800135be  call    cs:__imp_EtwEventEnabled
0x1800135c4  test    al, al
0x1800135c6  jz      short loc_180013604
0x1800135c8  mov     qword ptr [rsp+48h+var_28], rbx
0x1800135cd  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800135d1  inc     rax
0x1800135d4  cmp     [rbx+rax*2], si
0x1800135d8  jnz     short loc_1800135D1
0x1800135da  mov     rcx, cs:qword_180032A08
0x1800135e1  lea     eax, ds:2[rax*2]
0x1800135e8  lea     r9, [rsp+48h+var_28]
0x1800135ed  mov     dword ptr [rsp+48h+var_28+8], eax
0x1800135f1  mov     r8d, 1
0x1800135f7  mov     dword ptr [rsp+48h+var_28+0Ch], esi
0x1800135fb  mov     rdx, rdi
0x1800135fe  call    cs:__imp_EtwEventWrite
0x180013604  mov     rcx, [rsp+48h+var_18]
0x180013609  xor     rcx, rsp; StackCookie
0x18001360c  call    __security_check_cookie
0x180013611  mov     rbx, [rsp+48h+arg_0]
0x180013616  mov     rsi, [rsp+48h+arg_10]
0x18001361b  add     rsp, 40h
0x18001361f  pop     rdi
0x180013620  retn
```
