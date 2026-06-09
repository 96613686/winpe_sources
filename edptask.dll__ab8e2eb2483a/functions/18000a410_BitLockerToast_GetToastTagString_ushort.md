# BitLockerToast::GetToastTagString(ushort * *)

- ea: `0x18000a410`
- end: `0x18000a48c`
- name: `?GetToastTagString@BitLockerToast@@UEAAJPEAPEAG@Z`
- size: `124`
- prototype: `__int64 __fastcall(BitLockerToast *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800056c4`
- `0x180008278`
- `0x18000a410`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a46d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a46d`

## string_xrefs

- `0x18000a451`: `ds\security\efs\edptask\toast\edptoast.cpp`

## pseudocode

```c
__int64 __fastcall BitLockerToast::GetToastTagString(BitLockerToast *this, unsigned __int16 **a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  LPVOID pv[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  pv[0] = 0;
  pv[1] = (LPVOID)-1LL;
  pv[2] = (LPVOID)-1LL;
  v3 = CoAllocString(L"BitlockerToastTag", (unsigned __int16 **)pv);
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
      (void *)0x6AC,
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
0x18000a410  mov     r11, rsp
0x18000a413  mov     [r11+8], rbx
0x18000a417  push    rdi
0x18000a418  sub     rsp, 40h
0x18000a41c  mov     rdi, rdx
0x18000a41f  mov     qword ptr [r11-28h], 0
0x18000a427  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a42b  mov     [r11-20h], rax
0x18000a42f  mov     [r11-18h], rax
0x18000a433  lea     rdx, [r11-28h]; unsigned __int16 **
0x18000a437  lea     rcx, aBitlockertoast_0; "BitlockerToastTag"
0x18000a43e  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x18000a443  mov     ebx, eax
0x18000a445  test    eax, eax
0x18000a447  jns     short loc_18000A477
0x18000a449  mov     rcx, [rsp+48h]; this
0x18000a44e  mov     r9d, eax; char *
0x18000a451  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x18000a458  mov     edx, 6ACh; void *
0x18000a45d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a462  nop
0x18000a463  mov     rcx, [rsp+48h+pv]; pv
0x18000a468  test    rcx, rcx
0x18000a46b  jz      short loc_18000A473
0x18000a46d  call    cs:__imp_CoTaskMemFree
0x18000a473  mov     eax, ebx
0x18000a475  jmp     short loc_18000A481
0x18000a477  mov     rax, [rsp+48h+pv]
0x18000a47c  mov     [rdi], rax
0x18000a47f  xor     eax, eax
0x18000a481  mov     rbx, [rsp+48h+arg_0]
0x18000a486  add     rsp, 40h
0x18000a48a  pop     rdi
0x18000a48b  retn
```
