# CVCompress(x,x,x,x,x,x,x)

- ea: `0x1000425b`
- end: `0x100042f3`
- name: `_CVCompress@28`
- size: `152`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x100042f3`
- `0x1000fc97`

## callees

- `0x1000425b`
- `0x10004de7`
- `0x10013581`

## pseudocode

```c
int __fastcall CVCompress(int a1, int a2, int a3, _BYTE *a4, int a5, int a6, int a7, int a8, int a9)
{
  unsigned int v10; // eax
  _BYTE v12[4]; // [esp+14h] [ebp-20h] BYREF
  unsigned int v13; // [esp+18h] [ebp-1Ch]
  int v14; // [esp+1Ch] [ebp-18h]
  _DWORD v15[5]; // [esp+20h] [ebp-14h] BYREF

  v15[3] = a2;
  v14 = a1;
  if ( *a4 )
  {
    *(_BYTE *)(a1 + 82) = 0;
    *(_BYTE *)(*(_DWORD *)(a1 + 196) + 10) = 16;
  }
  else
  {
    *(_BYTE *)(a1 + 82) = 1;
    *(_BYTE *)(*(_DWORD *)(a1 + 196) + 10) = 17;
  }
  CalcFrameSize(v15, v12, &a6, &a7);
  if ( v15[0] )
    v10 = (v15[0] - ((*(_BYTE *)(a1 + 106) & 2) != 0 ? 0x18 : 0) - 10) / (unsigned int)*(__int16 *)(a1 + 208) - 12;
  else
    v10 = 0;
  v13 = v10;
  *(_DWORD *)(a1 + 168) = 0;
  *(_DWORD *)(a1 + 144) = 0;
  _setjmp3(a1, 0);
  return sub_100042F3(a3, a4, a5, a6, a7);
}

```

## disassembly

```asm
0x1000425b  mov     edi, edi
0x1000425d  push    ebp
0x1000425e  mov     ebp, esp
0x10004260  sub     esp, 28h
0x10004263  mov     eax, [ebp+arg_4]
0x10004266  push    ebx
0x10004267  push    esi
0x10004268  xor     ebx, ebx
0x1000426a  mov     [ebp+var_8], edx
0x1000426d  mov     esi, ecx
0x1000426f  mov     [ebp+var_24], edx
0x10004272  push    edi
0x10004273  mov     [ebp+var_18], esi
0x10004276  cmp     [eax], bl
0x10004278  jz      short loc_10004289
0x1000427a  mov     [esi+52h], bl
0x1000427d  mov     eax, [esi+0C4h]
0x10004283  mov     byte ptr [eax+0Ah], 10h
0x10004287  jmp     short loc_10004297
0x10004289  mov     byte ptr [esi+52h], 1
0x1000428d  mov     eax, [esi+0C4h]
0x10004293  mov     byte ptr [eax+0Ah], 11h
0x10004297  mov     edx, [ebp+arg_8]
0x1000429a  lea     eax, [ebp+arg_10]
0x1000429d  push    eax
0x1000429e  lea     eax, [ebp+arg_C]
0x100042a1  push    eax
0x100042a2  lea     eax, [ebp+var_20]
0x100042a5  push    eax
0x100042a6  lea     eax, [ebp+var_14]
0x100042a9  push    eax
0x100042aa  call    _CalcFrameSize@24; CalcFrameSize(x,x,x,x,x,x)
0x100042af  mov     eax, [ebp+var_14]
0x100042b2  test    eax, eax
0x100042b4  jz      short loc_100042DB
0x100042b6  mov     cl, [esi+6Ah]
0x100042b9  and     cl, 2
0x100042bc  movzx   ecx, cl
0x100042bf  neg     ecx
0x100042c1  sbb     ecx, ecx
0x100042c3  xor     edx, edx
0x100042c5  and     ecx, 18h
0x100042c8  sub     eax, ecx
0x100042ca  movsx   ecx, word ptr [esi+0D0h]
0x100042d1  sub     eax, 0Ah
0x100042d4  div     ecx
0x100042d6  sub     eax, 0Ch
0x100042d9  jmp     short loc_100042DD
0x100042db  mov     eax, ebx
0x100042dd  push    ebx
0x100042de  push    esi
0x100042df  mov     [ebp+var_1C], eax
0x100042e2  mov     [esi+0A8h], ebx
0x100042e8  mov     [esi+90h], ebx
0x100042ee  call    __setjmp3
```
