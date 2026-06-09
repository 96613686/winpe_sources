# CmsCloseContainer

- ea: `0x1800071d0`
- end: `0x1800072a4`
- name: `CmsCloseContainer`
- size: `212`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000a010`

## callees

- `0x180001944`
- `0x1800021dc`
- `0x180003bc4`
- `0x180003e68`
- `0x1800048a0`
- `0x1800066e4`
- `0x1800071d0`

## string_xrefs

- `0x180007292`: `onecore\base\gendrv\silos\clem\core\inc\CmClientServerCommon.h`
- `0x180007211`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsCloseContainer(__int64 *a1)
{
  __int64 v1; // rbx
  int v3; // eax
  const char *v4; // r9
  unsigned int v5; // edi
  void *v7; // rdi
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v10; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v11; // [rsp+38h] [rbp+10h] BYREF

  v1 = *a1;
  v10 = *(_QWORD *)(*a1 + 24);
  v11 = &v10;
  v3 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(CmsRpcClt_CloseContainer, &v11);
  v5 = v3;
  if ( v3 >= 0 )
  {
    v7 = *(void **)(v1 + 40);
    v11 = 0;
    *(_QWORD *)(v1 + 40) = 0;
    if ( v7 )
    {
      Csl::OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>(v7);
      operator delete(v7, (const struct std::nothrow_t *)0x18);
    }
    if ( *(_DWORD *)(v1 + 20) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\inc\\CmClientServerCommon.h",
        v4);
    operator delete((void *)v1, (const struct std::nothrow_t *)0x30);
    *a1 = 0;
    wistd::unique_ptr<Container::Manager::Client::OutOfProcClientContainerHandle,wistd::default_delete<Container::Manager::Client::OutOfProcClientContainerHandle>>::~unique_ptr<Container::Manager::Client::OutOfProcClientContainerHandle,wistd::default_delete<Container::Manager::Client::OutOfProcClientContainerHandle>>(&v11);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14A,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)(unsigned int)v3,
      v8);
    return v5;
  }
}

```

## disassembly

```asm
0x1800071d0  mov     r11, rsp
0x1800071d3  mov     [r11+18h], rbx
0x1800071d7  mov     [r11+20h], rsi
0x1800071db  push    rdi; int
0x1800071dc  sub     rsp, 20h
0x1800071e0  mov     rbx, [rcx]
0x1800071e3  lea     rdx, [r11+10h]
0x1800071e7  mov     rsi, rcx
0x1800071ea  lea     rcx, CmsRpcClt_CloseContainer
0x1800071f1  mov     rax, [rbx+18h]
0x1800071f5  mov     [r11+8], rax
0x1800071f9  lea     rax, [r11+8]
0x1800071fd  mov     [r11+10h], rax
0x180007201  call    ??$InvokeStubFunction@P6AJPEAX@ZAEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAX@ZAEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(long (*)(void *),void * &)
0x180007206  mov     edi, eax
0x180007208  test    eax, eax
0x18000720a  jns     short loc_180007229
0x18000720c  mov     rcx, [rsp+28h]; this
0x180007211  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180007218  mov     r9d, eax; char *
0x18000721b  mov     edx, 14Ah; void *
0x180007220  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007225  mov     eax, edi
0x180007227  jmp     short loc_18000727D
0x180007229  mov     rdi, [rbx+28h]
0x18000722d  mov     [rsp+28h+arg_8], 0
0x180007236  mov     qword ptr [rbx+28h], 0
0x18000723e  test    rdi, rdi
0x180007241  jz      short loc_180007258
0x180007243  mov     rcx, rdi
0x180007246  call    ??1?$OutOfProcNotificationSubscriber@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@QEAA@XZ; Csl::OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>(void)
0x18000724b  mov     edx, 18h; struct std::nothrow_t *
0x180007250  mov     rcx, rdi; void *
0x180007253  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007258  mov     eax, [rbx+14h]
0x18000725b  test    eax, eax
0x18000725d  jnz     short loc_18000728D
0x18000725f  lea     edx, [rax+30h]; struct std::nothrow_t *
0x180007262  mov     rcx, rbx; void *
0x180007265  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000726a  lea     rcx, [rsp+28h+arg_8]
0x18000726f  mov     qword ptr [rsi], 0
0x180007276  call    ??1?$unique_ptr@VOutOfProcClientContainerHandle@Client@Manager@Container@@U?$default_delete@VOutOfProcClientContainerHandle@Client@Manager@Container@@@wistd@@@wistd@@QEAA@XZ; wistd::unique_ptr<Container::Manager::Client::OutOfProcClientContainerHandle,wistd::default_delete<Container::Manager::Client::OutOfProcClientContainerHandle>>::~unique_ptr<Container::Manager::Client::OutOfProcClientContainerHandle,wistd::default_delete<Container::Manager::Client::OutOfProcClientContainerHandle>>(void)
0x18000727b  xor     eax, eax
0x18000727d  mov     rbx, [rsp+28h+arg_10]
0x180007282  mov     rsi, [rsp+28h+arg_18]
0x180007287  add     rsp, 20h
0x18000728b  pop     rdi
0x18000728c  retn
0x18000728d  mov     rcx, [rsp+28h]; this
0x180007292  lea     r8, aOnecoreBaseGen_10; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180007299  mov     edx, 35h ; '5'; void *
0x18000729e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
