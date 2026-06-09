# CHtmlScanner::ReadTag(int)

- ea: `0x180008210`
- end: `0x18000867f`
- name: `?ReadTag@CHtmlScanner@@AEAAXH@Z`
- size: `1135`
- prototype: `void __fastcall(CHtmlScanner *__hidden this, int)`
- caller_count: `21`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180005110`
- `0x180005230`
- `0x180005470`
- `0x180005b40`
- `0x180005dc0`
- `0x180006a10`
- `0x180006b90`
- `0x180006d10`
- `0x180007020`
- `0x180007180`
- `0x180008690`
- `0x18000a3c0`
- `0x18000ad20`
- `0x18000b110`
- `0x18000b68c`
- `0x18000bea0`
- `0x18000cce0`
- `0x18000eac8`
- `0x180011a50`
- `0x180011a90`
- `0x18001f480`

## callees

- `0x180006768`
- `0x180006ad0`
- `0x180007094`
- `0x180008210`
- `0x180009a90`
- `0x18000a374`
- `0x18000a9a0`
- `0x18000ab00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1800083d8`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180008407`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1800083d8`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180008407`

## pseudocode

```c
void __fastcall CHtmlScanner::ReadTag(CHtmlScanner *this, int a2)
{
  int v4; // eax
  int v5; // r15d
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rcx
  wchar_t *v9; // rdx
  wchar_t Char; // ax
  CSerialStream *v11; // rcx
  wchar_t v12; // di
  bool v13; // zf
  unsigned int i; // r14d
  wchar_t v15; // ax
  wchar_t v16; // [rsp+50h] [rbp+8h] BYREF

  if ( *((_DWORD *)this + 8) != 1 )
  {
    v4 = *((_DWORD *)this + 9);
    *((_DWORD *)this + 8) = 1;
    *((_DWORD *)this + 7) = 0;
    if ( v4 == 22 )
    {
      CHtmlScanner::ReadComment(this, a2);
    }
    else
    {
      if ( v4 != 4 )
      {
        v5 = 0;
        while ( 1 )
        {
          v6 = *((_QWORD *)this + 1);
          if ( *(__int16 *)(v6 + 40) <= 0
            && *(_QWORD *)(v6 + 88) >= v6 + 2 * ((unsigned __int64)*(unsigned int *)(v6 + 84) + 21)
            && !*(_DWORD *)(v6 + 116)
            && *(_DWORD *)(v6 + 100) >= *(_DWORD *)(v6 + 104)
            && *(_DWORD *)(v6 + 96) == *(_DWORD *)(v6 + 296)
            && (unsigned int)CMmStreamConsecBuf::Eof((CMmStreamConsecBuf *)(v6 + 288)) )
          {
            return;
          }
          v7 = *((_QWORD *)this + 1);
          v8 = *(__int16 *)(v7 + 40);
          if ( (__int16)v8 > 0 )
          {
            *(_WORD *)(v7 + 40) = v8 - 1;
            v12 = *(_WORD *)(v7 + 2 * v8 - 2);
          }
          else
          {
            v9 = *(wchar_t **)(v7 + 88);
            if ( (unsigned __int64)v9 < v7 + 2 * ((unsigned __int64)*(unsigned int *)(v7 + 84) + 21) )
            {
              v12 = *v9;
              *(_QWORD *)(v7 + 88) = v9 + 1;
            }
            else if ( !*(_DWORD *)(v7 + 116)
                   && *(_DWORD *)(v7 + 100) >= *(_DWORD *)(v7 + 104)
                   && *(_DWORD *)(v7 + 96) == *(_DWORD *)(v7 + 296)
                   && (unsigned int)CMmStreamConsecBuf::Eof((CMmStreamConsecBuf *)(v7 + 288)) )
            {
              v12 = -1;
            }
            else
            {
              Char = CMemoryMappedInputStream::GetChar((CMemoryMappedInputStream *)(v7 + 96));
              v16 = Char;
              v12 = Char;
              if ( Char == 10 || Char == 13 )
              {
                v12 = 32;
              }
              else if ( Char == 38 )
              {
                *(_WORD *)(v7 + 42) = 38;
                for ( i = 1; i < 0x14; ++i )
                {
                  if ( !*(_DWORD *)(v7 + 116)
                    && *(_DWORD *)(v7 + 100) >= *(_DWORD *)(v7 + 104)
                    && *(_DWORD *)(v7 + 96) == *(_DWORD *)(v7 + 296)
                    && (unsigned int)CMmStreamConsecBuf::Eof((CMmStreamConsecBuf *)(v7 + 288)) )
                  {
                    if ( i == 1 )
                    {
                      v12 = 38;
                      goto LABEL_14;
                    }
                    --i;
                    break;
                  }
                  v15 = CMemoryMappedInputStream::GetChar((CMemoryMappedInputStream *)(v7 + 96));
                  v16 = v15;
                  v12 = v15;
                  if ( v15 == 10 || v15 == 13 )
                  {
                    v12 = 32;
                    v16 = 32;
                    *(_WORD *)(v7 + 2LL * i + 42) = 32;
                  }
                  else
                  {
                    *(_WORD *)(v7 + 2LL * i + 42) = v15;
                    if ( v15 == 59 )
                      goto LABEL_60;
                    if ( v15 == 38 )
                      break;
                  }
                }
                if ( v12 == 59
                  || !*(_DWORD *)(v7 + 116)
                  && *(_DWORD *)(v7 + 100) >= *(_DWORD *)(v7 + 104)
                  && *(_DWORD *)(v7 + 96) == *(_DWORD *)(v7 + 296)
                  && (unsigned int)CMmStreamConsecBuf::Eof((CMmStreamConsecBuf *)(v7 + 288)) )
                {
LABEL_60:
                  if ( *(_WORD *)(v7 + 44) == 35
                    && (unsigned int)CSerialStream::IsUnicodeNumber(v11, (const wchar_t *)(v7 + 46), i - 2, &v16) )
                  {
                    v12 = v16;
                  }
                  else if ( (unsigned int)LookupSpecialChar((const wchar_t *)(v7 + 44), i - 1, &v16) )
                  {
                    v12 = v16;
                  }
                  else
                  {
                    *(_QWORD *)(v7 + 88) = v7 + 44;
                    *(_DWORD *)(v7 + 84) = i + 1;
                    v12 = 38;
                  }
                  goto LABEL_14;
                }
                if ( v12 == 38 )
                {
                  *(_DWORD *)(v7 + 116) = 1;
                  *(_WORD *)(v7 + 120) = 38;
                  v12 = 38;
                  *(_DWORD *)(v7 + 84) = i;
                }
                else
                {
                  *(_DWORD *)(v7 + 84) = i;
                  v12 = 38;
                }
                *(_QWORD *)(v7 + 88) = v7 + 44;
              }
            }
          }
LABEL_14:
          switch ( v5 )
          {
            case 6:
              v13 = v12 == 34;
              break;
            case 0:
              if ( v12 == 62 )
                return;
              v5 = _o_iswspace(v12) == 0;
              goto LABEL_18;
            case 1:
              if ( v12 == 62 )
                return;
              if ( v12 == 61 )
                v5 = 4;
              goto LABEL_18;
            case 4:
              if ( v12 == 34 )
              {
                v5 = 6;
              }
              else if ( v12 != 9 && v12 != 32 )
              {
                if ( v12 == 39 )
                {
                  v5 = 5;
                }
                else
                {
                  if ( v12 == 62 )
                    return;
                  v5 = 7;
                }
              }
              goto LABEL_18;
            case 5:
              v13 = v12 == 39;
              break;
            default:
              if ( v12 == 62 )
                return;
              if ( !(unsigned int)_o_iswspace(v12) )
                goto LABEL_18;
LABEL_17:
              v5 = 0;
              goto LABEL_18;
          }
          if ( v13 )
            goto LABEL_17;
LABEL_18:
          if ( a2 )
          {
            if ( *((_DWORD *)this + 7) >= *((_DWORD *)this + 6) && (int)CHtmlScanner::GrowTagBuffer(this) < 0 )
              return;
            *(_WORD *)(*((_QWORD *)this + 2) + 2LL * (unsigned int)(*((_DWORD *)this + 7))++) = v12;
          }
        }
      }
      CHtmlScanner::EatAspCode(this);
    }
  }
}

```

## disassembly

```asm
0x180008210  push    rbp
0x180008212  push    r12
0x180008214  sub     rsp, 38h
0x180008218  cmp     dword ptr [rcx+20h], 1
0x18000821c  mov     r12d, edx
0x18000821f  mov     rbp, rcx
0x180008222  jz      loc_18000838C
0x180008228  mov     eax, [rcx+24h]
0x18000822b  mov     dword ptr [rcx+20h], 1
0x180008232  mov     dword ptr [rcx+1Ch], 0
0x180008239  cmp     eax, 16h
0x18000823c  jz      loc_1800085C8
0x180008242  cmp     eax, 4
0x180008245  jz      loc_1800085FD
0x18000824b  mov     [rsp+48h+arg_8], rbx
0x180008250  mov     [rsp+48h+arg_10], rsi
0x180008255  mov     [rsp+48h+arg_18], rdi
0x18000825a  mov     [rsp+48h+var_18], r13
0x18000825f  mov     r13d, 20h ; ' '
0x180008265  mov     [rsp+48h+var_20], r14
0x18000826a  mov     [rsp+48h+var_28], r15
0x18000826f  xor     r15d, r15d
0x180008272  mov     rax, [rbp+8]
0x180008276  cmp     word ptr [rax+28h], 0
0x18000827b  jg      short loc_180008292
0x18000827d  mov     edx, [rax+54h]
0x180008280  add     rdx, 15h
0x180008284  lea     rdx, [rax+rdx*2]
0x180008288  cmp     [rax+58h], rdx
0x18000828c  jnb     loc_180008338
0x180008292  mov     rbx, [rbp+8]
0x180008296  movsx   rcx, word ptr [rbx+28h]
0x18000829b  test    cx, cx
0x18000829e  jg      loc_18000841A
0x1800082a4  mov     ecx, [rbx+54h]
0x1800082a7  mov     rdx, [rbx+58h]
0x1800082ab  add     rcx, 15h
0x1800082af  lea     rcx, [rbx+rcx*2]
0x1800082b3  cmp     rdx, rcx
0x1800082b6  jb      loc_18000843C
0x1800082bc  cmp     dword ptr [rbx+74h], 0
0x1800082c0  jnz     short loc_1800082CE
0x1800082c2  mov     eax, [rbx+68h]
0x1800082c5  cmp     [rbx+64h], eax
0x1800082c8  jnb     loc_18000844C
0x1800082ce  lea     rcx, [rbx+60h]; this
0x1800082d2  call    ?GetChar@CMemoryMappedInputStream@@QEAA_WXZ; CMemoryMappedInputStream::GetChar(void)
0x1800082d7  mov     [rsp+48h+arg_0], ax
0x1800082dc  movzx   edi, ax
0x1800082df  cmp     ax, 0Ah
0x1800082e3  jz      loc_180008476
0x1800082e9  cmp     ax, 0Dh
0x1800082ed  jz      loc_180008476
0x1800082f3  cmp     ax, 26h ; '&'
0x1800082f7  jz      loc_1800084BD
0x1800082fd  cmp     r15d, 6
0x180008301  jnz     loc_180008394
0x180008307  cmp     di, 22h ; '"'
0x18000830b  jnz     short loc_180008310
0x18000830d  xor     r15d, r15d
0x180008310  test    r12d, r12d
0x180008313  jz      loc_180008272
0x180008319  mov     eax, [rbp+18h]
0x18000831c  cmp     [rbp+1Ch], eax
0x18000831f  jnb     loc_18000847F
0x180008325  mov     ecx, [rbp+1Ch]
0x180008328  mov     rax, [rbp+10h]
0x18000832c  mov     [rax+rcx*2], di
0x180008330  inc     dword ptr [rbp+1Ch]
0x180008333  jmp     loc_180008272
0x180008338  cmp     dword ptr [rax+74h], 0
0x18000833c  jnz     loc_180008292
0x180008342  mov     ecx, [rax+68h]
0x180008345  cmp     [rax+64h], ecx
0x180008348  jb      loc_180008292
0x18000834e  lea     rcx, [rax+120h]; this
0x180008355  mov     edx, [rcx+8]
0x180008358  cmp     [rax+60h], edx
0x18000835b  jnz     loc_180008292
0x180008361  call    ?Eof@CMmStreamConsecBuf@@QEAAHXZ; CMmStreamConsecBuf::Eof(void)
0x180008366  test    eax, eax
0x180008368  jz      loc_180008292
0x18000836e  mov     r14, [rsp+48h+var_20]
0x180008373  mov     r13, [rsp+48h+var_18]
0x180008378  mov     rdi, [rsp+48h+arg_18]
0x18000837d  mov     rsi, [rsp+48h+arg_10]
0x180008382  mov     rbx, [rsp+48h+arg_8]
0x180008387  mov     r15, [rsp+48h+var_28]
0x18000838c  add     rsp, 38h
0x180008390  pop     r12
0x180008392  pop     rbp
0x180008393  retn
0x180008394  mov     ecx, r15d
0x180008397  test    r15d, r15d
0x18000839a  jz      short loc_1800083CF
0x18000839c  sub     ecx, 1
0x18000839f  jnz     short loc_1800083BC
0x1800083a1  cmp     di, 3Eh ; '>'
0x1800083a5  jz      short loc_18000836E
0x1800083a7  cmp     di, 3Dh ; '='
0x1800083ab  jnz     loc_180008310
0x1800083b1  mov     r15d, 4
0x1800083b7  jmp     loc_180008310
0x1800083bc  sub     ecx, 3
0x1800083bf  jz      short loc_18000842B
0x1800083c1  sub     ecx, 1
0x1800083c4  jnz     short loc_1800083F1
0x1800083c6  cmp     di, 27h ; '''
0x1800083ca  jmp     loc_18000830B
0x1800083cf  cmp     di, 3Eh ; '>'
0x1800083d3  jz      short loc_18000836E
0x1800083d5  movzx   ecx, di
0x1800083d8  call    cs:__imp__o_iswspace
0x1800083de  test    eax, eax
0x1800083e0  jnz     loc_180008310
0x1800083e6  mov     r15d, 1
0x1800083ec  jmp     loc_180008310
0x1800083f1  cmp     ecx, 2
0x1800083f4  jnz     loc_180008310
0x1800083fa  cmp     di, 3Eh ; '>'
0x1800083fe  jz      loc_18000836E
0x180008404  movzx   ecx, di
0x180008407  call    cs:__imp__o_iswspace
0x18000840d  test    eax, eax
0x18000840f  jnz     loc_18000830D
0x180008415  jmp     loc_180008310
0x18000841a  lea     eax, [rcx-1]
0x18000841d  mov     [rbx+28h], ax
0x180008421  movzx   edi, word ptr [rbx+rcx*2-2]
0x180008426  jmp     loc_1800082FD
0x18000842b  cmp     di, 22h ; '"'
0x18000842f  jnz     short loc_180008494
0x180008431  mov     r15d, 6
0x180008437  jmp     loc_180008310
0x18000843c  movzx   edi, word ptr [rdx]
0x18000843f  lea     rax, [rdx+2]
0x180008443  mov     [rbx+58h], rax
0x180008447  jmp     loc_1800082FD
0x18000844c  lea     rcx, [rbx+120h]; this
0x180008453  mov     eax, [rcx+8]
0x180008456  cmp     [rbx+60h], eax
0x180008459  jnz     loc_1800082CE
0x18000845f  call    ?Eof@CMmStreamConsecBuf@@QEAAHXZ; CMmStreamConsecBuf::Eof(void)
0x180008464  test    eax, eax
0x180008466  jz      loc_1800082CE
0x18000846c  mov     edi, 0FFFFh
0x180008471  jmp     loc_1800082FD
0x180008476  movzx   edi, r13w
0x18000847a  jmp     loc_1800082FD
0x18000847f  mov     rcx, rbp; this
0x180008482  call    ?GrowTagBuffer@CHtmlScanner@@AEAAJXZ; CHtmlScanner::GrowTagBuffer(void)
0x180008487  test    eax, eax
0x180008489  jns     loc_180008325
0x18000848f  jmp     loc_18000836E
0x180008494  cmp     di, 9
0x180008498  jz      loc_180008310
0x18000849e  cmp     di, r13w
0x1800084a2  jz      loc_180008310
0x1800084a8  cmp     di, 27h ; '''
0x1800084ac  jnz     loc_180008551
0x1800084b2  mov     r15d, 5
0x1800084b8  jmp     loc_180008310
0x1800084bd  mov     [rbx+2Ah], ax
0x1800084c1  mov     r14d, 1
0x1800084c7  nop     word ptr [rax+rax+00000000h]
0x1800084d0  cmp     r14d, 14h
0x1800084d4  jnb     loc_180008609
0x1800084da  cmp     dword ptr [rbx+74h], 0
0x1800084de  jnz     short loc_1800084EC
0x1800084e0  mov     eax, [rbx+68h]
0x1800084e3  cmp     [rbx+64h], eax
0x1800084e6  jnb     loc_180008586
0x1800084ec  lea     rcx, [rbx+60h]; this
0x1800084f0  call    ?GetChar@CMemoryMappedInputStream@@QEAA_WXZ; CMemoryMappedInputStream::GetChar(void)
0x1800084f5  mov     [rsp+48h+arg_0], ax
0x1800084fa  movzx   edi, ax
0x1800084fd  cmp     ax, 0Ah
0x180008501  jz      loc_1800085D4
0x180008507  cmp     ax, 0Dh
0x18000850b  jz      loc_1800085D4
0x180008511  mov     eax, r14d
0x180008514  mov     [rbx+rax*2+2Ah], di
0x180008519  cmp     di, 3Bh ; ';'
0x18000851d  jnz     loc_1800085BA
0x180008523  cmp     word ptr [rbx+2Ch], 23h ; '#'
0x180008528  lea     rdi, [rbx+2Ch]
0x18000852c  jz      short loc_180008566
0x18000852e  lea     edx, [r14-1]; unsigned int
0x180008532  mov     rcx, rdi; Src
0x180008535  lea     r8, [rsp+48h+arg_0]; wchar_t *
0x18000853a  call    ?LookupSpecialChar@@YAHPEB_WKAEA_W@Z; LookupSpecialChar(wchar_t const *,ulong,wchar_t &)
0x18000853f  test    eax, eax
0x180008541  jz      loc_1800085E8
0x180008547  movzx   edi, [rsp+48h+arg_0]
0x18000854c  jmp     loc_1800082FD
0x180008551  cmp     di, 3Eh ; '>'
0x180008555  jz      loc_18000836E
0x18000855b  mov     r15d, 7
0x180008561  jmp     loc_180008310
0x180008566  lea     r8d, [r14-2]; unsigned int
0x18000856a  lea     rdx, [rbx+2Eh]; wchar_t *
0x18000856e  lea     r9, [rsp+48h+arg_0]; wchar_t *
0x180008573  call    ?IsUnicodeNumber@CSerialStream@@AEAAHPEB_WIAEA_W@Z; CSerialStream::IsUnicodeNumber(wchar_t const *,uint,wchar_t &)
0x180008578  test    eax, eax
0x18000857a  jz      short loc_18000852E
0x18000857c  movzx   edi, [rsp+48h+arg_0]
0x180008581  jmp     loc_1800082FD
0x180008586  lea     rcx, [rbx+120h]; this
0x18000858d  mov     eax, [rcx+8]
0x180008590  cmp     [rbx+60h], eax
0x180008593  jnz     loc_1800084EC
0x180008599  call    ?Eof@CMmStreamConsecBuf@@QEAAHXZ; CMmStreamConsecBuf::Eof(void)
0x18000859e  test    eax, eax
0x1800085a0  jz      loc_1800084EC
0x1800085a6  cmp     r14d, 1
0x1800085aa  jnz     loc_18000867A
0x1800085b0  mov     edi, 26h ; '&'
0x1800085b5  jmp     loc_1800082FD
0x1800085ba  cmp     di, 26h ; '&'
0x1800085be  jz      short loc_180008609
0x1800085c0  inc     r14d
0x1800085c3  jmp     loc_1800084D0
0x1800085c8  add     rsp, 38h
0x1800085cc  pop     r12
0x1800085ce  pop     rbp
0x1800085cf  jmp     ?ReadComment@CHtmlScanner@@AEAAXH@Z; CHtmlScanner::ReadComment(int)
0x1800085d4  mov     eax, r14d
0x1800085d7  mov     edi, r13d
0x1800085da  mov     [rsp+48h+arg_0], r13w
0x1800085e0  mov     [rbx+rax*2+2Ah], r13w
0x1800085e6  jmp     short loc_1800085C0
0x1800085e8  lea     eax, [r14+1]
0x1800085ec  mov     [rbx+58h], rdi
0x1800085f0  mov     [rbx+54h], eax
0x1800085f3  mov     edi, 26h ; '&'
0x1800085f8  jmp     loc_1800082FD
0x1800085fd  add     rsp, 38h
0x180008601  pop     r12
0x180008603  pop     rbp
0x180008604  jmp     ?EatAspCode@CHtmlScanner@@QEAAXXZ; CHtmlScanner::EatAspCode(void)
0x180008609  cmp     di, 3Bh ; ';'
0x18000860d  jz      loc_180008523
0x180008613  cmp     dword ptr [rbx+74h], 0
0x180008617  jnz     short loc_180008621
0x180008619  mov     eax, [rbx+68h]
0x18000861c  cmp     [rbx+64h], eax
0x18000861f  jnb     short loc_18000865D
0x180008621  lea     rax, [rbx+2Ch]
0x180008625  cmp     di, 26h ; '&'
0x180008629  jnz     short loc_18000864B
0x18000862b  mov     ecx, 26h ; '&'
0x180008630  mov     dword ptr [rbx+74h], 1
0x180008637  mov     [rbx+78h], cx
0x18000863b  movzx   edi, cx
0x18000863e  mov     [rbx+54h], r14d
0x180008642  mov     [rbx+58h], rax
0x180008646  jmp     loc_1800082FD
0x18000864b  mov     [rbx+54h], r14d
0x18000864f  mov     edi, 26h ; '&'
0x180008654  mov     [rbx+58h], rax
0x180008658  jmp     loc_1800082FD
0x18000865d  lea     rcx, [rbx+120h]; this
0x180008664  mov     eax, [rcx+8]
0x180008667  cmp     [rbx+60h], eax
0x18000866a  jnz     short loc_180008621
0x18000866c  call    ?Eof@CMmStreamConsecBuf@@QEAAHXZ; CMmStreamConsecBuf::Eof(void)
0x180008671  test    eax, eax
0x180008673  jz      short loc_180008621
0x180008675  jmp     loc_180008523
0x18000867a  dec     r14d
0x18000867d  jmp     short loc_180008609
```
