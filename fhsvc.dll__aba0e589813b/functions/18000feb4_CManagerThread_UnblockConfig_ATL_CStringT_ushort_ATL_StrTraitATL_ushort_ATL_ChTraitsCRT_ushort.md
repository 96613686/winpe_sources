# CManagerThread::UnblockConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)

- ea: `0x18000feb4`
- end: `0x180010032`
- name: `?UnblockConfig@CManagerThread@@QEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `382`
- prototype: `__int64 __fastcall(_QWORD **, __int64 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000dd60`
- `0x18000df70`

## callees

- `0x180004e30`
- `0x18000aa08`
- `0x18000ac14`
- `0x18000b5f8`
- `0x18000bc98`
- `0x18000d910`
- `0x18000d970`
- `0x18000feb4`
- `0x1800104d0`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180010000`
- `KERNEL32!SetEvent` at `0x180010000`
- `KERNEL32!EnterCriticalSection` at `0x18000fecd`
- `KERNEL32!EnterCriticalSection` at `0x18000fecd`
- `KERNEL32!LeaveCriticalSection` at `0x180010017`
- `KERNEL32!LeaveCriticalSection` at `0x180010017`

## pseudocode

```c
__int64 __fastcall CManagerThread::UnblockConfig(_QWORD **a1, __int64 *a2)
{
  _QWORD *v3; // rax
  __int64 v4; // rcx
  int ConfigDescriptor; // eax
  unsigned int v6; // edi
  _QWORD **v7; // rax
  int v8; // r9d
  _QWORD **v10; // [rsp+40h] [rbp+8h] BYREF
  __int64 v11; // [rsp+50h] [rbp+18h] BYREF

  v10 = a1;
  EnterCriticalSection(&CriticalSection);
  SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(&v10);
  v3 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
         &v11,
         a2);
  ConfigDescriptor = CManagerThread::GetConfigDescriptor(v4, v3, &v10, 0);
  v6 = ConfigDescriptor;
  if ( ConfigDescriptor >= 0 )
  {
    v7 = v10;
    v8 = _InterlockedDecrement((volatile signed __int32 *)*v10 + 11);
    if ( v8 >= 0 )
    {
      if ( v8 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, (_DWORD)WPP_GLOBAL_Control, v8, *a2);
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, *a2);
      }
    }
    else
    {
      *((_DWORD *)*v7 + 11) = 0;
      v6 = -2147418113;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          67,
          (unsigned int)&WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
          *a2,
          255);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      66,
      (unsigned int)&WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
      *a2,
      ConfigDescriptor);
  }
  SetEvent(hEvent);
  SmartPtr<CConfigDescriptor>::~SmartPtr<CConfigDescriptor>((__int64 *)&v10);
  LeaveCriticalSection(&CriticalSection);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(a2);
  return v6;
}

```

## disassembly

```asm
0x18000feb4  mov     [rsp+arg_8], rbx
0x18000feb9  mov     [rsp+arg_0], rcx
0x18000febe  push    rdi
0x18000febf  sub     rsp, 30h
0x18000fec3  mov     rbx, rdx
0x18000fec6  lea     rcx, CriticalSection; lpCriticalSection
0x18000fecd  call    cs:__imp_EnterCriticalSection
0x18000fed3  lea     rcx, [rsp+38h+arg_0]
0x18000fed8  call    ??0?$SmartPtr@VCConfigDescriptor@@@@QEAA@PEAVCConfigDescriptor@@@Z; SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(CConfigDescriptor *)
0x18000fedd  mov     rdx, rbx
0x18000fee0  lea     rcx, [rsp+38h+arg_10]
0x18000fee5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000feea  mov     rdx, rax
0x18000feed  xor     r9d, r9d
0x18000fef0  lea     r8, [rsp+38h+arg_0]
0x18000fef5  call    ?GetConfigDescriptor@CManagerThread@@AEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$SmartPtr@VCConfigDescriptor@@@@H@Z; CManagerThread::GetConfigDescriptor(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor> &,int)
0x18000fefa  mov     edi, eax
0x18000fefc  test    eax, eax
0x18000fefe  jns     short loc_18000FF43
0x18000ff00  lea     rcx, WPP_GLOBAL_Control
0x18000ff07  mov     r10, cs:WPP_GLOBAL_Control
0x18000ff0e  cmp     r10, rcx
0x18000ff11  jz      loc_18000FFF9
0x18000ff17  test    byte ptr [r10+1Ch], 1
0x18000ff1c  jz      loc_18000FFF9
0x18000ff22  mov     edx, 42h ; 'B'
0x18000ff27  mov     dword ptr [rsp+38h+var_18], eax
0x18000ff2b  mov     rcx, [r10+10h]
0x18000ff2f  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000ff36  mov     r9, [rbx]
0x18000ff39  call    WPP_SF_Sd
0x18000ff3e  jmp     loc_18000FFF9
0x18000ff43  mov     rax, [rsp+38h+arg_0]
0x18000ff48  mov     rcx, [rax]
0x18000ff4b  or      r9d, 0FFFFFFFFh
0x18000ff4f  lock xadd [rcx+2Ch], r9d
0x18000ff55  sub     r9d, 1
0x18000ff59  jns     short loc_18000FF92
0x18000ff5b  mov     rcx, [rax]
0x18000ff5e  mov     dword ptr [rcx+2Ch], 0
0x18000ff65  mov     edi, 8000FFFFh
0x18000ff6a  lea     rcx, WPP_GLOBAL_Control
0x18000ff71  mov     rax, cs:WPP_GLOBAL_Control
0x18000ff78  cmp     rax, rcx
0x18000ff7b  jz      short loc_18000FFF9
0x18000ff7d  test    byte ptr [rax+1Ch], 1
0x18000ff81  jz      short loc_18000FFF9
0x18000ff83  mov     edx, 43h ; 'C'
0x18000ff88  mov     dword ptr [rsp+38h+var_18], edi
0x18000ff8c  mov     rcx, [rax+10h]
0x18000ff90  jmp     short loc_18000FF2F
0x18000ff92  test    r9d, r9d
0x18000ff95  jnz     short loc_18000FFC9
0x18000ff97  lea     rcx, WPP_GLOBAL_Control
0x18000ff9e  mov     rax, cs:WPP_GLOBAL_Control
0x18000ffa5  cmp     rax, rcx
0x18000ffa8  jz      short loc_18000FFF9
0x18000ffaa  test    byte ptr [rax+1Ch], 8
0x18000ffae  jz      short loc_18000FFF9
0x18000ffb0  lea     edx, [r9+44h]
0x18000ffb4  mov     r9, [rbx]
0x18000ffb7  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000ffbe  mov     rcx, [rax+10h]
0x18000ffc2  call    WPP_SF_S
0x18000ffc7  jmp     short loc_18000FFF9
0x18000ffc9  lea     rcx, WPP_GLOBAL_Control
0x18000ffd0  mov     r8, cs:WPP_GLOBAL_Control
0x18000ffd7  cmp     r8, rcx
0x18000ffda  jz      short loc_18000FFF9
0x18000ffdc  test    byte ptr [r8+1Ch], 8
0x18000ffe1  jz      short loc_18000FFF9
0x18000ffe3  mov     edx, 45h ; 'E'
0x18000ffe8  mov     rax, [rbx]
0x18000ffeb  mov     [rsp+38h+var_18], rax
0x18000fff0  mov     rcx, [r8+10h]
0x18000fff4  call    WPP_SF_dS
0x18000fff9  mov     rcx, cs:hEvent; hEvent
0x180010000  call    cs:__imp_SetEvent
0x180010006  lea     rcx, [rsp+38h+arg_0]
0x18001000b  call    ??1?$SmartPtr@VCConfigDescriptor@@@@QEAA@XZ; SmartPtr<CConfigDescriptor>::~SmartPtr<CConfigDescriptor>(void)
0x180010010  lea     rcx, CriticalSection; lpCriticalSection
0x180010017  call    cs:__imp_LeaveCriticalSection
0x18001001d  mov     rcx, rbx
0x180010020  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180010025  mov     eax, edi
0x180010027  mov     rbx, [rsp+38h+arg_8]
0x18001002c  add     rsp, 30h
0x180010030  pop     rdi
0x180010031  retn
```
