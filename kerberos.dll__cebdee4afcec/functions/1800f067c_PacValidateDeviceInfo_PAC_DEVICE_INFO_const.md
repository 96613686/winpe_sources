# PacValidateDeviceInfo(_PAC_DEVICE_INFO * const)

- ea: `0x1800f067c`
- end: `0x1800f0752`
- name: `?PacValidateDeviceInfo@@YAJQEAU_PAC_DEVICE_INFO@@@Z`
- size: `214`
- prototype: `__int64 __fastcall(struct _PAC_DEVICE_INFO *const)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800f05f4`

## callees

- `0x1800f067c`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x1800f06c6`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800f0706`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800f06c6`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800f0706`
- `ntdll!RtlValidSid` at `0x1800f06b8`
- `ntdll!RtlValidSid` at `0x1800f06f4`
- `ntdll!RtlValidSid` at `0x1800f0729`
- `ntdll!RtlValidSid` at `0x1800f06b8`
- `ntdll!RtlValidSid` at `0x1800f06f4`
- `ntdll!RtlValidSid` at `0x1800f0729`

## pseudocode

```c
__int64 __fastcall PacValidateDeviceInfo(struct _PAC_DEVICE_INFO *const a1)
{
  unsigned int v1; // eax
  unsigned int v3; // ecx
  unsigned int v4; // esi
  __int64 i; // rdi
  __int64 v6; // rcx
  unsigned int j; // edi

  v1 = *((_DWORD *)a1 + 4);
  if ( v1 > 0x4000 )
    return 3221225818LL;
  v3 = *((_DWORD *)a1 + 8);
  if ( v3 > 0x4000 )
    return 3221225818LL;
  v4 = v3 + v1;
  if ( v3 + v1 > 0x4000 )
    return 3221225818LL;
  if ( !RtlValidSid(*((PSID *)a1 + 1)) || *RtlSubAuthorityCountSid(*((PSID *)a1 + 1)) == 15 )
    return 3221225592LL;
  for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 12); i = (unsigned int)(i + 1) )
  {
    v6 = *((_QWORD *)a1 + 7);
    if ( *(_DWORD *)(v6 + 24 * i + 8) > 0x4000u )
      return 3221225818LL;
    v4 += *(_DWORD *)(v6 + 24 * i + 8);
    if ( v4 > 0x4000 )
      return 3221225818LL;
    if ( !RtlValidSid(*(PSID *)(v6 + 24 * i)) || *RtlSubAuthorityCountSid(*(PSID *)(*((_QWORD *)a1 + 7) + 24 * i)) == 15 )
      return 3221225592LL;
  }
  for ( j = 0; j < *((_DWORD *)a1 + 8); ++j )
  {
    if ( !RtlValidSid(*(PSID *)(*((_QWORD *)a1 + 5) + 16LL * j)) )
      return 3221225592LL;
  }
  return 0;
}

```

## disassembly

```asm
0x1800f067c  push    rbx
0x1800f067e  push    rbp
0x1800f067f  push    rsi
0x1800f0680  push    rdi
0x1800f0681  push    r14
0x1800f0683  sub     rsp, 20h
0x1800f0687  mov     eax, [rcx+10h]
0x1800f068a  mov     r14d, 4000h
0x1800f0690  mov     rbx, rcx
0x1800f0693  cmp     eax, r14d
0x1800f0696  ja      loc_1800F0742
0x1800f069c  mov     ecx, [rcx+20h]
0x1800f069f  cmp     ecx, r14d
0x1800f06a2  ja      loc_1800F0742
0x1800f06a8  lea     esi, [rcx+rax]
0x1800f06ab  cmp     esi, r14d
0x1800f06ae  ja      loc_1800F0742
0x1800f06b4  mov     rcx, [rbx+8]; Sid
0x1800f06b8  call    cs:__imp_RtlValidSid
0x1800f06be  test    al, al
0x1800f06c0  jz      short loc_1800F073B
0x1800f06c2  mov     rcx, [rbx+8]; Sid
0x1800f06c6  call    cs:__imp_RtlSubAuthorityCountSid
0x1800f06cc  cmp     byte ptr [rax], 0Fh
0x1800f06cf  jz      short loc_1800F073B
0x1800f06d1  xor     edi, edi
0x1800f06d3  cmp     edi, [rbx+30h]
0x1800f06d6  jnb     short loc_1800F0715
0x1800f06d8  mov     rcx, [rbx+38h]
0x1800f06dc  lea     rbp, [rdi+rdi*2]
0x1800f06e0  cmp     [rcx+rbp*8+8], r14d
0x1800f06e5  ja      short loc_1800F0742
0x1800f06e7  add     esi, [rcx+rbp*8+8]
0x1800f06eb  cmp     esi, r14d
0x1800f06ee  ja      short loc_1800F0742
0x1800f06f0  mov     rcx, [rcx+rbp*8]; Sid
0x1800f06f4  call    cs:__imp_RtlValidSid
0x1800f06fa  test    al, al
0x1800f06fc  jz      short loc_1800F073B
0x1800f06fe  mov     rcx, [rbx+38h]
0x1800f0702  mov     rcx, [rcx+rbp*8]; Sid
0x1800f0706  call    cs:__imp_RtlSubAuthorityCountSid
0x1800f070c  cmp     byte ptr [rax], 0Fh
0x1800f070f  jz      short loc_1800F073B
0x1800f0711  inc     edi
0x1800f0713  jmp     short loc_1800F06D3
0x1800f0715  xor     edi, edi
0x1800f0717  cmp     edi, [rbx+20h]
0x1800f071a  jnb     short loc_1800F0737
0x1800f071c  mov     rcx, [rbx+28h]
0x1800f0720  mov     eax, edi
0x1800f0722  add     rax, rax
0x1800f0725  mov     rcx, [rcx+rax*8]; Sid
0x1800f0729  call    cs:__imp_RtlValidSid
0x1800f072f  test    al, al
0x1800f0731  jz      short loc_1800F073B
0x1800f0733  inc     edi
0x1800f0735  jmp     short loc_1800F0717
0x1800f0737  xor     eax, eax
0x1800f0739  jmp     short loc_1800F0747
0x1800f073b  mov     eax, 0C0000078h
0x1800f0740  jmp     short loc_1800F0747
0x1800f0742  mov     eax, 0C000015Ah
0x1800f0747  add     rsp, 20h
0x1800f074b  pop     r14
0x1800f074d  pop     rdi
0x1800f074e  pop     rsi
0x1800f074f  pop     rbp
0x1800f0750  pop     rbx
0x1800f0751  retn
```
