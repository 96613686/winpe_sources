# HvsocketTraceEndpointError

- ea: `0x14000975c`
- end: `0x14000982c`
- name: `HvsocketTraceEndpointError`
- size: `208`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `45`
- callee_count: `3`
- tags: ``

## callers

- `0x140001d04`
- `0x140002e48`
- `0x140002f34`
- `0x14000309c`
- `0x1400034f4`
- `0x1400036d0`
- `0x140003890`
- `0x140003fe0`
- `0x1400042d0`
- `0x14000440c`
- `0x1400045c0`
- `0x140004690`
- `0x1400049a0`
- `0x140004e9c`
- `0x1400059b8`
- `0x140005d74`
- `0x140006290`
- `0x1400065fc`
- `0x140007034`
- `0x14000727c`
- `0x140007b00`
- `0x140008200`
- `0x1400083f0`
- `0x14000a920`
- `0x14000b130`
- `0x140019290`
- `0x14001960c`
- `0x140019b70`
- `0x140019fc0`
- `0x14001a42c`
- `0x14001a4e4`
- `0x14001a5b4`
- `0x14001b800`
- `0x14001bd20`
- `0x14001c2d0`
- `0x14001cc80`
- `0x14001cf60`
- `0x140022b58`
- `0x140022cd8`
- `0x140022db8`
- `0x140022e88`
- `0x140022f54`
- `0x140023020`
- `0x140023110`
- `0x1400231b0`

## callees

- `0x140001008`
- `0x14000975c`
- `0x14000bfa0`

## pseudocode

```c
NTSTATUS __fastcall HvsocketTraceEndpointError(const int *a1, int a2, __int64 a3, __int64 a4)
{
  NTSTATUS result; // eax
  __int64 v5; // rax
  int v6; // eax
  int v7; // [rsp+30h] [rbp-29h] BYREF
  int v8; // [rsp+34h] [rbp-25h] BYREF
  __int64 v9; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+40h] [rbp-19h] BYREF
  const int *v11; // [rsp+60h] [rbp+7h]
  int v12; // [rsp+68h] [rbp+Fh]
  int v13; // [rsp+6Ch] [rbp+13h]
  int *v14; // [rsp+70h] [rbp+17h]
  __int64 v15; // [rsp+78h] [rbp+1Fh]
  int *v16; // [rsp+80h] [rbp+27h]
  __int64 v17; // [rsp+88h] [rbp+2Fh]
  __int64 *v18; // [rsp+90h] [rbp+37h]
  __int64 v19; // [rsp+98h] [rbp+3Fh]

  result = dword_140013058;
  if ( (unsigned int)dword_140013058 > 2 )
  {
    if ( a1 )
    {
      v5 = -1;
      do
        ++v5;
      while ( *((_BYTE *)a1 + v5) );
      v6 = v5 + 1;
    }
    else
    {
      a1 = &byte_14000E6BD;
      v6 = 1;
    }
    v12 = v6;
    v14 = &v7;
    v16 = &v8;
    v18 = &v9;
    v11 = a1;
    v7 = a2;
    v13 = 0;
    v15 = 4;
    v8 = a3;
    v17 = 4;
    v9 = a4;
    v19 = 8;
    return tlgWriteTransfer_EtwWriteTransfer(
             (__int64)&dword_140013058,
             (unsigned __int8 *)&qword_1400118C8,
             a3,
             a4,
             6u,
             &v10);
  }
  return result;
}

```

## disassembly

```asm
0x14000975c  push    rbp
0x14000975e  lea     rbp, [rsp-57h]
0x140009763  sub     rsp, 0B0h
0x14000976a  mov     rax, cs:__security_cookie
0x140009771  xor     rax, rsp
0x140009774  mov     [rbp+57h+var_10], rax
0x140009778  mov     eax, cs:dword_140013058
0x14000977e  cmp     eax, 2
0x140009781  jbe     loc_140009816
0x140009787  xor     r10d, r10d
0x14000978a  test    rcx, rcx
0x14000978d  jz      short loc_1400097A0
0x14000978f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140009793  inc     rax
0x140009796  cmp     [rcx+rax], r10b
0x14000979a  jnz     short loc_140009793
0x14000979c  inc     eax
0x14000979e  jmp     short loc_1400097AC
0x1400097a0  lea     rcx, byte_14000E6BD
0x1400097a7  mov     eax, 1
0x1400097ac  mov     [rbp+57h+var_48], eax
0x1400097af  lea     rax, [rbp+57h+var_80]
0x1400097b3  mov     [rbp+57h+var_40], rax
0x1400097b7  lea     rax, [rbp+57h+var_7C]
0x1400097bb  mov     [rbp+57h+var_30], rax
0x1400097bf  lea     rax, [rbp+57h+var_78]
0x1400097c3  mov     [rbp+57h+var_20], rax
0x1400097c7  lea     rax, [rbp+57h+var_70]
0x1400097cb  mov     [rbp+57h+var_50], rcx
0x1400097cf  lea     rcx, dword_140013058; int
0x1400097d6  mov     [rbp+57h+var_80], edx
0x1400097d9  lea     rdx, qword_1400118C8; int
0x1400097e0  mov     [rsp+0B0h+var_88], rax; __int64
0x1400097e5  mov     [rsp+0B0h+var_90], 6; ULONG
0x1400097ed  mov     [rbp+57h+var_44], r10d
0x1400097f1  mov     [rbp+57h+var_38], 4
0x1400097f9  mov     [rbp+57h+var_7C], r8d
0x1400097fd  mov     [rbp+57h+var_28], 4
0x140009805  mov     [rbp+57h+var_78], r9
0x140009809  mov     [rbp+57h+var_18], 8
0x140009811  call    _tlgWriteTransfer_EtwWriteTransfer
0x140009816  mov     rcx, [rbp+57h+var_10]
0x14000981a  xor     rcx, rsp; StackCookie
0x14000981d  call    __security_check_cookie
0x140009822  add     rsp, 0B0h
0x140009829  pop     rbp
0x14000982a  retn
```
