# CILogCreateStorage2W::CreateStorage(ushort *,ulong,ulong,int,uint,uint,uint)

- ea: `0x1800022f0`
- end: `0x180002361`
- name: `?CreateStorage@CILogCreateStorage2W@@UEAAJPEAGKKHIII@Z`
- size: `113`
- prototype: `__int64 __fastcall(CLogMgr **this, unsigned __int16 *, unsigned int, unsigned int, int, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800022f0`
- `0x1800065c8`

## pseudocode

```c
__int64 __fastcall CILogCreateStorage2W::CreateStorage(
        CLogMgr **this,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8)
{
  unsigned int v9; // [rsp+80h] [rbp+18h] BYREF

  v9 = a3;
  if ( a3 && a2 )
    return CLogMgr::Init(this[1], 1, &v9, 0, a2, a4, a5, a6, a7, a8, 0xC8u);
  else
    return 2147942487LL;
}

```

## disassembly

```asm
0x1800022f0  mov     r11, rsp
0x1800022f3  mov     [r11+18h], r8d
0x1800022f7  sub     rsp, 68h
0x1800022fb  test    r8d, r8d
0x1800022fe  jz      short loc_180002357
0x180002300  test    rdx, rdx
0x180002303  jz      short loc_180002357
0x180002305  mov     eax, [rsp+68h+arg_38]
0x18000230c  lea     r8, [r11+18h]; unsigned int *
0x180002310  mov     rcx, [rcx+8]; this
0x180002314  mov     [rsp+68h+var_18], 0C8h; unsigned int
0x18000231c  mov     [rsp+68h+var_20], eax; unsigned int
0x180002320  mov     eax, [rsp+68h+arg_30]
0x180002327  mov     [rsp+68h+var_28], eax; unsigned int
0x18000232b  mov     eax, [rsp+68h+arg_28]
0x180002332  mov     [rsp+68h+var_30], eax; unsigned int
0x180002336  mov     eax, [rsp+68h+arg_20]
0x18000233d  mov     [rsp+68h+var_38], eax; int
0x180002341  mov     [r11-40h], r9d
0x180002345  xor     r9d, r9d; unsigned int *
0x180002348  mov     [r11-48h], rdx
0x18000234c  lea     edx, [r9+1]; int
0x180002350  call    ?Init@CLogMgr@@IEAAJHPEAK0PEAGKHIIII@Z; CLogMgr::Init(int,ulong *,ulong *,ushort *,ulong,int,uint,uint,uint,uint)
0x180002355  jmp     short loc_18000235C
0x180002357  mov     eax, 80070057h
0x18000235c  add     rsp, 68h
0x180002360  retn
```
