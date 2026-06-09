# std::basic_filebuf<char,std::char_traits<char>>::_Endwrite(void)

- ea: `0x18007e484`
- end: `0x18007e55b`
- name: `?_Endwrite@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAA_NXZ`
- size: `215`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18007af78`
- `0x18007f120`
- `0x18007f4a0`

## callees

- `0x18004ca90`
- `0x18007e484`
- `0x180096010`

## import_xrefs

- `msvcp_win!?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x18007e4ea`
- `msvcp_win!?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x18007e4ea`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18007e543`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18007e543`

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
0x18007e484  mov     [rsp+arg_8], rbx
0x18007e489  push    rdi
0x18007e48a  sub     rsp, 60h
0x18007e48e  mov     rax, cs:__security_cookie
0x18007e495  xor     rax, rsp
0x18007e498  mov     [rsp+68h+var_10], rax
0x18007e49d  cmp     qword ptr [rcx+68h], 0
0x18007e4a2  mov     rbx, rcx
0x18007e4a5  jz      short loc_18007E502
0x18007e4a7  cmp     byte ptr [rcx+71h], 0
0x18007e4ab  jz      short loc_18007E502
0x18007e4ad  mov     rax, [rcx]
0x18007e4b0  or      edx, 0FFFFFFFFh
0x18007e4b3  mov     rax, [rax+18h]
0x18007e4b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e4bc  cmp     eax, 0FFFFFFFFh
0x18007e4bf  jz      loc_18007E557
0x18007e4c5  mov     rcx, [rbx+68h]
0x18007e4c9  lea     rax, [rsp+68h+var_38]
0x18007e4ce  lea     rdx, [rbx+74h]
0x18007e4d2  mov     [rsp+68h+var_48], rax
0x18007e4d7  lea     r9, [rsp+68h+var_10]
0x18007e4dc  mov     [rsp+68h+var_38], 0
0x18007e4e5  lea     r8, [rsp+68h+var_30]
0x18007e4ea  call    cs:__imp_?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z; std::codecvt<char,char,_Mbstatet>::unshift(_Mbstatet &,char *,char *,char * &)
0x18007e4f0  test    eax, eax
0x18007e4f2  jz      short loc_18007E51C
0x18007e4f4  sub     eax, 1
0x18007e4f7  jz      short loc_18007E520
0x18007e4f9  cmp     eax, 2
0x18007e4fc  jnz     short loc_18007E557
0x18007e4fe  mov     byte ptr [rbx+71h], 0
0x18007e502  mov     al, 1
0x18007e504  mov     rcx, [rsp+68h+var_10]
0x18007e509  xor     rcx, rsp; StackCookie
0x18007e50c  call    __security_check_cookie
0x18007e511  mov     rbx, [rsp+68h+arg_8]
0x18007e516  add     rsp, 60h
0x18007e51a  pop     rdi
0x18007e51b  retn
0x18007e51c  mov     byte ptr [rbx+71h], 0
0x18007e520  mov     rdi, [rsp+68h+var_38]
0x18007e525  lea     rax, [rsp+68h+var_30]
0x18007e52a  sub     rdi, rax
0x18007e52d  jz      short loc_18007E54E
0x18007e52f  mov     r9, [rbx+80h]
0x18007e536  lea     rcx, [rsp+68h+var_30]
0x18007e53b  mov     r8, rdi
0x18007e53e  mov     edx, 1
0x18007e543  call    cs:__imp__o_fwrite
0x18007e549  cmp     rdi, rax
0x18007e54c  jnz     short loc_18007E557
0x18007e54e  cmp     byte ptr [rbx+71h], 0
0x18007e552  setz    al
0x18007e555  jmp     short loc_18007E504
0x18007e557  xor     al, al
0x18007e559  jmp     short loc_18007E504
```
