# JsonArray::ToJsonString(ushort * *)

- ea: `0x14001d400`
- end: `0x14001d6bc`
- name: `?ToJsonString@JsonArray@@UEBAKPEAPEAG@Z`
- size: `700`
- prototype: `unsigned int __fastcall(JsonArray *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14001c78c`
- `0x14001d400`
- `0x14002c3e8`
- `0x140030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001d5c5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001d629`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001d659`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001d66d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001d684`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001d5c5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001d629`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001d659`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001d66d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001d684`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14001d5a4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14001d5a4`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x14001d511`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x14001d511`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001d5e3`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001d609`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001d618`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001d63e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001d5e3`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001d609`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001d618`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001d63e`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14001d57a`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14001d57a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall JsonArray::ToJsonString(JsonArray *this, unsigned __int16 **a2)
{
  JsonArray *v2; // rax
  _QWORD *v3; // r14
  unsigned int v4; // ebx
  __int64 v5; // r15
  _WORD *v6; // rsi
  __int64 v7; // r13
  char v8; // r12
  __int64 v9; // rcx
  unsigned int v10; // edi
  unsigned int v11; // r8d
  unsigned int v12; // eax
  unsigned int v13; // r12d
  __int64 v14; // rax
  size_t v15; // rax
  void *v16; // rdi
  void *v17; // rcx
  _BYTE pExceptionObject[16]; // [rsp+20h] [rbp-48h] BYREF
  void **v20; // [rsp+30h] [rbp-38h]
  void **v21; // [rsp+38h] [rbp-30h]
  __int64 v22; // [rsp+40h] [rbp-28h]
  __int64 v23; // [rsp+48h] [rbp-20h]
  int v24; // [rsp+50h] [rbp-18h]
  int v25; // [rsp+54h] [rbp-14h]
  wchar_t *Source; // [rsp+C8h] [rbp+60h] BYREF

  v2 = this;
  v20 = &CStackTemplate<unsigned short *>::`vftable';
  v21 = &DynamicBuffer<unsigned short *>::`vftable';
  v3 = 0;
  v22 = 0;
  v23 = 0;
  v4 = 0;
  v24 = 5;
  v25 = 5;
  v5 = 3;
  *a2 = 0;
  Source = 0;
  v6 = 0;
  v7 = (__int64)(*((_QWORD *)v2 + 3) - *((_QWORD *)v2 + 2)) >> 3;
  v8 = 1;
  while ( 1 )
  {
    LODWORD(v7) = v7 - 1;
    if ( (int)v7 < 0 )
    {
      v6 = malloc(2 * v5);
      if ( v6 )
      {
        *v6 = 0;
        _o_wcscat_s(v6, v5, L"[");
        while ( v4 )
        {
          v16 = (void *)v3[--v4];
          if ( !v8 )
            _o_wcscat_s(v6, v5, L",");
          _o_wcscat_s(v6, v5, v16);
          v8 = 0;
          if ( v16 )
            free(v16);
        }
        _o_wcscat_s(v6, v5, L"]");
        v10 = 0;
      }
      else
      {
        v10 = -895090686;
      }
      goto LABEL_39;
    }
    v9 = *((_QWORD *)v2 + 2);
    if ( (unsigned int)v7 >= (unsigned __int64)((*((_QWORD *)v2 + 3) - v9) >> 3) )
    {
      JsonException::JsonException((JsonException *)pExceptionObject, -895090685);
      throw (JsonException *)pExceptionObject;
    }
    v10 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **))(**(_QWORD **)(v9 + 8LL * (unsigned int)v7) + 8LL))(
            *(_QWORD *)(v9 + 8LL * (unsigned int)v7),
            &Source);
    if ( v10 )
      goto LABEL_39;
    v11 = v4 + 1;
    if ( v4 + 1 < v4 || v4 == -1 )
    {
      v10 = -895090684;
    }
    else
    {
      v12 = v4 - (v4 + 5) % 5 + 5;
      v10 = v12 < v11 ? 0xCAA60004 : 0;
      if ( v12 < v11 )
      {
        v8 = 1;
      }
      else
      {
        v13 = v4 - (v4 + 5) % 5 + 5;
        if ( v12 < 5 )
          v13 = 5;
        if ( v13 > (unsigned int)v23 )
        {
          v14 = _o_realloc(v3, 8LL * v13);
          if ( v14 )
          {
            v3 = (_QWORD *)v14;
            v22 = v14;
            LODWORD(v23) = v13;
          }
          v10 = -895090686;
          if ( v14 )
            v10 = 0;
          v11 = v4 + 1;
        }
        else
        {
          v10 = 0;
        }
        v8 = 1;
        if ( !v10 )
        {
          v3[v4] = Source;
          v4 = v11;
          HIDWORD(v23) = v11;
        }
      }
    }
    if ( v10 )
      break;
    if ( Source )
    {
      v15 = wcsnlen(Source, 0x7FFFFFFFu);
      if ( v15 == 0x7FFFFFFF )
        goto LABEL_39;
    }
    else
    {
      v15 = 0;
    }
    v5 += v15 + 2;
    v2 = this;
  }
  if ( Source )
  {
    free(Source);
    Source = 0;
  }
LABEL_39:
  while ( v4 )
  {
    v17 = (void *)v3[--v4];
    if ( v17 )
      free(v17);
  }
  if ( v10 )
  {
    if ( v6 )
      free(v6);
  }
  else
  {
    *a2 = v6;
  }
  if ( v3 )
    free(v3);
  return v10;
}

```

## disassembly

```asm
0x14001d400  mov     [rsp-40h+arg_8], rdx
0x14001d405  mov     [rsp-40h+arg_0], rcx
0x14001d40a  push    rbp
0x14001d40b  push    rbx
0x14001d40c  push    rsi
0x14001d40d  push    rdi
0x14001d40e  push    r12
0x14001d410  push    r13
0x14001d412  push    r14
0x14001d414  push    r15
0x14001d416  mov     rbp, rsp
0x14001d419  sub     rsp, 68h
0x14001d41d  mov     rax, rcx
0x14001d420  lea     rcx, ??_7?$CStackTemplate@PEAG@@6B@; const CStackTemplate<ushort *>::`vftable'
0x14001d427  mov     [rbp+var_38], rcx
0x14001d42b  lea     rcx, ??_7?$DynamicBuffer@PEAG@@6B@; const DynamicBuffer<ushort *>::`vftable'
0x14001d432  mov     [rbp+var_30], rcx
0x14001d436  xor     r14d, r14d
0x14001d439  mov     [rbp+var_28], r14
0x14001d43d  mov     [rbp+var_20], r14
0x14001d441  xor     ebx, ebx
0x14001d443  lea     ecx, [rbx+5]
0x14001d446  mov     [rbp+var_18], ecx
0x14001d449  mov     [rbp+var_14], ecx
0x14001d44c  lea     r15d, [r14+3]
0x14001d450  mov     [rdx], rbx
0x14001d453  mov     [rbp+Source], rbx
0x14001d457  xor     esi, esi
0x14001d459  mov     r13, [rax+18h]
0x14001d45d  sub     r13, [rax+10h]
0x14001d461  sar     r13, 3
0x14001d465  lea     r12d, [r14+1]
0x14001d469  jmp     loc_14001D597
0x14001d46e  mov     rcx, [rax+10h]
0x14001d472  mov     edx, r13d
0x14001d475  mov     rax, [rax+18h]
0x14001d479  sub     rax, rcx
0x14001d47c  sar     rax, 3
0x14001d480  cmp     rdx, rax
0x14001d483  jnb     loc_14001D69D
0x14001d489  mov     rcx, [rcx+r13*8]
0x14001d48d  mov     rax, [rcx]
0x14001d490  lea     rdx, [rbp+Source]
0x14001d494  mov     rax, [rax+8]
0x14001d498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d49d  mov     edi, eax
0x14001d49f  test    eax, eax
0x14001d4a1  jnz     loc_14001D646
0x14001d4a7  lea     r8d, [rbx+1]
0x14001d4ab  mov     [rbp+arg_10], r8d
0x14001d4af  cmp     r8d, ebx
0x14001d4b2  jb      loc_14001D55F
0x14001d4b8  cmp     r8d, r12d
0x14001d4bb  jb      loc_14001D55F
0x14001d4c1  lea     ecx, [rbx+5]
0x14001d4c4  mov     eax, 0CCCCCCCDh
0x14001d4c9  mul     ecx
0x14001d4cb  shr     edx, 2
0x14001d4ce  lea     eax, [rdx+rdx*4]
0x14001d4d1  sub     ecx, eax
0x14001d4d3  mov     eax, ebx
0x14001d4d5  sub     eax, ecx
0x14001d4d7  add     eax, 5
0x14001d4da  cmp     eax, r8d
0x14001d4dd  sbb     edi, edi
0x14001d4df  and     edi, 0CAA60004h
0x14001d4e5  mov     r12d, r8d
0x14001d4e8  cmp     eax, r8d
0x14001d4eb  cmovnb  r12d, eax
0x14001d4ef  jb      short loc_14001D557
0x14001d4f1  mov     eax, 5
0x14001d4f6  cmp     r12d, eax
0x14001d4f9  cmovb   r12d, eax
0x14001d4fd  cmp     r12d, dword ptr [rbp+var_20]
0x14001d501  ja      short loc_14001D507
0x14001d503  xor     edi, edi
0x14001d505  jmp     short loc_14001D53B
0x14001d507  mov     edx, r12d
0x14001d50a  shl     rdx, 3
0x14001d50e  mov     rcx, r14
0x14001d511  call    cs:__imp__o_realloc
0x14001d517  mov     rcx, rax
0x14001d51a  test    rax, rax
0x14001d51d  jz      short loc_14001D52A
0x14001d51f  mov     r14, rax
0x14001d522  mov     [rbp+var_28], rax
0x14001d526  mov     dword ptr [rbp+var_20], r12d
0x14001d52a  mov     edi, 0CAA60002h
0x14001d52f  xor     eax, eax
0x14001d531  test    rcx, rcx
0x14001d534  cmovnz  edi, eax
0x14001d537  mov     r8d, [rbp+arg_10]
0x14001d53b  mov     r12d, 1
0x14001d541  test    edi, edi
0x14001d543  jnz     short loc_14001D564
0x14001d545  mov     ecx, ebx
0x14001d547  mov     rax, [rbp+Source]
0x14001d54b  mov     [r14+rcx*8], rax
0x14001d54f  mov     ebx, r8d
0x14001d552  mov     dword ptr [rbp+var_20+4], ebx
0x14001d555  jmp     short loc_14001D564
0x14001d557  mov     r12d, 1
0x14001d55d  jmp     short loc_14001D564
0x14001d55f  mov     edi, 0CAA60004h
0x14001d564  mov     rcx, [rbp+Source]; Block
0x14001d568  test    edi, edi
0x14001d56a  jnz     short loc_14001D5BC
0x14001d56c  test    rcx, rcx
0x14001d56f  jnz     short loc_14001D575
0x14001d571  xor     eax, eax
0x14001d573  jmp     short loc_14001D58C
0x14001d575  mov     edx, 7FFFFFFFh; MaxCount
0x14001d57a  call    cs:__imp_wcsnlen
0x14001d580  cmp     rax, 7FFFFFFFh
0x14001d586  jz      loc_14001D646
0x14001d58c  add     rax, 2
0x14001d590  add     r15, rax
0x14001d593  mov     rax, [rbp+arg_0]
0x14001d597  sub     r13d, r12d
0x14001d59a  jns     loc_14001D46E
0x14001d5a0  lea     rcx, [r15+r15]; Size
0x14001d5a4  call    cs:__imp_malloc
0x14001d5aa  mov     rsi, rax
0x14001d5ad  test    rax, rax
0x14001d5b0  jnz     short loc_14001D5D1
0x14001d5b2  mov     edi, 0CAA60002h
0x14001d5b7  jmp     loc_14001D646
0x14001d5bc  test    rcx, rcx
0x14001d5bf  jz      loc_14001D646
0x14001d5c5  call    cs:__imp_free
0x14001d5cb  mov     [rbp+Source], rsi
0x14001d5cf  jmp     short loc_14001D646
0x14001d5d1  xor     eax, eax
0x14001d5d3  mov     [rsi], ax
0x14001d5d6  lea     r8, asc_14003751C; "["
0x14001d5dd  mov     rdx, r15
0x14001d5e0  mov     rcx, rsi
0x14001d5e3  call    cs:__imp__o_wcscat_s
0x14001d5e9  test    ebx, ebx
0x14001d5eb  jz      short loc_14001D631
0x14001d5ed  lea     ecx, [rbx-1]
0x14001d5f0  mov     rdi, [r14+rcx*8]
0x14001d5f4  cmovnz  ebx, ecx
0x14001d5f7  test    r12b, r12b
0x14001d5fa  jnz     short loc_14001D60F
0x14001d5fc  lea     r8, asc_140037514; ","
0x14001d603  mov     rdx, r15
0x14001d606  mov     rcx, rsi
0x14001d609  call    cs:__imp__o_wcscat_s
0x14001d60f  mov     r8, rdi
0x14001d612  mov     rdx, r15
0x14001d615  mov     rcx, rsi
0x14001d618  call    cs:__imp__o_wcscat_s
0x14001d61e  xor     r12b, r12b
0x14001d621  test    rdi, rdi
0x14001d624  jz      short loc_14001D5E9
0x14001d626  mov     rcx, rdi; Block
0x14001d629  call    cs:__imp_free
0x14001d62f  jmp     short loc_14001D5E9
0x14001d631  lea     r8, asc_140037520; "]"
0x14001d638  mov     rdx, r15
0x14001d63b  mov     rcx, rsi
0x14001d63e  call    cs:__imp__o_wcscat_s
0x14001d644  xor     edi, edi
0x14001d646  test    ebx, ebx
0x14001d648  jz      short loc_14001D661
0x14001d64a  lea     edx, [rbx-1]
0x14001d64d  mov     rcx, [r14+rdx*8]; Block
0x14001d651  cmovnz  ebx, edx
0x14001d654  test    rcx, rcx
0x14001d657  jz      short loc_14001D646
0x14001d659  call    cs:__imp_free
0x14001d65f  jmp     short loc_14001D646
0x14001d661  test    edi, edi
0x14001d663  jz      short loc_14001D675
0x14001d665  test    rsi, rsi
0x14001d668  jz      short loc_14001D67C
0x14001d66a  mov     rcx, rsi; Block
0x14001d66d  call    cs:__imp_free
0x14001d673  jmp     short loc_14001D67C
0x14001d675  mov     rax, [rbp+arg_8]
0x14001d679  mov     [rax], rsi
0x14001d67c  test    r14, r14
0x14001d67f  jz      short loc_14001D68A
0x14001d681  mov     rcx, r14; Block
0x14001d684  call    cs:__imp_free
0x14001d68a  mov     eax, edi
0x14001d68c  add     rsp, 68h
0x14001d690  pop     r15
0x14001d692  pop     r14
0x14001d694  pop     r13
0x14001d696  pop     r12
0x14001d698  pop     rdi
0x14001d699  pop     rsi
0x14001d69a  pop     rbx
0x14001d69b  pop     rbp
0x14001d69c  retn
0x14001d69d  mov     edx, 0CAA60003h; int
0x14001d6a2  lea     rcx, [rbp+pExceptionObject]; this
0x14001d6a6  call    ??0JsonException@@QEAA@J@Z; JsonException::JsonException(long)
0x14001d6ab  lea     rdx, _TI2?AVJsonException@@; pThrowInfo
0x14001d6b2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14001d6b6  call    _CxxThrowException_0
```
