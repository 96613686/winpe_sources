# Dhcpv6UnicodeToOem

- ea: `0x18001e060`
- end: `0x18001e10a`
- name: `Dhcpv6UnicodeToOem`
- size: `170`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180005014`

## callees

- `0x180007564`
- `0x18000c740`
- `0x18001e060`

## import_xrefs

- `ntdll!RtlUnicodeStringToOemString` at `0x18001e0d8`
- `ntdll!RtlUnicodeStringToOemString` at `0x18001e0d8`
- `ntdll!RtlxUnicodeStringToOemSize` at `0x18001e09a`
- `ntdll!RtlxUnicodeStringToOemSize` at `0x18001e09a`
- `ntdll!RtlInitUnicodeString` at `0x18001e085`
- `ntdll!RtlInitUnicodeString` at `0x18001e085`

## pseudocode

```c
PCHAR __fastcall Dhcpv6UnicodeToOem(PCWSTR SourceString, CHAR *a2)
{
  CHAR *v3; // rax
  struct _STRING v5; // [rsp+20h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF

  v5 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  if ( a2 )
  {
    v5.Buffer = a2;
    v5.MaximumLength = 1000;
    v3 = a2;
  }
  else
  {
    v5.MaximumLength = RtlxUnicodeStringToOemSize(&DestinationString);
    v3 = (CHAR *)DhcpAlloc(v5.MaximumLength);
    v5.Buffer = v3;
  }
  if ( !v3 )
    return 0;
  if ( RtlUnicodeStringToOemString(&v5, &DestinationString, 0) < 0 )
  {
    if ( !a2 )
      DhcpFree((LPVOID *)&v5.Buffer);
    return 0;
  }
  return v5.Buffer;
}

```

## disassembly

```asm
0x18001e060  mov     [rsp-8+arg_0], rbx
0x18001e065  push    rbp
0x18001e066  mov     rbp, rsp
0x18001e069  sub     rsp, 40h
0x18001e06d  mov     rbx, rdx
0x18001e070  xorps   xmm0, xmm0
0x18001e073  mov     rdx, rcx; SourceString
0x18001e076  xorps   xmm1, xmm1
0x18001e079  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001e07d  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x18001e081  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x18001e085  call    cs:__imp_RtlInitUnicodeString
0x18001e08c  nop     dword ptr [rax+rax+00h]
0x18001e091  test    rbx, rbx
0x18001e094  jnz     short loc_18001E0B8
0x18001e096  lea     rcx, [rbp+DestinationString]; UnicodeString
0x18001e09a  call    cs:__imp_RtlxUnicodeStringToOemSize
0x18001e0a1  nop     dword ptr [rax+rax+00h]
0x18001e0a6  movzx   ecx, ax
0x18001e0a9  mov     [rbp+var_20.MaximumLength], ax
0x18001e0ad  call    DhcpAlloc
0x18001e0b2  mov     [rbp+var_20.Buffer], rax
0x18001e0b6  jmp     short loc_18001E0C8
0x18001e0b8  mov     eax, 3E8h
0x18001e0bd  mov     [rbp+var_20.Buffer], rbx
0x18001e0c1  mov     [rbp+var_20.MaximumLength], ax
0x18001e0c5  mov     rax, rbx
0x18001e0c8  test    rax, rax
0x18001e0cb  jz      short loc_18001E0F6
0x18001e0cd  xor     r8d, r8d; AllocateDestinationString
0x18001e0d0  lea     rdx, [rbp+DestinationString]; SourceString
0x18001e0d4  lea     rcx, [rbp+var_20]; DestinationString
0x18001e0d8  call    cs:__imp_RtlUnicodeStringToOemString
0x18001e0df  nop     dword ptr [rax+rax+00h]
0x18001e0e4  test    eax, eax
0x18001e0e6  jns     short loc_18001E104
0x18001e0e8  test    rbx, rbx
0x18001e0eb  jnz     short loc_18001E0F6
0x18001e0ed  lea     rcx, [rbp+var_20.Buffer]
0x18001e0f1  call    DhcpFree
0x18001e0f6  xor     eax, eax
0x18001e0f8  mov     rbx, [rsp+40h+arg_0]
0x18001e0fd  add     rsp, 40h
0x18001e101  pop     rbp
0x18001e102  retn
0x18001e104  mov     rax, [rbp+var_20.Buffer]
0x18001e108  jmp     short loc_18001E0F8
```
