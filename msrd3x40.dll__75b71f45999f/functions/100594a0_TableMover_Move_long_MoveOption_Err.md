# TableMover::Move(long,MoveOption,Err &)

- ea: `0x100594a0`
- end: `0x100596f8`
- name: `?Move@TableMover@@UAEXJW4MoveOption@@AAVErr@@@Z`
- size: `600`
- prototype: `void __thiscall __high(int, enum MoveOption, struct Err *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x1000eb60`
- `0x10025ee0`
- `0x100594a0`
- `0x1005a260`
- `0x1005a340`
- `0x1005a420`
- `0x1005a590`
- `0x1005e7e8`

## pseudocode

```c
void __thiscall TableMover::Move(int this, int a2, int a3, struct Err *a4)
{
  _DWORD *v4; // ecx
  int v5; // esi
  int v6; // eax
  _DWORD *v7; // edi
  _DWORD *v8; // eax
  _DWORD *v9; // eax

  (*(void (__thiscall **)(_DWORD, struct Err *))(**(_DWORD **)(this + 4) + 124))(*(_DWORD *)(this + 4), a4);
  v5 = a2;
  *(_DWORD *)(this + 52) = 0;
  *(_DWORD *)(this + 56) = 0;
  *(_DWORD *)(this + 60) = 0;
  if ( a2 > 0 )
  {
    v4 = (_DWORD *)(this + 12);
    while ( 2 )
    {
      v6 = *(_DWORD *)a4;
      --v5;
      v7 = v4;
      if ( (*(_DWORD *)a4 & 8) == 0 )
      {
        switch ( a3 )
        {
          case 0:
            do
            {
              TableMover::GetFirstRow((TableMover *)this, a4);
              if ( !*v7 )
                break;
              if ( v5 <= 0 )
                break;
              v7 = (_DWORD *)(this + 12);
              --v5;
            }
            while ( (*(_BYTE *)a4 & 8) == 0 );
            break;
          case 1:
            do
            {
              TableMover::GetLastRow((TableMover *)this, a4);
              if ( !*v7 )
                break;
              if ( v5 <= 0 )
                break;
              v7 = (_DWORD *)(this + 12);
              --v5;
            }
            while ( (*(_BYTE *)a4 & 8) == 0 );
            break;
          case 2:
            v8 = (_DWORD *)this;
            while ( 1 )
            {
              v4 = (_DWORD *)v8[2];
              if ( !v4 || v4 == (_DWORD *)4 )
              {
                TableMover::GetNextRow((TableMover *)v8, a4);
              }
              else
              {
                if ( v4 != (_DWORD *)1 )
                  goto LABEL_27;
                TableMover::GetFirstRow((TableMover *)v8, a4);
                if ( (*(_BYTE *)a4 & 8) == 0 )
                {
                  v8 = (_DWORD *)this;
                  if ( *(_DWORD *)(this + 12) )
                    *(_DWORD *)(this + 8) = 0;
LABEL_27:
                  if ( !*v7 || v5 <= 0 )
                    goto LABEL_58;
                  goto LABEL_37;
                }
              }
              if ( !*v7 || v5 <= 0 )
                goto LABEL_58;
              v8 = (_DWORD *)this;
LABEL_37:
              v4 = v8 + 3;
              --v5;
              v7 = v8 + 3;
              if ( (*(_BYTE *)a4 & 8) != 0 )
                goto LABEL_58;
            }
          case 3:
            v9 = (_DWORD *)this;
LABEL_40:
            v4 = (_DWORD *)v9[2];
            if ( !v4 || v4 == (_DWORD *)4 )
            {
              TableMover::GetPriorRow((TableMover *)v9, a4);
            }
            else
            {
              if ( v4 != (_DWORD *)2 )
                goto LABEL_43;
              TableMover::GetLastRow((TableMover *)v9, a4);
              if ( (*(_BYTE *)a4 & 8) == 0 )
              {
                v9 = (_DWORD *)this;
                if ( *(_DWORD *)(this + 12) )
                  *(_DWORD *)(this + 8) = 0;
LABEL_43:
                if ( *v7 && v5 > 0 )
                {
LABEL_53:
                  v4 = v9 + 3;
                  --v5;
                  v7 = v9 + 3;
                  if ( (*(_BYTE *)a4 & 8) != 0 )
                    break;
                  goto LABEL_40;
                }
                break;
              }
            }
            if ( *v7 && v5 > 0 )
            {
              v9 = (_DWORD *)this;
              goto LABEL_53;
            }
            break;
          case 6:
            do
            {
              *v7 = 0;
              if ( !*v7 )
                break;
              if ( v5 <= 0 )
                break;
              --v5;
              v7 = v4;
            }
            while ( (*(_BYTE *)a4 & 8) == 0 );
            break;
          default:
            if ( v6 < 8 )
            {
              if ( (v6 & 0xFFFFFFFE) != 0 )
              {
                if ( *((_DWORD *)a4 + 3) )
                  operator delete[](*((void **)a4 + 3));
                if ( *((_DWORD *)a4 + 4) )
                  operator delete[](*((void **)a4 + 4));
              }
              v4 = (_DWORD *)(this + 12);
              *(_DWORD *)a4 = 8;
              *((_DWORD *)a4 + 1) = -1906;
              *((_DWORD *)a4 + 2) = 0;
              *((_DWORD *)a4 + 3) = 0;
              *((_DWORD *)a4 + 4) = 0;
            }
            if ( *v7 && v5 > 0 )
              continue;
            goto LABEL_58;
        }
      }
      break;
    }
  }
LABEL_58:
  if ( (*(_BYTE *)a4 & 8) == 0 )
  {
    if ( *(_DWORD *)(this + 12) )
    {
      *(_DWORD *)(this + 8) = 0;
    }
    else
    {
      Err::SetError(a4, -1603, v4);
      *(_DWORD *)(this + 8) = (a3 != 3) + 1;
    }
  }
}

```

## disassembly

```asm
0x100594a0  mov     edi, edi
0x100594a2  push    ebp
0x100594a3  mov     ebp, esp
0x100594a5  sub     esp, 8
0x100594a8  push    ebx
0x100594a9  mov     ebx, [ebp+arg_8]
0x100594ac  mov     eax, ecx
0x100594ae  push    esi
0x100594af  push    edi; unsigned int
0x100594b0  mov     [ebp+var_4], eax
0x100594b3  mov     edi, [eax+4]
0x100594b6  push    ebx; void *
0x100594b7  mov     eax, [edi]
0x100594b9  mov     esi, [eax+7Ch]
0x100594bc  mov     ecx, esi
0x100594be  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100594c4  mov     ecx, edi
0x100594c6  call    esi
0x100594c8  mov     eax, [ebp+var_4]
0x100594cb  mov     esi, [ebp+arg_0]
0x100594ce  mov     dword ptr [eax+34h], 0
0x100594d5  mov     dword ptr [eax+38h], 0
0x100594dc  mov     dword ptr [eax+3Ch], 0
0x100594e3  test    esi, esi
0x100594e5  jle     loc_100596B7
0x100594eb  lea     ecx, [eax+0Ch]
0x100594ee  mov     [ebp+var_8], ecx
0x100594f1  mov     eax, [ebx]
0x100594f3  dec     esi
0x100594f4  mov     edi, ecx
0x100594f6  test    al, 8
0x100594f8  jnz     loc_100596B7
0x100594fe  mov     edx, [ebp+arg_4]
0x10059501  cmp     edx, 6; switch 7 cases
0x10059504  ja      short def_10059506; jumptable 10059506 default case, cases 4,5
0x10059506  jmp     ds:jpt_10059506[edx*4]; switch jump
0x1005950d  cmp     eax, 8; jumptable 10059506 default case, cases 4,5
0x10059510  jge     short loc_1005955E
0x10059512  test    eax, 0FFFFFFFEh
0x10059517  jz      short loc_10059539
0x10059519  mov     eax, [ebx+0Ch]
0x1005951c  test    eax, eax
0x1005951e  jz      short loc_10059529
0x10059520  push    eax; Block
0x10059521  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10059526  add     esp, 4
0x10059529  mov     eax, [ebx+10h]
0x1005952c  test    eax, eax
0x1005952e  jz      short loc_10059539
0x10059530  push    eax; Block
0x10059531  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10059536  add     esp, 4
0x10059539  mov     ecx, [ebp+var_8]
0x1005953c  mov     dword ptr [ebx], 8
0x10059542  mov     dword ptr [ebx+4], 0FFFFF88Eh
0x10059549  mov     dword ptr [ebx+8], 0
0x10059550  mov     dword ptr [ebx+0Ch], 0
0x10059557  mov     dword ptr [ebx+10h], 0
0x1005955e  cmp     dword ptr [edi], 0
0x10059561  jz      loc_100596B7
0x10059567  test    esi, esi
0x10059569  jg      short loc_100594F1
0x1005956b  jmp     loc_100596B7
0x10059570  mov     ecx, [ebp+var_4]; jumptable 10059506 case 0
0x10059573  push    ebx; struct Err *
0x10059574  call    ?GetFirstRow@TableMover@@IAEXAAVErr@@@Z; TableMover::GetFirstRow(Err &)
0x10059579  cmp     dword ptr [edi], 0
0x1005957c  jz      loc_100596B7
0x10059582  test    esi, esi
0x10059584  jle     loc_100596B7
0x1005958a  mov     edi, [ebp+var_8]
0x1005958d  dec     esi
0x1005958e  test    byte ptr [ebx], 8
0x10059591  jz      short loc_10059570; jumptable 10059506 case 0
0x10059593  jmp     loc_100596B7
0x100595a0  mov     ecx, [ebp+var_4]; jumptable 10059506 case 1
0x100595a3  push    ebx; struct Err *
0x100595a4  call    ?GetLastRow@TableMover@@IAEXAAVErr@@@Z; TableMover::GetLastRow(Err &)
0x100595a9  cmp     dword ptr [edi], 0
0x100595ac  jz      loc_100596B7
0x100595b2  test    esi, esi
0x100595b4  jle     loc_100596B7
0x100595ba  mov     edi, [ebp+var_8]
0x100595bd  dec     esi
0x100595be  test    byte ptr [ebx], 8
0x100595c1  jz      short loc_100595A0; jumptable 10059506 case 1
0x100595c3  jmp     loc_100596B7
0x100595c8  mov     eax, [ebp+var_4]; jumptable 10059506 case 2
0x100595cb  nop     dword ptr [eax+eax+00h]
0x100595d0  mov     ecx, [eax+8]
0x100595d3  test    ecx, ecx
0x100595d5  jz      short loc_10059613
0x100595d7  cmp     ecx, 4
0x100595da  jz      short loc_10059613
0x100595dc  cmp     ecx, 1
0x100595df  jz      short loc_100595F4
0x100595e1  cmp     dword ptr [edi], 0
0x100595e4  jz      loc_100596B7
0x100595ea  test    esi, esi
0x100595ec  jle     loc_100596B7
0x100595f2  jmp     short loc_1005962F
0x100595f4  push    ebx; struct Err *
0x100595f5  mov     ecx, eax; this
0x100595f7  call    ?GetFirstRow@TableMover@@IAEXAAVErr@@@Z; TableMover::GetFirstRow(Err &)
0x100595fc  test    byte ptr [ebx], 8
0x100595ff  jnz     short loc_1005961B
0x10059601  mov     eax, [ebp+var_4]
0x10059604  cmp     dword ptr [eax+0Ch], 0
0x10059608  jz      short loc_100595E1
0x1005960a  mov     dword ptr [eax+8], 0
0x10059611  jmp     short loc_100595E1
0x10059613  push    ebx; struct Err *
0x10059614  mov     ecx, eax; this
0x10059616  call    ?GetNextRow@TableMover@@IAEXAAVErr@@@Z; TableMover::GetNextRow(Err &)
0x1005961b  cmp     dword ptr [edi], 0
0x1005961e  jz      loc_100596B7
0x10059624  test    esi, esi
0x10059626  jle     loc_100596B7
0x1005962c  mov     eax, [ebp+var_4]
0x1005962f  lea     ecx, [eax+0Ch]
0x10059632  dec     esi
0x10059633  test    byte ptr [ebx], 8
0x10059636  mov     edi, ecx
0x10059638  jz      short loc_100595D0
0x1005963a  jmp     short loc_100596B7
0x1005963c  mov     eax, [ebp+var_4]; jumptable 10059506 case 3
0x1005963f  nop
0x10059640  mov     ecx, [eax+8]
0x10059643  test    ecx, ecx
0x10059645  jz      short loc_1005967B
0x10059647  cmp     ecx, 4
0x1005964a  jz      short loc_1005967B
0x1005964c  cmp     ecx, 2
0x1005964f  jz      short loc_1005965C
0x10059651  cmp     dword ptr [edi], 0
0x10059654  jz      short loc_100596B7
0x10059656  test    esi, esi
0x10059658  jle     short loc_100596B7
0x1005965a  jmp     short loc_1005968F
0x1005965c  push    ebx; struct Err *
0x1005965d  mov     ecx, eax; this
0x1005965f  call    ?GetLastRow@TableMover@@IAEXAAVErr@@@Z; TableMover::GetLastRow(Err &)
0x10059664  test    byte ptr [ebx], 8
0x10059667  jnz     short loc_10059683
0x10059669  mov     eax, [ebp+var_4]
0x1005966c  cmp     dword ptr [eax+0Ch], 0
0x10059670  jz      short loc_10059651
0x10059672  mov     dword ptr [eax+8], 0
0x10059679  jmp     short loc_10059651
0x1005967b  push    ebx; struct Err *
0x1005967c  mov     ecx, eax; this
0x1005967e  call    ?GetPriorRow@TableMover@@IAEXAAVErr@@@Z; TableMover::GetPriorRow(Err &)
0x10059683  cmp     dword ptr [edi], 0
0x10059686  jz      short loc_100596B7
0x10059688  test    esi, esi
0x1005968a  jle     short loc_100596B7
0x1005968c  mov     eax, [ebp+var_4]
0x1005968f  lea     ecx, [eax+0Ch]
0x10059692  dec     esi
0x10059693  test    byte ptr [ebx], 8
0x10059696  mov     edi, ecx
0x10059698  jz      short loc_10059640
0x1005969a  jmp     short loc_100596B7
0x100596a0  mov     dword ptr [edi], 0; jumptable 10059506 case 6
0x100596a6  cmp     dword ptr [edi], 0
0x100596a9  jz      short loc_100596B7
0x100596ab  test    esi, esi
0x100596ad  jle     short loc_100596B7
0x100596af  dec     esi
0x100596b0  mov     edi, ecx
0x100596b2  test    byte ptr [ebx], 8
0x100596b5  jz      short loc_100596A0; jumptable 10059506 case 6
0x100596b7  test    byte ptr [ebx], 8
0x100596ba  jnz     short loc_100596EF
0x100596bc  mov     esi, [ebp+var_4]
0x100596bf  cmp     dword ptr [esi+0Ch], 0
0x100596c3  jz      short loc_100596D5
0x100596c5  pop     edi
0x100596c6  mov     dword ptr [esi+8], 0
0x100596cd  pop     esi
0x100596ce  pop     ebx
0x100596cf  mov     esp, ebp
0x100596d1  pop     ebp
0x100596d2  retn    0Ch
0x100596d5  push    ecx
0x100596d6  push    0FFFFF9BDh
0x100596db  mov     ecx, ebx
0x100596dd  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x100596e2  xor     eax, eax
0x100596e4  cmp     [ebp+arg_4], 3
0x100596e8  setnz   al
0x100596eb  inc     eax
0x100596ec  mov     [esi+8], eax
0x100596ef  pop     edi
0x100596f0  pop     esi
0x100596f1  pop     ebx
0x100596f2  mov     esp, ebp
0x100596f4  pop     ebp
0x100596f5  retn    0Ch
```
