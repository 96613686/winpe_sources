# CFatVolume::FreeDir(_QUEUED_DIR * *)

- ea: `0x18001fed8`
- end: `0x18001ff12`
- name: `?FreeDir@CFatVolume@@AEAAXPEAPEAU_QUEUED_DIR@@@Z`
- size: `58`
- prototype: `void __fastcall(CFatVolume *__hidden this, struct _QUEUED_DIR **)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800164ac`
- `0x18001f468`
- `0x18002479c`
- `0x18003d0b0`
- `0x1800402b0`
- `0x180062bd0`

## callees

- `0x18001fed8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001feec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001feff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001feec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001feff`

## pseudocode

```c
void __fastcall CFatVolume::FreeDir(CFatVolume *this, LPVOID **a2)
{
  if ( *a2 )
  {
    CoTaskMemFree(**a2);
    **a2 = 0;
    CoTaskMemFree(*a2);
    *a2 = 0;
  }
}

```

## disassembly

```asm
0x18001fed8  push    rbx
0x18001feda  sub     rsp, 20h
0x18001fede  mov     rcx, [rdx]
0x18001fee1  mov     rbx, rdx
0x18001fee4  test    rcx, rcx
0x18001fee7  jz      short loc_18001FF0C
0x18001fee9  mov     rcx, [rcx]; pv
0x18001feec  call    cs:__imp_CoTaskMemFree
0x18001fef2  mov     rax, [rbx]
0x18001fef5  mov     qword ptr [rax], 0
0x18001fefc  mov     rcx, [rbx]; pv
0x18001feff  call    cs:__imp_CoTaskMemFree
0x18001ff05  mov     qword ptr [rbx], 0
0x18001ff0c  add     rsp, 20h
0x18001ff10  pop     rbx
0x18001ff11  retn
```
