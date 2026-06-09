# CngSiloContextCleanup(void *)

- ea: `0x180073e20`
- end: `0x180073eb8`
- name: `?CngSiloContextCleanup@@YAXPEAX@Z`
- size: `152`
- prototype: `void __fastcall(void *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180076828`
- `0x180076ab0`

## callees

- `0x180025ec0`
- `0x180073e20`
- `0x180079a24`
- `0x18007a814`
- `0x18007bc80`
- `0x18007c204`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x180073ea5`
- `ntoskrnl!ExDeleteResourceLite` at `0x180073ea5`

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
0x180073e20  test    rcx, rcx
0x180073e23  jz      locret_180073EB6
0x180073e29  push    rbx
0x180073e2a  sub     rsp, 20h
0x180073e2e  mov     eax, [rcx]
0x180073e30  mov     rbx, rcx
0x180073e33  test    al, 8
0x180073e35  jz      short loc_180073E40
0x180073e37  add     rcx, 8; Resource
0x180073e3b  call    PrvReg_Shutdown
0x180073e40  mov     eax, [rbx]
0x180073e42  test    al, 10h
0x180073e44  jz      short loc_180073E52
0x180073e46  lea     rcx, [rbx+88h]; Resource
0x180073e4d  call    CfgReg_Shutdown
0x180073e52  mov     eax, [rbx]
0x180073e54  test    al, 4
0x180073e56  jz      short loc_180073E64
0x180073e58  mov     rcx, [rbx+1A8h]; P
0x180073e5f  call    RegKeyNotificationCleanup
0x180073e64  mov     eax, [rbx]
0x180073e66  test    al, 2
0x180073e68  jz      short loc_180073E76
0x180073e6a  mov     rcx, [rbx+108h]; P
0x180073e71  call    CcnDestroyPublisher
0x180073e76  mov     eax, [rbx]
0x180073e78  test    al, 1
0x180073e7a  jz      short loc_180073EB1
0x180073e7c  mov     rcx, [rbx+180h]; P
0x180073e83  test    rcx, rcx
0x180073e86  jz      short loc_180073E8D
0x180073e88  call    BCryptFree
0x180073e8d  mov     rcx, [rbx+198h]; P
0x180073e94  test    rcx, rcx
0x180073e97  jz      short loc_180073E9E
0x180073e99  call    BCryptFree
0x180073e9e  lea     rcx, [rbx+110h]; Resource
0x180073ea5  call    cs:__imp_ExDeleteResourceLite
0x180073eac  nop     dword ptr [rax+rax+00h]
0x180073eb1  add     rsp, 20h
0x180073eb5  pop     rbx
0x180073eb6  retn
```
