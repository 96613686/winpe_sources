# ATL::CComAggObject<CIisRestart>::Release(void)

- ea: `0x140002820`
- end: `0x1400028a3`
- name: `?Release@?$CComAggObject@VCIisRestart@@@ATL@@UEAAKXZ`
- size: `131`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001054`
- `0x140002820`
- `0x1400029d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140002883`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140002883`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CIisRestart>::Release(struct _RTL_CRITICAL_SECTION *Block)
{
  CExeModule *i; // rcx
  unsigned int v3; // edi

  for ( i = (CExeModule *)(unsigned int)Block->LockCount;
        (_DWORD)i != 0x7FFFFFFF
     && (_DWORD)i != _InterlockedCompareExchange(&Block->LockCount, (_DWORD)i - 1, (signed __int32)i);
        i = (CExeModule *)(unsigned int)Block->LockCount )
  {
    ;
  }
  v3 = (_DWORD)i - 1;
  if ( (_DWORD)i == 1 )
  {
    _InterlockedIncrement(&dword_14000A798);
    if ( Block )
    {
      Block->LockCount = 1;
      Block->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&ATL::CComAggObject<CIisRestart>::`vftable';
      CExeModule::Unlock(i);
      if ( LOBYTE(Block[2].DebugInfo) != (_BYTE)v3 )
      {
        LOBYTE(Block[2].DebugInfo) = v3;
        DeleteCriticalSection(Block + 1);
      }
      operator delete(Block);
    }
    CExeModule::Unlock(i);
  }
  return v3;
}

```

## disassembly

```asm
0x140002820  mov     [rsp+arg_0], rbx
0x140002825  push    rdi
0x140002826  sub     rsp, 20h
0x14000282a  mov     rbx, rcx
0x14000282d  mov     r8d, 7FFFFFFFh
0x140002833  mov     ecx, [rcx+8]
0x140002836  jmp     short loc_140002847
0x140002838  lea     edx, [rcx-1]
0x14000283b  mov     eax, ecx
0x14000283d  lock cmpxchg [rbx+8], edx
0x140002842  jz      short loc_14000284C
0x140002844  mov     ecx, [rbx+8]; this
0x140002847  cmp     ecx, r8d
0x14000284a  jnz     short loc_140002838
0x14000284c  lea     edi, [rcx-1]
0x14000284f  test    edi, edi
0x140002851  jnz     short loc_140002896
0x140002853  lock inc cs:dword_14000A798
0x14000285a  test    rbx, rbx
0x14000285d  jz      short loc_140002891
0x14000285f  lea     rax, ??_7?$CComAggObject@VCIisRestart@@@ATL@@6B@; const ATL::CComAggObject<CIisRestart>::`vftable'
0x140002866  mov     dword ptr [rbx+8], 1
0x14000286d  mov     [rbx], rax
0x140002870  call    ?Unlock@CExeModule@@QEAAJXZ; CExeModule::Unlock(void)
0x140002875  lea     rcx, [rbx+28h]; lpCriticalSection
0x140002879  cmp     [rcx+28h], dil
0x14000287d  jz      short loc_140002889
0x14000287f  mov     [rcx+28h], dil
0x140002883  call    cs:__imp_DeleteCriticalSection
0x140002889  mov     rcx, rbx; Block
0x14000288c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002891  call    ?Unlock@CExeModule@@QEAAJXZ; CExeModule::Unlock(void)
0x140002896  mov     rbx, [rsp+28h+arg_0]
0x14000289b  mov     eax, edi
0x14000289d  add     rsp, 20h
0x1400028a1  pop     rdi
0x1400028a2  retn
```
