# DriverSecurityContext::AllocateAndCopyUserCert(void *,ulong)

- ea: `0x14000e710`
- end: `0x14000e82b`
- name: `?AllocateAndCopyUserCert@DriverSecurityContext@@AEAA_NPEAXK@Z`
- size: `283`
- prototype: `bool(DriverSecurityContext *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000e9a8`

## callees

- `0x1400010a4`
- `0x140001128`
- `0x140001c04`
- `0x140001c34`
- `0x14000e710`
- `0x140024cc0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14000e789`
- `ntoskrnl!ProbeForRead` at `0x14000e789`

## pseudocode

```c
char __fastcall DriverSecurityContext::AllocateAndCopyUserCert(DriverSecurityContext *this, void *a2, unsigned int a3)
{
  unsigned __int64 v3; // rbx
  void *v7; // rax

  v3 = a3;
  if ( !a2 && !a3 )
    return 1;
  if ( a2 )
  {
    if ( a3 )
      goto LABEL_11;
LABEL_8:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 20, WPP_4c6ce2037c62380b46350ba0cf7eb059_Traceguids);
    }
    return 0;
  }
  if ( a3 )
    goto LABEL_8;
LABEL_11:
  ProbeForRead(a2, a3, 1u);
  v7 = operator new(v3, 0x100u, 0x4355514Du, LowPoolPriority);
  *((_QWORD *)this + 1) = v7;
  if ( v7 )
  {
    memmove(v7, a2, v3);
    *((_DWORD *)this + 10) = v3;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x14000e710  mov     [rsp+arg_0], rcx
0x14000e715  push    rbx
0x14000e716  push    rsi
0x14000e717  push    rdi
0x14000e718  push    r14
0x14000e71a  sub     rsp, 28h
0x14000e71e  mov     ebx, r8d
0x14000e721  mov     rdi, rdx
0x14000e724  mov     rsi, rcx
0x14000e727  test    rdx, rdx
0x14000e72a  jnz     short loc_14000E738
0x14000e72c  test    r8d, r8d
0x14000e72f  jnz     short loc_14000E738
0x14000e731  mov     al, 1
0x14000e733  jmp     loc_14000E820
0x14000e738  test    rdi, rdi
0x14000e73b  jnz     short loc_14000E747
0x14000e73d  test    r8d, r8d
0x14000e740  jnz     short loc_14000E74C
0x14000e742  test    rdi, rdi
0x14000e745  jz      short loc_14000E77D
0x14000e747  test    r8d, r8d
0x14000e74a  jnz     short loc_14000E77D
0x14000e74c  lea     rax, WPP_GLOBAL_Control
0x14000e753  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e75a  cmp     rcx, rax
0x14000e75d  jz      short loc_14000E7B4
0x14000e75f  mov     eax, [rcx+6Ch]
0x14000e762  test    al, 1
0x14000e764  jz      short loc_14000E7B4
0x14000e766  mov     edx, 14h
0x14000e76b  lea     r8, WPP_4c6ce2037c62380b46350ba0cf7eb059_Traceguids
0x14000e772  mov     rcx, [rcx+58h]
0x14000e776  call    WPP_SF_
0x14000e77b  jmp     short loc_14000E7B4
0x14000e77d  mov     r8d, 1; Alignment
0x14000e783  mov     rdx, rbx; Length
0x14000e786  mov     rcx, rdi; Address
0x14000e789  call    cs:__imp_ProbeForRead
0x14000e790  nop     dword ptr [rax+rax+00h]
0x14000e795  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x14000e798  mov     edx, 100h; unsigned __int64
0x14000e79d  mov     r8d, 4355514Dh; unsigned int
0x14000e7a3  mov     rcx, rbx; unsigned __int64
0x14000e7a6  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x14000e7ab  mov     [rsi+8], rax
0x14000e7af  test    rax, rax
0x14000e7b2  jnz     short loc_14000E7B8
0x14000e7b4  xor     al, al
0x14000e7b6  jmp     short loc_14000E820
0x14000e7b8  mov     r8, rbx; Size
0x14000e7bb  mov     rdx, rdi; Src
0x14000e7be  mov     rcx, rax; void *
0x14000e7c1  call    memmove
0x14000e7c6  mov     [rsi+28h], ebx
0x14000e7c9  jmp     loc_14000E731
0x14000e7ce  lea     rdx, WPP_GLOBAL_Control
0x14000e7d5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e7dc  cmp     rcx, rdx
0x14000e7df  jz      short loc_14000E801
0x14000e7e1  mov     edx, [rcx+6Ch]
0x14000e7e4  test    dl, 1
0x14000e7e7  jz      short loc_14000E801
0x14000e7e9  mov     r9d, eax
0x14000e7ec  mov     edx, 15h
0x14000e7f1  lea     r8, WPP_4c6ce2037c62380b46350ba0cf7eb059_Traceguids
0x14000e7f8  mov     rcx, [rcx+58h]
0x14000e7fc  call    WPP_SF_d
0x14000e801  mov     rbx, [rsp+48h+arg_0]
0x14000e806  mov     rcx, [rbx+8]; void *
0x14000e80a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000e80f  mov     qword ptr [rbx+8], 0
0x14000e817  mov     dword ptr [rbx+28h], 0
0x14000e81e  xor     al, al
0x14000e820  add     rsp, 28h
0x14000e824  pop     r14
0x14000e826  pop     rdi
0x14000e827  pop     rsi
0x14000e828  pop     rbx
0x14000e829  retn
```
