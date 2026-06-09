# CThreadInputMgr::UpdateIMMStatus(IMMStatusUpdateSource,bool)

- ea: `0x180019cfc`
- end: `0x18001a26f`
- name: `?UpdateIMMStatus@CThreadInputMgr@@QEAAXW4IMMStatusUpdateSource@@_N@Z`
- size: `1395`
- prototype: ``
- caller_count: `7`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180018670`
- `0x180019180`
- `0x180019b98`
- `0x180019be0`
- `0x180028d60`
- `0x180029200`
- `0x180080540`

## callees

- `0x18000fcf0`
- `0x180019cfc`
- `0x18002b424`
- `0x180055a4c`
- `0x180057444`
- `0x18005fb80`
- `0x1800662e8`
- `0x18009eaea`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019ee7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019ee7`
- `USER32!NotifyWinEvent` at `0x18001a1dc`
- `USER32!NotifyWinEvent` at `0x18001a1dc`
- `IMM32!ImmGetOpenStatus` at `0x180019dc8`
- `IMM32!ImmGetOpenStatus` at `0x180019dc8`
- `IMM32!ImmGetConversionStatus` at `0x180019da9`
- `IMM32!ImmGetConversionStatus` at `0x180019da9`
- `IMM32!ImmReleaseContext` at `0x180019fa0`
- `IMM32!ImmReleaseContext` at `0x180019fa0`
- `IMM32!ImmGetContext` at `0x180019d85`
- `IMM32!ImmGetContext` at `0x18001a0f0`
- `IMM32!ImmGetContext` at `0x180019d85`
- `IMM32!ImmGetContext` at `0x18001a0f0`
- `IMM32!ImmGetDefaultIMEWnd` at `0x18001a0db`
- `IMM32!ImmGetDefaultIMEWnd` at `0x18001a0db`

## pseudocode

```c
void __fastcall CThreadInputMgr::UpdateIMMStatus(__int64 a1, int a2, char a3)
{
  HWND v3; // r14
  bool v4; // r12
  __int16 v6; // r13
  int v7; // r10d
  unsigned int v8; // r15d
  unsigned __int16 v9; // si
  HIMC Context; // rdi
  BOOL OpenStatus; // eax
  __int64 (__fastcall **v12)(__int64, GUID *, unsigned int *); // rax
  char v13; // r12
  int v14; // r14d
  __int64 v15; // rcx
  __int16 v16; // ax
  unsigned __int16 v17; // r12
  DWORD CurrentThreadId; // eax
  int v19; // r13d
  unsigned int v20; // ecx
  HWND v21; // rdx
  __int64 v22; // rax
  __int64 v23; // r14
  unsigned int v24; // r12d
  unsigned int v25; // r13d
  struct IInputContextPrivate *TopInputContext; // rax
  struct IInputContextPrivate *v27; // r14
  __int64 v28; // rcx
  char v29; // al
  __int64 v30; // rcx
  bool v31; // sf
  HWND DefaultIMEWnd; // rax
  __int64 v33; // rax
  __int64 v34; // r9
  __int64 v35; // rax
  bool v36; // [rsp+40h] [rbp-99h] BYREF
  char v37; // [rsp+41h] [rbp-98h]
  DWORD fdwConversion; // [rsp+44h] [rbp-95h] BYREF
  unsigned int v39[2]; // [rsp+48h] [rbp-91h] BYREF
  DWORD fdwSentence; // [rsp+50h] [rbp-89h] BYREF
  HWND v41; // [rsp+58h] [rbp-81h]
  __int128 v42; // [rsp+60h] [rbp-79h] BYREF
  __int64 v43; // [rsp+70h] [rbp-69h]
  _DWORD v44[20]; // [rsp+80h] [rbp-59h] BYREF
  unsigned int v45[4]; // [rsp+D0h] [rbp-9h] BYREF

  v3 = *(HWND *)(a1 + 2976);
  v37 = a3;
  v4 = a2 != 1;
  v6 = 0;
  v36 = a2 != 1;
  if ( v3 )
  {
    if ( !*(_QWORD *)(a1 + 3760) )
      goto LABEL_47;
    if ( !CThreadInputMgr::IsTSF3IMEActive((CThreadInputMgr *)a1) )
    {
      v36 = v4;
      goto LABEL_5;
    }
    if ( v7 == 2 )
    {
LABEL_47:
      if ( !*(_QWORD *)(a1 + 3760) )
        return;
      v36 = 0;
    }
LABEL_5:
    v8 = *(_DWORD *)(a1 + 3684);
    v9 = 16;
    fdwConversion = 0;
    fdwSentence = 0;
    Context = ImmGetContext(v3);
    if ( !Context )
    {
      v41 = 0;
      if ( !HasActiveTsfInputContext() )
        goto LABEL_12;
      DefaultIMEWnd = ImmGetDefaultIMEWnd(0);
      v3 = DefaultIMEWnd;
      if ( !DefaultIMEWnd )
        goto LABEL_12;
      Context = ImmGetContext(DefaultIMEWnd);
    }
    if ( Context )
    {
      if ( ImmGetConversionStatus(Context, &fdwConversion, &fdwSentence) )
        v8 = (unsigned __int16)fdwConversion | ((unsigned __int16)fdwSentence << 16);
      OpenStatus = ImmGetOpenStatus(Context);
      v41 = v3;
      v9 = 1;
      if ( !OpenStatus )
        v9 = 2;
    }
    else
    {
      v41 = 0;
    }
LABEL_12:
    *(_QWORD *)v45 = 0;
    v43 = 0;
    v12 = *(__int64 (__fastcall ***)(__int64, GUID *, unsigned int *))a1;
    *(_QWORD *)v39 = 0;
    v13 = 0;
    v42 = 0;
    v14 = (*v12)(a1, &IID_ITfCompartmentMgr, v45);
    if ( v14 >= 0 )
    {
      if ( !*(_QWORD *)v45 )
        goto LABEL_19;
      v14 = (*(__int64 (__fastcall **)(_QWORD, GUID *, unsigned int *))(**(_QWORD **)v45 + 24LL))(
              *(_QWORD *)v45,
              &GUID_COMPARTMENT_OPENSTATUS_EXPLICITLY_CHANGED_BY_USER,
              v39);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v45 + 16LL))(*(_QWORD *)v45);
    }
    if ( v14 >= 0 )
    {
      if ( !(*(unsigned int (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)v39 + 32LL))(*(_QWORD *)v39, &v42) )
        v13 = BYTE8(v42);
      (*(void (**)(void))(**(_QWORD **)v39 + 16LL))();
    }
LABEL_19:
    v15 = *(_QWORD *)(a1 + 2944);
    if ( v15 )
    {
      v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 72LL))(v15);
      *(_QWORD *)v45 = 0;
      v23 = v22;
      if ( v22 && !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v22 + 224LL))(v22) )
      {
        if ( v37 && (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v23 + 88LL))(v23, v45) >= 0 )
        {
          v6 = v45[0];
          v16 = 4096;
          goto LABEL_21;
        }
      }
      else
      {
        v9 = 16;
      }
    }
    v16 = 0;
LABEL_21:
    v17 = v16 | v6 & 0xFFF | ((v13 & 1) << 13);
    if ( v17 || v9 != *(_WORD *)(a1 + 3680) || v9 == 1 && v8 != *(_DWORD *)(a1 + 3684) )
    {
      memset_0(v44, 0, 0x48u);
      v44[0] = 4718624;
      CurrentThreadId = GetCurrentThreadId();
      v44[10] = 16777244;
      v44[11] = CurrentThreadId;
      v44[14] = v9;
      v44[15] = v8;
      if ( (int)MsgBase::Send((MsgBase *)v44) >= 0 )
      {
        v19 = 0;
        *(_WORD *)(a1 + 3680) = v9;
        *(_DWORD *)(a1 + 3684) = v8;
        if ( v9 == 1 )
          v19 = 0x20000;
        v20 = 0;
        if ( v9 == 16 )
          v20 = 0x10000;
        v39[0] = v20;
        if ( v36 && *(_QWORD *)(*(_QWORD *)(a1 + 208) + 96LL) )
        {
          v33 = *(_QWORD *)(a1 + 168);
          *(_OWORD *)v45 = 0;
          if ( (*(int (__fastcall **)(__int64, unsigned int *))(v33 + 208))(a1 + 168, v45) >= 0 )
          {
            v35 = *(_QWORD *)(a1 + 208);
            v42 = *(_OWORD *)v45;
            LOBYTE(v34) = v9 == 1;
            (*(void (__fastcall **)(_QWORD, __int128 *, _QWORD, __int64, bool, _WORD))(**(_QWORD **)(v35 + 96) + 136LL))(
              *(_QWORD *)(v35 + 96),
              &v42,
              0,
              v34,
              v9 == 16,
              v8);
          }
          v20 = v39[0];
        }
        v21 = *(HWND *)(*(_QWORD *)(a1 + 208) + 136LL);
        if ( v21 )
          NotifyWinEvent(0x7FFFFF30u, v21, (v17 << 16) | 3, ((v19 | v20 | v8 & 0xFFF) << 14) | HIWORD(v8) & 0x1F);
        if ( Context )
        {
          v24 = 0;
          v25 = 0;
          TopInputContext = CThreadInputMgr::GetTopInputContext((CThreadInputMgr *)a1);
          v27 = TopInputContext;
          if ( TopInputContext )
          {
            v28 = *(_QWORD *)TopInputContext;
            *(_QWORD *)v45 = 0;
            v29 = (*(__int64 (__fastcall **)(struct IInputContextPrivate *))(v28 + 184))(TopInputContext);
            v30 = *(_QWORD *)v27;
            v36 = v29;
            v31 = (*(int (__fastcall **)(struct IInputContextPrivate *, unsigned int *))(v30 + 88))(v27, v45) < 0;
            LOBYTE(TopInputContext) = v36;
            if ( !v31 )
            {
              v24 = v45[1];
              v25 = v45[0];
            }
          }
          CInputSessionMgr::OnStatusChanged(
            (CInputSessionMgr *)(a1 + 3128),
            v9 == 1,
            fdwConversion,
            v24,
            v25,
            (bool)TopInputContext);
        }
      }
    }
    if ( v9 == *(_WORD *)(a1 + 3680) && v9 == 2 && v8 != *(_DWORD *)(a1 + 3684) )
    {
      v45[0] = 0;
      v39[0] = 0;
      v36 = 0;
      CThreadInputMgr::GetTopContextData((CThreadInputMgr *)a1, v45, v39, &v36);
      CInputSessionMgr::OnStatusChanged((CInputSessionMgr *)(a1 + 3128), 1, fdwConversion, v45[0], v39[0], v36);
    }
    if ( Context )
      ImmReleaseContext(v41, Context);
    return;
  }
  if ( !a2 )
    *(_DWORD *)(a1 + 3668) |= 0x8000u;
}

```

## disassembly

```asm
0x180019cfc  push    rbp
0x180019cfe  push    rbx
0x180019cff  push    rsi
0x180019d00  push    rdi
0x180019d01  push    r12
0x180019d03  push    r13
0x180019d05  push    r14
0x180019d07  push    r15
0x180019d09  lea     rbp, [rsp-1Fh]
0x180019d0e  sub     rsp, 0F8h
0x180019d15  mov     rax, cs:__security_cookie
0x180019d1c  xor     rax, rsp
0x180019d1f  mov     [rbp+57h+var_50], rax
0x180019d23  mov     r14, [rcx+0BA0h]
0x180019d2a  cmp     edx, 1
0x180019d2d  mov     [rsp+130h+var_EF], r8b
0x180019d32  mov     r10d, edx
0x180019d35  setnz   r12b
0x180019d39  mov     rbx, rcx
0x180019d3c  xor     r13d, r13d
0x180019d3f  mov     [rsp+130h+var_F0], r12b
0x180019d44  test    r14, r14
0x180019d47  jz      loc_18001A259
0x180019d4d  cmp     [rcx+0EB0h], r13
0x180019d54  jz      loc_18001A0C2
0x180019d5a  call    ?IsTSF3IMEActive@CThreadInputMgr@@QEBA_NXZ; CThreadInputMgr::IsTSF3IMEActive(void)
0x180019d5f  test    al, al
0x180019d61  jnz     loc_18001A0B8
0x180019d67  mov     [rsp+130h+var_F0], r12b
0x180019d6c  mov     r15d, [rbx+0E64h]
0x180019d73  mov     rcx, r14; HWND
0x180019d76  mov     esi, 10h
0x180019d7b  mov     [rsp+130h+fdwConversion], r13d
0x180019d80  mov     [rsp+130h+fdwSentence], r13d
0x180019d85  call    cs:__imp_ImmGetContext
0x180019d8b  mov     rdi, rax
0x180019d8e  test    rax, rax
0x180019d91  jz      short loc_180019DE3
0x180019d93  test    rdi, rdi
0x180019d96  jz      loc_18001A0FE
0x180019d9c  lea     r8, [rsp+130h+fdwSentence]; lpfdwSentence
0x180019da1  mov     rcx, rdi; HIMC
0x180019da4  lea     rdx, [rsp+130h+fdwConversion]; lpfdwConversion
0x180019da9  call    cs:__imp_ImmGetConversionStatus
0x180019daf  test    eax, eax
0x180019db1  jz      short loc_180019DC5
0x180019db3  movzx   r15d, word ptr [rsp+130h+fdwSentence]
0x180019db9  movzx   eax, word ptr [rsp+130h+fdwConversion]
0x180019dbe  shl     r15d, 10h
0x180019dc2  or      r15d, eax
0x180019dc5  mov     rcx, rdi; HIMC
0x180019dc8  call    cs:__imp_ImmGetOpenStatus
0x180019dce  mov     [rsp+130h+var_D8], r14
0x180019dd3  mov     esi, 1
0x180019dd8  test    eax, eax
0x180019dda  jnz     short loc_180019DF5
0x180019ddc  mov     esi, 2
0x180019de1  jmp     short loc_180019DF5
0x180019de3  mov     [rsp+130h+var_D8], r13
0x180019de8  call    ?HasActiveTsfInputContext@@YA_NXZ; HasActiveTsfInputContext(void)
0x180019ded  test    al, al
0x180019def  jnz     loc_18001A0D9
0x180019df5  xor     eax, eax
0x180019df7  mov     qword ptr [rbp+57h+var_60], r13
0x180019dfb  mov     [rbp+57h+var_C0], rax
0x180019dff  lea     r8, [rbp+57h+var_60]
0x180019e03  mov     rax, [rbx]
0x180019e06  lea     rdx, IID_ITfCompartmentMgr
0x180019e0d  xorps   xmm0, xmm0
0x180019e10  mov     qword ptr [rsp+130h+var_E8], r13
0x180019e15  mov     rcx, rbx
0x180019e18  mov     r12d, r13d
0x180019e1b  movups  [rbp+57h+var_D0], xmm0
0x180019e1f  mov     rax, [rax]
0x180019e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e27  mov     r14d, eax
0x180019e2a  test    eax, eax
0x180019e2c  js      short loc_180019E62
0x180019e2e  mov     rcx, qword ptr [rbp+57h+var_60]
0x180019e32  test    rcx, rcx
0x180019e35  jz      short loc_180019E94
0x180019e37  mov     rax, [rcx]
0x180019e3a  lea     r8, [rsp+130h+var_E8]
0x180019e3f  lea     rdx, GUID_COMPARTMENT_OPENSTATUS_EXPLICITLY_CHANGED_BY_USER
0x180019e46  mov     rax, [rax+18h]
0x180019e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e4f  mov     rcx, qword ptr [rbp+57h+var_60]
0x180019e53  mov     r14d, eax
0x180019e56  mov     rax, [rcx]
0x180019e59  mov     rax, [rax+10h]
0x180019e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e62  test    r14d, r14d
0x180019e65  js      short loc_180019E94
0x180019e67  mov     rcx, qword ptr [rsp+130h+var_E8]
0x180019e6c  lea     rdx, [rbp+57h+var_D0]
0x180019e70  mov     rax, [rcx]
0x180019e73  mov     rax, [rax+20h]
0x180019e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e7c  mov     rcx, qword ptr [rsp+130h+var_E8]
0x180019e81  test    eax, eax
0x180019e83  cmovz   r12d, dword ptr [rbp+57h+var_D0+8]
0x180019e88  mov     rax, [rcx]
0x180019e8b  mov     rax, [rax+10h]
0x180019e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e94  mov     rcx, [rbx+0B80h]
0x180019e9b  test    rcx, rcx
0x180019e9e  jnz     loc_180019FC6
0x180019ea4  xor     eax, eax
0x180019ea6  mov     r14d, 1
0x180019eac  mov     ecx, 0FFFh
0x180019eb1  and     r12w, r14w
0x180019eb5  and     r13w, cx
0x180019eb9  shl     r12w, 0Dh
0x180019ebe  or      r12w, r13w
0x180019ec2  or      r12w, ax
0x180019ec6  jz      loc_18001A108
0x180019ecc  mov     r14d, 48h ; 'H'
0x180019ed2  lea     rcx, [rbp+57h+var_B0]; void *
0x180019ed6  mov     r8d, r14d; Size
0x180019ed9  xor     edx, edx; Val
0x180019edb  call    memset_0
0x180019ee0  mov     [rbp+57h+var_B0], 480020h
0x180019ee7  call    cs:__imp_GetCurrentThreadId
0x180019eed  lea     rcx, [rbp+57h+var_B0]; this
0x180019ef1  mov     [rbp+57h+var_88], 100001Ch
0x180019ef8  mov     [rbp+57h+var_84], eax
0x180019efb  movzx   eax, si
0x180019efe  mov     [rbp+57h+var_78], eax
0x180019f01  mov     [rbp+57h+var_74], r15d
0x180019f05  call    ?Send@MsgBase@@QEAAJK@Z; MsgBase::Send(ulong)
0x180019f0a  test    eax, eax
0x180019f0c  js      short loc_180019F80
0x180019f0e  xor     r13d, r13d
0x180019f11  mov     [rbx+0E60h], si
0x180019f18  mov     eax, 20000h
0x180019f1d  mov     [rbx+0E64h], r15d
0x180019f24  movzx   r14d, r15w
0x180019f28  lea     ecx, [r13+1]
0x180019f2c  cmp     si, cx
0x180019f2f  cmovz   r13d, eax
0x180019f33  xor     ecx, ecx
0x180019f35  mov     eax, 10000h
0x180019f3a  lea     edx, [rcx+10h]
0x180019f3d  cmp     si, dx
0x180019f40  cmovz   ecx, eax
0x180019f43  cmp     [rsp+130h+var_F0], 0
0x180019f48  mov     [rsp+130h+var_E8], ecx
0x180019f4c  jz      short loc_180019F60
0x180019f4e  mov     rax, [rbx+0D0h]
0x180019f55  cmp     qword ptr [rax+60h], 0
0x180019f5a  jnz     loc_18001A131
0x180019f60  mov     rax, [rbx+0D0h]
0x180019f67  mov     rdx, [rax+88h]; hwnd
0x180019f6e  test    rdx, rdx
0x180019f71  jnz     loc_18001A1AC
0x180019f77  test    rdi, rdi
0x180019f7a  jnz     loc_18001A002
0x180019f80  mov     r14d, 1
0x180019f86  cmp     si, [rbx+0E60h]
0x180019f8d  jz      loc_18001A1E7
0x180019f93  test    rdi, rdi
0x180019f96  jz      short loc_180019FA6
0x180019f98  mov     rcx, [rsp+130h+var_D8]; HWND
0x180019f9d  mov     rdx, rdi; HIMC
0x180019fa0  call    cs:__imp_ImmReleaseContext
0x180019fa6  mov     rcx, [rbp+57h+var_50]
0x180019faa  xor     rcx, rsp; StackCookie
0x180019fad  call    __security_check_cookie
0x180019fb2  add     rsp, 0F8h
0x180019fb9  pop     r15
0x180019fbb  pop     r14
0x180019fbd  pop     r13
0x180019fbf  pop     r12
0x180019fc1  pop     rdi
0x180019fc2  pop     rsi
0x180019fc3  pop     rbx
0x180019fc4  pop     rbp
0x180019fc5  retn
0x180019fc6  mov     rax, [rcx]
0x180019fc9  mov     rax, [rax+48h]
0x180019fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fd2  mov     qword ptr [rbp+57h+var_60], r13
0x180019fd6  mov     r14, rax
0x180019fd9  test    rax, rax
0x180019fdc  jz      short loc_180019FF8
0x180019fde  mov     rcx, [rax]
0x180019fe1  mov     rax, [rcx+0E0h]
0x180019fe8  mov     rcx, r14
0x180019feb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ff0  test    al, al
0x180019ff2  jz      loc_18001A084
0x180019ff8  mov     esi, 10h
0x180019ffd  jmp     loc_180019EA4
0x18001a002  mov     rcx, rbx; this
0x18001a005  xor     r12d, r12d
0x18001a008  xor     r13d, r13d
0x18001a00b  call    ?GetTopInputContext@CThreadInputMgr@@QEBAPEAUIInputContextPrivate@@XZ; CThreadInputMgr::GetTopInputContext(void)
0x18001a010  mov     r14, rax
0x18001a013  test    rax, rax
0x18001a016  jz      short loc_18001A055
0x18001a018  mov     rcx, [rax]
0x18001a01b  mov     qword ptr [rbp+57h+var_60], r12
0x18001a01f  mov     rax, [rcx+0B8h]
0x18001a026  mov     rcx, r14
0x18001a029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a02e  mov     rcx, [r14]
0x18001a031  lea     rdx, [rbp+57h+var_60]
0x18001a035  mov     [rsp+130h+var_F0], al
0x18001a039  mov     rax, [rcx+58h]
0x18001a03d  mov     rcx, r14
0x18001a040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a045  test    eax, eax
0x18001a047  mov     al, [rsp+130h+var_F0]
0x18001a04b  js      short loc_18001A055
0x18001a04d  mov     r12d, [rbp+57h+var_60+4]
0x18001a051  mov     r13d, [rbp+57h+var_60]
0x18001a055  mov     r8d, [rsp+130h+fdwConversion]; unsigned int
0x18001a05a  lea     rcx, [rbx+0C38h]; this
0x18001a061  mov     [rsp+130h+var_108], al; bool
0x18001a065  mov     r14d, 1
0x18001a06b  cmp     si, r14w
0x18001a06f  mov     [rsp+130h+var_110], r13d; unsigned int
0x18001a074  mov     r9d, r12d; unsigned int
0x18001a077  setz    dl; bool
0x18001a07a  call    ?OnStatusChanged@CInputSessionMgr@@QEAAX_NKKK0@Z; CInputSessionMgr::OnStatusChanged(bool,ulong,ulong,ulong,bool)
0x18001a07f  jmp     loc_180019F86
0x18001a084  cmp     [rsp+130h+var_EF], r13b
0x18001a089  jz      loc_180019EA4
0x18001a08f  mov     rax, [r14]
0x18001a092  lea     rdx, [rbp+57h+var_60]
0x18001a096  mov     rcx, r14
0x18001a099  mov     rax, [rax+58h]
0x18001a09d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0a2  test    eax, eax
0x18001a0a4  js      loc_180019EA4
0x18001a0aa  mov     r13d, [rbp+57h+var_60]
0x18001a0ae  mov     eax, 1000h
0x18001a0b3  jmp     loc_180019EA6
0x18001a0b8  cmp     r10d, 2
0x18001a0bc  jnz     loc_180019D6C
0x18001a0c2  cmp     [rbx+0EB0h], r13
0x18001a0c9  jz      loc_180019FA6
0x18001a0cf  mov     [rsp+130h+var_F0], r13b
0x18001a0d4  jmp     loc_180019D6C
0x18001a0d9  xor     ecx, ecx; HWND
0x18001a0db  call    cs:__imp_ImmGetDefaultIMEWnd
0x18001a0e1  mov     r14, rax
0x18001a0e4  test    rax, rax
0x18001a0e7  jz      loc_180019DF5
0x18001a0ed  mov     rcx, rax; HWND
0x18001a0f0  call    cs:__imp_ImmGetContext
0x18001a0f6  mov     rdi, rax
0x18001a0f9  jmp     loc_180019D93
0x18001a0fe  mov     [rsp+130h+var_D8], r13
0x18001a103  jmp     loc_180019DF5
0x18001a108  cmp     si, [rbx+0E60h]
0x18001a10f  jnz     loc_180019ECC
0x18001a115  cmp     si, r14w
0x18001a119  jnz     loc_180019F86
0x18001a11f  cmp     r15d, [rbx+0E64h]
0x18001a126  jz      loc_180019F86
0x18001a12c  jmp     loc_180019ECC
0x18001a131  lea     rcx, [rbx+0A8h]
0x18001a138  xorps   xmm0, xmm0
0x18001a13b  mov     rax, [rcx]
0x18001a13e  lea     rdx, [rbp+57h+var_60]
0x18001a142  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x18001a146  mov     rax, [rax+0D0h]
0x18001a14d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a152  test    eax, eax
0x18001a154  js      short loc_18001A1A3
0x18001a156  mov     rax, [rbx+0D0h]
0x18001a15d  mov     edx, 10h
0x18001a162  movaps  xmm0, xmmword ptr [rbp+57h+var_60]
0x18001a166  cmp     si, dx
0x18001a169  mov     r8d, 1
0x18001a16f  mov     word ptr [rsp+130h+var_108], r14w
0x18001a175  setz    dl
0x18001a178  movdqa  [rbp+57h+var_D0], xmm0
0x18001a17d  mov     rcx, [rax+60h]
0x18001a181  cmp     si, r8w
0x18001a185  mov     byte ptr [rsp+130h+var_110], dl
0x18001a189  lea     rdx, [rbp+57h+var_D0]
0x18001a18d  setz    r9b
0x18001a191  xor     r8d, r8d
0x18001a194  mov     rax, [rcx]
0x18001a197  mov     rax, [rax+88h]
0x18001a19e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1a3  mov     ecx, [rsp+130h+var_E8]
0x18001a1a7  jmp     loc_180019F60
0x18001a1ac  and     r14d, 0FFFh
0x18001a1b3  movzx   r8d, r12w
0x18001a1b7  or      r14d, ecx
0x18001a1ba  shl     r8d, 10h
0x18001a1be  mov     r9d, r15d
0x18001a1c1  or      r14d, r13d
0x18001a1c4  shr     r9d, 10h
0x18001a1c8  or      r8d, 3; idObject
0x18001a1cc  shl     r14d, 0Eh
0x18001a1d0  and     r9d, 1Fh
  ... truncated ...
```
