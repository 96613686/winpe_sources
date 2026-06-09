# LkmdTelSubmitReport

- ea: `0x140054e28`
- end: `0x140054f17`
- name: `LkmdTelSubmitReport`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140028000`

## callees

- `0x140054e28`
- `0x140054f48`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140054e4f`
- `ntoskrnl!DbgPrintEx` at `0x140054e8b`
- `ntoskrnl!DbgPrintEx` at `0x140054ec5`
- `ntoskrnl!DbgPrintEx` at `0x140054ef6`
- `ntoskrnl!DbgPrintEx` at `0x140054e4f`
- `ntoskrnl!DbgPrintEx` at `0x140054e8b`
- `ntoskrnl!DbgPrintEx` at `0x140054ec5`
- `ntoskrnl!DbgPrintEx` at `0x140054ef6`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCloseHandle` at `0x140054ed4`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCloseHandle` at `0x140054ed4`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelSubmitReport` at `0x140054e6a`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelSubmitReport` at `0x140054e6a`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCancelReport` at `0x140054ea3`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelCancelReport` at `0x140054ea3`

## string_xrefs

- `0x140054e42`: `LKMDTEL: LkmdTelSubmitReport: LkmdTelpWriteDumpFile failed, status 0x%X\n`

## pseudocode

```c
__int64 __fastcall LkmdTelSubmitReport(__int64 a1)
{
  int v2; // eax
  int v3; // edi
  _QWORD *v4; // rbx
  int v5; // eax
  int v6; // eax
  int v7; // eax

  v2 = LkmdTelpWriteDumpFile(a1);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v4 = (_QWORD *)(a1 + 96);
    v5 = WerLiveKernelSubmitReport(*v4, 0);
    v3 = v5;
    if ( v5 < 0 )
      DbgPrintEx(5u, 0, "LKMDTEL: LkmdTelSubmitReport: WerLiveKernelSubmitReport failed, status 0x%X\n", v5);
  }
  else
  {
    DbgPrintEx(5u, 0, "LKMDTEL: LkmdTelSubmitReport: LkmdTelpWriteDumpFile failed, status 0x%X\n", v2);
    v4 = (_QWORD *)(a1 + 96);
  }
  if ( *v4 )
  {
    if ( v3 < 0 )
    {
      v6 = WerLiveKernelCancelReport();
      if ( v6 < 0 )
        DbgPrintEx(5u, 1u, "LKMDTEL: LkmdTelSubmitReport: WerLiveKernelCancelReport failed, status 0x%X\n", v6);
    }
    v7 = WerLiveKernelCloseHandle(*v4);
    if ( v7 < 0 )
      DbgPrintEx(5u, 1u, "LKMDTEL: LkmdTelSubmitReport: WerLiveKernelCloseHandle failed, status 0x%X\n", v7);
    *v4 = 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140054e28  mov     [rsp+arg_0], rbx
0x140054e2d  push    rdi
0x140054e2e  sub     rsp, 20h
0x140054e32  mov     rbx, rcx
0x140054e35  call    LkmdTelpWriteDumpFile
0x140054e3a  mov     edi, eax
0x140054e3c  test    eax, eax
0x140054e3e  jns     short loc_140054E61
0x140054e40  xor     edx, edx; Level
0x140054e42  lea     r8, aLkmdtelLkmdtel_2; "LKMDTEL: LkmdTelSubmitReport: LkmdTelpW"...
0x140054e49  mov     r9d, eax
0x140054e4c  lea     ecx, [rdx+5]; ComponentId
0x140054e4f  call    cs:__imp_DbgPrintEx
0x140054e56  nop     dword ptr [rax+rax+00h]
0x140054e5b  add     rbx, 60h ; '`'
0x140054e5f  jmp     short loc_140054E97
0x140054e61  add     rbx, 60h ; '`'
0x140054e65  xor     edx, edx
0x140054e67  mov     rcx, [rbx]
0x140054e6a  call    cs:__imp_WerLiveKernelSubmitReport
0x140054e71  nop     dword ptr [rax+rax+00h]
0x140054e76  mov     edi, eax
0x140054e78  test    eax, eax
0x140054e7a  jns     short loc_140054E97
0x140054e7c  xor     edx, edx; Level
0x140054e7e  lea     r8, aLkmdtelLkmdtel_0; "LKMDTEL: LkmdTelSubmitReport: WerLiveKe"...
0x140054e85  mov     r9d, eax
0x140054e88  lea     ecx, [rdx+5]; ComponentId
0x140054e8b  call    cs:__imp_DbgPrintEx
0x140054e92  nop     dword ptr [rax+rax+00h]
0x140054e97  mov     rcx, [rbx]
0x140054e9a  test    rcx, rcx
0x140054e9d  jz      short loc_140054F09
0x140054e9f  test    edi, edi
0x140054ea1  jns     short loc_140054ED1
0x140054ea3  call    cs:__imp_WerLiveKernelCancelReport
0x140054eaa  nop     dword ptr [rax+rax+00h]
0x140054eaf  test    eax, eax
0x140054eb1  jns     short loc_140054ED1
0x140054eb3  mov     edx, 1; Level
0x140054eb8  lea     r8, aLkmdtelLkmdtel_3; "LKMDTEL: LkmdTelSubmitReport: WerLiveKe"...
0x140054ebf  mov     r9d, eax
0x140054ec2  lea     ecx, [rdx+4]; ComponentId
0x140054ec5  call    cs:__imp_DbgPrintEx
0x140054ecc  nop     dword ptr [rax+rax+00h]
0x140054ed1  mov     rcx, [rbx]
0x140054ed4  call    cs:__imp_WerLiveKernelCloseHandle
0x140054edb  nop     dword ptr [rax+rax+00h]
0x140054ee0  test    eax, eax
0x140054ee2  jns     short loc_140054F02
0x140054ee4  mov     edx, 1; Level
0x140054ee9  lea     r8, aLkmdtelLkmdtel; "LKMDTEL: LkmdTelSubmitReport: WerLiveKe"...
0x140054ef0  mov     r9d, eax
0x140054ef3  lea     ecx, [rdx+4]; ComponentId
0x140054ef6  call    cs:__imp_DbgPrintEx
0x140054efd  nop     dword ptr [rax+rax+00h]
0x140054f02  mov     qword ptr [rbx], 0
0x140054f09  mov     rbx, [rsp+28h+arg_0]
0x140054f0e  mov     eax, edi
0x140054f10  add     rsp, 20h
0x140054f14  pop     rdi
0x140054f15  retn
```
