# CLogInfo::Refresh(void)

- ea: `0x180016ffc`
- end: `0x180017180`
- name: `?Refresh@CLogInfo@@QEAAXXZ`
- size: `388`
- prototype: `void __fastcall(CLogInfo *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007ee4`

## callees

- `0x1800046a8`
- `0x180005f64`
- `0x180016ffc`
- `0x18001abd8`
- `0x18001ac04`
- `0x18001ae60`
- `0x18001e214`

## string_xrefs

- `0x1800170b9`: `SYSTEM\CurrentControlSet\Services\EventLog`

## pseudocode

```c
void __fastcall CLogInfo::Refresh(CLogInfo *this)
{
  __int16 v2; // ax
  __int16 v3; // cx
  BOOL v4; // r14d
  CComponentData *v5; // rcx
  const WCHAR *CurrentFocus; // rax
  HCURSOR v7; // r8
  CSynchWindow *v8; // rcx
  HKEY v9; // rdx
  __int16 v10; // ax
  HKEY v11; // [rsp+50h] [rbp+30h] BYREF
  __int64 v12; // [rsp+58h] [rbp+38h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp+40h] BYREF

  CSources::Clear((CLogInfo *)((char *)this + 4784));
  v2 = *((_WORD *)this + 12);
  v3 = v2 & 0x200;
  if ( (v2 & 1) != 0 )
  {
    if ( v3 )
    {
      *((_WORD *)this + 12) = v2 & 0xFDFF;
      CSynchWindow::Post((CSynchWindow *)0xFDFF, 0x7E9u, *((_QWORD *)this + 609), (__int64)this);
    }
    return;
  }
  v4 = v3 != 0;
  *((_WORD *)this + 12) = v2 | 0x700;
  v5 = (CComponentData *)*((_QWORD *)this + 609);
  phkResult = 0;
  v11 = 0;
  v12 = 0;
  CurrentFocus = CComponentData::GetCurrentFocus(v5);
  if ( !CurrentFocus )
  {
    v9 = HKEY_LOCAL_MACHINE;
    goto LABEL_8;
  }
  if ( (int)CSafeReg::Connect(&phkResult, CurrentFocus, v7) >= 0 )
  {
    v9 = phkResult;
LABEL_8:
    if ( (int)CSafeReg::Open((CSafeReg *)&v11, v9, L"SYSTEM\\CurrentControlSet\\Services\\EventLog", 8u) >= 0
      && (int)CSafeReg::Open((CSafeReg *)&v12, v11, (const unsigned __int16 *)this + 277, 1u) >= 0 )
    {
      *((_WORD *)this + 12) &= ~0x200u;
      v10 = *((_WORD *)this + 12);
      if ( (v10 & 8) == 0 )
        *((_WORD *)this + 12) = v10 & 0xFEFF;
      CSafeReg::Close((CSafeReg *)&v12);
      if ( (int)CSafeReg::Open((CSafeReg *)&v12, v11, (const unsigned __int16 *)this + 277, 2u) >= 0 )
        *((_WORD *)this + 12) &= ~0x400u;
    }
  }
  if ( v4 != ((*((unsigned __int16 *)this + 12) >> 9) & 1) )
    CSynchWindow::Post(v8, 0x7E9u, *((_QWORD *)this + 609), (__int64)this);
  CSafeReg::Close((CSafeReg *)&v12);
  CSafeReg::Close((CSafeReg *)&v11);
  CSafeReg::Close((CSafeReg *)&phkResult);
}

```

## disassembly

```asm
0x180016ffc  push    rbp
0x180016ffe  push    rbx
0x180016fff  push    rsi
0x180017000  push    rdi
0x180017001  push    r14
0x180017003  mov     rbp, rsp
0x180017006  sub     rsp, 20h
0x18001700a  mov     rbx, rcx
0x18001700d  add     rcx, 12B0h; this
0x180017014  call    ?Clear@CSources@@QEAAXXZ; CSources::Clear(void)
0x180017019  movzx   eax, word ptr [rbx+18h]
0x18001701d  mov     edx, 200h
0x180017022  movzx   ecx, ax
0x180017025  and     cx, dx
0x180017028  test    al, 1
0x18001702a  jz      short loc_18001705A
0x18001702c  test    cx, cx
0x18001702f  jz      loc_180017175
0x180017035  mov     ecx, 0FDFFh; this
0x18001703a  mov     r9, rbx; __int64
0x18001703d  and     ax, cx
0x180017040  mov     edx, 7E9h; unsigned int
0x180017045  mov     [rbx+18h], ax
0x180017049  mov     r8, [rbx+1308h]; unsigned __int64
0x180017050  call    ?Post@CSynchWindow@@QEAAJI_K_J@Z; CSynchWindow::Post(uint,unsigned __int64,__int64)
0x180017055  jmp     loc_180017175
0x18001705a  xor     edi, edi
0x18001705c  test    cx, cx
0x18001705f  mov     r14d, edi
0x180017062  setnz   r14b
0x180017066  or      ax, dx
0x180017069  or      ax, 400h
0x18001706d  or      ax, 100h
0x180017071  mov     [rbx+18h], ax
0x180017075  mov     rcx, [rbx+1308h]; this
0x18001707c  mov     [rbp+phkResult], rdi
0x180017080  mov     [rbp+arg_0], rdi
0x180017084  mov     [rbp+arg_8], rdi
0x180017088  call    ?GetCurrentFocus@CComponentData@@QEAAPEBGXZ; CComponentData::GetCurrentFocus(void)
0x18001708d  test    rax, rax
0x180017090  jz      short loc_1800170AC
0x180017092  mov     rdx, rax; lpMachineName
0x180017095  lea     rcx, [rbp+phkResult]; phkResult
0x180017099  call    ?Connect@CSafeReg@@QEAAJPEBGPEAUHKEY__@@@Z; CSafeReg::Connect(ushort const *,HKEY__ *)
0x18001709e  test    eax, eax
0x1800170a0  js      loc_180017137
0x1800170a6  mov     rdx, [rbp+phkResult]
0x1800170aa  jmp     short loc_1800170B3
0x1800170ac  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1800170b3  mov     r9d, 8; unsigned int
0x1800170b9  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ev"...
0x1800170c0  lea     rcx, [rbp+arg_0]; this
0x1800170c4  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x1800170c9  test    eax, eax
0x1800170cb  js      short loc_180017137
0x1800170cd  mov     rdx, [rbp+arg_0]; HKEY
0x1800170d1  lea     rsi, [rbx+22Ah]
0x1800170d8  mov     r8, rsi; unsigned __int16 *
0x1800170db  lea     rcx, [rbp+arg_8]; this
0x1800170df  mov     r9d, 1; unsigned int
0x1800170e5  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x1800170ea  test    eax, eax
0x1800170ec  js      short loc_180017137
0x1800170ee  mov     ecx, 0FDFFh
0x1800170f3  and     [rbx+18h], cx
0x1800170f7  movzx   eax, word ptr [rbx+18h]
0x1800170fb  test    al, 8
0x1800170fd  jnz     short loc_18001710B
0x1800170ff  mov     ecx, 0FEFFh
0x180017104  and     ax, cx
0x180017107  mov     [rbx+18h], ax
0x18001710b  lea     rcx, [rbp+arg_8]; this
0x18001710f  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180017114  mov     rdx, [rbp+arg_0]; HKEY
0x180017118  lea     rcx, [rbp+arg_8]; this
0x18001711c  mov     r9d, 2; unsigned int
0x180017122  mov     r8, rsi; unsigned __int16 *
0x180017125  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x18001712a  test    eax, eax
0x18001712c  js      short loc_180017137
0x18001712e  mov     eax, 0FBFFh
0x180017133  and     [rbx+18h], ax
0x180017137  movzx   eax, word ptr [rbx+18h]
0x18001713b  shr     eax, 9
0x18001713e  and     eax, 1
0x180017141  cmp     r14d, eax
0x180017144  jz      short loc_18001715A
0x180017146  mov     r8, [rbx+1308h]; unsigned __int64
0x18001714d  mov     r9, rbx; __int64
0x180017150  mov     edx, 7E9h; unsigned int
0x180017155  call    ?Post@CSynchWindow@@QEAAJI_K_J@Z; CSynchWindow::Post(uint,unsigned __int64,__int64)
0x18001715a  lea     rcx, [rbp+arg_8]; this
0x18001715e  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180017163  lea     rcx, [rbp+arg_0]; this
0x180017167  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x18001716c  lea     rcx, [rbp+phkResult]; this
0x180017170  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180017175  add     rsp, 20h
0x180017179  pop     r14
0x18001717b  pop     rdi
0x18001717c  pop     rsi
0x18001717d  pop     rbx
0x18001717e  pop     rbp
0x18001717f  retn
```
