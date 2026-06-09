# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Tidy(bool,unsigned __int64)

- ea: `0x180001910`
- end: `0x18000196b`
- name: `?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z`
- size: `91`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `44`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180001974`
- `0x180005354`
- `0x18000536c`
- `0x1800056c0`
- `0x180006040`
- `0x180007830`
- `0x180007bd8`
- `0x180007f70`
- `0x180008728`
- `0x180008be0`
- `0x1800098e0`
- `0x180009a24`
- `0x180009c7c`
- `0x18000aac0`
- `0x18000cca8`
- `0x18000d078`
- `0x18000d444`
- `0x18000dfdc`
- `0x18000e208`
- `0x18000e664`
- `0x18000e908`
- `0x18000eb2c`
- `0x18000f8f4`
- `0x180010710`
- `0x180010bc8`
- `0x180010e8c`
- `0x180012c10`
- `0x1800130a8`
- `0x1800131b8`
- `0x1800135d0`
- `0x180013810`
- `0x1800152e8`
- `0x180016084`
- `0x180016cd4`
- `0x1800172cc`
- `0x18001c770`
- `0x18001de94`
- `0x18001eef4`
- `0x18001f858`
- `0x18001f9cc`
- `0x18001fd74`
- `0x18001fff4`
- `0x180021460`
- `0x180022380`

## callees

- `0x180001910`
- `0x18000265c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180001943`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001943`

## pseudocode

```c
__int64 __fastcall std::wstring::_Tidy(void **a1, char a2, __int64 a3)
{
  void *v5; // rsi
  __int64 result; // rax

  if ( a2 && (unsigned __int64)a1[3] >= 8 )
  {
    v5 = *a1;
    if ( a3 )
      std::char_traits<unsigned short>::copy(a1, *a1, a3);
    operator delete(v5);
  }
  a1[3] = (void *)7;
  result = 0;
  a1[2] = (void *)a3;
  *((_WORD *)a1 + a3) = 0;
  return result;
}

```

## disassembly

```asm
0x180001910  mov     [rsp+arg_8], rbx
0x180001915  push    rdi
0x180001916  sub     rsp, 20h
0x18000191a  mov     rdi, r8
0x18000191d  mov     rbx, rcx
0x180001920  test    dl, dl
0x180001922  jz      short loc_18000194E
0x180001924  cmp     qword ptr [rcx+18h], 8
0x180001929  jb      short loc_18000194E
0x18000192b  mov     [rsp+28h+arg_0], rsi
0x180001930  mov     rsi, [rcx]
0x180001933  test    r8, r8
0x180001936  jz      short loc_180001940
0x180001938  mov     rdx, rsi
0x18000193b  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x180001940  mov     rcx, rsi
0x180001943  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180001949  mov     rsi, [rsp+28h+arg_0]
0x18000194e  mov     qword ptr [rbx+18h], 7
0x180001956  xor     eax, eax
0x180001958  mov     [rbx+10h], rdi
0x18000195c  mov     [rbx+rdi*2], ax
0x180001960  mov     rbx, [rsp+28h+arg_8]
0x180001965  add     rsp, 20h
0x180001969  pop     rdi
0x18000196a  retn
```
