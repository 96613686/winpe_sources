# std::basic_filebuf<char,std::char_traits<char>>::_Endwrite(void)

- ea: `0x18000c234`
- end: `0x18000c30b`
- name: `?_Endwrite@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAA_NXZ`
- size: `215`
- prototype: `bool __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c578`
- `0x18000cd00`
- `0x18000cde0`

## callees

- `0x180001a70`
- `0x18000c234`
- `0x180012010`

## import_xrefs

- `msvcp_win!?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x18000c29a`
- `msvcp_win!?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x18000c29a`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18000c2f3`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18000c2f3`

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
0x18000c234  mov     [rsp+arg_8], rbx
0x18000c239  push    rdi
0x18000c23a  sub     rsp, 60h
0x18000c23e  mov     rax, cs:__security_cookie
0x18000c245  xor     rax, rsp
0x18000c248  mov     [rsp+68h+var_10], rax
0x18000c24d  cmp     qword ptr [rcx+68h], 0
0x18000c252  mov     rbx, rcx
0x18000c255  jz      short loc_18000C2B2
0x18000c257  cmp     byte ptr [rcx+71h], 0
0x18000c25b  jz      short loc_18000C2B2
0x18000c25d  mov     rax, [rcx]
0x18000c260  or      edx, 0FFFFFFFFh
0x18000c263  mov     rax, [rax+18h]
0x18000c267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c26c  cmp     eax, 0FFFFFFFFh
0x18000c26f  jz      loc_18000C307
0x18000c275  mov     rcx, [rbx+68h]
0x18000c279  lea     rax, [rsp+68h+var_38]
0x18000c27e  lea     rdx, [rbx+74h]
0x18000c282  mov     [rsp+68h+var_48], rax
0x18000c287  lea     r9, [rsp+68h+var_10]
0x18000c28c  mov     [rsp+68h+var_38], 0
0x18000c295  lea     r8, [rsp+68h+var_30]
0x18000c29a  call    cs:__imp_?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z; std::codecvt<char,char,_Mbstatet>::unshift(_Mbstatet &,char *,char *,char * &)
0x18000c2a0  test    eax, eax
0x18000c2a2  jz      short loc_18000C2CC
0x18000c2a4  sub     eax, 1
0x18000c2a7  jz      short loc_18000C2D0
0x18000c2a9  cmp     eax, 2
0x18000c2ac  jnz     short loc_18000C307
0x18000c2ae  mov     byte ptr [rbx+71h], 0
0x18000c2b2  mov     al, 1
0x18000c2b4  mov     rcx, [rsp+68h+var_10]
0x18000c2b9  xor     rcx, rsp; StackCookie
0x18000c2bc  call    __security_check_cookie
0x18000c2c1  mov     rbx, [rsp+68h+arg_8]
0x18000c2c6  add     rsp, 60h
0x18000c2ca  pop     rdi
0x18000c2cb  retn
0x18000c2cc  mov     byte ptr [rbx+71h], 0
0x18000c2d0  mov     rdi, [rsp+68h+var_38]
0x18000c2d5  lea     rax, [rsp+68h+var_30]
0x18000c2da  sub     rdi, rax
0x18000c2dd  jz      short loc_18000C2FE
0x18000c2df  mov     r9, [rbx+80h]
0x18000c2e6  lea     rcx, [rsp+68h+var_30]
0x18000c2eb  mov     r8, rdi
0x18000c2ee  mov     edx, 1
0x18000c2f3  call    cs:__imp__o_fwrite
0x18000c2f9  cmp     rdi, rax
0x18000c2fc  jnz     short loc_18000C307
0x18000c2fe  cmp     byte ptr [rbx+71h], 0
0x18000c302  setz    al
0x18000c305  jmp     short loc_18000C2B4
0x18000c307  xor     al, al
0x18000c309  jmp     short loc_18000C2B4
```
