# CHTMLSnapinComponent::GetResultViewType(__int64,ushort * *,long *)

- ea: `0x18008df60`
- end: `0x18008e41a`
- name: `?GetResultViewType@CHTMLSnapinComponent@@UEAAJ_JPEAPEAGPEAJ@Z`
- size: `1210`
- prototype: `__int64 __fastcall(CHTMLSnapinComponent *__hidden this, __int64, unsigned __int16 **, int *)`
- caller_count: `0`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003edc`
- `0x1800063c0`
- `0x1800074d0`
- `0x18000784c`
- `0x180019670`
- `0x1800304c0`
- `0x1800304ec`
- `0x18003e914`
- `0x18003e9fc`
- `0x180057074`
- `0x1800743b4`
- `0x18007d90c`
- `0x18008dc8c`
- `0x18008df60`
- `0x1801262fc`
- `0x180126380`
- `0x180126594`
- `0x18013f010`

## import_xrefs

- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18008e205`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18008e3eb`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18008e205`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18008e3eb`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18008df94`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18008df94`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18008e1f1`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18008e3e2`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18008e1f1`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18008e3e2`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18008e1be`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18008e1be`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18008dfa6`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18008dfa6`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18008e1d3`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18008e1fb`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18008e1d3`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18008e1fb`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18008e1c9`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18008e3f7`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18008e1c9`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18008e3f7`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18008e2a5`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18008e2a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18008e28d`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18008e28d`
- `USER32!CharLowerW` at `0x18008e11f`
- `USER32!CharLowerW` at `0x18008e11f`
- `ole32!CoTaskMemAlloc` at `0x18008e182`
- `ole32!CoTaskMemAlloc` at `0x18008e182`

## string_xrefs

- `0x18008df9b`: `CHTMLSnapinComponent::GetResultViewType`

## pseudocode

```c
// Hidden C++ exception states: #wind=15 #try_helpers=1
__int64 __fastcall CHTMLSnapinComponent::GetResultViewType(
        CHTMLSnapinComponent *this,
        __int64 a2,
        unsigned __int16 **a3,
        int *a4)
{
  struct CSnapinComponentDataImpl *ComponentData; // rax
  struct CSnapinComponentDataImpl *v8; // r13
  unsigned int v9; // ebx
  const unsigned __int16 *v10; // rdx
  int v11; // r12d
  int v12; // eax
  int v13; // eax
  int v14; // eax
  unsigned int v15; // r15d
  unsigned int v16; // eax
  unsigned int v17; // r14d
  __int64 v18; // rsi
  unsigned __int16 *v19; // rbx
  unsigned __int64 v20; // rdi
  __int64 v21; // r8
  __int64 v22; // rax
  unsigned int v23; // eax
  WCHAR *Buffer; // rax
  DWORD v25; // eax
  DWORD v26; // r15d
  int v27; // eax
  int v28; // r15d
  int v29; // eax
  int v30; // eax
  mmcerror::SC *v31; // rax
  _BYTE v33[24]; // [rsp+38h] [rbp-79h] BYREF
  void **v34; // [rsp+50h] [rbp-61h] BYREF
  LPWSTR lpsz; // [rsp+58h] [rbp-59h]
  __int64 v36; // [rsp+60h] [rbp-51h]
  int v37; // [rsp+68h] [rbp-49h]
  _QWORD v38[2]; // [rsp+70h] [rbp-41h] BYREF
  __int64 v39; // [rsp+80h] [rbp-31h]
  int v40; // [rsp+88h] [rbp-29h]
  void **v41; // [rsp+90h] [rbp-21h] BYREF
  unsigned __int16 *v42; // [rsp+98h] [rbp-19h]
  __int64 v43; // [rsp+A0h] [rbp-11h]
  int v44; // [rsp+A8h] [rbp-9h]
  _QWORD v45[3]; // [rsp+B0h] [rbp-1h] BYREF
  int v46; // [rsp+C8h] [rbp+17h]

  mmcerror::SC::SC((mmcerror::SC *)v33, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v33, L"CHTMLSnapinComponent::GetResultViewType");
  if ( !a3 || !a4 )
  {
    v31 = (mmcerror::SC *)mmcerror::SC::operator=(v33, 2147549183LL);
    v9 = mmcerror::SC::ToHr(v31);
    goto LABEL_55;
  }
  ComponentData = CSnapinComponentImpl::GetComponentData(this);
  v8 = ComponentData;
  if ( !ComponentData )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 14, WPP_92046b9d13f4309e06923444decfc0b8_Traceguids);
    v9 = -2147418113;
    goto LABEL_55;
  }
  v38[0] = &CStr::`vftable';
  v38[1] = &CStr::s_rgwchEmptyStringBuffer;
  v39 = 0;
  v40 = 0;
  v10 = (const unsigned __int16 *)((char *)ComponentData + 216);
  v11 = 8;
  if ( *((_QWORD *)ComponentData + 30) >= 8u )
    v10 = *(const unsigned __int16 **)v10;
  v12 = CStr::Assign((CStr *)v38, v10);
  if ( v12 < 0 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      15,
      WPP_92046b9d13f4309e06923444decfc0b8_Traceguids,
      (unsigned int)v12);
  v41 = &CStr::`vftable';
  v42 = &CStr::s_rgwchEmptyStringBuffer;
  v43 = 0;
  v44 = 0;
  v13 = CStr::Assign((CStr *)&v41, (const struct CStr *)v38);
  if ( v13 < 0 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      16,
      WPP_92046b9d13f4309e06923444decfc0b8_Traceguids,
      (unsigned int)v13);
  v34 = &CStr::`vftable';
  lpsz = &CStr::s_rgwchEmptyStringBuffer;
  v36 = 0;
  v37 = 0;
  v14 = CStr::Assign((CStr *)&v34, (const struct CStr *)v38);
  if ( v14 < 0 && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      17,
      WPP_92046b9d13f4309e06923444decfc0b8_Traceguids,
      (unsigned int)v14);
  CharLowerW(lpsz);
  v15 = CStr::Find((CStr *)&v34, L"%windir%");
  v16 = CStr::Find((CStr *)&v34, L"%systemroot%");
  v17 = v16;
  v18 = -1;
  if ( v15 != -1 )
  {
    v17 = v15;
    goto LABEL_30;
  }
  if ( v16 != -1 )
  {
LABEL_30:
    if ( v15 == -1 )
      v11 = 12;
    v45[0] = &CStr::`vftable';
    v45[1] = &CStr::s_rgwchEmptyStringBuffer;
    v45[2] = 0;
    v46 = 0;
    Buffer = CStr::GetBuffer((CStr *)v45, 4096);
    if ( Buffer )
    {
      v25 = v15 == -1 ? GetEnvironmentVariableW(L"systemroot", Buffer, 0x1000u) : GetWindowsDirectoryW(Buffer, 0x1000u);
      v26 = v25;
      CStr::ReleaseBuffer((CStr *)v45, -1);
      if ( v26 )
      {
        v27 = CStr::AssignLeft((CStr *)&v41, (const struct CStr *)v38, v17);
        v28 = v27;
        if ( v27 < 0
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
        {
          WPP_SF_Dd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            18,
            WPP_92046b9d13f4309e06923444decfc0b8_Traceguids,
            v17,
            v27);
        }
        CStr::Append((CStr *)&v41, (const struct CStr *)v45);
        if ( v28 < 0
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
        {
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            19,
            WPP_92046b9d13f4309e06923444decfc0b8_Traceguids,
            (unsigned int)v28);
        }
        v29 = CStr::AssignMid((CStr *)&v34, (const struct CStr *)v38, v11 + v17, v39 - v11 - v17);
        if ( v29 < 0
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
        {
          WPP_SF_ddd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            20,
            WPP_92046b9d13f4309e06923444decfc0b8_Traceguids,
            v17,
            v11,
            v29);
        }
        v30 = CStr::Append((CStr *)&v41, (const struct CStr *)&v34);
        if ( v30 < 0
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
        {
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            21,
            WPP_92046b9d13f4309e06923444decfc0b8_Traceguids,
            (unsigned int)v30);
        }
      }
    }
    v45[0] = &CStr::`vftable';
    CStr::Empty((CStr *)v45);
  }
  v19 = v42;
  do
    ++v18;
  while ( v42[v18] );
  v20 = (int)v18 + 1;
  *a3 = (unsigned __int16 *)CoTaskMemAlloc(2 * v20);
  v21 = *(unsigned int *)((*(__int64 (__fastcall **)(struct CSnapinComponentDataImpl *))(*(_QWORD *)v8 + 80LL))(v8) + 20);
  *a4 = v21;
  v22 = ScCheckPointers(v45, *a3, v21);
  mmcerror::SC::operator=(v33, v22);
  mmcerror::SC::~SC((mmcerror::SC *)v45);
  if ( !(unsigned __int8)mmcerror::SC::operator bool(v33) )
  {
    v23 = StringCchCopyW(*a3, v20, v19);
    mmcerror::SC::operator=(v33, v23);
    mmcerror::SC::operator bool(v33);
  }
  v9 = mmcerror::SC::ToHr((mmcerror::SC *)v33);
  v34 = &CStr::`vftable';
  CStr::Empty((CStr *)&v34);
  v41 = &CStr::`vftable';
  CStr::Empty((CStr *)&v41);
  v38[0] = &CStr::`vftable';
  CStr::Empty((CStr *)v38);
LABEL_55:
  mmcerror::SC::~SC((mmcerror::SC *)v33);
  return v9;
}

```

## disassembly

```asm
0x18008df60  mov     rax, rsp
0x18008df63  mov     [rax+8], rbx
0x18008df67  mov     [rax+20h], r9
0x18008df6b  mov     [rax+18h], r8
0x18008df6f  push    rbp
0x18008df70  push    rsi
0x18008df71  push    rdi
0x18008df72  push    r12
0x18008df74  push    r13
0x18008df76  push    r14
0x18008df78  push    r15
0x18008df7a  lea     rbp, [rax-5Fh]
0x18008df7e  sub     rsp, 0D0h
0x18008df85  mov     rsi, r9
0x18008df88  mov     rdi, r8
0x18008df8b  mov     rbx, rcx
0x18008df8e  xor     edx, edx
0x18008df90  lea     rcx, [rbp+57h+var_D0]
0x18008df94  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x18008df9a  nop
0x18008df9b  lea     rdx, aChtmlsnapincom; "CHTMLSnapinComponent::GetResultViewType"
0x18008dfa2  lea     rcx, [rbp+57h+var_D0]
0x18008dfa6  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x18008dfac  xor     r14d, r14d
0x18008dfaf  test    rdi, rdi
0x18008dfb2  jz      loc_18008E3D9
0x18008dfb8  test    rsi, rsi
0x18008dfbb  jz      loc_18008E3D9
0x18008dfc1  mov     rcx, rbx; this
0x18008dfc4  call    ?GetComponentData@CSnapinComponentImpl@@IEAAPEAVCSnapinComponentDataImpl@@XZ; CSnapinComponentImpl::GetComponentData(void)
0x18008dfc9  mov     r13, rax
0x18008dfcc  test    rax, rax
0x18008dfcf  jnz     short loc_18008E007
0x18008dfd1  lea     rbx, WPP_GLOBAL_Control
0x18008dfd8  mov     rcx, cs:WPP_GLOBAL_Control
0x18008dfdf  cmp     rcx, rbx
0x18008dfe2  jz      short loc_18008DFFD
0x18008dfe4  cmp     byte ptr [rcx+19h], 2
0x18008dfe8  jb      short loc_18008DFFD
0x18008dfea  lea     edx, [rax+0Eh]
0x18008dfed  lea     r8, WPP_92046b9d13f4309e06923444decfc0b8_Traceguids
0x18008dff4  mov     rcx, [rcx+10h]
0x18008dff8  call    WPP_SF_
0x18008dffd  mov     ebx, 8000FFFFh
0x18008e002  jmp     loc_18008E3F3
0x18008e007  lea     rsi, ??_7CStr@@6B@; const CStr::`vftable'
0x18008e00e  mov     [rbp+57h+var_98], rsi
0x18008e012  lea     rax, ?s_rgwchEmptyStringBuffer@CStr@@0PAGA; ushort near * CStr::s_rgwchEmptyStringBuffer
0x18008e019  mov     [rbp+57h+var_90], rax
0x18008e01d  mov     [rbp+57h+var_88], r14
0x18008e021  mov     [rbp+57h+var_80], r14d
0x18008e025  lea     rdx, [r13+0D8h]
0x18008e02c  mov     r12d, 8
0x18008e032  cmp     [rdx+18h], r12
0x18008e036  jb      short loc_18008E03B
0x18008e038  mov     rdx, [rdx]; unsigned __int16 *
0x18008e03b  lea     rcx, [rbp+57h+var_98]; this
0x18008e03f  call    ?Assign@CStr@@QEAAJPEBG@Z; CStr::Assign(ushort const *)
0x18008e044  lea     rdi, WPP_92046b9d13f4309e06923444decfc0b8_Traceguids
0x18008e04b  mov     r15b, 3
0x18008e04e  lea     rbx, WPP_GLOBAL_Control
0x18008e055  test    eax, eax
0x18008e057  jns     short loc_18008E07F
0x18008e059  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e060  cmp     rcx, rbx
0x18008e063  jz      short loc_18008E07F
0x18008e065  cmp     [rcx+19h], r15b
0x18008e069  jb      short loc_18008E07F
0x18008e06b  mov     edx, 0Fh
0x18008e070  mov     r9d, eax
0x18008e073  mov     r8, rdi
0x18008e076  mov     rcx, [rcx+10h]
0x18008e07a  call    WPP_SF_d
0x18008e07f  mov     [rbp+57h+var_78], rsi
0x18008e083  lea     rax, ?s_rgwchEmptyStringBuffer@CStr@@0PAGA; ushort near * CStr::s_rgwchEmptyStringBuffer
0x18008e08a  mov     [rbp+57h+var_70], rax
0x18008e08e  mov     [rbp+57h+var_68], r14
0x18008e092  mov     [rbp+57h+var_60], r14d
0x18008e096  lea     rdx, [rbp+57h+var_98]; struct CStr *
0x18008e09a  lea     rcx, [rbp+57h+var_78]; this
0x18008e09e  call    ?Assign@CStr@@QEAAJAEBV1@@Z; CStr::Assign(CStr const &)
0x18008e0a3  test    eax, eax
0x18008e0a5  jns     short loc_18008E0CD
0x18008e0a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e0ae  cmp     rcx, rbx
0x18008e0b1  jz      short loc_18008E0CD
0x18008e0b3  cmp     [rcx+19h], r15b
0x18008e0b7  jb      short loc_18008E0CD
0x18008e0b9  mov     edx, 10h
0x18008e0be  mov     r9d, eax
0x18008e0c1  mov     r8, rdi
0x18008e0c4  mov     rcx, [rcx+10h]
0x18008e0c8  call    WPP_SF_d
0x18008e0cd  mov     [rbp+57h+var_B8], rsi
0x18008e0d1  lea     rax, ?s_rgwchEmptyStringBuffer@CStr@@0PAGA; ushort near * CStr::s_rgwchEmptyStringBuffer
0x18008e0d8  mov     [rbp+57h+lpsz], rax
0x18008e0dc  mov     [rbp+57h+var_A8], r14
0x18008e0e0  mov     [rbp+57h+var_A0], r14d
0x18008e0e4  lea     rdx, [rbp+57h+var_98]; struct CStr *
0x18008e0e8  lea     rcx, [rbp+57h+var_B8]; this
0x18008e0ec  call    ?Assign@CStr@@QEAAJAEBV1@@Z; CStr::Assign(CStr const &)
0x18008e0f1  test    eax, eax
0x18008e0f3  jns     short loc_18008E11B
0x18008e0f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e0fc  cmp     rcx, rbx
0x18008e0ff  jz      short loc_18008E11B
0x18008e101  cmp     [rcx+19h], r15b
0x18008e105  jb      short loc_18008E11B
0x18008e107  mov     edx, 11h
0x18008e10c  mov     r9d, eax
0x18008e10f  mov     r8, rdi
0x18008e112  mov     rcx, [rcx+10h]
0x18008e116  call    WPP_SF_d
0x18008e11b  mov     rcx, [rbp+57h+lpsz]; lpsz
0x18008e11f  call    cs:__imp_CharLowerW
0x18008e125  lea     rdx, aWindir; "%windir%"
0x18008e12c  lea     rcx, [rbp+57h+var_B8]; this
0x18008e130  call    ?Find@CStr@@QEBAHPEBG@Z; CStr::Find(ushort const *)
0x18008e135  mov     r15d, eax
0x18008e138  lea     rdx, aSystemroot; "%systemroot%"
0x18008e13f  lea     rcx, [rbp+57h+var_B8]; this
0x18008e143  call    ?Find@CStr@@QEBAHPEBG@Z; CStr::Find(ushort const *)
0x18008e148  mov     r14d, eax
0x18008e14b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18008e14f  cmp     r15d, esi
0x18008e152  jnz     loc_18008E23B
0x18008e158  cmp     eax, esi
0x18008e15a  jnz     loc_18008E23E
0x18008e160  lea     r15, ??_7CStr@@6B@; const CStr::`vftable'
0x18008e167  mov     rbx, [rbp+57h+var_70]
0x18008e16b  xor     r14d, r14d
0x18008e16e  inc     rsi
0x18008e171  cmp     [rbx+rsi*2], r14w
0x18008e176  jnz     short loc_18008E16E
0x18008e178  lea     eax, [rsi+1]
0x18008e17b  movsxd  rdi, eax
0x18008e17e  lea     rcx, [rdi+rdi]; cb
0x18008e182  call    cs:__imp_CoTaskMemAlloc
0x18008e188  mov     rsi, [rbp+57h+arg_10]
0x18008e18c  mov     [rsi], rax
0x18008e18f  mov     rax, [r13+0]
0x18008e193  mov     rcx, r13
0x18008e196  mov     rax, [rax+50h]
0x18008e19a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e19f  mov     r8d, [rax+14h]
0x18008e1a3  mov     rax, [rbp+57h+arg_18]
0x18008e1a7  mov     [rax], r8d
0x18008e1aa  mov     rdx, [rsi]
0x18008e1ad  lea     rcx, [rbp+57h+var_58]
0x18008e1b1  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x18008e1b6  nop
0x18008e1b7  mov     rdx, rax
0x18008e1ba  lea     rcx, [rbp+57h+var_D0]
0x18008e1be  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x18008e1c4  nop
0x18008e1c5  lea     rcx, [rbp+57h+var_58]
0x18008e1c9  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18008e1cf  lea     rcx, [rbp+57h+var_D0]
0x18008e1d3  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18008e1d9  test    al, al
0x18008e1db  jnz     short loc_18008E201
0x18008e1dd  mov     r8, rbx; unsigned __int16 *
0x18008e1e0  mov     rdx, rdi; unsigned __int64
0x18008e1e3  mov     rcx, [rsi]; unsigned __int16 *
0x18008e1e6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008e1eb  mov     edx, eax
0x18008e1ed  lea     rcx, [rbp+57h+var_D0]
0x18008e1f1  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18008e1f7  lea     rcx, [rbp+57h+var_D0]
0x18008e1fb  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18008e201  lea     rcx, [rbp+57h+var_D0]
0x18008e205  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x18008e20b  mov     ebx, eax
0x18008e20d  mov     [rbp+57h+var_B8], r15
0x18008e211  lea     rcx, [rbp+57h+var_B8]; this
0x18008e215  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x18008e21a  nop
0x18008e21b  mov     [rbp+57h+var_78], r15
0x18008e21f  lea     rcx, [rbp+57h+var_78]; this
0x18008e223  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x18008e228  nop
0x18008e229  mov     [rbp+57h+var_98], r15
0x18008e22d  lea     rcx, [rbp+57h+var_98]; this
0x18008e231  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x18008e236  jmp     loc_18008E3F3
0x18008e23b  mov     r14d, r15d
0x18008e23e  mov     eax, 0Ch
0x18008e243  cmp     r15d, esi
0x18008e246  cmovz   r12d, eax
0x18008e24a  lea     rax, ??_7CStr@@6B@; const CStr::`vftable'
0x18008e251  mov     [rbp+57h+var_58], rax
0x18008e255  lea     rax, ?s_rgwchEmptyStringBuffer@CStr@@0PAGA; ushort near * CStr::s_rgwchEmptyStringBuffer
0x18008e25c  mov     [rbp+57h+var_50], rax
0x18008e260  xor     eax, eax
0x18008e262  mov     [rbp+57h+var_48], rax
0x18008e266  mov     [rbp+57h+var_40], eax
0x18008e269  mov     edx, 1000h; int
0x18008e26e  lea     rcx, [rbp+57h+var_58]; this
0x18008e272  call    ?GetBuffer@CStr@@QEAAPEAGH@Z; CStr::GetBuffer(int)
0x18008e277  test    rax, rax
0x18008e27a  jz      loc_18008E3C0
0x18008e280  cmp     r15d, esi
0x18008e283  jz      short loc_18008E295
0x18008e285  mov     edx, 1000h; uSize
0x18008e28a  mov     rcx, rax; lpBuffer
0x18008e28d  call    cs:__imp_GetWindowsDirectoryW
0x18008e293  jmp     short loc_18008E2AB
0x18008e295  mov     r8d, 1000h; nSize
0x18008e29b  mov     rdx, rax; lpBuffer
0x18008e29e  lea     rcx, Name; "systemroot"
0x18008e2a5  call    cs:__imp_GetEnvironmentVariableW
0x18008e2ab  mov     r15d, eax
0x18008e2ae  mov     edx, esi; int
0x18008e2b0  lea     rcx, [rbp+57h+var_58]; this
0x18008e2b4  call    ?ReleaseBuffer@CStr@@QEAAXH@Z; CStr::ReleaseBuffer(int)
0x18008e2b9  test    r15d, r15d
0x18008e2bc  jz      loc_18008E3C0
0x18008e2c2  mov     r8d, r14d; unsigned int
0x18008e2c5  lea     rdx, [rbp+57h+var_98]; struct CStr *
0x18008e2c9  lea     rcx, [rbp+57h+var_78]; this
0x18008e2cd  call    ?AssignLeft@CStr@@QEAAJAEBV1@I@Z; CStr::AssignLeft(CStr const &,uint)
0x18008e2d2  mov     r15d, eax
0x18008e2d5  test    eax, eax
0x18008e2d7  jns     short loc_18008E303
0x18008e2d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e2e0  cmp     rcx, rbx
0x18008e2e3  jz      short loc_18008E303
0x18008e2e5  cmp     byte ptr [rcx+19h], 3
0x18008e2e9  jb      short loc_18008E303
0x18008e2eb  mov     edx, 12h
0x18008e2f0  mov     [rsp+100h+var_E0], eax
0x18008e2f4  mov     r9d, r14d
0x18008e2f7  mov     r8, rdi
0x18008e2fa  mov     rcx, [rcx+10h]
0x18008e2fe  call    WPP_SF_Dd
0x18008e303  lea     rdx, [rbp+57h+var_58]; struct CStr *
0x18008e307  lea     rcx, [rbp+57h+var_78]; this
0x18008e30b  call    ?Append@CStr@@QEAAJAEBV1@@Z; CStr::Append(CStr const &)
0x18008e310  test    r15d, r15d
0x18008e313  jns     short loc_18008E33B
0x18008e315  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e31c  cmp     rcx, rbx
0x18008e31f  jz      short loc_18008E33B
0x18008e321  cmp     byte ptr [rcx+19h], 3
0x18008e325  jb      short loc_18008E33B
0x18008e327  mov     edx, 13h
0x18008e32c  mov     r9d, r15d
0x18008e32f  mov     r8, rdi
0x18008e332  mov     rcx, [rcx+10h]
0x18008e336  call    WPP_SF_d
0x18008e33b  mov     r9d, dword ptr [rbp+57h+var_88]
0x18008e33f  sub     r9d, r12d
0x18008e342  sub     r9d, r14d; unsigned int
0x18008e345  lea     r8d, [r12+r14]; unsigned int
0x18008e349  lea     rdx, [rbp+57h+var_98]; struct CStr *
0x18008e34d  lea     rcx, [rbp+57h+var_B8]; this
0x18008e351  call    ?AssignMid@CStr@@QEAAJAEBV1@II@Z; CStr::AssignMid(CStr const &,uint,uint)
0x18008e356  test    eax, eax
0x18008e358  jns     short loc_18008E389
0x18008e35a  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e361  cmp     rcx, rbx
0x18008e364  jz      short loc_18008E389
0x18008e366  cmp     byte ptr [rcx+19h], 3
0x18008e36a  jb      short loc_18008E389
0x18008e36c  mov     edx, 14h
0x18008e371  mov     [rsp+28h], eax
0x18008e375  mov     [rsp+100h+var_E0], r12d
0x18008e37a  mov     r9d, r14d
0x18008e37d  mov     r8, rdi
0x18008e380  mov     rcx, [rcx+10h]
0x18008e384  call    WPP_SF_ddd
0x18008e389  lea     rdx, [rbp+57h+var_B8]; struct CStr *
0x18008e38d  lea     rcx, [rbp+57h+var_78]; this
0x18008e391  call    ?Append@CStr@@QEAAJAEBV1@@Z; CStr::Append(CStr const &)
0x18008e396  test    eax, eax
0x18008e398  jns     short loc_18008E3C0
0x18008e39a  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e3a1  cmp     rcx, rbx
0x18008e3a4  jz      short loc_18008E3C0
0x18008e3a6  cmp     byte ptr [rcx+19h], 3
0x18008e3aa  jb      short loc_18008E3C0
0x18008e3ac  mov     edx, 15h
0x18008e3b1  mov     r9d, eax
0x18008e3b4  mov     r8, rdi
0x18008e3b7  mov     rcx, [rcx+10h]
0x18008e3bb  call    WPP_SF_d
0x18008e3c0  lea     r15, ??_7CStr@@6B@; const CStr::`vftable'
0x18008e3c7  mov     [rbp+57h+var_58], r15
0x18008e3cb  lea     rcx, [rbp+57h+var_58]; this
0x18008e3cf  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x18008e3d4  jmp     loc_18008E167
0x18008e3d9  mov     edx, 8000FFFFh
0x18008e3de  lea     rcx, [rbp+57h+var_D0]
0x18008e3e2  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18008e3e8  mov     rcx, rax
0x18008e3eb  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x18008e3f1  mov     ebx, eax
0x18008e3f3  lea     rcx, [rbp+57h+var_D0]
0x18008e3f7  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18008e3fd  mov     eax, ebx
  ... truncated ...
```
