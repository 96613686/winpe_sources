# TlsGeneratePSKPreMasterKey

- ea: `0x180020a70`
- end: `0x180020bbc`
- name: `TlsGeneratePSKPreMasterKey`
- size: `332`
- prototype: `__int64 __fastcall(int, int, int, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180006070`

## callees

- `0x180007940`
- `0x1800081a8`
- `0x18000b654`
- `0x180020a70`
- `0x180024fb0`
- `0x180025660`

## string_xrefs

- `0x180020b8e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall TlsGeneratePSKPreMasterKey(int a1, int a2, int a3, __int64 *a4)
{
  int v6; // eax
  unsigned int v7; // ebp
  __int64 v8; // r9
  __int64 v9; // rcx
  size_t v10; // r14
  unsigned int v11; // ebx
  __int64 v12; // rax
  __int64 v13; // r12
  __int64 v14; // rsi
  void *v15; // rdx
  void *Src; // [rsp+60h] [rbp-38h] BYREF
  size_t Size; // [rsp+B8h] [rbp+20h] BYREF

  Src = 0;
  LODWORD(Size) = 0;
  if ( !a4 || *a4 || a1 != 4 )
  {
    v7 = -2146893779;
    v8 = 1058;
    v9 = 2148073517LL;
    goto LABEL_10;
  }
  v6 = TlsParseParameterList(a3, a2, 0, 0, 0, 0, 0, 0, (__int64)&Src, (__int64)&Size, 0);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 1076;
    v9 = (unsigned int)v6;
LABEL_10:
    DebugTraceError(v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v8);
    return v7;
  }
  v10 = (unsigned int)Size;
  v11 = 2 * Size + 16;
  v12 = SafeAllocaAllocateFromHeap(v11);
  v13 = v12;
  if ( !v12 )
  {
    v7 = -2146893810;
    v8 = 1094;
    v9 = 2148073486LL;
    goto LABEL_10;
  }
  v14 = v12 + 12;
  *(_DWORD *)v12 = v11;
  *(_DWORD *)(v12 + 4) = 1936944183;
  *(_BYTE *)(v12 + 12) = BYTE1(v10);
  *(_DWORD *)(v12 + 8) = a2;
  *(_BYTE *)(v12 + 13) = v10;
  memset((void *)(v12 + 14), 0, v10);
  v15 = Src;
  *(_BYTE *)((unsigned int)(v10 + 2) + v14) = BYTE1(v10);
  *(_BYTE *)((unsigned int)(v10 + 3) + v14) = v10;
  memmove((void *)(v14 + (unsigned int)(v10 + 4)), v15, v10);
  *a4 = v13;
  return v7;
}

```

## disassembly

```asm
0x180020a70  mov     r11, rsp
0x180020a73  mov     [r11+8], rbx
0x180020a77  mov     [r11+10h], rbp
0x180020a7b  push    rsi
0x180020a7c  push    rdi
0x180020a7d  push    r12
0x180020a7f  push    r14
0x180020a81  push    r15
0x180020a83  sub     rsp, 70h
0x180020a87  xor     esi, esi
0x180020a89  mov     r15, r9
0x180020a8c  mov     [r11-38h], rsi
0x180020a90  mov     rax, r8
0x180020a93  mov     [r11+20h], esi
0x180020a97  mov     edi, edx
0x180020a99  test    r9, r9
0x180020a9c  jz      loc_180020B7E
0x180020aa2  cmp     [r9], rsi
0x180020aa5  jnz     loc_180020B7E
0x180020aab  cmp     ecx, 4
0x180020aae  jnz     loc_180020B7E
0x180020ab4  mov     [r11-48h], rsi
0x180020ab8  lea     rcx, [r11+20h]
0x180020abc  mov     [r11-50h], rcx
0x180020ac0  xor     r9d, r9d
0x180020ac3  lea     rcx, [r11-38h]
0x180020ac7  xor     r8d, r8d
0x180020aca  mov     [r11-58h], rcx
0x180020ace  mov     rcx, rax
0x180020ad1  mov     [r11-60h], rsi
0x180020ad5  mov     [r11-68h], rsi
0x180020ad9  mov     [r11-70h], rsi
0x180020add  mov     [r11-78h], rsi
0x180020ae1  call    TlsParseParameterList
0x180020ae6  mov     ebp, eax
0x180020ae8  test    eax, eax
0x180020aea  jns     short loc_180020AF9
0x180020aec  mov     r9d, 434h
0x180020af2  mov     ecx, eax
0x180020af4  jmp     loc_180020B8E
0x180020af9  mov     r14d, dword ptr [rsp+98h+Size]
0x180020b01  lea     ebx, ds:10h[r14*2]
0x180020b09  mov     ecx, ebx
0x180020b0b  call    SafeAllocaAllocateFromHeap
0x180020b10  mov     r12, rax
0x180020b13  test    rax, rax
0x180020b16  jnz     short loc_180020B2A
0x180020b18  mov     ebp, 8009000Eh
0x180020b1d  mov     r9d, 446h
0x180020b23  mov     ecx, 8009000Eh
0x180020b28  jmp     short loc_180020B8E
0x180020b2a  lea     rsi, [rax+0Ch]
0x180020b2e  mov     [rax], ebx
0x180020b30  movzx   ebx, r14w
0x180020b34  mov     dword ptr [rax+4], 73736C37h
0x180020b3b  shr     bx, 8
0x180020b3f  lea     rcx, [rsi+2]; void *
0x180020b43  mov     r8, r14; Size
0x180020b46  mov     [rsi], bl
0x180020b48  xor     edx, edx; Val
0x180020b4a  mov     [rax+8], edi
0x180020b4d  mov     [rsi+1], r14b
0x180020b51  call    memset
0x180020b56  mov     rdx, [rsp+98h+Src]; Src
0x180020b5b  lea     eax, [r14+2]
0x180020b5f  lea     ecx, [r14+4]
0x180020b63  mov     r8, r14; Size
0x180020b66  add     rcx, rsi; void *
0x180020b69  mov     [rax+rsi], bl
0x180020b6c  lea     eax, [r14+3]
0x180020b70  mov     [rax+rsi], r14b
0x180020b74  call    memmove
0x180020b79  mov     [r15], r12
0x180020b7c  jmp     short loc_180020BA1
0x180020b7e  mov     ebp, 8009002Dh
0x180020b83  mov     r9d, 422h
0x180020b89  mov     ecx, 8009002Dh
0x180020b8e  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180020b95  lea     rdx, aStatus; "Status"
0x180020b9c  call    DebugTraceError
0x180020ba1  lea     r11, [rsp+98h+var_28]
0x180020ba6  mov     eax, ebp
0x180020ba8  mov     rbx, [r11+30h]
0x180020bac  mov     rbp, [r11+38h]
0x180020bb0  mov     rsp, r11
0x180020bb3  pop     r15
0x180020bb5  pop     r14
0x180020bb7  pop     r12
0x180020bb9  pop     rdi
0x180020bba  pop     rsi
0x180020bbb  retn
```
