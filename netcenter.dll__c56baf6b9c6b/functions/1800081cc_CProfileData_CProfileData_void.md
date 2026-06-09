# CProfileData::~CProfileData(void)

- ea: `0x1800081cc`
- end: `0x18000823f`
- name: `??1CProfileData@@QEAA@XZ`
- size: `115`
- prototype: `void __fastcall(CProfileData *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000874c`

## callees

- `0x180007618`
- `0x1800077a4`
- `0x1800081cc`
- `0x18001e460`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800081de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800081f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000820c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800081de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800081f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000820c`

## pseudocode

```c
void __fastcall CProfileData::~CProfileData(CProfileData *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  __int64 v5; // rcx

  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *((_QWORD *)this + 2) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 3);
  if ( v3 )
  {
    CoTaskMemFree(v3);
    *((_QWORD *)this + 3) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 5);
  if ( v4 )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 5) = 0;
  }
  ClearNetConnPropList((char *)this + 80);
  std::_List_node<IPicture *,void *>::_Free_non_head<std::allocator<std::_List_node<IPicture *,void *>>>(
    v5,
    *((_QWORD *)this + 10));
  std::_Deallocate<16>(*((_QWORD *)this + 10), 24);
}

```

## disassembly

```asm
0x1800081cc  push    rbx
0x1800081ce  sub     rsp, 20h
0x1800081d2  mov     rbx, rcx
0x1800081d5  mov     rcx, [rcx+10h]; pv
0x1800081d9  test    rcx, rcx
0x1800081dc  jz      short loc_1800081EC
0x1800081de  call    cs:__imp_CoTaskMemFree
0x1800081e4  mov     qword ptr [rbx+10h], 0
0x1800081ec  mov     rcx, [rbx+18h]; pv
0x1800081f0  test    rcx, rcx
0x1800081f3  jz      short loc_180008203
0x1800081f5  call    cs:__imp_CoTaskMemFree
0x1800081fb  mov     qword ptr [rbx+18h], 0
0x180008203  mov     rcx, [rbx+28h]; pv
0x180008207  test    rcx, rcx
0x18000820a  jz      short loc_18000821A
0x18000820c  call    cs:__imp_CoTaskMemFree
0x180008212  mov     qword ptr [rbx+28h], 0
0x18000821a  lea     rcx, [rbx+50h]
0x18000821e  call    ?ClearNetConnPropList@@YAXPEAV?$list@PEAUtagNETCON_PROPERTIES@@V?$allocator@PEAUtagNETCON_PROPERTIES@@@std@@@std@@@Z; ClearNetConnPropList(std::list<tagNETCON_PROPERTIES *> *)
0x180008223  mov     rdx, [rbx+50h]
0x180008227  call    ??$_Free_non_head@V?$allocator@U?$_List_node@PEAUIPicture@@PEAX@std@@@std@@@?$_List_node@PEAUIPicture@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@PEAUIPicture@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<IPicture *,void *>::_Free_non_head<std::allocator<std::_List_node<IPicture *,void *>>>(std::allocator<std::_List_node<IPicture *,void *>> &,std::_List_node<IPicture *,void *> *)
0x18000822c  mov     rcx, [rbx+50h]
0x180008230  mov     edx, 18h
0x180008235  add     rsp, 20h
0x180008239  pop     rbx
0x18000823a  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
