# RtlImageDirectoryEntryToData

- ea: `0x180082a00`
- end: `0x180082bb0`
- name: `RtlImageDirectoryEntryToData`
- size: `432`
- prototype: ``
- caller_count: `26`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180028510`
- `0x180050718`
- `0x180074140`
- `0x18007d9a8`
- `0x18008234c`
- `0x180082490`
- `0x180082640`
- `0x180082850`
- `0x1800832c0`
- `0x180085904`
- `0x18008612c`
- `0x1800b6f08`
- `0x1800c2290`
- `0x1800c8e64`
- `0x1800d1c34`
- `0x1800d218c`
- `0x1800fcd6c`
- `0x1800fd044`
- `0x1800fe670`
- `0x180105e10`
- `0x18010a750`
- `0x18010d874`
- `0x1801379c4`
- `0x18013b4d0`
- `0x18015c378`
- `0x18015c478`

## callees

- `0x18001f070`
- `0x180082a00`
- `0x180084a90`

## pseudocode

```c
__int64 __fastcall RtlImageDirectoryEntryToData(__int64 a1, char a2, unsigned __int16 a3, _DWORD *a4)
{
  __int64 v5; // rbx
  __int64 v6; // rsi
  __int64 v7; // rdx
  __int64 v9; // rdi
  int v10; // eax
  __int64 v11; // r9
  __int16 v12; // ax
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v16; // r10
  unsigned int v17; // r11d
  unsigned int *v18; // rdx
  unsigned int i; // r8d
  __int64 v20; // r9
  char v21; // cl
  int v22; // ecx
  __int64 v23; // [rsp+40h] [rbp+8h] BYREF

  v5 = 0;
  v6 = a3;
  v7 = a1 & 1;
  v23 = 0;
  v9 = a1;
  if ( (a1 & 2) != 0 || (a1 & 1) != 0 )
  {
    v21 = 0;
    v9 &= 0xFFFFFFFFFFFFFFFCuLL;
    if ( !v7 )
      v21 = a2;
    a2 = v21;
  }
  v10 = RtlImageNtHeaderEx(1, v9, 0, &v23);
  v11 = v23;
  if ( !v23 )
    goto LABEL_11;
  v12 = *(_WORD *)(v23 + 24);
  if ( v12 == 267 )
  {
    if ( (unsigned int)v6 < *(_DWORD *)(v23 + 116) )
    {
      v16 = *(unsigned int *)(v23 + 8 * v6 + 120);
      if ( !(_DWORD)v16 )
        goto LABEL_28;
      *a4 = *(_DWORD *)(v23 + 8 * v6 + 124);
      if ( a2 || (unsigned int)v16 < *(_DWORD *)(v11 + 84) )
      {
        v5 = v9 + v16;
        v10 = 0;
        goto LABEL_11;
      }
      v17 = *(unsigned __int16 *)(v11 + 6);
      v18 = (unsigned int *)(v11 + *(unsigned __int16 *)(v11 + 20) + 24LL);
      for ( i = 0; i < v17; ++i )
      {
        v20 = v18[3];
        if ( (unsigned int)v16 >= (unsigned int)v20 && (unsigned int)v16 < (unsigned int)v20 + v18[4] )
        {
          v5 = v9 + v18[5] - v20 + v16;
          if ( v5 )
            goto LABEL_10;
          break;
        }
        v18 += 10;
      }
    }
LABEL_24:
    v10 = -1073741811;
    goto LABEL_11;
  }
  if ( v12 != 523 || (unsigned int)v6 >= *(_DWORD *)(v23 + 132) )
    goto LABEL_24;
  v13 = *(unsigned int *)(v23 + 8 * v6 + 136);
  if ( !(_DWORD)v13 )
  {
LABEL_28:
    v10 = -1073741822;
    goto LABEL_11;
  }
  *a4 = *(_DWORD *)(v23 + 8 * v6 + 140);
  if ( a2 || (unsigned int)v13 < *(_DWORD *)(v11 + 84) )
  {
    v5 = v9 + v13;
LABEL_10:
    v10 = 0;
  }
  else
  {
    v5 = RtlAddressInSectionTable(v11, v9, (unsigned int)v13);
    v22 = 0;
    if ( !v5 )
      v22 = -1073741811;
    v10 = v22;
  }
LABEL_11:
  v14 = 0;
  if ( v10 >= 0 )
    return v5;
  return v14;
}

```

## disassembly

```asm
0x180082a00  mov     [rsp+arg_8], rbx
0x180082a05  mov     [rsp+arg_10], rbp
0x180082a0a  push    rsi
0x180082a0b  push    rdi
0x180082a0c  push    r14
0x180082a0e  sub     rsp, 20h
0x180082a12  movzx   ebp, dl
0x180082a15  xor     ebx, ebx
0x180082a17  mov     rdx, rcx
0x180082a1a  movzx   esi, r8w
0x180082a1e  and     edx, 1
0x180082a21  mov     [rsp+38h+arg_0], 0
0x180082a2a  mov     r14, r9
0x180082a2d  mov     rdi, rcx
0x180082a30  test    cl, 2
0x180082a33  jnz     loc_180082B58
0x180082a39  test    rdx, rdx
0x180082a3c  jnz     loc_180082B58
0x180082a42  lea     r9, [rsp+38h+arg_0]
0x180082a47  xor     r8d, r8d
0x180082a4a  mov     rdx, rdi
0x180082a4d  mov     ecx, 1
0x180082a52  call    RtlImageNtHeaderEx
0x180082a57  mov     r9, [rsp+38h+arg_0]
0x180082a5c  test    r9, r9
0x180082a5f  jz      short loc_180082AB5
0x180082a61  movzx   eax, word ptr [r9+18h]
0x180082a66  mov     ecx, 10Bh
0x180082a6b  cmp     ax, cx
0x180082a6e  jz      short loc_180082AD4
0x180082a70  mov     ecx, 20Bh
0x180082a75  cmp     ax, cx
0x180082a78  jnz     loc_180082B4E
0x180082a7e  cmp     esi, [r9+84h]
0x180082a85  jnb     loc_180082B4E
0x180082a8b  mov     ecx, [r9+rsi*8+88h]
0x180082a93  test    ecx, ecx
0x180082a95  jz      loc_180082B6C
0x180082a9b  mov     eax, [r9+rsi*8+8Ch]
0x180082aa3  mov     [r14], eax
0x180082aa6  test    bpl, bpl
0x180082aa9  jz      loc_180082B76
0x180082aaf  lea     rbx, [rdi+rcx]
0x180082ab3  xor     eax, eax
0x180082ab5  mov     rbp, [rsp+38h+arg_10]
0x180082aba  xor     ecx, ecx
0x180082abc  test    eax, eax
0x180082abe  cmovns  rcx, rbx
0x180082ac2  mov     rbx, [rsp+38h+arg_8]
0x180082ac7  mov     rax, rcx
0x180082aca  add     rsp, 20h
0x180082ace  pop     r14
0x180082ad0  pop     rdi
0x180082ad1  pop     rsi
0x180082ad2  retn
0x180082ad4  cmp     esi, [r9+74h]
0x180082ad8  jnb     short loc_180082B4E
0x180082ada  mov     r10d, [r9+rsi*8+78h]
0x180082adf  test    r10d, r10d
0x180082ae2  jz      loc_180082B6C
0x180082ae8  mov     eax, [r9+rsi*8+7Ch]
0x180082aed  mov     [r14], eax
0x180082af0  test    bpl, bpl
0x180082af3  jnz     loc_180082BA5
0x180082af9  cmp     r10d, [r9+54h]
0x180082afd  jb      loc_180082BA5
0x180082b03  movzx   edx, word ptr [r9+14h]
0x180082b08  movzx   r11d, word ptr [r9+6]
0x180082b0d  add     rdx, 18h
0x180082b11  add     rdx, r9
0x180082b14  xor     r8d, r8d
0x180082b17  cmp     r8d, r11d
0x180082b1a  jnb     short loc_180082B4E
0x180082b1c  mov     r9d, [rdx+0Ch]
0x180082b20  cmp     r10d, r9d
0x180082b23  jb      short loc_180082B30
0x180082b25  mov     ecx, [rdx+10h]
0x180082b28  add     ecx, r9d
0x180082b2b  cmp     r10d, ecx
0x180082b2e  jb      short loc_180082B39
0x180082b30  add     rdx, 28h ; '('
0x180082b34  inc     r8d
0x180082b37  jmp     short loc_180082B17
0x180082b39  mov     eax, [rdx+14h]
0x180082b3c  mov     rbx, r10
0x180082b3f  sub     rax, r9
0x180082b42  add     rax, rdi
0x180082b45  add     rbx, rax
0x180082b48  jnz     loc_180082AB3
0x180082b4e  mov     eax, 0C000000Dh
0x180082b53  jmp     loc_180082AB5
0x180082b58  xor     ecx, ecx
0x180082b5a  and     rdi, 0FFFFFFFFFFFFFFFCh
0x180082b5e  test    rdx, rdx
0x180082b61  cmovz   ecx, ebp
0x180082b64  movzx   ebp, cl
0x180082b67  jmp     loc_180082A42
0x180082b6c  mov     eax, 0C0000002h
0x180082b71  jmp     loc_180082AB5
0x180082b76  cmp     ecx, [r9+54h]
0x180082b7a  jb      loc_180082AAF
0x180082b80  mov     r8d, ecx
0x180082b83  mov     rdx, rdi
0x180082b86  mov     rcx, r9
0x180082b89  call    RtlAddressInSectionTable
0x180082b8e  mov     rbx, rax
0x180082b91  xor     ecx, ecx
0x180082b93  mov     eax, 0C000000Dh
0x180082b98  test    rbx, rbx
0x180082b9b  cmovz   ecx, eax
0x180082b9e  mov     eax, ecx
0x180082ba0  jmp     loc_180082AB5
0x180082ba5  lea     rbx, [rdi+r10]
0x180082ba9  xor     eax, eax
0x180082bab  jmp     loc_180082AB5
```
