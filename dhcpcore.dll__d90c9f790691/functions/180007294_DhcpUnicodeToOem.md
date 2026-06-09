# DhcpUnicodeToOem

- ea: `0x180007294`
- end: `0x180007321`
- name: `DhcpUnicodeToOem`
- size: `141`
- prototype: `PCHAR __fastcall(PCWSTR SourceString, CHAR *)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1800026fc`
- `0x180003ea0`
- `0x18000a194`
- `0x180020e78`
- `0x180023928`

## callees

- `0x1800057f0`
- `0x180006440`
- `0x180007294`

## import_xrefs

- `ntdll!RtlxUnicodeStringToOemSize` at `0x1800072c0`
- `ntdll!RtlxUnicodeStringToOemSize` at `0x1800072c0`
- `ntdll!RtlUnicodeStringToOemString` at `0x1800072ef`
- `ntdll!RtlUnicodeStringToOemString` at `0x1800072ef`
- `ntdll!RtlInitUnicodeString` at `0x1800072b5`
- `ntdll!RtlInitUnicodeString` at `0x1800072b5`

## pseudocode

```c
PCHAR __fastcall DhcpUnicodeToOem(PCWSTR SourceString, CHAR *a2)
{
  USHORT v3; // ax
  CHAR *v4; // rax
  struct _STRING v6; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF

  v6 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  v3 = RtlxUnicodeStringToOemSize(&DestinationString);
  v6.MaximumLength = v3;
  if ( a2 )
  {
    v4 = a2;
    v6.Buffer = a2;
  }
  else
  {
    v4 = (CHAR *)DhcpAlloc(v3);
    v6.Buffer = v4;
  }
  if ( v4 )
  {
    if ( RtlUnicodeStringToOemString(&v6, &DestinationString, 0) >= 0 )
      return v6.Buffer;
    if ( !a2 )
      DhcpPunycodeFree((LPVOID *)&v6.Buffer);
  }
  return 0;
}

```

## disassembly

```asm
0x180007294  push    rbx
0x180007296  sub     rsp, 40h
0x18000729a  mov     rbx, rdx
0x18000729d  xorps   xmm0, xmm0
0x1800072a0  mov     rdx, rcx; SourceString
0x1800072a3  xorps   xmm1, xmm1
0x1800072a6  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x1800072ab  movups  xmmword ptr [rsp+48h+var_28.Length], xmm0
0x1800072b0  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm1
0x1800072b5  call    cs:__imp_RtlInitUnicodeString
0x1800072bb  lea     rcx, [rsp+48h+DestinationString]; UnicodeString
0x1800072c0  call    cs:__imp_RtlxUnicodeStringToOemSize
0x1800072c6  mov     [rsp+48h+var_28.MaximumLength], ax
0x1800072cb  test    rbx, rbx
0x1800072ce  jnz     short loc_180007304
0x1800072d0  movzx   ecx, ax
0x1800072d3  call    DhcpAlloc
0x1800072d8  mov     [rsp+48h+var_28.Buffer], rax
0x1800072dd  test    rax, rax
0x1800072e0  jz      short loc_18000731D
0x1800072e2  xor     r8d, r8d; AllocateDestinationString
0x1800072e5  lea     rdx, [rsp+48h+DestinationString]; SourceString
0x1800072ea  lea     rcx, [rsp+48h+var_28]; DestinationString
0x1800072ef  call    cs:__imp_RtlUnicodeStringToOemString
0x1800072f5  test    eax, eax
0x1800072f7  js      short loc_18000730E
0x1800072f9  mov     rax, [rsp+48h+var_28.Buffer]
0x1800072fe  add     rsp, 40h
0x180007302  pop     rbx
0x180007303  retn
0x180007304  mov     rax, rbx
0x180007307  mov     [rsp+48h+var_28.Buffer], rbx
0x18000730c  jmp     short loc_1800072DD
0x18000730e  test    rbx, rbx
0x180007311  jnz     short loc_18000731D
0x180007313  lea     rcx, [rsp+48h+var_28.Buffer]
0x180007318  call    DhcpPunycodeFree
0x18000731d  xor     eax, eax
0x18000731f  jmp     short loc_1800072FE
```
