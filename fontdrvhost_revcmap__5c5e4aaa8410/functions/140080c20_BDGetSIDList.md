# BDGetSIDList

- ea: `0x140080c20`
- end: `0x140080cdf`
- name: `BDGetSIDList`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14007da08`

## callees

- `0x140034478`
- `0x14003b310`
- `0x1400687ac`
- `0x14007e634`
- `0x140080c20`

## pseudocode

```c
__int64 __fastcall BDGetSIDList(__int64 a1)
{
  unsigned int v2; // ebx
  unsigned __int16 v3; // si
  __int64 v4; // rdx
  __int64 v5; // r14
  __int64 v6; // rcx
  __int16 v8; // [rsp+20h] [rbp-28h]
  int v9; // [rsp+24h] [rbp-24h]
  __int64 v10; // [rsp+58h] [rbp+10h] BYREF

  v2 = -1;
  v10 = 0;
  v3 = 0;
  if ( (unsigned int)ValidateIFILE(*(_QWORD *)a1, &v10) == 1 )
  {
    LOBYTE(v4) = 1;
    v5 = v10;
    if ( (unsigned int)GetFontParseInfo(v10, v4, 0xFFFFFFFFLL) == 1 )
    {
      v2 = 0;
      if ( (*(_BYTE *)(v5 + 1109) & 8) != 0 )
      {
        v6 = *(_QWORD *)(v5 + 24);
        v3 = *(_WORD *)(v6 + 274);
        if ( *(_WORD *)(a1 + 8) >= v3 )
        {
          v9 = -1;
          v8 = *(_WORD *)(v6 + 274);
          v2 = -((unsigned int)CFFEnumerateDict(*(_QWORD *)(v6 + 176), 7, a1, FillInSIDList, v8) != 0);
        }
      }
    }
  }
  *(_WORD *)(a1 + 8) = v3;
  DoneWithParsedInfo(v10);
  return v2;
}

```

## disassembly

```asm
0x140080c20  mov     rax, rsp
0x140080c23  mov     [rax+18h], rbx
0x140080c27  mov     [rax+8], rcx
0x140080c2b  push    rsi
0x140080c2c  push    rdi
0x140080c2d  push    r14
0x140080c2f  sub     rsp, 30h
0x140080c33  mov     rdi, rcx
0x140080c36  or      ebx, 0FFFFFFFFh
0x140080c39  mov     qword ptr [rax+10h], 0
0x140080c41  xor     esi, esi
0x140080c43  mov     [rax-28h], si
0x140080c47  lea     rdx, [rax+10h]
0x140080c4b  mov     rcx, [rcx]
0x140080c4e  call    ValidateIFILE
0x140080c53  cmp     eax, 1
0x140080c56  jnz     short loc_140080CC1
0x140080c58  or      r8d, ebx
0x140080c5b  mov     dl, al
0x140080c5d  mov     r14, [rsp+48h+arg_8]
0x140080c62  mov     rcx, r14
0x140080c65  call    GetFontParseInfo
0x140080c6a  cmp     eax, 1
0x140080c6d  jnz     short loc_140080CC1
0x140080c6f  xor     ebx, ebx
0x140080c71  mov     [rsp+48h+var_24], ebx
0x140080c75  test    byte ptr [r14+455h], 8
0x140080c7d  jz      short loc_140080CC1
0x140080c7f  mov     rcx, [r14+18h]
0x140080c83  movzx   eax, word ptr [rcx+112h]
0x140080c8a  movzx   esi, ax
0x140080c8d  mov     [rsp+48h+var_28], ax
0x140080c92  cmp     [rdi+8], ax
0x140080c96  jb      short loc_140080CC1
0x140080c98  mov     [rsp+48h+var_24], 0FFFFFFFFh
0x140080ca0  lea     r9, FillInSIDList
0x140080ca7  mov     r8, rdi
0x140080caa  lea     edx, [rbx+7]
0x140080cad  mov     rcx, [rcx+0B0h]
0x140080cb4  call    CFFEnumerateDict
0x140080cb9  neg     eax
0x140080cbb  sbb     ebx, ebx
0x140080cbd  mov     [rsp+48h+var_24], ebx
0x140080cc1  mov     [rdi+8], si
0x140080cc5  mov     rcx, [rsp+48h+arg_8]
0x140080cca  call    DoneWithParsedInfo
0x140080ccf  mov     eax, ebx
0x140080cd1  mov     rbx, [rsp+48h+arg_10]
0x140080cd6  add     rsp, 30h
0x140080cda  pop     r14
0x140080cdc  pop     rdi
0x140080cdd  pop     rsi
0x140080cde  retn
0x1400979d3  push    rbp
0x1400979d5  sub     rsp, 20h
0x1400979d9  mov     rbp, rdx
0x1400979dc  movzx   ecx, word ptr [rbp+20h]
0x1400979e0  mov     rax, [rbp+50h]
0x1400979e4  mov     [rax+8], cx
0x1400979e8  mov     rcx, [rbp+58h]
0x1400979ec  add     rsp, 20h
0x1400979f0  pop     rbp
0x1400979f1  jmp     DoneWithParsedInfo
```
