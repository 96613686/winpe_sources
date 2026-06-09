# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,CachedAdapterInformation,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CachedAdapterInformation>>,0>>::emplace<ushort (&)[40],CachedAdapterInformation>(ushort (&)[40],CachedAdapterInformation &&)

- ea: `0x140004d34`
- end: `0x140004ef8`
- name: `??$emplace@AEAY0CI@GUCachedAdapterInformation@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@@std@@@std@@@std@@_N@1@AEAY0CI@G$$QEAUCachedAdapterInformation@@@Z`
- size: `452`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x1400051f8`

## callees

- `0x1400022c4`
- `0x140002578`
- `0x140004810`
- `0x140004d34`
- `0x1400050cc`
- `0x140006334`
- `0x140010130`
- `0x140010440`
- `0x14001113c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004ed5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004ed5`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<std::wstring,CachedAdapterInformation,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CachedAdapterInformation>>,0>>::emplace<unsigned short (&)[40],CachedAdapterInformation>(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v8; // rdi
  char *v9; // rbp
  const wchar_t **v10; // r14
  _QWORD *v11; // rax
  __int128 v12; // xmm6
  __int64 inserted; // rsi
  const wchar_t *v14; // rdx
  unsigned __int64 v15; // rdi
  unsigned __int64 v16; // rbx
  const wchar_t *v17; // rcx
  size_t v18; // r8
  int v19; // eax
  char v20; // bl
  HKEY v22; // rcx
  __int128 v23; // [rsp+20h] [rbp-88h] BYREF
  _QWORD v24[4]; // [rsp+30h] [rbp-78h] BYREF

  v8 = *a1;
  *(_QWORD *)&v23 = a1;
  v9 = (char *)operator new(0xA8u);
  *((_QWORD *)&v23 + 1) = v9;
  v10 = (const wchar_t **)(v9 + 32);
  std::wstring::wstring(v9 + 32, a3);
  *((_QWORD *)v9 + 8) = *(_QWORD *)a4;
  *(_QWORD *)a4 = 0;
  *((_QWORD *)v9 + 9) = *(_QWORD *)(a4 + 8);
  *((_QWORD *)v9 + 10) = *(_QWORD *)(a4 + 16);
  *((_QWORD *)v9 + 11) = *(_QWORD *)(a4 + 24);
  *((_DWORD *)v9 + 24) = *(_DWORD *)(a4 + 32);
  *(_OWORD *)(v9 + 104) = 0;
  *((_QWORD *)v9 + 15) = 0;
  *((_QWORD *)v9 + 16) = 0;
  *(_OWORD *)(v9 + 104) = *(_OWORD *)(a4 + 40);
  *(_OWORD *)(v9 + 120) = *(_OWORD *)(a4 + 56);
  *(_QWORD *)(a4 + 56) = 0;
  *(_QWORD *)(a4 + 64) = 7;
  *(_WORD *)(a4 + 40) = 0;
  *((_QWORD *)v9 + 17) = *(_QWORD *)(a4 + 72);
  *((_QWORD *)v9 + 18) = *(_QWORD *)(a4 + 80);
  *((_QWORD *)v9 + 19) = *(_QWORD *)(a4 + 88);
  *((_DWORD *)v9 + 40) = *(_DWORD *)(a4 + 96);
  *(_QWORD *)v9 = v8;
  *((_QWORD *)v9 + 1) = v8;
  *((_QWORD *)v9 + 2) = v8;
  *((_WORD *)v9 + 12) = 0;
  v11 = std::_Tree<std::_Tmap_traits<std::wstring,CachedAdapterInformation,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CachedAdapterInformation>>,0>>::_Find_lower_bound<std::wstring>(
          (__int64)a1,
          v24,
          (__int64)(v9 + 32));
  v12 = *(_OWORD *)v11;
  inserted = v11[2];
  if ( *(_BYTE *)(inserted + 25) )
    goto LABEL_11;
  v14 = (const wchar_t *)(inserted + 32);
  v15 = *(_QWORD *)(inserted + 48);
  if ( *(_QWORD *)(inserted + 56) > 7u )
    v14 = *(const wchar_t **)v14;
  v16 = *((_QWORD *)v9 + 6);
  if ( *((_QWORD *)v9 + 7) <= 7u )
    v17 = (const wchar_t *)(v9 + 32);
  else
    v17 = *v10;
  v18 = *((_QWORD *)v9 + 6);
  if ( v15 < v16 )
    v18 = *(_QWORD *)(inserted + 48);
  v19 = wmemcmp(v17, v14, v18);
  if ( v19 )
  {
    if ( v19 < 0 )
      goto LABEL_11;
  }
  else if ( v16 < v15 )
  {
LABEL_11:
    if ( a1[1] == 0x186186186186186LL )
      std::_Throw_tree_length_error();
    v23 = v12;
    inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CachedAdapterInformation>>>::_Insert_node(
                 a1,
                 &v23,
                 v9);
    v20 = 1;
    goto LABEL_13;
  }
  v20 = 0;
  std::wstring::~wstring(v9 + 104);
  v22 = (HKEY)*((_QWORD *)v9 + 8);
  if ( v22 )
    RegCloseKey(v22);
  std::wstring::~wstring(v10);
  operator delete(v9, 0xA8u);
LABEL_13:
  *(_QWORD *)a2 = inserted;
  *(_BYTE *)(a2 + 8) = v20;
  return a2;
}

```

## disassembly

```asm
0x140004d34  push    rbx
0x140004d36  push    rbp
0x140004d37  push    rsi
0x140004d38  push    rdi
0x140004d39  push    r12
0x140004d3b  push    r13
0x140004d3d  push    r14
0x140004d3f  push    r15
0x140004d41  sub     rsp, 68h
0x140004d45  movaps  [rsp+0A8h+var_58], xmm6
0x140004d4a  mov     rsi, r9
0x140004d4d  mov     rbx, r8
0x140004d50  mov     r15, rdx
0x140004d53  mov     r12, rcx
0x140004d56  mov     rdi, [rcx]
0x140004d59  mov     qword ptr [rsp+0A8h+var_88], rcx
0x140004d5e  mov     qword ptr [rsp+0A8h+var_88+8], 0
0x140004d67  mov     ecx, 0A8h; Size
0x140004d6c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140004d71  mov     rbp, rax
0x140004d74  mov     qword ptr [rsp+0A8h+var_88+8], rax
0x140004d79  lea     r14, [rax+20h]
0x140004d7d  mov     rdx, rbx
0x140004d80  mov     rcx, r14
0x140004d83  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140004d88  mov     rax, [rsi]
0x140004d8b  mov     [r14+20h], rax
0x140004d8f  xor     ebx, ebx
0x140004d91  mov     [rsi], rbx
0x140004d94  mov     rax, [rsi+8]
0x140004d98  mov     [r14+28h], rax
0x140004d9c  mov     rax, [rsi+10h]
0x140004da0  mov     [r14+30h], rax
0x140004da4  mov     rax, [rsi+18h]
0x140004da8  mov     [r14+38h], rax
0x140004dac  mov     eax, [rsi+20h]
0x140004daf  mov     [r14+40h], eax
0x140004db3  lea     r13, [r14+48h]
0x140004db7  xorps   xmm0, xmm0
0x140004dba  movups  xmmword ptr [r13+0], xmm0
0x140004dbf  mov     [r13+10h], rbx
0x140004dc3  mov     [r13+18h], rbx
0x140004dc7  movups  xmm0, xmmword ptr [rsi+28h]
0x140004dcb  movups  xmmword ptr [r13+0], xmm0
0x140004dd0  movups  xmm1, xmmword ptr [rsi+38h]
0x140004dd4  movups  xmmword ptr [r13+10h], xmm1
0x140004dd9  mov     [rsi+38h], rbx
0x140004ddd  mov     qword ptr [rsi+40h], 7
0x140004de5  mov     [rsi+28h], bx
0x140004de9  mov     rax, [rsi+48h]
0x140004ded  mov     [r14+68h], rax
0x140004df1  mov     rax, [rsi+50h]
0x140004df5  mov     [r14+70h], rax
0x140004df9  mov     rax, [rsi+58h]
0x140004dfd  mov     [r14+78h], rax
0x140004e01  mov     eax, [rsi+60h]
0x140004e04  mov     [r14+80h], eax
0x140004e0b  mov     [rbp+0], rdi
0x140004e0f  mov     [rbp+8], rdi
0x140004e13  mov     [rbp+10h], rdi
0x140004e17  mov     [rbp+18h], bx
0x140004e1b  mov     r8, r14
0x140004e1e  lea     rdx, [rsp+0A8h+var_78]
0x140004e23  mov     rcx, r12
0x140004e26  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CachedAdapterInformation,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,CachedAdapterInformation>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x140004e2b  movups  xmm6, xmmword ptr [rax]
0x140004e2e  mov     rsi, [rax+10h]
0x140004e32  cmp     [rsi+19h], bl
0x140004e35  jnz     short loc_140004E74
0x140004e37  lea     rdx, [rsi+20h]
0x140004e3b  mov     rdi, [rdx+10h]
0x140004e3f  cmp     qword ptr [rdx+18h], 7
0x140004e44  jbe     short loc_140004E49
0x140004e46  mov     rdx, [rdx]; S2
0x140004e49  mov     rbx, [r14+10h]
0x140004e4d  cmp     qword ptr [r14+18h], 7
0x140004e52  jbe     short loc_140004E59
0x140004e54  mov     rcx, [r14]
0x140004e57  jmp     short loc_140004E5C
0x140004e59  mov     rcx, r14; S1
0x140004e5c  mov     r8, rbx
0x140004e5f  cmp     rdi, rbx
0x140004e62  cmovb   r8, rdi; N
0x140004e66  call    wmemcmp
0x140004e6b  test    eax, eax
0x140004e6d  jnz     short loc_140004EC0
0x140004e6f  cmp     rbx, rdi
0x140004e72  jnb     short loc_140004EC2
0x140004e74  mov     rax, 186186186186186h
0x140004e7e  cmp     [r12+8], rax
0x140004e83  jz      short loc_140004EF2
0x140004e85  movdqu  [rsp+0A8h+var_88], xmm6
0x140004e8b  mov     r8, rbp
0x140004e8e  lea     rdx, [rsp+0A8h+var_88]
0x140004e93  mov     rcx, r12
0x140004e96  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CachedAdapterInformation>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,CachedAdapterInformation>,void *> *>,std::_Tree_node<std::pair<std::wstring const,CachedAdapterInformation>,void *> * const)
0x140004e9b  mov     rsi, rax
0x140004e9e  mov     bl, 1
0x140004ea0  mov     [r15], rsi
0x140004ea3  mov     [r15+8], bl
0x140004ea7  mov     rax, r15
0x140004eaa  movaps  xmm6, [rsp+0A8h+var_58]
0x140004eaf  add     rsp, 68h
0x140004eb3  pop     r15
0x140004eb5  pop     r14
0x140004eb7  pop     r13
0x140004eb9  pop     r12
0x140004ebb  pop     rdi
0x140004ebc  pop     rsi
0x140004ebd  pop     rbp
0x140004ebe  pop     rbx
0x140004ebf  retn
0x140004ec0  js      short loc_140004E74
0x140004ec2  xor     bl, bl
0x140004ec4  mov     rcx, r13
0x140004ec7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140004ecc  mov     rcx, [r14+20h]; hKey
0x140004ed0  test    rcx, rcx
0x140004ed3  jz      short loc_140004EDB
0x140004ed5  call    cs:__imp_RegCloseKey
0x140004edb  mov     rcx, r14
0x140004ede  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140004ee3  mov     edx, 0A8h; unsigned __int64
0x140004ee8  mov     rcx, rbp; void *
0x140004eeb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140004ef0  jmp     short loc_140004EA0
0x140004ef2  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
