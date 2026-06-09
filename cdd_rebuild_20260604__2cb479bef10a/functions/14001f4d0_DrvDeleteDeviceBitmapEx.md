# DrvDeleteDeviceBitmapEx

- ea: `0x14001f4d0`
- end: `0x14001f5bd`
- name: `DrvDeleteDeviceBitmapEx`
- size: `237`
- prototype: `FN_DrvDeleteDeviceBitmapEx`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14001f4d0`
- `0x1400372d0`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdTrace` at `0x14001f502`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14001f535`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14001f502`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14001f535`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001f585`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001f585`
- `watchdog!WdLogSingleEntry0` at `0x14001f56f`
- `watchdog!WdLogSingleEntry0` at `0x14001f56f`

## pseudocode

```c
void __stdcall DrvDeleteDeviceBitmapEx(DHSURF a1)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rax
  __int64 v4; // rdx
  __int64 v5; // rcx
  _QWORD *v6; // rax

  if ( !a1 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 2693;
    v6 = (_QWORD *)WdLogNewEntry5_WdAssertion(v5, v4);
    v6[3] = gCddImageInfo;
    v6[4] = (unsigned int)dword_14003E570;
    v6[5] = 215857758;
    WdLogGlobalForLineNumber = 2693;
  }
  if ( g_bEnableTraceBitmapExReuse )
  {
    v2 = (_QWORD *)WdLogNewEntry5_WdTrace();
    v2[3] = a1;
    v2[4] = *((unsigned int *)a1 + 4);
    v2[5] = *((unsigned int *)a1 + 5);
    v2[6] = *((int *)a1 + 46);
    WdLogGlobalForLineNumber = 2699;
    v3 = (_QWORD *)WdLogNewEntry5_WdTrace();
    v3[3] = gCddImageInfo;
    v3[4] = (unsigned int)dword_14003E570;
    v3[5] = 215857758;
    WdLogGlobalForLineNumber = 2699;
  }
  (*(void (__fastcall **)(DHSURF))(*(_QWORD *)a1 + 48LL))(a1);
}

```

## disassembly

```asm
0x14001f4d0  push    rbx
0x14001f4d2  sub     rsp, 20h
0x14001f4d6  mov     rbx, rcx
0x14001f4d9  test    rcx, rcx
0x14001f4dc  jz      loc_14001F56A
0x14001f4e2  mov     eax, cs:?g_bEnableTraceBitmapExReuse@@3HC; int volatile g_bEnableTraceBitmapExReuse
0x14001f4e8  test    eax, eax
0x14001f4ea  jnz     short loc_14001F502
0x14001f4ec  mov     rax, [rbx]
0x14001f4ef  mov     rcx, rbx
0x14001f4f2  mov     rax, [rax+30h]
0x14001f4f6  call    _guard_dispatch_icall
0x14001f4fb  add     rsp, 20h
0x14001f4ff  pop     rbx
0x14001f500  retn
0x14001f502  call    cs:__imp_WdLogNewEntry5_WdTrace
0x14001f509  nop     dword ptr [rax+rax+00h]
0x14001f50e  mov     [rax+18h], rbx
0x14001f512  mov     ecx, [rbx+10h]
0x14001f515  mov     [rax+20h], rcx
0x14001f519  mov     ecx, [rbx+14h]
0x14001f51c  mov     [rax+28h], rcx
0x14001f520  movsxd  rcx, dword ptr [rbx+0B8h]
0x14001f527  mov     [rax+30h], rcx
0x14001f52b  mov     cs:WdLogGlobalForLineNumber, 0A8Bh
0x14001f535  call    cs:__imp_WdLogNewEntry5_WdTrace
0x14001f53c  nop     dword ptr [rax+rax+00h]
0x14001f541  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001f548  mov     [rax+18h], rcx
0x14001f54c  mov     ecx, cs:dword_14003E570
0x14001f552  mov     [rax+20h], rcx
0x14001f556  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001f55e  mov     cs:WdLogGlobalForLineNumber, 0A8Bh
0x14001f568  jmp     short loc_14001F4EC
0x14001f56a  mov     ecx, 1
0x14001f56f  call    cs:__imp_WdLogSingleEntry0
0x14001f576  nop     dword ptr [rax+rax+00h]
0x14001f57b  mov     cs:WdLogGlobalForLineNumber, 0A85h
0x14001f585  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14001f58c  nop     dword ptr [rax+rax+00h]
0x14001f591  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001f598  mov     [rax+18h], rcx
0x14001f59c  mov     ecx, cs:dword_14003E570
0x14001f5a2  mov     [rax+20h], rcx
0x14001f5a6  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001f5ae  mov     cs:WdLogGlobalForLineNumber, 0A85h
0x14001f5b8  jmp     loc_14001F4E2
```
