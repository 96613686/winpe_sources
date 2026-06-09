# _CreateNamedSection

- ea: `0x1800637bc`
- end: `0x180063867`
- name: `_CreateNamedSection`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004bc34`

## callees

- `0x180018410`
- `0x180031b30`
- `0x1800637bc`
- `0x180063870`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063856`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063856`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180063807`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180063807`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063815`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180063815`

## pseudocode

```c
HANDLE __fastcall CreateNamedSection(__int64 a1, __int64 a2)
{
  HANDLE v2; // rbx
  struct _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+30h] [rbp-28h] BYREF

  v2 = 0;
  *(_QWORD *)&FileMappingAttributes.nLength = 24;
  *(_QWORD *)&FileMappingAttributes.bInheritHandle = 0;
  FileMappingAttributes.lpSecurityDescriptor = 0;
  if ( (int)CreateSharedHandleACL(a1, a2, &FileMappingAttributes.lpSecurityDescriptor) >= 0 )
  {
    v2 = CreateFileMappingW(
           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
           &FileMappingAttributes,
           4u,
           0,
           0x6Cu,
           L"Local\\windows_ie_global_counters");
    LocalFree(FileMappingAttributes.lpSecurityDescriptor);
    if ( v2 )
    {
      if ( ((unsigned __int8)IEConfiguration_GetBool(536870913) || !(unsigned __int8)IEConfiguration_GetBool(536870916))
        && (int)SetWindowsHandleAccess(v2, 0x2110Fu, 0xC0000002) < 0 )
      {
        CloseHandle(v2);
        return 0;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800637bc  mov     rax, rsp
0x1800637bf  push    rbx
0x1800637c0  sub     rsp, 50h
0x1800637c4  xor     ebx, ebx
0x1800637c6  mov     qword ptr [rax-28h], 18h
0x1800637ce  lea     r8, [rax-20h]
0x1800637d2  mov     [rax-18h], rbx
0x1800637d6  mov     [rax-20h], rbx
0x1800637da  call    _CreateSharedHandleACL
0x1800637df  test    eax, eax
0x1800637e1  js      short loc_18006385E
0x1800637e3  lea     rax, aLocalWindowsIe; "Local\\windows_ie_global_counters"
0x1800637ea  xor     r9d, r9d; dwMaximumSizeHigh
0x1800637ed  mov     [rsp+58h+lpName], rax; lpName
0x1800637f2  lea     r8d, [rbx+4]; flProtect
0x1800637f6  lea     rdx, [rsp+58h+FileMappingAttributes]; lpFileMappingAttributes
0x1800637fb  mov     [rsp+58h+dwMaximumSizeLow], 6Ch ; 'l'; dwMaximumSizeLow
0x180063803  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180063807  call    cs:__imp_CreateFileMappingW
0x18006380d  mov     rcx, [rsp+58h+FileMappingAttributes.lpSecurityDescriptor]; hMem
0x180063812  mov     rbx, rax
0x180063815  call    cs:__imp_LocalFree
0x18006381b  test    rbx, rbx
0x18006381e  jz      short loc_18006385E
0x180063820  mov     ecx, 20000001h
0x180063825  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18006382a  test    al, al
0x18006382c  jnz     short loc_18006383C
0x18006382e  mov     ecx, 20000004h
0x180063833  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180063838  test    al, al
0x18006383a  jnz     short loc_18006385E
0x18006383c  mov     edx, 2110Fh; unsigned int
0x180063841  mov     r8d, 0C0000002h; unsigned int
0x180063847  mov     rcx, rbx; void *
0x18006384a  call    ?SetWindowsHandleAccess@@YAJPEAXKK@Z; SetWindowsHandleAccess(void *,ulong,ulong)
0x18006384f  test    eax, eax
0x180063851  jns     short loc_18006385E
0x180063853  mov     rcx, rbx; hObject
0x180063856  call    cs:__imp_CloseHandle
0x18006385c  xor     ebx, ebx
0x18006385e  mov     rax, rbx
0x180063861  add     rsp, 50h
0x180063865  pop     rbx
0x180063866  retn
```
