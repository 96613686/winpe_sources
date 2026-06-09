# EfsKRpcNotifyEnterpriseFileWrite

- ea: `0x18000cbf0`
- end: `0x18000ccef`
- name: `EfsKRpcNotifyEnterpriseFileWrite`
- size: `255`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000cbf0`
- `0x18000d03c`

## import_xrefs

- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000ccbb`
- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000ccbb`
- `EFSCORE!EdpDllQueueFileForEncryption` at `0x18000cc8e`
- `EFSCORE!EdpDllQueueFileForEncryption` at `0x18000cc8e`
- `EFSCORE!EfsDllDisabled` at `0x18000cc60`
- `EFSCORE!EfsDllDisabled` at `0x18000cc60`

## pseudocode

```c
__int64 __fastcall EfsKRpcNotifyEnterpriseFileWrite(void *a1)
{
  EfspValidateClientCall(a1);
  return 3221225506LL;
}

```

## disassembly

```asm
0x18000cbf0  push    rbx
0x18000cbf2  push    rbp
0x18000cbf3  push    rsi
0x18000cbf4  push    r14
0x18000cbf6  sub     rsp, 48h
0x18000cbfa  mov     r14, rdx
0x18000cbfd  mov     [rsp+68h+var_38], 0
0x18000cc05  lea     rdx, [rsp+68h+var_38]
0x18000cc0a  mov     rbx, r9
0x18000cc0d  mov     rbp, r8
0x18000cc10  call    EfspValidateClientCall
0x18000cc15  test    eax, eax
0x18000cc17  jnz     loc_18000CCDF
0x18000cc1d  cmp     [rsp+68h+var_38], eax
0x18000cc21  jz      loc_18000CCDF
0x18000cc27  test    rbp, rbp
0x18000cc2a  jnz     short loc_18000CC45
0x18000cc2c  test    rbx, rbx
0x18000cc2f  jnz     short loc_18000CC3B
0x18000cc31  cmp     [rsp+68h+arg_20], rbx
0x18000cc39  jnz     short loc_18000CC4A
0x18000cc3b  mov     eax, 0C000000Dh
0x18000cc40  jmp     loc_18000CCE4
0x18000cc45  test    rbx, rbx
0x18000cc48  jmp     short loc_18000CC39
0x18000cc4a  mov     rsi, [rsp+68h+arg_28]
0x18000cc52  test    rsi, rsi
0x18000cc55  jz      short loc_18000CC3B
0x18000cc57  cmp     cs:EfsServerInitialized, 0
0x18000cc5e  jz      short loc_18000CCD8
0x18000cc60  call    cs:__imp_EfsDllDisabled
0x18000cc67  nop     dword ptr [rax+rax+00h]
0x18000cc6c  test    al, al
0x18000cc6e  jnz     short loc_18000CCD8
0x18000cc70  mov     r9, [rsp+68h+arg_20]
0x18000cc78  mov     r8, rbx
0x18000cc7b  mov     rdx, rbp
0x18000cc7e  mov     [rsp+68h+var_38], 0
0x18000cc86  mov     rcx, r14
0x18000cc89  mov     [rsp+68h+var_48], rsi
0x18000cc8e  call    cs:__imp_EdpDllQueueFileForEncryption
0x18000cc95  nop     dword ptr [rax+rax+00h]
0x18000cc9a  test    eax, eax
0x18000cc9c  jns     short loc_18000CCD2
0x18000cc9e  mov     ecx, eax
0x18000cca0  and     ecx, 1FFF0000h
0x18000cca6  cmp     ecx, 70000h
0x18000ccac  movzx   ecx, ax
0x18000ccaf  jz      short loc_18000CCB6
0x18000ccb1  mov     ecx, 54Fh
0x18000ccb6  lea     rdx, [rsp+68h+var_38]
0x18000ccbb  call    cs:__imp_EfsDllErrorToNtStatus
0x18000ccc2  nop     dword ptr [rax+rax+00h]
0x18000ccc7  test    eax, eax
0x18000ccc9  jnz     short loc_18000CCD2
0x18000cccb  mov     eax, 0C0000001h
0x18000ccd0  jmp     short loc_18000CCE4
0x18000ccd2  mov     eax, [rsp+68h+var_38]
0x18000ccd6  jmp     short loc_18000CCE4
0x18000ccd8  mov     eax, 0C00000BBh
0x18000ccdd  jmp     short loc_18000CCE4
0x18000ccdf  mov     eax, 0C0000022h
0x18000cce4  add     rsp, 48h
0x18000cce8  pop     r14
0x18000ccea  pop     rsi
0x18000cceb  pop     rbp
0x18000ccec  pop     rbx
0x18000cced  retn
```
