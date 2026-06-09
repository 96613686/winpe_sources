# EdpKRpcWriteNetworkAppLearningEvt

- ea: `0x18000b7e0`
- end: `0x18000b879`
- name: `EdpKRpcWriteNetworkAppLearningEvt`
- size: `153`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000b7e0`
- `0x18000c244`

## import_xrefs

- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000b84b`
- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000b84b`
- `EFSCORE!EfsDllDisabled` at `0x18000b828`
- `EFSCORE!EfsDllDisabled` at `0x18000b828`
- `EFSCORE!EdpWriteAppLearningLog` at `0x18000b83a`
- `EFSCORE!EdpWriteAppLearningLog` at `0x18000b83a`

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
0x18000b7e0  mov     rax, rsp
0x18000b7e3  mov     [rax+8], rbx
0x18000b7e7  push    rdi
0x18000b7e8  sub     rsp, 30h
0x18000b7ec  mov     rbx, rdx
0x18000b7ef  mov     dword ptr [rax-18h], 0
0x18000b7f6  lea     rdx, [rax+20h]
0x18000b7fa  mov     dword ptr [rax+20h], 0
0x18000b801  mov     edi, r8d
0x18000b804  call    EfspValidateClientCall
0x18000b809  test    eax, eax
0x18000b80b  jnz     short loc_18000B869
0x18000b80d  cmp     [rsp+38h+arg_18], eax
0x18000b811  jz      short loc_18000B869
0x18000b813  test    rbx, rbx
0x18000b816  jnz     short loc_18000B81F
0x18000b818  mov     eax, 0C000000Dh
0x18000b81d  jmp     short loc_18000B86E
0x18000b81f  cmp     cs:EfsServerInitialized, 0
0x18000b826  jz      short loc_18000B862
0x18000b828  call    cs:__imp_EfsDllDisabled
0x18000b82e  test    al, al
0x18000b830  jnz     short loc_18000B862
0x18000b832  mov     r8d, edi
0x18000b835  mov     dl, 1
0x18000b837  mov     rcx, rbx
0x18000b83a  call    cs:__imp_EdpWriteAppLearningLog
0x18000b840  test    eax, eax
0x18000b842  jz      short loc_18000B85C
0x18000b844  lea     rdx, [rsp+38h+var_18]
0x18000b849  mov     ecx, eax
0x18000b84b  call    cs:__imp_EfsDllErrorToNtStatus
0x18000b851  test    eax, eax
0x18000b853  jnz     short loc_18000B85C
0x18000b855  mov     eax, 0C0000001h
0x18000b85a  jmp     short loc_18000B86E
0x18000b85c  mov     eax, [rsp+38h+var_18]
0x18000b860  jmp     short loc_18000B86E
0x18000b862  mov     eax, 0C00000BBh
0x18000b867  jmp     short loc_18000B86E
0x18000b869  mov     eax, 0C0000022h
0x18000b86e  mov     rbx, [rsp+38h+arg_0]
0x18000b873  add     rsp, 30h
0x18000b877  pop     rdi
0x18000b878  retn
```
