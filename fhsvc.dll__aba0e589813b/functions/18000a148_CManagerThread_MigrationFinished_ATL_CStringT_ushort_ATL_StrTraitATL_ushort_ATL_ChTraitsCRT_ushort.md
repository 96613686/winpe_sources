# CManagerThread::MigrationFinished(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)

- ea: `0x18000a148`
- end: `0x18000a24b`
- name: `?MigrationFinished@CManagerThread@@QEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `259`
- prototype: `__int64 __fastcall(const FILETIME **, _QWORD *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000dd60`
- `0x18000e5d0`

## callees

- `0x180004e30`
- `0x180006dd0`
- `0x18000a148`
- `0x18000aa08`
- `0x18000ac14`
- `0x18000b5f8`
- `0x18000bc98`
- `0x18000d970`
- `0x18000daf0`

## string_xrefs

- `0x18000a188`: `ConfigPath`

## pseudocode

```c
__int64 __fastcall CManagerThread::MigrationFinished(const FILETIME **a1, _QWORD *a2)
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
      (*v9)[18].dwLowDateTime = 255;
      v10 = v6;
      if ( v6 )
        ++*((_DWORD *)v6 + 2);
      CManagerThread::PublishProtectionState((__int64)v7, &v10);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        105,
        (unsigned int)&WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
        *a2,
        ConfigDescriptor);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, "ConfigPath");
    ConfigDescriptor = -2147024809;
  }
  SmartPtr<CConfigDescriptor>::~SmartPtr<CConfigDescriptor>((__int64 *)&v9);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(a2);
  return (unsigned int)ConfigDescriptor;
}

```

## disassembly

```asm
0x18000a148  mov     [rsp+arg_10], rbx
0x18000a14d  mov     [rsp+arg_0], rcx
0x18000a152  push    rdi
0x18000a153  sub     rsp, 30h
0x18000a157  mov     rdi, rdx
0x18000a15a  lea     rcx, [rsp+38h+arg_0]
0x18000a15f  call    ??0?$SmartPtr@VCConfigDescriptor@@@@QEAA@PEAVCConfigDescriptor@@@Z; SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(CConfigDescriptor *)
0x18000a164  cmp     qword ptr [rdi], 0
0x18000a168  jnz     short loc_18000A1A9
0x18000a16a  lea     rax, WPP_GLOBAL_Control
0x18000a171  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a178  cmp     rcx, rax
0x18000a17b  jz      short loc_18000A19F
0x18000a17d  test    byte ptr [rcx+1Ch], 1
0x18000a181  jz      short loc_18000A19F
0x18000a183  mov     edx, 68h ; 'h'
0x18000a188  lea     r9, aConfigpath; "ConfigPath"
0x18000a18f  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000a196  mov     rcx, [rcx+10h]
0x18000a19a  call    WPP_SF_s
0x18000a19f  mov     ebx, 80070057h
0x18000a1a4  jmp     loc_18000A22C
0x18000a1a9  mov     rdx, rdi
0x18000a1ac  lea     rcx, [rsp+38h+arg_8]
0x18000a1b1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000a1b6  mov     rdx, rax
0x18000a1b9  xor     r9d, r9d
0x18000a1bc  lea     r8, [rsp+38h+arg_0]
0x18000a1c1  call    ?GetConfigDescriptor@CManagerThread@@AEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$SmartPtr@VCConfigDescriptor@@@@H@Z; CManagerThread::GetConfigDescriptor(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor> &,int)
0x18000a1c6  mov     ebx, eax
0x18000a1c8  test    eax, eax
0x18000a1ca  jns     short loc_18000A203
0x18000a1cc  lea     rax, WPP_GLOBAL_Control
0x18000a1d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1da  cmp     rcx, rax
0x18000a1dd  jz      short loc_18000A22C
0x18000a1df  test    byte ptr [rcx+1Ch], 1
0x18000a1e3  jz      short loc_18000A22C
0x18000a1e5  mov     edx, 69h ; 'i'
0x18000a1ea  mov     [rsp+38h+var_18], ebx
0x18000a1ee  mov     r9, [rdi]
0x18000a1f1  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000a1f8  mov     rcx, [rcx+10h]
0x18000a1fc  call    WPP_SF_Sd
0x18000a201  jmp     short loc_18000A22C
0x18000a203  mov     rax, [rsp+38h+arg_0]
0x18000a208  mov     rcx, [rax]
0x18000a20b  mov     dword ptr [rcx+90h], 0FFh
0x18000a215  mov     [rsp+38h+arg_8], rax
0x18000a21a  test    rax, rax
0x18000a21d  jz      short loc_18000A222
0x18000a21f  inc     dword ptr [rax+8]
0x18000a222  lea     rdx, [rsp+38h+arg_8]
0x18000a227  call    ?PublishProtectionState@CManagerThread@@AEAAXV?$SmartPtr@VCConfigDescriptor@@@@@Z; CManagerThread::PublishProtectionState(SmartPtr<CConfigDescriptor>)
0x18000a22c  lea     rcx, [rsp+38h+arg_0]
0x18000a231  call    ??1?$SmartPtr@VCConfigDescriptor@@@@QEAA@XZ; SmartPtr<CConfigDescriptor>::~SmartPtr<CConfigDescriptor>(void)
0x18000a236  mov     rcx, rdi
0x18000a239  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000a23e  mov     eax, ebx
0x18000a240  mov     rbx, [rsp+38h+arg_10]
0x18000a245  add     rsp, 30h
0x18000a249  pop     rdi
0x18000a24a  retn
```
