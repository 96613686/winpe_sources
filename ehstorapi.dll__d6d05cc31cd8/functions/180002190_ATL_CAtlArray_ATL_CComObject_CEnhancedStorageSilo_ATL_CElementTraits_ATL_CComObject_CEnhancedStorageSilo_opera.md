# ATL::CAtlArray<ATL::CComObject<CEnhancedStorageSilo> *,ATL::CElementTraits<ATL::CComObject<CEnhancedStorageSilo> *>>::operator[](unsigned __int64)

- ea: `0x180002190`
- end: `0x1800021b1`
- name: `??A?$CAtlArray@PEAV?$CComObject@VCEnhancedStorageSilo@@@ATL@@V?$CElementTraits@PEAV?$CComObject@VCEnhancedStorageSilo@@@ATL@@@2@@ATL@@QEAAAEAPEAV?$CComObject@VCEnhancedStorageSilo@@@1@_K@Z`
- size: `33`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002360`
- `0x1800025dc`
- `0x180002a60`
- `0x180003a80`

## callees

- `0x180002190`
- `0x180002338`

## pseudocode

```c
__int64 __fastcall ATL::CAtlArray<ATL::CComObject<CEnhancedStorageSilo> *,ATL::CElementTraits<ATL::CComObject<CEnhancedStorageSilo> *>>::operator[](
        _QWORD *a1,
        unsigned __int64 a2)
{
  if ( a2 >= a1[1] )
    ATL::AtlThrowImpl(-2147024809);
  return *a1 + 8 * a2;
}

```

## disassembly

```asm
0x180002190  sub     rsp, 28h
0x180002194  cmp     rdx, [rcx+8]
0x180002198  jb      short loc_1800021A5
0x18000219a  mov     ecx, 80070057h; int
0x18000219f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800021a5  mov     rax, [rcx]
0x1800021a8  lea     rax, [rax+rdx*8]
0x1800021ac  add     rsp, 28h
0x1800021b0  retn
```
