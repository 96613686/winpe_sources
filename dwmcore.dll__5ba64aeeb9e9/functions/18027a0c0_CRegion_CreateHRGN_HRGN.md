# CRegion::CreateHRGN(HRGN__ * *)

- ea: `0x18027a0c0`
- end: `0x18027a2f9`
- name: `?CreateHRGN@CRegion@@QEBAJPEAPEAUHRGN__@@@Z`
- size: `569`
- prototype: `__int64 __fastcall(CRegion *__hidden this, HRGN *)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18028b800`
- `0x18028b980`

## callees

- `0x18001c5b0`
- `0x18001c5e8`
- `0x18001d9d0`
- `0x180050270`
- `0x1800516b0`
- `0x1800562d8`
- `0x18016dd20`
- `0x1802284b0`
- `0x18022945c`
- `0x18027a0c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18027a11c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18027a253`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18027a11c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18027a253`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18027a139`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18027a281`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18027a139`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18027a281`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!ExtCreateRegion` at `0x18027a261`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!ExtCreateRegion` at `0x18027a261`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CreateRectRgnIndirect` at `0x18027a127`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!CreateRectRgnIndirect` at `0x18027a127`

## pseudocode

```c
__int64 __fastcall CRegion::CreateHRGN(CRegion *this, HRGN *a2)
{
  unsigned int RectangleCount; // eax
  unsigned int v5; // esi
  HRGN Region; // rsi
  signed int v7; // eax
  signed int v8; // ebx
  int v9; // r14d
  DWORD v10; // r12d
  RGNDATA *p_Data; // rbx
  char *Buffer; // rsi
  _DWORD *v13; // rcx
  int v14; // eax
  FastRegion::Internal::CRgnData *v15; // rcx
  __int64 v16; // rdx
  signed int LastError; // eax
  _BYTE v19[8]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v20; // [rsp+38h] [rbp-C8h]
  _DWORD *v21; // [rsp+40h] [rbp-C0h]
  FastRegion::Internal::CRgnData *v22; // [rsp+48h] [rbp-B8h]
  int v23; // [rsp+50h] [rbp-B0h]
  RECT rect; // [rsp+60h] [rbp-A0h] BYREF
  RGNDATA Data; // [rsp+70h] [rbp-90h] BYREF

  RectangleCount = FastRegion::CRegion::GetRectangleCount(this);
  v5 = RectangleCount;
  if ( RectangleCount > 1 )
  {
    *(_QWORD *)&rect.left = 0;
    v9 = 16 * RectangleCount;
    v10 = 16 * RectangleCount + 32;
    memset_0(&Data, 0, 0x120u);
    if ( v5 > 0x10 )
    {
      *(_QWORD *)&rect.left = MIDL_user_allocate(v10);
      p_Data = *(RGNDATA **)&rect.left;
      if ( !*(_QWORD *)&rect.left )
      {
        v8 = -2147024882;
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024882, 0x61u, 0);
        goto LABEL_23;
      }
    }
    else
    {
      p_Data = &Data;
    }
    *(_QWORD *)&p_Data->rdh.rcBound.left = 0;
    *(_QWORD *)&p_Data->rdh.rcBound.right = 0;
    p_Data->rdh.nCount = v5;
    Buffer = p_Data->Buffer;
    p_Data->rdh.dwSize = 32;
    p_Data->rdh.iType = 1;
    p_Data->rdh.nRgnSize = v9;
    FastRegion::CRegion::BeginIterator(this, v19);
    while ( 1 )
    {
      v13 = v21;
      if ( (unsigned __int64)v21 >= v20 )
        break;
      *((_DWORD *)Buffer + 1) = *v21;
      v14 = v13[2];
      v15 = v22;
      *((_DWORD *)Buffer + 3) = v14;
      v16 = 2 * v23;
      *(_DWORD *)Buffer = *((_DWORD *)v15 + v16);
      *((_DWORD *)Buffer + 2) = *((_DWORD *)v15 + v16 + 1);
      Buffer += 16;
      FastRegion::Internal::CRgnData::StepIterator(v15, (struct FastRegion::CRegion::Iterator *)v19);
    }
    SetLastError(0);
    Region = ExtCreateRegion(0, v10, p_Data);
    if ( Region )
    {
      std::unique_ptr<detail::aligned_storage_for<EffectInput> [0],std::default_delete<detail::aligned_storage_for<EffectInput> [0]>>::~unique_ptr<detail::aligned_storage_for<EffectInput> [0],std::default_delete<detail::aligned_storage_for<EffectInput> [0]>>(&rect);
      goto LABEL_17;
    }
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 >= 0 )
      v8 = -2003304445;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v8, 0x7Du, 0);
LABEL_23:
    std::unique_ptr<detail::aligned_storage_for<EffectInput> [0],std::default_delete<detail::aligned_storage_for<EffectInput> [0]>>::~unique_ptr<detail::aligned_storage_for<EffectInput> [0],std::default_delete<detail::aligned_storage_for<EffectInput> [0]>>(&rect);
    return (unsigned int)v8;
  }
  rect = 0;
  FastRegion::CRegion::GetBoundingRect(this, &rect);
  SetLastError(0);
  Region = CreateRectRgnIndirect(&rect);
  if ( Region )
  {
LABEL_17:
    v8 = 0;
    *a2 = Region;
    return (unsigned int)v8;
  }
  v7 = GetLastError();
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( v8 >= 0 )
    v8 = -2003304445;
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v8, 0x4Cu, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18027a0c0  mov     [rsp-8+arg_10], rbx
0x18027a0c5  mov     [rsp-8+arg_18], rsi
0x18027a0ca  push    rbp
0x18027a0cb  push    r12
0x18027a0cd  push    r13
0x18027a0cf  push    r14
0x18027a0d1  push    r15
0x18027a0d3  lea     rbp, [rsp-0A0h]
0x18027a0db  sub     rsp, 1A0h
0x18027a0e2  mov     rax, cs:__security_cookie
0x18027a0e9  xor     rax, rsp
0x18027a0ec  mov     [rbp+0C0h+var_30], rax
0x18027a0f3  mov     r13, rdx
0x18027a0f6  mov     r15, rcx
0x18027a0f9  call    ?GetRectangleCount@CRegion@FastRegion@@QEBAIXZ; FastRegion::CRegion::GetRectangleCount(void)
0x18027a0fe  mov     esi, eax
0x18027a100  cmp     eax, 1
0x18027a103  ja      short loc_18027A17E
0x18027a105  xorps   xmm0, xmm0
0x18027a108  lea     rdx, [rsp+1C0h+rect]; struct tagRECT *
0x18027a10d  mov     rcx, r15; this
0x18027a110  movups  xmmword ptr [rsp+1C0h+rect.left], xmm0
0x18027a115  call    ?GetBoundingRect@CRegion@FastRegion@@QEBA_NAEAUtagRECT@@@Z; FastRegion::CRegion::GetBoundingRect(tagRECT &)
0x18027a11a  xor     ecx, ecx; dwErrCode
0x18027a11c  call    cs:__imp_SetLastError
0x18027a122  lea     rcx, [rsp+1C0h+rect]; lprect
0x18027a127  call    cs:__imp_CreateRectRgnIndirect
0x18027a12d  mov     rsi, rax
0x18027a130  test    rax, rax
0x18027a133  jnz     loc_18027A279
0x18027a139  call    cs:__imp_GetLastError
0x18027a13f  mov     ebx, eax
0x18027a141  test    eax, eax
0x18027a143  jle     short loc_18027A14E
0x18027a145  movzx   ebx, ax
0x18027a148  or      ebx, 80070000h
0x18027a14e  test    ebx, ebx
0x18027a150  mov     [rsp+1C0h+var_198], 0; void *
0x18027a159  mov     eax, 88980003h
0x18027a15e  mov     [rsp+1C0h+var_1A0], 4Ch ; 'L'; unsigned int
0x18027a166  cmovns  ebx, eax
0x18027a169  xor     edx, edx; int *
0x18027a16b  mov     r9d, ebx; int
0x18027a16e  xor     r8d, r8d; unsigned int
0x18027a171  lea     ecx, [rdx+14h]; unsigned int
0x18027a174  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18027a179  jmp     loc_18027A2CB
0x18027a17e  mov     r14d, esi
0x18027a181  mov     qword ptr [rsp+1C0h+rect.left], 0
0x18027a18a  shl     r14d, 4
0x18027a18e  lea     rcx, [rsp+1C0h+Data]; void *
0x18027a193  xor     edx, edx; Val
0x18027a195  mov     r8d, 120h; Size
0x18027a19b  lea     r12d, [r14+20h]
0x18027a19f  call    memset_0
0x18027a1a4  cmp     esi, 10h
0x18027a1a7  ja      short loc_18027A224
0x18027a1a9  lea     rbx, [rsp+1C0h+Data]
0x18027a1ae  mov     qword ptr [rbx+10h], 0
0x18027a1b6  lea     rdx, [rsp+1C0h+var_190]
0x18027a1bb  mov     qword ptr [rbx+18h], 0
0x18027a1c3  mov     rcx, r15
0x18027a1c6  mov     [rbx+8], esi
0x18027a1c9  lea     rsi, [rbx+20h]
0x18027a1cd  mov     dword ptr [rbx], 20h ; ' '
0x18027a1d3  mov     dword ptr [rbx+4], 1
0x18027a1da  mov     [rbx+0Ch], r14d
0x18027a1de  call    ?BeginIterator@CRegion@FastRegion@@QEBA?AVIterator@12@XZ; FastRegion::CRegion::BeginIterator(void)
0x18027a1e3  mov     rcx, [rsp+1C0h+var_180]
0x18027a1e8  cmp     rcx, [rsp+1C0h+var_188]
0x18027a1ed  jnb     short loc_18027A251
0x18027a1ef  mov     eax, [rcx]
0x18027a1f1  mov     [rsi+4], eax
0x18027a1f4  mov     eax, [rcx+8]
0x18027a1f7  mov     rcx, [rsp+1C0h+var_178]; this
0x18027a1fc  mov     [rsi+0Ch], eax
0x18027a1ff  mov     eax, [rsp+1C0h+var_170]
0x18027a203  add     eax, eax
0x18027a205  movsxd  rdx, eax
0x18027a208  mov     eax, [rcx+rdx*4]
0x18027a20b  mov     [rsi], eax
0x18027a20d  mov     eax, [rcx+rdx*4+4]
0x18027a211  lea     rdx, [rsp+1C0h+var_190]; struct FastRegion::CRegion::Iterator *
0x18027a216  mov     [rsi+8], eax
0x18027a219  add     rsi, 10h
0x18027a21d  call    ?StepIterator@CRgnData@Internal@FastRegion@@QEBAXPEAVIterator@CRegion@3@@Z; FastRegion::Internal::CRgnData::StepIterator(FastRegion::CRegion::Iterator *)
0x18027a222  jmp     short loc_18027A1E3
0x18027a224  mov     ecx, r12d; size
0x18027a227  call    MIDL_user_allocate
0x18027a22c  mov     qword ptr [rsp+1C0h+rect.left], rax
0x18027a231  mov     rbx, rax
0x18027a234  test    rax, rax
0x18027a237  jnz     loc_18027A1AE
0x18027a23d  mov     [rsp+1C0h+var_198], rax
0x18027a242  mov     ebx, 8007000Eh
0x18027a247  mov     [rsp+1C0h+var_1A0], 61h ; 'a'
0x18027a24f  jmp     short loc_18027A2B1
0x18027a251  xor     ecx, ecx; dwErrCode
0x18027a253  call    cs:__imp_SetLastError
0x18027a259  mov     r8, rbx; lpData
0x18027a25c  mov     edx, r12d; nCount
0x18027a25f  xor     ecx, ecx; lpx
0x18027a261  call    cs:__imp_ExtCreateRegion
0x18027a267  mov     rsi, rax
0x18027a26a  test    rax, rax
0x18027a26d  jz      short loc_18027A281
0x18027a26f  lea     rcx, [rsp+1C0h+rect]
0x18027a274  call    ??1?$unique_ptr@$$BY0A@U?$aligned_storage_for@UEffectInput@@@detail@@U?$default_delete@$$BY0A@U?$aligned_storage_for@UEffectInput@@@detail@@@std@@@std@@QEAA@XZ; std::unique_ptr<detail::aligned_storage_for<EffectInput> [0],std::default_delete<detail::aligned_storage_for<EffectInput> [0]>>::~unique_ptr<detail::aligned_storage_for<EffectInput> [0],std::default_delete<detail::aligned_storage_for<EffectInput> [0]>>(void)
0x18027a279  xor     ebx, ebx
0x18027a27b  mov     [r13+0], rsi
0x18027a27f  jmp     short loc_18027A2CB
0x18027a281  call    cs:__imp_GetLastError
0x18027a287  mov     ebx, eax
0x18027a289  test    eax, eax
0x18027a28b  jle     short loc_18027A296
0x18027a28d  movzx   ebx, ax
0x18027a290  or      ebx, 80070000h
0x18027a296  test    ebx, ebx
0x18027a298  mov     [rsp+1C0h+var_198], 0; void *
0x18027a2a1  mov     eax, 88980003h
0x18027a2a6  mov     [rsp+1C0h+var_1A0], 7Dh ; '}'; unsigned int
0x18027a2ae  cmovns  ebx, eax
0x18027a2b1  xor     edx, edx; int *
0x18027a2b3  mov     r9d, ebx; int
0x18027a2b6  xor     r8d, r8d; unsigned int
0x18027a2b9  lea     ecx, [rdx+14h]; unsigned int
0x18027a2bc  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18027a2c1  lea     rcx, [rsp+1C0h+rect]
0x18027a2c6  call    ??1?$unique_ptr@$$BY0A@U?$aligned_storage_for@UEffectInput@@@detail@@U?$default_delete@$$BY0A@U?$aligned_storage_for@UEffectInput@@@detail@@@std@@@std@@QEAA@XZ; std::unique_ptr<detail::aligned_storage_for<EffectInput> [0],std::default_delete<detail::aligned_storage_for<EffectInput> [0]>>::~unique_ptr<detail::aligned_storage_for<EffectInput> [0],std::default_delete<detail::aligned_storage_for<EffectInput> [0]>>(void)
0x18027a2cb  mov     eax, ebx
0x18027a2cd  mov     rcx, [rbp+0C0h+var_30]
0x18027a2d4  xor     rcx, rsp; StackCookie
0x18027a2d7  call    __security_check_cookie
0x18027a2dc  lea     r11, [rsp+1C0h+var_20]
0x18027a2e4  mov     rbx, [r11+40h]
0x18027a2e8  mov     rsi, [r11+48h]
0x18027a2ec  mov     rsp, r11
0x18027a2ef  pop     r15
0x18027a2f1  pop     r14
0x18027a2f3  pop     r13
0x18027a2f5  pop     r12
0x18027a2f7  pop     rbp
0x18027a2f8  retn
```
