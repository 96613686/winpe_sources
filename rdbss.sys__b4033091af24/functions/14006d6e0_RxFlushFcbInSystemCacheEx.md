# RxFlushFcbInSystemCacheEx

- ea: `0x14006d6e0`
- end: `0x14006d7f0`
- name: `RxFlushFcbInSystemCacheEx`
- size: `272`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140044c78`
- `0x140045030`
- `0x1400511d0`
- `0x14006c500`
- `0x14006c5c0`
- `0x1400708e0`

## callees

- `0x140008030`
- `0x140008190`
- `0x140016e70`
- `0x1400241d8`
- `0x14006d6e0`

## import_xrefs

- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14006d76e`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14006d76e`

## pseudocode

```c
__int64 __fastcall RxFlushFcbInSystemCacheEx(__int64 a1, char a2, __int64 a3, int a4)
{
  __int64 v5; // r14
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // esi
  __int128 Parameter; // [rsp+40h] [rbp-68h] BYREF
  __int128 v13; // [rsp+50h] [rbp-58h]
  __int64 v14; // [rsp+60h] [rbp-48h]

  Parameter = 0;
  v14 = 0;
  v13 = 0;
  v5 = a3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_34a45793cf6d31669b6348460c85d061_Traceguids, a1);
  }
  if ( a2 )
  {
    LOBYTE(a3) = 1;
    RxAcquirePagingIoResource(0, a1, a3);
  }
  *(_QWORD *)&Parameter = a1;
  *((_QWORD *)&Parameter + 1) = v5;
  LODWORD(v13) = a4;
  KeExpandKernelStackAndCalloutEx(
    (PEXPAND_STACK_CALLOUT)RxpFlushFcbInSystemCacheCallout,
    &Parameter,
    0x6000u,
    0,
    *(PVOID *)&RxContextLookasideList.L.Depth);
  v10 = DWORD2(v13);
  if ( a2 )
    RxReleasePagingIoResource(0, a1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_LqDi(WPP_GLOBAL_Control->AttachedDevice, v8, v9, v10);
  }
  return v10;
}

```

## disassembly

```asm
0x14006d6e0  push    rbx
0x14006d6e2  push    rbp
0x14006d6e3  push    rsi
0x14006d6e4  push    rdi
0x14006d6e5  push    r14
0x14006d6e7  push    r15
0x14006d6e9  sub     rsp, 78h
0x14006d6ed  xorps   xmm0, xmm0
0x14006d6f0  xor     eax, eax
0x14006d6f2  movups  [rsp+0A8h+Parameter], xmm0
0x14006d6f7  mov     [rsp+0A8h+var_48], rax
0x14006d6fc  mov     ebp, r9d
0x14006d6ff  movups  [rsp+0A8h+var_58], xmm0
0x14006d704  mov     r14, r8
0x14006d707  movzx   edi, dl
0x14006d70a  mov     rbx, rcx
0x14006d70d  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d714  lea     r15, WPP_GLOBAL_Control
0x14006d71b  cmp     rcx, r15
0x14006d71e  jz      short loc_14006D72D
0x14006d720  test    dword ptr [rcx+2Ch], 200h
0x14006d727  jnz     loc_14006D7B2
0x14006d72d  test    dil, dil
0x14006d730  jz      short loc_14006D73F
0x14006d732  mov     r8b, 1
0x14006d735  mov     rdx, rbx
0x14006d738  xor     ecx, ecx
0x14006d73a  call    RxAcquirePagingIoResource
0x14006d73f  mov     rax, qword ptr cs:RxContextLookasideList.L.Depth
0x14006d746  lea     rdx, [rsp+0A8h+Parameter]; Parameter
0x14006d74b  xor     r9d, r9d; Wait
0x14006d74e  mov     [rsp+0A8h+Context], rax; Context
0x14006d753  mov     r8d, 6000h; Size
0x14006d759  mov     qword ptr [rsp+0A8h+Parameter], rbx
0x14006d75e  lea     rcx, RxpFlushFcbInSystemCacheCallout; Callout
0x14006d765  mov     qword ptr [rsp+0A8h+Parameter+8], r14
0x14006d76a  mov     dword ptr [rsp+0A8h+var_58], ebp
0x14006d76e  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14006d775  nop     dword ptr [rax+rax+00h]
0x14006d77a  mov     esi, dword ptr [rsp+0A8h+var_58+8]
0x14006d77e  test    dil, dil
0x14006d781  jz      short loc_14006D78D
0x14006d783  mov     rdx, rbx
0x14006d786  xor     ecx, ecx
0x14006d788  call    RxReleasePagingIoResource
0x14006d78d  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d794  cmp     rcx, r15
0x14006d797  jz      short loc_14006D7A2
0x14006d799  test    dword ptr [rcx+2Ch], 200h
0x14006d7a0  jnz     short loc_14006D7D9
0x14006d7a2  mov     eax, esi
0x14006d7a4  add     rsp, 78h
0x14006d7a8  pop     r15
0x14006d7aa  pop     r14
0x14006d7ac  pop     rdi
0x14006d7ad  pop     rsi
0x14006d7ae  pop     rbp
0x14006d7af  pop     rbx
0x14006d7b0  retn
0x14006d7b2  cmp     byte ptr [rcx+29h], 2
0x14006d7b6  jb      loc_14006D72D
0x14006d7bc  mov     rcx, [rcx+18h]
0x14006d7c0  lea     r8, WPP_34a45793cf6d31669b6348460c85d061_Traceguids
0x14006d7c7  mov     edx, 17h
0x14006d7cc  mov     r9, rbx
0x14006d7cf  call    WPP_SF_q
0x14006d7d4  jmp     loc_14006D72D
0x14006d7d9  cmp     byte ptr [rcx+29h], 4
0x14006d7dd  jb      short loc_14006D7A2
0x14006d7df  test    r14, r14
0x14006d7e2  jz      loc_14007EFE0
0x14006d7e8  mov     rax, [r14]
0x14006d7eb  jmp     loc_14007EFE2
0x14007efe0  xor     eax, eax
0x14007efe2  mov     rcx, [rcx+18h]
0x14007efe6  mov     r9d, esi
0x14007efe9  mov     [rsp+0A8h+var_78], rax
0x14007efee  mov     [rsp+0A8h+var_80], ebp
0x14007eff2  mov     [rsp+0A8h+Context], rbx
0x14007eff7  call    WPP_SF_LqDi
0x14007effc  nop
0x14007effd  jmp     loc_14006D7A2
```
