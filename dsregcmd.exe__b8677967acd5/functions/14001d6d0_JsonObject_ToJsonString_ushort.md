# JsonObject::ToJsonString(ushort * *)

- ea: `0x14001d6d0`
- end: `0x14001da8f`
- name: `?ToJsonString@JsonObject@@UEBAKPEAPEAG@Z`
- size: `959`
- prototype: `unsigned int __fastcall(JsonObject *__hidden this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140029854`
- `0x14002a154`

## callees

- `0x14001d06c`
- `0x14001d6d0`
- `0x140030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001d83f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001d84e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001d997`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001da22`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001da5f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001da76`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001d83f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001d84e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001d997`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001da22`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001da5f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001da76`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14001d7e2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14001d9a6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14001d7e2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14001d9a6`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x14001d8c3`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x14001d8c3`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001d808`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001d81c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001d82d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001d9d1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001da02`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001da11`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001da37`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001d808`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001d81c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001d82d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001d9d1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001da02`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001da11`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001da37`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14001d79e`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14001d7c5`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14001d924`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14001d79e`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14001d7c5`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14001d924`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall JsonObject::ToJsonString(JsonObject *this, unsigned __int16 **a2)
{
  JsonObject *v2; // rax
  _QWORD *v3; // r13
  unsigned int v4; // esi
  _WORD *v5; // r14
  __int64 v6; // rdi
  _QWORD *v7; // rbx
  size_t v8; // r12
  const unsigned __int16 *v9; // rcx
  unsigned int JsonEncodedQuotedString; // edi
  wchar_t *v11; // r15
  size_t v12; // rax
  wchar_t *v13; // r12
  unsigned int v14; // r12d
  unsigned int v15; // eax
  unsigned int v16; // r15d
  __int64 v17; // rax
  wchar_t *v18; // rcx
  size_t v19; // rax
  __int64 **v20; // rcx
  __int64 i; // rax
  __int64 *j; // rcx
  char v23; // r15
  void *v24; // rbx
  wchar_t *v26; // [rsp+20h] [rbp-48h] BYREF
  __int64 v27; // [rsp+28h] [rbp-40h]
  __int64 v28; // [rsp+30h] [rbp-38h]
  void **v29; // [rsp+38h] [rbp-30h]
  void **v30; // [rsp+40h] [rbp-28h]
  __int64 v31; // [rsp+48h] [rbp-20h]
  __int64 v32; // [rsp+50h] [rbp-18h]
  int v33; // [rsp+58h] [rbp-10h]
  int v34; // [rsp+5Ch] [rbp-Ch]
  wchar_t *v37; // [rsp+C0h] [rbp+58h]
  wchar_t *Source; // [rsp+C8h] [rbp+60h] BYREF

  v2 = this;
  v29 = &CStackTemplate<unsigned short *>::`vftable';
  v30 = &DynamicBuffer<unsigned short *>::`vftable';
  v3 = 0;
  v31 = 0;
  v32 = 0;
  v4 = 0;
  v33 = 5;
  v34 = 5;
  v5 = 0;
  v6 = 3;
  v27 = 3;
  v7 = (_QWORD *)**((_QWORD **)this + 2);
  while ( v7 != *((_QWORD **)v2 + 2) )
  {
    v28 = v7[8];
    v26 = 0;
    v8 = 0;
    v37 = 0;
    Source = 0;
    v9 = (const unsigned __int16 *)(v7 + 4);
    if ( v7[7] > 7u )
      v9 = *(const unsigned __int16 **)v9;
    JsonEncodedQuotedString = JsonUtil::GetJsonEncodedQuotedString(v9, &Source);
    v11 = Source;
    if ( !JsonEncodedQuotedString )
    {
      Source = 0;
      JsonEncodedQuotedString = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v28 + 8LL))(v28, &v26);
      if ( JsonEncodedQuotedString )
        goto LABEL_13;
      if ( !v11 || (v8 = wcsnlen(v11, 0x7FFFFFFFu), v8 != 0x7FFFFFFF) )
      {
        if ( v26 )
        {
          v12 = wcsnlen(v26, 0x7FFFFFFFu);
          if ( v12 == 0x7FFFFFFF )
            goto LABEL_16;
        }
        else
        {
          v12 = 0;
        }
        v8 += v12 + 2;
        Source = (wchar_t *)v8;
LABEL_13:
        v13 = (wchar_t *)malloc(2 * v8);
        if ( v13 )
        {
          *v13 = 0;
          _o_wcscat_s(v13, Source, v11);
          _o_wcscat_s(v13, Source, L":");
          _o_wcscat_s(v13, Source, v26);
          v37 = v13;
        }
        else
        {
          JsonEncodedQuotedString = -895090686;
        }
      }
    }
LABEL_16:
    if ( v11 )
      free(v11);
    if ( v26 )
      free(v26);
    if ( JsonEncodedQuotedString )
      goto LABEL_60;
    v14 = v4 + 1;
    if ( v4 + 1 < v4 || v4 == -1 )
    {
      JsonEncodedQuotedString = -895090684;
LABEL_35:
      v18 = v37;
      goto LABEL_36;
    }
    v15 = v4 - (v4 + 5) % 5 + 5;
    JsonEncodedQuotedString = v15 < v14 ? 0xCAA60004 : 0;
    if ( v15 < v14 )
      goto LABEL_35;
    v16 = v4 - (v4 + 5) % 5 + 5;
    if ( v15 < 5 )
      v16 = 5;
    if ( v16 > (unsigned int)v32 )
    {
      v17 = _o_realloc(v3, 8LL * v16);
      if ( v17 )
      {
        v3 = (_QWORD *)v17;
        v31 = v17;
        LODWORD(v32) = v16;
      }
      JsonEncodedQuotedString = -895090686;
      if ( v17 )
        JsonEncodedQuotedString = 0;
    }
    else
    {
      JsonEncodedQuotedString = 0;
    }
    v18 = v37;
    if ( JsonEncodedQuotedString )
      goto LABEL_49;
    v3[v4++] = v37;
    HIDWORD(v32) = v14;
LABEL_36:
    if ( JsonEncodedQuotedString )
      goto LABEL_49;
    if ( v18 )
    {
      v19 = wcsnlen(v18, 0x7FFFFFFFu);
      if ( v19 == 0x7FFFFFFF )
        goto LABEL_60;
    }
    else
    {
      v19 = 0;
    }
    v6 = v19 + v27 + 2;
    v27 = v6;
    v20 = (__int64 **)v7[2];
    if ( *((_BYTE *)v20 + 25) )
    {
      for ( i = v7[1]; !*(_BYTE *)(i + 25) && v7 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
        v7 = (_QWORD *)i;
      v7 = (_QWORD *)i;
    }
    else
    {
      v7 = (_QWORD *)v7[2];
      for ( j = *v20; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v7 = j;
    }
    v2 = this;
  }
  v5 = malloc(2 * v6);
  if ( v5 )
  {
    *v5 = 0;
    _o_wcscat_s(v5, v6, L"{");
    v23 = 1;
    while ( v4 )
    {
      v24 = (void *)v3[--v4];
      if ( !v23 )
        _o_wcscat_s(v5, v6, L",");
      _o_wcscat_s(v5, v6, v24);
      v23 = 0;
      if ( v24 )
        free(v24);
    }
    _o_wcscat_s(v5, v6, L"}");
    JsonEncodedQuotedString = 0;
  }
  else
  {
    JsonEncodedQuotedString = -895090686;
  }
LABEL_60:
  while ( v4 )
  {
    v18 = (wchar_t *)v3[--v4];
LABEL_49:
    if ( v18 )
      free(v18);
  }
  if ( JsonEncodedQuotedString )
  {
    if ( v5 )
      free(v5);
  }
  else
  {
    *a2 = v5;
  }
  if ( v3 )
    free(v3);
  return JsonEncodedQuotedString;
}

```

## disassembly

```asm
0x14001d6d0  mov     [rsp-40h+arg_8], rdx
0x14001d6d5  mov     [rsp-40h+arg_0], rcx
0x14001d6da  push    rbp
0x14001d6db  push    rbx
0x14001d6dc  push    rsi
0x14001d6dd  push    rdi
0x14001d6de  push    r12
0x14001d6e0  push    r13
0x14001d6e2  push    r14
0x14001d6e4  push    r15
0x14001d6e6  mov     rbp, rsp
0x14001d6e9  sub     rsp, 68h
0x14001d6ed  mov     rax, rcx
0x14001d6f0  lea     rcx, ??_7?$CStackTemplate@PEAG@@6B@; const CStackTemplate<ushort *>::`vftable'
0x14001d6f7  mov     [rbp+var_30], rcx
0x14001d6fb  lea     rcx, ??_7?$DynamicBuffer@PEAG@@6B@; const DynamicBuffer<ushort *>::`vftable'
0x14001d702  mov     [rbp+var_28], rcx
0x14001d706  xor     r13d, r13d
0x14001d709  mov     [rbp+var_20], r13
0x14001d70d  mov     [rbp+var_18], r13
0x14001d711  xor     esi, esi
0x14001d713  lea     ecx, [rsi+5]
0x14001d716  mov     [rbp+var_10], ecx
0x14001d719  mov     [rbp+var_C], ecx
0x14001d71c  xor     r14d, r14d
0x14001d71f  lea     edi, [rsi+3]
0x14001d722  mov     [rbp+var_40], rdi
0x14001d726  mov     rbx, [rax+10h]
0x14001d72a  mov     rbx, [rbx]
0x14001d72d  cmp     rbx, [rax+10h]
0x14001d731  jz      loc_14001D9A2
0x14001d737  mov     rax, [rbx+40h]
0x14001d73b  mov     [rbp+var_38], rax
0x14001d73f  mov     [rbp+var_48], r14
0x14001d743  xor     r12d, r12d
0x14001d746  mov     [rbp+arg_10], r12
0x14001d74a  mov     [rbp+Source], r12
0x14001d74e  lea     rcx, [rbx+20h]
0x14001d752  cmp     qword ptr [rbx+38h], 7
0x14001d757  jbe     short loc_14001D75C
0x14001d759  mov     rcx, [rcx]; unsigned __int16 *
0x14001d75c  lea     rdx, [rbp+Source]; unsigned __int16 **
0x14001d760  call    ?GetJsonEncodedQuotedString@JsonUtil@@SAKPEBGPEAPEAG@Z; JsonUtil::GetJsonEncodedQuotedString(ushort const *,ushort * *)
0x14001d765  mov     edi, eax
0x14001d767  mov     r15, [rbp+Source]
0x14001d76b  test    eax, eax
0x14001d76d  jnz     loc_14001D837
0x14001d773  mov     [rbp+Source], r12
0x14001d777  mov     rcx, [rbp+var_38]
0x14001d77b  mov     rax, [rcx]
0x14001d77e  lea     rdx, [rbp+var_48]
0x14001d782  mov     rax, [rax+8]
0x14001d786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d78b  mov     edi, eax
0x14001d78d  test    eax, eax
0x14001d78f  jnz     short loc_14001D7DE
0x14001d791  test    r15, r15
0x14001d794  jz      short loc_14001D7B3
0x14001d796  mov     edx, 7FFFFFFFh; MaxCount
0x14001d79b  mov     rcx, r15; Source
0x14001d79e  call    cs:__imp_wcsnlen
0x14001d7a4  mov     r12, rax
0x14001d7a7  cmp     rax, 7FFFFFFFh
0x14001d7ad  jz      loc_14001D837
0x14001d7b3  mov     rcx, [rbp+var_48]; Source
0x14001d7b7  test    rcx, rcx
0x14001d7ba  jnz     short loc_14001D7C0
0x14001d7bc  xor     eax, eax
0x14001d7be  jmp     short loc_14001D7D3
0x14001d7c0  mov     edx, 7FFFFFFFh; MaxCount
0x14001d7c5  call    cs:__imp_wcsnlen
0x14001d7cb  cmp     rax, 7FFFFFFFh
0x14001d7d1  jz      short loc_14001D837
0x14001d7d3  add     r12, 2
0x14001d7d7  add     r12, rax
0x14001d7da  mov     [rbp+Source], r12
0x14001d7de  lea     rcx, [r12+r12]; Size
0x14001d7e2  call    cs:__imp_malloc
0x14001d7e8  mov     r12, rax
0x14001d7eb  test    rax, rax
0x14001d7ee  jnz     short loc_14001D7F7
0x14001d7f0  mov     edi, 0CAA60002h
0x14001d7f5  jmp     short loc_14001D837
0x14001d7f7  xor     eax, eax
0x14001d7f9  mov     [r12], ax
0x14001d7fe  mov     r8, r15
0x14001d801  mov     rdx, [rbp+Source]
0x14001d805  mov     rcx, r12
0x14001d808  call    cs:__imp__o_wcscat_s
0x14001d80e  lea     r8, asc_1400374A4; ":"
0x14001d815  mov     rdx, [rbp+Source]
0x14001d819  mov     rcx, r12
0x14001d81c  call    cs:__imp__o_wcscat_s
0x14001d822  mov     r8, [rbp+var_48]
0x14001d826  mov     rdx, [rbp+Source]
0x14001d82a  mov     rcx, r12
0x14001d82d  call    cs:__imp__o_wcscat_s
0x14001d833  mov     [rbp+arg_10], r12
0x14001d837  test    r15, r15
0x14001d83a  jz      short loc_14001D845
0x14001d83c  mov     rcx, r15; Block
0x14001d83f  call    cs:__imp_free
0x14001d845  mov     rcx, [rbp+var_48]; Block
0x14001d849  test    rcx, rcx
0x14001d84c  jz      short loc_14001D854
0x14001d84e  call    cs:__imp_free
0x14001d854  test    edi, edi
0x14001d856  jnz     loc_14001DA3F
0x14001d85c  lea     r12d, [rsi+1]
0x14001d860  cmp     r12d, esi
0x14001d863  jb      loc_14001D905
0x14001d869  cmp     r12d, 1
0x14001d86d  jb      loc_14001D905
0x14001d873  lea     ecx, [rsi+5]
0x14001d876  mov     eax, 0CCCCCCCDh
0x14001d87b  mul     ecx
0x14001d87d  shr     edx, 2
0x14001d880  lea     eax, [rdx+rdx*4]
0x14001d883  sub     ecx, eax
0x14001d885  mov     eax, esi
0x14001d887  sub     eax, ecx
0x14001d889  add     eax, 5
0x14001d88c  cmp     eax, r12d
0x14001d88f  sbb     edi, edi
0x14001d891  and     edi, 0CAA60004h
0x14001d897  mov     r15d, r12d
0x14001d89a  cmp     eax, r12d
0x14001d89d  cmovnb  r15d, eax
0x14001d8a1  jb      short loc_14001D90A
0x14001d8a3  mov     eax, 5
0x14001d8a8  cmp     r15d, eax
0x14001d8ab  cmovb   r15d, eax
0x14001d8af  cmp     r15d, dword ptr [rbp+var_18]
0x14001d8b3  ja      short loc_14001D8B9
0x14001d8b5  xor     edi, edi
0x14001d8b7  jmp     short loc_14001D8E9
0x14001d8b9  mov     edx, r15d
0x14001d8bc  shl     rdx, 3
0x14001d8c0  mov     rcx, r13
0x14001d8c3  call    cs:__imp__o_realloc
0x14001d8c9  mov     rcx, rax
0x14001d8cc  test    rax, rax
0x14001d8cf  jz      short loc_14001D8DC
0x14001d8d1  mov     r13, rax
0x14001d8d4  mov     [rbp+var_20], rax
0x14001d8d8  mov     dword ptr [rbp+var_18], r15d
0x14001d8dc  mov     edi, 0CAA60002h
0x14001d8e1  xor     eax, eax
0x14001d8e3  test    rcx, rcx
0x14001d8e6  cmovnz  edi, eax
0x14001d8e9  mov     rcx, [rbp+arg_10]; Block
0x14001d8ed  test    edi, edi
0x14001d8ef  jnz     loc_14001D98E
0x14001d8f5  mov     eax, esi
0x14001d8f7  mov     [r13+rax*8+0], rcx
0x14001d8fc  mov     esi, r12d
0x14001d8ff  mov     dword ptr [rbp+var_18+4], r12d
0x14001d903  jmp     short loc_14001D90E
0x14001d905  mov     edi, 0CAA60004h
0x14001d90a  mov     rcx, [rbp+arg_10]; Source
0x14001d90e  test    edi, edi
0x14001d910  jnz     short loc_14001D98E
0x14001d912  test    rcx, rcx
0x14001d915  jnz     short loc_14001D91B
0x14001d917  xor     eax, eax
0x14001d919  jmp     short loc_14001D933
0x14001d91b  mov     r12d, 7FFFFFFFh
0x14001d921  mov     edx, r12d; MaxCount
0x14001d924  call    cs:__imp_wcsnlen
0x14001d92a  cmp     rax, r12
0x14001d92d  jz      loc_14001DA3F
0x14001d933  mov     rdi, [rbp+var_40]
0x14001d937  add     rdi, 2
0x14001d93b  add     rdi, rax
0x14001d93e  mov     [rbp+var_40], rdi
0x14001d942  mov     rcx, [rbx+10h]
0x14001d946  cmp     [rcx+19h], r14b
0x14001d94a  jz      short loc_14001D96A
0x14001d94c  mov     rax, [rbx+8]
0x14001d950  jmp     short loc_14001D95F
0x14001d952  cmp     rbx, [rax+10h]
0x14001d956  jnz     short loc_14001D965
0x14001d958  mov     rbx, rax
0x14001d95b  mov     rax, [rax+8]
0x14001d95f  cmp     [rax+19h], r14b
0x14001d963  jz      short loc_14001D952
0x14001d965  mov     rbx, rax
0x14001d968  jmp     short loc_14001D985
0x14001d96a  mov     rbx, rcx
0x14001d96d  mov     rcx, [rcx]
0x14001d970  cmp     [rcx+19h], r14b
0x14001d974  jnz     short loc_14001D985
0x14001d976  mov     rbx, rcx
0x14001d979  mov     rax, [rcx]
0x14001d97c  mov     rcx, rax
0x14001d97f  cmp     [rax+19h], r14b
0x14001d983  jz      short loc_14001D976
0x14001d985  mov     rax, [rbp+arg_0]
0x14001d989  jmp     loc_14001D72D
0x14001d98e  test    rcx, rcx
0x14001d991  jz      loc_14001DA3F
0x14001d997  call    cs:__imp_free
0x14001d99d  jmp     loc_14001DA3F
0x14001d9a2  lea     rcx, [rdi+rdi]; Size
0x14001d9a6  call    cs:__imp_malloc
0x14001d9ac  mov     r14, rax
0x14001d9af  test    rax, rax
0x14001d9b2  jnz     short loc_14001D9BE
0x14001d9b4  mov     edi, 0CAA60002h
0x14001d9b9  jmp     loc_14001DA3F
0x14001d9be  xor     eax, eax
0x14001d9c0  mov     [r14], ax
0x14001d9c4  lea     r8, asc_140037510; "{"
0x14001d9cb  mov     rdx, rdi
0x14001d9ce  mov     rcx, r14
0x14001d9d1  call    cs:__imp__o_wcscat_s
0x14001d9d7  mov     r15d, 1
0x14001d9dd  mov     edx, esi
0x14001d9df  test    esi, esi
0x14001d9e1  jz      short loc_14001DA2A
0x14001d9e3  lea     ecx, [rsi-1]
0x14001d9e6  mov     rbx, [r13+rcx*8+0]
0x14001d9eb  test    edx, edx
0x14001d9ed  cmovnz  esi, ecx
0x14001d9f0  test    r15b, r15b
0x14001d9f3  jnz     short loc_14001DA08
0x14001d9f5  lea     r8, asc_140037514; ","
0x14001d9fc  mov     rdx, rdi
0x14001d9ff  mov     rcx, r14
0x14001da02  call    cs:__imp__o_wcscat_s
0x14001da08  mov     r8, rbx
0x14001da0b  mov     rdx, rdi
0x14001da0e  mov     rcx, r14
0x14001da11  call    cs:__imp__o_wcscat_s
0x14001da17  xor     r15b, r15b
0x14001da1a  test    rbx, rbx
0x14001da1d  jz      short loc_14001D9DD
0x14001da1f  mov     rcx, rbx; Block
0x14001da22  call    cs:__imp_free
0x14001da28  jmp     short loc_14001D9DD
0x14001da2a  lea     r8, asc_140037518; "}"
0x14001da31  mov     rdx, rdi
0x14001da34  mov     rcx, r14
0x14001da37  call    cs:__imp__o_wcscat_s
0x14001da3d  xor     edi, edi
0x14001da3f  test    esi, esi
0x14001da41  jz      short loc_14001DA53
0x14001da43  lea     edx, [rsi-1]
0x14001da46  mov     rcx, [r13+rdx*8+0]
0x14001da4b  cmovnz  esi, edx
0x14001da4e  jmp     loc_14001D98E
0x14001da53  test    edi, edi
0x14001da55  jz      short loc_14001DA67
0x14001da57  test    r14, r14
0x14001da5a  jz      short loc_14001DA6E
0x14001da5c  mov     rcx, r14; Block
0x14001da5f  call    cs:__imp_free
0x14001da65  jmp     short loc_14001DA6E
0x14001da67  mov     rax, [rbp+arg_8]
0x14001da6b  mov     [rax], r14
0x14001da6e  test    r13, r13
0x14001da71  jz      short loc_14001DA7C
0x14001da73  mov     rcx, r13; Block
0x14001da76  call    cs:__imp_free
0x14001da7c  mov     eax, edi
0x14001da7e  add     rsp, 68h
0x14001da82  pop     r15
0x14001da84  pop     r14
0x14001da86  pop     r13
0x14001da88  pop     r12
0x14001da8a  pop     rdi
0x14001da8b  pop     rsi
0x14001da8c  pop     rbx
0x14001da8d  pop     rbp
0x14001da8e  retn
```
