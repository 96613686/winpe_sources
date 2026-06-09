# CDPA_Base<CSurrogateFactory,CTContainer_PolicyUnOwned<CSurrogateFactory>>::~CDPA_Base<CSurrogateFactory,CTContainer_PolicyUnOwned<CSurrogateFactory>>(void)

- ea: `0x140002790`
- end: `0x14000281d`
- name: `??1?$CDPA_Base@VCSurrogateFactory@@V?$CTContainer_PolicyUnOwned@VCSurrogateFactory@@@@@@QEAA@XZ`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140004c60`

## callees

- `0x1400010e2`
- `0x1400010ee`
- `0x140002790`
- `0x140006010`

## import_xrefs

- `COMCTL32!__imp_DPA_Destroy` at `0x14000280a`
- `COMCTL32!__imp_DPA_Destroy` at `0x14000280a`
- `COMCTL32!__imp_DPA_DestroyCallback` at `0x1400027fb`
- `COMCTL32!__imp_DPA_DestroyCallback` at `0x1400027fb`

## string_xrefs

- `0x1400027ab`: `ntdll.dll`
- `0x1400027bc`: `RtlDllShutdownInProgress`

## pseudocode

```c
void __fastcall CDPA_Base<CSurrogateFactory,CTContainer_PolicyUnOwned<CSurrogateFactory>>::~CDPA_Base<CSurrogateFactory,CTContainer_PolicyUnOwned<CSurrogateFactory>>(
        HDPA *a1)
{
  unsigned __int8 (*RtlDllShutdownInProgress)(void); // rax
  HMODULE ModuleHandleW_0; // rax

  if ( *a1 )
  {
    if ( (RtlDllShutdownInProgress = (unsigned __int8 (*)(void))qword_14000A2F0) == 0
      && ((ModuleHandleW_0 = GetModuleHandleW_0(L"ntdll.dll")) == 0
        ? (RtlDllShutdownInProgress = (unsigned __int8 (*)(void))qword_14000A2F0)
        : (unsigned __int8 (*)(void))(RtlDllShutdownInProgress = (unsigned __int8 (*)(void))GetProcAddress_0(
                                                                                              ModuleHandleW_0,
                                                                                              "RtlDllShutdownInProgress"),
                                      qword_14000A2F0 = (__int64)RtlDllShutdownInProgress),
          !RtlDllShutdownInProgress)
      || !RtlDllShutdownInProgress() )
    {
      if ( *a1 )
      {
        DPA_DestroyCallback(
          *a1,
          CDPA_Base<CSurrogateFactory,CTContainer_PolicyUnOwned<CSurrogateFactory>>::_StandardDestroyCB,
          0);
        *a1 = 0;
        DPA_Destroy(0);
        *a1 = 0;
      }
    }
  }
}

```

## disassembly

```asm
0x140002790  push    rbx
0x140002792  sub     rsp, 20h
0x140002796  cmp     qword ptr [rcx], 0
0x14000279a  mov     rbx, rcx
0x14000279d  jz      short loc_140002817
0x14000279f  mov     rax, cs:qword_14000A2F0
0x1400027a6  test    rax, rax
0x1400027a9  jnz     short loc_1400027E0
0x1400027ab  lea     rcx, ModuleName; "ntdll.dll"
0x1400027b2  call    GetModuleHandleW_0
0x1400027b7  test    rax, rax
0x1400027ba  jz      short loc_1400027D4
0x1400027bc  lea     rdx, ProcName; "RtlDllShutdownInProgress"
0x1400027c3  mov     rcx, rax; hModule
0x1400027c6  call    GetProcAddress_0
0x1400027cb  mov     cs:qword_14000A2F0, rax
0x1400027d2  jmp     short loc_1400027DB
0x1400027d4  mov     rax, cs:qword_14000A2F0
0x1400027db  test    rax, rax
0x1400027de  jz      short loc_1400027E9
0x1400027e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400027e5  test    al, al
0x1400027e7  jnz     short loc_140002817
0x1400027e9  mov     rcx, [rbx]; hdpa
0x1400027ec  test    rcx, rcx
0x1400027ef  jz      short loc_140002817
0x1400027f1  xor     r8d, r8d; pData
0x1400027f4  lea     rdx, ?_StandardDestroyCB@?$CDPA_Base@VCSurrogateFactory@@V?$CTContainer_PolicyUnOwned@VCSurrogateFactory@@@@@@CAHPEAVCSurrogateFactory@@PEAX@Z; pfnCB
0x1400027fb  call    cs:__imp_DPA_DestroyCallback
0x140002801  xor     ecx, ecx; hdpa
0x140002803  mov     qword ptr [rbx], 0
0x14000280a  call    cs:__imp_DPA_Destroy
0x140002810  mov     qword ptr [rbx], 0
0x140002817  add     rsp, 20h
0x14000281b  pop     rbx
0x14000281c  retn
```
