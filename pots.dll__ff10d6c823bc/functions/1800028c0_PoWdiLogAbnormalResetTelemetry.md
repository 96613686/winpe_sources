# PoWdiLogAbnormalResetTelemetry

- ea: `0x1800028c0`
- end: `0x18000296d`
- name: `PoWdiLogAbnormalResetTelemetry`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004710`

## callees

- `0x18000113c`
- `0x1800024e8`
- `0x1800028c0`
- `0x180004930`

## import_xrefs

- `wdi!WdiSetFeedback` at `0x180002954`
- `wdi!WdiSetFeedback` at `0x180002954`

## pseudocode

```c
__int64 __fastcall PoWdiLogAbnormalResetTelemetry(__int64 a1, struct _EVENT_RECORD *a2)
{
  __int64 result; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  BYTE v6[8]; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v7[32]; // [rsp+38h] [rbp-30h] BYREF

  *(_DWORD *)v6 = 0;
  result = PoWdiGetULongProperty(a2, (ULONGLONG)L"ResetReasonMask", v6);
  if ( (_DWORD)result )
  {
    if ( (unsigned int)dword_1800091A8 > 5
      && (qword_1800091B8 & 0x400000000000LL) != 0
      && (qword_1800091C0 & 0x400000000000LL) == qword_1800091C0 )
    {
      tlgWriteTransfer_EtwEventWriteTransfer(qword_1800091C0, byte_180006EDF, v4, v5, 2, (__int64)v7);
    }
    return WdiSetFeedback(a1, 1);
  }
  return result;
}

```

## disassembly

```asm
0x1800028c0  push    rbx
0x1800028c2  sub     rsp, 60h
0x1800028c6  mov     rax, cs:__security_cookie
0x1800028cd  xor     rax, rsp
0x1800028d0  mov     [rsp+68h+var_10], rax
0x1800028d5  mov     rax, rdx
0x1800028d8  mov     dword ptr [rsp+68h+var_38], 0
0x1800028e0  mov     rbx, rcx
0x1800028e3  lea     r8, [rsp+68h+var_38]
0x1800028e8  mov     rcx, rax
0x1800028eb  lea     rdx, aResetreasonmas; "ResetReasonMask"
0x1800028f2  call    PoWdiGetULongProperty
0x1800028f7  test    eax, eax
0x1800028f9  jz      short loc_18000295A
0x1800028fb  mov     eax, cs:dword_1800091A8
0x180002901  cmp     eax, 5
0x180002904  jbe     short loc_18000294C
0x180002906  mov     rcx, cs:qword_1800091C0
0x18000290d  mov     rdx, 400000000000h
0x180002917  mov     rax, cs:qword_1800091B8
0x18000291e  test    rdx, rax
0x180002921  jz      short loc_18000294C
0x180002923  mov     rax, rcx
0x180002926  and     rax, rdx
0x180002929  cmp     rax, rcx
0x18000292c  jnz     short loc_18000294C
0x18000292e  lea     rax, [rsp+68h+var_30]
0x180002933  mov     [rsp+68h+var_40], rax
0x180002938  lea     rdx, byte_180006EDF
0x18000293f  mov     [rsp+68h+var_48], 2
0x180002947  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18000294c  mov     edx, 1
0x180002951  mov     rcx, rbx
0x180002954  call    cs:__imp_WdiSetFeedback
0x18000295a  mov     rcx, [rsp+68h+var_10]
0x18000295f  xor     rcx, rsp; StackCookie
0x180002962  call    __security_check_cookie
0x180002967  add     rsp, 60h
0x18000296b  pop     rbx
0x18000296c  retn
```
