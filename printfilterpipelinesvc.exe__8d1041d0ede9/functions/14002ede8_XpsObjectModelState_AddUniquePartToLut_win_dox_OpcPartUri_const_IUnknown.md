# XpsObjectModelState::AddUniquePartToLut(win_dox::OpcPartUri const &,IUnknown *)

- ea: `0x14002ede8`
- end: `0x14002ef69`
- name: `?AddUniquePartToLut@XpsObjectModelState@@QEAAXAEBVOpcPartUri@win_dox@@PEAUIUnknown@@@Z`
- size: `385`
- prototype: `void __fastcall(XpsObjectModelState *__hidden this, const struct win_dox::OpcPartUri *, struct IUnknown *)`
- caller_count: `16`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x14002c6c0`
- `0x14002ca60`
- `0x14002ce00`
- `0x14002d190`
- `0x14002d530`
- `0x14002d8d0`
- `0x14002e220`
- `0x14002e5f0`
- `0x14002ea50`
- `0x14003dee0`
- `0x14003e270`
- `0x14003efa0`
- `0x14003f350`
- `0x14003f740`
- `0x14003fbd0`
- `0x1400400a0`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x14000f9d8`
- `0x140015980`
- `0x1400172e8`
- `0x140025478`
- `0x140029c10`
- `0x14002ede8`
- `0x140038a74`
- `0x1400411d8`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x140055e58`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x14002ee7d`
- `KERNEL32!LeaveCriticalSection` at `0x14002ee7d`

## string_xrefs

- `0x14002eec7`: `Uri %ws already in LUT.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall XpsObjectModelState::AddUniquePartToLut(
        XpsObjectModelState *this,
        const struct win_dox::OpcPartUri *a2,
        struct IUnknown *a3)
{
  char *v6; // rdi
  win_dox::OpcPartUri *v7; // rax
  char v8; // bl
  int v10; // r8d
  const struct SplException::TSystemException *v11; // r8
  const struct _GUID *v12; // r9
  _QWORD *v13; // r8
  _QWORD *v14; // r9
  unsigned int v15; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *v16; // [rsp+28h] [rbp-D8h]
  HINSTANCE v17; // [rsp+30h] [rbp-D0h]
  __int64 v18[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v19[32]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v20[3]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v21; // [rsp+88h] [rbp-78h]
  _BYTE v22[160]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+130h] [rbp+30h] BYREF

  v6 = (char *)this + 24;
  v18[1] = (__int64)this + 24;
  NCoreLibrary::TCriticalSection::Enter((struct _RTL_CRITICAL_SECTION *)((char *)this + 24));
  v18[0] = (__int64)a3;
  PrnExcept::SmartAddRef<IPrintPipelineProgressReport>((__int64)a3);
  v7 = PartMapItem::PartMapItem((win_dox::OpcPartUri *)v19, a2, v18);
  v8 = PartMapInsert((char *)this + 80, v7);
  std::pair<win_dox::OpcPartUri const,PrnExcept::TRefSmartPtr<IStream>>::~pair<win_dox::OpcPartUri const,PrnExcept::TRefSmartPtr<IStream>>((win_dox::OpcPartUri *)v19);
  if ( (*((_DWORD *)v6 + 11))-- == 1 )
    *((_DWORD *)v6 + 10) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v6);
  win_dox::Uri::GetAbsoluteUri(a2, v20);
  if ( !v8 )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v22, "-", 0);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v22,
      0x80004005,
      v11,
      v12,
      v15,
      v16,
      v17);
    v13 = v20;
    if ( v21 > 7 )
      v13 = (_QWORD *)v20[0];
    SplException::TSystemException::Message((SplException::TSystemException *)v22, "Uri %ws already in LUT.", v13);
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v22);
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v14 = v20;
    if ( v21 > 7 )
      LODWORD(v14) = v20[0];
    WPP_SF_Sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, v10, (_DWORD)v14, (char)this);
  }
  std::wstring::_Tidy_deallocate(v20);
}

```

## disassembly

```asm
0x14002ede8  mov     [rsp-8+arg_10], rbx
0x14002eded  mov     [rsp-8+arg_18], rsi
0x14002edf2  push    rbp
0x14002edf3  push    rdi
0x14002edf4  push    r14
0x14002edf6  lea     rbp, [rsp-0E0h]
0x14002edfe  sub     rsp, 1E0h
0x14002ee05  mov     rax, cs:__security_cookie
0x14002ee0c  xor     rax, rsp
0x14002ee0f  mov     [rbp+0F0h+var_20], rax
0x14002ee16  mov     rbx, r8
0x14002ee19  mov     r14, rdx
0x14002ee1c  mov     rsi, rcx
0x14002ee1f  lea     rdi, [rcx+18h]
0x14002ee23  mov     [rsp+1F0h+var_1A8], rdi
0x14002ee28  mov     rcx, rdi; this
0x14002ee2b  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x14002ee30  nop
0x14002ee31  mov     [rsp+1F0h+var_1B0], rbx
0x14002ee36  mov     rcx, rbx
0x14002ee39  call    ??$SmartAddRef@UIPrintPipelineProgressReport@@@PrnExcept@@YAXPEAUIPrintPipelineProgressReport@@@Z; PrnExcept::SmartAddRef<IPrintPipelineProgressReport>(IPrintPipelineProgressReport *)
0x14002ee3e  lea     r8, [rsp+1F0h+var_1B0]
0x14002ee43  mov     rdx, r14
0x14002ee46  lea     rcx, [rsp+1F0h+var_1A0]
0x14002ee4b  call    ??0PartMapItem@@QEAA@AEBVOpcPartUri@win_dox@@V?$TRefSmartPtr@UIUnknown@@@PrnExcept@@@Z; PartMapItem::PartMapItem(win_dox::OpcPartUri const &,PrnExcept::TRefSmartPtr<IUnknown>)
0x14002ee50  nop
0x14002ee51  lea     rcx, [rsi+50h]
0x14002ee55  mov     rdx, rax
0x14002ee58  call    ?PartMapInsert@@YA_NPEAV?$map@VOpcPartUri@win_dox@@UPartMapItem@@U?$less@VOpcPartUri@win_dox@@@std@@V?$allocator@U?$pair@$$CBVOpcPartUri@win_dox@@UPartMapItem@@@std@@@5@@std@@AEAUPartMapItem@@@Z; PartMapInsert(std::map<win_dox::OpcPartUri,PartMapItem> *,PartMapItem &)
0x14002ee5d  mov     bl, al
0x14002ee5f  lea     rcx, [rsp+1F0h+var_1A0]; this
0x14002ee64  call    ??1?$pair@$$CBVOpcPartUri@win_dox@@V?$TRefSmartPtr@UIStream@@@PrnExcept@@@std@@QEAA@XZ; std::pair<win_dox::OpcPartUri const,PrnExcept::TRefSmartPtr<IStream>>::~pair<win_dox::OpcPartUri const,PrnExcept::TRefSmartPtr<IStream>>(void)
0x14002ee69  nop
0x14002ee6a  add     dword ptr [rdi+2Ch], 0FFFFFFFFh
0x14002ee6e  mov     edx, [rdi+2Ch]
0x14002ee71  jnz     short loc_14002EE7A
0x14002ee73  mov     dword ptr [rdi+28h], 0
0x14002ee7a  mov     rcx, rdi; lpCriticalSection
0x14002ee7d  call    cs:__imp_LeaveCriticalSection
0x14002ee83  lea     rdx, [rsp+1F0h+var_180]
0x14002ee88  mov     rcx, r14
0x14002ee8b  call    ?GetAbsoluteUri@Uri@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; win_dox::Uri::GetAbsoluteUri(void)
0x14002ee90  nop
0x14002ee91  test    bl, bl
0x14002ee93  jnz     short loc_14002EEF5
0x14002ee95  xor     r8d, r8d; unsigned int
0x14002ee98  lea     rdx, asc_1400696D8; "-"
0x14002ee9f  lea     rcx, [rbp+0F0h+var_160]; this
0x14002eea3  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x14002eea8  nop
0x14002eea9  mov     edx, 80004005h; unsigned int
0x14002eeae  lea     rcx, [rbp+0F0h+var_160]; this
0x14002eeb2  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x14002eeb7  lea     r8, [rsp+1F0h+var_180]
0x14002eebc  cmp     [rbp+0F0h+var_168], 7
0x14002eec1  cmova   r8, [rsp+1F0h+var_180]
0x14002eec7  lea     rdx, aUriWsAlreadyIn; "Uri %ws already in LUT."
0x14002eece  lea     rcx, [rbp+0F0h+var_160]; this
0x14002eed2  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x14002eed7  lea     rdx, [rbp+0F0h+var_160]; struct SplException::THResultException *
0x14002eedb  lea     rcx, [rbp+0F0h+pExceptionObject]; this
0x14002eedf  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x14002eee4  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x14002eeeb  lea     rcx, [rbp+0F0h+pExceptionObject]; pExceptionObject
0x14002eeef  call    _CxxThrowException_0
0x14002eef5  lea     rax, WPP_GLOBAL_Control
0x14002eefc  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ef03  cmp     rcx, rax
0x14002ef06  jz      short loc_14002EF38
0x14002ef08  test    byte ptr [rcx+1Ch], 10h
0x14002ef0c  jz      short loc_14002EF38
0x14002ef0e  cmp     byte ptr [rcx+19h], 3
0x14002ef12  jb      short loc_14002EF38
0x14002ef14  lea     r9, [rsp+1F0h+var_180]
0x14002ef19  cmp     [rbp+0F0h+var_168], 7
0x14002ef1e  cmova   r9, [rsp+1F0h+var_180]
0x14002ef24  mov     edx, 0ACh
0x14002ef29  mov     [rsp+1F0h+var_1D0], rsi
0x14002ef2e  mov     rcx, [rcx+10h]
0x14002ef32  call    WPP_SF_Sq
0x14002ef37  nop
0x14002ef38  lea     rcx, [rsp+1F0h+var_180]
0x14002ef3d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14002ef42  mov     rcx, [rbp+0F0h+var_20]
0x14002ef49  xor     rcx, rsp; StackCookie
0x14002ef4c  call    __security_check_cookie
0x14002ef51  lea     r11, [rsp+1F0h+var_10]
0x14002ef59  mov     rbx, [r11+30h]
0x14002ef5d  mov     rsi, [r11+38h]
0x14002ef61  mov     rsp, r11
0x14002ef64  pop     r14
0x14002ef66  pop     rdi
0x14002ef67  pop     rbp
0x14002ef68  retn
```
