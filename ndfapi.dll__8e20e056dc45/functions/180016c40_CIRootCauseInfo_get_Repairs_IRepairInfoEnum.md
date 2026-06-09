# CIRootCauseInfo::get_Repairs(IRepairInfoEnum * *)

- ea: `0x180016c40`
- end: `0x180016d0d`
- name: `?get_Repairs@CIRootCauseInfo@@UEAAJPEAPEAUIRepairInfoEnum@@@Z`
- size: `205`
- prototype: `__int64 __fastcall(CIRootCauseInfo *__hidden this, struct IRepairInfoEnum **)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800125e4`
- `0x180016c40`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall CIRootCauseInfo::get_Repairs(CIRootCauseInfo *this, struct IRepairInfoEnum **a2)
{
  int v5; // ebx
  __int64 v6; // rdx
  struct IRepairInfoEnum *v7; // rbx
  __int64 v8; // rdi
  int v9; // ecx
  __int64 v10; // rcx
  struct IRepairInfoEnum *v11; // [rsp+50h] [rbp+8h] BYREF

  if ( !*((_QWORD *)this + 9) )
    return 2147942421LL;
  v11 = 0;
  v5 = ATL::CComCreator<ATL::CComObject<CIRepairInfoEnum>>::CreateInstance((__int64)this, (__int64)a2, &v11);
  if ( v5 >= 0 )
  {
    v6 = *((_QWORD *)this + 9);
    v7 = v11;
    v8 = *((_QWORD *)this + 8);
    v9 = *(unsigned __int16 *)(v6 + 56);
    *((_QWORD *)v11 + 9) = *(_QWORD *)(v6 + 48);
    *((_DWORD *)v7 + 20) = v9;
    *((_QWORD *)v7 + 11) = v6;
    if ( *((_QWORD *)v7 + 8) != v8 )
    {
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
      v10 = *((_QWORD *)v7 + 8);
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      *((_QWORD *)v7 + 8) = v8;
    }
    v5 = (*(__int64 (__fastcall **)(struct IRepairInfoEnum *))(*(_QWORD *)v7 + 64LL))(v7);
    if ( v5 < 0 )
      (*(void (__fastcall **)(struct IRepairInfoEnum *))(*(_QWORD *)v11 + 16LL))(v11);
    else
      *a2 = v11;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180016c40  push    rbx
0x180016c42  push    rsi
0x180016c43  push    rdi
0x180016c44  push    r14
0x180016c46  sub     rsp, 28h
0x180016c4a  cmp     qword ptr [rcx+48h], 0
0x180016c4f  mov     r14, rdx
0x180016c52  mov     rsi, rcx
0x180016c55  jnz     short loc_180016C61
0x180016c57  mov     eax, 80070015h
0x180016c5c  jmp     loc_180016D03
0x180016c61  lea     r8, [rsp+48h+arg_0]
0x180016c66  mov     [rsp+48h+arg_0], 0
0x180016c6f  call    ?CreateInstance@?$CComCreator@V?$CComObject@VCIRepairInfoEnum@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CIRepairInfoEnum>>::CreateInstance(void *,_GUID const &,void * *)
0x180016c74  mov     ebx, eax
0x180016c76  test    eax, eax
0x180016c78  js      loc_180016D01
0x180016c7e  mov     rdx, [rsi+48h]
0x180016c82  mov     rbx, [rsp+48h+arg_0]
0x180016c87  mov     rdi, [rsi+40h]
0x180016c8b  movzx   ecx, word ptr [rdx+38h]
0x180016c8f  mov     rax, [rdx+30h]
0x180016c93  mov     [rbx+48h], rax
0x180016c97  mov     [rbx+50h], ecx
0x180016c9a  mov     [rbx+58h], rdx
0x180016c9e  cmp     [rbx+40h], rdi
0x180016ca2  jz      short loc_180016CD1
0x180016ca4  test    rdi, rdi
0x180016ca7  jz      short loc_180016CB8
0x180016ca9  mov     rax, [rdi]
0x180016cac  mov     rcx, rdi
0x180016caf  mov     rax, [rax+8]
0x180016cb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cb8  mov     rcx, [rbx+40h]
0x180016cbc  test    rcx, rcx
0x180016cbf  jz      short loc_180016CCD
0x180016cc1  mov     rax, [rcx]
0x180016cc4  mov     rax, [rax+10h]
0x180016cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ccd  mov     [rbx+40h], rdi
0x180016cd1  mov     rax, [rbx]
0x180016cd4  mov     rcx, rbx
0x180016cd7  mov     rax, [rax+40h]
0x180016cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ce0  mov     ebx, eax
0x180016ce2  test    eax, eax
0x180016ce4  js      short loc_180016CF0
0x180016ce6  mov     rax, [rsp+48h+arg_0]
0x180016ceb  mov     [r14], rax
0x180016cee  jmp     short loc_180016D01
0x180016cf0  mov     rcx, [rsp+48h+arg_0]
0x180016cf5  mov     rax, [rcx]
0x180016cf8  mov     rax, [rax+10h]
0x180016cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d01  mov     eax, ebx
0x180016d03  add     rsp, 28h
0x180016d07  pop     r14
0x180016d09  pop     rdi
0x180016d0a  pop     rsi
0x180016d0b  pop     rbx
0x180016d0c  retn
```
