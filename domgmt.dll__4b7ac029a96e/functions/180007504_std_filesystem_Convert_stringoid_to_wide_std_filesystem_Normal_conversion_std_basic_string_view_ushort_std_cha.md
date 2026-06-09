# std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort,std::char_traits<ushort>>,std::filesystem::_Normal_conversion)

- ea: `0x180007504`
- end: `0x1800075d5`
- name: `??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z`
- size: `209`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x1800084c8`
- `0x18000993c`
- `0x180009ab8`
- `0x180009d90`
- `0x180009ec0`

## callees

- `0x18000739c`
- `0x180007504`
- `0x18000aa3c`
- `0x18000d5b4`

## pseudocode

```c
_QWORD *__fastcall std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(
        _QWORD *a1,
        __int64 a2)
{
  unsigned __int64 v2; // rbx
  __int64 v4; // rcx
  const void *v5; // rbp
  size_t v6; // rbx
  _QWORD *v7; // rax
  _QWORD *v8; // rcx
  _QWORD *v9; // rdi
  size_t v10; // rbx
  _QWORD *v12; // [rsp+60h] [rbp+8h] BYREF

  v12 = a1;
  v2 = *(_QWORD *)(a2 + 8);
  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 0;
  v4 = 0x7FFFFFFFFFFFFFFELL;
  if ( v2 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  v5 = *(const void **)a2;
  if ( v2 > 7 )
  {
    if ( (v2 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v4 = v2 | 7;
      if ( (v2 | 7) < 0xA )
        v4 = 10;
    }
    v12 = (_QWORD *)v4;
    v7 = std::wstring::_Allocate_for_capacity<0>(v4, &v12);
    v8 = v12;
    a1[2] = v2;
    v9 = v7;
    a1[3] = v8;
    v10 = 2 * v2;
    *a1 = v7;
    memcpy_0(v7, v5, v10);
    *(_WORD *)((char *)v9 + v10) = 0;
  }
  else
  {
    a1[2] = v2;
    v6 = 2 * v2;
    a1[3] = 7;
    memcpy_0(a1, v5, v6);
    *(_WORD *)((char *)a1 + v6) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180007504  mov     [rsp+arg_0], rcx
0x180007509  push    rbx
0x18000750a  push    rbp
0x18000750b  push    rsi
0x18000750c  push    rdi
0x18000750d  sub     rsp, 38h
0x180007511  mov     rbx, [rdx+8]
0x180007515  xorps   xmm0, xmm0
0x180007518  movups  xmmword ptr [rcx], xmm0
0x18000751b  mov     qword ptr [rcx+10h], 0
0x180007523  mov     rsi, rcx
0x180007526  mov     qword ptr [rcx+18h], 0
0x18000752e  mov     rcx, 7FFFFFFFFFFFFFFEh
0x180007538  cmp     rbx, rcx
0x18000753b  ja      loc_1800075CF
0x180007541  mov     rbp, [rdx]
0x180007544  cmp     rbx, 7
0x180007548  ja      short loc_18000756F
0x18000754a  mov     [rsi+10h], rbx
0x18000754e  mov     rdx, rbp; Src
0x180007551  add     rbx, rbx
0x180007554  mov     qword ptr [rsi+18h], 7
0x18000755c  mov     r8, rbx; Size
0x18000755f  mov     rcx, rsi; void *
0x180007562  call    memcpy_0
0x180007567  xor     eax, eax
0x180007569  mov     [rbx+rsi], ax
0x18000756d  jmp     short loc_1800075C3
0x18000756f  mov     rax, rbx
0x180007572  or      rax, 7
0x180007576  cmp     rax, rcx
0x180007579  ja      short loc_18000758A
0x18000757b  mov     edx, 0Ah
0x180007580  mov     rcx, rax
0x180007583  cmp     rax, rdx
0x180007586  cmovb   rcx, rdx
0x18000758a  lea     rdx, [rsp+58h+arg_0]
0x18000758f  mov     [rsp+58h+arg_0], rcx
0x180007594  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x180007599  mov     rcx, [rsp+58h+arg_0]
0x18000759e  mov     rdx, rbp; Src
0x1800075a1  mov     [rsi+10h], rbx
0x1800075a5  mov     rdi, rax
0x1800075a8  mov     [rsi+18h], rcx
0x1800075ac  add     rbx, rbx
0x1800075af  mov     rcx, rax; void *
0x1800075b2  mov     [rsi], rax
0x1800075b5  mov     r8, rbx; Size
0x1800075b8  call    memcpy_0
0x1800075bd  xor     ecx, ecx
0x1800075bf  mov     [rbx+rdi], cx
0x1800075c3  mov     rax, rsi
0x1800075c6  add     rsp, 38h
0x1800075ca  pop     rdi
0x1800075cb  pop     rsi
0x1800075cc  pop     rbp
0x1800075cd  pop     rbx
0x1800075ce  retn
0x1800075cf  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
