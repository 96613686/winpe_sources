# BinaryLogReader_Core_Cleanup

- ea: `0x180029720`
- end: `0x1800297a0`
- name: `BinaryLogReader_Core_Cleanup`
- size: `128`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180025e90`
- `0x180025f40`
- `0x1800298c0`

## callees

- `0x18000af38`
- `0x180029720`
- `0x180029adc`
- `0x180043cd8`

## import_xrefs

- `msvcrt!_close` at `0x180029731`
- `msvcrt!_close` at `0x180029731`
- `msvcrt!free` at `0x18002974c`
- `msvcrt!free` at `0x180029764`
- `msvcrt!free` at `0x180029785`
- `msvcrt!free` at `0x180029794`
- `msvcrt!free` at `0x18002974c`
- `msvcrt!free` at `0x180029764`
- `msvcrt!free` at `0x180029785`
- `msvcrt!free` at `0x180029794`

## pseudocode

```c
void __fastcall BinaryLogReader_Core_Cleanup(__int64 a1)
{
  int v2; // ecx
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  void *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  void *v9; // rcx

  v2 = *(_DWORD *)(a1 + 4);
  if ( v2 != -1 )
  {
    _close(v2);
    *(_DWORD *)(a1 + 4) = -1;
    trace_BinLogWriter_ClosedLogFile(v4, v3, v5);
  }
  v6 = *(void **)(a1 + 56);
  if ( v6 )
    free(v6);
  v7 = *(_QWORD *)(a1 + 32);
  if ( v7 )
  {
    HashMap_Destroy(v7);
    free(*(void **)(a1 + 32));
  }
  DeleteClassesFromMOF(*(void **)(a1 + 72));
  v8 = *(_QWORD *)(a1 + 80);
  if ( v8 )
  {
    HashMap_Destroy(v8);
    free(*(void **)(a1 + 80));
  }
  v9 = *(void **)(a1 + 88);
  if ( v9 )
    free(v9);
}

```

## disassembly

```asm
0x180029720  push    rbx
0x180029722  sub     rsp, 20h
0x180029726  mov     rbx, rcx
0x180029729  mov     ecx, [rcx+4]; FileHandle
0x18002972c  cmp     ecx, 0FFFFFFFFh
0x18002972f  jz      short loc_180029743
0x180029731  call    cs:__imp__close
0x180029737  mov     dword ptr [rbx+4], 0FFFFFFFFh
0x18002973e  call    trace_BinLogWriter_ClosedLogFile
0x180029743  mov     rcx, [rbx+38h]; Block
0x180029747  test    rcx, rcx
0x18002974a  jz      short loc_180029752
0x18002974c  call    cs:__imp_free
0x180029752  mov     rcx, [rbx+20h]
0x180029756  test    rcx, rcx
0x180029759  jz      short loc_18002976A
0x18002975b  call    HashMap_Destroy
0x180029760  mov     rcx, [rbx+20h]; Block
0x180029764  call    cs:__imp_free
0x18002976a  mov     rcx, [rbx+48h]; Block
0x18002976e  call    DeleteClassesFromMOF
0x180029773  mov     rcx, [rbx+50h]
0x180029777  test    rcx, rcx
0x18002977a  jz      short loc_18002978B
0x18002977c  call    HashMap_Destroy
0x180029781  mov     rcx, [rbx+50h]; Block
0x180029785  call    cs:__imp_free
0x18002978b  mov     rcx, [rbx+58h]; Block
0x18002978f  test    rcx, rcx
0x180029792  jz      short loc_18002979A
0x180029794  call    cs:__imp_free
0x18002979a  add     rsp, 20h
0x18002979e  pop     rbx
0x18002979f  retn
```
