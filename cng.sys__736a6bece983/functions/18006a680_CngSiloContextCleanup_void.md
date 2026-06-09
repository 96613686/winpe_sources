# CngSiloContextCleanup(void *)

- ea: `0x18006a680`
- end: `0x18006a718`
- name: `?CngSiloContextCleanup@@YAXPEAX@Z`
- size: `152`
- prototype: `void __fastcall(void *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18006d088`
- `0x18006d310`

## callees

- `0x180018e40`
- `0x18006a680`
- `0x180070284`
- `0x180071074`
- `0x1800724e0`
- `0x180072a64`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x18006a705`
- `ntoskrnl!ExDeleteResourceLite` at `0x18006a705`

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
0x18006a680  test    rcx, rcx
0x18006a683  jz      locret_18006A716
0x18006a689  push    rbx
0x18006a68a  sub     rsp, 20h
0x18006a68e  mov     eax, [rcx]
0x18006a690  mov     rbx, rcx
0x18006a693  test    al, 8
0x18006a695  jz      short loc_18006A6A0
0x18006a697  add     rcx, 8; Resource
0x18006a69b  call    PrvReg_Shutdown
0x18006a6a0  mov     eax, [rbx]
0x18006a6a2  test    al, 10h
0x18006a6a4  jz      short loc_18006A6B2
0x18006a6a6  lea     rcx, [rbx+88h]; Resource
0x18006a6ad  call    CfgReg_Shutdown
0x18006a6b2  mov     eax, [rbx]
0x18006a6b4  test    al, 4
0x18006a6b6  jz      short loc_18006A6C4
0x18006a6b8  mov     rcx, [rbx+1A8h]; P
0x18006a6bf  call    RegKeyNotificationCleanup
0x18006a6c4  mov     eax, [rbx]
0x18006a6c6  test    al, 2
0x18006a6c8  jz      short loc_18006A6D6
0x18006a6ca  mov     rcx, [rbx+108h]; P
0x18006a6d1  call    CcnDestroyPublisher
0x18006a6d6  mov     eax, [rbx]
0x18006a6d8  test    al, 1
0x18006a6da  jz      short loc_18006A711
0x18006a6dc  mov     rcx, [rbx+180h]; P
0x18006a6e3  test    rcx, rcx
0x18006a6e6  jz      short loc_18006A6ED
0x18006a6e8  call    BCryptFree
0x18006a6ed  mov     rcx, [rbx+198h]; P
0x18006a6f4  test    rcx, rcx
0x18006a6f7  jz      short loc_18006A6FE
0x18006a6f9  call    BCryptFree
0x18006a6fe  lea     rcx, [rbx+110h]; Resource
0x18006a705  call    cs:__imp_ExDeleteResourceLite
0x18006a70c  nop     dword ptr [rax+rax+00h]
0x18006a711  add     rsp, 20h
0x18006a715  pop     rbx
0x18006a716  retn
```
