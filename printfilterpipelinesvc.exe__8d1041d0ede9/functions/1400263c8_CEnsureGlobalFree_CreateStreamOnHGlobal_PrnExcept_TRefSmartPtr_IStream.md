# CEnsureGlobalFree::CreateStreamOnHGlobal(PrnExcept::TRefSmartPtr<IStream> &)

- ea: `0x1400263c8`
- end: `0x1400263f8`
- name: `?CreateStreamOnHGlobal@CEnsureGlobalFree@@QEAAXAEAV?$TRefSmartPtr@UIStream@@@PrnExcept@@@Z`
- size: `48`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140025b48`
- `0x140025d5c`
- `0x140025ee4`

## callees

- `0x1400263c8`
- `0x14004650c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1400263dc`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1400263dc`

## pseudocode

```c
HRESULT __fastcall CEnsureGlobalFree::CreateStreamOnHGlobal(__int64 a1, LPSTREAM *a2)
{
  HRESULT result; // eax
  int v4; // edx
  const char *v5; // r8
  unsigned int v6; // r9d

  result = CreateStreamOnHGlobal(*(HGLOBAL *)a1, 1, a2);
  if ( result < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)result, v4, v5, v6);
  *(_BYTE *)(a1 + 8) = 1;
  return result;
}

```

## disassembly

```asm
0x1400263c8  push    rbx
0x1400263ca  sub     rsp, 20h
0x1400263ce  mov     rbx, rcx
0x1400263d1  mov     r8, rdx; ppstm
0x1400263d4  mov     rcx, [rcx]; hGlobal
0x1400263d7  mov     edx, 1; fDeleteOnRelease
0x1400263dc  call    cs:__imp_CreateStreamOnHGlobal
0x1400263e2  test    eax, eax
0x1400263e4  jns     short loc_1400263EE
0x1400263e6  mov     ecx, eax; this
0x1400263e8  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1400263ee  mov     byte ptr [rbx+8], 1
0x1400263f2  add     rsp, 20h
0x1400263f6  pop     rbx
0x1400263f7  retn
```
