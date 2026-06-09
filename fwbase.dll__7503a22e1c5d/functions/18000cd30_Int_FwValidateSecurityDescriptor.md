# Int_FwValidateSecurityDescriptor

- ea: `0x18000cd30`
- end: `0x18000cdea`
- name: `Int_FwValidateSecurityDescriptor`
- size: `186`
- prototype: `__int64 __fastcall(LPCWSTR StringSecurityDescriptor)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800150e0`

## callees

- `0x18000ccd4`
- `0x18000cd30`
- `0x18000cdf0`
- `0x180017d1c`

## pseudocode

```c
__int64 __fastcall Int_FwValidateSecurityDescriptor(LPCWSTR StringSecurityDescriptor, int a2)
{
  _QWORD *v4; // rcx
  __int64 v6; // rax
  unsigned int v7; // ebx

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 294, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !StringSecurityDescriptor )
    return 0;
  v6 = -1;
  do
    ++v6;
  while ( StringSecurityDescriptor[v6] );
  if ( v6 )
  {
    return (unsigned int)Int_FwValidateAndMigrateSecurityDescriptor(StringSecurityDescriptor, a2, 0);
  }
  else
  {
    v7 = 87;
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 )
      WPP_SF_d(v4[2], 295, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids, 87);
  }
  return v7;
}

```

## disassembly

```asm
0x18000cd30  mov     [rsp+arg_0], rbx
0x18000cd35  mov     [rsp+arg_8], rsi
0x18000cd3a  push    rdi
0x18000cd3b  sub     rsp, 20h
0x18000cd3f  mov     edi, edx
0x18000cd41  mov     rbx, rcx
0x18000cd44  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd4b  lea     rsi, WPP_GLOBAL_Control
0x18000cd52  cmp     rcx, rsi
0x18000cd55  jz      short loc_18000CD5D
0x18000cd57  test    byte ptr [rcx+1Ch], 8
0x18000cd5b  jnz     short loc_18000CDA2
0x18000cd5d  test    rbx, rbx
0x18000cd60  jnz     short loc_18000CD74
0x18000cd62  xor     eax, eax
0x18000cd64  mov     rbx, [rsp+28h+arg_0]
0x18000cd69  mov     rsi, [rsp+28h+arg_8]
0x18000cd6e  add     rsp, 20h
0x18000cd72  pop     rdi
0x18000cd73  retn
0x18000cd74  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000cd7b  nop     dword ptr [rax+rax+00h]
0x18000cd80  inc     rax
0x18000cd83  cmp     word ptr [rbx+rax*2], 0
0x18000cd88  jnz     short loc_18000CD80
0x18000cd8a  test    rax, rax
0x18000cd8d  jz      short loc_18000CDC0
0x18000cd8f  xor     r8d, r8d
0x18000cd92  mov     edx, edi
0x18000cd94  mov     rcx, rbx; StringSecurityDescriptor
0x18000cd97  call    Int_FwValidateAndMigrateSecurityDescriptor
0x18000cd9c  mov     ebx, eax
0x18000cd9e  mov     eax, ebx
0x18000cda0  jmp     short loc_18000CD64
0x18000cda2  mov     rcx, [rcx+10h]
0x18000cda6  lea     r8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x18000cdad  mov     edx, 126h
0x18000cdb2  call    WPP_SF_
0x18000cdb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cdbe  jmp     short loc_18000CD5D
0x18000cdc0  mov     ebx, 57h ; 'W'
0x18000cdc5  cmp     rcx, rsi
0x18000cdc8  jz      short loc_18000CD9E
0x18000cdca  test    byte ptr [rcx+1Ch], 1
0x18000cdce  jz      short loc_18000CD9E
0x18000cdd0  mov     rcx, [rcx+10h]
0x18000cdd4  lea     r8, WPP_dc1da3d064dd39eb2d226a0cd9c5fd20_Traceguids
0x18000cddb  mov     edx, 127h
0x18000cde0  mov     r9d, ebx
0x18000cde3  call    WPP_SF_d
0x18000cde8  jmp     short loc_18000CD9E
```
