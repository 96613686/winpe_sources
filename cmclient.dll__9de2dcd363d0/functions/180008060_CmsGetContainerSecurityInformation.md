# CmsGetContainerSecurityInformation

- ea: `0x180008060`
- end: `0x18000813d`
- name: `CmsGetContainerSecurityInformation`
- size: `221`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800024a8`
- `0x1800066e4`
- `0x180008060`
- `0x18000db50`
- `0x18000ee00`

## string_xrefs

- `0x1800080c4`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsGetContainerSecurityInformation(
        __int64 a1,
        unsigned int a2,
        void *a3,
        unsigned int a4,
        _DWORD *a5)
{
  int v7; // eax
  unsigned int v8; // ebx
  size_t v10; // rcx
  void *v11; // rbx
  int v12; // [rsp+20h] [rbp-30h]
  void *Src; // [rsp+30h] [rbp-20h] BYREF
  int v14[2]; // [rsp+38h] [rbp-18h] BYREF
  void **p_Src; // [rsp+40h] [rbp-10h] BYREF
  __int64 v16; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  size_t Size; // [rsp+70h] [rbp+20h] BYREF
  unsigned int v19; // [rsp+78h] [rbp+28h] BYREF

  v19 = a2;
  LODWORD(Size) = 0;
  *(_QWORD *)v14 = &Size;
  Src = 0;
  p_Src = &Src;
  v16 = *(_QWORD *)(a1 + 24);
  v7 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,unsigned long,unsigned char * *,unsigned long *),void *,unsigned long &,unsigned char * *,unsigned long *>(
         a1,
         &v16,
         &v19,
         &p_Src,
         v14);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v10 = (unsigned int)Size;
    *a5 = Size;
    if ( a4 >= (unsigned int)v10 )
    {
      v11 = Src;
      memcpy_0(a3, Src, v10);
      if ( v11 )
        MIDL_user_free(v11);
      return 0;
    }
    else
    {
      if ( Src )
        MIDL_user_free(Src);
      return 2147942522LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21E,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)(unsigned int)v7,
      v12);
    if ( Src )
      MIDL_user_free(Src);
    return v8;
  }
}

```

## disassembly

```asm
0x180008060  mov     [rsp-18h+arg_10], rbx
0x180008065  mov     [rsp-18h+arg_8], edx
0x180008069  push    rbp
0x18000806a  push    rsi
0x18000806b  push    rdi
0x18000806c  mov     rbp, rsp
0x18000806f  sub     rsp, 50h
0x180008073  lea     rax, [rbp+Size]
0x180008077  mov     dword ptr [rbp+Size], 0
0x18000807e  mov     qword ptr [rbp+var_18], rax
0x180008082  lea     rdx, [rbp+var_8]
0x180008086  lea     rax, [rbp+Src]
0x18000808a  mov     [rbp+Src], 0
0x180008092  mov     [rbp+var_10], rax
0x180008096  mov     edi, r9d
0x180008099  mov     rax, [rcx+18h]
0x18000809d  lea     r9, [rbp+var_10]
0x1800080a1  mov     [rbp+var_8], rax
0x1800080a5  mov     rsi, r8
0x1800080a8  lea     rax, [rbp+var_18]
0x1800080ac  lea     r8, [rbp+arg_8]
0x1800080b0  mov     qword ptr [rsp+50h+var_30], rax; int
0x1800080b5  call    ??$InvokeStubFunction@P6AJPEAXKPEAPEAEPEAK@ZPEAXAEAKPEAPEAEPEAK@Rpc@Manager@Container@@YAJP6AJPEAXKPEAPEAEPEAK@Z$$QEAPEAXAEAK$$QEAPEAPEAE$$QEAPEAK@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,ulong,uchar * *,ulong *),void *,ulong &,uchar * *,ulong *>(long (*)(void *,ulong,uchar * *,ulong *),void * &&,ulong &,uchar * * &&,ulong * &&)
0x1800080ba  mov     ebx, eax
0x1800080bc  test    eax, eax
0x1800080be  jns     short loc_1800080EA
0x1800080c0  mov     rcx, [rbp+18h]; this
0x1800080c4  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x1800080cb  mov     r9d, eax; char *
0x1800080ce  mov     edx, 21Eh; void *
0x1800080d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800080d8  mov     rcx, [rbp+Src]; void *
0x1800080dc  test    rcx, rcx
0x1800080df  jz      short loc_1800080E6
0x1800080e1  call    MIDL_user_free
0x1800080e6  mov     eax, ebx
0x1800080e8  jmp     short loc_18000812D
0x1800080ea  mov     ecx, dword ptr [rbp+Size]
0x1800080ed  mov     rax, [rbp+arg_20]
0x1800080f1  mov     [rax], ecx
0x1800080f3  cmp     edi, ecx
0x1800080f5  jnb     short loc_18000810C
0x1800080f7  mov     rcx, [rbp+Src]; void *
0x1800080fb  test    rcx, rcx
0x1800080fe  jz      short loc_180008105
0x180008100  call    MIDL_user_free
0x180008105  mov     eax, 8007007Ah
0x18000810a  jmp     short loc_18000812D
0x18000810c  mov     rbx, [rbp+Src]
0x180008110  mov     r8, rcx; Size
0x180008113  mov     rdx, rbx; Src
0x180008116  mov     rcx, rsi; void *
0x180008119  call    memcpy_0
0x18000811e  test    rbx, rbx
0x180008121  jz      short loc_18000812B
0x180008123  mov     rcx, rbx; void *
0x180008126  call    MIDL_user_free
0x18000812b  xor     eax, eax
0x18000812d  mov     rbx, [rsp+50h+arg_10]
0x180008135  add     rsp, 50h
0x180008139  pop     rdi
0x18000813a  pop     rsi
0x18000813b  pop     rbp
0x18000813c  retn
```
