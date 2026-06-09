# CNetDiagClient::FindCatchAllRootCauseReplacement(tagRootCauseInfo &,_GUID &)

- ea: `0x180019964`
- end: `0x180019af2`
- name: `?FindCatchAllRootCauseReplacement@CNetDiagClient@@IEAAJAEAUtagRootCauseInfo@@AEAU_GUID@@@Z`
- size: `398`
- prototype: `__int64 __fastcall(CNetDiagClient *__hidden this, struct tagRootCauseInfo *, struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x180018ed4`

## callees

- `0x180019964`
- `0x18001b0f8`
- `0x18001b378`
- `0x18001f690`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180019a8e`
- `msvcrt!??3@YAXPEAX@Z` at `0x180019a8e`

## pseudocode

```c
__int64 __fastcall CNetDiagClient::FindCatchAllRootCauseReplacement(
        CNetDiagClient *this,
        struct tagRootCauseInfo *a2,
        struct _GUID *a3)
{
  CNetDiagClient *v4; // r8
  unsigned int v5; // esi
  unsigned int v6; // ebx
  LPWSTR pwszClassName; // rdx
  struct _GUID **v8; // r14
  struct _GUID *v9; // rdi
  struct _GUID *v10; // rcx
  unsigned __int64 v11; // r11
  unsigned __int64 v12; // rax
  _WORD *v13; // rdx
  void *v14; // r12
  unsigned __int64 v15; // r15
  int v16; // eax
  struct _GUID *v18; // [rsp+20h] [rbp-78h] BYREF
  struct _GUID *v19; // [rsp+28h] [rbp-70h]
  CNetDiagClient *v20; // [rsp+30h] [rbp-68h]
  _QWORD v21[2]; // [rsp+38h] [rbp-60h] BYREF
  unsigned __int64 v22; // [rsp+48h] [rbp-50h]
  unsigned __int64 v23; // [rsp+50h] [rbp-48h]

  v19 = a3;
  v4 = this;
  v20 = this;
  v5 = 0;
  v6 = 1;
  while ( v5 < a2->repairCount )
  {
    pwszClassName = a2->pRepairs[v5].repair.pwszClassName;
    if ( !pwszClassName )
      goto LABEL_31;
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v8 = (struct _GUID **)((char *)v4 + 64);
      v23 = 7;
      v22 = 0;
      LOWORD(v21[0]) = 0;
      std::wstring::assign(v21, pwszClassName);
      std::_Tree<std::_Tmap_traits<std::wstring,_GUID,WstringLessThan,std::allocator<std::pair<std::wstring const,_GUID>>,0>>::lower_bound(
        v8,
        &v18,
        v21);
      v9 = v18;
      if ( v18 == *v8 )
      {
        v15 = v23;
        v14 = (void *)v21[0];
      }
      else
      {
        if ( *(_QWORD *)v18[3].Data4 < 8u )
          v10 = v18 + 2;
        else
          v10 = *(struct _GUID **)&v18[2].Data1;
        v11 = *(_QWORD *)&v18[3].Data1;
        v12 = v22;
        if ( v22 >= v11 )
          v12 = *(_QWORD *)&v18[3].Data1;
        v13 = v21;
        v14 = (void *)v21[0];
        v15 = v23;
        if ( v23 >= 8 )
          v13 = (_WORD *)v21[0];
        if ( v12 )
        {
          while ( *v13 == LOWORD(v10->Data1) )
          {
            ++v13;
            v10 = (struct _GUID *)((char *)v10 + 2);
            if ( !--v12 )
              goto LABEL_16;
          }
          v16 = *v13 < LOWORD(v10->Data1) ? -1 : 1;
        }
        else
        {
LABEL_16:
          if ( v22 >= v11 )
            v16 = v22 != v11;
          else
            v16 = -1;
        }
        if ( v16 >= 0 )
          goto LABEL_24;
      }
      v9 = *v8;
LABEL_24:
      if ( v15 >= 8 )
        operator delete(v14);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        LODWORD(v18) = -2147024882;
        v6 = (unsigned int)v18;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180019AE0);
        return v6;
      }
      if ( __eh34_catch_type(0, &exception `RTTI Type Descriptor', 0) )
      {
        LODWORD(v18) = -2147467259;
        v6 = (unsigned int)v18;
        __eh34_try_continuation(0, &exception `RTTI Type Descriptor', &loc_180019AE0);
        return v6;
      }
    }
    v23 = 7;
    v22 = 0;
    LOWORD(v21[0]) = 0;
    if ( v9 != *v8 )
    {
      v6 = 0;
      *v19 = v9[4];
      return v6;
    }
    v4 = v20;
LABEL_31:
    ++v5;
  }
  return v6;
}

```

## disassembly

```asm
0x180019964  push    rbx
0x180019966  push    rsi
0x180019967  push    rdi
0x180019968  push    r12
0x18001996a  push    r13
0x18001996c  push    r14
0x18001996e  push    r15
0x180019970  sub     rsp, 60h
0x180019974  mov     rax, cs:__security_cookie
0x18001997b  xor     rax, rsp
0x18001997e  mov     [rsp+98h+var_40], rax
0x180019983  mov     [rsp+98h+var_70], r8
0x180019988  mov     r13, rdx
0x18001998b  mov     r8, rcx
0x18001998e  mov     [rsp+98h+var_68], rcx
0x180019993  xor     esi, esi
0x180019995  lea     ebx, [rsi+1]
0x180019998  movzx   eax, word ptr [r13+38h]
0x18001999d  cmp     esi, eax
0x18001999f  jnb     loc_180019AC1
0x1800199a5  mov     eax, esi
0x1800199a7  imul    rcx, rax, 78h ; 'x'
0x1800199ab  mov     rax, [r13+30h]
0x1800199af  mov     rdx, [rcx+rax+10h]; Src
0x1800199b4  test    rdx, rdx
0x1800199b7  jz      loc_180019AEB
0x1800199bd  lea     r14, [r8+40h]
0x1800199c1  mov     [rsp+98h+var_48], 7
0x1800199ca  mov     [rsp+98h+var_50], 0
0x1800199d3  xor     eax, eax
0x1800199d5  mov     word ptr [rsp+98h+var_60], ax
0x1800199da  lea     rcx, [rsp+98h+var_60]; void *
0x1800199df  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800199e4  lea     r8, [rsp+98h+var_60]
0x1800199e9  lea     rdx, [rsp+98h+var_78]
0x1800199ee  mov     rcx, r14
0x1800199f1  call    ?lower_bound@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@UWstringLessThan@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,_GUID,WstringLessThan,std::allocator<std::pair<std::wstring const,_GUID>>,0>>::lower_bound(std::wstring const &)
0x1800199f6  mov     rdi, [rsp+98h+var_78]
0x1800199fb  cmp     rdi, [r14]
0x1800199fe  jz      short loc_180019A78
0x180019a00  cmp     qword ptr [rdi+38h], 8
0x180019a05  jb      short loc_180019A0D
0x180019a07  mov     rcx, [rdi+20h]
0x180019a0b  jmp     short loc_180019A11
0x180019a0d  lea     rcx, [rdi+20h]
0x180019a11  mov     r11, [rdi+30h]
0x180019a15  mov     r10, [rsp+98h+var_50]
0x180019a1a  mov     rax, r10
0x180019a1d  cmp     r10, r11
0x180019a20  cmovnb  rax, r11
0x180019a24  lea     rdx, [rsp+98h+var_60]
0x180019a29  mov     r12, [rsp+98h+var_60]
0x180019a2e  mov     r15, [rsp+98h+var_48]
0x180019a33  cmp     r15, 8
0x180019a37  cmovnb  rdx, r12
0x180019a3b  test    rax, rax
0x180019a3e  jz      short loc_180019A57
0x180019a40  movzx   r8d, word ptr [rdx]
0x180019a44  cmp     r8w, [rcx]
0x180019a48  jnz     short loc_180019A61
0x180019a4a  add     rdx, 2
0x180019a4e  add     rcx, 2
0x180019a52  sub     rax, rbx
0x180019a55  jnz     short loc_180019A40
0x180019a57  cmp     r10, r11
0x180019a5a  jnb     short loc_180019A6A
0x180019a5c  or      eax, 0FFFFFFFFh
0x180019a5f  jmp     short loc_180019A72
0x180019a61  sbb     eax, eax
0x180019a63  and     eax, 0FFFFFFFEh
0x180019a66  add     eax, ebx
0x180019a68  jmp     short loc_180019A72
0x180019a6a  xor     eax, eax
0x180019a6c  cmp     r10, r11
0x180019a6f  setnz   al
0x180019a72  test    eax, eax
0x180019a74  js      short loc_180019A82
0x180019a76  jmp     short loc_180019A85
0x180019a78  mov     r15, [rsp+98h+var_48]
0x180019a7d  mov     r12, [rsp+98h+var_60]
0x180019a82  mov     rdi, [r14]
0x180019a85  cmp     r15, 8
0x180019a89  jb      short loc_180019A94
0x180019a8b  mov     rcx, r12
0x180019a8e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180019a94  mov     [rsp+98h+var_48], 7
0x180019a9d  mov     [rsp+98h+var_50], 0
0x180019aa6  xor     eax, eax
0x180019aa8  mov     word ptr [rsp+98h+var_60], ax
0x180019aad  cmp     rdi, [r14]
0x180019ab0  jz      short loc_180019AE6
0x180019ab2  xor     ebx, ebx
0x180019ab4  movups  xmm0, xmmword ptr [rdi+40h]
0x180019ab8  mov     rax, [rsp+98h+var_70]
0x180019abd  movdqu  xmmword ptr [rax], xmm0
0x180019ac1  mov     eax, ebx
0x180019ac3  mov     rcx, [rsp+98h+var_40]
0x180019ac8  xor     rcx, rsp; StackCookie
0x180019acb  call    __security_check_cookie
0x180019ad0  add     rsp, 60h
0x180019ad4  pop     r15
0x180019ad6  pop     r14
0x180019ad8  pop     r13
0x180019ada  pop     r12
0x180019adc  pop     rdi
0x180019add  pop     rsi
0x180019ade  pop     rbx
0x180019adf  retn
0x180019ae0  mov     ebx, dword ptr [rsp+98h+var_78]
0x180019ae4  jmp     short loc_180019AC1
0x180019ae6  mov     r8, [rsp+98h+var_68]
0x180019aeb  add     esi, ebx
0x180019aed  jmp     loc_180019998
```
