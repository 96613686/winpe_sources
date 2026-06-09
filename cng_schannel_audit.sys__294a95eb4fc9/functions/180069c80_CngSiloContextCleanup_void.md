# CngSiloContextCleanup(void *)

- ea: `0x180069c80`
- end: `0x180069d18`
- name: `?CngSiloContextCleanup@@YAXPEAX@Z`
- size: `152`
- prototype: `void __fastcall(void *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18006c688`
- `0x18006c910`

## callees

- `0x18001bd90`
- `0x180069c80`
- `0x18006f884`
- `0x180070674`
- `0x180071ae0`
- `0x180072064`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x180069d05`
- `ntoskrnl!ExDeleteResourceLite` at `0x180069d05`

## pseudocode

```c
void __fastcall CngSiloContextCleanup(char *a1)
{
  void *v2; // rcx
  void *v3; // rcx

  if ( a1 )
  {
    if ( (*(_DWORD *)a1 & 8) != 0 )
      PrvReg_Shutdown((PERESOURCE)(a1 + 8));
    if ( (*(_DWORD *)a1 & 0x10) != 0 )
      CfgReg_Shutdown((PERESOURCE)(a1 + 136));
    if ( (*(_DWORD *)a1 & 4) != 0 )
      RegKeyNotificationCleanup(*((PVOID *)a1 + 53));
    if ( (*(_DWORD *)a1 & 2) != 0 )
      CcnDestroyPublisher(*((PVOID *)a1 + 33));
    if ( (*(_DWORD *)a1 & 1) != 0 )
    {
      v2 = (void *)*((_QWORD *)a1 + 48);
      if ( v2 )
        BCryptFree(v2);
      v3 = (void *)*((_QWORD *)a1 + 51);
      if ( v3 )
        BCryptFree(v3);
      ExDeleteResourceLite((PERESOURCE)(a1 + 272));
    }
  }
}

```

## disassembly

```asm
0x180069c80  test    rcx, rcx
0x180069c83  jz      locret_180069D16
0x180069c89  push    rbx
0x180069c8a  sub     rsp, 20h
0x180069c8e  mov     eax, [rcx]
0x180069c90  mov     rbx, rcx
0x180069c93  test    al, 8
0x180069c95  jz      short loc_180069CA0
0x180069c97  add     rcx, 8; Resource
0x180069c9b  call    PrvReg_Shutdown
0x180069ca0  mov     eax, [rbx]
0x180069ca2  test    al, 10h
0x180069ca4  jz      short loc_180069CB2
0x180069ca6  lea     rcx, [rbx+88h]; Resource
0x180069cad  call    CfgReg_Shutdown
0x180069cb2  mov     eax, [rbx]
0x180069cb4  test    al, 4
0x180069cb6  jz      short loc_180069CC4
0x180069cb8  mov     rcx, [rbx+1A8h]; P
0x180069cbf  call    RegKeyNotificationCleanup
0x180069cc4  mov     eax, [rbx]
0x180069cc6  test    al, 2
0x180069cc8  jz      short loc_180069CD6
0x180069cca  mov     rcx, [rbx+108h]; P
0x180069cd1  call    CcnDestroyPublisher
0x180069cd6  mov     eax, [rbx]
0x180069cd8  test    al, 1
0x180069cda  jz      short loc_180069D11
0x180069cdc  mov     rcx, [rbx+180h]; P
0x180069ce3  test    rcx, rcx
0x180069ce6  jz      short loc_180069CED
0x180069ce8  call    BCryptFree
0x180069ced  mov     rcx, [rbx+198h]; P
0x180069cf4  test    rcx, rcx
0x180069cf7  jz      short loc_180069CFE
0x180069cf9  call    BCryptFree
0x180069cfe  lea     rcx, [rbx+110h]; Resource
0x180069d05  call    cs:__imp_ExDeleteResourceLite
0x180069d0c  nop     dword ptr [rax+rax+00h]
0x180069d11  add     rsp, 20h
0x180069d15  pop     rbx
0x180069d16  retn
```
