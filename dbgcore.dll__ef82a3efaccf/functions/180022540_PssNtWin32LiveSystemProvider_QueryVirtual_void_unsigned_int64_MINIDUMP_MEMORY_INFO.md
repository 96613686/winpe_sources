# PssNtWin32LiveSystemProvider::QueryVirtual(void *,unsigned __int64,_MINIDUMP_MEMORY_INFO *)

- ea: `0x180022540`
- end: `0x180022796`
- name: `?QueryVirtual@PssNtWin32LiveSystemProvider@@UEAAJPEAX_KPEAU_MINIDUMP_MEMORY_INFO@@@Z`
- size: `598`
- prototype: `__int64 __fastcall(PssNtWin32LiveSystemProvider *__hidden this, void *, unsigned __int64, struct _MINIDUMP_MEMORY_INFO *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800021f4`
- `0x180015550`
- `0x180022540`
- `0x18002c010`

## pseudocode

```c
signed int __fastcall PssNtWin32LiveSystemProvider::QueryVirtual(
        PssNtWin32LiveSystemProvider *this,
        void *a2,
        unsigned __int64 a3,
        struct _MINIDUMP_MEMORY_INFO *a4)
{
  struct _MINIDUMP_MEMORY_INFO *v4; // rbx
  unsigned __int64 v5; // rsi
  PssNtWin32LiveSystemProvider *v6; // rdi
  signed int result; // eax
  bool v8; // cc
  ULONG64 v9; // rcx
  ULONG64 v10; // rdx
  ULONG32 v11; // eax
  _QWORD v12[3]; // [rsp+30h] [rbp-59h] BYREF
  ULONG32 v13; // [rsp+48h] [rbp-41h]
  ULONG64 v14; // [rsp+50h] [rbp-39h]
  ULONG32 v15; // [rsp+58h] [rbp-31h]
  ULONG32 v16; // [rsp+5Ch] [rbp-2Dh]
  ULONG32 v17; // [rsp+60h] [rbp-29h]
  unsigned int v18; // [rsp+78h] [rbp-11h]
  _QWORD v19[2]; // [rsp+80h] [rbp-9h] BYREF
  ULONG32 v20; // [rsp+90h] [rbp+7h]
  ULONG64 v21; // [rsp+98h] [rbp+Fh]
  ULONG32 v22; // [rsp+A0h] [rbp+17h]
  ULONG32 v23; // [rsp+A4h] [rbp+1Bh]
  ULONG32 v24; // [rsp+A8h] [rbp+1Fh]
  int v25; // [rsp+F0h] [rbp+67h] BYREF
  void *v26; // [rsp+F8h] [rbp+6Fh] BYREF

  v4 = a4;
  v5 = a3;
  v6 = this;
  if ( a2 != *((void **)this + 153) )
    return Win32LiveSystemProvider::QueryVirtual(this, a2, a3, a4);
  v25 = 0;
  memset_0(v12, 0, 0x50u);
  v26 = 0;
  memset_0(v19, 0, 0x50u);
  result = (*((__int64 (__fastcall **)(_QWORD))v6 + 148))(*((_QWORD *)v6 + 155));
  v8 = result <= 0;
  if ( !result )
  {
    while ( !(*((unsigned int (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD *, int))v6 + 143))(
               *((_QWORD *)v6 + 153),
               1,
               *((_QWORD *)v6 + 155),
               v19,
               80) )
    {
      v9 = v19[0];
      if ( v5 >= v19[0] )
      {
        v10 = v21;
        if ( v5 < v21 + v19[0] )
        {
          v4->__alignment1 = 0;
          v4->__alignment2 = 0;
          v4->AllocationBase = v19[1];
          v4->AllocationProtect = v20;
          v4->State = v22;
          v4->Protect = v23;
          v11 = v24;
          v4->BaseAddress = v9;
          v4->RegionSize = v10;
LABEL_14:
          v4->Type = v11;
          return 0;
        }
      }
      memset_0(v19, 0, 0x50u);
    }
    if ( !(*((unsigned int (__fastcall **)(_QWORD, __int64, int *))v6 + 142))(*((_QWORD *)v6 + 153), 2, &v25) && v25 )
    {
      memset_0(v12, 0, 0x50u);
      result = (*((__int64 (__fastcall **)(_QWORD))v6 + 148))(*((_QWORD *)v6 + 154));
      v8 = result <= 0;
      if ( result )
        goto LABEL_3;
      while ( !(*((unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD *, int))v6 + 143))(
                 *((_QWORD *)v6 + 153),
                 0,
                 *((_QWORD *)v6 + 154),
                 v12,
                 80) )
      {
        if ( v5 >= v12[0] && v5 < v12[0] + (unsigned __int64)v18 )
        {
          v4->__alignment1 = 0;
          v4->__alignment2 = 0;
          v4->BaseAddress = v12[1];
          v4->AllocationBase = v12[2];
          v4->AllocationProtect = v13;
          v4->RegionSize = v14;
          v4->State = v15;
          v4->Protect = v16;
          v11 = v17;
          goto LABEL_14;
        }
        memset_0(v12, 0, 0x50u);
      }
    }
    result = (*((__int64 (__fastcall **)(_QWORD, __int64, void **))v6 + 142))(*((_QWORD *)v6 + 153), 1, &v26);
    v8 = result <= 0;
    if ( !result )
    {
      a2 = v26;
      a4 = v4;
      a3 = v5;
      this = v6;
      return Win32LiveSystemProvider::QueryVirtual(this, a2, a3, a4);
    }
  }
LABEL_3:
  if ( !v8 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180022540  mov     [rsp-8+arg_10], rbx
0x180022545  mov     [rsp-8+arg_18], rsi
0x18002254a  push    rbp
0x18002254b  push    rdi
0x18002254c  push    r15
0x18002254e  lea     rbp, [rsp-47h]
0x180022553  sub     rsp, 0D0h
0x18002255a  mov     rbx, r9
0x18002255d  mov     rsi, r8
0x180022560  mov     rdi, rcx
0x180022563  cmp     rdx, [rcx+4C8h]
0x18002256a  jnz     loc_18002273A
0x180022570  mov     r15d, 50h ; 'P'
0x180022576  mov     [rbp+57h+arg_0], 0
0x18002257d  mov     r8d, r15d; Size
0x180022580  lea     rcx, [rbp+57h+var_B0]; void *
0x180022584  xor     edx, edx; Val
0x180022586  call    memset_0
0x18002258b  mov     r8d, r15d; Size
0x18002258e  mov     [rbp+57h+arg_8], 0
0x180022596  xor     edx, edx; Val
0x180022598  lea     rcx, [rbp+57h+var_60]; void *
0x18002259c  call    memset_0
0x1800225a1  mov     rcx, [rdi+4D8h]
0x1800225a8  mov     rax, [rdi+4A0h]
0x1800225af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225b4  test    eax, eax
0x1800225b6  jz      short loc_1800225F3
0x1800225b8  jle     loc_18002273F
0x1800225be  movzx   eax, ax
0x1800225c1  or      eax, 80070000h
0x1800225c6  jmp     loc_18002273F
0x1800225cb  mov     rcx, [rbp+57h+var_60]
0x1800225cf  cmp     rsi, rcx
0x1800225d2  jb      short loc_1800225E5
0x1800225d4  mov     rdx, [rbp+57h+var_48]
0x1800225d8  lea     rax, [rdx+rcx]
0x1800225dc  cmp     rsi, rax
0x1800225df  jb      loc_18002267B
0x1800225e5  mov     r8, r15; Size
0x1800225e8  lea     rcx, [rbp+57h+var_60]; void *
0x1800225ec  xor     edx, edx; Val
0x1800225ee  call    memset_0
0x1800225f3  mov     r8, [rdi+4D8h]
0x1800225fa  lea     r9, [rbp+57h+var_60]
0x1800225fe  mov     rcx, [rdi+4C8h]
0x180022605  mov     edx, 1
0x18002260a  mov     rax, [rdi+478h]
0x180022611  mov     [rsp+0E0h+var_C0], r15d
0x180022616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002261b  test    eax, eax
0x18002261d  jz      short loc_1800225CB
0x18002261f  mov     rcx, [rdi+4C8h]
0x180022626  lea     r8, [rbp+57h+arg_0]
0x18002262a  mov     rax, [rdi+470h]
0x180022631  mov     r9d, 4
0x180022637  lea     edx, [r9-2]
0x18002263b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022640  test    eax, eax
0x180022642  jnz     loc_180022704
0x180022648  cmp     [rbp+57h+arg_0], eax
0x18002264b  jz      loc_180022704
0x180022651  mov     r8, r15; Size
0x180022654  lea     rcx, [rbp+57h+var_B0]; void *
0x180022658  xor     edx, edx; Val
0x18002265a  call    memset_0
0x18002265f  mov     rcx, [rdi+4D0h]
0x180022666  mov     rax, [rdi+4A0h]
0x18002266d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022672  test    eax, eax
0x180022674  jz      short loc_1800226DB
0x180022676  jmp     loc_1800225B8
0x18002267b  mov     dword ptr [rbx+14h], 0
0x180022682  mov     dword ptr [rbx+2Ch], 0
0x180022689  mov     rax, [rbp+57h+var_58]
0x18002268d  mov     [rbx+8], rax
0x180022691  mov     eax, [rbp+57h+var_50]
0x180022694  mov     [rbx+10h], eax
0x180022697  mov     eax, [rbp+57h+var_40]
0x18002269a  mov     [rbx+20h], eax
0x18002269d  mov     eax, [rbp+57h+var_3C]
0x1800226a0  mov     [rbx+24h], eax
0x1800226a3  mov     eax, [rbp+57h+var_38]
0x1800226a6  mov     [rbx], rcx
0x1800226a9  mov     [rbx+18h], rdx
0x1800226ad  mov     [rbx+28h], eax
0x1800226b0  xor     eax, eax
0x1800226b2  jmp     loc_18002273F
0x1800226b7  cmp     rsi, [rbp+57h+var_B0]
0x1800226bb  jb      short loc_1800226CD
0x1800226bd  mov     eax, [rbp+57h+var_68]
0x1800226c0  add     rax, [rbp+57h+var_B0]
0x1800226c4  cmp     rsi, rax
0x1800226c7  jb      loc_180022757
0x1800226cd  mov     r8, r15; Size
0x1800226d0  lea     rcx, [rbp+57h+var_B0]; void *
0x1800226d4  xor     edx, edx; Val
0x1800226d6  call    memset_0
0x1800226db  mov     r8, [rdi+4D0h]
0x1800226e2  lea     r9, [rbp+57h+var_B0]
0x1800226e6  mov     rcx, [rdi+4C8h]
0x1800226ed  xor     edx, edx
0x1800226ef  mov     rax, [rdi+478h]
0x1800226f6  mov     [rsp+0E0h+var_C0], r15d
0x1800226fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022700  test    eax, eax
0x180022702  jz      short loc_1800226B7
0x180022704  mov     rcx, [rdi+4C8h]
0x18002270b  lea     r8, [rbp+57h+arg_8]
0x18002270f  mov     rax, [rdi+470h]
0x180022716  mov     r9d, 8
0x18002271c  lea     edx, [r9-7]
0x180022720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022725  test    eax, eax
0x180022727  jnz     loc_1800225B8
0x18002272d  mov     rdx, [rbp+57h+arg_8]; void *
0x180022731  mov     r9, rbx; struct _MINIDUMP_MEMORY_INFO *
0x180022734  mov     r8, rsi; unsigned __int64
0x180022737  mov     rcx, rdi; this
0x18002273a  call    ?QueryVirtual@Win32LiveSystemProvider@@UEAAJPEAX_KPEAU_MINIDUMP_MEMORY_INFO@@@Z; Win32LiveSystemProvider::QueryVirtual(void *,unsigned __int64,_MINIDUMP_MEMORY_INFO *)
0x18002273f  lea     r11, [rsp+0E0h+var_10]
0x180022747  mov     rbx, [r11+30h]
0x18002274b  mov     rsi, [r11+38h]
0x18002274f  mov     rsp, r11
0x180022752  pop     r15
0x180022754  pop     rdi
0x180022755  pop     rbp
0x180022756  retn
0x180022757  mov     dword ptr [rbx+14h], 0
0x18002275e  mov     dword ptr [rbx+2Ch], 0
0x180022765  mov     rax, [rbp+57h+var_A8]
0x180022769  mov     [rbx], rax
0x18002276c  mov     rax, [rbp+57h+var_A0]
0x180022770  mov     [rbx+8], rax
0x180022774  mov     eax, [rbp+57h+var_98]
0x180022777  mov     [rbx+10h], eax
0x18002277a  mov     rax, [rbp+57h+var_90]
0x18002277e  mov     [rbx+18h], rax
0x180022782  mov     eax, [rbp+57h+var_88]
0x180022785  mov     [rbx+20h], eax
0x180022788  mov     eax, [rbp+57h+var_84]
0x18002278b  mov     [rbx+24h], eax
0x18002278e  mov     eax, [rbp+57h+var_80]
0x180022791  jmp     loc_1800226AD
```
