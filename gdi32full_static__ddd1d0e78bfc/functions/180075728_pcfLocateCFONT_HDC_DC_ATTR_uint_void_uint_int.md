# pcfLocateCFONT(HDC__ *,_DC_ATTR *,uint,void *,uint,int)

- ea: `0x180075728`
- end: `0x180075b5d`
- name: `?pcfLocateCFONT@@YA?AV?$ReturnValueTracer@PEAU_CFONT@@@@PEAUHDC__@@PEAU_DC_ATTR@@IPEAXIH@Z`
- size: `1077`
- prototype: ``
- caller_count: `8`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180006840`
- `0x180022cf0`
- `0x180043a90`
- `0x180058460`
- `0x18005bf20`
- `0x180060230`
- `0x180075b70`
- `0x180075d80`

## callees

- `0x180017710`
- `0x180042038`
- `0x180042600`
- `0x1800426e8`
- `0x180042964`
- `0x180043e50`
- `0x18004e938`
- `0x1800756cc`
- `0x180075728`
- `0x18008a1bc`

## import_xrefs

- `GDI32!GdiGetEntry` at `0x18007584f`
- `GDI32!GdiGetEntry` at `0x18007584f`
- `GDI32!gW32PID` at `0x18007588e`
- `GDI32!gCookie` at `0x1800758b2`
- `GDI32!gMaxGdiHandleCount` at `0x18007582a`
- `win32u!NtGdiComputeXformCoefficients` at `0x1800757af`
- `win32u!NtGdiComputeXformCoefficients` at `0x1800757af`

## pseudocode

```c
__int64 __fastcall pcfLocateCFONT(
        __int64 a1,
        HDC a2,
        __int64 a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int a6,
        int a7)
{
  __int64 v11; // r15
  int CodePage; // eax
  unsigned int v13; // eax
  int v14; // ecx
  struct _CFONT *v15; // rdx
  struct _CFONT *i; // rbx
  unsigned int v18; // eax
  __int64 v19; // rsi
  struct _CFONT **v20; // rax
  struct _CFONT *CFONT; // rax
  unsigned __int8 *v22; // r8
  int v23; // eax
  int j; // ecx
  __int64 v25; // rax
  unsigned __int8 *v26; // rax
  int v27; // eax
  unsigned int v28; // r9d
  int v29; // eax
  unsigned int v30; // r9d
  __int128 v31; // [rsp+30h] [rbp-58h] BYREF
  __int64 v32; // [rsp+40h] [rbp-48h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10);
  }
  if ( (int)GetDCDpiScaleValue(a2) > 1 )
    goto LABEL_18;
  if ( (unsigned int)QueryFontAssocStatus() )
    goto LABEL_18;
  v11 = *(_QWORD *)(a3 + 296);
  if ( (*(_BYTE *)(a3 + 152) & 0x20) != 0 )
    goto LABEL_18;
  if ( (*(_DWORD *)(a3 + 340) & 0xE000) != 0 || (*(_BYTE *)(a3 + 64) & 1) == 0 )
  {
    if ( !(unsigned int)NtGdiComputeXformCoefficients(a2) )
      *(_DWORD *)(a3 + 152) |= 0x20u;
    if ( (*(_BYTE *)(a3 + 152) & 0x20) != 0 )
      goto LABEL_18;
  }
  if ( guintDBCScp != -1 )
  {
    CodePage = GetCodePage(a2);
    if ( guintDBCScp != CodePage )
    {
      v13 = CodePage - 932;
      if ( v13 <= 0x12 )
      {
        v14 = 393233;
        if ( _bittest(&v14, v13) )
        {
          *(_DWORD *)(a3 + 152) |= 0x20u;
LABEL_18:
          v15 = 0;
          goto LABEL_19;
        }
      }
    }
  }
  i = 0;
  v18 = HANDLE_TO_INDEX(v11);
  if ( v18 < gMaxGdiHandleCount
    && (v32 = 0, v31 = 0, (int)GdiGetEntry(v18, &v31) >= 0)
    && BYTE14(v31) == 10
    && WORD6(v31) == WORD1(v11)
    && (DWORD2(v31) & 0xFFFFFFFE) == gW32PID
    && v32
    && (v19 = gCookie ^ __ROR8__(v32, 64 - (gCookie & 0x3Fu))) != 0
    && (v20 = *(struct _CFONT ***)(v19 + 8)) != 0
    && (*(_BYTE *)v19 & 1) == 0 )
  {
    for ( i = *v20; ; i = *(struct _CFONT **)i )
    {
      if ( !i )
      {
        CFONT = pcfCreateCFONT(a2, (struct _DC_ATTR *)a3, a4, a5, a6, a7);
        i = CFONT;
        if ( CFONT )
        {
          *((_QWORD *)CFONT + 2) = v11;
          if ( (*(_BYTE *)a3 & 2) != 0 )
          {
            *((_QWORD *)CFONT + 5) = 0;
            *((_QWORD *)CFONT + 1) = 0;
          }
          else
          {
            *((_QWORD *)CFONT + 5) = a2;
            *((_QWORD *)CFONT + 1) = *(_QWORD *)(a3 + 352);
            *(_QWORD *)(a3 + 352) = CFONT;
          }
          *(_QWORD *)CFONT = **(_QWORD **)(v19 + 8);
          **(_QWORD **)(v19 + 8) = CFONT;
        }
        goto LABEL_81;
      }
      if ( (!*((_QWORD *)i + 5) && (*(_BYTE *)a3 & 2) != 0 || *((HDC *)i + 5) == a2)
        && *((float *)i + 12) == *(float *)(a3 + 32)
        && *((float *)i + 13) == *(float *)(a3 + 44) )
      {
        break;
      }
    }
    ++*((_DWORD *)i + 6);
    if ( (*((_BYTE *)i + 28) & 1) != 0 )
      goto LABEL_41;
    v22 = a5;
    v23 = *((_DWORD *)i + 7) & 0x20;
    if ( a5 )
    {
      if ( v23 )
      {
        if ( a7 )
        {
          if ( (*((_BYTE *)i + 28) & 4) != 0 )
          {
            for ( j = a6; j > 0; ++v22 )
            {
              v25 = *v22;
              if ( *((_WORD *)gpwcDBCSCharSet + v25) == 0xFFFF )
              {
                v26 = v22 + 1;
                if ( !j )
                  v26 = v22;
                v22 = v26;
                v27 = j - 1;
                if ( !j )
                  v27 = 0;
                j = v27;
              }
              else if ( *((_WORD *)i + v25 + 42) == 0xFFFF )
              {
                break;
              }
              --j;
            }
            v28 = 0;
            if ( j >= 0 )
              v28 = j;
          }
          else
          {
            v28 = a6;
            if ( !a6 )
              goto LABEL_81;
            do
            {
              if ( *((_WORD *)i + *v22 + 42) == 0xFFFF )
                break;
              ++v22;
              --v28;
            }
            while ( v28 );
          }
        }
        else
        {
          v28 = a6;
          if ( !a6 )
            goto LABEL_81;
          do
          {
            if ( *((_WORD *)i + *(unsigned __int16 *)v22 + 42) == 0xFFFF )
              break;
            v22 += 2;
            --v28;
          }
          while ( v28 );
        }
      }
      else
      {
        v28 = a6;
      }
      if ( !v28 )
        goto LABEL_81;
      v29 = bFillWidthTableForGTE(a2, i, v22, v28, a7);
    }
    else
    {
      v30 = a6;
      if ( !v23 || ((a4 | (a4 + a6)) & 0xFFFFFF00) != 0 )
      {
LABEL_74:
        if ( !v30 )
          goto LABEL_81;
      }
      else
      {
        if ( !a6 )
          goto LABEL_81;
        while ( *((_WORD *)i + a4 + 42) != 0xFFFF )
        {
          ++a4;
          if ( !--v30 )
            goto LABEL_74;
        }
      }
      v29 = bFillWidthTableForGCW(a2, i, a4, v30);
    }
    if ( v29 == -1 )
    {
      --*((_DWORD *)i + 6);
      *(_DWORD *)(a3 + 152) |= 0x20u;
      i = 0;
    }
  }
  else
  {
    *(_DWORD *)(a3 + 152) |= 0x20u;
  }
LABEL_81:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11);
  }
LABEL_41:
  v15 = i;
LABEL_19:
  ReturnValueTracer<_CFONT *>::ReturnValueTracer<_CFONT *>(a1, v15);
  return a1;
}

```

## disassembly

```asm
0x180075728  push    rbx
0x18007572a  push    rbp
0x18007572b  push    rsi
0x18007572c  push    rdi
0x18007572d  push    r12
0x18007572f  push    r14
0x180075731  push    r15
0x180075733  sub     rsp, 50h
0x180075737  mov     r14d, r9d
0x18007573a  mov     rdi, r8
0x18007573d  mov     r12, rdx
0x180075740  mov     rbp, rcx
0x180075743  mov     rcx, cs:WPP_GLOBAL_Control
0x18007574a  lea     rax, WPP_GLOBAL_Control
0x180075751  cmp     rcx, rax
0x180075754  jz      short loc_180075770
0x180075756  test    byte ptr [rcx+1Ch], 1
0x18007575a  jz      short loc_180075770
0x18007575c  cmp     byte ptr [rcx+19h], 5
0x180075760  jb      short loc_180075770
0x180075762  mov     rcx, [rcx+10h]
0x180075766  mov     edx, 0Ah
0x18007576b  call    WPP_SF_
0x180075770  mov     rcx, r12
0x180075773  call    GetDCDpiScaleValue
0x180075778  cmp     eax, 1
0x18007577b  jg      loc_180075803
0x180075781  call    QueryFontAssocStatus
0x180075786  test    eax, eax
0x180075788  jnz     short loc_180075803
0x18007578a  test    byte ptr [rdi+98h], 20h
0x180075791  mov     r15, [rdi+128h]
0x180075798  jnz     short loc_180075803
0x18007579a  test    dword ptr [rdi+154h], 0E000h
0x1800757a4  jnz     short loc_1800757AC
0x1800757a6  test    byte ptr [rdi+40h], 1
0x1800757aa  jnz     short loc_1800757CF
0x1800757ac  mov     rcx, r12
0x1800757af  call    cs:__imp_NtGdiComputeXformCoefficients
0x1800757b6  nop     dword ptr [rax+rax+00h]
0x1800757bb  test    eax, eax
0x1800757bd  jnz     short loc_1800757C6
0x1800757bf  or      dword ptr [rdi+98h], 20h
0x1800757c6  test    byte ptr [rdi+98h], 20h
0x1800757cd  jnz     short loc_180075803
0x1800757cf  cmp     cs:guintDBCScp, 0FFFFFFFFh
0x1800757d6  jz      short loc_180075820
0x1800757d8  mov     rcx, r12
0x1800757db  call    GetCodePage
0x1800757e0  cmp     cs:guintDBCScp, eax
0x1800757e6  jz      short loc_180075820
0x1800757e8  add     eax, 0FFFFFC5Ch
0x1800757ed  cmp     eax, 12h
0x1800757f0  ja      short loc_180075820
0x1800757f2  mov     ecx, 60011h
0x1800757f7  bt      ecx, eax
0x1800757fa  jnb     short loc_180075820
0x1800757fc  or      dword ptr [rdi+98h], 20h
0x180075803  xor     edx, edx
0x180075805  mov     rcx, rbp
0x180075808  call    ??0?$ReturnValueTracer@PEAU_CFONT@@@@QEAA@QEAU_CFONT@@@Z; ReturnValueTracer<_CFONT *>::ReturnValueTracer<_CFONT *>(_CFONT * const)
0x18007580d  mov     rax, rbp
0x180075810  add     rsp, 50h
0x180075814  pop     r15
0x180075816  pop     r14
0x180075818  pop     r12
0x18007581a  pop     rdi
0x18007581b  pop     rsi
0x18007581c  pop     rbp
0x18007581d  pop     rbx
0x18007581e  retn
0x180075820  mov     rcx, r15
0x180075823  xor     ebx, ebx
0x180075825  call    HANDLE_TO_INDEX
0x18007582a  mov     rcx, cs:__imp_gMaxGdiHandleCount
0x180075831  cmp     eax, [rcx]
0x180075833  jnb     loc_180075B18
0x180075839  xor     ecx, ecx
0x18007583b  lea     rdx, [rsp+88h+var_58]
0x180075840  mov     [rsp+88h+var_48], rcx
0x180075845  xorps   xmm0, xmm0
0x180075848  mov     ecx, eax
0x18007584a  movups  [rsp+88h+var_58], xmm0
0x18007584f  call    cs:__imp_GdiGetEntry
0x180075856  nop     dword ptr [rax+rax+00h]
0x18007585b  test    eax, eax
0x18007585d  js      loc_180075B18
0x180075863  cmp     byte ptr [rsp+88h+var_58+0Eh], 0Ah
0x180075868  jnz     loc_180075B18
0x18007586e  movzx   eax, byte ptr [rsp+88h+var_58+0Ch]
0x180075873  movzx   ecx, byte ptr [rsp+88h+var_58+0Dh]
0x180075878  shl     cx, 8
0x18007587c  or      cx, ax
0x18007587f  mov     eax, r15d
0x180075882  shr     eax, 10h
0x180075885  cmp     cx, ax
0x180075888  jnz     loc_180075B18
0x18007588e  mov     rax, cs:__imp_gW32PID
0x180075895  mov     ecx, dword ptr [rsp+88h+var_58+8]
0x180075899  and     ecx, 0FFFFFFFEh
0x18007589c  cmp     ecx, [rax]
0x18007589e  jnz     loc_180075B18
0x1800758a4  mov     rsi, [rsp+88h+var_48]
0x1800758a9  test    rsi, rsi
0x1800758ac  jz      loc_180075B18
0x1800758b2  mov     rax, cs:__imp_gCookie
0x1800758b9  lea     ecx, [rbx+40h]
0x1800758bc  mov     rdx, [rax]
0x1800758bf  mov     eax, edx
0x1800758c1  and     eax, 3Fh
0x1800758c4  sub     ecx, eax
0x1800758c6  ror     rsi, cl
0x1800758c9  xor     rsi, rdx
0x1800758cc  jz      loc_180075B18
0x1800758d2  mov     rax, [rsi+8]
0x1800758d6  test    rax, rax
0x1800758d9  jz      loc_180075B18
0x1800758df  test    byte ptr [rsi], 1
0x1800758e2  jnz     loc_180075B18
0x1800758e8  mov     rbx, [rax]
0x1800758eb  jmp     short loc_18007591C
0x1800758ed  cmp     qword ptr [rbx+28h], 0
0x1800758f2  jnz     short loc_1800758F9
0x1800758f4  test    byte ptr [rdi], 2
0x1800758f7  jnz     short loc_1800758FF
0x1800758f9  cmp     [rbx+28h], r12
0x1800758fd  jnz     short loc_180075919
0x1800758ff  movss   xmm0, dword ptr [rbx+30h]
0x180075904  ucomiss xmm0, dword ptr [rdi+20h]
0x180075908  jp      short loc_180075919
0x18007590a  jnz     short loc_180075919
0x18007590c  movss   xmm0, dword ptr [rbx+34h]
0x180075911  ucomiss xmm0, dword ptr [rdi+2Ch]
0x180075915  jp      short loc_180075919
0x180075917  jz      short loc_18007597B
0x180075919  mov     rbx, [rbx]
0x18007591c  test    rbx, rbx
0x18007591f  jnz     short loc_1800758ED
0x180075921  mov     eax, [rsp+88h+arg_30]
0x180075928  mov     r8d, r14d; unsigned int
0x18007592b  mov     r9, [rsp+88h+arg_20]; void *
0x180075933  mov     rdx, rdi; struct _DC_ATTR *
0x180075936  mov     [rsp+88h+var_60], eax; int
0x18007593a  mov     rcx, r12; HDC
0x18007593d  mov     eax, [rsp+88h+arg_28]
0x180075944  mov     [rsp+88h+var_68], eax; unsigned int
0x180075948  call    ?pcfCreateCFONT@@YAPEAU_CFONT@@PEAUHDC__@@PEAU_DC_ATTR@@IPEAXIH@Z; pcfCreateCFONT(HDC__ *,_DC_ATTR *,uint,void *,uint,int)
0x18007594d  mov     rbx, rax
0x180075950  test    rax, rax
0x180075953  jz      loc_180075B1F
0x180075959  mov     [rax+10h], r15
0x18007595d  test    byte ptr [rdi], 2
0x180075960  jz      loc_180075AEF
0x180075966  mov     qword ptr [rax+28h], 0
0x18007596e  mov     qword ptr [rax+8], 0
0x180075976  jmp     loc_180075B05
0x18007597b  inc     dword ptr [rbx+18h]
0x18007597e  test    byte ptr [rbx+1Ch], 1
0x180075982  jz      short loc_18007598C
0x180075984  mov     rdx, rbx
0x180075987  jmp     loc_180075805
0x18007598c  mov     eax, [rbx+1Ch]
0x18007598f  mov     r8, [rsp+88h+arg_20]; void *
0x180075997  and     eax, 20h
0x18007599a  test    r8, r8
0x18007599d  jz      loc_180075A92
0x1800759a3  mov     r10d, [rsp+88h+arg_30]
0x1800759ab  test    eax, eax
0x1800759ad  jz      loc_180075A6F
0x1800759b3  test    r10d, r10d
0x1800759b6  jz      loc_180075A42
0x1800759bc  test    byte ptr [rbx+1Ch], 4
0x1800759c0  jz      short loc_180075A16
0x1800759c2  mov     ecx, [rsp+88h+arg_28]
0x1800759c9  test    ecx, ecx
0x1800759cb  jle     short loc_180075A0B
0x1800759cd  mov     r9, cs:gpwcDBCSCharSet
0x1800759d4  mov     edx, 0FFFFh
0x1800759d9  movzx   eax, byte ptr [r8]
0x1800759dd  cmp     [r9+rax*2], dx
0x1800759e2  jnz     short loc_1800759FB
0x1800759e4  test    ecx, ecx
0x1800759e6  lea     rax, [r8+1]
0x1800759ea  cmovz   rax, r8
0x1800759ee  mov     r8, rax
0x1800759f1  lea     eax, [rcx-1]
0x1800759f4  cmovz   eax, ecx
0x1800759f7  mov     ecx, eax
0x1800759f9  jmp     short loc_180075A02
0x1800759fb  cmp     [rbx+rax*2+54h], dx
0x180075a00  jz      short loc_180075A0B
0x180075a02  dec     ecx
0x180075a04  inc     r8
0x180075a07  test    ecx, ecx
0x180075a09  jg      short loc_1800759D9
0x180075a0b  xor     r9d, r9d
0x180075a0e  test    ecx, ecx
0x180075a10  cmovns  r9d, ecx
0x180075a14  jmp     short loc_180075A77
0x180075a16  mov     r9d, [rsp+88h+arg_28]
0x180075a1e  test    r9d, r9d
0x180075a21  jz      loc_180075B1F
0x180075a27  mov     edx, 0FFFFh
0x180075a2c  movzx   eax, byte ptr [r8]
0x180075a30  cmp     [rbx+rax*2+54h], dx
0x180075a35  jz      short loc_180075A77
0x180075a37  inc     r8
0x180075a3a  add     r9d, 0FFFFFFFFh
0x180075a3e  jnz     short loc_180075A2C
0x180075a40  jmp     short loc_180075A77
0x180075a42  mov     r9d, [rsp+88h+arg_28]
0x180075a4a  test    r9d, r9d
0x180075a4d  jz      loc_180075B1F
0x180075a53  mov     edx, 0FFFFh
0x180075a58  movzx   eax, word ptr [r8]
0x180075a5c  cmp     [rbx+rax*2+54h], dx
0x180075a61  jz      short loc_180075A77
0x180075a63  add     r8, 2
0x180075a67  add     r9d, 0FFFFFFFFh
0x180075a6b  jnz     short loc_180075A58
0x180075a6d  jmp     short loc_180075A77
0x180075a6f  mov     r9d, [rsp+88h+arg_28]; unsigned int
0x180075a77  test    r9d, r9d
0x180075a7a  jz      loc_180075B1F
0x180075a80  mov     rdx, rbx; struct _CFONT *
0x180075a83  mov     [rsp+88h+var_68], r10d; int
0x180075a88  mov     rcx, r12; HDC
0x180075a8b  call    ?bFillWidthTableForGTE@@YAHPEAUHDC__@@PEAU_CFONT@@PEAXIH@Z; bFillWidthTableForGTE(HDC__ *,_CFONT *,void *,uint,int)
0x180075a90  jmp     short loc_180075ADC
0x180075a92  mov     r9d, [rsp+88h+arg_28]
0x180075a9a  test    eax, eax
0x180075a9c  jz      short loc_180075AC9
0x180075a9e  lea     eax, [r14+r9]
0x180075aa2  or      eax, r14d
0x180075aa5  test    eax, 0FFFFFF00h
0x180075aaa  jnz     short loc_180075AC9
0x180075aac  test    r9d, r9d
0x180075aaf  jz      short loc_180075B1F
0x180075ab1  mov     edx, 0FFFFh
0x180075ab6  mov     eax, r14d
0x180075ab9  cmp     [rbx+rax*2+54h], dx
0x180075abe  jz      short loc_180075ACE
0x180075ac0  inc     r14d
0x180075ac3  add     r9d, 0FFFFFFFFh; unsigned int
0x180075ac7  jnz     short loc_180075AB6
0x180075ac9  test    r9d, r9d
0x180075acc  jz      short loc_180075B1F
0x180075ace  mov     r8d, r14d; unsigned int
0x180075ad1  mov     rdx, rbx; struct _CFONT *
0x180075ad4  mov     rcx, r12; HDC
0x180075ad7  call    ?bFillWidthTableForGCW@@YAHPEAUHDC__@@PEAU_CFONT@@II@Z; bFillWidthTableForGCW(HDC__ *,_CFONT *,uint,uint)
0x180075adc  cmp     eax, 0FFFFFFFFh
0x180075adf  jnz     short loc_180075B1F
0x180075ae1  dec     dword ptr [rbx+18h]
0x180075ae4  or      dword ptr [rdi+98h], 20h
0x180075aeb  xor     ebx, ebx
0x180075aed  jmp     short loc_180075B1F
0x180075aef  mov     [rax+28h], r12
0x180075af3  mov     rax, [rdi+160h]
0x180075afa  mov     [rbx+8], rax
0x180075afe  mov     [rdi+160h], rbx
0x180075b05  mov     rax, [rsi+8]
0x180075b09  mov     rcx, [rax]
0x180075b0c  mov     [rbx], rcx
0x180075b0f  mov     rax, [rsi+8]
0x180075b13  mov     [rax], rbx
0x180075b16  jmp     short loc_180075B1F
0x180075b18  or      dword ptr [rdi+98h], 20h
0x180075b1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180075b26  lea     rax, WPP_GLOBAL_Control
0x180075b2d  cmp     rcx, rax
0x180075b30  jz      loc_180075984
0x180075b36  test    byte ptr [rcx+1Ch], 1
0x180075b3a  jz      loc_180075984
0x180075b40  cmp     byte ptr [rcx+19h], 5
0x180075b44  jb      loc_180075984
0x180075b4a  mov     rcx, [rcx+10h]
0x180075b4e  mov     edx, 0Bh
0x180075b53  call    WPP_SF_
0x180075b58  jmp     loc_180075984
```
