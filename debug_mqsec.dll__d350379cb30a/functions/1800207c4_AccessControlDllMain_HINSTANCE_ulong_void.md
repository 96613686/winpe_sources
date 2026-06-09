# AccessControlDllMain(HINSTANCE__ *,ulong,void *)

- ea: `0x1800207c4`
- end: `0x1800208c5`
- name: `?AccessControlDllMain@@YAHPEAUHINSTANCE__@@KPEAX@Z`
- size: `257`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180013b18`

## callees

- `0x1800138c0`
- `0x1800207c4`
- `0x1800208cc`
- `0x1800209a8`
- `0x180025550`

## pseudocode

```c
__int64 __fastcall AccessControlDllMain(HINSTANCE a1, int a2, void *a3)
{
  if ( a2 == 1 )
  {
    if ( !InitWellKnownSIDs() )
    {
      LogIllegalPoint((wchar_t *)L"acssctrl/acssinit", 0x44Cu);
      return 0;
    }
    dword_180042F00 = 131115;
    dword_180042F20 = 131104;
    dword_180042F2C = 983095;
    dword_180042F30 = 131104;
    qword_180042F34 = 131104;
    dword_180042F4C = 983095;
    qword_180042F04 = 131108;
    dword_180042F0C = 983103;
    dword_180042F10 = 131299;
    qword_180042F14 = 131108;
    dword_180042F1C = 983287;
    qword_180042F24 = 131108;
    dword_180042F3C = 983089;
    dword_180042F40 = 131105;
    qword_180042F44 = 131111;
    dword_180042F50 = 131220;
    dword_180042F54 = 131112;
    dword_180042F58 = 131076;
    dword_180042F5C = 983551;
    InitSendAcls();
  }
  else if ( !a2 )
  {
    FreeSecurityResources();
  }
  return 1;
}

```

## disassembly

```asm
0x1800207c4  sub     rsp, 28h
0x1800207c8  cmp     edx, 1
0x1800207cb  jnz     loc_1800208B2
0x1800207d1  call    InitWellKnownSIDs
0x1800207d6  test    al, al
0x1800207d8  jnz     short loc_1800207F2
0x1800207da  mov     edx, 44Ch; unsigned __int16
0x1800207df  lea     rcx, aAcssctrlAcssin; "acssctrl/acssinit"
0x1800207e6  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x1800207eb  xor     eax, eax
0x1800207ed  jmp     loc_1800208C0
0x1800207f2  mov     eax, 20020h
0x1800207f7  mov     cs:dword_180042F00, 2002Bh
0x180020801  mov     edx, 0F0037h
0x180020806  mov     cs:dword_180042F20, eax
0x18002080c  mov     cs:dword_180042F2C, edx
0x180020812  mov     cs:dword_180042F30, eax
0x180020818  mov     cs:qword_180042F34, rax
0x18002081f  mov     cs:dword_180042F4C, edx
0x180020825  mov     cs:qword_180042F04, 20024h
0x180020830  mov     cs:dword_180042F0C, 0F003Fh
0x18002083a  mov     cs:dword_180042F10, 200E3h
0x180020844  mov     cs:qword_180042F14, 20024h
0x18002084f  mov     cs:dword_180042F1C, 0F00F7h
0x180020859  mov     cs:qword_180042F24, 20024h
0x180020864  mov     cs:dword_180042F3C, 0F0031h
0x18002086e  mov     cs:dword_180042F40, 20021h
0x180020878  mov     cs:qword_180042F44, 20027h
0x180020883  mov     cs:dword_180042F50, 20094h
0x18002088d  mov     cs:dword_180042F54, 20028h
0x180020897  mov     cs:dword_180042F58, 20004h
0x1800208a1  mov     cs:dword_180042F5C, 0F01FFh
0x1800208ab  call    ?InitSendAcls@@YAXXZ; InitSendAcls(void)
0x1800208b0  jmp     short loc_1800208BB
0x1800208b2  test    edx, edx
0x1800208b4  jnz     short loc_1800208BB
0x1800208b6  call    ?FreeSecurityResources@@YAXXZ; FreeSecurityResources(void)
0x1800208bb  mov     eax, 1
0x1800208c0  add     rsp, 28h
0x1800208c4  retn
```
