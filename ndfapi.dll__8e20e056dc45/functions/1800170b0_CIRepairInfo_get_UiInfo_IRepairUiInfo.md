# CIRepairInfo::get_UiInfo(IRepairUiInfo * *)

- ea: `0x1800170b0`
- end: `0x180017160`
- name: `?get_UiInfo@CIRepairInfo@@UEAAJPEAPEAUIRepairUiInfo@@@Z`
- size: `176`
- prototype: `__int64 __fastcall(CIRepairInfo *__hidden this, struct IRepairUiInfo **)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180012704`
- `0x1800170b0`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall CIRepairInfo::get_UiInfo(CIRepairInfo *this, struct IRepairUiInfo **a2)
{
  __int64 v2; // rax
  int v6; // ecx
  __int64 v7; // rdi
  __int64 v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // [rsp+50h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 10);
  if ( !v2 )
    return 2147942421LL;
  if ( (*(_DWORD *)(v2 + 56) & 0xFFFFFFFA) == 0 && *(_DWORD *)(v2 + 56) != 5 )
    return 2147500033LL;
  v10 = 0;
  v6 = ATL::CComCreator<ATL::CComObject<CIRepairUiInfo>>::CreateInstance((__int64)this, (__int64)a2, &v10);
  if ( v6 >= 0 )
  {
    v7 = v10;
    v8 = *((_QWORD *)this + 8);
    *(_QWORD *)(v10 + 72) = *((_QWORD *)this + 10) + 56LL;
    if ( *(_QWORD *)(v7 + 64) != v8 )
    {
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
      v9 = *(_QWORD *)(v7 + 64);
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      *(_QWORD *)(v7 + 64) = v8;
    }
    v6 = 0;
    *a2 = (struct IRepairUiInfo *)v10;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800170b0  push    rbx
0x1800170b2  push    rsi
0x1800170b3  push    rdi
0x1800170b4  push    r14
0x1800170b6  sub     rsp, 28h
0x1800170ba  mov     rax, [rcx+50h]
0x1800170be  mov     r14, rdx
0x1800170c1  mov     rsi, rcx
0x1800170c4  test    rax, rax
0x1800170c7  jnz     short loc_1800170D3
0x1800170c9  mov     eax, 80070015h
0x1800170ce  jmp     loc_180017156
0x1800170d3  test    dword ptr [rax+38h], 0FFFFFFFAh
0x1800170da  jnz     short loc_1800170E9
0x1800170dc  cmp     dword ptr [rax+38h], 5
0x1800170e0  jz      short loc_1800170E9
0x1800170e2  mov     eax, 80004001h
0x1800170e7  jmp     short loc_180017156
0x1800170e9  lea     r8, [rsp+48h+arg_0]
0x1800170ee  mov     [rsp+48h+arg_0], 0
0x1800170f7  call    ?CreateInstance@?$CComCreator@V?$CComObject@VCIRepairUiInfo@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CIRepairUiInfo>>::CreateInstance(void *,_GUID const &,void * *)
0x1800170fc  mov     ecx, eax
0x1800170fe  test    eax, eax
0x180017100  js      short loc_180017154
0x180017102  mov     rdi, [rsp+48h+arg_0]
0x180017107  mov     rax, [rsi+50h]
0x18001710b  mov     rbx, [rsi+40h]
0x18001710f  add     rax, 38h ; '8'
0x180017113  mov     [rdi+48h], rax
0x180017117  cmp     [rdi+40h], rbx
0x18001711b  jz      short loc_18001714A
0x18001711d  test    rbx, rbx
0x180017120  jz      short loc_180017131
0x180017122  mov     rax, [rbx]
0x180017125  mov     rcx, rbx
0x180017128  mov     rax, [rax+8]
0x18001712c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017131  mov     rcx, [rdi+40h]
0x180017135  test    rcx, rcx
0x180017138  jz      short loc_180017146
0x18001713a  mov     rax, [rcx]
0x18001713d  mov     rax, [rax+10h]
0x180017141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017146  mov     [rdi+40h], rbx
0x18001714a  mov     rax, [rsp+48h+arg_0]
0x18001714f  xor     ecx, ecx
0x180017151  mov     [r14], rax
0x180017154  mov     eax, ecx
0x180017156  add     rsp, 28h
0x18001715a  pop     r14
0x18001715c  pop     rdi
0x18001715d  pop     rsi
0x18001715e  pop     rbx
0x18001715f  retn
```
