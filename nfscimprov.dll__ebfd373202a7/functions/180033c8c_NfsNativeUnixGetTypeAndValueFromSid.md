# NfsNativeUnixGetTypeAndValueFromSid

- ea: `0x180033c8c`
- end: `0x180033d7b`
- name: `NfsNativeUnixGetTypeAndValueFromSid`
- size: `239`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180019940`

## callees

- `0x180033c8c`

## import_xrefs

- `ntdll!RtlEqualPrefixSid` at `0x180033cbe`
- `ntdll!RtlEqualPrefixSid` at `0x180033cd7`
- `ntdll!RtlEqualPrefixSid` at `0x180033cf2`
- `ntdll!RtlEqualPrefixSid` at `0x180033cbe`
- `ntdll!RtlEqualPrefixSid` at `0x180033cd7`
- `ntdll!RtlEqualPrefixSid` at `0x180033cf2`
- `ntdll!RtlEqualSid` at `0x180033d0d`
- `ntdll!RtlEqualSid` at `0x180033d0d`
- `ntdll!RtlSubAuthoritySid` at `0x180033d4b`
- `ntdll!RtlSubAuthoritySid` at `0x180033d4b`
- `ntdll!RtlValidSid` at `0x180033ca4`
- `ntdll!RtlValidSid` at `0x180033ca4`

## pseudocode

```c
__int64 __fastcall NfsNativeUnixGetTypeAndValueFromSid(PSID Sid, int *a2, ULONG *a3)
{
  ULONG v6; // ebp
  unsigned int v7; // edi
  int v8; // ebx

  v6 = 0;
  if ( RtlValidSid(Sid) )
  {
    v7 = 0;
    if ( RtlEqualPrefixSid(Sid, Sid2) )
    {
      v8 = 2;
    }
    else if ( RtlEqualPrefixSid(Sid, qword_180056750) )
    {
      v8 = 3;
    }
    else if ( RtlEqualPrefixSid(Sid, qword_180056720) )
    {
      v8 = 5;
    }
    else
    {
      v8 = RtlEqualSid(Sid, qword_180056728) != 0 ? 4 : 1;
    }
    if ( a3 && ((unsigned int)(v8 - 2) <= 1 || v8 == 5) )
      v6 = *RtlSubAuthoritySid(Sid, 2u);
  }
  else
  {
    v8 = 0;
    v7 = -1073741704;
  }
  if ( a2 )
    *a2 = v8;
  if ( a3 )
    *a3 = v6;
  return v7;
}

```

## disassembly

```asm
0x180033c8c  push    rbx
0x180033c8e  push    rbp
0x180033c8f  push    rsi
0x180033c90  push    rdi
0x180033c91  push    r14
0x180033c93  push    r15
0x180033c95  sub     rsp, 28h
0x180033c99  mov     r14, r8
0x180033c9c  mov     r15, rdx
0x180033c9f  mov     rsi, rcx
0x180033ca2  xor     ebp, ebp
0x180033ca4  call    cs:__imp_RtlValidSid
0x180033caa  test    al, al
0x180033cac  jz      loc_180033D55
0x180033cb2  mov     rdx, cs:Sid2; Sid2
0x180033cb9  mov     rcx, rsi; Sid1
0x180033cbc  xor     edi, edi
0x180033cbe  call    cs:__imp_RtlEqualPrefixSid
0x180033cc4  test    al, al
0x180033cc6  jz      short loc_180033CCD
0x180033cc8  lea     ebx, [rbp+2]
0x180033ccb  jmp     short loc_180033D20
0x180033ccd  mov     rdx, cs:qword_180056750; Sid2
0x180033cd4  mov     rcx, rsi; Sid1
0x180033cd7  call    cs:__imp_RtlEqualPrefixSid
0x180033cdd  test    al, al
0x180033cdf  jz      short loc_180033CE8
0x180033ce1  mov     ebx, 3
0x180033ce6  jmp     short loc_180033D20
0x180033ce8  mov     rdx, cs:qword_180056720; Sid2
0x180033cef  mov     rcx, rsi; Sid1
0x180033cf2  call    cs:__imp_RtlEqualPrefixSid
0x180033cf8  test    al, al
0x180033cfa  jz      short loc_180033D03
0x180033cfc  mov     ebx, 5
0x180033d01  jmp     short loc_180033D20
0x180033d03  mov     rdx, cs:qword_180056728; Sid2
0x180033d0a  mov     rcx, rsi; Sid1
0x180033d0d  call    cs:__imp_RtlEqualSid
0x180033d13  neg     al
0x180033d15  mov     ebx, 3
0x180033d1a  sbb     ecx, ecx
0x180033d1c  and     ebx, ecx
0x180033d1e  inc     ebx
0x180033d20  test    r14, r14
0x180033d23  jz      short loc_180033D5C
0x180033d25  lea     eax, [rbx-2]
0x180033d28  cmp     eax, 1
0x180033d2b  jbe     short loc_180033D43
0x180033d2d  cmp     ebx, 5
0x180033d30  jnz     short loc_180033D5C
0x180033d32  mov     ecx, ebx
0x180033d34  sub     ecx, 2
0x180033d37  jz      short loc_180033D43
0x180033d39  sub     ecx, 1
0x180033d3c  jz      short loc_180033D43
0x180033d3e  cmp     ecx, 2
0x180033d41  jnz     short loc_180033D57
0x180033d43  mov     edx, 2; SubAuthority
0x180033d48  mov     rcx, rsi; Sid
0x180033d4b  call    cs:__imp_RtlSubAuthoritySid
0x180033d51  mov     ebp, [rax]
0x180033d53  jmp     short loc_180033D5C
0x180033d55  xor     ebx, ebx
0x180033d57  mov     edi, 0C0000078h
0x180033d5c  test    r15, r15
0x180033d5f  jz      short loc_180033D64
0x180033d61  mov     [r15], ebx
0x180033d64  test    r14, r14
0x180033d67  jz      short loc_180033D6C
0x180033d69  mov     [r14], ebp
0x180033d6c  mov     eax, edi
0x180033d6e  add     rsp, 28h
0x180033d72  pop     r15
0x180033d74  pop     r14
0x180033d76  pop     rdi
0x180033d77  pop     rsi
0x180033d78  pop     rbp
0x180033d79  pop     rbx
0x180033d7a  retn
```
