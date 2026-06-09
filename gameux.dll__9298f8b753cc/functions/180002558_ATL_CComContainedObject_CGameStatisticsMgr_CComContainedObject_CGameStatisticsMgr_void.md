# ATL::CComContainedObject<CGameStatisticsMgr>::CComContainedObject<CGameStatisticsMgr>(void *)

- ea: `0x180002558`
- end: `0x180002577`
- name: `??0?$CComContainedObject@VCGameStatisticsMgr@@@ATL@@QEAA@PEAX@Z`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002864`

## callees

- `0x18000259c`

## pseudocode

```c
_QWORD *__fastcall ATL::CComContainedObject<CGameStatisticsMgr>::CComContainedObject<CGameStatisticsMgr>(
        CGameStatisticsMgr *a1)
{
  __int64 v1; // rdx
  _QWORD *v2; // rcx

  CGameStatisticsMgr::CGameStatisticsMgr(a1);
  v2[1] = v1;
  *v2 = &ATL::CComContainedObject<CGameStatisticsMgr>::`vftable';
  return v2;
}

```

## disassembly

```asm
0x180002558  sub     rsp, 28h
0x18000255c  call    ??0CGameStatisticsMgr@@QEAA@XZ; CGameStatisticsMgr::CGameStatisticsMgr(void)
0x180002561  lea     r8, ??_7?$CComContainedObject@VCGameStatisticsMgr@@@ATL@@6B@; const ATL::CComContainedObject<CGameStatisticsMgr>::`vftable'
0x180002568  mov     [rcx+8], rdx
0x18000256c  mov     [rcx], r8
0x18000256f  mov     rax, rcx
0x180002572  add     rsp, 28h
0x180002576  retn
```
