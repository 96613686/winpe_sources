# NtWin32LiveSystemProvider::QueryProcessVmCounters(void *,_MINIDUMP_PROCESS_VM_COUNTERS_2 *,ulong)

- ea: `0x180025b00`
- end: `0x180025d3b`
- name: `?QueryProcessVmCounters@NtWin32LiveSystemProvider@@UEAAJPEAXPEAU_MINIDUMP_PROCESS_VM_COUNTERS_2@@K@Z`
- size: `571`
- prototype: `__int64 __fastcall(NtWin32LiveSystemProvider *__hidden this, void *, struct _MINIDUMP_PROCESS_VM_COUNTERS_2 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800222d0`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x1800153b0`
- `0x180025b00`
- `0x18002c010`

## pseudocode

```c
int __fastcall NtWin32LiveSystemProvider::QueryProcessVmCounters(
        NtWin32LiveSystemProvider *this,
        void *a2,
        struct _MINIDUMP_PROCESS_VM_COUNTERS_2 *a3,
        unsigned int a4)
{
  USHORT Flags; // cx
  ULONG64 v9; // rax
  ULONG64 v10; // [rsp+30h] [rbp-49h] BYREF
  ULONG64 v11; // [rsp+38h] [rbp-41h]
  ULONG v12; // [rsp+40h] [rbp-39h]
  int v13; // [rsp+44h] [rbp-35h]
  ULONG64 v14; // [rsp+48h] [rbp-31h]
  ULONG64 v15; // [rsp+50h] [rbp-29h]
  ULONG64 v16; // [rsp+58h] [rbp-21h]
  ULONG64 v17; // [rsp+60h] [rbp-19h]
  ULONG64 v18; // [rsp+68h] [rbp-11h]
  ULONG64 v19; // [rsp+70h] [rbp-9h]
  ULONG64 v20; // [rsp+78h] [rbp-1h]
  ULONG64 v21; // [rsp+80h] [rbp+7h]
  ULONG64 v22; // [rsp+88h] [rbp+Fh]
  ULONG64 v23; // [rsp+90h] [rbp+17h]
  ULONG64 v24; // [rsp+98h] [rbp+1Fh]

  if ( *((_DWORD *)this + 17) < 0x272Du )
    return Win32LiveSystemProvider::QueryProcessVmCounters(this, a2, a3, a4);
  if ( !*((_QWORD *)this + 107) )
    return -2147024846;
  if ( a4 != 152 )
    return -2147024872;
  memset_0(&v10, 0, 0x70u);
  memset_0(&a3->PageFaultCount, 0, 0x94u);
  *(_DWORD *)&a3->Revision = 983042;
  if ( (*((int (__fastcall **)(void *, __int64, ULONG64 *, __int64, _QWORD))this + 107))(a2, 3, &v10, 112, 0) < 0 )
  {
    a3->Flags &= ~8u;
    if ( (*((int (__fastcall **)(void *, __int64, ULONG64 *, __int64, _QWORD))this + 107))(a2, 3, &v10, 96, 0) < 0 )
    {
      a3->Flags &= ~4u;
      if ( (*((int (__fastcall **)(void *, __int64, ULONG64 *, __int64, _QWORD))this + 107))(a2, 3, &v10, 88, 0) < 0 )
        a3->Flags &= 0xFFFCu;
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
    a3->PeakPagefileUsage = v21;
  }
  if ( (Flags & 2) != 0 )
  {
    a3->PeakVirtualSize = v10;
    a3->VirtualSize = v11;
  }
  if ( (Flags & 4) != 0 )
    a3->PrivateUsage = v22;
  if ( (Flags & 8) != 0 )
  {
    a3->PrivateWorkingSetSize = v23;
    a3->SharedCommitUsage = v24;
  }
  if ( *((_DWORD *)this + 17) >= 0x2748u
    && (*((int (__fastcall **)(void *, __int64, ULONG64 *))this + 107))(a2, 69, &v10) >= 0 )
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
0x180025b00  push    rbp
0x180025b02  push    rbx
0x180025b03  push    rsi
0x180025b04  push    rdi
0x180025b05  push    r12
0x180025b07  lea     rbp, [rsp-37h]
0x180025b0c  sub     rsp, 0B0h
0x180025b13  mov     rax, cs:__security_cookie
0x180025b1a  xor     rax, rsp
0x180025b1d  mov     [rbp+57h+var_30], rax
0x180025b21  cmp     dword ptr [rcx+44h], 272Dh
0x180025b28  mov     rbx, r8
0x180025b2b  mov     rsi, rdx
0x180025b2e  mov     rdi, rcx
0x180025b31  jnb     short loc_180025B3D
0x180025b33  call    ?QueryProcessVmCounters@Win32LiveSystemProvider@@UEAAJPEAXPEAU_MINIDUMP_PROCESS_VM_COUNTERS_2@@K@Z; Win32LiveSystemProvider::QueryProcessVmCounters(void *,_MINIDUMP_PROCESS_VM_COUNTERS_2 *,ulong)
0x180025b38  jmp     loc_180025D21
0x180025b3d  cmp     qword ptr [rcx+358h], 0
0x180025b45  jnz     short loc_180025B51
0x180025b47  mov     eax, 80070032h
0x180025b4c  jmp     loc_180025D21
0x180025b51  cmp     r9d, 98h
0x180025b58  jz      short loc_180025B64
0x180025b5a  mov     eax, 80070018h
0x180025b5f  jmp     loc_180025D21
0x180025b64  xor     edx, edx; Val
0x180025b66  lea     rcx, [rbp+57h+var_A0]; void *
0x180025b6a  lea     r8d, [rdx+70h]; Size
0x180025b6e  call    memset_0
0x180025b73  lea     rcx, [rbx+4]; void *
0x180025b77  xor     edx, edx; Val
0x180025b79  mov     r8d, 94h; Size
0x180025b7f  call    memset_0
0x180025b84  mov     r12d, 2
0x180025b8a  mov     dword ptr [rbx], 0F0002h
0x180025b90  mov     rax, [rdi+358h]
0x180025b97  lea     r8, [rbp+57h+var_A0]
0x180025b9b  mov     rcx, rsi
0x180025b9e  mov     [rsp+0D0h+var_B0], 0
0x180025ba7  lea     r9d, [r12+6Eh]
0x180025bac  lea     edx, [r12+1]
0x180025bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bb6  test    eax, eax
0x180025bb8  jns     short loc_180025C29
0x180025bba  mov     eax, 0FFF7h
0x180025bbf  mov     [rsp+0D0h+var_B0], 0
0x180025bc8  and     [rbx+2], ax
0x180025bcc  lea     r9d, [r12+5Eh]
0x180025bd1  mov     rax, [rdi+358h]
0x180025bd8  lea     r8, [rbp+57h+var_A0]
0x180025bdc  lea     edx, [r12+1]
0x180025be1  mov     rcx, rsi
0x180025be4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025be9  test    eax, eax
0x180025beb  jns     short loc_180025C29
0x180025bed  mov     eax, 0FFFBh
0x180025bf2  mov     [rsp+0D0h+var_B0], 0
0x180025bfb  and     [rbx+2], ax
0x180025bff  lea     r9d, [r12+56h]
0x180025c04  mov     rax, [rdi+358h]
0x180025c0b  lea     r8, [rbp+57h+var_A0]
0x180025c0f  lea     edx, [r12+1]
0x180025c14  mov     rcx, rsi
0x180025c17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c1c  test    eax, eax
0x180025c1e  jns     short loc_180025C29
0x180025c20  mov     eax, 0FFFCh
0x180025c25  and     [rbx+2], ax
0x180025c29  movzx   ecx, word ptr [rbx+2]
0x180025c2d  test    cl, 1
0x180025c30  jz      short loc_180025C78
0x180025c32  mov     eax, [rbp+57h+var_90]
0x180025c35  mov     [rbx+4], eax
0x180025c38  mov     rax, [rbp+57h+var_88]
0x180025c3c  mov     [rbx+8], rax
0x180025c40  mov     rax, [rbp+57h+var_80]
0x180025c44  mov     [rbx+10h], rax
0x180025c48  mov     rax, [rbp+57h+var_78]
0x180025c4c  mov     [rbx+18h], rax
0x180025c50  mov     rax, [rbp+57h+var_70]
0x180025c54  mov     [rbx+20h], rax
0x180025c58  mov     rax, [rbp+57h+var_68]
0x180025c5c  mov     [rbx+28h], rax
0x180025c60  mov     rax, [rbp+57h+var_60]
0x180025c64  mov     [rbx+30h], rax
0x180025c68  mov     rax, [rbp+57h+var_58]
0x180025c6c  mov     [rbx+38h], rax
0x180025c70  mov     rax, [rbp+57h+var_50]
0x180025c74  mov     [rbx+40h], rax
0x180025c78  test    r12b, cl
0x180025c7b  jz      short loc_180025C8D
0x180025c7d  mov     rax, [rbp+57h+var_A0]
0x180025c81  mov     [rbx+48h], rax
0x180025c85  mov     rax, [rbp+57h+var_98]
0x180025c89  mov     [rbx+50h], rax
0x180025c8d  test    cl, 4
0x180025c90  jz      short loc_180025C9A
0x180025c92  mov     rax, [rbp+57h+var_48]
0x180025c96  mov     [rbx+58h], rax
0x180025c9a  test    cl, 8
0x180025c9d  jz      short loc_180025CAF
0x180025c9f  mov     rax, [rbp+57h+var_40]
0x180025ca3  mov     [rbx+60h], rax
0x180025ca7  mov     rax, [rbp+57h+var_38]
0x180025cab  mov     [rbx+68h], rax
0x180025caf  cmp     dword ptr [rdi+44h], 2748h
0x180025cb6  jb      short loc_180025D1F
0x180025cb8  mov     rax, [rdi+358h]
0x180025cbf  lea     r8, [rbp+57h+var_A0]
0x180025cc3  mov     r9d, 28h ; '('
0x180025cc9  mov     [rsp+0D0h+var_B0], 0
0x180025cd2  mov     rcx, rsi
0x180025cd5  lea     edx, [r9+1Dh]
0x180025cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025cde  test    eax, eax
0x180025ce0  js      short loc_180025D1F
0x180025ce2  mov     rax, [rbp+57h+var_A0]
0x180025ce6  or      word ptr [rbx+2], 10h
0x180025ceb  mov     [rbx+70h], rax
0x180025cef  mov     rax, [rbp+57h+var_98]
0x180025cf3  mov     [rbx+78h], rax
0x180025cf7  mov     eax, [rbp+57h+var_90]
0x180025cfa  mov     [rbx+80h], eax
0x180025d00  mov     eax, [rbp+57h+var_8C]
0x180025d03  mov     [rbx+84h], eax
0x180025d09  mov     rax, [rbp+57h+var_88]
0x180025d0d  mov     [rbx+88h], rax
0x180025d14  mov     rax, [rbp+57h+var_80]
0x180025d18  mov     [rbx+90h], rax
0x180025d1f  xor     eax, eax
0x180025d21  mov     rcx, [rbp+57h+var_30]
0x180025d25  xor     rcx, rsp; StackCookie
0x180025d28  call    __security_check_cookie
0x180025d2d  add     rsp, 0B0h
0x180025d34  pop     r12
0x180025d36  pop     rdi
0x180025d37  pop     rsi
0x180025d38  pop     rbx
0x180025d39  pop     rbp
0x180025d3a  retn
```
