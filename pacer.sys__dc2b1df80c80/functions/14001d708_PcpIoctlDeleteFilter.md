# PcpIoctlDeleteFilter

- ea: `0x14001d708`
- end: `0x14001d7c3`
- name: `PcpIoctlDeleteFilter`
- size: `187`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140020b50`

## callees

- `0x14000dbb8`
- `0x14000e91c`
- `0x14000eb54`
- `0x14001d708`

## import_xrefs

- `fwpkclnt!FwpmFilterDeleteByKey0` at `0x14001d752`
- `fwpkclnt!FwpmFilterDeleteByKey0` at `0x14001d752`

## pseudocode

```c
__int64 __fastcall PcpIoctlDeleteFilter(__int64 a1, __int64 a2, _DWORD *a3)
{
  __int64 v4; // r14
  GUID *v5; // rdi
  NTSTATUS v6; // ebx
  __int64 result; // rax

  if ( *(_DWORD *)(a2 + 16) < 0x10u || *(_DWORD *)(a2 + 8) < 4u )
    return 3221225507LL;
  v4 = *(_QWORD *)(a1 + 24);
  v5 = *(GUID **)(v4 + 8);
  v6 = PcpRemoveFilter(v5, *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL));
  if ( v6 >= 0 )
  {
    v6 = FwpmFilterDeleteByKey0(PcgWfpEngineHandle, v5 + 1);
    if ( v6 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        WPP_af99db03d8cf39a69caee5869b1abac6_Traceguids,
        (unsigned int)v6);
    }
    PcpFreeFilter(v5);
  }
  *(_DWORD *)v4 = v6;
  result = (unsigned int)v6;
  *a3 = 4;
  return result;
}

```

## disassembly

```asm
0x14001d708  push    rbx
0x14001d70a  push    rsi
0x14001d70b  push    rdi
0x14001d70c  push    r14
0x14001d70e  sub     rsp, 28h
0x14001d712  cmp     dword ptr [rdx+10h], 10h
0x14001d716  mov     rsi, r8
0x14001d719  jb      loc_14001D7B3
0x14001d71f  cmp     dword ptr [rdx+8], 4
0x14001d723  jb      loc_14001D7B3
0x14001d729  mov     r14, [rcx+18h]
0x14001d72d  mov     rdx, [rdx+30h]
0x14001d731  mov     rdi, [r14+8]
0x14001d735  mov     rdx, [rdx+18h]
0x14001d739  mov     rcx, rdi
0x14001d73c  call    PcpRemoveFilter
0x14001d741  mov     ebx, eax
0x14001d743  test    eax, eax
0x14001d745  js      short loc_14001D7A6
0x14001d747  mov     rcx, cs:PcgWfpEngineHandle; engineHandle
0x14001d74e  lea     rdx, [rdi+10h]; key
0x14001d752  call    cs:__imp_FwpmFilterDeleteByKey0
0x14001d759  nop     dword ptr [rax+rax+00h]
0x14001d75e  mov     ebx, eax
0x14001d760  test    eax, eax
0x14001d762  jns     short loc_14001D79E
0x14001d764  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d76b  lea     rax, WPP_GLOBAL_Control
0x14001d772  cmp     rcx, rax
0x14001d775  jz      short loc_14001D79E
0x14001d777  cmp     byte ptr [rcx+29h], 3
0x14001d77b  jb      short loc_14001D79E
0x14001d77d  test    dword ptr [rcx+2Ch], 800h
0x14001d784  jz      short loc_14001D79E
0x14001d786  mov     rcx, [rcx+18h]
0x14001d78a  lea     r8, WPP_af99db03d8cf39a69caee5869b1abac6_Traceguids
0x14001d791  mov     edx, 0Dh
0x14001d796  mov     r9d, ebx
0x14001d799  call    WPP_SF_D
0x14001d79e  mov     rcx, rdi; P
0x14001d7a1  call    PcpFreeFilter
0x14001d7a6  mov     [r14], ebx
0x14001d7a9  mov     eax, ebx
0x14001d7ab  mov     dword ptr [rsi], 4
0x14001d7b1  jmp     short loc_14001D7B8
0x14001d7b3  mov     eax, 0C0000023h
0x14001d7b8  add     rsp, 28h
0x14001d7bc  pop     r14
0x14001d7be  pop     rdi
0x14001d7bf  pop     rsi
0x14001d7c0  pop     rbx
0x14001d7c1  retn
```
