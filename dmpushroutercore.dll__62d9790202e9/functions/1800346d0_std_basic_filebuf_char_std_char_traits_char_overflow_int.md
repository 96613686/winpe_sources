# std::basic_filebuf<char,std::char_traits<char>>::overflow(int)

- ea: `0x1800346d0`
- end: `0x180034856`
- name: `?overflow@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAAHH@Z`
- size: `390`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800039f0`
- `0x1800346d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x180034793`
- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x180034793`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x180034816`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x180034816`
- `msvcp_win!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x1800347dc`
- `msvcp_win!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x1800347dc`

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
  __int64 v14; // rcx
  bool v15; // zf
  int v16; // eax
  int v17; // eax
  __int64 v18; // r14
  char v19; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v20[7]; // [rsp+41h] [rbp-3Fh] BYREF
  _BYTE *v21; // [rsp+48h] [rbp-38h] BYREF
  char *v22; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v23[32]; // [rsp+58h] [rbp-28h] BYREF
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
      v14 = (unsigned int)(char)a2;
LABEL_11:
      v15 = (unsigned int)_o_fputc(v14, *(_QWORD *)(a1 + 128)) == -1;
LABEL_19:
      if ( !v15 )
        return a2;
      return v2;
    }
    v19 = a2;
    v22 = 0;
    v21 = 0;
    v16 = std::codecvt<char,char,_Mbstatet>::out(v13, a1 + 116, &v19, v20, &v22, v23, &v24, &v21);
    if ( !v16 || (v17 = v16 - 1) == 0 )
    {
      if ( v21 != v23 )
      {
        v18 = v21 - v23;
        if ( v18 != _o_fwrite(v23, 1, v21 - v23, *(_QWORD *)(a1 + 128)) )
          return v2;
      }
      *(_BYTE *)(a1 + 113) = 1;
      v15 = v22 == &v19;
      goto LABEL_19;
    }
    if ( v17 == 2 )
    {
      v14 = (unsigned int)v19;
      goto LABEL_11;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800346d0  mov     [rsp-18h+arg_10], rbx
0x1800346d5  mov     [rsp-18h+arg_18], rsi
0x1800346da  push    rbp
0x1800346db  push    rdi
0x1800346dc  push    r14
0x1800346de  mov     rbp, rsp
0x1800346e1  sub     rsp, 80h
0x1800346e8  mov     rax, cs:__security_cookie
0x1800346ef  xor     rax, rsp
0x1800346f2  mov     [rbp+var_8], rax
0x1800346f6  or      edi, 0FFFFFFFFh
0x1800346f9  mov     esi, edx
0x1800346fb  mov     rbx, rcx
0x1800346fe  cmp     edx, edi
0x180034700  jnz     short loc_180034709
0x180034702  xor     eax, eax
0x180034704  jmp     loc_180034832
0x180034709  mov     rax, [rcx+40h]
0x18003470d  xor     r14d, r14d
0x180034710  cmp     [rax], r14
0x180034713  jz      short loc_180034745
0x180034715  mov     rdx, [rcx+58h]
0x180034719  movsxd  r8, dword ptr [rdx]
0x18003471c  mov     rcx, r8
0x18003471f  add     rcx, [rax]
0x180034722  cmp     [rax], rcx
0x180034725  jnb     short loc_180034745
0x180034727  lea     ecx, [r8-1]
0x18003472b  mov     eax, esi
0x18003472d  mov     [rdx], ecx
0x18003472f  mov     rdx, [rbx+40h]
0x180034733  mov     r8, [rdx]
0x180034736  lea     rcx, [r8+1]
0x18003473a  mov     [rdx], rcx
0x18003473d  mov     [r8], sil
0x180034740  jmp     loc_180034832
0x180034745  cmp     [rbx+80h], r14
0x18003474c  jz      loc_180034830
0x180034752  mov     r8, [rbx+18h]
0x180034756  lea     rax, [rbx+70h]
0x18003475a  cmp     [r8], rax
0x18003475d  jnz     short loc_18003477F
0x18003475f  mov     rcx, [rbx+88h]
0x180034766  mov     rdx, [rbx+90h]
0x18003476d  mov     [r8], rcx
0x180034770  sub     edx, ecx
0x180034772  mov     rax, [rbx+38h]
0x180034776  mov     [rax], rcx
0x180034779  mov     rax, [rbx+50h]
0x18003477d  mov     [rax], edx
0x18003477f  mov     rcx, [rbx+68h]
0x180034783  test    rcx, rcx
0x180034786  jnz     short loc_1800347A0
0x180034788  movsx   ecx, sil
0x18003478c  mov     rdx, [rbx+80h]
0x180034793  call    cs:__imp__o_fputc
0x180034799  cmp     eax, edi
0x18003479b  jmp     loc_18003482D
0x1800347a0  lea     rax, [rbp+var_38]
0x1800347a4  mov     [rbp+var_40], sil
0x1800347a8  mov     [rsp+80h+var_48], rax
0x1800347ad  lea     rdx, [rbx+74h]
0x1800347b1  lea     rax, [rbp+var_8]
0x1800347b5  mov     [rbp+var_30], r14
0x1800347b9  mov     [rsp+80h+var_50], rax
0x1800347be  lea     r9, [rbp+var_3F]
0x1800347c2  lea     rax, [rbp+var_28]
0x1800347c6  mov     [rbp+var_38], r14
0x1800347ca  mov     [rsp+80h+var_58], rax
0x1800347cf  lea     r8, [rbp+var_40]
0x1800347d3  lea     rax, [rbp+var_30]
0x1800347d7  mov     [rsp+80h+var_60], rax
0x1800347dc  call    cs:__imp_?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z; std::codecvt<char,char,_Mbstatet>::out(_Mbstatet &,char const *,char const *,char const * &,char *,char *,char * &)
0x1800347e2  test    eax, eax
0x1800347e4  jz      short loc_1800347F6
0x1800347e6  sub     eax, 1
0x1800347e9  jz      short loc_1800347F6
0x1800347eb  cmp     eax, 2
0x1800347ee  jnz     short loc_180034830
0x1800347f0  movsx   ecx, [rbp+var_40]
0x1800347f4  jmp     short loc_18003478C
0x1800347f6  mov     r14, [rbp+var_38]
0x1800347fa  lea     rax, [rbp+var_28]
0x1800347fe  sub     r14, rax
0x180034801  jz      short loc_180034821
0x180034803  mov     r9, [rbx+80h]
0x18003480a  lea     rcx, [rbp+var_28]
0x18003480e  mov     r8, r14
0x180034811  mov     edx, 1
0x180034816  call    cs:__imp__o_fwrite
0x18003481c  cmp     r14, rax
0x18003481f  jnz     short loc_180034830
0x180034821  lea     rax, [rbp+var_40]
0x180034825  mov     byte ptr [rbx+71h], 1
0x180034829  cmp     [rbp+var_30], rax
0x18003482d  cmovnz  edi, esi
0x180034830  mov     eax, edi
0x180034832  mov     rcx, [rbp+var_8]
0x180034836  xor     rcx, rsp; StackCookie
0x180034839  call    __security_check_cookie
0x18003483e  lea     r11, [rsp+80h+var_s0]
0x180034846  mov     rbx, [r11+30h]
0x18003484a  mov     rsi, [r11+38h]
0x18003484e  mov     rsp, r11
0x180034851  pop     r14
0x180034853  pop     rdi
0x180034854  pop     rbp
0x180034855  retn
```
