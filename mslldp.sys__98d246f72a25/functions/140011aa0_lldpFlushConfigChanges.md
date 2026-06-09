# lldpFlushConfigChanges

- ea: `0x140011aa0`
- end: `0x140011ca6`
- name: `lldpFlushConfigChanges`
- size: `518`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x14001186c`

## callees

- `0x140002180`
- `0x140003d80`
- `0x140006720`
- `0x140011a40`
- `0x140011aa0`
- `0x140011cac`

## pseudocode

```c
int __fastcall lldpFlushConfigChanges(char *Context, char a2)
{
  unsigned int v2; // r13d
  int v4; // ebp
  char v5; // al
  int v7; // edx
  int v8; // ecx
  unsigned int v9; // edi
  int v10; // r9d
  int v11; // r15d
  int v12; // r11d
  int v13; // r8d
  int v14; // r10d
  char v15; // di
  int result; // eax
  char v17; // r8
  char v18; // dl
  int v19; // ebp
  char v20; // cl
  int v21; // r15d
  char v22; // al
  __int128 v23; // xmm1

  v2 = *((_DWORD *)Context + 66);
  v4 = *((_DWORD *)Context + 62);
  v5 = 0;
  v7 = *((_DWORD *)Context + 67);
  v8 = *((_DWORD *)Context + 64);
  v9 = *((_DWORD *)Context + 73);
  v10 = *((_DWORD *)Context + 63);
  v11 = *((_DWORD *)Context + 69);
  v12 = *((_DWORD *)Context + 74);
  v13 = *((_DWORD *)Context + 71);
  v14 = *((_DWORD *)Context + 70);
  if ( v2 != v9 )
  {
    if ( v2 <= v9 )
    {
      if ( v2 >= v9 )
        goto LABEL_2;
      if ( (signed int)v9 >= *((_DWORD *)Context + 218) )
        v9 = *((_DWORD *)Context + 218);
      *((_DWORD *)Context + 218) = v9;
    }
    else
    {
      *((_DWORD *)Context + 218) += v2 - v9;
    }
    v5 = 0;
  }
LABEL_2:
  if ( (v8 != v13 || (v15 = 0, v7 != v12)) && (v15 = 1, v8 != v13) || v10 != v14 )
  {
    lldpUpdateTxTtl(Context);
    v5 = 0;
  }
  if ( v4 != v11 )
  {
    v17 = v4 && (v4 == 1 || v4 == 3);
    v18 = v11 && (v11 == 1 || v11 == 3);
    v20 = 0;
    if ( v4 )
    {
      v19 = v4 - 1;
      if ( v19 )
      {
        if ( (unsigned int)(v19 - 1) < 2 )
          v20 = 1;
      }
    }
    v22 = 0;
    if ( v11 )
    {
      v21 = v11 - 1;
      if ( v21 )
      {
        if ( (unsigned int)(v21 - 1) < 2 )
          v22 = 1;
      }
    }
    if ( v17 != v18 )
      v15 = 1;
    if ( v20 == v22 )
    {
      v5 = 0;
    }
    else
    {
      lldpAdjustRxPacketFilters((__int64)Context);
      v5 = 1;
    }
  }
  if ( a2 && !v5 )
    lldpAdjustRxPacketFilters((__int64)Context);
  if ( v15 )
    lldpEnableTxFastMode(Context);
  result = memcmp(Context + 248, Context + 276, 0x1Cu);
  if ( result )
  {
    v23 = *(_OWORD *)(Context + 260);
    *(_OWORD *)(Context + 276) = *(_OWORD *)(Context + 248);
    *((_OWORD *)Context + 18) = v23;
    if ( !a2 )
      return lldpQueueChangeNotificationEx(Context);
  }
  return result;
}

```

## disassembly

```asm
0x140011aa0  push    rbx
0x140011aa2  push    rbp
0x140011aa3  push    rsi
0x140011aa4  push    rdi
0x140011aa5  push    r12
0x140011aa7  push    r13
0x140011aa9  push    r14
0x140011aab  push    r15
0x140011aad  sub     rsp, 28h
0x140011ab1  mov     r13d, [rcx+108h]
0x140011ab8  mov     rbx, rcx
0x140011abb  mov     ebp, [rcx+0F8h]
0x140011ac1  xor     al, al
0x140011ac3  movzx   r12d, dl
0x140011ac7  mov     edx, [rcx+10Ch]
0x140011acd  mov     ecx, [rcx+100h]
0x140011ad3  mov     edi, [rbx+124h]
0x140011ad9  mov     r9d, [rbx+0FCh]
0x140011ae0  mov     r15d, [rbx+114h]
0x140011ae7  mov     r11d, [rbx+128h]
0x140011aee  mov     r8d, [rbx+11Ch]
0x140011af5  mov     r10d, [rbx+118h]
0x140011afc  cmp     r13d, edi
0x140011aff  jnz     loc_140011BE8
0x140011b05  cmp     ecx, r8d
0x140011b08  jnz     short loc_140011B6B
0x140011b0a  xor     dil, dil
0x140011b0d  cmp     edx, r11d
0x140011b10  jnz     short loc_140011B6B
0x140011b12  cmp     r9d, r10d
0x140011b15  jnz     short loc_140011B73
0x140011b17  cmp     ebp, r15d
0x140011b1a  jnz     short loc_140011B7F
0x140011b1c  test    r12b, r12b
0x140011b1f  jnz     short loc_140011B5D
0x140011b21  test    dil, dil
0x140011b24  jnz     loc_140011C5F
0x140011b2a  mov     r8d, 1Ch; Size
0x140011b30  lea     rdx, [rbx+114h]; Buf2
0x140011b37  lea     rcx, [rbx+0F8h]; Buf1
0x140011b3e  call    memcmp
0x140011b43  test    eax, eax
0x140011b45  jnz     loc_140011C6C
0x140011b4b  add     rsp, 28h
0x140011b4f  pop     r15
0x140011b51  pop     r14
0x140011b53  pop     r13
0x140011b55  pop     r12
0x140011b57  pop     rdi
0x140011b58  pop     rsi
0x140011b59  pop     rbp
0x140011b5a  pop     rbx
0x140011b5b  retn
0x140011b5d  test    al, al
0x140011b5f  jnz     short loc_140011B21
0x140011b61  mov     rcx, rbx
0x140011b64  call    lldpAdjustRxPacketFilters
0x140011b69  jmp     short loc_140011B21
0x140011b6b  mov     dil, 1
0x140011b6e  cmp     ecx, r8d
0x140011b71  jz      short loc_140011B12
0x140011b73  mov     rcx, rbx
0x140011b76  call    lldpUpdateTxTtl
0x140011b7b  xor     al, al
0x140011b7d  jmp     short loc_140011B17
0x140011b7f  mov     ecx, ebp
0x140011b81  test    ebp, ebp
0x140011b83  jz      short loc_140011B9C
0x140011b85  sub     ecx, 1
0x140011b88  jz      loc_140011C22
0x140011b8e  sub     ecx, 1
0x140011b91  jz      short loc_140011B9C
0x140011b93  cmp     ecx, 1
0x140011b96  jz      loc_140011C22
0x140011b9c  xor     r8b, r8b
0x140011b9f  mov     ecx, r15d
0x140011ba2  test    r15d, r15d
0x140011ba5  jz      short loc_140011BB6
0x140011ba7  sub     ecx, 1
0x140011baa  jz      short loc_140011C2A
0x140011bac  sub     ecx, 1
0x140011baf  jz      short loc_140011BB6
0x140011bb1  cmp     ecx, 1
0x140011bb4  jz      short loc_140011C2A
0x140011bb6  xor     dl, dl
0x140011bb8  test    ebp, ebp
0x140011bba  jz      short loc_140011BCB
0x140011bbc  sub     ebp, 1
0x140011bbf  jz      short loc_140011BCB
0x140011bc1  sub     ebp, 1
0x140011bc4  jz      short loc_140011C2E
0x140011bc6  cmp     ebp, 1
0x140011bc9  jz      short loc_140011C2E
0x140011bcb  xor     cl, cl
0x140011bcd  test    r15d, r15d
0x140011bd0  jz      short loc_140011BE4
0x140011bd2  sub     r15d, 1
0x140011bd6  jz      short loc_140011BE4
0x140011bd8  sub     r15d, 1
0x140011bdc  jz      short loc_140011C32
0x140011bde  cmp     r15d, 1
0x140011be2  jz      short loc_140011C32
0x140011be4  xor     al, al
0x140011be6  jmp     short loc_140011C34
0x140011be8  jbe     short loc_140011BFF
0x140011bea  mov     eax, [rbx+368h]
0x140011bf0  sub     r13d, edi
0x140011bf3  add     r13d, eax
0x140011bf6  mov     [rbx+368h], r13d
0x140011bfd  jmp     short loc_140011C1B
0x140011bff  jnb     loc_140011B05
0x140011c05  mov     eax, [rbx+368h]
0x140011c0b  cmp     edi, eax
0x140011c0d  jl      short loc_140011C15
0x140011c0f  mov     edi, [rbx+368h]
0x140011c15  mov     [rbx+368h], edi
0x140011c1b  xor     al, al
0x140011c1d  jmp     loc_140011B05
0x140011c22  mov     r8b, 1
0x140011c25  jmp     loc_140011B9F
0x140011c2a  mov     dl, 1
0x140011c2c  jmp     short loc_140011BB8
0x140011c2e  mov     cl, 1
0x140011c30  jmp     short loc_140011BCD
0x140011c32  mov     al, 1
0x140011c34  cmp     r8b, dl
0x140011c37  movzx   edi, dil
0x140011c3b  mov     r9d, 1
0x140011c41  cmovnz  edi, r9d
0x140011c45  cmp     cl, al
0x140011c47  jz      short loc_140011C58
0x140011c49  mov     rcx, rbx
0x140011c4c  call    lldpAdjustRxPacketFilters
0x140011c51  mov     al, 1
0x140011c53  jmp     loc_140011B1C
0x140011c58  xor     al, al
0x140011c5a  jmp     loc_140011B1C
0x140011c5f  mov     rcx, rbx
0x140011c62  call    lldpEnableTxFastMode
0x140011c67  jmp     loc_140011B2A
0x140011c6c  movups  xmm0, xmmword ptr [rbx+0F8h]
0x140011c73  movups  xmm1, xmmword ptr [rbx+104h]
0x140011c7a  movups  xmmword ptr [rbx+114h], xmm0
0x140011c81  movups  xmmword ptr [rbx+120h], xmm1
0x140011c88  test    r12b, r12b
0x140011c8b  jnz     loc_140011B4B
0x140011c91  xor     edx, edx
0x140011c93  mov     r8d, 4
0x140011c99  mov     rcx, rbx; Context
0x140011c9c  call    lldpQueueChangeNotificationEx
0x140011ca1  jmp     loc_140011B4B
```
