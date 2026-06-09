# MupReleaseFileContext

- ea: `0x14001cbd0`
- end: `0x14001cd41`
- name: `MupReleaseFileContext`
- size: `369`
- prototype: `void __fastcall(char *P)`
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x140019598`
- `0x14001a128`
- `0x14001a3c0`
- `0x14001a920`
- `0x14001c350`

## callees

- `0x140001c90`
- `0x140002700`
- `0x140002754`
- `0x14001c6e0`
- `0x14001c7b0`
- `0x14001c8c0`
- `0x14001cbd0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001cca6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cd30`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cca6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cd30`

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
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids, P);
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
    MupCleanupUncHardeningFileContext(P + 248);
    ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x14001cbd0  mov     [rsp+arg_8], rbx
0x14001cbd5  push    rdi
0x14001cbd6  sub     rsp, 30h
0x14001cbda  mov     rbx, rcx
0x14001cbdd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cbe4  lea     rdi, WPP_GLOBAL_Control
0x14001cbeb  cmp     rcx, rdi
0x14001cbee  jz      short loc_14001CBFD
0x14001cbf0  test    dword ptr [rcx+2Ch], 4000000h
0x14001cbf7  jnz     loc_14001CCD7
0x14001cbfd  mov     eax, 0FFFFFFFFh
0x14001cc02  lock xadd [rbx+4], eax
0x14001cc07  cmp     eax, 1
0x14001cc0a  jnz     loc_14001CCB2
0x14001cc10  mov     [rsp+38h+arg_0], rsi
0x14001cc15  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cc1c  cmp     rcx, rdi
0x14001cc1f  jz      short loc_14001CC2E
0x14001cc21  test    dword ptr [rcx+2Ch], 4000000h
0x14001cc28  jnz     loc_14001CCFD
0x14001cc2e  lea     rdi, [rbx+0C8h]
0x14001cc35  mov     rsi, [rdi]
0x14001cc38  cmp     rsi, rdi
0x14001cc3b  jnz     loc_14001CCC0
0x14001cc41  mov     rcx, [rbx+0A8h]
0x14001cc48  mov     rsi, [rsp+38h+arg_0]
0x14001cc4d  test    rcx, rcx
0x14001cc50  jz      short loc_14001CC57
0x14001cc52  call    MupReleaseUncProvider
0x14001cc57  mov     rcx, [rbx+0B8h]; P
0x14001cc5e  test    rcx, rcx
0x14001cc61  jz      short loc_14001CC68
0x14001cc63  call    MupReleaseSurrogateProvider
0x14001cc68  mov     rcx, [rbx+0B0h]
0x14001cc6f  test    rcx, rcx
0x14001cc72  jnz     loc_14001CD1A
0x14001cc78  mov     rcx, [rbx+0C0h]; P
0x14001cc7f  test    rcx, rcx
0x14001cc82  jnz     loc_14001CD24
0x14001cc88  mov     rcx, [rbx+58h]; P
0x14001cc8c  test    rcx, rcx
0x14001cc8f  jnz     loc_14001CD2E
0x14001cc95  lea     rcx, [rbx+0F8h]
0x14001cc9c  call    MupCleanupUncHardeningFileContext
0x14001cca1  xor     edx, edx; Tag
0x14001cca3  mov     rcx, rbx; P
0x14001cca6  call    cs:__imp_ExFreePoolWithTag
0x14001ccad  nop     dword ptr [rax+rax+00h]
0x14001ccb2  mov     rbx, [rsp+38h+arg_8]
0x14001ccb7  add     rsp, 30h
0x14001ccbb  pop     rdi
0x14001ccbc  retn
0x14001ccc0  lea     rcx, [rsi-8]; P
0x14001ccc4  mov     rsi, [rsi]
0x14001ccc7  call    MupReleaseSurrogateFileContext
0x14001cccc  cmp     rsi, rdi
0x14001cccf  jz      loc_14001CC41
0x14001ccd5  jmp     short loc_14001CCC0
0x14001ccd7  mov     r9, [rbx+90h]
0x14001ccde  lea     r8, WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids
0x14001cce5  mov     rcx, [rcx+18h]
0x14001cce9  mov     edx, 0Ah
0x14001ccee  mov     [rsp+38h+var_18], rbx
0x14001ccf3  call    WPP_SF_qq
0x14001ccf8  jmp     loc_14001CBFD
0x14001ccfd  mov     rcx, [rcx+18h]
0x14001cd01  lea     r8, WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids
0x14001cd08  mov     edx, 0Bh
0x14001cd0d  mov     r9, rbx
0x14001cd10  call    WPP_SF_q
0x14001cd15  jmp     loc_14001CC2E
0x14001cd1a  call    MupReleaseUncProvider
0x14001cd1f  jmp     loc_14001CC78
0x14001cd24  call    MupReleaseSurrogateProvider
0x14001cd29  jmp     loc_14001CC88
0x14001cd2e  xor     edx, edx; Tag
0x14001cd30  call    cs:__imp_ExFreePoolWithTag
0x14001cd37  nop     dword ptr [rax+rax+00h]
0x14001cd3c  jmp     loc_14001CC95
```
