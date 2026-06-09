# CContext::~CContext(void)

- ea: `0x18004ec44`
- end: `0x18004eeba`
- name: `??1CContext@@QEAA@XZ`
- size: `630`
- prototype: `void __fastcall(CContext *__hidden this)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18004eb98`
- `0x18004ec08`

## callees

- `0x180011050`
- `0x180029cd4`
- `0x180029f48`
- `0x18002bd20`
- `0x180037290`
- `0x18004e06c`
- `0x18004ec44`
- `0x18004eec0`
- `0x18004ef2c`
- `0x18004f190`
- `0x18004f1c4`
- `0x18009d94c`
- `0x1800a51d0`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ee67`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ee67`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004ee75`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004ee75`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004ec99`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004ec99`

## pseudocode

```c
void __fastcall CContext::~CContext(CContext *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  void *v6; // rcx
  __int64 v7; // rax
  _QWORD *v8; // rdi
  _QWORD *v9; // rdi
  void *v10; // rcx
  _QWORD *v11; // rsi
  __int64 v12; // rcx
  HANDLE ProcessHeap; // rax

  if ( *((_DWORD *)this + 928) == 1 )
  {
    v7 = *((_QWORD *)this + 4925);
    if ( v7 )
    {
      *(_BYTE *)(v7 + 212) = 0;
      CCommandListCache::TrimList(*((CCommandListCache **)this + 4925));
      CLockOwnerChild<CDevice,0>::UCReleaseUse(*((_QWORD *)this + 4925) + 152LL);
    }
    v8 = (_QWORD *)*((_QWORD *)this + 4926);
    if ( v8 )
    {
      v11 = (_QWORD *)v8[48];
      while ( v11 != v8 )
      {
        v12 = v11[19];
        v11 = (_QWORD *)v11[48];
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 56LL))(v12);
        v8 = (_QWORD *)*((_QWORD *)this + 4926);
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v8);
    }
    v9 = (_QWORD *)*((_QWORD *)this + 4928);
    while ( v9 != (_QWORD *)((char *)this + 39416) )
    {
      v10 = v9;
      v9 = (_QWORD *)v9[1];
      operator delete(v10);
    }
    _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)this + 20) + 3672LL));
    std::list<CTaskRecord *>::clear((char *)this + 39504);
  }
  SmallDDIElLayout::operator delete(*((void **)this + 4958), 0x898u);
  SmallDDIElLayout::operator delete(*((void **)this + 4955), 0x178u);
  SmallDDIElLayout::operator delete(*((void **)this + 4956), 0x7E8u);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 1018);
  std::unique_ptr<SAPIPipelineState>::~unique_ptr<SAPIPipelineState>((char *)this + 39656);
  v2 = *((_QWORD *)this + 4949);
  if ( v2 )
  {
    std::_Deallocate<16>(v2, (*((_QWORD *)this + 4951) - v2) & 0xFFFFFFFFFFFFFFF0uLL);
    *((_QWORD *)this + 4949) = 0;
    *((_QWORD *)this + 4950) = 0;
    *((_QWORD *)this + 4951) = 0;
  }
  v3 = *((_QWORD *)this + 4946);
  if ( v3 )
  {
    std::_Deallocate<16>(v3, (*((_QWORD *)this + 4948) - v3) & 0xFFFFFFFFFFFFFFF0uLL);
    *((_QWORD *)this + 4946) = 0;
    *((_QWORD *)this + 4947) = 0;
    *((_QWORD *)this + 4948) = 0;
  }
  v4 = *((_QWORD *)this + 4943);
  if ( v4 )
  {
    std::_Deallocate<16>(v4, (*((_QWORD *)this + 4945) - v4) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 4943) = 0;
    *((_QWORD *)this + 4944) = 0;
    *((_QWORD *)this + 4945) = 0;
  }
  v5 = *((_QWORD *)this + 4940);
  if ( v5 )
  {
    std::_Deallocate<16>(v5, (*((_QWORD *)this + 4942) - v5) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 4940) = 0;
    *((_QWORD *)this + 4941) = 0;
    *((_QWORD *)this + 4942) = 0;
  }
  std::_List_node<CTaskRecord *,void *>::_Free_non_head<std::allocator<std::_List_node<CTaskRecord *,void *>>>(
    v5,
    *((_QWORD *)this + 4938));
  std::_Deallocate<16>(*((_QWORD *)this + 4938), 24);
  segmented_stack<unsigned __int64,256,ddi_stack_unary>::~segmented_stack<unsigned __int64,256,ddi_stack_unary>((char *)this + 39432);
  std::unique_ptr<void>::~unique_ptr<void>((char *)this + 39344);
  v6 = (void *)*((_QWORD *)this + 472);
  if ( v6 )
    SmallDDIElLayout::operator delete(v6, 0x8A88u);
  CCLSManager<cls_unary>::~CCLSManager<cls_unary>((char *)this + 3728);
  CDeviceChild<ID3D11CryptoSession>::~CDeviceChild<ID3D11CryptoSession>(this);
}

```

## disassembly

```asm
0x18004ec44  push    rbx
0x18004ec46  push    rbp
0x18004ec47  push    rsi
0x18004ec48  push    rdi
0x18004ec49  sub     rsp, 28h
0x18004ec4d  xor     ebp, ebp
0x18004ec4f  mov     rbx, rcx
0x18004ec52  cmp     dword ptr [rcx+0E80h], 1
0x18004ec59  jz      loc_18004EDDC
0x18004ec5f  mov     rcx, [rbx+9AF0h]; void *
0x18004ec66  mov     edx, 898h; unsigned int
0x18004ec6b  call    ??3SmallDDIElLayout@@KAXPEAXI@Z; SmallDDIElLayout::operator delete(void *,uint)
0x18004ec70  mov     rcx, [rbx+9AD8h]; void *
0x18004ec77  mov     edx, 178h; unsigned int
0x18004ec7c  call    ??3SmallDDIElLayout@@KAXPEAXI@Z; SmallDDIElLayout::operator delete(void *,uint)
0x18004ec81  mov     rcx, [rbx+9AE0h]; void *
0x18004ec88  mov     edx, 7E8h; unsigned int
0x18004ec8d  call    ??3SmallDDIElLayout@@KAXPEAXI@Z; SmallDDIElLayout::operator delete(void *,uint)
0x18004ec92  lea     rcx, [rbx+9F10h]; lpCriticalSection
0x18004ec99  call    cs:__imp_DeleteCriticalSection
0x18004ec9f  lea     rcx, [rbx+9AE8h]
0x18004eca6  call    ??1?$unique_ptr@USAPIPipelineState@@U?$default_delete@USAPIPipelineState@@@std@@@std@@QEAA@XZ; std::unique_ptr<SAPIPipelineState>::~unique_ptr<SAPIPipelineState>(void)
0x18004ecab  mov     rcx, [rbx+9AA8h]
0x18004ecb2  test    rcx, rcx
0x18004ecb5  jz      short loc_18004ECDF
0x18004ecb7  mov     rdx, [rbx+9AB8h]
0x18004ecbe  sub     rdx, rcx
0x18004ecc1  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18004ecc5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004ecca  mov     [rbx+9AA8h], rbp
0x18004ecd1  mov     [rbx+9AB0h], rbp
0x18004ecd8  mov     [rbx+9AB8h], rbp
0x18004ecdf  mov     rcx, [rbx+9A90h]
0x18004ece6  test    rcx, rcx
0x18004ece9  jz      short loc_18004ED13
0x18004eceb  mov     rdx, [rbx+9AA0h]
0x18004ecf2  sub     rdx, rcx
0x18004ecf5  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18004ecf9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004ecfe  mov     [rbx+9A90h], rbp
0x18004ed05  mov     [rbx+9A98h], rbp
0x18004ed0c  mov     [rbx+9AA0h], rbp
0x18004ed13  mov     rcx, [rbx+9A78h]
0x18004ed1a  test    rcx, rcx
0x18004ed1d  jz      short loc_18004ED47
0x18004ed1f  mov     rdx, [rbx+9A88h]
0x18004ed26  sub     rdx, rcx
0x18004ed29  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18004ed2d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004ed32  mov     [rbx+9A78h], rbp
0x18004ed39  mov     [rbx+9A80h], rbp
0x18004ed40  mov     [rbx+9A88h], rbp
0x18004ed47  mov     rcx, [rbx+9A60h]
0x18004ed4e  test    rcx, rcx
0x18004ed51  jz      short loc_18004ED7B
0x18004ed53  mov     rdx, [rbx+9A70h]
0x18004ed5a  sub     rdx, rcx
0x18004ed5d  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18004ed61  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004ed66  mov     [rbx+9A60h], rbp
0x18004ed6d  mov     [rbx+9A68h], rbp
0x18004ed74  mov     [rbx+9A70h], rbp
0x18004ed7b  mov     rdx, [rbx+9A50h]
0x18004ed82  call    ??$_Free_non_head@V?$allocator@U?$_List_node@PEAVCTaskRecord@@PEAX@std@@@std@@@?$_List_node@PEAVCTaskRecord@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@PEAVCTaskRecord@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<CTaskRecord *,void *>::_Free_non_head<std::allocator<std::_List_node<CTaskRecord *,void *>>>(std::allocator<std::_List_node<CTaskRecord *,void *>> &,std::_List_node<CTaskRecord *,void *> *)
0x18004ed87  mov     rcx, [rbx+9A50h]
0x18004ed8e  mov     edx, 18h
0x18004ed93  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004ed98  lea     rcx, [rbx+9A08h]
0x18004ed9f  call    ??1?$segmented_stack@_K$0BAA@Uddi_stack_unary@@@@QEAA@XZ; segmented_stack<unsigned __int64,256,ddi_stack_unary>::~segmented_stack<unsigned __int64,256,ddi_stack_unary>(void)
0x18004eda4  lea     rcx, [rbx+99B0h]
0x18004edab  call    ??1?$unique_ptr@XU?$default_delete@X@std@@@std@@QEAA@XZ; std::unique_ptr<void>::~unique_ptr<void>(void)
0x18004edb0  mov     rcx, [rbx+0EC0h]; void *
0x18004edb7  test    rcx, rcx
0x18004edba  jnz     loc_18004EEAB
0x18004edc0  lea     rcx, [rbx+0E90h]
0x18004edc7  call    ??1?$CCLSManager@Ucls_unary@@@@QEAA@XZ; CCLSManager<cls_unary>::~CCLSManager<cls_unary>(void)
0x18004edcc  mov     rcx, rbx
0x18004edcf  add     rsp, 28h
0x18004edd3  pop     rdi
0x18004edd4  pop     rsi
0x18004edd5  pop     rbp
0x18004edd6  pop     rbx
0x18004edd7  jmp     ??1?$CDeviceChild@UID3D11CryptoSession@@@@QEAA@XZ; CDeviceChild<ID3D11CryptoSession>::~CDeviceChild<ID3D11CryptoSession>(void)
0x18004eddc  mov     rax, [rcx+99E8h]
0x18004ede3  test    rax, rax
0x18004ede6  jnz     loc_18004EE80
0x18004edec  mov     rdi, [rbx+99F0h]
0x18004edf3  test    rdi, rdi
0x18004edf6  jnz     short loc_18004EE38
0x18004edf8  mov     rdi, [rbx+9A00h]
0x18004edff  lea     rsi, [rbx+99F8h]
0x18004ee06  jmp     short loc_18004EE14
0x18004ee08  mov     rcx, rdi; lpMem
0x18004ee0b  mov     rdi, [rdi+8]
0x18004ee0f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004ee14  cmp     rdi, rsi
0x18004ee17  jnz     short loc_18004EE08
0x18004ee19  mov     rax, [rbx+0A0h]
0x18004ee20  lea     rcx, [rbx+9A50h]
0x18004ee27  lock dec dword ptr [rax+0E58h]
0x18004ee2e  call    ?clear@?$list@PEAVCTaskRecord@@V?$allocator@PEAVCTaskRecord@@@std@@@std@@QEAAXXZ; std::list<CTaskRecord *>::clear(void)
0x18004ee33  jmp     loc_18004EC5F
0x18004ee38  mov     rsi, [rdi+180h]
0x18004ee3f  jmp     short loc_18004EE62
0x18004ee41  mov     rcx, [rsi+98h]
0x18004ee48  mov     rsi, [rsi+180h]
0x18004ee4f  mov     rax, [rcx]
0x18004ee52  mov     rax, [rax+38h]
0x18004ee56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ee5b  mov     rdi, [rbx+99F0h]
0x18004ee62  cmp     rsi, rdi
0x18004ee65  jnz     short loc_18004EE41
0x18004ee67  call    cs:__imp_GetProcessHeap
0x18004ee6d  mov     r8, rdi; lpMem
0x18004ee70  xor     edx, edx; dwFlags
0x18004ee72  mov     rcx, rax; hHeap
0x18004ee75  call    cs:__imp_HeapFree
0x18004ee7b  jmp     loc_18004EDF8
0x18004ee80  mov     [rax+0D4h], bpl
0x18004ee87  mov     rcx, [rcx+99E8h]; this
0x18004ee8e  call    ?TrimList@CCommandListCache@@QEAAXXZ; CCommandListCache::TrimList(void)
0x18004ee93  mov     rcx, [rbx+99E8h]
0x18004ee9a  add     rcx, 98h
0x18004eea1  call    ?UCReleaseUse@?$CLockOwnerChild@VCDevice@@$0A@@@QEAAKXZ; CLockOwnerChild<CDevice,0>::UCReleaseUse(void)
0x18004eea6  jmp     loc_18004EDEC
0x18004eeab  mov     edx, 8A88h; unsigned int
0x18004eeb0  call    ??3SmallDDIElLayout@@KAXPEAXI@Z; SmallDDIElLayout::operator delete(void *,uint)
0x18004eeb5  jmp     loc_18004EDC0
```
