# iSNSBuildRequestPacket

- ea: `0x18000d5c0`
- end: `0x18000d684`
- name: `iSNSBuildRequestPacket`
- size: `196`
- prototype: `__int64 __fastcall(_WORD *, unsigned int, __int16, __int16, __int64, _DWORD *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c474`
- `0x18000ce28`
- `0x18000d364`
- `0x18000d430`
- `0x18000d490`
- `0x18000d68c`

## callees

- `0x18000d5c0`
- `0x18001bf3c`

## pseudocode

```c
__int64 __fastcall iSNSBuildRequestPacket(_WORD *a1, unsigned int a2, __int16 a3, __int16 a4, __int64 a5, _DWORD *a6)
{
  __int16 v8; // bp
  int v9; // eax
  int v10; // edi
  _WORD *v11; // rcx
  char *v12; // r14
  _WORD *v13; // [rsp+20h] [rbp-38h] BYREF

  if ( a2 < 0x14 )
    return 1;
  v8 = (_WORD)a1 + 12;
  v9 = 0;
  v10 = 0;
  *a1 = 256;
  a1[1] = __ROR2__(a3, 8);
  a1[3] = 156;
  a1[4] = __ROR2__(a4, 8);
  a1[5] = 0;
  v11 = a1 + 6;
  v12 = (char *)a1 + a2;
  v13 = v11;
  if ( *(_BYTE *)(a5 + 4) )
  {
    while ( !v9 )
    {
      v9 = iSNSAppendAttribute(&v13, v12, a5 + 16LL * v10++);
      if ( !*(_BYTE *)(a5 + 16LL * v10 + 4) )
      {
        if ( !v9 )
        {
          LODWORD(v11) = (_DWORD)v13;
          goto LABEL_8;
        }
        return 2;
      }
    }
    return 2;
  }
  else
  {
LABEL_8:
    a1[2] = __ROR2__((_WORD)v11 - v8, 8);
    *a6 = (_DWORD)v11 - (_DWORD)a1;
    return 0;
  }
}

```

## disassembly

```asm
0x18000d5c0  push    rbx
0x18000d5c2  push    rbp
0x18000d5c3  push    rsi
0x18000d5c4  push    rdi
0x18000d5c5  push    r14
0x18000d5c7  sub     rsp, 30h
0x18000d5cb  mov     rbx, rcx
0x18000d5ce  cmp     edx, 14h
0x18000d5d1  jnb     short loc_18000D5DD
0x18000d5d3  mov     eax, 1
0x18000d5d8  jmp     loc_18000D672
0x18000d5dd  mov     rsi, [rsp+58h+arg_20]
0x18000d5e5  lea     rbp, [rcx+0Ch]
0x18000d5e9  ror     r8w, 8
0x18000d5ee  xor     eax, eax
0x18000d5f0  ror     r9w, 8
0x18000d5f5  xor     edi, edi
0x18000d5f7  mov     word ptr [rcx], 100h
0x18000d5fc  mov     [rcx+2], r8w
0x18000d601  mov     word ptr [rcx+6], 9Ch
0x18000d607  mov     [rcx+8], r9w
0x18000d60c  mov     [rcx+0Ah], ax
0x18000d610  mov     rcx, rbp
0x18000d613  mov     r14d, edx
0x18000d616  add     r14, rbx
0x18000d619  mov     [rsp+58h+var_38], rcx
0x18000d61e  cmp     [rsi+4], al
0x18000d621  jz      short loc_18000D656
0x18000d623  test    eax, eax
0x18000d625  jnz     short loc_18000D67D
0x18000d627  movsxd  r8, edi
0x18000d62a  lea     rcx, [rsp+58h+var_38]
0x18000d62f  shl     r8, 4
0x18000d633  mov     rdx, r14
0x18000d636  add     r8, rsi
0x18000d639  call    iSNSAppendAttribute
0x18000d63e  inc     edi
0x18000d640  movsxd  rcx, edi
0x18000d643  add     rcx, rcx
0x18000d646  cmp     byte ptr [rsi+rcx*8+4], 0
0x18000d64b  jnz     short loc_18000D623
0x18000d64d  test    eax, eax
0x18000d64f  jnz     short loc_18000D67D
0x18000d651  mov     rcx, [rsp+58h+var_38]
0x18000d656  movzx   eax, cx
0x18000d659  sub     ecx, ebx
0x18000d65b  sub     ax, bp
0x18000d65e  ror     ax, 8
0x18000d662  mov     [rbx+4], ax
0x18000d666  mov     rax, [rsp+58h+arg_28]
0x18000d66e  mov     [rax], ecx
0x18000d670  xor     eax, eax
0x18000d672  add     rsp, 30h
0x18000d676  pop     r14
0x18000d678  pop     rdi
0x18000d679  pop     rsi
0x18000d67a  pop     rbp
0x18000d67b  pop     rbx
0x18000d67c  retn
0x18000d67d  mov     eax, 2
0x18000d682  jmp     short loc_18000D672
```
