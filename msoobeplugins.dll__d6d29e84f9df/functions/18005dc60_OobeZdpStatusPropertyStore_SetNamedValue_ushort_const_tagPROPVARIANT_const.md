# OobeZdpStatusPropertyStore::SetNamedValue(ushort const *,tagPROPVARIANT const &)

- ea: `0x18005dc60`
- end: `0x18005dda8`
- name: `?SetNamedValue@OobeZdpStatusPropertyStore@@UEAAJPEBGAEBUtagPROPVARIANT@@@Z`
- size: `328`
- prototype: `int(OobeZdpStatusPropertyStore *__hidden this, const unsigned __int16 *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180008544`
- `0x18001d004`
- `0x18005dc24`
- `0x18005dc60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005dcfb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005dcfb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005dc91`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005dd32`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005dc91`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005dd32`
- `PROPSYS!PropVariantToUInt32` at `0x18005dcac`
- `PROPSYS!PropVariantToUInt32` at `0x18005dcac`
- `PROPSYS!PropVariantToBoolean` at `0x18005dd4d`
- `PROPSYS!PropVariantToBoolean` at `0x18005dd4d`

## string_xrefs

- `0x18005dd87`: `shell\oobe\machine\plugins\adapters\com\oobezdpmanager.cpp`

## pseudocode

```c
__int64 __fastcall OobeZdpStatusPropertyStore::SetNamedValue(
        RTL_SRWLOCK *this,
        const unsigned __int16 *a2,
        const PROPVARIANT *a3)
{
  HRESULT v6; // ebx
  __int64 v7; // rdx
  int v8; // edi
  void *v9; // rdx
  wil::details **Ptr; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-28h]
  RTL_SRWLOCK *v13; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  ULONG pulRet; // [rsp+68h] [rbp+20h] BYREF

  if ( CompareStringOrdinal(a2, -1, L"ZDPSTATUS", -1, 0) != 2 )
  {
    if ( CompareStringOrdinal(a2, -1, L"REBOOT", -1, 0) != 2 )
    {
      v6 = -2147418113;
      v7 = 81;
      goto LABEL_21;
    }
    pulRet = 0;
    v6 = PropVariantToBoolean(a3, (BOOL *)&pulRet);
    if ( v6 < 0 )
    {
      v7 = 73;
      goto LABEL_21;
    }
    if ( !pulRet )
      return 0;
    Ptr = (wil::details **)this[4].Ptr;
LABEL_18:
    wil::details::SetEvent(Ptr[15], v9);
    return 0;
  }
  pulRet = 0;
  v6 = PropVariantToUInt32(a3, &pulRet);
  if ( v6 >= 0 )
  {
    v8 = 0;
    switch ( pulRet )
    {
      case 1u:
        v8 = 1;
        break;
      case 2u:
        v8 = 2;
        break;
      case 3u:
        v8 = 3;
        break;
      case 4u:
        v8 = 4;
        break;
    }
    AcquireSRWLockExclusive(this + 5);
    v13 = this + 5;
    LODWORD(this[6].Ptr) = v8;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
    Ptr = (wil::details **)this[3].Ptr;
    goto LABEL_18;
  }
  v7 = 62;
LABEL_21:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobezdpmanager.cpp",
    (const char *)(unsigned int)v6,
    bIgnoreCase);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18005dc60  mov     [rsp+arg_0], rbx
0x18005dc65  mov     [rsp+arg_8], rsi
0x18005dc6a  push    rdi
0x18005dc6b  sub     rsp, 40h
0x18005dc6f  mov     rdi, rdx
0x18005dc72  mov     [rsp+48h+bIgnoreCase], 0; bIgnoreCase
0x18005dc7a  or      r9d, 0FFFFFFFFh; cchCount2
0x18005dc7e  mov     rbx, r8
0x18005dc81  mov     rsi, rcx
0x18005dc84  lea     r8, aZdpstatus; "ZDPSTATUS"
0x18005dc8b  or      edx, r9d; cchCount1
0x18005dc8e  mov     rcx, rdi; lpString1
0x18005dc91  call    cs:__imp_CompareStringOrdinal
0x18005dc97  cmp     eax, 2
0x18005dc9a  jnz     short loc_18005DD19
0x18005dc9c  lea     rdx, [rsp+48h+pulRet]; pulRet
0x18005dca1  mov     [rsp+48h+pulRet], 0
0x18005dca9  mov     rcx, rbx; propvarIn
0x18005dcac  call    cs:__imp_PropVariantToUInt32
0x18005dcb2  mov     ebx, eax
0x18005dcb4  test    eax, eax
0x18005dcb6  jns     short loc_18005DCC2
0x18005dcb8  mov     edx, 3Eh ; '>'
0x18005dcbd  jmp     loc_18005DD82
0x18005dcc2  mov     ecx, [rsp+48h+pulRet]
0x18005dcc6  xor     edi, edi
0x18005dcc8  sub     ecx, 1
0x18005dccb  jz      short loc_18005DCEF
0x18005dccd  sub     ecx, 1
0x18005dcd0  jz      short loc_18005DCE8
0x18005dcd2  sub     ecx, 1
0x18005dcd5  jz      short loc_18005DCE1
0x18005dcd7  cmp     ecx, 1
0x18005dcda  jnz     short loc_18005DCF4
0x18005dcdc  lea     edi, [rcx+3]
0x18005dcdf  jmp     short loc_18005DCF4
0x18005dce1  mov     edi, 3
0x18005dce6  jmp     short loc_18005DCF4
0x18005dce8  mov     edi, 2
0x18005dced  jmp     short loc_18005DCF4
0x18005dcef  mov     edi, 1
0x18005dcf4  lea     rbx, [rsi+28h]
0x18005dcf8  mov     rcx, rbx; SRWLock
0x18005dcfb  call    cs:__imp_AcquireSRWLockExclusive
0x18005dd01  lea     rcx, [rsp+48h+var_18]
0x18005dd06  mov     [rsp+48h+var_18], rbx
0x18005dd0b  mov     [rsi+30h], edi
0x18005dd0e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18005dd13  mov     rcx, [rsi+18h]
0x18005dd17  jmp     short loc_18005DD6B
0x18005dd19  or      r9d, 0FFFFFFFFh; cchCount2
0x18005dd1d  mov     [rsp+48h+bIgnoreCase], 0; int
0x18005dd25  or      edx, r9d; cchCount1
0x18005dd28  lea     r8, aReboot; "REBOOT"
0x18005dd2f  mov     rcx, rdi; lpString1
0x18005dd32  call    cs:__imp_CompareStringOrdinal
0x18005dd38  cmp     eax, 2
0x18005dd3b  jnz     short loc_18005DD78
0x18005dd3d  lea     rdx, [rsp+48h+pulRet]; pfRet
0x18005dd42  mov     [rsp+48h+pulRet], 0
0x18005dd4a  mov     rcx, rbx; propvarIn
0x18005dd4d  call    cs:__imp_PropVariantToBoolean
0x18005dd53  mov     ebx, eax
0x18005dd55  test    eax, eax
0x18005dd57  jns     short loc_18005DD60
0x18005dd59  mov     edx, 49h ; 'I'
0x18005dd5e  jmp     short loc_18005DD82
0x18005dd60  cmp     [rsp+48h+pulRet], 0
0x18005dd65  jz      short loc_18005DD74
0x18005dd67  mov     rcx, [rsi+20h]
0x18005dd6b  mov     rcx, [rcx+78h]; this
0x18005dd6f  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18005dd74  xor     eax, eax
0x18005dd76  jmp     short loc_18005DD98
0x18005dd78  mov     ebx, 8000FFFFh
0x18005dd7d  mov     edx, 51h ; 'Q'; void *
0x18005dd82  mov     rcx, [rsp+48h]; this
0x18005dd87  lea     r8, aShellOobeMachi_33; "shell\\oobe\\machine\\plugins\\adapters"...
0x18005dd8e  mov     r9d, ebx; char *
0x18005dd91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005dd96  mov     eax, ebx
0x18005dd98  mov     rbx, [rsp+48h+arg_0]
0x18005dd9d  mov     rsi, [rsp+48h+arg_8]
0x18005dda2  add     rsp, 40h
0x18005dda6  pop     rdi
0x18005dda7  retn
```
