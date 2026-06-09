# std::basic_filebuf<ushort,std::char_traits<ushort>>::_Endwrite(void)

- ea: `0x140038c24`
- end: `0x140038cff`
- name: `?_Endwrite@?$basic_filebuf@GU?$char_traits@G@std@@@std@@IEAA_NXZ`
- size: `219`
- prototype: `bool __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140038d64`
- `0x140039fb0`
- `0x14003a250`

## callees

- `0x140002f60`
- `0x140038c24`
- `0x14003e010`

## import_xrefs

- `msvcp_win!?unshift@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x140038c8e`
- `msvcp_win!?unshift@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x140038c8e`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x140038ce7`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x140038ce7`

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
0x140038c24  mov     [rsp+arg_8], rbx
0x140038c29  push    rdi
0x140038c2a  sub     rsp, 60h
0x140038c2e  mov     rax, cs:__security_cookie
0x140038c35  xor     rax, rsp
0x140038c38  mov     [rsp+68h+var_10], rax
0x140038c3d  cmp     qword ptr [rcx+68h], 0
0x140038c42  mov     rbx, rcx
0x140038c45  jz      short loc_140038CA6
0x140038c47  cmp     byte ptr [rcx+72h], 0
0x140038c4b  jz      short loc_140038CA6
0x140038c4d  mov     rax, [rcx]
0x140038c50  mov     edi, 0FFFFh
0x140038c55  mov     edx, edi
0x140038c57  mov     rax, [rax+18h]
0x140038c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038c60  cmp     di, ax
0x140038c63  jz      loc_140038CFB
0x140038c69  mov     rcx, [rbx+68h]
0x140038c6d  lea     rax, [rsp+68h+var_38]
0x140038c72  lea     rdx, [rbx+74h]
0x140038c76  mov     [rsp+68h+var_48], rax
0x140038c7b  lea     r9, [rsp+68h+var_10]
0x140038c80  mov     [rsp+68h+var_38], 0
0x140038c89  lea     r8, [rsp+68h+var_30]
0x140038c8e  call    cs:__imp_?unshift@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z; std::codecvt<ushort,char,_Mbstatet>::unshift(_Mbstatet &,char *,char *,char * &)
0x140038c94  test    eax, eax
0x140038c96  jz      short loc_140038CC0
0x140038c98  sub     eax, 1
0x140038c9b  jz      short loc_140038CC4
0x140038c9d  cmp     eax, 2
0x140038ca0  jnz     short loc_140038CFB
0x140038ca2  mov     byte ptr [rbx+72h], 0
0x140038ca6  mov     al, 1
0x140038ca8  mov     rcx, [rsp+68h+var_10]
0x140038cad  xor     rcx, rsp; StackCookie
0x140038cb0  call    __security_check_cookie
0x140038cb5  mov     rbx, [rsp+68h+arg_8]
0x140038cba  add     rsp, 60h
0x140038cbe  pop     rdi
0x140038cbf  retn
0x140038cc0  mov     byte ptr [rbx+72h], 0
0x140038cc4  mov     rdi, [rsp+68h+var_38]
0x140038cc9  lea     rax, [rsp+68h+var_30]
0x140038cce  sub     rdi, rax
0x140038cd1  jz      short loc_140038CF2
0x140038cd3  mov     r9, [rbx+80h]
0x140038cda  lea     rcx, [rsp+68h+var_30]
0x140038cdf  mov     r8, rdi
0x140038ce2  mov     edx, 1
0x140038ce7  call    cs:__imp__o_fwrite
0x140038ced  cmp     rdi, rax
0x140038cf0  jnz     short loc_140038CFB
0x140038cf2  cmp     byte ptr [rbx+72h], 0
0x140038cf6  setz    al
0x140038cf9  jmp     short loc_140038CA8
0x140038cfb  xor     al, al
0x140038cfd  jmp     short loc_140038CA8
```
