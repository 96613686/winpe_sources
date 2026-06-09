# std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort,std::char_traits<ushort>>,std::filesystem::_Normal_conversion)

- ea: `0x1800015e0`
- end: `0x1800016b9`
- name: `??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z`
- size: `217`
- prototype: `char **__fastcall(char **, __int64)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x1800012a0`
- `0x180001380`
- `0x180001520`
- `0x180001590`
- `0x1800035b0`

## callees

- `0x1800015e0`
- `0x180001f30`
- `0x180003e14`
- `0x18000a6d4`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000161b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000161b`

## pseudocode

```c
char **__fastcall std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(
        char **a1,
        __int64 a2)
{
  unsigned __int64 v2; // rsi
  const void *v4; // rbp
  __int64 v5; // r14
  __int64 v6; // rcx
  char *v7; // rax
  char *v8; // rdi
  __int64 v10; // [rsp+50h] [rbp+8h] BYREF

  v10 = (__int64)a1;
  v2 = *(_QWORD *)(a2 + 8);
  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 0;
  if ( v2 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  v4 = *(const void **)a2;
  v5 = 2 * v2;
  if ( v2 > 7 )
  {
    v10 = std::wstring::_Calculate_growth(v2, 7);
    v7 = (char *)std::wstring::_Allocate_for_capacity<0>(v6, &v10);
    a1[3] = (char *)v10;
    *a1 = v7;
    v8 = v7;
    a1[2] = (char *)v2;
    memcpy_0(v7, v4, 2 * v2);
    *(_WORD *)&v8[v5] = 0;
  }
  else
  {
    a1[2] = (char *)v2;
    a1[3] = (char *)7;
    memcpy_0(a1, v4, 2 * v2);
    *(_WORD *)((char *)a1 + v5) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x1800015e0  mov     [rsp+arg_0], rcx
0x1800015e5  push    rbx
0x1800015e6  push    rsi
0x1800015e7  push    r15
0x1800015e9  sub     rsp, 30h
0x1800015ed  mov     rsi, [rdx+8]
0x1800015f1  xor     r15d, r15d
0x1800015f4  xorps   xmm0, xmm0
0x1800015f7  mov     r8, 7FFFFFFFFFFFFFFEh
0x180001601  mov     rbx, rcx
0x180001604  movups  xmmword ptr [rcx], xmm0
0x180001607  mov     [rcx+10h], r15
0x18000160b  mov     [rcx+18h], r15
0x18000160f  cmp     rsi, r8
0x180001612  jbe     short loc_180001622
0x180001614  lea     rcx, aStringTooLong; "string too long"
0x18000161b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180001622  mov     [rsp+48h+arg_8], rbp
0x180001627  mov     rbp, [rdx]
0x18000162a  mov     [rsp+48h+arg_18], r14
0x18000162f  lea     r14, [rsi+rsi]
0x180001633  cmp     rsi, 7
0x180001637  ja      short loc_180001657
0x180001639  mov     r8, r14; Size
0x18000163c  mov     [rcx+10h], rsi
0x180001640  mov     rdx, rbp; Src
0x180001643  mov     qword ptr [rcx+18h], 7
0x18000164b  call    memcpy_0
0x180001650  mov     [r14+rbx], r15w
0x180001655  jmp     short loc_1800016A3
0x180001657  mov     edx, 7
0x18000165c  mov     [rsp+48h+arg_10], rdi
0x180001661  mov     rcx, rsi
0x180001664  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x180001669  lea     rdx, [rsp+48h+arg_0]
0x18000166e  mov     [rsp+48h+arg_0], rax
0x180001673  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x180001678  mov     rcx, [rsp+48h+arg_0]
0x18000167d  mov     r8, r14; Size
0x180001680  mov     [rbx+18h], rcx
0x180001684  mov     rdx, rbp; Src
0x180001687  mov     rcx, rax; void *
0x18000168a  mov     [rbx], rax
0x18000168d  mov     rdi, rax
0x180001690  mov     [rbx+10h], rsi
0x180001694  call    memcpy_0
0x180001699  mov     [r14+rdi], r15w
0x18000169e  mov     rdi, [rsp+48h+arg_10]
0x1800016a3  mov     r14, [rsp+48h+arg_18]
0x1800016a8  mov     rax, rbx
0x1800016ab  mov     rbp, [rsp+48h+arg_8]
0x1800016b0  add     rsp, 30h
0x1800016b4  pop     r15
0x1800016b6  pop     rsi
0x1800016b7  pop     rbx
0x1800016b8  retn
```
