# CNDFHelperClass::~CNDFHelperClass(void)

- ea: `0x18000cb80`
- end: `0x18000ccb7`
- name: `??1CNDFHelperClass@@QEAA@XZ`
- size: `311`
- prototype: `void __fastcall(CNDFHelperClass *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800055d0`
- `0x180007a20`
- `0x180007d5c`

## callees

- `0x18000ca20`
- `0x18000ca90`
- `0x18000cb04`
- `0x18000cb80`
- `0x180011178`
- `0x180011224`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000cc54`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cc90`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cc54`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cc90`
- `KERNEL32!DeleteCriticalSection` at `0x18000cc1e`
- `KERNEL32!DeleteCriticalSection` at `0x18000cc1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cb9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cbab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cbbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cbcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cbdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cbeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cbfb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cc0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cb9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cbab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cbbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cbcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cbdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cbeb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cbfb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cc0b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CNDFHelperClass::~CNDFHelperClass(CNDFHelperClass *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &CNDFHelperClass::`vftable';
  CoTaskMemFree(*((LPVOID *)this + 1));
  CoTaskMemFree(*((LPVOID *)this + 3));
  CoTaskMemFree(*((LPVOID *)this + 5));
  CoTaskMemFree(*((LPVOID *)this + 6));
  CoTaskMemFree(*((LPVOID *)this + 8));
  CoTaskMemFree(*((LPVOID *)this + 2));
  CoTaskMemFree(*((LPVOID *)this + 7));
  CoTaskMemFree(*((LPVOID *)this + 9));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 8);
  std::vector<StoredMatchValue>::~vector<StoredMatchValue>((char *)this + 296);
  std::vector<StoredHelperAttributeInfo>::~vector<StoredHelperAttributeInfo>((char *)this + 264);
  std::_Tree<std::_Tmap_traits<_GUID,GUIDVarInfo const *,std::less<_GUID>,std::allocator<std::pair<_GUID const,GUIDVarInfo const *>>,1>>::clear((char *)this + 240);
  operator delete(*((void **)this + 30));
  std::vector<GUIDVarInfo>::~vector<GUIDVarInfo>((char *)this + 208);
  std::vector<GUIDVarInfo>::~vector<GUIDVarInfo>((char *)this + 176);
  std::vector<std::wstring>::_Tidy((char *)this + 144);
  v2 = (void *)*((_QWORD *)this + 14);
  if ( v2 )
  {
    operator delete(v2);
    *((_QWORD *)this + 14) = 0;
    *((_QWORD *)this + 15) = 0;
    *((_QWORD *)this + 16) = 0;
  }
}

```

## disassembly

```asm
0x18000cb80  mov     [rsp+arg_0], rbx
0x18000cb85  push    rdi
0x18000cb86  sub     rsp, 20h
0x18000cb8a  mov     rdi, rcx
0x18000cb8d  lea     rax, ??_7CNDFHelperClass@@6B@; const CNDFHelperClass::`vftable'
0x18000cb94  mov     [rcx], rax
0x18000cb97  mov     rcx, [rcx+8]; pv
0x18000cb9b  call    cs:__imp_CoTaskMemFree
0x18000cba2  nop     dword ptr [rax+rax+00h]
0x18000cba7  mov     rcx, [rdi+18h]; pv
0x18000cbab  call    cs:__imp_CoTaskMemFree
0x18000cbb2  nop     dword ptr [rax+rax+00h]
0x18000cbb7  mov     rcx, [rdi+28h]; pv
0x18000cbbb  call    cs:__imp_CoTaskMemFree
0x18000cbc2  nop     dword ptr [rax+rax+00h]
0x18000cbc7  mov     rcx, [rdi+30h]; pv
0x18000cbcb  call    cs:__imp_CoTaskMemFree
0x18000cbd2  nop     dword ptr [rax+rax+00h]
0x18000cbd7  mov     rcx, [rdi+40h]; pv
0x18000cbdb  call    cs:__imp_CoTaskMemFree
0x18000cbe2  nop     dword ptr [rax+rax+00h]
0x18000cbe7  mov     rcx, [rdi+10h]; pv
0x18000cbeb  call    cs:__imp_CoTaskMemFree
0x18000cbf2  nop     dword ptr [rax+rax+00h]
0x18000cbf7  mov     rcx, [rdi+38h]; pv
0x18000cbfb  call    cs:__imp_CoTaskMemFree
0x18000cc02  nop     dword ptr [rax+rax+00h]
0x18000cc07  mov     rcx, [rdi+48h]; pv
0x18000cc0b  call    cs:__imp_CoTaskMemFree
0x18000cc12  nop     dword ptr [rax+rax+00h]
0x18000cc17  lea     rcx, [rdi+140h]; lpCriticalSection
0x18000cc1e  call    cs:__imp_DeleteCriticalSection
0x18000cc25  nop     dword ptr [rax+rax+00h]
0x18000cc2a  lea     rcx, [rdi+128h]
0x18000cc31  call    ??1?$vector@UStoredMatchValue@@V?$allocator@UStoredMatchValue@@@std@@@std@@QEAA@XZ; std::vector<StoredMatchValue>::~vector<StoredMatchValue>(void)
0x18000cc36  lea     rcx, [rdi+108h]
0x18000cc3d  call    ??1?$vector@UStoredHelperAttributeInfo@@V?$allocator@UStoredHelperAttributeInfo@@@std@@@std@@QEAA@XZ; std::vector<StoredHelperAttributeInfo>::~vector<StoredHelperAttributeInfo>(void)
0x18000cc42  lea     rbx, [rdi+0F0h]
0x18000cc49  mov     rcx, rbx
0x18000cc4c  call    ?clear@?$_Tree@V?$_Tmap_traits@U_GUID@@PEBUGUIDVarInfo@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEBUGUIDVarInfo@@@std@@@4@$00@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<_GUID,GUIDVarInfo const *,std::less<_GUID>,std::allocator<std::pair<_GUID const,GUIDVarInfo const *>>,1>>::clear(void)
0x18000cc51  mov     rcx, [rbx]
0x18000cc54  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000cc5b  nop     dword ptr [rax+rax+00h]
0x18000cc60  nop
0x18000cc61  lea     rcx, [rdi+0D0h]
0x18000cc68  call    ??1?$vector@UGUIDVarInfo@@V?$allocator@UGUIDVarInfo@@@std@@@std@@QEAA@XZ; std::vector<GUIDVarInfo>::~vector<GUIDVarInfo>(void)
0x18000cc6d  lea     rcx, [rdi+0B0h]
0x18000cc74  call    ??1?$vector@UGUIDVarInfo@@V?$allocator@UGUIDVarInfo@@@std@@@std@@QEAA@XZ; std::vector<GUIDVarInfo>::~vector<GUIDVarInfo>(void)
0x18000cc79  lea     rcx, [rdi+90h]
0x18000cc80  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18000cc85  mov     rcx, [rdi+70h]
0x18000cc89  xor     ebx, ebx
0x18000cc8b  test    rcx, rcx
0x18000cc8e  jz      short loc_18000CCAB
0x18000cc90  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000cc97  nop     dword ptr [rax+rax+00h]
0x18000cc9c  mov     [rdi+70h], rbx
0x18000cca0  mov     [rdi+78h], rbx
0x18000cca4  mov     [rdi+80h], rbx
0x18000ccab  mov     rbx, [rsp+28h+arg_0]
0x18000ccb0  add     rsp, 20h
0x18000ccb4  pop     rdi
0x18000ccb5  retn
```
