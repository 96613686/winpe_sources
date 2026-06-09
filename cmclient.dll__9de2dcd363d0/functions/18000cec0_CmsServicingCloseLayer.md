# CmsServicingCloseLayer

- ea: `0x18000cec0`
- end: `0x18000cf4c`
- name: `CmsServicingCloseLayer`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting, installer_update`

## callees

- `0x180001944`
- `0x1800021dc`
- `0x1800066e4`
- `0x18000cec0`
- `0x18000db50`

## string_xrefs

- `0x18000cf00`: `onecore\base\gendrv\silos\clem\client\dll\servicingapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsServicingCloseLayer(__int64 **a1)
{
  __int64 *v1; // rbx
  int v3; // eax
  unsigned int v4; // edi
  __int64 result; // rax
  void *v6; // rcx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v9; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v10; // [rsp+38h] [rbp+10h] BYREF

  v1 = *a1;
  v9 = **a1;
  v10 = &v9;
  v3 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(
         (__int64 (__fastcall *)(_QWORD))CmsRpcClt_CloseLayer,
         &v10);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v6 = (void *)v1[3];
    if ( v6 )
      MIDL_user_free(v6);
    operator delete(v1, (const struct std::nothrow_t *)0x20);
    result = 0;
    *a1 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC6,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\servicingapi.cpp",
      (const char *)(unsigned int)v3,
      v7);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x18000cec0  mov     r11, rsp
0x18000cec3  mov     [r11+18h], rbx
0x18000cec7  mov     [r11+20h], rsi
0x18000cecb  push    rdi; int
0x18000cecc  sub     rsp, 20h
0x18000ced0  mov     rbx, [rcx]
0x18000ced3  lea     rdx, [r11+10h]
0x18000ced7  mov     rsi, rcx
0x18000ceda  lea     rcx, CmsRpcClt_CloseLayer
0x18000cee1  mov     rax, [rbx]
0x18000cee4  mov     [r11+8], rax
0x18000cee8  lea     rax, [r11+8]
0x18000ceec  mov     [r11+10h], rax
0x18000cef0  call    ??$InvokeStubFunction@P6AJPEAX@ZAEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAX@ZAEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(long (*)(void *),void * &)
0x18000cef5  mov     edi, eax
0x18000cef7  test    eax, eax
0x18000cef9  jns     short loc_18000CF18
0x18000cefb  mov     rcx, [rsp+28h]; this
0x18000cf00  lea     r8, aOnecoreBaseGen_7; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000cf07  mov     r9d, eax; char *
0x18000cf0a  mov     edx, 0C6h; void *
0x18000cf0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cf14  mov     eax, edi
0x18000cf16  jmp     short loc_18000CF3C
0x18000cf18  mov     rcx, [rbx+18h]; void *
0x18000cf1c  test    rcx, rcx
0x18000cf1f  jz      short loc_18000CF26
0x18000cf21  call    MIDL_user_free
0x18000cf26  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x18000cf2b  mov     rcx, rbx; void *
0x18000cf2e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000cf33  xor     eax, eax
0x18000cf35  mov     qword ptr [rsi], 0
0x18000cf3c  mov     rbx, [rsp+28h+arg_10]
0x18000cf41  mov     rsi, [rsp+28h+arg_18]
0x18000cf46  add     rsp, 20h
0x18000cf4a  pop     rdi
0x18000cf4b  retn
```
