# QuicCryptoWriteCryptoFrames

- ea: `0x14001b7ec`
- end: `0x14001ba3c`
- name: `QuicCryptoWriteCryptoFrames`
- size: `592`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001bbc8`

## callees

- `0x14001b7ec`
- `0x14001ba44`
- `0x14001bcf0`
- `0x1400337e4`

## pseudocode

```c
__int64 __fastcall QuicCryptoWriteCryptoFrames(
        __int64 a1,
        __int64 a2,
        unsigned __int16 *a3,
        unsigned __int16 a4,
        __int64 a5)
{
  int v5; // r12d
  unsigned __int16 v7; // cx
  __int64 i; // r9
  unsigned int v10; // r15d
  unsigned int v11; // ebp
  unsigned int v12; // r14d
  unsigned int v13; // edx
  unsigned int v14; // esi
  __int64 v15; // rdi
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  unsigned int v19; // ecx
  __int64 v20; // rdi
  int v21; // ecx
  unsigned int v22; // eax
  unsigned int v23; // edx
  __int64 v25; // [rsp+38h] [rbp-40h]
  unsigned __int16 v27; // [rsp+98h] [rbp+20h] BYREF

  v5 = a4;
  v7 = *a3;
  for ( i = a2; v7 < (unsigned __int16)v5 && *(_BYTE *)(*(_QWORD *)(i + 408) + 90LL) < 0xCu; i = a2 )
  {
    v10 = *(_DWORD *)(a1 + 216);
    v11 = v10;
    v12 = *(_DWORD *)(a1 + 220);
    if ( v10 >= v12 )
      v11 = *(_DWORD *)(a1 + 212);
    v13 = *(_DWORD *)(a1 + 40);
    if ( v11 == v13 )
      break;
    v14 = v11 + v5 - v7;
    if ( v10 < v12 && v14 > v12 && v12 != *(_DWORD *)(a1 + 212) )
      v14 = *(_DWORD *)(a1 + 220);
    if ( v11 == *(_DWORD *)(a1 + 204) )
    {
      v15 = 0;
LABEL_12:
      if ( v14 > v13 )
        v14 = *(_DWORD *)(a1 + 40);
    }
    else
    {
      v19 = 0;
      do
      {
        if ( v19 >= *(_DWORD *)(a1 + 232) )
        {
          v15 = 0;
          goto LABEL_12;
        }
        v20 = v19++;
        v15 = *(_QWORD *)(a1 + 224) + 16 * v20;
        if ( !v15 )
          goto LABEL_12;
      }
      while ( *(_QWORD *)v15 < (unsigned __int64)v11 );
      if ( (unsigned __int64)v14 > *(_QWORD *)v15 )
        v14 = *(_DWORD *)v15;
    }
    v16 = *(unsigned __int8 *)(i + 376);
    if ( *(_DWORD *)(a1 + 852) == -817679509 )
    {
      v17 = v16 - 1;
      if ( v17 )
      {
        v18 = v17 - 1;
        if ( !v18 )
        {
          CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\crypto.c", 797, "0");
          __int2c();
LABEL_34:
          i = a2;
          v21 = 0;
          v13 = 0;
          goto LABEL_37;
        }
LABEL_28:
        if ( v18 == 1 )
        {
          v22 = *(_DWORD *)(a1 + 48);
          v21 = *(_DWORD *)(a1 + 44);
          if ( !v22 )
            v22 = *(_DWORD *)(a1 + 40);
          v13 = v22;
        }
        else
        {
          v21 = *(_DWORD *)(a1 + 48);
        }
        goto LABEL_37;
      }
    }
    else if ( *(_BYTE *)(i + 376) )
    {
      v18 = v16 - 1;
      if ( !v18 )
      {
        CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\crypto.c", 827, "0");
        __int2c();
        goto LABEL_34;
      }
      goto LABEL_28;
    }
    v21 = 0;
    if ( *(_DWORD *)(a1 + 44) )
      v13 = *(_DWORD *)(a1 + 44);
LABEL_37:
    if ( v14 > v13 )
      v14 = v13;
    if ( v11 >= v14 )
      return QuicCryptoDumpSendState(a1);
    v25 = *(_QWORD *)(i + 408);
    v27 = v14 - v11;
    if ( !(unsigned __int8)QuicCryptoWriteOneFrame(a1, v21, v11, (unsigned int)&v27, (__int64)a3, v5, a5, v25) )
      return QuicCryptoDumpSendState(a1);
    v23 = v11 + v27;
    if ( v10 < v12 )
    {
      *(_DWORD *)(a1 + 216) = v23;
      if ( v15 )
      {
        if ( v23 == *(_QWORD *)v15 )
          *(_DWORD *)(a1 + 216) = v23 + *(_DWORD *)(v15 + 8);
      }
    }
    if ( *(_DWORD *)(a1 + 212) < v23 )
    {
      *(_DWORD *)(a1 + 212) = v23;
      if ( v15 )
      {
        if ( v23 == *(_QWORD *)v15 )
          *(_DWORD *)(a1 + 212) = v23 + *(_DWORD *)(v15 + 8);
      }
    }
    if ( *(_DWORD *)(a1 + 204) < v23 )
      *(_DWORD *)(a1 + 204) = v23;
    v7 = *a3;
  }
  return QuicCryptoDumpSendState(a1);
}

```

## disassembly

```asm
0x14001b7ec  mov     [rsp+arg_0], rbx
0x14001b7f1  mov     [rsp+arg_8], rdx
0x14001b7f6  push    rbp
0x14001b7f7  push    rsi
0x14001b7f8  push    rdi
0x14001b7f9  push    r12
0x14001b7fb  push    r13
0x14001b7fd  push    r14
0x14001b7ff  push    r15
0x14001b801  sub     rsp, 40h
0x14001b805  movzx   r12d, r9w
0x14001b809  mov     rbx, rcx
0x14001b80c  movzx   ecx, word ptr [r8]
0x14001b810  mov     r9, rdx
0x14001b813  mov     r13, r8
0x14001b816  jmp     loc_14001BA11
0x14001b81b  mov     rax, [r9+198h]
0x14001b822  cmp     byte ptr [rax+5Ah], 0Ch
0x14001b826  jnb     loc_14001BA1B
0x14001b82c  mov     r15d, [rbx+0D8h]
0x14001b833  mov     ebp, r15d
0x14001b836  mov     r14d, [rbx+0DCh]
0x14001b83d  cmp     r15d, r14d
0x14001b840  jb      short loc_14001B848
0x14001b842  mov     ebp, [rbx+0D4h]
0x14001b848  mov     edx, [rbx+28h]
0x14001b84b  cmp     ebp, edx
0x14001b84d  jz      loc_14001BA1B
0x14001b853  movzx   eax, cx
0x14001b856  mov     esi, r12d
0x14001b859  sub     esi, eax
0x14001b85b  add     esi, ebp
0x14001b85d  cmp     r15d, r14d
0x14001b860  jnb     short loc_14001B872
0x14001b862  cmp     esi, r14d
0x14001b865  jbe     short loc_14001B872
0x14001b867  cmp     r14d, [rbx+0D4h]
0x14001b86e  cmovnz  esi, r14d
0x14001b872  cmp     ebp, [rbx+0CCh]
0x14001b878  jnz     short loc_14001B8BF
0x14001b87a  xor     edi, edi
0x14001b87c  cmp     esi, edx
0x14001b87e  cmova   esi, edx
0x14001b881  cmp     dword ptr [rbx+354h], 0CF43336Bh
0x14001b88b  movzx   ecx, byte ptr [r9+178h]
0x14001b893  jnz     short loc_14001B8FC
0x14001b895  sub     ecx, 1
0x14001b898  jz      loc_14001B946
0x14001b89e  sub     ecx, 1
0x14001b8a1  jnz     short loc_14001B905
0x14001b8a3  lea     r8, a0; "0"
0x14001b8aa  mov     edx, 31Dh
0x14001b8af  lea     rcx, aCW1SMsquicSrcC_15; "C:\\__w\\1\\s\\msquic\\src\\core\\crypt"...
0x14001b8b6  call    CxPlatLogAssert
0x14001b8bb  int     2Ch; Windows NT - assertion failure
0x14001b8bd  jmp     short loc_14001B938
0x14001b8bf  mov     r8d, [rbx+0E8h]
0x14001b8c6  xor     ecx, ecx
0x14001b8c8  cmp     ecx, r8d
0x14001b8cb  jnb     short loc_14001B8EA
0x14001b8cd  mov     edi, ecx
0x14001b8cf  inc     ecx
0x14001b8d1  shl     rdi, 4
0x14001b8d5  add     rdi, [rbx+0E0h]
0x14001b8dc  test    rdi, rdi
0x14001b8df  jz      short loc_14001B87C
0x14001b8e1  mov     eax, ebp
0x14001b8e3  cmp     [rdi], rax
0x14001b8e6  jb      short loc_14001B8C8
0x14001b8e8  jmp     short loc_14001B8F1
0x14001b8ea  xor     edi, edi
0x14001b8ec  test    rdi, rdi
0x14001b8ef  jz      short loc_14001B87C
0x14001b8f1  mov     eax, esi
0x14001b8f3  cmp     rax, [rdi]
0x14001b8f6  jbe     short loc_14001B881
0x14001b8f8  mov     esi, [rdi]
0x14001b8fa  jmp     short loc_14001B881
0x14001b8fc  test    ecx, ecx
0x14001b8fe  jz      short loc_14001B946
0x14001b900  sub     ecx, 1
0x14001b903  jz      short loc_14001B91E
0x14001b905  cmp     ecx, 1
0x14001b908  jz      short loc_14001B90F
0x14001b90a  mov     ecx, [rbx+30h]
0x14001b90d  jmp     short loc_14001B950
0x14001b90f  mov     eax, [rbx+30h]
0x14001b912  test    eax, eax
0x14001b914  mov     ecx, [rbx+2Ch]
0x14001b917  cmovz   eax, edx
0x14001b91a  mov     edx, eax
0x14001b91c  jmp     short loc_14001B950
0x14001b91e  lea     r8, a0; "0"
0x14001b925  mov     edx, 33Bh
0x14001b92a  lea     rcx, aCW1SMsquicSrcC_15; "C:\\__w\\1\\s\\msquic\\src\\core\\crypt"...
0x14001b931  call    CxPlatLogAssert
0x14001b936  int     2Ch; Windows NT - assertion failure
0x14001b938  mov     r9, [rsp+78h+arg_8]
0x14001b940  xor     ecx, ecx
0x14001b942  xor     edx, edx
0x14001b944  jmp     short loc_14001B950
0x14001b946  mov     eax, [rbx+2Ch]
0x14001b949  xor     ecx, ecx
0x14001b94b  test    eax, eax
0x14001b94d  cmovnz  edx, eax
0x14001b950  cmp     esi, edx
0x14001b952  cmova   esi, edx
0x14001b955  cmp     ebp, esi
0x14001b957  jnb     loc_14001BA1B
0x14001b95d  mov     rax, [r9+198h]
0x14001b964  mov     edx, ecx
0x14001b966  mov     [rsp+78h+var_40], rax
0x14001b96b  lea     r9, [rsp+78h+arg_18]
0x14001b973  mov     rax, [rsp+78h+arg_20]
0x14001b97b  sub     si, bp
0x14001b97e  mov     [rsp+78h+var_48], rax
0x14001b983  mov     r8d, ebp
0x14001b986  mov     [rsp+78h+var_50], r12w
0x14001b98c  mov     rcx, rbx
0x14001b98f  mov     [rsp+78h+var_58], r13
0x14001b994  mov     [rsp+78h+arg_18], si
0x14001b99c  call    QuicCryptoWriteOneFrame
0x14001b9a1  test    al, al
0x14001b9a3  jz      short loc_14001BA1B
0x14001b9a5  movzx   edx, [rsp+78h+arg_18]
0x14001b9ad  add     edx, ebp
0x14001b9af  cmp     r15d, r14d
0x14001b9b2  jnb     short loc_14001B9D1
0x14001b9b4  mov     [rbx+0D8h], edx
0x14001b9ba  test    rdi, rdi
0x14001b9bd  jz      short loc_14001B9D1
0x14001b9bf  mov     eax, edx
0x14001b9c1  cmp     rax, [rdi]
0x14001b9c4  jnz     short loc_14001B9D1
0x14001b9c6  mov     ecx, [rdi+8]
0x14001b9c9  add     ecx, edx
0x14001b9cb  mov     [rbx+0D8h], ecx
0x14001b9d1  cmp     [rbx+0D4h], edx
0x14001b9d7  jnb     short loc_14001B9F6
0x14001b9d9  mov     [rbx+0D4h], edx
0x14001b9df  test    rdi, rdi
0x14001b9e2  jz      short loc_14001B9F6
0x14001b9e4  mov     eax, edx
0x14001b9e6  cmp     rax, [rdi]
0x14001b9e9  jnz     short loc_14001B9F6
0x14001b9eb  mov     ecx, [rdi+8]
0x14001b9ee  add     ecx, edx
0x14001b9f0  mov     [rbx+0D4h], ecx
0x14001b9f6  cmp     [rbx+0CCh], edx
0x14001b9fc  jnb     short loc_14001BA04
0x14001b9fe  mov     [rbx+0CCh], edx
0x14001ba04  movzx   ecx, word ptr [r13+0]
0x14001ba09  mov     r9, [rsp+78h+arg_8]
0x14001ba11  cmp     cx, r12w
0x14001ba15  jb      loc_14001B81B
0x14001ba1b  mov     rcx, rbx
0x14001ba1e  call    QuicCryptoDumpSendState
0x14001ba23  mov     rbx, [rsp+78h+arg_0]
0x14001ba2b  add     rsp, 40h
0x14001ba2f  pop     r15
0x14001ba31  pop     r14
0x14001ba33  pop     r13
0x14001ba35  pop     r12
0x14001ba37  pop     rdi
0x14001ba38  pop     rsi
0x14001ba39  pop     rbp
0x14001ba3a  retn
```
