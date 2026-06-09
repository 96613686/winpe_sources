# MetCreateSecurityDescriptor(_SECURITY_ATTRIBUTES *)

- ea: `0x140056cf8`
- end: `0x140056dc6`
- name: `?MetCreateSecurityDescriptor@@YAJPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `206`
- prototype: `__int64 __fastcall(struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140056a68`

## callees

- `0x140020420`
- `0x140056c70`
- `0x140056cf8`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140056d52`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140056d52`
- `KERNEL32!GetLastError` at `0x140056d98`
- `KERNEL32!GetLastError` at `0x140056d98`
- `OLEAUT32!__imp_SysFreeString` at `0x140056d7e`
- `OLEAUT32!__imp_SysFreeString` at `0x140056d7e`

## string_xrefs

- `0x140056d28`: `MetCreateSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall MetCreateSecurityDescriptor(struct _SECURITY_ATTRIBUTES *a1)
{
  int Sddl; // eax
  signed int v3; // ebx
  signed int LastError; // eax
  LPCWSTR StringSecurityDescriptor; // [rsp+48h] [rbp+10h] BYREF

  StringSecurityDescriptor = 0;
  Sddl = MetCreateSddl((unsigned __int16 **)&StringSecurityDescriptor);
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
        SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetCreateSecurityDescriptor", 521, v3);
        goto LABEL_7;
      }
    }
    a1->nLength = 24;
    a1->bInheritHandle = 0;
    goto LABEL_7;
  }
  SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "MetCreateSecurityDescriptor", 511, Sddl);
LABEL_7:
  if ( StringSecurityDescriptor )
    SysFreeString((BSTR)StringSecurityDescriptor);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140056cf8  mov     [rsp+arg_0], rbx
0x140056cfd  push    rdi
0x140056cfe  sub     rsp, 30h
0x140056d02  mov     rdi, rcx
0x140056d05  mov     [rsp+38h+StringSecurityDescriptor], 0
0x140056d0e  lea     rcx, [rsp+38h+StringSecurityDescriptor]; unsigned __int16 **
0x140056d13  call    ?MetCreateSddl@@YAJPEAPEAG@Z; MetCreateSddl(ushort * *)
0x140056d18  mov     ebx, eax
0x140056d1a  test    eax, eax
0x140056d1c  jns     short loc_140056D42
0x140056d1e  mov     [rsp+38h+var_18], eax
0x140056d22  mov     r9d, 1FFh
0x140056d28  lea     r8, aMetcreatesecur; "MetCreateSecurityDescriptor"
0x140056d2f  mov     ecx, 1; Level
0x140056d34  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x140056d3b  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140056d40  jmp     short loc_140056D71
0x140056d42  mov     rcx, [rsp+38h+StringSecurityDescriptor]; StringSecurityDescriptor
0x140056d47  lea     r8, [rdi+8]; SecurityDescriptor
0x140056d4b  xor     r9d, r9d; SecurityDescriptorSize
0x140056d4e  lea     edx, [r9+1]; StringSDRevision
0x140056d52  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140056d59  nop     dword ptr [rax+rax+00h]
0x140056d5e  test    eax, eax
0x140056d60  jz      short loc_140056D98
0x140056d62  xor     ebx, ebx
0x140056d64  mov     dword ptr [rdi], 18h
0x140056d6a  mov     dword ptr [rdi+10h], 0
0x140056d71  cmp     [rsp+38h+StringSecurityDescriptor], 0
0x140056d77  jz      short loc_140056D8A
0x140056d79  mov     rcx, [rsp+38h+StringSecurityDescriptor]; bstrString
0x140056d7e  call    cs:__imp_SysFreeString
0x140056d85  nop     dword ptr [rax+rax+00h]
0x140056d8a  mov     eax, ebx
0x140056d8c  mov     rbx, [rsp+38h+arg_0]
0x140056d91  add     rsp, 30h
0x140056d95  pop     rdi
0x140056d96  retn
0x140056d98  call    cs:__imp_GetLastError
0x140056d9f  nop     dword ptr [rax+rax+00h]
0x140056da4  mov     ebx, eax
0x140056da6  test    eax, eax
0x140056da8  jle     short loc_140056DB3
0x140056daa  movzx   ebx, ax
0x140056dad  or      ebx, 80070000h
0x140056db3  test    ebx, ebx
0x140056db5  jns     short loc_140056D64
0x140056db7  mov     [rsp+38h+var_18], ebx
0x140056dbb  mov     r9d, 209h
0x140056dc1  jmp     loc_140056D28
```
