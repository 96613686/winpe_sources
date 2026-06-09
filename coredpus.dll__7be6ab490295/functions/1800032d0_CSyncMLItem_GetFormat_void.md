# CSyncMLItem::GetFormat(void)

- ea: `0x1800032d0`
- end: `0x18000331e`
- name: `?GetFormat@CSyncMLItem@@QEBA?AW4ConfigDataType@@XZ`
- size: `78`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180010654`
- `0x18001e454`
- `0x18001ef60`
- `0x1800212c8`

## callees

- `0x1800032d0`
- `0x180003330`
- `0x180003350`

## pseudocode

```c
__int64 __fastcall CSyncMLItem::GetFormat(__int64 a1)
{
  __int64 i; // rax
  unsigned int v2; // eax
  CSyncMLMeta *v3; // r9

  if ( *(_QWORD *)(a1 + 16) )
  {
LABEL_6:
    v2 = CSyncMLMeta::SyncMLPropToIndex(0);
    return (__int64)CSyncMLMeta::GetPropertyEx(v3, v2, (void *)1);
  }
  else
  {
    for ( i = *(_QWORD *)(a1 + 8); i; i = *(_QWORD *)(i + 136) )
    {
      if ( *(_QWORD *)(i + 96) )
        goto LABEL_6;
    }
    return 1;
  }
}

```

## disassembly

```asm
0x1800032d0  sub     rsp, 28h
0x1800032d4  mov     r9, [rcx+10h]
0x1800032d8  test    r9, r9
0x1800032db  jnz     short loc_1800032F8
0x1800032dd  mov     rax, [rcx+8]
0x1800032e1  test    rax, rax
0x1800032e4  jz      short loc_180003313
0x1800032e6  mov     r9, [rax+60h]
0x1800032ea  test    r9, r9
0x1800032ed  jnz     short loc_1800032F8
0x1800032ef  mov     rax, [rax+88h]
0x1800032f6  jmp     short loc_1800032E1
0x1800032f8  xor     ecx, ecx
0x1800032fa  call    ?SyncMLPropToIndex@CSyncMLMeta@@CAKW4SyncMLProp@@@Z; CSyncMLMeta::SyncMLPropToIndex(SyncMLProp)
0x1800032ff  mov     edx, eax; unsigned int
0x180003301  mov     r8d, 1; void *
0x180003307  mov     rcx, r9; this
0x18000330a  add     rsp, 28h
0x18000330e  jmp     ?GetPropertyEx@CSyncMLMeta@@AEBAPEAXKPEAX@Z; CSyncMLMeta::GetPropertyEx(ulong,void *)
0x180003313  mov     eax, 1
0x180003318  add     rsp, 28h
0x18000331c  retn
```
