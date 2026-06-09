# CW32System::WriteFmtUserTypeStg(IStorage *,ushort,ushort *)

- ea: `0x180090f8c`
- end: `0x180090fea`
- name: `?WriteFmtUserTypeStg@CW32System@@SAJPEAUIStorage@@GPEAG@Z`
- size: `94`
- prototype: `__int64 __fastcall(struct IStorage *, unsigned __int16, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18005361c`

## callees

- `0x180041adc`
- `0x1800907ac`
- `0x180090f8c`
- `0x180092010`

## string_xrefs

- `0x180090fb0`: `WriteFmtUserTypeStg`

## pseudocode

```c
__int64 __fastcall CW32System::WriteFmtUserTypeStg(struct IStorage *a1, unsigned __int16 a2, unsigned __int16 *a3)
{
  struct COLE32_PROC *Ole32Procs; // rax
  __int64 (__fastcall **v7)(struct IStorage *, _QWORD, unsigned __int16 *); // rbx

  Ole32Procs = CThreadData::GetOle32Procs();
  v7 = (__int64 (__fastcall **)(struct IStorage *, _QWORD, unsigned __int16 *))((char *)Ole32Procs + 216);
  if ( !*((_QWORD *)Ole32Procs + 27) )
    SetProcAddr((FARPROC *)Ole32Procs + 27, 1, "WriteFmtUserTypeStg");
  if ( *v7 )
    return (*v7)(a1, a2, a3);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x180090f8c  push    rbx
0x180090f8e  push    rbp
0x180090f8f  push    rsi
0x180090f90  push    rdi
0x180090f91  sub     rsp, 28h
0x180090f95  mov     rdi, r8
0x180090f98  movzx   esi, dx
0x180090f9b  mov     rbp, rcx
0x180090f9e  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x180090fa3  lea     rbx, [rax+0D8h]
0x180090faa  cmp     qword ptr [rbx], 0
0x180090fae  jnz     short loc_180090FC4
0x180090fb0  lea     r8, aWritefmtuserty; "WriteFmtUserTypeStg"
0x180090fb7  mov     edx, 1
0x180090fbc  mov     rcx, rbx
0x180090fbf  call    SetProcAddr
0x180090fc4  mov     rax, [rbx]
0x180090fc7  test    rax, rax
0x180090fca  jz      short loc_180090FDC
0x180090fcc  mov     r8, rdi
0x180090fcf  movzx   edx, si
0x180090fd2  mov     rcx, rbp
0x180090fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090fda  jmp     short loc_180090FE1
0x180090fdc  mov     eax, 80004005h
0x180090fe1  add     rsp, 28h
0x180090fe5  pop     rdi
0x180090fe6  pop     rsi
0x180090fe7  pop     rbp
0x180090fe8  pop     rbx
0x180090fe9  retn
```
