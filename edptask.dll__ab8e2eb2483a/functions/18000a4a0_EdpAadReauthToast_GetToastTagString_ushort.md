# EdpAadReauthToast::GetToastTagString(ushort * *)

- ea: `0x18000a4a0`
- end: `0x18000a51c`
- name: `?GetToastTagString@EdpAadReauthToast@@UEAAJPEAPEAG@Z`
- size: `124`
- prototype: `__int64 __fastcall(EdpAadReauthToast *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800056c4`
- `0x180008278`
- `0x18000a4a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a4fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a4fd`

## string_xrefs

- `0x18000a4e1`: `ds\security\efs\edptask\toast\edptoast.cpp`

## pseudocode

```c
__int64 __fastcall EdpAadReauthToast::GetToastTagString(EdpAadReauthToast *this, unsigned __int16 **a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  LPVOID pv[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  pv[0] = 0;
  pv[1] = (LPVOID)-1LL;
  pv[2] = (LPVOID)-1LL;
  v3 = CoAllocString(L"WIPToastReAuthTag", (unsigned __int16 **)pv);
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
      (void *)0x2DF,
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
0x18000a4a0  mov     r11, rsp
0x18000a4a3  mov     [r11+8], rbx
0x18000a4a7  push    rdi
0x18000a4a8  sub     rsp, 40h
0x18000a4ac  mov     rdi, rdx
0x18000a4af  mov     qword ptr [r11-28h], 0
0x18000a4b7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a4bb  mov     [r11-20h], rax
0x18000a4bf  mov     [r11-18h], rax
0x18000a4c3  lea     rdx, [r11-28h]; unsigned __int16 **
0x18000a4c7  lea     rcx, aWiptoastreauth; "WIPToastReAuthTag"
0x18000a4ce  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x18000a4d3  mov     ebx, eax
0x18000a4d5  test    eax, eax
0x18000a4d7  jns     short loc_18000A507
0x18000a4d9  mov     rcx, [rsp+48h]; this
0x18000a4de  mov     r9d, eax; char *
0x18000a4e1  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x18000a4e8  mov     edx, 2DFh; void *
0x18000a4ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a4f2  nop
0x18000a4f3  mov     rcx, [rsp+48h+pv]; pv
0x18000a4f8  test    rcx, rcx
0x18000a4fb  jz      short loc_18000A503
0x18000a4fd  call    cs:__imp_CoTaskMemFree
0x18000a503  mov     eax, ebx
0x18000a505  jmp     short loc_18000A511
0x18000a507  mov     rax, [rsp+48h+pv]
0x18000a50c  mov     [rdi], rax
0x18000a50f  xor     eax, eax
0x18000a511  mov     rbx, [rsp+48h+arg_0]
0x18000a516  add     rsp, 40h
0x18000a51a  pop     rdi
0x18000a51b  retn
```
