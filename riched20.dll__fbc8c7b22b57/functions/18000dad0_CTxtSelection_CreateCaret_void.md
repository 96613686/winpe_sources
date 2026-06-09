# CTxtSelection::CreateCaret(void)

- ea: `0x18000dad0`
- end: `0x18000e1d7`
- name: `?CreateCaret@CTxtSelection@@QEAAXXZ`
- size: `1799`
- prototype: `void __fastcall(CTxtSelection *__hidden this)`
- caller_count: `6`
- callee_count: `14`
- tags: ``

## callers

- `0x18000c840`
- `0x180035230`
- `0x180041604`
- `0x18004a41c`
- `0x1800820e0`
- `0x180086670`

## callees

- `0x180009070`
- `0x18000b5e0`
- `0x18000da20`
- `0x18000dad0`
- `0x18000e538`
- `0x180025bb0`
- `0x180039990`
- `0x18003be60`
- `0x18003ea4c`
- `0x180046cb4`
- `0x180081340`
- `0x180091fb0`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000e052`
- `KERNEL32!EnterCriticalSection` at `0x18000e052`
- `KERNEL32!LeaveCriticalSection` at `0x18000df21`
- `KERNEL32!LeaveCriticalSection` at `0x18000df21`
- `GDI32!GetDeviceCaps` at `0x18000e08d`
- `GDI32!GetDeviceCaps` at `0x18000e08d`
- `GDI32!CreateBitmap` at `0x18000e1a2`
- `GDI32!CreateBitmap` at `0x18000e1a2`

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
  if ( (*(int (__fastcall **)(struct IFormatCache *, __int64, __int64 **))(*(_QWORD *)qword_1800A72D0 + 32LL))(
         qword_1800A72D0,
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
  if ( qword_1800A6D40 || qword_1800A6D48 || qword_1800A6DA0 )
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
        Ccs = CFontCache::GetCcs(qword_1800A6FC0, CF, v39, 0, 0);
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
0x18000dad0  push    rbp
0x18000dad2  push    rsi
0x18000dad3  push    r12
0x18000dad5  push    r13
0x18000dad7  push    r15
0x18000dad9  lea     rbp, [rsp-3D0h]
0x18000dae1  sub     rsp, 4D0h
0x18000dae8  mov     rax, cs:__security_cookie
0x18000daef  xor     rax, rsp
0x18000daf2  mov     [rbp+3F0h+var_30], rax
0x18000daf9  movsx   edx, word ptr [rcx+60h]
0x18000dafd  xor     r15d, r15d
0x18000db00  mov     r12, [rcx+30h]
0x18000db04  mov     r13, rcx
0x18000db07  mov     [rsp+4F0h+var_4A0], r15
0x18000db0c  test    edx, edx
0x18000db0e  jns     short loc_18000DB19
0x18000db10  movsx   edx, word ptr [r12+114h]
0x18000db19  mov     rcx, cs:qword_1800A72D0
0x18000db20  lea     r8, [rsp+4F0h+var_4A0]
0x18000db25  mov     [rsp+4F0h+arg_18], r14
0x18000db2d  mov     rax, [rcx]
0x18000db30  mov     rax, [rax+20h]
0x18000db34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db39  test    eax, eax
0x18000db3b  jns     loc_18000DD4E
0x18000db41  lea     r14, ?g_defaultCF@@3VCCharFormat@@A; CCharFormat g_defaultCF
0x18000db48  mov     [rsp+4F0h+var_4A0], r14
0x18000db4d  mov     r8d, [r13+84h]
0x18000db54  mov     ecx, 200h
0x18000db59  cmp     r8d, ecx
0x18000db5c  mov     [rsp+4F0h+arg_8], rbx
0x18000db64  mov     eax, r8d
0x18000db67  mov     [rsp+4F0h+arg_10], rdi
0x18000db6f  cmovg   eax, ecx
0x18000db72  mov     esi, r15d
0x18000db75  test    eax, eax
0x18000db77  cmovns  esi, eax
0x18000db7a  cmp     cs:qword_1800A6D40, r15
0x18000db81  jnz     loc_18000DF7A
0x18000db87  cmp     cs:qword_1800A6D48, r15
0x18000db8e  jnz     loc_18000DF7A
0x18000db94  cmp     cs:qword_1800A6DA0, r15
0x18000db9b  jnz     loc_18000DF7A
0x18000dba1  mov     eax, 13h
0x18000dba6  lea     rdx, ?_hkl@CW32System@@0PAPEAUHKL__@@A; HKL__ * near * CW32System::_hkl
0x18000dbad  nop     dword ptr [rax]
0x18000dbb0  cmp     eax, 16h
0x18000dbb3  jg      short loc_18000DBC6
0x18000dbb5  movsxd  rcx, eax
0x18000dbb8  cmp     [rdx+rcx*8], r15
0x18000dbbc  jnz     loc_18000DF7A
0x18000dbc2  inc     eax
0x18000dbc4  jmp     short loc_18000DBB0
0x18000dbc6  test    byte ptr [r14], 2
0x18000dbca  mov     edi, r15d
0x18000dbcd  jnz     loc_18000DF66
0x18000dbd3  mov     ebx, r15d
0x18000dbd6  mov     ecx, [r13+58h]
0x18000dbda  mov     edx, r15d
0x18000dbdd  test    ecx, ecx
0x18000dbdf  setz    dl
0x18000dbe2  test    dword ptr [r12+0B4h], 20000000h
0x18000dbee  jz      loc_18000DD64
0x18000dbf4  mov     r11d, [r13+28h]
0x18000dbf8  lea     r8, [r12+0F8h]
0x18000dc00  mov     rbx, [r12+40h]
0x18000dc05  mov     eax, r11d
0x18000dc08  sub     eax, ecx
0x18000dc0a  mov     [rsp+4F0h+var_4A0], r15
0x18000dc0f  test    ecx, ecx
0x18000dc11  mov     [rsp+4F0h+var_490], r15
0x18000dc16  mov     [rbp+3F0h+var_468], r15
0x18000dc1a  cmovns  r11d, eax
0x18000dc1e  mov     [rbp+3F0h+var_458], r12
0x18000dc22  mov     [rbp+3F0h+var_460], r15d
0x18000dc26  lea     rax, ??_7CRchTxtPtr@@6B@; const CRchTxtPtr::`vftable'
0x18000dc2d  mov     [rsp+4F0h+var_480], rax
0x18000dc32  mov     [rbp+3F0h+var_470], r8
0x18000dc36  test    r8, r8
0x18000dc39  jz      loc_18000DCBD
0x18000dc3f  cmp     [r8+8], r15d
0x18000dc43  jz      short loc_18000DCBD
0x18000dc45  mov     edx, r15d
0x18000dc48  mov     eax, r15d
0x18000dc4b  mov     dword ptr [rbp+3F0h+var_468], edx
0x18000dc4e  mov     dword ptr [rbp+3F0h+var_468+4], eax
0x18000dc51  test    r11d, r11d
0x18000dc54  jz      short loc_18000DCB9
0x18000dc56  mov     r9d, [r8+8]
0x18000dc5a  test    r9d, r9d
0x18000dc5d  jz      short loc_18000DCB9
0x18000dc5f  mov     ecx, r11d
0x18000dc62  test    r11d, r11d
0x18000dc65  js      loc_18000DE00
0x18000dc6b  test    r9d, r9d
0x18000dc6e  jle     loc_18000DE56
0x18000dc74  mov     r9, [r8]
0x18000dc77  test    r9, r9
0x18000dc7a  jz      loc_18000DE56
0x18000dc80  test    ecx, ecx
0x18000dc82  jle     short loc_18000DCB6
0x18000dc84  mov     eax, [r9]
0x18000dc87  mov     dword ptr [rbp+3F0h+var_468+4], ecx
0x18000dc8a  cmp     ecx, eax
0x18000dc8c  jl      short loc_18000DCB3
0x18000dc8e  mov     r10d, edx
0x18000dc91  sub     ecx, eax
0x18000dc93  inc     edx
0x18000dc95  mov     dword ptr [rbp+3F0h+var_468], edx
0x18000dc98  cmp     edx, [r8+8]
0x18000dc9c  jge     loc_18000DD58
0x18000dca2  mov     dword ptr [rbp+3F0h+var_468+4], r15d
0x18000dca6  movsxd  rax, dword ptr [r8+10h]
0x18000dcaa  add     r9, rax
0x18000dcad  jmp     short loc_18000DC80
0x18000dcaf  mov     dword ptr [rbp+3F0h+var_468+4], r9d
0x18000dcb3  mov     ecx, r15d
0x18000dcb6  sub     r11d, ecx
0x18000dcb9  mov     [rbp+3F0h+var_460], r11d
0x18000dcbd  lea     rcx, [rsp+4F0h+var_480]; this
0x18000dcc2  mov     [rbp+3F0h+var_450], r15
0x18000dcc6  mov     [rbp+3F0h+var_448], r15
0x18000dcca  mov     [rbp+3F0h+var_440], r15
0x18000dcce  mov     [rbp+3F0h+var_438], r15
0x18000dcd2  call    ?InitRunPtrs@CRchTxtPtr@@IEAAXXZ; CRchTxtPtr::InitRunPtrs(void)
0x18000dcd7  mov     rax, [rbx]
0x18000dcda  lea     rcx, [rsp+4F0h+var_4A0]
0x18000dcdf  mov     [rsp+4F0h+var_4B8], r15
0x18000dce4  lea     rdx, [rsp+4F0h+var_480]
0x18000dce9  mov     [rsp+4F0h+var_4C0], r15d
0x18000dcee  xor     r9d, r9d
0x18000dcf1  mov     [rsp+4F0h+var_4C8], r15
0x18000dcf6  xor     r8d, r8d
0x18000dcf9  mov     rax, [rax+0F0h]
0x18000dd00  mov     [rsp+4F0h+lpBits], rcx
0x18000dd05  mov     rcx, rbx
0x18000dd08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd0d  cmp     eax, 0FFFFFFFFh
0x18000dd10  jnz     loc_18000DFD8
0x18000dd16  mov     r14, [rsp+4F0h+arg_18]
0x18000dd1e  mov     rdi, [rsp+4F0h+arg_10]
0x18000dd26  mov     rbx, [rsp+4F0h+arg_8]
0x18000dd2e  mov     rcx, [rbp+3F0h+var_30]
0x18000dd35  xor     rcx, rsp; StackCookie
0x18000dd38  call    __security_check_cookie
0x18000dd3d  add     rsp, 4D0h
0x18000dd44  pop     r15
0x18000dd46  pop     r13
0x18000dd48  pop     r12
0x18000dd4a  pop     rsi
0x18000dd4b  pop     rbp
0x18000dd4c  retn
0x18000dd4e  mov     r14, [rsp+4F0h+var_4A0]
0x18000dd53  jmp     loc_18000DB4D
0x18000dd58  mov     dword ptr [rbp+3F0h+var_468], r10d
0x18000dd5c  mov     dword ptr [rbp+3F0h+var_468+4], eax
0x18000dd5f  jmp     loc_18000DCB6
0x18000dd64  shl     r8d, 0Fh
0x18000dd68  mov     eax, edi
0x18000dd6a  or      r8d, ebx
0x18000dd6d  or      eax, 10h
0x18000dd70  add     r8d, r8d
0x18000dd73  shl     eax, 4
0x18000dd76  or      r8d, eax
0x18000dd79  mov     r15d, 4
0x18000dd7f  or      r8d, edx
0x18000dd82  cmp     r8d, [r13+0B8h]
0x18000dd89  jnz     loc_18000E0D3
0x18000dd8f  mov     rcx, [r12+30h]
0x18000dd94  mov     r8d, 1
0x18000dd9a  mov     r9d, [r13+84h]
0x18000dda1  mov     rdx, [r13+0B0h]
0x18000dda8  mov     rax, [rcx]
0x18000ddab  mov     rax, [rax+58h]
0x18000ddaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddb4  or      dword ptr [r13+88h], 100h
0x18000ddbf  mov     rcx, [r13+0B0h]
0x18000ddc6  neg     rcx
0x18000ddc9  sbb     r8d, r8d
0x18000ddcc  and     r8d, 2
0x18000ddd0  test    ebx, ebx
0x18000ddd2  jnz     loc_18000E1BA
0x18000ddd8  mov     edx, [r13+78h]
0x18000dddc  sub     edx, r8d
0x18000dddf  mov     r8d, [r13+7Ch]
0x18000dde3  mov     rcx, [r12+30h]
0x18000dde8  mov     rax, [rcx]
0x18000ddeb  mov     rax, [rax+68h]
0x18000ddef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddf4  jmp     loc_18000DD16
0x18000de00  test    ecx, ecx
0x18000de02  jns     loc_18000DCB6
0x18000de08  lea     r9d, [rax+rcx]
0x18000de0c  neg     ecx
0x18000de0e  cmp     ecx, eax
0x18000de10  jle     loc_18000DCAF
0x18000de16  mov     ecx, r9d
0x18000de19  test    edx, edx
0x18000de1b  jle     loc_18000DFCF
0x18000de21  dec     edx
0x18000de23  mov     dword ptr [rbp+3F0h+var_468], edx
0x18000de26  mov     eax, [r8+8]
0x18000de2a  test    eax, eax
0x18000de2c  jle     short loc_18000DE51
0x18000de2e  cmp     edx, eax
0x18000de30  jge     short loc_18000DE51
0x18000de32  mov     r9, [r8]
0x18000de35  test    r9, r9
0x18000de38  jz      short loc_18000DE51
0x18000de3a  test    edx, edx
0x18000de3c  js      short loc_18000DE51
0x18000de3e  mov     eax, edx
0x18000de40  imul    eax, [r8+10h]
0x18000de45  cdqe
0x18000de47  add     rax, r9
0x18000de4a  mov     eax, [rax]
0x18000de4c  mov     dword ptr [rbp+3F0h+var_468+4], eax
0x18000de4f  jmp     short loc_18000DE00
0x18000de51  mov     rax, r15
0x18000de54  jmp     short loc_18000DE4A
0x18000de56  mov     r9, r15
0x18000de59  jmp     loc_18000DC80
0x18000de5e  mov     ecx, 7
0x18000de63  lea     eax, [rsi+rsi*4]
0x18000de66  cdq
0x18000de67  mov     r8d, 1
0x18000de6d  and     edx, 0Fh
0x18000de70  add     eax, edx
0x18000de72  sar     eax, 4
0x18000de75  dec     eax
0x18000de77  cmp     eax, ecx
0x18000de79  cmovl   ecx, eax
0x18000de7c  shl     r8w, cl
0x18000de80  cmp     esi, 23h ; '#'
0x18000de83  jl      short loc_18000DECA
0x18000de85  mov     eax, 92492493h
0x18000de8a  imul    esi
0x18000de8c  lea     ecx, [rsi+rdx]
0x18000de8f  sar     ecx, 2
0x18000de92  mov     eax, ecx
0x18000de94  shr     eax, 1Fh
0x18000de97  add     ecx, eax
0x18000de99  mov     r9d, esi
0x18000de9c  dec     r9d
0x18000de9f  movsxd  rax, r9d
0x18000dea2  mov     word ptr [rbp+rax*2+3F0h+Bits], r8w
0x18000dea8  mov     eax, r9d
0x18000deab  cdq
0x18000deac  idiv    ecx
0x18000deae  movzx   eax, r8w
0x18000deb2  shr     ax, 1
0x18000deb5  test    edx, edx
0x18000deb7  cmovnz  ax, r8w
0x18000debc  movzx   r8d, ax
0x18000dec0  test    r9d, r9d
0x18000dec3  jnz     short loc_18000DE9C
0x18000dec5  jmp     loc_18000E189
0x18000deca  mov     ecx, r15d
0x18000decd  jmp     short loc_18000DE99
0x18000decf  test    byte ptr [r12+0C0h], 1
0x18000ded8  jz      loc_18000E189
0x18000dede  mov     [rbp+3F0h+Bits], 300038h
0x18000dee5  jmp     loc_18000E189
0x18000deea  lea     r8, [rsp+4F0h+var_498]; int *
0x18000deef  mov     [rsp+4F0h+var_498], 0
0x18000def7  mov     dx, 0AC00h; unsigned __int16
0x18000defb  mov     rcx, rbx; this
0x18000defe  call    ?Include@CCcs@@QEAAHGAEAJ@Z; CCcs::Include(ushort,long &)
0x18000df03  test    eax, eax
0x18000df05  movzx   eax, word ptr [rbx+0Ah]
0x18000df09  cmovnz  esi, [rsp+4F0h+var_498]
0x18000df0e  test    ax, ax
0x18000df11  jz      short loc_18000DF1A
0x18000df13  dec     ax
0x18000df16  mov     [rbx+0Ah], ax
0x18000df1a  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000df21  call    cs:__imp_LeaveCriticalSection
0x18000df28  nop     dword ptr [rax+rax+00h]
0x18000df2d  mov     rcx, [r12+30h]
0x18000df32  mov     r8d, esi
0x18000df35  mov     r9d, dword ptr [rsp+4F0h+var_490+4]
0x18000df3a  xor     edx, edx
0x18000df3c  sub     r9d, dword ptr [rsp+4F0h+var_4A0+4]
0x18000df41  mov     rax, [rcx]
0x18000df44  mov     rax, [rax+58h]
0x18000df48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df4d  or      dword ptr [r13+88h], 100h
0x18000df58  mov     r8d, dword ptr [rsp+4F0h+var_4A0+4]
0x18000df5d  mov     edx, dword ptr [rsp+4F0h+var_4A0]
0x18000df61  jmp     loc_18000DDE3
0x18000df66  cmp     r8d, 0Fh
0x18000df6a  jle     loc_18000DBD3
0x18000df70  mov     ebx, 1
0x18000df75  jmp     loc_18000DBD6
0x18000df7a  movzx   edx, word ptr cs:?_hklCurrent@CW32System@@0PEAUHKL__@@EA; HKL__ * CW32System::_hklCurrent
0x18000df81  mov     ebx, r15d
0x18000df84  mov     ecx, edx; unsigned int
0x18000df86  call    ?IsBiDiLcid@CW32System@@SAHK@Z; CW32System::IsBiDiLcid(ulong)
0x18000df8b  test    eax, eax
  ... truncated ...
```
