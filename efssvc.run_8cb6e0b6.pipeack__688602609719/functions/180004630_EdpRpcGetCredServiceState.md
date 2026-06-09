# EdpRpcGetCredServiceState

- ea: `0x180004630`
- end: `0x1800047ae`
- name: `EdpRpcGetCredServiceState`
- size: `382`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x1800037b8`
- `0x180003864`
- `0x180003a24`
- `0x180004630`
- `0x18000d192`

## import_xrefs

- `EFSCORE!EdpDllGetCredServiceState` at `0x180004750`
- `EFSCORE!EdpDllGetCredServiceState` at `0x180004750`

## pseudocode

```c
__int64 __fastcall EdpRpcGetCredServiceState(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  int v13; // eax
  int v14; // ecx
  unsigned int v15; // ebx
  int CredServiceState; // eax
  int v17; // ecx
  _BYTE v19[168]; // [rsp+50h] [rbp-A8h] BYREF

  memset_0(v19, 0, 0x70u);
  if ( a2 && a3 && a4 && a5 && a6 && a7 && a8 && a9 && a10 )
  {
    v13 = EdpBeginLocalOnlyRpcCall((__int64)v19);
    v15 = v13;
    if ( v13 >= 0 )
    {
      CredServiceState = EdpDllGetCredServiceState(v19, a2, a3, a4, a5, a6, a7, a8, a9, a10);
      v15 = CredServiceState;
      if ( CredServiceState < 0 )
        fnEfsLogTrace1(v17, (unsigned int)EFS_API_ERROR, CredServiceState, 6, 246);
      EdpCleanupLocalOnlyRpcCall((__int64)v19);
    }
    else
    {
      fnEfsLogTrace1(v14, (unsigned int)EFS_API_ERROR, v13, 6, 229);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v15;
}

```

## disassembly

```asm
0x180004630  mov     [rsp+arg_0], rbx
0x180004635  mov     [rsp+arg_10], r8
0x18000463a  mov     [rsp+arg_8], rdx
0x18000463f  push    rbp
0x180004640  push    rsi
0x180004641  push    rdi
0x180004642  push    r12
0x180004644  push    r13
0x180004646  push    r14
0x180004648  push    r15
0x18000464a  sub     rsp, 0C0h
0x180004651  mov     rdi, rdx
0x180004654  lea     rcx, [rsp+0F8h+var_A8]; void *
0x180004659  xor     edx, edx; Val
0x18000465b  mov     rbx, r8
0x18000465e  mov     r13, r9
0x180004661  lea     r8d, [rdx+70h]; Size
0x180004665  call    memset_0
0x18000466a  test    rdi, rdi
0x18000466d  jz      loc_18000478B
0x180004673  test    rbx, rbx
0x180004676  jz      loc_18000478B
0x18000467c  test    r13, r13
0x18000467f  jz      loc_18000478B
0x180004685  mov     rdi, [rsp+0F8h+arg_20]
0x18000468d  test    rdi, rdi
0x180004690  jz      loc_18000478B
0x180004696  mov     rsi, [rsp+0F8h+arg_28]
0x18000469e  test    rsi, rsi
0x1800046a1  jz      loc_18000478B
0x1800046a7  mov     rbp, [rsp+0F8h+arg_30]
0x1800046af  test    rbp, rbp
0x1800046b2  jz      loc_18000478B
0x1800046b8  mov     r14, [rsp+0F8h+arg_38]
0x1800046c0  test    r14, r14
0x1800046c3  jz      loc_18000478B
0x1800046c9  mov     r15, [rsp+0F8h+arg_40]
0x1800046d1  test    r15, r15
0x1800046d4  jz      loc_18000478B
0x1800046da  mov     r12, [rsp+0F8h+arg_48]
0x1800046e2  test    r12, r12
0x1800046e5  jz      loc_18000478B
0x1800046eb  lea     rcx, [rsp+0F8h+var_A8]
0x1800046f0  call    EdpBeginLocalOnlyRpcCall
0x1800046f5  mov     ebx, eax
0x1800046f7  test    eax, eax
0x1800046f9  jns     short loc_18000471A
0x1800046fb  mov     r9d, 6
0x180004701  mov     dword ptr [rsp+0F8h+var_D8], 0CE5h
0x180004709  mov     r8d, eax
0x18000470c  lea     rdx, EFS_API_ERROR
0x180004713  call    fnEfsLogTrace1
0x180004718  jmp     short loc_180004790
0x18000471a  mov     r8, [rsp+0F8h+arg_10]
0x180004722  lea     rcx, [rsp+0F8h+var_A8]
0x180004727  mov     rdx, [rsp+0F8h+arg_8]
0x18000472f  mov     r9, r13
0x180004732  mov     [rsp+0F8h+var_B0], r12
0x180004737  mov     [rsp+0F8h+var_B8], r15
0x18000473c  mov     [rsp+0F8h+var_C0], r14
0x180004741  mov     [rsp+0F8h+var_C8], rbp
0x180004746  mov     [rsp+0F8h+var_D0], rsi
0x18000474b  mov     [rsp+0F8h+var_D8], rdi
0x180004750  call    cs:__imp_EdpDllGetCredServiceState
0x180004757  nop     dword ptr [rax+rax+00h]
0x18000475c  mov     ebx, eax
0x18000475e  test    eax, eax
0x180004760  jns     short loc_18000477F
0x180004762  mov     r9d, 6
0x180004768  mov     dword ptr [rsp+0F8h+var_D8], 0CF6h
0x180004770  mov     r8d, eax
0x180004773  lea     rdx, EFS_API_ERROR
0x18000477a  call    fnEfsLogTrace1
0x18000477f  lea     rcx, [rsp+0F8h+var_A8]
0x180004784  call    EdpCleanupLocalOnlyRpcCall
0x180004789  jmp     short loc_180004790
0x18000478b  mov     ebx, 80004003h
0x180004790  mov     eax, ebx
0x180004792  mov     rbx, [rsp+0F8h+arg_0]
0x18000479a  add     rsp, 0C0h
0x1800047a1  pop     r15
0x1800047a3  pop     r14
0x1800047a5  pop     r13
0x1800047a7  pop     r12
0x1800047a9  pop     rdi
0x1800047aa  pop     rsi
0x1800047ab  pop     rbp
0x1800047ac  retn
```
