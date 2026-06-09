# FwSidAndAttribCompare(_SID_AND_ATTRIBUTES const *,_SID_AND_ATTRIBUTES const *)

- ea: `0x18004d0b0`
- end: `0x18004d145`
- name: `?FwSidAndAttribCompare@@YAHPEBU_SID_AND_ATTRIBUTES@@0@Z`
- size: `149`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18004d0b0`
- `0x1800738a6`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18004d0c7`
- `ntdll!RtlLengthSid` at `0x18004d0d2`
- `ntdll!RtlLengthSid` at `0x18004d0df`
- `ntdll!RtlLengthSid` at `0x18004d10c`
- `ntdll!RtlLengthSid` at `0x18004d117`
- `ntdll!RtlLengthSid` at `0x18004d124`
- `ntdll!RtlLengthSid` at `0x18004d12f`
- `ntdll!RtlLengthSid` at `0x18004d0c7`
- `ntdll!RtlLengthSid` at `0x18004d0d2`
- `ntdll!RtlLengthSid` at `0x18004d0df`
- `ntdll!RtlLengthSid` at `0x18004d10c`
- `ntdll!RtlLengthSid` at `0x18004d117`
- `ntdll!RtlLengthSid` at `0x18004d124`
- `ntdll!RtlLengthSid` at `0x18004d12f`

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
0x18004d0b0  push    rbx
0x18004d0b2  push    rbp
0x18004d0b3  push    rsi
0x18004d0b4  push    rdi
0x18004d0b5  push    r14
0x18004d0b7  sub     rsp, 20h
0x18004d0bb  mov     rbx, [rdx]
0x18004d0be  mov     r14, rcx
0x18004d0c1  mov     rcx, [rcx]; Sid
0x18004d0c4  mov     rsi, rdx
0x18004d0c7  call    cs:__imp_RtlLengthSid
0x18004d0cd  mov     rcx, rbx; Sid
0x18004d0d0  mov     edi, eax
0x18004d0d2  call    cs:__imp_RtlLengthSid
0x18004d0d8  cmp     edi, eax
0x18004d0da  jb      short loc_18004D140
0x18004d0dc  mov     rcx, [rsi]; Sid
0x18004d0df  call    cs:__imp_RtlLengthSid
0x18004d0e5  mov     rbp, [rsi]
0x18004d0e8  mov     rcx, [r14]; Buf1
0x18004d0eb  mov     rdx, rbp; Buf2
0x18004d0ee  mov     r8d, eax; Size
0x18004d0f1  call    memcmp_0
0x18004d0f6  mov     edi, eax
0x18004d0f8  test    eax, eax
0x18004d0fa  jz      short loc_18004D109
0x18004d0fc  mov     eax, edi
0x18004d0fe  add     rsp, 20h
0x18004d102  pop     r14
0x18004d104  pop     rdi
0x18004d105  pop     rsi
0x18004d106  pop     rbp
0x18004d107  pop     rbx
0x18004d108  retn
0x18004d109  mov     rcx, [r14]; Sid
0x18004d10c  call    cs:__imp_RtlLengthSid
0x18004d112  mov     rcx, rbp; Sid
0x18004d115  mov     ebx, eax
0x18004d117  call    cs:__imp_RtlLengthSid
0x18004d11d  cmp     ebx, eax
0x18004d11f  jz      short loc_18004D0FC
0x18004d121  mov     rcx, [r14]; Sid
0x18004d124  call    cs:__imp_RtlLengthSid
0x18004d12a  mov     rcx, [rsi]; Sid
0x18004d12d  mov     ebx, eax
0x18004d12f  call    cs:__imp_RtlLengthSid
0x18004d135  cmp     eax, ebx
0x18004d137  sbb     eax, eax
0x18004d139  and     eax, 2
0x18004d13c  dec     eax
0x18004d13e  jmp     short loc_18004D0FE
0x18004d140  mov     rcx, [r14]
0x18004d143  jmp     short loc_18004D0DF
```
