# std::basic_filebuf<char,std::char_traits<char>>::_Endwrite(void)

- ea: `0x1800341dc`
- end: `0x1800342b3`
- name: `?_Endwrite@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAA_NXZ`
- size: `215`
- prototype: `bool __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180034414`
- `0x180034af0`
- `0x180034c00`

## callees

- `0x1800039f0`
- `0x1800341dc`
- `0x18003b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18003429b`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18003429b`
- `msvcp_win!?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x180034242`
- `msvcp_win!?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x180034242`

## pseudocode

```c
bool __fastcall std::filebuf::_Endwrite(__int64 a1)
{
  __int64 v2; // rcx
  int v3; // eax
  int v4; // eax
  __int64 v6; // rdi
  _BYTE *v7; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v9; // [rsp+58h] [rbp-10h] BYREF

  if ( !*(_QWORD *)(a1 + 104) || !*(_BYTE *)(a1 + 113) )
    return 1;
  if ( (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 24LL))(a1, 0xFFFFFFFFLL) == -1 )
    return 0;
  v2 = *(_QWORD *)(a1 + 104);
  v7 = 0;
  v3 = std::codecvt<char,char,_Mbstatet>::unshift(v2, a1 + 116, v8, &v9, &v7);
  if ( v3 )
  {
    v4 = v3 - 1;
    if ( v4 )
    {
      if ( v4 == 2 )
      {
        *(_BYTE *)(a1 + 113) = 0;
        return 1;
      }
      return 0;
    }
  }
  else
  {
    *(_BYTE *)(a1 + 113) = 0;
  }
  if ( v7 == v8 )
    return *(_BYTE *)(a1 + 113) == 0;
  v6 = v7 - v8;
  if ( v6 == _o_fwrite(v8, 1, v7 - v8, *(_QWORD *)(a1 + 128)) )
    return *(_BYTE *)(a1 + 113) == 0;
  return 0;
}

```

## disassembly

```asm
0x1800341dc  mov     [rsp+arg_8], rbx
0x1800341e1  push    rdi
0x1800341e2  sub     rsp, 60h
0x1800341e6  mov     rax, cs:__security_cookie
0x1800341ed  xor     rax, rsp
0x1800341f0  mov     [rsp+68h+var_10], rax
0x1800341f5  cmp     qword ptr [rcx+68h], 0
0x1800341fa  mov     rbx, rcx
0x1800341fd  jz      short loc_18003425A
0x1800341ff  cmp     byte ptr [rcx+71h], 0
0x180034203  jz      short loc_18003425A
0x180034205  mov     rax, [rcx]
0x180034208  or      edx, 0FFFFFFFFh
0x18003420b  mov     rax, [rax+18h]
0x18003420f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034214  cmp     eax, 0FFFFFFFFh
0x180034217  jz      loc_1800342AF
0x18003421d  mov     rcx, [rbx+68h]
0x180034221  lea     rax, [rsp+68h+var_38]
0x180034226  lea     rdx, [rbx+74h]
0x18003422a  mov     [rsp+68h+var_48], rax
0x18003422f  lea     r9, [rsp+68h+var_10]
0x180034234  mov     [rsp+68h+var_38], 0
0x18003423d  lea     r8, [rsp+68h+var_30]
0x180034242  call    cs:__imp_?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z; std::codecvt<char,char,_Mbstatet>::unshift(_Mbstatet &,char *,char *,char * &)
0x180034248  test    eax, eax
0x18003424a  jz      short loc_180034274
0x18003424c  sub     eax, 1
0x18003424f  jz      short loc_180034278
0x180034251  cmp     eax, 2
0x180034254  jnz     short loc_1800342AF
0x180034256  mov     byte ptr [rbx+71h], 0
0x18003425a  mov     al, 1
0x18003425c  mov     rcx, [rsp+68h+var_10]
0x180034261  xor     rcx, rsp; StackCookie
0x180034264  call    __security_check_cookie
0x180034269  mov     rbx, [rsp+68h+arg_8]
0x18003426e  add     rsp, 60h
0x180034272  pop     rdi
0x180034273  retn
0x180034274  mov     byte ptr [rbx+71h], 0
0x180034278  mov     rdi, [rsp+68h+var_38]
0x18003427d  lea     rax, [rsp+68h+var_30]
0x180034282  sub     rdi, rax
0x180034285  jz      short loc_1800342A6
0x180034287  mov     r9, [rbx+80h]
0x18003428e  lea     rcx, [rsp+68h+var_30]
0x180034293  mov     r8, rdi
0x180034296  mov     edx, 1
0x18003429b  call    cs:__imp__o_fwrite
0x1800342a1  cmp     rdi, rax
0x1800342a4  jnz     short loc_1800342AF
0x1800342a6  cmp     byte ptr [rbx+71h], 0
0x1800342aa  setz    al
0x1800342ad  jmp     short loc_18003425C
0x1800342af  xor     al, al
0x1800342b1  jmp     short loc_18003425C
```
