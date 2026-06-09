# ATL::CComObject<CWwanSvcNotificationManager>::`scalar deleting destructor'(uint)

- ea: `0x18000d760`
- end: `0x18000d7d3`
- name: `??_G?$CComObject@VCWwanSvcNotificationManager@@@ATL@@UEAAPEAXI@Z`
- size: `115`
- prototype: `char *__fastcall(char *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800028b0`
- `0x18000d760`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d7ac`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d7ac`

## pseudocode

```c
char *__fastcall ATL::CComObject<CWwanSvcNotificationManager>::`scalar deleting destructor'(char *Block, char a2)
{
  *((_DWORD *)Block + 4) = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CWwanSvcNotificationManager>::`vftable'{for `IMbaeNotificationManager'};
  *((_QWORD *)Block + 1) = &ATL::CComObject<CWwanSvcNotificationManager>::`vftable'{for `INotificationActivationCallback'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( Block[64] )
  {
    Block[64] = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 24));
  }
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000d760  mov     [rsp+arg_0], rbx
0x18000d765  push    rdi
0x18000d766  sub     rsp, 20h
0x18000d76a  mov     dword ptr [rcx+10h], 0C0000001h
0x18000d771  lea     rax, ??_7?$CComObject@VCWwanSvcNotificationManager@@@ATL@@6BIMbaeNotificationManager@@@; const ATL::CComObject<CWwanSvcNotificationManager>::`vftable'{for `IMbaeNotificationManager'}
0x18000d778  mov     [rcx], rax
0x18000d77b  mov     rbx, rcx
0x18000d77e  lea     rax, ??_7?$CComObject@VCWwanSvcNotificationManager@@@ATL@@6BINotificationActivationCallback@@@; const ATL::CComObject<CWwanSvcNotificationManager>::`vftable'{for `INotificationActivationCallback'}
0x18000d785  mov     edi, edx
0x18000d787  mov     [rcx+8], rax
0x18000d78b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000d792  mov     rax, [rcx]
0x18000d795  mov     rax, [rax+10h]
0x18000d799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d79e  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000d7a2  cmp     byte ptr [rcx+28h], 0
0x18000d7a6  jz      short loc_18000D7B2
0x18000d7a8  mov     byte ptr [rcx+28h], 0
0x18000d7ac  call    cs:__imp_DeleteCriticalSection
0x18000d7b2  test    dil, 1
0x18000d7b6  jz      short loc_18000D7C5
0x18000d7b8  mov     edx, 48h ; 'H'
0x18000d7bd  mov     rcx, rbx; Block
0x18000d7c0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d7c5  mov     rax, rbx
0x18000d7c8  mov     rbx, [rsp+28h+arg_0]
0x18000d7cd  add     rsp, 20h
0x18000d7d1  pop     rdi
0x18000d7d2  retn
```
