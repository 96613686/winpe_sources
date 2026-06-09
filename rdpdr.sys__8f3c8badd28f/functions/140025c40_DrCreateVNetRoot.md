# DrCreateVNetRoot

- ea: `0x140025c40`
- end: `0x140026375`
- name: `DrCreateVNetRoot`
- size: `1845`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: ``

## callees

- `0x140001660`
- `0x140001890`
- `0x140002ca4`
- `0x140003020`
- `0x14000324c`
- `0x14000327c`
- `0x1400035a0`
- `0x140004afc`
- `0x140004b64`
- `0x140006480`
- `0x140006560`
- `0x1400068c0`
- `0x14001195c`
- `0x140025c40`
- `0x1400268e0`
- `0x140026a48`
- `0x140026c18`
- `0x140026f90`
- `0x140028cc0`
- `0x140028da0`

## import_xrefs

- `ntoskrnl!RtlUnicodeToUTF8N` at `0x140025ea6`
- `ntoskrnl!RtlUnicodeToUTF8N` at `0x140025ea6`
- `ntoskrnl!_stricmp` at `0x140025f40`
- `ntoskrnl!_stricmp` at `0x140025fdf`
- `ntoskrnl!_stricmp` at `0x140026190`
- `ntoskrnl!_stricmp` at `0x140025f40`
- `ntoskrnl!_stricmp` at `0x140025fdf`
- `ntoskrnl!_stricmp` at `0x140026190`

## pseudocode

```c
__int64 __fastcall DrCreateVNetRoot(__int64 a1)
{
  __int64 v1; // r14
  RefCount *v3; // rbx
  __int64 v4; // r13
  __int64 v5; // r15
  unsigned __int16 *v6; // r10
  __int64 v7; // rdi
  __int64 v8; // rdx
  unsigned __int64 v9; // r8
  wchar_t *v10; // r9
  wchar_t *Buffer; // rdx
  wchar_t *v12; // rcx
  unsigned __int16 Length; // ax
  NTSTATUS v14; // edi
  size_t v15; // rcx
  WCHAR *v16; // r8
  wchar_t *v17; // r9
  __int64 v18; // rdx
  WCHAR *v19; // rcx
  unsigned int v20; // edi
  int v21; // eax
  unsigned int SessionIdFromFileName; // eax
  int v23; // r12d
  int v24; // eax
  PDEVICE_OBJECT v25; // rcx
  __int64 v26; // rdx
  NTSTATUS v27; // eax
  void (__fastcall *v28)(__int64); // rax
  ULONG dwFlags; // [rsp+20h] [rbp-E0h]
  ULONG dwFlagsa[2]; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+28h] [rbp-D8h]
  UNICODE_STRING SourceString; // [rsp+30h] [rbp-D0h] BYREF
  ULONG UTF8StringActualByteCount; // [rsp+40h] [rbp-C0h] BYREF
  RefCount *v35; // [rsp+48h] [rbp-B8h] BYREF
  RefCount *v36; // [rsp+50h] [rbp-B0h] BYREF
  int v37; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *ppszSrc[2]; // [rsp+60h] [rbp-A0h] BYREF
  size_t pcchSrcLength[2]; // [rsp+70h] [rbp-90h] BYREF
  CHAR UTF8StringDestination[272]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR UnicodeStringSource[264]; // [rsp+190h] [rbp+90h] BYREF

  v1 = *(_QWORD *)(a1 + 32);
  v36 = 0;
  v3 = 0;
  v35 = 0;
  *(_QWORD *)&SourceString.Length = 0;
  SourceString.Buffer = 0;
  UTF8StringActualByteCount = 0;
  v37 = 0;
  memset(UnicodeStringSource, 0, 0x208u);
  memset(UTF8StringDestination, 0, 0x104u);
  v4 = *(_QWORD *)(a1 + 264);
  *(_OWORD *)ppszSrc = 0;
  v5 = *(_QWORD *)(v4 + 32);
  v6 = *(unsigned __int16 **)(v5 + 88);
  v7 = *(_QWORD *)(v5 + 32);
  v8 = *((_QWORD *)v6 + 1);
  v9 = v8 + *v6;
  v10 = (wchar_t *)(v8 + 2 * ((unsigned __int64)**(unsigned __int16 **)(v7 + 64) >> 1));
  Buffer = v10;
  v12 = v10;
  for ( SourceString.Buffer = v10; (unsigned __int64)v10 < v9; ++v10 )
  {
    if ( *v10 == 92 && v10 != v12 )
      break;
  }
  ppszSrc[1] = v10;
  Length = (_WORD)v10 - (_WORD)v12;
  LOWORD(v9) = v9 - (_WORD)v10;
  SourceString.MaximumLength = (_WORD)v10 - (_WORD)v12;
  WORD1(ppszSrc[0]) = v9;
  LOWORD(ppszSrc[0]) = v9;
  SourceString.Length = (_WORD)v10 - (_WORD)v12;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids, v6);
      Buffer = SourceString.Buffer;
      Length = SourceString.Length;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_ZZZ(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)Buffer,
        v9,
        *(_QWORD *)(v7 + 64),
        (__int64)&SourceString,
        (__int64)ppszSrc);
      Buffer = SourceString.Buffer;
      Length = SourceString.Length;
    }
  }
  if ( Length < 2u )
  {
    v14 = -1073741620;
    goto LABEL_97;
  }
  if ( *Buffer == 92 )
  {
    SourceString.Buffer = Buffer + 1;
    SourceString.MaximumLength -= 2;
    SourceString.Length = Length - 2;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids, &SourceString);
  ppszSrc[0] = 0;
  pcchSrcLength[0] = 0;
  v14 = RtlUnicodeStringValidateSrcWorker(&SourceString, ppszSrc, pcchSrcLength, (const size_t)v10, dwFlags);
  if ( v14 < 0 )
  {
    UnicodeStringSource[0] = 0;
LABEL_94:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        24,
        WPP_bd9402812a03393f9299abe31314ec3e_Traceguids,
        (unsigned int)v14);
    goto LABEL_97;
  }
  v15 = pcchSrcLength[0];
  v16 = UnicodeStringSource;
  v17 = ppszSrc[0];
  v18 = 260;
  do
  {
    if ( !v15 )
      break;
    --v15;
    *v16++ = *v17++;
    --v18;
  }
  while ( v18 );
  v19 = v16 - 1;
  v14 = -2147483643;
  if ( v18 )
  {
    v19 = v16;
    v14 = 0;
  }
  *v19 = 0;
  if ( !v18 )
    goto LABEL_94;
  if ( RtlUnicodeToUTF8N(UTF8StringDestination, 0x103u, &UTF8StringActualByteCount, UnicodeStringSource, 0x208u) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids);
  }
  else
  {
    if ( UTF8StringActualByteCount >= 0x104uLL )
      _report_rangecheckfailure();
    UTF8StringDestination[UTF8StringActualByteCount] = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_s(
        WPP_GLOBAL_Control->AttachedDevice,
        25,
        WPP_bd9402812a03393f9299abe31314ec3e_Traceguids,
        UTF8StringDestination,
        *(_QWORD *)dwFlagsa,
        v32);
  }
  v20 = -1;
  if ( (unsigned __int8)DrIsSystemProcessRequest(*(_QWORD *)(v1 + 544)) )
  {
    v21 = _stricmp(UTF8StringDestination, "SCARD");
    *(_OWORD *)ppszSrc = *(_OWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 48) + 48LL) + 88LL);
    if ( v21 )
      SessionIdFromFileName = DrGetSessionIdFromFileName(ppszSrc);
    else
      SessionIdFromFileName = DrGetScardSessionIdFromFileName(ppszSrc);
    v20 = SessionIdFromFileName;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        27,
        WPP_bd9402812a03393f9299abe31314ec3e_Traceguids,
        *(unsigned int *)(v4 + 88));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids, v20);
  }
  if ( v20 == -1 )
    v20 = *(_DWORD *)(v4 + 88);
  v23 = _stricmp(UTF8StringDestination, "SCARD");
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids);
  if ( (unsigned int)DrSessionManager::FindOrCreateSessionById(
                       WPP_MAIN_CB.Queue.Wcb.DeviceContext,
                       v20,
                       v23 == 0,
                       (unsigned int)&v37,
                       (__int64)&v36) )
  {
    v14 = -1073741620;
    goto LABEL_97;
  }
  if ( !v37 )
  {
    if ( v23 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids);
      v14 = -1073741790;
      goto LABEL_97;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids);
    DrExchangeManager::Start((RefCount *)((char *)v36 + 688));
    goto LABEL_75;
  }
  if ( *(_QWORD *)(v4 + 40) )
  {
    v14 = 0;
    goto LABEL_97;
  }
  if ( UTF8StringActualByteCount != -1 )
  {
    if ( (unsigned int)DrDeviceManager::FindDeviceByDosName((char *)v36 + 912, UTF8StringDestination, &v35) )
    {
      v3 = v35;
      RefCount::AddRef(v35);
      v14 = 0;
      *(_QWORD *)(v4 + 40) = v3;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids);
      v24 = *((_DWORD *)v3 + 11);
      switch ( v24 )
      {
        case 8:
          if ( (*(unsigned int (__fastcall **)(RefCount *))(*(_QWORD *)v3 + 56LL))(v3) )
          {
            *(_DWORD *)(v5 + 80) = 7;
            *(_BYTE *)(v5 + 77) = 0;
            goto LABEL_97;
          }
          RefCount::Release(v3);
          *(_QWORD *)(v4 + 40) = 0;
          v14 = -1073741620;
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            v26 = 31;
LABEL_65:
            WPP_SF_(v25->AttachedDevice, v26, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids);
            goto LABEL_97;
          }
          break;
        case 1:
          *(_DWORD *)(v5 + 80) = 27;
          *(_BYTE *)(v5 + 77) = 2;
          break;
        case 32:
          *(_DWORD *)(v5 + 80) = 7;
          *(_BYTE *)(v5 + 77) = 0;
          break;
        default:
          *(_BYTE *)(v5 + 77) = 3;
          *(_DWORD *)(v5 + 80) = 24;
          break;
      }
      goto LABEL_97;
    }
    if ( _stricmp(UTF8StringDestination, "SCARD") )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids);
      v3 = v35;
      v14 = -1073741620;
      goto LABEL_97;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids);
LABEL_75:
    v27 = DrCreateSCardDevice(&v36, v4, &v35);
    v3 = v35;
    v14 = v27;
    goto LABEL_97;
  }
  v14 = -1073741620;
  v25 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    v26 = 34;
    goto LABEL_65;
  }
LABEL_97:
  v28 = *(void (__fastcall **)(__int64))(a1 + 272);
  *(_DWORD *)(a1 + 284) = 0;
  *(_DWORD *)(a1 + 280) = v14;
  v28(a1);
  if ( v3 )
    RefCount::Release(v3);
  if ( v36 )
    RefCount::Release(v36);
  return 259;
}

```

## disassembly

```asm
0x140025c40  push    rbp
0x140025c42  push    rbx
0x140025c43  push    rsi
0x140025c44  push    rdi
0x140025c45  push    r12
0x140025c47  push    r13
0x140025c49  push    r14
0x140025c4b  push    r15
0x140025c4d  lea     rbp, [rsp-2B8h]
0x140025c55  sub     rsp, 3B8h
0x140025c5c  mov     rax, cs:__security_cookie
0x140025c63  xor     rax, rsp
0x140025c66  mov     [rbp+2F0h+var_50], rax
0x140025c6d  mov     r14, [rcx+20h]
0x140025c71  mov     rsi, rcx
0x140025c74  xor     ecx, ecx
0x140025c76  xor     edx, edx; Val
0x140025c78  mov     [rsp+3F0h+var_3A0], rcx
0x140025c7d  mov     ebx, ecx
0x140025c7f  mov     [rsp+3F0h+var_3A8], rcx
0x140025c84  mov     r8d, 208h; Size
0x140025c8a  mov     qword ptr [rsp+3F0h+SourceString.Length], rcx
0x140025c8f  mov     [rsp+3F0h+SourceString.Buffer], rcx
0x140025c94  mov     [rsp+3F0h+UTF8StringActualByteCount], ecx
0x140025c98  mov     [rsp+3F0h+var_398], ecx
0x140025c9c  lea     rcx, [rbp+2F0h+UnicodeStringSource]; void *
0x140025ca3  call    memset
0x140025ca8  xor     edx, edx; Val
0x140025caa  lea     rcx, [rbp+2F0h+UTF8StringDestination]; void *
0x140025cae  mov     r8d, 104h; Size
0x140025cb4  call    memset
0x140025cb9  mov     r13, [rsi+108h]
0x140025cc0  xorps   xmm0, xmm0
0x140025cc3  movups  xmmword ptr [rsp+3F0h+ppszSrc], xmm0
0x140025cc8  mov     r15, [r13+20h]
0x140025ccc  mov     r10, [r15+58h]
0x140025cd0  mov     rdi, [r15+20h]
0x140025cd4  mov     rdx, [r10+8]
0x140025cd8  mov     rax, [rdi+40h]
0x140025cdc  movzx   r8d, word ptr [r10]
0x140025ce0  add     r8, rdx
0x140025ce3  movzx   ecx, word ptr [rax]
0x140025ce6  shr     rcx, 1
0x140025ce9  lea     r9, [rdx+rcx*2]
0x140025ced  mov     rdx, r9
0x140025cf0  mov     rcx, r9
0x140025cf3  mov     [rsp+3F0h+SourceString.Buffer], rdx
0x140025cf8  cmp     r9, r8
0x140025cfb  jnb     short loc_140025D12
0x140025cfd  cmp     word ptr [r9], 5Ch ; '\'
0x140025d02  jnz     short loc_140025D09
0x140025d04  cmp     r9, rcx
0x140025d07  jnz     short loc_140025D12
0x140025d09  add     r9, 2
0x140025d0d  cmp     r9, r8
0x140025d10  jb      short loc_140025CFD
0x140025d12  movzx   eax, r9w
0x140025d16  mov     [rsp+3F0h+ppszSrc+8], r9
0x140025d1b  sub     ax, cx
0x140025d1e  sub     r8w, r9w
0x140025d22  mov     [rsp+3F0h+SourceString.MaximumLength], ax
0x140025d27  mov     word ptr [rsp+3F0h+ppszSrc+2], r8w
0x140025d2d  mov     word ptr [rsp+3F0h+ppszSrc], r8w
0x140025d33  mov     [rsp+3F0h+SourceString.Length], ax
0x140025d38  mov     rcx, cs:WPP_GLOBAL_Control
0x140025d3f  lea     r12, WPP_GLOBAL_Control
0x140025d46  cmp     rcx, r12
0x140025d49  jz      short loc_140025DB0
0x140025d4b  cmp     byte ptr [rcx+29h], 4
0x140025d4f  jb      short loc_140025D73
0x140025d51  mov     rcx, [rcx+18h]
0x140025d55  lea     r8, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids
0x140025d5c  mov     edx, 0Fh
0x140025d61  mov     r9, r10
0x140025d64  call    WPP_SF_Z
0x140025d69  mov     rdx, [rsp+3F0h+SourceString.Buffer]
0x140025d6e  movzx   eax, [rsp+3F0h+SourceString.Length]
0x140025d73  mov     rcx, cs:WPP_GLOBAL_Control
0x140025d7a  cmp     rcx, r12
0x140025d7d  jz      short loc_140025DB0
0x140025d7f  cmp     byte ptr [rcx+29h], 4
0x140025d83  jb      short loc_140025DB0
0x140025d85  mov     r9, [rdi+40h]
0x140025d89  lea     rax, [rsp+3F0h+ppszSrc]
0x140025d8e  mov     rcx, [rcx+18h]
0x140025d92  mov     [rsp+3F0h+var_3C8], rax
0x140025d97  lea     rax, [rsp+3F0h+SourceString]
0x140025d9c  mov     qword ptr [rsp+3F0h+dwFlags], rax; dwFlags
0x140025da1  call    WPP_SF_ZZZ
0x140025da6  mov     rdx, [rsp+3F0h+SourceString.Buffer]
0x140025dab  movzx   eax, [rsp+3F0h+SourceString.Length]
0x140025db0  cmp     ax, 2
0x140025db4  jnb     short loc_140025DC0
0x140025db6  mov     edi, 0C00000CCh
0x140025dbb  jmp     loc_140026311
0x140025dc0  cmp     word ptr [rdx], 5Ch ; '\'
0x140025dc4  jnz     short loc_140025DE1
0x140025dc6  mov     ecx, 0FFFEh
0x140025dcb  add     rdx, 2
0x140025dcf  add     ax, cx
0x140025dd2  mov     [rsp+3F0h+SourceString.Buffer], rdx
0x140025dd7  add     [rsp+3F0h+SourceString.MaximumLength], cx
0x140025ddc  mov     [rsp+3F0h+SourceString.Length], ax
0x140025de1  mov     rcx, cs:WPP_GLOBAL_Control
0x140025de8  cmp     rcx, r12
0x140025deb  jz      short loc_140025E0D
0x140025ded  cmp     byte ptr [rcx+29h], 4
0x140025df1  jb      short loc_140025E0D
0x140025df3  mov     rcx, [rcx+18h]
0x140025df7  lea     r9, [rsp+3F0h+SourceString]
0x140025dfc  mov     edx, 17h
0x140025e01  lea     r8, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids
0x140025e08  call    WPP_SF_Z
0x140025e0d  xor     eax, eax
0x140025e0f  lea     r8, [rsp+3F0h+pcchSrcLength]; pcchSrcLength
0x140025e14  lea     rdx, [rsp+3F0h+ppszSrc]; ppszSrc
0x140025e19  mov     [rsp+3F0h+ppszSrc], rax
0x140025e1e  lea     rcx, [rsp+3F0h+SourceString]; SourceString
0x140025e23  mov     [rsp+3F0h+pcchSrcLength], rax
0x140025e28  call    RtlUnicodeStringValidateSrcWorker
0x140025e2d  mov     edi, eax
0x140025e2f  test    eax, eax
0x140025e31  js      loc_1400262DE
0x140025e37  mov     rcx, [rsp+3F0h+pcchSrcLength]
0x140025e3c  lea     r8, [rbp+2F0h+UnicodeStringSource]
0x140025e43  mov     r9, [rsp+3F0h+ppszSrc]
0x140025e48  mov     edx, 104h
0x140025e4d  test    rcx, rcx
0x140025e50  jz      short loc_140025E6B
0x140025e52  movzx   eax, word ptr [r9]
0x140025e56  dec     rcx
0x140025e59  mov     [r8], ax
0x140025e5d  add     r9, 2
0x140025e61  add     r8, 2
0x140025e65  sub     rdx, 1
0x140025e69  jnz     short loc_140025E4D
0x140025e6b  xor     eax, eax
0x140025e6d  lea     rcx, [r8-2]
0x140025e71  test    rdx, rdx
0x140025e74  mov     edi, 80000005h
0x140025e79  cmovnz  rcx, r8
0x140025e7d  cmovnz  edi, eax
0x140025e80  mov     [rcx], ax
0x140025e83  jz      loc_1400262E7
0x140025e89  lea     r9, [rbp+2F0h+UnicodeStringSource]; UnicodeStringSource
0x140025e90  mov     [rsp+3F0h+dwFlags], 208h; UnicodeStringByteCount
0x140025e98  lea     r8, [rsp+3F0h+UTF8StringActualByteCount]; UTF8StringActualByteCount
0x140025e9d  mov     edx, 103h; UTF8StringMaxByteCount
0x140025ea2  lea     rcx, [rbp+2F0h+UTF8StringDestination]; UTF8StringDestination
0x140025ea6  call    cs:__imp_RtlUnicodeToUTF8N
0x140025ead  nop     dword ptr [rax+rax+00h]
0x140025eb2  test    eax, eax
0x140025eb4  js      short loc_140025EF9
0x140025eb6  mov     eax, [rsp+3F0h+UTF8StringActualByteCount]
0x140025eba  cmp     rax, 104h
0x140025ec0  jnb     short loc_140025EF3
0x140025ec2  mov     [rbp+rax+2F0h+UTF8StringDestination], bl
0x140025ec6  mov     rcx, cs:WPP_GLOBAL_Control
0x140025ecd  cmp     rcx, r12
0x140025ed0  jz      short loc_140025F20
0x140025ed2  cmp     byte ptr [rcx+29h], 4
0x140025ed6  jb      short loc_140025F20
0x140025ed8  mov     rcx, [rcx+18h]
0x140025edc  lea     r9, [rbp+2F0h+UTF8StringDestination]
0x140025ee0  mov     edx, 19h
0x140025ee5  lea     r8, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids
0x140025eec  call    WPP_SF_s
0x140025ef1  jmp     short loc_140025F20
0x140025ef3  call    __report_rangecheckfailure
0x140025ef9  mov     rcx, cs:WPP_GLOBAL_Control
0x140025f00  cmp     rcx, r12
0x140025f03  jz      short loc_140025F20
0x140025f05  cmp     byte ptr [rcx+29h], 2
0x140025f09  jb      short loc_140025F20
0x140025f0b  mov     rcx, [rcx+18h]
0x140025f0f  lea     r8, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids
0x140025f16  mov     edx, 1Ah
0x140025f1b  call    WPP_SF_
0x140025f20  mov     rcx, [r14+220h]
0x140025f27  mov     edi, 0FFFFFFFFh
0x140025f2c  call    DrIsSystemProcessRequest
0x140025f31  test    al, al
0x140025f33  jz      short loc_140025F76
0x140025f35  lea     rdx, Str1; "SCARD"
0x140025f3c  lea     rcx, [rbp+2F0h+UTF8StringDestination]; Str1
0x140025f40  call    cs:__imp__stricmp
0x140025f47  nop     dword ptr [rax+rax+00h]
0x140025f4c  mov     ecx, eax
0x140025f4e  mov     rax, [r14+30h]
0x140025f52  test    ecx, ecx
0x140025f54  lea     rcx, [rsp+3F0h+ppszSrc]
0x140025f59  mov     rdx, [rax+30h]
0x140025f5d  movups  xmm0, xmmword ptr [rdx+58h]
0x140025f61  movaps  xmmword ptr [rsp+3F0h+ppszSrc], xmm0
0x140025f66  jnz     short loc_140025F6F
0x140025f68  call    DrGetScardSessionIdFromFileName
0x140025f6d  jmp     short loc_140025F74
0x140025f6f  call    DrGetSessionIdFromFileName
0x140025f74  mov     edi, eax
0x140025f76  mov     rcx, cs:WPP_GLOBAL_Control
0x140025f7d  cmp     rcx, r12
0x140025f80  jz      short loc_140025FCB
0x140025f82  cmp     byte ptr [rcx+29h], 4
0x140025f86  jb      short loc_140025FA1
0x140025f88  mov     r9d, [r13+58h]
0x140025f8c  lea     r8, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids
0x140025f93  mov     rcx, [rcx+18h]
0x140025f97  mov     edx, 1Bh
0x140025f9c  call    WPP_SF_d
0x140025fa1  mov     rcx, cs:WPP_GLOBAL_Control
0x140025fa8  cmp     rcx, r12
0x140025fab  jz      short loc_140025FCB
0x140025fad  cmp     byte ptr [rcx+29h], 4
0x140025fb1  jb      short loc_140025FCB
0x140025fb3  mov     rcx, [rcx+18h]
0x140025fb7  lea     r8, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids
0x140025fbe  mov     edx, 1Ch
0x140025fc3  mov     r9d, edi
0x140025fc6  call    WPP_SF_d
0x140025fcb  cmp     edi, 0FFFFFFFFh
0x140025fce  jnz     short loc_140025FD4
0x140025fd0  mov     edi, [r13+58h]
0x140025fd4  lea     rdx, Str1; "SCARD"
0x140025fdb  lea     rcx, [rbp+2F0h+UTF8StringDestination]; Str1
0x140025fdf  call    cs:__imp__stricmp
0x140025fe6  nop     dword ptr [rax+rax+00h]
0x140025feb  mov     r12d, eax
0x140025fee  mov     rcx, cs:WPP_GLOBAL_Control
0x140025ff5  xor     r14d, r14d
0x140025ff8  test    eax, eax
0x140025ffa  lea     rax, WPP_GLOBAL_Control
0x140026001  setz    r14b
0x140026005  cmp     rcx, rax
0x140026008  jz      short loc_140026025
0x14002600a  cmp     byte ptr [rcx+29h], 4
0x14002600e  jb      short loc_140026025
0x140026010  mov     rcx, [rcx+18h]
0x140026014  lea     r8, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids
0x14002601b  mov     edx, 1Dh
0x140026020  call    WPP_SF_
0x140026025  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+20h
0x14002602c  lea     rax, [rsp+3F0h+var_3A0]
0x140026031  lea     r9, [rsp+3F0h+var_398]
0x140026036  mov     qword ptr [rsp+3F0h+dwFlags], rax
0x14002603b  mov     r8d, r14d
0x14002603e  mov     edx, edi
0x140026040  call    ?FindOrCreateSessionById@DrSessionManager@@QEAAJKHPEAHAEAV?$SmartPtr@VDrSession@@@@@Z; DrSessionManager::FindOrCreateSessionById(ulong,int,int *,SmartPtr<DrSession> &)
0x140026045  test    eax, eax
0x140026047  jz      short loc_140026053
0x140026049  mov     edi, 0C00000CCh
0x14002604e  jmp     loc_140026311
0x140026053  cmp     [rsp+3F0h+var_398], ebx
0x140026057  jz      loc_140026260
0x14002605d  cmp     [r13+28h], rbx
0x140026061  jnz     loc_140026259
0x140026067  cmp     [rsp+3F0h+UTF8StringActualByteCount], 0FFFFFFFFh
0x14002606c  jz      loc_140026229
0x140026072  mov     rcx, [rsp+3F0h+var_3A0]
0x140026077  lea     r8, [rsp+3F0h+var_3A8]
0x14002607c  add     rcx, 390h
0x140026083  lea     rdx, [rbp+2F0h+UTF8StringDestination]
0x140026087  call    ?FindDeviceByDosName@DrDeviceManager@@QEAAHPEAEAEAV?$SmartPtr@VDrDevice@@@@H@Z; DrDeviceManager::FindDeviceByDosName(uchar *,SmartPtr<DrDevice> &,int)
0x14002608c  test    eax, eax
0x14002608e  jz      loc_140026185
0x140026094  mov     rbx, [rsp+3F0h+var_3A8]
0x140026099  mov     rcx, rbx; this
0x14002609c  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x1400260a1  xor     edi, edi
0x1400260a3  mov     [r13+28h], rbx
0x1400260a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400260ae  lea     r14, WPP_GLOBAL_Control
0x1400260b5  cmp     rcx, r14
0x1400260b8  jz      short loc_1400260D5
0x1400260ba  cmp     byte ptr [rcx+29h], 4
0x1400260be  jb      short loc_1400260D5
0x1400260c0  mov     rcx, [rcx+18h]
0x1400260c4  lea     r8, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids
0x1400260cb  mov     edx, 1Eh
0x1400260d0  call    WPP_SF_
0x1400260d5  mov     eax, [rbx+2Ch]
0x1400260d8  cmp     eax, 8
0x1400260db  jnz     short loc_140026146
0x1400260dd  mov     rax, [rbx]
0x1400260e0  mov     rcx, rbx
0x1400260e3  mov     rax, [rax+38h]
0x1400260e7  call    _guard_dispatch_icall
0x1400260ec  test    eax, eax
0x1400260ee  jz      short loc_140026101
0x1400260f0  mov     dword ptr [r15+50h], 7
0x1400260f8  mov     [r15+4Dh], dil
0x1400260fc  jmp     loc_140026311
0x140026101  mov     rcx, rbx; this
0x140026104  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x140026109  mov     [r13+28h], rdi
0x14002610d  mov     edi, 0C00000CCh
0x140026112  mov     rcx, cs:WPP_GLOBAL_Control
0x140026119  cmp     rcx, r14
0x14002611c  jz      loc_140026311
0x140026122  cmp     byte ptr [rcx+29h], 4
0x140026126  jb      loc_140026311
  ... truncated ...
```
