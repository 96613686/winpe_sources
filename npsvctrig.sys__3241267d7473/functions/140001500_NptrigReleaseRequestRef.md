# NptrigReleaseRequestRef

- ea: `0x140001500`
- end: `0x14000156c`
- name: `NptrigReleaseRequestRef`
- size: `108`
- prototype: `void __fastcall(volatile signed __int32 *P, __int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1400013e0`
- `0x140008520`
- `0x140008ed0`
- `0x140009da0`
- `0x140009fa0`

## callees

- `0x140001220`
- `0x140001500`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140001554`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001554`

## pseudocode

```c
void __fastcall NptrigReleaseRequestRef(volatile signed __int32 *P, __int64 a2, __int64 a3)
{
  signed __int32 v4; // ebx

  v4 = _InterlockedDecrement(P + 28);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 37, a3, P, v4);
  if ( !v4 )
    ExFreePoolWithTag((PVOID)P, 0x6774704Eu);
}

```

## disassembly

```asm
0x140001500  mov     [rsp+arg_0], rbx
0x140001505  push    rdi
0x140001506  sub     rsp, 30h
0x14000150a  mov     rdi, rcx
0x14000150d  mov     ebx, 0FFFFFFFFh
0x140001512  lock xadd [rcx+70h], ebx
0x140001517  dec     ebx
0x140001519  mov     rcx, cs:WPP_GLOBAL_Control
0x140001520  lea     rax, WPP_GLOBAL_Control
0x140001527  cmp     rcx, rax
0x14000152a  jz      short loc_140001548
0x14000152c  mov     eax, [rcx+2Ch]
0x14000152f  test    al, 4
0x140001531  jz      short loc_140001548
0x140001533  mov     rcx, [rcx+18h]
0x140001537  mov     edx, 25h ; '%'
0x14000153c  mov     r9, rdi
0x14000153f  mov     [rsp+38h+var_18], ebx
0x140001543  call    WPP_SF_qd
0x140001548  test    ebx, ebx
0x14000154a  jnz     short loc_140001560
0x14000154c  mov     edx, 6774704Eh; Tag
0x140001551  mov     rcx, rdi; P
0x140001554  call    cs:__imp_ExFreePoolWithTag
0x14000155b  nop     dword ptr [rax+rax+00h]
0x140001560  mov     rbx, [rsp+38h+arg_0]
0x140001565  add     rsp, 30h
0x140001569  pop     rdi
0x14000156a  retn
```
