# CLegacyRemotingSwapChain::RailAppPresent(unsigned __int64,TMilRect_<int,tagRECT,Mil3DRectL,D2D_POINTANDSIZE_L,RectUniqueness::_CMilRectL_> const &)

- ea: `0x18028b980`
- end: `0x18028bbe8`
- name: `?RailAppPresent@CLegacyRemotingSwapChain@@UEAAJ_KAEBV?$TMilRect_@HUtagRECT@@UMil3DRectL@@UD2D_POINTANDSIZE_L@@U_CMilRectL_@RectUniqueness@@@@@Z`
- size: `616`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update`

## callees

- `0x1800244b0`
- `0x180050270`
- `0x18006f5b0`
- `0x18007253c`
- `0x18016dd20`
- `0x1801d1bb0`
- `0x1802284b0`
- `0x18022945c`
- `0x18027a0c0`
- `0x18028b980`
- `0x18028bcc8`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18028ba60`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18028ba60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18028ba83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18028ba83`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18028bb90`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18028bb90`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!OffsetRgn` at `0x18028ba79`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!OffsetRgn` at `0x18028ba79`

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
0x18028b980  mov     [rsp-8+arg_8], rbx
0x18028b985  mov     [rsp-8+arg_18], rsi
0x18028b98a  push    rbp
0x18028b98b  push    rdi
0x18028b98c  push    r12
0x18028b98e  push    r14
0x18028b990  push    r15
0x18028b992  lea     rbp, [rsp-40h]
0x18028b997  sub     rsp, 140h
0x18028b99e  mov     rax, cs:__security_cookie
0x18028b9a5  xor     rax, rsp
0x18028b9a8  mov     [rbp+60h+var_30], rax
0x18028b9ac  mov     rsi, r8
0x18028b9af  mov     r12, rdx
0x18028b9b2  mov     r15, rcx
0x18028b9b5  xor     edi, edi
0x18028b9b7  xor     edx, edx; Val
0x18028b9b9  mov     [rsp+160h+hrgn], rdi
0x18028b9be  mov     r8d, 90h; Size
0x18028b9c4  lea     rcx, [rsp+160h+var_110]; void *
0x18028b9c9  call    memset_0
0x18028b9ce  mov     rcx, [r15+38h]; this
0x18028b9d2  call    ?Flush@CD3DDevice@@QEAAXXZ; CD3DDevice::Flush(void)
0x18028b9d7  mov     eax, [rsi+8]
0x18028b9da  lea     r14, [r15+70h]
0x18028b9de  sub     eax, [rsi]
0x18028b9e0  mov     [rsp+160h+var_100], eax
0x18028b9e4  mov     eax, [rsi+0Ch]
0x18028b9e7  sub     eax, [rsi+4]
0x18028b9ea  mov     [rsp+160h+var_FC], eax
0x18028b9ee  mov     rax, [r14]
0x18028b9f1  mov     [rsp+160h+var_110], edi
0x18028b9f5  mov     [rsp+160h+var_108], r12
0x18028b9fa  mov     [rsp+160h+var_F8], rdi
0x18028b9ff  cmp     [rax], edi
0x18028ba01  jnz     short loc_18028BA0B
0x18028ba03  lea     ebx, [rdi+1]
0x18028ba06  jmp     loc_18028BAF8
0x18028ba0b  mov     rcx, r15; this
0x18028ba0e  call    ?UpdateSectionBits@CLegacyRemotingSwapChain@@IEAAJXZ; CLegacyRemotingSwapChain::UpdateSectionBits(void)
0x18028ba13  mov     ebx, eax
0x18028ba15  test    eax, eax
0x18028ba17  js      loc_18028BB98
0x18028ba1d  mov     rdx, rsi; struct tagRECT *
0x18028ba20  lea     rcx, [rbp+60h+var_80]; this
0x18028ba24  call    ??0CRegion@FastRegion@@QEAA@AEBUtagRECT@@@Z; FastRegion::CRegion::CRegion(tagRECT const &)
0x18028ba29  lea     rdx, [rbp+60h+var_80]; struct CRegion *
0x18028ba2d  mov     rcx, r14; this
0x18028ba30  call    ?Intersect@CRegion@@QEAAXAEBV1@@Z; CRegion::Intersect(CRegion const &)
0x18028ba35  lea     rdx, [rsp+160h+var_128]; struct tagRECT *
0x18028ba3a  mov     qword ptr [rsp+160h+var_128.left], rdi
0x18028ba3f  mov     rcx, r14; this
0x18028ba42  call    ?GetBoundingRect@CRegion@FastRegion@@QEBA_NAEAUtagRECT@@@Z; FastRegion::CRegion::GetBoundingRect(tagRECT &)
0x18028ba47  lea     rdx, [rsp+160h+hrgn]; HRGN *
0x18028ba4c  mov     rcx, r14; this
0x18028ba4f  call    ?CreateHRGN@CRegion@@QEBAJPEAPEAUHRGN__@@@Z; CRegion::CreateHRGN(HRGN__ * *)
0x18028ba54  mov     ebx, eax
0x18028ba56  test    eax, eax
0x18028ba58  js      loc_18028BB5D
0x18028ba5e  xor     ecx, ecx; dwErrCode
0x18028ba60  call    cs:__imp_SetLastError
0x18028ba66  mov     r8d, [rsi+4]
0x18028ba6a  mov     edx, [rsi]
0x18028ba6c  neg     r8d; y
0x18028ba6f  mov     rdi, [rsp+160h+hrgn]
0x18028ba74  neg     edx; x
0x18028ba76  mov     rcx, rdi; hrgn
0x18028ba79  call    cs:__imp_OffsetRgn
0x18028ba7f  test    eax, eax
0x18028ba81  jnz     short loc_18028BAD1
0x18028ba83  call    cs:__imp_GetLastError
0x18028ba89  mov     ebx, eax
0x18028ba8b  test    eax, eax
0x18028ba8d  jle     short loc_18028BA98
0x18028ba8f  movzx   ebx, ax
0x18028ba92  or      ebx, 80070000h
0x18028ba98  mov     eax, 88980003h
0x18028ba9d  mov     [rsp+160h+var_138], 0; void *
0x18028baa6  test    ebx, ebx
0x18028baa8  mov     [rsp+160h+var_140], 12Dh; unsigned int
0x18028bab0  cmovns  ebx, eax
0x18028bab3  xor     edx, edx; int *
0x18028bab5  mov     r9d, ebx; int
0x18028bab8  xor     r8d, r8d; unsigned int
0x18028babb  lea     ecx, [rdx+14h]; unsigned int
0x18028babe  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18028bac3  lea     rcx, [rbp+60h+var_80]; this
0x18028bac7  call    ?FreeMemory@CRegion@FastRegion@@IEAAXXZ; FastRegion::CRegion::FreeMemory(void)
0x18028bacc  jmp     loc_18028BB88
0x18028bad1  mov     eax, [rsp+160h+var_128.left]
0x18028bad5  lea     rcx, [rbp+60h+var_80]; this
0x18028bad9  mov     [rbp+60h+var_A8], eax
0x18028badc  mov     ebx, 2
0x18028bae1  mov     eax, [rsp+160h+var_128.top]
0x18028bae5  mov     [rbp+60h+var_A4], eax
0x18028bae8  mov     [rbp+60h+var_C8], ebx
0x18028baeb  mov     [rbp+60h+var_C0], r12
0x18028baef  mov     [rbp+60h+var_B8], rdi
0x18028baf3  call    ?FreeMemory@CRegion@FastRegion@@IEAAXXZ; FastRegion::CRegion::FreeMemory(void)
0x18028baf8  mov     rcx, [r15+60h]
0x18028bafc  lea     rdx, [rsp+160h+var_110]
0x18028bb01  mov     r8d, ebx
0x18028bb04  mov     rax, [rcx]
0x18028bb07  mov     rax, [rax+38h]
0x18028bb0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028bb10  mov     ebx, eax
0x18028bb12  add     eax, 7FFFBFFFh
0x18028bb17  test    eax, 0FFFFFFFBh
0x18028bb1c  jz      short loc_18028BB45
0x18028bb1e  test    ebx, ebx
0x18028bb20  jns     short loc_18028BB88
0x18028bb22  mov     [rsp+160h+var_138], 0; void *
0x18028bb2b  mov     [rsp+160h+var_140], 142h; unsigned int
0x18028bb33  xor     edx, edx; int *
0x18028bb35  mov     r9d, ebx; int
0x18028bb38  xor     r8d, r8d; unsigned int
0x18028bb3b  lea     ecx, [rdx+14h]; unsigned int
0x18028bb3e  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18028bb43  jmp     short loc_18028BB88
0x18028bb45  mov     [rsp+160h+var_138], 0
0x18028bb4e  mov     ebx, 8898008Dh
0x18028bb53  mov     [rsp+160h+var_140], 13Eh
0x18028bb5b  jmp     short loc_18028BB33
0x18028bb5d  xor     edx, edx; int *
0x18028bb5f  mov     [rsp+160h+var_138], rdi; void *
0x18028bb64  mov     r9d, eax; int
0x18028bb67  mov     [rsp+160h+var_140], 129h; unsigned int
0x18028bb6f  xor     r8d, r8d; unsigned int
0x18028bb72  lea     ecx, [rdx+14h]; unsigned int
0x18028bb75  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18028bb7a  lea     rcx, [rbp+60h+var_80]; this
0x18028bb7e  call    ?FreeMemory@CRegion@FastRegion@@IEAAXXZ; FastRegion::CRegion::FreeMemory(void)
0x18028bb83  mov     rdi, [rsp+160h+hrgn]
0x18028bb88  test    rdi, rdi
0x18028bb8b  jz      short loc_18028BBB5
0x18028bb8d  mov     rcx, rdi; ho
0x18028bb90  call    cs:__imp_DeleteObject
0x18028bb96  jmp     short loc_18028BBB5
0x18028bb98  xor     edx, edx; int *
0x18028bb9a  mov     [rsp+160h+var_138], rdi; void *
0x18028bb9f  mov     r9d, eax; int
0x18028bba2  mov     [rsp+160h+var_140], 11Eh; unsigned int
0x18028bbaa  xor     r8d, r8d; unsigned int
0x18028bbad  lea     ecx, [rdx+14h]; unsigned int
0x18028bbb0  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18028bbb5  mov     rax, [r14]
0x18028bbb8  mov     dword ptr [rax], 0
0x18028bbbe  mov     eax, ebx
0x18028bbc0  mov     rcx, [rbp+60h+var_30]
0x18028bbc4  xor     rcx, rsp; StackCookie
0x18028bbc7  call    __security_check_cookie
0x18028bbcc  lea     r11, [rsp+160h+var_20]
0x18028bbd4  mov     rbx, [r11+38h]
0x18028bbd8  mov     rsi, [r11+48h]
0x18028bbdc  mov     rsp, r11
0x18028bbdf  pop     r15
0x18028bbe1  pop     r14
0x18028bbe3  pop     r12
0x18028bbe5  pop     rdi
0x18028bbe6  pop     rbp
0x18028bbe7  retn
```
