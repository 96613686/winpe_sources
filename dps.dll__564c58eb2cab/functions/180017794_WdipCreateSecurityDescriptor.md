# WdipCreateSecurityDescriptor

- ea: `0x180017794`
- end: `0x18001780f`
- name: `WdipCreateSecurityDescriptor`
- size: `123`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010374`

## callees

- `0x180009090`
- `0x180017794`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800177c7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800177b9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800177b9`

## string_xrefs

- `0x1800177f5`: `clientcore\base\diagnosis\pdi\wdi\framework\common\utils.cpp`
- `0x1800177ee`: `WdipCreateSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall WdipCreateSecurityDescriptor(__int64 a1, __int64 a2)
{
  signed int Args; // ebx
  signed int LastError; // eax

  *(_DWORD *)a2 = 24;
  *(_DWORD *)(a2 + 16) = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;GR;;;WD)", 1u, (PSECURITY_DESCRIPTOR *)(a2 + 8), 0) )
  {
    return 0;
  }
  else
  {
    LastError = GetLastError();
    Args = LastError;
    if ( LastError > 0 )
      Args = (unsigned __int16)LastError | 0x80070000;
    if ( Args < 0 )
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\utils.cpp",
        (int)L"WdipCreateSecurityDescriptor",
        332,
        (int)L"Error = %d",
        Args);
  }
  return (unsigned int)Args;
}

```

## disassembly

```asm
0x180017794  push    rbx
0x180017796  sub     rsp, 30h
0x18001779a  xor     r9d, r9d; SecurityDescriptorSize
0x18001779d  mov     dword ptr [rdx], 18h
0x1800177a3  mov     dword ptr [rdx+10h], 0
0x1800177aa  lea     r8, [rdx+8]; SecurityDescriptor
0x1800177ae  lea     rcx, StringSecurityDescriptor; "D:(A;;GR;;;WD)"
0x1800177b5  lea     edx, [r9+1]; StringSDRevision
0x1800177b9  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800177bf  test    eax, eax
0x1800177c1  jz      short loc_1800177C7
0x1800177c3  xor     ebx, ebx
0x1800177c5  jmp     short loc_180017807
0x1800177c7  call    cs:__imp_GetLastError
0x1800177cd  mov     ebx, eax
0x1800177cf  test    eax, eax
0x1800177d1  jle     short loc_1800177DC
0x1800177d3  movzx   ebx, ax
0x1800177d6  or      ebx, 80070000h
0x1800177dc  test    ebx, ebx
0x1800177de  jns     short loc_180017807
0x1800177e0  movzx   ecx, bx
0x1800177e3  lea     r9, aErrorD; "Error = %d"
0x1800177ea  mov     dword ptr [rsp+38h+Args], ecx; Args
0x1800177ee  lea     rdx, aWdipcreatesecu; "WdipCreateSecurityDescriptor"
0x1800177f5  lea     rcx, aClientcoreBase_0; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800177fc  mov     r8d, 14Ch; int
0x180017802  call    WdipTraceError
0x180017807  mov     eax, ebx
0x180017809  add     rsp, 30h
0x18001780d  pop     rbx
0x18001780e  retn
```
