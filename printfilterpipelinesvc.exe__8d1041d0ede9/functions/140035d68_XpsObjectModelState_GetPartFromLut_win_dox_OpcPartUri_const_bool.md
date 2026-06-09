# XpsObjectModelState::GetPartFromLut(win_dox::OpcPartUri const &,bool)

- ea: `0x140035d68`
- end: `0x140035f0f`
- name: `?GetPartFromLut@XpsObjectModelState@@QEAAPEAUIUnknown@@AEBVOpcPartUri@win_dox@@_N@Z`
- size: `423`
- prototype: `struct IUnknown *__fastcall(XpsObjectModelState *__hidden this, const struct win_dox::OpcPartUri *, bool)`
- caller_count: `15`
- callee_count: `13`
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
- `0x140035f18`
- `0x14003dee0`
- `0x14003efa0`
- `0x14003fbd0`
- `0x1400400a0`
- `0x1400404e0`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x14000fa68`
- `0x140010148`
- `0x1400172e8`
- `0x140027b1c`
- `0x140035d68`
- `0x1400411d8`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`
- `0x140055e58`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140035ddc`
- `KERNEL32!LeaveCriticalSection` at `0x140035ddc`

## string_xrefs

- `0x140035e7e`: `Uri %ws not found in LUT %p.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct IUnknown *__fastcall XpsObjectModelState::GetPartFromLut(
        XpsObjectModelState *this,
        const struct win_dox::OpcPartUri *a2,
        char a3)
{
  char *v6; // rbx
  __int64 v7; // rdi
  int v9; // r8d
  OLECHAR *v10; // r9
  const struct SplException::TSystemException *v11; // r8
  const struct _GUID *v12; // r9
  OLECHAR *v13; // r8
  __int64 v15; // rbx
  unsigned int v16; // [rsp+20h] [rbp-E0h]
  const struct win_musl::TStringEllipseBase *v17; // [rsp+28h] [rbp-D8h]
  HINSTANCE v18; // [rsp+30h] [rbp-D0h]
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v20[8]; // [rsp+48h] [rbp-B8h] BYREF
  OLECHAR v21[12]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v22; // [rsp+68h] [rbp-98h]
  _BYTE v23[160]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+110h] [rbp+10h] BYREF

  v6 = (char *)this + 24;
  v19 = (__int64)this + 24;
  NCoreLibrary::TCriticalSection::Enter((struct _RTL_CRITICAL_SECTION *)((char *)this + 24));
  v7 = *(_QWORD *)std::_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>::find(
                    (char *)this + 80,
                    v20,
                    a2);
  if ( (*((_DWORD *)v6 + 11))-- == 1 )
    *((_DWORD *)v6 + 10) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v6);
  if ( v7 == *((_QWORD *)this + 10) )
  {
    if ( a3 )
    {
      win_dox::Uri::GetAbsoluteUri((__int64 *)a2, v21);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v10 = v21;
        if ( v22 > 7 )
          LODWORD(v10) = *(_DWORD *)v21;
        WPP_SF_Sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 173, v9, (_DWORD)v10, (char)this);
      }
      SplException::THResultException::THResultException((SplException::THResultException *)v23, "-", 0);
      SplException::TSystemException::InternalInit(
        (SplException::TSystemException *)v23,
        0x80070490,
        v11,
        v12,
        v16,
        v17,
        v18);
      v13 = v21;
      if ( v22 > 7 )
        v13 = *(OLECHAR **)v21;
      SplException::TSystemException::Message(
        (SplException::TSystemException *)v23,
        "Uri %ws not found in LUT %p.",
        v13,
        this);
      SplException::THResultException::THResultException(
        (SplException::THResultException *)pExceptionObject,
        (const struct SplException::THResultException *)v23);
      throw (SplException::THResultException *)pExceptionObject;
    }
    return 0;
  }
  else
  {
    v19 = 0;
    PrnExcept::TRefSmartPtr<IUnknown>::operator=(&v19, v7 + 80);
    v15 = v19;
    v19 = 0;
    PrnExcept::SmartRelease<IPartResourceDictionary>(&v19);
    return (struct IUnknown *)v15;
  }
}

```

## disassembly

```asm
0x140035d68  mov     [rsp-8+arg_10], rbx
0x140035d6d  mov     [rsp-8+arg_18], rsi
0x140035d72  push    rbp
0x140035d73  push    rdi
0x140035d74  push    r12
0x140035d76  push    r14
0x140035d78  push    r15
0x140035d7a  lea     rbp, [rsp-0C0h]
0x140035d82  sub     rsp, 1C0h
0x140035d89  mov     rax, cs:__security_cookie
0x140035d90  xor     rax, rsp
0x140035d93  mov     [rbp+0E0h+var_30], rax
0x140035d9a  mov     r12b, r8b
0x140035d9d  mov     r15, rdx
0x140035da0  mov     rsi, rcx
0x140035da3  lea     rbx, [rcx+18h]
0x140035da7  mov     [rsp+1E0h+var_1A0], rbx
0x140035dac  mov     rcx, rbx; this
0x140035daf  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x140035db4  nop
0x140035db5  mov     r8, r15
0x140035db8  lea     rdx, [rsp+1E0h+var_198]
0x140035dbd  lea     rcx, [rsi+50h]
0x140035dc1  call    ?find@?$_Tree@V?$_Tset_traits@VOpcPartUri@win_dox@@U?$less@VOpcPartUri@win_dox@@@std@@V?$allocator@VOpcPartUri@win_dox@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@VOpcPartUri@win_dox@@@std@@@std@@@2@AEBVOpcPartUri@win_dox@@@Z; std::_Tree<std::_Tset_traits<win_dox::OpcPartUri,std::less<win_dox::OpcPartUri>,std::allocator<win_dox::OpcPartUri>,0>>::find(win_dox::OpcPartUri const &)
0x140035dc6  mov     rdi, [rax]
0x140035dc9  add     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x140035dcd  mov     eax, [rbx+2Ch]
0x140035dd0  jnz     short loc_140035DD9
0x140035dd2  mov     dword ptr [rbx+28h], 0
0x140035dd9  mov     rcx, rbx; lpCriticalSection
0x140035ddc  call    cs:__imp_LeaveCriticalSection
0x140035de2  cmp     rdi, [rsi+50h]
0x140035de6  jnz     loc_140035EB2
0x140035dec  test    r12b, r12b
0x140035def  jz      loc_140035EAE
0x140035df5  lea     rdx, [rsp+1E0h+var_190]
0x140035dfa  mov     rcx, r15
0x140035dfd  call    ?GetAbsoluteUri@Uri@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; win_dox::Uri::GetAbsoluteUri(void)
0x140035e02  nop
0x140035e03  lea     rax, WPP_GLOBAL_Control
0x140035e0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140035e11  cmp     rcx, rax
0x140035e14  jz      short loc_140035E46
0x140035e16  test    byte ptr [rcx+1Ch], 10h
0x140035e1a  jz      short loc_140035E46
0x140035e1c  cmp     byte ptr [rcx+19h], 3
0x140035e20  jb      short loc_140035E46
0x140035e22  lea     r9, [rsp+1E0h+var_190]
0x140035e27  cmp     [rsp+1E0h+var_178], 7
0x140035e2d  cmova   r9, qword ptr [rsp+1E0h+var_190]
0x140035e33  mov     edx, 0ADh
0x140035e38  mov     qword ptr [rsp+1E0h+var_1C0], rsi; unsigned int
0x140035e3d  mov     rcx, [rcx+10h]
0x140035e41  call    WPP_SF_Sq
0x140035e46  xor     r8d, r8d; unsigned int
0x140035e49  lea     rdx, asc_1400696D8; "-"
0x140035e50  lea     rcx, [rsp+1E0h+var_170]; this
0x140035e55  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140035e5a  nop
0x140035e5b  mov     edx, 80070490h; unsigned int
0x140035e60  lea     rcx, [rsp+1E0h+var_170]; this
0x140035e65  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140035e6a  lea     r8, [rsp+1E0h+var_190]
0x140035e6f  cmp     [rsp+1E0h+var_178], 7
0x140035e75  cmova   r8, qword ptr [rsp+1E0h+var_190]
0x140035e7b  mov     r9, rsi
0x140035e7e  lea     rdx, aUriWsNotFoundI; "Uri %ws not found in LUT %p."
0x140035e85  lea     rcx, [rsp+1E0h+var_170]; this
0x140035e8a  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140035e8f  lea     rdx, [rsp+1E0h+var_170]; struct SplException::THResultException *
0x140035e94  lea     rcx, [rbp+0E0h+pExceptionObject]; this
0x140035e98  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140035e9d  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140035ea4  lea     rcx, [rbp+0E0h+pExceptionObject]; pExceptionObject
0x140035ea8  call    _CxxThrowException_0
0x140035eae  xor     eax, eax
0x140035eb0  jmp     short loc_140035EE4
0x140035eb2  mov     [rsp+1E0h+var_1A0], 0
0x140035ebb  lea     rdx, [rdi+50h]
0x140035ebf  lea     rcx, [rsp+1E0h+var_1A0]
0x140035ec4  call    ??4?$TRefSmartPtr@UIUnknown@@@PrnExcept@@QEAAAEAV01@AEBV01@@Z; PrnExcept::TRefSmartPtr<IUnknown>::operator=(PrnExcept::TRefSmartPtr<IUnknown> const &)
0x140035ec9  mov     rbx, [rsp+1E0h+var_1A0]
0x140035ece  mov     [rsp+1E0h+var_1A0], 0
0x140035ed7  lea     rcx, [rsp+1E0h+var_1A0]
0x140035edc  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x140035ee1  mov     rax, rbx
0x140035ee4  mov     rcx, [rbp+0E0h+var_30]
0x140035eeb  xor     rcx, rsp; StackCookie
0x140035eee  call    __security_check_cookie
0x140035ef3  lea     r11, [rsp+1E0h+var_20]
0x140035efb  mov     rbx, [r11+40h]
0x140035eff  mov     rsi, [r11+48h]
0x140035f03  mov     rsp, r11
0x140035f06  pop     r15
0x140035f08  pop     r14
0x140035f0a  pop     r12
0x140035f0c  pop     rdi
0x140035f0d  pop     rbp
0x140035f0e  retn
```
