# BitLockerToast::GetToastText(ushort * *)

- ea: `0x18000a5c0`
- end: `0x18000a645`
- name: `?GetToastText@BitLockerToast@@UEAAJPEAPEAG@Z`
- size: `133`
- prototype: `__int64 __fastcall(BitLockerToast *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800056c4`
- `0x18000a5c0`
- `0x18000a91c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a626`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a626`

## string_xrefs

- `0x18000a608`: `ds\security\efs\edptask\toast\edptoast.cpp`

## pseudocode

```c
__int64 __fastcall BitLockerToast::GetToastText(BitLockerToast *this, unsigned __int16 **a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  LPVOID pv[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  memset(pv, 0, 24);
  v3 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
         pv,
         &_ImageBase,
         208);
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
      (void *)0x644,
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
0x18000a5c0  mov     rax, rsp
0x18000a5c3  mov     [rax+8], rbx
0x18000a5c7  push    rdi
0x18000a5c8  sub     rsp, 40h
0x18000a5cc  mov     rdi, rdx
0x18000a5cf  mov     qword ptr [rax-28h], 0
0x18000a5d7  lea     rdx, __ImageBase
0x18000a5de  mov     qword ptr [rax-20h], 0
0x18000a5e6  mov     r8d, 0D0h
0x18000a5ec  mov     qword ptr [rax-18h], 0
0x18000a5f4  lea     rcx, [rax-28h]
0x18000a5f8  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@I@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint)
0x18000a5fd  mov     ebx, eax
0x18000a5ff  test    eax, eax
0x18000a601  jns     short loc_18000A630
0x18000a603  mov     rcx, [rsp+48h]; this
0x18000a608  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x18000a60f  mov     r9d, eax; char *
0x18000a612  mov     edx, 644h; void *
0x18000a617  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a61c  mov     rcx, [rsp+48h+pv]; pv
0x18000a621  test    rcx, rcx
0x18000a624  jz      short loc_18000A62C
0x18000a626  call    cs:__imp_CoTaskMemFree
0x18000a62c  mov     eax, ebx
0x18000a62e  jmp     short loc_18000A63A
0x18000a630  mov     rax, [rsp+48h+pv]
0x18000a635  mov     [rdi], rax
0x18000a638  xor     eax, eax
0x18000a63a  mov     rbx, [rsp+48h+arg_0]
0x18000a63f  add     rsp, 40h
0x18000a643  pop     rdi
0x18000a644  retn
```
