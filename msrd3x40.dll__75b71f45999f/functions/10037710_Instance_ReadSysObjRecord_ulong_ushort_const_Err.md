# Instance::ReadSysObjRecord(ulong,ushort const *,Err &)

- ea: `0x10037710`
- end: `0x10037afb`
- name: `?ReadSysObjRecord@Instance@@QAEXKPBGAAVErr@@@Z`
- size: `1003`
- prototype: `void __thiscall(Instance *this, unsigned int, unsigned __int16 *, void **)`
- caller_count: `9`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10026200`
- `0x1002b6b0`
- `0x1002b7b0`
- `0x10036160`
- `0x100364e0`
- `0x10036620`
- `0x10036a70`
- `0x10036dc0`
- `0x10037b10`

## callees

- `0x1000eb60`
- `0x1000f750`
- `0x10025db0`
- `0x10025f50`
- `0x10037710`
- `0x1004dbb0`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
void __thiscall Instance::ReadSysObjRecord(Instance *this, unsigned int a2, unsigned __int16 *a3, void **a4)
{
  Instance *v4; // esi
  unsigned __int16 *v5; // edx
  void **v6; // ebx
  Err *v7; // ecx
  int v9; // edi
  unsigned int v10; // edx
  int v11; // ecx
  int v12; // ecx
  int v13; // edi
  int v14; // eax
  unsigned __int16 *v15; // [esp-4h] [ebp-25Ch]
  _DWORD v16[3]; // [esp+24h] [ebp-234h] BYREF
  __int16 v17; // [esp+30h] [ebp-228h]
  int v18; // [esp+34h] [ebp-224h]
  int v19; // [esp+38h] [ebp-220h]
  unsigned int v20; // [esp+3Ch] [ebp-21Ch]
  unsigned __int16 *v21; // [esp+40h] [ebp-218h]
  Instance *v22; // [esp+44h] [ebp-214h]
  unsigned int v23[132]; // [esp+48h] [ebp-210h] BYREF

  v4 = this;
  v22 = this;
  v5 = a3;
  v6 = a4;
  v21 = a3;
  v7 = (Err *)(a3 + 1);
  while ( *v5++ )
    ;
  v9 = *((_DWORD *)v4 + 5);
  v20 = 2 * (((char *)v5 - (char *)v7) >> 1);
  if ( v9 )
  {
    if ( (unsigned int)(2 * (((char *)v5 - (char *)v7) >> 1)) <= 0xFF )
    {
      if ( !*((_DWORD *)v4 + 6)
        || (v4 = v22,
            *((_DWORD *)v22 + 6) != (*(int (__thiscall **)(_DWORD))(**(_DWORD **)(v9 + 36) + 52))(*(_DWORD *)(v9 + 36))) )
      {
        (*(void (__thiscall **)(_DWORD, const wchar_t *, void **))(**((_DWORD **)v4 + 5) + 8))(
          *((_DWORD *)v4 + 5),
          L"ParentIdName",
          v6);
        v4 = v22;
        if ( (*(_BYTE *)v6 & 8) == 0 )
          *((_DWORD *)v22 + 6) = (*(int (__thiscall **)(_DWORD))(**(_DWORD **)(*((_DWORD *)v22 + 5) + 36) + 52))(*(_DWORD *)(*((_DWORD *)v22 + 5) + 36));
      }
    }
    else
    {
      if ( ((unsigned int)*a4 & 0xFFFFFFFE) != 0 )
      {
        if ( a4[3] )
          operator delete[](a4[3]);
        if ( v6[4] )
          operator delete[](v6[4]);
      }
      v15 = v21;
      *v6 = (void *)8;
      v6[1] = (void *)-1305;
      v6[2] = (void *)-8300;
      Err::CopyString(v7, (unsigned __int16 **)v6 + 3, v15);
      v6[4] = 0;
      v23[131] = -1;
    }
  }
  else if ( (int)*a4 < 8 )
  {
    if ( ((unsigned int)*a4 & 0xFFFFFFFE) != 0 )
    {
      if ( a4[3] )
        operator delete[](a4[3]);
      if ( v6[4] )
        operator delete[](v6[4]);
    }
    *v6 = (void *)8;
    v6[1] = (void *)-1305;
    v6[2] = 0;
    v6[3] = 0;
    v6[4] = 0;
  }
  v10 = (unsigned int)*v6;
  if ( ((unsigned __int8)*v6 & 8) != 0 )
  {
    if ( (v10 & 1) == 0 && v6[1] == (void *)-1404 )
    {
      v12 = *((_DWORD *)v4 + 4);
      v13 = *(_DWORD *)(v12 + 224);
      if ( !v13 )
        v13 = *(unsigned __int16 *)(v12 + 86);
      v16[0] = v21;
      v16[1] = v20;
      v16[2] = *(_DWORD *)(v12 + 92);
      v17 = *(_WORD *)(v12 + 88);
      v18 = v13;
      v19 = 0;
      if ( (v10 & 0xFFFFFFFE) != 0 )
      {
        if ( v6[3] )
          operator delete[](v6[3]);
        if ( v6[4] )
          operator delete[](v6[4]);
      }
      *v6 = (void *)1;
      (*(void (__thiscall **)(_DWORD, int, _DWORD, void **))(**(_DWORD **)(*((_DWORD *)v4 + 5) + 36) + 8))(
        *(_DWORD *)(*((_DWORD *)v4 + 5) + 36),
        1,
        0,
        v6);
      while ( (*(_BYTE *)v6 & 8) == 0 )
      {
        (*(void (__thiscall **)(_DWORD, _DWORD, unsigned int *, int, _DWORD, void **))(**((_DWORD **)v22 + 5) + 108))(
          *((_DWORD *)v22 + 5),
          *((_DWORD *)v22 + 7),
          v23,
          512,
          0,
          v6);
        if ( (*(_BYTE *)v6 & 8) != 0 )
          break;
        if ( v23[0] == a2 )
        {
          v14 = (*(int (__thiscall **)(_DWORD, _DWORD, unsigned int *, int, _DWORD, void **))(**((_DWORD **)v22 + 5)
                                                                                            + 108))(
                  *((_DWORD *)v22 + 5),
                  *((_DWORD *)v22 + 9),
                  v23,
                  512,
                  0,
                  v6);
          if ( (*(_BYTE *)v6 & 8) == 0 && !LString::Compare(v16, v23, v14, 0) )
            break;
        }
        (*(void (__thiscall **)(_DWORD, int, int, void **))(**(_DWORD **)(*((_DWORD *)v22 + 5) + 36) + 8))(
          *(_DWORD *)(*((_DWORD *)v22 + 5) + 36),
          1,
          2,
          v6);
      }
      if ( (*(_BYTE *)v6 & 1) == 0 && v6[1] == (void *)-1603 )
        goto LABEL_44;
    }
  }
  else
  {
    (*(void (__thiscall **)(_DWORD, unsigned int *, int, _DWORD, void **))(**(_DWORD **)(*((_DWORD *)v4 + 5) + 36) + 24))(
      *(_DWORD *)(*((_DWORD *)v4 + 5) + 36),
      &a2,
      4,
      0,
      v6);
    if ( (*(_BYTE *)v6 & 8) == 0 )
    {
      (*(void (__thiscall **)(_DWORD, unsigned __int16 *, unsigned int, int, void **))(**(_DWORD **)(*((_DWORD *)v22 + 5) + 36)
                                                                                     + 24))(
        *(_DWORD *)(*((_DWORD *)v22 + 5) + 36),
        v21,
        v20,
        1,
        v6);
      if ( (*(_BYTE *)v6 & 8) == 0 )
      {
        (*(void (__thiscall **)(_DWORD, _DWORD, void **))(**(_DWORD **)(*((_DWORD *)v22 + 5) + 36) + 28))(
          *(_DWORD *)(*((_DWORD *)v22 + 5) + 36),
          0,
          v6);
        if ( (*(_BYTE *)v6 & 8) != 0 )
LABEL_44:
          Err::SetError(v6, -1305, -8300, v21, 0, v11);
      }
    }
  }
}

```

## disassembly

```asm
0x10037710  mov     edi, edi
0x10037712  push    ebp
0x10037713  mov     ebp, esp
0x10037715  push    0FFFFFFFFh
0x10037717  push    offset ?ReadSysObjRecord@Instance@@QAEXKPBGAAVErr@@@Z_SEH
0x1003771c  mov     eax, large fs:0
0x10037722  push    eax
0x10037723  sub     esp, 23Ch
0x10037729  mov     eax, ___security_cookie
0x1003772e  xor     eax, ebp
0x10037730  mov     [ebp+var_10], eax
0x10037733  push    ebx
0x10037734  push    esi
0x10037735  push    edi; unsigned int
0x10037736  push    eax; void *
0x10037737  lea     eax, [ebp+var_C]
0x1003773a  mov     large fs:0, eax
0x10037740  mov     esi, ecx
0x10037742  mov     [ebp+var_214], esi
0x10037748  mov     eax, [ebp+arg_4]
0x1003774b  mov     edx, eax
0x1003774d  mov     ebx, [ebp+arg_8]
0x10037750  mov     [ebp+var_218], eax
0x10037756  lea     ecx, [edx+2]
0x10037759  nop     dword ptr [eax+00000000h]
0x10037760  mov     ax, [edx]
0x10037763  add     edx, 2
0x10037766  test    ax, ax
0x10037769  jnz     short loc_10037760
0x1003776b  mov     edi, [esi+14h]
0x1003776e  sub     edx, ecx
0x10037770  sar     edx, 1
0x10037772  lea     eax, [edx+edx]
0x10037775  mov     [ebp+var_21C], eax
0x1003777b  test    edi, edi
0x1003777d  jnz     short loc_100377D8
0x1003777f  mov     eax, [ebx]
0x10037781  cmp     eax, 8
0x10037784  jge     loc_100378AC
0x1003778a  test    eax, 0FFFFFFFEh
0x1003778f  jz      short loc_100377B1
0x10037791  mov     eax, [ebx+0Ch]
0x10037794  test    eax, eax
0x10037796  jz      short loc_100377A1
0x10037798  push    eax; Block
0x10037799  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1003779e  add     esp, 4
0x100377a1  mov     eax, [ebx+10h]
0x100377a4  test    eax, eax
0x100377a6  jz      short loc_100377B1
0x100377a8  push    eax; Block
0x100377a9  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100377ae  add     esp, 4
0x100377b1  mov     dword ptr [ebx], 8
0x100377b7  mov     dword ptr [ebx+4], 0FFFFFAE7h
0x100377be  mov     dword ptr [ebx+8], 0
0x100377c5  mov     dword ptr [ebx+0Ch], 0
0x100377cc  mov     dword ptr [ebx+10h], 0
0x100377d3  jmp     loc_100378AC
0x100377d8  cmp     eax, 0FFh
0x100377dd  jbe     short loc_1003783A
0x100377df  test    dword ptr [ebx], 0FFFFFFFEh
0x100377e5  jz      short loc_10037807
0x100377e7  mov     eax, [ebx+0Ch]
0x100377ea  test    eax, eax
0x100377ec  jz      short loc_100377F7
0x100377ee  push    eax; Block
0x100377ef  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100377f4  add     esp, 4
0x100377f7  mov     eax, [ebx+10h]
0x100377fa  test    eax, eax
0x100377fc  jz      short loc_10037807
0x100377fe  push    eax; Block
0x100377ff  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10037804  add     esp, 4
0x10037807  push    [ebp+var_218]; unsigned __int16 *
0x1003780d  lea     eax, [ebx+0Ch]
0x10037810  mov     dword ptr [ebx], 8
0x10037816  push    eax; unsigned __int16 **
0x10037817  mov     dword ptr [ebx+4], 0FFFFFAE7h
0x1003781e  mov     dword ptr [ebx+8], 0FFFFDF94h
0x10037825  call    ?CopyString@Err@@AAEXAAPAGPBG@Z; Err::CopyString(ushort * &,ushort const *)
0x1003782a  mov     dword ptr [ebx+10h], 0
0x10037831  mov     [ebp+var_4], 0FFFFFFFFh
0x10037838  jmp     short loc_100378AC
0x1003783a  cmp     dword ptr [esi+18h], 0
0x1003783e  jz      short loc_1003785F
0x10037840  mov     edi, [edi+24h]
0x10037843  mov     eax, [edi]
0x10037845  mov     esi, [eax+34h]
0x10037848  mov     ecx, esi
0x1003784a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10037850  mov     ecx, edi
0x10037852  call    esi
0x10037854  mov     esi, [ebp+var_214]
0x1003785a  cmp     [esi+18h], eax
0x1003785d  jz      short loc_100378AC
0x1003785f  mov     edi, [esi+14h]
0x10037862  push    ebx; unsigned int
0x10037863  push    offset aParentidname; "ParentIdName"
0x10037868  mov     eax, [edi]
0x1003786a  mov     esi, [eax+8]
0x1003786d  mov     ecx, esi
0x1003786f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10037875  mov     ecx, edi
0x10037877  call    esi
0x10037879  test    byte ptr [ebx], 8
0x1003787c  jnz     short loc_100378A6
0x1003787e  mov     eax, [ebp+var_214]
0x10037884  mov     eax, [eax+14h]
0x10037887  mov     edi, [eax+24h]
0x1003788a  mov     eax, [edi]
0x1003788c  mov     esi, [eax+34h]
0x1003788f  mov     ecx, esi
0x10037891  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10037897  mov     ecx, edi
0x10037899  call    esi
0x1003789b  mov     esi, [ebp+var_214]
0x100378a1  mov     [esi+18h], eax
0x100378a4  jmp     short loc_100378AC
0x100378a6  mov     esi, [ebp+var_214]
0x100378ac  mov     edx, [ebx]
0x100378ae  test    dl, 8
0x100378b1  jnz     loc_10037943
0x100378b7  mov     eax, [esi+14h]
0x100378ba  push    ebx
0x100378bb  push    0
0x100378bd  push    4; unsigned int
0x100378bf  mov     edi, [eax+24h]
0x100378c2  lea     eax, [ebp+arg_0]
0x100378c5  push    eax; void *
0x100378c6  mov     esi, [edi]
0x100378c8  mov     esi, [esi+18h]
0x100378cb  mov     ecx, esi
0x100378cd  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100378d3  mov     ecx, edi
0x100378d5  call    esi
0x100378d7  test    byte ptr [ebx], 8
0x100378da  jnz     loc_10037ADD
0x100378e0  mov     eax, [ebp+var_214]
0x100378e6  push    ebx
0x100378e7  push    1
0x100378e9  push    [ebp+var_21C]; unsigned int
0x100378ef  mov     eax, [eax+14h]
0x100378f2  push    [ebp+var_218]; void *
0x100378f8  mov     edi, [eax+24h]
0x100378fb  mov     eax, [edi]
0x100378fd  mov     esi, [eax+18h]
0x10037900  mov     ecx, esi
0x10037902  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10037908  mov     ecx, edi
0x1003790a  call    esi
0x1003790c  test    byte ptr [ebx], 8
0x1003790f  jnz     loc_10037ADD
0x10037915  mov     eax, [ebp+var_214]
0x1003791b  push    ebx; unsigned int
0x1003791c  push    0; void *
0x1003791e  mov     eax, [eax+14h]
0x10037921  mov     edi, [eax+24h]
0x10037924  mov     eax, [edi]
0x10037926  mov     esi, [eax+1Ch]
0x10037929  mov     ecx, esi
0x1003792b  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10037931  mov     ecx, edi
0x10037933  call    esi
0x10037935  test    byte ptr [ebx], 8
0x10037938  jz      loc_10037ADD
0x1003793e  jmp     loc_10037AC3
0x10037943  test    dl, 1
0x10037946  jnz     loc_10037ADD
0x1003794c  cmp     dword ptr [ebx+4], 0FFFFFA84h
0x10037953  jnz     loc_10037ADD
0x10037959  mov     ecx, [esi+10h]
0x1003795c  mov     edi, [ecx+0E0h]
0x10037962  test    edi, edi
0x10037964  jnz     short loc_1003796A
0x10037966  movzx   edi, word ptr [ecx+56h]
0x1003796a  mov     eax, [ebp+var_218]
0x10037970  mov     [ebp+var_234], eax
0x10037976  mov     eax, [ebp+var_21C]
0x1003797c  mov     [ebp+var_230], eax
0x10037982  mov     eax, [ecx+5Ch]
0x10037985  mov     [ebp+var_22C], eax
0x1003798b  mov     ax, [ecx+58h]
0x1003798f  mov     [ebp+var_228], ax
0x10037996  mov     [ebp+var_224], edi
0x1003799c  mov     [ebp+var_220], 0
0x100379a6  test    edx, 0FFFFFFFEh
0x100379ac  jz      short loc_100379CE
0x100379ae  mov     eax, [ebx+0Ch]
0x100379b1  test    eax, eax
0x100379b3  jz      short loc_100379BE
0x100379b5  push    eax; Block
0x100379b6  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100379bb  add     esp, 4
0x100379be  mov     eax, [ebx+10h]
0x100379c1  test    eax, eax
0x100379c3  jz      short loc_100379CE
0x100379c5  push    eax; Block
0x100379c6  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100379cb  add     esp, 4
0x100379ce  mov     dword ptr [ebx], 1
0x100379d4  mov     eax, [esi+14h]
0x100379d7  push    ebx
0x100379d8  push    0; unsigned int
0x100379da  push    1; void *
0x100379dc  mov     edi, [eax+24h]
0x100379df  mov     eax, [edi]
0x100379e1  mov     esi, [eax+8]
0x100379e4  mov     ecx, esi
0x100379e6  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100379ec  mov     ecx, edi
0x100379ee  call    esi
0x100379f0  test    byte ptr [ebx], 8
0x100379f3  jnz     loc_10037AB5
0x100379f9  nop     dword ptr [eax+00000000h]
0x10037a00  mov     eax, [ebp+var_214]
0x10037a06  lea     ecx, [ebp+var_210]
0x10037a0c  push    ebx
0x10037a0d  push    0
0x10037a0f  push    200h
0x10037a14  mov     edi, [eax+14h]
0x10037a17  push    ecx; unsigned int
0x10037a18  push    dword ptr [eax+1Ch]; void *
0x10037a1b  mov     esi, [edi]
0x10037a1d  mov     esi, [esi+6Ch]
0x10037a20  mov     ecx, esi
0x10037a22  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10037a28  mov     ecx, edi
0x10037a2a  call    esi
0x10037a2c  test    byte ptr [ebx], 8
0x10037a2f  jnz     loc_10037AB5
0x10037a35  mov     eax, [ebp+var_210]
0x10037a3b  cmp     eax, [ebp+arg_0]
0x10037a3e  jnz     short loc_10037A8A
0x10037a40  mov     ecx, [ebp+var_214]
0x10037a46  push    ebx
0x10037a47  push    0
0x10037a49  push    200h
0x10037a4e  mov     edi, [ecx+14h]
0x10037a51  mov     eax, [edi]
0x10037a53  mov     esi, [eax+6Ch]
0x10037a56  lea     eax, [ebp+var_210]
0x10037a5c  push    eax; unsigned int
0x10037a5d  push    dword ptr [ecx+24h]; void *
0x10037a60  mov     ecx, esi
0x10037a62  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10037a68  mov     ecx, edi
0x10037a6a  call    esi
0x10037a6c  test    byte ptr [ebx], 8
0x10037a6f  jnz     short loc_10037A8A
0x10037a71  push    0
0x10037a73  push    eax
0x10037a74  lea     eax, [ebp+var_210]
0x10037a7a  push    eax
0x10037a7b  lea     ecx, [ebp+var_234]
0x10037a81  call    ?Compare@LString@@QAE?AW4LCmp@@PAEIW4LSpec@@@Z; LString::Compare(uchar *,uint,LSpec)
0x10037a86  test    eax, eax
0x10037a88  jz      short loc_10037AB5
0x10037a8a  mov     eax, [ebp+var_214]
0x10037a90  push    ebx
0x10037a91  push    2; unsigned int
0x10037a93  push    1; void *
0x10037a95  mov     eax, [eax+14h]
0x10037a98  mov     edi, [eax+24h]
0x10037a9b  mov     eax, [edi]
0x10037a9d  mov     esi, [eax+8]
0x10037aa0  mov     ecx, esi
0x10037aa2  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10037aa8  mov     ecx, edi
0x10037aaa  call    esi
0x10037aac  test    byte ptr [ebx], 8
0x10037aaf  jz      loc_10037A00
0x10037ab5  test    byte ptr [ebx], 1
0x10037ab8  jnz     short loc_10037ADD
0x10037aba  cmp     dword ptr [ebx+4], 0FFFFF9BDh
0x10037ac1  jnz     short loc_10037ADD
0x10037ac3  push    ecx
0x10037ac4  push    0
0x10037ac6  push    [ebp+var_218]
0x10037acc  mov     ecx, ebx
0x10037ace  push    0FFFFDF94h
0x10037ad3  push    0FFFFFAE7h
0x10037ad8  call    ?SetError@Err@@QAEXJJPBG0W4ErrAssert@@@Z; Err::SetError(long,long,ushort const *,ushort const *,ErrAssert)
0x10037add  mov     ecx, [ebp+var_C]
0x10037ae0  mov     large fs:0, ecx
0x10037ae7  pop     ecx
0x10037ae8  pop     edi
0x10037ae9  pop     esi
0x10037aea  pop     ebx
0x10037aeb  mov     ecx, [ebp+var_10]
0x10037aee  xor     ecx, ebp; StackCookie
0x10037af0  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10037af5  mov     esp, ebp
0x10037af7  pop     ebp
0x10037af8  retn    0Ch
0x10060d30  lea     ecx, [ebp+var_248]; this
0x10060d36  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x10060d40  nop
0x10060d41  nop
  ... truncated ...
```
