# CHtmlScanner::ScanTagBuffer(wchar_t const *,wchar_t * &,uint &)

- ea: `0x180007aa0`
- end: `0x180008208`
- name: `?ScanTagBuffer@CHtmlScanner@@QEAAXPEB_WAEAPEA_WAEAI@Z`
- size: `1896`
- prototype: `void __fastcall(CHtmlScanner *__hidden this, const wchar_t *, wchar_t **, unsigned int *)`
- caller_count: `9`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180005230`
- `0x180005b40`
- `0x180005dc0`
- `0x180006b90`
- `0x180006d10`
- `0x180007180`
- `0x180008690`
- `0x18000b68c`
- `0x18000bea0`

## callees

- `0x180006768`
- `0x180006ad0`
- `0x180007094`
- `0x180007aa0`
- `0x180009a90`
- `0x18000a374`
- `0x18000a9a0`
- `0x18000ab00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180007e6d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180007fa8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180007fd9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180008137`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180007e6d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180007fa8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180007fd9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180008137`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180007cb1`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180007cdd`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180007d20`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180007e36`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1800080c2`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180007cb1`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180007cdd`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180007d20`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180007e36`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1800080c2`

## pseudocode

```c
void __fastcall CHtmlScanner::ScanTagBuffer(CHtmlScanner *this, const wchar_t *a2, wchar_t **a3, unsigned int *a4)
{
  unsigned int v4; // r15d
  int v7; // eax
  int v8; // r14d
  __int64 v9; // rdx
  __int64 v10; // rbx
  __int64 v11; // rcx
  wchar_t *v12; // rdx
  wchar_t Char; // ax
  CSerialStream *v14; // rcx
  wchar_t v15; // si
  bool v16; // zf
  __int64 v17; // rbp
  wchar_t *v18; // rbx
  int v19; // esi
  wchar_t *v20; // r15
  int v21; // r14d
  int v22; // r12d
  __int64 v23; // rcx
  unsigned int *v24; // rcx
  wchar_t v25; // ax
  __int64 v26; // r9
  wchar_t v27; // [rsp+60h] [rbp+8h] BYREF
  wchar_t **v28; // [rsp+70h] [rbp+18h]
  unsigned int *v29; // [rsp+78h] [rbp+20h]

  v29 = a4;
  v28 = a3;
  v4 = 1;
  if ( *((_DWORD *)this + 8) != 1 )
  {
    v7 = *((_DWORD *)this + 9);
    *((_DWORD *)this + 8) = 1;
    *((_DWORD *)this + 7) = 0;
    if ( v7 == 22 )
    {
      CHtmlScanner::ReadComment(this, 1);
    }
    else
    {
      if ( v7 != 4 )
      {
        v8 = 0;
        while ( 1 )
        {
          v9 = *((_QWORD *)this + 1);
          if ( *(__int16 *)(v9 + 40) <= 0
            && *(_QWORD *)(v9 + 88) >= v9 + 2 * ((unsigned __int64)*(unsigned int *)(v9 + 84) + 21)
            && !*(_DWORD *)(v9 + 116)
            && *(_DWORD *)(v9 + 100) >= *(_DWORD *)(v9 + 104)
            && *(_DWORD *)(v9 + 96) == *(_DWORD *)(v9 + 296)
            && (unsigned int)CMmStreamConsecBuf::Eof((CMmStreamConsecBuf *)(v9 + 288)) )
          {
            goto LABEL_24;
          }
          v10 = *((_QWORD *)this + 1);
          v11 = *(__int16 *)(v10 + 40);
          if ( (__int16)v11 > 0 )
          {
            *(_WORD *)(v10 + 40) = v11 - 1;
            v15 = *(_WORD *)(v10 + 2 * v11 - 2);
          }
          else
          {
            v12 = *(wchar_t **)(v10 + 88);
            if ( (unsigned __int64)v12 < v10 + 2 * ((unsigned __int64)*(unsigned int *)(v10 + 84) + 21) )
            {
              v15 = *v12;
              *(_QWORD *)(v10 + 88) = v12 + 1;
            }
            else if ( !*(_DWORD *)(v10 + 116)
                   && *(_DWORD *)(v10 + 100) >= *(_DWORD *)(v10 + 104)
                   && *(_DWORD *)(v10 + 96) == *(_DWORD *)(v10 + 296)
                   && (unsigned int)CMmStreamConsecBuf::Eof((CMmStreamConsecBuf *)(v10 + 288)) )
            {
              v15 = -1;
            }
            else
            {
              Char = CMemoryMappedInputStream::GetChar((CMemoryMappedInputStream *)(v10 + 96));
              v27 = Char;
              v15 = Char;
              if ( Char == 10 || Char == 13 )
              {
                v15 = 32;
              }
              else if ( Char == 38 )
              {
                *(_WORD *)(v10 + 42) = 38;
                while ( v4 < 0x14 )
                {
                  if ( !*(_DWORD *)(v10 + 116)
                    && *(_DWORD *)(v10 + 100) >= *(_DWORD *)(v10 + 104)
                    && *(_DWORD *)(v10 + 96) == *(_DWORD *)(v10 + 296)
                    && (unsigned int)CMmStreamConsecBuf::Eof((CMmStreamConsecBuf *)(v10 + 288)) )
                  {
                    if ( v4 == 1 )
                    {
                      v15 = 38;
                      goto LABEL_14;
                    }
                    --v4;
                    break;
                  }
                  v25 = CMemoryMappedInputStream::GetChar((CMemoryMappedInputStream *)(v10 + 96));
                  v27 = v25;
                  v15 = v25;
                  if ( v25 == 10 || v25 == 13 )
                  {
                    v15 = 32;
                    v27 = 32;
                    *(_WORD *)(v10 + 2LL * v4 + 42) = 32;
                  }
                  else
                  {
                    *(_WORD *)(v10 + 2LL * v4 + 42) = v25;
                    if ( v25 == 59 )
                      goto LABEL_90;
                    if ( v25 == 38 )
                      break;
                  }
                  ++v4;
                }
                if ( v15 == 59
                  || !*(_DWORD *)(v10 + 116)
                  && *(_DWORD *)(v10 + 100) >= *(_DWORD *)(v10 + 104)
                  && *(_DWORD *)(v10 + 96) == *(_DWORD *)(v10 + 296)
                  && (unsigned int)CMmStreamConsecBuf::Eof((CMmStreamConsecBuf *)(v10 + 288)) )
                {
LABEL_90:
                  if ( *(_WORD *)(v10 + 44) == 35
                    && (unsigned int)CSerialStream::IsUnicodeNumber(v14, (const wchar_t *)(v10 + 46), v4 - 2, &v27) )
                  {
                    v15 = v27;
                    v4 = 1;
                  }
                  else
                  {
                    if ( (unsigned int)LookupSpecialChar((const wchar_t *)(v10 + 44), v4 - 1, &v27) )
                    {
                      v15 = v27;
                    }
                    else
                    {
                      *(_QWORD *)(v10 + 88) = v10 + 44;
                      *(_DWORD *)(v10 + 84) = v4 + 1;
                      v15 = 38;
                    }
                    v4 = 1;
                  }
                  goto LABEL_14;
                }
                if ( v15 == 38 )
                {
                  *(_DWORD *)(v10 + 116) = 1;
                  *(_WORD *)(v10 + 120) = 38;
                  v15 = 38;
                  *(_DWORD *)(v10 + 84) = v4;
                }
                else
                {
                  *(_DWORD *)(v10 + 84) = v4;
                  v15 = 38;
                }
                v4 = 1;
                *(_QWORD *)(v10 + 88) = v10 + 44;
              }
            }
          }
LABEL_14:
          if ( v8 == 6 )
            break;
          switch ( v8 )
          {
            case 0:
              if ( v15 == 62 )
                goto LABEL_24;
              if ( !(unsigned int)_o_iswspace(v15) )
                v8 = v4;
              goto LABEL_18;
            case 1:
              if ( v15 == 62 )
                goto LABEL_24;
              if ( v15 == 61 )
                v8 = 4;
              goto LABEL_18;
            case 4:
              if ( v15 == 34 )
              {
                v8 = 6;
              }
              else if ( v15 != 9 && v15 != 32 )
              {
                if ( v15 == 39 )
                {
                  v8 = 5;
                }
                else
                {
                  if ( v15 == 62 )
                    goto LABEL_24;
                  v8 = 7;
                }
              }
              goto LABEL_18;
            case 5:
              v16 = v15 == 39;
LABEL_16:
              if ( v16 )
                goto LABEL_17;
              goto LABEL_18;
          }
          if ( v15 == 62 )
            goto LABEL_24;
          if ( (unsigned int)_o_iswspace(v15) )
LABEL_17:
            v8 = 0;
LABEL_18:
          if ( *((_DWORD *)this + 7) >= *((_DWORD *)this + 6) && (int)CHtmlScanner::GrowTagBuffer(this) < 0 )
            goto LABEL_24;
          *(_WORD *)(*((_QWORD *)this + 2) + 2LL * (unsigned int)(*((_DWORD *)this + 7))++) = v15;
        }
        v16 = v15 == 34;
        goto LABEL_16;
      }
      CHtmlScanner::EatAspCode(this);
    }
LABEL_24:
    a3 = v28;
  }
  v17 = -1;
  do
    ++v17;
  while ( a2[v17] );
  v18 = (wchar_t *)*((_QWORD *)this + 2);
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  while ( (unsigned __int64)v18 < *((_QWORD *)this + 2) + 2 * (unsigned __int64)*((unsigned int *)this + 7) )
  {
    v23 = *v18;
    if ( v19 == 6 )
    {
      if ( (_WORD)v23 == 34 )
      {
        if ( v22 )
          goto LABEL_56;
        v19 = 0;
      }
      else if ( (_WORD)v23 == 61
             && (_DWORD)v17 == 13
             && !(unsigned int)_o__wcsnicmp(a2, L"location.href", 13, &_ImageBase)
             && (unsigned int)(v18 - *v28) >= 0xD
             && !(unsigned int)_o__wcsnicmp(a2, v18 - 13, 13, v26) )
      {
LABEL_126:
        v22 = 1;
LABEL_58:
        v19 = 4;
      }
LABEL_32:
      a3 = v28;
      ++v18;
    }
    else
    {
      switch ( v19 )
      {
        case 0:
          goto LABEL_119;
        case 1:
          if ( (_WORD)v23 != 61 )
          {
            if ( (unsigned int)_o_iswspace(v23) )
            {
              a3 = v28;
              v19 = 3;
            }
            else
            {
              a3 = v28;
              v21 = v18 - v20 + 1;
            }
            ++v18;
            continue;
          }
          if ( (_DWORD)v17 != v21 )
            goto LABEL_58;
          v19 = 4;
          if ( !(unsigned int)_o__wcsnicmp(a2, v20, (unsigned int)v17, &_ImageBase) )
            v22 = 1;
          goto LABEL_32;
        case 3:
          if ( (_WORD)v23 != 61 )
          {
LABEL_119:
            if ( (unsigned int)_o_iswspace(v23) )
              goto LABEL_32;
            a3 = v28;
            v21 = 0;
            v20 = v18;
            v19 = 1;
            ++v18;
            continue;
          }
          if ( (_DWORD)v17 != v21 || (unsigned int)_o__wcsnicmp(a2, v20, (unsigned int)v17, &_ImageBase) )
            goto LABEL_58;
          goto LABEL_126;
        case 4:
          if ( (_WORD)v23 == 34 )
          {
            v19 = 6;
            *a3 = ++v18;
            a3 = v28;
            continue;
          }
          if ( (_WORD)v23 == 39 )
          {
            v19 = 5;
            *a3 = ++v18;
            a3 = v28;
            continue;
          }
          if ( (_WORD)v23 != 9 && (_WORD)v23 != 32 )
          {
            *a3 = v18;
            v19 = 7;
            a3 = v28;
            ++v18;
            continue;
          }
          goto LABEL_32;
        case 5:
          if ( (_WORD)v23 != 39 )
            goto LABEL_32;
          if ( v22 )
            goto LABEL_56;
          v19 = 0;
          goto LABEL_32;
        case 7:
          if ( !(unsigned int)_o_iswspace(v23) )
            goto LABEL_32;
          if ( v22 )
          {
            *v29 = v18 - *v28;
            return;
          }
          a3 = v28;
          v19 = 0;
          ++v18;
          break;
        default:
          goto LABEL_32;
      }
    }
  }
  if ( v19 == 7 && v22 )
  {
LABEL_56:
    *v29 = v18 - *a3;
  }
  else
  {
    v24 = v29;
    *a3 = 0;
    *v24 = 0;
  }
}

```

## disassembly

```asm
0x180007aa0  mov     [rsp+arg_8], rbx
0x180007aa5  mov     [rsp+arg_18], r9
0x180007aaa  mov     [rsp+arg_10], r8
0x180007aaf  push    rbp
0x180007ab0  push    rsi
0x180007ab1  push    rdi
0x180007ab2  push    r12
0x180007ab4  push    r13
0x180007ab6  push    r14
0x180007ab8  push    r15
0x180007aba  sub     rsp, 20h
0x180007abe  mov     r15d, 1
0x180007ac4  mov     r13, rdx
0x180007ac7  mov     rdi, rcx
0x180007aca  cmp     [rcx+20h], r15d
0x180007ace  jz      loc_180007BF8
0x180007ad4  mov     eax, [rcx+24h]
0x180007ad7  mov     [rcx+20h], r15d
0x180007adb  mov     dword ptr [rcx+1Ch], 0
0x180007ae2  cmp     eax, 16h
0x180007ae5  jz      loc_1800080E9
0x180007aeb  cmp     eax, 4
0x180007aee  jz      loc_180008150
0x180007af4  xor     r14d, r14d
0x180007af7  mov     r12d, 20h ; ' '
0x180007afd  nop     dword ptr [rax]
0x180007b00  mov     rdx, [rdi+8]
0x180007b04  cmp     word ptr [rdx+28h], 0
0x180007b09  jg      short loc_180007B20
0x180007b0b  mov     ecx, [rdx+54h]
0x180007b0e  add     rcx, 15h
0x180007b12  lea     rcx, [rdx+rcx*2]
0x180007b16  cmp     [rdx+58h], rcx
0x180007b1a  jnb     loc_180007BBD
0x180007b20  mov     rbx, [rdi+8]
0x180007b24  movsx   rcx, word ptr [rbx+28h]
0x180007b29  test    cx, cx
0x180007b2c  jg      loc_180007CF0
0x180007b32  mov     ecx, [rbx+54h]
0x180007b35  mov     rdx, [rbx+58h]
0x180007b39  add     rcx, 15h
0x180007b3d  lea     rcx, [rbx+rcx*2]
0x180007b41  cmp     rdx, rcx
0x180007b44  jb      loc_180007DBF
0x180007b4a  cmp     dword ptr [rbx+74h], 0
0x180007b4e  jnz     short loc_180007B5C
0x180007b50  mov     eax, [rbx+68h]
0x180007b53  cmp     [rbx+64h], eax
0x180007b56  jnb     loc_180007DE5
0x180007b5c  lea     rcx, [rbx+60h]; this
0x180007b60  call    ?GetChar@CMemoryMappedInputStream@@QEAA_WXZ; CMemoryMappedInputStream::GetChar(void)
0x180007b65  mov     [rsp+58h+arg_0], ax
0x180007b6a  movzx   esi, ax
0x180007b6d  cmp     ax, 0Ah
0x180007b71  jz      loc_180007E0F
0x180007b77  cmp     ax, 0Dh
0x180007b7b  jz      loc_180007E0F
0x180007b81  cmp     ax, 26h ; '&'
0x180007b85  jz      loc_180007EC6
0x180007b8b  cmp     r14d, 6
0x180007b8f  jnz     loc_180007C61
0x180007b95  cmp     si, 22h ; '"'
0x180007b99  jnz     short loc_180007B9E
0x180007b9b  xor     r14d, r14d
0x180007b9e  mov     eax, [rdi+18h]
0x180007ba1  cmp     [rdi+1Ch], eax
0x180007ba4  jnb     loc_180007E88
0x180007baa  mov     ecx, [rdi+1Ch]
0x180007bad  mov     rax, [rdi+10h]
0x180007bb1  mov     [rax+rcx*2], si
0x180007bb5  inc     dword ptr [rdi+1Ch]
0x180007bb8  jmp     loc_180007B00
0x180007bbd  cmp     dword ptr [rdx+74h], 0
0x180007bc1  jnz     loc_180007B20
0x180007bc7  mov     eax, [rdx+68h]
0x180007bca  cmp     [rdx+64h], eax
0x180007bcd  jb      loc_180007B20
0x180007bd3  lea     rcx, [rdx+120h]; this
0x180007bda  mov     eax, [rcx+8]
0x180007bdd  cmp     [rdx+60h], eax
0x180007be0  jnz     loc_180007B20
0x180007be6  call    ?Eof@CMmStreamConsecBuf@@QEAAHXZ; CMmStreamConsecBuf::Eof(void)
0x180007beb  test    eax, eax
0x180007bed  jz      loc_180007B20
0x180007bf3  mov     r8, [rsp+58h+arg_10]
0x180007bf8  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x180007bff  nop
0x180007c00  inc     rbp
0x180007c03  cmp     word ptr [r13+rbp*2+0], 0
0x180007c0a  jnz     short loc_180007C00
0x180007c0c  mov     rbx, [rdi+10h]
0x180007c10  xor     esi, esi
0x180007c12  xor     r15d, r15d
0x180007c15  xor     r14d, r14d
0x180007c18  xor     r12d, r12d
0x180007c1b  mov     ecx, [rdi+1Ch]
0x180007c1e  lea     r9, __ImageBase
0x180007c25  mov     rax, [rdi+10h]
0x180007c29  lea     rcx, [rax+rcx*2]
0x180007c2d  cmp     rbx, rcx
0x180007c30  jnb     loc_180007E18
0x180007c36  movzx   ecx, word ptr [rbx]
0x180007c39  cmp     esi, 6
0x180007c3c  jnz     loc_180007D01
0x180007c42  cmp     cx, 22h ; '"'
0x180007c46  jz      loc_180007D6C
0x180007c4c  cmp     cx, 3Dh ; '='
0x180007c50  jz      loc_180007F8F
0x180007c56  mov     r8, [rsp+58h+arg_10]; jumptable 0000000180007D18 default case, cases 2,6
0x180007c5b  add     rbx, 2
0x180007c5f  jmp     short loc_180007C1B
0x180007c61  mov     ecx, r14d
0x180007c64  test    r14d, r14d
0x180007c67  jz      short loc_180007CA4
0x180007c69  sub     ecx, 1
0x180007c6c  jnz     short loc_180007C8D
0x180007c6e  cmp     si, 3Eh ; '>'
0x180007c72  jz      loc_180007BF3
0x180007c78  cmp     si, 3Dh ; '='
0x180007c7c  jnz     loc_180007B9E
0x180007c82  mov     r14d, 4
0x180007c88  jmp     loc_180007B9E
0x180007c8d  sub     ecx, 3
0x180007c90  jz      loc_180007DAA
0x180007c96  sub     ecx, 1
0x180007c99  jnz     short loc_180007CC7
0x180007c9b  cmp     si, 27h ; '''
0x180007c9f  jmp     loc_180007B99
0x180007ca4  cmp     si, 3Eh ; '>'
0x180007ca8  jz      loc_180007BF3
0x180007cae  movzx   ecx, si
0x180007cb1  call    cs:__imp__o_iswspace
0x180007cb7  test    eax, eax
0x180007cb9  jnz     loc_180007B9E
0x180007cbf  mov     r14d, r15d
0x180007cc2  jmp     loc_180007B9E
0x180007cc7  cmp     ecx, 2
0x180007cca  jnz     loc_180007B9E
0x180007cd0  cmp     si, 3Eh ; '>'
0x180007cd4  jz      loc_180007BF3
0x180007cda  movzx   ecx, si
0x180007cdd  call    cs:__imp__o_iswspace
0x180007ce3  test    eax, eax
0x180007ce5  jnz     loc_180007B9B
0x180007ceb  jmp     loc_180007B9E
0x180007cf0  lea     eax, [rcx-1]
0x180007cf3  mov     [rbx+28h], ax
0x180007cf7  movzx   esi, word ptr [rbx+rcx*2-2]
0x180007cfc  jmp     loc_180007B8B
0x180007d01  cmp     esi, 7; switch 8 cases
0x180007d04  ja      def_180007D18; jumptable 0000000180007D18 default case, cases 2,6
0x180007d0a  movsxd  rax, esi
0x180007d0d  mov     edx, ds:(jpt_180007D18 - 180000000h)[r9+rax*4]
0x180007d15  add     rdx, r9
0x180007d18  jmp     rdx; switch jump
0x180007d1a  cmp     cx, 3Dh ; '='; jumptable 0000000180007D18 case 1
0x180007d1e  jz      short loc_180007D97
0x180007d20  call    cs:__imp__o_iswspace
0x180007d26  test    eax, eax
0x180007d28  jnz     loc_18000809B
0x180007d2e  mov     r8, [rsp+58h+arg_10]
0x180007d33  mov     r14, rbx
0x180007d36  sub     r14, r15
0x180007d39  sar     r14, 1
0x180007d3c  inc     r14d
0x180007d3f  add     rbx, 2
0x180007d43  jmp     loc_180007C1B
0x180007d48  cmp     cx, 22h ; '"'; jumptable 0000000180007D18 case 4
0x180007d4c  jnz     loc_180007F5B
0x180007d52  lea     rax, [rbx+2]
0x180007d56  mov     esi, 6
0x180007d5b  mov     [r8], rax
0x180007d5e  add     rbx, 2
0x180007d62  mov     r8, [rsp+58h+arg_10]
0x180007d67  jmp     loc_180007C1B
0x180007d6c  test    r12d, r12d
0x180007d6f  jz      loc_1800081DF
0x180007d75  sub     rbx, [r8]
0x180007d78  mov     rcx, [rsp+58h+arg_18]
0x180007d7d  sar     rbx, 1
0x180007d80  mov     [rcx], ebx
0x180007d82  mov     rbx, [rsp+58h+arg_8]
0x180007d87  add     rsp, 20h
0x180007d8b  pop     r15
0x180007d8d  pop     r14
0x180007d8f  pop     r13
0x180007d91  pop     r12
0x180007d93  pop     rdi
0x180007d94  pop     rsi
0x180007d95  pop     rbp
0x180007d96  retn
0x180007d97  cmp     ebp, r14d
0x180007d9a  jz      loc_180007E64
0x180007da0  mov     esi, 4
0x180007da5  jmp     def_180007D18; jumptable 0000000180007D18 default case, cases 2,6
0x180007daa  cmp     si, 22h ; '"'
0x180007dae  jnz     loc_180007E9D
0x180007db4  mov     r14d, 6
0x180007dba  jmp     loc_180007B9E
0x180007dbf  movzx   esi, word ptr [rdx]
0x180007dc2  lea     rax, [rdx+2]
0x180007dc6  mov     [rbx+58h], rax
0x180007dca  jmp     loc_180007B8B
0x180007dcf  cmp     cx, 27h ; '''; jumptable 0000000180007D18 case 5
0x180007dd3  jnz     def_180007D18; jumptable 0000000180007D18 default case, cases 2,6
0x180007dd9  test    r12d, r12d
0x180007ddc  jnz     short loc_180007D75
0x180007dde  xor     esi, esi
0x180007de0  jmp     def_180007D18; jumptable 0000000180007D18 default case, cases 2,6
0x180007de5  lea     rcx, [rbx+120h]; this
0x180007dec  mov     eax, [rcx+8]
0x180007def  cmp     [rbx+60h], eax
0x180007df2  jnz     loc_180007B5C
0x180007df8  call    ?Eof@CMmStreamConsecBuf@@QEAAHXZ; CMmStreamConsecBuf::Eof(void)
0x180007dfd  test    eax, eax
0x180007dff  jz      loc_180007B5C
0x180007e05  mov     esi, 0FFFFh
0x180007e0a  jmp     loc_180007B8B
0x180007e0f  movzx   esi, r12w
0x180007e13  jmp     loc_180007B8B
0x180007e18  cmp     esi, 7
0x180007e1b  jz      loc_1800080AE
0x180007e21  mov     rcx, [rsp+58h+arg_18]
0x180007e26  xor     eax, eax
0x180007e28  mov     qword ptr [r8], 0
0x180007e2f  mov     [rcx], eax
0x180007e31  jmp     loc_180007D82
0x180007e36  call    cs:__imp__o_iswspace; jumptable 0000000180007D18 case 7
0x180007e3c  test    eax, eax
0x180007e3e  jz      def_180007D18; jumptable 0000000180007D18 default case, cases 2,6
0x180007e44  test    r12d, r12d
0x180007e47  jz      loc_18000802B
0x180007e4d  mov     rcx, [rsp+58h+arg_10]
0x180007e52  sub     rbx, [rcx]
0x180007e55  mov     rcx, [rsp+58h+arg_18]
0x180007e5a  sar     rbx, 1
0x180007e5d  mov     [rcx], ebx
0x180007e5f  jmp     loc_180007D82
0x180007e64  mov     r8d, ebp
0x180007e67  mov     rdx, r15
0x180007e6a  mov     rcx, r13
0x180007e6d  call    cs:__imp__o__wcsnicmp
0x180007e73  test    eax, eax
0x180007e75  mov     esi, 4
0x180007e7a  mov     eax, 1
0x180007e7f  cmovz   r12d, eax
0x180007e83  jmp     def_180007D18; jumptable 0000000180007D18 default case, cases 2,6
0x180007e88  mov     rcx, rdi; this
0x180007e8b  call    ?GrowTagBuffer@CHtmlScanner@@AEAAJXZ; CHtmlScanner::GrowTagBuffer(void)
0x180007e90  test    eax, eax
0x180007e92  jns     loc_180007BAA
0x180007e98  jmp     loc_180007BF3
0x180007e9d  cmp     si, 9
0x180007ea1  jz      loc_180007B9E
0x180007ea7  cmp     si, r12w
0x180007eab  jz      loc_180007B9E
0x180007eb1  cmp     si, 27h ; '''
0x180007eb5  jnz     loc_180007FEC
0x180007ebb  mov     r14d, 5
0x180007ec1  jmp     loc_180007B9E
0x180007ec6  mov     [rbx+2Ah], ax
0x180007eca  nop     word ptr [rax+rax+00h]
0x180007ed0  cmp     r15d, 14h
0x180007ed4  jnb     loc_18000815A
0x180007eda  cmp     dword ptr [rbx+74h], 0
0x180007ede  jnz     short loc_180007EEC
0x180007ee0  mov     eax, [rbx+68h]
0x180007ee3  cmp     [rbx+64h], eax
0x180007ee6  jnb     loc_180008055
0x180007eec  lea     rcx, [rbx+60h]; this
0x180007ef0  call    ?GetChar@CMemoryMappedInputStream@@QEAA_WXZ; CMemoryMappedInputStream::GetChar(void)
0x180007ef5  mov     [rsp+58h+arg_0], ax
0x180007efa  movzx   esi, ax
0x180007efd  cmp     ax, 0Ah
0x180007f01  jz      loc_1800080F6
0x180007f07  cmp     ax, 0Dh
0x180007f0b  jz      loc_1800080F6
0x180007f11  mov     eax, r15d
0x180007f14  mov     [rbx+rax*2+2Ah], si
0x180007f19  cmp     si, 3Bh ; ';'
0x180007f1d  jnz     loc_180008089
0x180007f23  cmp     word ptr [rbx+2Ch], 23h ; '#'
0x180007f28  lea     rsi, [rbx+2Ch]
0x180007f2c  jz      loc_180008001
0x180007f32  lea     edx, [r15-1]; unsigned int
0x180007f36  mov     rcx, rsi; Src
0x180007f39  lea     r8, [rsp+58h+arg_0]; wchar_t *
0x180007f3e  call    ?LookupSpecialChar@@YAHPEB_WKAEA_W@Z; LookupSpecialChar(wchar_t const *,ulong,wchar_t &)
0x180007f43  test    eax, eax
0x180007f45  jz      loc_18000810A
0x180007f4b  movzx   esi, [rsp+58h+arg_0]
0x180007f50  mov     r15d, 1
0x180007f56  jmp     loc_180007B8B
0x180007f5b  cmp     cx, 27h ; '''
0x180007f5f  jz      loc_18000803B
0x180007f65  cmp     cx, 9
0x180007f69  jz      def_180007D18; jumptable 0000000180007D18 default case, cases 2,6
0x180007f6f  cmp     cx, 20h ; ' '
0x180007f73  jz      def_180007D18; jumptable 0000000180007D18 default case, cases 2,6
0x180007f79  mov     [r8], rbx
  ... truncated ...
```
