# tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),-1>::_Delete(void)

- ea: `0x18000f1a0`
- end: `0x18000f1b8`
- name: `?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0?0@tlx@@AEAAXXZ`
- size: `24`
- prototype: `BOOL __fastcall(HANDLE *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c704`
- `0x18000c930`
- `0x18000ca4c`
- `0x18000d3e4`
- `0x1800125c4`
- `0x18001a6f0`
- `0x18001a7cc`
- `0x18001ab6c`

## callees

- `0x18000f1a0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f1ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f1ad`

## pseudocode

```c
BOOL __fastcall tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),-1>::_Delete(HANDLE *a1)
{
  BOOL result; // eax

  if ( *a1 != (HANDLE)-1LL )
    return CloseHandle(*a1);
  return result;
}

```

## disassembly

```asm
0x18000f1a0  sub     rsp, 28h
0x18000f1a4  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x18000f1a8  jz      short loc_18000F1B3
0x18000f1aa  mov     rcx, [rcx]; hObject
0x18000f1ad  call    cs:__imp_CloseHandle
0x18000f1b3  add     rsp, 28h
0x18000f1b7  retn
```
