# CImplMediaEvent::Notify(long,__int64,__int64)

- ea: `0x180013810`
- end: `0x180013e99`
- name: `?Notify@CImplMediaEvent@@UEAAJJ_J0@Z`
- size: `1673`
- prototype: `int(CImplMediaEvent *__hidden this, int, __int64, __int64)`
- caller_count: `10`
- callee_count: `14`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180005390`
- `0x1800229e8`
- `0x18002a428`
- `0x18006fb70`
- `0x18006fe6c`
- `0x18006ff74`
- `0x180070f78`
- `0x180071090`
- `0x180071554`
- `0x180076148`

## callees

- `0x180013810`
- `0x18001a050`
- `0x1800274d0`
- `0x180038458`
- `0x18005d5f8`
- `0x180064ae0`
- `0x1800706c8`
- `0x1800708c0`
- `0x180070eec`
- `0x180071d84`
- `0x1800777d8`
- `0x180077e10`
- `0x180139f68`
- `0x18015e010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180013bda`
- `KERNEL32!SetEvent` at `0x180013c4e`
- `KERNEL32!SetEvent` at `0x180013bda`
- `KERNEL32!SetEvent` at `0x180013c4e`
- `KERNEL32!LeaveCriticalSection` at `0x180013c2f`
- `KERNEL32!LeaveCriticalSection` at `0x180013d56`
- `KERNEL32!LeaveCriticalSection` at `0x180013c2f`
- `KERNEL32!LeaveCriticalSection` at `0x180013d56`
- `KERNEL32!EnterCriticalSection` at `0x180013b93`
- `KERNEL32!EnterCriticalSection` at `0x180013b93`
- `USER32!PostMessageW` at `0x180013aba`
- `USER32!PostMessageW` at `0x180013bfd`
- `USER32!PostMessageW` at `0x180013aba`
- `USER32!PostMessageW` at `0x180013bfd`
- `ole32!CoTaskMemFree` at `0x180013d37`
- `ole32!CoTaskMemFree` at `0x180013d46`
- `ole32!CoTaskMemFree` at `0x180013d37`
- `ole32!CoTaskMemFree` at `0x180013d46`

## pseudocode

```c
__int64 __fastcall CImplMediaEvent::Notify(CImplMediaEvent *this, int a2, __int64 a3, struct IUnknown *a4)
{
  struct IUnknown *v4; // r14
  char *v8; // r9
  int v10; // ebp
  void (__fastcall **v11)(__int64, GUID *, struct IUnknown **); // rax
  CFGControl *v12; // rcx
  unsigned int v13; // ebp
  __int64 *v14; // r13
  int i; // r12d
  __int64 v16; // rcx
  __int64 v17; // r10
  CFGControl::CImplMediaSeeking *v18; // rcx
  __int64 *v19; // rax
  __int64 v20; // r13
  LPARAM v21; // r9
  UINT v22; // edx
  WPARAM v23; // r8
  HWND v24; // rcx
  unsigned int v25; // edx
  int *v26; // rax
  int *v27; // r15
  HWND v28; // rcx
  _QWORD *v29; // rbx
  void *v30; // rcx
  __int64 v31; // rsi
  __int64 v32; // rsi
  __int64 v33; // rsi
  struct IUnknown *v34; // [rsp+30h] [rbp-38h] BYREF
  __int64 v35; // [rsp+38h] [rbp-30h] BYREF

  v4 = a4;
  if ( (Microsoft_Windows_DirectShow_CoreEnableBits & 0x10) != 0 )
    McTemplateU0pdpp_EventWriteTransfer((_DWORD)this, a2, **((_QWORD **)this + 1), a2, a3, (char)a4);
  if ( a2 == 3 || a2 == 6 )
  {
    if ( ((*((_QWORD *)this + 20) >> a2) & 1) != 0 )
      return 0;
LABEL_9:
    v8 = (char *)this - 40;
    *((_QWORD *)this + 20) |= 1LL << a2;
    if ( (((*((_QWORD *)v8 + 23) | *((_QWORD *)v8 + 24) & ~*((_QWORD *)v8 + 22)) >> a2) & 1) != 0 )
      goto LABEL_12;
    goto LABEL_10;
  }
  if ( (unsigned int)a2 <= 0x3F )
    goto LABEL_9;
  v8 = (char *)this - 40;
LABEL_10:
  if ( *((_DWORD *)v8 + 52) )
  {
    v10 = 0;
    goto LABEL_13;
  }
LABEL_12:
  v10 = 1;
LABEL_13:
  if ( a2 != 21 )
  {
    if ( a2 == 1 )
      return (unsigned int)CImplMediaEvent::ProcessEC_COMPLETE((CImplMediaEvent *)v8, a3, (__int64)v4);
    switch ( a2 )
    {
      case 5:
      case 21:
      case 26:
      case 27:
      case 31:
        goto LABEL_29;
      case 18:
      case 19:
      case 37:
        if ( v4 )
          ((void (__fastcall *)(struct IUnknown *))v4->lpVtbl->AddRef)(v4);
        break;
      case 22:
        if ( (__int64)v4 <= 0 )
        {
LABEL_29:
          if ( a3 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
        }
        else
        {
          v14 = (__int64 *)a3;
          for ( i = (int)v4; i; --i )
          {
            v16 = *v14++;
            if ( v16 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
          }
        }
        break;
      case 30:
        v18 = (CFGControl::CImplMediaSeeking *)(*((_QWORD *)this + 1) + 968LL);
        v35 = 0;
        CFGControl::CImplMediaSeeking::GetStopPosition(v18, &v35);
        break;
      case 81:
        v19 = (__int64 *)*((_QWORD *)this + 1);
        v20 = *v19;
        if ( !*(_DWORD *)(*v19 + 288) )
        {
          CFilterGraph::SetSyncSource((CFilterGraph *)(v20 + 152), 0);
          *(_DWORD *)(v20 + 288) = 0;
        }
        break;
      default:
        break;
    }
    v17 = *((_QWORD *)this + 1);
    if ( *(_DWORD *)(v17 + 216) )
    {
      if ( a2 != 28 )
        CImplMediaEvent::RealFreeEventParams(a2, a3, (__int64)v4);
      return 1;
    }
    if ( v10 )
    {
      v13 = 0;
      switch ( a2 )
      {
        case 5:
          v21 = a3;
          v22 = 1025;
          goto LABEL_39;
        case 12:
          CFGControl::Shutdown(*((CFGControl **)this + 1));
          return v13;
        case 19:
          v21 = (LPARAM)v4;
          v23 = a3;
          v22 = 1027;
          goto LABEL_40;
        case 20:
          *(_DWORD *)(v17 + 172) = 1;
          v21 = 0;
          v23 = a3;
          v22 = 1028;
          v24 = *(HWND *)(*((_QWORD *)this + 1) + 504LL);
          goto LABEL_41;
        case 22:
          v21 = (LPARAM)v4;
          v23 = a3;
          v22 = 1031;
          goto LABEL_40;
        case 23:
          v21 = 0;
          v22 = 1029;
LABEL_39:
          v23 = *(unsigned int *)(v17 + 164);
          goto LABEL_40;
        case 28:
          if ( (_DWORD)v4 == *(_DWORD *)(v17 + 1068) )
          {
            _InterlockedIncrement((volatile signed __int32 *)(v17 + 1080));
            CFGControl::CImplMediaSeeking::CheckEndOfSegment((CFGControl::CImplMediaSeeking *)(v17 + 968));
          }
          return v13;
        case 29:
          ++*(_DWORD *)(v17 + 1076);
          return v13;
        case 36:
          v23 = a3;
          v25 = *(_DWORD *)(v17 + 168) + 1;
          v21 = v25;
          *(_DWORD *)(*((_QWORD *)this + 1) + 168LL) = v25;
          v22 = 1037;
          goto LABEL_40;
        case 37:
          v21 = (LPARAM)v4;
          v23 = a3;
          v22 = 1038;
LABEL_40:
          v24 = *(HWND *)(v17 + 504);
LABEL_41:
          PostMessageW(v24, v22, v23, v21);
          break;
        default:
          CImplMediaEvent::RealFreeEventParams(a2, a3, (__int64)v4);
          break;
      }
      return v13;
    }
LABEL_53:
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    if ( (*((_BYTE *)this + 48) & 1) == 0 )
    {
      v26 = (int *)operator new(0x18u);
      v27 = v26;
      if ( v26 )
      {
        *v26 = a2;
        *((_QWORD *)v26 + 1) = a3;
        *((_QWORD *)v26 + 2) = v4;
        if ( CBaseList::AddTailI((CImplMediaEvent *)((char *)this + 56), v26) )
        {
          SetEvent(*((HANDLE *)this + 5));
          v28 = (HWND)*((_QWORD *)this + 2);
          if ( v28 )
            PostMessageW(v28, *((_DWORD *)this + 6), 0, *((_QWORD *)this + 4));
          goto LABEL_82;
        }
      }
      else
      {
        v27 = 0;
      }
      operator delete(v27);
      CImplMediaEvent::RealFreeEventParams(a2, a3, (__int64)v4);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
      return (unsigned int)-2147024882;
    }
    v34 = v4;
    v35 = a3;
    if ( a2 <= 594 )
    {
      if ( a2 != 594 )
      {
        switch ( a2 )
        {
          case 1:
          case 18:
          case 19:
          case 37:
            if ( v4 )
              ((void (__fastcall *)(struct IUnknown *))v4->lpVtbl->Release)(v4);
            goto LABEL_82;
          case 5:
          case 21:
          case 26:
          case 27:
          case 31:
            goto LABEL_67;
          case 22:
            if ( !(_DWORD)v4 )
            {
LABEL_67:
              if ( a3 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 16LL))(a3);
              goto LABEL_82;
            }
            v29 = (_QWORD *)a3;
            do
            {
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v29 + 16LL))(*v29);
              ++v29;
              LODWORD(v4) = (_DWORD)v4 - 1;
            }
            while ( (_DWORD)v4 );
LABEL_66:
            v30 = (void *)a3;
            break;
          case 24:
          case 65:
            FreeBSTR(&v35);
            goto LABEL_72;
          case 28:
            goto LABEL_66;
          case 69:
LABEL_72:
            FreeBSTR(&v34);
            goto LABEL_82;
          default:
            goto LABEL_82;
        }
LABEL_81:
        CoTaskMemFree(v30);
        goto LABEL_82;
      }
      if ( v4 )
      {
        v31 = a3 - 9;
        if ( v31 )
        {
          v32 = v31 - 14;
          if ( v32 )
          {
            v33 = v32 - 1;
            if ( v33 )
            {
              if ( v33 != 2 )
                goto LABEL_82;
            }
          }
        }
        else
        {
          CoTaskMemFree(v4[1].lpVtbl);
        }
        v30 = v4;
        goto LABEL_81;
      }
    }
LABEL_82:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    return 0;
  }
  v11 = *(void (__fastcall ***)(__int64, GUID *, struct IUnknown **))a3;
  v34 = 0;
  (*v11)(a3, &IID_IUnknown, &v34);
  v12 = (CFGControl *)*((_QWORD *)this + 1);
  if ( !*((_DWORD *)v12 + 54) && !v10 )
    goto LABEL_53;
  v13 = CFGControl::ReleaseFocus(v12, v34);
  ((void (__fastcall *)(struct IUnknown *))v34->lpVtbl->Release)(v34);
  return v13;
}

```

## disassembly

```asm
0x180013810  push    rbx
0x180013812  push    rsi
0x180013813  push    rdi
0x180013814  push    r14
0x180013816  sub     rsp, 48h
0x18001381a  test    cs:Microsoft_Windows_DirectShow_CoreEnableBits, 10h
0x180013821  mov     r14, r9
0x180013824  mov     rsi, r8
0x180013827  mov     ebx, edx
0x180013829  mov     rdi, rcx
0x18001382c  jz      short loc_180013847
0x18001382e  mov     r8, [rcx+8]
0x180013832  mov     [rsp+68h+var_40], r9
0x180013837  mov     r9d, edx
0x18001383a  mov     [rsp+68h+var_48], rsi
0x18001383f  mov     r8, [r8]
0x180013842  call    McTemplateU0pdpp_EventWriteTransfer
0x180013847  mov     [rsp+68h+arg_0], rbp
0x18001384c  cmp     ebx, 3
0x18001384f  jz      short loc_18001386A
0x180013851  cmp     ebx, 6
0x180013854  jz      short loc_18001386A
0x180013856  cmp     ebx, 3Fh ; '?'
0x180013859  jbe     short loc_180013881
0x18001385b  lea     r9, [rdi-28h]
0x18001385f  test    ebx, ebx
0x180013861  js      short loc_1800138B7
0x180013863  cmp     ebx, 3Fh ; '?'
0x180013866  jg      short loc_1800138B7
0x180013868  jmp     short loc_180013896
0x18001386a  mov     rax, [rdi+0A0h]
0x180013871  mov     ecx, ebx
0x180013873  shr     rax, cl
0x180013876  test    al, 1
0x180013878  jz      short loc_180013881
0x18001387a  xor     eax, eax
0x18001387c  jmp     loc_180013D70
0x180013881  mov     ecx, ebx
0x180013883  lea     r9, [rdi-28h]
0x180013887  mov     eax, 1
0x18001388c  shl     rax, cl
0x18001388f  or      [rdi+0A0h], rax
0x180013896  mov     rax, [r9+0B0h]
0x18001389d  mov     ecx, ebx
0x18001389f  not     rax
0x1800138a2  and     rax, [r9+0C0h]
0x1800138a9  or      rax, [r9+0B8h]
0x1800138b0  shr     rax, cl
0x1800138b3  test    al, 1
0x1800138b5  jnz     short loc_1800138C5
0x1800138b7  cmp     dword ptr [r9+0D0h], 0
0x1800138bf  jz      short loc_1800138C5
0x1800138c1  xor     ebp, ebp
0x1800138c3  jmp     short loc_1800138CA
0x1800138c5  mov     ebp, 1
0x1800138ca  mov     [rsp+68h+arg_8], r12
0x1800138cf  lea     r12, __ImageBase
0x1800138d6  mov     [rsp+68h+var_28], r15
0x1800138db  cmp     ebx, 15h
0x1800138de  jnz     short loc_18001393A
0x1800138e0  mov     rax, [rsi]
0x1800138e3  lea     r8, [rsp+68h+var_38]
0x1800138e8  lea     rdx, IID_IUnknown
0x1800138ef  mov     [rsp+68h+var_38], 0
0x1800138f8  mov     rcx, rsi
0x1800138fb  mov     rax, [rax]
0x1800138fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013903  mov     rcx, [rdi+8]; this
0x180013907  cmp     dword ptr [rcx+0D8h], 0
0x18001390e  jnz     short loc_180013918
0x180013910  test    ebp, ebp
0x180013912  jz      loc_180013B8F
0x180013918  mov     rdx, [rsp+68h+var_38]; struct IUnknown *
0x18001391d  call    ?ReleaseFocus@CFGControl@@QEAAJPEAUIUnknown@@@Z; CFGControl::ReleaseFocus(IUnknown *)
0x180013922  mov     rcx, [rsp+68h+var_38]
0x180013927  mov     ebp, eax
0x180013929  mov     rdx, [rcx]
0x18001392c  mov     rax, [rdx+10h]
0x180013930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013935  jmp     loc_180013D64
0x18001393a  cmp     ebx, 1
0x18001393d  jnz     short loc_180013954
0x18001393f  mov     r8, r14; __int64
0x180013942  mov     rdx, rsi; __int64
0x180013945  mov     rcx, r9; this
0x180013948  call    ?ProcessEC_COMPLETE@CImplMediaEvent@@QEAAJ_J0@Z; CImplMediaEvent::ProcessEC_COMPLETE(__int64,__int64)
0x18001394d  mov     ebp, eax
0x18001394f  jmp     loc_180013D64
0x180013954  lea     r15d, [rbx-5]; switch 77 cases
0x180013958  cmp     r15d, 4Ch
0x18001395c  ja      short def_18001397D; jumptable 000000018001397D default case
0x18001395e  mov     [rsp+68h+arg_10], r13
0x180013966  movsxd  rax, r15d
0x180013969  movzx   eax, ds:(byte_180013D98 - 180000000h)[r12+rax]
0x180013972  mov     ecx, ds:(jpt_18001397D - 180000000h)[r12+rax*4]
0x18001397a  add     rcx, r12
0x18001397d  jmp     rcx; switch jump
0x180013983  test    r14, r14; jumptable 000000018001397D case 22
0x180013986  jle     short loc_1800139F1; jumptable 000000018001397D cases 5,21,26,27,31
0x180013988  mov     r13, rsi
0x18001398b  mov     r12d, r14d
0x18001398e  test    r14d, r14d
0x180013991  jz      short loc_1800139B4
0x180013993  mov     rcx, [r13+0]
0x180013997  lea     r13, [r13+8]
0x18001399b  dec     r12d
0x18001399e  test    rcx, rcx
0x1800139a1  jz      short loc_1800139AF
0x1800139a3  mov     rax, [rcx]
0x1800139a6  mov     rax, [rax+8]
0x1800139aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139af  test    r12d, r12d
0x1800139b2  jnz     short loc_180013993
0x1800139b4  lea     r12, __ImageBase
0x1800139bb  mov     r13, [rsp+68h+arg_10]; jumptable 000000018001397D cases 6-17,20,23-25,28,29,32-36,38-80
0x1800139c3  mov     r10, [rdi+8]; jumptable 000000018001397D default case
0x1800139c7  cmp     dword ptr [r10+0D8h], 0
0x1800139cf  jz      loc_180013A73
0x1800139d5  cmp     ebx, 1Ch
0x1800139d8  jz      short loc_1800139E7
0x1800139da  mov     r8, r14; __int64
0x1800139dd  mov     rdx, rsi; __int64
0x1800139e0  mov     ecx, ebx; int
0x1800139e2  call    ?RealFreeEventParams@CImplMediaEvent@@SAJJ_J0@Z; CImplMediaEvent::RealFreeEventParams(long,__int64,__int64)
0x1800139e7  mov     ebp, 1
0x1800139ec  jmp     loc_180013D64
0x1800139f1  test    rsi, rsi; jumptable 000000018001397D cases 5,21,26,27,31
0x1800139f4  jz      short loc_1800139BB; jumptable 000000018001397D cases 6-17,20,23-25,28,29,32-36,38-80
0x1800139f6  mov     rax, [rsi]
0x1800139f9  mov     rcx, rsi
0x1800139fc  mov     rax, [rax+8]
0x180013a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a05  jmp     short loc_1800139BB; jumptable 000000018001397D cases 6-17,20,23-25,28,29,32-36,38-80
0x180013a07  test    r14, r14; jumptable 000000018001397D cases 18,19,37
0x180013a0a  jz      short loc_1800139BB; jumptable 000000018001397D cases 6-17,20,23-25,28,29,32-36,38-80
0x180013a0c  mov     rax, [r14]
0x180013a0f  mov     rcx, r14
0x180013a12  mov     rax, [rax+8]
0x180013a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a1b  jmp     short loc_1800139BB; jumptable 000000018001397D cases 6-17,20,23-25,28,29,32-36,38-80
0x180013a1d  mov     rcx, [rdi+8]; jumptable 000000018001397D case 30
0x180013a21  lea     rdx, [rsp+68h+var_30]; __int64 *
0x180013a26  add     rcx, 3C8h; this
0x180013a2d  mov     [rsp+68h+var_30], 0
0x180013a36  call    ?GetStopPosition@CImplMediaSeeking@CFGControl@@UEAAJPEA_J@Z; CFGControl::CImplMediaSeeking::GetStopPosition(__int64 *)
0x180013a3b  jmp     loc_1800139BB; jumptable 000000018001397D cases 6-17,20,23-25,28,29,32-36,38-80
0x180013a40  mov     rax, [rdi+8]; jumptable 000000018001397D case 81
0x180013a44  mov     r13, [rax]
0x180013a47  cmp     dword ptr [r13+120h], 0
0x180013a4f  jnz     loc_1800139BB; jumptable 000000018001397D cases 6-17,20,23-25,28,29,32-36,38-80
0x180013a55  lea     rcx, [r13+98h]; this
0x180013a5c  xor     edx, edx; struct IReferenceClock *
0x180013a5e  call    ?SetSyncSource@CFilterGraph@@UEAAJPEAUIReferenceClock@@@Z; CFilterGraph::SetSyncSource(IReferenceClock *)
0x180013a63  mov     dword ptr [r13+120h], 0
0x180013a6e  jmp     loc_1800139BB; jumptable 000000018001397D cases 6-17,20,23-25,28,29,32-36,38-80
0x180013a73  test    ebp, ebp
0x180013a75  jz      loc_180013B8F
0x180013a7b  xor     ebp, ebp
0x180013a7d  cmp     r15d, 20h; switch 33 cases
0x180013a81  ja      def_180013A9E; jumptable 0000000180013A9E default case, cases 1-6,8-13,16,19-22,25-30
0x180013a87  movsxd  rax, r15d
0x180013a8a  movzx   eax, ds:(byte_180013E14 - 180000000h)[r12+rax]
0x180013a93  mov     ecx, ds:(jpt_180013A9E - 180000000h)[r12+rax*4]
0x180013a9b  add     rcx, r12
0x180013a9e  jmp     rcx; switch jump
0x180013aa4  xor     r9d, r9d; jumptable 0000000180013A9E case 18
0x180013aa7  mov     edx, 405h; Msg
0x180013aac  mov     r8d, [r10+0A4h]; wParam
0x180013ab3  mov     rcx, [r10+1F8h]; hWnd
0x180013aba  call    cs:__imp_PostMessageW
0x180013ac1  nop     dword ptr [rax+rax+00h]
0x180013ac6  jmp     loc_180013D64
0x180013acb  mov     r9, r14; jumptable 0000000180013A9E case 14
0x180013ace  mov     r8, rsi
0x180013ad1  mov     edx, 403h
0x180013ad6  jmp     short loc_180013AB3
0x180013ad8  mov     r9, r14; jumptable 0000000180013A9E case 17
0x180013adb  mov     r8, rsi
0x180013ade  mov     edx, 407h
0x180013ae3  jmp     short loc_180013AB3
0x180013ae5  mov     rcx, r10; jumptable 0000000180013A9E case 7
0x180013ae8  call    ?Shutdown@CFGControl@@QEAAJXZ; CFGControl::Shutdown(void)
0x180013aed  jmp     loc_180013D64
0x180013af2  mov     r9, rsi; jumptable 0000000180013A9E case 0
0x180013af5  mov     edx, 401h
0x180013afa  jmp     short loc_180013AAC
0x180013afc  mov     dword ptr [r10+0ACh], 1; jumptable 0000000180013A9E case 15
0x180013b07  xor     r9d, r9d
0x180013b0a  mov     rcx, [rdi+8]
0x180013b0e  mov     r8, rsi
0x180013b11  mov     edx, 404h
0x180013b16  mov     rcx, [rcx+1F8h]
0x180013b1d  jmp     short loc_180013ABA
0x180013b1f  inc     dword ptr [r10+434h]; jumptable 0000000180013A9E case 24
0x180013b26  jmp     loc_180013D64
0x180013b2b  lea     rcx, [r10+3C8h]; jumptable 0000000180013A9E case 23
0x180013b32  cmp     r14d, [rcx+64h]
0x180013b36  jnz     loc_180013D64
0x180013b3c  lock inc dword ptr [rcx+70h]
0x180013b40  call    ?CheckEndOfSegment@CImplMediaSeeking@CFGControl@@QEAAXXZ; CFGControl::CImplMediaSeeking::CheckEndOfSegment(void)
0x180013b45  jmp     loc_180013D64
0x180013b4a  mov     edx, [r10+0A8h]; jumptable 0000000180013A9E case 31
0x180013b51  mov     r8, rsi
0x180013b54  mov     rax, [rdi+8]
0x180013b58  inc     edx
0x180013b5a  mov     r9d, edx
0x180013b5d  mov     [rax+0A8h], edx
0x180013b63  mov     edx, 40Dh
0x180013b68  jmp     loc_180013AB3
0x180013b6d  mov     r9, r14; jumptable 0000000180013A9E case 32
0x180013b70  mov     r8, rsi
0x180013b73  mov     edx, 40Eh
0x180013b78  jmp     loc_180013AB3
0x180013b7d  mov     r8, r14; jumptable 0000000180013A9E default case, cases 1-6,8-13,16,19-22,25-30
0x180013b80  mov     rdx, rsi; __int64
0x180013b83  mov     ecx, ebx; int
0x180013b85  call    ?RealFreeEventParams@CImplMediaEvent@@SAJJ_J0@Z; CImplMediaEvent::RealFreeEventParams(long,__int64,__int64)
0x180013b8a  jmp     loc_180013D64
0x180013b8f  lea     rcx, [rdi+60h]; lpCriticalSection
0x180013b93  call    cs:__imp_EnterCriticalSection
0x180013b9a  nop     dword ptr [rax+rax+00h]
0x180013b9f  test    byte ptr [rdi+30h], 1
0x180013ba3  jnz     loc_180013C45
0x180013ba9  mov     ecx, 18h; Size
0x180013bae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013bb3  mov     r15, rax
0x180013bb6  test    rax, rax
0x180013bb9  jz      short loc_180013C0E
0x180013bbb  mov     rdx, rax; void *
0x180013bbe  mov     [rax], ebx
0x180013bc0  lea     rcx, [rdi+38h]; this
0x180013bc4  mov     [rax+8], rsi
0x180013bc8  mov     [rax+10h], r14
0x180013bcc  call    ?AddTailI@CBaseList@@IEAAPEAU__POSITION@@PEAX@Z; CBaseList::AddTailI(void *)
0x180013bd1  test    rax, rax
0x180013bd4  jz      short loc_180013C11
0x180013bd6  mov     rcx, [rdi+28h]; hEvent
0x180013bda  call    cs:__imp_SetEvent
0x180013be1  nop     dword ptr [rax+rax+00h]
0x180013be6  mov     rcx, [rdi+10h]; hWnd
0x180013bea  test    rcx, rcx
0x180013bed  jz      def_180013CA6; jumptable 0000000180013CA6 default case, cases 2-4,6-17,20,23,25,29,30,32-36,38-64,66-68
0x180013bf3  mov     r9, [rdi+20h]; lParam
0x180013bf7  xor     r8d, r8d; wParam
0x180013bfa  mov     edx, [rdi+18h]; Msg
0x180013bfd  call    cs:__imp_PostMessageW
0x180013c04  nop     dword ptr [rax+rax+00h]
0x180013c09  jmp     def_180013CA6; jumptable 0000000180013CA6 default case, cases 2-4,6-17,20,23,25,29,30,32-36,38-64,66-68
0x180013c0e  xor     r15d, r15d
0x180013c11  mov     edx, 18h
0x180013c16  mov     rcx, r15; Block
0x180013c19  call    ??3@YAXPEAXAEBUthrowing_tag@KsOpmLib@@@Z; operator delete(void *,KsOpmLib::throwing_tag const &)
0x180013c1e  mov     r8, r14; __int64
0x180013c21  mov     rdx, rsi; __int64
0x180013c24  mov     ecx, ebx; int
0x180013c26  call    ?RealFreeEventParams@CImplMediaEvent@@SAJJ_J0@Z; CImplMediaEvent::RealFreeEventParams(long,__int64,__int64)
0x180013c2b  lea     rcx, [rdi+60h]; lpCriticalSection
0x180013c2f  call    cs:__imp_LeaveCriticalSection
0x180013c36  nop     dword ptr [rax+rax+00h]
0x180013c3b  mov     ebp, 8007000Eh
0x180013c40  jmp     loc_180013D64
0x180013c45  cmp     ebx, 1
0x180013c48  jnz     short loc_180013C68
0x180013c4a  mov     rcx, [rdi+28h]; hEvent
0x180013c4e  call    cs:__imp_SetEvent
0x180013c55  nop     dword ptr [rax+rax+00h]
0x180013c5a  dec     ebx
0x180013c5c  mov     [rsp+68h+var_38], r14
0x180013c61  mov     [rsp+68h+var_30], rsi
0x180013c66  jmp     short loc_180013C8F
0x180013c68  mov     [rsp+68h+var_38], r14
0x180013c6d  mov     [rsp+68h+var_30], rsi
0x180013c72  cmp     ebx, 252h
0x180013c78  jg      def_180013CA6; jumptable 0000000180013CA6 default case, cases 2-4,6-17,20,23,25,29,30,32-36,38-64,66-68
0x180013c7e  jz      loc_180013D14
0x180013c84  dec     ebx; switch 69 cases
0x180013c86  cmp     ebx, 44h
0x180013c89  ja      def_180013CA6; jumptable 0000000180013CA6 default case, cases 2-4,6-17,20,23,25,29,30,32-36,38-64,66-68
0x180013c8f  movsxd  rax, ebx
0x180013c92  movzx   eax, ds:(byte_180013E54 - 180000000h)[r12+rax]
0x180013c9b  mov     ecx, ds:(jpt_180013CA6 - 180000000h)[r12+rax*4]
0x180013ca3  add     rcx, r12
0x180013ca6  jmp     rcx; switch jump
0x180013cac  test    r14d, r14d; jumptable 0000000180013CA6 case 22
0x180013caf  jz      short loc_180013CD2; jumptable 0000000180013CA6 cases 5,21,26,27,31
0x180013cb1  mov     rbx, rsi
0x180013cb4  mov     rcx, [rbx]
0x180013cb7  mov     rax, [rcx]
0x180013cba  mov     rax, [rax+10h]
0x180013cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cc3  lea     rbx, [rbx+8]
0x180013cc7  add     r14d, 0FFFFFFFFh
0x180013ccb  jnz     short loc_180013CB4
0x180013ccd  mov     rcx, rsi; jumptable 0000000180013CA6 case 28
0x180013cd0  jmp     short loc_180013D46
0x180013cd2  test    rsi, rsi; jumptable 0000000180013CA6 cases 5,21,26,27,31
0x180013cd5  jz      short def_180013CA6; jumptable 0000000180013CA6 default case, cases 2-4,6-17,20,23,25,29,30,32-36,38-64,66-68
0x180013cd7  mov     rax, [rsi]
0x180013cda  mov     rcx, rsi
0x180013cdd  mov     rax, [rax+10h]
  ... truncated ...
```
