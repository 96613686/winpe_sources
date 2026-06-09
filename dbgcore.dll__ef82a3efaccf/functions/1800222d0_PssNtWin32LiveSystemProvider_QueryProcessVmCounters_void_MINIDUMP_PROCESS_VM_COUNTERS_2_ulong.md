# PssNtWin32LiveSystemProvider::QueryProcessVmCounters(void *,_MINIDUMP_PROCESS_VM_COUNTERS_2 *,ulong)

- ea: `0x1800222d0`
- end: `0x180022537`
- name: `?QueryProcessVmCounters@PssNtWin32LiveSystemProvider@@UEAAJPEAXPEAU_MINIDUMP_PROCESS_VM_COUNTERS_2@@K@Z`
- size: `615`
- prototype: `__int64 __fastcall(PssNtWin32LiveSystemProvider *__hidden this, void *, struct _MINIDUMP_PROCESS_VM_COUNTERS_2 *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x180003430`
- `0x1800222d0`
- `0x180025b00`
- `0x18002c010`

## pseudocode

```c
int __fastcall PssNtWin32LiveSystemProvider::QueryProcessVmCounters(
        PssNtWin32LiveSystemProvider *this,
        void *a2,
        struct _MINIDUMP_PROCESS_VM_COUNTERS_2 *a3,
        unsigned int a4)
{
  int v7; // eax
  USHORT Flags; // cx
  ULONG64 v9; // rax
  ULONG64 v10; // [rsp+30h] [rbp-D0h] BYREF
  ULONG64 v11; // [rsp+38h] [rbp-C8h]
  ULONG v12; // [rsp+40h] [rbp-C0h]
  int v13; // [rsp+44h] [rbp-BCh]
  ULONG64 v14; // [rsp+48h] [rbp-B8h]
  ULONG64 v15; // [rsp+50h] [rbp-B0h]
  ULONG64 v16; // [rsp+58h] [rbp-A8h]
  ULONG64 v17; // [rsp+60h] [rbp-A0h]
  ULONG64 v18; // [rsp+68h] [rbp-98h]
  ULONG64 v19; // [rsp+70h] [rbp-90h]
  ULONG64 v20; // [rsp+78h] [rbp-88h]
  _QWORD Src[78]; // [rsp+80h] [rbp-80h] BYREF

  if ( *((void **)this + 153) != a2 )
    return NtWin32LiveSystemProvider::QueryProcessVmCounters(this, a2, a3, a4);
  if ( a4 != 152 )
    return -2147024872;
  memset_0(&v10, 0, 0x2C0u);
  memset_0(&a3->PageFaultCount, 0, 0x94u);
  *(_DWORD *)&a3->Revision = 983042;
  v7 = (*((__int64 (__fastcall **)(_QWORD, __int64, ULONG64 *, __int64))this + 142))(
         *((_QWORD *)this + 153),
         8,
         &v10,
         112);
  if ( v7 == 24 )
  {
    a3->Flags &= ~8u;
    v7 = (*((__int64 (__fastcall **)(_QWORD, __int64, ULONG64 *, __int64))this + 142))(
           *((_QWORD *)this + 153),
           8,
           &v10,
           96);
    if ( v7 == 24 )
    {
      a3->Flags &= ~4u;
      v7 = (*((__int64 (__fastcall **)(_QWORD, __int64, ULONG64 *, __int64))this + 142))(
             *((_QWORD *)this + 153),
             8,
             &v10,
             88);
    }
  }
  if ( v7 )
  {
    a3->Flags &= 0xFFFCu;
    if ( !(*((unsigned int (__fastcall **)(_QWORD, _QWORD, ULONG64 *, __int64))this + 142))(
            *((_QWORD *)this + 153),
            0,
            &v10,
            704) )
    {
      a3->Flags = 7;
      memmove_0(&v10, Src, 0x70u);
    }
  }
  Flags = a3->Flags;
  if ( (Flags & 1) != 0 )
  {
    a3->PageFaultCount = v12;
    a3->PeakWorkingSetSize = v14;
    a3->WorkingSetSize = v15;
    a3->QuotaPeakPagedPoolUsage = v16;
    a3->QuotaPagedPoolUsage = v17;
    a3->QuotaPeakNonPagedPoolUsage = v18;
    a3->QuotaNonPagedPoolUsage = v19;
    a3->PagefileUsage = v20;
    a3->PeakPagefileUsage = Src[0];
  }
  if ( (Flags & 2) != 0 )
  {
    a3->PeakVirtualSize = v10;
    a3->VirtualSize = v11;
  }
  if ( (Flags & 4) != 0 )
    a3->PrivateUsage = Src[1];
  if ( (Flags & 8) != 0 )
  {
    a3->PrivateWorkingSetSize = Src[2];
    a3->SharedCommitUsage = Src[3];
  }
  if ( !(*((unsigned int (__fastcall **)(_QWORD, __int64, ULONG64 *))this + 142))(*((_QWORD *)this + 153), 9, &v10) )
  {
    v9 = v10;
    a3->Flags |= 0x10u;
    a3->JobSharedCommitUsage = v9;
    a3->JobPrivateCommitUsage = v11;
    LODWORD(a3->JobPeakPrivateCommitUsage) = v12;
    HIDWORD(a3->JobPeakPrivateCommitUsage) = v13;
    a3->JobPrivateCommitLimit = v14;
    a3->JobTotalCommitLimit = v15;
  }
  return 0;
}

```

## disassembly

```asm
0x1800222d0  mov     [rsp-8+arg_18], rbx
0x1800222d5  push    rbp
0x1800222d6  push    rdi
0x1800222d7  push    r15
0x1800222d9  lea     rbp, [rsp-200h]
0x1800222e1  sub     rsp, 300h
0x1800222e8  mov     rax, cs:__security_cookie
0x1800222ef  xor     rax, rsp
0x1800222f2  mov     [rbp+210h+var_20], rax
0x1800222f9  mov     rbx, r8
0x1800222fc  mov     rdi, rcx
0x1800222ff  cmp     [rcx+4C8h], rdx
0x180022306  jz      short loc_180022312
0x180022308  call    ?QueryProcessVmCounters@NtWin32LiveSystemProvider@@UEAAJPEAXPEAU_MINIDUMP_PROCESS_VM_COUNTERS_2@@K@Z; NtWin32LiveSystemProvider::QueryProcessVmCounters(void *,_MINIDUMP_PROCESS_VM_COUNTERS_2 *,ulong)
0x18002230d  jmp     loc_180022514
0x180022312  cmp     r9d, 98h
0x180022319  jz      short loc_180022325
0x18002231b  mov     eax, 80070018h
0x180022320  jmp     loc_180022514
0x180022325  xor     edx, edx; Val
0x180022327  lea     rcx, [rsp+310h+var_2E0]; void *
0x18002232c  mov     r8d, 2C0h; Size
0x180022332  call    memset_0
0x180022337  lea     rcx, [rbx+4]; void *
0x18002233b  xor     edx, edx; Val
0x18002233d  mov     r8d, 94h; Size
0x180022343  call    memset_0
0x180022348  mov     dword ptr [rbx], 0F0002h
0x18002234e  lea     r8, [rsp+310h+var_2E0]
0x180022353  mov     rcx, [rdi+4C8h]
0x18002235a  mov     r15d, 2
0x180022360  mov     rax, [rdi+470h]
0x180022367  lea     r9d, [r15+6Eh]
0x18002236b  lea     edx, [r15+6]
0x18002236f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022374  cmp     eax, 18h
0x180022377  jnz     short loc_1800223D0
0x180022379  mov     eax, 0FFF7h
0x18002237e  lea     r9d, [r15+5Eh]
0x180022382  and     [rbx+2], ax
0x180022386  lea     r8, [rsp+310h+var_2E0]
0x18002238b  mov     rcx, [rdi+4C8h]
0x180022392  lea     edx, [r15+6]
0x180022396  mov     rax, [rdi+470h]
0x18002239d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223a2  cmp     eax, 18h
0x1800223a5  jnz     short loc_1800223D0
0x1800223a7  mov     eax, 0FFFBh
0x1800223ac  lea     r9d, [r15+56h]
0x1800223b0  and     [rbx+2], ax
0x1800223b4  lea     r8, [rsp+310h+var_2E0]
0x1800223b9  mov     rcx, [rdi+4C8h]
0x1800223c0  lea     edx, [r15+6]
0x1800223c4  mov     rax, [rdi+470h]
0x1800223cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223d0  test    eax, eax
0x1800223d2  jz      short loc_180022419
0x1800223d4  mov     eax, 0FFFCh
0x1800223d9  lea     r8, [rsp+310h+var_2E0]
0x1800223de  and     [rbx+2], ax
0x1800223e2  mov     r9d, 2C0h
0x1800223e8  mov     rcx, [rdi+4C8h]
0x1800223ef  xor     edx, edx
0x1800223f1  mov     rax, [rdi+470h]
0x1800223f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223fd  test    eax, eax
0x1800223ff  jnz     short loc_180022419
0x180022401  lea     r8d, [rax+70h]; Size
0x180022405  mov     word ptr [rbx+2], 7
0x18002240b  lea     rdx, [rbp+210h+Src]; Src
0x18002240f  lea     rcx, [rsp+310h+var_2E0]; void *
0x180022414  call    memmove_0
0x180022419  movzx   ecx, word ptr [rbx+2]
0x18002241d  test    cl, 1
0x180022420  jz      short loc_180022470
0x180022422  mov     eax, [rsp+310h+var_2D0]
0x180022426  mov     [rbx+4], eax
0x180022429  mov     rax, [rsp+310h+var_2C8]
0x18002242e  mov     [rbx+8], rax
0x180022432  mov     rax, [rsp+310h+var_2C0]
0x180022437  mov     [rbx+10h], rax
0x18002243b  mov     rax, [rsp+310h+var_2B8]
0x180022440  mov     [rbx+18h], rax
0x180022444  mov     rax, [rsp+310h+var_2B0]
0x180022449  mov     [rbx+20h], rax
0x18002244d  mov     rax, [rsp+310h+var_2A8]
0x180022452  mov     [rbx+28h], rax
0x180022456  mov     rax, [rsp+310h+var_2A0]
0x18002245b  mov     [rbx+30h], rax
0x18002245f  mov     rax, [rsp+310h+var_298]
0x180022464  mov     [rbx+38h], rax
0x180022468  mov     rax, [rbp+210h+Src]
0x18002246c  mov     [rbx+40h], rax
0x180022470  test    r15b, cl
0x180022473  jz      short loc_180022487
0x180022475  mov     rax, [rsp+310h+var_2E0]
0x18002247a  mov     [rbx+48h], rax
0x18002247e  mov     rax, [rsp+310h+var_2D8]
0x180022483  mov     [rbx+50h], rax
0x180022487  test    cl, 4
0x18002248a  jz      short loc_180022494
0x18002248c  mov     rax, [rbp+210h+var_288]
0x180022490  mov     [rbx+58h], rax
0x180022494  test    cl, 8
0x180022497  jz      short loc_1800224A9
0x180022499  mov     rax, [rbp+210h+var_280]
0x18002249d  mov     [rbx+60h], rax
0x1800224a1  mov     rax, [rbp+210h+var_278]
0x1800224a5  mov     [rbx+68h], rax
0x1800224a9  mov     rcx, [rdi+4C8h]
0x1800224b0  lea     r8, [rsp+310h+var_2E0]
0x1800224b5  mov     rax, [rdi+470h]
0x1800224bc  mov     r9d, 28h ; '('
0x1800224c2  lea     edx, [r9-1Fh]
0x1800224c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224cb  test    eax, eax
0x1800224cd  jnz     short loc_180022512
0x1800224cf  mov     rax, [rsp+310h+var_2E0]
0x1800224d4  or      word ptr [rbx+2], 10h
0x1800224d9  mov     [rbx+70h], rax
0x1800224dd  mov     rax, [rsp+310h+var_2D8]
0x1800224e2  mov     [rbx+78h], rax
0x1800224e6  mov     eax, [rsp+310h+var_2D0]
0x1800224ea  mov     [rbx+80h], eax
0x1800224f0  mov     eax, [rsp+310h+var_2CC]
0x1800224f4  mov     [rbx+84h], eax
0x1800224fa  mov     rax, [rsp+310h+var_2C8]
0x1800224ff  mov     [rbx+88h], rax
0x180022506  mov     rax, [rsp+310h+var_2C0]
0x18002250b  mov     [rbx+90h], rax
0x180022512  xor     eax, eax
0x180022514  mov     rcx, [rbp+210h+var_20]
0x18002251b  xor     rcx, rsp; StackCookie
0x18002251e  call    __security_check_cookie
0x180022523  mov     rbx, [rsp+310h+arg_18]
0x18002252b  add     rsp, 300h
0x180022532  pop     r15
0x180022534  pop     rdi
0x180022535  pop     rbp
0x180022536  retn
```
