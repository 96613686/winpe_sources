# EdpMissingCredsToast::GetToastTagString(ushort * *)

- ea: `0x18000a530`
- end: `0x18000a5ac`
- name: `?GetToastTagString@EdpMissingCredsToast@@UEAAJPEAPEAG@Z`
- size: `124`
- prototype: `__int64 __fastcall(EdpMissingCredsToast *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800056c4`
- `0x180008278`
- `0x18000a530`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a58d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a58d`

## string_xrefs

- `0x18000a571`: `ds\security\efs\edptask\toast\edptoast.cpp`

## pseudocode

```c
__int64 __fastcall EdpMissingCredsToast::GetToastTagString(EdpMissingCredsToast *this, unsigned __int16 **a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  LPVOID pv[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  pv[0] = 0;
  pv[1] = (LPVOID)-1LL;
  pv[2] = (LPVOID)-1LL;
  v3 = CoAllocString(L"WIPToastMissingCredsTag", (unsigned __int16 **)pv);
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
      (void *)0x3C7,
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
0x18000a530  mov     r11, rsp
0x18000a533  mov     [r11+8], rbx
0x18000a537  push    rdi
0x18000a538  sub     rsp, 40h
0x18000a53c  mov     rdi, rdx
0x18000a53f  mov     qword ptr [r11-28h], 0
0x18000a547  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a54b  mov     [r11-20h], rax
0x18000a54f  mov     [r11-18h], rax
0x18000a553  lea     rdx, [r11-28h]; unsigned __int16 **
0x18000a557  lea     rcx, aWiptoastmissin; "WIPToastMissingCredsTag"
0x18000a55e  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x18000a563  mov     ebx, eax
0x18000a565  test    eax, eax
0x18000a567  jns     short loc_18000A597
0x18000a569  mov     rcx, [rsp+48h]; this
0x18000a56e  mov     r9d, eax; char *
0x18000a571  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x18000a578  mov     edx, 3C7h; void *
0x18000a57d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a582  nop
0x18000a583  mov     rcx, [rsp+48h+pv]; pv
0x18000a588  test    rcx, rcx
0x18000a58b  jz      short loc_18000A593
0x18000a58d  call    cs:__imp_CoTaskMemFree
0x18000a593  mov     eax, ebx
0x18000a595  jmp     short loc_18000A5A1
0x18000a597  mov     rax, [rsp+48h+pv]
0x18000a59c  mov     [rdi], rax
0x18000a59f  xor     eax, eax
0x18000a5a1  mov     rbx, [rsp+48h+arg_0]
0x18000a5a6  add     rsp, 40h
0x18000a5aa  pop     rdi
0x18000a5ab  retn
```
