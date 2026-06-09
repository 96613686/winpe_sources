# operator new(unsigned __int64)

- ea: `0x180006ec0`
- end: `0x180006ef5`
- name: `??2@YAPEAX_K@Z`
- size: `53`
- prototype: `void *__fastcall(SIZE_T uBytes)`
- caller_count: `51`
- callee_count: `3`
- tags: ``

## callers

- `0x180005ebc`
- `0x180006a38`
- `0x180006fb8`
- `0x18000729c`
- `0x180007614`
- `0x180008060`
- `0x180009b34`
- `0x18000a640`
- `0x18000aa00`
- `0x18000ab10`
- `0x18000b52c`
- `0x18000b8fc`
- `0x18000c01c`
- `0x18000c224`
- `0x18000c8c4`
- `0x18000e918`
- `0x18000f994`
- `0x18000ff40`
- `0x18001003c`
- `0x1800108c0`
- `0x180010db0`
- `0x180011500`
- `0x180011790`
- `0x180011a10`
- `0x18001270c`
- `0x1800130ac`
- `0x180013468`
- `0x180013b8c`
- `0x180014b80`
- `0x180015440`
- `0x180015694`
- `0x180016120`
- `0x180016340`
- `0x1800170dc`
- `0x180017edc`
- `0x180018a68`
- `0x1800190e4`
- `0x180019500`
- `0x180019d74`
- `0x180019dd0`
- `0x180019fb0`
- `0x18001a09c`
- `0x18001a15c`
- `0x18001a1f4`
- `0x18001a274`
- `0x18001a30c`
- `0x18001a49c`
- `0x18001a5f0`
- `0x18001acac`
- `0x18001bb38`

## callees

- `0x180006ea4`
- `0x180006ec0`
- `0x18001ce34`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006ec9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006ec9`

## pseudocode

```c
HLOCAL __fastcall operator new(SIZE_T uBytes)
{
  HLOCAL result; // rax
  char pExceptionObject; // [rsp+38h] [rbp+10h] BYREF

  result = LocalAlloc(0, uBytes);
  if ( !result )
  {
    CAllocException::CAllocException((CAllocException *)&pExceptionObject);
    throw (CAllocException *)&pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180006ec0  sub     rsp, 28h
0x180006ec4  mov     rdx, rcx; uBytes
0x180006ec7  xor     ecx, ecx; uFlags
0x180006ec9  call    cs:__imp_LocalAlloc
0x180006ecf  test    rax, rax
0x180006ed2  jz      short loc_180006ED9
0x180006ed4  add     rsp, 28h
0x180006ed8  retn
0x180006ed9  lea     rcx, [rsp+28h+pExceptionObject]; this
0x180006ede  call    ??0CAllocException@@QEAA@XZ; CAllocException::CAllocException(void)
0x180006ee3  lea     rdx, _TI3?AVCAllocException@@; pThrowInfo
0x180006eea  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180006eef  call    _CxxThrowException_0
```
