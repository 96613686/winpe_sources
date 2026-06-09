# MakeUniqueNoThrow<FveEasUtil,std::shared_ptr<IBackupStatusCache> &,std::shared_ptr<IBackupStatusCache> &,bool &>(std::unique_ptr<FveEasUtil,std::default_delete<FveEasUtil>> &,std::shared_ptr<IBackupStatusCache> &,std::shared_ptr<IBackupStatusCache> &,bool &)

- ea: `0x1800239c8`
- end: `0x180023a38`
- name: `??$MakeUniqueNoThrow@VFveEasUtil@@AEAV?$shared_ptr@VIBackupStatusCache@@@std@@AEAV23@AEA_N@@YAJAEAV?$unique_ptr@VFveEasUtil@@U?$default_delete@VFveEasUtil@@@std@@@std@@AEAV?$shared_ptr@VIBackupStatusCache@@@1@1AEA_N@Z`
- size: `112`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180027a3c`

## callees

- `0x180001c00`
- `0x1800239c8`
- `0x180023ce8`
- `0x180023efc`

## pseudocode

```c
__int64 __fastcall MakeUniqueNoThrow<FveEasUtil,std::shared_ptr<IBackupStatusCache> &,std::shared_ptr<IBackupStatusCache> &,bool &>(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        _BYTE *a4)
{
  unsigned int v8; // ebx
  void *v9; // rax
  __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r10
  char v14; // r8
  __int64 v15; // rdx

  try
  {
    v8 = 0;
    v9 = operator new(0x38u);
    LOBYTE(v10) = *a4;
    std::shared_ptr<IBackupStatusCache>::shared_ptr<IBackupStatusCache>(v9, a2, v10);
    std::shared_ptr<IBackupStatusCache>::shared_ptr<IBackupStatusCache>(v11 + 16, a3, v12);
    *(_QWORD *)(v13 + 32) = 0;
    *(_QWORD *)(v13 + 40) = 0;
    *(_BYTE *)(v13 + 48) = v14;
    v15 = *a1;
    *a1 = v13;
    if ( v15 )
      std::default_delete<FveEasUtil>::operator()();
  }
  catch ( std::bad_alloc )
  {
    return (unsigned int)-2147024882;
  }
  v8 = 0;
}

```

## disassembly

```asm
0x1800239c8  push    rbx
0x1800239ca  push    rsi
0x1800239cb  push    rdi
0x1800239cc  push    r14
0x1800239ce  push    r15
0x1800239d0  sub     rsp, 30h
0x1800239d4  mov     rsi, r9
0x1800239d7  mov     r14, r8
0x1800239da  mov     r15, rdx
0x1800239dd  mov     rdi, rcx
0x1800239e0  xor     ebx, ebx
0x1800239e2  lea     ecx, [rbx+38h]; Size
0x1800239e5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800239ea  mov     r10, rax
0x1800239ed  mov     r8b, [rsi]
0x1800239f0  mov     rdx, r15
0x1800239f3  mov     rcx, rax
0x1800239f6  call    ??0?$shared_ptr@VIBackupStatusCache@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<IBackupStatusCache>::shared_ptr<IBackupStatusCache>(std::shared_ptr<IBackupStatusCache> const &)
0x1800239fb  lea     rcx, [rcx+10h]
0x1800239ff  mov     rdx, r14
0x180023a02  call    ??0?$shared_ptr@VIBackupStatusCache@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<IBackupStatusCache>::shared_ptr<IBackupStatusCache>(std::shared_ptr<IBackupStatusCache> const &)
0x180023a07  mov     [r10+20h], rbx
0x180023a0b  mov     [r10+28h], rbx
0x180023a0f  mov     [r10+30h], r8b
0x180023a13  mov     rdx, [rdi]
0x180023a16  mov     [rdi], r10
0x180023a19  test    rdx, rdx
0x180023a1c  jz      short loc_180023A24
0x180023a1e  call    ??R?$default_delete@VFveEasUtil@@@std@@QEBAXPEAVFveEasUtil@@@Z; std::default_delete<FveEasUtil>::operator()(FveEasUtil *)
0x180023a23  nop
0x180023a24  jmp     short loc_180023A2A
0x180023a26  mov     ebx, [rsp+58h+var_38]
0x180023a2a  mov     eax, ebx
0x180023a2c  add     rsp, 30h
0x180023a30  pop     r15
0x180023a32  pop     r14
0x180023a34  pop     rdi
0x180023a35  pop     rsi
0x180023a36  pop     rbx
0x180023a37  retn
```
