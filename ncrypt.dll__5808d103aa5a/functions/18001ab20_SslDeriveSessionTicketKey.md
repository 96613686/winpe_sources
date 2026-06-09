# SslDeriveSessionTicketKey

- ea: `0x18001ab20`
- end: `0x18001ac66`
- name: `SslDeriveSessionTicketKey`
- size: `326`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180009cd0`
- `0x180009ea0`
- `0x18000a770`
- `0x18000c8e0`
- `0x18000e120`
- `0x18001ab20`
- `0x180020010`

## string_xrefs

- `0x18001ab59`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18001ac12`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslDeriveSessionTicketKey(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        BYTE *a5,
        DWORD *a6,
        DWORD *a7,
        int a8)
{
  __int64 v11; // rsi
  unsigned int v12; // edi
  __int64 v13; // r9
  __int64 v14; // rcx
  NCRYPT_KEY_HANDLE *v15; // rdx
  NCryptKeyName **v16; // r8
  NCryptAlgorithmName **v17; // r9
  _OWORD *v18; // rax
  _OWORD *v19; // rbx
  int v20; // eax

  v11 = ValidateSslProvHandle(a1);
  if ( *(_WORD *)(v11 + 32) < 7u )
  {
    v12 = -2146893783;
    v13 = 4880;
    v14 = 2148073513LL;
LABEL_3:
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v13);
    return NormalizeNteStatus(v12, v15, v16, v17, a5, a6, a7);
  }
  if ( !a7 )
  {
    v12 = -2146893785;
    v13 = 4898;
    v14 = 2148073511LL;
    goto LABEL_3;
  }
  v18 = (_OWORD *)SafeAllocaAllocateFromHeap(32);
  v19 = v18;
  if ( !v18 )
  {
    v12 = -2146893810;
    v13 = 4910;
    v14 = 2148073486LL;
    goto LABEL_3;
  }
  *v18 = 0;
  v18[1] = 0;
  v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, BYTE *, _DWORD, _OWORD *, int))(v11 + 376))(
          *(_QWORD *)(v11 + 424),
          a2,
          a3,
          a4,
          a5,
          (_DWORD)a6,
          v18 + 1,
          a8);
  v12 = v20;
  if ( v20 >= 0 )
  {
    *(_DWORD *)v19 = 32;
    *(_QWORD *)((char *)v19 + 4) = 1145324610;
    *((_DWORD *)v19 + 3) = 1;
    *((_QWORD *)v19 + 3) = v11;
    *(_QWORD *)a7 = v19;
    _InterlockedIncrement((volatile signed __int32 *)(v11 + 16));
    v12 = 0;
  }
  else
  {
    DebugTraceError((unsigned int)v20, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 4930);
    MSCryptFree(v19);
  }
  return NormalizeNteStatus(v12, v15, v16, v17, a5, a6, a7);
}

```

## disassembly

```asm
0x18001ab20  push    rbx
0x18001ab22  push    rbp
0x18001ab23  push    rsi
0x18001ab24  push    rdi
0x18001ab25  push    r14
0x18001ab27  push    r15
0x18001ab29  sub     rsp, 58h
0x18001ab2d  mov     edi, r9d
0x18001ab30  mov     rbp, r8
0x18001ab33  mov     r15d, edx
0x18001ab36  call    ValidateSslProvHandle
0x18001ab3b  mov     rsi, rax
0x18001ab3e  mov     eax, 7
0x18001ab43  cmp     ax, [rsi+20h]
0x18001ab47  jbe     short loc_18001AB71
0x18001ab49  mov     edi, 80090029h
0x18001ab4e  mov     r9d, 1310h
0x18001ab54  mov     ecx, 80090029h
0x18001ab59  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001ab60  lea     rdx, aStatus; "Status"
0x18001ab67  call    DebugTraceError
0x18001ab6c  jmp     loc_18001AC53
0x18001ab71  mov     r14, [rsp+88h+arg_30]
0x18001ab79  test    r14, r14
0x18001ab7c  jnz     short loc_18001AB90
0x18001ab7e  mov     edi, 80090027h
0x18001ab83  mov     r9d, 1322h
0x18001ab89  mov     ecx, 80090027h
0x18001ab8e  jmp     short loc_18001AB59
0x18001ab90  mov     ecx, 20h ; ' '
0x18001ab95  call    SafeAllocaAllocateFromHeap
0x18001ab9a  mov     rbx, rax
0x18001ab9d  test    rax, rax
0x18001aba0  jnz     short loc_18001ABB4
0x18001aba2  mov     edi, 8009000Eh
0x18001aba7  mov     r9d, 132Eh
0x18001abad  mov     ecx, 8009000Eh
0x18001abb2  jmp     short loc_18001AB59
0x18001abb4  mov     ecx, [rsp+88h+arg_38]
0x18001abbb  lea     rdx, [rax+10h]
0x18001abbf  mov     [rsp+88h+var_50], ecx
0x18001abc3  xorps   xmm0, xmm0
0x18001abc6  mov     ecx, dword ptr [rsp+88h+arg_28]
0x18001abcd  mov     r9d, edi
0x18001abd0  mov     [rsp+88h+var_58], rdx
0x18001abd5  mov     r8, rbp
0x18001abd8  mov     [rsp+88h+var_60], ecx
0x18001abdc  mov     edx, r15d
0x18001abdf  mov     rcx, [rsp+88h+arg_20]
0x18001abe7  movups  xmmword ptr [rax], xmm0
0x18001abea  mov     [rsp+88h+var_68], rcx
0x18001abef  movups  xmmword ptr [rax+10h], xmm0
0x18001abf3  mov     rcx, [rsi+1A8h]
0x18001abfa  mov     rax, [rsi+178h]
0x18001ac01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac06  mov     edi, eax
0x18001ac08  test    eax, eax
0x18001ac0a  jns     short loc_18001AC31
0x18001ac0c  mov     r9d, 1342h
0x18001ac12  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001ac19  lea     rdx, aStatus; "Status"
0x18001ac20  mov     ecx, eax
0x18001ac22  call    DebugTraceError
0x18001ac27  mov     rcx, rbx
0x18001ac2a  call    MSCryptFree
0x18001ac2f  jmp     short loc_18001AC53
0x18001ac31  mov     dword ptr [rbx], 20h ; ' '
0x18001ac37  mov     qword ptr [rbx+4], 44444442h
0x18001ac3f  mov     dword ptr [rbx+0Ch], 1
0x18001ac46  mov     [rbx+18h], rsi
0x18001ac4a  mov     [r14], rbx
0x18001ac4d  lock inc dword ptr [rsi+10h]
0x18001ac51  xor     edi, edi
0x18001ac53  mov     ecx, edi
0x18001ac55  add     rsp, 58h
0x18001ac59  pop     r15
0x18001ac5b  pop     r14
0x18001ac5d  pop     rdi
0x18001ac5e  pop     rsi
0x18001ac5f  pop     rbp
0x18001ac60  pop     rbx
0x18001ac61  jmp     NormalizeNteStatus
```
