# EdpAadReauthToast::GetToastTitle(ushort * *)

- ea: `0x18000a800`
- end: `0x18000a885`
- name: `?GetToastTitle@EdpAadReauthToast@@UEAAJPEAPEAG@Z`
- size: `133`
- prototype: `__int64 __fastcall(EdpAadReauthToast *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800056c4`
- `0x18000a800`
- `0x18000a91c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a866`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a866`

## string_xrefs

- `0x18000a848`: `ds\security\efs\edptask\toast\edptoast.cpp`

## pseudocode

```c
__int64 __fastcall EdpAadReauthToast::GetToastTitle(EdpAadReauthToast *this, unsigned __int16 **a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  LPVOID pv[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  memset(pv, 0, 24);
  v3 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
         pv,
         &_ImageBase,
         203);
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
      (void *)0x248,
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
0x18000a800  mov     rax, rsp
0x18000a803  mov     [rax+8], rbx
0x18000a807  push    rdi
0x18000a808  sub     rsp, 40h
0x18000a80c  mov     rdi, rdx
0x18000a80f  mov     qword ptr [rax-28h], 0
0x18000a817  lea     rdx, __ImageBase
0x18000a81e  mov     qword ptr [rax-20h], 0
0x18000a826  mov     r8d, 0CBh
0x18000a82c  mov     qword ptr [rax-18h], 0
0x18000a834  lea     rcx, [rax-28h]
0x18000a838  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@I@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint)
0x18000a83d  mov     ebx, eax
0x18000a83f  test    eax, eax
0x18000a841  jns     short loc_18000A870
0x18000a843  mov     rcx, [rsp+48h]; this
0x18000a848  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x18000a84f  mov     r9d, eax; char *
0x18000a852  mov     edx, 248h; void *
0x18000a857  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a85c  mov     rcx, [rsp+48h+pv]; pv
0x18000a861  test    rcx, rcx
0x18000a864  jz      short loc_18000A86C
0x18000a866  call    cs:__imp_CoTaskMemFree
0x18000a86c  mov     eax, ebx
0x18000a86e  jmp     short loc_18000A87A
0x18000a870  mov     rax, [rsp+48h+pv]
0x18000a875  mov     [rdi], rax
0x18000a878  xor     eax, eax
0x18000a87a  mov     rbx, [rsp+48h+arg_0]
0x18000a87f  add     rsp, 40h
0x18000a883  pop     rdi
0x18000a884  retn
```
