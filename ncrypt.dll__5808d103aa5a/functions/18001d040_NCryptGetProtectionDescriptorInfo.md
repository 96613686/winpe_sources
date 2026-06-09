# NCryptGetProtectionDescriptorInfo

- ea: `0x18001d040`
- end: `0x18001d0e2`
- name: `NCryptGetProtectionDescriptorInfo`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000e120`
- `0x18001d040`
- `0x18001d538`

## string_xrefs

- `0x18001d0c7`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`

## pseudocode

```c
__int64 __fastcall NCryptGetProtectionDescriptorInfo(__int64 a1, __int64 *a2, int a3, wchar_t **a4)
{
  unsigned int v5; // ebx
  __int64 v6; // r9
  __int64 v7; // rcx
  __int64 *v8; // rdx
  unsigned int v9; // eax

  if ( !a4 )
  {
    v5 = -2146893785;
    v6 = 2078;
    v7 = 2148073511LL;
LABEL_13:
    DebugTraceError(
      v7,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
      v6);
    return v5;
  }
  if ( !a1 || *(_DWORD *)a1 != 40 )
  {
    v5 = -2146893786;
    v6 = 2087;
    v7 = 2148073510LL;
    goto LABEL_13;
  }
  *a4 = 0;
  v8 = &NCryptDefaultAllocPara;
  if ( a2 )
    v8 = a2;
  if ( a3 != 1 )
  {
    v5 = -2146893783;
    v6 = 2120;
    v7 = 2148073513LL;
    goto LABEL_13;
  }
  v9 = CNG_DescriptorInfoToString(*(_QWORD *)(a1 + 8), (__int64)v8, a4);
  v5 = v9;
  if ( v9 )
  {
    v6 = 2110;
    v7 = v9;
    goto LABEL_13;
  }
  return 0;
}

```

## disassembly

```asm
0x18001d040  push    rbx
0x18001d042  sub     rsp, 20h
0x18001d046  mov     rax, rdx
0x18001d049  test    r9, r9
0x18001d04c  jnz     short loc_18001D060
0x18001d04e  mov     ebx, 80090027h
0x18001d053  mov     r9d, 81Eh
0x18001d059  mov     ecx, 80090027h
0x18001d05e  jmp     short loc_18001D0C7
0x18001d060  test    rcx, rcx
0x18001d063  jz      short loc_18001D0B7
0x18001d065  cmp     dword ptr [rcx], 28h ; '('
0x18001d068  jnz     short loc_18001D0B7
0x18001d06a  test    rax, rax
0x18001d06d  mov     qword ptr [r9], 0
0x18001d074  lea     rdx, NCryptDefaultAllocPara
0x18001d07b  cmovnz  rdx, rax
0x18001d07f  cmp     r8d, 1
0x18001d083  jz      short loc_18001D097
0x18001d085  mov     ebx, 80090029h
0x18001d08a  mov     r9d, 848h
0x18001d090  mov     ecx, 80090029h
0x18001d095  jmp     short loc_18001D0C7
0x18001d097  mov     rcx, [rcx+8]
0x18001d09b  mov     r8, r9
0x18001d09e  call    CNG_DescriptorInfoToString
0x18001d0a3  mov     ebx, eax
0x18001d0a5  test    eax, eax
0x18001d0a7  jz      short loc_18001D0B3
0x18001d0a9  mov     r9d, 83Eh
0x18001d0af  mov     ecx, eax
0x18001d0b1  jmp     short loc_18001D0C7
0x18001d0b3  xor     ebx, ebx
0x18001d0b5  jmp     short loc_18001D0DA
0x18001d0b7  mov     ebx, 80090026h
0x18001d0bc  mov     r9d, 827h
0x18001d0c2  mov     ecx, 80090026h
0x18001d0c7  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001d0ce  lea     rdx, aStatus; "Status"
0x18001d0d5  call    DebugTraceError
0x18001d0da  mov     eax, ebx
0x18001d0dc  add     rsp, 20h
0x18001d0e0  pop     rbx
0x18001d0e1  retn
```
