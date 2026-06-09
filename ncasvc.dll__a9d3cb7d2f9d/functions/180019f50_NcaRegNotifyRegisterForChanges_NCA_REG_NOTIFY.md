# NcaRegNotifyRegisterForChanges(NCA_REG_NOTIFY_ *)

- ea: `0x180019f50`
- end: `0x18001a006`
- name: `?NcaRegNotifyRegisterForChanges@@YAJPEAUNCA_REG_NOTIFY_@@@Z`
- size: `182`
- prototype: `__int64 __fastcall(struct NCA_REG_NOTIFY_ *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001a5c0`

## callees

- `0x1800033bc`
- `0x1800037b0`
- `0x1800199b4`
- `0x180019f50`
- `0x18001a00c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180019fa6`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180019fa6`

## string_xrefs

- `0x180019fd9`: `NcaRegNotifyCreateKey`

## pseudocode

```c
__int64 __fastcall NcaRegNotifyRegisterForChanges(struct NCA_REG_NOTIFY_ *a1)
{
  HKEY *v2; // rsi
  const WCHAR *v3; // rdx
  HKEY v4; // rcx
  int Key; // eax
  unsigned int v6; // ebx
  unsigned int v7; // eax

  v2 = (HKEY *)((char *)a1 + 48);
  do
  {
    NcaRegCloseKey(*v2);
    v3 = (const WCHAR *)*((_QWORD *)a1 + 1);
    v4 = *(HKEY *)a1;
    *v2 = 0;
    Key = NcaRegCreateKey(v4, v3, 0x10u);
    v6 = Key;
    if ( Key < 0 )
    {
      NcaReportReturnError("NcaRegNotifyCreateKey", (unsigned int)Key);
      NcaReportReturnError("NcaRegNotifyRegisterForChanges", v6);
      return v6;
    }
    v7 = RegNotifyChangeKeyValue(*v2, *((_DWORD *)a1 + 4), *((_DWORD *)a1 + 5), *((HANDLE *)a1 + 7), 1);
  }
  while ( v7 == 1018 );
  if ( v7 )
    return (unsigned int)NcaReportErrorAsWinError("NcaRegNotifyRegisterForChanges", "RegNotifyChangeKeyValue", v7);
  return v6;
}

```

## disassembly

```asm
0x180019f50  mov     [rsp+arg_0], rbx
0x180019f55  mov     [rsp+arg_8], rsi
0x180019f5a  push    rdi
0x180019f5b  sub     rsp, 30h
0x180019f5f  mov     rdi, rcx
0x180019f62  lea     rsi, [rcx+30h]
0x180019f66  mov     rcx, [rsi]
0x180019f69  call    NcaRegCloseKey
0x180019f6e  mov     rdx, [rdi+8]; lpSubKey
0x180019f72  mov     r9, rsi
0x180019f75  mov     rcx, [rdi]; hKey
0x180019f78  mov     r8d, 10h; samDesired
0x180019f7e  mov     qword ptr [rsi], 0
0x180019f85  call    NcaRegCreateKey
0x180019f8a  mov     ebx, eax
0x180019f8c  test    eax, eax
0x180019f8e  js      short loc_180019FD7
0x180019f90  mov     r9, [rdi+38h]; hEvent
0x180019f94  mov     r8d, [rdi+14h]; dwNotifyFilter
0x180019f98  mov     edx, [rdi+10h]; bWatchSubtree
0x180019f9b  mov     rcx, [rsi]; hKey
0x180019f9e  mov     [rsp+38h+fAsynchronous], 1; fAsynchronous
0x180019fa6  call    cs:__imp_RegNotifyChangeKeyValue
0x180019fad  nop     dword ptr [rax+rax+00h]
0x180019fb2  cmp     eax, 3FAh
0x180019fb7  jz      short loc_180019F66
0x180019fb9  test    eax, eax
0x180019fbb  jz      short loc_180019FF3
0x180019fbd  mov     r8d, eax
0x180019fc0  lea     rdx, aRegnotifychang; "RegNotifyChangeKeyValue"
0x180019fc7  lea     rcx, aNcaregnotifyre; "NcaRegNotifyRegisterForChanges"
0x180019fce  call    NcaReportErrorAsWinError
0x180019fd3  mov     ebx, eax
0x180019fd5  jmp     short loc_180019FF3
0x180019fd7  mov     edx, ebx
0x180019fd9  lea     rcx, aNcaregnotifycr_0; "NcaRegNotifyCreateKey"
0x180019fe0  call    NcaReportReturnError
0x180019fe5  mov     edx, ebx
0x180019fe7  lea     rcx, aNcaregnotifyre; "NcaRegNotifyRegisterForChanges"
0x180019fee  call    NcaReportReturnError
0x180019ff3  mov     rsi, [rsp+38h+arg_8]
0x180019ff8  mov     eax, ebx
0x180019ffa  mov     rbx, [rsp+38h+arg_0]
0x180019fff  add     rsp, 30h
0x18001a003  pop     rdi
0x18001a004  retn
```
