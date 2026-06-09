# CDPA_Base<ushort,CTContainer_PolicyCoTaskMem>::~CDPA_Base<ushort,CTContainer_PolicyCoTaskMem>(void)

- ea: `0x14000a600`
- end: `0x14000a68d`
- name: `??1?$CDPA_Base@GVCTContainer_PolicyCoTaskMem@@@@QEAA@XZ`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000a694`

## callees

- `0x140001be4`
- `0x140001bf0`
- `0x14000a600`
- `0x140010010`

## import_xrefs

- `COMCTL32!__imp_DPA_Destroy` at `0x14000a67a`
- `COMCTL32!__imp_DPA_Destroy` at `0x14000a67a`
- `COMCTL32!__imp_DPA_DestroyCallback` at `0x14000a66b`
- `COMCTL32!__imp_DPA_DestroyCallback` at `0x14000a66b`

## string_xrefs

- `0x14000a61b`: `ntdll.dll`
- `0x14000a62c`: `RtlDllShutdownInProgress`

## pseudocode

```c
void __fastcall CDPA_Base<unsigned short,CTContainer_PolicyCoTaskMem>::~CDPA_Base<unsigned short,CTContainer_PolicyCoTaskMem>(
        HDPA *a1)
{
  unsigned __int8 (*RtlDllShutdownInProgress)(void); // rax
  HMODULE ModuleHandleW_0; // rax

  if ( *a1 )
  {
    if ( (RtlDllShutdownInProgress = (unsigned __int8 (*)(void))qword_140016878) == 0
      && ((ModuleHandleW_0 = GetModuleHandleW_0(L"ntdll.dll")) == 0
        ? (RtlDllShutdownInProgress = (unsigned __int8 (*)(void))qword_140016878)
        : (unsigned __int8 (*)(void))(RtlDllShutdownInProgress = (unsigned __int8 (*)(void))GetProcAddress_0(
                                                                                              ModuleHandleW_0,
                                                                                              "RtlDllShutdownInProgress"),
                                      qword_140016878 = (__int64)RtlDllShutdownInProgress),
          !RtlDllShutdownInProgress)
      || !RtlDllShutdownInProgress() )
    {
      if ( *a1 )
      {
        DPA_DestroyCallback(
          *a1,
          (PFNDAENUMCALLBACK)CDPA_Base<unsigned short,CTContainer_PolicyCoTaskMem>::_StandardDestroyCB,
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
0x14000a600  push    rbx
0x14000a602  sub     rsp, 20h
0x14000a606  cmp     qword ptr [rcx], 0
0x14000a60a  mov     rbx, rcx
0x14000a60d  jz      short loc_14000A687
0x14000a60f  mov     rax, cs:qword_140016878
0x14000a616  test    rax, rax
0x14000a619  jnz     short loc_14000A650
0x14000a61b  lea     rcx, aNtdllDll; "ntdll.dll"
0x14000a622  call    GetModuleHandleW_0
0x14000a627  test    rax, rax
0x14000a62a  jz      short loc_14000A644
0x14000a62c  lea     rdx, aRtldllshutdown; "RtlDllShutdownInProgress"
0x14000a633  mov     rcx, rax; hModule
0x14000a636  call    GetProcAddress_0
0x14000a63b  mov     cs:qword_140016878, rax
0x14000a642  jmp     short loc_14000A64B
0x14000a644  mov     rax, cs:qword_140016878
0x14000a64b  test    rax, rax
0x14000a64e  jz      short loc_14000A659
0x14000a650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a655  test    al, al
0x14000a657  jnz     short loc_14000A687
0x14000a659  mov     rcx, [rbx]; hdpa
0x14000a65c  test    rcx, rcx
0x14000a65f  jz      short loc_14000A687
0x14000a661  xor     r8d, r8d; pData
0x14000a664  lea     rdx, ?_StandardDestroyCB@?$CDPA_Base@GVCTContainer_PolicyCoTaskMem@@@@CAHPEAGPEAX@Z; pfnCB
0x14000a66b  call    cs:__imp_DPA_DestroyCallback
0x14000a671  xor     ecx, ecx; hdpa
0x14000a673  mov     qword ptr [rbx], 0
0x14000a67a  call    cs:__imp_DPA_Destroy
0x14000a680  mov     qword ptr [rbx], 0
0x14000a687  add     rsp, 20h
0x14000a68b  pop     rbx
0x14000a68c  retn
```
