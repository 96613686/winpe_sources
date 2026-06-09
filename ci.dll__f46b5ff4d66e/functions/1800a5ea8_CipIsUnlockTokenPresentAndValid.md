# CipIsUnlockTokenPresentAndValid

- ea: `0x1800a5ea8`
- end: `0x1800a5f82`
- name: `CipIsUnlockTokenPresentAndValid`
- size: `218`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180074730`
- `0x1800a5cf8`

## callees

- `0x18000e15c`
- `0x1800a5ea8`
- `0x1800a5f88`
- `0x1800a5fa8`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1800a5f47`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800a5f47`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1800a5f02`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1800a5f02`

## string_xrefs

- `0x1800a5ec3`: `\EFI\Microsoft\Boot\Policies\UnlockToken.pol`

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
0x1800a5ea8  mov     [rsp-8+arg_10], rbx
0x1800a5ead  mov     [rsp-8+arg_18], rdi
0x1800a5eb2  push    rbp
0x1800a5eb3  mov     rbp, rsp
0x1800a5eb6  sub     rsp, 60h
0x1800a5eba  xor     edi, edi
0x1800a5ebc  mov     [rbp+arg_0], 0
0x1800a5ec3  lea     rax, aEfiMicrosoftBo_1; "\\EFI\\Microsoft\\Boot\\Policies\\Unloc"...
0x1800a5eca  mov     [rbp+arg_8], rdi
0x1800a5ece  mov     [rbp+Parameter], rax
0x1800a5ed2  lea     rdx, [rbp+Parameter]; Parameter
0x1800a5ed6  lea     rax, [rbp+UnicodeString]
0x1800a5eda  mov     [rbp+var_8], rdi
0x1800a5ede  xorps   xmm0, xmm0
0x1800a5ee1  mov     [rbp+var_18], rax
0x1800a5ee5  xor     r9d, r9d; Wait
0x1800a5ee8  mov     [rbp+var_10], rdi
0x1800a5eec  mov     r8d, 11800h; Size
0x1800a5ef2  mov     [rsp+60h+Context], rdi; Context
0x1800a5ef7  lea     rcx, CipGetSupplementalPolicyPathOnExpandedStackCallout; Callout
0x1800a5efe  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x1800a5f02  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x1800a5f09  nop     dword ptr [rax+rax+00h]
0x1800a5f0e  mov     ebx, eax
0x1800a5f10  test    eax, eax
0x1800a5f12  js      short loc_1800A5F36
0x1800a5f14  mov     ebx, dword ptr [rbp+var_8]
0x1800a5f17  test    ebx, ebx
0x1800a5f19  js      short loc_1800A5F36
0x1800a5f1b  mov     rdx, [rbp+UnicodeString.Buffer]
0x1800a5f1f  lea     r9, [rbp+arg_0]
0x1800a5f23  lea     r8, [rbp+arg_8]
0x1800a5f27  call    SbLoadFile
0x1800a5f2c  mov     rdi, [rbp+arg_8]
0x1800a5f30  mov     ebx, eax
0x1800a5f32  test    eax, eax
0x1800a5f34  jns     short loc_1800A5F68
0x1800a5f36  test    rdi, rdi
0x1800a5f39  jz      short loc_1800A5F43
0x1800a5f3b  mov     rcx, rdi
0x1800a5f3e  call    SbeFree
0x1800a5f43  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x1800a5f47  call    cs:__imp_RtlFreeUnicodeString
0x1800a5f4e  nop     dword ptr [rax+rax+00h]
0x1800a5f53  lea     r11, [rsp+60h+var_s0]
0x1800a5f58  mov     eax, ebx
0x1800a5f5a  mov     rbx, [r11+20h]
0x1800a5f5e  mov     rdi, [r11+28h]
0x1800a5f62  mov     rsp, r11
0x1800a5f65  pop     rbp
0x1800a5f66  retn
0x1800a5f68  mov     r8b, byte ptr cs:g_CiOptions
0x1800a5f6f  mov     rcx, rdi
0x1800a5f72  mov     edx, [rbp+arg_0]
0x1800a5f75  and     r8b, 8
0x1800a5f79  call    SbValidateSkuUnlockToken
0x1800a5f7e  mov     ebx, eax
0x1800a5f80  jmp     short loc_1800A5F36
```
