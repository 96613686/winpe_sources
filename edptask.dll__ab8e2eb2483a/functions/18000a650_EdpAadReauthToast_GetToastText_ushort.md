# EdpAadReauthToast::GetToastText(ushort * *)

- ea: `0x18000a650`
- end: `0x18000a6d5`
- name: `?GetToastText@EdpAadReauthToast@@UEAAJPEAPEAG@Z`
- size: `133`
- prototype: `__int64 __fastcall(EdpAadReauthToast *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800056c4`
- `0x18000a650`
- `0x18000a91c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a6b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a6b6`

## string_xrefs

- `0x18000a698`: `ds\security\efs\edptask\toast\edptoast.cpp`

## pseudocode

```c
__int64 __fastcall EdpAadReauthToast::GetToastText(EdpAadReauthToast *this, unsigned __int16 **a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  LPVOID pv[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  memset(pv, 0, 24);
  v3 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
         pv,
         &_ImageBase,
         204);
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
      (void *)0x262,
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
0x18000a650  mov     rax, rsp
0x18000a653  mov     [rax+8], rbx
0x18000a657  push    rdi
0x18000a658  sub     rsp, 40h
0x18000a65c  mov     rdi, rdx
0x18000a65f  mov     qword ptr [rax-28h], 0
0x18000a667  lea     rdx, __ImageBase
0x18000a66e  mov     qword ptr [rax-20h], 0
0x18000a676  mov     r8d, 0CCh
0x18000a67c  mov     qword ptr [rax-18h], 0
0x18000a684  lea     rcx, [rax-28h]
0x18000a688  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@I@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint)
0x18000a68d  mov     ebx, eax
0x18000a68f  test    eax, eax
0x18000a691  jns     short loc_18000A6C0
0x18000a693  mov     rcx, [rsp+48h]; this
0x18000a698  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x18000a69f  mov     r9d, eax; char *
0x18000a6a2  mov     edx, 262h; void *
0x18000a6a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a6ac  mov     rcx, [rsp+48h+pv]; pv
0x18000a6b1  test    rcx, rcx
0x18000a6b4  jz      short loc_18000A6BC
0x18000a6b6  call    cs:__imp_CoTaskMemFree
0x18000a6bc  mov     eax, ebx
0x18000a6be  jmp     short loc_18000A6CA
0x18000a6c0  mov     rax, [rsp+48h+pv]
0x18000a6c5  mov     [rdi], rax
0x18000a6c8  xor     eax, eax
0x18000a6ca  mov     rbx, [rsp+48h+arg_0]
0x18000a6cf  add     rsp, 40h
0x18000a6d3  pop     rdi
0x18000a6d4  retn
```
