# _CEventSource<CComObjectObserver>::~_CEventSource<CComObjectObserver>(void)

- ea: `0x180005590`
- end: `0x18000560f`
- name: `??1?$_CEventSource@VCComObjectObserver@@@@UEAA@XZ`
- size: `127`
- prototype: `__int64 __fastcall(struct CEventSourceBase *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180013100`
- `0x18001c3a0`

## callees

- `0x180005590`
- `0x18000566c`
- `0x180007908`
- `0x18000792c`
- `0x1800132f8`

## pseudocode

```c
void **__fastcall _CEventSource<CComObjectObserver>::~_CEventSource<CComObjectObserver>(struct CEventSourceBase *a1)
{
  __int64 **v1; // rsi
  __int64 *v2; // rbx
  CObserverBase *v4; // rcx
  void **result; // rax

  ++*((_DWORD *)a1 + 6);
  v1 = (__int64 **)((char *)a1 + 8);
  *(_QWORD *)a1 = &_CEventSource<CComObjectObserver>::`vftable';
  v2 = (__int64 *)*((_QWORD *)a1 + 1);
  while ( 1 )
  {
    v2 = (__int64 *)*v2;
    if ( v2 == *v1 )
      break;
    if ( !*((_BYTE *)v2 + 24) )
    {
      v4 = (CObserverBase *)v2[2];
      if ( v4 )
        CObserverBase::UnadviseObserver(v4, a1);
    }
  }
  if ( (*((_DWORD *)a1 + 6))-- == 1 )
    _CEventSource<CComObjectObserver>::CleanupDeleted(a1);
  std::list<_CEventSource<CComObjectObserver>::ObserverData,std::allocator<_CEventSource<CComObjectObserver>::ObserverData>>::clear(v1);
  std::list<_CEventSource<CComObjectObserver>::ObserverData,std::allocator<_CEventSource<CComObjectObserver>::ObserverData>>::~list<_CEventSource<CComObjectObserver>::ObserverData,std::allocator<_CEventSource<CComObjectObserver>::ObserverData>>(v1);
  result = &CEventSourceBase::`vftable';
  *(_QWORD *)a1 = &CEventSourceBase::`vftable';
  return result;
}

```

## disassembly

```asm
0x180005590  mov     [rsp+arg_8], rbx
0x180005595  mov     [rsp+arg_10], rsi
0x18000559a  push    rdi
0x18000559b  sub     rsp, 20h
0x18000559f  inc     dword ptr [rcx+18h]
0x1800055a2  lea     rax, ??_7?$_CEventSource@VCComObjectObserver@@@@6B@; const _CEventSource<CComObjectObserver>::`vftable'
0x1800055a9  lea     rsi, [rcx+8]
0x1800055ad  mov     [rcx], rax
0x1800055b0  mov     rbx, [rsi]
0x1800055b3  mov     rdi, rcx
0x1800055b6  mov     rbx, [rbx]
0x1800055b9  cmp     rbx, [rsi]
0x1800055bc  jz      short loc_1800055D7
0x1800055be  cmp     byte ptr [rbx+18h], 0
0x1800055c2  jnz     short loc_1800055B6
0x1800055c4  mov     rcx, [rbx+10h]; this
0x1800055c8  test    rcx, rcx
0x1800055cb  jz      short loc_1800055B6
0x1800055cd  mov     rdx, rdi; struct CEventSourceBase *
0x1800055d0  call    ?UnadviseObserver@CObserverBase@@QEAAXAEAVCEventSourceBase@@@Z; CObserverBase::UnadviseObserver(CEventSourceBase &)
0x1800055d5  jmp     short loc_1800055B6
0x1800055d7  sub     dword ptr [rdi+18h], 1
0x1800055db  jnz     short loc_1800055E5
0x1800055dd  mov     rcx, rdi
0x1800055e0  call    ?CleanupDeleted@?$_CEventSource@VCComObjectObserver@@@@AEAAXXZ; _CEventSource<CComObjectObserver>::CleanupDeleted(void)
0x1800055e5  mov     rcx, rsi
0x1800055e8  call    ?clear@?$list@UObserverData@?$_CEventSource@VCComObjectObserver@@@@V?$allocator@UObserverData@?$_CEventSource@VCComObjectObserver@@@@@std@@@std@@QEAAXXZ; std::list<_CEventSource<CComObjectObserver>::ObserverData,std::allocator<_CEventSource<CComObjectObserver>::ObserverData>>::clear(void)
0x1800055ed  mov     rcx, rsi
0x1800055f0  call    ??1?$list@UObserverData@?$_CEventSource@VCComObjectObserver@@@@V?$allocator@UObserverData@?$_CEventSource@VCComObjectObserver@@@@@std@@@std@@QEAA@XZ; std::list<_CEventSource<CComObjectObserver>::ObserverData,std::allocator<_CEventSource<CComObjectObserver>::ObserverData>>::~list<_CEventSource<CComObjectObserver>::ObserverData,std::allocator<_CEventSource<CComObjectObserver>::ObserverData>>(void)
0x1800055f5  mov     rbx, [rsp+28h+arg_8]
0x1800055fa  lea     rax, ??_7CEventSourceBase@@6B@; const CEventSourceBase::`vftable'
0x180005601  mov     rsi, [rsp+28h+arg_10]
0x180005606  mov     [rdi], rax
0x180005609  add     rsp, 20h
0x18000560d  pop     rdi
0x18000560e  retn
```
