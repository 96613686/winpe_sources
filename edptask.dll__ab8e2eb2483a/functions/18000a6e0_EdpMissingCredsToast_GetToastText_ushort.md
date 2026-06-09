# EdpMissingCredsToast::GetToastText(ushort * *)

- ea: `0x18000a6e0`
- end: `0x18000a765`
- name: `?GetToastText@EdpMissingCredsToast@@UEAAJPEAPEAG@Z`
- size: `133`
- prototype: `__int64 __fastcall(EdpMissingCredsToast *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800056c4`
- `0x18000a6e0`
- `0x18000a91c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a746`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a746`

## string_xrefs

- `0x18000a728`: `ds\security\efs\edptask\toast\edptoast.cpp`

## pseudocode

```c
__int64 __fastcall EdpMissingCredsToast::GetToastText(EdpMissingCredsToast *this, unsigned __int16 **a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  LPVOID pv[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  memset(pv, 0, 24);
  v3 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
         pv,
         &_ImageBase,
         206);
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
      (void *)0x35F,
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
0x18000a6e0  mov     rax, rsp
0x18000a6e3  mov     [rax+8], rbx
0x18000a6e7  push    rdi
0x18000a6e8  sub     rsp, 40h
0x18000a6ec  mov     rdi, rdx
0x18000a6ef  mov     qword ptr [rax-28h], 0
0x18000a6f7  lea     rdx, __ImageBase
0x18000a6fe  mov     qword ptr [rax-20h], 0
0x18000a706  mov     r8d, 0CEh
0x18000a70c  mov     qword ptr [rax-18h], 0
0x18000a714  lea     rcx, [rax-28h]
0x18000a718  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@I@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint)
0x18000a71d  mov     ebx, eax
0x18000a71f  test    eax, eax
0x18000a721  jns     short loc_18000A750
0x18000a723  mov     rcx, [rsp+48h]; this
0x18000a728  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x18000a72f  mov     r9d, eax; char *
0x18000a732  mov     edx, 35Fh; void *
0x18000a737  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a73c  mov     rcx, [rsp+48h+pv]; pv
0x18000a741  test    rcx, rcx
0x18000a744  jz      short loc_18000A74C
0x18000a746  call    cs:__imp_CoTaskMemFree
0x18000a74c  mov     eax, ebx
0x18000a74e  jmp     short loc_18000A75A
0x18000a750  mov     rax, [rsp+48h+pv]
0x18000a755  mov     [rdi], rax
0x18000a758  xor     eax, eax
0x18000a75a  mov     rbx, [rsp+48h+arg_0]
0x18000a75f  add     rsp, 40h
0x18000a763  pop     rdi
0x18000a764  retn
```
