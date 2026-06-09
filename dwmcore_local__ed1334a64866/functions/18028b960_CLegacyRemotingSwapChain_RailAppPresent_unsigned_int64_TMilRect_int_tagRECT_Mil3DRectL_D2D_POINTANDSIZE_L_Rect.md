# CLegacyRemotingSwapChain::RailAppPresent(unsigned __int64,TMilRect_<int,tagRECT,Mil3DRectL,D2D_POINTANDSIZE_L,RectUniqueness::_CMilRectL_> const &)

- ea: `0x18028b960`
- end: `0x18028bbc8`
- name: `?RailAppPresent@CLegacyRemotingSwapChain@@UEAAJ_KAEBV?$TMilRect_@HUtagRECT@@UMil3DRectL@@UD2D_POINTANDSIZE_L@@U_CMilRectL_@RectUniqueness@@@@@Z`
- size: `616`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update`

## callees

- `0x180015070`
- `0x180028de0`
- `0x18002bd6c`
- `0x180042de0`
- `0x180168d00`
- `0x1801cfb40`
- `0x180228490`
- `0x18022943c`
- `0x18027a0a0`
- `0x18028b960`
- `0x18028bca8`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18028ba40`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18028ba40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18028ba63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18028ba63`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18028bb70`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18028bb70`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!OffsetRgn` at `0x18028ba59`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!OffsetRgn` at `0x18028ba59`

## pseudocode

```c
__int64 __fastcall CLegacyRemotingSwapChain::RailAppPresent(CD3DDevice **this, __int64 a2, const struct tagRECT *a3)
{
  HRGN v6; // rdi
  CD3DDevice *v7; // rax
  unsigned int v8; // ebx
  int updated; // eax
  signed int v10; // ebx
  int v11; // eax
  signed int LastError; // eax
  HRGN hrgn; // [rsp+30h] [rbp-D0h] BYREF
  struct tagRECT v15; // [rsp+38h] [rbp-C8h] BYREF
  int v16; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v17; // [rsp+58h] [rbp-A8h]
  int v18; // [rsp+60h] [rbp-A0h]
  int v19; // [rsp+64h] [rbp-9Ch]
  __int64 v20; // [rsp+68h] [rbp-98h]
  int v21; // [rsp+98h] [rbp-68h]
  __int64 v22; // [rsp+A0h] [rbp-60h]
  HRGN v23; // [rsp+A8h] [rbp-58h]
  LONG left; // [rsp+B8h] [rbp-48h]
  LONG top; // [rsp+BCh] [rbp-44h]
  _BYTE v26[80]; // [rsp+E0h] [rbp-20h] BYREF

  v6 = 0;
  hrgn = 0;
  memset_0(&v16, 0, 0x90u);
  CD3DDevice::Flush(this[7]);
  v18 = a3->right - a3->left;
  v19 = a3->bottom - a3->top;
  v7 = this[14];
  v16 = 0;
  v17 = a2;
  v20 = 0;
  if ( !*(_DWORD *)v7 )
  {
    v8 = 1;
LABEL_12:
    v10 = (*(__int64 (__fastcall **)(CD3DDevice *, int *, _QWORD))(*(_QWORD *)this[12] + 56LL))(this[12], &v16, v8);
    if ( ((v10 + 2147467263) & 0xFFFFFFFB) != 0 )
    {
      if ( v10 < 0 )
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v10, 0x142u, 0);
    }
    else
    {
      v10 = -2003304307;
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2003304307, 0x13Eu, 0);
    }
    goto LABEL_18;
  }
  updated = CLegacyRemotingSwapChain::UpdateSectionBits((CLegacyRemotingSwapChain *)this);
  v10 = updated;
  if ( updated < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, updated, 0x11Eu, 0);
    goto LABEL_21;
  }
  FastRegion::CRegion::CRegion((FastRegion::CRegion *)v26, a3);
  CRegion::Intersect((CRegion *)(this + 14), (const struct CRegion *)v26);
  *(_QWORD *)&v15.left = 0;
  FastRegion::CRegion::GetBoundingRect((FastRegion::CRegion *)(this + 14), &v15);
  v11 = CRegion::CreateHRGN((CRegion *)(this + 14), &hrgn);
  v10 = v11;
  if ( v11 >= 0 )
  {
    SetLastError(0);
    v6 = hrgn;
    if ( !OffsetRgn(hrgn, -a3->left, -a3->top) )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      if ( v10 >= 0 )
        v10 = -2003304445;
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v10, 0x12Du, 0);
      FastRegion::CRegion::FreeMemory((FastRegion::CRegion *)v26);
      goto LABEL_18;
    }
    left = v15.left;
    v8 = 2;
    top = v15.top;
    v21 = 2;
    v22 = a2;
    v23 = v6;
    FastRegion::CRegion::FreeMemory((FastRegion::CRegion *)v26);
    goto LABEL_12;
  }
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v11, 0x129u, 0);
  FastRegion::CRegion::FreeMemory((FastRegion::CRegion *)v26);
  v6 = hrgn;
LABEL_18:
  if ( v6 )
    DeleteObject(v6);
LABEL_21:
  *(_DWORD *)this[14] = 0;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18028b960  mov     [rsp-8+arg_8], rbx
0x18028b965  mov     [rsp-8+arg_18], rsi
0x18028b96a  push    rbp
0x18028b96b  push    rdi
0x18028b96c  push    r12
0x18028b96e  push    r14
0x18028b970  push    r15
0x18028b972  lea     rbp, [rsp-40h]
0x18028b977  sub     rsp, 140h
0x18028b97e  mov     rax, cs:__security_cookie
0x18028b985  xor     rax, rsp
0x18028b988  mov     [rbp+60h+var_30], rax
0x18028b98c  mov     rsi, r8
0x18028b98f  mov     r12, rdx
0x18028b992  mov     r15, rcx
0x18028b995  xor     edi, edi
0x18028b997  xor     edx, edx; Val
0x18028b999  mov     [rsp+160h+hrgn], rdi
0x18028b99e  mov     r8d, 90h; Size
0x18028b9a4  lea     rcx, [rsp+160h+var_110]; void *
0x18028b9a9  call    memset_0
0x18028b9ae  mov     rcx, [r15+38h]; this
0x18028b9b2  call    ?Flush@CD3DDevice@@QEAAXXZ; CD3DDevice::Flush(void)
0x18028b9b7  mov     eax, [rsi+8]
0x18028b9ba  lea     r14, [r15+70h]
0x18028b9be  sub     eax, [rsi]
0x18028b9c0  mov     [rsp+160h+var_100], eax
0x18028b9c4  mov     eax, [rsi+0Ch]
0x18028b9c7  sub     eax, [rsi+4]
0x18028b9ca  mov     [rsp+160h+var_FC], eax
0x18028b9ce  mov     rax, [r14]
0x18028b9d1  mov     [rsp+160h+var_110], edi
0x18028b9d5  mov     [rsp+160h+var_108], r12
0x18028b9da  mov     [rsp+160h+var_F8], rdi
0x18028b9df  cmp     [rax], edi
0x18028b9e1  jnz     short loc_18028B9EB
0x18028b9e3  lea     ebx, [rdi+1]
0x18028b9e6  jmp     loc_18028BAD8
0x18028b9eb  mov     rcx, r15; this
0x18028b9ee  call    ?UpdateSectionBits@CLegacyRemotingSwapChain@@IEAAJXZ; CLegacyRemotingSwapChain::UpdateSectionBits(void)
0x18028b9f3  mov     ebx, eax
0x18028b9f5  test    eax, eax
0x18028b9f7  js      loc_18028BB78
0x18028b9fd  mov     rdx, rsi; struct tagRECT *
0x18028ba00  lea     rcx, [rbp+60h+var_80]; this
0x18028ba04  call    ??0CRegion@FastRegion@@QEAA@AEBUtagRECT@@@Z; FastRegion::CRegion::CRegion(tagRECT const &)
0x18028ba09  lea     rdx, [rbp+60h+var_80]; struct CRegion *
0x18028ba0d  mov     rcx, r14; this
0x18028ba10  call    ?Intersect@CRegion@@QEAAXAEBV1@@Z; CRegion::Intersect(CRegion const &)
0x18028ba15  lea     rdx, [rsp+160h+var_128]; struct tagRECT *
0x18028ba1a  mov     qword ptr [rsp+160h+var_128.left], rdi
0x18028ba1f  mov     rcx, r14; this
0x18028ba22  call    ?GetBoundingRect@CRegion@FastRegion@@QEBA_NAEAUtagRECT@@@Z; FastRegion::CRegion::GetBoundingRect(tagRECT &)
0x18028ba27  lea     rdx, [rsp+160h+hrgn]; HRGN *
0x18028ba2c  mov     rcx, r14; this
0x18028ba2f  call    ?CreateHRGN@CRegion@@QEBAJPEAPEAUHRGN__@@@Z; CRegion::CreateHRGN(HRGN__ * *)
0x18028ba34  mov     ebx, eax
0x18028ba36  test    eax, eax
0x18028ba38  js      loc_18028BB3D
0x18028ba3e  xor     ecx, ecx; dwErrCode
0x18028ba40  call    cs:__imp_SetLastError
0x18028ba46  mov     r8d, [rsi+4]
0x18028ba4a  mov     edx, [rsi]
0x18028ba4c  neg     r8d; y
0x18028ba4f  mov     rdi, [rsp+160h+hrgn]
0x18028ba54  neg     edx; x
0x18028ba56  mov     rcx, rdi; hrgn
0x18028ba59  call    cs:__imp_OffsetRgn
0x18028ba5f  test    eax, eax
0x18028ba61  jnz     short loc_18028BAB1
0x18028ba63  call    cs:__imp_GetLastError
0x18028ba69  mov     ebx, eax
0x18028ba6b  test    eax, eax
0x18028ba6d  jle     short loc_18028BA78
0x18028ba6f  movzx   ebx, ax
0x18028ba72  or      ebx, 80070000h
0x18028ba78  mov     eax, 88980003h
0x18028ba7d  mov     [rsp+160h+var_138], 0; void *
0x18028ba86  test    ebx, ebx
0x18028ba88  mov     [rsp+160h+var_140], 12Dh; unsigned int
0x18028ba90  cmovns  ebx, eax
0x18028ba93  xor     edx, edx; int *
0x18028ba95  mov     r9d, ebx; int
0x18028ba98  xor     r8d, r8d; unsigned int
0x18028ba9b  lea     ecx, [rdx+14h]; unsigned int
0x18028ba9e  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18028baa3  lea     rcx, [rbp+60h+var_80]; this
0x18028baa7  call    ?FreeMemory@CRegion@FastRegion@@IEAAXXZ; FastRegion::CRegion::FreeMemory(void)
0x18028baac  jmp     loc_18028BB68
0x18028bab1  mov     eax, [rsp+160h+var_128.left]
0x18028bab5  lea     rcx, [rbp+60h+var_80]; this
0x18028bab9  mov     [rbp+60h+var_A8], eax
0x18028babc  mov     ebx, 2
0x18028bac1  mov     eax, [rsp+160h+var_128.top]
0x18028bac5  mov     [rbp+60h+var_A4], eax
0x18028bac8  mov     [rbp+60h+var_C8], ebx
0x18028bacb  mov     [rbp+60h+var_C0], r12
0x18028bacf  mov     [rbp+60h+var_B8], rdi
0x18028bad3  call    ?FreeMemory@CRegion@FastRegion@@IEAAXXZ; FastRegion::CRegion::FreeMemory(void)
0x18028bad8  mov     rcx, [r15+60h]
0x18028badc  lea     rdx, [rsp+160h+var_110]
0x18028bae1  mov     r8d, ebx
0x18028bae4  mov     rax, [rcx]
0x18028bae7  mov     rax, [rax+38h]
0x18028baeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028baf0  mov     ebx, eax
0x18028baf2  add     eax, 7FFFBFFFh
0x18028baf7  test    eax, 0FFFFFFFBh
0x18028bafc  jz      short loc_18028BB25
0x18028bafe  test    ebx, ebx
0x18028bb00  jns     short loc_18028BB68
0x18028bb02  mov     [rsp+160h+var_138], 0; void *
0x18028bb0b  mov     [rsp+160h+var_140], 142h; unsigned int
0x18028bb13  xor     edx, edx; int *
0x18028bb15  mov     r9d, ebx; int
0x18028bb18  xor     r8d, r8d; unsigned int
0x18028bb1b  lea     ecx, [rdx+14h]; unsigned int
0x18028bb1e  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18028bb23  jmp     short loc_18028BB68
0x18028bb25  mov     [rsp+160h+var_138], 0
0x18028bb2e  mov     ebx, 8898008Dh
0x18028bb33  mov     [rsp+160h+var_140], 13Eh
0x18028bb3b  jmp     short loc_18028BB13
0x18028bb3d  xor     edx, edx; int *
0x18028bb3f  mov     [rsp+160h+var_138], rdi; void *
0x18028bb44  mov     r9d, eax; int
0x18028bb47  mov     [rsp+160h+var_140], 129h; unsigned int
0x18028bb4f  xor     r8d, r8d; unsigned int
0x18028bb52  lea     ecx, [rdx+14h]; unsigned int
0x18028bb55  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18028bb5a  lea     rcx, [rbp+60h+var_80]; this
0x18028bb5e  call    ?FreeMemory@CRegion@FastRegion@@IEAAXXZ; FastRegion::CRegion::FreeMemory(void)
0x18028bb63  mov     rdi, [rsp+160h+hrgn]
0x18028bb68  test    rdi, rdi
0x18028bb6b  jz      short loc_18028BB95
0x18028bb6d  mov     rcx, rdi; ho
0x18028bb70  call    cs:__imp_DeleteObject
0x18028bb76  jmp     short loc_18028BB95
0x18028bb78  xor     edx, edx; int *
0x18028bb7a  mov     [rsp+160h+var_138], rdi; void *
0x18028bb7f  mov     r9d, eax; int
0x18028bb82  mov     [rsp+160h+var_140], 11Eh; unsigned int
0x18028bb8a  xor     r8d, r8d; unsigned int
0x18028bb8d  lea     ecx, [rdx+14h]; unsigned int
0x18028bb90  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18028bb95  mov     rax, [r14]
0x18028bb98  mov     dword ptr [rax], 0
0x18028bb9e  mov     eax, ebx
0x18028bba0  mov     rcx, [rbp+60h+var_30]
0x18028bba4  xor     rcx, rsp; StackCookie
0x18028bba7  call    __security_check_cookie
0x18028bbac  lea     r11, [rsp+160h+var_20]
0x18028bbb4  mov     rbx, [r11+38h]
0x18028bbb8  mov     rsi, [r11+48h]
0x18028bbbc  mov     rsp, r11
0x18028bbbf  pop     r15
0x18028bbc1  pop     r14
0x18028bbc3  pop     r12
0x18028bbc5  pop     rdi
0x18028bbc6  pop     rbp
0x18028bbc7  retn
```
