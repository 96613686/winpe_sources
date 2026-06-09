# CPackage::DAdvise(tagFORMATETC *,ulong,IAdviseSink *,ulong *)

- ea: `0x1800048d0`
- end: `0x180004947`
- name: `?DAdvise@CPackage@@UEAAJPEAUtagFORMATETC@@KPEAUIAdviseSink@@PEAK@Z`
- size: `119`
- prototype: `__int64 __fastcall(unsigned __int64 this, struct tagFORMATETC *, unsigned int, struct IAdviseSink *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800048d0`
- `0x18000e010`

## import_xrefs

- `ole32!CreateDataAdviseHolder` at `0x1800048f7`
- `ole32!CreateDataAdviseHolder` at `0x1800048f7`

## pseudocode

```c
__int64 __fastcall CPackage::DAdvise(
        unsigned __int64 this,
        struct tagFORMATETC *a2,
        unsigned int a3,
        struct IAdviseSink *a4,
        unsigned int *a5)
{
  _QWORD *v5; // rbx

  v5 = (_QWORD *)(this + 128);
  if ( *(_QWORD *)(this + 128) || CreateDataAdviseHolder((LPDATAADVISEHOLDER *)(this + 128)) >= 0 )
    return (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct tagFORMATETC *, _QWORD, struct IAdviseSink *, unsigned int *))(*(_QWORD *)*v5 + 24LL))(
             *v5,
             this & ((unsigned __int128)-(__int128)(this - 32) >> 64),
             a2,
             a3,
             a4,
             a5);
  else
    return 2147942414LL;
}

```

## disassembly

```asm
0x1800048d0  push    rbx
0x1800048d2  push    rbp
0x1800048d3  push    rsi
0x1800048d4  push    rdi
0x1800048d5  push    r14
0x1800048d7  sub     rsp, 40h
0x1800048db  lea     rbx, [rcx+80h]
0x1800048e2  mov     rsi, r9
0x1800048e5  cmp     qword ptr [rbx], 0
0x1800048e9  mov     ebp, r8d
0x1800048ec  mov     r14, rdx
0x1800048ef  mov     rdi, rcx
0x1800048f2  jnz     short loc_180004908
0x1800048f4  mov     rcx, rbx; ppDAHolder
0x1800048f7  call    cs:__imp_CreateDataAdviseHolder
0x1800048fd  test    eax, eax
0x1800048ff  jns     short loc_180004908
0x180004901  mov     eax, 8007000Eh
0x180004906  jmp     short loc_18000493C
0x180004908  mov     rcx, [rbx]
0x18000490b  lea     rax, [rdi-20h]
0x18000490f  neg     rax
0x180004912  mov     r9d, ebp
0x180004915  sbb     rdx, rdx
0x180004918  mov     r8, [rcx]
0x18000491b  and     rdx, rdi
0x18000491e  mov     rax, [r8+18h]
0x180004922  mov     r8, [rsp+68h+arg_20]
0x18000492a  mov     [rsp+68h+var_40], r8
0x18000492f  mov     r8, r14
0x180004932  mov     [rsp+68h+var_48], rsi
0x180004937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000493c  add     rsp, 40h
0x180004940  pop     r14
0x180004942  pop     rdi
0x180004943  pop     rsi
0x180004944  pop     rbp
0x180004945  pop     rbx
0x180004946  retn
```
