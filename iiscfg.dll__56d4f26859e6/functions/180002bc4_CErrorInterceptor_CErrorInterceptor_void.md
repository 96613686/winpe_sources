# CErrorInterceptor::~CErrorInterceptor(void)

- ea: `0x180002bc4`
- end: `0x180002bea`
- name: `??1CErrorInterceptor@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(CErrorInterceptor *__hidden this)`
- caller_count: `44`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800043f0`
- `0x180005cb8`
- `0x180005fdc`
- `0x180006750`
- `0x180009acc`
- `0x180009e84`
- `0x18000a1c8`
- `0x18000a9b4`
- `0x18000ce00`
- `0x18000d110`
- `0x180015f34`
- `0x180017e84`
- `0x180019128`
- `0x1800199c8`
- `0x180019f9c`
- `0x18001b188`
- `0x18001b82c`
- `0x18001bd60`
- `0x18001c86c`
- `0x18001d2a0`
- `0x18001d604`
- `0x18001da08`
- `0x18001dd08`
- `0x1800234ac`
- `0x180028868`
- `0x18002e6f3`
- `0x18002e73b`
- `0x18002e74d`
- `0x18002e75f`
- `0x18002e771`
- `0x18002e783`
- `0x18002e795`
- `0x18002e7d1`
- `0x18002e807`
- `0x18002e8bb`
- `0x18002e903`
- `0x18002e915`
- `0x18002e927`
- `0x18002e939`
- `0x18002e94b`
- `0x18002e95d`
- `0x18002e96f`
- `0x18002ea23`
- `0x18002ea35`

## callees

- `0x180002bc4`
- `0x180002c4c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180002bde`
- `ole32!CoTaskMemFree` at `0x180002bde`

## pseudocode

```c
void __fastcall CErrorInterceptor::~CErrorInterceptor(CErrorInterceptor *this)
{
  void *v1; // rbx

  v1 = (void *)*((_QWORD *)this + 1);
  if ( v1 )
  {
    CErrorInterceptor::ErrorInterceptorStorage::~ErrorInterceptorStorage(*((CErrorInterceptor::ErrorInterceptorStorage **)this
                                                                         + 1));
    CoTaskMemFree(v1);
  }
}

```

## disassembly

```asm
0x180002bc4  push    rbx
0x180002bc6  sub     rsp, 20h
0x180002bca  mov     rbx, [rcx+8]
0x180002bce  test    rbx, rbx
0x180002bd1  jz      short loc_180002BE4
0x180002bd3  mov     rcx, rbx; this
0x180002bd6  call    ??1ErrorInterceptorStorage@CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::ErrorInterceptorStorage::~ErrorInterceptorStorage(void)
0x180002bdb  mov     rcx, rbx; pv
0x180002bde  call    cs:__imp_CoTaskMemFree
0x180002be4  add     rsp, 20h
0x180002be8  pop     rbx
0x180002be9  retn
```
