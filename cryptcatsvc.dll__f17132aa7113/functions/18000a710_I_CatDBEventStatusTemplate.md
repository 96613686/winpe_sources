# I_CatDBEventStatusTemplate

- ea: `0x18000a710`
- end: `0x18000a78a`
- name: `I_CatDBEventStatusTemplate`
- size: `122`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a490`
- `0x18001b8f4`
- `0x18001c03c`
- `0x18001c9e0`
- `0x18001cca0`

## callees

- `0x18000a710`
- `0x18000be40`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000a771`
- `ntdll!EtwEventWrite` at `0x18000a771`
- `ntdll!EtwEventEnabled` at `0x18000a73f`
- `ntdll!EtwEventEnabled` at `0x18000a73f`

## pseudocode

```c
void __fastcall I_CatDBEventStatusTemplate(int a1, __int64 a2)
{
  __int128 v3; // [rsp+20h] [rbp-28h] BYREF
  int v4; // [rsp+50h] [rbp+8h] BYREF

  v4 = a1;
  v3 = 0;
  if ( qword_180032A08 )
  {
    if ( (unsigned __int8)EtwEventEnabled(qword_180032A08, a2) )
    {
      *(_QWORD *)&v3 = &v4;
      *((_QWORD *)&v3 + 1) = 4;
      EtwEventWrite(qword_180032A08, a2, 1, &v3);
    }
  }
}

```

## disassembly

```asm
0x18000a710  mov     [rsp+arg_0], ecx
0x18000a714  push    rbx
0x18000a715  sub     rsp, 40h
0x18000a719  mov     rax, cs:__security_cookie
0x18000a720  xor     rax, rsp
0x18000a723  mov     [rsp+48h+var_18], rax
0x18000a728  mov     rcx, cs:qword_180032A08
0x18000a72f  xorps   xmm0, xmm0
0x18000a732  mov     rbx, rdx
0x18000a735  movups  [rsp+48h+var_28], xmm0
0x18000a73a  test    rcx, rcx
0x18000a73d  jz      short loc_18000A777
0x18000a73f  call    cs:__imp_EtwEventEnabled
0x18000a745  test    al, al
0x18000a747  jz      short loc_18000A777
0x18000a749  mov     rcx, cs:qword_180032A08
0x18000a750  lea     rax, [rsp+48h+arg_0]
0x18000a755  lea     r9, [rsp+48h+var_28]
0x18000a75a  mov     qword ptr [rsp+48h+var_28], rax
0x18000a75f  mov     r8d, 1
0x18000a765  mov     qword ptr [rsp+48h+var_28+8], 4
0x18000a76e  mov     rdx, rbx
0x18000a771  call    cs:__imp_EtwEventWrite
0x18000a777  mov     rcx, [rsp+48h+var_18]
0x18000a77c  xor     rcx, rsp; StackCookie
0x18000a77f  call    __security_check_cookie
0x18000a784  add     rsp, 40h
0x18000a788  pop     rbx
0x18000a789  retn
```
