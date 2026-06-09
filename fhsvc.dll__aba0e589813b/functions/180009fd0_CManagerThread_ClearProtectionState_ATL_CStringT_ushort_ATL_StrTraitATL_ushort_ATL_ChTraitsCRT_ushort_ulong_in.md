# CManagerThread::ClearProtectionState(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ulong,int)

- ea: `0x180009fd0`
- end: `0x18000a140`
- name: `?ClearProtectionState@CManagerThread@@QEAAXV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@KH@Z`
- size: `368`
- prototype: `__int64 __fastcall(__int64 **, _QWORD *, int, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18000e2f0`

## callees

- `0x180004e30`
- `0x180006dd0`
- `0x1800093e0`
- `0x180009fd0`
- `0x18000aa08`
- `0x18000ac14`
- `0x18000b5f8`
- `0x18000bc98`
- `0x18000d970`
- `0x1800104d0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180009fed`
- `KERNEL32!EnterCriticalSection` at `0x180009fed`
- `KERNEL32!LeaveCriticalSection` at `0x18000a12a`
- `KERNEL32!LeaveCriticalSection` at `0x18000a12a`

## pseudocode

```c
__int64 __fastcall CManagerThread::ClearProtectionState(__int64 **a1, _QWORD *a2, int a3, int a4)
{
  _QWORD *v7; // rax
  __int64 v8; // rcx
  int ConfigDescriptor; // eax
  __int64 v10; // rcx
  __int64 **v11; // rbx
  CConfigDescriptor *v12; // rax
  const FILETIME **v14[7]; // [rsp+30h] [rbp-38h] BYREF
  __int64 **v15; // [rsp+70h] [rbp+8h] BYREF

  v15 = a1;
  EnterCriticalSection(&CriticalSection);
  SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(&v15);
  v7 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
         v14,
         a2);
  ConfigDescriptor = CManagerThread::GetConfigDescriptor(v8, v7, &v15, 0);
  if ( ConfigDescriptor >= 0 )
  {
    v10 = 0;
    v11 = v15;
    if ( *((unsigned __int8 *)*v15 + 144) == a3 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, (unsigned int)*v15, a3, **v15);
      *((_BYTE *)*v11 + 144) = 0;
      *((_DWORD *)*v11 + 36) |= 0xFFu;
      v10 = 1;
    }
    if ( a4 && ((v12 = (CConfigDescriptor *)*v11, *((_DWORD *)*v11 + 38)) || *((_DWORD *)v12 + 37)) )
    {
      *((_DWORD *)v12 + 38) = 0;
      *((_DWORD *)*v11 + 37) = 0;
      CConfigDescriptor::CachePropertiesInRegistry((CConfigDescriptor *)*v11);
    }
    else if ( !(_DWORD)v10 )
    {
      goto LABEL_18;
    }
    v14[0] = (const FILETIME **)v11;
    if ( v11 )
      ++*((_DWORD *)v11 + 2);
    CManagerThread::PublishProtectionState(v10, v14);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      70,
      (unsigned int)&WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
      *a2,
      ConfigDescriptor);
  }
LABEL_18:
  SmartPtr<CConfigDescriptor>::~SmartPtr<CConfigDescriptor>((__int64 *)&v15);
  LeaveCriticalSection(&CriticalSection);
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(a2);
}

```

## disassembly

```asm
0x180009fd0  mov     [rsp+arg_0], rcx
0x180009fd5  push    rbx
0x180009fd6  push    rbp
0x180009fd7  push    rsi
0x180009fd8  push    rdi
0x180009fd9  sub     rsp, 48h
0x180009fdd  mov     ebp, r9d
0x180009fe0  mov     esi, r8d
0x180009fe3  mov     rdi, rdx
0x180009fe6  lea     rcx, CriticalSection; lpCriticalSection
0x180009fed  call    cs:__imp_EnterCriticalSection
0x180009ff3  lea     rcx, [rsp+68h+arg_0]
0x180009ff8  call    ??0?$SmartPtr@VCConfigDescriptor@@@@QEAA@PEAVCConfigDescriptor@@@Z; SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(CConfigDescriptor *)
0x180009ffd  mov     rdx, rdi
0x18000a000  lea     rcx, [rsp+68h+var_38]
0x18000a005  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000a00a  mov     rdx, rax
0x18000a00d  xor     r9d, r9d
0x18000a010  lea     r8, [rsp+68h+arg_0]
0x18000a015  call    ?GetConfigDescriptor@CManagerThread@@AEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$SmartPtr@VCConfigDescriptor@@@@H@Z; CManagerThread::GetConfigDescriptor(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor> &,int)
0x18000a01a  test    eax, eax
0x18000a01c  jns     short loc_18000A060
0x18000a01e  lea     rdx, WPP_GLOBAL_Control
0x18000a025  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a02c  cmp     rcx, rdx
0x18000a02f  jz      loc_18000A119
0x18000a035  test    byte ptr [rcx+1Ch], 1
0x18000a039  jz      loc_18000A119
0x18000a03f  mov     edx, 46h ; 'F'
0x18000a044  mov     dword ptr [rsp+68h+var_48], eax
0x18000a048  mov     r9, [rdi]
0x18000a04b  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000a052  mov     rcx, [rcx+10h]
0x18000a056  call    WPP_SF_Sd
0x18000a05b  jmp     loc_18000A119
0x18000a060  xor     ecx, ecx
0x18000a062  mov     rbx, [rsp+68h+arg_0]
0x18000a067  mov     r8, [rbx]
0x18000a06a  movzx   eax, byte ptr [r8+90h]
0x18000a072  cmp     eax, esi
0x18000a074  jnz     short loc_18000A0C4
0x18000a076  lea     rdx, WPP_GLOBAL_Control
0x18000a07d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a084  cmp     rcx, rdx
0x18000a087  jz      short loc_18000A0A8
0x18000a089  test    byte ptr [rcx+1Ch], 8
0x18000a08d  jz      short loc_18000A0A8
0x18000a08f  mov     edx, 47h ; 'G'
0x18000a094  mov     rax, [r8]
0x18000a097  mov     [rsp+68h+var_48], rax
0x18000a09c  mov     r9d, esi
0x18000a09f  mov     rcx, [rcx+10h]
0x18000a0a3  call    WPP_SF_dS
0x18000a0a8  mov     rax, [rbx]
0x18000a0ab  mov     byte ptr [rax+90h], 0
0x18000a0b2  mov     rax, [rbx]
0x18000a0b5  or      dword ptr [rax+90h], 0FFh
0x18000a0bf  mov     ecx, 1
0x18000a0c4  test    ebp, ebp
0x18000a0c6  jz      short loc_18000A0FE
0x18000a0c8  mov     rax, [rbx]
0x18000a0cb  cmp     dword ptr [rax+98h], 0
0x18000a0d2  jnz     short loc_18000A0DD
0x18000a0d4  cmp     dword ptr [rax+94h], 0
0x18000a0db  jz      short loc_18000A0FE
0x18000a0dd  mov     dword ptr [rax+98h], 0
0x18000a0e7  mov     rax, [rbx]
0x18000a0ea  mov     dword ptr [rax+94h], 0
0x18000a0f4  mov     rcx, [rbx]; this
0x18000a0f7  call    ?CachePropertiesInRegistry@CConfigDescriptor@@QEAAXXZ; CConfigDescriptor::CachePropertiesInRegistry(void)
0x18000a0fc  jmp     short loc_18000A102
0x18000a0fe  test    ecx, ecx
0x18000a100  jz      short loc_18000A119
0x18000a102  mov     [rsp+68h+var_38], rbx
0x18000a107  test    rbx, rbx
0x18000a10a  jz      short loc_18000A10F
0x18000a10c  inc     dword ptr [rbx+8]
0x18000a10f  lea     rdx, [rsp+68h+var_38]
0x18000a114  call    ?PublishProtectionState@CManagerThread@@AEAAXV?$SmartPtr@VCConfigDescriptor@@@@@Z; CManagerThread::PublishProtectionState(SmartPtr<CConfigDescriptor>)
0x18000a119  lea     rcx, [rsp+68h+arg_0]
0x18000a11e  call    ??1?$SmartPtr@VCConfigDescriptor@@@@QEAA@XZ; SmartPtr<CConfigDescriptor>::~SmartPtr<CConfigDescriptor>(void)
0x18000a123  lea     rcx, CriticalSection; lpCriticalSection
0x18000a12a  call    cs:__imp_LeaveCriticalSection
0x18000a130  mov     rcx, rdi
0x18000a133  add     rsp, 48h
0x18000a137  pop     rdi
0x18000a138  pop     rsi
0x18000a139  pop     rbp
0x18000a13a  pop     rbx
0x18000a13b  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
