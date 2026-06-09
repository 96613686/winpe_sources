# CPackage::Advise(IAdviseSink *,ulong *)

- ea: `0x180004fb0`
- end: `0x180005004`
- name: `?Advise@CPackage@@UEAAJPEAUIAdviseSink@@PEAK@Z`
- size: `84`
- prototype: `HRESULT __fastcall(CPackage *this, struct IAdviseSink *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004fb0`
- `0x18000e010`

## import_xrefs

- `ole32!CreateOleAdviseHolder` at `0x180004fd5`
- `ole32!CreateOleAdviseHolder` at `0x180004fd5`

## pseudocode

```c
HRESULT __fastcall CPackage::Advise(CPackage *this, struct IAdviseSink *a2, unsigned int *a3)
{
  _QWORD *v3; // rbx
  HRESULT result; // eax

  v3 = (_QWORD *)((char *)this + 152);
  if ( *((_QWORD *)this + 19) )
    return (*(__int64 (__fastcall **)(_QWORD, struct IAdviseSink *, unsigned int *))(*(_QWORD *)*v3 + 24LL))(
             *v3,
             a2,
             a3);
  result = CreateOleAdviseHolder((LPOLEADVISEHOLDER *)this + 19);
  if ( result >= 0 )
    return (*(__int64 (__fastcall **)(_QWORD, struct IAdviseSink *, unsigned int *))(*(_QWORD *)*v3 + 24LL))(
             *v3,
             a2,
             a3);
  return result;
}

```

## disassembly

```asm
0x180004fb0  mov     [rsp+arg_0], rbx
0x180004fb5  mov     [rsp+arg_8], rsi
0x180004fba  push    rdi
0x180004fbb  sub     rsp, 20h
0x180004fbf  lea     rbx, [rcx+98h]
0x180004fc6  mov     rdi, r8
0x180004fc9  cmp     qword ptr [rbx], 0
0x180004fcd  mov     rsi, rdx
0x180004fd0  jnz     short loc_180004FDF
0x180004fd2  mov     rcx, rbx; ppOAHolder
0x180004fd5  call    cs:__imp_CreateOleAdviseHolder
0x180004fdb  test    eax, eax
0x180004fdd  js      short loc_180004FF4
0x180004fdf  mov     rcx, [rbx]
0x180004fe2  mov     r8, rdi
0x180004fe5  mov     rdx, rsi
0x180004fe8  mov     rax, [rcx]
0x180004feb  mov     rax, [rax+18h]
0x180004fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ff4  mov     rbx, [rsp+28h+arg_0]
0x180004ff9  mov     rsi, [rsp+28h+arg_8]
0x180004ffe  add     rsp, 20h
0x180005002  pop     rdi
0x180005003  retn
```
