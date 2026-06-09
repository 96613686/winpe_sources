# ASN1BERDecLength

- ea: `0x180003a60`
- end: `0x180003bb8`
- name: `ASN1BERDecLength`
- size: `344`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180001f80`
- `0x1800022c0`
- `0x180003070`
- `0x1800030d0`
- `0x180009c10`
- `0x180009e70`
- `0x180009f20`
- `0x180009fa0`

## callees

- `0x180003a60`
- `0x180004310`

## pseudocode

```c
__int64 __fastcall ASN1BERDecLength(__int64 a1, unsigned int *a2, _DWORD *a3)
{
  int v4; // r9d
  int v5; // r10d
  unsigned __int8 *v6; // rax
  unsigned int v7; // edi
  unsigned int v8; // edx
  unsigned __int8 *v9; // rbx
  unsigned int *v10; // r9
  unsigned int v12; // eax
  __int64 v13; // rax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // edx

  if ( a3 )
    *a3 = 0;
  v4 = *(_DWORD *)(a1 + 16);
  v5 = *(_DWORD *)(a1 + 24);
  if ( !(v5 + v4 - *(_DWORD *)(a1 + 40)) )
    goto LABEL_26;
  v6 = *(unsigned __int8 **)(a1 + 40);
  v7 = 1;
  v8 = *v6;
  v9 = v6 + 1;
  *(_QWORD *)(a1 + 40) = v6 + 1;
  if ( v8 < 0x80 )
  {
    v10 = a2;
    goto LABEL_6;
  }
  if ( v8 != 128 )
  {
    if ( v8 > 0x84 )
    {
      v16 = -1003;
      goto LABEL_27;
    }
    v12 = v8 - 128;
    if ( v8 - 128 <= v5 + v4 - (int)v9 )
    {
      v8 = 0;
      v10 = a2;
      if ( v12 != 2 )
      {
        v14 = v12 - 1;
        if ( !v14 )
          goto LABEL_15;
        v15 = v14 - 2;
        if ( v15 )
        {
          if ( v15 != 1 )
          {
LABEL_6:
            *v10 = v8;
            if ( !a3 )
              goto LABEL_7;
            goto LABEL_21;
          }
          v8 = *v9++ << 24;
          *(_QWORD *)(a1 + 40) = v9;
        }
        v8 |= *v9++ << 16;
        *(_QWORD *)(a1 + 40) = v9;
      }
      v8 |= *v9++ << 8;
      *(_QWORD *)(a1 + 40) = v9;
LABEL_15:
      v8 |= *v9;
      *(_QWORD *)(a1 + 40) = v9 + 1;
      goto LABEL_6;
    }
LABEL_26:
    v16 = -1002;
LABEL_27:
    ASN1DecSetError(a1, v16);
    return 0;
  }
  *a2 = 0;
  if ( a3 )
  {
    *a3 = 1;
LABEL_21:
    if ( *a3 )
      return v7;
LABEL_7:
    if ( *a2 > *(_DWORD *)(a1 + 16) + *(_DWORD *)(a1 + 24) - *(_DWORD *)(a1 + 40) )
    {
      ASN1DecSetError(a1, 0xFFFFFC16);
      return 0;
    }
    return v7;
  }
  do
  {
    v13 = *(_QWORD *)(a1 + 56);
    *(_DWORD *)(a1 + 32) = -1003;
    if ( a1 == v13 )
      break;
    a1 = v13;
  }
  while ( v13 );
  return 0;
}

```

## disassembly

```asm
0x180003a60  sub     rsp, 28h
0x180003a64  mov     r11, rdx
0x180003a67  test    r8, r8
0x180003a6a  jz      short loc_180003A73
0x180003a6c  mov     dword ptr [r8], 0
0x180003a73  mov     r9d, [rcx+10h]
0x180003a77  mov     eax, r9d
0x180003a7a  sub     eax, [rcx+28h]
0x180003a7d  mov     r10d, [rcx+18h]
0x180003a81  add     eax, r10d
0x180003a84  mov     [rsp+28h+arg_0], rbx
0x180003a89  mov     [rsp+28h+var_8], rdi
0x180003a8e  cmp     eax, 1
0x180003a91  jb      loc_180003B7D
0x180003a97  mov     rax, [rcx+28h]
0x180003a9b  mov     edi, 1
0x180003aa0  movzx   edx, byte ptr [rax]
0x180003aa3  lea     rbx, [rax+1]
0x180003aa7  mov     [rcx+28h], rbx
0x180003aab  cmp     edx, 80h
0x180003ab1  jnb     short loc_180003AE5
0x180003ab3  mov     r9, r11
0x180003ab6  mov     [r9], edx
0x180003ab9  test    r8, r8
0x180003abc  jnz     loc_180003B54
0x180003ac2  mov     eax, [rcx+18h]
0x180003ac5  sub     eax, [rcx+28h]
0x180003ac8  add     eax, [rcx+10h]
0x180003acb  cmp     [r11], eax
0x180003ace  ja      loc_180003B89
0x180003ad4  mov     eax, edi
0x180003ad6  mov     rdi, [rsp+28h+var_8]
0x180003adb  mov     rbx, [rsp+28h+arg_0]
0x180003ae0  add     rsp, 28h
0x180003ae4  retn
0x180003ae5  jz      short loc_180003B29
0x180003ae7  cmp     edx, 84h
0x180003aed  ja      loc_180003BB1
0x180003af3  sub     r9d, ebx
0x180003af6  lea     eax, [rdx-80h]
0x180003af9  add     r9d, r10d
0x180003afc  cmp     eax, r9d
0x180003aff  ja      short loc_180003B7D
0x180003b01  xor     edx, edx
0x180003b03  mov     r9, r11
0x180003b06  cmp     eax, 2
0x180003b09  jnz     short loc_180003B63
0x180003b0b  movzx   eax, byte ptr [rbx]
0x180003b0e  shl     eax, 8
0x180003b11  or      edx, eax
0x180003b13  inc     rbx
0x180003b16  mov     [rcx+28h], rbx
0x180003b1a  movzx   eax, byte ptr [rbx]
0x180003b1d  or      edx, eax
0x180003b1f  lea     rax, [rbx+1]
0x180003b23  mov     [rcx+28h], rax
0x180003b27  jmp     short loc_180003AB6
0x180003b29  mov     dword ptr [r11], 0
0x180003b30  test    r8, r8
0x180003b33  jnz     short loc_180003B51
0x180003b35  mov     rax, [rcx+38h]
0x180003b39  mov     dword ptr [rcx+20h], 0FFFFFC15h
0x180003b40  cmp     rcx, rax
0x180003b43  jz      short loc_180003B4D
0x180003b45  mov     rcx, rax
0x180003b48  test    rax, rax
0x180003b4b  jnz     short loc_180003B35
0x180003b4d  xor     eax, eax
0x180003b4f  jmp     short loc_180003AD6
0x180003b51  mov     [r8], edi
0x180003b54  cmp     dword ptr [r8], 0
0x180003b58  jz      loc_180003AC2
0x180003b5e  jmp     loc_180003AD4
0x180003b63  sub     eax, edi
0x180003b65  jz      short loc_180003B1A
0x180003b67  sub     eax, 2
0x180003b6a  jnz     short loc_180003B9A
0x180003b6c  movzx   eax, byte ptr [rbx]
0x180003b6f  shl     eax, 10h
0x180003b72  or      edx, eax
0x180003b74  inc     rbx
0x180003b77  mov     [rcx+28h], rbx
0x180003b7b  jmp     short loc_180003B0B
0x180003b7d  mov     edx, 0FFFFFC16h
0x180003b82  call    ASN1DecSetError
0x180003b87  jmp     short loc_180003B4D
0x180003b89  mov     edx, 0FFFFFC16h
0x180003b8e  call    ASN1DecSetError
0x180003b93  xor     edi, edi
0x180003b95  jmp     loc_180003AD4
0x180003b9a  cmp     eax, edi
0x180003b9c  jnz     loc_180003AB6
0x180003ba2  movzx   edx, byte ptr [rbx]
0x180003ba5  shl     edx, 18h
0x180003ba8  inc     rbx
0x180003bab  mov     [rcx+28h], rbx
0x180003baf  jmp     short loc_180003B6C
0x180003bb1  mov     edx, 0FFFFFC15h
0x180003bb6  jmp     short loc_180003B82
```
