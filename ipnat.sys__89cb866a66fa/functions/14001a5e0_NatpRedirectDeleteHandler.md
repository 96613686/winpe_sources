# NatpRedirectDeleteHandler

- ea: `0x14001a5e0`
- end: `0x14001a754`
- name: `NatpRedirectDeleteHandler`
- size: `372`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x14000218c`
- `0x14000f134`
- `0x140019cec`
- `0x14001a5e0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001a644`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001a644`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001a6ba`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001a6ba`

## pseudocode

```c
void __fastcall NatpRedirectDeleteHandler(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v6; // rcx
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 102, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids);
  }
  if ( !a3 || a4 == 3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 103, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        v8 = 104;
        goto LABEL_21;
      }
    }
  }
  else
  {
    KeAcquireSpinLockAtDpcLevel(&RedirectLock);
    v6 = *(_QWORD *)(a3 + 152);
    if ( v6 )
    {
      NatQueryInformationMapping(v6, 0, 0, 0, 0, 0, 0, 0, a3 + 160);
      *(_QWORD *)(a3 + 152) = 0;
    }
    *(_DWORD *)(a3 + 112) &= ~0x20000000u;
    NatpCleanupRedirect((char *)a3, 0);
    KeReleaseSpinLockFromDpcLevel(&RedirectLock);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      v8 = 105;
LABEL_21:
      WPP_SF_(v7->AttachedDevice, v8, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x14001a5e0  mov     [rsp+arg_0], rbx
0x14001a5e5  mov     [rsp+arg_8], rdi
0x14001a5ea  push    r12
0x14001a5ec  sub     rsp, 50h
0x14001a5f0  mov     edi, r9d
0x14001a5f3  mov     rbx, r8
0x14001a5f6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a5fd  lea     r12, WPP_GLOBAL_Control
0x14001a604  cmp     rcx, r12
0x14001a607  jz      short loc_14001A62B
0x14001a609  mov     eax, [rcx+2Ch]
0x14001a60c  test    al, 1
0x14001a60e  jz      short loc_14001A62B
0x14001a610  cmp     byte ptr [rcx+29h], 6
0x14001a614  jb      short loc_14001A62B
0x14001a616  mov     rcx, [rcx+18h]
0x14001a61a  lea     r8, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids
0x14001a621  mov     edx, 66h ; 'f'
0x14001a626  call    WPP_SF_
0x14001a62b  test    rbx, rbx
0x14001a62e  jz      loc_14001A6E6
0x14001a634  cmp     edi, 3
0x14001a637  jz      loc_14001A6E6
0x14001a63d  lea     rcx, RedirectLock; SpinLock
0x14001a644  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001a64b  nop     dword ptr [rax+rax+00h]
0x14001a650  mov     rcx, [rbx+98h]
0x14001a657  test    rcx, rcx
0x14001a65a  jz      short loc_14001A6A4
0x14001a65c  lea     rax, [rbx+0A0h]
0x14001a663  xor     r9d, r9d
0x14001a666  mov     [rsp+58h+var_18], rax
0x14001a66b  xor     r8d, r8d
0x14001a66e  mov     [rsp+58h+var_20], 0
0x14001a677  xor     edx, edx
0x14001a679  mov     [rsp+58h+var_28], 0
0x14001a682  mov     [rsp+58h+var_30], 0
0x14001a68b  mov     [rsp+58h+var_38], 0
0x14001a694  call    NatQueryInformationMapping
0x14001a699  mov     qword ptr [rbx+98h], 0
0x14001a6a4  btr     dword ptr [rbx+70h], 1Dh
0x14001a6a9  xor     edx, edx
0x14001a6ab  mov     rcx, rbx; P
0x14001a6ae  call    NatpCleanupRedirect
0x14001a6b3  lea     rcx, RedirectLock; SpinLock
0x14001a6ba  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001a6c1  nop     dword ptr [rax+rax+00h]
0x14001a6c6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a6cd  cmp     rcx, r12
0x14001a6d0  jz      short loc_14001A742
0x14001a6d2  mov     eax, [rcx+2Ch]
0x14001a6d5  test    al, 1
0x14001a6d7  jz      short loc_14001A742
0x14001a6d9  cmp     byte ptr [rcx+29h], 6
0x14001a6dd  jb      short loc_14001A742
0x14001a6df  mov     edx, 69h ; 'i'
0x14001a6e4  jmp     short loc_14001A732
0x14001a6e6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a6ed  cmp     rcx, r12
0x14001a6f0  jz      short loc_14001A742
0x14001a6f2  mov     eax, [rcx+2Ch]
0x14001a6f5  test    al, 1
0x14001a6f7  jz      short loc_14001A714
0x14001a6f9  cmp     byte ptr [rcx+29h], 2
0x14001a6fd  jb      short loc_14001A714
0x14001a6ff  mov     rcx, [rcx+18h]
0x14001a703  lea     r8, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids
0x14001a70a  mov     edx, 67h ; 'g'
0x14001a70f  call    WPP_SF_
0x14001a714  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a71b  cmp     rcx, r12
0x14001a71e  jz      short loc_14001A742
0x14001a720  mov     eax, [rcx+2Ch]
0x14001a723  test    al, 1
0x14001a725  jz      short loc_14001A742
0x14001a727  cmp     byte ptr [rcx+29h], 6
0x14001a72b  jb      short loc_14001A742
0x14001a72d  mov     edx, 68h ; 'h'
0x14001a732  mov     rcx, [rcx+18h]
0x14001a736  lea     r8, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids
0x14001a73d  call    WPP_SF_
0x14001a742  mov     rbx, [rsp+58h+arg_0]
0x14001a747  mov     rdi, [rsp+58h+arg_8]
0x14001a74c  add     rsp, 50h
0x14001a750  pop     r12
0x14001a752  retn
```
