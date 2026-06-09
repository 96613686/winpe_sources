# EdpMissingCredsToast::GetAction1Text(ushort * *)

- ea: `0x180008920`
- end: `0x1800089a5`
- name: `?GetAction1Text@EdpMissingCredsToast@@UEAAJPEAPEAG@Z`
- size: `133`
- prototype: `__int64 __fastcall(EdpMissingCredsToast *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800056c4`
- `0x180008920`
- `0x18000a91c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008986`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008986`

## string_xrefs

- `0x180008968`: `ds\security\efs\edptask\toast\edptoast.cpp`

## pseudocode

```c
__int64 __fastcall EdpMissingCredsToast::GetAction1Text(EdpMissingCredsToast *this, unsigned __int16 **a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  LPVOID pv[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  memset(pv, 0, 24);
  v3 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
         pv,
         &_ImageBase,
         209);
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
      (void *)0x3FB,
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
0x180008920  mov     rax, rsp
0x180008923  mov     [rax+8], rbx
0x180008927  push    rdi
0x180008928  sub     rsp, 40h
0x18000892c  mov     rdi, rdx
0x18000892f  mov     qword ptr [rax-28h], 0
0x180008937  lea     rdx, __ImageBase
0x18000893e  mov     qword ptr [rax-20h], 0
0x180008946  mov     r8d, 0D1h
0x18000894c  mov     qword ptr [rax-18h], 0
0x180008954  lea     rcx, [rax-28h]
0x180008958  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@I@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint)
0x18000895d  mov     ebx, eax
0x18000895f  test    eax, eax
0x180008961  jns     short loc_180008990
0x180008963  mov     rcx, [rsp+48h]; this
0x180008968  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x18000896f  mov     r9d, eax; char *
0x180008972  mov     edx, 3FBh; void *
0x180008977  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000897c  mov     rcx, [rsp+48h+pv]; pv
0x180008981  test    rcx, rcx
0x180008984  jz      short loc_18000898C
0x180008986  call    cs:__imp_CoTaskMemFree
0x18000898c  mov     eax, ebx
0x18000898e  jmp     short loc_18000899A
0x180008990  mov     rax, [rsp+48h+pv]
0x180008995  mov     [rdi], rax
0x180008998  xor     eax, eax
0x18000899a  mov     rbx, [rsp+48h+arg_0]
0x18000899f  add     rsp, 40h
0x1800089a3  pop     rdi
0x1800089a4  retn
```
