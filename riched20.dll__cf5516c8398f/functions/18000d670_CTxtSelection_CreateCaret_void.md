# CTxtSelection::CreateCaret(void)

- ea: `0x18000d670`
- end: `0x18000dd57`
- name: `?CreateCaret@CTxtSelection@@QEAAXXZ`
- size: `1767`
- prototype: `void __fastcall(CTxtSelection *__hidden this)`
- caller_count: `6`
- callee_count: `14`
- tags: ``

## callers

- `0x18000c070`
- `0x18002bfc0`
- `0x180040b64`
- `0x1800492b0`
- `0x18007fc58`
- `0x1800840a0`

## callees

- `0x180008f80`
- `0x18000b440`
- `0x18000d4a0`
- `0x18000d670`
- `0x18000e0b8`
- `0x180033b90`
- `0x180038bd0`
- `0x18003b4b0`
- `0x18003dea4`
- `0x180045f24`
- `0x18007eee0`
- `0x18008f6a0`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000dbe4`
- `KERNEL32!EnterCriticalSection` at `0x18000dbe4`
- `KERNEL32!LeaveCriticalSection` at `0x18000dab9`
- `KERNEL32!LeaveCriticalSection` at `0x18000dab9`
- `GDI32!GetDeviceCaps` at `0x18000dc19`
- `GDI32!GetDeviceCaps` at `0x18000dc19`
- `GDI32!CreateBitmap` at `0x18000dd28`
- `GDI32!CreateBitmap` at `0x18000dd28`

## pseudocode

```c
void __fastcall CTxtSelection::CreateCaret(CTxtSelection *this)
{
  __int64 v1; // rdx
  __int64 v2; // r12
  __int64 *v4; // r14
  int v5; // r8d
  int v6; // eax
  int v7; // esi
  int i; // eax
  int v9; // edi
  BOOL v10; // ebx
  int v11; // ecx
  int v12; // r11d
  int **v13; // r8
  __int64 v14; // rbx
  int v15; // edx
  int v16; // r9d
  int v17; // ecx
  int *v18; // r9
  int v19; // eax
  unsigned int v20; // r10d
  int v21; // r8d
  int v22; // r8d
  __int64 v23; // rdx
  __int64 v24; // r8
  char v25; // cl
  unsigned __int16 v26; // r8
  int v27; // ecx
  int v28; // r9d
  unsigned __int16 v29; // ax
  bool v30; // zf
  __int16 v31; // ax
  unsigned int v32; // esi
  unsigned int v33; // edx
  const struct CCharFormat *CF; // r15
  HDC ScreenDC; // r14
  int ZoomDenominator; // edi
  int ZoomNumerator; // ebx
  int DeviceCaps; // eax
  int v39; // eax
  CCcs *Ccs; // rax
  CCcs *v41; // rbx
  int v42; // r8d
  __int16 v43; // dx
  int v44; // ecx
  unsigned int v45; // edi
  __int64 *v46; // [rsp+50h] [rbp-B0h] BYREF
  int v47; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v48; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v49[3]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v50; // [rsp+88h] [rbp-78h]
  int v51; // [rsp+90h] [rbp-70h]
  __int64 v52; // [rsp+98h] [rbp-68h]
  __int64 v53; // [rsp+A0h] [rbp-60h]
  __int64 v54; // [rsp+A8h] [rbp-58h]
  __int64 v55; // [rsp+B0h] [rbp-50h]
  __int64 v56; // [rsp+B8h] [rbp-48h]
  _DWORD Bits[256]; // [rsp+C0h] [rbp-40h] BYREF

  v1 = (unsigned int)*((__int16 *)this + 48);
  v2 = *((_QWORD *)this + 6);
  v46 = 0;
  if ( (int)v1 < 0 )
    v1 = (unsigned int)*(__int16 *)(v2 + 276);
  if ( (*(int (__fastcall **)(struct IFormatCache *, __int64, __int64 **))(*(_QWORD *)qword_1800A41F0 + 32LL))(
         qword_1800A41F0,
         v1,
         &v46) >= 0 )
  {
    v4 = v46;
  }
  else
  {
    v4 = g_defaultCF;
    v46 = g_defaultCF;
  }
  v5 = *((_DWORD *)this + 33);
  v6 = v5;
  if ( v5 > 512 )
    v6 = 512;
  v7 = 0;
  if ( v6 >= 0 )
    v7 = v6;
  if ( qword_1800A3C60 || qword_1800A3C68 || qword_1800A3CC0 )
  {
LABEL_65:
    v10 = 0;
    if ( (unsigned int)CW32System::IsBiDiLcid((unsigned __int16)CW32System::_hklCurrent) )
    {
      v9 = 3;
    }
    else if ( (v33 & 0x3FF) == 0x1E )
    {
      v9 = 5;
    }
    else
    {
      v9 = 1;
      if ( (unsigned int)CW32System::IsIndicLcid(v33) )
        v9 = 9;
    }
  }
  else
  {
    for ( i = 19; i <= 22; ++i )
    {
      if ( (&CW32System::_hkl)[i] )
        goto LABEL_65;
    }
    v9 = 0;
    v10 = (*(_BYTE *)v4 & 2) != 0 && v5 > 15;
  }
  v11 = *((_DWORD *)this + 22);
  if ( (*(_DWORD *)(v2 + 180) & 0x20000000) == 0 )
  {
    v21 = (v11 == 0) | (16 * (v9 | 0x10)) | (2 * (v10 | (v5 << 15)));
    if ( v21 == *((_DWORD *)this + 46) )
      goto LABEL_40;
    *((_DWORD *)this + 46) = v21;
    CTxtSelection::DeleteCaretBitmap(this, 0);
    if ( !v7 || v7 != *((_DWORD *)this + 33) )
      goto LABEL_40;
    v42 = *((_DWORD *)this + 22);
    if ( v42 )
    {
      v10 = 0;
      v7 = 1;
      v43 = 0;
    }
    else
    {
      if ( v10 )
      {
        v25 = 7;
        if ( 5 * v7 / 16 - 1 < 7 )
          v25 = 5 * v7 / 16 - 1;
        v26 = 1 << v25;
        if ( v7 < 35 )
          v27 = 4;
        else
          v27 = v7 / 7;
        v28 = v7;
        do
        {
          *((_WORD *)Bits + --v28) = v26;
          v29 = v26 >> 1;
          if ( v28 % v27 )
            v29 = v26;
          v26 = v29;
        }
        while ( v28 );
        goto LABEL_96;
      }
      if ( !v9 )
      {
LABEL_40:
        (*(void (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(**(_QWORD **)(v2 + 48) + 88LL))(
          *(_QWORD *)(v2 + 48),
          *((_QWORD *)this + 22),
          1,
          *((unsigned int *)this + 33));
        *((_DWORD *)this + 34) |= 0x100u;
        v22 = *((_QWORD *)this + 22) != 0 ? 2 : 0;
        if ( v10 )
        {
          if ( *((_WORD *)v4 + 3) == 1 )
            v22 = 4;
          v22 += v7 / 16;
        }
        v23 = (unsigned int)(*((_DWORD *)this + 30) - v22);
        v24 = *((unsigned int *)this + 31);
        goto LABEL_42;
      }
      v43 = 32;
    }
    v44 = v7;
    do
      *((_WORD *)Bits + --v44) = v43;
    while ( v44 );
    if ( !v42 && v9 )
    {
      v45 = v9 & 0xFFFFFFFE;
      switch ( v45 )
      {
        case 2u:
          Bits[0] = 6291680;
          break;
        case 4u:
          if ( v7 > 1 )
            *((_WORD *)&Bits[-1] + v7) = 48;
          *((_WORD *)&v56 + v7 + 3) = 56;
          break;
        case 8u:
          Bits[0] = 7340280;
          break;
        default:
          if ( (*(_BYTE *)(v2 + 192) & 1) != 0 )
            Bits[0] = 3145784;
          break;
      }
    }
LABEL_96:
    *((_QWORD *)this + 22) = CreateBitmap(8, v7, 1u, 1u, Bits);
    goto LABEL_40;
  }
  v12 = *((_DWORD *)this + 10);
  v13 = (int **)(v2 + 248);
  v14 = *(_QWORD *)(v2 + 64);
  v46 = 0;
  v48 = 0;
  v50 = 0;
  if ( v11 >= 0 )
    v12 -= v11;
  v52 = v2;
  v51 = 0;
  v49[0] = &CRchTxtPtr::`vftable';
  v49[2] = v2 + 248;
  if ( v2 != -248 && *(_DWORD *)(v2 + 256) )
  {
    v15 = 0;
    v50 = 0;
    if ( v12 )
    {
      v16 = *(_DWORD *)(v2 + 256);
      if ( v16 )
      {
        v17 = v12;
        if ( v12 < 0 )
        {
          v17 = v12;
          v50 = 0;
        }
        else
        {
          if ( v16 <= 0 || (v18 = *v13) == 0 )
            v18 = 0;
          while ( v17 > 0 )
          {
            v19 = *v18;
            HIDWORD(v50) = v17;
            if ( v17 < v19 )
            {
              v17 = 0;
              break;
            }
            v20 = v15;
            v17 -= v19;
            LODWORD(v50) = ++v15;
            if ( v15 >= *(_DWORD *)(v2 + 256) )
            {
              v50 = __PAIR64__(v19, v20);
              break;
            }
            HIDWORD(v50) = 0;
            v18 = (int *)((char *)v18 + *(int *)(v2 + 264));
          }
        }
        v12 -= v17;
      }
    }
    v51 = v12;
  }
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  CRchTxtPtr::InitRunPtrs((CRchTxtPtr *)v49);
  if ( (*(unsigned int (__fastcall **)(__int64, _QWORD *, _QWORD, _QWORD, __int64 **, _QWORD, _DWORD, _QWORD))(*(_QWORD *)v14 + 240LL))(
         v14,
         v49,
         0,
         0,
         &v46,
         0,
         0,
         0) != -1
    && (*(unsigned int (__fastcall **)(__int64, _QWORD *, _QWORD, _QWORD, __int64 *, _QWORD, int, _QWORD))(*(_QWORD *)v14 + 240LL))(
         v14,
         v49,
         0,
         0,
         &v48,
         0,
         10,
         0) != -1 )
  {
    CTxtSelection::DeleteCaretBitmap(this, 1);
    v32 = v48 - (_DWORD)v46;
    if ( (*(_BYTE *)(v2 + 198) & 1) == 0 )
    {
      CF = CRchTxtPtr::GetCF((CRchTxtPtr *)v49);
      EnterCriticalSection(&g_CriticalSection);
      ScreenDC = CW32System::GetScreenDC();
      if ( ScreenDC )
      {
        ZoomDenominator = CDisplay::GetZoomDenominator(*((CDisplay **)this + 13));
        ZoomNumerator = CDisplay::GetZoomNumerator(*((CDisplay **)this + 13));
        DeviceCaps = GetDeviceCaps(ScreenDC, 90);
        v39 = CW32System::MulDiv(DeviceCaps, ZoomNumerator, ZoomDenominator);
        Ccs = CFontCache::GetCcs(qword_1800A3EE0, CF, v39, 0, 0);
        v41 = Ccs;
        if ( Ccs )
        {
          v47 = 0;
          v30 = (unsigned int)CCcs::Include(Ccs, 0xAC00u, &v47) == 0;
          v31 = *((_WORD *)v41 + 5);
          if ( !v30 )
            v32 = v47;
          if ( v31 )
            *((_WORD *)v41 + 5) = v31 - 1;
        }
      }
      LeaveCriticalSection(&g_CriticalSection);
    }
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(v2 + 48) + 88LL))(
      *(_QWORD *)(v2 + 48),
      0,
      v32,
      (unsigned int)(HIDWORD(v48) - HIDWORD(v46)));
    *((_DWORD *)this + 34) |= 0x100u;
    v24 = HIDWORD(v46);
    v23 = (unsigned int)v46;
LABEL_42:
    (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v2 + 48) + 104LL))(*(_QWORD *)(v2 + 48), v23, v24);
  }
}

```

## disassembly

```asm
0x18000d670  push    rbp
0x18000d672  push    rsi
0x18000d673  push    r12
0x18000d675  push    r13
0x18000d677  push    r15
0x18000d679  lea     rbp, [rsp-3D0h]
0x18000d681  sub     rsp, 4D0h
0x18000d688  mov     rax, cs:__security_cookie
0x18000d68f  xor     rax, rsp
0x18000d692  mov     [rbp+3F0h+var_30], rax
0x18000d699  movsx   edx, word ptr [rcx+60h]
0x18000d69d  xor     r15d, r15d
0x18000d6a0  mov     r12, [rcx+30h]
0x18000d6a4  mov     r13, rcx
0x18000d6a7  mov     [rsp+4F0h+var_4A0], r15
0x18000d6ac  test    edx, edx
0x18000d6ae  jns     short loc_18000D6B9
0x18000d6b0  movsx   edx, word ptr [r12+114h]
0x18000d6b9  mov     rcx, cs:qword_1800A41F0
0x18000d6c0  lea     r8, [rsp+4F0h+var_4A0]
0x18000d6c5  mov     [rsp+4F0h+arg_18], r14
0x18000d6cd  mov     rax, [rcx]
0x18000d6d0  mov     rax, [rax+20h]
0x18000d6d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6d9  test    eax, eax
0x18000d6db  jns     loc_18000D8ED
0x18000d6e1  lea     r14, ?g_defaultCF@@3VCCharFormat@@A; CCharFormat g_defaultCF
0x18000d6e8  mov     [rsp+4F0h+var_4A0], r14
0x18000d6ed  mov     r8d, [r13+84h]
0x18000d6f4  mov     ecx, 200h
0x18000d6f9  cmp     r8d, ecx
0x18000d6fc  mov     [rsp+4F0h+arg_8], rbx
0x18000d704  mov     eax, r8d
0x18000d707  mov     [rsp+4F0h+arg_10], rdi
0x18000d70f  cmovg   eax, ecx
0x18000d712  mov     esi, r15d
0x18000d715  test    eax, eax
0x18000d717  cmovns  esi, eax
0x18000d71a  cmp     cs:qword_1800A3C60, r15
0x18000d721  jnz     loc_18000DB0C
0x18000d727  cmp     cs:qword_1800A3C68, r15
0x18000d72e  jnz     loc_18000DB0C
0x18000d734  cmp     cs:qword_1800A3CC0, r15
0x18000d73b  jnz     loc_18000DB0C
0x18000d741  mov     eax, 13h
0x18000d746  lea     rdx, ?_hkl@CW32System@@0PAPEAUHKL__@@A; HKL__ * near * CW32System::_hkl
0x18000d74d  nop     dword ptr [rax]
0x18000d750  cmp     eax, 16h
0x18000d753  jg      short loc_18000D766
0x18000d755  movsxd  rcx, eax
0x18000d758  cmp     [rdx+rcx*8], r15
0x18000d75c  jnz     loc_18000DB0C
0x18000d762  inc     eax
0x18000d764  jmp     short loc_18000D750
0x18000d766  test    byte ptr [r14], 2
0x18000d76a  mov     edi, r15d
0x18000d76d  jnz     loc_18000DAF8
0x18000d773  mov     ebx, r15d
0x18000d776  mov     ecx, [r13+58h]
0x18000d77a  mov     edx, r15d
0x18000d77d  test    ecx, ecx
0x18000d77f  setz    dl
0x18000d782  test    dword ptr [r12+0B4h], 20000000h
0x18000d78e  jz      loc_18000D903
0x18000d794  mov     r11d, [r13+28h]
0x18000d798  lea     r8, [r12+0F8h]
0x18000d7a0  mov     rbx, [r12+40h]
0x18000d7a5  mov     eax, r11d
0x18000d7a8  sub     eax, ecx
0x18000d7aa  mov     [rsp+4F0h+var_4A0], r15
0x18000d7af  test    ecx, ecx
0x18000d7b1  mov     [rsp+4F0h+var_490], r15
0x18000d7b6  mov     [rbp+3F0h+var_468], r15
0x18000d7ba  cmovns  r11d, eax
0x18000d7be  mov     [rbp+3F0h+var_458], r12
0x18000d7c2  mov     [rbp+3F0h+var_460], r15d
0x18000d7c6  lea     rax, ??_7CRchTxtPtr@@6B@; const CRchTxtPtr::`vftable'
0x18000d7cd  mov     [rsp+4F0h+var_480], rax
0x18000d7d2  mov     [rbp+3F0h+var_470], r8
0x18000d7d6  test    r8, r8
0x18000d7d9  jz      loc_18000D85D
0x18000d7df  cmp     [r8+8], r15d
0x18000d7e3  jz      short loc_18000D85D
0x18000d7e5  mov     edx, r15d
0x18000d7e8  mov     eax, r15d
0x18000d7eb  mov     dword ptr [rbp+3F0h+var_468], edx
0x18000d7ee  mov     dword ptr [rbp+3F0h+var_468+4], eax
0x18000d7f1  test    r11d, r11d
0x18000d7f4  jz      short loc_18000D859
0x18000d7f6  mov     r9d, [r8+8]
0x18000d7fa  test    r9d, r9d
0x18000d7fd  jz      short loc_18000D859
0x18000d7ff  mov     ecx, r11d
0x18000d802  test    r11d, r11d
0x18000d805  js      loc_18000D998
0x18000d80b  test    r9d, r9d
0x18000d80e  jle     loc_18000D9EE
0x18000d814  mov     r9, [r8]
0x18000d817  test    r9, r9
0x18000d81a  jz      loc_18000D9EE
0x18000d820  test    ecx, ecx
0x18000d822  jle     short loc_18000D856
0x18000d824  mov     eax, [r9]
0x18000d827  mov     dword ptr [rbp+3F0h+var_468+4], ecx
0x18000d82a  cmp     ecx, eax
0x18000d82c  jl      short loc_18000D853
0x18000d82e  mov     r10d, edx
0x18000d831  sub     ecx, eax
0x18000d833  inc     edx
0x18000d835  mov     dword ptr [rbp+3F0h+var_468], edx
0x18000d838  cmp     edx, [r8+8]
0x18000d83c  jge     loc_18000D8F7
0x18000d842  mov     dword ptr [rbp+3F0h+var_468+4], r15d
0x18000d846  movsxd  rax, dword ptr [r8+10h]
0x18000d84a  add     r9, rax
0x18000d84d  jmp     short loc_18000D820
0x18000d84f  mov     dword ptr [rbp+3F0h+var_468+4], r9d
0x18000d853  mov     ecx, r15d
0x18000d856  sub     r11d, ecx
0x18000d859  mov     [rbp+3F0h+var_460], r11d
0x18000d85d  lea     rcx, [rsp+4F0h+var_480]; this
0x18000d862  mov     [rbp+3F0h+var_450], r15
0x18000d866  mov     [rbp+3F0h+var_448], r15
0x18000d86a  mov     [rbp+3F0h+var_440], r15
0x18000d86e  mov     [rbp+3F0h+var_438], r15
0x18000d872  call    ?InitRunPtrs@CRchTxtPtr@@IEAAXXZ; CRchTxtPtr::InitRunPtrs(void)
0x18000d877  mov     rax, [rbx]
0x18000d87a  lea     rcx, [rsp+4F0h+var_4A0]
0x18000d87f  mov     [rsp+4F0h+var_4B8], r15
0x18000d884  lea     rdx, [rsp+4F0h+var_480]
0x18000d889  mov     [rsp+4F0h+var_4C0], r15d
0x18000d88e  xor     r9d, r9d
0x18000d891  mov     [rsp+4F0h+var_4C8], r15
0x18000d896  xor     r8d, r8d
0x18000d899  mov     rax, [rax+0F0h]
0x18000d8a0  mov     [rsp+4F0h+lpBits], rcx
0x18000d8a5  mov     rcx, rbx
0x18000d8a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8ad  cmp     eax, 0FFFFFFFFh
0x18000d8b0  jnz     loc_18000DB6A
0x18000d8b6  mov     r14, [rsp+4F0h+arg_18]
0x18000d8be  mov     rdi, [rsp+4F0h+arg_10]
0x18000d8c6  mov     rbx, [rsp+4F0h+arg_8]
0x18000d8ce  mov     rcx, [rbp+3F0h+var_30]
0x18000d8d5  xor     rcx, rsp; StackCookie
0x18000d8d8  call    __security_check_cookie
0x18000d8dd  add     rsp, 4D0h
0x18000d8e4  pop     r15
0x18000d8e6  pop     r13
0x18000d8e8  pop     r12
0x18000d8ea  pop     rsi
0x18000d8eb  pop     rbp
0x18000d8ec  retn
0x18000d8ed  mov     r14, [rsp+4F0h+var_4A0]
0x18000d8f2  jmp     loc_18000D6ED
0x18000d8f7  mov     dword ptr [rbp+3F0h+var_468], r10d
0x18000d8fb  mov     dword ptr [rbp+3F0h+var_468+4], eax
0x18000d8fe  jmp     loc_18000D856
0x18000d903  shl     r8d, 0Fh
0x18000d907  mov     eax, edi
0x18000d909  or      r8d, ebx
0x18000d90c  or      eax, 10h
0x18000d90f  add     r8d, r8d
0x18000d912  shl     eax, 4
0x18000d915  or      r8d, eax
0x18000d918  mov     r15d, 4
0x18000d91e  or      r8d, edx
0x18000d921  cmp     r8d, [r13+0B8h]
0x18000d928  jnz     loc_18000DC59
0x18000d92e  mov     rcx, [r12+30h]
0x18000d933  mov     r8d, 1
0x18000d939  mov     r9d, [r13+84h]
0x18000d940  mov     rdx, [r13+0B0h]
0x18000d947  mov     rax, [rcx]
0x18000d94a  mov     rax, [rax+58h]
0x18000d94e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d953  or      dword ptr [r13+88h], 100h
0x18000d95e  mov     rcx, [r13+0B0h]
0x18000d965  neg     rcx
0x18000d968  sbb     r8d, r8d
0x18000d96b  and     r8d, 2
0x18000d96f  test    ebx, ebx
0x18000d971  jnz     loc_18000DD3A
0x18000d977  mov     edx, [r13+78h]
0x18000d97b  sub     edx, r8d
0x18000d97e  mov     r8d, [r13+7Ch]
0x18000d982  mov     rcx, [r12+30h]
0x18000d987  mov     rax, [rcx]
0x18000d98a  mov     rax, [rax+68h]
0x18000d98e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d993  jmp     loc_18000D8B6
0x18000d998  test    ecx, ecx
0x18000d99a  jns     loc_18000D856
0x18000d9a0  lea     r9d, [rax+rcx]
0x18000d9a4  neg     ecx
0x18000d9a6  cmp     ecx, eax
0x18000d9a8  jle     loc_18000D84F
0x18000d9ae  mov     ecx, r9d
0x18000d9b1  test    edx, edx
0x18000d9b3  jle     loc_18000DB61
0x18000d9b9  dec     edx
0x18000d9bb  mov     dword ptr [rbp+3F0h+var_468], edx
0x18000d9be  mov     eax, [r8+8]
0x18000d9c2  test    eax, eax
0x18000d9c4  jle     short loc_18000D9E9
0x18000d9c6  cmp     edx, eax
0x18000d9c8  jge     short loc_18000D9E9
0x18000d9ca  mov     r9, [r8]
0x18000d9cd  test    r9, r9
0x18000d9d0  jz      short loc_18000D9E9
0x18000d9d2  test    edx, edx
0x18000d9d4  js      short loc_18000D9E9
0x18000d9d6  mov     eax, edx
0x18000d9d8  imul    eax, [r8+10h]
0x18000d9dd  cdqe
0x18000d9df  add     rax, r9
0x18000d9e2  mov     eax, [rax]
0x18000d9e4  mov     dword ptr [rbp+3F0h+var_468+4], eax
0x18000d9e7  jmp     short loc_18000D998
0x18000d9e9  mov     rax, r15
0x18000d9ec  jmp     short loc_18000D9E2
0x18000d9ee  mov     r9, r15
0x18000d9f1  jmp     loc_18000D820
0x18000d9f6  mov     ecx, 7
0x18000d9fb  lea     eax, [rsi+rsi*4]
0x18000d9fe  cdq
0x18000d9ff  mov     r8d, 1
0x18000da05  and     edx, 0Fh
0x18000da08  add     eax, edx
0x18000da0a  sar     eax, 4
0x18000da0d  dec     eax
0x18000da0f  cmp     eax, ecx
0x18000da11  cmovl   ecx, eax
0x18000da14  shl     r8w, cl
0x18000da18  cmp     esi, 23h ; '#'
0x18000da1b  jl      short loc_18000DA62
0x18000da1d  mov     eax, 92492493h
0x18000da22  imul    esi
0x18000da24  lea     ecx, [rsi+rdx]
0x18000da27  sar     ecx, 2
0x18000da2a  mov     eax, ecx
0x18000da2c  shr     eax, 1Fh
0x18000da2f  add     ecx, eax
0x18000da31  mov     r9d, esi
0x18000da34  dec     r9d
0x18000da37  movsxd  rax, r9d
0x18000da3a  mov     word ptr [rbp+rax*2+3F0h+Bits], r8w
0x18000da40  mov     eax, r9d
0x18000da43  cdq
0x18000da44  idiv    ecx
0x18000da46  movzx   eax, r8w
0x18000da4a  shr     ax, 1
0x18000da4d  test    edx, edx
0x18000da4f  cmovnz  ax, r8w
0x18000da54  movzx   r8d, ax
0x18000da58  test    r9d, r9d
0x18000da5b  jnz     short loc_18000DA34
0x18000da5d  jmp     loc_18000DD0F
0x18000da62  mov     ecx, r15d
0x18000da65  jmp     short loc_18000DA31
0x18000da67  test    byte ptr [r12+0C0h], 1
0x18000da70  jz      loc_18000DD0F
0x18000da76  mov     [rbp+3F0h+Bits], 300038h
0x18000da7d  jmp     loc_18000DD0F
0x18000da82  lea     r8, [rsp+4F0h+var_498]; int *
0x18000da87  mov     [rsp+4F0h+var_498], 0
0x18000da8f  mov     dx, 0AC00h; unsigned __int16
0x18000da93  mov     rcx, rbx; this
0x18000da96  call    ?Include@CCcs@@QEAAHGAEAJ@Z; CCcs::Include(ushort,long &)
0x18000da9b  test    eax, eax
0x18000da9d  movzx   eax, word ptr [rbx+0Ah]
0x18000daa1  cmovnz  esi, [rsp+4F0h+var_498]
0x18000daa6  test    ax, ax
0x18000daa9  jz      short loc_18000DAB2
0x18000daab  dec     ax
0x18000daae  mov     [rbx+0Ah], ax
0x18000dab2  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000dab9  call    cs:__imp_LeaveCriticalSection
0x18000dabf  mov     rcx, [r12+30h]
0x18000dac4  mov     r8d, esi
0x18000dac7  mov     r9d, dword ptr [rsp+4F0h+var_490+4]
0x18000dacc  xor     edx, edx
0x18000dace  sub     r9d, dword ptr [rsp+4F0h+var_4A0+4]
0x18000dad3  mov     rax, [rcx]
0x18000dad6  mov     rax, [rax+58h]
0x18000dada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dadf  or      dword ptr [r13+88h], 100h
0x18000daea  mov     r8d, dword ptr [rsp+4F0h+var_4A0+4]
0x18000daef  mov     edx, dword ptr [rsp+4F0h+var_4A0]
0x18000daf3  jmp     loc_18000D982
0x18000daf8  cmp     r8d, 0Fh
0x18000dafc  jle     loc_18000D773
0x18000db02  mov     ebx, 1
0x18000db07  jmp     loc_18000D776
0x18000db0c  movzx   edx, word ptr cs:?_hklCurrent@CW32System@@0PEAUHKL__@@EA; HKL__ * CW32System::_hklCurrent
0x18000db13  mov     ebx, r15d
0x18000db16  mov     ecx, edx; unsigned int
0x18000db18  call    ?IsBiDiLcid@CW32System@@SAHK@Z; CW32System::IsBiDiLcid(ulong)
0x18000db1d  test    eax, eax
0x18000db1f  jz      short loc_18000DB2B
  ... truncated ...
```
