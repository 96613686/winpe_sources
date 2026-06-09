# RxGetCurrentServerSilo

- ea: `0x140051130`
- end: `0x140051186`
- name: `RxGetCurrentServerSilo`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140051130`

## import_xrefs

- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x14005113d`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x14005113d`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140051167`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x140051167`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14005114d`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14005114d`

## pseudocode

```c
__int64 RxGetCurrentServerSilo()
{
  __int64 CurrentServerSilo; // rax
  __int64 v2; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  if ( (unsigned __int8)PsIsCurrentThreadInServerSilo()
    && (CurrentServerSilo = PsGetCurrentServerSilo(),
        (int)PsGetPermanentSiloContext(CurrentServerSilo, (unsigned int)g_RxSiloContextSlot, &v2) >= 0) )
  {
    return v2;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x140051130  sub     rsp, 28h
0x140051134  mov     [rsp+28h+arg_0], 0
0x14005113d  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x140051144  nop     dword ptr [rax+rax+00h]
0x140051149  test    al, al
0x14005114b  jz      short loc_14005117E
0x14005114d  call    cs:__imp_PsGetCurrentServerSilo
0x140051154  nop     dword ptr [rax+rax+00h]
0x140051159  mov     edx, cs:g_RxSiloContextSlot
0x14005115f  lea     r8, [rsp+28h+arg_0]
0x140051164  mov     rcx, rax
0x140051167  call    cs:__imp_PsGetPermanentSiloContext
0x14005116e  nop     dword ptr [rax+rax+00h]
0x140051173  test    eax, eax
0x140051175  js      short loc_14005117E
0x140051177  mov     rax, [rsp+28h+arg_0]
0x14005117c  jmp     short loc_140051180
0x14005117e  xor     eax, eax
0x140051180  add     rsp, 28h
0x140051184  retn
```
