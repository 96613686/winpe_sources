# CIRepairInfoEnum::get_Next(IRepairInfo * *)

- ea: `0x180016810`
- end: `0x1800168e4`
- name: `?get_Next@CIRepairInfoEnum@@UEAAJPEAPEAUIRepairInfo@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(CIRepairInfoEnum *__hidden this, struct IRepairInfo **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800124a4`
- `0x180016810`
- `0x18001e244`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall CIRepairInfoEnum::get_Next(CIRepairInfoEnum *this, struct IRepairInfo **a2)
{
  int v5; // ecx
  __int64 v6; // rdi
  __int64 v7; // rsi
  __int64 v8; // rdx
  __int64 v9; // rcx
  DiagnosisTextParserImpl *v10; // rcx
  int v11; // ecx
  BOOL v12; // eax
  __int64 v13; // [rsp+50h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 21) >= *((_DWORD *)this + 20) )
    return 2147745794LL;
  v13 = 0;
  v5 = ATL::CComCreator<ATL::CComObject<CIRepairInfo>>::CreateInstance((__int64)this, (__int64)a2, &v13);
  if ( v5 >= 0 )
  {
    v6 = v13;
    v7 = *((_QWORD *)this + 8);
    v8 = *((_QWORD *)this + 11);
    *(_QWORD *)(v13 + 80) = *((_QWORD *)this + 9) + 120LL * *((unsigned int *)this + 21);
    *(_QWORD *)(v6 + 72) = v8;
    if ( *(_QWORD *)(v6 + 64) != v7 )
    {
      if ( v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
      v9 = *(_QWORD *)(v6 + 64);
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      *(_QWORD *)(v6 + 64) = v7;
    }
    v10 = *(DiagnosisTextParserImpl **)(v6 + 96);
    if ( v10 )
      v11 = DiagnosisTextParserImpl::SetXML(v10, *(const unsigned __int16 **)(*(_QWORD *)(v6 + 80) + 24LL));
    else
      v11 = -2147024882;
    v12 = v11 == 0;
    v5 = 0;
    *(_DWORD *)(v6 + 88) = v12;
    *a2 = (struct IRepairInfo *)v13;
    ++*((_DWORD *)this + 21);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180016810  push    rbx
0x180016812  push    rsi
0x180016813  push    rdi
0x180016814  push    r14
0x180016816  sub     rsp, 28h
0x18001681a  mov     eax, [rcx+50h]
0x18001681d  mov     r14, rdx
0x180016820  mov     rbx, rcx
0x180016823  cmp     [rcx+54h], eax
0x180016826  jb      short loc_180016832
0x180016828  mov     eax, 80040002h
0x18001682d  jmp     loc_1800168DA
0x180016832  lea     r8, [rsp+48h+arg_0]
0x180016837  mov     [rsp+48h+arg_0], 0
0x180016840  call    ?CreateInstance@?$CComCreator@V?$CComObject@VCIRepairInfo@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CIRepairInfo>>::CreateInstance(void *,_GUID const &,void * *)
0x180016845  mov     ecx, eax
0x180016847  test    eax, eax
0x180016849  js      loc_1800168D8
0x18001684f  mov     eax, [rbx+54h]
0x180016852  mov     rdi, [rsp+48h+arg_0]
0x180016857  mov     rsi, [rbx+40h]
0x18001685b  mov     rdx, [rbx+58h]
0x18001685f  imul    rcx, rax, 78h ; 'x'
0x180016863  add     rcx, [rbx+48h]
0x180016867  mov     [rdi+50h], rcx
0x18001686b  mov     [rdi+48h], rdx
0x18001686f  cmp     [rdi+40h], rsi
0x180016873  jz      short loc_1800168A2
0x180016875  test    rsi, rsi
0x180016878  jz      short loc_180016889
0x18001687a  mov     rax, [rsi]
0x18001687d  mov     rcx, rsi
0x180016880  mov     rax, [rax+8]
0x180016884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016889  mov     rcx, [rdi+40h]
0x18001688d  test    rcx, rcx
0x180016890  jz      short loc_18001689E
0x180016892  mov     rax, [rcx]
0x180016895  mov     rax, [rax+10h]
0x180016899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001689e  mov     [rdi+40h], rsi
0x1800168a2  mov     rcx, [rdi+60h]; this
0x1800168a6  test    rcx, rcx
0x1800168a9  jz      short loc_1800168BC
0x1800168ab  mov     rdx, [rdi+50h]
0x1800168af  mov     rdx, [rdx+18h]; unsigned __int16 *
0x1800168b3  call    ?SetXML@DiagnosisTextParserImpl@@QEAAJPEBG@Z; DiagnosisTextParserImpl::SetXML(ushort const *)
0x1800168b8  mov     ecx, eax
0x1800168ba  jmp     short loc_1800168C1
0x1800168bc  mov     ecx, 8007000Eh
0x1800168c1  xor     eax, eax
0x1800168c3  test    ecx, ecx
0x1800168c5  setz    al
0x1800168c8  xor     ecx, ecx
0x1800168ca  mov     [rdi+58h], eax
0x1800168cd  mov     rax, [rsp+48h+arg_0]
0x1800168d2  mov     [r14], rax
0x1800168d5  inc     dword ptr [rbx+54h]
0x1800168d8  mov     eax, ecx
0x1800168da  add     rsp, 28h
0x1800168de  pop     r14
0x1800168e0  pop     rdi
0x1800168e1  pop     rsi
0x1800168e2  pop     rbx
0x1800168e3  retn
```
