# ParseMsgSecurityContext

- ea: `0x18000bf80`
- end: `0x18000c008`
- name: `ParseMsgSecurityContext`
- size: `136`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000bf80`
- `0x1800136dc`
- `0x180013bbc`
- `0x180013c74`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000bfc2`
- `KERNEL32!LeaveCriticalSection` at `0x18000bfc2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ParseMsgSecurityContext(__int64 a1, __int64 a2)
{
  unsigned int v3; // edi
  CContextMap *v5; // rcx
  __int64 v6; // rdi

  v3 = *(_DWORD *)(a1 + 8);
  if ( !v3 )
    return 1074659331;
  try
  {
    CCriticalSection::Lock((CCriticalSection *)&CriticalSection);
    v6 = *(_QWORD *)CContextMap::FindContext(v5, v3);
    LeaveCriticalSection(&CriticalSection);
  }
  catch ( exception )
  {
    LogMsgHR(-1072824267, (wchar_t *)L"rt/property", 0x1B3u);
    return 3222143029LL;
  }
  if ( *(_DWORD *)(v6 + 32) == 1 )
  {
    *(_QWORD *)a2 = v6;
    *(_DWORD *)(a2 + 8) |= 2u;
    return 0;
  }
  else
  {
    LogMsgHR(-1072824267, (wchar_t *)L"rt/property", 0x1B8u);
    return 3222143029LL;
  }
}

```

## disassembly

```asm
0x18000bf80  mov     [rsp+arg_8], rbx
0x18000bf85  mov     [rsp+arg_10], rsi
0x18000bf8a  push    rdi
0x18000bf8b  sub     rsp, 20h
0x18000bf8f  mov     rbx, rdx
0x18000bf92  mov     edi, [rcx+8]
0x18000bf95  test    edi, edi
0x18000bf97  jnz     short loc_18000BFA0
0x18000bf99  mov     eax, 400E0003h
0x18000bf9e  jmp     short loc_18000BFF8
0x18000bfa0  lea     rsi, CriticalSection
0x18000bfa7  mov     [rsp+28h+arg_0], rsi
0x18000bfac  mov     rcx, rsi; this
0x18000bfaf  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18000bfb4  nop
0x18000bfb5  mov     edx, edi; unsigned int
0x18000bfb7  call    ?FindContext@CContextMap@@IEAAPEAUContextEntry@1@K@Z; CContextMap::FindContext(ulong)
0x18000bfbc  mov     rdi, [rax]
0x18000bfbf  mov     rcx, rsi; lpCriticalSection
0x18000bfc2  call    cs:__imp_LeaveCriticalSection
0x18000bfc8  nop
0x18000bfc9  cmp     dword ptr [rdi+20h], 1
0x18000bfcd  jz      short loc_18000BFE8
0x18000bfcf  mov     r8d, 1B8h; unsigned __int16
0x18000bfd5  lea     rdx, aRtProperty; "rt/property"
0x18000bfdc  mov     ecx, 0C00E0035h; int
0x18000bfe1  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000bfe6  jmp     short loc_18000BFF3
0x18000bfe8  mov     [rbx], rdi
0x18000bfeb  or      dword ptr [rbx+8], 2
0x18000bfef  xor     eax, eax
0x18000bff1  jmp     short loc_18000BFF8
0x18000bff3  mov     eax, 0C00E0035h
0x18000bff8  mov     rbx, [rsp+28h+arg_8]
0x18000bffd  mov     rsi, [rsp+28h+arg_10]
0x18000c002  add     rsp, 20h
0x18000c006  pop     rdi
0x18000c007  retn
```
