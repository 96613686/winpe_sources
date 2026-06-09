# ndisIsMacAddressHidden

- ea: `0x140165470`
- end: `0x14016566c`
- name: `ndisIsMacAddressHidden`
- size: `508`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400126e0`
- `0x140014e60`
- `0x1400178f0`

## callees

- `0x1400eb380`
- `0x1400eb4c0`
- `0x140165470`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x1401655e7`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1401655e7`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x140165511`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x140165511`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140165522`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140165522`
- `ntoskrnl!wcschr` at `0x14016554f`
- `ntoskrnl!wcschr` at `0x14016554f`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1401654df`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1401654df`

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
0x140165470  mov     [rsp-8+arg_8], rbx
0x140165475  mov     [rsp-8+arg_10], rsi
0x14016547a  push    rbp
0x14016547b  push    rdi
0x14016547c  push    r14
0x14016547e  lea     rbp, [rsp-100h]
0x140165486  sub     rsp, 200h
0x14016548d  mov     rax, cs:__security_cookie
0x140165494  xor     rax, rsp
0x140165497  mov     [rbp+110h+var_20], rax
0x14016549e  cmp     cs:?ndisForceUWPWlanMacAddressBlock@@3EA, 0; uchar ndisForceUWPWlanMacAddressBlock
0x1401654a5  lea     rax, [rbp+110h+var_B0]
0x1401654a9  mov     [rsp+210h+String1.Buffer], rax
0x1401654ae  lea     rax, aWindowsImmersi; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x1401654b5  mov     [rsp+210h+Src], rax
0x1401654ba  mov     [rsp+210h+var_1C8], 100h
0x1401654c3  mov     [rsp+210h+var_1E0], 0
0x1401654c8  mov     qword ptr [rsp+210h+String1.Length], 820000h
0x1401654d1  mov     [rsp+210h+var_1C0], 580056h
0x1401654d9  jz      loc_140165621
0x1401654df  call    cs:__imp_PsReferencePrimaryToken
0x1401654e6  nop     dword ptr [rax+rax+00h]
0x1401654eb  xor     r9d, r9d
0x1401654ee  lea     r8, [rsp+210h+var_1C8]
0x1401654f3  mov     rdi, rax
0x1401654f6  lea     rdx, [rsp+210h+Str]
0x1401654fb  lea     rax, [rsp+210h+var_1E0]
0x140165500  mov     rcx, rdi
0x140165503  mov     [rsp+210h+var_1E8], rax
0x140165508  mov     [rsp+210h+var_1F0], 0
0x140165511  call    cs:__imp_RtlQueryPackageIdentity
0x140165518  nop     dword ptr [rax+rax+00h]
0x14016551d  mov     rcx, rdi; PrimaryToken
0x140165520  mov     ebx, eax
0x140165522  call    cs:__imp_PsDereferencePrimaryToken
0x140165529  nop     dword ptr [rax+rax+00h]
0x14016552e  test    ebx, ebx
0x140165530  js      loc_1401655F7
0x140165536  cmp     [rsp+210h+var_1E0], 0
0x14016553b  jz      loc_1401655F7
0x140165541  mov     ebx, dword ptr [rsp+210h+var_1C8]
0x140165545  lea     rcx, [rsp+210h+Str]; Str
0x14016554a  mov     edx, 5Fh ; '_'; Ch
0x14016554f  call    cs:__imp_wcschr
0x140165556  nop     dword ptr [rax+rax+00h]
0x14016555b  mov     rdi, rax
0x14016555e  test    rax, rax
0x140165561  jz      loc_14016562F
0x140165567  lea     rax, [rsp+210h+Str]
0x14016556c  xor     esi, esi
0x14016556e  sub     edi, eax
0x140165570  lea     r14, [rsp+rbx+210h+Src+6]
0x140165575  cmp     word ptr [r14], 5Fh ; '_'
0x14016557a  jnz     loc_140165640
0x140165580  movzx   eax, [rsp+210h+String1.MaximumLength]
0x140165585  lea     ecx, [rsi+rdi]
0x140165588  add     rcx, 2
0x14016558c  cmp     rcx, rax
0x14016558f  ja      short loc_1401655F7
0x140165591  mov     rcx, [rsp+210h+String1.Buffer]; void *
0x140165596  lea     rdx, [rsp+210h+Str]; Src
0x14016559b  mov     r8d, edi; Size
0x14016559e  mov     ebx, edi
0x1401655a0  call    memmove
0x1401655a5  mov     rcx, [rsp+210h+String1.Buffer]
0x1401655aa  mov     rdx, r14; Src
0x1401655ad  mov     r8d, esi
0x1401655b0  add     rcx, rbx; void *
0x1401655b3  add     r8, 2; Size
0x1401655b7  call    memmove
0x1401655bc  add     si, di
0x1401655bf  mov     [rsp+210h+String1.Length], si
0x1401655c4  xor     ebx, ebx
0x1401655c6  movsxd  rax, ebx
0x1401655c9  cmp     rax, 1
0x1401655cd  jnb     loc_140165668
0x1401655d3  shl     rax, 4
0x1401655d7  lea     rdx, [rsp+210h+var_1C0]
0x1401655dc  add     rdx, rax; String2
0x1401655df  lea     rcx, [rsp+210h+String1]; String1
0x1401655e4  mov     r8b, 1; CaseInSensitive
0x1401655e7  call    cs:__imp_RtlCompareUnicodeString
0x1401655ee  nop     dword ptr [rax+rax+00h]
0x1401655f3  test    eax, eax
0x1401655f5  jnz     short loc_140165661
0x1401655f7  xor     al, al
0x1401655f9  mov     rcx, [rbp+110h+var_20]
0x140165600  xor     rcx, rsp; StackCookie
0x140165603  call    __security_check_cookie
0x140165608  lea     r11, [rsp+210h+var_10]
0x140165610  mov     rbx, [r11+28h]
0x140165614  mov     rsi, [r11+30h]
0x140165618  mov     rsp, r11
0x14016561b  pop     r14
0x14016561d  pop     rdi
0x14016561e  pop     rbp
0x14016561f  retn
0x140165621  cmp     cs:?ndisCtaPolicyEnabled@@3EA, 0; uchar ndisCtaPolicyEnabled
0x140165628  jz      short loc_1401655F7
0x14016562a  jmp     loc_1401654DF
0x14016562f  lea     rcx, [rsp+210h+Str]
0x140165634  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14016563b  jmp     loc_140174E2A
0x140165640  lea     rax, [rsp+210h+Str]
0x140165645  cmp     r14, rax
0x140165648  jz      loc_140165580
0x14016564e  sub     r14, 2
0x140165652  add     esi, 2
0x140165655  cmp     word ptr [r14], 5Fh ; '_'
0x14016565a  jnz     short loc_140165640
0x14016565c  jmp     loc_140165580
0x140165661  inc     ebx
0x140165663  jmp     loc_1401655C6
0x140165668  mov     al, 1
0x14016566a  jmp     short loc_1401655F9
0x140174e2a  cmp     word ptr [rcx+rax*2+2], 0
0x140174e30  lea     rax, [rax+1]
0x140174e34  jnz     short loc_140174E2A
0x140174e36  lea     edi, [rsp+210h+Str]
0x140174e3a  lea     edi, [rdi+rax*2]
0x140174e3d  jmp     loc_140165567
```
