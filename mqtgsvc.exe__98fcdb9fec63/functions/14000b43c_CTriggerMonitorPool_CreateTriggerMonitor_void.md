# CTriggerMonitorPool::CreateTriggerMonitor(void)

- ea: `0x14000b43c`
- end: `0x14000b599`
- name: `?CreateTriggerMonitor@CTriggerMonitorPool@@AEAAJXZ`
- size: `349`
- prototype: `__int64 __fastcall(CTriggerMonitorPool *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000bdc0`
- `0x14000c0e0`
- `0x14000c490`

## callees

- `0x140003dc8`
- `0x140004538`
- `0x140006d34`
- `0x14000752c`
- `0x140007554`
- `0x140007c78`
- `0x140007ea8`
- `0x140008f08`
- `0x14000b43c`
- `0x14000ed18`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000b4f8`
- `KERNEL32!GetLastError` at `0x14000b4f8`

## pseudocode

```c
__int64 __fastcall CTriggerMonitorPool::CreateTriggerMonitor(CTriggerMonitorPool *this)
{
  unsigned int v2; // edi
  _QWORD *v3; // rcx
  _QWORD *i; // rax
  unsigned int v5; // r8d
  struct IUnknown *v6; // rax
  CThread *v8; // rax
  CThread *v9; // rdi
  signed int LastError; // ebx
  CThread *v11; // [rsp+40h] [rbp+8h] BYREF

  v2 = 0;
  v3 = (_QWORD *)*((_QWORD *)this + 23);
  for ( i = (_QWORD *)*v3; i != v3; i = (_QWORD *)*i )
  {
    v5 = v2 + 1;
    if ( !*(_BYTE *)(i[2] + 72LL) )
      v5 = v2;
    v2 = v5;
  }
  v6 = (struct IUnknown *)_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->((__int64 *)this + 2);
  if ( v2 >= (unsigned int)IMSMQTriggersConfig::GetMaxThreads(v6) )
    return 2147500037LL;
  v8 = (CThread *)MmAllocate(0x78u);
  v11 = v8;
  if ( v8 )
    v8 = CTriggerMonitor::CTriggerMonitor(
           v8,
           this,
           *((struct IMSMQTriggersConfig **)this + 2),
           (void **)this + 18,
           *((struct CQueueManager **)this + 33));
  v11 = v8;
  std::list<R<CRuntimeTriggerInfo>>::_Insert((char *)this + 176, *((_QWORD *)this + 23), &v11);
  v9 = v11;
  if ( CThread::Resume(v11) )
  {
    v11 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids);
    return 0;
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( v9 )
      CReference::Release(v9);
    return (unsigned int)LastError;
  }
}

```

## disassembly

```asm
0x14000b43c  mov     [rsp+arg_8], rbx
0x14000b441  mov     [rsp+arg_10], rsi
0x14000b446  push    rdi
0x14000b447  sub     rsp, 30h
0x14000b44b  mov     rbx, rcx
0x14000b44e  xor     edi, edi
0x14000b450  mov     rcx, [rcx+0B8h]
0x14000b457  mov     rax, [rcx]
0x14000b45a  cmp     rax, rcx
0x14000b45d  jz      short loc_14000B477
0x14000b45f  mov     rdx, [rax+10h]
0x14000b463  lea     r8d, [rdi+1]
0x14000b467  cmp     byte ptr [rdx+48h], 0
0x14000b46b  cmovz   r8d, edi
0x14000b46f  mov     edi, r8d
0x14000b472  mov     rax, [rax]
0x14000b475  jmp     short loc_14000B45A
0x14000b477  lea     rcx, [rbx+10h]
0x14000b47b  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x14000b480  mov     rcx, rax; this
0x14000b483  call    ?GetMaxThreads@IMSMQTriggersConfig@@QEAAJXZ; IMSMQTriggersConfig::GetMaxThreads(void)
0x14000b488  cmp     edi, eax
0x14000b48a  jb      short loc_14000B496
0x14000b48c  mov     eax, 80004005h
0x14000b491  jmp     loc_14000B589
0x14000b496  mov     ecx, 78h ; 'x'; unsigned __int64
0x14000b49b  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x14000b4a0  mov     [rsp+38h+arg_0], rax
0x14000b4a5  test    rax, rax
0x14000b4a8  jz      short loc_14000B4CD
0x14000b4aa  lea     r9, [rbx+90h]; void **
0x14000b4b1  mov     rcx, [rbx+108h]
0x14000b4b8  mov     [rsp+38h+var_18], rcx; struct CQueueManager *
0x14000b4bd  mov     r8, [rbx+10h]; struct IMSMQTriggersConfig *
0x14000b4c1  mov     rdx, rbx; struct CTriggerMonitorPool *
0x14000b4c4  mov     rcx, rax; this
0x14000b4c7  call    ??0CTriggerMonitor@@QEAA@PEAVCTriggerMonitorPool@@PEAUIMSMQTriggersConfig@@PEAPEAXPEAVCQueueManager@@@Z; CTriggerMonitor::CTriggerMonitor(CTriggerMonitorPool *,IMSMQTriggersConfig *,void * *,CQueueManager *)
0x14000b4cc  nop
0x14000b4cd  mov     [rsp+38h+arg_0], rax
0x14000b4d2  lea     rcx, [rbx+0B0h]
0x14000b4d9  lea     r8, [rsp+38h+arg_0]
0x14000b4de  mov     rdx, [rcx+8]
0x14000b4e2  call    ?_Insert@?$list@V?$R@VCRuntimeTriggerInfo@@@@V?$allocator@V?$R@VCRuntimeTriggerInfo@@@@@std@@@std@@QEAAXViterator@12@AEBV?$R@VCRuntimeTriggerInfo@@@@@Z; std::list<R<CRuntimeTriggerInfo>>::_Insert(std::list<R<CRuntimeTriggerInfo>>::iterator,R<CRuntimeTriggerInfo> const &)
0x14000b4e7  mov     rdi, [rsp+38h+arg_0]
0x14000b4ec  mov     rcx, rdi; this
0x14000b4ef  call    ?Resume@CThread@@QEAA_NXZ; CThread::Resume(void)
0x14000b4f4  test    al, al
0x14000b4f6  jnz     short loc_14000B54F
0x14000b4f8  call    cs:__imp_GetLastError
0x14000b4fe  mov     ebx, eax
0x14000b500  lea     rax, WPP_GLOBAL_Control
0x14000b507  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b50e  cmp     rcx, rax
0x14000b511  jz      short loc_14000B531
0x14000b513  test    byte ptr [rcx+1Ch], 1
0x14000b517  jz      short loc_14000B531
0x14000b519  mov     edx, 14h
0x14000b51e  mov     r9d, ebx
0x14000b521  lea     r8, WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids
0x14000b528  mov     rcx, [rcx+10h]
0x14000b52c  call    WPP_SF_d
0x14000b531  test    ebx, ebx
0x14000b533  jle     short loc_14000B53E
0x14000b535  movzx   ebx, bx
0x14000b538  or      ebx, 80070000h
0x14000b53e  test    rdi, rdi
0x14000b541  jz      short loc_14000B54B
0x14000b543  mov     rcx, rdi; this
0x14000b546  call    ?Release@CReference@@QEBAXXZ; CReference::Release(void)
0x14000b54b  mov     eax, ebx
0x14000b54d  jmp     short loc_14000B589
0x14000b54f  mov     [rsp+38h+arg_0], 0
0x14000b558  lea     rax, WPP_GLOBAL_Control
0x14000b55f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b566  cmp     rcx, rax
0x14000b569  jz      short loc_14000B587
0x14000b56b  test    byte ptr [rcx+1Ch], 4
0x14000b56f  jz      short loc_14000B587
0x14000b571  mov     edx, 15h
0x14000b576  lea     r8, WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids
0x14000b57d  mov     rcx, [rcx+10h]
0x14000b581  call    WPP_SF_
0x14000b586  nop
0x14000b587  xor     eax, eax
0x14000b589  mov     rbx, [rsp+38h+arg_8]
0x14000b58e  mov     rsi, [rsp+38h+arg_10]
0x14000b593  add     rsp, 30h
0x14000b597  pop     rdi
0x14000b598  retn
```
