# ReferenceCursor::Move(long,MoveOption,Err &)

- ea: `0x10034f00`
- end: `0x1003508c`
- name: `?Move@ReferenceCursor@@UAEXJW4MoveOption@@AAVErr@@@Z`
- size: `396`
- prototype: `void __thiscall __high(int, enum MoveOption, struct Err *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x1000eb60`
- `0x10034f00`
- `0x100351b0`
- `0x1005e7e8`

## pseudocode

```c
void __thiscall ReferenceCursor::Move(_DWORD *this, int a2, int a3, int a4)
{
  int v4; // ebx
  _DWORD *v5; // esi
  int v6; // eax
  int v7; // eax
  int v8; // ecx
  int v9; // eax
  int v10; // ecx
  int v11; // edx

  v4 = a2;
  v5 = this;
  if ( a2 > 0 )
  {
    v6 = a3;
    do
    {
      --v4;
      switch ( v6 )
      {
        case 0:
          if ( !v5[1] )
          {
            v5[3] = v5[2];
            v5[4] = 0;
            break;
          }
          ReferenceCursor::GetNextReference((ReferenceCursor *)(v5 - 91), -1);
          goto LABEL_7;
        case 1:
        case 3:
        case 4:
          if ( *(int *)a4 >= 8 )
            continue;
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
          break;
        case 2:
          v7 = (*(int (__thiscall **)(_DWORD *))(*(v5 - 91) + 60))(v5 - 91);
          v5 = this;
          v8 = v7;
          v9 = this[3];
          if ( v9 < 0 )
            goto LABEL_15;
          if ( v9 >= *(_DWORD *)(v8 + 24) )
            goto LABEL_15;
          if ( *(_DWORD *)(v8 + 4 * v9 + 1524) == -1 )
            goto LABEL_15;
          _mm_lfence();
          v10 = *(_DWORD *)(v8 + 4 * *(_DWORD *)(v8 + 4 * v9 + 1524) + 1396);
          if ( !v10 )
            goto LABEL_15;
          v11 = this[4] + 1;
          this[4] = v11;
          if ( v11 >= *(_DWORD *)(*(_DWORD *)(v10 + 8) + 32) )
          {
            if ( this[2] == -1 )
            {
              ReferenceCursor::GetNextReference((ReferenceCursor *)(this - 91), this[3]);
LABEL_7:
              v5[4] = 0;
            }
            else
            {
LABEL_15:
              this[3] = -1;
            }
          }
          break;
        default:
          continue;
      }
      v6 = a3;
    }
    while ( v4 > 0 );
  }
  if ( v5[3] == -1 && *(int *)a4 < 8 )
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
0x10034f00  mov     edi, edi
0x10034f02  push    ebp
0x10034f03  mov     ebp, esp
0x10034f05  sub     esp, 8
0x10034f08  push    ebx
0x10034f09  mov     ebx, [ebp+arg_0]
0x10034f0c  push    esi; unsigned int
0x10034f0d  mov     esi, ecx
0x10034f0f  mov     [ebp+var_8], esi
0x10034f12  push    edi; void *
0x10034f13  mov     edi, [ebp+arg_8]
0x10034f16  test    ebx, ebx
0x10034f18  jle     loc_1003502D
0x10034f1e  mov     eax, [ebp+arg_4]
0x10034f21  dec     ebx
0x10034f22  cmp     eax, 4; switch 5 cases
0x10034f25  ja      def_10034F2B; jumptable 10034F2B default case
0x10034f2b  jmp     ds:jpt_10034F2B[eax*4]; switch jump
0x10034f32  cmp     dword ptr [esi+4], 0; jumptable 10034F2B case 0
0x10034f36  jnz     short loc_10034F4A
0x10034f38  mov     eax, [esi+8]
0x10034f3b  mov     [esi+0Ch], eax
0x10034f3e  mov     dword ptr [esi+10h], 0
0x10034f45  jmp     loc_10035022
0x10034f4a  push    0FFFFFFFFh; int
0x10034f4c  lea     ecx, [esi-16Ch]; this
0x10034f52  call    ?GetNextReference@ReferenceCursor@@AAEXJ@Z; ReferenceCursor::GetNextReference(long)
0x10034f57  mov     dword ptr [esi+10h], 0
0x10034f5e  jmp     loc_10035022
0x10034f63  lea     eax, [esi-16Ch]; jumptable 10034F2B case 2
0x10034f69  mov     [ebp+var_4], eax
0x10034f6c  mov     eax, [eax]
0x10034f6e  mov     esi, [eax+3Ch]
0x10034f71  mov     ecx, esi
0x10034f73  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10034f79  mov     ecx, [ebp+var_4]
0x10034f7c  call    esi
0x10034f7e  mov     esi, [ebp+var_8]
0x10034f81  mov     ecx, eax
0x10034f83  mov     eax, [esi+0Ch]
0x10034f86  test    eax, eax
0x10034f88  js      short loc_10034FC8
0x10034f8a  cmp     eax, [ecx+18h]
0x10034f8d  jge     short loc_10034FC8
0x10034f8f  cmp     dword ptr [ecx+eax*4+5F4h], 0FFFFFFFFh
0x10034f97  jz      short loc_10034FC8
0x10034f99  lfence
0x10034f9c  mov     eax, [ecx+eax*4+5F4h]
0x10034fa3  mov     ecx, [ecx+eax*4+574h]
0x10034faa  test    ecx, ecx
0x10034fac  jz      short loc_10034FC8
0x10034fae  mov     edx, [esi+10h]
0x10034fb1  inc     edx
0x10034fb2  mov     [esi+10h], edx
0x10034fb5  mov     eax, [ecx+8]
0x10034fb8  cmp     edx, [eax+20h]
0x10034fbb  jl      short loc_10035022
0x10034fbd  cmp     dword ptr [esi+8], 0FFFFFFFFh
0x10034fc1  jnz     short loc_10034FC8
0x10034fc3  push    dword ptr [esi+0Ch]
0x10034fc6  jmp     short loc_10034F4C
0x10034fc8  mov     dword ptr [esi+0Ch], 0FFFFFFFFh
0x10034fcf  jmp     short loc_10035022
0x10034fd1  mov     ecx, [edi]; jumptable 10034F2B cases 1,3,4
0x10034fd3  cmp     ecx, 8
0x10034fd6  jge     short def_10034F2B; jumptable 10034F2B default case
0x10034fd8  test    ecx, 0FFFFFFFEh
0x10034fde  jz      short loc_10035000
0x10034fe0  mov     eax, [edi+0Ch]
0x10034fe3  test    eax, eax
0x10034fe5  jz      short loc_10034FF0
0x10034fe7  push    eax; Block
0x10034fe8  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10034fed  add     esp, 4
0x10034ff0  mov     eax, [edi+10h]
0x10034ff3  test    eax, eax
0x10034ff5  jz      short loc_10035000
0x10034ff7  push    eax; Block
0x10034ff8  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10034ffd  add     esp, 4
0x10035000  mov     dword ptr [edi], 8
0x10035006  mov     dword ptr [edi+4], 0FFFFF88Eh
0x1003500d  mov     dword ptr [edi+8], 0
0x10035014  mov     dword ptr [edi+0Ch], 0
0x1003501b  mov     dword ptr [edi+10h], 0
0x10035022  mov     eax, [ebp+arg_4]
0x10035025  test    ebx, ebx; jumptable 10034F2B default case
0x10035027  jg      loc_10034F21
0x1003502d  cmp     dword ptr [esi+0Ch], 0FFFFFFFFh
0x10035031  jnz     short loc_10035083
0x10035033  mov     eax, [edi]
0x10035035  cmp     eax, 8
0x10035038  jge     short loc_10035083
0x1003503a  test    eax, 0FFFFFFFEh
0x1003503f  jz      short loc_10035061
0x10035041  mov     eax, [edi+0Ch]
0x10035044  test    eax, eax
0x10035046  jz      short loc_10035051
0x10035048  push    eax; Block
0x10035049  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1003504e  add     esp, 4
0x10035051  mov     eax, [edi+10h]
0x10035054  test    eax, eax
0x10035056  jz      short loc_10035061
0x10035058  push    eax; Block
0x10035059  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1003505e  add     esp, 4
0x10035061  mov     dword ptr [edi], 8
0x10035067  mov     dword ptr [edi+4], 0FFFFF9BDh
0x1003506e  mov     dword ptr [edi+8], 0
0x10035075  mov     dword ptr [edi+0Ch], 0
0x1003507c  mov     dword ptr [edi+10h], 0
0x10035083  pop     edi
0x10035084  pop     esi
0x10035085  pop     ebx
0x10035086  mov     esp, ebp
0x10035088  pop     ebp
0x10035089  retn    0Ch
```
