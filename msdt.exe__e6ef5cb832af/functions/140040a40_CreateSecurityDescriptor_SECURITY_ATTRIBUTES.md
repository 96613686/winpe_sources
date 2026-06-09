# CreateSecurityDescriptor(_SECURITY_ATTRIBUTES *)

- ea: `0x140040a40`
- end: `0x140040b0e`
- name: `?CreateSecurityDescriptor@@YAJPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `206`
- prototype: `__int64 __fastcall(struct _SECURITY_ATTRIBUTES *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400407b0`
- `0x140040b14`
- `0x140042bf8`

## callees

- `0x140020420`
- `0x1400409b8`
- `0x140040a40`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140040a9a`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140040a9a`
- `KERNEL32!GetLastError` at `0x140040ae0`
- `KERNEL32!GetLastError` at `0x140040ae0`
- `OLEAUT32!__imp_SysFreeString` at `0x140040ac6`
- `OLEAUT32!__imp_SysFreeString` at `0x140040ac6`

## string_xrefs

- `0x140040a70`: `CreateSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall CreateSecurityDescriptor(struct _SECURITY_ATTRIBUTES *a1)
{
  int Sddl; // eax
  signed int v3; // ebx
  signed int LastError; // eax
  LPCWSTR StringSecurityDescriptor; // [rsp+48h] [rbp+10h] BYREF

  StringSecurityDescriptor = 0;
  Sddl = CreateSddl((unsigned __int16 **)&StringSecurityDescriptor);
  v3 = Sddl;
  if ( Sddl >= 0 )
  {
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
           StringSecurityDescriptor,
           1u,
           &a1->lpSecurityDescriptor,
           0) )
    {
      v3 = 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( v3 < 0 )
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateSecurityDescriptor", 927, v3);
        goto LABEL_7;
      }
    }
    a1->nLength = 24;
    a1->bInheritHandle = 0;
    goto LABEL_7;
  }
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateSecurityDescriptor", 917, Sddl);
LABEL_7:
  if ( StringSecurityDescriptor )
    SysFreeString((BSTR)StringSecurityDescriptor);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140040a40  mov     [rsp+arg_0], rbx
0x140040a45  push    rdi
0x140040a46  sub     rsp, 30h
0x140040a4a  mov     rdi, rcx
0x140040a4d  mov     [rsp+38h+StringSecurityDescriptor], 0
0x140040a56  lea     rcx, [rsp+38h+StringSecurityDescriptor]; unsigned __int16 **
0x140040a5b  call    ?CreateSddl@@YAJPEAPEAG@Z; CreateSddl(ushort * *)
0x140040a60  mov     ebx, eax
0x140040a62  test    eax, eax
0x140040a64  jns     short loc_140040A8A
0x140040a66  mov     [rsp+38h+var_18], eax
0x140040a6a  mov     r9d, 395h
0x140040a70  lea     r8, aCreatesecurity; "CreateSecurityDescriptor"
0x140040a77  mov     ecx, 1; Level
0x140040a7c  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140040a83  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140040a88  jmp     short loc_140040AB9
0x140040a8a  mov     rcx, [rsp+38h+StringSecurityDescriptor]; StringSecurityDescriptor
0x140040a8f  lea     r8, [rdi+8]; SecurityDescriptor
0x140040a93  xor     r9d, r9d; SecurityDescriptorSize
0x140040a96  lea     edx, [r9+1]; StringSDRevision
0x140040a9a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140040aa1  nop     dword ptr [rax+rax+00h]
0x140040aa6  test    eax, eax
0x140040aa8  jz      short loc_140040AE0
0x140040aaa  xor     ebx, ebx
0x140040aac  mov     dword ptr [rdi], 18h
0x140040ab2  mov     dword ptr [rdi+10h], 0
0x140040ab9  cmp     [rsp+38h+StringSecurityDescriptor], 0
0x140040abf  jz      short loc_140040AD2
0x140040ac1  mov     rcx, [rsp+38h+StringSecurityDescriptor]; bstrString
0x140040ac6  call    cs:__imp_SysFreeString
0x140040acd  nop     dword ptr [rax+rax+00h]
0x140040ad2  mov     eax, ebx
0x140040ad4  mov     rbx, [rsp+38h+arg_0]
0x140040ad9  add     rsp, 30h
0x140040add  pop     rdi
0x140040ade  retn
0x140040ae0  call    cs:__imp_GetLastError
0x140040ae7  nop     dword ptr [rax+rax+00h]
0x140040aec  mov     ebx, eax
0x140040aee  test    eax, eax
0x140040af0  jle     short loc_140040AFB
0x140040af2  movzx   ebx, ax
0x140040af5  or      ebx, 80070000h
0x140040afb  test    ebx, ebx
0x140040afd  jns     short loc_140040AAC
0x140040aff  mov     [rsp+38h+var_18], ebx
0x140040b03  mov     r9d, 39Fh
0x140040b09  jmp     loc_140040A70
```
