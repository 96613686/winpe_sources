# EdpMissingCredsToast::GetAction2Text(ushort * *)

- ea: `0x1800089e0`
- end: `0x180008a65`
- name: `?GetAction2Text@EdpMissingCredsToast@@UEAAJPEAPEAG@Z`
- size: `133`
- prototype: `__int64 __fastcall(EdpMissingCredsToast *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800056c4`
- `0x1800089e0`
- `0x18000a91c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008a46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008a46`

## string_xrefs

- `0x180008a28`: `ds\security\efs\edptask\toast\edptoast.cpp`

## pseudocode

```c
__int64 __fastcall EdpMissingCredsToast::GetAction2Text(EdpMissingCredsToast *this, unsigned __int16 **a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  LPVOID pv[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  memset(pv, 0, 24);
  v3 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
         pv,
         &_ImageBase,
         210);
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
      (void *)0x415,
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
0x1800089e0  mov     rax, rsp
0x1800089e3  mov     [rax+8], rbx
0x1800089e7  push    rdi
0x1800089e8  sub     rsp, 40h
0x1800089ec  mov     rdi, rdx
0x1800089ef  mov     qword ptr [rax-28h], 0
0x1800089f7  lea     rdx, __ImageBase
0x1800089fe  mov     qword ptr [rax-20h], 0
0x180008a06  mov     r8d, 0D2h
0x180008a0c  mov     qword ptr [rax-18h], 0
0x180008a14  lea     rcx, [rax-28h]
0x180008a18  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@I@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint)
0x180008a1d  mov     ebx, eax
0x180008a1f  test    eax, eax
0x180008a21  jns     short loc_180008A50
0x180008a23  mov     rcx, [rsp+48h]; this
0x180008a28  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x180008a2f  mov     r9d, eax; char *
0x180008a32  mov     edx, 415h; void *
0x180008a37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008a3c  mov     rcx, [rsp+48h+pv]; pv
0x180008a41  test    rcx, rcx
0x180008a44  jz      short loc_180008A4C
0x180008a46  call    cs:__imp_CoTaskMemFree
0x180008a4c  mov     eax, ebx
0x180008a4e  jmp     short loc_180008A5A
0x180008a50  mov     rax, [rsp+48h+pv]
0x180008a55  mov     [rdi], rax
0x180008a58  xor     eax, eax
0x180008a5a  mov     rbx, [rsp+48h+arg_0]
0x180008a5f  add     rsp, 40h
0x180008a63  pop     rdi
0x180008a64  retn
```
