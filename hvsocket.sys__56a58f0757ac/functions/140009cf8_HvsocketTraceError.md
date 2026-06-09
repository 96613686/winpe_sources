# HvsocketTraceError

- ea: `0x140009cf8`
- end: `0x140009dea`
- name: `HvsocketTraceError`
- size: `242`
- prototype: `NTSTATUS __fastcall(const int *, int, __int64, const int *)`
- caller_count: `25`
- callee_count: `3`
- tags: ``

## callers

- `0x140001350`
- `0x140001418`
- `0x140001714`
- `0x140003a20`
- `0x14000727c`
- `0x1400085c8`
- `0x140008774`
- `0x140019838`
- `0x140019960`
- `0x140019a10`
- `0x140019b70`
- `0x14001a148`
- `0x14001b140`
- `0x14002052c`
- `0x1400209c0`
- `0x140020b80`
- `0x1400213d0`
- `0x140021550`
- `0x140021cb4`
- `0x140022634`
- `0x140023280`
- `0x1400234e0`
- `0x140023b40`
- `0x140024250`
- `0x140026868`

## callees

- `0x140001008`
- `0x140009cf8`
- `0x14000bfa0`

## pseudocode

```c
NTSTATUS __fastcall HvsocketTraceError(const int *a1, int a2, __int64 a3, const int *a4)
{
  NTSTATUS result; // eax
  __int64 v6; // rax
  int v7; // r10d
  __int64 v8; // rdx
  int v9; // edx
  int v10; // [rsp+30h] [rbp-29h] BYREF
  int v11; // [rsp+34h] [rbp-25h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+40h] [rbp-19h] BYREF
  const int *v13; // [rsp+60h] [rbp+7h]
  int v14; // [rsp+68h] [rbp+Fh]
  int v15; // [rsp+6Ch] [rbp+13h]
  int *v16; // [rsp+70h] [rbp+17h]
  __int64 v17; // [rsp+78h] [rbp+1Fh]
  int *v18; // [rsp+80h] [rbp+27h]
  __int64 v19; // [rsp+88h] [rbp+2Fh]
  const int *v20; // [rsp+90h] [rbp+37h]
  int v21; // [rsp+98h] [rbp+3Fh]
  int v22; // [rsp+9Ch] [rbp+43h]

  result = dword_140013058;
  if ( (unsigned int)dword_140013058 > 2 )
  {
    v6 = -1;
    v7 = 1;
    if ( a1 )
    {
      v8 = -1;
      do
        ++v8;
      while ( *((_BYTE *)a1 + v8) );
      v9 = v8 + 1;
    }
    else
    {
      a1 = &byte_14000E6BD;
      v9 = 1;
    }
    v13 = a1;
    v16 = &v10;
    v18 = &v11;
    v14 = v9;
    v15 = 0;
    v10 = a2;
    v17 = 4;
    v11 = a3;
    v19 = 4;
    if ( a4 )
    {
      do
        ++v6;
      while ( *((_BYTE *)a4 + v6) );
      v7 = v6 + 1;
    }
    else
    {
      a4 = &byte_14000E6BD;
    }
    v20 = a4;
    v21 = v7;
    v22 = 0;
    return tlgWriteTransfer_EtwWriteTransfer(
             (__int64)&dword_140013058,
             (unsigned __int8 *)&byte_14001179F,
             a3,
             (__int64)a4,
             6u,
             &v12);
  }
  return result;
}

```

## disassembly

```asm
0x140009cf8  push    rbp
0x140009cfa  lea     rbp, [rsp-57h]
0x140009cff  sub     rsp, 0B0h
0x140009d06  mov     rax, cs:__security_cookie
0x140009d0d  xor     rax, rsp
0x140009d10  mov     [rbp+57h+var_10], rax
0x140009d14  mov     eax, cs:dword_140013058
0x140009d1a  mov     r11d, edx
0x140009d1d  cmp     eax, 2
0x140009d20  jbe     loc_140009DD4
0x140009d26  or      rax, 0FFFFFFFFFFFFFFFFh
0x140009d2a  mov     r10d, 1
0x140009d30  test    rcx, rcx
0x140009d33  jz      short loc_140009D45
0x140009d35  mov     rdx, rax
0x140009d38  inc     rdx
0x140009d3b  cmp     byte ptr [rcx+rdx], 0
0x140009d3f  jnz     short loc_140009D38
0x140009d41  inc     edx
0x140009d43  jmp     short loc_140009D4F
0x140009d45  lea     rcx, byte_14000E6BD
0x140009d4c  mov     edx, r10d
0x140009d4f  mov     [rbp+57h+var_50], rcx
0x140009d53  lea     rcx, [rbp+57h+var_80]
0x140009d57  mov     [rbp+57h+var_40], rcx
0x140009d5b  lea     rcx, [rbp+57h+var_7C]
0x140009d5f  mov     [rbp+57h+var_30], rcx
0x140009d63  mov     [rbp+57h+var_48], edx
0x140009d66  mov     [rbp+57h+var_44], 0
0x140009d6d  mov     [rbp+57h+var_80], r11d
0x140009d71  mov     [rbp+57h+var_38], 4
0x140009d79  mov     [rbp+57h+var_7C], r8d
0x140009d7d  mov     [rbp+57h+var_28], 4
0x140009d85  test    r9, r9
0x140009d88  jz      short loc_140009D9A
0x140009d8a  inc     rax
0x140009d8d  cmp     byte ptr [r9+rax], 0
0x140009d92  jnz     short loc_140009D8A
0x140009d94  lea     r10d, [rax+1]
0x140009d98  jmp     short loc_140009DA1
0x140009d9a  lea     r9, byte_14000E6BD; int
0x140009da1  lea     rax, [rbp+57h+var_70]
0x140009da5  mov     [rbp+57h+var_20], r9
0x140009da9  mov     [rsp+0B0h+var_88], rax; __int64
0x140009dae  lea     rdx, byte_14001179F; int
0x140009db5  lea     rcx, dword_140013058; int
0x140009dbc  mov     [rsp+0B0h+var_90], 6; ULONG
0x140009dc4  mov     [rbp+57h+var_18], r10d
0x140009dc8  mov     [rbp+57h+var_14], 0
0x140009dcf  call    _tlgWriteTransfer_EtwWriteTransfer
0x140009dd4  mov     rcx, [rbp+57h+var_10]
0x140009dd8  xor     rcx, rsp; StackCookie
0x140009ddb  call    __security_check_cookie
0x140009de0  add     rsp, 0B0h
0x140009de7  pop     rbp
0x140009de8  retn
```
