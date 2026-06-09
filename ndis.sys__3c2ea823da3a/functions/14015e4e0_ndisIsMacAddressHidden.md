# ndisIsMacAddressHidden

- ea: `0x14015e4e0`
- end: `0x14015e6dc`
- name: `ndisIsMacAddressHidden`
- size: `508`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001e580`
- `0x140020d00`
- `0x140023790`

## callees

- `0x1400e6160`
- `0x1400e62c0`
- `0x14015e4e0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14015e657`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14015e657`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x14015e581`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x14015e581`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14015e592`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14015e592`
- `ntoskrnl!wcschr` at `0x14015e5bf`
- `ntoskrnl!wcschr` at `0x14015e5bf`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14015e54f`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14015e54f`

## pseudocode

```c
char __fastcall ndisIsMacAddressHidden(struct _KPROCESS *a1)
{
  PACCESS_TOKEN v1; // rdi
  int v2; // ebx
  __int64 v3; // rbx
  wchar_t *v4; // rax
  int v5; // edi
  unsigned int v6; // esi
  unsigned int v7; // edi
  wchar_t *i; // r14
  int j; // ebx
  __int64 v11; // rax
  int v13; // esp
  int v14; // edi
  _BYTE v15[8]; // [rsp+30h] [rbp-D0h] BYREF
  UNICODE_STRING String1; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  UNICODE_STRING v18; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Str[128]; // [rsp+60h] [rbp-A0h] BYREF
  char v20; // [rsp+160h] [rbp+60h] BYREF

  String1.Buffer = (wchar_t *)&v20;
  v18.Buffer = L"windows.immersivecontrolpanel_cw5n1h2txyewy";
  v17 = 256;
  v15[0] = 0;
  *(_QWORD *)&String1.Length = 8519680;
  *(_DWORD *)&v18.Length = 5767254;
  if ( !ndisForceUWPWlanMacAddressBlock && !ndisCtaPolicyEnabled )
    return 0;
  v1 = PsReferencePrimaryToken(a1);
  v2 = RtlQueryPackageIdentity(v1, Str, &v17, 0, 0, v15);
  PsDereferencePrimaryToken(v1);
  if ( v2 < 0 || !v15[0] )
    return 0;
  v3 = (unsigned int)v17;
  v4 = wcschr(Str, 0x5Fu);
  v5 = (int)v4;
  if ( !v4 )
  {
    v11 = -1;
    while ( Str[++v11] != 0 )
      ;
    v14 = v13 + 96;
    v5 = v14 + 2 * v11;
  }
  v6 = 0;
  v7 = v5 - (unsigned int)Str;
  for ( i = (wchar_t *)((char *)&v18.Buffer + v3 + 6); *i != 95; v6 += 2 )
  {
    if ( i == Str )
      break;
    --i;
  }
  if ( (unsigned __int64)(v6 + v7) + 2 > String1.MaximumLength )
    return 0;
  memmove(String1.Buffer, Str, v7);
  memmove((char *)String1.Buffer + v7, i, v6 + 2LL);
  String1.Length = v7 + v6;
  for ( j = 0; !j; j = 1 )
  {
    if ( !RtlCompareUnicodeString(&String1, &v18, 1u) )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x14015e4e0  mov     [rsp-8+arg_8], rbx
0x14015e4e5  mov     [rsp-8+arg_10], rsi
0x14015e4ea  push    rbp
0x14015e4eb  push    rdi
0x14015e4ec  push    r14
0x14015e4ee  lea     rbp, [rsp-100h]
0x14015e4f6  sub     rsp, 200h
0x14015e4fd  mov     rax, cs:__security_cookie
0x14015e504  xor     rax, rsp
0x14015e507  mov     [rbp+110h+var_20], rax
0x14015e50e  cmp     cs:?ndisForceUWPWlanMacAddressBlock@@3EA, 0; uchar ndisForceUWPWlanMacAddressBlock
0x14015e515  lea     rax, [rbp+110h+var_B0]
0x14015e519  mov     [rsp+210h+String1.Buffer], rax
0x14015e51e  lea     rax, aWindowsImmersi; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x14015e525  mov     [rsp+210h+Src], rax
0x14015e52a  mov     [rsp+210h+var_1C8], 100h
0x14015e533  mov     [rsp+210h+var_1E0], 0
0x14015e538  mov     qword ptr [rsp+210h+String1.Length], 820000h
0x14015e541  mov     [rsp+210h+var_1C0], 580056h
0x14015e549  jz      loc_14015E691
0x14015e54f  call    cs:__imp_PsReferencePrimaryToken
0x14015e556  nop     dword ptr [rax+rax+00h]
0x14015e55b  xor     r9d, r9d
0x14015e55e  lea     r8, [rsp+210h+var_1C8]
0x14015e563  mov     rdi, rax
0x14015e566  lea     rdx, [rsp+210h+Str]
0x14015e56b  lea     rax, [rsp+210h+var_1E0]
0x14015e570  mov     rcx, rdi
0x14015e573  mov     [rsp+210h+var_1E8], rax
0x14015e578  mov     [rsp+210h+var_1F0], 0
0x14015e581  call    cs:__imp_RtlQueryPackageIdentity
0x14015e588  nop     dword ptr [rax+rax+00h]
0x14015e58d  mov     rcx, rdi; PrimaryToken
0x14015e590  mov     ebx, eax
0x14015e592  call    cs:__imp_PsDereferencePrimaryToken
0x14015e599  nop     dword ptr [rax+rax+00h]
0x14015e59e  test    ebx, ebx
0x14015e5a0  js      loc_14015E667
0x14015e5a6  cmp     [rsp+210h+var_1E0], 0
0x14015e5ab  jz      loc_14015E667
0x14015e5b1  mov     ebx, dword ptr [rsp+210h+var_1C8]
0x14015e5b5  lea     rcx, [rsp+210h+Str]; Str
0x14015e5ba  mov     edx, 5Fh ; '_'; Ch
0x14015e5bf  call    cs:__imp_wcschr
0x14015e5c6  nop     dword ptr [rax+rax+00h]
0x14015e5cb  mov     rdi, rax
0x14015e5ce  test    rax, rax
0x14015e5d1  jz      loc_14015E69F
0x14015e5d7  lea     rax, [rsp+210h+Str]
0x14015e5dc  xor     esi, esi
0x14015e5de  sub     edi, eax
0x14015e5e0  lea     r14, [rsp+rbx+210h+Src+6]
0x14015e5e5  cmp     word ptr [r14], 5Fh ; '_'
0x14015e5ea  jnz     loc_14015E6B0
0x14015e5f0  movzx   eax, [rsp+210h+String1.MaximumLength]
0x14015e5f5  lea     ecx, [rsi+rdi]
0x14015e5f8  add     rcx, 2
0x14015e5fc  cmp     rcx, rax
0x14015e5ff  ja      short loc_14015E667
0x14015e601  mov     rcx, [rsp+210h+String1.Buffer]; void *
0x14015e606  lea     rdx, [rsp+210h+Str]; Src
0x14015e60b  mov     r8d, edi; Size
0x14015e60e  mov     ebx, edi
0x14015e610  call    memmove
0x14015e615  mov     rcx, [rsp+210h+String1.Buffer]
0x14015e61a  mov     rdx, r14; Src
0x14015e61d  mov     r8d, esi
0x14015e620  add     rcx, rbx; void *
0x14015e623  add     r8, 2; Size
0x14015e627  call    memmove
0x14015e62c  add     si, di
0x14015e62f  mov     [rsp+210h+String1.Length], si
0x14015e634  xor     ebx, ebx
0x14015e636  movsxd  rax, ebx
0x14015e639  cmp     rax, 1
0x14015e63d  jnb     loc_14015E6D8
0x14015e643  shl     rax, 4
0x14015e647  lea     rdx, [rsp+210h+var_1C0]
0x14015e64c  add     rdx, rax; String2
0x14015e64f  lea     rcx, [rsp+210h+String1]; String1
0x14015e654  mov     r8b, 1; CaseInSensitive
0x14015e657  call    cs:__imp_RtlCompareUnicodeString
0x14015e65e  nop     dword ptr [rax+rax+00h]
0x14015e663  test    eax, eax
0x14015e665  jnz     short loc_14015E6D1
0x14015e667  xor     al, al
0x14015e669  mov     rcx, [rbp+110h+var_20]
0x14015e670  xor     rcx, rsp; StackCookie
0x14015e673  call    __security_check_cookie
0x14015e678  lea     r11, [rsp+210h+var_10]
0x14015e680  mov     rbx, [r11+28h]
0x14015e684  mov     rsi, [r11+30h]
0x14015e688  mov     rsp, r11
0x14015e68b  pop     r14
0x14015e68d  pop     rdi
0x14015e68e  pop     rbp
0x14015e68f  retn
0x14015e691  cmp     cs:?ndisCtaPolicyEnabled@@3EA, 0; uchar ndisCtaPolicyEnabled
0x14015e698  jz      short loc_14015E667
0x14015e69a  jmp     loc_14015E54F
0x14015e69f  lea     rcx, [rsp+210h+Str]
0x14015e6a4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14015e6ab  jmp     loc_14016DF74
0x14015e6b0  lea     rax, [rsp+210h+Str]
0x14015e6b5  cmp     r14, rax
0x14015e6b8  jz      loc_14015E5F0
0x14015e6be  sub     r14, 2
0x14015e6c2  add     esi, 2
0x14015e6c5  cmp     word ptr [r14], 5Fh ; '_'
0x14015e6ca  jnz     short loc_14015E6B0
0x14015e6cc  jmp     loc_14015E5F0
0x14015e6d1  inc     ebx
0x14015e6d3  jmp     loc_14015E636
0x14015e6d8  mov     al, 1
0x14015e6da  jmp     short loc_14015E669
0x14016df74  cmp     word ptr [rcx+rax*2+2], 0
0x14016df7a  lea     rax, [rax+1]
0x14016df7e  jnz     short loc_14016DF74
0x14016df80  lea     edi, [rsp+210h+Str]
0x14016df84  lea     edi, [rdi+rax*2]
0x14016df87  jmp     loc_14015E5D7
```
