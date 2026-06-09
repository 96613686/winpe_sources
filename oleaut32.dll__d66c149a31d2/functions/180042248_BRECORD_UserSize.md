# BRECORD_UserSize

- ea: `0x180042248`
- end: `0x1800423f7`
- name: `BRECORD_UserSize`
- size: `431`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002f010`
- `0x18002f3a0`

## callees

- `0x180042248`
- `0x18009c010`

## import_xrefs

- `combase!WdtpInterfacePointer_UserSize` at `0x1800422c9`
- `combase!WdtpInterfacePointer_UserSize` at `0x1800422c9`
- `combase!__imp_CoDoesOtherSideSupportUDTMarshaling` at `0x18004227f`
- `combase!__imp_CoDoesOtherSideSupportUDTMarshaling` at `0x18004227f`
- `RPCRT4!RpcRaiseException` at `0x18004228e`
- `RPCRT4!RpcRaiseException` at `0x180042317`
- `RPCRT4!RpcRaiseException` at `0x1800423a7`
- `RPCRT4!RpcRaiseException` at `0x1800423c1`
- `RPCRT4!RpcRaiseException` at `0x1800423e4`
- `RPCRT4!RpcRaiseException` at `0x1800423f0`
- `RPCRT4!RpcRaiseException` at `0x18004228e`
- `RPCRT4!RpcRaiseException` at `0x180042317`
- `RPCRT4!RpcRaiseException` at `0x1800423a7`
- `RPCRT4!RpcRaiseException` at `0x1800423c1`
- `RPCRT4!RpcRaiseException` at `0x1800423e4`
- `RPCRT4!RpcRaiseException` at `0x1800423f0`

## pseudocode

```c
__int64 __fastcall BRECORD_UserSize(
        unsigned int *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 (__fastcall ***a4)(_QWORD, GUID *, __int64 *),
        __int64 a5)
{
  __int64 result; // rax
  unsigned int v10; // eax
  __int64 v11; // r8
  __int64 v12; // r15
  unsigned int v13; // ecx
  unsigned int v14; // esi
  __int64 (__fastcall **v15)(_QWORD, GUID *, __int64 *); // rax
  RPC_STATUS v16; // eax
  __int64 (__fastcall **v17)(_QWORD, GUID *, __int64 *); // rax
  __int64 v18; // r13
  unsigned int v19; // ebx
  unsigned int i; // edi
  __int64 v21; // r9
  __int64 v22; // r8
  RPC_STATUS v23; // r14d
  unsigned int v24; // [rsp+30h] [rbp-18h] BYREF
  __int64 v25; // [rsp+38h] [rbp-10h] BYREF
  int v26; // [rsp+A8h] [rbp+60h] BYREF

  if ( !a4 )
    return a2;
  if ( !(unsigned int)CoDoesOtherSideSupportUDTMarshaling(a1) )
    RpcRaiseException(1733);
  v10 = (a2 + 3) & 0xFFFFFFFC;
  if ( v10 < a2 || (v11 = v10 + 16, (unsigned int)v11 < v10) )
    RpcRaiseException(-2147418096);
  result = WdtpInterfacePointer_UserSize(a1, *a1, v11, a4, &IID_IRecordInfo);
  v12 = a5;
  if ( a5 )
  {
    v13 = (result + 3) & 0xFFFFFFFC;
    if ( v13 < (unsigned int)result )
      goto LABEL_21;
    v14 = v13 + 4;
    if ( v13 + 4 < v13 )
      goto LABEL_21;
    v15 = *a4;
    v25 = 0;
    v16 = (*v15)(a4, &IID_ITypeMarshal, &v25);
    if ( v16 < 0 )
      RpcRaiseException(v16);
    v17 = *a4;
    v18 = *((_QWORD *)a1 + 1);
    v24 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), unsigned int *))v17[8])(a4, &v24);
    v19 = 0;
    for ( i = 0; i < a3; ++i )
    {
      v21 = *(_QWORD *)(v18 + 200);
      v22 = *(unsigned int *)(v18 + 196);
      v26 = 0;
      v23 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, int *))(*(_QWORD *)v25 + 24LL))(
              v25,
              v12,
              v22,
              v21,
              &v26);
      if ( v23 < 0 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        RpcRaiseException(v23);
      }
      if ( v19 + v26 < v19 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        RpcRaiseException(-2147418096);
      }
      v19 += v26;
      v12 += v24;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    result = v14 + v19;
    if ( (unsigned int)result < v14 )
LABEL_21:
      RpcRaiseException(-2147418096);
  }
  return result;
}

```

## disassembly

```asm
0x180042248  push    rbp
0x18004224a  push    rbx
0x18004224b  push    rsi
0x18004224c  push    rdi
0x18004224d  push    r12
0x18004224f  push    r13
0x180042251  push    r14
0x180042253  push    r15
0x180042255  mov     rbp, rsp
0x180042258  sub     rsp, 48h
0x18004225c  mov     rdi, r9
0x18004225f  mov     r12d, r8d
0x180042262  mov     ebx, edx
0x180042264  mov     r14, rcx
0x180042267  test    r9, r9
0x18004226a  jnz     short loc_18004227F
0x18004226c  mov     eax, edx
0x18004226e  add     rsp, 48h
0x180042272  pop     r15
0x180042274  pop     r14
0x180042276  pop     r13
0x180042278  pop     r12
0x18004227a  pop     rdi
0x18004227b  pop     rsi
0x18004227c  pop     rbx
0x18004227d  pop     rbp
0x18004227e  retn
0x18004227f  call    cs:__imp_CoDoesOtherSideSupportUDTMarshaling
0x180042285  test    eax, eax
0x180042287  jnz     short loc_180042295
0x180042289  mov     ecx, 6C5h; exception
0x18004228e  call    cs:__imp_RpcRaiseException
0x180042294  int     3; Trap to Debugger
0x180042295  lea     eax, [rbx+3]
0x180042298  mov     esi, 0FFFFFFFCh
0x18004229d  and     eax, esi
0x18004229f  cmp     eax, ebx
0x1800422a1  jb      loc_1800423EB
0x1800422a7  lea     r8d, [rax+10h]
0x1800422ab  cmp     r8d, eax
0x1800422ae  jb      loc_1800423EB
0x1800422b4  mov     edx, [r14]
0x1800422b7  lea     rax, IID_IRecordInfo
0x1800422be  mov     r9, rdi
0x1800422c1  mov     [rsp+48h+var_28], rax
0x1800422c6  mov     rcx, r14
0x1800422c9  call    cs:__imp_WdtpInterfacePointer_UserSize
0x1800422cf  mov     r15, [rbp+arg_20]
0x1800422d3  test    r15, r15
0x1800422d6  jz      short loc_18004226E
0x1800422d8  lea     ecx, [rax+3]
0x1800422db  and     ecx, esi
0x1800422dd  cmp     ecx, eax
0x1800422df  jb      loc_1800423DF
0x1800422e5  lea     esi, [rcx+4]
0x1800422e8  cmp     esi, ecx
0x1800422ea  jb      loc_1800423DF
0x1800422f0  mov     rax, [rdi]
0x1800422f3  lea     r8, [rbp+var_10]
0x1800422f7  lea     rdx, IID_ITypeMarshal
0x1800422fe  mov     [rbp+var_10], 0
0x180042306  mov     rcx, rdi
0x180042309  mov     rax, [rax]
0x18004230c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042311  test    eax, eax
0x180042313  jns     short loc_18004231E
0x180042315  mov     ecx, eax; exception
0x180042317  call    cs:__imp_RpcRaiseException
0x18004231d  int     3; Trap to Debugger
0x18004231e  mov     rax, [rdi]
0x180042321  lea     rdx, [rbp+var_18]
0x180042325  mov     r13, [r14+8]
0x180042329  mov     rcx, rdi
0x18004232c  mov     [rbp+var_18], 0
0x180042333  mov     rax, [rax+40h]
0x180042337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004233c  xor     ebx, ebx
0x18004233e  xor     edi, edi
0x180042340  mov     rcx, [rbp+var_10]
0x180042344  cmp     edi, r12d
0x180042347  jnb     short loc_1800423C8
0x180042349  mov     r9, [r13+0C8h]
0x180042350  lea     rdx, [rbp+arg_18]
0x180042354  mov     r8d, [r13+0C4h]
0x18004235b  mov     [rbp+arg_18], 0
0x180042362  mov     rax, [rcx]
0x180042365  mov     [rsp+48h+var_28], rdx
0x18004236a  mov     rdx, r15
0x18004236d  mov     rax, [rax+18h]
0x180042371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042376  mov     r14d, eax
0x180042379  test    eax, eax
0x18004237b  js      short loc_1800423AE
0x18004237d  mov     ecx, [rbp+arg_18]
0x180042380  add     ecx, ebx
0x180042382  cmp     ecx, ebx
0x180042384  jb      short loc_180042392
0x180042386  mov     eax, [rbp+var_18]
0x180042389  mov     ebx, ecx
0x18004238b  add     r15, rax
0x18004238e  inc     edi
0x180042390  jmp     short loc_180042340
0x180042392  mov     rcx, [rbp+var_10]
0x180042396  mov     rax, [rcx]
0x180042399  mov     rax, [rax+10h]
0x18004239d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800423a2  mov     ecx, 80010010h; exception
0x1800423a7  call    cs:__imp_RpcRaiseException
0x1800423ad  int     3; Trap to Debugger
0x1800423ae  mov     rcx, [rbp+var_10]
0x1800423b2  mov     rax, [rcx]
0x1800423b5  mov     rax, [rax+10h]
0x1800423b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800423be  mov     ecx, r14d; exception
0x1800423c1  call    cs:__imp_RpcRaiseException
0x1800423c7  int     3; Trap to Debugger
0x1800423c8  mov     rax, [rcx]
0x1800423cb  mov     rax, [rax+10h]
0x1800423cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800423d4  lea     eax, [rsi+rbx]
0x1800423d7  cmp     eax, esi
0x1800423d9  jnb     loc_18004226E
0x1800423df  mov     ecx, 80010010h; exception
0x1800423e4  call    cs:__imp_RpcRaiseException
0x1800423ea  int     3; Trap to Debugger
0x1800423eb  mov     ecx, 80010010h; exception
0x1800423f0  call    cs:__imp_RpcRaiseException
```
