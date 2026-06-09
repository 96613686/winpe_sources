# ATL::CComObject<ATL::CComEnum<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>,ATL::CComMultiThreadModel>>::CComObject<ATL::CComEnum<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>,ATL::CComMultiThreadModel>>(void *)

- ea: `0x18000b10c`
- end: `0x18000b19d`
- name: `??0?$CComObject@V?$CComEnum@UIEnumDiscMasterFormats@@$1?IID_IEnumDiscMasterFormats@@3U_GUID@@BU3@V?$_Copy@U_GUID@@@ATL@@VCComMultiThreadModel@5@@ATL@@@ATL@@QEAA@PEAX@Z`
- size: `145`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b8f0`
- `0x18000bc60`

## callees

- `0x180002ac4`
- `0x180002f5c`
- `0x18000b10c`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<ATL::CComEnum<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>,ATL::CComMultiThreadModel>>::CComObject<ATL::CComEnum<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>,ATL::CComMultiThreadModel>>(
        __int64 a1)
{
  __int64 v2; // rcx
  int v3; // eax
  ATL::CAtlModule *v4; // rcx

  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_DWORD *)(a1 + 40) = 0;
  *(_DWORD *)(a1 + 48) = 0;
  *(_OWORD *)(a1 + 56) = 0;
  *(_OWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_BYTE *)(a1 + 96) = 0;
  v2 = a1 + 104;
  *(_OWORD *)v2 = 0;
  *(_OWORD *)(v2 + 16) = 0;
  *(_QWORD *)(v2 + 32) = 0;
  v3 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)v2);
  if ( v3 < 0 )
    ATL::AtlThrowImpl(v3);
  v4 = ATL::_pAtlModule;
  *(_QWORD *)a1 = &ATL::CComObject<ATL::CComEnum<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>,ATL::CComMultiThreadModel>>::`vftable';
  (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)v4 + 8LL))(v4);
  return a1;
}

```

## disassembly

```asm
0x18000b10c  push    rbx
0x18000b10e  sub     rsp, 20h
0x18000b112  mov     qword ptr [rcx+8], 0
0x18000b11a  xorps   xmm0, xmm0
0x18000b11d  mov     qword ptr [rcx+20h], 0
0x18000b125  xor     eax, eax
0x18000b127  mov     qword ptr [rcx+18h], 0
0x18000b12f  mov     rbx, rcx
0x18000b132  mov     qword ptr [rcx+10h], 0
0x18000b13a  mov     dword ptr [rcx+28h], 0
0x18000b141  mov     dword ptr [rcx+30h], 0
0x18000b148  movups  xmmword ptr [rcx+38h], xmm0
0x18000b14c  movups  xmmword ptr [rcx+48h], xmm0
0x18000b150  mov     [rcx+58h], rax
0x18000b154  mov     [rcx+60h], al
0x18000b157  add     rcx, 68h ; 'h'; this
0x18000b15b  movups  xmmword ptr [rcx], xmm0
0x18000b15e  movups  xmmword ptr [rcx+10h], xmm0
0x18000b162  mov     [rcx+20h], rax
0x18000b166  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000b16b  test    eax, eax
0x18000b16d  js      short loc_18000B195
0x18000b16f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000b176  lea     rax, ??_7?$CComObject@V?$CComEnum@UIEnumDiscMasterFormats@@$1?IID_IEnumDiscMasterFormats@@3U_GUID@@BU3@V?$_Copy@U_GUID@@@ATL@@VCComMultiThreadModel@5@@ATL@@@ATL@@6B@; const ATL::CComObject<ATL::CComEnum<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>,ATL::CComMultiThreadModel>>::`vftable'
0x18000b17d  mov     [rbx], rax
0x18000b180  mov     rax, [rcx]
0x18000b183  mov     rax, [rax+8]
0x18000b187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b18c  mov     rax, rbx
0x18000b18f  add     rsp, 20h
0x18000b193  pop     rbx
0x18000b194  retn
0x18000b195  mov     ecx, eax; int
0x18000b197  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
