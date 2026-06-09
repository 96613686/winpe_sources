# BitLockerToast::GetToastIdString(ushort * *)

- ea: `0x18000a260`
- end: `0x18000a2dc`
- name: `?GetToastIdString@BitLockerToast@@UEAAJPEAPEAG@Z`
- size: `124`
- prototype: `__int64 __fastcall(BitLockerToast *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800056c4`
- `0x180008278`
- `0x18000a260`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a2bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a2bd`

## string_xrefs

- `0x18000a2a1`: `ds\security\efs\edptask\toast\edptoast.cpp`

## pseudocode

```c
__int64 __fastcall BitLockerToast::GetToastIdString(BitLockerToast *this, unsigned __int16 **a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  LPVOID pv[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  pv[0] = 0;
  pv[1] = (LPVOID)-1LL;
  pv[2] = (LPVOID)-1LL;
  v3 = CoAllocString(L"Windows.SystemToast.BitLockerPolicyRefresh", (unsigned __int16 **)pv);
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
      (void *)0x678,
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
0x18000a260  mov     r11, rsp
0x18000a263  mov     [r11+8], rbx
0x18000a267  push    rdi
0x18000a268  sub     rsp, 40h
0x18000a26c  mov     rdi, rdx
0x18000a26f  mov     qword ptr [r11-28h], 0
0x18000a277  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a27b  mov     [r11-20h], rax
0x18000a27f  mov     [r11-18h], rax
0x18000a283  lea     rdx, [r11-28h]; unsigned __int16 **
0x18000a287  lea     rcx, aWindowsSystemt; "Windows.SystemToast.BitLockerPolicyRefr"...
0x18000a28e  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x18000a293  mov     ebx, eax
0x18000a295  test    eax, eax
0x18000a297  jns     short loc_18000A2C7
0x18000a299  mov     rcx, [rsp+48h]; this
0x18000a29e  mov     r9d, eax; char *
0x18000a2a1  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x18000a2a8  mov     edx, 678h; void *
0x18000a2ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a2b2  nop
0x18000a2b3  mov     rcx, [rsp+48h+pv]; pv
0x18000a2b8  test    rcx, rcx
0x18000a2bb  jz      short loc_18000A2C3
0x18000a2bd  call    cs:__imp_CoTaskMemFree
0x18000a2c3  mov     eax, ebx
0x18000a2c5  jmp     short loc_18000A2D1
0x18000a2c7  mov     rax, [rsp+48h+pv]
0x18000a2cc  mov     [rdi], rax
0x18000a2cf  xor     eax, eax
0x18000a2d1  mov     rbx, [rsp+48h+arg_0]
0x18000a2d6  add     rsp, 40h
0x18000a2da  pop     rdi
0x18000a2db  retn
```
