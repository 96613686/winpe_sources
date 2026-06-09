# DiscpFreeTargetAddress

- ea: `0x180006870`
- end: `0x1800068c4`
- name: `DiscpFreeTargetAddress`
- size: `84`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180007a94`
- `0x18000eeb0`
- `0x18000f280`
- `0x18000f388`
- `0x180010770`

## callees

- `0x180006870`

## import_xrefs

- `ISCSIUM!DiscpFreeMemory` at `0x180006882`
- `ISCSIUM!DiscpFreeMemory` at `0x1800068aa`
- `ISCSIUM!DiscpFreeMemory` at `0x180006882`
- `ISCSIUM!DiscpFreeMemory` at `0x1800068aa`

## pseudocode

```c
__int64 __fastcall DiscpFreeTargetAddress(__int64 *a1)
{
  __int64 v2; // rcx
  __int64 *v3; // rax
  __int64 **v4; // rcx
  __int64 result; // rax

  v2 = a1[11];
  if ( v2 )
    DiscpFreeMemory(v2);
  if ( (*((_BYTE *)a1 + 20) & 1) != 0 )
  {
    v3 = (__int64 *)*a1;
    if ( *(__int64 **)(*a1 + 8) != a1 || (v4 = (__int64 **)a1[1], *v4 != a1) )
      __fastfail(3u);
    *v4 = v3;
    v3[1] = (__int64)v4;
  }
  result = DiscpFreeMemory(a1);
  _InterlockedDecrement(&TargetAddressCount);
  return result;
}

```

## disassembly

```asm
0x180006870  push    rbx
0x180006872  sub     rsp, 20h
0x180006876  mov     rbx, rcx
0x180006879  mov     rcx, [rcx+58h]
0x18000687d  test    rcx, rcx
0x180006880  jz      short loc_180006888
0x180006882  call    cs:__imp_DiscpFreeMemory
0x180006888  test    byte ptr [rbx+14h], 1
0x18000688c  jz      short loc_1800068A7
0x18000688e  mov     rax, [rbx]
0x180006891  cmp     [rax+8], rbx
0x180006895  jnz     short loc_1800068BD
0x180006897  mov     rcx, [rbx+8]
0x18000689b  cmp     [rcx], rbx
0x18000689e  jnz     short loc_1800068BD
0x1800068a0  mov     [rcx], rax
0x1800068a3  mov     [rax+8], rcx
0x1800068a7  mov     rcx, rbx
0x1800068aa  call    cs:__imp_DiscpFreeMemory
0x1800068b0  lock dec cs:TargetAddressCount
0x1800068b7  add     rsp, 20h
0x1800068bb  pop     rbx
0x1800068bc  retn
0x1800068bd  mov     ecx, 3
0x1800068c2  int     29h; Win8: RtlFailFast(ecx)
```
