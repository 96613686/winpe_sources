# SrvCryptFreeProvider

- ea: `0x180009e90`
- end: `0x180009f10`
- name: `SrvCryptFreeProvider`
- size: `128`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800025b0`
- `0x180003540`
- `0x180003cf0`
- `0x180005510`
- `0x180009e90`

## string_xrefs

- `0x180009ef0`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvCryptFreeProvider(struct _RTL_CRITICAL_SECTION *a1, __int64 a2)
{
  __int64 v3; // r9
  unsigned int v4; // ebx
  __int64 v5; // rcx
  _QWORD *v6; // rax
  _QWORD *v7; // rdi
  int v8; // eax

  if ( !a1 )
  {
    v3 = 1845;
LABEL_3:
    v4 = -2146893786;
    v5 = 2148073510LL;
LABEL_8:
    DebugTraceError(v5, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v3);
    return v4;
  }
  v6 = SrvLookupAndReferenceProvider(a1, a2, 1);
  v7 = v6;
  if ( !v6 )
  {
    v3 = 1860;
    goto LABEL_3;
  }
  SrvRemoveProviderFromList(a1, v6);
  v8 = SrvDereferenceProvider(v7);
  v4 = v8;
  if ( v8 < 0 )
  {
    v3 = 1875;
    v5 = (unsigned int)v8;
    goto LABEL_8;
  }
  return v4;
}

```

## disassembly

```asm
0x180009e90  mov     [rsp+arg_0], rbx
0x180009e95  push    rdi
0x180009e96  sub     rsp, 20h
0x180009e9a  mov     rbx, rcx
0x180009e9d  test    rcx, rcx
0x180009ea0  jnz     short loc_180009EB4
0x180009ea2  mov     r9d, 735h
0x180009ea8  mov     ebx, 80090026h
0x180009ead  mov     ecx, 80090026h
0x180009eb2  jmp     short loc_180009EF0
0x180009eb4  mov     r8d, 1
0x180009eba  call    SrvLookupAndReferenceProvider
0x180009ebf  mov     rdi, rax
0x180009ec2  test    rax, rax
0x180009ec5  jnz     short loc_180009ECF
0x180009ec7  mov     r9d, 744h
0x180009ecd  jmp     short loc_180009EA8
0x180009ecf  mov     rdx, rdi
0x180009ed2  mov     rcx, rbx
0x180009ed5  call    SrvRemoveProviderFromList
0x180009eda  mov     rcx, rdi
0x180009edd  call    SrvDereferenceProvider
0x180009ee2  mov     ebx, eax
0x180009ee4  test    eax, eax
0x180009ee6  jns     short loc_180009F03
0x180009ee8  mov     r9d, 753h
0x180009eee  mov     ecx, eax
0x180009ef0  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009ef7  lea     rdx, aStatus; "Status"
0x180009efe  call    DebugTraceError
0x180009f03  mov     eax, ebx
0x180009f05  mov     rbx, [rsp+28h+arg_0]
0x180009f0a  add     rsp, 20h
0x180009f0e  pop     rdi
0x180009f0f  retn
```
