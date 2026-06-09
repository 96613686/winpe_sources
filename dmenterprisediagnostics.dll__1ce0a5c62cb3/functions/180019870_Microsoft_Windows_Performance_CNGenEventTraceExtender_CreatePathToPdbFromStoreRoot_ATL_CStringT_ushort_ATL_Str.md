# Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_RSDS const &)

- ea: `0x180019870`
- end: `0x18001992d`
- name: `?CreatePathToPdbFromStoreRoot@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_RSDS@@@Z`
- size: `189`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180019194`
- `0x18001964c`

## callees

- `0x18000a5d4`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  int v6; // [rsp+20h] [rbp-A8h]
  int v7; // [rsp+28h] [rbp-A0h]
  int v8; // [rsp+30h] [rbp-98h]
  int v9; // [rsp+38h] [rbp-90h]
  int v10; // [rsp+40h] [rbp-88h]
  int v11; // [rsp+48h] [rbp-80h]
  int v12; // [rsp+50h] [rbp-78h]
  int v13; // [rsp+58h] [rbp-70h]
  int v14; // [rsp+60h] [rbp-68h]
  int v15; // [rsp+68h] [rbp-60h]
  int v16; // [rsp+70h] [rbp-58h]
  int v17; // [rsp+78h] [rbp-50h]

  v17 = *(_DWORD *)(a5 + 20);
  v16 = *(unsigned __int8 *)(a5 + 19);
  v15 = *(unsigned __int8 *)(a5 + 18);
  v14 = *(unsigned __int8 *)(a5 + 17);
  v13 = *(unsigned __int8 *)(a5 + 16);
  v12 = *(unsigned __int8 *)(a5 + 15);
  v11 = *(unsigned __int8 *)(a5 + 14);
  v10 = *(unsigned __int8 *)(a5 + 13);
  v9 = *(unsigned __int8 *)(a5 + 12);
  v8 = *(unsigned __int16 *)(a5 + 10);
  v7 = *(unsigned __int16 *)(a5 + 8);
  v6 = *(_DWORD *)(a5 + 4);
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
           a2,
           L"%ws\\%hs\\%08x%04x%04x%02x%02x%02x%02x%02x%02x%02x%02x%x",
           a3,
           a4,
           v6,
           v7,
           v8,
           v9,
           v10,
           v11,
           v12,
           v13,
           v14,
           v15,
           v16,
           v17);
}

```

## disassembly

```asm
0x180019870  mov     [rsp+arg_8], rdx
0x180019875  push    rbx
0x180019876  push    rbp
0x180019877  push    rsi
0x180019878  push    rdi
0x180019879  push    r12
0x18001987b  push    r13
0x18001987d  push    r14
0x18001987f  push    r15
0x180019881  sub     rsp, 88h
0x180019888  mov     r13, [rsp+0C8h+arg_20]
0x180019890  lea     rdx, aWsHs08x04x04x0; "%ws\\%hs\\%08x%04x%04x%02x%02x%02x%02x%"...
0x180019897  mov     r12, r9
0x18001989a  movzx   ecx, byte ptr [r13+13h]
0x18001989f  mov     eax, [r13+14h]
0x1800198a3  movzx   r9d, word ptr [r13+8]
0x1800198a8  movzx   r10d, byte ptr [r13+12h]
0x1800198ad  movzx   r11d, byte ptr [r13+11h]
0x1800198b2  movzx   ebx, byte ptr [r13+10h]
0x1800198b7  movzx   edi, byte ptr [r13+0Fh]
0x1800198bc  movzx   esi, byte ptr [r13+0Eh]
0x1800198c1  movzx   ebp, byte ptr [r13+0Dh]
0x1800198c6  movzx   r14d, byte ptr [r13+0Ch]
0x1800198cb  movzx   r15d, word ptr [r13+0Ah]
0x1800198d0  mov     [rsp+0C8h+var_50], eax
0x1800198d4  mov     eax, [r13+4]
0x1800198d8  mov     [rsp+0C8h+var_58], ecx
0x1800198dc  mov     rcx, [rsp+0C8h+arg_8]
0x1800198e4  mov     [rsp+0C8h+var_60], r10d
0x1800198e9  mov     [rsp+0C8h+var_68], r11d
0x1800198ee  mov     [rsp+0C8h+var_70], ebx
0x1800198f2  mov     [rsp+0C8h+var_78], edi
0x1800198f6  mov     [rsp+0C8h+var_80], esi
0x1800198fa  mov     [rsp+0C8h+var_88], ebp
0x1800198fe  mov     [rsp+0C8h+var_90], r14d
0x180019903  mov     [rsp+0C8h+var_98], r15d
0x180019908  mov     [rsp+0C8h+var_A0], r9d
0x18001990d  mov     r9, r12
0x180019910  mov     [rsp+0C8h+var_A8], eax
0x180019914  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180019919  add     rsp, 88h
0x180019920  pop     r15
0x180019922  pop     r14
0x180019924  pop     r13
0x180019926  pop     r12
0x180019928  pop     rdi
0x180019929  pop     rsi
0x18001992a  pop     rbp
0x18001992b  pop     rbx
0x18001992c  retn
```
