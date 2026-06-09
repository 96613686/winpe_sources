# DAS::DevnodeManagment::DevnodeFactory::OnComplete(IAepDevnode *,long)

- ea: `0x18002afc0`
- end: `0x18002b0e6`
- name: `?OnComplete@DevnodeFactory@DevnodeManagment@DAS@@UEAAJPEAUIAepDevnode@@J@Z`
- size: `294`
- prototype: `int(DAS::DevnodeManagment::DevnodeFactory *__hidden this, struct IAepDevnode *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800074c0`
- `0x18001dfe0`
- `0x18001eae0`
- `0x18002a948`
- `0x18002afc0`
- `0x18005c320`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b093`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b0ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b093`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002b0ce`

## string_xrefs

- `0x18002afff`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`
- `0x18002b06e`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`
- `0x18002b0a9`: `onecore\base\devices\association\service\lib\devnodefactory.cpp`

## pseudocode

```c
__int64 __fastcall DAS::DevnodeManagment::DevnodeFactory::OnComplete(RTL_SRWLOCK *this, struct IAepDevnode *a2, int a3)
{
  __int64 v6; // r8
  __int64 (__fastcall *v7)(struct IAepDevnode *, __int64 *); // rbx
  int v8; // eax
  unsigned int v9; // edi
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v13; // [rsp+30h] [rbp+8h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp+20h] BYREF

  wil::AcquireSRWLockShared(&SRWLock, this + 26);
  if ( !LOBYTE(this[27].Ptr) )
  {
    a3 = -2140930029;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x835,
      (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodefactory.cpp",
      (const char *)0x80640013LL,
      v11);
LABEL_12:
    if ( SRWLock )
      ReleaseSRWLockShared(SRWLock);
    return (unsigned int)a3;
  }
  v6 = 0;
  v13 = 0;
  if ( a3 >= 0 )
  {
    v7 = *(__int64 (__fastcall **)(struct IAepDevnode *, __int64 *))(*(_QWORD *)a2 + 40LL);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v13,
      0);
    a3 = v7(a2, &v13);
    v6 = v13;
  }
  v8 = DAS::DevnodeManagment::CompleteDasHostFactoryOp(
         (DAS::DevnodeManagment *)&this[22],
         (void **)LODWORD(this[25].Ptr),
         v6,
         (const unsigned __int16 *)(unsigned int)a3);
  v9 = v8;
  if ( v8 >= 0 )
  {
    if ( a3 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x846,
        (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodefactory.cpp",
        (const char *)(unsigned int)a3,
        v11);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v13);
    goto LABEL_12;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x844,
    (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodefactory.cpp",
    (const char *)(unsigned int)v8,
    v11);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v13);
  if ( SRWLock )
    ReleaseSRWLockShared(SRWLock);
  return v9;
}

```

## disassembly

```asm
0x18002afc0  mov     [rsp+arg_8], rbx
0x18002afc5  mov     [rsp+arg_10], rsi
0x18002afca  push    rdi; int
0x18002afcb  sub     rsp, 20h
0x18002afcf  mov     ebx, r8d
0x18002afd2  mov     rsi, rdx
0x18002afd5  mov     rdi, rcx
0x18002afd8  lea     rdx, [rcx+0D0h]
0x18002afdf  lea     rcx, [rsp+28h+SRWLock]
0x18002afe4  call    ?AcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockShared(_RTL_SRWLOCK *)
0x18002afe9  cmp     byte ptr [rdi+0D8h], 0
0x18002aff0  jnz     short loc_18002B015
0x18002aff2  mov     rcx, [rsp+28h]; this
0x18002aff7  mov     ebx, 80640013h
0x18002affc  mov     r9d, ebx; char *
0x18002afff  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x18002b006  mov     edx, 835h; void *
0x18002b00b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b010  jmp     loc_18002B0C4
0x18002b015  xor     r8d, r8d
0x18002b018  mov     [rsp+28h+arg_0], r8
0x18002b01d  test    ebx, ebx
0x18002b01f  js      short loc_18002B04B
0x18002b021  mov     rax, [rsi]
0x18002b024  mov     rbx, [rax+28h]
0x18002b028  xor     edx, edx
0x18002b02a  lea     rcx, [rsp+28h+arg_0]
0x18002b02f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002b034  lea     rdx, [rsp+28h+arg_0]
0x18002b039  mov     rcx, rsi
0x18002b03c  mov     rax, rbx
0x18002b03f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b044  mov     ebx, eax
0x18002b046  mov     r8, [rsp+28h+arg_0]; unsigned int
0x18002b04b  lea     rcx, [rdi+0B0h]; this
0x18002b052  mov     r9d, ebx; unsigned __int16 *
0x18002b055  mov     edx, [rdi+0C8h]; void **
0x18002b05b  call    ?CompleteDasHostFactoryOp@DevnodeManagment@DAS@@YAJPEAPEAXKPEBGJ@Z; DAS::DevnodeManagment::CompleteDasHostFactoryOp(void * *,ulong,ushort const *,long)
0x18002b060  mov     edi, eax
0x18002b062  test    eax, eax
0x18002b064  jns     short loc_18002B09D
0x18002b066  mov     rcx, [rsp+28h]; this
0x18002b06b  mov     r9d, eax; char *
0x18002b06e  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x18002b075  mov     edx, 844h; void *
0x18002b07a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b07f  lea     rcx, [rsp+28h+arg_0]
0x18002b084  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b089  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x18002b08e  test    rcx, rcx
0x18002b091  jz      short loc_18002B099
0x18002b093  call    cs:__imp_ReleaseSRWLockShared
0x18002b099  mov     eax, edi
0x18002b09b  jmp     short loc_18002B0D6
0x18002b09d  test    ebx, ebx
0x18002b09f  jns     short loc_18002B0BA
0x18002b0a1  mov     rcx, [rsp+28h]; this
0x18002b0a6  mov     r9d, ebx; char *
0x18002b0a9  lea     r8, aOnecoreBaseDev_18; "onecore\\base\\devices\\association\\se"...
0x18002b0b0  mov     edx, 846h; void *
0x18002b0b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b0ba  lea     rcx, [rsp+28h+arg_0]
0x18002b0bf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b0c4  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x18002b0c9  test    rcx, rcx
0x18002b0cc  jz      short loc_18002B0D4
0x18002b0ce  call    cs:__imp_ReleaseSRWLockShared
0x18002b0d4  mov     eax, ebx
0x18002b0d6  mov     rbx, [rsp+28h+arg_8]
0x18002b0db  mov     rsi, [rsp+28h+arg_10]
0x18002b0e0  add     rsp, 20h
0x18002b0e4  pop     rdi
0x18002b0e5  retn
```
