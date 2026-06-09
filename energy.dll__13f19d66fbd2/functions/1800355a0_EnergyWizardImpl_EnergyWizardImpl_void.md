# EnergyWizardImpl::~EnergyWizardImpl(void)

- ea: `0x1800355a0`
- end: `0x18003564d`
- name: `??1EnergyWizardImpl@@QEAA@XZ`
- size: `173`
- prototype: `void __fastcall(EnergyWizardImpl *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18005e1b0`

## callees

- `0x18000b6f0`
- `0x180028510`
- `0x1800355a0`
- `0x18003bb60`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800355ea`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800355ea`

## pseudocode

```c
void __fastcall EnergyWizardImpl::~EnergyWizardImpl(EnergyWizardImpl *this)
{
  _QWORD *i; // rbx
  _QWORD **v3; // rcx
  _QWORD *v4; // rsi
  _QWORD *v5; // rbx

  for ( i = *(_QWORD **)this; i != *((_QWORD **)this + 1); ++i )
  {
    if ( *i )
      (**(void (__fastcall ***)(_QWORD, __int64))*i)(*i, 1);
  }
  if ( *(_QWORD *)this != *((_QWORD *)this + 1) )
    *((_QWORD *)this + 1) = *(_QWORD *)this;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v3 = (_QWORD **)*((_QWORD *)this + 15);
  *v3[1] = 0;
  v4 = *v3;
  if ( *v3 )
  {
    do
    {
      v5 = (_QWORD *)*v4;
      std::pair<std::wstring const,unsigned long>::~pair<std::wstring const,unsigned long>(v4 + 2);
      std::_Deallocate<16>(v4, 0x30u);
      v4 = v5;
    }
    while ( v5 );
  }
  std::_Deallocate<16>(*((void **)this + 15), 0x30u);
  std::vector<Troubleshooter *>::_Tidy(this);
}

```

## disassembly

```asm
0x1800355a0  mov     [rsp+arg_0], rbx
0x1800355a5  mov     [rsp+arg_8], rsi
0x1800355aa  push    rdi
0x1800355ab  sub     rsp, 20h
0x1800355af  mov     rbx, [rcx]
0x1800355b2  mov     rdi, rcx
0x1800355b5  cmp     rbx, [rdi+8]
0x1800355b9  jz      short loc_1800355D9
0x1800355bb  mov     rcx, [rbx]
0x1800355be  test    rcx, rcx
0x1800355c1  jz      short loc_1800355D3
0x1800355c3  mov     rax, [rcx]
0x1800355c6  mov     edx, 1
0x1800355cb  mov     rax, [rax]
0x1800355ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800355d3  add     rbx, 8
0x1800355d7  jmp     short loc_1800355B5
0x1800355d9  mov     rax, [rdi]
0x1800355dc  cmp     rax, [rdi+8]
0x1800355e0  jz      short loc_1800355E6
0x1800355e2  mov     [rdi+8], rax
0x1800355e6  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800355ea  call    cs:__imp_DeleteCriticalSection
0x1800355f0  mov     rcx, [rdi+78h]
0x1800355f4  mov     rax, [rcx+8]
0x1800355f8  mov     qword ptr [rax], 0
0x1800355ff  mov     rsi, [rcx]
0x180035602  test    rsi, rsi
0x180035605  jz      short loc_180035628
0x180035607  mov     rbx, [rsi]
0x18003560a  lea     rcx, [rsi+10h]; void *
0x18003560e  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring const,ulong>::~pair<std::wstring const,ulong>(void)
0x180035613  mov     edx, 30h ; '0'
0x180035618  mov     rcx, rsi
0x18003561b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180035620  mov     rsi, rbx
0x180035623  test    rbx, rbx
0x180035626  jnz     short loc_180035607
0x180035628  mov     rcx, [rdi+78h]
0x18003562c  mov     edx, 30h ; '0'
0x180035631  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180035636  mov     rcx, rdi
0x180035639  mov     rbx, [rsp+28h+arg_0]
0x18003563e  mov     rsi, [rsp+28h+arg_8]
0x180035643  add     rsp, 20h
0x180035647  pop     rdi
0x180035648  jmp     ?_Tidy@?$vector@PEAVTroubleshooter@@V?$allocator@PEAVTroubleshooter@@@std@@@std@@AEAAXXZ; std::vector<Troubleshooter *>::_Tidy(void)
```
