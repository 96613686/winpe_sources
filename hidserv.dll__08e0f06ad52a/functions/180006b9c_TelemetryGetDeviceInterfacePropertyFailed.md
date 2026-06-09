# TelemetryGetDeviceInterfacePropertyFailed

- ea: `0x180006b9c`
- end: `0x180006cae`
- name: `TelemetryGetDeviceInterfacePropertyFailed`
- size: `274`
- prototype: `ULONG __fastcall(const int *, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005708`

## callees

- `0x180006b9c`
- `0x1800081d4`
- `0x180008450`

## pseudocode

```c
ULONG __fastcall TelemetryGetDeviceInterfacePropertyFailed(const int *a1, int a2, __int64 a3)
{
  ULONG result; // eax
  __int64 v4; // rax
  int v5; // eax
  int v6; // [rsp+30h] [rbp-49h] BYREF
  int v7; // [rsp+34h] [rbp-45h] BYREF
  __int64 v8; // [rsp+38h] [rbp-41h] BYREF
  __int64 v9; // [rsp+40h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+50h] [rbp-29h] BYREF
  __int64 *v11; // [rsp+70h] [rbp-9h]
  __int64 v12; // [rsp+78h] [rbp-1h]
  const int *v13; // [rsp+80h] [rbp+7h]
  int v14; // [rsp+88h] [rbp+Fh]
  int v15; // [rsp+8Ch] [rbp+13h]
  int *v16; // [rsp+90h] [rbp+17h]
  __int64 v17; // [rsp+98h] [rbp+1Fh]
  int *v18; // [rsp+A0h] [rbp+27h]
  __int64 v19; // [rsp+A8h] [rbp+2Fh]
  __int64 *v20; // [rsp+B0h] [rbp+37h]
  __int64 v21; // [rsp+B8h] [rbp+3Fh]

  result = dword_18000D000;
  if ( (unsigned int)dword_18000D000 > 5 )
  {
    result = qword_18000D010;
    if ( (qword_18000D010 & 0x400000000000LL) != 0 )
    {
      result = 0;
      if ( (qword_18000D018 & 0x400000000000LL) == qword_18000D018 )
      {
        v8 = 1;
        v12 = 8;
        v11 = &v8;
        if ( a1 )
        {
          v4 = -1;
          do
            ++v4;
          while ( *((_WORD *)a1 + v4) );
          v5 = 2 * v4 + 2;
        }
        else
        {
          a1 = &dword_18000A75C;
          v5 = 2;
        }
        v14 = v5;
        v16 = &v6;
        v18 = &v7;
        v20 = &v9;
        v6 = a2;
        v13 = a1;
        v15 = 0;
        v17 = 4;
        v7 = a3;
        v19 = 4;
        v9 = 0x1000000;
        v21 = 8;
        return tlgWriteAgg((__int64)a1, (unsigned __int8 *)&dword_18000AD94, a3, 0, &v10);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006b9c  push    rbp
0x180006b9e  lea     rbp, [rsp-57h]
0x180006ba3  sub     rsp, 0D0h
0x180006baa  mov     rax, cs:__security_cookie
0x180006bb1  xor     rax, rsp
0x180006bb4  mov     [rbp+57h+var_10], rax
0x180006bb8  mov     eax, cs:dword_18000D000
0x180006bbe  cmp     eax, 5
0x180006bc1  jbe     loc_180006C99
0x180006bc7  mov     r9, cs:qword_18000D018
0x180006bce  mov     r10, 400000000000h
0x180006bd8  mov     rax, cs:qword_18000D010
0x180006bdf  test    r10, rax
0x180006be2  jz      loc_180006C99
0x180006be8  mov     rax, r9
0x180006beb  and     rax, r10
0x180006bee  cmp     rax, r9
0x180006bf1  jnz     loc_180006C99
0x180006bf7  xor     r9d, r9d; int
0x180006bfa  mov     [rbp+57h+var_98], 1
0x180006c02  mov     [rbp+57h+var_58], 8
0x180006c0a  lea     rax, [rbp+57h+var_98]
0x180006c0e  mov     [rbp+57h+var_60], rax
0x180006c12  test    rcx, rcx
0x180006c15  jz      short loc_180006C2E
0x180006c17  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006c1b  inc     rax
0x180006c1e  cmp     [rcx+rax*2], r9w
0x180006c23  jnz     short loc_180006C1B
0x180006c25  lea     eax, ds:2[rax*2]
0x180006c2c  jmp     short loc_180006C3A
0x180006c2e  lea     rcx, dword_18000A75C; int
0x180006c35  mov     eax, 2
0x180006c3a  mov     [rbp+57h+var_48], eax
0x180006c3d  lea     rax, [rbp+57h+var_A0]
0x180006c41  mov     [rbp+57h+var_40], rax
0x180006c45  lea     rax, [rbp+57h+var_9C]
0x180006c49  mov     [rbp+57h+var_30], rax
0x180006c4d  lea     rax, [rbp+57h+var_90]
0x180006c51  mov     [rbp+57h+var_20], rax
0x180006c55  lea     rax, [rbp+57h+var_80]
0x180006c59  mov     [rbp+57h+var_A0], edx
0x180006c5c  lea     rdx, dword_18000AD94; int
0x180006c63  mov     [rsp+0D0h+var_B0], rax; PEVENT_DATA_DESCRIPTOR
0x180006c68  mov     [rbp+57h+var_50], rcx
0x180006c6c  mov     [rbp+57h+var_44], r9d
0x180006c70  mov     [rbp+57h+var_38], 4
0x180006c78  mov     [rbp+57h+var_9C], r8d
0x180006c7c  mov     [rbp+57h+var_28], 4
0x180006c84  mov     [rbp+57h+var_90], 1000000h
0x180006c8c  mov     [rbp+57h+var_18], 8
0x180006c94  call    _tlgWriteAgg
0x180006c99  mov     rcx, [rbp+57h+var_10]
0x180006c9d  xor     rcx, rsp; StackCookie
0x180006ca0  call    __security_check_cookie
0x180006ca5  add     rsp, 0D0h
0x180006cac  pop     rbp
0x180006cad  retn
```
