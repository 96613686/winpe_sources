# RxFlushFcbInSystemCache

- ea: `0x140071700`
- end: `0x140071816`
- name: `RxFlushFcbInSystemCache`
- size: `278`
- prototype: `NTSTATUS __stdcall(PFCB Fcb, BOOLEAN SynchronizeWithLazyWriter)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140004180`
- `0x14000f690`

## callees

- `0x140008030`
- `0x140008190`
- `0x140016e70`
- `0x1400241d8`
- `0x140071700`

## import_xrefs

- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14007178a`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14007178a`

## pseudocode

```c
NTSTATUS __stdcall RxFlushFcbInSystemCache(PFCB Fcb, BOOLEAN SynchronizeWithLazyWriter)
{
  __int64 v2; // r8
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned int v7; // esi
  __int128 Parameter; // [rsp+40h] [rbp-58h] BYREF
  __int128 v10; // [rsp+50h] [rbp-48h]
  __int64 v11; // [rsp+60h] [rbp-38h]

  Parameter = 0;
  v11 = 0;
  v10 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 23, &WPP_34a45793cf6d31669b6348460c85d061_Traceguids, Fcb);
  }
  if ( SynchronizeWithLazyWriter )
  {
    LOBYTE(v2) = 1;
    RxAcquirePagingIoResource(0, Fcb, v2);
  }
  LODWORD(v10) = 0;
  Parameter = (unsigned __int64)Fcb;
  KeExpandKernelStackAndCalloutEx(
    (PEXPAND_STACK_CALLOUT)RxpFlushFcbInSystemCacheCallout,
    &Parameter,
    0x6000u,
    0,
    *(PVOID *)&RxContextLookasideList.L.Depth);
  v7 = DWORD2(v10);
  if ( SynchronizeWithLazyWriter )
    RxReleasePagingIoResource(0, Fcb);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_LqDi(WPP_GLOBAL_Control->AttachedDevice, v5, v6, v7);
  }
  return v7;
}

```

## disassembly

```asm
0x140071700  push    rbx
0x140071702  push    rbp
0x140071703  push    rsi
0x140071704  push    rdi
0x140071705  push    r14
0x140071707  sub     rsp, 70h
0x14007170b  xorps   xmm0, xmm0
0x14007170e  xor     eax, eax
0x140071710  movups  [rsp+98h+Parameter], xmm0
0x140071715  mov     [rsp+98h+var_38], rax
0x14007171a  movzx   edi, dl
0x14007171d  movups  [rsp+98h+var_48], xmm0
0x140071722  mov     rbx, rcx
0x140071725  mov     rcx, cs:WPP_GLOBAL_Control
0x14007172c  lea     rbp, WPP_GLOBAL_Control
0x140071733  cmp     rcx, rbp
0x140071736  jz      short loc_140071745
0x140071738  test    dword ptr [rcx+2Ch], 200h
0x14007173f  jnz     loc_1400717CC
0x140071745  test    dil, dil
0x140071748  jz      short loc_140071757
0x14007174a  mov     r8b, 1
0x14007174d  mov     rdx, rbx
0x140071750  xor     ecx, ecx
0x140071752  call    RxAcquirePagingIoResource
0x140071757  mov     rax, qword ptr cs:RxContextLookasideList.L.Depth
0x14007175e  lea     rdx, [rsp+98h+Parameter]; Parameter
0x140071763  xor     r14d, r14d
0x140071766  mov     [rsp+98h+Context], rax; Context
0x14007176b  xor     r9d, r9d; Wait
0x14007176e  mov     qword ptr [rsp+98h+Parameter+8], r14
0x140071773  mov     r8d, 6000h; Size
0x140071779  mov     dword ptr [rsp+98h+var_48], r14d
0x14007177e  lea     rcx, RxpFlushFcbInSystemCacheCallout; Callout
0x140071785  mov     qword ptr [rsp+98h+Parameter], rbx
0x14007178a  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x140071791  nop     dword ptr [rax+rax+00h]
0x140071796  mov     esi, dword ptr [rsp+98h+var_48+8]
0x14007179a  test    dil, dil
0x14007179d  jz      short loc_1400717A9
0x14007179f  mov     rdx, rbx
0x1400717a2  xor     ecx, ecx
0x1400717a4  call    RxReleasePagingIoResource
0x1400717a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400717b0  cmp     rcx, rbp
0x1400717b3  jz      short loc_1400717BE
0x1400717b5  test    dword ptr [rcx+2Ch], 200h
0x1400717bc  jnz     short loc_1400717F3
0x1400717be  mov     eax, esi
0x1400717c0  add     rsp, 70h
0x1400717c4  pop     r14
0x1400717c6  pop     rdi
0x1400717c7  pop     rsi
0x1400717c8  pop     rbp
0x1400717c9  pop     rbx
0x1400717ca  retn
0x1400717cc  cmp     byte ptr [rcx+29h], 2
0x1400717d0  jb      loc_140071745
0x1400717d6  mov     rcx, [rcx+18h]
0x1400717da  lea     r8, WPP_34a45793cf6d31669b6348460c85d061_Traceguids
0x1400717e1  mov     edx, 17h
0x1400717e6  mov     r9, rbx
0x1400717e9  call    WPP_SF_q
0x1400717ee  jmp     loc_140071745
0x1400717f3  cmp     byte ptr [rcx+29h], 4
0x1400717f7  jb      short loc_1400717BE
0x1400717f9  mov     rcx, [rcx+18h]
0x1400717fd  mov     r9d, esi
0x140071800  mov     [rsp+98h+var_68], r14
0x140071805  mov     [rsp+98h+var_70], r14d
0x14007180a  mov     [rsp+98h+Context], rbx
0x14007180f  call    WPP_SF_LqDi
0x140071814  jmp     short loc_1400717BE
```
