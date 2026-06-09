# SrvCryptVerifySignature

- ea: `0x18000f4a0`
- end: `0x18000f59b`
- name: `SrvCryptVerifySignature`
- size: `251`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, int, __int64, int, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800048f0`
- `0x1800055e0`
- `0x180005f00`
- `0x18000f4a0`
- `0x180019010`

## string_xrefs

- `0x18000f4bb`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000f55b`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvCryptVerifySignature(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        int a8,
        int a9)
{
  __int64 v10; // r9
  int v11; // ebx
  __int64 v12; // rax
  __int64 v13; // rdi
  unsigned int v14; // eax
  unsigned int v15; // ebx
  int v16; // eax

  if ( !a1 )
  {
    v10 = 3602;
LABEL_3:
    v11 = -2146893786;
    DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v10);
    return (unsigned int)v11;
  }
  v12 = SrvLookupAndReferenceKey(a1, a3, 0);
  v13 = v12;
  if ( !v12 )
  {
    v10 = 3611;
    goto LABEL_3;
  }
  v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64, int, __int64, int, int))(*(_QWORD *)(v12 + 32)
                                                                                            + 208LL))(
          *(_QWORD *)(*(_QWORD *)(v12 + 32) + 296LL),
          *(_QWORD *)(v12 + 40),
          a4,
          a5,
          a6,
          a7,
          a8,
          a9);
  v15 = v14;
  if ( v14 )
  {
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 3632);
    v11 = NormalizeNteStatus(v15);
  }
  else
  {
    v11 = 0;
  }
  v16 = SrvDereferenceKey(v13);
  if ( v16 < 0 && v11 >= 0 )
    return (unsigned int)v16;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000f4a0  mov     [rsp+arg_0], rbx
0x18000f4a5  push    rdi
0x18000f4a6  sub     rsp, 50h
0x18000f4aa  mov     rbx, r9
0x18000f4ad  mov     rax, r8
0x18000f4b0  test    rcx, rcx
0x18000f4b3  jnz     short loc_18000F4DD
0x18000f4b5  mov     r9d, 0E12h
0x18000f4bb  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f4c2  mov     ecx, 80090026h
0x18000f4c7  lea     rdx, aStatus; "Status"
0x18000f4ce  mov     ebx, 80090026h
0x18000f4d3  call    DebugTraceError
0x18000f4d8  jmp     loc_18000F58E
0x18000f4dd  xor     r8d, r8d
0x18000f4e0  mov     rdx, rax
0x18000f4e3  call    SrvLookupAndReferenceKey
0x18000f4e8  mov     rdi, rax
0x18000f4eb  test    rax, rax
0x18000f4ee  jnz     short loc_18000F4F8
0x18000f4f0  mov     r9d, 0E1Bh
0x18000f4f6  jmp     short loc_18000F4BB
0x18000f4f8  mov     rcx, [rax+20h]
0x18000f4fc  mov     r8, rbx
0x18000f4ff  mov     eax, [rsp+58h+arg_40]
0x18000f506  mov     r9, [rsp+58h+arg_20]
0x18000f50e  mov     rdx, [rdi+28h]
0x18000f512  mov     r10, [rcx+0D0h]
0x18000f519  mov     rcx, [rcx+128h]
0x18000f520  mov     [rsp+58h+var_20], eax
0x18000f524  mov     eax, [rsp+58h+arg_38]
0x18000f52b  mov     [rsp+58h+var_28], eax
0x18000f52f  mov     rax, [rsp+58h+arg_30]
0x18000f537  mov     [rsp+58h+var_30], rax
0x18000f53c  mov     eax, [rsp+58h+arg_28]
0x18000f543  mov     [rsp+58h+var_38], eax
0x18000f547  mov     rax, r10
0x18000f54a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f54f  mov     ebx, eax
0x18000f551  test    eax, eax
0x18000f553  jz      short loc_18000F57B
0x18000f555  mov     r9d, 0E30h
0x18000f55b  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f562  lea     rdx, aStatus; "Status"
0x18000f569  mov     ecx, eax
0x18000f56b  call    DebugTraceError
0x18000f570  mov     ecx, ebx
0x18000f572  call    NormalizeNteStatus
0x18000f577  mov     ebx, eax
0x18000f579  jmp     short loc_18000F57D
0x18000f57b  xor     ebx, ebx
0x18000f57d  mov     rcx, rdi
0x18000f580  call    SrvDereferenceKey
0x18000f585  test    eax, eax
0x18000f587  jns     short loc_18000F58E
0x18000f589  test    ebx, ebx
0x18000f58b  cmovns  ebx, eax
0x18000f58e  mov     eax, ebx
0x18000f590  mov     rbx, [rsp+58h+arg_0]
0x18000f595  add     rsp, 50h
0x18000f599  pop     rdi
0x18000f59a  retn
```
