# CNG_GetDescriptorFromMessage

- ea: `0x1800058b0`
- end: `0x180005a12`
- name: `CNG_GetDescriptorFromMessage`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800053ac`

## callees

- `0x1800058b0`
- `0x180005a18`
- `0x180008cfc`
- `0x18000962c`
- `0x18000e120`
- `0x18001f175`
- `0x18001f1b0`

## string_xrefs

- `0x1800059fb`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`

## pseudocode

```c
__int64 __fastcall CNG_GetDescriptorFromMessage(__int64 a1, __int64 *a2)
{
  __int64 v4; // rdi
  __int64 v5; // rbx
  __int64 v6; // rsi
  _OWORD *v7; // rcx
  __int128 v8; // xmm1
  __int64 v9; // rcx
  unsigned int ProtectionDescriptor; // eax
  unsigned int v11; // esi
  _DWORD v13[2]; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD *v14; // [rsp+38h] [rbp-C8h]
  _QWORD v15[8]; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v16[16]; // [rsp+80h] [rbp-80h] BYREF

  v13[1] = 0;
  memset_0(v15, 0, sizeof(v15));
  memset_0(v16, 0, sizeof(v16));
  v4 = 0;
  v5 = 0;
  *a2 = 0;
  v14 = v16;
  v13[0] = 0;
  if ( !*(_DWORD *)(a1 + 40) )
    goto LABEL_8;
  do
  {
    if ( (unsigned int)v4 >= 8 )
      break;
    if ( !(unsigned int)I_GetDescriptorFromRecipientInfo((int *)(160 * v5 + *(_QWORD *)(a1 + 48)), &v15[v4]) )
    {
      v6 = 2LL * (unsigned int)v4;
      v7 = *(_OWORD **)(v15[v4] + 8LL);
      v16[v6] = *v7;
      v8 = v7[1];
      v9 = *(_QWORD *)(a1 + 48);
      v16[v6 + 1] = v8;
      v4 = (unsigned int)(v4 + 1);
      LODWORD(v16[v6 + 1]) = v5;
      v13[0] = v4;
      *((_QWORD *)&v16[v6 + 1] + 1) = 160 * v5 + v9;
    }
    v5 = (unsigned int)(v5 + 1);
  }
  while ( (unsigned int)v5 < *(_DWORD *)(a1 + 40) );
  if ( (_DWORD)v4
    && (ProtectionDescriptor = I_CreateProtectionDescriptor(0, (__int64)v13, 1u, 0, a2),
        (v11 = ProtectionDescriptor) != 0) )
  {
    DebugTraceError(
      ProtectionDescriptor,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
      1797);
  }
  else
  {
LABEL_8:
    v11 = 0;
  }
  while ( (_DWORD)v4 )
  {
    LODWORD(v4) = v4 - 1;
    CNG_FreeProtectionDescriptor(v15[(unsigned int)v4]);
  }
  return v11;
}

```

## disassembly

```asm
0x1800058b0  mov     [rsp-8+arg_10], rbx
0x1800058b5  push    rbp
0x1800058b6  push    rsi
0x1800058b7  push    rdi
0x1800058b8  push    r12
0x1800058ba  push    r13
0x1800058bc  push    r14
0x1800058be  push    r15
0x1800058c0  lea     rbp, [rsp-90h]
0x1800058c8  sub     rsp, 190h
0x1800058cf  mov     rax, cs:__security_cookie
0x1800058d6  xor     rax, rsp
0x1800058d9  mov     [rbp+0C0h+var_40], rax
0x1800058e0  xor     eax, eax
0x1800058e2  mov     r13, rdx
0x1800058e5  mov     r14, rcx
0x1800058e8  mov     [rsp+1C0h+var_190], rax
0x1800058ed  xor     edx, edx; Val
0x1800058ef  lea     rcx, [rsp+1C0h+var_180]; void *
0x1800058f4  lea     r8d, [rax+40h]; Size
0x1800058f8  call    memset_0
0x1800058fd  xor     edx, edx; Val
0x1800058ff  lea     rcx, [rbp+0C0h+var_140]; void *
0x180005903  mov     r8d, 100h; Size
0x180005909  call    memset_0
0x18000590e  xor     edi, edi
0x180005910  lea     rax, [rbp+0C0h+var_140]
0x180005914  xor     ebx, ebx
0x180005916  mov     [r13+0], rdi
0x18000591a  mov     [rsp+1C0h+var_188], rax
0x18000591f  mov     dword ptr [rsp+1C0h+var_190], edi
0x180005923  cmp     [r14+28h], ebx
0x180005927  jbe     loc_1800059B5
0x18000592d  cmp     edi, 8
0x180005930  jnb     short loc_180005993
0x180005932  mov     rcx, [r14+30h]
0x180005936  lea     r15, [rbx+rbx*4]
0x18000593a  lea     r12, [rsp+1C0h+var_180]
0x18000593f  shl     r15, 5
0x180005943  lea     r12, [r12+rdi*8]
0x180005947  mov     esi, edi
0x180005949  add     rcx, r15
0x18000594c  mov     rdx, r12
0x18000594f  call    I_GetDescriptorFromRecipientInfo
0x180005954  test    eax, eax
0x180005956  jnz     short loc_18000598B
0x180005958  mov     rax, [r12]
0x18000595c  shl     rsi, 5
0x180005960  mov     rcx, [rax+8]
0x180005964  movups  xmm0, xmmword ptr [rcx]
0x180005967  movups  [rbp+rsi+0C0h+var_140], xmm0
0x18000596c  movups  xmm1, xmmword ptr [rcx+10h]
0x180005970  mov     rcx, [r14+30h]
0x180005974  add     rcx, r15
0x180005977  movups  [rbp+rsi+0C0h+var_130], xmm1
0x18000597c  inc     edi
0x18000597e  mov     dword ptr [rbp+rsi+0C0h+var_130], ebx
0x180005982  mov     dword ptr [rsp+1C0h+var_190], edi
0x180005986  mov     qword ptr [rbp+rsi+0C0h+var_130+8], rcx
0x18000598b  inc     ebx
0x18000598d  cmp     ebx, [r14+28h]
0x180005991  jb      short loc_18000592D
0x180005993  test    edi, edi
0x180005995  jz      short loc_1800059B5
0x180005997  xor     r9d, r9d
0x18000599a  mov     [rsp+1C0h+var_1A0], r13; __int64
0x18000599f  lea     rdx, [rsp+1C0h+var_190]
0x1800059a4  xor     ecx, ecx; Src
0x1800059a6  lea     r8d, [r9+1]
0x1800059aa  call    I_CreateProtectionDescriptor
0x1800059af  mov     esi, eax
0x1800059b1  test    eax, eax
0x1800059b3  jnz     short loc_1800059F5
0x1800059b5  xor     esi, esi
0x1800059b7  jmp     short loc_1800059C5
0x1800059b9  dec     edi
0x1800059bb  mov     rcx, [rsp+rdi*8+1C0h+var_180]
0x1800059c0  call    CNG_FreeProtectionDescriptor
0x1800059c5  test    edi, edi
0x1800059c7  jnz     short loc_1800059B9
0x1800059c9  mov     eax, esi
0x1800059cb  mov     rcx, [rbp+0C0h+var_40]
0x1800059d2  xor     rcx, rsp; StackCookie
0x1800059d5  call    __security_check_cookie
0x1800059da  mov     rbx, [rsp+1C0h+arg_10]
0x1800059e2  add     rsp, 190h
0x1800059e9  pop     r15
0x1800059eb  pop     r14
0x1800059ed  pop     r13
0x1800059ef  pop     r12
0x1800059f1  pop     rdi
0x1800059f2  pop     rsi
0x1800059f3  pop     rbp
0x1800059f4  retn
0x1800059f5  mov     r9d, 705h
0x1800059fb  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005a02  lea     rdx, aStatus; "Status"
0x180005a09  mov     ecx, eax
0x180005a0b  call    DebugTraceError
0x180005a10  jmp     short loc_1800059C5
```
