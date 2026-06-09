# SettingsCopier::CopyATSettings(ATL::CRegKey &,ATL::CRegKey &)

- ea: `0x14002491c`
- end: `0x140024b9d`
- name: `?CopyATSettings@SettingsCopier@@AEAAJAEAVCRegKey@ATL@@0@Z`
- size: `641`
- prototype: `int(SettingsCopier *__hidden this, struct ATL::CRegKey *, struct ATL::CRegKey *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140025184`

## callees

- `0x140005c90`
- `0x14000966c`
- `0x14000df20`
- `0x14001c768`
- `0x14001d3ac`
- `0x14001eb04`
- `0x14002491c`
- `0x140024ba4`
- `0x140024ea0`
- `0x140025240`
- `0x140025470`
- `0x140025d70`

## import_xrefs

- `msvcrt!free` at `0x140024abf`
- `msvcrt!free` at `0x140024b52`
- `msvcrt!free` at `0x140024abf`
- `msvcrt!free` at `0x140024b52`

## string_xrefs

- `0x140024968`: `enduser\ezap\easeofaccess\atmanager\settingscopier.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SettingsCopier::CopyATSettings(SettingsCopier *this, HKEY *a2, HKEY *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v9; // rcx
  __int64 Next; // rax
  LPCWSTR *v11; // rsi
  DWORD v12; // edi
  signed int RegKeyValue; // eax
  unsigned int v14; // ebx
  BYTE *v15; // rcx
  BYTE *v16; // rbx
  LSTATUS v17; // eax
  BYTE *v18; // rcx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  DWORD lpData; // [rsp+20h] [rbp-E0h]
  DWORD dwType[2]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE *v24; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v26[3]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v27[4]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t String1[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v6 = SettingsCopier::DeleteATSettings(a3);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FC,
      (unsigned int)"enduser\\ezap\\easeofaccess\\atmanager\\settingscopier.cpp",
      (const char *)(unsigned int)v6,
      lpData);
    return v7;
  }
  v9 = *(_QWORD *)ATManager::GetAccommodations(*(_QWORD *)this);
  v25 = v9;
  if ( !v9 )
    return 0;
  do
  {
    Next = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GetNext(
             v9,
             &v25);
    v11 = *(LPCWSTR **)Next;
    if ( !*(_DWORD *)(*(_QWORD *)Next + 68LL) )
      continue;
    memset(v27, 0, 24);
    memset(v26, 0, sizeof(v26));
    v12 = 0;
    while ( 1 )
    {
      dwType[1] = 0;
      dwType[0] = 0;
      v24 = 0;
      RegKeyValue = SettingsCopier::GetRegKeyValue(*a2, *v11, v12, String1, lpData, &dwType[1], (void **)&v24, dwType);
      v14 = RegKeyValue;
      if ( RegKeyValue == 1 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_29;
        v20 = 10;
        v21 = 1;
        goto LABEL_28;
      }
      if ( RegKeyValue < 0 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_29;
        v20 = 11;
        v21 = (unsigned int)RegKeyValue;
LABEL_28:
        WPP_SF_d(v19[2], v20, WPP_fe5ab529b727364d0549539a0e90a98d_Traceguids, v21);
LABEL_29:
        v18 = v24;
        goto LABEL_30;
      }
      if ( !(unsigned int)CATUtils::IsInteractiveUser() && (unsigned __int8)IsBlockedCopyValue(String1) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_fe5ab529b727364d0549539a0e90a98d_Traceguids, v14);
        v15 = v24;
        goto LABEL_16;
      }
      v16 = v24;
      v17 = SettingsCopier::SetRegKeyValue(*a3, *v11, String1, dwType[1], v24, dwType[0]);
      if ( v17 < 0 )
        break;
      v15 = v16;
LABEL_16:
      free(v15);
      if ( ++v12 > 0x64 )
        goto LABEL_31;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_fe5ab529b727364d0549539a0e90a98d_Traceguids,
        (unsigned int)v17);
    v18 = v16;
LABEL_30:
    free(v18);
LABEL_31:
    ATL::CRegKey::Close((ATL::CRegKey *)v26);
    ATL::CRegKey::Close((ATL::CRegKey *)v27);
  }
  while ( v25 );
  return 0;
}

```

## disassembly

```asm
0x14002491c  push    rbp
0x14002491e  push    rbx
0x14002491f  push    rsi
0x140024920  push    rdi
0x140024921  push    r13
0x140024923  push    r14
0x140024925  push    r15
0x140024927  lea     rbp, [rsp-1B0h]
0x14002492f  sub     rsp, 2B0h
0x140024936  mov     rax, cs:__security_cookie
0x14002493d  xor     rax, rsp
0x140024940  mov     [rbp+1E0h+var_40], rax
0x140024947  mov     r14, r8
0x14002494a  mov     r15, rdx
0x14002494d  mov     rdi, rcx
0x140024950  mov     rcx, r8; struct ATL::CRegKey *
0x140024953  call    ?DeleteATSettings@SettingsCopier@@CAJAEAVCRegKey@ATL@@@Z; SettingsCopier::DeleteATSettings(ATL::CRegKey &)
0x140024958  mov     ebx, eax
0x14002495a  test    eax, eax
0x14002495c  jns     short loc_140024980
0x14002495e  mov     rcx, [rbp+1E8h]; this
0x140024965  mov     r9d, eax; char *
0x140024968  lea     r8, aEnduserEzapEas; "enduser\\ezap\\easeofaccess\\atmanager"...
0x14002496f  mov     edx, 1FCh; void *
0x140024974  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140024979  mov     eax, ebx
0x14002497b  jmp     loc_140024B7C
0x140024980  mov     rcx, [rdi]
0x140024983  call    ?GetAccommodations@ATManager@@QEAAAEBV?$CAtlList@PEAVAccommodation@@V?$CElementTraits@PEAVAccommodation@@@ATL@@@ATL@@XZ; ATManager::GetAccommodations(void)
0x140024988  mov     rcx, [rax]
0x14002498b  mov     [rsp+2E0h+var_290], rcx
0x140024990  test    rcx, rcx
0x140024993  jz      loc_140024B7A
0x140024999  lea     r13, WPP_GLOBAL_Control
0x1400249a0  lea     rdx, [rsp+2E0h+var_290]
0x1400249a5  call    ?GetNext@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAPEAU__POSITION@@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GetNext(__POSITION * &)
0x1400249aa  mov     rsi, [rax]
0x1400249ad  cmp     dword ptr [rsi+44h], 0
0x1400249b1  jz      loc_140024B6E
0x1400249b7  mov     [rsp+2E0h+var_270], 0
0x1400249c0  mov     [rsp+2E0h+var_268], 0
0x1400249c9  mov     [rbp+1E0h+var_260], 0
0x1400249d1  mov     [rsp+2E0h+var_288], 0
0x1400249da  mov     [rsp+2E0h+var_280], 0
0x1400249e3  mov     [rsp+2E0h+var_278], 0
0x1400249ec  xor     edi, edi
0x1400249ee  mov     [rsp+2E0h+dwType+4], 0
0x1400249f6  mov     [rsp+2E0h+dwType], 0
0x1400249fe  mov     [rsp+2E0h+var_298], 0
0x140024a07  lea     rax, [rsp+2E0h+dwType]
0x140024a0c  mov     [rsp+2E0h+var_2A8], rax; __int64
0x140024a11  lea     rax, [rsp+2E0h+var_298]
0x140024a16  mov     [rsp+2E0h+var_2B0], rax; __int64
0x140024a1b  lea     rax, [rsp+2E0h+dwType+4]
0x140024a20  mov     qword ptr [rsp+2E0h+var_2B8], rax; __int64
0x140024a25  lea     r9, [rbp+1E0h+String1]
0x140024a29  mov     r8d, edi
0x140024a2c  mov     rdx, [rsi]; lpSubKey
0x140024a2f  mov     rcx, [r15]; hKey
0x140024a32  call    ?GetRegKeyValue@SettingsCopier@@CAJPEAUHKEY__@@PEBGKPEAGKPEAKAEAV?$CHeapPtr@EVCCRTAllocator@ATL@@@ATL@@3@Z; SettingsCopier::GetRegKeyValue(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong *,ATL::CHeapPtr<uchar,ATL::CCRTAllocator> &,ulong *)
0x140024a37  mov     ebx, eax
0x140024a39  cmp     eax, 1
0x140024a3c  jz      loc_140024B21
0x140024a42  test    eax, eax
0x140024a44  js      loc_140024B05
0x140024a4a  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x140024a4f  test    eax, eax
0x140024a51  jnz     short loc_140024A92
0x140024a53  lea     rcx, [rbp+1E0h+String1]; String1
0x140024a57  call    IsBlockedCopyValue
0x140024a5c  test    al, al
0x140024a5e  jz      short loc_140024A92
0x140024a60  mov     rcx, cs:WPP_GLOBAL_Control
0x140024a67  cmp     rcx, r13
0x140024a6a  jz      short loc_140024A8B
0x140024a6c  test    byte ptr [rcx+1Ch], 10h
0x140024a70  jz      short loc_140024A8B
0x140024a72  mov     edx, 0Ch
0x140024a77  mov     r9d, ebx
0x140024a7a  lea     r8, WPP_fe5ab529b727364d0549539a0e90a98d_Traceguids
0x140024a81  mov     rcx, [rcx+10h]
0x140024a85  call    WPP_SF_d
0x140024a8a  nop
0x140024a8b  mov     rcx, [rsp+2E0h+var_298]
0x140024a90  jmp     short loc_140024ABF
0x140024a92  mov     eax, [rsp+2E0h+dwType]
0x140024a96  mov     [rsp+2E0h+var_2B8], eax; DWORD
0x140024a9a  mov     rbx, [rsp+2E0h+var_298]
0x140024a9f  mov     [rsp+2E0h+lpData], rbx; lpData
0x140024aa4  mov     r9d, [rsp+2E0h+dwType+4]; dwType
0x140024aa9  lea     r8, [rbp+1E0h+String1]; lpValueName
0x140024aad  mov     rdx, [rsi]; lpSubKey
0x140024ab0  mov     rcx, [r14]; hKey
0x140024ab3  call    ?SetRegKeyValue@SettingsCopier@@CAJPEAUHKEY__@@PEBG1KPEBEK@Z; SettingsCopier::SetRegKeyValue(HKEY__ *,ushort const *,ushort const *,ulong,uchar const *,ulong)
0x140024ab8  test    eax, eax
0x140024aba  js      short loc_140024AD5
0x140024abc  mov     rcx, rbx; Block
0x140024abf  call    cs:__imp_free
0x140024ac5  inc     edi
0x140024ac7  cmp     edi, 64h ; 'd'
0x140024aca  jbe     loc_1400249EE
0x140024ad0  jmp     loc_140024B59
0x140024ad5  mov     rcx, cs:WPP_GLOBAL_Control
0x140024adc  cmp     rcx, r13
0x140024adf  jz      short loc_140024B00
0x140024ae1  test    byte ptr [rcx+1Ch], 8
0x140024ae5  jz      short loc_140024B00
0x140024ae7  mov     edx, 0Dh
0x140024aec  mov     r9d, eax
0x140024aef  lea     r8, WPP_fe5ab529b727364d0549539a0e90a98d_Traceguids
0x140024af6  mov     rcx, [rcx+10h]
0x140024afa  call    WPP_SF_d
0x140024aff  nop
0x140024b00  mov     rcx, rbx
0x140024b03  jmp     short loc_140024B52
0x140024b05  mov     rcx, cs:WPP_GLOBAL_Control
0x140024b0c  cmp     rcx, r13
0x140024b0f  jz      short loc_140024B4D
0x140024b11  test    byte ptr [rcx+1Ch], 8
0x140024b15  jz      short loc_140024B4D
0x140024b17  mov     edx, 0Bh
0x140024b1c  mov     r9d, ebx
0x140024b1f  jmp     short loc_140024B3C
0x140024b21  mov     rcx, cs:WPP_GLOBAL_Control
0x140024b28  cmp     rcx, r13
0x140024b2b  jz      short loc_140024B4D
0x140024b2d  test    byte ptr [rcx+1Ch], 10h
0x140024b31  jz      short loc_140024B4D
0x140024b33  mov     edx, 0Ah
0x140024b38  lea     r9d, [rdx-9]
0x140024b3c  lea     r8, WPP_fe5ab529b727364d0549539a0e90a98d_Traceguids
0x140024b43  mov     rcx, [rcx+10h]
0x140024b47  call    WPP_SF_d
0x140024b4c  nop
0x140024b4d  mov     rcx, [rsp+2E0h+var_298]; Block
0x140024b52  call    cs:__imp_free
0x140024b58  nop
0x140024b59  lea     rcx, [rsp+2E0h+var_288]; this
0x140024b5e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140024b63  nop
0x140024b64  lea     rcx, [rsp+2E0h+var_270]; this
0x140024b69  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140024b6e  cmp     [rsp+2E0h+var_290], 0
0x140024b74  jnz     loc_1400249A0
0x140024b7a  xor     eax, eax
0x140024b7c  mov     rcx, [rbp+1E0h+var_40]
0x140024b83  xor     rcx, rsp; StackCookie
0x140024b86  call    __security_check_cookie
0x140024b8b  add     rsp, 2B0h
0x140024b92  pop     r15
0x140024b94  pop     r14
0x140024b96  pop     r13
0x140024b98  pop     rdi
0x140024b99  pop     rsi
0x140024b9a  pop     rbx
0x140024b9b  pop     rbp
0x140024b9c  retn
```
