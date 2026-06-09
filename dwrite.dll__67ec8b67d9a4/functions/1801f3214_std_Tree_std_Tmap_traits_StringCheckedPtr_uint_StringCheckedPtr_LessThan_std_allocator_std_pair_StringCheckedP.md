# std::_Tree<std::_Tmap_traits<StringCheckedPtr,uint,StringCheckedPtr::LessThan,std::allocator<std::pair<StringCheckedPtr const,uint>>,0>>::_Emplace<std::pair<StringCheckedPtr,uint>>(std::pair<StringCheckedPtr,uint> &&)

- ea: `0x1801f3214`
- end: `0x1801f33e1`
- name: `??$_Emplace@U?$pair@VStringCheckedPtr@@I@std@@@?$_Tree@V?$_Tmap_traits@VStringCheckedPtr@@IULessThan@1@V?$allocator@U?$pair@$$CBVStringCheckedPtr@@I@std@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVStringCheckedPtr@@I@std@@PEAX@std@@_N@1@$$QEAU?$pair@VStringCheckedPtr@@I@1@@Z`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180154830`

## callees

- `0x1801ee584`
- `0x1801ef914`
- `0x1801f3214`
- `0x1801f37b0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801f32e1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801f3328`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801f32e1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801f3328`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1801f32b2`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1801f32b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall std::_Tree<std::_Tmap_traits<StringCheckedPtr,unsigned int,StringCheckedPtr::LessThan,std::allocator<std::pair<StringCheckedPtr const,unsigned int>>,0>>::_Emplace<std::pair<StringCheckedPtr,unsigned int>>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 *v6; // rdi
  __int64 *v7; // r12
  unsigned int v8; // ebp
  __int64 *i; // rbx
  const WCHAR *lpString2; // rax
  const WCHAR *v11; // r8
  const WCHAR *v12; // rax
  unsigned int cchCount2; // ecx
  unsigned int v14; // r9d
  unsigned int v15; // edx
  unsigned int v16; // r9d
  __int64 *v17; // rbx
  __int64 v18; // rax
  __int64 *v20; // [rsp+30h] [rbp-38h] BYREF
  __int64 v21; // [rsp+38h] [rbp-30h]

  v6 = (__int64 *)*a1;
  v7 = *(__int64 **)(*a1 + 8);
  v8 = 0;
  for ( i = v7; !*((_BYTE *)i + 25); i = (__int64 *)*i )
  {
    v7 = i;
    lpString2 = *(const WCHAR **)a3;
    v11 = (const WCHAR *)i[4];
    if ( v11 )
    {
      if ( lpString2 )
      {
        cchCount2 = *(_DWORD *)(a3 + 8);
        if ( cchCount2 > 0x7FFFFFFF )
          goto LABEL_21;
        v14 = *((_DWORD *)i + 10);
        if ( v14 > 0x7FFFFFFF )
          goto LABEL_21;
        if ( CompareStringW(0x7Fu, 1u, v11, v14, lpString2, cchCount2) - 2 < 0 )
        {
LABEL_15:
          v8 = 0;
          i += 2;
          continue;
        }
      }
    }
    else if ( lpString2 )
    {
      goto LABEL_15;
    }
    v8 = 1;
    v6 = i;
  }
  if ( *((_BYTE *)v6 + 25) )
    goto LABEL_9;
  v12 = (const WCHAR *)v6[4];
  if ( *(_QWORD *)a3 )
  {
    if ( v12 )
    {
      v15 = *((_DWORD *)v6 + 10);
      if ( v15 > 0x7FFFFFFF || (v16 = *(_DWORD *)(a3 + 8), v16 > 0x7FFFFFFF) )
LABEL_21:
        SafeIntExceptionHandler<Exception>::SafeIntOnOverflow();
      if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)a3, v16, v12, v15) - 2 < 0 )
        goto LABEL_9;
    }
LABEL_20:
    *(_QWORD *)a2 = v6;
    *(_BYTE *)(a2 + 8) = 0;
    return a2;
  }
  if ( !v12 )
    goto LABEL_20;
LABEL_9:
  if ( a1[1] == 0x492492492492492LL )
    std::_Xlength_error("map/set too long");
  v17 = (__int64 *)*a1;
  v20 = a1;
  v18 = std::_Allocate<16,std::_Default_allocate_traits>(56);
  v21 = v18;
  *(_OWORD *)(v18 + 32) = *(_OWORD *)a3;
  *(_DWORD *)(v18 + 48) = *(_DWORD *)(a3 + 16);
  *(_QWORD *)v18 = v17;
  *(_QWORD *)(v18 + 8) = v17;
  *(_QWORD *)(v18 + 16) = v17;
  *(_WORD *)(v18 + 24) = 0;
  v20 = v7;
  v21 = v8;
  *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short const,DWriteCore::CacheHelpers::CoalescedRegionPtr<DWriteCore::CacheHelpers::ArrayRegion<DWriteCore::FontApi::NameDictionaryEntry>>>>>::_Insert_node(
                    a1,
                    &v20,
                    v18);
  *(_BYTE *)(a2 + 8) = 1;
  return a2;
}

```

## disassembly

```asm
0x1801f3214  mov     [rsp+arg_8], rbx
0x1801f3219  mov     [rsp+arg_10], rbp
0x1801f321e  push    rsi
0x1801f321f  push    rdi
0x1801f3220  push    r12
0x1801f3222  push    r14
0x1801f3224  push    r15
0x1801f3226  sub     rsp, 40h
0x1801f322a  mov     r14, r8
0x1801f322d  mov     rsi, rdx
0x1801f3230  mov     r15, rcx
0x1801f3233  mov     rdi, [rcx]
0x1801f3236  mov     r12, [rdi+8]
0x1801f323a  xor     ebp, ebp
0x1801f323c  xor     eax, eax
0x1801f323e  mov     [rsp+68h+arg_0], rax
0x1801f3243  mov     rbx, r12
0x1801f3246  mov     r10d, 7FFFFFFFh
0x1801f324c  cmp     [r12+19h], al
0x1801f3251  jnz     short loc_1801F327C
0x1801f3253  mov     r12, rbx
0x1801f3256  mov     rax, [r14]
0x1801f3259  mov     r8, [rbx+20h]; lpString1
0x1801f325d  test    r8, r8
0x1801f3260  jnz     short loc_1801F32B9
0x1801f3262  test    rax, rax
0x1801f3265  jnz     loc_1801F32F6
0x1801f326b  mov     ebp, 1
0x1801f3270  mov     rdi, rbx
0x1801f3273  mov     rbx, [rbx]
0x1801f3276  cmp     byte ptr [rbx+19h], 0
0x1801f327a  jz      short loc_1801F3253
0x1801f327c  cmp     byte ptr [rdi+19h], 0
0x1801f3280  jnz     short loc_1801F3297
0x1801f3282  mov     rax, [rdi+20h]
0x1801f3286  mov     r8, [r14]; lpString1
0x1801f3289  test    r8, r8
0x1801f328c  jnz     short loc_1801F3301
0x1801f328e  test    rax, rax
0x1801f3291  jz      loc_1801F3337
0x1801f3297  mov     rax, 492492492492492h
0x1801f32a1  cmp     [r15+8], rax
0x1801f32a5  jnz     loc_1801F3349
0x1801f32ab  lea     rcx, aMapSetTooLong; "map/set too long"
0x1801f32b2  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1801f32b9  test    rax, rax
0x1801f32bc  jz      short loc_1801F326B
0x1801f32be  mov     ecx, [r14+8]
0x1801f32c2  cmp     ecx, r10d
0x1801f32c5  ja      short loc_1801F3343
0x1801f32c7  mov     r9d, [rbx+28h]; cchCount1
0x1801f32cb  cmp     r9d, r10d
0x1801f32ce  ja      short loc_1801F3343
0x1801f32d0  mov     [rsp+68h+cchCount2], ecx; cchCount2
0x1801f32d4  mov     [rsp+68h+lpString2], rax; lpString2
0x1801f32d9  mov     edx, 1; dwCmpFlags
0x1801f32de  lea     ecx, [rdx+7Eh]; Locale
0x1801f32e1  call    cs:__imp_CompareStringW
0x1801f32e7  add     eax, 0FFFFFFFEh
0x1801f32ea  mov     r10d, 7FFFFFFFh
0x1801f32f0  jns     loc_1801F326B
0x1801f32f6  xor     ebp, ebp
0x1801f32f8  add     rbx, 10h
0x1801f32fc  jmp     loc_1801F3273
0x1801f3301  test    rax, rax
0x1801f3304  jz      short loc_1801F3337
0x1801f3306  mov     edx, [rdi+28h]
0x1801f3309  cmp     edx, r10d
0x1801f330c  ja      short loc_1801F3343
0x1801f330e  mov     r9d, [r14+8]; cchCount1
0x1801f3312  cmp     r9d, r10d
0x1801f3315  ja      short loc_1801F3343
0x1801f3317  mov     [rsp+68h+cchCount2], edx; cchCount2
0x1801f331b  mov     [rsp+68h+lpString2], rax; lpString2
0x1801f3320  mov     edx, 1; dwCmpFlags
0x1801f3325  lea     ecx, [rdx+7Eh]; Locale
0x1801f3328  call    cs:__imp_CompareStringW
0x1801f332e  add     eax, 0FFFFFFFEh
0x1801f3331  js      loc_1801F3297
0x1801f3337  mov     [rsi], rdi
0x1801f333a  mov     byte ptr [rsi+8], 0
0x1801f333e  jmp     loc_1801F33C5
0x1801f3343  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
0x1801f3349  mov     rbx, [r15]
0x1801f334c  mov     [rsp+68h+var_38], r15
0x1801f3351  mov     [rsp+68h+var_30], 0
0x1801f335a  mov     [rsp+68h+var_30], 0
0x1801f3363  mov     ecx, 38h ; '8'
0x1801f3368  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1801f336d  mov     [rsp+68h+var_30], rax
0x1801f3372  movups  xmm0, xmmword ptr [r14]
0x1801f3376  movdqu  xmmword ptr [rax+20h], xmm0
0x1801f337b  mov     ecx, [r14+10h]
0x1801f337f  mov     [rax+30h], ecx
0x1801f3382  mov     [rax], rbx
0x1801f3385  mov     [rax+8], rbx
0x1801f3389  mov     [rax+10h], rbx
0x1801f338d  mov     word ptr [rax+18h], 0
0x1801f3393  mov     [rsp+68h+var_30], 0
0x1801f339c  mov     [rsp+68h+var_38], r12
0x1801f33a1  mov     dword ptr [rsp+68h+var_30], ebp
0x1801f33a5  mov     rcx, [rsp+68h+arg_0]
0x1801f33aa  mov     dword ptr [rsp+68h+var_30+4], ecx
0x1801f33ae  mov     r8, rax
0x1801f33b1  lea     rdx, [rsp+68h+var_38]
0x1801f33b6  mov     rcx, r15
0x1801f33b9  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBGV?$CoalescedRegionPtr@V?$ArrayRegion@UNameDictionaryEntry@FontApi@DWriteCore@@@CacheHelpers@DWriteCore@@@CacheHelpers@DWriteCore@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBGV?$CoalescedRegionPtr@V?$ArrayRegion@UNameDictionaryEntry@FontApi@DWriteCore@@@CacheHelpers@DWriteCore@@@CacheHelpers@DWriteCore@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBGV?$CoalescedRegionPtr@V?$ArrayRegion@UNameDictionaryEntry@FontApi@DWriteCore@@@CacheHelpers@DWriteCore@@@CacheHelpers@DWriteCore@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ushort const,DWriteCore::CacheHelpers::CoalescedRegionPtr<DWriteCore::CacheHelpers::ArrayRegion<DWriteCore::FontApi::NameDictionaryEntry>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<ushort const,DWriteCore::CacheHelpers::CoalescedRegionPtr<DWriteCore::CacheHelpers::ArrayRegion<DWriteCore::FontApi::NameDictionaryEntry>>>,void *> *>,std::_Tree_node<std::pair<ushort const,DWriteCore::CacheHelpers::CoalescedRegionPtr<DWriteCore::CacheHelpers::ArrayRegion<DWriteCore::FontApi::NameDictionaryEntry>>>,void *> * const)
0x1801f33be  mov     [rsi], rax
0x1801f33c1  mov     byte ptr [rsi+8], 1
0x1801f33c5  mov     rax, rsi
0x1801f33c8  lea     r11, [rsp+68h+var_28]
0x1801f33cd  mov     rbx, [r11+38h]
0x1801f33d1  mov     rbp, [r11+40h]
0x1801f33d5  mov     rsp, r11
0x1801f33d8  pop     r15
0x1801f33da  pop     r14
0x1801f33dc  pop     r12
0x1801f33de  pop     rdi
0x1801f33df  pop     rsi
0x1801f33e0  retn
```
