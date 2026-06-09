# CiLogSIPolicyRefreshFinished

- ea: `0x18006ca88`
- end: `0x18006cb37`
- name: `CiLogSIPolicyRefreshFinished`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180057408`

## callees

- `0x18002bef0`
- `0x18006ca88`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x18006cac4`
- `ntoskrnl!EtwEventEnabled` at `0x18006cac4`
- `ntoskrnl!EtwWrite` at `0x18006cb18`
- `ntoskrnl!EtwWrite` at `0x18006cb18`

## pseudocode

```c
NTSTATUS __fastcall CiLogSIPolicyRefreshFinished(__int64 a1, int a2)
{
  int v3; // [rsp+30h] [rbp-30h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+38h] [rbp-28h] BYREF
  __int128 v5; // [rsp+48h] [rbp-18h]
  int v6; // [rsp+78h] [rbp+18h] BYREF

  v6 = a2;
  UserData = 0;
  v3 = g_NumberOfSiPolicies;
  v5 = 0;
  if ( !EtwEventEnabled(g_EtwEventHandle, &CiPolicyRefreshFinished) )
    return 0;
  UserData.Ptr = (ULONGLONG)&v3;
  *(_QWORD *)&UserData.Size = 4;
  *(_QWORD *)&v5 = &v6;
  *((_QWORD *)&v5 + 1) = 4;
  return EtwWrite(g_EtwEventHandle, &CiPolicyRefreshFinished, 0, 2u, &UserData);
}

```

## disassembly

```asm
0x18006ca88  mov     [rsp-8+arg_8], edx
0x18006ca8c  push    rbp
0x18006ca8d  mov     rbp, rsp
0x18006ca90  sub     rsp, 60h
0x18006ca94  mov     rax, cs:__security_cookie
0x18006ca9b  xor     rax, rsp
0x18006ca9e  mov     [rbp+var_8], rax
0x18006caa2  mov     eax, cs:g_NumberOfSiPolicies
0x18006caa8  lea     rdx, CiPolicyRefreshFinished; EventDescriptor
0x18006caaf  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006cab6  xorps   xmm0, xmm0
0x18006cab9  movups  xmmword ptr [rbp+var_28.Ptr], xmm0
0x18006cabd  mov     [rbp+var_30], eax
0x18006cac0  movups  [rbp+var_18], xmm0
0x18006cac4  call    cs:__imp_EtwEventEnabled
0x18006cacb  nop     dword ptr [rax+rax+00h]
0x18006cad0  test    al, al
0x18006cad2  jnz     short loc_18006CAD8
0x18006cad4  xor     eax, eax
0x18006cad6  jmp     short loc_18006CB24
0x18006cad8  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x18006cadf  lea     rax, [rbp+var_30]
0x18006cae3  mov     [rbp+var_28.Ptr], rax
0x18006cae7  lea     rdx, CiPolicyRefreshFinished; EventDescriptor
0x18006caee  lea     rax, [rbp+arg_8]
0x18006caf2  mov     qword ptr [rbp+var_28.Size], 4
0x18006cafa  mov     qword ptr [rbp+var_18], rax
0x18006cafe  mov     r9d, 2; UserDataCount
0x18006cb04  lea     rax, [rbp+var_28]
0x18006cb08  mov     qword ptr [rbp+var_18+8], 4
0x18006cb10  xor     r8d, r8d; ActivityId
0x18006cb13  mov     [rsp+60h+UserData], rax; UserData
0x18006cb18  call    cs:__imp_EtwWrite
0x18006cb1f  nop     dword ptr [rax+rax+00h]
0x18006cb24  mov     rcx, [rbp+var_8]
0x18006cb28  xor     rcx, rsp; StackCookie
0x18006cb2b  call    __security_check_cookie
0x18006cb30  add     rsp, 60h
0x18006cb34  pop     rbp
0x18006cb35  retn
```
