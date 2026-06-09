# SmartPtr<DrFile>::~SmartPtr<DrFile>(void)

- ea: `0x1400016a0`
- end: `0x1400016d4`
- name: `??1?$SmartPtr@VDrFile@@@@QEAA@XZ`
- size: `52`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `61`
- callee_count: `2`
- tags: ``

## callers

- `0x1400010fc`
- `0x140001350`
- `0x140004024`
- `0x1400054f0`
- `0x140011010`
- `0x140012330`
- `0x1400125e0`
- `0x1400127a0`
- `0x140012f40`
- `0x140012ff0`
- `0x1400131e0`
- `0x1400137c0`
- `0x140013e70`
- `0x140014360`
- `0x140014b40`
- `0x140014bf0`
- `0x140014ca0`
- `0x140014d50`
- `0x1400152a0`
- `0x1400154a0`
- `0x140015830`
- `0x140015c50`
- `0x140016130`
- `0x14001652c`
- `0x1400166b4`
- `0x140016fb0`
- `0x140017040`
- `0x1400170d0`
- `0x140017190`
- `0x140017220`
- `0x1400172d0`
- `0x1400173c0`
- `0x140017450`
- `0x140017bf0`
- `0x140017f90`
- `0x140019720`
- `0x140019aa4`
- `0x14001ac10`
- `0x14001bcb0`
- `0x14001bf2c`
- `0x14001d938`
- `0x14001d9d4`
- `0x14001dafc`
- `0x14001dc18`
- `0x14001e900`
- `0x14001ec90`
- `0x14001eeb0`
- `0x14001f310`
- `0x14001f5fc`
- `0x14001f710`

## callees

- `0x1400016a0`
- `0x140006560`

## pseudocode

```c
__int64 __fastcall SmartPtr<DrFile>::~SmartPtr<DrFile>(volatile signed __int32 **a1)
{
  volatile signed __int32 *v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
  {
    result = (unsigned int)_InterlockedExchangeAdd(v1 + 4, 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
      return (*(__int64 (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v1 + 16LL))(v1, 1);
  }
  return result;
}

```

## disassembly

```asm
0x1400016a0  sub     rsp, 28h
0x1400016a4  mov     rcx, [rcx]
0x1400016a7  test    rcx, rcx
0x1400016aa  jz      short loc_1400016BB
0x1400016ac  mov     eax, 0FFFFFFFFh
0x1400016b1  lock xadd [rcx+10h], eax
0x1400016b6  cmp     eax, 1
0x1400016b9  jz      short loc_1400016C1
0x1400016bb  add     rsp, 28h
0x1400016bf  retn
0x1400016c1  mov     rax, [rcx]
0x1400016c4  mov     edx, 1
0x1400016c9  mov     rax, [rax+10h]
0x1400016cd  call    _guard_dispatch_icall
0x1400016d2  jmp     short loc_1400016BB
```
