# CHandleT<_TP_WORK *,ThreadPoolWorkTrait>::Close(void)

- ea: `0x180003660`
- end: `0x180003694`
- name: `?Close@?$CHandleT@PEAU_TP_WORK@@UThreadPoolWorkTrait@@@@QEAAXXZ`
- size: `52`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000502c`
- `0x180014190`

## callees

- `0x180003660`

## import_xrefs

- `KERNEL32!CloseThreadpoolWork` at `0x18000367d`
- `KERNEL32!CloseThreadpoolWork` at `0x18000367d`

## pseudocode

```c
void __fastcall CHandleT<_TP_WORK *,ThreadPoolWorkTrait>::Close(__int64 a1)
{
  struct _TP_WORK *v2; // rcx

  v2 = *(struct _TP_WORK **)a1;
  if ( v2 && (!*(_BYTE *)(a1 + 12) || !*(_DWORD *)(a1 + 8)) )
  {
    CloseThreadpoolWork(v2);
    *(_QWORD *)a1 = 0;
    *(_BYTE *)(a1 + 12) = 0;
  }
}

```

## disassembly

```asm
0x180003660  push    rbx
0x180003662  sub     rsp, 20h
0x180003666  mov     rbx, rcx
0x180003669  mov     rcx, [rcx]; pwk
0x18000366c  test    rcx, rcx
0x18000366f  jz      short loc_18000368E
0x180003671  cmp     byte ptr [rbx+0Ch], 0
0x180003675  jz      short loc_18000367D
0x180003677  cmp     dword ptr [rbx+8], 0
0x18000367b  jnz     short loc_18000368E
0x18000367d  call    cs:__imp_CloseThreadpoolWork
0x180003683  mov     qword ptr [rbx], 0
0x18000368a  mov     byte ptr [rbx+0Ch], 0
0x18000368e  add     rsp, 20h
0x180003692  pop     rbx
0x180003693  retn
```
