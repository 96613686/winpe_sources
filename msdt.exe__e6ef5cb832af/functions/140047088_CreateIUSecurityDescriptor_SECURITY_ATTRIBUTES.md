# CreateIUSecurityDescriptor(_SECURITY_ATTRIBUTES *)

- ea: `0x140047088`
- end: `0x14004716e`
- name: `?CreateIUSecurityDescriptor@@YAJPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `230`
- prototype: `__int64 __fastcall(struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400472d0`

## callees

- `0x140020420`
- `0x140047088`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400470ea`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400470ea`
- `KERNEL32!GetLastError` at `0x14004712b`
- `KERNEL32!GetLastError` at `0x14004712b`
- `OLEAUT32!__imp_SysAllocString` at `0x1400470a1`
- `OLEAUT32!__imp_SysAllocString` at `0x1400470a1`
- `OLEAUT32!__imp_SysFreeString` at `0x14004710c`
- `OLEAUT32!__imp_SysFreeString` at `0x14004710c`

## string_xrefs

- `0x1400470ba`: `CreateIUSecurityDescriptor`
- `0x140047154`: `CreateIUSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall CreateIUSecurityDescriptor(struct _SECURITY_ATTRIBUTES *a1)
{
  const WCHAR *v2; // rax
  OLECHAR *v3; // rsi
  unsigned int v4; // ebx
  signed int LastError; // eax

  v2 = SysAllocString(L"D:(A;OICI;GA;;;IU)");
  v3 = (OLECHAR *)v2;
  if ( v2 )
  {
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v2, 1u, &a1->lpSecurityDescriptor, 0) )
    {
      v4 = 0;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( (v4 & 0x80000000) != 0 )
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateIUSecurityDescriptor", 334, v4);
        goto LABEL_6;
      }
    }
    a1->nLength = 24;
    a1->bInheritHandle = 0;
LABEL_6:
    SysFreeString(v3);
    return v4;
  }
  v4 = -2147024882;
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CreateIUSecurityDescriptor", 324, -2147024882);
  return v4;
}

```

## disassembly

```asm
0x140047088  mov     [rsp+arg_0], rbx
0x14004708d  mov     [rsp+arg_8], rsi
0x140047092  push    rdi
0x140047093  sub     rsp, 30h
0x140047097  mov     rdi, rcx
0x14004709a  lea     rcx, aDAOiciGaIu; "D:(A;OICI;GA;;;IU)"
0x1400470a1  call    cs:__imp_SysAllocString
0x1400470a8  nop     dword ptr [rax+rax+00h]
0x1400470ad  mov     rsi, rax
0x1400470b0  test    rax, rax
0x1400470b3  jnz     short loc_1400470DC
0x1400470b5  mov     ebx, 8007000Eh
0x1400470ba  lea     r8, aCreateiusecuri; "CreateIUSecurityDescriptor"
0x1400470c1  mov     r9d, 144h
0x1400470c7  mov     [rsp+38h+var_18], ebx
0x1400470cb  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400470d2  lea     ecx, [rax+1]; Level
0x1400470d5  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400470da  jmp     short loc_140047118
0x1400470dc  xor     r9d, r9d; SecurityDescriptorSize
0x1400470df  lea     r8, [rdi+8]; SecurityDescriptor
0x1400470e3  mov     rcx, rsi; StringSecurityDescriptor
0x1400470e6  lea     edx, [r9+1]; StringSDRevision
0x1400470ea  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1400470f1  nop     dword ptr [rax+rax+00h]
0x1400470f6  test    eax, eax
0x1400470f8  jz      short loc_14004712B
0x1400470fa  xor     ebx, ebx
0x1400470fc  mov     dword ptr [rdi], 18h
0x140047102  mov     dword ptr [rdi+10h], 0
0x140047109  mov     rcx, rsi; bstrString
0x14004710c  call    cs:__imp_SysFreeString
0x140047113  nop     dword ptr [rax+rax+00h]
0x140047118  mov     rsi, [rsp+38h+arg_8]
0x14004711d  mov     eax, ebx
0x14004711f  mov     rbx, [rsp+38h+arg_0]
0x140047124  add     rsp, 30h
0x140047128  pop     rdi
0x140047129  retn
0x14004712b  call    cs:__imp_GetLastError
0x140047132  nop     dword ptr [rax+rax+00h]
0x140047137  mov     ebx, eax
0x140047139  test    eax, eax
0x14004713b  jle     short loc_140047146
0x14004713d  movzx   ebx, ax
0x140047140  or      ebx, 80070000h
0x140047146  test    ebx, ebx
0x140047148  jns     short loc_1400470FC
0x14004714a  mov     r9d, 14Eh
0x140047150  mov     [rsp+38h+var_18], ebx
0x140047154  lea     r8, aCreateiusecuri; "CreateIUSecurityDescriptor"
0x14004715b  mov     ecx, 1; Level
0x140047160  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140047167  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14004716c  jmp     short loc_140047109
```
