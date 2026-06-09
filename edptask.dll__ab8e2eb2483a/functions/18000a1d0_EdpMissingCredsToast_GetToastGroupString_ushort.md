# EdpMissingCredsToast::GetToastGroupString(ushort * *)

- ea: `0x18000a1d0`
- end: `0x18000a24c`
- name: `?GetToastGroupString@EdpMissingCredsToast@@UEAAJPEAPEAG@Z`
- size: `124`
- prototype: `__int64 __fastcall(EdpMissingCredsToast *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800056c4`
- `0x180008278`
- `0x18000a1d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a22d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a22d`

## string_xrefs

- `0x18000a211`: `ds\security\efs\edptask\toast\edptoast.cpp`

## pseudocode

```c
__int64 __fastcall EdpMissingCredsToast::GetToastGroupString(EdpMissingCredsToast *this, unsigned __int16 **a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  LPVOID pv[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  pv[0] = 0;
  pv[1] = (LPVOID)-1LL;
  pv[2] = (LPVOID)-1LL;
  v3 = CoAllocString(L"WIPToastGroup", (unsigned __int16 **)pv);
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
      (void *)0x3AD,
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
0x18000a1d0  mov     r11, rsp
0x18000a1d3  mov     [r11+8], rbx
0x18000a1d7  push    rdi
0x18000a1d8  sub     rsp, 40h
0x18000a1dc  mov     rdi, rdx
0x18000a1df  mov     qword ptr [r11-28h], 0
0x18000a1e7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a1eb  mov     [r11-20h], rax
0x18000a1ef  mov     [r11-18h], rax
0x18000a1f3  lea     rdx, [r11-28h]; unsigned __int16 **
0x18000a1f7  lea     rcx, aWiptoastgroup; "WIPToastGroup"
0x18000a1fe  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x18000a203  mov     ebx, eax
0x18000a205  test    eax, eax
0x18000a207  jns     short loc_18000A237
0x18000a209  mov     rcx, [rsp+48h]; this
0x18000a20e  mov     r9d, eax; char *
0x18000a211  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x18000a218  mov     edx, 3ADh; void *
0x18000a21d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a222  nop
0x18000a223  mov     rcx, [rsp+48h+pv]; pv
0x18000a228  test    rcx, rcx
0x18000a22b  jz      short loc_18000A233
0x18000a22d  call    cs:__imp_CoTaskMemFree
0x18000a233  mov     eax, ebx
0x18000a235  jmp     short loc_18000A241
0x18000a237  mov     rax, [rsp+48h+pv]
0x18000a23c  mov     [rdi], rax
0x18000a23f  xor     eax, eax
0x18000a241  mov     rbx, [rsp+48h+arg_0]
0x18000a246  add     rsp, 40h
0x18000a24a  pop     rdi
0x18000a24b  retn
```
