# FIPreCloseCallback

- ea: `0x140012850`
- end: `0x140012a7d`
- name: `FIPreCloseCallback`
- size: `557`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001c00`
- `0x140001da0`
- `0x140003920`
- `0x140003a00`
- `0x14000d3cc`
- `0x140012850`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x1400128cb`
- `ntoskrnl!PsGetThreadId` at `0x1400128cb`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140012a51`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140012a51`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x140012908`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x140012908`

## pseudocode

```c
_BOOL8 __fastcall FIPreCloseCallback(__int64 a1, __int64 a2, _QWORD *a3)
{
  void (__fastcall *v5)(_QWORD, _QWORD *, __int64, __int64, __int16, __int128 *); // rdi
  struct _KTHREAD *v6; // rcx
  unsigned int ThreadId; // eax
  int ActivityIdCallbackData; // eax
  __int128 *v9; // rdx
  __int64 v10; // rbx
  __int64 v11; // r9
  __int64 v12; // rbx
  struct _EX_RUNDOWN_REF *Count; // rdi
  __int64 v15; // [rsp+40h] [rbp-68h] BYREF
  __int64 v16; // [rsp+48h] [rbp-60h]
  __int64 v17; // [rsp+50h] [rbp-58h]
  unsigned int v18; // [rsp+58h] [rbp-50h]
  __int128 v19; // [rsp+60h] [rbp-48h] BYREF
  _QWORD v20[2]; // [rsp+70h] [rbp-38h] BYREF

  *a3 = 0;
  if ( *(_QWORD *)(qword_140009A00 + 16) )
  {
    v19 = 0;
    v5 = *(void (__fastcall **)(_QWORD, _QWORD *, __int64, __int64, __int16, __int128 *))(qword_140009A00 + 16);
    if ( v5 )
    {
      v6 = *(struct _KTHREAD **)(a1 + 8);
      v16 = 0;
      v17 = 0;
      v18 = 0;
      v15 = a1;
      if ( v6 )
        ThreadId = (unsigned int)PsGetThreadId(v6);
      else
        ThreadId = -1;
      v18 = ThreadId;
      v16 = *(_QWORD *)(a2 + 32);
      v17 = *(_QWORD *)(v16 + 24);
      v20[0] = &v15;
      v20[1] = 28;
      ActivityIdCallbackData = FltGetActivityIdCallbackData(a1, &v19);
      v9 = &v19;
      if ( ActivityIdCallbackData < 0 )
        v9 = 0;
      v5(*(_QWORD *)(a1 + 8), v20, 1, 0x4000000, 1090, v9);
    }
  }
  v10 = *(_QWORD *)(a2 + 32);
  FILockSharedAcquire(&qword_140009648);
  if ( (unsigned int)qword_140009654 >> 5 )
  {
    v11 = -1LL << (qword_140009654 & 0x1F);
    v12 = v11 & v10;
    v20[0] = v12;
    Count = (struct _EX_RUNDOWN_REF *)(*(__int64 *)((char *)&qword_140009654 + 4)
                                     + 8LL
                                     * ((((unsigned int)qword_140009654 >> 5) - 1)
                                      & (HIBYTE(v12)
                                       + 37
                                       * (BYTE6(v12)
                                        + 37
                                        * (BYTE5(v12)
                                         + 37
                                         * (BYTE4(v12)
                                          + 37
                                          * (BYTE3(v12)
                                           + 37
                                           * (BYTE2(v12) + 37 * (BYTE1(v12) + 37 * ((unsigned __int8)v12 + 11623883))))))))));
    while ( 1 )
    {
      Count = (struct _EX_RUNDOWN_REF *)Count->Count;
      if ( ((unsigned __int8)Count & 1) != 0 )
        break;
      if ( v12 == (v11 & Count[1].Count) )
      {
        if ( !Count )
          break;
        ExAcquireRundownProtection(Count + 2);
        FILockExclusiveRelease(&qword_140009648);
        FIFileObjectDeleteContext(Count);
        return *(_QWORD *)(qword_140009A00 + 24) == 0;
      }
    }
  }
  FILockExclusiveRelease(&qword_140009648);
  return *(_QWORD *)(qword_140009A00 + 24) == 0;
}

```

## disassembly

```asm
0x140012850  mov     r11, rsp
0x140012853  push    rbx
0x140012854  push    rbp
0x140012855  push    rdi
0x140012856  sub     rsp, 90h
0x14001285d  mov     rax, cs:__security_cookie
0x140012864  xor     rax, rsp
0x140012867  mov     [rsp+0A8h+var_28], rax
0x14001286f  xor     ebp, ebp
0x140012871  mov     [r11+20h], rsi
0x140012875  mov     [r8], rbp
0x140012878  mov     rbx, rcx
0x14001287b  mov     rax, cs:qword_140009A00
0x140012882  mov     rsi, rdx
0x140012885  mov     rcx, [rax+10h]
0x140012889  test    rcx, rcx
0x14001288c  jz      loc_140012948
0x140012892  mov     rax, cs:qword_140009A00
0x140012899  xorps   xmm0, xmm0
0x14001289c  movups  [rsp+0A8h+var_48], xmm0
0x1400128a1  mov     rdi, [rax+10h]
0x1400128a5  test    rdi, rdi
0x1400128a8  jz      loc_140012948
0x1400128ae  mov     rcx, [rbx+8]; Thread
0x1400128b2  mov     [r11-60h], rbp
0x1400128b6  mov     [r11-58h], rbp
0x1400128ba  mov     [rsp+0A8h+var_50], ebp
0x1400128be  mov     [r11-68h], rbx
0x1400128c2  test    rcx, rcx
0x1400128c5  jz      loc_140012A73
0x1400128cb  call    cs:__imp_PsGetThreadId
0x1400128d2  nop     dword ptr [rax+rax+00h]
0x1400128d7  mov     [rsp+0A8h+var_50], eax
0x1400128db  lea     rdx, [rsp+0A8h+var_48]
0x1400128e0  mov     rax, [rsi+20h]
0x1400128e4  mov     rcx, rbx
0x1400128e7  mov     [rsp+0A8h+var_60], rax
0x1400128ec  mov     rax, [rax+18h]
0x1400128f0  mov     [rsp+0A8h+var_58], rax
0x1400128f5  lea     rax, [rsp+0A8h+var_68]
0x1400128fa  mov     [rsp+0A8h+var_38], rax
0x1400128ff  mov     [rsp+0A8h+var_30], 1Ch
0x140012908  call    cs:__imp_FltGetActivityIdCallbackData
0x14001290f  nop     dword ptr [rax+rax+00h]
0x140012914  mov     rcx, [rbx+8]
0x140012918  lea     rdx, [rsp+0A8h+var_48]
0x14001291d  test    eax, eax
0x14001291f  mov     r9d, 4000000h
0x140012925  mov     r8d, 1
0x14001292b  mov     rax, rdi
0x14001292e  cmovs   rdx, rbp
0x140012932  mov     [rsp+0A8h+var_80], rdx
0x140012937  lea     rdx, [rsp+0A8h+var_38]
0x14001293c  mov     [rsp+0A8h+var_88], 442h
0x140012943  call    _guard_dispatch_icall
0x140012948  mov     rbx, [rsi+20h]
0x14001294c  lea     rcx, qword_140009648
0x140012953  call    FILockSharedAcquire
0x140012958  mov     ecx, dword ptr cs:qword_140009654
0x14001295e  mov     eax, ecx
0x140012960  mov     rsi, [rsp+0A8h+arg_18]
0x140012968  shr     eax, 5
0x14001296b  test    eax, eax
0x14001296d  jz      loc_140012A01
0x140012973  and     ecx, 1Fh
0x140012976  lea     r10, [rsp+0A8h+var_38]
0x14001297b  mov     r9, 0FFFFFFFFFFFFFFFFh
0x140012982  shl     r9, cl
0x140012985  and     rbx, r9
0x140012988  mov     [rsp+0A8h+var_38], rbx
0x14001298d  movzx   ecx, byte ptr [r10]
0x140012991  add     ecx, 0B15DCBh
0x140012997  imul    edx, ecx, 25h ; '%'
0x14001299a  movzx   ecx, byte ptr [r10+1]
0x14001299f  add     edx, ecx
0x1400129a1  movzx   ecx, byte ptr [r10+2]
0x1400129a6  imul    r8d, edx, 25h ; '%'
0x1400129aa  add     r8d, ecx
0x1400129ad  movzx   ecx, byte ptr [r10+3]
0x1400129b2  imul    edx, r8d, 25h ; '%'
0x1400129b6  add     edx, ecx
0x1400129b8  movzx   ecx, byte ptr [r10+4]
0x1400129bd  imul    r8d, edx, 25h ; '%'
0x1400129c1  add     r8d, ecx
0x1400129c4  movzx   ecx, byte ptr [r10+5]
0x1400129c9  imul    edx, r8d, 25h ; '%'
0x1400129cd  add     edx, ecx
0x1400129cf  movzx   ecx, byte ptr [r10+6]
0x1400129d4  imul    r8d, edx, 25h ; '%'
0x1400129d8  add     r8d, ecx
0x1400129db  movzx   ecx, byte ptr [r10+7]
0x1400129e0  imul    r8d, 25h ; '%'
0x1400129e4  add     r8d, ecx
0x1400129e7  lea     ecx, [rax-1]
0x1400129ea  mov     rax, cs:qword_140009654+4
0x1400129f1  and     r8, rcx
0x1400129f4  lea     rdi, [rax+r8*8]
0x1400129f8  mov     rdi, [rdi]
0x1400129fb  test    dil, 1
0x1400129ff  jz      short loc_140012A3C
0x140012a01  lea     rcx, qword_140009648
0x140012a08  call    FILockExclusiveRelease
0x140012a0d  mov     rax, cs:qword_140009A00
0x140012a14  mov     rcx, [rax+18h]
0x140012a18  mov     eax, ebp
0x140012a1a  test    rcx, rcx
0x140012a1d  setz    al
0x140012a20  mov     rcx, [rsp+0A8h+var_28]
0x140012a28  xor     rcx, rsp; StackCookie
0x140012a2b  call    __security_check_cookie
0x140012a30  add     rsp, 90h
0x140012a37  pop     rdi
0x140012a38  pop     rbp
0x140012a39  pop     rbx
0x140012a3a  retn
0x140012a3c  mov     rax, [rdi+8]
0x140012a40  and     rax, r9
0x140012a43  cmp     rbx, rax
0x140012a46  jnz     short loc_1400129F8
0x140012a48  test    rdi, rdi
0x140012a4b  jz      short loc_140012A01
0x140012a4d  lea     rcx, [rdi+10h]; RunRef
0x140012a51  call    cs:__imp_ExAcquireRundownProtection
0x140012a58  nop     dword ptr [rax+rax+00h]
0x140012a5d  lea     rcx, qword_140009648
0x140012a64  call    FILockExclusiveRelease
0x140012a69  mov     rcx, rdi; P
0x140012a6c  call    FIFileObjectDeleteContext
0x140012a71  jmp     short loc_140012A0D
0x140012a73  mov     eax, 0FFFFFFFFh
0x140012a78  jmp     loc_1400128D7
```
