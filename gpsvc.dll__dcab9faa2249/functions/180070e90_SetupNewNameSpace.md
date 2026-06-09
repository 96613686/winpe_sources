# SetupNewNameSpace

- ea: `0x180070e90`
- end: `0x18007168a`
- name: `SetupNewNameSpace`
- size: `2042`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180071890`

## callees

- `0x180003770`
- `0x18000a504`
- `0x18001d0c0`
- `0x18001d220`
- `0x18001ee6c`
- `0x18002c690`
- `0x18003d8d0`
- `0x180049bf0`
- `0x18004b090`
- `0x18004b300`
- `0x18004dfd0`
- `0x18004e164`
- `0x18004f03c`
- `0x180053510`
- `0x180070e90`
- `0x180072a08`
- `0x18007d320`
- `0x1800b5ca8`
- `0x1800b7494`
- `0x1800b74e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070fb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070fd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071041`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800710cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071231`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070fb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070fd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071041`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800710cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071231`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071447`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800710b0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180071117`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800711bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007121f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180071435`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800710b0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180071117`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800711bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007121f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180071435`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x180071037`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorControl` at `0x180071037`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18007107d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18007107d`

## string_xrefs

- `0x180071047`: `SetupNewNameSpace::SetSecurityDescriptorControl failed with %d`
- `0x180071533`: `Computer`
- `0x18007155a`: `Computer`
- `0x18007108d`: `SetupNewNameSpace::CoCreateGuid failed with 0x%x`
- `0x180071237`: `SetupNewNameSpace::CreateNameSpace couldn't allocate memory with error %d`
- `0x18007144d`: `SetupNewNameSpace::CreateNameSpace couldn't allocate memory with error %d`
- `0x180071379`: `SetupNewNameSpace::CreateNameSpace failed with 0x%x`
- `0x1800714f3`: `SetupNewNameSpace::CreateNameSpace failed with 0x%x`
- `0x18007158b`: `SetupNewNameSpace::CreateNameSpace failed with 0x%x`
- `0x1800715cf`: `SetupNewNameSpace::computer part of rsop failed with 0x%x`

## pseudocode

```c
__int64 __fastcall SetupNewNameSpace(
        __int64 *a1,
        __int64 a2,
        _WORD *a3,
        void *a4,
        struct IWbemLocator *a5,
        char a6,
        _DWORD *a7)
{
  int v10; // ebx
  struct _SECURITY_DESCRIPTOR *SelfRelativeSD; // rax
  PSECURITY_DESCRIPTOR Src; // r14
  DWORD LastError; // eax
  signed int v14; // eax
  signed int v15; // r15d
  DWORD v16; // eax
  HRESULT v17; // eax
  __int64 v18; // r9
  const unsigned __int16 *v19; // r8
  HLOCAL v20; // rax
  unsigned __int16 *v21; // rdi
  DWORD v22; // eax
  __int64 v23; // rsi
  int v24; // eax
  HLOCAL v25; // rax
  unsigned __int16 *v26; // rbx
  __int64 v27; // rax
  int v28; // eax
  HLOCAL v29; // rax
  unsigned __int16 *v30; // rsi
  _WORD *v31; // r15
  __int64 v32; // rax
  HLOCAL v33; // rax
  DWORD v34; // eax
  void **v35; // rcx
  __int64 v36; // r10
  int v37; // eax
  unsigned __int16 *v38; // rdi
  unsigned __int16 *v39; // rsi
  int v40; // esi
  _WORD *v41; // r15
  __int64 v42; // rax
  _WORD *v43; // rax
  DWORD v44; // eax
  __int64 v45; // r10
  int v46; // eax
  int v47; // esi
  unsigned int v48; // edi
  __int64 v49; // rdi
  int v50; // eax
  _DWORD *v51; // rbx
  int v53; // [rsp+20h] [rbp-E0h]
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+80h] [rbp-80h] BYREF
  _WORD *v55; // [rsp+88h] [rbp-78h] BYREF
  void *v56; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v57; // [rsp+98h] [rbp-68h]
  __int64 v58; // [rsp+A0h] [rbp-60h]
  _BYTE v59[40]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v60; // [rsp+D0h] [rbp-30h] BYREF
  struct IWbemLocator *v61; // [rsp+D8h] [rbp-28h]
  _DWORD *v62; // [rsp+E0h] [rbp-20h]
  unsigned __int16 *v63; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int16 *v64; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 *v65; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int64 v66; // [rsp+100h] [rbp+0h]
  __int64 v67; // [rsp+108h] [rbp+8h]
  __int64 *v68; // [rsp+110h] [rbp+10h]
  GUID pguid; // [rsp+118h] [rbp+18h] BYREF

  v61 = a5;
  v62 = a7;
  LODWORD(v56) = a6 & 0x10;
  v55 = a3;
  v68 = a1;
  pguid = 0;
  v65 = 0;
  v64 = 0;
  v63 = 0;
  v60 = 0;
  if ( (a6 & 0x10) != 0 || (a6 & 0xC) != 0 )
  {
    v10 = a6 & 2;
    if ( (a6 & 2) == 0 )
    {
      CDebugWrapper::Msg((CDebugWrapper *)dbgRsop, 2u, L"SetupNewNameSpace::invalid flag parameters");
LABEL_18:
      v15 = -2147024809;
      goto LABEL_82;
    }
  }
  else
  {
    v10 = a6 & 2;
  }
  pSecurityDescriptor = 0;
  CSecDesc::CSecDesc((CSecDesc *)v59);
  *a1 = 0;
  CSecDesc::AddLocalSystem((CSecDesc *)v59, 393279, 2);
  CSecDesc::AddAdministrators((CSecDesc *)v59, 393279, 2);
  if ( v10 )
    CSecDesc::AddNetworkService((CSecDesc *)v59, 393279, 2);
  CSecDesc::AddSid((CSecDesc *)v59, a4, (a6 & 0x10) != 0 ? 131107 : 393279, 2);
  CSecDesc::AddAdministratorsAsOwner((CSecDesc *)v59);
  CSecDesc::AddAdministratorsAsGroup((CSecDesc *)v59);
  SelfRelativeSD = CSecDesc::MakeSelfRelativeSD((CSecDesc *)v59);
  XPtrLF<_SECURITY_DESCRIPTOR>::operator=(&pSecurityDescriptor, SelfRelativeSD);
  Src = pSecurityDescriptor;
  if ( !pSecurityDescriptor )
  {
    LastError = GetLastError();
    CDebugWrapper::Msg((CDebugWrapper *)dbgRsop, 2u, L"SetupNewNameSpace::Makeselfrelativesd failed with %d", LastError);
    goto LABEL_8;
  }
  if ( !SetSecurityDescriptorControl(pSecurityDescriptor, 0x1000u, 0x1000u) )
  {
    v16 = GetLastError();
    CDebugWrapper::Msg(
      (CDebugWrapper *)dbgRsop,
      2u,
      L"SetupNewNameSpace::SetSecurityDescriptorControl failed with %d",
      v16);
    goto LABEL_8;
  }
  if ( v10 && !a3 )
  {
    CSecDesc::~CSecDesc((CSecDesc *)v59);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&pSecurityDescriptor);
    goto LABEL_18;
  }
  v17 = CoCreateGuid(&pguid);
  v15 = v17;
  if ( v17 < 0 )
  {
    v18 = (unsigned int)v17;
    v19 = L"SetupNewNameSpace::CoCreateGuid failed with 0x%x";
LABEL_21:
    CDebugWrapper::Msg((CDebugWrapper *)dbgRsop, 2u, v19, v18);
    goto LABEL_10;
  }
  v20 = LocalAlloc(0x40u, 0x2Au);
  XPtrLF<unsigned short>::operator=((void **)&v64, v20);
  v21 = v64;
  if ( !v64 )
    goto LABEL_23;
  if ( a3 )
  {
    v23 = -1;
    do
      ++v23;
    while ( v55[v23] );
  }
  else
  {
    LODWORD(v23) = 0;
  }
  v24 = 2 * v23;
  if ( !v10 )
    v24 = v23;
  v57 = (unsigned int)(v24 + 50);
  v25 = LocalAlloc(0x40u, 2 * v57);
  XPtrLF<unsigned short>::operator=((void **)&v63, v25);
  v26 = v63;
  if ( !v63 )
  {
LABEL_23:
    v22 = GetLastError();
    CDebugWrapper::Msg((CDebugWrapper *)dbgRsop, 2u, L"SetupNewNameSpace::Not enough Space. Error - 0x%x", v22);
LABEL_8:
    v14 = GetLastError();
    v15 = v14;
    if ( v14 > 0 )
      v15 = (unsigned __int16)v14 | 0x80070000;
    goto LABEL_10;
  }
  v15 = StringCchPrintfW(v21, 0x15u, L"\\\\%s\\Root\\Rsop", L".");
  if ( v15 >= 0 )
  {
    v15 = StringCchCopyW(v26, v57, L"\\\\.\\Root\\Rsop");
    if ( v15 >= 0 )
    {
      v27 = -1;
      do
        ++v27;
      while ( v26[v27] );
      v67 = v27;
      CDebugWrapper::Msg((CDebugWrapper *)dbgRsop, 4u, L"SetupNewNameSpace: Creating new NameSpace <%s>", v21);
      v28 = 100;
      if ( (int)v23 > 100 )
        v28 = v23;
      v66 = (unsigned int)(v28 + 1);
      v29 = LocalAlloc(0x40u, 2LL * (unsigned int)v66);
      XPtrLF<unsigned short>::operator=((void **)&v65, v29);
      v30 = v65;
      if ( !v65 )
      {
        v15 = -2147024882;
        v19 = L"SetupNewNameSpace::AllocMem failed with 0x%x";
        v18 = 2147942414LL;
        goto LABEL_21;
      }
      if ( (_DWORD)v56 )
      {
        v31 = v55;
        v32 = -1;
        do
          ++v32;
        while ( v55[v32] );
        v58 = v32 + 1;
        v33 = LocalAlloc(0x40u, 2 * (v32 + 1));
        v56 = v33;
        if ( !v33 )
        {
          v34 = GetLastError();
          CDebugWrapper::Msg(
            (CDebugWrapper *)dbgRsop,
            2u,
            L"SetupNewNameSpace::CreateNameSpace couldn't allocate memory with error %d",
            v34);
          v35 = &v56;
LABEL_44:
          XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(v35);
          CSecDesc::~CSecDesc((CSecDesc *)v59);
          XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&pSecurityDescriptor);
          v15 = -2147024882;
          goto LABEL_82;
        }
        ConvertSidToWMIName(v31, v58, v33);
        v15 = StringCchPrintfW(v30, v66, L"%s%s", L"NS", v36);
        XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&v56);
      }
      else
      {
        v15 = StringCchPrintfW(
                v65,
                v66,
                L"%s%08lX_%04X_%04X_%02X%02X_%02X%02X%02X%02X%02X%02X",
                L"NS",
                pguid.Data1,
                pguid.Data2,
                pguid.Data3,
                pguid.Data4[0],
                pguid.Data4[1],
                pguid.Data4[2],
                pguid.Data4[3],
                pguid.Data4[4],
                pguid.Data4[5],
                pguid.Data4[6],
                pguid.Data4[7]);
      }
      if ( v15 < 0 )
        goto LABEL_10;
      v37 = CreateAndCopyNameSpace(v61, 0, Src, (__int64)&v60);
      v15 = v37;
      if ( v37 < 0 )
      {
        v18 = (unsigned int)v37;
        v19 = L"SetupNewNameSpace::CreateNameSpace failed with 0x%x";
        goto LABEL_21;
      }
      v38 = &v26[v67];
      if ( v62 )
        *v62 &= 0xFFFFFFFC;
      v15 = StringCchCatW(v38, v57 - (v38 - v26), L"\\");
      if ( v15 < 0 )
        goto LABEL_10;
      v39 = v38 + 1;
      LODWORD(v56) = a6 & 1;
      if ( (a6 & 1) != 0 || (a6 & 4) != 0 )
      {
        v15 = StringCchCopyW(v39, v57 - (v39 - v26), L"User");
        if ( v15 < 0 )
          goto LABEL_10;
        v40 = 1;
      }
      else
      {
        v41 = v55;
        v42 = -1;
        do
          ++v42;
        while ( v55[v42] );
        v58 = v42 + 1;
        v43 = LocalAlloc(0x40u, 2 * (v42 + 1));
        v55 = v43;
        if ( !v43 )
        {
          v44 = GetLastError();
          CDebugWrapper::Msg(
            (CDebugWrapper *)dbgRsop,
            2u,
            L"SetupNewNameSpace::CreateNameSpace couldn't allocate memory with error %d",
            v44);
          v35 = (void **)&v55;
          goto LABEL_44;
        }
        ConvertSidToWMIName(v41, v58, v43);
        v15 = StringCchPrintfW(v39, v57 - (v39 - v26), L"User\\%s", v45);
        if ( v15 < 0 )
        {
          XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v55);
          goto LABEL_10;
        }
        v40 = 5;
        XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v55);
      }
      v58 = v60;
      v46 = CreateAndCopyNameSpace(v61, v40, Src, 0);
      v47 = v46;
      if ( v46 < 0 )
        CDebugWrapper::Msg(
          (CDebugWrapper *)dbgRsop,
          2u,
          L"SetupNewNameSpace::CreateNameSpace failed with 0x%x",
          (unsigned int)v46);
      if ( (_DWORD)v56 )
        v48 = 1;
      else
        v48 = (~a6 & 8 | 2u) >> 1;
      v15 = StringCchCopyW(&v26[v67 + 1], v57 - ((2 * (v67 + 1)) >> 1), L"Computer");
      if ( v15 >= 0 )
      {
        v53 = v48;
        v49 = v58;
        v50 = CreateAndCopyNameSpace(v61, v53, Src, 0);
        v15 = v50;
        if ( v50 < 0 )
          CDebugWrapper::Msg(
            (CDebugWrapper *)dbgRsop,
            2u,
            L"SetupNewNameSpace::CreateNameSpace failed with 0x%x",
            (unsigned int)v50);
        v51 = v62;
        if ( v47 < 0 && v62 )
        {
          CDebugWrapper::Msg(
            (CDebugWrapper *)dbgRsop,
            2u,
            L"SetupNewNameSpace::User part of rsop failed with 0x%x",
            (unsigned int)v47);
          *v51 |= 1u;
        }
        if ( v15 < 0 && v51 )
        {
          CDebugWrapper::Msg(
            (CDebugWrapper *)dbgRsop,
            2u,
            L"SetupNewNameSpace::computer part of rsop failed with 0x%x",
            (unsigned int)v15);
          *v51 |= 2u;
        }
        if ( v47 < 0 )
        {
          CSecDesc::~CSecDesc((CSecDesc *)v59);
          XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&pSecurityDescriptor);
          v15 = v47;
          goto LABEL_82;
        }
        if ( v15 >= 0 )
        {
          CDebugWrapper::Msg((CDebugWrapper *)dbgRsop, 4u, L"SetupNewNameSpace: Returning Successfully");
          v60 = 0;
          *v68 = v49;
          CSecDesc::~CSecDesc((CSecDesc *)v59);
          XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&pSecurityDescriptor);
          v15 = 0;
          goto LABEL_82;
        }
      }
    }
  }
LABEL_10:
  CSecDesc::~CSecDesc((CSecDesc *)v59);
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&pSecurityDescriptor);
LABEL_82:
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v60);
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v63);
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v64);
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v65);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180070e90  mov     [rsp-8+arg_8], rbx
0x180070e95  push    rbp
0x180070e96  push    rsi
0x180070e97  push    rdi
0x180070e98  push    r12
0x180070e9a  push    r13
0x180070e9c  push    r14
0x180070e9e  push    r15
0x180070ea0  lea     rbp, [rsp-30h]
0x180070ea5  sub     rsp, 130h
0x180070eac  mov     rax, cs:__security_cookie
0x180070eb3  xor     rax, rsp
0x180070eb6  mov     [rbp+60h+var_38], rax
0x180070eba  mov     rax, [rbp+60h+arg_20]
0x180070ec1  xor     r12d, r12d
0x180070ec4  mov     ebx, dword ptr [rbp+60h+arg_28]
0x180070eca  xorps   xmm0, xmm0
0x180070ecd  mov     edi, ebx
0x180070ecf  mov     [rbp+60h+var_88], rax
0x180070ed3  mov     rax, [rbp+60h+arg_30]
0x180070eda  and     edi, 10h
0x180070edd  mov     [rbp+60h+var_80], rax
0x180070ee1  mov     r14, r9
0x180070ee4  mov     dword ptr [rbp+60h+var_D0], edi
0x180070ee7  mov     rsi, r8
0x180070eea  mov     [rbp+60h+var_D8], r8
0x180070eee  mov     r15, rcx
0x180070ef1  mov     [rbp+60h+var_50], rcx
0x180070ef5  movups  xmmword ptr [rbp+60h+pguid.Data1], xmm0
0x180070ef9  mov     [rbp+60h+var_68], r12
0x180070efd  mov     [rbp+60h+var_70], r12
0x180070f01  mov     [rbp+60h+var_78], r12
0x180070f05  mov     [rbp+60h+var_90], r12
0x180070f09  jnz     loc_180071005
0x180070f0f  test    bl, 0Ch
0x180070f12  jnz     loc_180071005
0x180070f18  lea     r13d, [r12+2]
0x180070f1d  and     ebx, r13d
0x180070f20  lea     rcx, [rbp+60h+var_B8]; this
0x180070f24  mov     [rbp+60h+pSecurityDescriptor], r12
0x180070f28  call    ??0CSecDesc@@QEAA@XZ; CSecDesc::CSecDesc(void)
0x180070f2d  mov     [r15], r12
0x180070f30  lea     rcx, [rbp+60h+var_B8]; this
0x180070f34  mov     r15d, 6003Fh
0x180070f3a  mov     r8d, r13d; unsigned int
0x180070f3d  mov     edx, r15d; unsigned int
0x180070f40  call    ?AddLocalSystem@CSecDesc@@QEAAHKK@Z; CSecDesc::AddLocalSystem(ulong,ulong)
0x180070f45  mov     r8d, r13d; unsigned int
0x180070f48  lea     rcx, [rbp+60h+var_B8]; this
0x180070f4c  mov     edx, r15d; unsigned int
0x180070f4f  call    ?AddAdministrators@CSecDesc@@QEAAHKK@Z; CSecDesc::AddAdministrators(ulong,ulong)
0x180070f54  test    ebx, ebx
0x180070f56  jz      short loc_180070F67
0x180070f58  mov     r8d, r13d; unsigned int
0x180070f5b  lea     rcx, [rbp+60h+var_B8]; this
0x180070f5f  mov     edx, r15d; unsigned int
0x180070f62  call    ?AddNetworkService@CSecDesc@@QEAAHKK@Z; CSecDesc::AddNetworkService(ulong,ulong)
0x180070f67  mov     eax, edi
0x180070f69  lea     rcx, [rbp+60h+var_B8]; this
0x180070f6d  neg     eax
0x180070f6f  mov     r9d, r13d; unsigned int
0x180070f72  mov     rdx, r14; void *
0x180070f75  sbb     r8d, r8d
0x180070f78  and     r8d, 0FFFBFFE4h
0x180070f7f  add     r8d, r15d; unsigned int
0x180070f82  call    ?AddSid@CSecDesc@@QEAAHPEAXKK@Z; CSecDesc::AddSid(void *,ulong,ulong)
0x180070f87  lea     rcx, [rbp+60h+var_B8]; this
0x180070f8b  call    ?AddAdministratorsAsOwner@CSecDesc@@QEAAHXZ; CSecDesc::AddAdministratorsAsOwner(void)
0x180070f90  lea     rcx, [rbp+60h+var_B8]; this
0x180070f94  call    ?AddAdministratorsAsGroup@CSecDesc@@QEAAHXZ; CSecDesc::AddAdministratorsAsGroup(void)
0x180070f99  lea     rcx, [rbp+60h+var_B8]; this
0x180070f9d  call    ?MakeSelfRelativeSD@CSecDesc@@QEAAPEAU_SECURITY_DESCRIPTOR@@XZ; CSecDesc::MakeSelfRelativeSD(void)
0x180070fa2  mov     rdx, rax
0x180070fa5  lea     rcx, [rbp+60h+pSecurityDescriptor]
0x180070fa9  call    ??4?$XPtrLF@U_SECURITY_DESCRIPTOR@@@@QEAAPEAU_SECURITY_DESCRIPTOR@@PEAU1@@Z; XPtrLF<_SECURITY_DESCRIPTOR>::operator=(_SECURITY_DESCRIPTOR *)
0x180070fae  mov     r14, [rbp+60h+pSecurityDescriptor]
0x180070fb2  test    r14, r14
0x180070fb5  jnz     short loc_18007102C
0x180070fb7  call    cs:__imp_GetLastError
0x180070fbd  lea     r8, aSetupnewnamesp_2; "SetupNewNameSpace::Makeselfrelativesd f"...
0x180070fc4  mov     r9d, eax
0x180070fc7  lea     rcx, ?dbgRsop@@3VCDebugWrapper@@A; this
0x180070fce  mov     edx, r13d; unsigned int
0x180070fd1  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x180070fd6  call    cs:__imp_GetLastError
0x180070fdc  mov     r15d, eax
0x180070fdf  test    eax, eax
0x180070fe1  jle     short loc_180070FEE
0x180070fe3  movzx   r15d, ax
0x180070fe7  or      r15d, 80070000h
0x180070fee  lea     rcx, [rbp+60h+var_B8]; this
0x180070ff2  call    ??1CSecDesc@@QEAA@XZ; CSecDesc::~CSecDesc(void)
0x180070ff7  lea     rcx, [rbp+60h+pSecurityDescriptor]
0x180070ffb  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x180071000  jmp     loc_18007163C
0x180071005  mov     r13d, 2
0x18007100b  and     ebx, r13d
0x18007100e  jnz     loc_180070F20
0x180071014  lea     r8, aSetupnewnamesp_7; "SetupNewNameSpace::invalid flag paramet"...
0x18007101b  mov     edx, r13d; unsigned int
0x18007101e  lea     rcx, ?dbgRsop@@3VCDebugWrapper@@A; this
0x180071025  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x18007102a  jmp     short loc_18007106E
0x18007102c  mov     edx, 1000h; ControlBitsOfInterest
0x180071031  mov     rcx, r14; pSecurityDescriptor
0x180071034  mov     r8d, edx; ControlBitsToSet
0x180071037  call    cs:__imp_SetSecurityDescriptorControl
0x18007103d  test    eax, eax
0x18007103f  jnz     short loc_180071053
0x180071041  call    cs:__imp_GetLastError
0x180071047  lea     r8, aSetupnewnamesp_8; "SetupNewNameSpace::SetSecurityDescripto"...
0x18007104e  jmp     loc_180070FC4
0x180071053  test    ebx, ebx
0x180071055  jz      short loc_180071079
0x180071057  test    rsi, rsi
0x18007105a  jnz     short loc_180071079
0x18007105c  lea     rcx, [rbp+60h+var_B8]; this
0x180071060  call    ??1CSecDesc@@QEAA@XZ; CSecDesc::~CSecDesc(void)
0x180071065  lea     rcx, [rbp+60h+pSecurityDescriptor]
0x180071069  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18007106e  mov     r15d, 80070057h
0x180071074  jmp     loc_18007163C
0x180071079  lea     rcx, [rbp+60h+pguid]; pguid
0x18007107d  call    cs:__imp_CoCreateGuid
0x180071083  mov     r15d, eax
0x180071086  test    eax, eax
0x180071088  jns     short loc_1800710A8
0x18007108a  mov     r9d, eax
0x18007108d  lea     r8, aSetupnewnamesp; "SetupNewNameSpace::CoCreateGuid failed "...
0x180071094  lea     rcx, ?dbgRsop@@3VCDebugWrapper@@A; this
0x18007109b  mov     edx, r13d; unsigned int
0x18007109e  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800710a3  jmp     loc_180070FEE
0x1800710a8  mov     edx, 2Ah ; '*'; uBytes
0x1800710ad  lea     ecx, [rdx+16h]; uFlags
0x1800710b0  call    cs:__imp_LocalAlloc
0x1800710b6  mov     rdx, rax
0x1800710b9  lea     rcx, [rbp+60h+var_70]
0x1800710bd  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x1800710c2  mov     rdi, [rbp+60h+var_70]
0x1800710c6  test    rdi, rdi
0x1800710c9  jnz     short loc_1800710DD
0x1800710cb  call    cs:__imp_GetLastError
0x1800710d1  lea     r8, aSetupnewnamesp_11; "SetupNewNameSpace::Not enough Space. Er"...
0x1800710d8  jmp     loc_180070FC4
0x1800710dd  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800710e1  xor     r15d, r15d
0x1800710e4  test    rsi, rsi
0x1800710e7  jnz     short loc_1800710EE
0x1800710e9  mov     esi, r15d
0x1800710ec  jmp     short loc_1800710FF
0x1800710ee  mov     rax, [rbp+60h+var_D8]
0x1800710f2  mov     rsi, r12
0x1800710f5  inc     rsi
0x1800710f8  cmp     [rax+rsi*2], r15w
0x1800710fd  jnz     short loc_1800710F5
0x1800710ff  lea     eax, [rsi+rsi]
0x180071102  test    ebx, ebx
0x180071104  mov     ecx, 40h ; '@'; uFlags
0x180071109  cmovz   eax, esi
0x18007110c  add     eax, 32h ; '2'
0x18007110f  mov     [rbp+60h+var_C8], rax
0x180071113  lea     rdx, [rax+rax]; uBytes
0x180071117  call    cs:__imp_LocalAlloc
0x18007111d  mov     rdx, rax
0x180071120  lea     rcx, [rbp+60h+var_78]
0x180071124  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x180071129  mov     rbx, [rbp+60h+var_78]
0x18007112d  test    rbx, rbx
0x180071130  jz      short loc_1800710CB
0x180071132  lea     r9, asc_1800C3A80; "."
0x180071139  mov     edx, 15h; unsigned __int64
0x18007113e  lea     r8, aSRootRsop; "\\\\%s\\Root\\Rsop"
0x180071145  mov     rcx, rdi; unsigned __int16 *
0x180071148  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007114d  mov     r15d, eax
0x180071150  test    eax, eax
0x180071152  js      loc_180070FEE
0x180071158  mov     rdx, [rbp+60h+var_C8]; unsigned __int64
0x18007115c  lea     r8, aRootRsop_1; "\\\\.\\Root\\Rsop"
0x180071163  mov     rcx, rbx; unsigned __int16 *
0x180071166  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007116b  xor     ecx, ecx
0x18007116d  mov     r15d, eax
0x180071170  test    eax, eax
0x180071172  js      loc_180070FEE
0x180071178  mov     rax, r12
0x18007117b  inc     rax
0x18007117e  cmp     [rbx+rax*2], cx
0x180071182  jnz     short loc_18007117B
0x180071184  lea     r12, ?dbgRsop@@3VCDebugWrapper@@A; CDebugWrapper dbgRsop
0x18007118b  mov     [rbp+60h+var_58], rax
0x18007118f  mov     rcx, r12; this
0x180071192  lea     r8, aSetupnewnamesp_4; "SetupNewNameSpace: Creating new NameSpa"...
0x180071199  mov     r9, rdi
0x18007119c  mov     edx, 4; unsigned int
0x1800711a1  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800711a6  mov     eax, 64h ; 'd'
0x1800711ab  mov     ecx, 40h ; '@'; uFlags
0x1800711b0  cmp     esi, eax
0x1800711b2  cmovg   eax, esi
0x1800711b5  inc     eax
0x1800711b7  mov     [rbp+60h+var_60], rax
0x1800711bb  lea     rdx, [rax+rax]; uBytes
0x1800711bf  call    cs:__imp_LocalAlloc
0x1800711c5  mov     rdx, rax
0x1800711c8  lea     rcx, [rbp+60h+var_68]
0x1800711cc  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x1800711d1  mov     rsi, [rbp+60h+var_68]
0x1800711d5  xor     ecx, ecx
0x1800711d7  test    rsi, rsi
0x1800711da  jnz     short loc_1800711F4
0x1800711dc  mov     r15d, 8007000Eh
0x1800711e2  lea     r8, aSetupnewnamesp_10; "SetupNewNameSpace::AllocMem failed with"...
0x1800711e9  mov     r9d, r15d
0x1800711ec  mov     rcx, r12
0x1800711ef  jmp     loc_18007109B
0x1800711f4  cmp     dword ptr [rbp+60h+var_D0], ecx
0x1800711f7  jz      loc_1800712B1
0x1800711fd  mov     r15, [rbp+60h+var_D8]
0x180071201  or      rax, 0FFFFFFFFFFFFFFFFh
0x180071205  inc     rax
0x180071208  cmp     [r15+rax*2], cx
0x18007120d  jnz     short loc_180071205
0x18007120f  inc     rax
0x180071212  mov     ecx, 40h ; '@'; uFlags
0x180071217  mov     [rbp+60h+var_C0], rax
0x18007121b  lea     rdx, [rax+rax]; uBytes
0x18007121f  call    cs:__imp_LocalAlloc
0x180071225  mov     [rbp+60h+var_D0], rax
0x180071229  mov     r10, rax
0x18007122c  test    rax, rax
0x18007122f  jnz     short loc_180071272
0x180071231  call    cs:__imp_GetLastError
0x180071237  lea     r8, aSetupnewnamesp_3; "SetupNewNameSpace::CreateNameSpace coul"...
0x18007123e  mov     edx, r13d; unsigned int
0x180071241  mov     r9d, eax
0x180071244  mov     rcx, r12; this
0x180071247  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x18007124c  lea     rcx, [rbp+60h+var_D0]
0x180071250  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x180071255  lea     rcx, [rbp+60h+var_B8]; this
0x180071259  call    ??1CSecDesc@@QEAA@XZ; CSecDesc::~CSecDesc(void)
0x18007125e  lea     rcx, [rbp+60h+pSecurityDescriptor]
0x180071262  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x180071267  mov     r15d, 8007000Eh
0x18007126d  jmp     loc_18007163C
0x180071272  mov     rdx, [rbp+60h+var_C0]
0x180071276  mov     r8, r10
0x180071279  mov     rcx, r15
0x18007127c  call    ConvertSidToWMIName
0x180071281  mov     rdx, [rbp+60h+var_60]; unsigned __int64
0x180071285  lea     r9, aNs; "NS"
0x18007128c  lea     r8, aSS_0; "%s%s"
0x180071293  mov     qword ptr [rsp+160h+var_140], r10
0x180071298  mov     rcx, rsi; unsigned __int16 *
0x18007129b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800712a0  lea     rcx, [rbp+60h+var_D0]
0x1800712a4  mov     r15d, eax
0x1800712a7  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800712ac  jmp     loc_180071340
0x1800712b1  movzx   eax, [rbp+60h+pguid.Data4+7]
0x1800712b5  movzx   ecx, [rbp+60h+pguid.Data4+6]
0x1800712b9  movzx   edx, [rbp+60h+pguid.Data4+5]
0x1800712bd  movzx   r8d, [rbp+60h+pguid.Data4+4]
0x1800712c2  movzx   r9d, [rbp+60h+pguid.Data4+3]
0x1800712c7  movzx   r10d, [rbp+60h+pguid.Data4+2]
0x1800712cc  movzx   r11d, [rbp+60h+pguid.Data4+1]
0x1800712d1  movzx   r15d, [rbp+60h+pguid.Data4]
0x1800712d6  movzx   r12d, [rbp+60h+pguid.Data3]
0x1800712db  movzx   r13d, [rbp+60h+pguid.Data2]
0x1800712e0  mov     [rsp+160h+var_F0], eax
0x1800712e4  mov     eax, [rbp+60h+pguid.Data1]
0x1800712e7  mov     [rsp+160h+var_F8], ecx
0x1800712eb  mov     rcx, rsi; unsigned __int16 *
0x1800712ee  mov     [rsp+160h+var_100], edx
0x1800712f2  mov     rdx, [rbp+60h+var_60]; unsigned __int64
0x1800712f6  mov     [rsp+160h+var_108], r8d
0x1800712fb  lea     r8, aS08lx04x04x02x; "%s%08lX_%04X_%04X_%02X%02X_%02X%02X%02X"...
0x180071302  mov     [rsp+160h+var_110], r9d
0x180071307  lea     r9, aNs; "NS"
0x18007130e  mov     [rsp+160h+var_118], r10d
0x180071313  mov     [rsp+160h+var_120], r11d
0x180071318  mov     [rsp+160h+var_128], r15d
0x18007131d  mov     dword ptr [rsp+160h+var_130], r12d
0x180071322  mov     dword ptr [rsp+160h+Src], r13d
0x180071327  mov     [rsp+160h+var_140], eax
0x18007132b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180071330  mov     r15d, eax
0x180071333  lea     r12, ?dbgRsop@@3VCDebugWrapper@@A; CDebugWrapper dbgRsop
0x18007133a  mov     r13d, 2
0x180071340  xor     ecx, ecx
0x180071342  test    r15d, r15d
0x180071345  js      loc_180070FEE
0x18007134b  lea     rax, [rbp+60h+var_90]
0x18007134f  mov     r9, rsi
0x180071352  mov     [rsp+160h+var_130], rax; __int64
0x180071357  mov     r8, rdi
0x18007135a  mov     [rsp+160h+Src], r14; Src
0x18007135f  mov     rdx, rbx
  ... truncated ...
```
