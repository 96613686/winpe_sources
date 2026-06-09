# AslRegistryGetKey

- ea: `0x140acb824`
- end: `0x140acb944`
- name: `AslRegistryGetKey`
- size: `288`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140821e50`
- `0x1408221bc`
- `0x140822734`
- `0x140822828`
- `0x140829be4`
- `0x140acb734`

## callees

- `0x1406dd620`
- `0x140827e40`
- `0x1408c14bc`
- `0x1408c2f88`
- `0x140acb824`
- `0x140acb94c`

## string_xrefs

- `0x140acb8c1`: `AslRegistryBuildMachinePath failed %x for %ws`
- `0x140acb8d3`: `AslRegistryGetKey`
- `0x140acb935`: `NtOpenKey failed %x for %ws`
- `0x140acb91f`: `AslRegistryBuildUserPath failed %x for %ws`

## pseudocode

```c
__int64 __fastcall AslRegistryGetKey(HANDLE *a1, const WCHAR *a2, ACCESS_MASK a3, int a4)
{
  int v6; // ebx
  NTSTATUS v7; // eax
  __int64 v8; // rcx
  const char *v9; // r9
  int v10; // r8d
  UNICODE_STRING Destination; // [rsp+30h] [rbp-40h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  HANDLE KeyHandle; // [rsp+90h] [rbp+20h] BYREF

  *a1 = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  Destination = 0;
  if ( a4 )
  {
    v6 = AslRegistryBuildMachinePath(&Destination, a2);
    if ( v6 >= 0 )
      goto LABEL_3;
    v9 = "AslRegistryBuildMachinePath failed %x for %ws";
    v10 = 1718;
LABEL_6:
    AslLogCallPrintf(1, (unsigned int)"AslRegistryGetKey", v10, (_DWORD)v9);
    goto LABEL_7;
  }
  v6 = AslRegistryBuildUserPath(&Destination, a2);
  if ( v6 < 0 )
  {
    v9 = "AslRegistryBuildUserPath failed %x for %ws";
    v10 = 1725;
    goto LABEL_6;
  }
LABEL_3:
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &Destination;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = ZwOpenKey(&KeyHandle, a3, &ObjectAttributes);
  v6 = v7;
  if ( v7 >= 0 )
  {
    v6 = 0;
    *a1 = KeyHandle;
    KeyHandle = 0;
    goto LABEL_7;
  }
  if ( v7 != -1073741772 )
  {
    v9 = "NtOpenKey failed %x for %ws";
    v10 = 1761;
    goto LABEL_6;
  }
LABEL_7:
  if ( Destination.Buffer )
    AslFree(v8, Destination.Buffer);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140acb824  mov     [rsp-18h+arg_8], rbx
0x140acb829  mov     [rsp-18h+arg_10], rsi
0x140acb82e  push    rbp
0x140acb82f  push    rdi
0x140acb830  push    r14
0x140acb832  mov     rbp, rsp
0x140acb835  sub     rsp, 70h
0x140acb839  xorps   xmm0, xmm0
0x140acb83c  xor     eax, eax
0x140acb83e  mov     [rcx], rax
0x140acb841  mov     rsi, rcx
0x140acb844  mov     [rbp+KeyHandle], rax
0x140acb848  lea     rcx, [rbp+Destination]; Destination
0x140acb84c  mov     r14d, r8d
0x140acb84f  mov     rdi, rdx
0x140acb852  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140acb856  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140acb85a  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140acb85e  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x140acb862  test    r9d, r9d
0x140acb865  jz      loc_140ACB910
0x140acb86b  call    AslRegistryBuildMachinePath
0x140acb870  mov     ebx, eax
0x140acb872  test    eax, eax
0x140acb874  js      short loc_140ACB8C1
0x140acb876  lea     rax, [rbp+Destination]
0x140acb87a  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140acb881  xorps   xmm0, xmm0
0x140acb884  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140acb888  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140acb88c  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140acb894  mov     edx, r14d; DesiredAccess
0x140acb897  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140acb89e  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140acb8a2  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140acb8a7  call    ZwOpenKey
0x140acb8ac  mov     ebx, eax
0x140acb8ae  test    eax, eax
0x140acb8b0  js      short loc_140ACB92E
0x140acb8b2  mov     rax, [rbp+KeyHandle]
0x140acb8b6  xor     ebx, ebx
0x140acb8b8  mov     [rsi], rax
0x140acb8bb  mov     [rbp+KeyHandle], rbx
0x140acb8bf  jmp     short loc_140ACB8E8
0x140acb8c1  lea     r9, aAslregistrybui; "AslRegistryBuildMachinePath failed %x f"...
0x140acb8c8  mov     r8d, 6B6h
0x140acb8ce  mov     [rsp+70h+var_48], rdi
0x140acb8d3  lea     rdx, aAslregistryget_0; "AslRegistryGetKey"
0x140acb8da  mov     ecx, 1
0x140acb8df  mov     [rsp+70h+var_50], eax
0x140acb8e3  call    AslLogCallPrintf
0x140acb8e8  mov     rdx, [rbp+Destination.Buffer]
0x140acb8ec  test    rdx, rdx
0x140acb8ef  jnz     short loc_140ACB909
0x140acb8f1  lea     r11, [rsp+70h+var_s0]
0x140acb8f6  mov     eax, ebx
0x140acb8f8  mov     rbx, [r11+28h]
0x140acb8fc  mov     rsi, [r11+30h]
0x140acb900  mov     rsp, r11
0x140acb903  pop     r14
0x140acb905  pop     rdi
0x140acb906  pop     rbp
0x140acb907  retn
0x140acb909  call    AslFree
0x140acb90e  jmp     short loc_140ACB8F1
0x140acb910  call    AslRegistryBuildUserPath
0x140acb915  mov     ebx, eax
0x140acb917  test    eax, eax
0x140acb919  jns     loc_140ACB876
0x140acb91f  lea     r9, aAslregistrybui_2; "AslRegistryBuildUserPath failed %x for "...
0x140acb926  mov     r8d, 6BDh
0x140acb92c  jmp     short loc_140ACB8CE
0x140acb92e  cmp     eax, 0C0000034h
0x140acb933  jz      short loc_140ACB8E8
0x140acb935  lea     r9, aNtopenkeyFaile; "NtOpenKey failed %x for %ws"
0x140acb93c  mov     r8d, 6E1h
0x140acb942  jmp     short loc_140ACB8CE
```
