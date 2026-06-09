# EdpAadReauthToast::GetToastGroupString(ushort * *)

- ea: `0x18000a140`
- end: `0x18000a1bc`
- name: `?GetToastGroupString@EdpAadReauthToast@@UEAAJPEAPEAG@Z`
- size: `124`
- prototype: `__int64 __fastcall(EdpAadReauthToast *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800056c4`
- `0x180008278`
- `0x18000a140`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a19d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a19d`

## string_xrefs

- `0x18000a181`: `ds\security\efs\edptask\toast\edptoast.cpp`

## pseudocode

```c
__int64 __fastcall EdpAadReauthToast::GetToastGroupString(EdpAadReauthToast *this, unsigned __int16 **a2)
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
      (void *)0x2C5,
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
0x18000a140  mov     r11, rsp
0x18000a143  mov     [r11+8], rbx
0x18000a147  push    rdi
0x18000a148  sub     rsp, 40h
0x18000a14c  mov     rdi, rdx
0x18000a14f  mov     qword ptr [r11-28h], 0
0x18000a157  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a15b  mov     [r11-20h], rax
0x18000a15f  mov     [r11-18h], rax
0x18000a163  lea     rdx, [r11-28h]; unsigned __int16 **
0x18000a167  lea     rcx, aWiptoastgroup; "WIPToastGroup"
0x18000a16e  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x18000a173  mov     ebx, eax
0x18000a175  test    eax, eax
0x18000a177  jns     short loc_18000A1A7
0x18000a179  mov     rcx, [rsp+48h]; this
0x18000a17e  mov     r9d, eax; char *
0x18000a181  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x18000a188  mov     edx, 2C5h; void *
0x18000a18d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a192  nop
0x18000a193  mov     rcx, [rsp+48h+pv]; pv
0x18000a198  test    rcx, rcx
0x18000a19b  jz      short loc_18000A1A3
0x18000a19d  call    cs:__imp_CoTaskMemFree
0x18000a1a3  mov     eax, ebx
0x18000a1a5  jmp     short loc_18000A1B1
0x18000a1a7  mov     rax, [rsp+48h+pv]
0x18000a1ac  mov     [rdi], rax
0x18000a1af  xor     eax, eax
0x18000a1b1  mov     rbx, [rsp+48h+arg_0]
0x18000a1b6  add     rsp, 40h
0x18000a1ba  pop     rdi
0x18000a1bb  retn
```
