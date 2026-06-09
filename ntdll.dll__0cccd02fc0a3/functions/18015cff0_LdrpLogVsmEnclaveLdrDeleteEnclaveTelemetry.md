# LdrpLogVsmEnclaveLdrDeleteEnclaveTelemetry

- ea: `0x18015cff0`
- end: `0x18015d0c9`
- name: `LdrpLogVsmEnclaveLdrDeleteEnclaveTelemetry`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180124600`

## callees

- `0x180045a00`
- `0x1800853a8`
- `0x180117224`
- `0x18015cff0`
- `0x180162000`

## string_xrefs

- `0x18015d065`: `LdrDeleteEnclave`

## pseudocode

```c
__int64 __fastcall LdrpLogVsmEnclaveLdrDeleteEnclaveTelemetry(int a1)
{
  __int64 result; // rax
  __int64 v3; // r8
  int v4; // r9d
  int v5; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v6[32]; // [rsp+40h] [rbp-58h] BYREF
  const char *v7; // [rsp+60h] [rbp-38h]
  __int64 v8; // [rsp+68h] [rbp-30h]
  int *v9; // [rsp+70h] [rbp-28h]
  __int64 v10; // [rsp+78h] [rbp-20h]

  result = (__int64)NtCurrentPeb();
  if ( *(_QWORD *)(result + 48) )
  {
    RtlRunOnceExecuteOnce(&VsmEnclaveTelemetryInitRunOnce, VsmEnclaveTelemetryInitOnce, 0, 0);
    result = (unsigned int)dword_1801C4A00;
    if ( (unsigned int)dword_1801C4A00 > 4 )
    {
      result = tlgKeywordOn(&dword_1801C4A00, 0x400000000000LL);
      if ( (_BYTE)result )
      {
        v8 = 17;
        v7 = "LdrDeleteEnclave";
        v5 = a1;
        v9 = &v5;
        v10 = v3;
        return tlgWriteTransfer_EtwEventWriteTransfer(
                 (unsigned int)&dword_1801C4A00,
                 (unsigned int)byte_18019BA49,
                 v3,
                 v4,
                 v3,
                 (__int64)v6);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18015cff0  push    rbx
0x18015cff2  sub     rsp, 90h
0x18015cff9  mov     rax, cs:__security_cookie
0x18015d000  xor     rax, rsp
0x18015d003  mov     [rsp+98h+var_18], rax
0x18015d00b  mov     rax, gs:60h
0x18015d014  mov     ebx, ecx
0x18015d016  cmp     qword ptr [rax+30h], 0
0x18015d01b  jz      loc_18015D0AF
0x18015d021  xor     r9d, r9d
0x18015d024  lea     rdx, VsmEnclaveTelemetryInitOnce
0x18015d02b  xor     r8d, r8d
0x18015d02e  lea     rcx, VsmEnclaveTelemetryInitRunOnce
0x18015d035  call    RtlRunOnceExecuteOnce
0x18015d03a  mov     eax, cs:dword_1801C4A00
0x18015d040  mov     r8d, 4
0x18015d046  cmp     eax, r8d
0x18015d049  jbe     short loc_18015D0AF
0x18015d04b  mov     rdx, 400000000000h
0x18015d055  lea     rcx, dword_1801C4A00
0x18015d05c  call    _tlgKeywordOn
0x18015d061  test    al, al
0x18015d063  jz      short loc_18015D0AF
0x18015d065  lea     rax, aLdrdeleteencla_0; "LdrDeleteEnclave"
0x18015d06c  mov     [rsp+98h+var_30], 11h
0x18015d075  mov     [rsp+98h+var_38], rax
0x18015d07a  lea     rdx, byte_18019BA49
0x18015d081  lea     rax, [rsp+98h+var_68]
0x18015d086  mov     [rsp+98h+var_68], ebx
0x18015d08a  mov     [rsp+98h+var_28], rax
0x18015d08f  lea     rcx, dword_1801C4A00
0x18015d096  lea     rax, [rsp+98h+var_58]
0x18015d09b  mov     [rsp+98h+var_20], r8
0x18015d0a0  mov     [rsp+98h+var_70], rax
0x18015d0a5  mov     [rsp+98h+var_78], r8d
0x18015d0aa  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18015d0af  mov     rcx, [rsp+98h+var_18]
0x18015d0b7  xor     rcx, rsp; StackCookie
0x18015d0ba  call    __security_check_cookie
0x18015d0bf  add     rsp, 90h
0x18015d0c6  pop     rbx
0x18015d0c7  retn
```
