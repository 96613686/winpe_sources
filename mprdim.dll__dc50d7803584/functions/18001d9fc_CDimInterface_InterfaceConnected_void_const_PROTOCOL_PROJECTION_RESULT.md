# CDimInterface::InterfaceConnected(void * const,_PROTOCOL_PROJECTION_RESULT *)

- ea: `0x18001d9fc`
- end: `0x18001dedd`
- name: `?InterfaceConnected@CDimInterface@@QEAAKQEAXPEAU_PROTOCOL_PROJECTION_RESULT@@@Z`
- size: `1249`
- prototype: `unsigned int __fastcall(CDimInterface *__hidden this, void *const, struct _PROTOCOL_PROJECTION_RESULT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180025cb0`

## callees

- `0x18000df70`
- `0x18001d9fc`
- `0x1800219f4`
- `0x18002e15c`
- `0x18002e664`
- `0x180045d40`
- `0x180045d7c`
- `0x180045da4`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dc27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dc27`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001dc1a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001dc1a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001dd8e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001dd8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001ddc2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001ddc2`
- `MPRDDM!ReConnectPersistentInterface` at `0x18001dc66`
- `MPRDDM!TimerQRemove` at `0x18001dc51`
- `MPRDDM!TimerQRemove` at `0x18001dc70`
- `MPRDDM!TimerQRemove` at `0x18001dc51`
- `MPRDDM!TimerQRemove` at `0x18001dc70`
- `MPRDDM!ReConnectInterface` at `0x18001dc47`

## string_xrefs

- `0x18001daf6`: `CDimInterface::InterfaceConnected interface already connected`
- `0x18001dcf9`: `CDimInterface::InterfaceConnected Notifying protocol %d that interface is connected`
- `0x18001ddd8`: `CDimInterface::InterfaceConnected Notifying protocol %d that interface is UnReachable INTERFACE_CONNECTION_FAILURE, error code %d`

## pseudocode

```c
__int64 __fastcall CDimInterface::InterfaceConnected(
        CDimInterface *this,
        void *const a2,
        struct _PROTOCOL_PROJECTION_RESULT *a3)
{
  struct _PROTOCOL_PROJECTION_RESULT *v3; // rsi
  int v6; // r12d
  __int64 v7; // rax
  __int128 *v8; // r9
  unsigned int v9; // eax
  __int64 v10; // rax
  __int128 *v11; // r9
  __int64 v12; // rbx
  int v13; // eax
  __int64 v14; // rax
  char *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rbx
  int v19; // eax
  _QWORD *v20; // rdi
  _QWORD *v21; // rbx
  unsigned int v22; // r12d
  unsigned int v23; // esi
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // rax
  __int128 *v27; // r9
  RTL_SRWLOCK *v28; // rsi
  struct CDimRouterManager::_ROUTER *Router; // rax
  void (__fastcall *v30)(__int64, _QWORD, struct _PROTOCOL_PROJECTION_RESULT *); // rax
  __int64 v31; // rax
  __int128 *v32; // r9
  __int64 v33; // rcx
  _QWORD *i; // rax
  int v36; // [rsp+30h] [rbp-D0h]
  __int64 v38; // [rsp+40h] [rbp-C0h]
  __int128 v39; // [rsp+48h] [rbp-B8h] BYREF
  GUID ActivityId; // [rsp+58h] [rbp-A8h] BYREF
  int v41; // [rsp+68h] [rbp-98h] BYREF
  __int128 v42; // [rsp+6Ch] [rbp-94h]
  __int128 v43; // [rsp+7Ch] [rbp-84h]
  int v44; // [rsp+8Ch] [rbp-74h]
  int v45; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v46[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  v3 = a3;
  v45 = 0;
  ActivityId = 0;
  v39 = 0;
  memset_0(v46, 0, sizeof(v46));
  v41 = 0;
  v44 = 0;
  v42 = 0;
  v43 = 0;
  v6 = SetActivityId((LPGUID)this + 194);
  v36 = v6;
  (**(void (__fastcall ***)(CDimInterface *))this)(this);
  if ( (*(unsigned int (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 40LL))(this) == 2 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
    {
      LOWORD(v41) = 0;
      v7 = (*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 280LL))(this);
      v8 = &v39;
      if ( this != (CDimInterface *)-3104LL )
        LODWORD(v8) = (_DWORD)this + 3104;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDimParamTraceInfo,
        (unsigned int)L"CDimInterface::InterfaceConnected interface already connected",
        (_DWORD)v8,
        v7,
        (__int64)&v41);
    }
  }
  else
  {
    if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
    {
      LOWORD(v45) = 0;
      LOWORD(v41) = 0;
      v9 = (*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 40LL))(this);
      FormatRRASErrorString(&v45, L"CDimInterface::InterfaceConnected Changing state from %d to CONNECTED", v9);
      if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
      {
        v10 = (*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 280LL))(this);
        v11 = &v39;
        if ( this != (CDimInterface *)-3104LL )
          LODWORD(v11) = (_DWORD)this + 3104;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDimParamTraceInfo,
          (unsigned int)&v45,
          (_DWORD)v11,
          v10,
          (__int64)&v41);
      }
    }
    (*(void (__fastcall **)(CDimInterface *, void *const))(*(_QWORD *)this + 256LL))(this, a2);
    (*(void (__fastcall **)(CDimInterface *, __int64))(*(_QWORD *)this + 48LL))(this, 2);
    (*(void (__fastcall **)(CDimInterface *, _QWORD))(*(_QWORD *)this + 32LL))(this, 0);
    v12 = *(_QWORD *)this;
    v13 = (*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 104LL))(this);
    (*(void (__fastcall **)(CDimInterface *, _QWORD))(v12 + 112))(this, v13 & 0xFFFFFFDF);
    v14 = *(_QWORD *)this;
    *((_DWORD *)this + 38) = 0;
    if ( ((*(__int64 (__fastcall **)(CDimInterface *))(v14 + 104))(this) & 1) == 0 )
    {
      v15 = (char *)*((_QWORD *)this + 20);
      if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        SetEvent(v15);
        CloseHandle(*((HANDLE *)this + 20));
        *((_QWORD *)this + 20) = -1;
      }
    }
    v16 = (*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 16LL))(this);
    TimerQRemove(v16, ReConnectInterface);
    v17 = (*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 16LL))(this);
    TimerQRemove(v17, ReConnectPersistentInterface);
    v18 = *(_QWORD *)this;
    v19 = (*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 104LL))(this);
    (*(void (__fastcall **)(CDimInterface *, _QWORD))(v18 + 112))(this, v19 & 0xFFFFF7FF);
    v20 = (_QWORD *)*((_QWORD *)this + 34);
    v21 = (_QWORD *)*v20;
    while ( v21 != v20 )
    {
      v22 = *((_DWORD *)v21 + 6);
      if ( v22 == 33 )
      {
        v23 = *((_DWORD *)v3 + 1);
      }
      else
      {
        v23 = 0;
        if ( v22 == 87 )
          v23 = *((_DWORD *)a3 + 15);
      }
      if ( (*(unsigned __int8 (__fastcall **)(CDimInterface *, _QWORD))(*(_QWORD *)this + 384LL))(this, v22) )
      {
        if ( v23 )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
          {
            LOWORD(v45) = 0;
            LOWORD(v41) = 0;
            FormatRRASErrorString(
              &v45,
              L"CDimInterface::InterfaceConnected Notifying protocol %d that interface is UnReachable INTERFACE_CONNECTION"
               "_FAILURE, error code %d",
              v22,
              v23);
            if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
            {
              v31 = (*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 280LL))(this);
              v32 = &v39;
              if ( this != (CDimInterface *)-3104LL )
                LODWORD(v32) = (_DWORD)this + 3104;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasDimParamTraceInfo,
                (unsigned int)&v45,
                (_DWORD)v32,
                v31,
                (__int64)&v41);
            }
          }
          CDimRouterManager::InterfaceNotReachable(v24, v22, v21[4], 1);
        }
        else
        {
          if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
          {
            LOWORD(v45) = 0;
            LOWORD(v41) = 0;
            FormatRRASErrorString(
              &v45,
              L"CDimInterface::InterfaceConnected Notifying protocol %d that interface is connected",
              v22);
            if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
            {
              v26 = (*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 280LL))(this);
              v27 = &v39;
              if ( this != (CDimInterface *)-3104LL )
                LODWORD(v27) = (_DWORD)this + 3104;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasDimParamTraceInfo,
                (unsigned int)&v45,
                (_DWORD)v27,
                v26,
                (__int64)&v41);
            }
          }
          LOBYTE(v25) = 1;
          (*(void (__fastcall **)(CDimInterface *, _QWORD, __int64))(*(_QWORD *)this + 416LL))(this, v22, v25);
          v28 = (RTL_SRWLOCK *)g_pCDimRouterManager;
          v38 = v21[4];
          AcquireSRWLockShared((PSRWLOCK)g_pCDimRouterManager + 1);
          Router = CDimRouterManager::GetRouter((CDimRouterManager *)v28, v22);
          if ( Router )
          {
            v30 = (void (__fastcall *)(__int64, _QWORD, struct _PROTOCOL_PROJECTION_RESULT *))*((_QWORD *)Router + 3);
            if ( v30 )
              v30(v38, 0, a3);
          }
          ReleaseSRWLockShared(v28 + 1);
        }
      }
      v3 = a3;
      if ( !*((_BYTE *)v21 + 49) )
      {
        v33 = v21[2];
        if ( *(_BYTE *)(v33 + 49) )
        {
          for ( i = (_QWORD *)v21[1]; !*((_BYTE *)i + 49) && v21 == (_QWORD *)i[2]; i = (_QWORD *)i[1] )
            v21 = i;
        }
        else
        {
          i = std::_Tree_val<std::_Tmap_traits<void *,std::tr1::shared_ptr<CDimInterface>,std::less<void *>,std::allocator<std::pair<void * const,std::tr1::shared_ptr<CDimInterface>>>,0>>::_Min((_QWORD *)v33);
        }
        v21 = i;
      }
    }
    v6 = v36;
  }
  (*(void (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 8LL))(this);
  if ( v6 )
    ReSetActivityId(&ActivityId);
  return 0;
}

```

## disassembly

```asm
0x18001d9fc  push    rbp
0x18001d9fe  push    rbx
0x18001d9ff  push    rsi
0x18001da00  push    rdi
0x18001da01  push    r12
0x18001da03  push    r13
0x18001da05  push    r14
0x18001da07  lea     rbp, [rsp-7A0h]
0x18001da0f  sub     rsp, 8A0h
0x18001da16  mov     rax, cs:__security_cookie
0x18001da1d  xor     rax, rsp
0x18001da20  mov     [rbp+7D0h+var_40], rax
0x18001da27  mov     rsi, r8
0x18001da2a  mov     [rsp+8D0h+var_898], r8
0x18001da2f  mov     rbx, rdx
0x18001da32  mov     r14, rcx
0x18001da35  xorps   xmm0, xmm0
0x18001da38  lea     rcx, [rbp+7D0h+var_83C]; void *
0x18001da3c  xorps   xmm1, xmm1
0x18001da3f  xor     eax, eax
0x18001da41  xor     edx, edx; Val
0x18001da43  mov     [rbp+7D0h+var_840], eax
0x18001da46  mov     r8d, 7FCh; Size
0x18001da4c  movups  xmmword ptr [rsp+8D0h+ActivityId.Data1], xmm0
0x18001da51  movups  [rsp+8D0h+var_888], xmm1
0x18001da56  call    memset_0
0x18001da5b  xor     eax, eax
0x18001da5d  lea     r13, [r14+0C20h]
0x18001da64  xorps   xmm0, xmm0
0x18001da67  mov     [rsp+8D0h+var_868], eax
0x18001da6b  mov     rcx, r13; ActivityId
0x18001da6e  mov     [rbp+7D0h+var_844], eax
0x18001da71  lea     rdx, [rsp+8D0h+ActivityId]
0x18001da76  movups  [rsp+8D0h+var_864], xmm0
0x18001da7b  movups  [rsp+8D0h+var_854], xmm0
0x18001da80  call    SetActivityId
0x18001da85  mov     rcx, [r14]
0x18001da88  mov     r12d, eax
0x18001da8b  mov     [rsp+8D0h+var_8A0], eax
0x18001da8f  mov     rax, [rcx]
0x18001da92  mov     rcx, r14
0x18001da95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da9a  mov     rcx, [r14]
0x18001da9d  mov     rax, [rcx+28h]
0x18001daa1  mov     rcx, r14
0x18001daa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001daa9  cmp     eax, 2
0x18001daac  jnz     short loc_18001DB0E
0x18001daae  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x18001dab5  jz      loc_18001DE9C
0x18001dabb  xor     eax, eax
0x18001dabd  mov     rcx, r14
0x18001dac0  mov     word ptr [rsp+8D0h+var_868], ax
0x18001dac5  mov     rax, [r14]
0x18001dac8  mov     rax, [rax+118h]
0x18001dacf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dad4  test    r13, r13
0x18001dad7  lea     rcx, [rsp+8D0h+var_868]
0x18001dadc  mov     [rsp+8D0h+var_8A8], rcx
0x18001dae1  lea     r9, [rsp+8D0h+var_888]
0x18001dae6  cmovnz  r9, r13
0x18001daea  mov     [rsp+8D0h+var_8B0], rax
0x18001daef  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001daf6  lea     r8, aCdiminterfaceI_1; "CDimInterface::InterfaceConnected inter"...
0x18001dafd  lea     rdx, RasDimParamTraceInfo
0x18001db04  call    McTemplateU0zjzz_EventWriteTransfer
0x18001db09  jmp     loc_18001DE9C
0x18001db0e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x18001db15  jz      short loc_18001DB91
0x18001db17  xor     eax, eax
0x18001db19  mov     rcx, r14
0x18001db1c  mov     word ptr [rbp+7D0h+var_840], ax
0x18001db20  mov     word ptr [rsp+8D0h+var_868], ax
0x18001db25  mov     rax, [r14]
0x18001db28  mov     rax, [rax+28h]
0x18001db2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db31  mov     r8d, eax
0x18001db34  lea     rdx, aCdiminterfaceI_2; "CDimInterface::InterfaceConnected Chang"...
0x18001db3b  lea     rcx, [rbp+7D0h+var_840]
0x18001db3f  call    FormatRRASErrorString
0x18001db44  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x18001db4b  jz      short loc_18001DB91
0x18001db4d  mov     rax, [r14]
0x18001db50  mov     rcx, r14
0x18001db53  mov     rax, [rax+118h]
0x18001db5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db5f  test    r13, r13
0x18001db62  lea     rcx, [rsp+8D0h+var_868]
0x18001db67  mov     [rsp+8D0h+var_8A8], rcx
0x18001db6c  lea     r9, [rsp+8D0h+var_888]
0x18001db71  cmovnz  r9, r13
0x18001db75  mov     [rsp+8D0h+var_8B0], rax
0x18001db7a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001db81  lea     r8, [rbp+7D0h+var_840]
0x18001db85  lea     rdx, RasDimParamTraceInfo
0x18001db8c  call    McTemplateU0zjzz_EventWriteTransfer
0x18001db91  mov     rax, [r14]
0x18001db94  mov     rdx, rbx
0x18001db97  mov     rcx, r14
0x18001db9a  mov     rax, [rax+100h]
0x18001dba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dba6  mov     rax, [r14]
0x18001dba9  mov     edx, 2
0x18001dbae  mov     rcx, r14
0x18001dbb1  mov     rax, [rax+30h]
0x18001dbb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbba  mov     rax, [r14]
0x18001dbbd  xor     edx, edx
0x18001dbbf  mov     rcx, r14
0x18001dbc2  mov     rax, [rax+20h]
0x18001dbc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbcb  mov     rbx, [r14]
0x18001dbce  mov     rcx, r14
0x18001dbd1  mov     rax, [rbx+68h]
0x18001dbd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbda  and     eax, 0FFFFFFDFh
0x18001dbdd  mov     rcx, r14
0x18001dbe0  mov     edx, eax
0x18001dbe2  mov     rax, [rbx+70h]
0x18001dbe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbeb  mov     rax, [r14]
0x18001dbee  mov     rcx, r14
0x18001dbf1  mov     dword ptr [r14+98h], 0
0x18001dbfc  mov     rax, [rax+68h]
0x18001dc00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc05  test    al, 1
0x18001dc07  jnz     short loc_18001DC38
0x18001dc09  mov     rcx, [r14+0A0h]; hEvent
0x18001dc10  lea     rax, [rcx-1]
0x18001dc14  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001dc18  ja      short loc_18001DC38
0x18001dc1a  call    cs:__imp_SetEvent
0x18001dc20  mov     rcx, [r14+0A0h]; hObject
0x18001dc27  call    cs:__imp_CloseHandle
0x18001dc2d  mov     qword ptr [r14+0A0h], 0FFFFFFFFFFFFFFFFh
0x18001dc38  mov     rax, [r14]
0x18001dc3b  mov     rcx, r14
0x18001dc3e  mov     rax, [rax+10h]
0x18001dc42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc47  mov     rdx, cs:__imp_ReConnectInterface
0x18001dc4e  mov     rcx, rax
0x18001dc51  call    cs:__imp_TimerQRemove
0x18001dc57  mov     rax, [r14]
0x18001dc5a  mov     rcx, r14
0x18001dc5d  mov     rax, [rax+10h]
0x18001dc61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc66  mov     rdx, cs:__imp_ReConnectPersistentInterface
0x18001dc6d  mov     rcx, rax
0x18001dc70  call    cs:__imp_TimerQRemove
0x18001dc76  mov     rbx, [r14]
0x18001dc79  mov     rcx, r14
0x18001dc7c  mov     rax, [rbx+68h]
0x18001dc80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc85  btr     eax, 0Bh
0x18001dc89  mov     rcx, r14
0x18001dc8c  mov     edx, eax
0x18001dc8e  mov     rax, [rbx+70h]
0x18001dc92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc97  mov     rdi, [r14+110h]
0x18001dc9e  mov     rbx, [rdi]
0x18001dca1  cmp     rbx, rdi
0x18001dca4  jz      loc_18001DE97
0x18001dcaa  mov     r12d, [rbx+18h]
0x18001dcae  cmp     r12d, 21h ; '!'
0x18001dcb2  jz      short loc_18001DCC6
0x18001dcb4  xor     esi, esi
0x18001dcb6  cmp     r12d, 57h ; 'W'
0x18001dcba  jnz     short loc_18001DCC9
0x18001dcbc  mov     rax, [rsp+8D0h+var_898]
0x18001dcc1  mov     esi, [rax+3Ch]
0x18001dcc4  jmp     short loc_18001DCC9
0x18001dcc6  mov     esi, [rsi+4]
0x18001dcc9  mov     rax, [r14]
0x18001dccc  mov     edx, r12d
0x18001dccf  mov     rcx, r14
0x18001dcd2  mov     rax, [rax+180h]
0x18001dcd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dcde  test    al, al
0x18001dce0  jz      loc_18001DE56
0x18001dce6  test    esi, esi
0x18001dce8  jnz     loc_18001DDCD
0x18001dcee  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x18001dcf5  jz      short loc_18001DD62
0x18001dcf7  xor     eax, eax
0x18001dcf9  lea     rdx, aCdiminterfaceI_0; "CDimInterface::InterfaceConnected Notif"...
0x18001dd00  mov     r8d, r12d
0x18001dd03  mov     word ptr [rbp+7D0h+var_840], ax
0x18001dd07  lea     rcx, [rbp+7D0h+var_840]
0x18001dd0b  mov     word ptr [rsp+8D0h+var_868], ax
0x18001dd10  call    FormatRRASErrorString
0x18001dd15  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x18001dd1c  jz      short loc_18001DD62
0x18001dd1e  mov     rax, [r14]
0x18001dd21  mov     rcx, r14
0x18001dd24  mov     rax, [rax+118h]
0x18001dd2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd30  test    r13, r13
0x18001dd33  lea     rcx, [rsp+8D0h+var_868]
0x18001dd38  mov     [rsp+8D0h+var_8A8], rcx
0x18001dd3d  lea     r9, [rsp+8D0h+var_888]
0x18001dd42  cmovnz  r9, r13
0x18001dd46  mov     [rsp+8D0h+var_8B0], rax
0x18001dd4b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001dd52  lea     r8, [rbp+7D0h+var_840]
0x18001dd56  lea     rdx, RasDimParamTraceInfo
0x18001dd5d  call    McTemplateU0zjzz_EventWriteTransfer
0x18001dd62  mov     rax, [r14]
0x18001dd65  mov     r8b, 1
0x18001dd68  mov     edx, r12d
0x18001dd6b  mov     rcx, r14
0x18001dd6e  mov     rax, [rax+1A0h]
0x18001dd75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd7a  mov     rsi, cs:?g_pCDimRouterManager@@3PEAVCDimRouterManager@@EA; CDimRouterManager * g_pCDimRouterManager
0x18001dd81  mov     rax, [rbx+20h]
0x18001dd85  mov     [rsp+8D0h+var_890], rax
0x18001dd8a  lea     rcx, [rsi+8]; SRWLock
0x18001dd8e  call    cs:__imp_AcquireSRWLockShared
0x18001dd94  mov     edx, r12d; unsigned int
0x18001dd97  mov     rcx, rsi; this
0x18001dd9a  call    ?GetRouter@CDimRouterManager@@AEAAPEAU_ROUTER@1@K@Z; CDimRouterManager::GetRouter(ulong)
0x18001dd9f  test    rax, rax
0x18001dda2  jz      short loc_18001DDBE
0x18001dda4  mov     rax, [rax+18h]
0x18001dda8  test    rax, rax
0x18001ddab  jz      short loc_18001DDBE
0x18001ddad  mov     r8, [rsp+8D0h+var_898]
0x18001ddb2  xor     edx, edx
0x18001ddb4  mov     rcx, [rsp+8D0h+var_890]
0x18001ddb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ddbe  lea     rcx, [rsi+8]; SRWLock
0x18001ddc2  call    cs:__imp_ReleaseSRWLockShared
0x18001ddc8  jmp     loc_18001DE56
0x18001ddcd  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x18001ddd4  jz      short loc_18001DE44
0x18001ddd6  xor     eax, eax
0x18001ddd8  lea     rdx, aCdiminterfaceI; "CDimInterface::InterfaceConnected Notif"...
0x18001dddf  mov     r9d, esi
0x18001dde2  mov     word ptr [rbp+7D0h+var_840], ax
0x18001dde6  mov     r8d, r12d
0x18001dde9  mov     word ptr [rsp+8D0h+var_868], ax
0x18001ddee  lea     rcx, [rbp+7D0h+var_840]
0x18001ddf2  call    FormatRRASErrorString
0x18001ddf7  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x18001ddfe  jz      short loc_18001DE44
0x18001de00  mov     rax, [r14]
0x18001de03  mov     rcx, r14
0x18001de06  mov     rax, [rax+118h]
0x18001de0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de12  test    r13, r13
0x18001de15  lea     rcx, [rsp+8D0h+var_868]
0x18001de1a  mov     [rsp+8D0h+var_8A8], rcx
0x18001de1f  lea     r9, [rsp+8D0h+var_888]
0x18001de24  cmovnz  r9, r13
0x18001de28  mov     [rsp+8D0h+var_8B0], rax
0x18001de2d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001de34  lea     r8, [rbp+7D0h+var_840]
0x18001de38  lea     rdx, RasDimParamTraceInfo
0x18001de3f  call    McTemplateU0zjzz_EventWriteTransfer
0x18001de44  mov     r8, [rbx+20h]
0x18001de48  mov     r9d, 1
0x18001de4e  mov     edx, r12d
0x18001de51  call    ?InterfaceNotReachable@CDimRouterManager@@QEAAKKPEAXW4_UNREACHABILITY_REASON@@@Z; CDimRouterManager::InterfaceNotReachable(ulong,void *,_UNREACHABILITY_REASON)
0x18001de56  cmp     byte ptr [rbx+31h], 0
0x18001de5a  mov     rsi, [rsp+8D0h+var_898]
0x18001de5f  jnz     loc_18001DCA1
0x18001de65  mov     rcx, [rbx+10h]
0x18001de69  cmp     byte ptr [rcx+31h], 0
0x18001de6d  jnz     short loc_18001DE76
0x18001de6f  call    ?_Min@?$_Tree_val@V?$_Tmap_traits@PEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@U?$less@PEAX@3@V?$allocator@U?$pair@QEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@@std@@@3@$0A@@std@@@std@@SAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@PEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@U?$less@PEAX@3@V?$allocator@U?$pair@QEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@@std@@@3@$0A@@std@@@2@PEAU342@@Z; std::_Tree_val<std::_Tmap_traits<void *,std::tr1::shared_ptr<CDimInterface>,std::less<void *>,std::allocator<std::pair<void * const,std::tr1::shared_ptr<CDimInterface>>>,0>>::_Min(std::_Tree_nod<std::_Tmap_traits<void *,std::tr1::shared_ptr<CDimInterface>,std::less<void *>,std::allocator<std::pair<void * const,std::tr1::shared_ptr<CDimInterface>>>,0>>::_Node *)
0x18001de74  jmp     short loc_18001DE8F
0x18001de76  mov     rax, [rbx+8]
0x18001de7a  jmp     short loc_18001DE89
0x18001de7c  cmp     rbx, [rax+10h]
0x18001de80  jnz     short loc_18001DE8F
0x18001de82  mov     rbx, rax
0x18001de85  mov     rax, [rax+8]
0x18001de89  cmp     byte ptr [rax+31h], 0
0x18001de8d  jz      short loc_18001DE7C
0x18001de8f  mov     rbx, rax
0x18001de92  jmp     loc_18001DCA1
0x18001de97  mov     r12d, [rsp+8D0h+var_8A0]
0x18001de9c  mov     rax, [r14]
0x18001de9f  mov     rcx, r14
0x18001dea2  mov     rax, [rax+8]
0x18001dea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001deab  test    r12d, r12d
0x18001deae  jz      short loc_18001DEBA
0x18001deb0  lea     rcx, [rsp+8D0h+ActivityId]; ActivityId
0x18001deb5  call    ReSetActivityId
0x18001deba  xor     eax, eax
0x18001debc  mov     rcx, [rbp+7D0h+var_40]
0x18001dec3  xor     rcx, rsp; StackCookie
0x18001dec6  call    __security_check_cookie
0x18001decb  add     rsp, 8A0h
0x18001ded2  pop     r14
0x18001ded4  pop     r13
0x18001ded6  pop     r12
0x18001ded8  pop     rdi
0x18001ded9  pop     rsi
0x18001deda  pop     rbx
  ... truncated ...
```
