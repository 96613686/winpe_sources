# WebCall::SendRequest(std::unique_ptr<WebRequest,std::default_delete<WebRequest>> const &,std::unique_ptr<WebCallResponse,std::default_delete<WebCallResponse>> const &)

- ea: `0x1400249f0`
- end: `0x140024c8b`
- name: `?SendRequest@WebCall@@QEAAXAEBV?$unique_ptr@VWebRequest@@U?$default_delete@VWebRequest@@@std@@@std@@AEBV?$unique_ptr@VWebCallResponse@@U?$default_delete@VWebCallResponse@@@std@@@3@@Z`
- size: `667`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops`

## callers

- `0x140010378`

## callees

- `0x1400028ac`
- `0x140005458`
- `0x1400054e8`
- `0x14000579c`
- `0x140005c80`
- `0x1400061dc`
- `0x140007bf8`
- `0x14000e000`
- `0x14000f978`
- `0x1400224fc`
- `0x14002266c`
- `0x140022b14`
- `0x140022bd8`
- `0x140023110`
- `0x1400249f0`
- `0x14002c3e8`
- `0x140030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WebCall::SendRequest(__int64 a1, __int64 *a2, __int64 **a3)
{
  __int64 v6; // rbx
  __int64 *v7; // rdx
  _QWORD *v8; // rdx
  _QWORD *v9; // rdx
  struct WebRequest *v10; // rbx
  _QWORD *v11; // rdx
  __int64 *ResponseHeaders; // rax
  __int64 v13; // r14
  __int64 v14; // rcx
  void **v15; // rbx
  void **v16; // rbx
  _QWORD *v17; // rax
  _QWORD *v18; // rdi
  __int64 v19; // rdx
  __int64 *v20; // rcx
  __int64 v21; // rax
  _BYTE pExceptionObject[16]; // [rsp+30h] [rbp-10h] BYREF
  void *Block; // [rsp+70h] [rbp+30h] BYREF
  __int64 v25; // [rsp+78h] [rbp+38h] BYREF

  v6 = *a2;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v25,
    *(_QWORD *)(a1 + 8));
  switch ( *(_DWORD *)a1 )
  {
    case 0:
      v7 = &WebRequest::MethodGet;
      goto LABEL_12;
    case 1:
      v7 = &WebRequest::MethodPost;
      goto LABEL_12;
    case 2:
      v7 = &WebRequest::MethodPut;
      goto LABEL_12;
    case 3:
      v7 = &WebRequest::MethodDelete;
LABEL_12:
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &Block,
        v7);
      goto LABEL_13;
  }
  Block = (void *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
          &Block,
          (__int64)&dword_14003353C) )
    ATL::CSimpleStringT<unsigned short,0>::SetString(&Block, &dword_14003353C, 0);
LABEL_13:
  WebRequest::Open(v6, &Block, &v25, (_QWORD *)(a1 + 32));
  v8 = (char *)Block - 24;
  if ( _InterlockedDecrement((volatile signed __int32 *)Block - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 8LL))(*v8);
  v9 = (_QWORD *)(v25 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v25 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 8LL))(*v9);
  if ( *(_QWORD *)(a1 + 24) )
    WebRequest::SetAdditionalRequestHeaders(*a2, (_QWORD ***)(a1 + 24));
  v10 = (struct WebRequest *)*a2;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &Block,
    *(_QWORD *)(a1 + 16));
  WebRequest::Send(v10);
  v11 = (char *)Block - 24;
  if ( _InterlockedDecrement((volatile signed __int32 *)Block - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 8LL))(*v11);
  if ( *(_WORD *)(*a2 + 88) != 4 )
  {
    InvalidCallException::InvalidCallException((InvalidCallException *)pExceptionObject, -895418365);
    throw (InvalidCallException *)pExceptionObject;
  }
  ResponseHeaders = WebRequest::GetResponseHeaders(*a2, &Block);
  v13 = a1 + 40;
  v14 = *ResponseHeaders;
  *ResponseHeaders = 0;
  v15 = *(void ***)(a1 + 40);
  *(_QWORD *)(a1 + 40) = v14;
  if ( v15 )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,void *>>>(
      (__int64)v15,
      (__int64)v15,
      *((__int64 **)*v15 + 1));
    operator delete(*v15);
    operator delete(v15);
  }
  v16 = (void **)Block;
  if ( Block )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,void *>>>(
      (__int64)Block,
      (__int64)Block,
      *(__int64 **)(*(_QWORD *)Block + 8LL));
    operator delete(*v16);
    operator delete(v16);
  }
  v17 = (_QWORD *)WebRequest::ResponseText(*a2, &Block);
  v18 = (_QWORD *)(a1 + 48);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(v18, v17);
  CSecureString::~CSecureString((CSecureString *)&Block);
  v19 = *(unsigned __int16 *)(*a2 + 92);
  v20 = *a3;
  v21 = **a3;
  if ( (_WORD)v19 == 200 )
    return (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD *))(v21 + 8))(v20, v13, v18);
  else
    return (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, _QWORD *))(v21 + 16))(v20, v19, v13, v18);
}

```

## disassembly

```asm
0x1400249f0  mov     [rsp-28h+arg_10], rbx
0x1400249f5  push    rbp
0x1400249f6  push    rsi
0x1400249f7  push    rdi
0x1400249f8  push    r14
0x1400249fa  push    r15
0x1400249fc  mov     rbp, rsp
0x1400249ff  sub     rsp, 40h
0x140024a03  mov     r15, r8
0x140024a06  mov     rsi, rdx
0x140024a09  mov     rdi, rcx
0x140024a0c  mov     rbx, [rdx]
0x140024a0f  mov     rdx, [rcx+8]
0x140024a13  lea     rcx, [rbp+arg_8]
0x140024a17  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140024a1c  nop
0x140024a1d  mov     r9d, [rdi]
0x140024a20  test    r9d, r9d
0x140024a23  jz      short loc_140024A9B
0x140024a25  sub     r9d, 1
0x140024a29  jz      short loc_140024A92
0x140024a2b  sub     r9d, 1
0x140024a2f  jz      short loc_140024A89
0x140024a31  cmp     r9d, 1
0x140024a35  jz      short loc_140024A80
0x140024a37  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140024a3e  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140024a45  mov     rax, [rax+18h]
0x140024a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024a4e  add     rax, 18h
0x140024a52  mov     [rbp+Block], rax
0x140024a56  lea     rdx, dword_14003353C
0x140024a5d  lea     rcx, [rbp+Block]
0x140024a61  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x140024a66  test    al, al
0x140024a68  jnz     short loc_140024A7E
0x140024a6a  xor     r8d, r8d
0x140024a6d  lea     rdx, dword_14003353C
0x140024a74  lea     rcx, [rbp+Block]
0x140024a78  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140024a7d  nop
0x140024a7e  jmp     short loc_140024AAC
0x140024a80  lea     rdx, ?MethodDelete@WebRequest@@2V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@B; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const WebRequest::MethodDelete
0x140024a87  jmp     short loc_140024AA2
0x140024a89  lea     rdx, ?MethodPut@WebRequest@@2V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@B; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const WebRequest::MethodPut
0x140024a90  jmp     short loc_140024AA2
0x140024a92  lea     rdx, ?MethodPost@WebRequest@@2V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@B; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const WebRequest::MethodPost
0x140024a99  jmp     short loc_140024AA2
0x140024a9b  lea     rdx, ?MethodGet@WebRequest@@2V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@B; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const WebRequest::MethodGet
0x140024aa2  lea     rcx, [rbp+Block]
0x140024aa6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140024aab  nop
0x140024aac  lea     r9, [rdi+20h]
0x140024ab0  lea     r8, [rbp+arg_8]
0x140024ab4  lea     rdx, [rbp+Block]
0x140024ab8  mov     rcx, rbx
0x140024abb  call    ?Open@WebRequest@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@00_NP6AX_KJ@Z@Z; WebRequest::Open(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool,void (*)(unsigned __int64,long))
0x140024ac0  nop
0x140024ac1  mov     rdx, [rbp+Block]
0x140024ac5  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140024ac9  or      r14d, 0FFFFFFFFh
0x140024acd  mov     eax, r14d
0x140024ad0  lock xadd [rdx+10h], eax
0x140024ad5  add     eax, r14d
0x140024ad8  test    eax, eax
0x140024ada  jg      short loc_140024AEC
0x140024adc  mov     rcx, [rdx]
0x140024adf  mov     rax, [rcx]
0x140024ae2  mov     rax, [rax+8]
0x140024ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024aeb  nop
0x140024aec  mov     rdx, [rbp+arg_8]
0x140024af0  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140024af4  mov     eax, r14d
0x140024af7  lock xadd [rdx+10h], eax
0x140024afc  add     eax, r14d
0x140024aff  test    eax, eax
0x140024b01  jg      short loc_140024B12
0x140024b03  mov     rcx, [rdx]
0x140024b06  mov     rax, [rcx]
0x140024b09  mov     rax, [rax+8]
0x140024b0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024b12  lea     rdx, [rdi+18h]
0x140024b16  cmp     qword ptr [rdx], 0
0x140024b1a  jz      short loc_140024B24
0x140024b1c  mov     rcx, [rsi]
0x140024b1f  call    ?SetAdditionalRequestHeaders@WebRequest@@QEAAXAEBV?$unique_ptr@V?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@U?$default_delete@V?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@@2@@std@@@Z; WebRequest::SetAdditionalRequestHeaders(std::unique_ptr<std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x140024b24  mov     rbx, [rsi]
0x140024b27  mov     rdx, [rdi+10h]
0x140024b2b  lea     rcx, [rbp+Block]
0x140024b2f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140024b34  nop
0x140024b35  lea     rdx, [rbp+Block]
0x140024b39  mov     rcx, rbx; struct WebRequest *
0x140024b3c  call    ?Send@WebRequest@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebRequest::Send(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140024b41  nop
0x140024b42  mov     rdx, [rbp+Block]
0x140024b46  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140024b4a  mov     eax, r14d
0x140024b4d  lock xadd [rdx+10h], eax
0x140024b52  add     eax, r14d
0x140024b55  test    eax, eax
0x140024b57  jg      short loc_140024B68
0x140024b59  mov     rcx, [rdx]
0x140024b5c  mov     rax, [rcx]
0x140024b5f  mov     rax, [rax+8]
0x140024b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024b68  mov     rcx, [rsi]
0x140024b6b  cmp     word ptr [rcx+58h], 4
0x140024b70  jnz     loc_140024C6C
0x140024b76  lea     rdx, [rbp+Block]
0x140024b7a  call    ?GetResponseHeaders@WebRequest@@QEAA?AV?$unique_ptr@V?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@U?$default_delete@V?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@@2@@std@@XZ; WebRequest::GetResponseHeaders(void)
0x140024b7f  lea     r14, [rdi+28h]
0x140024b83  mov     rcx, [rax]
0x140024b86  mov     qword ptr [rax], 0
0x140024b8d  mov     rbx, [r14]
0x140024b90  mov     [r14], rcx
0x140024b93  test    rbx, rbx
0x140024b96  jz      short loc_140024BC4
0x140024b98  mov     r8, [rbx]
0x140024b9b  mov     r8, [r8+8]
0x140024b9f  mov     rdx, rbx
0x140024ba2  mov     rcx, rbx
0x140024ba5  call    ??$_Erase_tree_and_orphan@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>> &,std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *)
0x140024baa  mov     edx, 30h ; '0'
0x140024baf  mov     rcx, [rbx]; Block
0x140024bb2  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x140024bb7  mov     edx, 10h
0x140024bbc  mov     rcx, rbx; Block
0x140024bbf  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x140024bc4  mov     rbx, [rbp+Block]
0x140024bc8  test    rbx, rbx
0x140024bcb  jz      short loc_140024BF9
0x140024bcd  mov     r8, [rbx]
0x140024bd0  mov     r8, [r8+8]
0x140024bd4  mov     rdx, rbx
0x140024bd7  mov     rcx, rbx
0x140024bda  call    ??$_Erase_tree_and_orphan@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>> &,std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *)
0x140024bdf  mov     edx, 30h ; '0'
0x140024be4  mov     rcx, [rbx]; Block
0x140024be7  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x140024bec  mov     edx, 10h
0x140024bf1  mov     rcx, rbx; Block
0x140024bf4  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x140024bf9  lea     rdx, [rbp+Block]
0x140024bfd  mov     rcx, [rsi]
0x140024c00  call    ?ResponseText@WebRequest@@QEBA?AVCSecureString@@XZ; WebRequest::ResponseText(void)
0x140024c05  nop
0x140024c06  add     rdi, 30h ; '0'
0x140024c0a  mov     rdx, rax
0x140024c0d  mov     rcx, rdi
0x140024c10  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140024c15  nop
0x140024c16  lea     rcx, [rbp+Block]; this
0x140024c1a  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x140024c1f  mov     rax, [rsi]
0x140024c22  movzx   edx, word ptr [rax+5Ch]
0x140024c26  mov     rcx, [r15]
0x140024c29  mov     rax, [rcx]
0x140024c2c  mov     r8d, 0C8h
0x140024c32  cmp     dx, r8w
0x140024c36  jnz     short loc_140024C49
0x140024c38  mov     r8, rdi
0x140024c3b  mov     rdx, r14
0x140024c3e  mov     rax, [rax+8]
0x140024c42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024c47  jmp     short loc_140024C58
0x140024c49  mov     r9, rdi
0x140024c4c  mov     r8, r14
0x140024c4f  mov     rax, [rax+10h]
0x140024c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024c58  mov     rbx, [rsp+40h+arg_10]
0x140024c60  add     rsp, 40h
0x140024c64  pop     r15
0x140024c66  pop     r14
0x140024c68  pop     rdi
0x140024c69  pop     rsi
0x140024c6a  pop     rbp
0x140024c6b  retn
0x140024c6c  mov     edx, 0CAA10003h; unsigned int
0x140024c71  lea     rcx, [rbp+pExceptionObject]; this
0x140024c75  call    ??0InvalidCallException@@QEAA@K@Z; InvalidCallException::InvalidCallException(ulong)
0x140024c7a  lea     rdx, _TI3?AVInvalidCallException@@; pThrowInfo
0x140024c81  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140024c85  call    _CxxThrowException_0
```
