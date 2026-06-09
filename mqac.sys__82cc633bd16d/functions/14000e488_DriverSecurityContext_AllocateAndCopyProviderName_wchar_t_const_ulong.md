# DriverSecurityContext::AllocateAndCopyProviderName(wchar_t const *,ulong)

- ea: `0x14000e488`
- end: `0x14000e5ee`
- name: `?AllocateAndCopyProviderName@DriverSecurityContext@@AEAA_NPEB_WK@Z`
- size: `358`
- prototype: `bool(DriverSecurityContext *__hidden this, const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000e9a8`

## callees

- `0x1400010a4`
- `0x140001128`
- `0x140001c04`
- `0x140001c34`
- `0x140007684`
- `0x14000e488`
- `0x140024cc0`

## pseudocode

```c
char __fastcall DriverSecurityContext::AllocateAndCopyProviderName(
        DriverSecurityContext *this,
        wchar_t *a2,
        unsigned int a3)
{
  unsigned __int64 v3; // rdi
  unsigned __int64 v7; // rax
  void *v8; // rax

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
      WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 18, WPP_4c6ce2037c62380b46350ba0cf7eb059_Traceguids);
    }
    return 0;
  }
  if ( a3 )
    goto LABEL_8;
LABEL_11:
  ACProbeArrayElementsForRead(a2, 2u, a3);
  v7 = 2 * v3;
  if ( !is_mul_ok(v3, 2u) )
    v7 = -1;
  v8 = operator new(v7, 0x100u, 0x4E50514Du, LowPoolPriority);
  *((_QWORD *)this + 2) = v8;
  if ( !v8 )
    return 0;
  memmove(v8, a2, 2 * v3);
  *((_DWORD *)this + 11) = v3;
  *(_WORD *)(*((_QWORD *)this + 2) + 2LL * (unsigned int)(v3 - 1)) = 0;
  return 1;
}

```

## disassembly

```asm
0x14000e488  mov     [rsp+arg_10], rbx
0x14000e48d  mov     [rsp+arg_18], rsi
0x14000e492  mov     [rsp+arg_0], rcx
0x14000e497  push    rdi
0x14000e498  push    r12
0x14000e49a  push    r13
0x14000e49c  push    r14
0x14000e49e  push    r15
0x14000e4a0  sub     rsp, 20h
0x14000e4a4  mov     edi, r8d
0x14000e4a7  mov     rsi, rdx
0x14000e4aa  mov     r14, rcx
0x14000e4ad  xor     ebx, ebx
0x14000e4af  test    rdx, rdx
0x14000e4b2  jnz     short loc_14000E4C0
0x14000e4b4  test    r8d, r8d
0x14000e4b7  jnz     short loc_14000E4C0
0x14000e4b9  mov     al, 1
0x14000e4bb  jmp     loc_14000E5D5
0x14000e4c0  test    rsi, rsi
0x14000e4c3  jnz     short loc_14000E4CF
0x14000e4c5  test    r8d, r8d
0x14000e4c8  jnz     short loc_14000E4D4
0x14000e4ca  test    rsi, rsi
0x14000e4cd  jz      short loc_14000E505
0x14000e4cf  test    r8d, r8d
0x14000e4d2  jnz     short loc_14000E505
0x14000e4d4  lea     rax, WPP_GLOBAL_Control
0x14000e4db  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e4e2  cmp     rcx, rax
0x14000e4e5  jz      short loc_14000E54E
0x14000e4e7  mov     eax, [rcx+6Ch]
0x14000e4ea  test    al, 1
0x14000e4ec  jz      short loc_14000E54E
0x14000e4ee  mov     edx, 12h
0x14000e4f3  lea     r8, WPP_4c6ce2037c62380b46350ba0cf7eb059_Traceguids
0x14000e4fa  mov     rcx, [rcx+58h]
0x14000e4fe  call    WPP_SF_
0x14000e503  jmp     short loc_14000E54E
0x14000e505  mov     r8d, edi; unsigned int
0x14000e508  mov     r15d, 2
0x14000e50e  mov     edx, r15d; unsigned int
0x14000e511  mov     rcx, rsi; void *
0x14000e514  call    ?ACProbeArrayElementsForRead@@YAXPEAXKK@Z; ACProbeArrayElementsForRead(void *,ulong,ulong)
0x14000e519  mov     eax, r15d
0x14000e51c  mul     rdi
0x14000e51f  lea     rcx, [r15-3]
0x14000e523  cmovb   rax, rcx
0x14000e527  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x14000e52a  mov     edx, 100h; unsigned __int64
0x14000e52f  mov     r8d, 4E50514Dh; unsigned int
0x14000e535  mov     rcx, rax; unsigned __int64
0x14000e538  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x14000e53d  lea     r15, [r14+10h]
0x14000e541  mov     [rsp+48h+arg_8], r15
0x14000e546  mov     [r15], rax
0x14000e549  test    rax, rax
0x14000e54c  jnz     short loc_14000E555
0x14000e54e  xor     al, al
0x14000e550  jmp     loc_14000E5D5
0x14000e555  mov     r12b, 1
0x14000e558  lea     r8, ds:0[rdi*2]; Size
0x14000e560  mov     rdx, rsi; Src
0x14000e563  mov     rcx, rax; void *
0x14000e566  call    memmove
0x14000e56b  mov     [r14+2Ch], edi
0x14000e56f  lea     ecx, [rdi-1]
0x14000e572  mov     rax, [r15]
0x14000e575  mov     [rax+rcx*2], bx
0x14000e579  jmp     short loc_14000E5BD
0x14000e57b  lea     rdx, WPP_GLOBAL_Control
0x14000e582  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e589  cmp     rcx, rdx
0x14000e58c  jz      short loc_14000E5AE
0x14000e58e  mov     edx, [rcx+6Ch]
0x14000e591  test    dl, 1
0x14000e594  jz      short loc_14000E5AE
0x14000e596  mov     r9d, eax
0x14000e599  mov     edx, 13h
0x14000e59e  lea     r8, WPP_4c6ce2037c62380b46350ba0cf7eb059_Traceguids
0x14000e5a5  mov     rcx, [rcx+58h]
0x14000e5a9  call    WPP_SF_d
0x14000e5ae  xor     r12b, r12b
0x14000e5b1  xor     ebx, ebx
0x14000e5b3  mov     r14, [rsp+48h+arg_0]
0x14000e5b8  mov     r15, [rsp+48h+arg_8]
0x14000e5bd  cmp     r12b, 1
0x14000e5c1  jz      short loc_14000E5D2
0x14000e5c3  mov     rcx, [r15]; void *
0x14000e5c6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000e5cb  mov     [r15], rbx
0x14000e5ce  mov     [r14+2Ch], ebx
0x14000e5d2  mov     al, r12b
0x14000e5d5  mov     rbx, [rsp+48h+arg_10]
0x14000e5da  mov     rsi, [rsp+48h+arg_18]
0x14000e5df  add     rsp, 20h
0x14000e5e3  pop     r15
0x14000e5e5  pop     r14
0x14000e5e7  pop     r13
0x14000e5e9  pop     r12
0x14000e5eb  pop     rdi
0x14000e5ec  retn
```
