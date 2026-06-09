# DataSharingServiceTelemetry::DSSUnrecoverableError<long &>(long &)

- ea: `0x18000fe6c`
- end: `0x18000ff21`
- name: `??$DSSUnrecoverableError@AEAJ@DataSharingServiceTelemetry@@SAXAEAJ@Z`
- size: `181`
- prototype: `const struct _tlgProvider_t *__fastcall(int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800114e4`

## callees

- `0x1800017ec`
- `0x180001818`
- `0x180005c54`
- `0x18000fe6c`
- `0x18001b340`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall DataSharingServiceTelemetry::DSSUnrecoverableError<long &>(int *a1)
{
  const struct _tlgProvider_t *result; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // r10
  int v6; // [rsp+30h] [rbp-68h] BYREF
  __int64 v7; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v8[32]; // [rsp+40h] [rbp-58h] BYREF
  int *v9; // [rsp+60h] [rbp-38h]
  __int64 v10; // [rsp+68h] [rbp-30h]
  __int64 *v11; // [rsp+70h] [rbp-28h]
  __int64 v12; // [rsp+78h] [rbp-20h]

  result = DataSharingServiceProvider::Provider();
  if ( *(_DWORD *)result > 5u )
  {
    result = (const struct _tlgProvider_t *)tlgKeywordOn(result, 0x200000000000LL, v3, v4);
    if ( (_BYTE)result )
    {
      v6 = *a1;
      v10 = 4;
      v11 = &v7;
      v7 = 0x1000000;
      v9 = &v6;
      v12 = 8;
      return (const struct _tlgProvider_t *)tlgWriteTransfer_EventWriteTransfer(v5, &word_180025E86, 0, 0, 4, v8);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000fe6c  push    rbx
0x18000fe6e  sub     rsp, 90h
0x18000fe75  mov     rax, cs:__security_cookie
0x18000fe7c  xor     rax, rsp
0x18000fe7f  mov     [rsp+98h+var_18], rax
0x18000fe87  mov     rbx, rcx
0x18000fe8a  call    ?Provider@DataSharingServiceProvider@@SAPEBU_tlgProvider_t@@XZ; DataSharingServiceProvider::Provider(void)
0x18000fe8f  mov     r10, rax
0x18000fe92  mov     edx, [rax]
0x18000fe94  cmp     edx, 5
0x18000fe97  jbe     short loc_18000FF08
0x18000fe99  mov     rdx, 200000000000h
0x18000fea3  mov     rcx, rax
0x18000fea6  call    _tlgKeywordOn
0x18000feab  test    al, al
0x18000fead  jz      short loc_18000FF08
0x18000feaf  mov     eax, [rbx]
0x18000feb1  lea     rdx, word_180025E86
0x18000feb8  mov     [rsp+98h+var_68], eax
0x18000febc  mov     ecx, 4
0x18000fec1  lea     rax, [rsp+98h+var_60]
0x18000fec6  mov     [rsp+98h+var_30], rcx
0x18000fecb  mov     [rsp+98h+var_28], rax
0x18000fed0  xor     r9d, r9d
0x18000fed3  lea     rax, [rsp+98h+var_68]
0x18000fed8  mov     [rsp+98h+var_60], 1000000h
0x18000fee1  mov     [rsp+98h+var_38], rax
0x18000fee6  xor     r8d, r8d
0x18000fee9  lea     rax, [rsp+98h+var_58]
0x18000feee  mov     [rsp+98h+var_20], 8
0x18000fef7  mov     [rsp+98h+var_70], rax
0x18000fefc  mov     [rsp+98h+var_78], ecx
0x18000ff00  mov     rcx, r10
0x18000ff03  call    _tlgWriteTransfer_EventWriteTransfer
0x18000ff08  mov     rcx, [rsp+98h+var_18]
0x18000ff10  xor     rcx, rsp; StackCookie
0x18000ff13  call    __security_check_cookie
0x18000ff18  add     rsp, 90h
0x18000ff1f  pop     rbx
0x18000ff20  retn
```
