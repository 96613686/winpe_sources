# CESimSettingApi::~CESimSettingApi(void)

- ea: `0x180050580`
- end: `0x18005060f`
- name: `??1CESimSettingApi@@QEAA@XZ`
- size: `143`
- prototype: `void __fastcall(CESimSettingApi *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180050700`

## callees

- `0x1800028b0`
- `0x1800503f8`
- `0x180050580`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800505f9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800505f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800505a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800505a3`

## pseudocode

```c
void __fastcall CESimSettingApi::~CESimSettingApi(CESimSettingApi *this)
{
  _QWORD *v2; // rbx
  void *v3; // rcx

  *(_QWORD *)this = &CESimSettingApi::`vftable';
  CloseHandle(*((HANDLE *)this + 20));
  v2 = *(_QWORD **)(*((_QWORD *)this + 24) + 8LL);
  while ( !*((_BYTE *)v2 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,enum ESimSettingOperation>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned long const,enum ESimSettingOperation>,void *>>>(
      (char *)this + 192,
      (char *)this + 192,
      v2[2]);
    v3 = v2;
    v2 = (_QWORD *)*v2;
    operator delete(v3);
  }
  operator delete(*((void **)this + 24));
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x180050580  mov     [rsp+arg_0], rbx
0x180050585  mov     [rsp+arg_8], rsi
0x18005058a  push    rdi
0x18005058b  sub     rsp, 20h
0x18005058f  lea     rax, ??_7CESimSettingApi@@6B@; const CESimSettingApi::`vftable'
0x180050596  mov     rdi, rcx
0x180050599  mov     [rcx], rax
0x18005059c  mov     rcx, [rcx+0A0h]; hObject
0x1800505a3  call    cs:__imp_CloseHandle
0x1800505a9  lea     rsi, [rdi+0C0h]
0x1800505b0  mov     rax, [rsi]
0x1800505b3  mov     rbx, [rax+8]
0x1800505b7  jmp     short loc_1800505D8
0x1800505b9  mov     r8, [rbx+10h]
0x1800505bd  mov     rdx, rsi
0x1800505c0  mov     rcx, rsi
0x1800505c3  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBKW4ESimSettingOperation@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKW4ESimSettingOperation@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBKW4ESimSettingOperation@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBKW4ESimSettingOperation@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,ESimSettingOperation>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ulong const,ESimSettingOperation>,void *>>>(std::allocator<std::_Tree_node<std::pair<ulong const,ESimSettingOperation>,void *>> &,std::_Tree_node<std::pair<ulong const,ESimSettingOperation>,void *> *)
0x1800505c8  mov     rcx, rbx; Block
0x1800505cb  mov     edx, 28h ; '('
0x1800505d0  mov     rbx, [rbx]
0x1800505d3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800505d8  cmp     byte ptr [rbx+19h], 0
0x1800505dc  jz      short loc_1800505B9
0x1800505de  mov     rcx, [rsi]; Block
0x1800505e1  mov     edx, 28h ; '('
0x1800505e6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800505eb  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800505ef  cmp     byte ptr [rcx+28h], 0
0x1800505f3  jz      short loc_1800505FF
0x1800505f5  mov     byte ptr [rcx+28h], 0
0x1800505f9  call    cs:__imp_DeleteCriticalSection
0x1800505ff  mov     rbx, [rsp+28h+arg_0]
0x180050604  mov     rsi, [rsp+28h+arg_8]
0x180050609  add     rsp, 20h
0x18005060d  pop     rdi
0x18005060e  retn
```
