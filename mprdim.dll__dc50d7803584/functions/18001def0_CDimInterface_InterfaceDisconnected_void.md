# CDimInterface::InterfaceDisconnected(void * *)

- ea: `0x18001def0`
- end: `0x18001e40e`
- name: `?InterfaceDisconnected@CDimInterface@@UEAAXPEAPEAX@Z`
- size: `1310`
- prototype: `void __fastcall(CDimInterface *__hidden this, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000df70`
- `0x18001def0`
- `0x1800219f4`
- `0x18002e664`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e0c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e0c3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001e0b6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001e0b6`
- `MPRDDM!TimerQInsert` at `0x18001e3de`
- `MPRDDM!TimerQInsert` at `0x18001e3de`
- `MPRDDM!ReConnectPersistentInterface` at `0x18001e082`
- `MPRDDM!ReConnectPersistentInterface` at `0x18001e3cf`
- `MPRDDM!TimerQRemove` at `0x18001e06d`
- `MPRDDM!TimerQRemove` at `0x18001e08c`
- `MPRDDM!TimerQRemove` at `0x18001e06d`
- `MPRDDM!TimerQRemove` at `0x18001e08c`
- `MPRDDM!ReConnectInterface` at `0x18001e063`

## string_xrefs

- `0x18001e019`: `InterfaceDisconnected: Already in RISTATE_DISCONNECTED`

## pseudocode

```c
void __fastcall CDimInterface::InterfaceDisconnected(CDimInterface *this, void **a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int128 *v6; // r9
  __int64 v7; // rax
  __int64 v8; // rax
  __int128 *v9; // r9
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  char *v13; // rcx
  __int64 v14; // rax
  unsigned int v15; // ebx
  unsigned int v16; // eax
  __int64 v17; // rax
  __int128 *v18; // r9
  __int64 v19; // rbx
  int v20; // eax
  __int64 v21; // rbx
  int v22; // eax
  unsigned int v23; // r15d
  char v24; // r14
  _QWORD *v25; // rdi
  _QWORD *v26; // rbx
  __int64 v27; // rax
  unsigned int v28; // r13d
  __int64 v29; // rcx
  __int64 v30; // rax
  __int128 *v31; // r9
  __int64 v32; // rcx
  _QWORD *i; // rax
  __int64 v34; // rax
  char v35; // [rsp+30h] [rbp-D0h]
  __int128 v36; // [rsp+38h] [rbp-C8h] BYREF
  int v37; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v38; // [rsp+4Ch] [rbp-B4h]
  __int128 v39; // [rsp+5Ch] [rbp-A4h]
  int v40; // [rsp+6Ch] [rbp-94h]
  int v41; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v42[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v41 = 0;
  v36 = 0;
  memset_0(v42, 0, sizeof(v42));
  v37 = 0;
  v40 = 0;
  v38 = 0;
  v39 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
  {
    v4 = *(_QWORD *)this;
    LOWORD(v37) = 0;
    v5 = (*(__int64 (__fastcall **)(CDimInterface *))(v4 + 280))(this);
    v6 = &v36;
    if ( this != (CDimInterface *)-3104LL )
      LODWORD(v6) = (_DWORD)this + 3104;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasDimParamTraceInfo,
      (unsigned int)L"InterfaceDisconnected: Called",
      (_DWORD)v6,
      v5,
      (__int64)&v37);
  }
  if ( !(*(unsigned int (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 40LL))(this) )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
    {
      v7 = *(_QWORD *)this;
      LOWORD(v37) = 0;
      v8 = (*(__int64 (__fastcall **)(CDimInterface *))(v7 + 280))(this);
      v9 = &v36;
      if ( this != (CDimInterface *)-3104LL )
        LODWORD(v9) = (_DWORD)this + 3104;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDimParamTraceInfo,
        (unsigned int)L"InterfaceDisconnected: Already in RISTATE_DISCONNECTED",
        (_DWORD)v9,
        v8,
        (__int64)&v37);
    }
    return;
  }
  v35 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 56LL))(this) )
  {
    v10 = *(_QWORD *)this;
    v35 = 1;
    *((_DWORD *)this + 34) = 0;
    v11 = (*(__int64 (__fastcall **)(CDimInterface *))(v10 + 16))(this);
    TimerQRemove(v11, ReConnectInterface);
    v12 = (*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 16LL))(this);
    TimerQRemove(v12, ReConnectPersistentInterface);
  }
  if ( ((*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 104LL))(this) & 1) == 0 )
  {
    v13 = (char *)*((_QWORD *)this + 20);
    if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      SetEvent(v13);
      CloseHandle(*((HANDLE *)this + 20));
      *((_QWORD *)this + 20) = -1;
    }
  }
  *a2 = (void *)(*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 248LL))(this);
  if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
  {
    v14 = *(_QWORD *)this;
    LOWORD(v41) = 0;
    LOWORD(v37) = 0;
    v15 = (*(__int64 (__fastcall **)(CDimInterface *))(v14 + 104))(this);
    v16 = (*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 40LL))(this);
    FormatRRASErrorString(
      &v41,
      L"InterfaceDisconnected: Change state from %d to RISTATE_DISCONNECTED, Flags %x",
      v16,
      v15);
    if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
    {
      v17 = (*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 280LL))(this);
      v18 = &v36;
      if ( this != (CDimInterface *)-3104LL )
        LODWORD(v18) = (_DWORD)this + 3104;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDimParamTraceInfo,
        (unsigned int)&v41,
        (_DWORD)v18,
        v17,
        (__int64)&v37);
    }
  }
  (*(void (__fastcall **)(CDimInterface *, _QWORD))(*(_QWORD *)this + 48LL))(this, 0);
  (*(void (__fastcall **)(CDimInterface *, _QWORD))(*(_QWORD *)this + 256LL))(this, 0);
  v19 = *(_QWORD *)this;
  v20 = (*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 104LL))(this);
  (*(void (__fastcall **)(CDimInterface *, _QWORD))(v19 + 112))(this, v20 & 0xFFFFFFFE);
  v21 = *(_QWORD *)this;
  v22 = (*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 104LL))(this);
  (*(void (__fastcall **)(CDimInterface *, _QWORD))(v21 + 112))(this, v22 & 0xFFFFF7FF);
  (*(void (__fastcall **)(CDimInterface *, _QWORD))(*(_QWORD *)this + 272LL))(this, 0);
  if ( ((*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 104LL))(this) & 0x20) == 0 )
  {
    if ( ((*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 104LL))(this) & 8) != 0 )
    {
      v23 = 0;
    }
    else if ( (_DWORD)qword_180070F24 == 7 )
    {
      v23 = 3;
    }
    else
    {
      v23 = 4;
      if ( ((*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 104LL))(this) & 4) != 0 )
      {
        if ( ((*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 104LL))(this) & 0x40) == 0 )
        {
          v24 = 1;
          v23 = 5;
          goto LABEL_30;
        }
      }
      else
      {
        v23 = 2;
      }
    }
    v24 = 0;
LABEL_30:
    v25 = (_QWORD *)*((_QWORD *)this + 34);
    v26 = (_QWORD *)*v25;
    while ( 1 )
    {
      v27 = *(_QWORD *)this;
      if ( v26 == v25 )
        break;
      v28 = *((_DWORD *)v26 + 6);
      (*(void (__fastcall **)(CDimInterface *, _QWORD, _QWORD))(v27 + 416))(this, v28, 0);
      if ( !v24 && (*(unsigned __int8 (__fastcall **)(CDimInterface *, _QWORD))(*(_QWORD *)this + 384LL))(this, v28) )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
        {
          LOWORD(v41) = 0;
          LOWORD(v37) = 0;
          FormatRRASErrorString(
            &v41,
            L"InterfaceDisconnected: Marking InterfaceNotReachable in RouterManager for transport %d",
            v28);
          if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
          {
            v30 = (*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 280LL))(this);
            v31 = &v36;
            if ( this != (CDimInterface *)-3104LL )
              LODWORD(v31) = (_DWORD)this + 3104;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDimParamTraceInfo,
              (unsigned int)&v41,
              (_DWORD)v31,
              v30,
              (__int64)&v37);
          }
        }
        CDimRouterManager::InterfaceNotReachable(v29, v28, v26[4], v23);
      }
      if ( !*((_BYTE *)v26 + 49) )
      {
        v32 = v26[2];
        if ( *(_BYTE *)(v32 + 49) )
        {
          for ( i = (_QWORD *)v26[1]; !*((_BYTE *)i + 49) && v26 == (_QWORD *)i[2]; i = (_QWORD *)i[1] )
            v26 = i;
        }
        else
        {
          i = std::_Tree_val<std::_Tmap_traits<void *,std::tr1::shared_ptr<CDimInterface>,std::less<void *>,std::allocator<std::pair<void * const,std::tr1::shared_ptr<CDimInterface>>>,0>>::_Min((_QWORD *)v32);
        }
        v26 = i;
      }
    }
    if ( v24 )
    {
      if ( ((*(__int64 (__fastcall **)(CDimInterface *))(v27 + 104))(this) & 2) != 0 && !v35 )
      {
        v34 = (*(__int64 (__fastcall **)(CDimInterface *))(*(_QWORD *)this + 16LL))(this);
        TimerQInsert(v34, 1, ReConnectPersistentInterface);
      }
    }
    else
    {
      (*(void (__fastcall **)(CDimInterface *))(v27 + 72))(this);
    }
  }
}

```

## disassembly

```asm
0x18001def0  mov     [rsp-8+arg_10], rbx
0x18001def5  push    rbp
0x18001def6  push    rsi
0x18001def7  push    rdi
0x18001def8  push    r12
0x18001defa  push    r13
0x18001defc  push    r14
0x18001defe  push    r15
0x18001df00  lea     rbp, [rsp-780h]
0x18001df08  sub     rsp, 880h
0x18001df0f  mov     rax, cs:__security_cookie
0x18001df16  xor     rax, rsp
0x18001df19  mov     [rbp+7B0h+var_40], rax
0x18001df20  mov     rbx, rdx
0x18001df23  mov     rsi, rcx
0x18001df26  xorps   xmm0, xmm0
0x18001df29  lea     rcx, [rsp+8B0h+var_83C]; void *
0x18001df2e  xor     r13d, r13d
0x18001df31  xor     edx, edx; Val
0x18001df33  mov     r8d, 7FCh; Size
0x18001df39  mov     [rsp+8B0h+var_840], r13d
0x18001df3e  movups  [rsp+8B0h+var_878], xmm0
0x18001df43  call    memset_0
0x18001df48  xor     eax, eax
0x18001df4a  mov     [rsp+8B0h+var_868], r13d
0x18001df4f  xorps   xmm0, xmm0
0x18001df52  mov     [rsp+8B0h+var_844], eax
0x18001df56  mov     dil, 8
0x18001df59  lea     r14, RasDimParamTraceInfo
0x18001df60  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x18001df67  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001df6e  movups  [rsp+8B0h+var_864], xmm0
0x18001df73  lea     r12, [rsi+0C20h]
0x18001df7a  movups  [rsp+8B0h+var_854], xmm0
0x18001df7f  jz      short loc_18001DFC6
0x18001df81  mov     rax, [rsi]
0x18001df84  mov     rcx, rsi
0x18001df87  mov     word ptr [rsp+8B0h+var_868], r13w
0x18001df8d  mov     rax, [rax+118h]
0x18001df94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df99  test    r12, r12
0x18001df9c  lea     rcx, [rsp+8B0h+var_868]
0x18001dfa1  mov     [rsp+8B0h+var_888], rcx
0x18001dfa6  lea     r9, [rsp+8B0h+var_878]
0x18001dfab  cmovnz  r9, r12
0x18001dfaf  mov     [rsp+8B0h+var_890], rax
0x18001dfb4  mov     rcx, r15
0x18001dfb7  lea     r8, aInterfacedisco_1; "InterfaceDisconnected: Called"
0x18001dfbe  mov     rdx, r14
0x18001dfc1  call    McTemplateU0zjzz_EventWriteTransfer
0x18001dfc6  mov     rax, [rsi]
0x18001dfc9  mov     rcx, rsi
0x18001dfcc  mov     rax, [rax+28h]
0x18001dfd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfd5  test    eax, eax
0x18001dfd7  jnz     short loc_18001E030
0x18001dfd9  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x18001dfe0  jz      loc_18001E3E4
0x18001dfe6  mov     rax, [rsi]
0x18001dfe9  mov     rcx, rsi
0x18001dfec  mov     word ptr [rsp+8B0h+var_868], r13w
0x18001dff2  mov     rax, [rax+118h]
0x18001dff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dffe  test    r12, r12
0x18001e001  lea     r8, [rsp+8B0h+var_868]
0x18001e006  mov     [rsp+8B0h+var_888], r8
0x18001e00b  lea     r9, [rsp+8B0h+var_878]
0x18001e010  cmovnz  r9, r12
0x18001e014  mov     [rsp+8B0h+var_890], rax
0x18001e019  lea     r8, aInterfacedisco_2; "InterfaceDisconnected: Already in RISTA"...
0x18001e020  mov     rdx, r14
0x18001e023  mov     rcx, r15
0x18001e026  call    McTemplateU0zjzz_EventWriteTransfer
0x18001e02b  jmp     loc_18001E3E4
0x18001e030  mov     rax, [rsi]
0x18001e033  mov     rcx, rsi
0x18001e036  mov     [rsp+8B0h+var_880], r13b
0x18001e03b  mov     rax, [rax+38h]
0x18001e03f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e044  test    al, al
0x18001e046  jz      short loc_18001E092
0x18001e048  mov     rax, [rsi]
0x18001e04b  mov     rcx, rsi
0x18001e04e  mov     [rsp+8B0h+var_880], 1
0x18001e053  mov     [rsi+88h], r13d
0x18001e05a  mov     rax, [rax+10h]
0x18001e05e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e063  mov     rdx, cs:__imp_ReConnectInterface
0x18001e06a  mov     rcx, rax
0x18001e06d  call    cs:__imp_TimerQRemove
0x18001e073  mov     rax, [rsi]
0x18001e076  mov     rcx, rsi
0x18001e079  mov     rax, [rax+10h]
0x18001e07d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e082  mov     rdx, cs:__imp_ReConnectPersistentInterface
0x18001e089  mov     rcx, rax
0x18001e08c  call    cs:__imp_TimerQRemove
0x18001e092  mov     rax, [rsi]
0x18001e095  mov     rcx, rsi
0x18001e098  mov     rax, [rax+68h]
0x18001e09c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0a1  test    al, 1
0x18001e0a3  jnz     short loc_18001E0D4
0x18001e0a5  mov     rcx, [rsi+0A0h]; hEvent
0x18001e0ac  lea     rax, [rcx-1]
0x18001e0b0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001e0b4  ja      short loc_18001E0D4
0x18001e0b6  call    cs:__imp_SetEvent
0x18001e0bc  mov     rcx, [rsi+0A0h]; hObject
0x18001e0c3  call    cs:__imp_CloseHandle
0x18001e0c9  mov     qword ptr [rsi+0A0h], 0FFFFFFFFFFFFFFFFh
0x18001e0d4  mov     rax, [rsi]
0x18001e0d7  mov     rcx, rsi
0x18001e0da  mov     rax, [rax+0F8h]
0x18001e0e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0e6  mov     [rbx], rax
0x18001e0e9  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x18001e0f0  jz      loc_18001E186
0x18001e0f6  mov     rax, [rsi]
0x18001e0f9  mov     rcx, rsi
0x18001e0fc  mov     word ptr [rsp+8B0h+var_840], r13w
0x18001e102  mov     word ptr [rsp+8B0h+var_868], r13w
0x18001e108  mov     rax, [rax+68h]
0x18001e10c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e111  mov     rcx, [rsi]
0x18001e114  mov     ebx, eax
0x18001e116  mov     rax, [rcx+28h]
0x18001e11a  mov     rcx, rsi
0x18001e11d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e122  mov     r9d, ebx
0x18001e125  lea     rdx, aInterfacedisco; "InterfaceDisconnected: Change state fro"...
0x18001e12c  mov     r8d, eax
0x18001e12f  lea     rcx, [rsp+8B0h+var_840]
0x18001e134  call    FormatRRASErrorString
0x18001e139  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x18001e140  jz      short loc_18001E186
0x18001e142  mov     rax, [rsi]
0x18001e145  mov     rcx, rsi
0x18001e148  mov     rax, [rax+118h]
0x18001e14f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e154  lea     rcx, [rsi+0C20h]
0x18001e15b  mov     rdx, r14
0x18001e15e  test    rcx, rcx
0x18001e161  lea     r9, [rsp+8B0h+var_878]
0x18001e166  lea     r8, [rsp+8B0h+var_840]
0x18001e16b  cmovnz  r9, rcx
0x18001e16f  lea     rcx, [rsp+8B0h+var_868]
0x18001e174  mov     [rsp+8B0h+var_888], rcx
0x18001e179  mov     rcx, r15
0x18001e17c  mov     [rsp+8B0h+var_890], rax
0x18001e181  call    McTemplateU0zjzz_EventWriteTransfer
0x18001e186  mov     rax, [rsi]
0x18001e189  xor     edx, edx
0x18001e18b  mov     rcx, rsi
0x18001e18e  mov     rax, [rax+30h]
0x18001e192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e197  mov     rax, [rsi]
0x18001e19a  xor     edx, edx
0x18001e19c  mov     rcx, rsi
0x18001e19f  mov     rax, [rax+100h]
0x18001e1a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1ab  mov     rbx, [rsi]
0x18001e1ae  mov     rcx, rsi
0x18001e1b1  mov     rax, [rbx+68h]
0x18001e1b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1ba  and     eax, 0FFFFFFFEh
0x18001e1bd  mov     rcx, rsi
0x18001e1c0  mov     edx, eax
0x18001e1c2  mov     rax, [rbx+70h]
0x18001e1c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1cb  mov     rbx, [rsi]
0x18001e1ce  mov     rcx, rsi
0x18001e1d1  mov     rax, [rbx+68h]
0x18001e1d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1da  btr     eax, 0Bh
0x18001e1de  mov     rcx, rsi
0x18001e1e1  mov     edx, eax
0x18001e1e3  mov     rax, [rbx+70h]
0x18001e1e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1ec  mov     rax, [rsi]
0x18001e1ef  xor     edx, edx
0x18001e1f1  mov     rcx, rsi
0x18001e1f4  mov     rax, [rax+110h]
0x18001e1fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e200  mov     rax, [rsi]
0x18001e203  mov     rcx, rsi
0x18001e206  mov     rax, [rax+68h]
0x18001e20a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e20f  test    al, 20h
0x18001e211  jnz     loc_18001E3E4
0x18001e217  mov     rax, [rsi]
0x18001e21a  mov     rcx, rsi
0x18001e21d  mov     rax, [rax+68h]
0x18001e221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e226  test    dil, al
0x18001e229  jz      short loc_18001E230
0x18001e22b  mov     r15d, r13d
0x18001e22e  jmp     short loc_18001E261
0x18001e230  cmp     dword ptr cs:qword_180070F24, 7
0x18001e237  jnz     short loc_18001E241
0x18001e239  mov     r15d, 3
0x18001e23f  jmp     short loc_18001E261
0x18001e241  mov     rax, [rsi]
0x18001e244  mov     rcx, rsi
0x18001e247  mov     rax, [rax+68h]
0x18001e24b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e250  mov     r15d, 4
0x18001e256  test    r15b, al
0x18001e259  jnz     short loc_18001E266
0x18001e25b  mov     r15d, 2
0x18001e261  mov     r14b, r13b
0x18001e264  jmp     short loc_18001E282
0x18001e266  mov     rax, [rsi]
0x18001e269  mov     rcx, rsi
0x18001e26c  mov     rax, [rax+68h]
0x18001e270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e275  test    al, 40h
0x18001e277  jnz     short loc_18001E261
0x18001e279  mov     r14b, 1
0x18001e27c  mov     r15d, 5
0x18001e282  mov     rdi, [rsi+110h]
0x18001e289  mov     rbx, [rdi]
0x18001e28c  mov     rax, [rsi]
0x18001e28f  mov     rcx, rsi
0x18001e292  cmp     rbx, rdi
0x18001e295  jz      loc_18001E39C
0x18001e29b  mov     r13d, [rbx+18h]
0x18001e29f  xor     r8d, r8d
0x18001e2a2  mov     rax, [rax+1A0h]
0x18001e2a9  mov     edx, r13d
0x18001e2ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2b1  test    r14b, r14b
0x18001e2b4  jnz     loc_18001E35D
0x18001e2ba  mov     rax, [rsi]
0x18001e2bd  mov     edx, r13d
0x18001e2c0  mov     rcx, rsi
0x18001e2c3  mov     rax, [rax+180h]
0x18001e2ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2cf  test    al, al
0x18001e2d1  jz      loc_18001E35D
0x18001e2d7  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x18001e2de  jz      short loc_18001E34E
0x18001e2e0  xor     eax, eax
0x18001e2e2  lea     rdx, aInterfacedisco_0; "InterfaceDisconnected: Marking Interfac"...
0x18001e2e9  mov     r8d, r13d
0x18001e2ec  mov     word ptr [rsp+8B0h+var_840], ax
0x18001e2f1  lea     rcx, [rsp+8B0h+var_840]
0x18001e2f6  mov     word ptr [rsp+8B0h+var_868], ax
0x18001e2fb  call    FormatRRASErrorString
0x18001e300  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x18001e307  jz      short loc_18001E34E
0x18001e309  mov     rax, [rsi]
0x18001e30c  mov     rcx, rsi
0x18001e30f  mov     rax, [rax+118h]
0x18001e316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e31b  test    r12, r12
0x18001e31e  lea     rcx, [rsp+8B0h+var_868]
0x18001e323  mov     [rsp+8B0h+var_888], rcx
0x18001e328  lea     r9, [rsp+8B0h+var_878]
0x18001e32d  cmovnz  r9, r12
0x18001e331  mov     [rsp+8B0h+var_890], rax
0x18001e336  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001e33d  lea     r8, [rsp+8B0h+var_840]
0x18001e342  lea     rdx, RasDimParamTraceInfo
0x18001e349  call    McTemplateU0zjzz_EventWriteTransfer
0x18001e34e  mov     r8, [rbx+20h]
0x18001e352  mov     r9d, r15d
0x18001e355  mov     edx, r13d
0x18001e358  call    ?InterfaceNotReachable@CDimRouterManager@@QEAAKKPEAXW4_UNREACHABILITY_REASON@@@Z; CDimRouterManager::InterfaceNotReachable(ulong,void *,_UNREACHABILITY_REASON)
0x18001e35d  xor     r13d, r13d
0x18001e360  cmp     [rbx+31h], r13b
0x18001e364  jnz     loc_18001E28C
0x18001e36a  mov     rcx, [rbx+10h]
0x18001e36e  cmp     [rcx+31h], r13b
0x18001e372  jnz     short loc_18001E37B
0x18001e374  call    ?_Min@?$_Tree_val@V?$_Tmap_traits@PEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@U?$less@PEAX@3@V?$allocator@U?$pair@QEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@@std@@@3@$0A@@std@@@std@@SAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@PEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@U?$less@PEAX@3@V?$allocator@U?$pair@QEAXV?$shared_ptr@VCDimInterface@@@tr1@std@@@std@@@3@$0A@@std@@@2@PEAU342@@Z; std::_Tree_val<std::_Tmap_traits<void *,std::tr1::shared_ptr<CDimInterface>,std::less<void *>,std::allocator<std::pair<void * const,std::tr1::shared_ptr<CDimInterface>>>,0>>::_Min(std::_Tree_nod<std::_Tmap_traits<void *,std::tr1::shared_ptr<CDimInterface>,std::less<void *>,std::allocator<std::pair<void * const,std::tr1::shared_ptr<CDimInterface>>>,0>>::_Node *)
0x18001e379  jmp     short loc_18001E394
0x18001e37b  mov     rax, [rbx+8]
0x18001e37f  jmp     short loc_18001E38E
0x18001e381  cmp     rbx, [rax+10h]
0x18001e385  jnz     short loc_18001E394
0x18001e387  mov     rbx, rax
0x18001e38a  mov     rax, [rax+8]
0x18001e38e  cmp     [rax+31h], r13b
0x18001e392  jz      short loc_18001E381
0x18001e394  mov     rbx, rax
0x18001e397  jmp     loc_18001E28C
0x18001e39c  test    r14b, r14b
0x18001e39f  jnz     short loc_18001E3AC
0x18001e3a1  mov     rax, [rax+48h]
0x18001e3a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3aa  jmp     short loc_18001E3E4
0x18001e3ac  mov     rax, [rax+68h]
0x18001e3b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3b5  test    al, 2
0x18001e3b7  jz      short loc_18001E3E4
0x18001e3b9  cmp     [rsp+8B0h+var_880], r13b
0x18001e3be  jnz     short loc_18001E3E4
0x18001e3c0  mov     rax, [rsi]
0x18001e3c3  mov     rcx, rsi
  ... truncated ...
```
