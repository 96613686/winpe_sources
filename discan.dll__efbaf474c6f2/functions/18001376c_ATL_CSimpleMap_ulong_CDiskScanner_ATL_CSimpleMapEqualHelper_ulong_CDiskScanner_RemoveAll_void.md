# ATL::CSimpleMap<ulong,CDiskScanner *,ATL::CSimpleMapEqualHelper<ulong,CDiskScanner *>>::RemoveAll(void)

- ea: `0x18001376c`
- end: `0x1800137b7`
- name: `?RemoveAll@?$CSimpleMap@KPEAVCDiskScanner@@V?$CSimpleMapEqualHelper@KPEAVCDiskScanner@@@ATL@@@ATL@@QEAAXXZ`
- size: `75`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180013760`
- `0x180013948`
- `0x180016a74`
- `0x180037de2`

## callees

- `0x18001376c`

## import_xrefs

- `msvcrt!free` at `0x180013781`
- `msvcrt!free` at `0x180013797`
- `msvcrt!free` at `0x180013781`
- `msvcrt!free` at `0x180013797`

## pseudocode

```c
void __fastcall ATL::CSimpleMap<unsigned long,CDiskScanner *,ATL::CSimpleMapEqualHelper<unsigned long,CDiskScanner *>>::RemoveAll(
        __int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    free(v2);
    *(_QWORD *)a1 = 0;
  }
  v3 = *(void **)(a1 + 8);
  if ( v3 )
  {
    free(v3);
    *(_QWORD *)(a1 + 8) = 0;
  }
  *(_DWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x18001376c  mov     [rsp+arg_0], rbx
0x180013771  push    rdi
0x180013772  sub     rsp, 20h
0x180013776  mov     rbx, rcx
0x180013779  mov     rcx, [rcx]; Block
0x18001377c  test    rcx, rcx
0x18001377f  jz      short loc_18001378E
0x180013781  call    cs:__imp_free
0x180013787  mov     qword ptr [rbx], 0
0x18001378e  mov     rcx, [rbx+8]; Block
0x180013792  test    rcx, rcx
0x180013795  jz      short loc_1800137A5
0x180013797  call    cs:__imp_free
0x18001379d  mov     qword ptr [rbx+8], 0
0x1800137a5  mov     dword ptr [rbx+10h], 0
0x1800137ac  mov     rbx, [rsp+28h+arg_0]
0x1800137b1  add     rsp, 20h
0x1800137b5  pop     rdi
0x1800137b6  retn
```
