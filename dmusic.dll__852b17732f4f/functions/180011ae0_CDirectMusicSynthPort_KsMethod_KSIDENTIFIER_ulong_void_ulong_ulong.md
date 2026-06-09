# CDirectMusicSynthPort::KsMethod(KSIDENTIFIER *,ulong,void *,ulong,ulong *)

- ea: `0x180011ae0`
- end: `0x180011b8d`
- name: `?KsMethod@CDirectMusicSynthPort@@UEAAJPEAUKSIDENTIFIER@@KPEAXKPEAK@Z`
- size: `173`
- prototype: `__int64 __fastcall(CDirectMusicSynthPort *__hidden this, struct KSIDENTIFIER *, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180011ae0`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CDirectMusicSynthPort::KsMethod(
        CDirectMusicSynthPort *this,
        struct KSIDENTIFIER *a2,
        unsigned int a3,
        void *a4,
        unsigned int a5,
        unsigned int *a6)
{
  __int64 result; // rax
  __int64 v11; // rcx
  __int64 v12; // rcx

  if ( a3 && !a2 || !a6 )
    return 2147500035LL;
  if ( !*((_QWORD *)this + 2) )
    return 2289570100LL;
  v11 = *((_QWORD *)this + 4);
  result = 2289570082LL;
  if ( !v11
    || (result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 32LL))(v11), (_DWORD)result == -2005397214) )
  {
    v12 = *((_QWORD *)this + 5);
    if ( v12 )
      return (*(__int64 (__fastcall **)(__int64, struct KSIDENTIFIER *, _QWORD, void *, unsigned int, unsigned int *))(*(_QWORD *)v12 + 32LL))(
               v12,
               a2,
               a3,
               a4,
               a5,
               a6);
  }
  return result;
}

```

## disassembly

```asm
0x180011ae0  push    rbx
0x180011ae2  push    rbp
0x180011ae3  push    rsi
0x180011ae4  push    rdi
0x180011ae5  push    r14
0x180011ae7  push    r15
0x180011ae9  sub     rsp, 48h
0x180011aed  mov     r15, r9
0x180011af0  mov     ebp, r8d
0x180011af3  mov     rsi, rdx
0x180011af6  mov     rbx, rcx
0x180011af9  test    r8d, r8d
0x180011afc  jz      short loc_180011B03
0x180011afe  test    rdx, rdx
0x180011b01  jz      short loc_180011B10
0x180011b03  mov     rdi, [rsp+78h+arg_28]
0x180011b0b  test    rdi, rdi
0x180011b0e  jnz     short loc_180011B17
0x180011b10  mov     eax, 80004003h
0x180011b15  jmp     short loc_180011B80
0x180011b17  cmp     qword ptr [rcx+10h], 0
0x180011b1c  jnz     short loc_180011B25
0x180011b1e  mov     eax, 88781134h
0x180011b23  jmp     short loc_180011B80
0x180011b25  mov     rcx, [rcx+20h]
0x180011b29  mov     eax, 88781122h
0x180011b2e  mov     r14d, [rsp+78h+arg_20]
0x180011b36  test    rcx, rcx
0x180011b39  jz      short loc_180011B58
0x180011b3b  mov     rax, [rcx]
0x180011b3e  mov     [rsp+78h+var_50], rdi
0x180011b43  mov     [rsp+78h+var_58], r14d
0x180011b48  mov     rax, [rax+20h]
0x180011b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b51  cmp     eax, 88781122h
0x180011b56  jnz     short loc_180011B80
0x180011b58  mov     rcx, [rbx+28h]
0x180011b5c  test    rcx, rcx
0x180011b5f  jz      short loc_180011B80
0x180011b61  mov     rax, [rcx]
0x180011b64  mov     r9, r15
0x180011b67  mov     [rsp+78h+var_50], rdi
0x180011b6c  mov     r8d, ebp
0x180011b6f  mov     rdx, rsi
0x180011b72  mov     [rsp+78h+var_58], r14d
0x180011b77  mov     rax, [rax+20h]
0x180011b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b80  add     rsp, 48h
0x180011b84  pop     r15
0x180011b86  pop     r14
0x180011b88  pop     rdi
0x180011b89  pop     rsi
0x180011b8a  pop     rbp
0x180011b8b  pop     rbx
0x180011b8c  retn
```
