# NCryptStreamOpenToUnprotectEx

- ea: `0x18001d460`
- end: `0x18001d532`
- name: `NCryptStreamOpenToUnprotectEx`
- size: `210`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002550`
- `0x18000e120`
- `0x180016128`
- `0x18001d460`

## string_xrefs

- `0x18001d498`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\stream.c`
- `0x18001d506`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\stream.c`

## pseudocode

```c
__int64 __fastcall NCryptStreamOpenToUnprotectEx(_OWORD *a1, unsigned int a2, __int64 a3, _QWORD *a4)
{
  __int64 v5; // rsi
  unsigned int v7; // ebx
  unsigned int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // r9
  __int64 v11; // rax
  __int64 v13; // [rsp+68h] [rbp+20h] BYREF

  v5 = 0;
  v13 = 0;
  if ( a4 && a1 && *(_QWORD *)a1 )
  {
    if ( (a2 & 0xFFFFFF3E) != 0 )
    {
      v7 = -2146893815;
      DebugTraceError(
        2148073481LL,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\stream.c",
        505);
      return v7;
    }
    v8 = I_StreamOpenToUnprotect(a2, a3, &v13);
    v7 = v8;
    if ( !v8 )
    {
      v11 = v13;
      v7 = 0;
      *(_OWORD *)(v13 + 16) = *a1;
      *(_DWORD *)(v11 + 32) = 1;
      *a4 = v11;
      return v7;
    }
    v5 = v13;
    v9 = v8;
    v10 = 512;
  }
  else
  {
    v7 = -2146893785;
    v9 = 2148073511LL;
    v10 = 498;
  }
  DebugTraceError(v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\stream.c", v10);
  if ( v5 )
    I_StreamFree(v5);
  return v7;
}

```

## disassembly

```asm
0x18001d460  push    rbx
0x18001d462  push    rsi
0x18001d463  push    rdi
0x18001d464  push    r14
0x18001d466  sub     rsp, 28h
0x18001d46a  mov     r14, r9
0x18001d46d  xor     esi, esi
0x18001d46f  mov     [rsp+48h+arg_18], rsi
0x18001d474  mov     r9, r8
0x18001d477  mov     eax, edx
0x18001d479  mov     rdi, rcx
0x18001d47c  test    r14, r14
0x18001d47f  jz      short loc_18001D4F6
0x18001d481  test    rcx, rcx
0x18001d484  jz      short loc_18001D4F6
0x18001d486  cmp     [rcx], rsi
0x18001d489  jz      short loc_18001D4F6
0x18001d48b  test    eax, 0FFFFFF3Eh
0x18001d490  jz      short loc_18001D4B7
0x18001d492  mov     r9d, 1F9h
0x18001d498  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001d49f  lea     rdx, aStatus; "Status"
0x18001d4a6  mov     ecx, 80090009h
0x18001d4ab  mov     ebx, 80090009h
0x18001d4b0  call    DebugTraceError
0x18001d4b5  jmp     short loc_18001D526
0x18001d4b7  lea     r8, [rsp+48h+arg_18]
0x18001d4bc  mov     rdx, r9
0x18001d4bf  mov     ecx, eax
0x18001d4c1  call    I_StreamOpenToUnprotect
0x18001d4c6  mov     ebx, eax
0x18001d4c8  test    eax, eax
0x18001d4ca  jz      short loc_18001D4DB
0x18001d4cc  mov     rsi, [rsp+48h+arg_18]
0x18001d4d1  mov     ecx, eax
0x18001d4d3  mov     r9d, 200h
0x18001d4d9  jmp     short loc_18001D506
0x18001d4db  mov     rax, [rsp+48h+arg_18]
0x18001d4e0  xor     ebx, ebx
0x18001d4e2  movups  xmm0, xmmword ptr [rdi]
0x18001d4e5  movdqu  xmmword ptr [rax+10h], xmm0
0x18001d4ea  mov     dword ptr [rax+20h], 1
0x18001d4f1  mov     [r14], rax
0x18001d4f4  jmp     short loc_18001D526
0x18001d4f6  mov     ebx, 80090027h
0x18001d4fb  mov     ecx, 80090027h
0x18001d500  mov     r9d, 1F2h
0x18001d506  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001d50d  lea     rdx, aStatus; "Status"
0x18001d514  call    DebugTraceError
0x18001d519  test    rsi, rsi
0x18001d51c  jz      short loc_18001D526
0x18001d51e  mov     rcx, rsi
0x18001d521  call    I_StreamFree
0x18001d526  mov     eax, ebx
0x18001d528  add     rsp, 28h
0x18001d52c  pop     r14
0x18001d52e  pop     rdi
0x18001d52f  pop     rsi
0x18001d530  pop     rbx
0x18001d531  retn
```
