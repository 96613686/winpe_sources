# EfsKRpcNotifyEnterpriseFileCleanup

- ea: `0x18000cb40`
- end: `0x18000cbde`
- name: `EfsKRpcNotifyEnterpriseFileCleanup`
- size: `158`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000cb40`
- `0x18000d03c`

## import_xrefs

- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000cbaf`
- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000cbaf`
- `EFSCORE!EfsDllDisabled` at `0x18000cb68`
- `EFSCORE!EfsDllDisabled` at `0x18000cb68`
- `EFSCORE!EdpDllServiceFileEncryptionQueue` at `0x18000cb82`
- `EFSCORE!EdpDllServiceFileEncryptionQueue` at `0x18000cb82`

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
0x18000cb40  sub     rsp, 28h
0x18000cb44  lea     rdx, [rsp+28h+arg_8]
0x18000cb49  mov     [rsp+28h+arg_8], 0
0x18000cb51  call    EfspValidateClientCall
0x18000cb56  test    eax, eax
0x18000cb58  jnz     short loc_18000CBD3
0x18000cb5a  cmp     [rsp+28h+arg_8], eax
0x18000cb5e  jz      short loc_18000CBD3
0x18000cb60  cmp     cs:EfsServerInitialized, al
0x18000cb66  jz      short loc_18000CBCC
0x18000cb68  call    cs:__imp_EfsDllDisabled
0x18000cb6f  nop     dword ptr [rax+rax+00h]
0x18000cb74  test    al, al
0x18000cb76  jnz     short loc_18000CBCC
0x18000cb78  xor     ecx, ecx
0x18000cb7a  mov     [rsp+28h+arg_8], 0
0x18000cb82  call    cs:__imp_EdpDllServiceFileEncryptionQueue
0x18000cb89  nop     dword ptr [rax+rax+00h]
0x18000cb8e  test    eax, eax
0x18000cb90  jns     short loc_18000CBC6
0x18000cb92  mov     ecx, eax
0x18000cb94  and     ecx, 1FFF0000h
0x18000cb9a  cmp     ecx, 70000h
0x18000cba0  movzx   ecx, ax
0x18000cba3  jz      short loc_18000CBAA
0x18000cba5  mov     ecx, 54Fh
0x18000cbaa  lea     rdx, [rsp+28h+arg_8]
0x18000cbaf  call    cs:__imp_EfsDllErrorToNtStatus
0x18000cbb6  nop     dword ptr [rax+rax+00h]
0x18000cbbb  test    eax, eax
0x18000cbbd  jnz     short loc_18000CBC6
0x18000cbbf  mov     eax, 0C0000001h
0x18000cbc4  jmp     short loc_18000CBD8
0x18000cbc6  mov     eax, [rsp+28h+arg_8]
0x18000cbca  jmp     short loc_18000CBD8
0x18000cbcc  mov     eax, 0C00000BBh
0x18000cbd1  jmp     short loc_18000CBD8
0x18000cbd3  mov     eax, 0C0000022h
0x18000cbd8  add     rsp, 28h
0x18000cbdc  retn
```
