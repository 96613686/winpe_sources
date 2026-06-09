# CopyDBIDs(tagDBID *,tagDBID const *)

- ea: `0x10025940`
- end: `0x10025b2c`
- name: `?CopyDBIDs@@YGJPAUtagDBID@@PBU1@@Z`
- size: `492`
- prototype: `int __stdcall(struct tagDBID *, const struct tagDBID *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x100123d0`
- `0x100131d0`
- `0x100132e0`

## callees

- `0x1000ba50`
- `0x10017830`
- `0x1001c6d0`
- `0x10025940`

## pseudocode

```c
int __fastcall CopyDBIDs(int a1, int a2)
{
  _WORD *v4; // edi
  _WORD *v5; // ecx
  int v7; // eax
  int result; // eax
  _WORD *v9; // edi
  _WORD *v10; // ecx
  int v12; // eax
  _OWORD *v13; // eax
  _WORD *v14; // edi
  _WORD *v15; // ecx
  int v17; // eax
  void *v18; // ecx
  _OWORD *v19; // eax
  const unsigned __int16 *v20; // [esp+0h] [ebp-14h]
  int v21; // [esp+4h] [ebp-10h]
  size_t *pcchNewDestLength; // [esp+Ch] [ebp-8h]

  if ( !a1 || !a2 )
    return 1;
  *(_DWORD *)(a1 + 16) = *(_DWORD *)(a2 + 16);
  switch ( *(_DWORD *)(a2 + 16) )
  {
    case 0:
      *(_OWORD *)a1 = *(_OWORD *)a2;
      v4 = *(_WORD **)(a2 + 20);
      v5 = v4 + 1;
      while ( *v4++ )
        ;
      pcchNewDestLength = (size_t *)(v4 - v5);
      v7 = (*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
             *(_DWORD *)(*(_DWORD *)Sys + 12),
             Sys,
             2 * ((_DWORD)pcchNewDestLength + 1));
      *(_DWORD *)(a1 + 20) = v7;
      if ( v7 )
        goto LABEL_18;
      goto LABEL_20;
    case 1:
      *(_OWORD *)a1 = *(_OWORD *)a2;
      goto LABEL_9;
    case 2:
      v9 = *(_WORD **)(a2 + 20);
      v10 = v9 + 1;
      while ( *v9++ )
        ;
      pcchNewDestLength = (size_t *)(v9 - v10);
      v12 = (*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
              *(_DWORD *)(*(_DWORD *)Sys + 12),
              Sys,
              2 * ((_DWORD)pcchNewDestLength + 1));
      *(_DWORD *)(a1 + 20) = v12;
      if ( v12 )
        goto LABEL_18;
      goto LABEL_20;
    case 3:
      v13 = (_OWORD *)(*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
                        *(_DWORD *)(*(_DWORD *)Sys + 12),
                        Sys,
                        16);
      *(_DWORD *)a1 = v13;
      if ( !v13 )
        goto LABEL_20;
      *v13 = *(_OWORD *)*(_DWORD *)a2;
      v14 = *(_WORD **)(a2 + 20);
      v15 = v14 + 1;
      while ( *v14++ )
        ;
      pcchNewDestLength = (size_t *)(v14 - v15);
      v17 = (*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
              *(_DWORD *)(*(_DWORD *)Sys + 12),
              Sys,
              2 * ((_DWORD)pcchNewDestLength + 1));
      *(_DWORD *)(a1 + 20) = v17;
      if ( v17 )
      {
LABEL_18:
        WCSNCPY(*(_DWORD *)(a2 + 20), pcchNewDestLength, v20, v21);
        result = 0;
      }
      else
      {
        System::Free(v18);
        *(_DWORD *)a1 = 0;
LABEL_20:
        result = -2147024882;
      }
      break;
    case 4:
      v19 = (_OWORD *)(*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
                        *(_DWORD *)(*(_DWORD *)Sys + 12),
                        Sys,
                        16);
      *(_DWORD *)a1 = v19;
      if ( !v19 )
        goto LABEL_20;
      *v19 = *(_OWORD *)*(_DWORD *)a2;
      *(_DWORD *)(a1 + 20) = *(_DWORD *)(a2 + 20);
      result = 0;
      break;
    case 5:
LABEL_9:
      *(_DWORD *)(a1 + 20) = *(_DWORD *)(a2 + 20);
      result = 0;
      break;
    case 6:
      result = 0;
      *(_OWORD *)a1 = *(_OWORD *)a2;
      break;
    default:
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x10025940  mov     edi, edi
0x10025942  push    ebp
0x10025943  mov     ebp, esp
0x10025945  sub     esp, 8
0x10025948  push    ebx
0x10025949  push    esi; int
0x1002594a  push    edi; unsigned __int16 *
0x1002594b  mov     edi, ecx
0x1002594d  mov     ebx, edx
0x1002594f  mov     [ebp+var_4], edi
0x10025952  test    edi, edi
0x10025954  jz      def_10025974; jumptable 10025974 default case
0x1002595a  test    ebx, ebx
0x1002595c  jz      def_10025974; jumptable 10025974 default case
0x10025962  mov     eax, [ebx+10h]
0x10025965  mov     [edi+10h], eax
0x10025968  mov     eax, [ebx+10h]
0x1002596b  cmp     eax, 6; switch 7 cases
0x1002596e  ja      def_10025974; jumptable 10025974 default case
0x10025974  jmp     ds:jpt_10025974[eax*4]; switch jump
0x1002597b  movups  xmm0, xmmword ptr [ebx]; jumptable 10025974 case 0
0x1002597e  movups  xmmword ptr [edi], xmm0
0x10025981  mov     edi, [ebx+14h]
0x10025984  lea     ecx, [edi+2]
0x10025987  mov     ax, [edi]
0x1002598a  add     edi, 2
0x1002598d  test    ax, ax
0x10025990  jnz     short loc_10025987
0x10025992  sub     edi, ecx
0x10025994  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x1002599a  sar     edi, 1
0x1002599c  mov     [ebp+pcchNewDestLength], edi
0x1002599f  inc     edi
0x100259a0  mov     eax, [ecx]
0x100259a2  mov     esi, [eax+0Ch]
0x100259a5  lea     eax, [edi+edi]
0x100259a8  push    eax
0x100259a9  push    ecx
0x100259aa  mov     ecx, esi
0x100259ac  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100259b2  call    esi
0x100259b4  mov     esi, [ebp+var_4]
0x100259b7  mov     [esi+14h], eax
0x100259ba  test    eax, eax
0x100259bc  jz      loc_10025AD0
0x100259c2  push    [ebp+pcchNewDestLength]; pcchNewDestLength
0x100259c5  mov     edx, edi
0x100259c7  mov     ecx, eax
0x100259c9  push    dword ptr [ebx+14h]; cchDest
0x100259cc  call    ?WCSNCPY@@YGPAGPAGIPBGH@Z; WCSNCPY(ushort *,uint,ushort const *,int)
0x100259d1  pop     edi
0x100259d2  pop     esi
0x100259d3  xor     eax, eax
0x100259d5  pop     ebx
0x100259d6  mov     esp, ebp
0x100259d8  pop     ebp
0x100259d9  retn
0x100259da  movups  xmm0, xmmword ptr [ebx]; jumptable 10025974 case 1
0x100259dd  movups  xmmword ptr [edi], xmm0
0x100259e0  mov     eax, [ebx+14h]; jumptable 10025974 case 5
0x100259e3  mov     [edi+14h], eax
0x100259e6  xor     eax, eax
0x100259e8  pop     edi
0x100259e9  pop     esi
0x100259ea  pop     ebx
0x100259eb  mov     esp, ebp
0x100259ed  pop     ebp
0x100259ee  retn
0x100259ef  mov     edi, [ebx+14h]; jumptable 10025974 case 2
0x100259f2  lea     ecx, [edi+2]
0x100259f5  mov     ax, [edi]
0x100259f8  add     edi, 2
0x100259fb  test    ax, ax
0x100259fe  jnz     short loc_100259F5
0x10025a00  sub     edi, ecx
0x10025a02  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x10025a08  sar     edi, 1
0x10025a0a  mov     [ebp+pcchNewDestLength], edi
0x10025a0d  inc     edi
0x10025a0e  mov     eax, [ecx]
0x10025a10  mov     esi, [eax+0Ch]
0x10025a13  lea     eax, [edi+edi]
0x10025a16  push    eax
0x10025a17  push    ecx
0x10025a18  mov     ecx, esi
0x10025a1a  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10025a20  call    esi
0x10025a22  mov     esi, [ebp+var_4]
0x10025a25  mov     [esi+14h], eax
0x10025a28  test    eax, eax
0x10025a2a  jz      loc_10025AD0
0x10025a30  push    [ebp+pcchNewDestLength]; pcchNewDestLength
0x10025a33  mov     edx, edi
0x10025a35  mov     ecx, eax
0x10025a37  push    dword ptr [ebx+14h]; cchDest
0x10025a3a  call    ?WCSNCPY@@YGPAGPAGIPBGH@Z; WCSNCPY(ushort *,uint,ushort const *,int)
0x10025a3f  pop     edi
0x10025a40  pop     esi
0x10025a41  xor     eax, eax
0x10025a43  pop     ebx
0x10025a44  mov     esp, ebp
0x10025a46  pop     ebp
0x10025a47  retn
0x10025a48  mov     ecx, ?Sys@@3VSystem@@A; jumptable 10025974 case 3
0x10025a4e  push    10h
0x10025a50  push    ecx
0x10025a51  mov     eax, [ecx]
0x10025a53  mov     esi, [eax+0Ch]
0x10025a56  mov     ecx, esi
0x10025a58  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10025a5e  call    esi
0x10025a60  mov     [edi], eax
0x10025a62  test    eax, eax
0x10025a64  jz      short loc_10025AD0
0x10025a66  mov     ecx, [ebx]
0x10025a68  movups  xmm0, xmmword ptr [ecx]
0x10025a6b  movups  xmmword ptr [eax], xmm0
0x10025a6e  mov     edi, [ebx+14h]
0x10025a71  lea     ecx, [edi+2]
0x10025a74  mov     ax, [edi]
0x10025a77  add     edi, 2
0x10025a7a  test    ax, ax
0x10025a7d  jnz     short loc_10025A74
0x10025a7f  sub     edi, ecx
0x10025a81  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x10025a87  sar     edi, 1
0x10025a89  mov     [ebp+pcchNewDestLength], edi
0x10025a8c  inc     edi
0x10025a8d  mov     eax, [ecx]
0x10025a8f  mov     esi, [eax+0Ch]
0x10025a92  lea     eax, [edi+edi]
0x10025a95  push    eax
0x10025a96  push    ecx
0x10025a97  mov     ecx, esi
0x10025a99  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10025a9f  call    esi
0x10025aa1  mov     esi, [ebp+var_4]
0x10025aa4  mov     [esi+14h], eax
0x10025aa7  test    eax, eax
0x10025aa9  jz      short loc_10025AC3
0x10025aab  push    [ebp+pcchNewDestLength]; pcchNewDestLength
0x10025aae  mov     edx, edi
0x10025ab0  mov     ecx, eax
0x10025ab2  push    dword ptr [ebx+14h]; cchDest
0x10025ab5  call    ?WCSNCPY@@YGPAGPAGIPBGH@Z; WCSNCPY(ushort *,uint,ushort const *,int)
0x10025aba  pop     edi
0x10025abb  pop     esi
0x10025abc  xor     eax, eax
0x10025abe  pop     ebx
0x10025abf  mov     esp, ebp
0x10025ac1  pop     ebp
0x10025ac2  retn
0x10025ac3  push    dword ptr [esi]
0x10025ac5  call    ?Free@System@@QAEXPAX@Z; System::Free(void *)
0x10025aca  mov     dword ptr [esi], 0
0x10025ad0  pop     edi
0x10025ad1  pop     esi
0x10025ad2  mov     eax, 8007000Eh
0x10025ad7  pop     ebx
0x10025ad8  mov     esp, ebp
0x10025ada  pop     ebp
0x10025adb  retn
0x10025adc  mov     ecx, ?Sys@@3VSystem@@A; jumptable 10025974 case 4
0x10025ae2  push    10h
0x10025ae4  push    ecx
0x10025ae5  mov     eax, [ecx]
0x10025ae7  mov     esi, [eax+0Ch]
0x10025aea  mov     ecx, esi
0x10025aec  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10025af2  call    esi
0x10025af4  mov     [edi], eax
0x10025af6  test    eax, eax
0x10025af8  jz      short loc_10025AD0
0x10025afa  mov     ecx, [ebx]
0x10025afc  movups  xmm0, xmmword ptr [ecx]
0x10025aff  movups  xmmword ptr [eax], xmm0
0x10025b02  mov     eax, [ebx+14h]
0x10025b05  mov     [edi+14h], eax
0x10025b08  xor     eax, eax
0x10025b0a  pop     edi
0x10025b0b  pop     esi
0x10025b0c  pop     ebx
0x10025b0d  mov     esp, ebp
0x10025b0f  pop     ebp
0x10025b10  retn
0x10025b11  movups  xmm0, xmmword ptr [ebx]; jumptable 10025974 case 6
0x10025b14  xor     eax, eax
0x10025b16  movups  xmmword ptr [edi], xmm0
0x10025b19  pop     edi
0x10025b1a  pop     esi
0x10025b1b  pop     ebx
0x10025b1c  mov     esp, ebp
0x10025b1e  pop     ebp
0x10025b1f  retn
0x10025b20  pop     edi; jumptable 10025974 default case
0x10025b21  pop     esi
0x10025b22  mov     eax, 1
0x10025b27  pop     ebx
0x10025b28  mov     esp, ebp
0x10025b2a  pop     ebp
0x10025b2b  retn
```
