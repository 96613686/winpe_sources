# ReferenceTapiProv

- ea: `0x1400028cc`
- end: `0x14000294f`
- name: `ReferenceTapiProv`
- size: `131`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140001608`
- `0x14000e3d8`
- `0x140010e50`
- `0x14001169c`

## callees

- `0x14000110c`
- `0x14000113c`
- `0x1400028cc`

## pseudocode

```c
__int64 __fastcall ReferenceTapiProv(__int64 a1)
{
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      result = WPP_SF_(
                 (__int64)WPP_GLOBAL_Control->AttachedDevice,
                 0xAu,
                 (__int64)WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids);
  }
  ++*(_DWORD *)(a1 + 80);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      return WPP_SF_d(
               (__int64)WPP_GLOBAL_Control->AttachedDevice,
               0xBu,
               (__int64)WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids,
               *(_DWORD *)(a1 + 80));
  }
  return result;
}

```

## disassembly

```asm
0x1400028cc  mov     [rsp+arg_0], rbx
0x1400028d1  push    rdi
0x1400028d2  sub     rsp, 20h
0x1400028d6  mov     rbx, rcx
0x1400028d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400028e0  lea     rdi, WPP_GLOBAL_Control
0x1400028e7  cmp     rcx, rdi
0x1400028ea  jz      short loc_14000290E
0x1400028ec  mov     eax, [rcx+2Ch]
0x1400028ef  test    al, 2
0x1400028f1  jz      short loc_14000290E
0x1400028f3  cmp     byte ptr [rcx+29h], 4
0x1400028f7  jb      short loc_14000290E
0x1400028f9  mov     rcx, [rcx+18h]
0x1400028fd  lea     r8, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids
0x140002904  mov     edx, 0Ah
0x140002909  call    WPP_SF_
0x14000290e  inc     dword ptr [rbx+50h]
0x140002911  mov     r9d, [rbx+50h]
0x140002915  mov     rcx, cs:WPP_GLOBAL_Control
0x14000291c  cmp     rcx, rdi
0x14000291f  jz      short loc_140002943
0x140002921  mov     eax, [rcx+2Ch]
0x140002924  test    al, 2
0x140002926  jz      short loc_140002943
0x140002928  cmp     byte ptr [rcx+29h], 4
0x14000292c  jb      short loc_140002943
0x14000292e  mov     rcx, [rcx+18h]
0x140002932  lea     r8, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids
0x140002939  mov     edx, 0Bh
0x14000293e  call    WPP_SF_d
0x140002943  mov     rbx, [rsp+28h+arg_0]
0x140002948  add     rsp, 20h
0x14000294c  pop     rdi
0x14000294d  retn
```
