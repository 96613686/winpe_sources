# CHtmlScanner::SkipCharsUntilNextRelevantToken(CToken &)

- ea: `0x18000ad20`
- end: `0x18000aeed`
- name: `?SkipCharsUntilNextRelevantToken@CHtmlScanner@@QEAAXAEAVCToken@@@Z`
- size: `461`
- prototype: `void __fastcall(CHtmlScanner *__hidden this, struct CToken *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x180005110`

## callees

- `0x180007048`
- `0x1800074e0`
- `0x180008210`
- `0x180009700`
- `0x18000a374`
- `0x18000abd0`
- `0x18000ad20`
- `0x18001357c`

## pseudocode

```c
void __fastcall CHtmlScanner::SkipCharsUntilNextRelevantToken(
        CHtmlScanner *this,
        struct CToken *a2,
        __int64 a3,
        const wchar_t *a4)
{
  struct CToken *v4; // rdi
  __int64 v6; // rax
  __int16 Char; // si
  CTagEntry *v8; // rsi
  __int64 v9; // rbp
  unsigned int i; // r14d
  __int64 v11; // rcx
  __int64 v12; // rax

  v4 = a2;
  *(_DWORD *)a2 = 1;
  *((_QWORD *)a2 + 1) = 0;
  while ( 1 )
  {
LABEL_2:
    v6 = *((_QWORD *)this + 1);
    if ( *(__int16 *)(v6 + 40) <= 0 )
    {
      a2 = (struct CToken *)(v6 + 2 * (*(unsigned int *)(v6 + 84) + 21LL));
      if ( *(_QWORD *)(v6 + 88) >= (unsigned __int64)a2
        && !*(_DWORD *)(v6 + 116)
        && *(_DWORD *)(v6 + 100) >= *(_DWORD *)(v6 + 104) )
      {
        a2 = (struct CToken *)*(unsigned int *)(v6 + 296);
        if ( *(_DWORD *)(v6 + 96) == (_DWORD)a2 )
        {
          if ( (unsigned int)CMmStreamConsecBuf::Eof((CMmStreamConsecBuf *)(v6 + 288)) )
          {
            *(_DWORD *)v4 = 2;
            return;
          }
        }
      }
    }
    Char = CSerialStream::GetChar(*((CSerialStream **)this + 1), (__int64)a2, a3, a4);
    if ( Char == 60 && (unsigned int)CHtmlScanner::Peek_ParseAsTag(this) )
    {
      CHtmlScanner::ScanTagName(this, v4);
      if ( *(_DWORD *)v4 != 2 )
      {
        switch ( *(_DWORD *)v4 )
        {
          case 2:
          case 4:
          case 0xA:
          case 0x14:
          case 0x15:
          case 0x16:
          case 0x17:
          case 0x18:
          case 0x19:
          case 0x1A:
          case 0x1B:
          case 0x1C:
          case 0x1D:
          case 0x1F:
          case 0x20:
          case 0x21:
          case 0x22:
          case 0x23:
          case 0x3D:
          case 0x3E:
            return;
          default:
            v8 = (CTagEntry *)*((_QWORD *)v4 + 1);
            if ( !v8 || !*((_DWORD *)v8 + 43) )
              goto LABEL_25;
            v9 = *(_QWORD *)this;
            if ( !*(_DWORD *)(*(_QWORD *)this + 64LL) )
            {
              for ( i = 0; ; ++i )
              {
                if ( i >= *(_DWORD *)(v9 + 68) )
                {
LABEL_25:
                  CHtmlScanner::ReadTag(this, 0);
                  goto LABEL_2;
                }
                if ( (unsigned int)CTagEntry::IsMatchProperty(
                                     v8,
                                     (struct CFullPropSpec *)(*(_QWORD *)(v9 + 72) + 32LL * i)) )
                  break;
              }
            }
            break;
        }
      }
      return;
    }
    if ( *(_DWORD *)(*(_QWORD *)this + 60LL) )
      break;
    CHtmlScanner::EatText(this);
  }
  v11 = *((_QWORD *)this + 1);
  v12 = *(__int16 *)(v11 + 40);
  if ( (int)v12 < 20 )
  {
    *(_WORD *)(v11 + 2 * v12) = Char;
    ++*(_WORD *)(v11 + 40);
  }
  *(_DWORD *)v4 = 8;
}

```

## disassembly

```asm
0x18000ad20  push    rbx
0x18000ad22  push    rbp
0x18000ad23  push    rsi
0x18000ad24  push    rdi
0x18000ad25  push    r14
0x18000ad27  push    r15
0x18000ad29  sub     rsp, 28h
0x18000ad2d  mov     rdi, rdx
0x18000ad30  mov     dword ptr [rdx], 1
0x18000ad36  mov     rbx, rcx
0x18000ad39  mov     qword ptr [rdx+8], 0
0x18000ad41  lea     r15, __ImageBase
0x18000ad48  mov     rax, [rbx+8]
0x18000ad4c  cmp     word ptr [rax+28h], 0
0x18000ad51  jg      short loc_18000AD68
0x18000ad53  mov     edx, [rax+54h]
0x18000ad56  add     rdx, 15h
0x18000ad5a  lea     rdx, [rax+rdx*2]
0x18000ad5e  cmp     [rax+58h], rdx
0x18000ad62  jnb     loc_18000AE2A
0x18000ad68  mov     rcx, [rbx+8]; this
0x18000ad6c  call    ?GetChar@CSerialStream@@QEAA_WXZ; CSerialStream::GetChar(void)
0x18000ad71  movzx   esi, ax
0x18000ad74  cmp     ax, 3Ch ; '<'
0x18000ad78  jnz     short loc_18000ADF4
0x18000ad7a  mov     rcx, rbx; this
0x18000ad7d  call    ?Peek_ParseAsTag@CHtmlScanner@@QEAAHXZ; CHtmlScanner::Peek_ParseAsTag(void)
0x18000ad82  test    eax, eax
0x18000ad84  jz      short loc_18000ADF4
0x18000ad86  mov     rdx, rdi; struct CToken *
0x18000ad89  mov     rcx, rbx; this
0x18000ad8c  call    ?ScanTagName@CHtmlScanner@@AEAAXAEAVCToken@@@Z; CHtmlScanner::ScanTagName(CToken &)
0x18000ad91  mov     eax, [rdi]
0x18000ad93  cmp     eax, 2
0x18000ad96  jz      loc_18000AE1D; jumptable 000000018000AEA5 cases 2,4,10,20-29,31-35,61,62
0x18000ad9c  add     eax, 0FFFFFFFEh; switch 61 cases
0x18000ad9f  cmp     eax, 3Ch
0x18000ada2  jbe     loc_18000AE8F
0x18000ada8  mov     rsi, [rdi+8]; jumptable 000000018000AEA5 default case, cases 3,5-9,11-19,30,36-60
0x18000adac  test    rsi, rsi
0x18000adaf  jz      loc_18000AE73
0x18000adb5  cmp     dword ptr [rsi+0ACh], 0
0x18000adbc  jz      loc_18000AE73
0x18000adc2  mov     rbp, [rbx]
0x18000adc5  cmp     dword ptr [rbp+40h], 0
0x18000adc9  jnz     short loc_18000AE1D; jumptable 000000018000AEA5 cases 2,4,10,20-29,31-35,61,62
0x18000adcb  xor     r14d, r14d
0x18000adce  cmp     r14d, [rbp+44h]
0x18000add2  jnb     loc_18000AE73
0x18000add8  mov     edx, r14d
0x18000addb  mov     rcx, rsi; this
0x18000adde  shl     rdx, 5
0x18000ade2  add     rdx, [rbp+48h]; struct CFullPropSpec *
0x18000ade6  call    ?IsMatchProperty@CTagEntry@@QEAAHAEAVCFullPropSpec@@@Z; CTagEntry::IsMatchProperty(CFullPropSpec &)
0x18000adeb  test    eax, eax
0x18000aded  jnz     short loc_18000AE1D; jumptable 000000018000AEA5 cases 2,4,10,20-29,31-35,61,62
0x18000adef  inc     r14d
0x18000adf2  jmp     short loc_18000ADCE
0x18000adf4  mov     rax, [rbx]
0x18000adf7  cmp     dword ptr [rax+3Ch], 0
0x18000adfb  jz      loc_18000AE82
0x18000ae01  mov     rcx, [rbx+8]
0x18000ae05  movsx   rax, word ptr [rcx+28h]
0x18000ae0a  cmp     eax, 14h
0x18000ae0d  jge     short loc_18000AE17
0x18000ae0f  mov     [rcx+rax*2], si
0x18000ae13  inc     word ptr [rcx+28h]
0x18000ae17  mov     dword ptr [rdi], 8
0x18000ae1d  add     rsp, 28h; jumptable 000000018000AEA5 cases 2,4,10,20-29,31-35,61,62
0x18000ae21  pop     r15
0x18000ae23  pop     r14
0x18000ae25  pop     rdi
0x18000ae26  pop     rsi
0x18000ae27  pop     rbp
0x18000ae28  pop     rbx
0x18000ae29  retn
0x18000ae2a  cmp     dword ptr [rax+74h], 0
0x18000ae2e  jnz     loc_18000AD68
0x18000ae34  mov     ecx, [rax+68h]
0x18000ae37  cmp     [rax+64h], ecx
0x18000ae3a  jb      loc_18000AD68
0x18000ae40  lea     rcx, [rax+120h]; this
0x18000ae47  mov     edx, [rcx+8]
0x18000ae4a  cmp     [rax+60h], edx
0x18000ae4d  jnz     loc_18000AD68
0x18000ae53  call    ?Eof@CMmStreamConsecBuf@@QEAAHXZ; CMmStreamConsecBuf::Eof(void)
0x18000ae58  test    eax, eax
0x18000ae5a  jz      loc_18000AD68
0x18000ae60  mov     dword ptr [rdi], 2
0x18000ae66  add     rsp, 28h
0x18000ae6a  pop     r15
0x18000ae6c  pop     r14
0x18000ae6e  pop     rdi
0x18000ae6f  pop     rsi
0x18000ae70  pop     rbp
0x18000ae71  pop     rbx
0x18000ae72  retn
0x18000ae73  xor     edx, edx; int
0x18000ae75  mov     rcx, rbx; this
0x18000ae78  call    ?ReadTag@CHtmlScanner@@AEAAXH@Z; CHtmlScanner::ReadTag(int)
0x18000ae7d  jmp     loc_18000AD48
0x18000ae82  mov     rcx, rbx; this
0x18000ae85  call    ?EatText@CHtmlScanner@@QEAAXXZ; CHtmlScanner::EatText(void)
0x18000ae8a  jmp     loc_18000AD48
0x18000ae8f  cdqe
0x18000ae91  movzx   eax, ds:(byte_18000AEB0 - 180000000h)[r15+rax]
0x18000ae9a  mov     ecx, ds:(jpt_18000AEA5 - 180000000h)[r15+rax*4]
0x18000aea2  add     rcx, r15
0x18000aea5  jmp     rcx; switch jump
```
