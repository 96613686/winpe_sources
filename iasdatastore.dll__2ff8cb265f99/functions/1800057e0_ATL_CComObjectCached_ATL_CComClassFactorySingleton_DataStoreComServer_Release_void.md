# ATL::CComObjectCached<ATL::CComClassFactorySingleton<DataStoreComServer>>::Release(void)

- ea: `0x1800057e0`
- end: `0x18000588d`
- name: `?Release@?$CComObjectCached@V?$CComClassFactorySingleton@VDataStoreComServer@@@ATL@@@ATL@@UEAAKXZ`
- size: `173`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800057e0`
- `0x180010010`

## import_xrefs

- `msvcrt!free` at `0x180005860`
- `msvcrt!free` at `0x180005860`
- `KERNEL32!DeleteCriticalSection` at `0x180005857`
- `KERNEL32!DeleteCriticalSection` at `0x180005857`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactorySingleton<DataStoreComServer>>::Release(
        char *Block,
        __int64 a2)
{
  signed __int32 i; // ecx
  unsigned __int32 v4; // edi
  __int64 v5; // rcx

  for ( i = *((_DWORD *)Block + 2); i != 0x7FFFFFFF; i = *((_DWORD *)Block + 2) )
  {
    a2 = (unsigned int)(i - 1);
    if ( i == _InterlockedCompareExchange((volatile signed __int32 *)Block + 2, a2, i) )
      break;
  }
  v4 = i - 1;
  if ( i == 1 )
  {
    if ( Block )
    {
      *((_DWORD *)Block + 2) = -1073741823;
      *(_QWORD *)Block = &ATL::CComClassFactorySingleton<DataStoreComServer>::`vftable';
      v5 = *((_QWORD *)Block + 10);
      if ( v5 )
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v5 + 16LL))(v5, a2, 0x7FFFFFFF);
      *(_QWORD *)Block = &ATL::CComClassFactory::`vftable';
      if ( Block[56] )
      {
        Block[56] = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 16));
      }
      free(Block);
    }
  }
  else if ( i == 2 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *, _QWORD, __int64))(*(_QWORD *)ATL::_pAtlModule + 16LL))(
      ATL::_pAtlModule,
      *(_QWORD *)ATL::_pAtlModule,
      0x7FFFFFFF);
  }
  return v4;
}

```

## disassembly

```asm
0x1800057e0  mov     [rsp+arg_0], rbx
0x1800057e5  push    rdi
0x1800057e6  sub     rsp, 20h
0x1800057ea  mov     rbx, rcx
0x1800057ed  mov     ecx, [rcx+8]
0x1800057f0  mov     r8d, 7FFFFFFFh
0x1800057f6  jmp     short loc_180005807
0x1800057f8  lea     edx, [rcx-1]
0x1800057fb  mov     eax, ecx
0x1800057fd  lock cmpxchg [rbx+8], edx
0x180005802  jz      short loc_18000580C
0x180005804  mov     ecx, [rbx+8]
0x180005807  cmp     ecx, r8d
0x18000580a  jnz     short loc_1800057F8
0x18000580c  lea     edi, [rcx-1]
0x18000580f  test    edi, edi
0x180005811  jnz     short loc_180005868
0x180005813  test    rbx, rbx
0x180005816  jz      short loc_180005880
0x180005818  mov     dword ptr [rbx+8], 0C0000001h
0x18000581f  lea     rax, ??_7?$CComClassFactorySingleton@VDataStoreComServer@@@ATL@@6B@; const ATL::CComClassFactorySingleton<DataStoreComServer>::`vftable'
0x180005826  mov     [rbx], rax
0x180005829  mov     rcx, [rbx+50h]
0x18000582d  test    rcx, rcx
0x180005830  jz      short loc_18000583F
0x180005832  mov     rax, [rcx]
0x180005835  mov     rax, [rax+10h]
0x180005839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000583e  nop
0x18000583f  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180005846  mov     [rbx], rax
0x180005849  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000584d  cmp     byte ptr [rcx+28h], 0
0x180005851  jz      short loc_18000585D
0x180005853  mov     byte ptr [rcx+28h], 0
0x180005857  call    cs:__imp_DeleteCriticalSection
0x18000585d  mov     rcx, rbx; Block
0x180005860  call    cs:__imp_free
0x180005866  jmp     short loc_180005880
0x180005868  cmp     edi, 1
0x18000586b  jnz     short loc_180005880
0x18000586d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005874  mov     rdx, [rcx]
0x180005877  mov     rax, [rdx+10h]
0x18000587b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005880  mov     eax, edi
0x180005882  mov     rbx, [rsp+28h+arg_0]
0x180005887  add     rsp, 20h
0x18000588b  pop     rdi
0x18000588c  retn
```
