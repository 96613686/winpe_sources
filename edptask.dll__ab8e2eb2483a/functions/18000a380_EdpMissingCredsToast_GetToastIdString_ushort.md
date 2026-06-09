# EdpMissingCredsToast::GetToastIdString(ushort * *)

- ea: `0x18000a380`
- end: `0x18000a3fc`
- name: `?GetToastIdString@EdpMissingCredsToast@@UEAAJPEAPEAG@Z`
- size: `124`
- prototype: `__int64 __fastcall(EdpMissingCredsToast *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800056c4`
- `0x180008278`
- `0x18000a380`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a3dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a3dd`

## string_xrefs

- `0x18000a3c1`: `ds\security\efs\edptask\toast\edptoast.cpp`

## pseudocode

```c
__int64 __fastcall EdpMissingCredsToast::GetToastIdString(EdpMissingCredsToast *this, unsigned __int16 **a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  LPVOID pv[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  pv[0] = 0;
  pv[1] = (LPVOID)-1LL;
  pv[2] = (LPVOID)-1LL;
  v3 = CoAllocString(L"Windows.SystemToast.EnterpriseDataProtection", (unsigned __int16 **)pv);
  v4 = v3;
  if ( v3 >= 0 )
  {
    *a2 = (unsigned __int16 *)pv[0];
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x393,
      (unsigned int)"ds\\security\\efs\\edptask\\toast\\edptoast.cpp",
      (const char *)(unsigned int)v3,
      (int)pv[0]);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    return v4;
  }
}

```

## disassembly

```asm
0x18000a380  mov     r11, rsp
0x18000a383  mov     [r11+8], rbx
0x18000a387  push    rdi
0x18000a388  sub     rsp, 40h
0x18000a38c  mov     rdi, rdx
0x18000a38f  mov     qword ptr [r11-28h], 0
0x18000a397  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a39b  mov     [r11-20h], rax
0x18000a39f  mov     [r11-18h], rax
0x18000a3a3  lea     rdx, [r11-28h]; unsigned __int16 **
0x18000a3a7  lea     rcx, aWindowsSystemt_0; "Windows.SystemToast.EnterpriseDataProte"...
0x18000a3ae  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x18000a3b3  mov     ebx, eax
0x18000a3b5  test    eax, eax
0x18000a3b7  jns     short loc_18000A3E7
0x18000a3b9  mov     rcx, [rsp+48h]; this
0x18000a3be  mov     r9d, eax; char *
0x18000a3c1  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x18000a3c8  mov     edx, 393h; void *
0x18000a3cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a3d2  nop
0x18000a3d3  mov     rcx, [rsp+48h+pv]; pv
0x18000a3d8  test    rcx, rcx
0x18000a3db  jz      short loc_18000A3E3
0x18000a3dd  call    cs:__imp_CoTaskMemFree
0x18000a3e3  mov     eax, ebx
0x18000a3e5  jmp     short loc_18000A3F1
0x18000a3e7  mov     rax, [rsp+48h+pv]
0x18000a3ec  mov     [rdi], rax
0x18000a3ef  xor     eax, eax
0x18000a3f1  mov     rbx, [rsp+48h+arg_0]
0x18000a3f6  add     rsp, 40h
0x18000a3fa  pop     rdi
0x18000a3fb  retn
```
