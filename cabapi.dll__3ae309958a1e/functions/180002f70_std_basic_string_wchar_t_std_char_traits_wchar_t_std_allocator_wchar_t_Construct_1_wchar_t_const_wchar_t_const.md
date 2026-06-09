# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)

- ea: `0x180002f70`
- end: `0x180003027`
- name: `??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z`
- size: `183`
- prototype: `__int64 __fastcall(__int64, const void *, unsigned __int64)`
- caller_count: `18`
- callee_count: `4`
- tags: ``

## callers

- `0x180005ea0`
- `0x1800069c0`
- `0x180006ac0`
- `0x180006b60`
- `0x180006d20`
- `0x180006fb0`
- `0x1800070f0`
- `0x180007220`
- `0x180007340`
- `0x180007490`
- `0x1800076f0`
- `0x180008d80`
- `0x180008fd8`
- `0x18000b84c`
- `0x18000bcac`
- `0x1800104d4`
- `0x18001084c`
- `0x180010d4c`

## callees

- `0x180002ddc`
- `0x180002f70`
- `0x18000678c`
- `0x180013df8`

## pseudocode

```c
__int64 __fastcall std::wstring::_Construct<1,wchar_t const *>(__int64 a1, const void *a2, unsigned __int64 a3)
{
  __int64 v5; // rdx
  _QWORD *v6; // rsi
  __int64 v7; // rbx
  __int64 result; // rax
  _QWORD *v9; // rax
  __int64 v10; // rcx
  _QWORD *v11; // rdi
  size_t v12; // rbx
  __int64 v13[5]; // [rsp+20h] [rbp-28h] BYREF

  v5 = 0x7FFFFFFFFFFFFFFELL;
  v6 = (_QWORD *)a1;
  if ( a3 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( a3 > 7 )
  {
    if ( (a3 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      a1 = 10;
      v5 = a3 | 7;
      if ( (a3 | 7) < 0xA )
        v5 = 10;
    }
    v13[0] = v5;
    v9 = std::wstring::_Allocate_for_capacity<0>(a1, v13);
    v10 = v13[0];
    v6[2] = a3;
    v11 = v9;
    v6[3] = v10;
    v12 = 2 * a3;
    *v6 = v9;
    memcpy_0(v9, a2, v12);
    result = 0;
    *(_WORD *)((char *)v11 + v12) = 0;
  }
  else
  {
    *(_QWORD *)(a1 + 16) = a3;
    v7 = 2 * a3;
    *(_QWORD *)(a1 + 24) = 7;
    memcpy_0((void *)a1, a2, 2 * a3);
    result = 0;
    *(_WORD *)((char *)v6 + v7) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002f70  mov     [rsp+arg_18], rbx
0x180002f75  push    rbp
0x180002f76  push    rsi
0x180002f77  push    rdi
0x180002f78  sub     rsp, 30h
0x180002f7c  mov     rbp, rdx
0x180002f7f  mov     rbx, r8
0x180002f82  mov     rdx, 7FFFFFFFFFFFFFFEh
0x180002f8c  mov     rsi, rcx
0x180002f8f  cmp     r8, rdx
0x180002f92  ja      loc_180003021
0x180002f98  cmp     rbx, 7
0x180002f9c  ja      short loc_180002FC0
0x180002f9e  mov     [rcx+10h], rbx
0x180002fa2  mov     rdx, rbp; Src
0x180002fa5  add     rbx, rbx
0x180002fa8  mov     qword ptr [rcx+18h], 7
0x180002fb0  mov     r8, rbx; Size
0x180002fb3  call    memcpy_0
0x180002fb8  xor     eax, eax
0x180002fba  mov     [rbx+rsi], ax
0x180002fbe  jmp     short loc_180003014
0x180002fc0  mov     rax, rbx
0x180002fc3  or      rax, 7
0x180002fc7  cmp     rax, rdx
0x180002fca  ja      short loc_180002FDB
0x180002fcc  mov     ecx, 0Ah
0x180002fd1  mov     rdx, rax
0x180002fd4  cmp     rax, rcx
0x180002fd7  cmovb   rdx, rcx
0x180002fdb  mov     [rsp+48h+var_28], rdx
0x180002fe0  lea     rdx, [rsp+48h+var_28]
0x180002fe5  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)
0x180002fea  mov     rcx, [rsp+48h+var_28]
0x180002fef  mov     rdx, rbp; Src
0x180002ff2  mov     [rsi+10h], rbx
0x180002ff6  mov     rdi, rax
0x180002ff9  mov     [rsi+18h], rcx
0x180002ffd  add     rbx, rbx
0x180003000  mov     rcx, rax; void *
0x180003003  mov     [rsi], rax
0x180003006  mov     r8, rbx; Size
0x180003009  call    memcpy_0
0x18000300e  xor     eax, eax
0x180003010  mov     [rbx+rdi], ax
0x180003014  mov     rbx, [rsp+48h+arg_18]
0x180003019  add     rsp, 30h
0x18000301d  pop     rdi
0x18000301e  pop     rsi
0x18000301f  pop     rbp
0x180003020  retn
0x180003021  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
