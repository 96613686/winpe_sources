# CGameStatistics::Create(GAMESTATS_OPEN_RESULT *,IGameStatistics * *)

- ea: `0x180002788`
- end: `0x180002846`
- name: `?Create@CGameStatistics@@SAJPEAW4GAMESTATS_OPEN_RESULT@@PEAPEAUIGameStatistics@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(enum GAMESTATS_OPEN_RESULT *, struct IGameStatistics **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800029d0`

## callees

- `0x180001268`
- `0x180002580`
- `0x180002788`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall CGameStatistics::Create(enum GAMESTATS_OPEN_RESULT *a1, struct IGameStatistics **a2)
{
  CGameStatistics *v5; // rax
  CGameStatistics *v6; // rdi
  unsigned int v7; // ebx

  if ( !a2 )
    return 2147942487LL;
  *a2 = 0;
  v5 = (CGameStatistics *)operator new(0x10u);
  v6 = v5;
  if ( v5 )
  {
    CGameStatistics::CGameStatistics(v5);
    *(_QWORD *)v6 = &ATL::CComObject<CGameStatistics>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    (*(void (__fastcall **)(CGameStatistics *))(*(_QWORD *)v6 + 8LL))(v6);
    v7 = (**(__int64 (__fastcall ***)(CGameStatistics *, GUID *, struct IGameStatistics **))v6)(
           v6,
           &GUID_3887c9ca_04a0_42ae_bc4c_5fa6c7721145,
           a2);
    (*(void (__fastcall **)(CGameStatistics *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( a1 )
      *a1 = GAMESTATS_OPEN_CREATED;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v7;
}

```

## disassembly

```asm
0x180002788  mov     [rsp+arg_0], rbx
0x18000278d  mov     [rsp+arg_8], rsi
0x180002792  push    rdi
0x180002793  sub     rsp, 20h
0x180002797  mov     rbx, rdx
0x18000279a  mov     rsi, rcx
0x18000279d  test    rdx, rdx
0x1800027a0  jnz     short loc_1800027AC
0x1800027a2  mov     eax, 80070057h
0x1800027a7  jmp     loc_180002836
0x1800027ac  mov     ecx, 10h; Size
0x1800027b1  mov     qword ptr [rdx], 0
0x1800027b8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800027bd  mov     rdi, rax
0x1800027c0  test    rax, rax
0x1800027c3  jz      short loc_18000282F
0x1800027c5  mov     rcx, rax; this
0x1800027c8  call    ??0CGameStatistics@@QEAA@XZ; CGameStatistics::CGameStatistics(void)
0x1800027cd  lea     rcx, ??_7?$CComObject@VCGameStatistics@@@ATL@@6B@; const ATL::CComObject<CGameStatistics>::`vftable'
0x1800027d4  mov     [rdi], rcx
0x1800027d7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800027de  mov     rdx, [rcx]
0x1800027e1  mov     rax, [rdx+8]
0x1800027e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027ea  mov     rax, [rdi]
0x1800027ed  mov     rcx, rdi
0x1800027f0  mov     rax, [rax+8]
0x1800027f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027f9  mov     rax, [rdi]
0x1800027fc  lea     rdx, _GUID_3887c9ca_04a0_42ae_bc4c_5fa6c7721145
0x180002803  mov     r8, rbx
0x180002806  mov     rcx, rdi
0x180002809  mov     rax, [rax]
0x18000280c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002811  mov     rcx, [rdi]
0x180002814  mov     ebx, eax
0x180002816  mov     rax, [rcx+10h]
0x18000281a  mov     rcx, rdi
0x18000281d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002822  test    rsi, rsi
0x180002825  jz      short loc_180002834
0x180002827  mov     dword ptr [rsi], 0
0x18000282d  jmp     short loc_180002834
0x18000282f  mov     ebx, 8007000Eh
0x180002834  mov     eax, ebx
0x180002836  mov     rbx, [rsp+28h+arg_0]
0x18000283b  mov     rsi, [rsp+28h+arg_8]
0x180002840  add     rsp, 20h
0x180002844  pop     rdi
0x180002845  retn
```
