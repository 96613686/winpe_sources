# ATL::CSession::Open(ATL::CDataSource const &,tagDBPROPSET *,ulong)

- ea: `0x18000985c`
- end: `0x1800098f2`
- name: `?Open@CSession@ATL@@QEAAJAEBVCDataSource@2@PEAUtagDBPROPSET@@K@Z`
- size: `150`
- prototype: `__int64 __fastcall(ATL::CSession *this, const struct ATL::CDataSource *, struct tagDBPROPSET *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800099e4`

## callees

- `0x18000985c`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CSession::Open(ATL::CSession *this, const struct ATL::CDataSource *a2, struct tagDBPROPSET *a3)
{
  int v4; // ebx
  __int64 v6; // [rsp+50h] [rbp+18h] BYREF

  v6 = 0;
  v4 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))a2)(
         *(_QWORD *)a2,
         &GUID_0c733a5d_2a1c_11ce_ade5_00aa0044773d,
         &v6);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, ATL::CSession *))(*(_QWORD *)v6 + 24LL))(
           v6,
           0,
           &GUID_0c733a69_2a1c_11ce_ade5_00aa0044773d,
           this);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  else if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000985c  mov     r11, rsp
0x18000985f  mov     [r11+8], rbx
0x180009863  mov     [r11+18h], r8
0x180009867  push    rdi
0x180009868  sub     rsp, 30h
0x18000986c  mov     rdi, rcx
0x18000986f  mov     qword ptr [r11+18h], 0
0x180009877  mov     rcx, [rdx]
0x18000987a  mov     rax, [rcx]
0x18000987d  lea     r8, [r11+18h]
0x180009881  lea     rdx, _GUID_0c733a5d_2a1c_11ce_ade5_00aa0044773d
0x180009888  mov     rax, [rax]
0x18000988b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009890  mov     ebx, eax
0x180009892  test    eax, eax
0x180009894  jns     short loc_1800098AF
0x180009896  mov     rcx, [rsp+38h+arg_10]
0x18000989b  test    rcx, rcx
0x18000989e  jz      short loc_1800098AD
0x1800098a0  mov     rdx, [rcx]
0x1800098a3  mov     rax, [rdx+10h]
0x1800098a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098ac  nop
0x1800098ad  jmp     short loc_1800098E5
0x1800098af  mov     rcx, [rsp+38h+arg_10]
0x1800098b4  mov     rax, [rcx]
0x1800098b7  mov     r9, rdi
0x1800098ba  lea     r8, _GUID_0c733a69_2a1c_11ce_ade5_00aa0044773d
0x1800098c1  xor     edx, edx
0x1800098c3  mov     rax, [rax+18h]
0x1800098c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098cc  mov     ebx, eax
0x1800098ce  mov     rcx, [rsp+38h+arg_10]
0x1800098d3  test    rcx, rcx
0x1800098d6  jz      short loc_1800098E5
0x1800098d8  mov     rdx, [rcx]
0x1800098db  mov     rax, [rdx+10h]
0x1800098df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098e4  nop
0x1800098e5  mov     eax, ebx
0x1800098e7  mov     rbx, [rsp+38h+arg_0]
0x1800098ec  add     rsp, 30h
0x1800098f0  pop     rdi
0x1800098f1  retn
```
