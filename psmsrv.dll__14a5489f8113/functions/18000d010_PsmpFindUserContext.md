# PsmpFindUserContext

- ea: `0x18000d010`
- end: `0x18000d074`
- name: `PsmpFindUserContext`
- size: `100`
- prototype: `__int64 *__fastcall(__int64, int, void *)`
- caller_count: `12`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001230`
- `0x18000191c`
- `0x18000b3d8`
- `0x18001a190`
- `0x18001aba0`
- `0x18002abe0`
- `0x18002afc0`
- `0x18002b470`
- `0x18002b760`
- `0x18002bd00`
- `0x18002bf90`
- `0x18002c250`

## callees

- `0x18000d010`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18000d039`
- `ntdll!RtlEqualSid` at `0x18000d039`

## pseudocode

```c
__int64 *__fastcall PsmpFindUserContext(__int64 a1, int a2, void *a3)
{
  __int64 *v3; // rdi
  __int64 *v4; // rsi
  signed __int32 v7; // eax
  signed __int32 v8; // edx

  v3 = *(__int64 **)(a1 + 24);
  v4 = (__int64 *)(a1 + 24);
  while ( v3 != v4 )
  {
    if ( *((_DWORD *)v3 - 1) == a2 && RtlEqualSid((PSID)v3[4], a3) )
    {
      _m_prefetchw(v3 - 1);
      v7 = *((_DWORD *)v3 - 2);
      while ( v7 > 0 )
      {
        v8 = v7;
        v7 = _InterlockedCompareExchange((volatile signed __int32 *)v3 - 2, v7 + 1, v7);
        if ( v7 == v8 )
          return v3 - 1;
      }
    }
    v3 = (__int64 *)*v3;
  }
  return 0;
}

```

## disassembly

```asm
0x18000d010  push    rbx
0x18000d012  push    rbp
0x18000d013  push    rsi
0x18000d014  push    rdi
0x18000d015  push    r14
0x18000d017  sub     rsp, 20h
0x18000d01b  mov     rdi, [rcx+18h]
0x18000d01f  lea     rsi, [rcx+18h]
0x18000d023  mov     r14, r8
0x18000d026  mov     ebp, edx
0x18000d028  cmp     rdi, rsi
0x18000d02b  jz      short loc_18000D070
0x18000d02d  cmp     [rdi-4], ebp
0x18000d030  jnz     short loc_18000D06B
0x18000d032  mov     rcx, [rdi+20h]; Sid1
0x18000d036  mov     rdx, r14; Sid2
0x18000d039  call    cs:__imp_RtlEqualSid
0x18000d03f  test    al, al
0x18000d041  jz      short loc_18000D06B
0x18000d043  prefetchw byte ptr [rdi-8]
0x18000d047  mov     eax, [rdi-8]
0x18000d04a  test    eax, eax
0x18000d04c  jle     short loc_18000D06B
0x18000d04e  mov     edx, eax
0x18000d050  lea     ecx, [rax+1]
0x18000d053  lock cmpxchg [rdi-8], ecx
0x18000d058  cmp     eax, edx
0x18000d05a  jnz     short loc_18000D04A
0x18000d05c  lea     rax, [rdi-8]
0x18000d060  add     rsp, 20h
0x18000d064  pop     r14
0x18000d066  pop     rdi
0x18000d067  pop     rsi
0x18000d068  pop     rbp
0x18000d069  pop     rbx
0x18000d06a  retn
0x18000d06b  mov     rdi, [rdi]
0x18000d06e  jmp     short loc_18000D028
0x18000d070  xor     eax, eax
0x18000d072  jmp     short loc_18000D060
```
