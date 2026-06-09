# DriverSecurityContext::AllocateAndCopySid(CACSecurityContext const *)

- ea: `0x14000e5f4`
- end: `0x14000e709`
- name: `?AllocateAndCopySid@DriverSecurityContext@@AEAA_NPEBVCACSecurityContext@@@Z`
- size: `277`
- prototype: `bool __fastcall(DriverSecurityContext *__hidden this, const struct CACSecurityContext *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000e9a8`

## callees

- `0x1400010a4`
- `0x140001128`
- `0x140001c04`
- `0x140001c34`
- `0x14000e5f4`
- `0x140024cc0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14000e66a`
- `ntoskrnl!ProbeForRead` at `0x14000e66a`

## pseudocode

```c
char __fastcall DriverSecurityContext::AllocateAndCopySid(DriverSecurityContext *this, volatile void **a2)
{
  unsigned __int64 v3; // rbx
  volatile void *v4; // rdi
  void *v6; // rax

  v3 = *((unsigned int *)a2 + 9);
  v4 = *a2;
  if ( !*a2 )
  {
    if ( !(_DWORD)v3 )
      return 1;
    goto LABEL_6;
  }
  if ( !(_DWORD)v3 )
  {
LABEL_6:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 16, WPP_4c6ce2037c62380b46350ba0cf7eb059_Traceguids);
    }
    return 0;
  }
  ProbeForRead(v4, *((unsigned int *)a2 + 9), 1u);
  v6 = operator new(v3, 0x100u, 0x5355514Du, LowPoolPriority);
  *(_QWORD *)this = v6;
  if ( v6 )
  {
    memmove(v6, (const void *)v4, v3);
    *((_DWORD *)this + 9) = v3;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x14000e5f4  mov     [rsp+arg_0], rcx
0x14000e5f9  push    rbx
0x14000e5fa  push    rsi
0x14000e5fb  push    rdi
0x14000e5fc  push    r14
0x14000e5fe  sub     rsp, 28h
0x14000e602  mov     rsi, rcx
0x14000e605  mov     ebx, [rdx+24h]
0x14000e608  mov     rdi, [rdx]
0x14000e60b  test    rdi, rdi
0x14000e60e  jnz     short loc_14000E629
0x14000e610  test    ebx, ebx
0x14000e612  jnz     short loc_14000E61B
0x14000e614  mov     al, 1
0x14000e616  jmp     loc_14000E6FE
0x14000e61b  test    rdi, rdi
0x14000e61e  jnz     short loc_14000E629
0x14000e620  test    ebx, ebx
0x14000e622  jnz     short loc_14000E62D
0x14000e624  test    rdi, rdi
0x14000e627  jz      short loc_14000E65E
0x14000e629  test    ebx, ebx
0x14000e62b  jnz     short loc_14000E65E
0x14000e62d  lea     rax, WPP_GLOBAL_Control
0x14000e634  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e63b  cmp     rcx, rax
0x14000e63e  jz      short loc_14000E694
0x14000e640  mov     eax, [rcx+6Ch]
0x14000e643  test    al, 1
0x14000e645  jz      short loc_14000E694
0x14000e647  mov     edx, 10h
0x14000e64c  lea     r8, WPP_4c6ce2037c62380b46350ba0cf7eb059_Traceguids
0x14000e653  mov     rcx, [rcx+58h]
0x14000e657  call    WPP_SF_
0x14000e65c  jmp     short loc_14000E694
0x14000e65e  mov     r8d, 1; Alignment
0x14000e664  mov     rdx, rbx; Length
0x14000e667  mov     rcx, rdi; Address
0x14000e66a  call    cs:__imp_ProbeForRead
0x14000e671  nop     dword ptr [rax+rax+00h]
0x14000e676  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x14000e679  mov     edx, 100h; unsigned __int64
0x14000e67e  mov     r8d, 5355514Dh; unsigned int
0x14000e684  mov     rcx, rbx; unsigned __int64
0x14000e687  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x14000e68c  mov     [rsi], rax
0x14000e68f  test    rax, rax
0x14000e692  jnz     short loc_14000E698
0x14000e694  xor     al, al
0x14000e696  jmp     short loc_14000E6FE
0x14000e698  mov     r8, rbx; Size
0x14000e69b  mov     rdx, rdi; Src
0x14000e69e  mov     rcx, rax; void *
0x14000e6a1  call    memmove
0x14000e6a6  mov     [rsi+24h], ebx
0x14000e6a9  jmp     loc_14000E614
0x14000e6ae  lea     rdx, WPP_GLOBAL_Control
0x14000e6b5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e6bc  cmp     rcx, rdx
0x14000e6bf  jz      short loc_14000E6E1
0x14000e6c1  mov     edx, [rcx+6Ch]
0x14000e6c4  test    dl, 1
0x14000e6c7  jz      short loc_14000E6E1
0x14000e6c9  mov     r9d, eax
0x14000e6cc  mov     edx, 11h
0x14000e6d1  lea     r8, WPP_4c6ce2037c62380b46350ba0cf7eb059_Traceguids
0x14000e6d8  mov     rcx, [rcx+58h]
0x14000e6dc  call    WPP_SF_d
0x14000e6e1  mov     rbx, [rsp+48h+arg_0]
0x14000e6e6  mov     rcx, [rbx]; void *
0x14000e6e9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000e6ee  mov     qword ptr [rbx], 0
0x14000e6f5  mov     dword ptr [rbx+24h], 0
0x14000e6fc  xor     al, al
0x14000e6fe  add     rsp, 28h
0x14000e702  pop     r14
0x14000e704  pop     rdi
0x14000e705  pop     rsi
0x14000e706  pop     rbx
0x14000e707  retn
```
