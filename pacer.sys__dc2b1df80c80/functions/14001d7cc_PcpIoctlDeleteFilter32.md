# PcpIoctlDeleteFilter32

- ea: `0x14001d7cc`
- end: `0x14001d8a1`
- name: `PcpIoctlDeleteFilter32`
- size: `213`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140020b50`

## callees

- `0x14000dbb8`
- `0x14000e9fc`
- `0x14000eb54`
- `0x14001d7cc`

## import_xrefs

- `fwpkclnt!FwpmFilterDeleteByKey0` at `0x14001d830`
- `fwpkclnt!FwpmFilterDeleteByKey0` at `0x14001d830`

## pseudocode

```c
__int64 __fastcall PcpIoctlDeleteFilter32(__int64 a1, __int64 a2, _DWORD *a3)
{
  bool v3; // cf
  NTSTATUS *v5; // rdi
  __int64 v6; // rcx
  NTSTATUS v7; // ebx
  PVOID v8; // rsi
  __int64 result; // rax
  PVOID P; // [rsp+50h] [rbp+8h] BYREF

  v3 = *(_DWORD *)(a2 + 16) < 8u;
  P = 0;
  if ( v3 || *(_DWORD *)(a2 + 8) < 4u )
    return 3221225507LL;
  v5 = *(NTSTATUS **)(a1 + 24);
  v6 = (unsigned int)v5[1];
  if ( (_DWORD)v6 )
  {
    v7 = PcpRemoveFilterByHandle32(v6, *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL), &P);
    if ( v7 >= 0 )
    {
      v8 = P;
      v7 = FwpmFilterDeleteByKey0(PcgWfpEngineHandle, (const GUID *)P + 1);
      if ( v7 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
      {
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          WPP_af99db03d8cf39a69caee5869b1abac6_Traceguids,
          (unsigned int)v7);
      }
      PcpFreeFilter(v8);
    }
  }
  else
  {
    v7 = -1073741275;
  }
  *v5 = v7;
  result = (unsigned int)v7;
  *a3 = 4;
  return result;
}

```

## disassembly

```asm
0x14001d7cc  push    rbx
0x14001d7ce  push    rsi
0x14001d7cf  push    rdi
0x14001d7d0  push    r14
0x14001d7d2  sub     rsp, 28h
0x14001d7d6  cmp     dword ptr [rdx+10h], 8
0x14001d7da  mov     r14, r8
0x14001d7dd  mov     [rsp+48h+P], 0
0x14001d7e6  jb      loc_14001D891
0x14001d7ec  cmp     dword ptr [rdx+8], 4
0x14001d7f0  jb      loc_14001D891
0x14001d7f6  mov     rdi, [rcx+18h]
0x14001d7fa  mov     ecx, [rdi+4]
0x14001d7fd  test    ecx, ecx
0x14001d7ff  jnz     short loc_14001D808
0x14001d801  mov     ebx, 0C0000225h
0x14001d806  jmp     short loc_14001D884
0x14001d808  mov     rdx, [rdx+30h]
0x14001d80c  lea     r8, [rsp+48h+P]
0x14001d811  mov     rdx, [rdx+18h]
0x14001d815  call    PcpRemoveFilterByHandle32
0x14001d81a  mov     ebx, eax
0x14001d81c  test    eax, eax
0x14001d81e  js      short loc_14001D884
0x14001d820  mov     rsi, [rsp+48h+P]
0x14001d825  mov     rcx, cs:PcgWfpEngineHandle; engineHandle
0x14001d82c  lea     rdx, [rsi+10h]; key
0x14001d830  call    cs:__imp_FwpmFilterDeleteByKey0
0x14001d837  nop     dword ptr [rax+rax+00h]
0x14001d83c  mov     ebx, eax
0x14001d83e  test    eax, eax
0x14001d840  jns     short loc_14001D87C
0x14001d842  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d849  lea     rax, WPP_GLOBAL_Control
0x14001d850  cmp     rcx, rax
0x14001d853  jz      short loc_14001D87C
0x14001d855  cmp     byte ptr [rcx+29h], 3
0x14001d859  jb      short loc_14001D87C
0x14001d85b  test    dword ptr [rcx+2Ch], 800h
0x14001d862  jz      short loc_14001D87C
0x14001d864  mov     rcx, [rcx+18h]
0x14001d868  lea     r8, WPP_af99db03d8cf39a69caee5869b1abac6_Traceguids
0x14001d86f  mov     edx, 0Eh
0x14001d874  mov     r9d, ebx
0x14001d877  call    WPP_SF_D
0x14001d87c  mov     rcx, rsi; P
0x14001d87f  call    PcpFreeFilter
0x14001d884  mov     [rdi], ebx
0x14001d886  mov     eax, ebx
0x14001d888  mov     dword ptr [r14], 4
0x14001d88f  jmp     short loc_14001D896
0x14001d891  mov     eax, 0C0000023h
0x14001d896  add     rsp, 28h
0x14001d89a  pop     r14
0x14001d89c  pop     rdi
0x14001d89d  pop     rsi
0x14001d89e  pop     rbx
0x14001d89f  retn
```
