# ColumnCursor::Move(long,MoveOption,Err &)

- ea: `0x10033e70`
- end: `0x10034074`
- name: `?Move@ColumnCursor@@UAEXJW4MoveOption@@AAVErr@@@Z`
- size: `516`
- prototype: `void __thiscall __high(int, enum MoveOption, struct Err *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x1000eb60`
- `0x10033e70`
- `0x1005e7e8`

## pseudocode

```c
void __thiscall ColumnCursor::Move(_DWORD *this, int a2, int a3, int a4)
{
  int v4; // esi
  _DWORD *v5; // edx
  int v6; // ebx
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // ecx
  int i; // eax
  int v12; // eax
  int v13; // ecx
  int v14; // eax

  v4 = a2;
  v5 = this;
  if ( a2 <= 0 )
  {
LABEL_4:
    v6 = a4;
  }
  else
  {
    while ( 2 )
    {
      --v4;
      switch ( a3 )
      {
        case 0:
          while ( 1 )
          {
            v7 = (*(int (__thiscall **)(_DWORD *))(*(v5 - 91) + 60))(v5 - 91);
            v5 = this;
            this[2] = *(_DWORD *)(v7 + 368);
            if ( v4 <= 0 )
              break;
            --v4;
          }
          goto LABEL_4;
        case 1:
          while ( 1 )
          {
            v9 = (*(int (__thiscall **)(_DWORD *))(*(v5 - 91) + 60))(v5 - 91);
            v10 = *(_DWORD *)(v9 + 368);
            if ( v10 != -1 )
            {
              for ( i = *(_DWORD *)(v9 + 360); *(_DWORD *)(i + 8 * v10) != -1; v10 = *(_DWORD *)(i + 8 * v10) )
                ;
            }
            v5 = this;
            this[2] = v10;
            if ( v4 <= 0 )
              break;
            --v4;
          }
          goto LABEL_4;
        case 2:
          while ( 1 )
          {
            v8 = (*(int (__thiscall **)(_DWORD *))(*(v5 - 91) + 60))(v5 - 91);
            v5 = this;
            this[2] = *(_DWORD *)(*(_DWORD *)(v8 + 360) + 8 * this[2]);
            if ( v4 <= 0 )
              break;
            --v4;
          }
          goto LABEL_4;
        case 3:
          while ( 1 )
          {
            v12 = (*(int (__thiscall **)(_DWORD *))(*(v5 - 91) + 60))(v5 - 91);
            v5 = this;
            v13 = this[2];
            v14 = v13 == -1 ? -1 : *(_DWORD *)(*(_DWORD *)(v12 + 360) + 8 * v13 + 4);
            this[2] = v14;
            if ( v4 <= 0 )
              break;
            --v4;
          }
          goto LABEL_4;
        case 4:
          v6 = a4;
          while ( 1 )
          {
            if ( *(int *)a4 < 8 )
            {
              if ( (*(_DWORD *)a4 & 0xFFFFFFFE) != 0 )
              {
                if ( *(_DWORD *)(a4 + 12) )
                  operator delete[](*(void **)(a4 + 12));
                if ( *(_DWORD *)(a4 + 16) )
                  operator delete[](*(void **)(a4 + 16));
              }
              *(_DWORD *)a4 = 8;
              *(_DWORD *)(a4 + 4) = -1906;
              *(_DWORD *)(a4 + 8) = 0;
              *(_DWORD *)(a4 + 12) = 0;
              *(_DWORD *)(a4 + 16) = 0;
            }
            if ( v4 <= 0 )
              break;
            --v4;
          }
          v5 = this;
          break;
        default:
          if ( v4 <= 0 )
            goto LABEL_4;
          continue;
      }
      break;
    }
  }
  if ( v5[2] == -1 && *(int *)v6 < 8 )
  {
    if ( (*(_DWORD *)v6 & 0xFFFFFFFE) != 0 )
    {
      if ( *(_DWORD *)(v6 + 12) )
        operator delete[](*(void **)(v6 + 12));
      if ( *(_DWORD *)(v6 + 16) )
        operator delete[](*(void **)(v6 + 16));
    }
    *(_DWORD *)v6 = 8;
    *(_DWORD *)(v6 + 4) = -1603;
    *(_DWORD *)(v6 + 8) = 0;
    *(_DWORD *)(v6 + 12) = 0;
    *(_DWORD *)(v6 + 16) = 0;
  }
}

```

## disassembly

```asm
0x10033e70  mov     edi, edi
0x10033e72  push    ebp
0x10033e73  mov     ebp, esp
0x10033e75  push    ecx
0x10033e76  push    ebx
0x10033e77  push    esi; unsigned int
0x10033e78  mov     esi, [ebp+arg_0]
0x10033e7b  mov     edx, ecx
0x10033e7d  mov     [ebp+var_4], edx
0x10033e80  push    edi; void *
0x10033e81  test    esi, esi
0x10033e83  jle     short loc_10033E99
0x10033e85  mov     eax, [ebp+arg_4]
0x10033e88  dec     esi
0x10033e89  cmp     eax, 4; switch 5 cases
0x10033e8c  ja      short def_10033E8E; jumptable 10033E8E default case
0x10033e8e  jmp     ds:jpt_10033E8E[eax*4]; switch jump
0x10033e95  test    esi, esi; jumptable 10033E8E default case
0x10033e97  jg      short loc_10033E88
0x10033e99  mov     ebx, [ebp+arg_8]
0x10033e9c  cmp     dword ptr [edx+8], 0FFFFFFFFh
0x10033ea0  jnz     short loc_10033EF2
0x10033ea2  mov     eax, [ebx]
0x10033ea4  cmp     eax, 8
0x10033ea7  jge     short loc_10033EF2
0x10033ea9  test    eax, 0FFFFFFFEh
0x10033eae  jz      short loc_10033ED0
0x10033eb0  mov     eax, [ebx+0Ch]
0x10033eb3  test    eax, eax
0x10033eb5  jz      short loc_10033EC0
0x10033eb7  push    eax; Block
0x10033eb8  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10033ebd  add     esp, 4
0x10033ec0  mov     eax, [ebx+10h]
0x10033ec3  test    eax, eax
0x10033ec5  jz      short loc_10033ED0
0x10033ec7  push    eax; Block
0x10033ec8  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10033ecd  add     esp, 4
0x10033ed0  mov     dword ptr [ebx], 8
0x10033ed6  mov     dword ptr [ebx+4], 0FFFFF9BDh
0x10033edd  mov     dword ptr [ebx+8], 0
0x10033ee4  mov     dword ptr [ebx+0Ch], 0
0x10033eeb  mov     dword ptr [ebx+10h], 0
0x10033ef2  pop     edi
0x10033ef3  pop     esi
0x10033ef4  pop     ebx
0x10033ef5  mov     esp, ebp
0x10033ef7  pop     ebp
0x10033ef8  retn    0Ch
0x10033f00  mov     eax, [edx-16Ch]; jumptable 10033E8E case 0
0x10033f06  lea     ebx, [edx-16Ch]
0x10033f0c  mov     edi, [eax+3Ch]
0x10033f0f  mov     ecx, edi
0x10033f11  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10033f17  mov     ecx, ebx
0x10033f19  call    edi
0x10033f1b  mov     edx, [ebp+var_4]
0x10033f1e  mov     eax, [eax+170h]
0x10033f24  mov     [edx+8], eax
0x10033f27  test    esi, esi
0x10033f29  jle     loc_10033E99
0x10033f2f  dec     esi
0x10033f30  jmp     short loc_10033F00; jumptable 10033E8E case 0
0x10033f40  mov     eax, [edx-16Ch]; jumptable 10033E8E case 2
0x10033f46  lea     ebx, [edx-16Ch]
0x10033f4c  mov     edi, [eax+3Ch]
0x10033f4f  mov     ecx, edi
0x10033f51  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10033f57  mov     ecx, ebx
0x10033f59  call    edi
0x10033f5b  mov     edx, [ebp+var_4]
0x10033f5e  mov     eax, [eax+168h]
0x10033f64  mov     ecx, [edx+8]
0x10033f67  mov     eax, [eax+ecx*8]
0x10033f6a  mov     [edx+8], eax
0x10033f6d  test    esi, esi
0x10033f6f  jle     loc_10033E99
0x10033f75  dec     esi
0x10033f76  jmp     short loc_10033F40; jumptable 10033E8E case 2
0x10033f80  mov     eax, [edx-16Ch]; jumptable 10033E8E case 1
0x10033f86  lea     ebx, [edx-16Ch]
0x10033f8c  mov     edi, [eax+3Ch]
0x10033f8f  mov     ecx, edi
0x10033f91  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10033f97  mov     ecx, ebx
0x10033f99  call    edi
0x10033f9b  mov     ecx, [eax+170h]
0x10033fa1  cmp     ecx, 0FFFFFFFFh
0x10033fa4  jz      short loc_10033FBB
0x10033fa6  mov     eax, [eax+168h]
0x10033fac  cmp     dword ptr [eax+ecx*8], 0FFFFFFFFh
0x10033fb0  jz      short loc_10033FBB
0x10033fb2  mov     ecx, [eax+ecx*8]
0x10033fb5  cmp     dword ptr [eax+ecx*8], 0FFFFFFFFh
0x10033fb9  jnz     short loc_10033FB2
0x10033fbb  mov     edx, [ebp+var_4]
0x10033fbe  mov     [edx+8], ecx
0x10033fc1  test    esi, esi
0x10033fc3  jle     loc_10033E99
0x10033fc9  dec     esi
0x10033fca  jmp     short loc_10033F80; jumptable 10033E8E case 1
0x10033fd0  mov     eax, [edx-16Ch]; jumptable 10033E8E case 3
0x10033fd6  lea     ebx, [edx-16Ch]
0x10033fdc  mov     edi, [eax+3Ch]
0x10033fdf  mov     ecx, edi
0x10033fe1  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10033fe7  mov     ecx, ebx
0x10033fe9  call    edi
0x10033feb  mov     edx, [ebp+var_4]
0x10033fee  mov     ecx, [edx+8]
0x10033ff1  cmp     ecx, 0FFFFFFFFh
0x10033ff4  jnz     short loc_10033FFA
0x10033ff6  or      eax, ecx
0x10033ff8  jmp     short loc_10034004
0x10033ffa  mov     eax, [eax+168h]
0x10034000  mov     eax, [eax+ecx*8+4]
0x10034004  mov     [edx+8], eax
0x10034007  test    esi, esi
0x10034009  jle     loc_10033E99
0x1003400f  dec     esi
0x10034010  jmp     short loc_10033FD0; jumptable 10033E8E case 3
0x10034012  mov     ebx, [ebp+arg_8]; jumptable 10033E8E case 4
0x10034015  mov     eax, [ebx]
0x10034017  cmp     eax, 8
0x1003401a  jge     short loc_10034065
0x1003401c  test    eax, 0FFFFFFFEh
0x10034021  jz      short loc_10034043
0x10034023  mov     eax, [ebx+0Ch]
0x10034026  test    eax, eax
0x10034028  jz      short loc_10034033
0x1003402a  push    eax; Block
0x1003402b  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10034030  add     esp, 4
0x10034033  mov     eax, [ebx+10h]
0x10034036  test    eax, eax
0x10034038  jz      short loc_10034043
0x1003403a  push    eax; Block
0x1003403b  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10034040  add     esp, 4
0x10034043  mov     dword ptr [ebx], 8
0x10034049  mov     dword ptr [ebx+4], 0FFFFF88Eh
0x10034050  mov     dword ptr [ebx+8], 0
0x10034057  mov     dword ptr [ebx+0Ch], 0
0x1003405e  mov     dword ptr [ebx+10h], 0
0x10034065  test    esi, esi
0x10034067  jle     short loc_1003406C
0x10034069  dec     esi
0x1003406a  jmp     short loc_10034015
0x1003406c  mov     edx, [ebp+var_4]
0x1003406f  jmp     loc_10033E9C
```
