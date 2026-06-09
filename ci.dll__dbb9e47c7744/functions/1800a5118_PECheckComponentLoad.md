# PECheckComponentLoad

- ea: `0x1800a5118`
- end: `0x1800a5319`
- name: `PECheckComponentLoad`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a4ffc`

## callees

- `0x18000ec18`
- `0x18002bf20`
- `0x1800a5118`
- `0x1800a5320`

## import_xrefs

- `ntoskrnl!PsIsProtectedProcess` at `0x1800a5179`
- `ntoskrnl!PsIsProtectedProcess` at `0x1800a5179`
- `ntoskrnl!EtwWrite` at `0x1800a5279`
- `ntoskrnl!EtwWrite` at `0x1800a5308`
- `ntoskrnl!EtwWrite` at `0x1800a5279`
- `ntoskrnl!EtwWrite` at `0x1800a5308`
- `ntoskrnl!IoGetCurrentProcess` at `0x1800a516a`
- `ntoskrnl!IoGetCurrentProcess` at `0x1800a516a`

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
0x1800a5118  push    rbp
0x1800a511a  push    rbx
0x1800a511b  push    rsi
0x1800a511c  push    rdi
0x1800a511d  push    r12
0x1800a511f  push    r14
0x1800a5121  push    r15
0x1800a5123  mov     rbp, rsp
0x1800a5126  sub     rsp, 80h
0x1800a512d  mov     rax, cs:__security_cookie
0x1800a5134  xor     rax, rsp
0x1800a5137  mov     [rbp+var_8], rax
0x1800a513b  mov     r14, [rbp+arg_20]
0x1800a513f  mov     r12, r9
0x1800a5142  mov     [rbp+var_50], 2
0x1800a5149  mov     esi, r8d
0x1800a514c  mov     [rbp+var_4C], 0
0x1800a5153  mov     r15, rdx
0x1800a5156  test    ecx, ecx
0x1800a5158  js      loc_1800A5201
0x1800a515e  xor     edi, edi
0x1800a5160  lea     ebx, [rdi+1]
0x1800a5163  test    esi, esi
0x1800a5165  jnz     short loc_1800A518A
0x1800a5167  mov     [rbp+var_50], ebx
0x1800a516a  call    cs:__imp_IoGetCurrentProcess
0x1800a5171  nop     dword ptr [rax+rax+00h]
0x1800a5176  mov     rcx, rax
0x1800a5179  call    cs:__imp_PsIsProtectedProcess
0x1800a5180  nop     dword ptr [rax+rax+00h]
0x1800a5185  test    eax, eax
0x1800a5187  cmovz   edi, ebx
0x1800a518a  mov     rcx, [r14+8]
0x1800a518e  test    rcx, rcx
0x1800a5191  jz      short loc_1800A51A1
0x1800a5193  mov     eax, cs:g_PEAuthConfigOptions
0x1800a5199  test    bl, al
0x1800a519b  jnz     loc_1800A5237
0x1800a51a1  lea     rax, [rbp+var_4C]
0x1800a51a5  mov     r9d, esi
0x1800a51a8  mov     [rsp+80h+var_58], rax
0x1800a51ad  mov     r8, r14
0x1800a51b0  mov     rdx, r12
0x1800a51b3  mov     dword ptr [rsp+80h+UserData], edi
0x1800a51b7  mov     rcx, r15
0x1800a51ba  call    PECheckComponentLoadEx
0x1800a51bf  mov     edi, eax
0x1800a51c1  test    eax, eax
0x1800a51c3  js      loc_1800A528A
0x1800a51c9  mov     rcx, [r14+8]
0x1800a51cd  test    rcx, rcx
0x1800a51d0  jz      short loc_1800A51E0
0x1800a51d2  mov     eax, cs:g_PEAuthConfigOptions
0x1800a51d8  test    bl, al
0x1800a51da  jnz     loc_1800A52C6
0x1800a51e0  mov     eax, edi
0x1800a51e2  mov     rcx, [rbp+var_8]
0x1800a51e6  xor     rcx, rsp; StackCookie
0x1800a51e9  call    __security_check_cookie
0x1800a51ee  add     rsp, 80h
0x1800a51f5  pop     r15
0x1800a51f7  pop     r14
0x1800a51f9  pop     r12
0x1800a51fb  pop     rdi
0x1800a51fc  pop     rsi
0x1800a51fd  pop     rbx
0x1800a51fe  pop     rbp
0x1800a51ff  retn
0x1800a5201  cmp     ecx, 0C0000603h
0x1800a5207  jz      loc_1800A515E
0x1800a520d  cmp     ecx, 0C0000428h
0x1800a5213  jz      loc_1800A515E
0x1800a5219  test    esi, esi
0x1800a521b  jnz     short loc_1800A5221
0x1800a521d  xor     eax, eax
0x1800a521f  jmp     short loc_1800A51E2
0x1800a5221  xor     edx, edx
0x1800a5223  lea     ecx, [rdx+1]
0x1800a5226  call    PEAuthStoreParameter
0x1800a522b  mov     cs:g_PEAuthStateVariables, 0
0x1800a5235  jmp     short loc_1800A521D
0x1800a5237  lea     rax, [rbp+var_50]
0x1800a523b  mov     [rbp+var_38], rcx
0x1800a523f  mov     rcx, cs:g_PEAuthEtwHandle; RegHandle
0x1800a5246  lea     rdx, PEAUTH_BEGIN_COMPONENT_LOAD; EventDescriptor
0x1800a524d  mov     [rbp+var_48.Ptr], rax
0x1800a5251  mov     r9d, 2; UserDataCount
0x1800a5257  movzx   eax, word ptr [r14]
0x1800a525b  xor     r8d, r8d; ActivityId
0x1800a525e  mov     [rbp+var_30], eax
0x1800a5261  lea     rax, [rbp+var_48]
0x1800a5265  mov     [rsp+80h+UserData], rax; UserData
0x1800a526a  mov     qword ptr [rbp+var_48.Size], 4
0x1800a5272  mov     [rbp+var_2C], 0
0x1800a5279  call    cs:__imp_EtwWrite
0x1800a5280  nop     dword ptr [rax+rax+00h]
0x1800a5285  jmp     loc_1800A51A1
0x1800a528a  cmp     edi, 0C0000603h
0x1800a5290  jz      loc_1800A51C9
0x1800a5296  mov     eax, 0C0000428h
0x1800a529b  cmp     edi, eax
0x1800a529d  jz      loc_1800A51C9
0x1800a52a3  test    esi, esi
0x1800a52a5  jz      short loc_1800A52BF
0x1800a52a7  xor     edx, edx
0x1800a52a9  mov     ecx, ebx
0x1800a52ab  call    PEAuthStoreParameter
0x1800a52b0  mov     cs:g_PEAuthStateVariables, 0
0x1800a52ba  jmp     loc_1800A51C9
0x1800a52bf  mov     edi, eax
0x1800a52c1  jmp     loc_1800A51C9
0x1800a52c6  lea     rax, [rbp+var_4C]
0x1800a52ca  mov     [rbp+var_18], rcx
0x1800a52ce  mov     rcx, cs:g_PEAuthEtwHandle; RegHandle
0x1800a52d5  lea     rdx, PEAUTH_END_COMPONENT_LOAD; EventDescriptor
0x1800a52dc  mov     [rbp+var_28.Ptr], rax
0x1800a52e0  mov     r9d, 2; UserDataCount
0x1800a52e6  movzx   eax, word ptr [r14]
0x1800a52ea  xor     r8d, r8d; ActivityId
0x1800a52ed  mov     [rbp+var_10], eax
0x1800a52f0  lea     rax, [rbp+var_28]
0x1800a52f4  mov     [rsp+80h+UserData], rax; UserData
0x1800a52f9  mov     qword ptr [rbp+var_28.Size], 4
0x1800a5301  mov     [rbp+var_C], 0
0x1800a5308  call    cs:__imp_EtwWrite
0x1800a530f  nop     dword ptr [rax+rax+00h]
0x1800a5314  jmp     loc_1800A51E0
```
