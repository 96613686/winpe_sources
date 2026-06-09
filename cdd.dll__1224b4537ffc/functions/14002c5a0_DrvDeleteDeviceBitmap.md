# DrvDeleteDeviceBitmap

- ea: `0x14002c5a0`
- end: `0x14002c610`
- name: `DrvDeleteDeviceBitmap`
- size: `112`
- prototype: `FN_DrvDeleteDeviceBitmap`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14002c5a0`
- `0x1400372d0`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002c5c7`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002c5c7`
- `watchdog!WdLogSingleEntry0` at `0x14002c5b1`
- `watchdog!WdLogSingleEntry0` at `0x14002c5b1`

## pseudocode

```c
void __stdcall DrvDeleteDeviceBitmap(DHSURF dhsurf)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  _QWORD *v4; // rax
  __int64 v5; // rcx

  if ( !dhsurf )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 2340;
    v4 = (_QWORD *)WdLogNewEntry5_WdAssertion(v3, v2);
    v5 = (unsigned int)dword_14003E570;
    v4[3] = gCddImageInfo;
    v4[4] = v5;
    v4[5] = 215857758;
    WdLogGlobalForLineNumber = 2340;
  }
  (*(void (__fastcall **)(DHSURF))(*(_QWORD *)dhsurf + 48LL))(dhsurf);
}

```

## disassembly

```asm
0x14002c5a0  push    rbx
0x14002c5a2  sub     rsp, 20h
0x14002c5a6  mov     rbx, rcx
0x14002c5a9  test    rcx, rcx
0x14002c5ac  jnz     short loc_14002C5FA
0x14002c5ae  lea     ecx, [rbx+1]
0x14002c5b1  call    cs:__imp_WdLogSingleEntry0
0x14002c5b8  nop     dword ptr [rax+rax+00h]
0x14002c5bd  mov     cs:WdLogGlobalForLineNumber, 924h
0x14002c5c7  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14002c5ce  nop     dword ptr [rax+rax+00h]
0x14002c5d3  mov     rdx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002c5da  mov     ecx, cs:dword_14003E570
0x14002c5e0  mov     [rax+18h], rdx
0x14002c5e4  mov     [rax+20h], rcx
0x14002c5e8  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002c5f0  mov     cs:WdLogGlobalForLineNumber, 924h
0x14002c5fa  mov     rax, [rbx]
0x14002c5fd  mov     rcx, rbx
0x14002c600  mov     rax, [rax+30h]
0x14002c604  call    _guard_dispatch_icall
0x14002c609  add     rsp, 20h
0x14002c60d  pop     rbx
0x14002c60e  retn
```
