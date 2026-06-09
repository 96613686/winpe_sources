# EdpAadReauthToast::GetToastIdString(ushort * *)

- ea: `0x18000a2f0`
- end: `0x18000a36c`
- name: `?GetToastIdString@EdpAadReauthToast@@UEAAJPEAPEAG@Z`
- size: `124`
- prototype: `__int64 __fastcall(EdpAadReauthToast *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800056c4`
- `0x180008278`
- `0x18000a2f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a34d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a34d`

## string_xrefs

- `0x18000a331`: `ds\security\efs\edptask\toast\edptoast.cpp`

## pseudocode

```c
__int64 __fastcall EdpAadReauthToast::GetToastIdString(EdpAadReauthToast *this, unsigned __int16 **a2)
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
      (void *)0x2AB,
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
0x18000a2f0  mov     r11, rsp
0x18000a2f3  mov     [r11+8], rbx
0x18000a2f7  push    rdi
0x18000a2f8  sub     rsp, 40h
0x18000a2fc  mov     rdi, rdx
0x18000a2ff  mov     qword ptr [r11-28h], 0
0x18000a307  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a30b  mov     [r11-20h], rax
0x18000a30f  mov     [r11-18h], rax
0x18000a313  lea     rdx, [r11-28h]; unsigned __int16 **
0x18000a317  lea     rcx, aWindowsSystemt_0; "Windows.SystemToast.EnterpriseDataProte"...
0x18000a31e  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x18000a323  mov     ebx, eax
0x18000a325  test    eax, eax
0x18000a327  jns     short loc_18000A357
0x18000a329  mov     rcx, [rsp+48h]; this
0x18000a32e  mov     r9d, eax; char *
0x18000a331  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x18000a338  mov     edx, 2ABh; void *
0x18000a33d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a342  nop
0x18000a343  mov     rcx, [rsp+48h+pv]; pv
0x18000a348  test    rcx, rcx
0x18000a34b  jz      short loc_18000A353
0x18000a34d  call    cs:__imp_CoTaskMemFree
0x18000a353  mov     eax, ebx
0x18000a355  jmp     short loc_18000A361
0x18000a357  mov     rax, [rsp+48h+pv]
0x18000a35c  mov     [rdi], rax
0x18000a35f  xor     eax, eax
0x18000a361  mov     rbx, [rsp+48h+arg_0]
0x18000a366  add     rsp, 40h
0x18000a36a  pop     rdi
0x18000a36b  retn
```
