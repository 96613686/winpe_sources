# CMSMQTransaction::Commit(tagVARIANT *,tagVARIANT *,tagVARIANT *)

- ea: `0x180020370`
- end: `0x1800204df`
- name: `?Commit@CMSMQTransaction@@UEAAJPEAUtagVARIANT@@00@Z`
- size: `367`
- prototype: `int(CMSMQTransaction *__hidden this, struct tagVARIANT *, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180005430`
- `0x18000cb34`
- `0x180020370`
- `0x180026934`
- `0x180026bc0`
- `0x180029010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800203aa`
- `KERNEL32!LeaveCriticalSection` at `0x18002040b`
- `KERNEL32!LeaveCriticalSection` at `0x180020422`
- `KERNEL32!LeaveCriticalSection` at `0x1800204bf`
- `KERNEL32!LeaveCriticalSection` at `0x1800203aa`
- `KERNEL32!LeaveCriticalSection` at `0x18002040b`
- `KERNEL32!LeaveCriticalSection` at `0x180020422`
- `KERNEL32!LeaveCriticalSection` at `0x1800204bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMSMQTransaction::Commit(
        CMSMQTransaction *this,
        struct tagVARIANT *a2,
        struct tagVARIANT *a3,
        struct tagVARIANT *a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // rdi
  __int64 v9; // rcx
  signed int v11; // eax
  unsigned int ErrorHelper; // ebx
  unsigned int Bool; // r15d
  unsigned int Number; // r12d
  unsigned int v15; // ebx
  signed int v16; // eax
  __int64 v17; // [rsp+60h] [rbp+8h] BYREF

  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 72);
  CCriticalSection::Lock((CMSMQTransaction *)((char *)this + 72));
  v9 = *((_QWORD *)this + 14);
  if ( !v9 )
    goto LABEL_2;
  v17 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *, _QWORD))(*(_QWORD *)v9 + 40LL))(
          v9,
          &GUID_0fb15084_af41_11ce_bd2b_204c4f4f5020,
          &v17,
          0);
  if ( v11 >= 0 )
  {
    if ( !v17 )
    {
LABEL_2:
      LeaveCriticalSection(v8);
      return 2147942487LL;
    }
    Bool = 0;
    Number = 0;
    v15 = 0;
    if ( a2 && a2->vt != 10 )
      Bool = GetBool(a2);
    if ( a3 && a3->vt != 10 )
      Number = GetNumber(a3, 0xFFFFFFFF);
    if ( a4 && a4->vt != 10 )
      v15 = GetNumber(a4, 0xFFFFFFFF);
    v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v17 + 24LL))(v17, Bool, Number, v15);
    ErrorHelper = CreateErrorHelper(v16, 6);
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  else
  {
    ErrorHelper = CreateErrorHelper(v11, 6);
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  LeaveCriticalSection(v8);
  return ErrorHelper;
}

```

## disassembly

```asm
0x180020370  mov     [rsp+arg_8], rbx
0x180020375  mov     [rsp+arg_10], rbp
0x18002037a  push    rsi
0x18002037b  push    rdi
0x18002037c  push    r12
0x18002037e  push    r14
0x180020380  push    r15
0x180020382  sub     rsp, 30h
0x180020386  mov     rbp, r9
0x180020389  mov     r14, r8
0x18002038c  mov     rsi, rdx
0x18002038f  mov     rbx, rcx
0x180020392  lea     rdi, [rcx+48h]
0x180020396  mov     rcx, rdi; this
0x180020399  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18002039e  mov     rcx, [rbx+70h]
0x1800203a2  test    rcx, rcx
0x1800203a5  jnz     short loc_1800203BB
0x1800203a7  mov     rcx, rdi; lpCriticalSection
0x1800203aa  call    cs:__imp_LeaveCriticalSection
0x1800203b0  nop
0x1800203b1  mov     eax, 80070057h
0x1800203b6  jmp     loc_1800204C8
0x1800203bb  mov     [rsp+58h+arg_0], 0
0x1800203c4  mov     rax, [rcx]
0x1800203c7  xor     r9d, r9d
0x1800203ca  lea     r8, [rsp+58h+arg_0]
0x1800203cf  lea     rdx, _GUID_0fb15084_af41_11ce_bd2b_204c4f4f5020
0x1800203d6  mov     rax, [rax+28h]
0x1800203da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203df  test    eax, eax
0x1800203e1  jns     short loc_180020417
0x1800203e3  mov     edx, 6
0x1800203e8  mov     ecx, eax
0x1800203ea  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x1800203ef  mov     ebx, eax
0x1800203f1  mov     rcx, [rsp+58h+arg_0]
0x1800203f6  test    rcx, rcx
0x1800203f9  jz      short loc_180020408
0x1800203fb  mov     rdx, [rcx]
0x1800203fe  mov     rax, [rdx+10h]
0x180020402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020407  nop
0x180020408  mov     rcx, rdi; lpCriticalSection
0x18002040b  call    cs:__imp_LeaveCriticalSection
0x180020411  nop
0x180020412  jmp     loc_1800204C6
0x180020417  cmp     [rsp+58h+arg_0], 0
0x18002041d  jnz     short loc_18002042B
0x18002041f  mov     rcx, rdi; lpCriticalSection
0x180020422  call    cs:__imp_LeaveCriticalSection
0x180020428  nop
0x180020429  jmp     short loc_1800203B1
0x18002042b  xor     r15d, r15d
0x18002042e  xor     r12d, r12d
0x180020431  xor     ebx, ebx
0x180020433  test    rsi, rsi
0x180020436  jz      short loc_180020449
0x180020438  cmp     word ptr [rsi], 0Ah
0x18002043c  jz      short loc_180020449
0x18002043e  mov     rcx, rsi; struct tagVARIANT *
0x180020441  call    ?GetBool@@YAHPEAUtagVARIANT@@@Z; GetBool(tagVARIANT *)
0x180020446  mov     r15d, eax
0x180020449  or      esi, 0FFFFFFFFh
0x18002044c  test    r14, r14
0x18002044f  jz      short loc_180020465
0x180020451  cmp     word ptr [r14], 0Ah
0x180020456  jz      short loc_180020465
0x180020458  mov     edx, esi; unsigned int
0x18002045a  mov     rcx, r14; pvarSrc
0x18002045d  call    ?GetNumber@@YAIPEAUtagVARIANT@@I@Z; GetNumber(tagVARIANT *,uint)
0x180020462  mov     r12d, eax
0x180020465  test    rbp, rbp
0x180020468  jz      short loc_18002047D
0x18002046a  cmp     word ptr [rbp+0], 0Ah
0x18002046f  jz      short loc_18002047D
0x180020471  mov     edx, esi; unsigned int
0x180020473  mov     rcx, rbp; pvarSrc
0x180020476  call    ?GetNumber@@YAIPEAUtagVARIANT@@I@Z; GetNumber(tagVARIANT *,uint)
0x18002047b  mov     ebx, eax
0x18002047d  mov     rcx, [rsp+58h+arg_0]
0x180020482  mov     rdx, [rcx]
0x180020485  mov     rax, [rdx+18h]
0x180020489  mov     r9d, ebx
0x18002048c  mov     r8d, r12d
0x18002048f  mov     edx, r15d
0x180020492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020497  mov     edx, 6
0x18002049c  mov     ecx, eax
0x18002049e  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x1800204a3  mov     ebx, eax
0x1800204a5  mov     rcx, [rsp+58h+arg_0]
0x1800204aa  test    rcx, rcx
0x1800204ad  jz      short loc_1800204BC
0x1800204af  mov     rdx, [rcx]
0x1800204b2  mov     rax, [rdx+10h]
0x1800204b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204bb  nop
0x1800204bc  mov     rcx, rdi; lpCriticalSection
0x1800204bf  call    cs:__imp_LeaveCriticalSection
0x1800204c5  nop
0x1800204c6  mov     eax, ebx
0x1800204c8  mov     rbx, [rsp+58h+arg_8]
0x1800204cd  mov     rbp, [rsp+58h+arg_10]
0x1800204d2  add     rsp, 30h
0x1800204d6  pop     r15
0x1800204d8  pop     r14
0x1800204da  pop     r12
0x1800204dc  pop     rdi
0x1800204dd  pop     rsi
0x1800204de  retn
```
