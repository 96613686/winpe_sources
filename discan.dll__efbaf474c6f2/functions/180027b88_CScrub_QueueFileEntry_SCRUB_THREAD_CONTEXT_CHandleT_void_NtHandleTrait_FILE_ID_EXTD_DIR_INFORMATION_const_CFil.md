# CScrub::_QueueFileEntry(_SCRUB_THREAD_CONTEXT *,CHandleT<void *,NtHandleTrait> *,_FILE_ID_EXTD_DIR_INFORMATION const *,CFileName *,_SCRUB_DIRECTORY_ENTRY_FLAGS)

- ea: `0x180027b88`
- end: `0x180028358`
- name: `?_QueueFileEntry@CScrub@@AEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEAV?$CHandleT@PEAXUNtHandleTrait@@@@PEBU_FILE_ID_EXTD_DIR_INFORMATION@@PEAVCFileName@@W4_SCRUB_DIRECTORY_ENTRY_FLAGS@@@Z`
- size: `2000`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, struct _SCRUB_THREAD_CONTEXT *, __int64, __int64, struct CFileName *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18002892c`

## callees

- `0x180001b78`
- `0x180001bc4`
- `0x180003134`
- `0x1800032f8`
- `0x180006688`
- `0x180012158`
- `0x1800137d4`
- `0x180020cec`
- `0x180021ad8`
- `0x180021c48`
- `0x1800277e0`
- `0x180027858`
- `0x180027b88`
- `0x18002bc58`
- `0x18002bddc`
- `0x18002c300`
- `0x18002c6f8`
- `0x1800375ee`
- `0x180037620`
- `0x180039010`

## import_xrefs

- `ntdll!NtWaitForMultipleObjects` at `0x180027f92`
- `ntdll!NtWaitForMultipleObjects` at `0x180027f92`
- `ntdll!NtClearEvent` at `0x180027eea`
- `ntdll!NtClearEvent` at `0x180027eea`
- `ntdll!NtSetEvent` at `0x180028209`
- `ntdll!NtSetEvent` at `0x180028209`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180027ef3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180027fb7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800282e6`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180027ef3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180027fb7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800282e6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180027ead`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180027f9d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180027ead`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180027f9d`
- `KERNEL32!SubmitThreadpoolWork` at `0x1800282dd`
- `KERNEL32!SubmitThreadpoolWork` at `0x1800282dd`

## pseudocode

```c
__int64 __fastcall CScrub::_QueueFileEntry(
        RTL_SRWLOCK *this,
        struct _SCRUB_THREAD_CONTEXT *a2,
        __int64 a3,
        __int64 a4,
        struct CFileName *a5)
{
  __int64 v9; // rdx
  USHORT v10; // dx
  USHORT Length; // cx
  USHORT v12; // ax
  _QWORD *v13; // rax
  _QWORD *v14; // r14
  __int64 result; // rax
  CFileName *v16; // rax
  CFileName *v17; // rbx
  _QWORD *v18; // rdi
  const struct _UNICODE_STRING *FullPathName; // rax
  __int64 v20; // r10
  NTSTATUS v21; // edi
  PVOID *v22; // r11
  PVOID v23; // rdx
  RTL_SRWLOCK **v24; // rcx
  RTL_SRWLOCK *v25; // rax
  RTL_SRWLOCK *v26; // rdi
  RTL_SRWLOCK v27; // rcx
  int v28; // ebx
  __int64 v29; // [rsp+50h] [rbp-A8h] BYREF
  unsigned int v30; // [rsp+58h] [rbp-A0h] BYREF
  const struct _UNICODE_STRING *v31; // [rsp+60h] [rbp-98h] BYREF
  int v32; // [rsp+68h] [rbp-90h]
  __int64 v33[2]; // [rsp+70h] [rbp-88h] BYREF
  struct _UNICODE_STRING v34; // [rsp+80h] [rbp-78h] BYREF
  RTL_SRWLOCK *v35; // [rsp+90h] [rbp-68h]
  HANDLE Object[2]; // [rsp+98h] [rbp-60h] BYREF
  HANDLE Ptr; // [rsp+A8h] [rbp-50h]

  v35 = this;
  v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v9 + 16) = &stru_18003EDE0;
  v31 = &stru_18003EDE0;
  v32 = 0;
  v10 = ++*(_WORD *)(v9 + 8);
  Length = GlobalIndentString.Length;
  v12 = GlobalIndentString.Length;
  if ( v10 < GlobalIndentString.Length )
    v12 = v10;
  LOWORD(v33[0]) = v12;
  if ( v10 < GlobalIndentString.Length )
    Length = v10;
  WORD1(v33[0]) = Length;
  HIDWORD(v33[0]) = 0;
  v33[1] = (__int64)off_180047060;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)&stru_18003EDE0);
  }
  try
  {
    *(_QWORD *)&v34.Length = 0;
    v34.Buffer = (PWSTR)(a4 + 88);
    v34.MaximumLength = *(_WORD *)(a4 + 60);
    v34.Length = v34.MaximumLength;
    v13 = operator new(0x50u);
    v14 = v13;
    if ( v13 )
      memset_0(v13, 0, 0x50u);
    else
      v14 = 0;
    v33[0] = (__int64)v14;
    if ( !v14 )
    {
      v32 = -2147024882;
      CHResultImp::~CHResultImp((CHResultImp *)&v31);
      return 2147942414LL;
    }
    v16 = (CFileName *)operator new(0x30u);
    v29 = (__int64)v16;
    if ( v16 )
      v17 = CFileName::CFileName(v16, a5, &v34);
    else
      v17 = 0;
    if ( v17 )
      (*(void (__fastcall **)(CFileName *))(*(_QWORD *)v17 + 8LL))(v17);
    v14[2] = *(unsigned int *)(a4 + 56);
    *(_OWORD *)(v14 + 3) = *(_OWORD *)(a4 + 72);
    v18 = v14 + 5;
    v33[0] = 0;
    ATL::CComPtrBase<CFileName>::Attach(v14 + 5, v17);
    v14[6] = a3;
    v14[7] = 0;
    v14[9] = 0;
    v14[8] = 0;
    FullPathName = CScrub::_GetFullPathName((CScrub *)this, a2, a5, 0);
    v29 = (__int64)FullPathName;
    if ( !FullPathName )
    {
      v32 = -2147024882;
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v33);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v14 + 5);
      operator delete(v14);
      CHResultImp::~CHResultImp((CHResultImp *)&v31);
      return 2147942414LL;
    }
    v20 = v14[4];
    if ( v20 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_DDZZZii(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *(_DWORD *)(*(_QWORD *)this->Ptr + 36LL),
          *((_QWORD *)this->Ptr + 8),
          *((_QWORD *)this->Ptr + 8),
          (__int64)FullPathName,
          v20,
          v14[3]);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDZZZi(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *(_DWORD *)(*(_QWORD *)this->Ptr + 36LL),
        *((_QWORD *)this->Ptr + 8),
        *((_QWORD *)this->Ptr + 8),
        (__int64)FullPathName,
        v14[3]);
    }
    AcquireSRWLockExclusive(this + 184);
    if ( SLODWORD(this[185].Ptr) < 100 )
    {
      v22 = (PVOID *)WPP_GLOBAL_Control;
    }
    else
    {
      Object[0] = this[2].Ptr;
      Object[1] = this[152].Ptr;
      Ptr = this[148].Ptr;
      NtClearEvent(Ptr);
      ReleaseSRWLockExclusive(this + 184);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_DDZdd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          163,
          this->Ptr,
          *(_DWORD *)(*(_QWORD *)this->Ptr + 16LL),
          *(_DWORD *)(*(_QWORD *)this->Ptr + 36LL),
          *((_QWORD *)this->Ptr + 8),
          (unsigned __int64)((char *)a2 - (char *)this[177].Ptr) / 0x88D0,
          (char)this[185].Ptr);
      }
      v21 = NtWaitForMultipleObjects(3u, Object, WaitAny, 0, 0);
      AcquireSRWLockExclusive(this + 184);
      if ( v21 != 2 )
      {
        CScrub::_DrainFileQueue((CScrub *)this);
        ReleaseSRWLockExclusive(this + 184);
        v29 = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_DDZd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            164,
            (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
            *(_DWORD *)(*(_QWORD *)this->Ptr + 16LL),
            *(_DWORD *)(*(_QWORD *)this->Ptr + 36LL),
            *((_QWORD *)this->Ptr + 8),
            (unsigned __int64)((char *)a2 - (char *)this[177].Ptr) / 0x88D0);
        }
        CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock((RTL_SRWLOCK **)&v29);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v33);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v14 + 5);
        operator delete(v14);
        CHResultImp::~CHResultImp((CHResultImp *)&v31);
        return 3489661194LL;
      }
      v22 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      {
LABEL_50:
        CHandleT<void *,NtHandleTrait>::AddRef(v14[6]);
        v24 = (RTL_SRWLOCK **)this[183].Ptr;
        if ( *v24 == &this[182] )
        {
          *v14 = this + 182;
          v14[1] = v24;
          *v24 = (RTL_SRWLOCK *)v14;
          this[183].Ptr = v14;
          ++LODWORD(this[185].Ptr);
          if ( LODWORD(this[172].Ptr) )
          {
            if ( WPP_GLOBAL_Control != v23
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_DDZdd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                167,
                (unsigned __int64)((char *)a2 - (char *)this[177].Ptr) / 0x88D0,
                *(_DWORD *)(*(_QWORD *)this->Ptr + 16LL),
                *(_DWORD *)(*(_QWORD *)this->Ptr + 36LL),
                *((_QWORD *)this->Ptr + 8),
                (unsigned __int64)((char *)a2 - (char *)this[177].Ptr) / 0x88D0,
                (char)this[172].Ptr);
            }
            NtSetEvent(this[148].Ptr, 0);
            goto LABEL_66;
          }
          v25 = this + 173;
          v26 = (RTL_SRWLOCK *)this[173].Ptr;
          if ( v26 == &this[173] )
          {
LABEL_66:
            ReleaseSRWLockExclusive(this + 184);
            v29 = 0;
            CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock((RTL_SRWLOCK **)&v29);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v33);
            v32 = 0;
            CHResultImp::~CHResultImp((CHResultImp *)&v31);
            return 0;
          }
          if ( v26[1].Ptr == v25 )
          {
            v27.Ptr = v26->Ptr;
            if ( *((RTL_SRWLOCK **)v26->Ptr + 1) == v26 )
            {
              v25->Ptr = v27.Ptr;
              *((_QWORD *)v27.Ptr + 1) = v25;
              if ( WPP_GLOBAL_Control != v23
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_DDZdd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  168,
                  (unsigned __int64)((char *)a2 - (char *)this[177].Ptr) / 0x88D0,
                  *(_DWORD *)(*(_QWORD *)this->Ptr + 16LL),
                  *(_DWORD *)(*(_QWORD *)this->Ptr + 36LL),
                  *((_QWORD *)this->Ptr + 8),
                  (unsigned __int64)((char *)a2 - (char *)this[177].Ptr) / 0x88D0,
                  (unsigned __int64)((char *)v26 - (char *)this[178].Ptr) / 0x88D0);
              }
              SubmitThreadpoolWork((PTP_WORK)v26[2].Ptr);
              goto LABEL_66;
            }
          }
        }
        __fastfail(3u);
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_DDZdd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          165,
          this->Ptr,
          *(_DWORD *)(*(_QWORD *)this->Ptr + 16LL),
          *(_DWORD *)(*(_QWORD *)this->Ptr + 36LL),
          *((_QWORD *)this->Ptr + 8),
          (unsigned __int64)((char *)a2 - (char *)this[177].Ptr) / 0x88D0,
          (char)this[185].Ptr);
        v22 = (PVOID *)WPP_GLOBAL_Control;
      }
      v18 = v14 + 5;
    }
    if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 1) != 0 && *((_BYTE *)v22 + 25) >= 4u )
      WPP_SF_DDZdZZ(
        (TRACEHANDLE)v22[2],
        *(_DWORD *)(*(_QWORD *)this->Ptr + 36LL),
        *((_QWORD *)this->Ptr + 8),
        (unsigned __int64)((char *)a2 - (char *)this[177].Ptr) / 0x88D0,
        v29,
        *v18 + 24LL);
    goto LABEL_50;
  }
  catch ( ATL::CAtlException v30 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      v28 = v30;
    }
    else
    {
      v28 = v30;
      WPP_SF_DDZd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        169,
        (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
        *(_DWORD *)(*(_QWORD *)v35->Ptr + 16LL),
        *(_DWORD *)(*(_QWORD *)v35->Ptr + 36LL),
        *((_QWORD *)v35->Ptr + 8),
        v30);
    }
    v32 = v28;
    CHResultImp::~CHResultImp((CHResultImp *)&v31);
    return v30;
  }
  *(_QWORD *)&v34.Length = 0;
}

```

## disassembly

```asm
0x180027b88  push    rbx
0x180027b8a  push    rsi
0x180027b8b  push    rdi
0x180027b8c  push    r12
0x180027b8e  push    r13
0x180027b90  push    r14
0x180027b92  push    r15
0x180027b94  sub     rsp, 0C0h
0x180027b9b  mov     rax, cs:__security_cookie
0x180027ba2  xor     rax, rsp
0x180027ba5  mov     [rsp+0F8h+var_48], rax
0x180027bad  mov     rdi, r9
0x180027bb0  mov     r12, r8
0x180027bb3  mov     r13, rdx
0x180027bb6  mov     rsi, rcx
0x180027bb9  mov     [rsp+0F8h+var_68], rcx
0x180027bc1  mov     r15, [rsp+0F8h+arg_20]
0x180027bc9  mov     ecx, cs:_tls_index
0x180027bcf  mov     rax, gs:58h
0x180027bd8  mov     rdx, [rax+rcx*8]
0x180027bdc  mov     eax, 10h
0x180027be1  lea     r9, stru_18003EDE0
0x180027be8  mov     [rax+rdx], r9
0x180027bec  mov     [rsp+0F8h+var_98], r9
0x180027bf1  mov     [rsp+0F8h+var_90], 0
0x180027bf9  mov     eax, 8
0x180027bfe  mov     r8d, 1
0x180027c04  add     [rax+rdx], r8w
0x180027c09  movzx   edx, word ptr [rax+rdx]
0x180027c0d  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180027c14  movzx   eax, cx
0x180027c17  cmp     dx, cx
0x180027c1a  cmovb   ax, dx
0x180027c1e  mov     word ptr [rsp+0F8h+var_88], ax
0x180027c23  cmovb   cx, dx
0x180027c27  mov     word ptr [rsp+0F8h+var_88+2], cx
0x180027c2c  xor     eax, eax
0x180027c2e  mov     dword ptr [rsp+0F8h+var_88+4], eax
0x180027c32  mov     rax, cs:off_180047060; "                                       "...
0x180027c39  mov     [rsp+0F8h+var_80], rax
0x180027c3e  lea     rax, WPP_GLOBAL_Control
0x180027c45  mov     rcx, cs:WPP_GLOBAL_Control
0x180027c4c  cmp     rcx, rax
0x180027c4f  jz      short loc_180027C75
0x180027c51  test    [rcx+1Ch], r8b
0x180027c55  jz      short loc_180027C75
0x180027c57  cmp     byte ptr [rcx+19h], 5
0x180027c5b  jb      short loc_180027C75
0x180027c5d  lea     edx, [r8+0Ch]
0x180027c61  mov     [rsp+0F8h+Time], r9; struct _UNICODE_STRING *
0x180027c66  lea     r9, [rsp+0F8h+var_88]
0x180027c6b  mov     rcx, [rcx+10h]; LoggerHandle
0x180027c6f  call    WPP_SF_aZs
0x180027c74  nop
0x180027c75  xorps   xmm0, xmm0
0x180027c78  movups  xmmword ptr [rsp+0F8h+var_78.Length], xmm0
0x180027c80  lea     rax, [rdi+58h]
0x180027c84  mov     [rsp+0F8h+var_78.Buffer], rax
0x180027c8c  movzx   eax, word ptr [rdi+3Ch]
0x180027c90  mov     [rsp+0F8h+var_78.MaximumLength], ax
0x180027c98  mov     [rsp+0F8h+var_78.Length], ax
0x180027ca0  mov     ebx, 50h ; 'P'
0x180027ca5  mov     ecx, ebx; Size
0x180027ca7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027cac  mov     r14, rax
0x180027caf  test    rax, rax
0x180027cb2  jz      short loc_180027CC3
0x180027cb4  mov     r8d, ebx; Size
0x180027cb7  xor     edx, edx; Val
0x180027cb9  mov     rcx, rax; void *
0x180027cbc  call    memset_0
0x180027cc1  jmp     short loc_180027CC6
0x180027cc3  xor     r14d, r14d
0x180027cc6  mov     [rsp+0F8h+var_88], r14
0x180027ccb  test    r14, r14
0x180027cce  jnz     short loc_180027CEA
0x180027cd0  mov     ebx, 8007000Eh
0x180027cd5  mov     [rsp+0F8h+var_90], ebx
0x180027cd9  lea     rcx, [rsp+0F8h+var_98]; this
0x180027cde  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x180027ce3  mov     eax, ebx
0x180027ce5  jmp     loc_180028335
0x180027cea  mov     ecx, 30h ; '0'; Size
0x180027cef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027cf4  mov     [rsp+0F8h+var_A8], rax
0x180027cf9  test    rax, rax
0x180027cfc  jz      short loc_180027D16
0x180027cfe  lea     r8, [rsp+0F8h+var_78]; struct _UNICODE_STRING *
0x180027d06  mov     rdx, r15; struct CFileName *
0x180027d09  mov     rcx, rax; this
0x180027d0c  call    ??0CFileName@@QEAA@PEAV0@PEBU_UNICODE_STRING@@@Z; CFileName::CFileName(CFileName *,_UNICODE_STRING const *)
0x180027d11  mov     rbx, rax
0x180027d14  jmp     short loc_180027D18
0x180027d16  xor     ebx, ebx
0x180027d18  test    rbx, rbx
0x180027d1b  jz      short loc_180027D2D
0x180027d1d  mov     rax, [rbx]
0x180027d20  mov     rcx, rbx
0x180027d23  mov     rax, [rax+8]
0x180027d27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d2c  nop
0x180027d2d  mov     eax, [rdi+38h]
0x180027d30  mov     [r14+10h], eax
0x180027d34  mov     dword ptr [r14+14h], 0
0x180027d3c  movups  xmm0, xmmword ptr [rdi+48h]
0x180027d40  movdqu  xmmword ptr [r14+18h], xmm0
0x180027d46  lea     rdi, [r14+28h]
0x180027d4a  mov     [rsp+0F8h+var_88], 0
0x180027d53  mov     rdx, rbx
0x180027d56  mov     rcx, rdi
0x180027d59  call    ?Attach@?$CComPtrBase@VCFileName@@@ATL@@QEAAXPEAVCFileName@@@Z; ATL::CComPtrBase<CFileName>::Attach(CFileName *)
0x180027d5e  mov     [r14+30h], r12
0x180027d62  xor     ebx, ebx
0x180027d64  mov     [r14+38h], rbx
0x180027d68  mov     [r14+48h], rbx
0x180027d6c  mov     [r14+40h], rbx
0x180027d70  xor     r9d, r9d; struct _UNICODE_STRING *
0x180027d73  mov     r8, r15; struct CFileName *
0x180027d76  mov     rdx, r13; struct _SCRUB_THREAD_CONTEXT *
0x180027d79  mov     rcx, rsi; this
0x180027d7c  call    ?_GetFullPathName@CScrub@@AEAAPEBU_UNICODE_STRING@@PEAU_SCRUB_THREAD_CONTEXT@@PEAVCFileName@@PEBU2@2@Z; CScrub::_GetFullPathName(_SCRUB_THREAD_CONTEXT *,CFileName *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x180027d81  mov     r11, rax
0x180027d84  mov     [rsp+0F8h+var_A8], rax
0x180027d89  test    rax, rax
0x180027d8c  jnz     short loc_180027DC4
0x180027d8e  mov     ebx, 8007000Eh
0x180027d93  mov     [rsp+0F8h+var_90], ebx
0x180027d97  lea     rcx, [rsp+0F8h+var_88]
0x180027d9c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180027da1  nop
0x180027da2  mov     rcx, rdi
0x180027da5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180027daa  mov     rcx, r14; Block
0x180027dad  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180027db2  nop
0x180027db3  lea     rcx, [rsp+0F8h+var_98]; this
0x180027db8  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x180027dbd  mov     eax, ebx
0x180027dbf  jmp     loc_180028335
0x180027dc4  mov     r10, [r14+20h]
0x180027dc8  test    r10, r10
0x180027dcb  jnz     short loc_180027E3A
0x180027dcd  mov     r8, cs:WPP_GLOBAL_Control
0x180027dd4  lea     r12, WPP_GLOBAL_Control
0x180027ddb  cmp     r8, r12
0x180027dde  jz      loc_180027EA0
0x180027de4  test    byte ptr [r8+1Ch], 1
0x180027de9  jz      loc_180027EA0
0x180027def  mov     r15b, 4
0x180027df2  cmp     [r8+19h], r15b
0x180027df6  jb      loc_180027EA3
0x180027dfc  mov     rax, [rsi]
0x180027dff  mov     rcx, [rax+40h]
0x180027e03  mov     r9, [rax]
0x180027e06  mov     edx, 0A0h
0x180027e0b  mov     rax, [r14+18h]
0x180027e0f  mov     qword ptr [rsp+0F8h+var_B8], rax; char
0x180027e14  mov     [rsp+0F8h+var_C0], r11; __int64
0x180027e19  mov     qword ptr [rsp+0F8h+var_C8], rcx; __int64
0x180027e1e  mov     [rsp+0F8h+var_D0], rcx; __int64
0x180027e23  mov     eax, [r9+24h]
0x180027e27  mov     dword ptr [rsp+0F8h+Time], eax; char
0x180027e2b  mov     r9d, [r9+10h]
0x180027e2f  mov     rcx, [r8+10h]; LoggerHandle
0x180027e33  call    WPP_SF_DDZZZi
0x180027e38  jmp     short loc_180027EA3
0x180027e3a  mov     r8, cs:WPP_GLOBAL_Control
0x180027e41  lea     r12, WPP_GLOBAL_Control
0x180027e48  cmp     r8, r12
0x180027e4b  jz      short loc_180027EA0
0x180027e4d  test    byte ptr [r8+1Ch], 1
0x180027e52  jz      short loc_180027EA0
0x180027e54  mov     r15b, 4
0x180027e57  cmp     [r8+19h], r15b
0x180027e5b  jb      short loc_180027EA3
0x180027e5d  mov     rax, [rsi]
0x180027e60  mov     rcx, [rax+40h]
0x180027e64  mov     r9, [rax]
0x180027e67  mov     edx, 0A1h
0x180027e6c  mov     rax, [r14+18h]
0x180027e70  mov     qword ptr [rsp+0F8h+var_B0], rax; char
0x180027e75  mov     qword ptr [rsp+0F8h+var_B8], r10; char
0x180027e7a  mov     [rsp+0F8h+var_C0], r11; __int64
0x180027e7f  mov     qword ptr [rsp+0F8h+var_C8], rcx; __int64
0x180027e84  mov     [rsp+0F8h+var_D0], rcx; __int64
0x180027e89  mov     eax, [r9+24h]
0x180027e8d  mov     dword ptr [rsp+0F8h+Time], eax; char
0x180027e91  mov     r9d, [r9+10h]
0x180027e95  mov     rcx, [r8+10h]; LoggerHandle
0x180027e99  call    WPP_SF_DDZZZii
0x180027e9e  jmp     short loc_180027EA3
0x180027ea0  mov     r15b, 4
0x180027ea3  lea     rbx, [rsi+5C0h]
0x180027eaa  mov     rcx, rbx; SRWLock
0x180027ead  call    cs:__imp_AcquireSRWLockExclusive
0x180027eb3  cmp     dword ptr [rsi+5C8h], 64h ; 'd'
0x180027eba  jl      loc_180028214
0x180027ec0  mov     rax, [rsi+10h]
0x180027ec4  mov     [rsp+0F8h+Object], rax
0x180027ecc  mov     rax, [rsi+4C0h]
0x180027ed3  mov     [rsp+0F8h+var_58], rax
0x180027edb  mov     rcx, [rsi+4A0h]; EventHandle
0x180027ee2  mov     [rsp+0F8h+var_50], rcx
0x180027eea  call    cs:__imp_NtClearEvent
0x180027ef0  mov     rcx, rbx; SRWLock
0x180027ef3  call    cs:__imp_ReleaseSRWLockExclusive
0x180027ef9  mov     r10, cs:WPP_GLOBAL_Control
0x180027f00  cmp     r10, r12
0x180027f03  jz      short loc_180027F6C
0x180027f05  test    byte ptr [r10+1Ch], 1
0x180027f0a  jz      short loc_180027F6C
0x180027f0c  cmp     [r10+19h], r15b
0x180027f10  jb      short loc_180027F6C
0x180027f12  mov     r8, [rsi]
0x180027f15  mov     r9, [r8]
0x180027f18  mov     rcx, r13
0x180027f1b  sub     rcx, [rsi+588h]
0x180027f22  mov     r12, 77C150CFB348283Bh
0x180027f2c  mov     rax, r12
0x180027f2f  mul     rcx
0x180027f32  mov     rcx, rdx
0x180027f35  shr     rcx, 0Eh
0x180027f39  mov     edx, 0A3h
0x180027f3e  mov     eax, [rsi+5C8h]
0x180027f44  mov     dword ptr [rsp+0F8h+var_C0], eax
0x180027f48  mov     dword ptr [rsp+0F8h+var_C8], ecx
0x180027f4c  mov     rax, [r8+40h]
0x180027f50  mov     [rsp+0F8h+var_D0], rax
0x180027f55  mov     eax, [r9+24h]
0x180027f59  mov     dword ptr [rsp+0F8h+Time], eax
0x180027f5d  mov     r9d, [r9+10h]
0x180027f61  mov     rcx, [r10+10h]
0x180027f65  call    WPP_SF_DDZdd
0x180027f6a  jmp     short loc_180027F76
0x180027f6c  mov     r12, 77C150CFB348283Bh
0x180027f76  mov     [rsp+0F8h+Time], 0; Time
0x180027f7f  xor     r9d, r9d; Alertable
0x180027f82  lea     r8d, [r9+1]; WaitType
0x180027f86  lea     rdx, [rsp+0F8h+Object]; Object
0x180027f8e  lea     ecx, [r9+3]; Count
0x180027f92  call    cs:__imp_NtWaitForMultipleObjects
0x180027f98  mov     edi, eax
0x180027f9a  mov     rcx, rbx; SRWLock
0x180027f9d  call    cs:__imp_AcquireSRWLockExclusive
0x180027fa3  cmp     edi, 2
0x180027fa6  jz      loc_180028069
0x180027fac  mov     rcx, rsi; this
0x180027faf  call    ?_DrainFileQueue@CScrub@@AEAAXXZ; CScrub::_DrainFileQueue(void)
0x180027fb4  mov     rcx, rbx; SRWLock
0x180027fb7  call    cs:__imp_ReleaseSRWLockExclusive
0x180027fbd  mov     [rsp+0F8h+var_A8], 0
0x180027fc6  mov     r10, cs:WPP_GLOBAL_Control
0x180027fcd  lea     rax, WPP_GLOBAL_Control
0x180027fd4  cmp     r10, rax
0x180027fd7  jz      short loc_18002802E
0x180027fd9  test    byte ptr [r10+1Ch], 1
0x180027fde  jz      short loc_18002802E
0x180027fe0  cmp     [r10+19h], r15b
0x180027fe4  jb      short loc_18002802E
0x180027fe6  mov     r8, [rsi]
0x180027fe9  mov     r9, [r8]
0x180027fec  sub     r13, [rsi+588h]
0x180027ff3  mov     rax, r12
0x180027ff6  mul     r13
0x180027ff9  mov     rcx, rdx
0x180027ffc  shr     rcx, 0Eh
0x180028000  mov     edx, 0A4h
0x180028005  mov     dword ptr [rsp+0F8h+var_C8], ecx
0x180028009  mov     rax, [r8+40h]
0x18002800d  mov     [rsp+0F8h+var_D0], rax
0x180028012  mov     eax, [r9+24h]
0x180028016  mov     dword ptr [rsp+0F8h+Time], eax
0x18002801a  mov     r9d, [r9+10h]
0x18002801e  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x180028025  mov     rcx, [r10+10h]
0x180028029  call    WPP_SF_DDZd
0x18002802e  lea     rcx, [rsp+0F8h+var_A8]; this
0x180028033  call    ??1CAutoSrwExclusiveLock@@QEAA@XZ; CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(void)
0x180028038  lea     rcx, [rsp+0F8h+var_88]
0x18002803d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180028042  nop
0x180028043  lea     rcx, [r14+28h]
0x180028047  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002804c  mov     rcx, r14; Block
0x18002804f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180028054  nop
0x180028055  lea     rcx, [rsp+0F8h+var_98]; this
0x18002805a  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18002805f  mov     eax, 0D000010Ah
0x180028064  jmp     loc_180028335
0x180028069  mov     r11, cs:WPP_GLOBAL_Control
0x180028070  lea     rdx, WPP_GLOBAL_Control
0x180028077  cmp     r11, rdx
0x18002807a  jz      loc_180028160
0x180028080  test    byte ptr [r11+1Ch], 1
0x180028085  jz      short loc_1800280E9
0x180028087  cmp     [r11+19h], r15b
0x18002808b  jb      short loc_1800280E9
0x18002808d  mov     r8, [rsi]
0x180028090  mov     r9, [r8]
  ... truncated ...
```
