# ComparePrefixSids

- ea: `0x1800441bc`
- end: `0x18004425e`
- name: `ComparePrefixSids`
- size: `162`
- prototype: `__int64 __fastcall(PSID Sid, PSID)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180044264`

## callees

- `0x1800441bc`
- `0x18004a0c5`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180044241`
- `ntdll!RtlEqualSid` at `0x180044241`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800441fc`
- `ntdll!RtlSubAuthorityCountSid` at `0x18004420e`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800441fc`
- `ntdll!RtlSubAuthorityCountSid` at `0x18004420e`

## pseudocode

```c
BOOLEAN __fastcall ComparePrefixSids(char *Sid, char *a2)
{
  int v4; // ecx
  unsigned int v5; // ebx
  __int64 v6; // r8

  if ( Sid[1] == 1 || a2[1] == 1 )
    return RtlEqualSid(Sid, a2);
  if ( *Sid != *a2 )
    return 0;
  v4 = *(_DWORD *)(Sid + 2) - *(_DWORD *)(a2 + 2);
  if ( !v4 )
    v4 = *((unsigned __int16 *)Sid + 3) - *((unsigned __int16 *)a2 + 3);
  if ( v4 )
    return 0;
  v5 = *RtlSubAuthorityCountSid(Sid);
  v6 = *RtlSubAuthorityCountSid(a2);
  if ( (unsigned __int8)v5 <= (unsigned __int8)v6 )
    v6 = v5;
  return memcmp_0(Sid + 8, a2 + 8, 4 * v6) == 0;
}

```

## disassembly

```asm
0x1800441bc  mov     [rsp+arg_0], rbx
0x1800441c1  mov     [rsp+arg_8], rsi
0x1800441c6  push    rdi
0x1800441c7  sub     rsp, 20h
0x1800441cb  cmp     byte ptr [rcx+1], 1
0x1800441cf  mov     rdi, rdx
0x1800441d2  mov     rsi, rcx
0x1800441d5  jz      short loc_180044241
0x1800441d7  cmp     byte ptr [rdx+1], 1
0x1800441db  jz      short loc_180044241
0x1800441dd  mov     al, [rdx]
0x1800441df  cmp     [rcx], al
0x1800441e1  jnz     short loc_18004423D
0x1800441e3  mov     ecx, [rcx+2]
0x1800441e6  sub     ecx, [rdx+2]
0x1800441e9  jnz     short loc_1800441F5
0x1800441eb  movzx   ecx, word ptr [rsi+6]
0x1800441ef  movzx   eax, word ptr [rdx+6]
0x1800441f3  sub     ecx, eax
0x1800441f5  test    ecx, ecx
0x1800441f7  jnz     short loc_18004423D
0x1800441f9  mov     rcx, rsi; Sid
0x1800441fc  call    cs:__imp_RtlSubAuthorityCountSid
0x180044203  nop     dword ptr [rax+rax+00h]
0x180044208  mov     rcx, rdi; Sid
0x18004420b  movzx   ebx, byte ptr [rax]
0x18004420e  call    cs:__imp_RtlSubAuthorityCountSid
0x180044215  nop     dword ptr [rax+rax+00h]
0x18004421a  lea     rdx, [rdi+8]; Buf2
0x18004421e  lea     rcx, [rsi+8]; Buf1
0x180044222  movzx   r8d, byte ptr [rax]
0x180044226  cmp     bl, r8b
0x180044229  cmovbe  r8d, ebx
0x18004422d  shl     r8, 2; Size
0x180044231  call    memcmp_0
0x180044236  test    eax, eax
0x180044238  setz    al
0x18004423b  jmp     short loc_18004424D
0x18004423d  xor     al, al
0x18004423f  jmp     short loc_18004424D
0x180044241  call    cs:__imp_RtlEqualSid
0x180044248  nop     dword ptr [rax+rax+00h]
0x18004424d  mov     rbx, [rsp+28h+arg_0]
0x180044252  mov     rsi, [rsp+28h+arg_8]
0x180044257  add     rsp, 20h
0x18004425b  pop     rdi
0x18004425c  retn
```
