# PECheckComponentLoad

- ea: `0x1800a4d6c`
- end: `0x1800a4f6d`
- name: `PECheckComponentLoad`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a4c50`

## callees

- `0x18000ec28`
- `0x18002c0d0`
- `0x1800a4d6c`
- `0x1800a4f74`

## import_xrefs

- `ntoskrnl!PsIsProtectedProcess` at `0x1800a4dcd`
- `ntoskrnl!PsIsProtectedProcess` at `0x1800a4dcd`
- `ntoskrnl!EtwWrite` at `0x1800a4ecd`
- `ntoskrnl!EtwWrite` at `0x1800a4f5c`
- `ntoskrnl!EtwWrite` at `0x1800a4ecd`
- `ntoskrnl!EtwWrite` at `0x1800a4f5c`
- `ntoskrnl!IoGetCurrentProcess` at `0x1800a4dbe`
- `ntoskrnl!IoGetCurrentProcess` at `0x1800a4dbe`

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
0x1800a4d6c  push    rbp
0x1800a4d6e  push    rbx
0x1800a4d6f  push    rsi
0x1800a4d70  push    rdi
0x1800a4d71  push    r12
0x1800a4d73  push    r14
0x1800a4d75  push    r15
0x1800a4d77  mov     rbp, rsp
0x1800a4d7a  sub     rsp, 80h
0x1800a4d81  mov     rax, cs:__security_cookie
0x1800a4d88  xor     rax, rsp
0x1800a4d8b  mov     [rbp+var_8], rax
0x1800a4d8f  mov     r14, [rbp+arg_20]
0x1800a4d93  mov     r12, r9
0x1800a4d96  mov     [rbp+var_50], 2
0x1800a4d9d  mov     esi, r8d
0x1800a4da0  mov     [rbp+var_4C], 0
0x1800a4da7  mov     r15, rdx
0x1800a4daa  test    ecx, ecx
0x1800a4dac  js      loc_1800A4E55
0x1800a4db2  xor     edi, edi
0x1800a4db4  lea     ebx, [rdi+1]
0x1800a4db7  test    esi, esi
0x1800a4db9  jnz     short loc_1800A4DDE
0x1800a4dbb  mov     [rbp+var_50], ebx
0x1800a4dbe  call    cs:__imp_IoGetCurrentProcess
0x1800a4dc5  nop     dword ptr [rax+rax+00h]
0x1800a4dca  mov     rcx, rax
0x1800a4dcd  call    cs:__imp_PsIsProtectedProcess
0x1800a4dd4  nop     dword ptr [rax+rax+00h]
0x1800a4dd9  test    eax, eax
0x1800a4ddb  cmovz   edi, ebx
0x1800a4dde  mov     rcx, [r14+8]
0x1800a4de2  test    rcx, rcx
0x1800a4de5  jz      short loc_1800A4DF5
0x1800a4de7  mov     eax, cs:g_PEAuthConfigOptions
0x1800a4ded  test    bl, al
0x1800a4def  jnz     loc_1800A4E8B
0x1800a4df5  lea     rax, [rbp+var_4C]
0x1800a4df9  mov     r9d, esi
0x1800a4dfc  mov     [rsp+80h+var_58], rax
0x1800a4e01  mov     r8, r14
0x1800a4e04  mov     rdx, r12
0x1800a4e07  mov     dword ptr [rsp+80h+UserData], edi
0x1800a4e0b  mov     rcx, r15
0x1800a4e0e  call    PECheckComponentLoadEx
0x1800a4e13  mov     edi, eax
0x1800a4e15  test    eax, eax
0x1800a4e17  js      loc_1800A4EDE
0x1800a4e1d  mov     rcx, [r14+8]
0x1800a4e21  test    rcx, rcx
0x1800a4e24  jz      short loc_1800A4E34
0x1800a4e26  mov     eax, cs:g_PEAuthConfigOptions
0x1800a4e2c  test    bl, al
0x1800a4e2e  jnz     loc_1800A4F1A
0x1800a4e34  mov     eax, edi
0x1800a4e36  mov     rcx, [rbp+var_8]
0x1800a4e3a  xor     rcx, rsp; StackCookie
0x1800a4e3d  call    __security_check_cookie
0x1800a4e42  add     rsp, 80h
0x1800a4e49  pop     r15
0x1800a4e4b  pop     r14
0x1800a4e4d  pop     r12
0x1800a4e4f  pop     rdi
0x1800a4e50  pop     rsi
0x1800a4e51  pop     rbx
0x1800a4e52  pop     rbp
0x1800a4e53  retn
0x1800a4e55  cmp     ecx, 0C0000603h
0x1800a4e5b  jz      loc_1800A4DB2
0x1800a4e61  cmp     ecx, 0C0000428h
0x1800a4e67  jz      loc_1800A4DB2
0x1800a4e6d  test    esi, esi
0x1800a4e6f  jnz     short loc_1800A4E75
0x1800a4e71  xor     eax, eax
0x1800a4e73  jmp     short loc_1800A4E36
0x1800a4e75  xor     edx, edx
0x1800a4e77  lea     ecx, [rdx+1]
0x1800a4e7a  call    PEAuthStoreParameter
0x1800a4e7f  mov     cs:g_PEAuthStateVariables, 0
0x1800a4e89  jmp     short loc_1800A4E71
0x1800a4e8b  lea     rax, [rbp+var_50]
0x1800a4e8f  mov     [rbp+var_38], rcx
0x1800a4e93  mov     rcx, cs:g_PEAuthEtwHandle; RegHandle
0x1800a4e9a  lea     rdx, PEAUTH_BEGIN_COMPONENT_LOAD; EventDescriptor
0x1800a4ea1  mov     [rbp+var_48.Ptr], rax
0x1800a4ea5  mov     r9d, 2; UserDataCount
0x1800a4eab  movzx   eax, word ptr [r14]
0x1800a4eaf  xor     r8d, r8d; ActivityId
0x1800a4eb2  mov     [rbp+var_30], eax
0x1800a4eb5  lea     rax, [rbp+var_48]
0x1800a4eb9  mov     [rsp+80h+UserData], rax; UserData
0x1800a4ebe  mov     qword ptr [rbp+var_48.Size], 4
0x1800a4ec6  mov     [rbp+var_2C], 0
0x1800a4ecd  call    cs:__imp_EtwWrite
0x1800a4ed4  nop     dword ptr [rax+rax+00h]
0x1800a4ed9  jmp     loc_1800A4DF5
0x1800a4ede  cmp     edi, 0C0000603h
0x1800a4ee4  jz      loc_1800A4E1D
0x1800a4eea  mov     eax, 0C0000428h
0x1800a4eef  cmp     edi, eax
0x1800a4ef1  jz      loc_1800A4E1D
0x1800a4ef7  test    esi, esi
0x1800a4ef9  jz      short loc_1800A4F13
0x1800a4efb  xor     edx, edx
0x1800a4efd  mov     ecx, ebx
0x1800a4eff  call    PEAuthStoreParameter
0x1800a4f04  mov     cs:g_PEAuthStateVariables, 0
0x1800a4f0e  jmp     loc_1800A4E1D
0x1800a4f13  mov     edi, eax
0x1800a4f15  jmp     loc_1800A4E1D
0x1800a4f1a  lea     rax, [rbp+var_4C]
0x1800a4f1e  mov     [rbp+var_18], rcx
0x1800a4f22  mov     rcx, cs:g_PEAuthEtwHandle; RegHandle
0x1800a4f29  lea     rdx, PEAUTH_END_COMPONENT_LOAD; EventDescriptor
0x1800a4f30  mov     [rbp+var_28.Ptr], rax
0x1800a4f34  mov     r9d, 2; UserDataCount
0x1800a4f3a  movzx   eax, word ptr [r14]
0x1800a4f3e  xor     r8d, r8d; ActivityId
0x1800a4f41  mov     [rbp+var_10], eax
0x1800a4f44  lea     rax, [rbp+var_28]
0x1800a4f48  mov     [rsp+80h+UserData], rax; UserData
0x1800a4f4d  mov     qword ptr [rbp+var_28.Size], 4
0x1800a4f55  mov     [rbp+var_C], 0
0x1800a4f5c  call    cs:__imp_EtwWrite
0x1800a4f63  nop     dword ptr [rax+rax+00h]
0x1800a4f68  jmp     loc_1800A4E34
```
