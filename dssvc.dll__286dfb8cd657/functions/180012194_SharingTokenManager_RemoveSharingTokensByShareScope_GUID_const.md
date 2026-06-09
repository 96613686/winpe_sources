# SharingTokenManager::RemoveSharingTokensByShareScope(_GUID const &)

- ea: `0x180012194`
- end: `0x18001226b`
- name: `?RemoveSharingTokensByShareScope@SharingTokenManager@@QEAAJAEBU_GUID@@@Z`
- size: `215`
- prototype: `__int64 __fastcall(SharingTokenManager *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1800134f4`

## callees

- `0x18000c758`
- `0x18000f254`
- `0x18000fe20`
- `0x1800120ac`
- `0x180012194`
- `0x180012310`
- `0x180017518`

## pseudocode

```c
__int64 __fastcall SharingTokenManager::RemoveSharingTokensByShareScope(
        SharingTokenManager *this,
        const struct _GUID *a2)
{
  __int64 v4; // rdx
  unsigned int v5; // edi
  int TokensByShareScope; // eax
  __int64 v8; // r9
  _QWORD *v9; // rbx
  _QWORD **v10; // rcx
  _QWORD *i; // r8
  __int64 v12; // rdx
  __int64 v13; // rax
  struct SharingToken *v14; // rdx
  int v15; // eax
  _QWORD v16[9]; // [rsp+20h] [rbp-48h] BYREF
  char v17; // [rsp+70h] [rbp+8h] BYREF

  utl::list<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::list<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>(v16);
  if ( *(_DWORD *)this )
  {
    TokensByShareScope = SharingTokenDatabase::GetTokensByShareScope(
                           (SharingTokenManager *)((char *)this + 8),
                           v4,
                           (__int64)v16);
    v5 = TokensByShareScope;
    if ( TokensByShareScope >= 0 || TokensByShareScope == -1055719418 )
    {
      v9 = (_QWORD *)v16[0];
      if ( (_QWORD *)v16[0] != v16 )
      {
        while ( v9 != v16 )
        {
          v10 = (_QWORD **)(v9[2] + 128LL);
          for ( i = *v10; i != v10; i = (_QWORD *)*i )
          {
            v12 = i[2];
            v13 = *(_QWORD *)(v12 + 44) - *(_QWORD *)&a2->Data1;
            if ( !v13 )
              v13 = *(_QWORD *)(v12 + 52) - *(_QWORD *)a2->Data4;
            if ( !v13 )
            {
              utl::list<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::erase(
                v10,
                &v17);
              break;
            }
          }
          v14 = (struct SharingToken *)v9[2];
          v15 = *((struct SharingToken **)v14 + 16) == (struct SharingToken *)((char *)v14 + 128)
              ? SharingTokenManager::RemoveSharingToken(this, v14, 0, v8)
              : SharingTokenManager::UpdateSharingToken(this, v14, (__int64)i, v8);
          v5 = v15;
          if ( v15 < 0 )
            break;
          v9 = (_QWORD *)*v9;
        }
      }
    }
  }
  else
  {
    v5 = -1055719422;
  }
  utl::list<tlx::smart_ptr<SharingToken,&void tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingToken,&void tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>>>::clear((__int64)v16);
  return v5;
}

```

## disassembly

```asm
0x180012194  push    rbx
0x180012196  push    rbp
0x180012197  push    rsi
0x180012198  push    rdi
0x180012199  sub     rsp, 48h
0x18001219d  mov     rsi, rcx
0x1800121a0  mov     rbp, rdx
0x1800121a3  lea     rcx, [rsp+68h+var_48]
0x1800121a8  call    ??0?$list@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAA@XZ; utl::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>(void)
0x1800121ad  cmp     dword ptr [rsi], 0
0x1800121b0  jnz     short loc_1800121CC
0x1800121b2  mov     edi, 0C1130002h
0x1800121b7  lea     rcx, [rsp+68h+var_48]
0x1800121bc  call    ?clear@?$list@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAAXXZ; utl::list<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>>>::clear(void)
0x1800121c1  mov     eax, edi
0x1800121c3  add     rsp, 48h
0x1800121c7  pop     rdi
0x1800121c8  pop     rsi
0x1800121c9  pop     rbp
0x1800121ca  pop     rbx
0x1800121cb  retn
0x1800121cc  lea     rcx, [rsi+8]; this
0x1800121d0  lea     r8, [rsp+68h+var_48]
0x1800121d5  call    ?GetTokensByShareScope@SharingTokenDatabase@@QEAAJAEBU_GUID@@AEAV?$list@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@@Z; SharingTokenDatabase::GetTokensByShareScope(_GUID const &,utl::list<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>>> &)
0x1800121da  mov     edi, eax
0x1800121dc  test    eax, eax
0x1800121de  jns     short loc_1800121E7
0x1800121e0  cmp     eax, 0C1130006h
0x1800121e5  jnz     short loc_1800121B7
0x1800121e7  mov     rbx, [rsp+68h+var_48]
0x1800121ec  lea     rax, [rsp+68h+var_48]
0x1800121f1  cmp     rbx, rax
0x1800121f4  jz      short loc_1800121B7
0x1800121f6  lea     rax, [rsp+68h+var_48]
0x1800121fb  cmp     rbx, rax
0x1800121fe  jz      short loc_1800121B7
0x180012200  mov     rcx, [rbx+10h]
0x180012204  sub     rcx, 0FFFFFFFFFFFFFF80h
0x180012208  mov     r8, [rcx]
0x18001220b  cmp     r8, rcx
0x18001220e  jz      short loc_18001223A
0x180012210  mov     rdx, [r8+10h]
0x180012214  mov     rax, [rdx+2Ch]
0x180012218  sub     rax, [rbp+0]
0x18001221c  jnz     short loc_180012226
0x18001221e  mov     rax, [rdx+34h]
0x180012222  sub     rax, [rbp+8]
0x180012226  test    rax, rax
0x180012229  jz      short loc_180012230
0x18001222b  mov     r8, [r8]
0x18001222e  jmp     short loc_18001220B
0x180012230  lea     rdx, [rsp+68h+arg_0]
0x180012235  call    ?erase@?$list@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAA?AV?$_DlistIt@U?$_DlistNode@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@2@V?$_DlistConstIt@U?$_DlistNode@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@2@@Z; utl::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::erase(utl::_DlistConstIt<utl::_DlistNode<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>,tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>)
0x18001223a  mov     rdx, [rbx+10h]; struct SharingToken *
0x18001223e  mov     rcx, rsi; this
0x180012241  lea     rax, [rdx+80h]
0x180012248  cmp     [rax], rax
0x18001224b  jnz     short loc_180012257
0x18001224d  xor     r8d, r8d; int
0x180012250  call    ?RemoveSharingToken@SharingTokenManager@@QEAAJPEAVSharingToken@@H@Z; SharingTokenManager::RemoveSharingToken(SharingToken *,int)
0x180012255  jmp     short loc_18001225C
0x180012257  call    ?UpdateSharingToken@SharingTokenManager@@QEAAJPEAVSharingToken@@@Z; SharingTokenManager::UpdateSharingToken(SharingToken *)
0x18001225c  mov     edi, eax
0x18001225e  test    eax, eax
0x180012260  js      loc_1800121B7
0x180012266  mov     rbx, [rbx]
0x180012269  jmp     short loc_1800121F6
```
