# MupReleaseFileContext

- ea: `0x14001cb80`
- end: `0x14001ccf1`
- name: `MupReleaseFileContext`
- size: `369`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x140019548`
- `0x14001a0d8`
- `0x14001a370`
- `0x14001a8d0`
- `0x14001c300`

## callees

- `0x140001c90`
- `0x140002700`
- `0x140002754`
- `0x14001c690`
- `0x14001c760`
- `0x14001c870`
- `0x14001cb80`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001cc56`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cce0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cc56`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cce0`

## pseudocode

```c
void __fastcall MupReleaseFileContext(char *P)
{
  char *v2; // rsi
  __int64 v3; // rcx
  void *v4; // rcx
  __int64 v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  char *v8; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids,
      *((_QWORD *)P + 18),
      P);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)P + 1, 0xFFFFFFFF) == 1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
    {
      WPP_SF_q(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0xBu,
        (__int64)WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids,
        P);
    }
    v2 = (char *)*((_QWORD *)P + 25);
    while ( v2 != P + 200 )
    {
      v8 = v2 - 8;
      v2 = *(char **)v2;
      MupReleaseSurrogateFileContext(v8);
    }
    v3 = *((_QWORD *)P + 21);
    if ( v3 )
      MupReleaseUncProvider(v3);
    v4 = (void *)*((_QWORD *)P + 23);
    if ( v4 )
      MupReleaseSurrogateProvider(v4);
    v5 = *((_QWORD *)P + 22);
    if ( v5 )
      MupReleaseUncProvider(v5);
    v6 = (void *)*((_QWORD *)P + 24);
    if ( v6 )
      MupReleaseSurrogateProvider(v6);
    v7 = (void *)*((_QWORD *)P + 11);
    if ( v7 )
      ExFreePoolWithTag(v7, 0);
    MupCleanupUncHardeningFileContext((__int64 *)P + 31);
    ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x14001cb80  mov     [rsp+arg_8], rbx
0x14001cb85  push    rdi
0x14001cb86  sub     rsp, 30h
0x14001cb8a  mov     rbx, rcx
0x14001cb8d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cb94  lea     rdi, WPP_GLOBAL_Control
0x14001cb9b  cmp     rcx, rdi
0x14001cb9e  jz      short loc_14001CBAD
0x14001cba0  test    dword ptr [rcx+2Ch], 4000000h
0x14001cba7  jnz     loc_14001CC87
0x14001cbad  mov     eax, 0FFFFFFFFh
0x14001cbb2  lock xadd [rbx+4], eax
0x14001cbb7  cmp     eax, 1
0x14001cbba  jnz     loc_14001CC62
0x14001cbc0  mov     [rsp+38h+arg_0], rsi
0x14001cbc5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cbcc  cmp     rcx, rdi
0x14001cbcf  jz      short loc_14001CBDE
0x14001cbd1  test    dword ptr [rcx+2Ch], 4000000h
0x14001cbd8  jnz     loc_14001CCAD
0x14001cbde  lea     rdi, [rbx+0C8h]
0x14001cbe5  mov     rsi, [rdi]
0x14001cbe8  cmp     rsi, rdi
0x14001cbeb  jnz     loc_14001CC70
0x14001cbf1  mov     rcx, [rbx+0A8h]
0x14001cbf8  mov     rsi, [rsp+38h+arg_0]
0x14001cbfd  test    rcx, rcx
0x14001cc00  jz      short loc_14001CC07
0x14001cc02  call    MupReleaseUncProvider
0x14001cc07  mov     rcx, [rbx+0B8h]; P
0x14001cc0e  test    rcx, rcx
0x14001cc11  jz      short loc_14001CC18
0x14001cc13  call    MupReleaseSurrogateProvider
0x14001cc18  mov     rcx, [rbx+0B0h]
0x14001cc1f  test    rcx, rcx
0x14001cc22  jnz     loc_14001CCCA
0x14001cc28  mov     rcx, [rbx+0C0h]; P
0x14001cc2f  test    rcx, rcx
0x14001cc32  jnz     loc_14001CCD4
0x14001cc38  mov     rcx, [rbx+58h]; P
0x14001cc3c  test    rcx, rcx
0x14001cc3f  jnz     loc_14001CCDE
0x14001cc45  lea     rcx, [rbx+0F8h]
0x14001cc4c  call    MupCleanupUncHardeningFileContext
0x14001cc51  xor     edx, edx; Tag
0x14001cc53  mov     rcx, rbx; P
0x14001cc56  call    cs:__imp_ExFreePoolWithTag
0x14001cc5d  nop     dword ptr [rax+rax+00h]
0x14001cc62  mov     rbx, [rsp+38h+arg_8]
0x14001cc67  add     rsp, 30h
0x14001cc6b  pop     rdi
0x14001cc6c  retn
0x14001cc70  lea     rcx, [rsi-8]; P
0x14001cc74  mov     rsi, [rsi]
0x14001cc77  call    MupReleaseSurrogateFileContext
0x14001cc7c  cmp     rsi, rdi
0x14001cc7f  jz      loc_14001CBF1
0x14001cc85  jmp     short loc_14001CC70
0x14001cc87  mov     r9, [rbx+90h]
0x14001cc8e  lea     r8, WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids
0x14001cc95  mov     rcx, [rcx+18h]
0x14001cc99  mov     edx, 0Ah
0x14001cc9e  mov     [rsp+38h+var_18], rbx
0x14001cca3  call    WPP_SF_qq
0x14001cca8  jmp     loc_14001CBAD
0x14001ccad  mov     rcx, [rcx+18h]
0x14001ccb1  lea     r8, WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids
0x14001ccb8  mov     edx, 0Bh
0x14001ccbd  mov     r9, rbx
0x14001ccc0  call    WPP_SF_q
0x14001ccc5  jmp     loc_14001CBDE
0x14001ccca  call    MupReleaseUncProvider
0x14001cccf  jmp     loc_14001CC28
0x14001ccd4  call    MupReleaseSurrogateProvider
0x14001ccd9  jmp     loc_14001CC38
0x14001ccde  xor     edx, edx; Tag
0x14001cce0  call    cs:__imp_ExFreePoolWithTag
0x14001cce7  nop     dword ptr [rax+rax+00h]
0x14001ccec  jmp     loc_14001CC45
```
