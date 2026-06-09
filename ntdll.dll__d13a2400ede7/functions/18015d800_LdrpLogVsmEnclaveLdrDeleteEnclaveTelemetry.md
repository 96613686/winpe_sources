# LdrpLogVsmEnclaveLdrDeleteEnclaveTelemetry

- ea: `0x18015d800`
- end: `0x18015d8d9`
- name: `LdrpLogVsmEnclaveLdrDeleteEnclaveTelemetry`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1801250f0`

## callees

- `0x180062600`
- `0x180091808`
- `0x180118624`
- `0x18015d800`
- `0x180162810`

## string_xrefs

- `0x18015d875`: `LdrDeleteEnclave`

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
    result = (unsigned int)dword_1801C49C8;
    if ( (unsigned int)dword_1801C49C8 > 4 )
    {
      result = tlgKeywordOn(&dword_1801C49C8, 0x400000000000LL);
      if ( (_BYTE)result )
      {
        v8 = 17;
        v7 = "LdrDeleteEnclave";
        v5 = a1;
        v9 = &v5;
        v10 = v3;
        return tlgWriteTransfer_EtwEventWriteTransfer(
                 (unsigned int)&dword_1801C49C8,
                 (unsigned int)byte_18019BA39,
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
0x18015d800  push    rbx
0x18015d802  sub     rsp, 90h
0x18015d809  mov     rax, cs:__security_cookie
0x18015d810  xor     rax, rsp
0x18015d813  mov     [rsp+98h+var_18], rax
0x18015d81b  mov     rax, gs:60h
0x18015d824  mov     ebx, ecx
0x18015d826  cmp     qword ptr [rax+30h], 0
0x18015d82b  jz      loc_18015D8BF
0x18015d831  xor     r9d, r9d
0x18015d834  lea     rdx, VsmEnclaveTelemetryInitOnce
0x18015d83b  xor     r8d, r8d
0x18015d83e  lea     rcx, VsmEnclaveTelemetryInitRunOnce
0x18015d845  call    RtlRunOnceExecuteOnce
0x18015d84a  mov     eax, cs:dword_1801C49C8
0x18015d850  mov     r8d, 4
0x18015d856  cmp     eax, r8d
0x18015d859  jbe     short loc_18015D8BF
0x18015d85b  mov     rdx, 400000000000h
0x18015d865  lea     rcx, dword_1801C49C8
0x18015d86c  call    _tlgKeywordOn
0x18015d871  test    al, al
0x18015d873  jz      short loc_18015D8BF
0x18015d875  lea     rax, aLdrdeleteencla_0; "LdrDeleteEnclave"
0x18015d87c  mov     [rsp+98h+var_30], 11h
0x18015d885  mov     [rsp+98h+var_38], rax
0x18015d88a  lea     rdx, byte_18019BA39
0x18015d891  lea     rax, [rsp+98h+var_68]
0x18015d896  mov     [rsp+98h+var_68], ebx
0x18015d89a  mov     [rsp+98h+var_28], rax
0x18015d89f  lea     rcx, dword_1801C49C8
0x18015d8a6  lea     rax, [rsp+98h+var_58]
0x18015d8ab  mov     [rsp+98h+var_20], r8
0x18015d8b0  mov     [rsp+98h+var_70], rax
0x18015d8b5  mov     [rsp+98h+var_78], r8d
0x18015d8ba  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18015d8bf  mov     rcx, [rsp+98h+var_18]
0x18015d8c7  xor     rcx, rsp; StackCookie
0x18015d8ca  call    __security_check_cookie
0x18015d8cf  add     rsp, 90h
0x18015d8d6  pop     rbx
0x18015d8d7  retn
```
