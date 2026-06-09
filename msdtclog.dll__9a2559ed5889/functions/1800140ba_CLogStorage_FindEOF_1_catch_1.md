# _CLogStorage::_FindEOF_::_1_::catch$1

- ea: `0x1800140ba`
- end: `0x18001412c`
- name: `_CLogStorage::_FindEOF_::_1_::catch$1`
- size: `114`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000c6b8`
- `0x18000d998`
- `0x18001266c`
- `0x1800140ba`

## string_xrefs

- `0x1800140eb`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`

## pseudocode

```c
__int64 __fastcall CLogStorage::_FindEOF_::_1_::catch_1(__int64 a1, __int64 a2)
{
  LPCVOID *v3; // rdx

  if ( *(_DWORD *)(a2 + 104) )
  {
    v3 = *(LPCVOID **)(a2 + 56);
    if ( v3 )
      CLogStorage::_UnmapBuffer(*(CLogStorage **)(a2 + 224), v3, 0);
    TraceFile(-1073737670, "IDS_DTC_E_LOG_CORRUPT_ERROR", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp", 2840);
    *(_DWORD *)(a2 + 96) = -1073737670;
    throw (ulong *)(a2 + 96);
  }
  return 0;
}

```

## disassembly

```asm
0x1800140ba  mov     [rsp+arg_8], rdx
0x1800140bf  push    rbp
0x1800140c0  sub     rsp, 30h
0x1800140c4  mov     rbp, rdx
0x1800140c7  cmp     dword ptr [rbp+68h], 0
0x1800140cb  jz      short loc_18001411B
0x1800140cd  mov     rdx, [rbp+38h]; struct CBuffer *
0x1800140d1  test    rdx, rdx
0x1800140d4  jz      short loc_1800140E5
0x1800140d6  xor     r8d, r8d; int
0x1800140d9  mov     rcx, [rbp+0E0h]; this
0x1800140e0  call    ?_UnmapBuffer@CLogStorage@@AEAAXPEAVCBuffer@@H@Z; CLogStorage::_UnmapBuffer(CBuffer *,int)
0x1800140e5  mov     r9d, 0B18h; unsigned int
0x1800140eb  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x1800140f2  lea     rdx, aIdsDtcELogCorr; "IDS_DTC_E_LOG_CORRUPT_ERROR"
0x1800140f9  mov     ecx, 0C000103Ah; int
0x1800140fe  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180014103  mov     dword ptr [rbp+60h], 0C000103Ah
0x18001410a  lea     rdx, _TI1K; pThrowInfo
0x180014111  lea     rcx, [rbp+60h]; pExceptionObject
0x180014115  call    _CxxThrowException_0
0x18001411b  mov     rax, 0
0x180014125  add     rsp, 30h
0x180014129  pop     rbp
0x18001412a  retn
```
