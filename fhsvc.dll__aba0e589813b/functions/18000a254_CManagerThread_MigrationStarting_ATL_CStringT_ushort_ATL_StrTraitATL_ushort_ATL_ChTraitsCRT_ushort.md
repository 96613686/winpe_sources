# CManagerThread::MigrationStarting(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)

- ea: `0x18000a254`
- end: `0x18000a357`
- name: `?MigrationStarting@CManagerThread@@QEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `259`
- prototype: `__int64 __fastcall(const FILETIME **, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000e740`

## callees

- `0x180004e30`
- `0x180006dd0`
- `0x18000a254`
- `0x18000aa08`
- `0x18000ac14`
- `0x18000b5f8`
- `0x18000bc98`
- `0x18000d970`
- `0x18000daf0`

## string_xrefs

- `0x18000a294`: `ConfigPath`

## pseudocode

```c
__int64 __fastcall CManagerThread::MigrationStarting(const FILETIME **a1, _QWORD *a2)
{
  int ConfigDescriptor; // ebx
  _QWORD *v4; // rax
  __int64 v5; // rcx
  const FILETIME **v6; // rax
  const FILETIME *v7; // rcx
  const FILETIME **v9; // [rsp+40h] [rbp+8h] BYREF
  const FILETIME **v10; // [rsp+48h] [rbp+10h] BYREF

  v9 = a1;
  SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(&v9);
  if ( *a2 )
  {
    v4 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
           &v10,
           a2);
    ConfigDescriptor = CManagerThread::GetConfigDescriptor(v5, v4, (_QWORD ***)&v9, 0);
    if ( ConfigDescriptor >= 0 )
    {
      v6 = v9;
      v7 = *v9;
      (*v9)[18].dwLowDateTime = 4;
      v10 = v6;
      if ( v6 )
        ++*((_DWORD *)v6 + 2);
      CManagerThread::PublishProtectionState((__int64)v7, &v10);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        103,
        (unsigned int)&WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
        *a2,
        ConfigDescriptor);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, "ConfigPath");
    ConfigDescriptor = -2147024809;
  }
  SmartPtr<CConfigDescriptor>::~SmartPtr<CConfigDescriptor>((__int64 *)&v9);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(a2);
  return (unsigned int)ConfigDescriptor;
}

```

## disassembly

```asm
0x18000a254  mov     [rsp+arg_10], rbx
0x18000a259  mov     [rsp+arg_0], rcx
0x18000a25e  push    rdi
0x18000a25f  sub     rsp, 30h
0x18000a263  mov     rdi, rdx
0x18000a266  lea     rcx, [rsp+38h+arg_0]
0x18000a26b  call    ??0?$SmartPtr@VCConfigDescriptor@@@@QEAA@PEAVCConfigDescriptor@@@Z; SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(CConfigDescriptor *)
0x18000a270  cmp     qword ptr [rdi], 0
0x18000a274  jnz     short loc_18000A2B5
0x18000a276  lea     rax, WPP_GLOBAL_Control
0x18000a27d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a284  cmp     rcx, rax
0x18000a287  jz      short loc_18000A2AB
0x18000a289  test    byte ptr [rcx+1Ch], 1
0x18000a28d  jz      short loc_18000A2AB
0x18000a28f  mov     edx, 66h ; 'f'
0x18000a294  lea     r9, aConfigpath; "ConfigPath"
0x18000a29b  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000a2a2  mov     rcx, [rcx+10h]
0x18000a2a6  call    WPP_SF_s
0x18000a2ab  mov     ebx, 80070057h
0x18000a2b0  jmp     loc_18000A338
0x18000a2b5  mov     rdx, rdi
0x18000a2b8  lea     rcx, [rsp+38h+arg_8]
0x18000a2bd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000a2c2  mov     rdx, rax
0x18000a2c5  xor     r9d, r9d
0x18000a2c8  lea     r8, [rsp+38h+arg_0]
0x18000a2cd  call    ?GetConfigDescriptor@CManagerThread@@AEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$SmartPtr@VCConfigDescriptor@@@@H@Z; CManagerThread::GetConfigDescriptor(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor> &,int)
0x18000a2d2  mov     ebx, eax
0x18000a2d4  test    eax, eax
0x18000a2d6  jns     short loc_18000A30F
0x18000a2d8  lea     rax, WPP_GLOBAL_Control
0x18000a2df  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2e6  cmp     rcx, rax
0x18000a2e9  jz      short loc_18000A338
0x18000a2eb  test    byte ptr [rcx+1Ch], 1
0x18000a2ef  jz      short loc_18000A338
0x18000a2f1  mov     edx, 67h ; 'g'
0x18000a2f6  mov     [rsp+38h+var_18], ebx
0x18000a2fa  mov     r9, [rdi]
0x18000a2fd  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000a304  mov     rcx, [rcx+10h]
0x18000a308  call    WPP_SF_Sd
0x18000a30d  jmp     short loc_18000A338
0x18000a30f  mov     rax, [rsp+38h+arg_0]
0x18000a314  mov     rcx, [rax]
0x18000a317  mov     dword ptr [rcx+90h], 4
0x18000a321  mov     [rsp+38h+arg_8], rax
0x18000a326  test    rax, rax
0x18000a329  jz      short loc_18000A32E
0x18000a32b  inc     dword ptr [rax+8]
0x18000a32e  lea     rdx, [rsp+38h+arg_8]
0x18000a333  call    ?PublishProtectionState@CManagerThread@@AEAAXV?$SmartPtr@VCConfigDescriptor@@@@@Z; CManagerThread::PublishProtectionState(SmartPtr<CConfigDescriptor>)
0x18000a338  lea     rcx, [rsp+38h+arg_0]
0x18000a33d  call    ??1?$SmartPtr@VCConfigDescriptor@@@@QEAA@XZ; SmartPtr<CConfigDescriptor>::~SmartPtr<CConfigDescriptor>(void)
0x18000a342  mov     rcx, rdi
0x18000a345  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000a34a  mov     eax, ebx
0x18000a34c  mov     rbx, [rsp+38h+arg_10]
0x18000a351  add     rsp, 30h
0x18000a355  pop     rdi
0x18000a356  retn
```
