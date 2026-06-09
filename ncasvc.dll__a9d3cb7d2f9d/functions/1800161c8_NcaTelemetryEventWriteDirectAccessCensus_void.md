# NcaTelemetryEventWriteDirectAccessCensus(void)

- ea: `0x1800161c8`
- end: `0x180016258`
- name: `?NcaTelemetryEventWriteDirectAccessCensus@@YAXXZ`
- size: `144`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800164e0`

## callees

- `0x18000124c`
- `0x180001278`
- `0x1800161c8`
- `0x180018c40`
- `0x18001cc70`

## pseudocode

```c
void __fastcall NcaTelemetryEventWriteDirectAccessCensus(__int64 a1)
{
  int HashId; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v2[32]; // [rsp+38h] [rbp-40h] BYREF
  int *p_HashId; // [rsp+58h] [rbp-20h]
  __int64 v4; // [rsp+60h] [rbp-18h]

  if ( (unsigned int)dword_180028048 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(a1, 0x800000000000LL) )
    {
      HashId = NcaEtwPerfTrackGetHashId(2);
      v4 = 4;
      p_HashId = &HashId;
      tlgWriteTransfer_EventWriteTransfer(&dword_180028048, word_180024422, 0, 0, 3, v2);
    }
  }
}

```

## disassembly

```asm
0x1800161c8  sub     rsp, 78h
0x1800161cc  mov     rax, cs:__security_cookie
0x1800161d3  xor     rax, rsp
0x1800161d6  mov     [rsp+78h+var_10], rax
0x1800161db  mov     eax, cs:dword_180028048
0x1800161e1  cmp     eax, 5
0x1800161e4  jbe     short loc_180016245
0x1800161e6  mov     rdx, 800000000000h
0x1800161f0  call    _tlgKeywordOn
0x1800161f5  test    al, al
0x1800161f7  jz      short loc_180016245
0x1800161f9  mov     ecx, 2
0x1800161fe  call    NcaEtwPerfTrackGetHashId
0x180016203  mov     [rsp+78h+var_48], eax
0x180016207  lea     rdx, word_180024422
0x18001620e  lea     rax, [rsp+78h+var_48]
0x180016213  mov     [rsp+78h+var_18], 4
0x18001621c  mov     [rsp+78h+var_20], rax
0x180016221  lea     rcx, dword_180028048
0x180016228  lea     rax, [rsp+78h+var_40]
0x18001622d  xor     r9d, r9d
0x180016230  mov     [rsp+78h+var_50], rax
0x180016235  xor     r8d, r8d
0x180016238  mov     [rsp+78h+var_58], 3
0x180016240  call    _tlgWriteTransfer_EventWriteTransfer
0x180016245  mov     rcx, [rsp+78h+var_10]
0x18001624a  xor     rcx, rsp; StackCookie
0x18001624d  call    __security_check_cookie
0x180016252  add     rsp, 78h
0x180016256  retn
```
