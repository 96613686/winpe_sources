# PECheckComponentLoad

- ea: `0x1800a3ae8`
- end: `0x1800a3ce9`
- name: `PECheckComponentLoad`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a39cc`

## callees

- `0x18000ec18`
- `0x18002bef0`
- `0x1800a3ae8`
- `0x1800a3cf0`

## import_xrefs

- `ntoskrnl!PsIsProtectedProcess` at `0x1800a3b49`
- `ntoskrnl!PsIsProtectedProcess` at `0x1800a3b49`
- `ntoskrnl!EtwWrite` at `0x1800a3c49`
- `ntoskrnl!EtwWrite` at `0x1800a3cd8`
- `ntoskrnl!EtwWrite` at `0x1800a3c49`
- `ntoskrnl!EtwWrite` at `0x1800a3cd8`
- `ntoskrnl!IoGetCurrentProcess` at `0x1800a3b3a`
- `ntoskrnl!IoGetCurrentProcess` at `0x1800a3b3a`

## pseudocode

```c
__int64 __fastcall PECheckComponentLoad(int a1, __int64 a2, unsigned int a3, __int64 a4, unsigned __int16 *a5)
{
  BOOL v8; // edi
  PEPROCESS CurrentProcess; // rax
  int v10; // edi
  __int64 v12; // [rsp+30h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+38h] [rbp-48h] BYREF
  __int64 v14; // [rsp+48h] [rbp-38h]
  int v15; // [rsp+50h] [rbp-30h]
  int v16; // [rsp+54h] [rbp-2Ch]
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+58h] [rbp-28h] BYREF
  __int64 v18; // [rsp+68h] [rbp-18h]
  int v19; // [rsp+70h] [rbp-10h]
  int v20; // [rsp+74h] [rbp-Ch]

  v12 = 2;
  if ( a1 >= 0 || a1 == -1073740285 || a1 == -1073740760 )
  {
    v8 = 0;
    if ( !a3 )
    {
      LODWORD(v12) = 1;
      CurrentProcess = IoGetCurrentProcess();
      v8 = PsIsProtectedProcess(CurrentProcess) == 0;
    }
    if ( *((_QWORD *)a5 + 1) && (g_PEAuthConfigOptions & 1) != 0 )
    {
      v14 = *((_QWORD *)a5 + 1);
      UserData.Ptr = (ULONGLONG)&v12;
      v15 = *a5;
      *(_QWORD *)&UserData.Size = 4;
      v16 = 0;
      EtwWrite(g_PEAuthEtwHandle, &PEAUTH_BEGIN_COMPONENT_LOAD, 0, 2u, &UserData);
    }
    v10 = PECheckComponentLoadEx(a2, a4, a5, a3, v8, (char *)&v12 + 4, v12);
    if ( v10 < 0 && v10 != -1073740285 && v10 != -1073740760 )
    {
      if ( a3 )
      {
        PEAuthStoreParameter(1, 0);
        g_PEAuthStateVariables = 0;
      }
      else
      {
        v10 = -1073740760;
      }
    }
    if ( *((_QWORD *)a5 + 1) )
    {
      if ( (g_PEAuthConfigOptions & 1) != 0 )
      {
        v18 = *((_QWORD *)a5 + 1);
        v17.Ptr = (ULONGLONG)&v12 + 4;
        v19 = *a5;
        *(_QWORD *)&v17.Size = 4;
        v20 = 0;
        EtwWrite(g_PEAuthEtwHandle, &PEAUTH_END_COMPONENT_LOAD, 0, 2u, &v17);
      }
    }
    return (unsigned int)v10;
  }
  else
  {
    if ( a3 )
    {
      PEAuthStoreParameter(1, 0);
      g_PEAuthStateVariables = 0;
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1800a3ae8  push    rbp
0x1800a3aea  push    rbx
0x1800a3aeb  push    rsi
0x1800a3aec  push    rdi
0x1800a3aed  push    r12
0x1800a3aef  push    r14
0x1800a3af1  push    r15
0x1800a3af3  mov     rbp, rsp
0x1800a3af6  sub     rsp, 80h
0x1800a3afd  mov     rax, cs:__security_cookie
0x1800a3b04  xor     rax, rsp
0x1800a3b07  mov     [rbp+var_8], rax
0x1800a3b0b  mov     r14, [rbp+arg_20]
0x1800a3b0f  mov     r12, r9
0x1800a3b12  mov     [rbp+var_50], 2
0x1800a3b19  mov     esi, r8d
0x1800a3b1c  mov     [rbp+var_4C], 0
0x1800a3b23  mov     r15, rdx
0x1800a3b26  test    ecx, ecx
0x1800a3b28  js      loc_1800A3BD1
0x1800a3b2e  xor     edi, edi
0x1800a3b30  lea     ebx, [rdi+1]
0x1800a3b33  test    esi, esi
0x1800a3b35  jnz     short loc_1800A3B5A
0x1800a3b37  mov     [rbp+var_50], ebx
0x1800a3b3a  call    cs:__imp_IoGetCurrentProcess
0x1800a3b41  nop     dword ptr [rax+rax+00h]
0x1800a3b46  mov     rcx, rax
0x1800a3b49  call    cs:__imp_PsIsProtectedProcess
0x1800a3b50  nop     dword ptr [rax+rax+00h]
0x1800a3b55  test    eax, eax
0x1800a3b57  cmovz   edi, ebx
0x1800a3b5a  mov     rcx, [r14+8]
0x1800a3b5e  test    rcx, rcx
0x1800a3b61  jz      short loc_1800A3B71
0x1800a3b63  mov     eax, cs:g_PEAuthConfigOptions
0x1800a3b69  test    bl, al
0x1800a3b6b  jnz     loc_1800A3C07
0x1800a3b71  lea     rax, [rbp+var_4C]
0x1800a3b75  mov     r9d, esi
0x1800a3b78  mov     [rsp+80h+var_58], rax
0x1800a3b7d  mov     r8, r14
0x1800a3b80  mov     rdx, r12
0x1800a3b83  mov     dword ptr [rsp+80h+UserData], edi
0x1800a3b87  mov     rcx, r15
0x1800a3b8a  call    PECheckComponentLoadEx
0x1800a3b8f  mov     edi, eax
0x1800a3b91  test    eax, eax
0x1800a3b93  js      loc_1800A3C5A
0x1800a3b99  mov     rcx, [r14+8]
0x1800a3b9d  test    rcx, rcx
0x1800a3ba0  jz      short loc_1800A3BB0
0x1800a3ba2  mov     eax, cs:g_PEAuthConfigOptions
0x1800a3ba8  test    bl, al
0x1800a3baa  jnz     loc_1800A3C96
0x1800a3bb0  mov     eax, edi
0x1800a3bb2  mov     rcx, [rbp+var_8]
0x1800a3bb6  xor     rcx, rsp; StackCookie
0x1800a3bb9  call    __security_check_cookie
0x1800a3bbe  add     rsp, 80h
0x1800a3bc5  pop     r15
0x1800a3bc7  pop     r14
0x1800a3bc9  pop     r12
0x1800a3bcb  pop     rdi
0x1800a3bcc  pop     rsi
0x1800a3bcd  pop     rbx
0x1800a3bce  pop     rbp
0x1800a3bcf  retn
0x1800a3bd1  cmp     ecx, 0C0000603h
0x1800a3bd7  jz      loc_1800A3B2E
0x1800a3bdd  cmp     ecx, 0C0000428h
0x1800a3be3  jz      loc_1800A3B2E
0x1800a3be9  test    esi, esi
0x1800a3beb  jnz     short loc_1800A3BF1
0x1800a3bed  xor     eax, eax
0x1800a3bef  jmp     short loc_1800A3BB2
0x1800a3bf1  xor     edx, edx
0x1800a3bf3  lea     ecx, [rdx+1]
0x1800a3bf6  call    PEAuthStoreParameter
0x1800a3bfb  mov     cs:g_PEAuthStateVariables, 0
0x1800a3c05  jmp     short loc_1800A3BED
0x1800a3c07  lea     rax, [rbp+var_50]
0x1800a3c0b  mov     [rbp+var_38], rcx
0x1800a3c0f  mov     rcx, cs:g_PEAuthEtwHandle; RegHandle
0x1800a3c16  lea     rdx, PEAUTH_BEGIN_COMPONENT_LOAD; EventDescriptor
0x1800a3c1d  mov     [rbp+var_48.Ptr], rax
0x1800a3c21  mov     r9d, 2; UserDataCount
0x1800a3c27  movzx   eax, word ptr [r14]
0x1800a3c2b  xor     r8d, r8d; ActivityId
0x1800a3c2e  mov     [rbp+var_30], eax
0x1800a3c31  lea     rax, [rbp+var_48]
0x1800a3c35  mov     [rsp+80h+UserData], rax; UserData
0x1800a3c3a  mov     qword ptr [rbp+var_48.Size], 4
0x1800a3c42  mov     [rbp+var_2C], 0
0x1800a3c49  call    cs:__imp_EtwWrite
0x1800a3c50  nop     dword ptr [rax+rax+00h]
0x1800a3c55  jmp     loc_1800A3B71
0x1800a3c5a  cmp     edi, 0C0000603h
0x1800a3c60  jz      loc_1800A3B99
0x1800a3c66  mov     eax, 0C0000428h
0x1800a3c6b  cmp     edi, eax
0x1800a3c6d  jz      loc_1800A3B99
0x1800a3c73  test    esi, esi
0x1800a3c75  jz      short loc_1800A3C8F
0x1800a3c77  xor     edx, edx
0x1800a3c79  mov     ecx, ebx
0x1800a3c7b  call    PEAuthStoreParameter
0x1800a3c80  mov     cs:g_PEAuthStateVariables, 0
0x1800a3c8a  jmp     loc_1800A3B99
0x1800a3c8f  mov     edi, eax
0x1800a3c91  jmp     loc_1800A3B99
0x1800a3c96  lea     rax, [rbp+var_4C]
0x1800a3c9a  mov     [rbp+var_18], rcx
0x1800a3c9e  mov     rcx, cs:g_PEAuthEtwHandle; RegHandle
0x1800a3ca5  lea     rdx, PEAUTH_END_COMPONENT_LOAD; EventDescriptor
0x1800a3cac  mov     [rbp+var_28.Ptr], rax
0x1800a3cb0  mov     r9d, 2; UserDataCount
0x1800a3cb6  movzx   eax, word ptr [r14]
0x1800a3cba  xor     r8d, r8d; ActivityId
0x1800a3cbd  mov     [rbp+var_10], eax
0x1800a3cc0  lea     rax, [rbp+var_28]
0x1800a3cc4  mov     [rsp+80h+UserData], rax; UserData
0x1800a3cc9  mov     qword ptr [rbp+var_28.Size], 4
0x1800a3cd1  mov     [rbp+var_C], 0
0x1800a3cd8  call    cs:__imp_EtwWrite
0x1800a3cdf  nop     dword ptr [rax+rax+00h]
0x1800a3ce4  jmp     loc_1800A3BB0
```
