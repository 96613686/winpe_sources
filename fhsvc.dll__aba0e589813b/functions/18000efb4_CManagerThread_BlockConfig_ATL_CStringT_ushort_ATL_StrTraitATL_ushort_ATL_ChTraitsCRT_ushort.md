# CManagerThread::BlockConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)

- ea: `0x18000efb4`
- end: `0x18000f0b0`
- name: `?BlockConfig@CManagerThread@@QEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `252`
- prototype: `__int64 __fastcall(_QWORD **, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000df70`

## callees

- `0x180004e30`
- `0x18000aa08`
- `0x18000ac14`
- `0x18000b5f8`
- `0x18000bc98`
- `0x18000d910`
- `0x18000d970`
- `0x18000efb4`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18000f07e`
- `KERNEL32!SetEvent` at `0x18000f07e`
- `KERNEL32!EnterCriticalSection` at `0x18000efcd`
- `KERNEL32!EnterCriticalSection` at `0x18000efcd`
- `KERNEL32!LeaveCriticalSection` at `0x18000f095`
- `KERNEL32!LeaveCriticalSection` at `0x18000f095`

## pseudocode

```c
__int64 __fastcall CManagerThread::BlockConfig(_QWORD **a1, _QWORD *a2)
{
  _QWORD *v3; // rax
  __int64 v4; // rcx
  int ConfigDescriptor; // eax
  unsigned int v6; // edi
  _QWORD **v8; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+50h] [rbp+18h] BYREF

  v8 = a1;
  EnterCriticalSection(&CriticalSection);
  SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(&v8);
  v3 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
         &v9,
         a2);
  ConfigDescriptor = CManagerThread::GetConfigDescriptor(v4, v3, &v8, 1);
  v6 = ConfigDescriptor;
  if ( ConfigDescriptor >= 0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)*v8 + 11);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, *a2);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      64,
      (unsigned int)&WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
      *a2,
      ConfigDescriptor);
  }
  SetEvent(hEvent);
  SmartPtr<CConfigDescriptor>::~SmartPtr<CConfigDescriptor>((__int64 *)&v8);
  LeaveCriticalSection(&CriticalSection);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(a2);
  return v6;
}

```

## disassembly

```asm
0x18000efb4  mov     [rsp+arg_8], rbx
0x18000efb9  mov     [rsp+arg_0], rcx
0x18000efbe  push    rdi
0x18000efbf  sub     rsp, 30h
0x18000efc3  mov     rbx, rdx
0x18000efc6  lea     rcx, CriticalSection; lpCriticalSection
0x18000efcd  call    cs:__imp_EnterCriticalSection
0x18000efd3  lea     rcx, [rsp+38h+arg_0]
0x18000efd8  call    ??0?$SmartPtr@VCConfigDescriptor@@@@QEAA@PEAVCConfigDescriptor@@@Z; SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(CConfigDescriptor *)
0x18000efdd  mov     rdx, rbx
0x18000efe0  lea     rcx, [rsp+38h+arg_10]
0x18000efe5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000efea  mov     rdx, rax
0x18000efed  mov     r9d, 1
0x18000eff3  lea     r8, [rsp+38h+arg_0]
0x18000eff8  call    ?GetConfigDescriptor@CManagerThread@@AEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$SmartPtr@VCConfigDescriptor@@@@H@Z; CManagerThread::GetConfigDescriptor(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor> &,int)
0x18000effd  mov     edi, eax
0x18000efff  test    eax, eax
0x18000f001  jns     short loc_18000F03A
0x18000f003  lea     rdx, WPP_GLOBAL_Control
0x18000f00a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f011  cmp     rcx, rdx
0x18000f014  jz      short loc_18000F077
0x18000f016  test    byte ptr [rcx+1Ch], 1
0x18000f01a  jz      short loc_18000F077
0x18000f01c  mov     edx, 40h ; '@'
0x18000f021  mov     [rsp+38h+var_18], eax
0x18000f025  mov     r9, [rbx]
0x18000f028  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000f02f  mov     rcx, [rcx+10h]
0x18000f033  call    WPP_SF_Sd
0x18000f038  jmp     short loc_18000F077
0x18000f03a  mov     rax, [rsp+38h+arg_0]
0x18000f03f  mov     rcx, [rax]
0x18000f042  lock inc dword ptr [rcx+2Ch]
0x18000f046  lea     rdx, WPP_GLOBAL_Control
0x18000f04d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f054  cmp     rcx, rdx
0x18000f057  jz      short loc_18000F077
0x18000f059  test    byte ptr [rcx+1Ch], 8
0x18000f05d  jz      short loc_18000F077
0x18000f05f  mov     edx, 41h ; 'A'
0x18000f064  mov     r9, [rbx]
0x18000f067  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000f06e  mov     rcx, [rcx+10h]
0x18000f072  call    WPP_SF_S
0x18000f077  mov     rcx, cs:hEvent; hEvent
0x18000f07e  call    cs:__imp_SetEvent
0x18000f084  lea     rcx, [rsp+38h+arg_0]
0x18000f089  call    ??1?$SmartPtr@VCConfigDescriptor@@@@QEAA@XZ; SmartPtr<CConfigDescriptor>::~SmartPtr<CConfigDescriptor>(void)
0x18000f08e  lea     rcx, CriticalSection; lpCriticalSection
0x18000f095  call    cs:__imp_LeaveCriticalSection
0x18000f09b  mov     rcx, rbx
0x18000f09e  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000f0a3  mov     eax, edi
0x18000f0a5  mov     rbx, [rsp+38h+arg_8]
0x18000f0aa  add     rsp, 30h
0x18000f0ae  pop     rdi
0x18000f0af  retn
```
