# CmsCloseLayer

- ea: `0x1800072b0`
- end: `0x18000733c`
- name: `CmsCloseLayer`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callees

- `0x180001944`
- `0x1800021dc`
- `0x1800066e4`
- `0x1800072b0`
- `0x18000db50`

## string_xrefs

- `0x1800072f0`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsCloseLayer(__int64 **a1)
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
      (void *)0x649,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)(unsigned int)v3,
      v7);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x1800072b0  mov     r11, rsp
0x1800072b3  mov     [r11+18h], rbx
0x1800072b7  mov     [r11+20h], rsi
0x1800072bb  push    rdi; int
0x1800072bc  sub     rsp, 20h
0x1800072c0  mov     rbx, [rcx]
0x1800072c3  lea     rdx, [r11+10h]
0x1800072c7  mov     rsi, rcx
0x1800072ca  lea     rcx, CmsRpcClt_CloseLayer
0x1800072d1  mov     rax, [rbx]
0x1800072d4  mov     [r11+8], rax
0x1800072d8  lea     rax, [r11+8]
0x1800072dc  mov     [r11+10h], rax
0x1800072e0  call    ??$InvokeStubFunction@P6AJPEAX@ZAEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAX@ZAEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(long (*)(void *),void * &)
0x1800072e5  mov     edi, eax
0x1800072e7  test    eax, eax
0x1800072e9  jns     short loc_180007308
0x1800072eb  mov     rcx, [rsp+28h]; this
0x1800072f0  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x1800072f7  mov     r9d, eax; char *
0x1800072fa  mov     edx, 649h; void *
0x1800072ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007304  mov     eax, edi
0x180007306  jmp     short loc_18000732C
0x180007308  mov     rcx, [rbx+18h]; void *
0x18000730c  test    rcx, rcx
0x18000730f  jz      short loc_180007316
0x180007311  call    MIDL_user_free
0x180007316  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x18000731b  mov     rcx, rbx; void *
0x18000731e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007323  xor     eax, eax
0x180007325  mov     qword ptr [rsi], 0
0x18000732c  mov     rbx, [rsp+28h+arg_10]
0x180007331  mov     rsi, [rsp+28h+arg_18]
0x180007336  add     rsp, 20h
0x18000733a  pop     rdi
0x18000733b  retn
```
