# EfsKRpcNotifyEnterpriseFileCleanup

- ea: `0x18000be00`
- end: `0x18000be8b`
- name: `EfsKRpcNotifyEnterpriseFileCleanup`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000be00`
- `0x18000c244`

## import_xrefs

- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000be63`
- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000be63`
- `EFSCORE!EfsDllDisabled` at `0x18000be28`
- `EFSCORE!EfsDllDisabled` at `0x18000be28`
- `EFSCORE!EdpDllServiceFileEncryptionQueue` at `0x18000be3c`
- `EFSCORE!EdpDllServiceFileEncryptionQueue` at `0x18000be3c`

## pseudocode

```c
__int64 __fastcall EfsKRpcNotifyEnterpriseFileCleanup(void *a1)
{
  __int64 v1; // rcx
  int v2; // eax
  __int64 v3; // rcx
  unsigned int v5; // [rsp+38h] [rbp+10h] BYREF

  v5 = 0;
  if ( (unsigned int)EfspValidateClientCall(a1) || !v5 )
    return 3221225506LL;
  if ( !EfsServerInitialized || (unsigned __int8)EfsDllDisabled(v1) )
    return 3221225659LL;
  v5 = 0;
  v2 = EdpDllServiceFileEncryptionQueue(0);
  if ( v2 >= 0 )
    return v5;
  v3 = (unsigned __int16)v2;
  if ( (v2 & 0x1FFF0000) != 0x70000 )
    v3 = 1359;
  if ( (unsigned int)EfsDllErrorToNtStatus(v3, &v5) )
    return v5;
  else
    return 3221225473LL;
}

```

## disassembly

```asm
0x18000be00  sub     rsp, 28h
0x18000be04  lea     rdx, [rsp+28h+arg_8]
0x18000be09  mov     [rsp+28h+arg_8], 0
0x18000be11  call    EfspValidateClientCall
0x18000be16  test    eax, eax
0x18000be18  jnz     short loc_18000BE81
0x18000be1a  cmp     [rsp+28h+arg_8], eax
0x18000be1e  jz      short loc_18000BE81
0x18000be20  cmp     cs:EfsServerInitialized, al
0x18000be26  jz      short loc_18000BE7A
0x18000be28  call    cs:__imp_EfsDllDisabled
0x18000be2e  test    al, al
0x18000be30  jnz     short loc_18000BE7A
0x18000be32  xor     ecx, ecx
0x18000be34  mov     [rsp+28h+arg_8], 0
0x18000be3c  call    cs:__imp_EdpDllServiceFileEncryptionQueue
0x18000be42  test    eax, eax
0x18000be44  jns     short loc_18000BE74
0x18000be46  mov     ecx, eax
0x18000be48  and     ecx, 1FFF0000h
0x18000be4e  cmp     ecx, 70000h
0x18000be54  movzx   ecx, ax
0x18000be57  jz      short loc_18000BE5E
0x18000be59  mov     ecx, 54Fh
0x18000be5e  lea     rdx, [rsp+28h+arg_8]
0x18000be63  call    cs:__imp_EfsDllErrorToNtStatus
0x18000be69  test    eax, eax
0x18000be6b  jnz     short loc_18000BE74
0x18000be6d  mov     eax, 0C0000001h
0x18000be72  jmp     short loc_18000BE86
0x18000be74  mov     eax, [rsp+28h+arg_8]
0x18000be78  jmp     short loc_18000BE86
0x18000be7a  mov     eax, 0C00000BBh
0x18000be7f  jmp     short loc_18000BE86
0x18000be81  mov     eax, 0C0000022h
0x18000be86  add     rsp, 28h
0x18000be8a  retn
```
