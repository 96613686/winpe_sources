# EdpMissingCredsToast::GetToastTitle(ushort * *)

- ea: `0x18000a890`
- end: `0x18000a915`
- name: `?GetToastTitle@EdpMissingCredsToast@@UEAAJPEAPEAG@Z`
- size: `133`
- prototype: `__int64 __fastcall(EdpMissingCredsToast *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800056c4`
- `0x18000a890`
- `0x18000a91c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a8f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a8f6`

## string_xrefs

- `0x18000a8d8`: `ds\security\efs\edptask\toast\edptoast.cpp`

## pseudocode

```c
__int64 __fastcall EdpMissingCredsToast::GetToastTitle(EdpMissingCredsToast *this, unsigned __int16 **a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  LPVOID pv[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  memset(pv, 0, 24);
  v3 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
         pv,
         &_ImageBase,
         205);
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
      (void *)0x345,
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
0x18000a890  mov     rax, rsp
0x18000a893  mov     [rax+8], rbx
0x18000a897  push    rdi
0x18000a898  sub     rsp, 40h
0x18000a89c  mov     rdi, rdx
0x18000a89f  mov     qword ptr [rax-28h], 0
0x18000a8a7  lea     rdx, __ImageBase
0x18000a8ae  mov     qword ptr [rax-20h], 0
0x18000a8b6  mov     r8d, 0CDh
0x18000a8bc  mov     qword ptr [rax-18h], 0
0x18000a8c4  lea     rcx, [rax-28h]
0x18000a8c8  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@I@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint)
0x18000a8cd  mov     ebx, eax
0x18000a8cf  test    eax, eax
0x18000a8d1  jns     short loc_18000A900
0x18000a8d3  mov     rcx, [rsp+48h]; this
0x18000a8d8  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x18000a8df  mov     r9d, eax; char *
0x18000a8e2  mov     edx, 345h; void *
0x18000a8e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a8ec  mov     rcx, [rsp+48h+pv]; pv
0x18000a8f1  test    rcx, rcx
0x18000a8f4  jz      short loc_18000A8FC
0x18000a8f6  call    cs:__imp_CoTaskMemFree
0x18000a8fc  mov     eax, ebx
0x18000a8fe  jmp     short loc_18000A90A
0x18000a900  mov     rax, [rsp+48h+pv]
0x18000a905  mov     [rdi], rax
0x18000a908  xor     eax, eax
0x18000a90a  mov     rbx, [rsp+48h+arg_0]
0x18000a90f  add     rsp, 40h
0x18000a913  pop     rdi
0x18000a914  retn
```
