# UpdateFrameSize(x,x,x)

- ea: `0x10004e8d`
- end: `0x10004f9e`
- name: `_UpdateFrameSize@12`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x100042f3`

## callees

- `0x10004dbe`
- `0x10004e8d`

## pseudocode

```c
void __fastcall UpdateFrameSize(int a1, int a2, int a3)
{
  int v5; // ecx
  __int16 v6; // di
  int v7; // ebx
  int v8; // [esp+8h] [ebp-Ch]
  int v9; // [esp+Ch] [ebp-8h]

  if ( *(_WORD *)(a1 + 212) )
  {
    if ( *(_DWORD *)(a1 + 220) )
      a2 = PaddedFrameSize(*(_DWORD *)(a1 + 220));
    *(_DWORD *)(a1 + 8 * *(__int16 *)(a1 + 1034) + 232) = a2;
    v5 = *(__int16 *)(a1 + 214);
    v8 = a2 + *(_DWORD *)(a1 + 1036);
    *(_DWORD *)(a1 + 1036) = v8;
    v9 = v5;
    v6 = (*(__int16 *)(a1 + 1034) + 1) % v5;
    *(_WORD *)(a1 + 1034) = v6;
    if ( *(_WORD *)(a1 + 1032) != 0xFFFF )
    {
      if ( !a3 )
        LOWORD(v5) = *(_WORD *)(a1 + 1032);
      *(_WORD *)(a1 + 1032) = v5 - 1;
    }
    v7 = *(_DWORD *)(a1 + 8 * v6 + 232);
    *(_DWORD *)(a1 + 8 * v6 + 232) = *(unsigned __int16 *)(a1 + 230)
                                   * (2 * *(_DWORD *)(a1 + 216) - v8)
                                   / (*(unsigned __int16 *)(a1 + 228) + *(unsigned __int16 *)(a1 + 230) * (v9 - 1));
    *(_DWORD *)(a1 + 8 * *(__int16 *)(a1 + 1034) + 236) = *(_DWORD *)(a1 + 8 * *(__int16 *)(a1 + 1034) + 232)
                                                        * *(unsigned __int16 *)(a1 + 228)
                                                        / *(unsigned __int16 *)(a1 + 230);
    *(_DWORD *)(a1 + 1036) -= v7;
  }
}

```

## disassembly

```asm
0x10004e8d  mov     edi, edi
0x10004e8f  push    ebp
0x10004e90  mov     ebp, esp
0x10004e92  sub     esp, 0Ch
0x10004e95  push    esi
0x10004e96  mov     esi, ecx
0x10004e98  push    edi
0x10004e99  mov     edi, edx
0x10004e9b  mov     [ebp+var_4], esi
0x10004e9e  cmp     word ptr [esi+0D4h], 0
0x10004ea6  jz      loc_10004F98
0x10004eac  mov     eax, [esi+0DCh]
0x10004eb2  test    eax, eax
0x10004eb4  jz      short loc_10004EC6
0x10004eb6  mov     edx, [esi+0E0h]
0x10004ebc  mov     ecx, edi
0x10004ebe  push    eax
0x10004ebf  call    _PaddedFrameSize@12; PaddedFrameSize(x,x,x)
0x10004ec4  mov     edi, eax
0x10004ec6  movsx   eax, word ptr [esi+40Ah]
0x10004ecd  mov     [esi+eax*8+0E8h], edi
0x10004ed4  mov     eax, [esi+40Ch]
0x10004eda  movsx   ecx, word ptr [esi+0D6h]
0x10004ee1  add     eax, edi
0x10004ee3  mov     [ebp+var_C], eax
0x10004ee6  mov     [esi+40Ch], eax
0x10004eec  movsx   eax, word ptr [esi+40Ah]
0x10004ef3  inc     eax
0x10004ef4  mov     [ebp+var_8], ecx
0x10004ef7  cdq
0x10004ef8  idiv    ecx
0x10004efa  movzx   eax, dx
0x10004efd  mov     edi, eax
0x10004eff  mov     [esi+40Ah], ax
0x10004f06  movzx   eax, word ptr [esi+408h]
0x10004f0d  mov     edx, eax
0x10004f0f  cmp     ax, 0FFFFh
0x10004f13  jz      short loc_10004F28
0x10004f15  cmp     [ebp+arg_0], 0
0x10004f19  movzx   ecx, cx
0x10004f1c  cmovz   ecx, eax
0x10004f1f  dec     cx
0x10004f21  mov     [esi+408h], cx
0x10004f28  movzx   ecx, word ptr [esi+0E6h]
0x10004f2f  mov     edx, [ebp+var_4]
0x10004f32  movsx   edi, di
0x10004f35  push    ebx
0x10004f36  movzx   eax, word ptr [edx+0E4h]
0x10004f3d  mov     ebx, [esi+edi*8+0E8h]
0x10004f44  mov     esi, [ebp+var_8]
0x10004f47  dec     esi
0x10004f48  imul    esi, ecx
0x10004f4b  add     esi, eax
0x10004f4d  mov     eax, [edx+0D8h]
0x10004f53  add     eax, eax
0x10004f55  sub     eax, [ebp+var_C]
0x10004f58  imul    eax, ecx
0x10004f5b  mov     ecx, [ebp+var_4]
0x10004f5e  cdq
0x10004f5f  idiv    esi
0x10004f61  mov     [ecx+edi*8+0E8h], eax
0x10004f68  mov     edi, ecx
0x10004f6a  movsx   esi, word ptr [edi+40Ah]
0x10004f71  movzx   eax, word ptr [edi+0E4h]
0x10004f78  movzx   ecx, word ptr [edi+0E6h]
0x10004f7f  imul    eax, [edi+esi*8+0E8h]
0x10004f87  cdq
0x10004f88  idiv    ecx
0x10004f8a  mov     [edi+esi*8+0ECh], eax
0x10004f91  sub     [edi+40Ch], ebx
0x10004f97  pop     ebx
0x10004f98  pop     edi
0x10004f99  pop     esi
0x10004f9a  leave
0x10004f9b  retn    4
```
