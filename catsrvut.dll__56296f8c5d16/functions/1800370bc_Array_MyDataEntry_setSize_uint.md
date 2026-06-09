# Array<MyDataEntry *>::setSize(uint)

- ea: `0x1800370bc`
- end: `0x1800371b2`
- name: `?setSize@?$Array@PEAUMyDataEntry@@@@QEAAJI@Z`
- size: `246`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800352e4`
- `0x1800353ac`
- `0x180037990`
- `0x180039dc0`

## callees

- `0x180005944`
- `0x1800370bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037196`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037196`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003715b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003715b`

## string_xrefs

- `0x180037133`: `com\complus\src\inc\array_t_raw.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Array<MyDataEntry *>::setSize(__int64 a1, unsigned int a2)
{
  unsigned int v4; // eax
  unsigned int v5; // edi
  _QWORD *v6; // r14
  __int64 i; // r8
  int v9; // [rsp+20h] [rbp-58h] BYREF
  __int16 v10; // [rsp+24h] [rbp-54h]
  int v11; // [rsp+28h] [rbp-50h]
  const unsigned __int16 *v12; // [rsp+30h] [rbp-48h]
  __int64 v13; // [rsp+38h] [rbp-40h]
  __int64 v14; // [rsp+40h] [rbp-38h]
  int v15; // [rsp+48h] [rbp-30h]
  int v16; // [rsp+4Ch] [rbp-2Ch]

  v4 = *(_DWORD *)(a1 + 12);
  if ( a2 > v4 )
  {
    v5 = (3 * v4) >> 1;
    if ( a2 > v5 )
      v5 = a2;
    if ( v5 > 0x20000000 )
    {
      v9 = 0;
      v10 = 21;
      v11 = -1073605930;
      v12 = L"itMaxNew <= itMaxMax";
      v13 = 0;
      v14 = 0;
      v16 = 1;
      v15 = 1;
      CError::WriteToLog((CError *)&v9, L"com\\complus\\src\\inc\\array_t_raw.h", 0x7Cu, L"itMaxNew <= itMaxMax");
    }
    v6 = CoTaskMemAlloc(saturated_mul(v5, 8u));
    if ( !v6 )
      return 2147942414LL;
    if ( *(_QWORD *)a1 )
    {
      for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 8); i = (unsigned int)(i + 1) )
        v6[i] = *(_QWORD *)(*(_QWORD *)a1 + 8 * i);
      CoTaskMemFree(*(LPVOID *)a1);
    }
    *(_QWORD *)a1 = v6;
    *(_DWORD *)(a1 + 12) = v5;
  }
  *(_DWORD *)(a1 + 8) = a2;
  return 0;
}

```

## disassembly

```asm
0x1800370bc  mov     r11, rsp
0x1800370bf  push    rbx
0x1800370c0  push    rsi
0x1800370c1  push    rdi
0x1800370c2  push    r14
0x1800370c4  sub     rsp, 58h
0x1800370c8  mov     esi, edx
0x1800370ca  mov     rbx, rcx
0x1800370cd  mov     eax, [rcx+0Ch]
0x1800370d0  cmp     edx, eax
0x1800370d2  jbe     loc_1800371A3
0x1800370d8  lea     edi, [rax+rax*2]
0x1800370db  shr     edi, 1
0x1800370dd  cmp     edx, edi
0x1800370df  cmova   edi, edx
0x1800370e2  cmp     edi, 20000000h
0x1800370e8  jbe     short loc_180037143
0x1800370ea  mov     [rsp+78h+var_58], 0
0x1800370f2  mov     eax, 15h
0x1800370f7  mov     [rsp+78h+var_54], ax
0x1800370fc  mov     [rsp+78h+var_50], 0C00212D6h
0x180037104  lea     r9, aItmaxnewItmaxm; "itMaxNew <= itMaxMax"
0x18003710b  mov     [r11-48h], r9
0x18003710f  mov     qword ptr [r11-40h], 0
0x180037117  mov     qword ptr [r11-38h], 0
0x18003711f  mov     [rsp+78h+var_2C], 1
0x180037127  mov     [rsp+78h+var_30], 1
0x18003712f  lea     r8d, [rax+67h]; unsigned int
0x180037133  lea     rdx, aComComplusSrcI; "com\\complus\\src\\inc\\array_t_raw.h"
0x18003713a  lea     rcx, [r11-58h]; this
0x18003713e  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180037143  mov     ecx, edi
0x180037145  mov     eax, 8
0x18003714a  mul     rcx
0x18003714d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180037154  cmovb   rax, rcx
0x180037158  mov     rcx, rax; cb
0x18003715b  call    cs:__imp_CoTaskMemAlloc
0x180037161  mov     r14, rax
0x180037164  test    rax, rax
0x180037167  jnz     short loc_180037170
0x180037169  mov     eax, 8007000Eh
0x18003716e  jmp     short loc_1800371A8
0x180037170  cmp     qword ptr [rbx], 0
0x180037174  jz      short loc_18003719D
0x180037176  xor     r8d, r8d
0x180037179  cmp     [rbx+8], r8d
0x18003717d  jbe     short loc_180037193
0x18003717f  mov     rax, [rbx]
0x180037182  mov     rcx, [rax+r8*8]
0x180037186  mov     [r14+r8*8], rcx
0x18003718a  inc     r8d
0x18003718d  cmp     r8d, [rbx+8]
0x180037191  jb      short loc_18003717F
0x180037193  mov     rcx, [rbx]; pv
0x180037196  call    cs:__imp_CoTaskMemFree
0x18003719c  nop
0x18003719d  mov     [rbx], r14
0x1800371a0  mov     [rbx+0Ch], edi
0x1800371a3  mov     [rbx+8], esi
0x1800371a6  xor     eax, eax
0x1800371a8  add     rsp, 58h
0x1800371ac  pop     r14
0x1800371ae  pop     rdi
0x1800371af  pop     rsi
0x1800371b0  pop     rbx
0x1800371b1  retn
```
