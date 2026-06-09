# BitLockerToast::GetToastTitle(ushort * *)

- ea: `0x18000a770`
- end: `0x18000a7f5`
- name: `?GetToastTitle@BitLockerToast@@UEAAJPEAPEAG@Z`
- size: `133`
- prototype: `__int64 __fastcall(BitLockerToast *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800056c4`
- `0x18000a770`
- `0x18000a91c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a7d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a7d6`

## string_xrefs

- `0x18000a7b8`: `ds\security\efs\edptask\toast\edptoast.cpp`

## pseudocode

```c
__int64 __fastcall BitLockerToast::GetToastTitle(BitLockerToast *this, unsigned __int16 **a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  LPVOID pv[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  memset(pv, 0, 24);
  v3 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
         pv,
         &_ImageBase,
         207);
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
      (void *)0x62A,
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
0x18000a770  mov     rax, rsp
0x18000a773  mov     [rax+8], rbx
0x18000a777  push    rdi
0x18000a778  sub     rsp, 40h
0x18000a77c  mov     rdi, rdx
0x18000a77f  mov     qword ptr [rax-28h], 0
0x18000a787  lea     rdx, __ImageBase
0x18000a78e  mov     qword ptr [rax-20h], 0
0x18000a796  mov     r8d, 0CFh
0x18000a79c  mov     qword ptr [rax-18h], 0
0x18000a7a4  lea     rcx, [rax-28h]
0x18000a7a8  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@I@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint)
0x18000a7ad  mov     ebx, eax
0x18000a7af  test    eax, eax
0x18000a7b1  jns     short loc_18000A7E0
0x18000a7b3  mov     rcx, [rsp+48h]; this
0x18000a7b8  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x18000a7bf  mov     r9d, eax; char *
0x18000a7c2  mov     edx, 62Ah; void *
0x18000a7c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a7cc  mov     rcx, [rsp+48h+pv]; pv
0x18000a7d1  test    rcx, rcx
0x18000a7d4  jz      short loc_18000A7DC
0x18000a7d6  call    cs:__imp_CoTaskMemFree
0x18000a7dc  mov     eax, ebx
0x18000a7de  jmp     short loc_18000A7EA
0x18000a7e0  mov     rax, [rsp+48h+pv]
0x18000a7e5  mov     [rdi], rax
0x18000a7e8  xor     eax, eax
0x18000a7ea  mov     rbx, [rsp+48h+arg_0]
0x18000a7ef  add     rsp, 40h
0x18000a7f3  pop     rdi
0x18000a7f4  retn
```
