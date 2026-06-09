# EdpRpcGetCredServiceState

- ea: `0x180004370`
- end: `0x1800044e7`
- name: `EdpRpcGetCredServiceState`
- size: `375`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x180003604`
- `0x1800036a0`
- `0x180003828`
- `0x180004370`
- `0x18000c392`

## import_xrefs

- `EFSCORE!EdpDllGetCredServiceState` at `0x180004490`
- `EFSCORE!EdpDllGetCredServiceState` at `0x180004490`

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
0x180004370  mov     [rsp+arg_0], rbx
0x180004375  mov     [rsp+arg_10], r8
0x18000437a  mov     [rsp+arg_8], rdx
0x18000437f  push    rbp
0x180004380  push    rsi
0x180004381  push    rdi
0x180004382  push    r12
0x180004384  push    r13
0x180004386  push    r14
0x180004388  push    r15
0x18000438a  sub     rsp, 0C0h
0x180004391  mov     rdi, rdx
0x180004394  lea     rcx, [rsp+0F8h+var_A8]; void *
0x180004399  xor     edx, edx; Val
0x18000439b  mov     rbx, r8
0x18000439e  mov     r13, r9
0x1800043a1  lea     r8d, [rdx+70h]; Size
0x1800043a5  call    memset_0
0x1800043aa  test    rdi, rdi
0x1800043ad  jz      loc_1800044C5
0x1800043b3  test    rbx, rbx
0x1800043b6  jz      loc_1800044C5
0x1800043bc  test    r13, r13
0x1800043bf  jz      loc_1800044C5
0x1800043c5  mov     rdi, [rsp+0F8h+arg_20]
0x1800043cd  test    rdi, rdi
0x1800043d0  jz      loc_1800044C5
0x1800043d6  mov     rsi, [rsp+0F8h+arg_28]
0x1800043de  test    rsi, rsi
0x1800043e1  jz      loc_1800044C5
0x1800043e7  mov     rbp, [rsp+0F8h+arg_30]
0x1800043ef  test    rbp, rbp
0x1800043f2  jz      loc_1800044C5
0x1800043f8  mov     r14, [rsp+0F8h+arg_38]
0x180004400  test    r14, r14
0x180004403  jz      loc_1800044C5
0x180004409  mov     r15, [rsp+0F8h+arg_40]
0x180004411  test    r15, r15
0x180004414  jz      loc_1800044C5
0x18000441a  mov     r12, [rsp+0F8h+arg_48]
0x180004422  test    r12, r12
0x180004425  jz      loc_1800044C5
0x18000442b  lea     rcx, [rsp+0F8h+var_A8]
0x180004430  call    EdpBeginLocalOnlyRpcCall
0x180004435  mov     ebx, eax
0x180004437  test    eax, eax
0x180004439  jns     short loc_18000445A
0x18000443b  mov     r9d, 6
0x180004441  mov     dword ptr [rsp+0F8h+var_D8], 0CE5h
0x180004449  mov     r8d, eax
0x18000444c  lea     rdx, EFS_API_ERROR
0x180004453  call    fnEfsLogTrace1
0x180004458  jmp     short loc_1800044CA
0x18000445a  mov     r8, [rsp+0F8h+arg_10]
0x180004462  lea     rcx, [rsp+0F8h+var_A8]
0x180004467  mov     rdx, [rsp+0F8h+arg_8]
0x18000446f  mov     r9, r13
0x180004472  mov     [rsp+0F8h+var_B0], r12
0x180004477  mov     [rsp+0F8h+var_B8], r15
0x18000447c  mov     [rsp+0F8h+var_C0], r14
0x180004481  mov     [rsp+0F8h+var_C8], rbp
0x180004486  mov     [rsp+0F8h+var_D0], rsi
0x18000448b  mov     [rsp+0F8h+var_D8], rdi
0x180004490  call    cs:__imp_EdpDllGetCredServiceState
0x180004496  mov     ebx, eax
0x180004498  test    eax, eax
0x18000449a  jns     short loc_1800044B9
0x18000449c  mov     r9d, 6
0x1800044a2  mov     dword ptr [rsp+0F8h+var_D8], 0CF6h
0x1800044aa  mov     r8d, eax
0x1800044ad  lea     rdx, EFS_API_ERROR
0x1800044b4  call    fnEfsLogTrace1
0x1800044b9  lea     rcx, [rsp+0F8h+var_A8]
0x1800044be  call    EdpCleanupLocalOnlyRpcCall
0x1800044c3  jmp     short loc_1800044CA
0x1800044c5  mov     ebx, 80004003h
0x1800044ca  mov     eax, ebx
0x1800044cc  mov     rbx, [rsp+0F8h+arg_0]
0x1800044d4  add     rsp, 0C0h
0x1800044db  pop     r15
0x1800044dd  pop     r14
0x1800044df  pop     r13
0x1800044e1  pop     r12
0x1800044e3  pop     rdi
0x1800044e4  pop     rsi
0x1800044e5  pop     rbp
0x1800044e6  retn
```
