# CService::Close(void)

- ea: `0x18003123c`
- end: `0x180031260`
- name: `?Close@CService@@QEAAXXZ`
- size: `36`
- prototype: `void __fastcall(CService *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800311e8`
- `0x1800312b4`
- `0x180031328`

## callees

- `0x18003123c`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x18003124d`
- `ADVAPI32!CloseServiceHandle` at `0x18003124d`

## pseudocode

```c
void __fastcall CService::Close(SC_HANDLE *this)
{
  SC_HANDLE v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    CloseServiceHandle(v2);
    *this = 0;
  }
}

```

## disassembly

```asm
0x18003123c  push    rbx
0x18003123e  sub     rsp, 20h
0x180031242  mov     rbx, rcx
0x180031245  mov     rcx, [rcx]; hSCObject
0x180031248  test    rcx, rcx
0x18003124b  jz      short loc_18003125A
0x18003124d  call    cs:__imp_CloseServiceHandle
0x180031253  mov     qword ptr [rbx], 0
0x18003125a  add     rsp, 20h
0x18003125e  pop     rbx
0x18003125f  retn
```
