# EdpKRpcWriteNetworkAppLearningEvt

- ea: `0x18000c470`
- end: `0x18000c51c`
- name: `EdpKRpcWriteNetworkAppLearningEvt`
- size: `172`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000c470`
- `0x18000d03c`

## import_xrefs

- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000c4e7`
- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000c4e7`
- `EFSCORE!EfsDllDisabled` at `0x18000c4b8`
- `EFSCORE!EfsDllDisabled` at `0x18000c4b8`
- `EFSCORE!EdpWriteAppLearningLog` at `0x18000c4d0`
- `EFSCORE!EdpWriteAppLearningLog` at `0x18000c4d0`

## pseudocode

```c
__int64 __fastcall EdpKRpcWriteNetworkAppLearningEvt(void *a1)
{
  EfspValidateClientCall(a1);
  return 3221225506LL;
}

```

## disassembly

```asm
0x18000c470  mov     rax, rsp
0x18000c473  mov     [rax+8], rbx
0x18000c477  push    rdi
0x18000c478  sub     rsp, 30h
0x18000c47c  mov     rbx, rdx
0x18000c47f  mov     dword ptr [rax-18h], 0
0x18000c486  lea     rdx, [rax+20h]
0x18000c48a  mov     dword ptr [rax+20h], 0
0x18000c491  mov     edi, r8d
0x18000c494  call    EfspValidateClientCall
0x18000c499  test    eax, eax
0x18000c49b  jnz     short loc_18000C50B
0x18000c49d  cmp     [rsp+38h+arg_18], eax
0x18000c4a1  jz      short loc_18000C50B
0x18000c4a3  test    rbx, rbx
0x18000c4a6  jnz     short loc_18000C4AF
0x18000c4a8  mov     eax, 0C000000Dh
0x18000c4ad  jmp     short loc_18000C510
0x18000c4af  cmp     cs:EfsServerInitialized, 0
0x18000c4b6  jz      short loc_18000C504
0x18000c4b8  call    cs:__imp_EfsDllDisabled
0x18000c4bf  nop     dword ptr [rax+rax+00h]
0x18000c4c4  test    al, al
0x18000c4c6  jnz     short loc_18000C504
0x18000c4c8  mov     r8d, edi
0x18000c4cb  mov     dl, 1
0x18000c4cd  mov     rcx, rbx
0x18000c4d0  call    cs:__imp_EdpWriteAppLearningLog
0x18000c4d7  nop     dword ptr [rax+rax+00h]
0x18000c4dc  test    eax, eax
0x18000c4de  jz      short loc_18000C4FE
0x18000c4e0  lea     rdx, [rsp+38h+var_18]
0x18000c4e5  mov     ecx, eax
0x18000c4e7  call    cs:__imp_EfsDllErrorToNtStatus
0x18000c4ee  nop     dword ptr [rax+rax+00h]
0x18000c4f3  test    eax, eax
0x18000c4f5  jnz     short loc_18000C4FE
0x18000c4f7  mov     eax, 0C0000001h
0x18000c4fc  jmp     short loc_18000C510
0x18000c4fe  mov     eax, [rsp+38h+var_18]
0x18000c502  jmp     short loc_18000C510
0x18000c504  mov     eax, 0C00000BBh
0x18000c509  jmp     short loc_18000C510
0x18000c50b  mov     eax, 0C0000022h
0x18000c510  mov     rbx, [rsp+38h+arg_0]
0x18000c515  add     rsp, 30h
0x18000c519  pop     rdi
0x18000c51a  retn
```
