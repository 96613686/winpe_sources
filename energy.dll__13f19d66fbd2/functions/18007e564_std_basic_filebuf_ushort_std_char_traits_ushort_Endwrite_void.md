# std::basic_filebuf<ushort,std::char_traits<ushort>>::_Endwrite(void)

- ea: `0x18007e564`
- end: `0x18007e63f`
- name: `?_Endwrite@?$basic_filebuf@GU?$char_traits@G@std@@@std@@IEAA_NXZ`
- size: `219`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18007e940`
- `0x18007f200`
- `0x18007f550`

## callees

- `0x18004ca90`
- `0x18007e564`
- `0x180096010`

## import_xrefs

- `msvcp_win!?unshift@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x18007e5ce`
- `msvcp_win!?unshift@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x18007e5ce`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18007e627`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18007e627`

## pseudocode

```c
bool __fastcall std::basic_filebuf<unsigned short>::_Endwrite(__int64 a1)
{
  __int64 v2; // rcx
  int v3; // eax
  int v4; // eax
  __int64 v6; // rdi
  _BYTE *v7; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v9; // [rsp+58h] [rbp-10h] BYREF

  if ( !*(_QWORD *)(a1 + 104) || !*(_BYTE *)(a1 + 114) )
    return 1;
  if ( (*(unsigned __int16 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 24LL))(a1, 0xFFFF) == 0xFFFF )
    return 0;
  v2 = *(_QWORD *)(a1 + 104);
  v7 = 0;
  v3 = std::codecvt<unsigned short,char,_Mbstatet>::unshift(v2, a1 + 116, v8, &v9, &v7);
  if ( v3 )
  {
    v4 = v3 - 1;
    if ( v4 )
    {
      if ( v4 == 2 )
      {
        *(_BYTE *)(a1 + 114) = 0;
        return 1;
      }
      return 0;
    }
  }
  else
  {
    *(_BYTE *)(a1 + 114) = 0;
  }
  if ( v7 == v8 )
    return *(_BYTE *)(a1 + 114) == 0;
  v6 = v7 - v8;
  if ( v6 == _o_fwrite(v8, 1, v7 - v8, *(_QWORD *)(a1 + 128)) )
    return *(_BYTE *)(a1 + 114) == 0;
  return 0;
}

```

## disassembly

```asm
0x18007e564  mov     [rsp+arg_8], rbx
0x18007e569  push    rdi
0x18007e56a  sub     rsp, 60h
0x18007e56e  mov     rax, cs:__security_cookie
0x18007e575  xor     rax, rsp
0x18007e578  mov     [rsp+68h+var_10], rax
0x18007e57d  cmp     qword ptr [rcx+68h], 0
0x18007e582  mov     rbx, rcx
0x18007e585  jz      short loc_18007E5E6
0x18007e587  cmp     byte ptr [rcx+72h], 0
0x18007e58b  jz      short loc_18007E5E6
0x18007e58d  mov     rax, [rcx]
0x18007e590  mov     edi, 0FFFFh
0x18007e595  mov     edx, edi
0x18007e597  mov     rax, [rax+18h]
0x18007e59b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e5a0  cmp     di, ax
0x18007e5a3  jz      loc_18007E63B
0x18007e5a9  mov     rcx, [rbx+68h]
0x18007e5ad  lea     rax, [rsp+68h+var_38]
0x18007e5b2  lea     rdx, [rbx+74h]
0x18007e5b6  mov     [rsp+68h+var_48], rax
0x18007e5bb  lea     r9, [rsp+68h+var_10]
0x18007e5c0  mov     [rsp+68h+var_38], 0
0x18007e5c9  lea     r8, [rsp+68h+var_30]
0x18007e5ce  call    cs:__imp_?unshift@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z; std::codecvt<ushort,char,_Mbstatet>::unshift(_Mbstatet &,char *,char *,char * &)
0x18007e5d4  test    eax, eax
0x18007e5d6  jz      short loc_18007E600
0x18007e5d8  sub     eax, 1
0x18007e5db  jz      short loc_18007E604
0x18007e5dd  cmp     eax, 2
0x18007e5e0  jnz     short loc_18007E63B
0x18007e5e2  mov     byte ptr [rbx+72h], 0
0x18007e5e6  mov     al, 1
0x18007e5e8  mov     rcx, [rsp+68h+var_10]
0x18007e5ed  xor     rcx, rsp; StackCookie
0x18007e5f0  call    __security_check_cookie
0x18007e5f5  mov     rbx, [rsp+68h+arg_8]
0x18007e5fa  add     rsp, 60h
0x18007e5fe  pop     rdi
0x18007e5ff  retn
0x18007e600  mov     byte ptr [rbx+72h], 0
0x18007e604  mov     rdi, [rsp+68h+var_38]
0x18007e609  lea     rax, [rsp+68h+var_30]
0x18007e60e  sub     rdi, rax
0x18007e611  jz      short loc_18007E632
0x18007e613  mov     r9, [rbx+80h]
0x18007e61a  lea     rcx, [rsp+68h+var_30]
0x18007e61f  mov     r8, rdi
0x18007e622  mov     edx, 1
0x18007e627  call    cs:__imp__o_fwrite
0x18007e62d  cmp     rdi, rax
0x18007e630  jnz     short loc_18007E63B
0x18007e632  cmp     byte ptr [rbx+72h], 0
0x18007e636  setz    al
0x18007e639  jmp     short loc_18007E5E8
0x18007e63b  xor     al, al
0x18007e63d  jmp     short loc_18007E5E8
```
