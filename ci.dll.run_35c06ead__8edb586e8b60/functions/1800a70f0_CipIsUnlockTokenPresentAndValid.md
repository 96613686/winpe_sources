# CipIsUnlockTokenPresentAndValid

- ea: `0x1800a70f0`
- end: `0x1800a71ca`
- name: `CipIsUnlockTokenPresentAndValid`
- size: `218`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180075fcc`
- `0x1800e92b4`

## callees

- `0x18000e16c`
- `0x1800a70f0`
- `0x1800a71d0`
- `0x1800a71f0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1800a718f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800a718f`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1800a714a`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1800a714a`

## string_xrefs

- `0x1800a710b`: `\EFI\Microsoft\Boot\Policies\UnlockToken.pol`

## pseudocode

```c
__int64 CipIsUnlockTokenPresentAndValid()
{
  __int64 v0; // rdi
  __int64 v1; // rcx
  int v2; // ebx
  int v3; // eax
  int v4; // r8d
  struct _UNICODE_STRING UnicodeString; // [rsp+30h] [rbp-30h] BYREF
  _QWORD Parameter[3]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v8; // [rsp+58h] [rbp-8h]
  int v9; // [rsp+70h] [rbp+10h] BYREF
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
0x1800a70f0  mov     [rsp-8+arg_10], rbx
0x1800a70f5  mov     [rsp-8+arg_18], rdi
0x1800a70fa  push    rbp
0x1800a70fb  mov     rbp, rsp
0x1800a70fe  sub     rsp, 60h
0x1800a7102  xor     edi, edi
0x1800a7104  mov     [rbp+arg_0], 0
0x1800a710b  lea     rax, aEfiMicrosoftBo_1; "\\EFI\\Microsoft\\Boot\\Policies\\Unloc"...
0x1800a7112  mov     [rbp+arg_8], rdi
0x1800a7116  mov     [rbp+Parameter], rax
0x1800a711a  lea     rdx, [rbp+Parameter]; Parameter
0x1800a711e  lea     rax, [rbp+UnicodeString]
0x1800a7122  mov     [rbp+var_8], rdi
0x1800a7126  xorps   xmm0, xmm0
0x1800a7129  mov     [rbp+var_18], rax
0x1800a712d  xor     r9d, r9d; Wait
0x1800a7130  mov     [rbp+var_10], rdi
0x1800a7134  mov     r8d, 11800h; Size
0x1800a713a  mov     [rsp+60h+Context], rdi; Context
0x1800a713f  lea     rcx, CipGetSupplementalPolicyPathOnExpandedStackCallout; Callout
0x1800a7146  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x1800a714a  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x1800a7151  nop     dword ptr [rax+rax+00h]
0x1800a7156  mov     ebx, eax
0x1800a7158  test    eax, eax
0x1800a715a  js      short loc_1800A717E
0x1800a715c  mov     ebx, dword ptr [rbp+var_8]
0x1800a715f  test    ebx, ebx
0x1800a7161  js      short loc_1800A717E
0x1800a7163  mov     rdx, [rbp+UnicodeString.Buffer]
0x1800a7167  lea     r9, [rbp+arg_0]
0x1800a716b  lea     r8, [rbp+arg_8]
0x1800a716f  call    SbLoadFile
0x1800a7174  mov     rdi, [rbp+arg_8]
0x1800a7178  mov     ebx, eax
0x1800a717a  test    eax, eax
0x1800a717c  jns     short loc_1800A71B0
0x1800a717e  test    rdi, rdi
0x1800a7181  jz      short loc_1800A718B
0x1800a7183  mov     rcx, rdi
0x1800a7186  call    SbeFree
0x1800a718b  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x1800a718f  call    cs:__imp_RtlFreeUnicodeString
0x1800a7196  nop     dword ptr [rax+rax+00h]
0x1800a719b  lea     r11, [rsp+60h+var_s0]
0x1800a71a0  mov     eax, ebx
0x1800a71a2  mov     rbx, [r11+20h]
0x1800a71a6  mov     rdi, [r11+28h]
0x1800a71aa  mov     rsp, r11
0x1800a71ad  pop     rbp
0x1800a71ae  retn
0x1800a71b0  mov     r8b, byte ptr cs:g_CiOptions
0x1800a71b7  mov     rcx, rdi
0x1800a71ba  mov     edx, [rbp+arg_0]
0x1800a71bd  and     r8b, 8
0x1800a71c1  call    SbValidateSkuUnlockToken
0x1800a71c6  mov     ebx, eax
0x1800a71c8  jmp     short loc_1800A717E
```
