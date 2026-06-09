# CWbemInstance::WriteToStream(IStream *)

- ea: `0x18005a440`
- end: `0x18005a72a`
- name: `?WriteToStream@CWbemInstance@@UEAAJPEAUIStream@@@Z`
- size: `746`
- prototype: `__int64 __fastcall(CWbemInstance *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18001e0e0`
- `0x180037120`
- `0x180050490`
- `0x18005a440`
- `0x18005a730`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18005a4c6`
- `wbemcomn!GetMemLogObject` at `0x18005a5e0`
- `wbemcomn!GetMemLogObject` at `0x18005a658`
- `wbemcomn!GetMemLogObject` at `0x18005a6b9`
- `wbemcomn!GetMemLogObject` at `0x18005a6f2`
- `wbemcomn!GetMemLogObject` at `0x18005a4c6`
- `wbemcomn!GetMemLogObject` at `0x18005a5e0`
- `wbemcomn!GetMemLogObject` at `0x18005a658`
- `wbemcomn!GetMemLogObject` at `0x18005a6b9`
- `wbemcomn!GetMemLogObject` at `0x18005a6f2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005a4d1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005a5eb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005a663`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005a6c4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005a6fd`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005a4d1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005a5eb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005a663`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005a6c4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005a6fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWbemInstance::WriteToStream(CWbemInstance *this, struct IStream *a2)
{
  int v4; // ebx
  CMemoryLog *MemLogObject; // rax
  CWbemRefreshingSvc *v7; // r10
  unsigned int Length; // eax
  CMemoryLog *v9; // rax
  __int64 v10; // rdx
  CMemoryLog *v11; // rax
  CWbemRefreshingSvc *v12; // r10
  __int64 v13; // rdx
  CMemoryLog *v14; // rax
  CMemoryLog *v15; // rax
  int v16; // [rsp+50h] [rbp+8h] BYREF
  int v17; // [rsp+60h] [rbp+18h] BYREF
  CWbemInstance *v18; // [rsp+68h] [rbp+20h] BYREF

  v18 = this;
  (*(void (__fastcall **)(CWbemInstance *, __int64))(*(_QWORD *)this + 280LL))(this, 1);
  if ( (*((_BYTE *)this + 60) & 0x14) != 0x14 )
  {
    v4 = CWbemObject::WriteToStream(this, a2);
    (*(void (__fastcall **)(CWbemInstance *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
    return (unsigned int)v4;
  }
  v17 = 305419896;
  v4 = ((__int64 (__fastcall *)(struct IStream *, int *, __int64))a2->lpVtbl->Write)(a2, &v17, 4);
  if ( v4 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v4);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_6;
    }
    v10 = 157;
LABEL_16:
    WPP_SF_d(*((_QWORD *)v7 + 2), v10, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids, (unsigned int)v4);
LABEL_6:
    (*(void (__fastcall **)(CWbemInstance *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
    return (unsigned int)v4;
  }
  v16 = 0;
  (*(void (__fastcall **)(CWbemInstance *, _QWORD, _QWORD, __int64, int *))(*(_QWORD *)this + 568LL))(
    this,
    0,
    0,
    7,
    &v16);
  v4 = ((__int64 (__fastcall *)(struct IStream *, int *, __int64))a2->lpVtbl->Write)(a2, &v16, 4);
  if ( v4 < 0 )
  {
    v11 = GetMemLogObject();
    CMemoryLog::Write(v11, v4);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_25;
    }
    v13 = 158;
    goto LABEL_24;
  }
  Length = CDecorationPart::GetLength((CWbemInstance *)((char *)this + 72));
  v4 = ((__int64 (__fastcall *)(struct IStream *, _QWORD, _QWORD, _QWORD))a2->lpVtbl->Write)(
         a2,
         *((_QWORD *)this + 9),
         Length,
         0);
  if ( v4 < 0 )
  {
    v9 = GetMemLogObject();
    CMemoryLog::Write(v9, v4);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_6;
    }
    v10 = 159;
    goto LABEL_16;
  }
  v4 = ((__int64 (__fastcall *)(struct IStream *, _QWORD, _QWORD, _QWORD))a2->lpVtbl->Write)(
         a2,
         *((_QWORD *)this + 56),
         **((unsigned int **)this + 56),
         0);
  if ( v4 < 0 )
  {
    v14 = GetMemLogObject();
    CMemoryLog::Write(v14, v4);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_25;
    }
    v13 = 160;
    goto LABEL_24;
  }
  v4 = ((__int64 (__fastcall *)(struct IStream *, _QWORD, _QWORD, _QWORD))a2->lpVtbl->Write)(
         a2,
         *((_QWORD *)this + 27),
         **((unsigned int **)this + 27),
         0);
  if ( v4 < 0 )
  {
    v15 = GetMemLogObject();
    CMemoryLog::Write(v15, v4);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_25;
    }
    v13 = 161;
LABEL_24:
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids, (unsigned int)v4);
LABEL_25:
    CWbemObject::CLock::~CLock((CWbemObject::CLock *)&v18);
    return (unsigned int)v4;
  }
  (*(void (__fastcall **)(CWbemInstance *, _QWORD))(*(_QWORD *)this + 288LL))(this, 0);
  return 0;
}

```

## disassembly

```asm
0x18005a440  push    rbx
0x18005a442  push    rsi
0x18005a443  push    rdi
0x18005a444  sub     rsp, 30h
0x18005a448  mov     rsi, rdx
0x18005a44b  mov     rdi, rcx
0x18005a44e  mov     [rsp+48h+arg_18], rcx
0x18005a453  mov     rax, [rcx]
0x18005a456  mov     edx, 1
0x18005a45b  mov     rax, [rax+118h]
0x18005a462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a467  nop
0x18005a468  mov     eax, [rdi+3Ch]
0x18005a46b  and     eax, 14h
0x18005a46e  cmp     al, 14h
0x18005a470  jz      short loc_18005A49D
0x18005a472  mov     rdx, rsi; struct IStream *
0x18005a475  mov     rcx, rdi; this
0x18005a478  call    ?WriteToStream@CWbemObject@@UEAAJPEAUIStream@@@Z; CWbemObject::WriteToStream(IStream *)
0x18005a47d  mov     ebx, eax
0x18005a47f  mov     rcx, [rdi]
0x18005a482  mov     rax, [rcx+120h]
0x18005a489  xor     edx, edx
0x18005a48b  mov     rcx, rdi
0x18005a48e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a493  mov     eax, ebx
0x18005a495  add     rsp, 30h
0x18005a499  pop     rdi
0x18005a49a  pop     rsi
0x18005a49b  pop     rbx
0x18005a49c  retn
0x18005a49d  mov     [rsp+48h+arg_10], 12345678h
0x18005a4a5  mov     rax, [rsi]
0x18005a4a8  xor     r9d, r9d
0x18005a4ab  lea     r8d, [r9+4]
0x18005a4af  lea     rdx, [rsp+48h+arg_10]
0x18005a4b4  mov     rcx, rsi
0x18005a4b7  mov     rax, [rax+20h]
0x18005a4bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a4c0  mov     ebx, eax
0x18005a4c2  test    eax, eax
0x18005a4c4  jns     short loc_18005A4FA
0x18005a4c6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005a4cc  mov     edx, ebx
0x18005a4ce  mov     rcx, rax
0x18005a4d1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005a4d7  lea     rcx, WPP_GLOBAL_Control
0x18005a4de  mov     r10, cs:WPP_GLOBAL_Control
0x18005a4e5  cmp     r10, rcx
0x18005a4e8  jnz     loc_18005A63B
0x18005a4ee  mov     rax, [rdi]
0x18005a4f1  mov     rax, [rax+120h]
0x18005a4f8  jmp     short loc_18005A489
0x18005a4fa  mov     [rsp+48h+arg_0], 0
0x18005a502  mov     rax, [rdi]
0x18005a505  lea     rcx, [rsp+48h+arg_0]
0x18005a50a  mov     [rsp+48h+var_28], rcx
0x18005a50f  mov     r9d, 7
0x18005a515  xor     r8d, r8d
0x18005a518  xor     edx, edx
0x18005a51a  mov     rcx, rdi
0x18005a51d  mov     rax, [rax+238h]
0x18005a524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a529  mov     rax, [rsi]
0x18005a52c  xor     r9d, r9d
0x18005a52f  lea     r8d, [r9+4]
0x18005a533  lea     rdx, [rsp+48h+arg_0]
0x18005a538  mov     rcx, rsi
0x18005a53b  mov     rax, [rax+20h]
0x18005a53f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a544  mov     ebx, eax
0x18005a546  test    eax, eax
0x18005a548  js      loc_18005A658
0x18005a54e  lea     rcx, [rdi+48h]; this
0x18005a552  call    ?GetLength@CDecorationPart@@QEAAKXZ; CDecorationPart::GetLength(void)
0x18005a557  mov     rcx, [rsi]
0x18005a55a  mov     r10, [rcx+20h]
0x18005a55e  xor     r9d, r9d
0x18005a561  mov     r8d, eax
0x18005a564  mov     rdx, [rdi+48h]
0x18005a568  mov     rcx, rsi
0x18005a56b  mov     rax, r10
0x18005a56e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a573  mov     ebx, eax
0x18005a575  test    eax, eax
0x18005a577  js      short loc_18005A5E0
0x18005a579  mov     rdx, [rdi+1C0h]
0x18005a580  mov     rax, [rsi]
0x18005a583  xor     r9d, r9d
0x18005a586  mov     r8d, [rdx]
0x18005a589  mov     rcx, rsi
0x18005a58c  mov     rax, [rax+20h]
0x18005a590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a595  mov     ebx, eax
0x18005a597  test    eax, eax
0x18005a599  js      loc_18005A6B9
0x18005a59f  mov     rdx, [rdi+0D8h]
0x18005a5a6  mov     rax, [rsi]
0x18005a5a9  xor     r9d, r9d
0x18005a5ac  mov     r8d, [rdx]
0x18005a5af  mov     rcx, rsi
0x18005a5b2  mov     rax, [rax+20h]
0x18005a5b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a5bb  mov     ebx, eax
0x18005a5bd  test    eax, eax
0x18005a5bf  js      loc_18005A6F2
0x18005a5c5  mov     rax, [rdi]
0x18005a5c8  xor     edx, edx
0x18005a5ca  mov     rcx, rdi
0x18005a5cd  mov     rax, [rax+120h]
0x18005a5d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a5d9  xor     eax, eax
0x18005a5db  jmp     loc_18005A495
0x18005a5e0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005a5e6  mov     edx, ebx
0x18005a5e8  mov     rcx, rax
0x18005a5eb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005a5f1  lea     rcx, WPP_GLOBAL_Control
0x18005a5f8  mov     r10, cs:WPP_GLOBAL_Control
0x18005a5ff  cmp     r10, rcx
0x18005a602  jz      loc_18005A4EE
0x18005a608  test    byte ptr [r10+1Ch], 1
0x18005a60d  jz      loc_18005A4EE
0x18005a613  cmp     byte ptr [r10+19h], 2
0x18005a618  jb      loc_18005A4EE
0x18005a61e  mov     edx, 9Fh
0x18005a623  mov     r9d, ebx
0x18005a626  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x18005a62d  mov     rcx, [r10+10h]
0x18005a631  call    WPP_SF_d
0x18005a636  jmp     loc_18005A4EE
0x18005a63b  test    byte ptr [r10+1Ch], 1
0x18005a640  jz      loc_18005A4EE
0x18005a646  cmp     byte ptr [r10+19h], 2
0x18005a64b  jb      loc_18005A4EE
0x18005a651  mov     edx, 9Dh
0x18005a656  jmp     short loc_18005A623
0x18005a658  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005a65e  mov     edx, ebx
0x18005a660  mov     rcx, rax
0x18005a663  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005a669  lea     rcx, WPP_GLOBAL_Control
0x18005a670  mov     r10, cs:WPP_GLOBAL_Control
0x18005a677  cmp     r10, rcx
0x18005a67a  jz      short loc_18005A6AA
0x18005a67c  test    byte ptr [r10+1Ch], 1
0x18005a681  jz      short loc_18005A6AA
0x18005a683  cmp     byte ptr [r10+19h], 2
0x18005a688  jb      short loc_18005A6AA
0x18005a68a  mov     edx, 9Eh
0x18005a68f  jmp     short loc_18005A696
0x18005a691  mov     edx, 0A1h
0x18005a696  mov     r9d, ebx
0x18005a699  lea     r8, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids
0x18005a6a0  mov     rcx, [r10+10h]
0x18005a6a4  call    WPP_SF_d
0x18005a6a9  nop
0x18005a6aa  lea     rcx, [rsp+48h+arg_18]; this
0x18005a6af  call    ??1CLock@CWbemObject@@QEAA@XZ; CWbemObject::CLock::~CLock(void)
0x18005a6b4  jmp     loc_18005A493
0x18005a6b9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005a6bf  mov     edx, ebx
0x18005a6c1  mov     rcx, rax
0x18005a6c4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005a6ca  lea     rcx, WPP_GLOBAL_Control
0x18005a6d1  mov     r10, cs:WPP_GLOBAL_Control
0x18005a6d8  cmp     r10, rcx
0x18005a6db  jz      short loc_18005A6AA
0x18005a6dd  test    byte ptr [r10+1Ch], 1
0x18005a6e2  jz      short loc_18005A6AA
0x18005a6e4  cmp     byte ptr [r10+19h], 2
0x18005a6e9  jb      short loc_18005A6AA
0x18005a6eb  mov     edx, 0A0h
0x18005a6f0  jmp     short loc_18005A696
0x18005a6f2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005a6f8  mov     edx, ebx
0x18005a6fa  mov     rcx, rax
0x18005a6fd  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005a703  lea     rcx, WPP_GLOBAL_Control
0x18005a70a  mov     r10, cs:WPP_GLOBAL_Control
0x18005a711  cmp     r10, rcx
0x18005a714  jz      short loc_18005A6AA
0x18005a716  test    byte ptr [r10+1Ch], 1
0x18005a71b  jz      short loc_18005A6AA
0x18005a71d  cmp     byte ptr [r10+19h], 2
0x18005a722  jb      short loc_18005A6AA
0x18005a724  jmp     loc_18005A691
```
