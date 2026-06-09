# RemoveSheetIndex

- ea: `0x10016fc0`
- end: `0x100170fe`
- name: `RemoveSheetIndex`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x10017110`

## callees

- `0x10013d10`
- `0x10016fc0`
- `0x100264c2`

## pseudocode

```c
int __fastcall RemoveSheetIndex(int a1, int *a2)
{
  int v3; // edi
  int v4; // eax
  __int16 *v5; // edi
  int v6; // edx
  int v7; // esi
  int i; // eax
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // eax
  int v13; // esi
  bool v14; // cc
  int v16; // [esp+10h] [ebp-10h]
  int v18; // [esp+18h] [ebp-8h]
  int v19; // [esp+18h] [ebp-8h]
  int v20; // [esp+1Ch] [ebp-4h]
  int savedregs; // [esp+20h] [ebp+0h] BYREF

  v20 = *(_DWORD *)(*(_DWORD *)(a1 + 48) + 40);
  v3 = 0;
  v4 = v20;
  v16 = 0;
  if ( *(__int16 *)(v20 + 8) > 0 )
  {
    do
    {
      v5 = *(__int16 **)(v4 + 4 * v3 + 16);
      if ( v5 )
      {
        v6 = 0;
        v7 = 0;
        for ( i = 0; i != 320; i += 10 )
        {
          if ( *(_DWORD *)&v5[i + 10] != -1 )
          {
            v9 = *(_DWORD *)&v5[i + 12];
            if ( v9 )
            {
              ++v6;
              *(_DWORD *)&v5[i + 12] = 0;
              if ( !v7 )
                v7 = v9;
            }
          }
        }
        v10 = a1;
        v18 = 20 * v6;
        if ( *(_DWORD *)a1 == 1 )
          v10 = *(_DWORD *)(a1 + 44);
        *(_DWORD *)(v10 + 104) = 0;
        *(_WORD *)(v10 + 96) = 0x4000;
        UpdateIndex(v7, (_DWORD *)a1, (int)&savedregs, -20 * v6, 1);
        BFRemoveFileSpace(*(_DWORD **)(a1 + 20), v7, v18);
        if ( *a2 > v7 )
          *a2 -= v18;
        if ( *(int *)(a1 + 4) >= 5 )
        {
          v11 = *((_DWORD *)v5 + 1);
          v19 = v11;
          if ( v11 )
          {
            v12 = a1;
            v13 = *v5 + 4;
            if ( *(_DWORD *)a1 == 1 )
              v12 = *(_DWORD *)(a1 + 44);
            *(_DWORD *)(v12 + 104) = 0;
            *(_WORD *)(v12 + 96) = 0x4000;
            UpdateIndex(v11, (_DWORD *)a1, (int)&savedregs, -v13, 1);
            BFRemoveFileSpace(*(_DWORD **)(a1 + 20), v19, v13);
            if ( *a2 > *((_DWORD *)v5 + 1) )
              *a2 = *a2 - *v5 - 4;
            *((_DWORD *)v5 + 1) = 0;
          }
        }
        v4 = v20;
      }
      v3 = v16 + 1;
      v14 = ++v16 < *(__int16 *)(v4 + 8);
      v4 = v20;
    }
    while ( v14 );
  }
  return 0;
}

```

## disassembly

```asm
0x10016fc0  mov     edi, edi
0x10016fc2  push    ebp
0x10016fc3  mov     ebp, esp
0x10016fc5  sub     esp, 14h
0x10016fc8  push    ebx
0x10016fc9  mov     ebx, ecx
0x10016fcb  mov     [ebp+var_C], edx
0x10016fce  push    esi
0x10016fcf  push    edi
0x10016fd0  xor     ecx, ecx
0x10016fd2  mov     eax, [ebx+30h]
0x10016fd5  mov     edi, [eax+28h]
0x10016fd8  mov     [ebp+var_4], edi
0x10016fdb  xor     edi, edi
0x10016fdd  mov     eax, [ebp+var_4]
0x10016fe0  mov     [ebp+var_10], edi
0x10016fe3  cmp     cx, [eax+8]
0x10016fe7  jge     loc_100170F5
0x10016fed  nop     dword ptr [eax]
0x10016ff0  mov     edi, [eax+edi*4+10h]
0x10016ff4  test    edi, edi
0x10016ff6  jz      loc_100170DF
0x10016ffc  xor     edx, edx
0x10016ffe  xor     esi, esi
0x10017000  xor     eax, eax
0x10017002  cmp     dword ptr [eax+edi+14h], 0FFFFFFFFh
0x10017007  jz      short loc_1001701F
0x10017009  mov     ecx, [eax+edi+18h]
0x1001700d  test    ecx, ecx
0x1001700f  jz      short loc_1001701F
0x10017011  inc     edx
0x10017012  mov     dword ptr [eax+edi+18h], 0
0x1001701a  test    esi, esi
0x1001701c  cmovz   esi, ecx
0x1001701f  add     eax, 14h
0x10017022  cmp     eax, 280h
0x10017027  jnz     short loc_10017002
0x10017029  lea     eax, [edx+edx*4]
0x1001702c  mov     ecx, ebx
0x1001702e  shl     eax, 2
0x10017031  cmp     dword ptr [ebx], 1
0x10017034  mov     [ebp+var_8], eax
0x10017037  jnz     short loc_1001703C
0x10017039  mov     ecx, [ebx+2Ch]
0x1001703c  mov     edx, 4000h
0x10017041  mov     dword ptr [ecx+68h], 0
0x10017048  mov     [ecx+60h], dx
0x1001704c  neg     eax
0x1001704e  push    1
0x10017050  push    eax
0x10017051  mov     edx, esi
0x10017053  mov     ecx, ebx
0x10017055  call    UpdateIndex
0x1001705a  push    [ebp+var_8]
0x1001705d  mov     ecx, [ebx+14h]
0x10017060  mov     edx, esi
0x10017062  call    _BFRemoveFileSpace@12; BFRemoveFileSpace(x,x,x)
0x10017067  mov     edx, [ebp+var_C]
0x1001706a  mov     eax, [edx]
0x1001706c  cmp     eax, esi
0x1001706e  jle     short loc_10017075
0x10017070  sub     eax, [ebp+var_8]
0x10017073  mov     [edx], eax
0x10017075  cmp     dword ptr [ebx+4], 5
0x10017079  jl      short loc_100170DC
0x1001707b  mov     ecx, [edi+4]
0x1001707e  mov     [ebp+var_8], ecx
0x10017081  test    ecx, ecx
0x10017083  jz      short loc_100170DC
0x10017085  movsx   esi, word ptr [edi]
0x10017088  mov     eax, ebx
0x1001708a  add     esi, 4
0x1001708d  cmp     dword ptr [ebx], 1
0x10017090  jnz     short loc_10017095
0x10017092  mov     eax, [ebx+2Ch]
0x10017095  mov     edx, 4000h
0x1001709a  mov     dword ptr [eax+68h], 0
0x100170a1  mov     [eax+60h], dx
0x100170a5  mov     eax, esi
0x100170a7  push    1
0x100170a9  neg     eax
0x100170ab  mov     edx, ecx
0x100170ad  push    eax
0x100170ae  mov     ecx, ebx
0x100170b0  call    UpdateIndex
0x100170b5  mov     edx, [ebp+var_8]
0x100170b8  mov     ecx, [ebx+14h]
0x100170bb  push    esi
0x100170bc  call    _BFRemoveFileSpace@12; BFRemoveFileSpace(x,x,x)
0x100170c1  mov     edx, [ebp+var_C]
0x100170c4  mov     ecx, [edx]
0x100170c6  cmp     ecx, [edi+4]
0x100170c9  jle     short loc_100170D5
0x100170cb  movsx   eax, word ptr [edi]
0x100170ce  sub     ecx, eax
0x100170d0  sub     ecx, 4
0x100170d3  mov     [edx], ecx
0x100170d5  mov     dword ptr [edi+4], 0
0x100170dc  mov     eax, [ebp+var_4]
0x100170df  mov     edi, [ebp+var_10]
0x100170e2  movsx   eax, word ptr [eax+8]
0x100170e6  inc     edi
0x100170e7  cmp     edi, eax
0x100170e9  mov     [ebp+var_10], edi
0x100170ec  mov     eax, [ebp+var_4]
0x100170ef  jl      loc_10016FF0
0x100170f5  pop     edi
0x100170f6  pop     esi
0x100170f7  xor     eax, eax
0x100170f9  pop     ebx
0x100170fa  mov     esp, ebp
0x100170fc  pop     ebp
0x100170fd  retn
```
