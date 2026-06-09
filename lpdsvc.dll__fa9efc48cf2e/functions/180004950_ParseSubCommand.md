# ParseSubCommand

- ea: `0x180004950`
- end: `0x180004b0d`
- name: `ParseSubCommand`
- size: `445`
- prototype: `__int64 __fastcall(__int64, int *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003480`

## callees

- `0x180002e7c`
- `0x180004950`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_atol` at `0x1800049aa`
- `api-ms-win-crt-private-l1-1-0!_o_atol` at `0x1800049aa`
- `KERNEL32!LocalAlloc` at `0x180004a52`
- `KERNEL32!LocalAlloc` at `0x180004a52`

## pseudocode

```c
__int64 __fastcall ParseSubCommand(__int64 a1, int *a2, _QWORD *a3)
{
  unsigned int v6; // esi
  const char *v7; // rbx
  int v8; // ebp
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  int v11; // ecx
  char v12; // al
  __int64 v13; // rdi
  _BYTE *v14; // rax
  _BYTE *v15; // rdx
  __int64 result; // rax
  unsigned __int16 i; // r8
  __int64 v18; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_be2477e7779735c2769a11d7e4a742b7_Traceguids);
  v6 = *(_DWORD *)(a1 + 40);
  v7 = (const char *)(*(_QWORD *)(a1 + 32) + 1LL);
  v8 = atol(v7);
  if ( v8 )
  {
    v11 = 1;
    while ( 1 )
    {
      if ( *v7 == 32 || ((*v7 - 9) & 0xFB) == 0 )
      {
        while ( 1 )
        {
          v12 = *v7;
          if ( *v7 != 32 && v12 != 9 && v12 != 13 )
            break;
          if ( ++v11 >= v6 )
          {
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              v10 = 17;
              goto LABEL_38;
            }
            return 20003;
          }
          ++v7;
        }
        v13 = 0;
        if ( v12 == 10 )
        {
LABEL_24:
          v14 = LocalAlloc(0, (unsigned int)(v13 + 1));
          v15 = v14;
          if ( v14 )
          {
            for ( i = 0; i < (unsigned int)v13; v14[v18] = v7[v18] )
              v18 = i++;
            v14[v13] = 0;
            result = 0;
            *a3 = v15;
            *a2 = v8;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_be2477e7779735c2769a11d7e4a742b7_Traceguids);
            return 20001;
          }
          return result;
        }
        while ( ++v11 < v6 )
        {
          v13 = (unsigned int)(v13 + 1);
          if ( v7[v13] == 10 )
            goto LABEL_24;
        }
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v10 = 18;
          goto LABEL_38;
        }
        return 20003;
      }
      if ( ++v11 >= v6 )
        break;
      ++v7;
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v10 = 16;
      goto LABEL_38;
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v10 = 15;
LABEL_38:
      WPP_SF_(v9[2], v10, WPP_be2477e7779735c2769a11d7e4a742b7_Traceguids);
    }
  }
  return 20003;
}

```

## disassembly

```asm
0x180004950  push    rbx
0x180004952  push    rbp
0x180004953  push    rsi
0x180004954  push    rdi
0x180004955  push    r12
0x180004957  push    r13
0x180004959  push    r14
0x18000495b  push    r15
0x18000495d  sub     rsp, 28h
0x180004961  mov     r14, r8
0x180004964  mov     r15, rdx
0x180004967  mov     rdi, rcx
0x18000496a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004971  lea     r12, WPP_GLOBAL_Control
0x180004978  mov     r13d, 1
0x18000497e  cmp     rcx, r12
0x180004981  jz      short loc_18000499D
0x180004983  test    [rcx+1Ch], r13b
0x180004987  jz      short loc_18000499D
0x180004989  mov     rcx, [rcx+10h]
0x18000498d  lea     edx, [r13+0Dh]
0x180004991  lea     r8, WPP_be2477e7779735c2769a11d7e4a742b7_Traceguids
0x180004998  call    WPP_SF_
0x18000499d  mov     rbx, [rdi+20h]
0x1800049a1  mov     esi, [rdi+28h]
0x1800049a4  add     rbx, r13
0x1800049a7  mov     rcx, rbx; String
0x1800049aa  call    cs:__imp_atol
0x1800049b0  mov     ebp, eax
0x1800049b2  test    eax, eax
0x1800049b4  jnz     short loc_1800049D8
0x1800049b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800049bd  cmp     rcx, r12
0x1800049c0  jz      loc_180004AF7
0x1800049c6  test    byte ptr [rcx+1Ch], 8
0x1800049ca  jz      loc_180004AF7
0x1800049d0  lea     edx, [rax+0Fh]
0x1800049d3  jmp     loc_180004AE7
0x1800049d8  mov     ecx, r13d
0x1800049db  mov     dl, 20h ; ' '
0x1800049dd  jmp     short loc_1800049EF
0x1800049df  sub     al, 9
0x1800049e1  test    al, 0FBh
0x1800049e3  jz      short loc_1800049F5
0x1800049e5  add     ecx, r13d
0x1800049e8  cmp     ecx, esi
0x1800049ea  jnb     short loc_180004A13
0x1800049ec  add     rbx, r13
0x1800049ef  mov     al, [rbx]
0x1800049f1  cmp     al, dl
0x1800049f3  jnz     short loc_1800049DF
0x1800049f5  mov     al, [rbx]
0x1800049f7  cmp     al, dl
0x1800049f9  jz      short loc_180004A03
0x1800049fb  cmp     al, 9
0x1800049fd  jz      short loc_180004A03
0x1800049ff  cmp     al, 0Dh
0x180004a01  jnz     short loc_180004A37
0x180004a03  add     ecx, r13d
0x180004a06  cmp     ecx, esi
0x180004a08  jnb     loc_180004AD0
0x180004a0e  add     rbx, r13
0x180004a11  jmp     short loc_1800049F5
0x180004a13  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a1a  cmp     rcx, r12
0x180004a1d  jz      loc_180004AF7
0x180004a23  test    byte ptr [rcx+1Ch], 8
0x180004a27  jz      loc_180004AF7
0x180004a2d  mov     edx, 10h
0x180004a32  jmp     loc_180004AE7
0x180004a37  xor     edi, edi
0x180004a39  cmp     al, 0Ah
0x180004a3b  jz      short loc_180004A4D
0x180004a3d  add     ecx, r13d
0x180004a40  cmp     ecx, esi
0x180004a42  jnb     short loc_180004A8C
0x180004a44  add     edi, r13d
0x180004a47  cmp     byte ptr [rdi+rbx], 0Ah
0x180004a4b  jnz     short loc_180004A3D
0x180004a4d  lea     edx, [rdi+1]; uBytes
0x180004a50  xor     ecx, ecx; uFlags
0x180004a52  call    cs:__imp_LocalAlloc
0x180004a58  mov     rdx, rax
0x180004a5b  test    rax, rax
0x180004a5e  jnz     short loc_180004AA5
0x180004a60  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a67  cmp     rcx, r12
0x180004a6a  jz      short loc_180004A85
0x180004a6c  test    byte ptr [rcx+1Ch], 8
0x180004a70  jz      short loc_180004A85
0x180004a72  mov     rcx, [rcx+10h]
0x180004a76  lea     edx, [rax+13h]
0x180004a79  lea     r8, WPP_be2477e7779735c2769a11d7e4a742b7_Traceguids
0x180004a80  call    WPP_SF_
0x180004a85  mov     eax, 4E21h
0x180004a8a  jmp     short loc_180004AFC
0x180004a8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a93  cmp     rcx, r12
0x180004a96  jz      short loc_180004AF7
0x180004a98  test    byte ptr [rcx+1Ch], 8
0x180004a9c  jz      short loc_180004AF7
0x180004a9e  mov     edx, 12h
0x180004aa3  jmp     short loc_180004AE7
0x180004aa5  xor     r8d, r8d
0x180004aa8  test    edi, edi
0x180004aaa  jz      short loc_180004AC2
0x180004aac  movzx   ecx, r8w
0x180004ab0  add     r8w, r13w
0x180004ab4  mov     al, [rcx+rbx]
0x180004ab7  mov     [rcx+rdx], al
0x180004aba  movzx   eax, r8w
0x180004abe  cmp     eax, edi
0x180004ac0  jb      short loc_180004AAC
0x180004ac2  mov     byte ptr [rdi+rdx], 0
0x180004ac6  xor     eax, eax
0x180004ac8  mov     [r14], rdx
0x180004acb  mov     [r15], ebp
0x180004ace  jmp     short loc_180004AFC
0x180004ad0  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ad7  cmp     rcx, r12
0x180004ada  jz      short loc_180004AF7
0x180004adc  test    byte ptr [rcx+1Ch], 8
0x180004ae0  jz      short loc_180004AF7
0x180004ae2  mov     edx, 11h
0x180004ae7  mov     rcx, [rcx+10h]
0x180004aeb  lea     r8, WPP_be2477e7779735c2769a11d7e4a742b7_Traceguids
0x180004af2  call    WPP_SF_
0x180004af7  mov     eax, 4E23h
0x180004afc  add     rsp, 28h
0x180004b00  pop     r15
0x180004b02  pop     r14
0x180004b04  pop     r13
0x180004b06  pop     r12
0x180004b08  pop     rdi
0x180004b09  pop     rsi
0x180004b0a  pop     rbp
0x180004b0b  pop     rbx
0x180004b0c  retn
```
