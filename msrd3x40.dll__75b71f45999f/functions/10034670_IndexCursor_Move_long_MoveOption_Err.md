# IndexCursor::Move(long,MoveOption,Err &)

- ea: `0x10034670`
- end: `0x10034aa7`
- name: `?Move@IndexCursor@@UAEXJW4MoveOption@@AAVErr@@@Z`
- size: `1079`
- prototype: `void __thiscall __high(int, enum MoveOption, struct Err *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x1000eb60`
- `0x10034670`
- `0x1005e7e8`

## pseudocode

```c
void __thiscall IndexCursor::Move(_DWORD *this, int a2, int a3, int a4)
{
  int v4; // ebx
  _DWORD *v5; // edi
  int v6; // esi
  int v7; // ecx
  int v8; // eax
  int v9; // edx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // esi
  int v14; // eax
  int v15; // esi
  int v16; // eax
  int v17; // ecx
  int v18; // eax
  int v19; // esi
  int v20; // eax
  int v21; // eax
  int v22; // ecx
  int *v23; // edi
  _DWORD *v24; // eax
  int v25; // ecx
  int v26; // eax
  int v27; // edx
  int v28; // esi
  int v29; // eax
  int v30; // esi
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // esi
  int v35; // eax
  bool v36; // zf
  _DWORD *v38; // [esp+10h] [ebp-8h]
  int v39; // [esp+14h] [ebp-4h]

  v4 = a2;
  v5 = this;
  v6 = 0;
  if ( a2 > 0 )
  {
    v7 = a3;
    v8 = *(_DWORD *)a4;
    while ( 2 )
    {
      v9 = v4--;
      v39 = v9;
      switch ( v7 )
      {
        case 0:
          v10 = 0;
          if ( v5[1] != -1 )
            v10 = v5[1];
          v5[2] = v10;
          v11 = *(v5 - 91);
          v5[3] = 0;
          v12 = (*(int (__thiscall **)(_DWORD *))(v11 + 60))(v5 - 91);
          v5 = this;
          v13 = v12;
          v14 = this[2];
          if ( v14 < 0 || v14 >= *(_DWORD *)(v13 + 24) || *(_DWORD *)(v13 + 4 * v14 + 1524) == -1 )
          {
            v6 = 0;
            this[2] = -1;
          }
          else
          {
            _mm_lfence();
            v6 = *(_DWORD *)(v13 + 4 * *(_DWORD *)(v13 + 4 * v14 + 1524) + 1396);
            if ( !v6 )
            {
              v7 = 2;
              this[2] = -1;
              a3 = 2;
              goto LABEL_25;
            }
          }
          v7 = 2;
          a3 = 2;
          goto LABEL_25;
        case 1:
          v22 = v5[1];
          v23 = v5 + 2;
          v24 = this - 91;
          v38 = this - 91;
          if ( v22 != -1 )
            goto LABEL_52;
          *v23 = 0;
          while ( 2 )
          {
            v25 = (*(int (__thiscall **)(_DWORD *))(*v24 + 60))(v38);
            v26 = *v23;
            if ( *v23 < 0 || v26 >= *(_DWORD *)(v25 + 24) || *(_DWORD *)(v25 + 4 * v26 + 1524) == -1 )
            {
              v27 = *v23;
            }
            else
            {
              _mm_lfence();
              v27 = *v23;
              if ( *(_DWORD *)(v25 + 4 * *(_DWORD *)(v25 + 4 * v26 + 1524) + 1396) )
              {
                *v23 = v27 + 1;
                v24 = this - 91;
                continue;
              }
            }
            break;
          }
          v22 = -1;
          if ( v27 )
            v22 = v27 - 1;
LABEL_52:
          *v23 = v22;
          v28 = (*(int (__thiscall **)(_DWORD *))(*v38 + 60))(v38);
          v29 = *v23;
          if ( *v23 < 0 || v29 >= *(_DWORD *)(v28 + 24) || *(_DWORD *)(v28 + 4 * v29 + 1524) == -1 )
          {
            v6 = 0;
          }
          else
          {
            _mm_lfence();
            v6 = *(_DWORD *)(v28 + 4 * *(_DWORD *)(v28 + 4 * v29 + 1524) + 1396);
            if ( v6 )
            {
              v7 = 3;
              v5 = this;
              a3 = 3;
              this[3] = *(_DWORD *)(*(_DWORD *)(v6 + 8) + 32) - 1;
              goto LABEL_25;
            }
          }
          v7 = 3;
          *v23 = -1;
          v5 = this;
          a3 = 3;
          goto LABEL_25;
        case 2:
          v15 = (*(int (__thiscall **)(_DWORD *))(*(v5 - 91) + 60))(v5 - 91);
          v16 = v5[2];
          if ( v16 < 0 || v16 >= *(_DWORD *)(v15 + 24) || *(_DWORD *)(v15 + 4 * v16 + 1524) == -1 )
            goto LABEL_41;
          _mm_lfence();
          v6 = *(_DWORD *)(v15 + 4 * *(_DWORD *)(v15 + 4 * v16 + 1524) + 1396);
          if ( !v6 )
            goto LABEL_23;
          v17 = v5[3] + 1;
          v5[3] = v17;
          if ( v17 < *(_DWORD *)(*(_DWORD *)(v6 + 8) + 32) )
            goto LABEL_24;
          if ( v5[1] != -1 )
            goto LABEL_23;
          v18 = *(v5 - 91);
          ++v5[2];
          v5[3] = 0;
          v19 = (*(int (__thiscall **)(_DWORD *))(v18 + 60))(v5 - 91);
          v20 = v5[2];
          if ( v20 < 0 || v20 >= *(_DWORD *)(v19 + 24) || *(_DWORD *)(v19 + 4 * v20 + 1524) == -1 )
            goto LABEL_41;
          _mm_lfence();
          v6 = *(_DWORD *)(v19 + 4 * *(_DWORD *)(v19 + 4 * v20 + 1524) + 1396);
          if ( !v6 )
            goto LABEL_23;
          goto LABEL_24;
        case 3:
          v30 = (*(int (__thiscall **)(_DWORD *))(*(v5 - 91) + 60))(v5 - 91);
          v31 = v5[2];
          if ( v31 < 0 || v31 >= *(_DWORD *)(v30 + 24) || *(_DWORD *)(v30 + 4 * v31 + 1524) == -1 )
            goto LABEL_41;
          _mm_lfence();
          v6 = *(_DWORD *)(v30 + 4 * *(_DWORD *)(v30 + 4 * v31 + 1524) + 1396);
          if ( !v6 )
            goto LABEL_23;
          v32 = v5[3];
          if ( v32 )
            goto LABEL_70;
          if ( v5[1] != -1 )
            goto LABEL_23;
          v33 = *(v5 - 91);
          --v5[2];
          v34 = (*(int (__thiscall **)(_DWORD *))(v33 + 60))(v5 - 91);
          v35 = v5[2];
          if ( v35 < 0 || v35 >= *(_DWORD *)(v34 + 24) || *(_DWORD *)(v34 + 4 * v35 + 1524) == -1 )
          {
LABEL_41:
            v6 = 0;
LABEL_23:
            v5[2] = -1;
            goto LABEL_24;
          }
          _mm_lfence();
          v6 = *(_DWORD *)(v34 + 4 * *(_DWORD *)(v34 + 4 * v35 + 1524) + 1396);
          if ( !v6 )
            goto LABEL_23;
          v32 = *(_DWORD *)(*(_DWORD *)(v6 + 8) + 32);
LABEL_70:
          v5[3] = v32 - 1;
LABEL_24:
          v7 = a3;
LABEL_25:
          v9 = v39;
LABEL_26:
          v21 = a4;
LABEL_27:
          v8 = *(_DWORD *)v21;
          if ( (v8 & 8) == 0 && v5[2] != -1 && *(_BYTE *)(v6 + 41) == 1 )
            v4 = v9;
          if ( v4 <= 0 )
            break;
          continue;
        case 4:
          if ( v8 >= 8 )
            goto LABEL_26;
          v36 = (v8 & 0xFFFFFFFE) == 0;
          v21 = a4;
          if ( !v36 )
          {
            if ( *(_DWORD *)(a4 + 12) )
            {
              operator delete[](*(void **)(a4 + 12));
              v21 = a4;
            }
            if ( *(_DWORD *)(v21 + 16) )
            {
              operator delete[](*(void **)(v21 + 16));
              v21 = a4;
            }
          }
          v7 = a3;
          v9 = v39;
          *(_DWORD *)v21 = 8;
          *(_DWORD *)(v21 + 4) = -1906;
          *(_DWORD *)(v21 + 8) = 0;
          *(_DWORD *)(v21 + 12) = 0;
          *(_DWORD *)(v21 + 16) = 0;
          goto LABEL_27;
        default:
          goto LABEL_26;
      }
      break;
    }
  }
  if ( v5[2] == -1 && *(int *)a4 < 8 )
  {
    if ( (*(_DWORD *)a4 & 0xFFFFFFFE) != 0 )
    {
      if ( *(_DWORD *)(a4 + 12) )
        operator delete[](*(void **)(a4 + 12));
      if ( *(_DWORD *)(a4 + 16) )
        operator delete[](*(void **)(a4 + 16));
    }
    *(_DWORD *)a4 = 8;
    *(_DWORD *)(a4 + 4) = -1603;
    *(_DWORD *)(a4 + 8) = 0;
    *(_DWORD *)(a4 + 12) = 0;
    *(_DWORD *)(a4 + 16) = 0;
  }
}

```

## disassembly

```asm
0x10034670  mov     edi, edi
0x10034672  push    ebp
0x10034673  mov     ebp, esp
0x10034675  sub     esp, 0Ch
0x10034678  push    ebx
0x10034679  mov     ebx, [ebp+arg_0]
0x1003467c  push    esi; unsigned int
0x1003467d  push    edi; void *
0x1003467e  mov     edi, ecx
0x10034680  xor     esi, esi
0x10034682  mov     [ebp+var_C], edi
0x10034685  test    ebx, ebx
0x10034687  jle     loc_10034820
0x1003468d  mov     eax, [ebp+arg_8]
0x10034690  mov     ecx, [ebp+arg_4]
0x10034693  mov     eax, [eax]
0x10034695  mov     edx, ebx
0x10034697  dec     ebx
0x10034698  mov     [ebp+var_4], edx
0x1003469b  cmp     ecx, 4; switch 5 cases
0x1003469e  ja      def_100346A4; jumptable 100346A4 default case
0x100346a4  jmp     ds:jpt_100346A4[ecx*4]; switch jump
0x100346ab  xor     eax, eax; jumptable 100346A4 case 0
0x100346ad  cmp     dword ptr [edi+4], 0FFFFFFFFh
0x100346b1  cmovnz  eax, [edi+4]
0x100346b5  mov     [edi+8], eax
0x100346b8  mov     eax, [edi-16Ch]
0x100346be  mov     dword ptr [edi+0Ch], 0
0x100346c5  mov     esi, [eax+3Ch]
0x100346c8  mov     ecx, esi
0x100346ca  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100346d0  lea     ecx, [edi-16Ch]
0x100346d6  call    esi
0x100346d8  mov     edi, [ebp+var_C]
0x100346db  mov     esi, eax
0x100346dd  mov     eax, [edi+8]
0x100346e0  test    eax, eax
0x100346e2  js      short loc_1003471C
0x100346e4  cmp     eax, [esi+18h]
0x100346e7  jge     short loc_1003471C
0x100346e9  cmp     dword ptr [esi+eax*4+5F4h], 0FFFFFFFFh
0x100346f1  jz      short loc_1003471C
0x100346f3  lfence
0x100346f6  mov     eax, [esi+eax*4+5F4h]
0x100346fd  mov     esi, [esi+eax*4+574h]
0x10034704  test    esi, esi
0x10034706  jnz     short loc_10034725
0x10034708  mov     ecx, 2
0x1003470d  mov     dword ptr [edi+8], 0FFFFFFFFh
0x10034714  mov     [ebp+arg_4], ecx
0x10034717  jmp     loc_100347FF
0x1003471c  xor     esi, esi
0x1003471e  mov     dword ptr [edi+8], 0FFFFFFFFh
0x10034725  mov     ecx, 2
0x1003472a  mov     [ebp+arg_4], ecx
0x1003472d  jmp     loc_100347FF
0x10034732  mov     eax, [edi-16Ch]; jumptable 100346A4 case 2
0x10034738  mov     esi, [eax+3Ch]
0x1003473b  mov     ecx, esi
0x1003473d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10034743  lea     ecx, [edi-16Ch]
0x10034749  call    esi
0x1003474b  mov     esi, eax
0x1003474d  mov     eax, [edi+8]
0x10034750  test    eax, eax
0x10034752  js      loc_10034882
0x10034758  cmp     eax, [esi+18h]
0x1003475b  jge     loc_10034882
0x10034761  cmp     dword ptr [esi+eax*4+5F4h], 0FFFFFFFFh
0x10034769  jz      loc_10034882
0x1003476f  lfence
0x10034772  mov     eax, [esi+eax*4+5F4h]
0x10034779  mov     esi, [esi+eax*4+574h]
0x10034780  test    esi, esi
0x10034782  jz      short loc_100347F5
0x10034784  mov     ecx, [edi+0Ch]
0x10034787  inc     ecx
0x10034788  mov     [edi+0Ch], ecx
0x1003478b  mov     eax, [esi+8]
0x1003478e  cmp     ecx, [eax+20h]
0x10034791  jl      short loc_100347FC
0x10034793  cmp     dword ptr [edi+4], 0FFFFFFFFh
0x10034797  jnz     short loc_100347F5
0x10034799  mov     eax, [edi-16Ch]
0x1003479f  inc     dword ptr [edi+8]
0x100347a2  mov     dword ptr [edi+0Ch], 0
0x100347a9  mov     esi, [eax+3Ch]
0x100347ac  mov     ecx, esi
0x100347ae  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100347b4  lea     ecx, [edi-16Ch]
0x100347ba  call    esi
0x100347bc  mov     esi, eax
0x100347be  mov     eax, [edi+8]
0x100347c1  test    eax, eax
0x100347c3  js      loc_10034882
0x100347c9  cmp     eax, [esi+18h]
0x100347cc  jge     loc_10034882
0x100347d2  cmp     dword ptr [esi+eax*4+5F4h], 0FFFFFFFFh
0x100347da  jz      loc_10034882
0x100347e0  lfence
0x100347e3  mov     eax, [esi+eax*4+5F4h]
0x100347ea  mov     esi, [esi+eax*4+574h]
0x100347f1  test    esi, esi
0x100347f3  jnz     short loc_100347FC
0x100347f5  mov     dword ptr [edi+8], 0FFFFFFFFh
0x100347fc  mov     ecx, [ebp+arg_4]
0x100347ff  mov     edx, [ebp+var_4]
0x10034802  mov     eax, [ebp+arg_8]; jumptable 100346A4 default case
0x10034805  mov     eax, [eax]
0x10034807  test    al, 8
0x10034809  jnz     short loc_10034818
0x1003480b  cmp     dword ptr [edi+8], 0FFFFFFFFh
0x1003480f  jz      short loc_10034818
0x10034811  cmp     byte ptr [esi+29h], 1
0x10034815  cmovz   ebx, edx
0x10034818  test    ebx, ebx
0x1003481a  jg      loc_10034695
0x10034820  cmp     dword ptr [edi+8], 0FFFFFFFFh
0x10034824  jnz     short loc_10034879
0x10034826  mov     ebx, [ebp+arg_8]
0x10034829  mov     eax, [ebx]
0x1003482b  cmp     eax, 8
0x1003482e  jge     short loc_10034879
0x10034830  test    eax, 0FFFFFFFEh
0x10034835  jz      short loc_10034857
0x10034837  mov     eax, [ebx+0Ch]
0x1003483a  test    eax, eax
0x1003483c  jz      short loc_10034847
0x1003483e  push    eax; Block
0x1003483f  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10034844  add     esp, 4
0x10034847  mov     eax, [ebx+10h]
0x1003484a  test    eax, eax
0x1003484c  jz      short loc_10034857
0x1003484e  push    eax; Block
0x1003484f  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10034854  add     esp, 4
0x10034857  mov     dword ptr [ebx], 8
0x1003485d  mov     dword ptr [ebx+4], 0FFFFF9BDh
0x10034864  mov     dword ptr [ebx+8], 0
0x1003486b  mov     dword ptr [ebx+0Ch], 0
0x10034872  mov     dword ptr [ebx+10h], 0
0x10034879  pop     edi
0x1003487a  pop     esi
0x1003487b  pop     ebx
0x1003487c  mov     esp, ebp
0x1003487e  pop     ebp
0x1003487f  retn    0Ch
0x10034882  xor     esi, esi
0x10034884  jmp     loc_100347F5
0x10034889  mov     ecx, [edi+4]; jumptable 100346A4 case 1
0x1003488c  add     edi, 8
0x1003488f  mov     eax, [ebp+var_C]
0x10034892  add     eax, 0FFFFFE94h
0x10034897  mov     [ebp+var_8], eax
0x1003489a  cmp     ecx, 0FFFFFFFFh
0x1003489d  jnz     short loc_100348FB
0x1003489f  mov     dword ptr [edi], 0
0x100348a5  mov     eax, [eax]
0x100348a7  mov     esi, [eax+3Ch]
0x100348aa  mov     ecx, esi
0x100348ac  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100348b2  mov     ecx, [ebp+var_8]
0x100348b5  call    esi
0x100348b7  mov     ecx, eax
0x100348b9  mov     eax, [edi]
0x100348bb  test    eax, eax
0x100348bd  js      short loc_100348EE
0x100348bf  cmp     eax, [ecx+18h]
0x100348c2  jge     short loc_100348EE
0x100348c4  cmp     dword ptr [ecx+eax*4+5F4h], 0FFFFFFFFh
0x100348cc  jz      short loc_100348EE
0x100348ce  lfence
0x100348d1  mov     eax, [ecx+eax*4+5F4h]
0x100348d8  mov     edx, [edi]
0x100348da  cmp     dword ptr [ecx+eax*4+574h], 0
0x100348e2  jz      short loc_100348F0
0x100348e4  lea     eax, [edx+1]
0x100348e7  mov     [edi], eax
0x100348e9  mov     eax, [ebp+var_8]
0x100348ec  jmp     short loc_100348A5
0x100348ee  mov     edx, eax
0x100348f0  or      ecx, 0FFFFFFFFh
0x100348f3  lea     eax, [edx-1]
0x100348f6  test    edx, edx
0x100348f8  cmovnz  ecx, eax
0x100348fb  mov     eax, edi
0x100348fd  mov     [eax], ecx
0x100348ff  mov     eax, [ebp+var_8]
0x10034902  mov     eax, [eax]
0x10034904  mov     esi, [eax+3Ch]
0x10034907  mov     ecx, esi
0x10034909  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003490f  mov     ecx, [ebp+var_8]
0x10034912  call    esi
0x10034914  mov     esi, eax
0x10034916  mov     eax, [edi]
0x10034918  test    eax, eax
0x1003491a  js      short loc_1003495A
0x1003491c  cmp     eax, [esi+18h]
0x1003491f  jge     short loc_1003495A
0x10034921  cmp     dword ptr [esi+eax*4+5F4h], 0FFFFFFFFh
0x10034929  jz      short loc_1003495A
0x1003492b  lfence
0x1003492e  mov     eax, [esi+eax*4+5F4h]
0x10034935  mov     esi, [esi+eax*4+574h]
0x1003493c  test    esi, esi
0x1003493e  jz      short loc_1003495C
0x10034940  mov     eax, [esi+8]
0x10034943  mov     ecx, 3
0x10034948  mov     edi, [ebp+var_C]
0x1003494b  mov     [ebp+arg_4], ecx
0x1003494e  mov     eax, [eax+20h]
0x10034951  dec     eax
0x10034952  mov     [edi+0Ch], eax
0x10034955  jmp     loc_100347FF
0x1003495a  xor     esi, esi
0x1003495c  mov     ecx, 3
0x10034961  mov     dword ptr [edi], 0FFFFFFFFh
0x10034967  mov     edi, [ebp+var_C]
0x1003496a  mov     [ebp+arg_4], ecx
0x1003496d  jmp     loc_100347FF
0x10034972  mov     eax, [edi-16Ch]; jumptable 100346A4 case 3
0x10034978  mov     esi, [eax+3Ch]
0x1003497b  mov     ecx, esi
0x1003497d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10034983  lea     ecx, [edi-16Ch]
0x10034989  call    esi
0x1003498b  mov     esi, eax
0x1003498d  mov     eax, [edi+8]
0x10034990  test    eax, eax
0x10034992  js      loc_10034882
0x10034998  cmp     eax, [esi+18h]
0x1003499b  jge     loc_10034882
0x100349a1  cmp     dword ptr [esi+eax*4+5F4h], 0FFFFFFFFh
0x100349a9  jz      loc_10034882
0x100349af  lfence
0x100349b2  mov     eax, [esi+eax*4+5F4h]
0x100349b9  mov     esi, [esi+eax*4+574h]
0x100349c0  test    esi, esi
0x100349c2  jz      loc_100347F5
0x100349c8  mov     eax, [edi+0Ch]
0x100349cb  test    eax, eax
0x100349cd  jnz     short loc_10034A38
0x100349cf  cmp     dword ptr [edi+4], 0FFFFFFFFh
0x100349d3  jnz     loc_100347F5
0x100349d9  mov     eax, [edi-16Ch]
0x100349df  dec     dword ptr [edi+8]
0x100349e2  mov     esi, [eax+3Ch]
0x100349e5  mov     ecx, esi
0x100349e7  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100349ed  lea     ecx, [edi-16Ch]
0x100349f3  call    esi
0x100349f5  mov     esi, eax
0x100349f7  mov     eax, [edi+8]
0x100349fa  test    eax, eax
0x100349fc  js      loc_10034882
0x10034a02  cmp     eax, [esi+18h]
0x10034a05  jge     loc_10034882
0x10034a0b  cmp     dword ptr [esi+eax*4+5F4h], 0FFFFFFFFh
0x10034a13  jz      loc_10034882
0x10034a19  lfence
0x10034a1c  mov     eax, [esi+eax*4+5F4h]
0x10034a23  mov     esi, [esi+eax*4+574h]
0x10034a2a  test    esi, esi
0x10034a2c  jz      loc_100347F5
0x10034a32  mov     eax, [esi+8]
0x10034a35  mov     eax, [eax+20h]
0x10034a38  dec     eax
0x10034a39  mov     [edi+0Ch], eax
0x10034a3c  jmp     loc_100347FC
0x10034a41  cmp     eax, 8; jumptable 100346A4 case 4
0x10034a44  jge     def_100346A4; jumptable 100346A4 default case
0x10034a4a  test    eax, 0FFFFFFFEh
0x10034a4f  mov     eax, [ebp+arg_8]
0x10034a52  jz      short loc_10034A7A
0x10034a54  mov     ecx, [eax+0Ch]
0x10034a57  test    ecx, ecx
0x10034a59  jz      short loc_10034A67
0x10034a5b  push    ecx; Block
0x10034a5c  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10034a61  mov     eax, [ebp+arg_8]
0x10034a64  add     esp, 4
0x10034a67  mov     ecx, [eax+10h]
0x10034a6a  test    ecx, ecx
0x10034a6c  jz      short loc_10034A7A
0x10034a6e  push    ecx; Block
0x10034a6f  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10034a74  mov     eax, [ebp+arg_8]
0x10034a77  add     esp, 4
0x10034a7a  mov     ecx, [ebp+arg_4]
0x10034a7d  mov     edx, [ebp+var_4]
0x10034a80  mov     dword ptr [eax], 8
0x10034a86  mov     dword ptr [eax+4], 0FFFFF88Eh
0x10034a8d  mov     dword ptr [eax+8], 0
0x10034a94  mov     dword ptr [eax+0Ch], 0
0x10034a9b  mov     dword ptr [eax+10h], 0
0x10034aa2  jmp     loc_10034805
```
