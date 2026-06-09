# MupWriteTelemetryKnownRemoteMailslotFailed

- ea: `0x140002668`
- end: `0x1400026f5`
- name: `MupWriteTelemetryKnownRemoteMailslotFailed`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000f21c`

## callees

- `0x140001008`
- `0x1400024fc`
- `0x140002668`
- `0x1400054a0`

## pseudocode

```c
NTSTATUS __fastcall MupWriteTelemetryKnownRemoteMailslotFailed(__int64 a1, __int64 a2)
{
  NTSTATUS result; // eax
  __int64 v3; // rcx
  unsigned __int16 *v4; // r8
  __int64 v5; // r9
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-58h] BYREF
  _DWORD *v7; // [rsp+50h] [rbp-38h]
  __int64 v8; // [rsp+58h] [rbp-30h]
  __int64 v9; // [rsp+60h] [rbp-28h]
  _DWORD v10[2]; // [rsp+68h] [rbp-20h] BYREF

  result = dword_14000A098;
  if ( (unsigned int)dword_14000A098 > 5 )
  {
    result = tlgKeywordOn(a1, a2, a1);
    if ( (_BYTE)result )
    {
      v8 = 2;
      v7 = v10;
      v9 = *((_QWORD *)v4 + 1);
      v10[0] = *v4;
      v10[1] = 0;
      return tlgWriteTransfer_EtwWriteTransfer(v3, (unsigned __int8 *)&word_140007FEE, (__int64)v4, v5, 4u, &v6);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140002668  sub     rsp, 88h
0x14000266f  mov     rax, cs:__security_cookie
0x140002676  xor     rax, rsp
0x140002679  mov     [rsp+88h+var_18], rax
0x14000267e  mov     eax, cs:dword_14000A098
0x140002684  mov     r8, rcx
0x140002687  cmp     eax, 5
0x14000268a  jbe     short loc_1400026DF
0x14000268c  call    _tlgKeywordOn
0x140002691  test    al, al
0x140002693  jz      short loc_1400026DF
0x140002695  lea     rax, [rsp+88h+var_20]
0x14000269a  mov     [rsp+88h+var_30], 2
0x1400026a3  mov     [rsp+88h+var_38], rax
0x1400026a8  lea     rdx, word_140007FEE; int
0x1400026af  mov     rax, [r8+8]
0x1400026b3  mov     [rsp+88h+var_28], rax
0x1400026b8  movzx   eax, word ptr [r8]
0x1400026bc  mov     [rsp+88h+var_20], eax
0x1400026c0  lea     rax, [rsp+88h+var_58]
0x1400026c5  mov     [rsp+88h+var_60], rax; __int64
0x1400026ca  mov     [rsp+88h+var_68], 4; ULONG
0x1400026d2  mov     [rsp+88h+var_1C], 0
0x1400026da  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400026df  mov     rcx, [rsp+88h+var_18]
0x1400026e4  xor     rcx, rsp; StackCookie
0x1400026e7  call    __security_check_cookie
0x1400026ec  add     rsp, 88h
0x1400026f3  retn
```
