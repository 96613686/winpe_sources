# CLRConfig::GetConfigValue(CLRConfig::ConfigStringInfo const &,ushort * *)

- ea: `0x14000a610`
- end: `0x14000a841`
- name: `?GetConfigValue@CLRConfig@@SAJAEBUConfigStringInfo@1@PEAPEAG@Z`
- size: `561`
- prototype: `__int64 __fastcall(wchar_t **, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x140007388`
- `0x140008ed0`
- `0x140010454`

## callees

- `0x14000a0d4`
- `0x14000a10c`
- `0x14000a2ac`
- `0x14000a610`
- `0x14000a844`
- `0x14000fe04`
- `0x140013200`
- `0x140013f30`

## import_xrefs

- `ucrtbase_clr0400!wcscpy_s` at `0x14000a6c4`
- `ucrtbase_clr0400!wcscpy_s` at `0x14000a7b4`
- `ucrtbase_clr0400!wcscpy_s` at `0x14000a6c4`
- `ucrtbase_clr0400!wcscpy_s` at `0x14000a7b4`

## pseudocode

```c
__int64 __fastcall CLRConfig::GetConfigValue(wchar_t **a1, unsigned __int16 **a2)
{
  unsigned __int16 *ConfigString_DontUse; // rbx
  wchar_t *v5; // rcx
  __int64 v6; // rdi
  unsigned __int64 v7; // rdi
  unsigned __int128 v8; // rax
  wchar_t *v9; // rax
  int v10; // r8d
  char v11; // dl
  char v12; // r14
  BOOL v13; // edi
  unsigned int v14; // r8d
  __int64 v15; // rdi
  unsigned __int64 v16; // rdi
  unsigned __int128 v17; // rax
  wchar_t *v18; // rax
  unsigned __int16 *v20; // rdi
  wchar_t *v21; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v22; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v23[264]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t Source[132]; // [rsp+148h] [rbp+48h] BYREF

  ConfigString_DontUse = 0;
  if ( ((_DWORD)a1[1] & 0x400) == 0 )
  {
    if ( CLRConfig::s_IsQuirkEnabledCallback )
    {
      v5 = *a1;
      LODWORD(v21) = 0;
      if ( (int)CLRConfig::getQuirkEnabledAndValueFromWinDB(v5, (int *)&v21, (struct _CPT_QUIRK_DATA *)v23) >= 0 )
      {
        if ( (_DWORD)v21 )
        {
          v6 = -1;
          do
            ++v6;
          while ( Source[v6] );
          v7 = v6 + 1;
          v8 = v7 * (unsigned __int128)2uLL;
          if ( !is_mul_ok(v7, 2u) )
            *(_QWORD *)&v8 = -1;
          v9 = (wchar_t *)operator new[](v8, *((const struct NoThrow **)&v8 + 1));
          ConfigString_DontUse = v9;
          if ( !v9 )
            return 2147942414LL;
          wcscpy_s(v9, v7, Source);
        }
      }
    }
  }
  v10 = *((_DWORD *)a1 + 2);
  v11 = ((v10 & 1) == 0) | 2;
  if ( (v10 & 8) != 0 )
    v11 = ((_DWORD)a1[1] & 1) == 0;
  v12 = v11 | 4;
  if ( (v10 & 4) != 0 )
    v12 = v11;
  v13 = (v10 & 2) == 0;
  if ( ConfigString_DontUse )
    goto LABEL_31;
  if ( (v10 & 0x20) == 0 )
  {
    ConfigString_DontUse = REGUTIL::GetConfigString_DontUse_(*a1, v13, v12, 1);
    if ( ConfigString_DontUse )
      goto LABEL_31;
  }
  v14 = *((_DWORD *)a1 + 2);
  if ( (v14 & 0x10) == 0
    && CLRConfig::s_GetConfigValueCallback
    && (int)CLRConfig::s_GetConfigValueCallback(*a1, &v21, (v14 >> 6) & 1, (v14 >> 7) & 1) >= 0
    && v21 )
  {
    v15 = -1;
    do
      ++v15;
    while ( v21[v15] );
    v16 = v15 + 1;
    v17 = v16 * (unsigned __int128)2uLL;
    if ( !is_mul_ok(v16, 2u) )
      *(_QWORD *)&v17 = -1;
    v18 = (wchar_t *)operator new[](v17, *((const struct NoThrow **)&v17 + 1));
    ConfigString_DontUse = v18;
    if ( !v18 )
      return 2147942414LL;
    wcscpy_s(v18, v16, v21);
    goto LABEL_31;
  }
  if ( ((_BYTE)a1[1] & 0x20) != 0 )
  {
    ConfigString_DontUse = REGUTIL::GetConfigString_DontUse_(*a1, v13, v12, 1);
    if ( ConfigString_DontUse )
    {
LABEL_31:
      if ( ((_DWORD)a1[1] & 0x100) != 0 )
      {
        v22 = 0;
        if ( (int)CLRConfig::TrimWhiteSpace(ConfigString_DontUse, &v22) >= 0 )
        {
          v20 = v22;
          if ( v22 )
          {
            operator delete(ConfigString_DontUse);
            ConfigString_DontUse = v20;
          }
        }
      }
    }
  }
  *a2 = ConfigString_DontUse;
  return 0;
}

```

## disassembly

```asm
0x14000a610  mov     [rsp-8+arg_10], rbx
0x14000a615  mov     [rsp-8+arg_18], rsi
0x14000a61a  push    rbp
0x14000a61b  push    rdi
0x14000a61c  push    r12
0x14000a61e  push    r14
0x14000a620  push    r15
0x14000a622  lea     rbp, [rsp-160h]
0x14000a62a  sub     rsp, 260h
0x14000a631  mov     rax, cs:__security_cookie
0x14000a638  xor     rax, rsp
0x14000a63b  mov     [rbp+180h+var_30], rax
0x14000a642  xor     r12d, r12d
0x14000a645  or      r14, 0FFFFFFFFFFFFFFFFh
0x14000a649  test    dword ptr [rcx+8], 400h
0x14000a650  mov     r15, rdx
0x14000a653  mov     rsi, rcx
0x14000a656  mov     ebx, r12d
0x14000a659  jnz     short loc_14000A6CA
0x14000a65b  cmp     cs:?s_IsQuirkEnabledCallback@CLRConfig@@0P6A_NPEBGK@ZEA, r12; bool (*CLRConfig::s_IsQuirkEnabledCallback)(ushort const *,ulong)
0x14000a662  jz      short loc_14000A6CA
0x14000a664  mov     rcx, [rcx]; Source
0x14000a667  lea     r8, [rsp+280h+var_240]; struct _CPT_QUIRK_DATA *
0x14000a66c  lea     rdx, [rsp+280h+var_250]; int *
0x14000a671  mov     dword ptr [rsp+280h+var_250], r12d
0x14000a676  call    ?getQuirkEnabledAndValueFromWinDB@CLRConfig@@SAJPEBGPEAHPEAU_CPT_QUIRK_DATA@@@Z; CLRConfig::getQuirkEnabledAndValueFromWinDB(ushort const *,int *,_CPT_QUIRK_DATA *)
0x14000a67b  test    eax, eax
0x14000a67d  js      short loc_14000A6CA
0x14000a67f  cmp     dword ptr [rsp+280h+var_250], r12d
0x14000a684  jz      short loc_14000A6CA
0x14000a686  lea     rax, [rbp+180h+Source]
0x14000a68a  mov     rdi, r14
0x14000a68d  inc     rdi
0x14000a690  cmp     [rax+rdi*2], r12w
0x14000a695  jnz     short loc_14000A68D
0x14000a697  inc     rdi
0x14000a69a  mov     eax, 2
0x14000a69f  mul     rdi
0x14000a6a2  cmovo   rax, r14
0x14000a6a6  mov     rcx, rax; dwBytes
0x14000a6a9  call    ??_U@YAPEAX_KAEBUNoThrow@@@Z; operator new[](unsigned __int64,NoThrow const &)
0x14000a6ae  mov     rbx, rax
0x14000a6b1  test    rax, rax
0x14000a6b4  jz      loc_14000A7A2
0x14000a6ba  lea     r8, [rbp+180h+Source]; Source
0x14000a6be  mov     rdx, rdi; SizeInWords
0x14000a6c1  mov     rcx, rax; Destination
0x14000a6c4  call    cs:__imp_wcscpy_s
0x14000a6ca  mov     r8d, [rsi+8]
0x14000a6ce  mov     eax, r8d
0x14000a6d1  mov     ecx, r8d
0x14000a6d4  mov     edi, r8d
0x14000a6d7  not     ecx
0x14000a6d9  and     ecx, 1
0x14000a6dc  mov     edx, ecx
0x14000a6de  or      edx, 2
0x14000a6e1  and     al, 8
0x14000a6e3  mov     eax, r8d
0x14000a6e6  cmovnz  edx, ecx
0x14000a6e9  mov     r14d, edx
0x14000a6ec  or      r14d, 4
0x14000a6f0  and     al, 4
0x14000a6f2  cmovnz  r14d, edx
0x14000a6f6  shr     edi, 1
0x14000a6f8  not     edi
0x14000a6fa  and     edi, 1
0x14000a6fd  test    rbx, rbx
0x14000a700  jnz     loc_14000A7DD
0x14000a706  test    r8b, 20h
0x14000a70a  jnz     short loc_14000A729
0x14000a70c  mov     rcx, [rsi]
0x14000a70f  lea     r9d, [rbx+1]
0x14000a713  mov     r8d, r14d
0x14000a716  mov     edx, edi
0x14000a718  call    ?GetConfigString_DontUse_@REGUTIL@@SAPEAGPEBGHW4CORConfigLevel@1@H@Z; REGUTIL::GetConfigString_DontUse_(ushort const *,int,REGUTIL::CORConfigLevel,int)
0x14000a71d  mov     rbx, rax
0x14000a720  test    rax, rax
0x14000a723  jnz     loc_14000A7DD
0x14000a729  mov     r8d, [rsi+8]
0x14000a72d  test    r8b, 10h
0x14000a731  jnz     loc_14000A7BC
0x14000a737  mov     rax, cs:?s_GetConfigValueCallback@CLRConfig@@0P6AJPEBGPEAPEBGHH@ZEA; long (*CLRConfig::s_GetConfigValueCallback)(ushort const *,ushort const * *,int,int)
0x14000a73e  test    rax, rax
0x14000a741  jz      short loc_14000A7BC
0x14000a743  mov     rcx, [rsi]
0x14000a746  lea     rdx, [rsp+280h+var_250]
0x14000a74b  mov     r9d, r8d
0x14000a74e  shr     r8d, 6
0x14000a752  shr     r9d, 7
0x14000a756  and     r8d, 1
0x14000a75a  and     r9d, 1
0x14000a75e  call    cs:__guard_dispatch_icall_fptr
0x14000a764  test    eax, eax
0x14000a766  js      short loc_14000A7BC
0x14000a768  mov     rcx, [rsp+280h+var_250]
0x14000a76d  test    rcx, rcx
0x14000a770  jz      short loc_14000A7BC
0x14000a772  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000a776  mov     rdi, r8
0x14000a779  inc     rdi
0x14000a77c  cmp     [rcx+rdi*2], r12w
0x14000a781  jnz     short loc_14000A779
0x14000a783  inc     rdi
0x14000a786  mov     eax, 2
0x14000a78b  mul     rdi
0x14000a78e  cmovo   rax, r8
0x14000a792  mov     rcx, rax; dwBytes
0x14000a795  call    ??_U@YAPEAX_KAEBUNoThrow@@@Z; operator new[](unsigned __int64,NoThrow const &)
0x14000a79a  mov     rbx, rax
0x14000a79d  test    rax, rax
0x14000a7a0  jnz     short loc_14000A7A9
0x14000a7a2  mov     eax, 8007000Eh
0x14000a7a7  jmp     short loc_14000A816
0x14000a7a9  mov     r8, [rsp+280h+var_250]; Source
0x14000a7ae  mov     rdx, rdi; SizeInWords
0x14000a7b1  mov     rcx, rax; Destination
0x14000a7b4  call    cs:__imp_wcscpy_s
0x14000a7ba  jmp     short loc_14000A7DD
0x14000a7bc  test    byte ptr [rsi+8], 20h
0x14000a7c0  jz      short loc_14000A811
0x14000a7c2  mov     rcx, [rsi]
0x14000a7c5  mov     r9d, 1
0x14000a7cb  mov     r8d, r14d
0x14000a7ce  mov     edx, edi
0x14000a7d0  call    ?GetConfigString_DontUse_@REGUTIL@@SAPEAGPEBGHW4CORConfigLevel@1@H@Z; REGUTIL::GetConfigString_DontUse_(ushort const *,int,REGUTIL::CORConfigLevel,int)
0x14000a7d5  mov     rbx, rax
0x14000a7d8  test    rax, rax
0x14000a7db  jz      short loc_14000A811
0x14000a7dd  test    dword ptr [rsi+8], 100h
0x14000a7e4  jz      short loc_14000A811
0x14000a7e6  lea     rdx, [rsp+280h+var_248]; unsigned __int16 **
0x14000a7eb  mov     [rsp+280h+var_248], r12
0x14000a7f0  mov     rcx, rbx; unsigned __int16 *
0x14000a7f3  call    ?TrimWhiteSpace@CLRConfig@@CAJPEBGPEAPEAG@Z; CLRConfig::TrimWhiteSpace(ushort const *,ushort * *)
0x14000a7f8  test    eax, eax
0x14000a7fa  js      short loc_14000A811
0x14000a7fc  mov     rdi, [rsp+280h+var_248]
0x14000a801  test    rdi, rdi
0x14000a804  jz      short loc_14000A811
0x14000a806  mov     rcx, rbx; lpMem
0x14000a809  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000a80e  mov     rbx, rdi
0x14000a811  mov     [r15], rbx
0x14000a814  xor     eax, eax
0x14000a816  mov     rcx, [rbp+180h+var_30]
0x14000a81d  xor     rcx, rsp; StackCookie
0x14000a820  call    __security_check_cookie
0x14000a825  lea     r11, [rsp+280h+var_20]
0x14000a82d  mov     rbx, [r11+40h]
0x14000a831  mov     rsi, [r11+48h]
0x14000a835  mov     rsp, r11
0x14000a838  pop     r15
0x14000a83a  pop     r14
0x14000a83c  pop     r12
0x14000a83e  pop     rdi
0x14000a83f  pop     rbp
0x14000a840  retn
```
