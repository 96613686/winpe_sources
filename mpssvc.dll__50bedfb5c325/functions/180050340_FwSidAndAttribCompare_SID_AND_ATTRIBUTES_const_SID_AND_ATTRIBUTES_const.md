# FwSidAndAttribCompare(_SID_AND_ATTRIBUTES const *,_SID_AND_ATTRIBUTES const *)

- ea: `0x180050340`
- end: `0x180050407`
- name: `?FwSidAndAttribCompare@@YAHPEBU_SID_AND_ATTRIBUTES@@0@Z`
- size: `199`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180050340`
- `0x180076d66`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180050357`
- `ntdll!RtlLengthSid` at `0x180050368`
- `ntdll!RtlLengthSid` at `0x18005037f`
- `ntdll!RtlLengthSid` at `0x1800503b3`
- `ntdll!RtlLengthSid` at `0x1800503c4`
- `ntdll!RtlLengthSid` at `0x1800503d7`
- `ntdll!RtlLengthSid` at `0x1800503e8`
- `ntdll!RtlLengthSid` at `0x180050357`
- `ntdll!RtlLengthSid` at `0x180050368`
- `ntdll!RtlLengthSid` at `0x18005037f`
- `ntdll!RtlLengthSid` at `0x1800503b3`
- `ntdll!RtlLengthSid` at `0x1800503c4`
- `ntdll!RtlLengthSid` at `0x1800503d7`
- `ntdll!RtlLengthSid` at `0x1800503e8`

## pseudocode

```c
__int64 __fastcall FwSidAndAttribCompare(PSID *a1, const void **a2)
{
  void *v2; // rbx
  ULONG v5; // edi
  PSID v6; // rcx
  ULONG v7; // eax
  void *v8; // rbp
  unsigned int v9; // edi
  ULONG v11; // ebx
  ULONG v12; // ebx

  v2 = (void *)*a2;
  v5 = RtlLengthSid(*a1);
  if ( v5 < RtlLengthSid(v2) )
    v6 = *a1;
  else
    v6 = (PSID)*a2;
  v7 = RtlLengthSid(v6);
  v8 = (void *)*a2;
  v9 = memcmp_0(*a1, *a2, v7);
  if ( v9 )
    return v9;
  v11 = RtlLengthSid(*a1);
  if ( v11 == RtlLengthSid(v8) )
    return v9;
  v12 = RtlLengthSid(*a1);
  return RtlLengthSid((PSID)*a2) < v12 ? 1 : -1;
}

```

## disassembly

```asm
0x180050340  push    rbx
0x180050342  push    rbp
0x180050343  push    rsi
0x180050344  push    rdi
0x180050345  push    r14
0x180050347  sub     rsp, 20h
0x18005034b  mov     rbx, [rdx]
0x18005034e  mov     r14, rcx
0x180050351  mov     rcx, [rcx]; Sid
0x180050354  mov     rsi, rdx
0x180050357  call    cs:__imp_RtlLengthSid
0x18005035e  nop     dword ptr [rax+rax+00h]
0x180050363  mov     rcx, rbx; Sid
0x180050366  mov     edi, eax
0x180050368  call    cs:__imp_RtlLengthSid
0x18005036f  nop     dword ptr [rax+rax+00h]
0x180050374  cmp     edi, eax
0x180050376  jb      loc_1800503FF
0x18005037c  mov     rcx, [rsi]; Sid
0x18005037f  call    cs:__imp_RtlLengthSid
0x180050386  nop     dword ptr [rax+rax+00h]
0x18005038b  mov     rbp, [rsi]
0x18005038e  mov     rcx, [r14]; Buf1
0x180050391  mov     rdx, rbp; Buf2
0x180050394  mov     r8d, eax; Size
0x180050397  call    memcmp_0
0x18005039c  mov     edi, eax
0x18005039e  test    eax, eax
0x1800503a0  jz      short loc_1800503B0
0x1800503a2  mov     eax, edi
0x1800503a4  add     rsp, 20h
0x1800503a8  pop     r14
0x1800503aa  pop     rdi
0x1800503ab  pop     rsi
0x1800503ac  pop     rbp
0x1800503ad  pop     rbx
0x1800503ae  retn
0x1800503b0  mov     rcx, [r14]; Sid
0x1800503b3  call    cs:__imp_RtlLengthSid
0x1800503ba  nop     dword ptr [rax+rax+00h]
0x1800503bf  mov     rcx, rbp; Sid
0x1800503c2  mov     ebx, eax
0x1800503c4  call    cs:__imp_RtlLengthSid
0x1800503cb  nop     dword ptr [rax+rax+00h]
0x1800503d0  cmp     ebx, eax
0x1800503d2  jz      short loc_1800503A2
0x1800503d4  mov     rcx, [r14]; Sid
0x1800503d7  call    cs:__imp_RtlLengthSid
0x1800503de  nop     dword ptr [rax+rax+00h]
0x1800503e3  mov     rcx, [rsi]; Sid
0x1800503e6  mov     ebx, eax
0x1800503e8  call    cs:__imp_RtlLengthSid
0x1800503ef  nop     dword ptr [rax+rax+00h]
0x1800503f4  cmp     eax, ebx
0x1800503f6  sbb     eax, eax
0x1800503f8  and     eax, 2
0x1800503fb  dec     eax
0x1800503fd  jmp     short loc_1800503A4
0x1800503ff  mov     rcx, [r14]
0x180050402  jmp     loc_18005037F
```
