# _CLogStorage::_FindEOF_::_1_::catch$0

- ea: `0x180014042`
- end: `0x1800140b4`
- name: `_CLogStorage::_FindEOF_::_1_::catch$0`
- size: `114`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000c6b8`
- `0x18000d998`
- `0x18001266c`
- `0x180014042`

## string_xrefs

- `0x180014073`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`

## pseudocode

```c
__int64 __fastcall CLogStorage::_FindEOF_::_1_::catch_0(__int64 a1, __int64 a2)
{
  LPCVOID *v3; // rdx

  if ( *(_DWORD *)(a2 + 100) )
  {
    v3 = *(LPCVOID **)(a2 + 56);
    if ( v3 )
      CLogStorage::_UnmapBuffer(*(CLogStorage **)(a2 + 224), v3, 0);
    TraceFile(-1073737670, "IDS_DTC_E_LOG_CORRUPT_ERROR", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp", 2827);
    *(_DWORD *)(a2 + 92) = -1073737670;
    throw (ulong *)(a2 + 92);
  }
  return 0;
}

```

## disassembly

```asm
0x180014042  mov     [rsp+arg_8], rdx
0x180014047  push    rbp
0x180014048  sub     rsp, 30h
0x18001404c  mov     rbp, rdx
0x18001404f  cmp     dword ptr [rbp+64h], 0
0x180014053  jz      short loc_1800140A3
0x180014055  mov     rdx, [rbp+38h]; struct CBuffer *
0x180014059  test    rdx, rdx
0x18001405c  jz      short loc_18001406D
0x18001405e  xor     r8d, r8d; int
0x180014061  mov     rcx, [rbp+0E0h]; this
0x180014068  call    ?_UnmapBuffer@CLogStorage@@AEAAXPEAVCBuffer@@H@Z; CLogStorage::_UnmapBuffer(CBuffer *,int)
0x18001406d  mov     r9d, 0B0Bh; unsigned int
0x180014073  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18001407a  lea     rdx, aIdsDtcELogCorr; "IDS_DTC_E_LOG_CORRUPT_ERROR"
0x180014081  mov     ecx, 0C000103Ah; int
0x180014086  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18001408b  mov     dword ptr [rbp+5Ch], 0C000103Ah
0x180014092  lea     rdx, _TI1K; pThrowInfo
0x180014099  lea     rcx, [rbp+5Ch]; pExceptionObject
0x18001409d  call    _CxxThrowException_0
0x1800140a3  mov     rax, 0
0x1800140ad  add     rsp, 30h
0x1800140b1  pop     rbp
0x1800140b2  retn
```
