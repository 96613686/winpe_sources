# std::basic_filebuf<ushort,std::char_traits<ushort>>::_Endwrite(void)

- ea: `0x140012aa8`
- end: `0x140012b8c`
- name: `?_Endwrite@?$basic_filebuf@GU?$char_traits@G@std@@@std@@IEAA_NXZ`
- size: `228`
- prototype: `bool __fastcall(__int64)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140012d94`
- `0x1400130c0`
- `0x1400131a0`

## callees

- `0x140002f40`
- `0x14000e16c`
- `0x140012aa8`
- `0x14001a010`

## import_xrefs

- `msvcp_win!?unshift@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x140012b1b`
- `msvcp_win!?unshift@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x140012b1b`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x140012b74`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x140012b74`

## pseudocode

```c
bool __fastcall std::basic_filebuf<unsigned short>::_Endwrite(__int64 a1)
{
  unsigned __int16 v2; // ax
  __int64 v3; // rcx
  int v4; // eax
  int v5; // eax
  __int64 v7; // rdi
  _BYTE *v8; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v9[32]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v10; // [rsp+58h] [rbp-10h] BYREF

  if ( !*(_QWORD *)(a1 + 104) || !*(_BYTE *)(a1 + 114) )
    return 1;
  v2 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 24LL))(a1, 0xFFFF);
  if ( (unsigned __int8)std::_WChar_traits<unsigned short>::eq_int_type(0xFFFF, v2) )
    return 0;
  v3 = *(_QWORD *)(a1 + 104);
  v8 = 0;
  v4 = std::codecvt<unsigned short,char,_Mbstatet>::unshift(v3, a1 + 116, v9, &v10, &v8);
  if ( v4 )
  {
    v5 = v4 - 1;
    if ( v5 )
    {
      if ( v5 == 2 )
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
  if ( v8 == v9 )
    return *(_BYTE *)(a1 + 114) == 0;
  v7 = v8 - v9;
  if ( v7 == _o_fwrite(v9, 1, v8 - v9, *(_QWORD *)(a1 + 128)) )
    return *(_BYTE *)(a1 + 114) == 0;
  return 0;
}

```

## disassembly

```asm
0x140012aa8  mov     [rsp+arg_8], rbx
0x140012aad  push    rdi
0x140012aae  sub     rsp, 60h
0x140012ab2  mov     rax, cs:__security_cookie
0x140012ab9  xor     rax, rsp
0x140012abc  mov     [rsp+68h+var_10], rax
0x140012ac1  cmp     qword ptr [rcx+68h], 0
0x140012ac6  mov     rbx, rcx
0x140012ac9  jz      short loc_140012B33
0x140012acb  cmp     byte ptr [rcx+72h], 0
0x140012acf  jz      short loc_140012B33
0x140012ad1  mov     rax, [rcx]
0x140012ad4  mov     edi, 0FFFFh
0x140012ad9  mov     edx, edi
0x140012adb  mov     rax, [rax+18h]
0x140012adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012ae4  movzx   edx, ax
0x140012ae7  mov     ecx, edi
0x140012ae9  call    ?eq_int_type@?$_WChar_traits@G@std@@SA_NGG@Z; std::_WChar_traits<ushort>::eq_int_type(ushort,ushort)
0x140012aee  test    al, al
0x140012af0  jnz     loc_140012B88
0x140012af6  mov     rcx, [rbx+68h]
0x140012afa  lea     rax, [rsp+68h+var_38]
0x140012aff  lea     rdx, [rbx+74h]
0x140012b03  mov     [rsp+68h+var_48], rax
0x140012b08  lea     r9, [rsp+68h+var_10]
0x140012b0d  mov     [rsp+68h+var_38], 0
0x140012b16  lea     r8, [rsp+68h+var_30]
0x140012b1b  call    cs:__imp_?unshift@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z; std::codecvt<ushort,char,_Mbstatet>::unshift(_Mbstatet &,char *,char *,char * &)
0x140012b21  test    eax, eax
0x140012b23  jz      short loc_140012B4D
0x140012b25  sub     eax, 1
0x140012b28  jz      short loc_140012B51
0x140012b2a  cmp     eax, 2
0x140012b2d  jnz     short loc_140012B88
0x140012b2f  mov     byte ptr [rbx+72h], 0
0x140012b33  mov     al, 1
0x140012b35  mov     rcx, [rsp+68h+var_10]
0x140012b3a  xor     rcx, rsp; StackCookie
0x140012b3d  call    __security_check_cookie
0x140012b42  mov     rbx, [rsp+68h+arg_8]
0x140012b47  add     rsp, 60h
0x140012b4b  pop     rdi
0x140012b4c  retn
0x140012b4d  mov     byte ptr [rbx+72h], 0
0x140012b51  mov     rdi, [rsp+68h+var_38]
0x140012b56  lea     rax, [rsp+68h+var_30]
0x140012b5b  sub     rdi, rax
0x140012b5e  jz      short loc_140012B7F
0x140012b60  mov     r9, [rbx+80h]
0x140012b67  lea     rcx, [rsp+68h+var_30]
0x140012b6c  mov     r8, rdi
0x140012b6f  mov     edx, 1
0x140012b74  call    cs:__imp__o_fwrite
0x140012b7a  cmp     rdi, rax
0x140012b7d  jnz     short loc_140012B88
0x140012b7f  cmp     byte ptr [rbx+72h], 0
0x140012b83  setz    al
0x140012b86  jmp     short loc_140012B35
0x140012b88  xor     al, al
0x140012b8a  jmp     short loc_140012B35
```
