# std::make_optional<std::filesystem::path,std::filesystem::path &,0>(std::filesystem::path &)

- ea: `0x1800016c0`
- end: `0x180001785`
- name: `??$make_optional@Vpath@filesystem@std@@AEAV123@$0A@@std@@YA?AV?$optional@Vpath@filesystem@std@@@0@AEAVpath@filesystem@0@@Z`
- size: `197`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180001380`

## callees

- `0x1800016c0`
- `0x180001f30`
- `0x180003e14`
- `0x18000a6d4`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000170e`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000170e`

## pseudocode

```c
__int64 __fastcall std::make_optional<std::filesystem::path,std::filesystem::path &,0>(__int64 a1, __int64 a2)
{
  _OWORD *v2; // rsi
  unsigned __int64 v4; // rdi
  __int64 v5; // rcx
  void *v6; // rax
  __int64 result; // rax
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF

  v8 = a1;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  v2 = (_OWORD *)a2;
  *(_QWORD *)(a1 + 24) = 0;
  v4 = *(_QWORD *)(a2 + 16);
  if ( *(_QWORD *)(a2 + 24) > 7u )
    v2 = *(_OWORD **)a2;
  if ( v4 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( v4 > 7 )
  {
    v8 = std::wstring::_Calculate_growth(v4, 7);
    v6 = (void *)std::wstring::_Allocate_for_capacity<0>(v5, &v8);
    *(_QWORD *)(a1 + 24) = v8;
    *(_QWORD *)a1 = v6;
    *(_QWORD *)(a1 + 16) = v4;
    memcpy_0(v6, v2, 2 * v4 + 2);
  }
  else
  {
    *(_QWORD *)(a1 + 16) = v4;
    *(_QWORD *)(a1 + 24) = 7;
    *(_OWORD *)a1 = *v2;
  }
  result = a1;
  *(_BYTE *)(a1 + 32) = 1;
  return result;
}

```

## disassembly

```asm
0x1800016c0  mov     [rsp+arg_8], rbx
0x1800016c5  mov     [rsp+arg_10], rsi
0x1800016ca  mov     [rsp+arg_0], rcx
0x1800016cf  push    rdi
0x1800016d0  sub     rsp, 30h
0x1800016d4  xor     eax, eax
0x1800016d6  xorps   xmm0, xmm0
0x1800016d9  movups  xmmword ptr [rcx], xmm0
0x1800016dc  mov     [rcx+10h], rax
0x1800016e0  mov     rsi, rdx
0x1800016e3  mov     [rcx+18h], rax
0x1800016e7  mov     rbx, rcx
0x1800016ea  cmp     qword ptr [rdx+18h], 7
0x1800016ef  mov     rdi, [rdx+10h]
0x1800016f3  jbe     short loc_1800016F8
0x1800016f5  mov     rsi, [rdx]
0x1800016f8  mov     r8, 7FFFFFFFFFFFFFFEh
0x180001702  cmp     rdi, r8
0x180001705  jbe     short loc_180001715
0x180001707  lea     rcx, aStringTooLong; "string too long"
0x18000170e  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180001715  cmp     rdi, 7
0x180001719  ja      short loc_18000172F
0x18000171b  mov     [rcx+10h], rdi
0x18000171f  mov     qword ptr [rcx+18h], 7
0x180001727  movups  xmm0, xmmword ptr [rsi]
0x18000172a  movups  xmmword ptr [rcx], xmm0
0x18000172d  jmp     short loc_18000176E
0x18000172f  mov     edx, 7
0x180001734  mov     rcx, rdi
0x180001737  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x18000173c  lea     rdx, [rsp+38h+arg_0]
0x180001741  mov     [rsp+38h+arg_0], rax
0x180001746  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x18000174b  mov     rcx, [rsp+38h+arg_0]
0x180001750  lea     r8, ds:2[rdi*2]; Size
0x180001758  mov     [rbx+18h], rcx
0x18000175c  mov     rdx, rsi; Src
0x18000175f  mov     rcx, rax; void *
0x180001762  mov     [rbx], rax
0x180001765  mov     [rbx+10h], rdi
0x180001769  call    memcpy_0
0x18000176e  mov     rsi, [rsp+38h+arg_10]
0x180001773  mov     rax, rbx
0x180001776  mov     byte ptr [rbx+20h], 1
0x18000177a  mov     rbx, [rsp+38h+arg_8]
0x18000177f  add     rsp, 30h
0x180001783  pop     rdi
0x180001784  retn
```
