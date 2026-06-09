# std::basic_filebuf<char,std::char_traits<char>>::overflow(int)

- ea: `0x14003b500`
- end: `0x14003b680`
- name: `?overflow@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAAHH@Z`
- size: `384`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001020`
- `0x14003b500`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!fputc` at `0x14003b5c2`
- `api-ms-win-crt-stdio-l1-1-0!fputc` at `0x14003b5c2`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x14003b640`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x14003b640`
- `MSVCP140!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x14003b603`
- `MSVCP140!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x14003b603`

## pseudocode

```c
__int64 __fastcall std::filebuf::overflow(__int64 a1, unsigned int a2)
{
  unsigned int v2; // edi
  __int64 result; // rax
  _QWORD *v6; // rax
  int *v7; // rdx
  _QWORD *v8; // rdx
  _BYTE *v9; // r8
  _QWORD *v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // ecx
  bool v15; // zf
  int v16; // eax
  int v17; // eax
  __int64 v18; // r14
  _BYTE *v19; // [rsp+40h] [rbp-40h] BYREF
  char *v20; // [rsp+48h] [rbp-38h] BYREF
  char v21; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v22[7]; // [rsp+51h] [rbp-2Fh] BYREF
  _BYTE Buffer[32]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v24; // [rsp+78h] [rbp-8h] BYREF

  v2 = -1;
  if ( a2 == -1 )
    return 0;
  v6 = *(_QWORD **)(a1 + 64);
  if ( *v6 )
  {
    v7 = *(int **)(a1 + 88);
    if ( *v6 < (unsigned __int64)(*v6 + *v7) )
    {
      result = a2;
      --*v7;
      v8 = *(_QWORD **)(a1 + 64);
      v9 = (_BYTE *)(*v8)++;
      *v9 = a2;
      return result;
    }
  }
  if ( *(_QWORD *)(a1 + 128) )
  {
    v10 = *(_QWORD **)(a1 + 24);
    if ( *v10 == a1 + 112 )
    {
      v11 = *(_QWORD *)(a1 + 136);
      v12 = *(_QWORD *)(a1 + 144);
      *v10 = v11;
      **(_QWORD **)(a1 + 56) = v11;
      **(_DWORD **)(a1 + 80) = v12 - v11;
    }
    v13 = *(_QWORD *)(a1 + 104);
    if ( !v13 )
    {
      v14 = (char)a2;
LABEL_11:
      v15 = fputc(v14, *(FILE **)(a1 + 128)) == -1;
LABEL_19:
      if ( !v15 )
        return a2;
      return v2;
    }
    v21 = a2;
    v16 = std::codecvt<char,char,_Mbstatet>::out(v13, a1 + 116, &v21, v22, &v20, Buffer, &v24, &v19);
    if ( !v16 || (v17 = v16 - 1) == 0 )
    {
      if ( v19 != Buffer )
      {
        _mm_lfence();
        v18 = v19 - Buffer;
        if ( v18 != fwrite(Buffer, 1u, v19 - Buffer, *(FILE **)(a1 + 128)) )
          return v2;
      }
      *(_BYTE *)(a1 + 113) = 1;
      v15 = v20 == &v21;
      goto LABEL_19;
    }
    if ( v17 == 2 )
    {
      v14 = v21;
      goto LABEL_11;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x14003b500  mov     [rsp-18h+arg_10], rbx
0x14003b505  mov     [rsp-18h+arg_18], rsi
0x14003b50a  push    rbp
0x14003b50b  push    rdi
0x14003b50c  push    r14
0x14003b50e  mov     rbp, rsp
0x14003b511  sub     rsp, 80h
0x14003b518  mov     rax, cs:__security_cookie
0x14003b51f  xor     rax, rsp
0x14003b522  mov     [rbp+var_8], rax
0x14003b526  or      edi, 0FFFFFFFFh
0x14003b529  mov     esi, edx
0x14003b52b  mov     rbx, rcx
0x14003b52e  cmp     edx, edi
0x14003b530  jnz     short loc_14003B539
0x14003b532  xor     eax, eax
0x14003b534  jmp     loc_14003B65C
0x14003b539  mov     rax, [rcx+40h]
0x14003b53d  cmp     qword ptr [rax], 0
0x14003b541  jz      short loc_14003B573
0x14003b543  mov     rdx, [rcx+58h]
0x14003b547  movsxd  r8, dword ptr [rdx]
0x14003b54a  mov     rcx, r8
0x14003b54d  add     rcx, [rax]
0x14003b550  cmp     [rax], rcx
0x14003b553  jnb     short loc_14003B573
0x14003b555  lea     ecx, [r8-1]
0x14003b559  mov     eax, esi
0x14003b55b  mov     [rdx], ecx
0x14003b55d  mov     rdx, [rbx+40h]
0x14003b561  mov     r8, [rdx]
0x14003b564  lea     rcx, [r8+1]
0x14003b568  mov     [rdx], rcx
0x14003b56b  mov     [r8], sil
0x14003b56e  jmp     loc_14003B65C
0x14003b573  cmp     qword ptr [rbx+80h], 0
0x14003b57b  jz      loc_14003B65A
0x14003b581  mov     r8, [rbx+18h]
0x14003b585  lea     rax, [rbx+70h]
0x14003b589  cmp     [r8], rax
0x14003b58c  jnz     short loc_14003B5AE
0x14003b58e  mov     rcx, [rbx+88h]
0x14003b595  mov     rdx, [rbx+90h]
0x14003b59c  mov     [r8], rcx
0x14003b59f  sub     edx, ecx
0x14003b5a1  mov     rax, [rbx+38h]
0x14003b5a5  mov     [rax], rcx
0x14003b5a8  mov     rax, [rbx+50h]
0x14003b5ac  mov     [rax], edx
0x14003b5ae  mov     rcx, [rbx+68h]
0x14003b5b2  test    rcx, rcx
0x14003b5b5  jnz     short loc_14003B5CF
0x14003b5b7  movsx   ecx, sil; Character
0x14003b5bb  mov     rdx, [rbx+80h]; Stream
0x14003b5c2  call    cs:__imp_fputc
0x14003b5c8  cmp     eax, edi
0x14003b5ca  jmp     loc_14003B657
0x14003b5cf  lea     rax, [rbp+var_40]
0x14003b5d3  mov     [rbp+var_30], sil
0x14003b5d7  mov     [rsp+80h+var_48], rax
0x14003b5dc  lea     rdx, [rbx+74h]
0x14003b5e0  lea     rax, [rbp+var_8]
0x14003b5e4  mov     [rsp+80h+var_50], rax
0x14003b5e9  lea     r9, [rbp+var_2F]
0x14003b5ed  lea     rax, [rbp+Buffer]
0x14003b5f1  mov     [rsp+80h+var_58], rax
0x14003b5f6  lea     r8, [rbp+var_30]
0x14003b5fa  lea     rax, [rbp+var_38]
0x14003b5fe  mov     [rsp+80h+var_60], rax
0x14003b603  call    cs:__imp_?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z; std::codecvt<char,char,_Mbstatet>::out(_Mbstatet &,char const *,char const *,char const * &,char *,char *,char * &)
0x14003b609  test    eax, eax
0x14003b60b  jz      short loc_14003B61D
0x14003b60d  sub     eax, 1
0x14003b610  jz      short loc_14003B61D
0x14003b612  cmp     eax, 2
0x14003b615  jnz     short loc_14003B65A
0x14003b617  movsx   ecx, [rbp+var_30]
0x14003b61b  jmp     short loc_14003B5BB
0x14003b61d  mov     r14, [rbp+var_40]
0x14003b621  lea     rax, [rbp+Buffer]
0x14003b625  sub     r14, rax
0x14003b628  jz      short loc_14003B64B
0x14003b62a  lfence
0x14003b62d  mov     r9, [rbx+80h]; Stream
0x14003b634  lea     rcx, [rbp+Buffer]; Buffer
0x14003b638  mov     r8, r14; ElementCount
0x14003b63b  mov     edx, 1; ElementSize
0x14003b640  call    cs:__imp_fwrite
0x14003b646  cmp     r14, rax
0x14003b649  jnz     short loc_14003B65A
0x14003b64b  lea     rax, [rbp+var_30]
0x14003b64f  mov     byte ptr [rbx+71h], 1
0x14003b653  cmp     [rbp+var_38], rax
0x14003b657  cmovnz  edi, esi
0x14003b65a  mov     eax, edi
0x14003b65c  mov     rcx, [rbp+var_8]
0x14003b660  xor     rcx, rsp; StackCookie
0x14003b663  call    __security_check_cookie
0x14003b668  lea     r11, [rsp+80h+var_s0]
0x14003b670  mov     rbx, [r11+30h]
0x14003b674  mov     rsi, [r11+38h]
0x14003b678  mov     rsp, r11
0x14003b67b  pop     r14
0x14003b67d  pop     rdi
0x14003b67e  pop     rbp
0x14003b67f  retn
```
