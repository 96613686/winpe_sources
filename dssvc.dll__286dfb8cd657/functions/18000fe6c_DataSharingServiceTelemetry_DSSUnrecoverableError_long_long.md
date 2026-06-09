# DataSharingServiceTelemetry::DSSUnrecoverableError<long &>(long &)

- ea: `0x18000fe6c`
- end: `0x18000ff21`
- name: `??$DSSUnrecoverableError@AEAJ@DataSharingServiceTelemetry@@SAXAEAJ@Z`
- size: `181`
- prototype: ``
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
int __fastcall DataSharingServiceTelemetry::DSSUnrecoverableError<long &>(int *a1)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r10
  int v5; // [rsp+30h] [rbp-68h] BYREF
  __int64 v6; // [rsp+38h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+40h] [rbp-58h] BYREF
  int *v8; // [rsp+60h] [rbp-38h]
  __int64 v9; // [rsp+68h] [rbp-30h]
  __int64 *v10; // [rsp+70h] [rbp-28h]
  __int64 v11; // [rsp+78h] [rbp-20h]

  v2 = DataSharingServiceProvider::Provider((__int64)a1);
  if ( *(_DWORD *)v2 > 5u )
  {
    LODWORD(v2) = tlgKeywordOn(v2, 0x200000000000LL);
    if ( (_BYTE)v2 )
    {
      v5 = *a1;
      v9 = 4;
      v10 = &v6;
      v6 = 0x1000000;
      v8 = &v5;
      v11 = 8;
      LODWORD(v2) = tlgWriteTransfer_EventWriteTransfer(v3, (unsigned __int8 *)&word_180025E86, 0, 0, 4u, &v7);
    }
  }
  return (int)v2;
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
