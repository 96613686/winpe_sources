# BitLockerToast::GetToastGroupString(ushort * *)

- ea: `0x18000a0b0`
- end: `0x18000a12c`
- name: `?GetToastGroupString@BitLockerToast@@UEAAJPEAPEAG@Z`
- size: `124`
- prototype: `__int64 __fastcall(BitLockerToast *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800056c4`
- `0x180008278`
- `0x18000a0b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a10d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a10d`

## string_xrefs

- `0x18000a0f1`: `ds\security\efs\edptask\toast\edptoast.cpp`

## pseudocode

```c
__int64 __fastcall BitLockerToast::GetToastGroupString(BitLockerToast *this, unsigned __int16 **a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  LPVOID pv[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  pv[0] = 0;
  pv[1] = (LPVOID)-1LL;
  pv[2] = (LPVOID)-1LL;
  v3 = CoAllocString(L"BitlockerToastGroup", (unsigned __int16 **)pv);
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
      (void *)0x692,
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
0x18000a0b0  mov     r11, rsp
0x18000a0b3  mov     [r11+8], rbx
0x18000a0b7  push    rdi
0x18000a0b8  sub     rsp, 40h
0x18000a0bc  mov     rdi, rdx
0x18000a0bf  mov     qword ptr [r11-28h], 0
0x18000a0c7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a0cb  mov     [r11-20h], rax
0x18000a0cf  mov     [r11-18h], rax
0x18000a0d3  lea     rdx, [r11-28h]; unsigned __int16 **
0x18000a0d7  lea     rcx, aBitlockertoast; "BitlockerToastGroup"
0x18000a0de  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x18000a0e3  mov     ebx, eax
0x18000a0e5  test    eax, eax
0x18000a0e7  jns     short loc_18000A117
0x18000a0e9  mov     rcx, [rsp+48h]; this
0x18000a0ee  mov     r9d, eax; char *
0x18000a0f1  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x18000a0f8  mov     edx, 692h; void *
0x18000a0fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a102  nop
0x18000a103  mov     rcx, [rsp+48h+pv]; pv
0x18000a108  test    rcx, rcx
0x18000a10b  jz      short loc_18000A113
0x18000a10d  call    cs:__imp_CoTaskMemFree
0x18000a113  mov     eax, ebx
0x18000a115  jmp     short loc_18000A121
0x18000a117  mov     rax, [rsp+48h+pv]
0x18000a11c  mov     [rdi], rax
0x18000a11f  xor     eax, eax
0x18000a121  mov     rbx, [rsp+48h+arg_0]
0x18000a126  add     rsp, 40h
0x18000a12a  pop     rdi
0x18000a12b  retn
```
