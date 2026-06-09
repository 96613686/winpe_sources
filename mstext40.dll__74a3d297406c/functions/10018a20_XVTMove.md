# XVTMove

- ea: `0x10018a20`
- end: `0x10018b72`
- name: `XVTMove`
- size: `338`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x10018850`

## callees

- `0x10018a20`

## pseudocode

```c
_DWORD *__stdcall XVTMove(int a1, _DWORD **a2, int a3, int a4)
{
  _DWORD **v4; // ecx
  _DWORD *v5; // eax
  _DWORD *result; // eax
  _DWORD *v7; // eax
  _DWORD *v8; // edx
  _DWORD *v9; // ecx
  int v10; // ecx
  _DWORD *v11; // eax
  int v12; // esi
  _DWORD *v13; // edx
  _DWORD *v14; // eax
  _DWORD *v15; // ecx

  switch ( a3 )
  {
    case 0:
      v4 = a2;
      v5 = (_DWORD *)*a2[1];
      if ( v5 )
        goto LABEL_3;
      *(_BYTE *)(a1 + 36) = 1;
      result = 0;
      break;
    case 1:
      v8 = a2[1];
      result = *a2;
      if ( v8 == *a2 )
      {
        *(_BYTE *)(a1 + 36) = 0;
        result = 0;
      }
      else
      {
        if ( !result )
          goto LABEL_32;
        while ( 1 )
        {
          v9 = (_DWORD *)*result;
          if ( (_DWORD *)*result == v8 )
            break;
          result = (_DWORD *)*result;
          if ( !v9 )
            return result;
        }
        a2[1] = result;
        *(_BYTE *)(a1 + 36) = 2;
        result = 0;
      }
      break;
    case 2:
      v4 = a2;
      v5 = *a2;
LABEL_3:
      v4[1] = v5;
      *(_BYTE *)(a1 + 36) = 2;
      result = 0;
      break;
    case 3:
      v7 = *a2;
      if ( !*a2 )
        goto LABEL_32;
      while ( *v7 )
        v7 = (_DWORD *)*v7;
      a2[1] = v7;
      *(_BYTE *)(a1 + 36) = 2;
      result = 0;
      break;
    case 4:
      v10 = 0;
      if ( a4 <= 0 )
        goto LABEL_32;
      while ( 1 )
      {
        v11 = (_DWORD *)*a2[1];
        if ( !v11 )
          break;
        ++v10;
        a2[1] = v11;
        *(_BYTE *)(a1 + 36) = 2;
        if ( v10 >= a4 )
          return 0;
      }
      *(_BYTE *)(a1 + 36) = 1;
      result = 0;
      break;
    case 5:
      v12 = 0;
      if ( -a4 < 0 || a4 == 0 )
        goto LABEL_32;
      do
      {
        v13 = a2[1];
        v14 = *a2;
        if ( v13 == *a2 )
        {
          *(_BYTE *)(a1 + 36) = 0;
          goto LABEL_32;
        }
        if ( v14 )
        {
          while ( 1 )
          {
            v15 = (_DWORD *)*v14;
            if ( (_DWORD *)*v14 == v13 )
              break;
            v14 = (_DWORD *)*v14;
            if ( !v15 )
              goto LABEL_29;
          }
          a2[1] = v14;
          *(_BYTE *)(a1 + 36) = 2;
        }
LABEL_29:
        ++v12;
      }
      while ( v12 < -a4 );
      result = 0;
      break;
    default:
LABEL_32:
      result = 0;
      break;
  }
  return result;
}

```

## disassembly

```asm
0x10018a20  mov     eax, [esp+arg_8]
0x10018a24  cmp     eax, 5; switch 6 cases
0x10018a27  ja      def_10018A2F; jumptable 10018A2F default case
0x10018a2d  push    esi
0x10018a2e  push    edi
0x10018a2f  jmp     ds:jpt_10018A2F[eax*4]; switch jump
0x10018a36  mov     ecx, [esp+8+arg_4]; jumptable 10018A2F case 2
0x10018a3a  mov     eax, [ecx]
0x10018a3c  mov     [ecx+4], eax
0x10018a3f  mov     eax, [esp+8+arg_0]
0x10018a43  pop     edi
0x10018a44  pop     esi
0x10018a45  mov     byte ptr [eax+24h], 2
0x10018a49  xor     eax, eax
0x10018a4b  retn    10h
0x10018a4e  mov     edx, [esp+8+arg_4]; jumptable 10018A2F case 3
0x10018a52  mov     eax, [edx]
0x10018a54  test    eax, eax
0x10018a56  jz      loc_10018B6B
0x10018a5c  lea     esp, [esp+0]
0x10018a60  mov     ecx, [eax]
0x10018a62  test    ecx, ecx
0x10018a64  jz      short loc_10018A71
0x10018a66  mov     eax, ecx
0x10018a68  test    eax, eax
0x10018a6a  jnz     short loc_10018A60
0x10018a6c  pop     edi
0x10018a6d  pop     esi
0x10018a6e  retn    10h
0x10018a71  mov     [edx+4], eax
0x10018a74  mov     eax, [esp+8+arg_0]
0x10018a78  pop     edi
0x10018a79  pop     esi
0x10018a7a  mov     byte ptr [eax+24h], 2
0x10018a7e  xor     eax, eax
0x10018a80  retn    10h
0x10018a83  mov     ecx, [esp+8+arg_4]; jumptable 10018A2F case 0
0x10018a87  mov     eax, [ecx+4]
0x10018a8a  mov     eax, [eax]
0x10018a8c  test    eax, eax
0x10018a8e  jnz     short loc_10018A3C
0x10018a90  mov     eax, [esp+8+arg_0]
0x10018a94  pop     edi
0x10018a95  pop     esi
0x10018a96  mov     byte ptr [eax+24h], 1
0x10018a9a  xor     eax, eax
0x10018a9c  retn    10h
0x10018a9f  mov     esi, [esp+8+arg_4]; jumptable 10018A2F case 1
0x10018aa3  mov     edx, [esi+4]
0x10018aa6  mov     eax, [esi]
0x10018aa8  cmp     edx, eax
0x10018aaa  jnz     short loc_10018ABB
0x10018aac  mov     eax, [esp+8+arg_0]
0x10018ab0  pop     edi
0x10018ab1  pop     esi
0x10018ab2  mov     byte ptr [eax+24h], 0
0x10018ab6  xor     eax, eax
0x10018ab8  retn    10h
0x10018abb  test    eax, eax
0x10018abd  jz      loc_10018B6B
0x10018ac3  mov     ecx, [eax]
0x10018ac5  cmp     ecx, edx
0x10018ac7  jz      short loc_10018AD4
0x10018ac9  mov     eax, ecx
0x10018acb  test    eax, eax
0x10018acd  jnz     short loc_10018AC3
0x10018acf  pop     edi
0x10018ad0  pop     esi
0x10018ad1  retn    10h
0x10018ad4  mov     [esi+4], eax
0x10018ad7  mov     eax, [esp+8+arg_0]
0x10018adb  pop     edi
0x10018adc  pop     esi
0x10018add  mov     byte ptr [eax+24h], 2
0x10018ae1  xor     eax, eax
0x10018ae3  retn    10h
0x10018ae6  mov     esi, [esp+8+arg_C]; jumptable 10018A2F case 4
0x10018aea  xor     ecx, ecx
0x10018aec  test    esi, esi
0x10018aee  jle     short loc_10018B6B
0x10018af0  mov     edx, [esp+8+arg_4]
0x10018af4  mov     edi, [esp+8+arg_0]
0x10018af8  mov     eax, [edx+4]
0x10018afb  mov     eax, [eax]
0x10018afd  test    eax, eax
0x10018aff  jz      short loc_10018B14
0x10018b01  inc     ecx
0x10018b02  mov     [edx+4], eax
0x10018b05  mov     byte ptr [edi+24h], 2
0x10018b09  cmp     ecx, esi
0x10018b0b  jl      short loc_10018AF8
0x10018b0d  pop     edi
0x10018b0e  pop     esi
0x10018b0f  xor     eax, eax
0x10018b11  retn    10h
0x10018b14  mov     byte ptr [edi+24h], 1
0x10018b18  xor     eax, eax
0x10018b1a  pop     edi
0x10018b1b  pop     esi
0x10018b1c  retn    10h
0x10018b1f  push    ebx; jumptable 10018A2F case 5
0x10018b20  mov     ebx, [esp+0Ch+arg_C]
0x10018b24  xor     esi, esi
0x10018b26  neg     ebx
0x10018b28  test    ebx, ebx
0x10018b2a  jle     short loc_10018B6A
0x10018b2c  mov     edi, [esp+0Ch+arg_4]
0x10018b30  push    ebp
0x10018b31  mov     ebp, [esp+10h+arg_0]
0x10018b35  mov     edx, [edi+4]
0x10018b38  mov     eax, [edi]
0x10018b3a  cmp     edx, eax
0x10018b3c  jz      short loc_10018B65
0x10018b3e  test    eax, eax
0x10018b40  jz      short loc_10018B57
0x10018b42  mov     ecx, [eax]
0x10018b44  cmp     ecx, edx
0x10018b46  jz      short loc_10018B50
0x10018b48  mov     eax, ecx
0x10018b4a  test    eax, eax
0x10018b4c  jnz     short loc_10018B42
0x10018b4e  jmp     short loc_10018B57
0x10018b50  mov     [edi+4], eax
0x10018b53  mov     byte ptr [ebp+24h], 2
0x10018b57  inc     esi
0x10018b58  cmp     esi, ebx
0x10018b5a  jl      short loc_10018B35
0x10018b5c  pop     ebp
0x10018b5d  pop     ebx
0x10018b5e  pop     edi
0x10018b5f  pop     esi
0x10018b60  xor     eax, eax
0x10018b62  retn    10h
0x10018b65  mov     byte ptr [ebp+24h], 0
0x10018b69  pop     ebp
0x10018b6a  pop     ebx
0x10018b6b  pop     edi
0x10018b6c  pop     esi
0x10018b6d  xor     eax, eax; jumptable 10018A2F default case
0x10018b6f  retn    10h
```
