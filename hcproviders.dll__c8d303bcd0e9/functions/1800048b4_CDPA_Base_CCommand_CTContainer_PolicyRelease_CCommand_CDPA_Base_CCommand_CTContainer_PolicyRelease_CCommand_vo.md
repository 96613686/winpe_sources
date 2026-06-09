# CDPA_Base<CCommand,CTContainer_PolicyRelease<CCommand>>::~CDPA_Base<CCommand,CTContainer_PolicyRelease<CCommand>>(void)

- ea: `0x1800048b4`
- end: `0x18000490d`
- name: `??1?$CDPA_Base@VCCommand@@V?$CTContainer_PolicyRelease@VCCommand@@@@@@QEAA@XZ`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004894`

## callees

- `0x1800037a0`
- `0x1800048b4`

## import_xrefs

- `COMCTL32!__imp_DPA_Destroy` at `0x1800048f3`
- `COMCTL32!__imp_DPA_Destroy` at `0x1800048f3`
- `COMCTL32!__imp_DPA_DestroyCallback` at `0x1800048de`
- `COMCTL32!__imp_DPA_DestroyCallback` at `0x1800048de`

## pseudocode

```c
void __fastcall CDPA_Base<CCommand,CTContainer_PolicyRelease<CCommand>>::~CDPA_Base<CCommand,CTContainer_PolicyRelease<CCommand>>(
        HDPA *a1)
{
  if ( *a1 && !IsProcessShutdownInProgress() )
  {
    if ( *a1 )
    {
      DPA_DestroyCallback(*a1, CDPA_Base<CCommand,CTContainer_PolicyRelease<CCommand>>::_StandardDestroyCB, 0);
      *a1 = 0;
      DPA_Destroy(0);
      *a1 = 0;
    }
  }
}

```

## disassembly

```asm
0x1800048b4  push    rbx
0x1800048b6  sub     rsp, 20h
0x1800048ba  cmp     qword ptr [rcx], 0
0x1800048be  mov     rbx, rcx
0x1800048c1  jz      short loc_180004906
0x1800048c3  call    ?IsProcessShutdownInProgress@@YA_NXZ; IsProcessShutdownInProgress(void)
0x1800048c8  test    al, al
0x1800048ca  jnz     short loc_180004906
0x1800048cc  mov     rcx, [rbx]; hdpa
0x1800048cf  test    rcx, rcx
0x1800048d2  jz      short loc_180004906
0x1800048d4  xor     r8d, r8d; pData
0x1800048d7  lea     rdx, ?_StandardDestroyCB@?$CDPA_Base@VCCommand@@V?$CTContainer_PolicyRelease@VCCommand@@@@@@CAHPEAVCCommand@@PEAX@Z; pfnCB
0x1800048de  call    cs:__imp_DPA_DestroyCallback
0x1800048e5  nop     dword ptr [rax+rax+00h]
0x1800048ea  xor     ecx, ecx; hdpa
0x1800048ec  mov     qword ptr [rbx], 0
0x1800048f3  call    cs:__imp_DPA_Destroy
0x1800048fa  nop     dword ptr [rax+rax+00h]
0x1800048ff  mov     qword ptr [rbx], 0
0x180004906  add     rsp, 20h
0x18000490a  pop     rbx
0x18000490b  retn
```
