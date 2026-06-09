# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180007f40`
- end: `0x180008007`
- name: `??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z`
- size: `199`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x180007dd4`
- `0x1800083ec`
- `0x180009f44`
- `0x18000c460`
- `0x18000de8c`
- `0x18000eae0`
- `0x180010170`
- `0x180010610`
- `0x180010864`

## callees

- `0x1800035e6`
- `0x180007ac0`
- `0x180007f40`
- `0x18000974c`

## pseudocode

```c
__int64 __fastcall std::wstring::wstring(__int64 a1, __int64 a2)
{
  _OWORD *v2; // rsi
  unsigned __int64 v4; // rdi
  __int64 v5; // rax
  unsigned __int64 v6; // rcx
  _QWORD *v7; // rax
  __int64 v9; // [rsp+30h] [rbp+8h] BYREF

  v2 = (_OWORD *)a2;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  v4 = *(_QWORD *)(a2 + 16);
  if ( *(_QWORD *)(a2 + 24) > 7u )
    v2 = *(_OWORD **)a2;
  v5 = 0x7FFFFFFFFFFFFFFELL;
  if ( v4 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( v4 > 7 )
  {
    v6 = v4 | 7;
    if ( (v4 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v5 = v4 | 7;
      if ( v6 < 0xA )
        v5 = 10;
    }
    v9 = v5;
    v7 = std::wstring::_Allocate_for_capacity<0>(v6, &v9);
    *(_QWORD *)(a1 + 24) = v9;
    *(_QWORD *)a1 = v7;
    *(_QWORD *)(a1 + 16) = v4;
    memcpy_0(v7, v2, 2 * v4 + 2);
  }
  else
  {
    *(_QWORD *)(a1 + 16) = v4;
    *(_QWORD *)(a1 + 24) = 7;
    *(_OWORD *)a1 = *v2;
  }
  return a1;
}

```

## disassembly

```asm
0x180007f40  mov     [rsp+arg_8], rbx
0x180007f45  mov     [rsp+arg_10], rsi
0x180007f4a  push    rdi
0x180007f4b  sub     rsp, 20h
0x180007f4f  mov     rsi, rdx
0x180007f52  xorps   xmm0, xmm0
0x180007f55  movups  xmmword ptr [rcx], xmm0
0x180007f58  mov     qword ptr [rcx+10h], 0
0x180007f60  mov     rbx, rcx
0x180007f63  mov     qword ptr [rcx+18h], 0
0x180007f6b  mov     rdi, [rdx+10h]
0x180007f6f  mov     edx, 7
0x180007f74  cmp     [rsi+18h], rdx
0x180007f78  jbe     short loc_180007F7D
0x180007f7a  mov     rsi, [rsi]
0x180007f7d  mov     rax, 7FFFFFFFFFFFFFFEh
0x180007f87  cmp     rdi, rax
0x180007f8a  ja      short loc_180008001
0x180007f8c  cmp     rdi, rdx
0x180007f8f  ja      short loc_180007FA2
0x180007f91  mov     [rcx+10h], rdi
0x180007f95  mov     [rcx+18h], rdx
0x180007f99  movups  xmm0, xmmword ptr [rsi]
0x180007f9c  movdqu  xmmword ptr [rcx], xmm0
0x180007fa0  jmp     short loc_180007FEE
0x180007fa2  mov     rcx, rdi
0x180007fa5  or      rcx, rdx
0x180007fa8  cmp     rcx, rax
0x180007fab  ja      short loc_180007FBC
0x180007fad  mov     edx, 0Ah
0x180007fb2  mov     rax, rcx
0x180007fb5  cmp     rcx, rdx
0x180007fb8  cmovb   rax, rdx
0x180007fbc  lea     rdx, [rsp+28h+arg_0]
0x180007fc1  mov     [rsp+28h+arg_0], rax
0x180007fc6  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x180007fcb  mov     rcx, [rsp+28h+arg_0]
0x180007fd0  lea     r8, ds:2[rdi*2]; Size
0x180007fd8  mov     [rbx+18h], rcx
0x180007fdc  mov     rdx, rsi; Src
0x180007fdf  mov     rcx, rax; void *
0x180007fe2  mov     [rbx], rax
0x180007fe5  mov     [rbx+10h], rdi
0x180007fe9  call    memcpy_0
0x180007fee  mov     rsi, [rsp+28h+arg_10]
0x180007ff3  mov     rax, rbx
0x180007ff6  mov     rbx, [rsp+28h+arg_8]
0x180007ffb  add     rsp, 20h
0x180007fff  pop     rdi
0x180008000  retn
0x180008001  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
