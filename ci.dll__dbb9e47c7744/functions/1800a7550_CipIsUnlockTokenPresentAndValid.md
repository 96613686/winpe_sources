# CipIsUnlockTokenPresentAndValid

- ea: `0x1800a7550`
- end: `0x1800a762a`
- name: `CipIsUnlockTokenPresentAndValid`
- size: `218`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180075cec`
- `0x1800e8a14`

## callees

- `0x18000e15c`
- `0x1800a7550`
- `0x1800a7630`
- `0x1800a7650`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1800a75ef`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800a75ef`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1800a75aa`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1800a75aa`

## string_xrefs

- `0x1800a756b`: `\EFI\Microsoft\Boot\Policies\UnlockToken.pol`

## pseudocode

```c
__int64 CipIsUnlockTokenPresentAndValid()
{
  __int64 v0; // rdi
  __int64 v1; // rcx
  NTSTATUS v2; // ebx
  int v3; // eax
  __int64 v4; // r8
  struct _UNICODE_STRING UnicodeString; // [rsp+30h] [rbp-30h] BYREF
  _QWORD Parameter[3]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v8; // [rsp+58h] [rbp-8h]
  unsigned int v9; // [rsp+70h] [rbp+10h] BYREF
  __int64 v10; // [rsp+78h] [rbp+18h] BYREF

  v0 = 0;
  v9 = 0;
  v10 = 0;
  Parameter[0] = L"\\EFI\\Microsoft\\Boot\\Policies\\UnlockToken.pol";
  v8 = 0;
  Parameter[1] = &UnicodeString;
  Parameter[2] = 0;
  UnicodeString = 0;
  v2 = KeExpandKernelStackAndCalloutEx(CipGetSupplementalPolicyPathOnExpandedStackCallout, Parameter, 0x11800u, 0, 0);
  if ( v2 >= 0 )
  {
    v2 = v8;
    if ( (int)v8 >= 0 )
    {
      v3 = SbLoadFile(v1, UnicodeString.Buffer, &v10, &v9);
      v0 = v10;
      v2 = v3;
      if ( v3 >= 0 )
      {
        LOBYTE(v4) = g_CiOptions & 8;
        v2 = SbValidateSkuUnlockToken(v10, v9, v4);
      }
    }
  }
  if ( v0 )
    SbeFree(v0);
  RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800a7550  mov     [rsp-8+arg_10], rbx
0x1800a7555  mov     [rsp-8+arg_18], rdi
0x1800a755a  push    rbp
0x1800a755b  mov     rbp, rsp
0x1800a755e  sub     rsp, 60h
0x1800a7562  xor     edi, edi
0x1800a7564  mov     [rbp+arg_0], 0
0x1800a756b  lea     rax, aEfiMicrosoftBo_1; "\\EFI\\Microsoft\\Boot\\Policies\\Unloc"...
0x1800a7572  mov     [rbp+arg_8], rdi
0x1800a7576  mov     [rbp+Parameter], rax
0x1800a757a  lea     rdx, [rbp+Parameter]; Parameter
0x1800a757e  lea     rax, [rbp+UnicodeString]
0x1800a7582  mov     [rbp+var_8], rdi
0x1800a7586  xorps   xmm0, xmm0
0x1800a7589  mov     [rbp+var_18], rax
0x1800a758d  xor     r9d, r9d; Wait
0x1800a7590  mov     [rbp+var_10], rdi
0x1800a7594  mov     r8d, 11800h; Size
0x1800a759a  mov     [rsp+60h+Context], rdi; Context
0x1800a759f  lea     rcx, CipGetSupplementalPolicyPathOnExpandedStackCallout; Callout
0x1800a75a6  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x1800a75aa  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x1800a75b1  nop     dword ptr [rax+rax+00h]
0x1800a75b6  mov     ebx, eax
0x1800a75b8  test    eax, eax
0x1800a75ba  js      short loc_1800A75DE
0x1800a75bc  mov     ebx, dword ptr [rbp+var_8]
0x1800a75bf  test    ebx, ebx
0x1800a75c1  js      short loc_1800A75DE
0x1800a75c3  mov     rdx, [rbp+UnicodeString.Buffer]
0x1800a75c7  lea     r9, [rbp+arg_0]
0x1800a75cb  lea     r8, [rbp+arg_8]
0x1800a75cf  call    SbLoadFile
0x1800a75d4  mov     rdi, [rbp+arg_8]
0x1800a75d8  mov     ebx, eax
0x1800a75da  test    eax, eax
0x1800a75dc  jns     short loc_1800A7610
0x1800a75de  test    rdi, rdi
0x1800a75e1  jz      short loc_1800A75EB
0x1800a75e3  mov     rcx, rdi
0x1800a75e6  call    SbeFree
0x1800a75eb  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x1800a75ef  call    cs:__imp_RtlFreeUnicodeString
0x1800a75f6  nop     dword ptr [rax+rax+00h]
0x1800a75fb  lea     r11, [rsp+60h+var_s0]
0x1800a7600  mov     eax, ebx
0x1800a7602  mov     rbx, [r11+20h]
0x1800a7606  mov     rdi, [r11+28h]
0x1800a760a  mov     rsp, r11
0x1800a760d  pop     rbp
0x1800a760e  retn
0x1800a7610  mov     r8b, byte ptr cs:g_CiOptions
0x1800a7617  mov     rcx, rdi
0x1800a761a  mov     edx, [rbp+arg_0]
0x1800a761d  and     r8b, 8
0x1800a7621  call    SbValidateSkuUnlockToken
0x1800a7626  mov     ebx, eax
0x1800a7628  jmp     short loc_1800A75DE
```
