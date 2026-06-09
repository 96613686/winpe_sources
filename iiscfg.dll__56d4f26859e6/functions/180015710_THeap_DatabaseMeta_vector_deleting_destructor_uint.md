# THeap<DatabaseMeta>::`vector deleting destructor'(uint)

- ea: `0x180015710`
- end: `0x180015740`
- name: `??_E?$THeap@UDatabaseMeta@@@@UEAAPEAXI@Z`
- size: `48`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18001551c`
- `0x180015710`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001572c`
- `ole32!CoTaskMemFree` at `0x18001572c`

## pseudocode

```c
TBaseHeap *__fastcall THeap<DatabaseMeta>::`vector deleting destructor'(TBaseHeap *pv, char a2)
{
  TBaseHeap::~TBaseHeap(pv);
  if ( (a2 & 1) != 0 )
    CoTaskMemFree(pv);
  return pv;
}

```

## disassembly

```asm
0x180015710  mov     [rsp+arg_0], rbx
0x180015715  push    rdi
0x180015716  sub     rsp, 20h
0x18001571a  mov     ebx, edx
0x18001571c  mov     rdi, rcx
0x18001571f  call    ??1TBaseHeap@@UEAA@XZ; TBaseHeap::~TBaseHeap(void)
0x180015724  test    bl, 1
0x180015727  jz      short loc_180015732
0x180015729  mov     rcx, rdi; pv
0x18001572c  call    cs:__imp_CoTaskMemFree
0x180015732  mov     rax, rdi
0x180015735  mov     rbx, [rsp+28h+arg_0]
0x18001573a  add     rsp, 20h
0x18001573e  pop     rdi
0x18001573f  retn
```
