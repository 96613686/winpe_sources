# CFilteringPlatformHelperClass::GetAttributeInfo(ulong *,tagHelperAttributeInfo * *)

- ea: `0x1800066c0`
- end: `0x1800067db`
- name: `?GetAttributeInfo@CFilteringPlatformHelperClass@@UEAAJPEAKPEAPEAUtagHelperAttributeInfo@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(CFilteringPlatformHelperClass *__hidden this, unsigned int *, struct tagHelperAttributeInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800066c0`
- `0x180008ac0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800067ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800067bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800067ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800067bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006730`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006730`

## pseudocode

```c
__int64 __fastcall CFilteringPlatformHelperClass::GetAttributeInfo(
        CFilteringPlatformHelperClass *this,
        unsigned int *a2,
        struct tagHelperAttributeInfo **a3)
{
  unsigned int v3; // esi
  const struct tagHelperAttributeInfo *v6; // r15
  const struct tagHelperAttributeInfo *v7; // rax
  unsigned int i; // edi
  int v9; // ebx
  SIZE_T v10; // rbx
  struct tagHelperAttributeInfo *v11; // rax
  struct tagHelperAttributeInfo *v12; // rbp
  struct tagHelperAttributeInfo *j; // r13
  unsigned int k; // edi
  LPWSTR pwszName; // rcx

  v3 = 0;
  if ( !a2 || !a3 )
    return (unsigned int)-2147024809;
  v6 = &CFilteringPlatformHelperClass::m_attrInfos;
  v7 = &CFilteringPlatformHelperClass::m_attrInfos;
  for ( i = 0; v7->pwszName; ++v7 )
    ++i;
  *a2 = 0;
  *a3 = 0;
  if ( !i )
    return 0;
  if ( i > 0x104 )
    return (unsigned int)-2147024809;
  v10 = 16LL * i;
  v11 = (struct tagHelperAttributeInfo *)CoTaskMemAlloc(v10);
  v12 = v11;
  if ( v11 )
  {
    for ( j = v11; v10; --v10 )
    {
      LOBYTE(v11->pwszName) = 0;
      v11 = (struct tagHelperAttributeInfo *)((char *)v11 + 1);
    }
    while ( 1 )
    {
      v9 = StringCchCopyWithAlloc(&j->pwszName, 0xFFFFu, v6->pwszName);
      if ( v9 < 0 )
        break;
      ++v3;
      j->type = v6->type;
      ++v6;
      ++j;
      if ( v3 >= i )
      {
        *a2 = i;
        v9 = 0;
        *a3 = v12;
        return (unsigned int)v9;
      }
    }
    if ( v3 )
    {
      for ( k = 0; k < v3; ++k )
      {
        pwszName = v12[k].pwszName;
        if ( pwszName )
          CoTaskMemFree(pwszName);
      }
    }
    CoTaskMemFree(v12);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800066c0  push    rbx
0x1800066c2  push    rbp
0x1800066c3  push    rsi
0x1800066c4  push    rdi
0x1800066c5  push    r12
0x1800066c7  push    r13
0x1800066c9  push    r14
0x1800066cb  push    r15
0x1800066cd  sub     rsp, 28h
0x1800066d1  xor     esi, esi
0x1800066d3  mov     r14, r8
0x1800066d6  mov     r12, rdx
0x1800066d9  test    rdx, rdx
0x1800066dc  jz      loc_1800067C3
0x1800066e2  test    r8, r8
0x1800066e5  jz      loc_1800067C3
0x1800066eb  cmp     cs:?m_attrInfos@CFilteringPlatformHelperClass@@0QBUtagHelperAttributeInfo@@B.pwszName, rsi; tagHelperAttributeInfo const near * const CFilteringPlatformHelperClass::m_attrInfos ...
0x1800066f2  lea     r15, ?m_attrInfos@CFilteringPlatformHelperClass@@0QBUtagHelperAttributeInfo@@B; tagHelperAttributeInfo const near * const CFilteringPlatformHelperClass::m_attrInfos
0x1800066f9  mov     rax, r15
0x1800066fc  mov     edi, esi
0x1800066fe  jz      short loc_18000670B
0x180006700  inc     edi
0x180006702  lea     rax, [rax+10h]
0x180006706  cmp     [rax], rsi
0x180006709  jnz     short loc_180006700
0x18000670b  mov     [rdx], esi
0x18000670d  mov     [r8], rsi
0x180006710  test    edi, edi
0x180006712  jnz     short loc_18000671B
0x180006714  mov     ebx, esi
0x180006716  jmp     loc_1800067C8
0x18000671b  cmp     edi, 104h
0x180006721  ja      loc_1800067C3
0x180006727  mov     ebx, edi
0x180006729  shl     rbx, 4
0x18000672d  mov     rcx, rbx; cb
0x180006730  call    cs:__imp_CoTaskMemAlloc
0x180006736  mov     rbp, rax
0x180006739  test    rax, rax
0x18000673c  jnz     short loc_180006748
0x18000673e  mov     ebx, 8007000Eh
0x180006743  jmp     loc_1800067C8
0x180006748  mov     r13, rbp
0x18000674b  test    rbx, rbx
0x18000674e  jz      short loc_18000675C
0x180006750  mov     [rax], sil
0x180006753  inc     rax
0x180006756  sub     rbx, 1
0x18000675a  jnz     short loc_180006750
0x18000675c  test    edi, edi
0x18000675e  jz      short loc_18000678C
0x180006760  mov     r8, [r15]; unsigned __int16 *
0x180006763  mov     edx, 0FFFFh; unsigned __int64
0x180006768  mov     rcx, r13; unsigned __int16 **
0x18000676b  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x180006770  mov     ebx, eax
0x180006772  test    eax, eax
0x180006774  js      short loc_180006797
0x180006776  mov     eax, [r15+8]
0x18000677a  inc     esi
0x18000677c  mov     [r13+8], eax
0x180006780  add     r15, 10h
0x180006784  add     r13, 10h
0x180006788  cmp     esi, edi
0x18000678a  jb      short loc_180006760
0x18000678c  mov     [r12], edi
0x180006790  xor     ebx, ebx
0x180006792  mov     [r14], rbp
0x180006795  jmp     short loc_1800067C8
0x180006797  test    esi, esi
0x180006799  jz      short loc_1800067B8
0x18000679b  xor     edi, edi
0x18000679d  mov     eax, edi
0x18000679f  add     rax, rax
0x1800067a2  mov     rcx, [rbp+rax*8+0]; pv
0x1800067a7  test    rcx, rcx
0x1800067aa  jz      short loc_1800067B2
0x1800067ac  call    cs:__imp_CoTaskMemFree
0x1800067b2  inc     edi
0x1800067b4  cmp     edi, esi
0x1800067b6  jb      short loc_18000679D
0x1800067b8  mov     rcx, rbp; pv
0x1800067bb  call    cs:__imp_CoTaskMemFree
0x1800067c1  jmp     short loc_1800067C8
0x1800067c3  mov     ebx, 80070057h
0x1800067c8  mov     eax, ebx
0x1800067ca  add     rsp, 28h
0x1800067ce  pop     r15
0x1800067d0  pop     r14
0x1800067d2  pop     r13
0x1800067d4  pop     r12
0x1800067d6  pop     rdi
0x1800067d7  pop     rsi
0x1800067d8  pop     rbp
0x1800067d9  pop     rbx
0x1800067da  retn
```
