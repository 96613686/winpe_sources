# CUstUtil::CreateStringCopy(ushort *,ushort * *)

- ea: `0x18001d264`
- end: `0x18001d31f`
- name: `?CreateStringCopy@CUstUtil@@SAJPEAGPEAPEAG@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001b5ec`
- `0x18001b7bc`
- `0x18001c058`
- `0x18001c6fc`

## callees

- `0x180008e5c`
- `0x180008ea0`
- `0x18000baec`
- `0x18001afa0`
- `0x18001d264`

## pseudocode

```c
__int64 __fastcall CUstUtil::CreateStringCopy(unsigned __int16 *a1, unsigned __int16 **a2)
{
  int v4; // ebx
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rax
  unsigned __int16 *v7; // rax
  __int64 v8; // r9
  unsigned __int64 v10; // [rsp+40h] [rbp+18h] BYREF

  v10 = 0;
  v4 = StringCchLengthW(a1, 0x7FFFFFFFu, &v10);
  if ( v4 >= 0 )
  {
    v5 = v10 + 1;
    v6 = 2 * (v10 + 1);
    if ( !is_mul_ok(v10 + 1, 2u) )
      v6 = -1;
    v7 = (unsigned __int16 *)operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
    *a2 = v7;
    if ( v7 )
    {
      return (unsigned int)StringCchCopyW(v7, v5, a1);
    }
    else
    {
      v4 = -2147024882;
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_4605e0ddd8c23f27c27a9c87ef558f20_Traceguids, v8);
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001d264  mov     rax, rsp
0x18001d267  mov     [rax+8], rbx
0x18001d26b  mov     [rax+10h], rsi
0x18001d26f  push    rdi
0x18001d270  sub     rsp, 20h
0x18001d274  mov     rsi, rdx
0x18001d277  mov     qword ptr [rax+18h], 0
0x18001d27f  mov     edx, 7FFFFFFFh; unsigned __int64
0x18001d284  lea     r8, [rax+18h]; unsigned __int64 *
0x18001d288  mov     rdi, rcx
0x18001d28b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001d290  mov     ebx, eax
0x18001d292  test    eax, eax
0x18001d294  js      short loc_18001D30D
0x18001d296  mov     rbx, [rsp+28h+arg_10]
0x18001d29b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001d2a2  inc     rbx
0x18001d2a5  mov     eax, 2
0x18001d2aa  mul     rbx
0x18001d2ad  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d2b4  cmovb   rax, rcx
0x18001d2b8  mov     rcx, rax; unsigned __int64
0x18001d2bb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001d2c0  mov     [rsi], rax
0x18001d2c3  test    rax, rax
0x18001d2c6  jnz     short loc_18001D2FD
0x18001d2c8  mov     ebx, 8007000Eh
0x18001d2cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d2d4  lea     rax, WPP_GLOBAL_Control
0x18001d2db  cmp     rcx, rax
0x18001d2de  jz      short loc_18001D30D
0x18001d2e0  test    byte ptr [rcx+1Ch], 1
0x18001d2e4  jz      short loc_18001D30D
0x18001d2e6  mov     rcx, [rcx+10h]
0x18001d2ea  lea     r8, WPP_4605e0ddd8c23f27c27a9c87ef558f20_Traceguids
0x18001d2f1  mov     edx, 0Ah
0x18001d2f6  call    WPP_SF_
0x18001d2fb  jmp     short loc_18001D30D
0x18001d2fd  mov     r8, rdi; unsigned __int16 *
0x18001d300  mov     rdx, rbx; unsigned __int64
0x18001d303  mov     rcx, rax; unsigned __int16 *
0x18001d306  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001d30b  mov     ebx, eax
0x18001d30d  mov     rsi, [rsp+28h+arg_8]
0x18001d312  mov     eax, ebx
0x18001d314  mov     rbx, [rsp+28h+arg_0]
0x18001d319  add     rsp, 20h
0x18001d31d  pop     rdi
0x18001d31e  retn
```
