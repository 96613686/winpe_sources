# CFGControl::~CFGControl(void)

- ea: `0x180003868`
- end: `0x180004050`
- name: `??1CFGControl@@AEAA@XZ`
- size: `2024`
- prototype: `void __fastcall(CFGControl *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180002710`

## callees

- `0x180003808`
- `0x180003868`
- `0x180004060`
- `0x180004454`
- `0x180004530`
- `0x180005358`
- `0x18000cb50`
- `0x1800274d0`
- `0x18002b7e0`
- `0x18002bd7c`
- `0x1800708c0`
- `0x180139f68`
- `0x18015e010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180003b2f`
- `KERNEL32!WaitForSingleObject` at `0x180003b2f`
- `KERNEL32!SetEvent` at `0x180003b1a`
- `KERNEL32!SetEvent` at `0x180003b1a`
- `KERNEL32!DeleteCriticalSection` at `0x180003e05`
- `KERNEL32!DeleteCriticalSection` at `0x180003e5e`
- `KERNEL32!DeleteCriticalSection` at `0x180003e71`
- `KERNEL32!DeleteCriticalSection` at `0x180003fe6`
- `KERNEL32!DeleteCriticalSection` at `0x180003ff6`
- `KERNEL32!DeleteCriticalSection` at `0x180003e05`
- `KERNEL32!DeleteCriticalSection` at `0x180003e5e`
- `KERNEL32!DeleteCriticalSection` at `0x180003e71`
- `KERNEL32!DeleteCriticalSection` at `0x180003fe6`
- `KERNEL32!DeleteCriticalSection` at `0x180003ff6`
- `KERNEL32!LeaveCriticalSection` at `0x180003a5f`
- `KERNEL32!LeaveCriticalSection` at `0x180003a5f`
- `KERNEL32!EnterCriticalSection` at `0x180003a49`
- `KERNEL32!EnterCriticalSection` at `0x180003a49`
- `KERNEL32!CloseHandle` at `0x180003b42`
- `KERNEL32!CloseHandle` at `0x180003df2`
- `KERNEL32!CloseHandle` at `0x180003b42`
- `KERNEL32!CloseHandle` at `0x180003df2`

## pseudocode

```c
void __fastcall CFGControl::~CFGControl(CFGControl *this)
{
  _QWORD *v2; // rcx
  __int64 v3; // rax
  _QWORD *v4; // rdx
  __int64 v5; // rax
  __int64 v6; // rbx
  _QWORD *v7; // rcx
  __int64 v8; // rax
  _QWORD *v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rbx
  _QWORD *v12; // rcx
  __int64 v13; // rax
  _QWORD *v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rbx
  __int64 v17; // rcx
  struct IUnknown *v18; // rdx
  __int64 v19; // rcx
  void *v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rsi
  int v28; // ebx
  __int64 v29; // rbx
  __int64 v30; // rcx
  int v31; // ebx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  _QWORD **v35; // rbx
  _QWORD *v36; // rcx
  _QWORD *v37; // rax
  _QWORD *v38; // rdx
  __int64 v39; // rax
  __int64 v40; // rsi
  __int64 v41; // rcx
  __int64 v42; // rcx
  _QWORD *v43; // rbx
  void *v44; // rcx
  _QWORD *v45; // rbx
  void *v46; // rcx
  _QWORD *v47; // rbx
  void *v48; // rcx
  _QWORD *v49; // rbx
  void *v50; // rcx
  _QWORD *v51; // rbx
  void *v52; // rcx
  _QWORD *v53; // rbx
  void *v54; // rcx
  _QWORD *v55; // rbx
  void *v56; // rcx
  _QWORD *v57; // rbx
  void *v58; // rcx
  _QWORD *v59; // rbx
  void *v60; // rcx
  _QWORD *v61; // rbx
  void *v62; // rcx
  CMsgMutex *v63; // [rsp+60h] [rbp+8h] BYREF

  *((_DWORD *)this + 6) = 0;
  while ( 1 )
  {
    v2 = (_QWORD *)*((_QWORD *)this + 36);
    if ( !v2 )
      break;
    v3 = v2[1];
    if ( *v2 )
      *(_QWORD *)(*v2 + 8LL) = v3;
    else
      *((_QWORD *)this + 36) = v3;
    v4 = (_QWORD *)v2[1];
    v5 = *v2;
    if ( v4 )
      *v4 = v5;
    else
      *((_QWORD *)this + 37) = v5;
    v6 = v2[2];
    if ( *((_DWORD *)this + 79) >= *((_DWORD *)this + 78) )
    {
      operator delete(v2);
    }
    else
    {
      v2[1] = *((_QWORD *)this + 40);
      ++*((_DWORD *)this + 79);
      *((_QWORD *)this + 40) = v2;
    }
    --*((_DWORD *)this + 76);
    if ( !v6 )
      break;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  while ( 1 )
  {
    v7 = (_QWORD *)*((_QWORD *)this + 41);
    if ( !v7 )
      break;
    v8 = v7[1];
    if ( *v7 )
      *(_QWORD *)(*v7 + 8LL) = v8;
    else
      *((_QWORD *)this + 41) = v8;
    v9 = (_QWORD *)v7[1];
    v10 = *v7;
    if ( v9 )
      *v9 = v10;
    else
      *((_QWORD *)this + 42) = v10;
    v11 = v7[2];
    if ( *((_DWORD *)this + 89) >= *((_DWORD *)this + 88) )
    {
      operator delete(v7);
    }
    else
    {
      v7[1] = *((_QWORD *)this + 45);
      ++*((_DWORD *)this + 89);
      *((_QWORD *)this + 45) = v7;
    }
    --*((_DWORD *)this + 86);
    if ( !v11 )
      break;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  while ( 1 )
  {
    v12 = (_QWORD *)*((_QWORD *)this + 46);
    if ( !v12 )
      break;
    v13 = v12[1];
    if ( *v12 )
      *(_QWORD *)(*v12 + 8LL) = v13;
    else
      *((_QWORD *)this + 46) = v13;
    v14 = (_QWORD *)v12[1];
    v15 = *v12;
    if ( v14 )
      *v14 = v15;
    else
      *((_QWORD *)this + 47) = v15;
    v16 = v12[2];
    if ( *((_DWORD *)this + 99) >= *((_DWORD *)this + 98) )
    {
      operator delete(v12);
    }
    else
    {
      v12[1] = *((_QWORD *)this + 50);
      ++*((_DWORD *)this + 99);
      *((_QWORD *)this + 50) = v12;
    }
    --*((_DWORD *)this + 96);
    if ( !v16 )
      break;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  *((_QWORD *)this + 34) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  v17 = *((_QWORD *)this + 35);
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    *((_QWORD *)this + 35) = 0;
  }
  v18 = (struct IUnknown *)*((_QWORD *)this + 28);
  if ( v18 )
    CFGControl::ReleaseFocus(this, v18);
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 61) + 8LL))((char *)this + 488);
  v19 = *((_QWORD *)this + 26);
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    *((_QWORD *)this + 26) = 0;
  }
  *((_QWORD *)this + 190) = &CFGControl::CImplQueueCommand::`vftable'{for `IQueueCommand'};
  *((_QWORD *)this + 191) = &CFGControl::CImplQueueCommand::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 194) = &CFGControl::CImplQueueCommand::`vftable'{for `CCmdQueue'};
  if ( *((_QWORD *)this + 218) )
  {
    v20 = (void *)*((_QWORD *)this + 210);
    *((_DWORD *)this + 438) = 1;
    SetEvent(v20);
    WaitForSingleObject(*((HANDLE *)this + 218), 0xFFFFFFFF);
    CloseHandle(*((HANDLE *)this + 218));
  }
  CCmdQueue::~CCmdQueue((CFGControl *)((char *)this + 1552));
  _InterlockedDecrement(&CBaseObject::m_cObjects);
  _InterlockedDecrement(&CBaseObject::m_cObjects);
  v21 = *((_QWORD *)this + 183);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  _InterlockedDecrement(&CBaseObject::m_cObjects);
  v22 = *((_QWORD *)this + 177);
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  _InterlockedDecrement(&CBaseObject::m_cObjects);
  v23 = *((_QWORD *)this + 155);
  *((_QWORD *)this + 144) = &CFGControl::CImplVideoWindow::`vftable'{for `IVideoWindow'};
  *((_QWORD *)this + 145) = &CFGControl::CImplVideoWindow::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 153) = 0;
  *((_QWORD *)this + 154) = 0;
  *((_DWORD *)this + 318) = 0;
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    *((_QWORD *)this + 155) = 0;
  }
  v24 = *((_QWORD *)this + 156);
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    *((_QWORD *)this + 156) = 0;
  }
  v25 = *((_QWORD *)this + 157);
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    *((_QWORD *)this + 157) = 0;
  }
  v26 = *((_QWORD *)this + 158);
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    *((_QWORD *)this + 158) = 0;
  }
  CAutoMsgMutex::CAutoMsgMutex(
    (CAutoMsgMutex *)&v63,
    *(struct CMsgMutex **)(*((_QWORD *)this + 149) + 16LL),
    0xFFFFFFFF);
  if ( *((_DWORD *)this + 304) == 1 )
  {
    v27 = 0;
    v28 = -2147220933;
  }
  else
  {
    v29 = *((_QWORD *)this + 149);
    CFGControl::UpdateLists((void **)v29);
    v27 = *(_QWORD *)(v29 + 272);
    if ( v27 )
    {
      v30 = *(_QWORD *)(v29 + 272);
      v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v30);
    }
    else
    {
      v28 = -2147467262;
    }
  }
  if ( v63 )
    CMsgMutex::Unlock(v63);
  if ( v28 >= 0 )
  {
    v31 =  IBasicVideo::`vcall'{248,{flat}}(v27, 0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    if ( v31 >= 0 )
      *((_QWORD *)this + 151) = 0;
  }
  v32 = *((_QWORD *)this + 148);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  _InterlockedDecrement(&CBaseObject::m_cObjects);
  v33 = *((_QWORD *)this + 142);
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  _InterlockedDecrement(&CBaseObject::m_cObjects);
  v34 = *((_QWORD *)this + 128);
  *((_QWORD *)this + 121) = &CFGControl::CImplMediaSeeking::`vftable'{for `IMediaSeeking'};
  *((_QWORD *)this + 122) = &CFGControl::CImplMediaSeeking::`vftable'{for `CUnknown'};
  if ( v34 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    *((_QWORD *)this + 128) = 0;
  }
  CFGControl::CImplMediaSeeking::ClearSegments((CFGControl *)((char *)this + 968));
  _InterlockedDecrement(&CBaseObject::m_cObjects);
  v35 = (_QWORD **)((char *)this + 848);
  while ( 1 )
  {
    v36 = *v35;
    if ( !*v35 )
      break;
    v37 = (_QWORD *)v36[1];
    if ( *v36 )
      *(_QWORD *)(*v36 + 8LL) = v37;
    else
      *v35 = v37;
    v38 = (_QWORD *)v36[1];
    v39 = *v36;
    if ( v38 )
      *v38 = v39;
    else
      *((_QWORD *)this + 107) = v39;
    v40 = v36[2];
    if ( *((_DWORD *)this + 219) >= *((_DWORD *)this + 218) )
    {
      operator delete(v36);
    }
    else
    {
      v36[1] = *((_QWORD *)this + 110);
      ++*((_DWORD *)this + 219);
      *((_QWORD *)this + 110) = v36;
    }
    --*((_DWORD *)this + 216);
    if ( !v40 )
      break;
    CImplMediaEvent::RealFreeEventParams(*(_DWORD *)v40, *(_QWORD *)(v40 + 8), *(_QWORD *)(v40 + 16));
    operator delete((void *)v40);
  }
  CloseHandle(*((HANDLE *)this + 104));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 888));
  CBaseList::~CBaseList((CFGControl *)((char *)this + 848));
  v41 = *((_QWORD *)this + 98);
  if ( v41 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  _InterlockedDecrement(&CBaseObject::m_cObjects);
  v42 = *((_QWORD *)this + 91);
  if ( v42 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  _InterlockedDecrement(&CBaseObject::m_cObjects);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 16);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 592));
  *((_QWORD *)this + 56) = &CResourceManager::`vftable'{for `IResourceManager'};
  *((_QWORD *)this + 57) = &CResourceManager::`vftable'{for `CUnknown'};
  CResourceManager::ProcessAttach(0);
  _InterlockedDecrement(&CBaseObject::m_cObjects);
  v43 = (_QWORD *)*((_QWORD *)this + 51);
  while ( v43 )
  {
    v44 = v43;
    v43 = (_QWORD *)v43[1];
    operator delete(v44);
  }
  v45 = (_QWORD *)*((_QWORD *)this + 55);
  *((_DWORD *)this + 106) = 0;
  *((_QWORD *)this + 52) = 0;
  *((_QWORD *)this + 51) = 0;
  while ( v45 )
  {
    v46 = v45;
    v45 = (_QWORD *)v45[1];
    operator delete(v46);
  }
  v47 = (_QWORD *)*((_QWORD *)this + 46);
  while ( v47 )
  {
    v48 = v47;
    v47 = (_QWORD *)v47[1];
    operator delete(v48);
  }
  v49 = (_QWORD *)*((_QWORD *)this + 50);
  *((_DWORD *)this + 96) = 0;
  *((_QWORD *)this + 47) = 0;
  *((_QWORD *)this + 46) = 0;
  while ( v49 )
  {
    v50 = v49;
    v49 = (_QWORD *)v49[1];
    operator delete(v50);
  }
  v51 = (_QWORD *)*((_QWORD *)this + 41);
  while ( v51 )
  {
    v52 = v51;
    v51 = (_QWORD *)v51[1];
    operator delete(v52);
  }
  v53 = (_QWORD *)*((_QWORD *)this + 45);
  *((_DWORD *)this + 86) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 41) = 0;
  while ( v53 )
  {
    v54 = v53;
    v53 = (_QWORD *)v53[1];
    operator delete(v54);
  }
  v55 = (_QWORD *)*((_QWORD *)this + 36);
  while ( v55 )
  {
    v56 = v55;
    v55 = (_QWORD *)v55[1];
    operator delete(v56);
  }
  v57 = (_QWORD *)*((_QWORD *)this + 40);
  *((_DWORD *)this + 76) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 36) = 0;
  while ( v57 )
  {
    v58 = v57;
    v57 = (_QWORD *)v57[1];
    operator delete(v58);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v59 = (_QWORD *)*((_QWORD *)this + 4);
  while ( v59 )
  {
    v60 = v59;
    v59 = (_QWORD *)v59[1];
    operator delete(v60);
  }
  v61 = (_QWORD *)*((_QWORD *)this + 8);
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 4) = 0;
  while ( v61 )
  {
    v62 = v61;
    v61 = (_QWORD *)v61[1];
    operator delete(v62);
  }
}

```

## disassembly

```asm
0x180003868  push    rbx
0x18000386a  push    rbp
0x18000386b  push    rsi
0x18000386c  push    rdi
0x18000386d  push    r14
0x18000386f  push    r15
0x180003871  sub     rsp, 28h
0x180003875  xor     r14d, r14d
0x180003878  mov     rdi, rcx
0x18000387b  mov     [rcx+18h], r14d
0x18000387f  lea     r15d, [r14+18h]
0x180003883  mov     rcx, [rdi+120h]; Block
0x18000388a  test    rcx, rcx
0x18000388d  jz      loc_180003917
0x180003893  mov     rdx, [rcx]
0x180003896  mov     rax, [rcx+8]
0x18000389a  test    rdx, rdx
0x18000389d  jnz     short loc_1800038A8
0x18000389f  mov     [rdi+120h], rax
0x1800038a6  jmp     short loc_1800038AC
0x1800038a8  mov     [rdx+8], rax
0x1800038ac  mov     rdx, [rcx+8]
0x1800038b0  mov     rax, [rcx]
0x1800038b3  test    rdx, rdx
0x1800038b6  jnz     short loc_1800038C1
0x1800038b8  mov     [rdi+128h], rax
0x1800038bf  jmp     short loc_1800038C4
0x1800038c1  mov     [rdx], rax
0x1800038c4  mov     eax, [rdi+138h]
0x1800038ca  mov     rbx, [rcx+10h]
0x1800038ce  cmp     [rdi+13Ch], eax
0x1800038d4  jge     short loc_1800038F0
0x1800038d6  mov     rax, [rdi+140h]
0x1800038dd  mov     [rcx+8], rax
0x1800038e1  inc     dword ptr [rdi+13Ch]
0x1800038e7  mov     [rdi+140h], rcx
0x1800038ee  jmp     short loc_1800038F8
0x1800038f0  mov     rdx, r15
0x1800038f3  call    ??3@YAXPEAXAEBUthrowing_tag@KsOpmLib@@@Z; operator delete(void *,KsOpmLib::throwing_tag const &)
0x1800038f8  dec     dword ptr [rdi+130h]
0x1800038fe  test    rbx, rbx
0x180003901  jz      short loc_180003917
0x180003903  mov     rax, [rbx]
0x180003906  mov     rcx, rbx
0x180003909  mov     rax, [rax+10h]
0x18000390d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003912  jmp     loc_180003883
0x180003917  mov     rcx, [rdi+148h]; Block
0x18000391e  test    rcx, rcx
0x180003921  jz      loc_1800039AB
0x180003927  mov     rdx, [rcx]
0x18000392a  mov     rax, [rcx+8]
0x18000392e  test    rdx, rdx
0x180003931  jnz     short loc_18000393C
0x180003933  mov     [rdi+148h], rax
0x18000393a  jmp     short loc_180003940
0x18000393c  mov     [rdx+8], rax
0x180003940  mov     rdx, [rcx+8]
0x180003944  mov     rax, [rcx]
0x180003947  test    rdx, rdx
0x18000394a  jnz     short loc_180003955
0x18000394c  mov     [rdi+150h], rax
0x180003953  jmp     short loc_180003958
0x180003955  mov     [rdx], rax
0x180003958  mov     eax, [rdi+160h]
0x18000395e  mov     rbx, [rcx+10h]
0x180003962  cmp     [rdi+164h], eax
0x180003968  jge     short loc_180003984
0x18000396a  mov     rax, [rdi+168h]
0x180003971  mov     [rcx+8], rax
0x180003975  inc     dword ptr [rdi+164h]
0x18000397b  mov     [rdi+168h], rcx
0x180003982  jmp     short loc_18000398C
0x180003984  mov     rdx, r15
0x180003987  call    ??3@YAXPEAXAEBUthrowing_tag@KsOpmLib@@@Z; operator delete(void *,KsOpmLib::throwing_tag const &)
0x18000398c  dec     dword ptr [rdi+158h]
0x180003992  test    rbx, rbx
0x180003995  jz      short loc_1800039AB
0x180003997  mov     rax, [rbx]
0x18000399a  mov     rcx, rbx
0x18000399d  mov     rax, [rax+10h]
0x1800039a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039a6  jmp     loc_180003917
0x1800039ab  mov     rcx, [rdi+170h]; Block
0x1800039b2  test    rcx, rcx
0x1800039b5  jz      loc_180003A3F
0x1800039bb  mov     rdx, [rcx]
0x1800039be  mov     rax, [rcx+8]
0x1800039c2  test    rdx, rdx
0x1800039c5  jnz     short loc_1800039D0
0x1800039c7  mov     [rdi+170h], rax
0x1800039ce  jmp     short loc_1800039D4
0x1800039d0  mov     [rdx+8], rax
0x1800039d4  mov     rdx, [rcx+8]
0x1800039d8  mov     rax, [rcx]
0x1800039db  test    rdx, rdx
0x1800039de  jnz     short loc_1800039E9
0x1800039e0  mov     [rdi+178h], rax
0x1800039e7  jmp     short loc_1800039EC
0x1800039e9  mov     [rdx], rax
0x1800039ec  mov     eax, [rdi+188h]
0x1800039f2  mov     rbx, [rcx+10h]
0x1800039f6  cmp     [rdi+18Ch], eax
0x1800039fc  jge     short loc_180003A18
0x1800039fe  mov     rax, [rdi+190h]
0x180003a05  mov     [rcx+8], rax
0x180003a09  inc     dword ptr [rdi+18Ch]
0x180003a0f  mov     [rdi+190h], rcx
0x180003a16  jmp     short loc_180003A20
0x180003a18  mov     rdx, r15
0x180003a1b  call    ??3@YAXPEAXAEBUthrowing_tag@KsOpmLib@@@Z; operator delete(void *,KsOpmLib::throwing_tag const &)
0x180003a20  dec     dword ptr [rdi+180h]
0x180003a26  test    rbx, rbx
0x180003a29  jz      short loc_180003A3F
0x180003a2b  mov     rax, [rbx]
0x180003a2e  mov     rcx, rbx
0x180003a31  mov     rax, [rax+10h]
0x180003a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a3a  jmp     loc_1800039AB
0x180003a3f  lea     rbp, [rdi+0E8h]
0x180003a46  mov     rcx, rbp; lpCriticalSection
0x180003a49  call    cs:__imp_EnterCriticalSection
0x180003a50  nop     dword ptr [rax+rax+00h]
0x180003a55  mov     rcx, rbp; lpCriticalSection
0x180003a58  mov     [rdi+110h], r14
0x180003a5f  call    cs:__imp_LeaveCriticalSection
0x180003a66  nop     dword ptr [rax+rax+00h]
0x180003a6b  mov     rcx, [rdi+118h]
0x180003a72  test    rcx, rcx
0x180003a75  jz      short loc_180003A8A
0x180003a77  mov     rax, [rcx]
0x180003a7a  mov     rax, [rax+10h]
0x180003a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a83  mov     [rdi+118h], r14
0x180003a8a  mov     rdx, [rdi+0E0h]; struct IUnknown *
0x180003a91  test    rdx, rdx
0x180003a94  jz      short loc_180003A9E
0x180003a96  mov     rcx, rdi; this
0x180003a99  call    ?ReleaseFocus@CFGControl@@QEAAJPEAUIUnknown@@@Z; CFGControl::ReleaseFocus(IUnknown *)
0x180003a9e  lea     rcx, [rdi+1E8h]
0x180003aa5  mov     rax, [rcx]
0x180003aa8  mov     rax, [rax+8]
0x180003aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ab1  mov     rcx, [rdi+0D0h]
0x180003ab8  test    rcx, rcx
0x180003abb  jz      short loc_180003AD0
0x180003abd  mov     rax, [rcx]
0x180003ac0  mov     rax, [rax+10h]
0x180003ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ac9  mov     [rdi+0D0h], r14
0x180003ad0  lea     rax, ??_7CImplQueueCommand@CFGControl@@6BIQueueCommand@@@; const CFGControl::CImplQueueCommand::`vftable'{for `IQueueCommand'}
0x180003ad7  or      esi, 0FFFFFFFFh
0x180003ada  lea     rbx, [rdi+610h]
0x180003ae1  mov     [rdi+5F0h], rax
0x180003ae8  lea     rax, ??_7CImplQueueCommand@CFGControl@@6BCUnknown@@@; const CFGControl::CImplQueueCommand::`vftable'{for `CUnknown'}
0x180003aef  mov     [rdi+5F8h], rax
0x180003af6  lea     rax, ??_7CImplQueueCommand@CFGControl@@6BCCmdQueue@@@; const CFGControl::CImplQueueCommand::`vftable'{for `CCmdQueue'}
0x180003afd  mov     [rbx], rax
0x180003b00  cmp     [rdi+6D0h], r14
0x180003b07  jz      short loc_180003B4E
0x180003b09  mov     rcx, [rdi+690h]; hEvent
0x180003b10  mov     dword ptr [rdi+6D8h], 1
0x180003b1a  call    cs:__imp_SetEvent
0x180003b21  nop     dword ptr [rax+rax+00h]
0x180003b26  mov     rcx, [rdi+6D0h]; hHandle
0x180003b2d  mov     edx, esi; dwMilliseconds
0x180003b2f  call    cs:__imp_WaitForSingleObject
0x180003b36  nop     dword ptr [rax+rax+00h]
0x180003b3b  mov     rcx, [rdi+6D0h]; hObject
0x180003b42  call    cs:__imp_CloseHandle
0x180003b49  nop     dword ptr [rax+rax+00h]
0x180003b4e  mov     rcx, rbx; this
0x180003b51  call    ??1CCmdQueue@@UEAA@XZ; CCmdQueue::~CCmdQueue(void)
0x180003b56  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180003b5d  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180003b64  mov     rcx, [rdi+5B8h]
0x180003b6b  test    rcx, rcx
0x180003b6e  jz      short loc_180003B7C
0x180003b70  mov     rax, [rcx]
0x180003b73  mov     rax, [rax+10h]
0x180003b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b7c  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180003b83  mov     rcx, [rdi+588h]
0x180003b8a  test    rcx, rcx
0x180003b8d  jz      short loc_180003B9B
0x180003b8f  mov     rax, [rcx]
0x180003b92  mov     rax, [rax+10h]
0x180003b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b9b  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180003ba2  lea     rax, ??_7CImplVideoWindow@CFGControl@@6BIVideoWindow@@@; const CFGControl::CImplVideoWindow::`vftable'{for `IVideoWindow'}
0x180003ba9  mov     rcx, [rdi+4D8h]
0x180003bb0  mov     [rdi+480h], rax
0x180003bb7  lea     rax, ??_7CImplVideoWindow@CFGControl@@6BCUnknown@@@; const CFGControl::CImplVideoWindow::`vftable'{for `CUnknown'}
0x180003bbe  mov     [rdi+488h], rax
0x180003bc5  mov     [rdi+4C8h], r14
0x180003bcc  mov     [rdi+4D0h], r14
0x180003bd3  mov     [rdi+4F8h], r14d
0x180003bda  test    rcx, rcx
0x180003bdd  jz      short loc_180003BF2
0x180003bdf  mov     rax, [rcx]
0x180003be2  mov     rax, [rax+10h]
0x180003be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003beb  mov     [rdi+4D8h], r14
0x180003bf2  mov     rcx, [rdi+4E0h]
0x180003bf9  test    rcx, rcx
0x180003bfc  jz      short loc_180003C11
0x180003bfe  mov     rax, [rcx]
0x180003c01  mov     rax, [rax+10h]
0x180003c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c0a  mov     [rdi+4E0h], r14
0x180003c11  mov     rcx, [rdi+4E8h]
0x180003c18  test    rcx, rcx
0x180003c1b  jz      short loc_180003C30
0x180003c1d  mov     rax, [rcx]
0x180003c20  mov     rax, [rax+10h]
0x180003c24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c29  mov     [rdi+4E8h], r14
0x180003c30  mov     rcx, [rdi+4F0h]
0x180003c37  test    rcx, rcx
0x180003c3a  jz      short loc_180003C4F
0x180003c3c  mov     rax, [rcx]
0x180003c3f  mov     rax, [rax+10h]
0x180003c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c48  mov     [rdi+4F0h], r14
0x180003c4f  mov     rdx, [rdi+4A8h]
0x180003c56  lea     rcx, [rsp+58h+arg_0]; this
0x180003c5b  mov     r8d, esi; unsigned int
0x180003c5e  mov     rdx, [rdx+10h]; struct CMsgMutex *
0x180003c62  call    ??0CAutoMsgMutex@@QEAA@PEAVCMsgMutex@@K@Z; CAutoMsgMutex::CAutoMsgMutex(CMsgMutex *,ulong)
0x180003c67  cmp     dword ptr [rdi+4C0h], 1
0x180003c6e  jnz     short loc_180003C7A
0x180003c70  mov     rsi, r14
0x180003c73  mov     ebx, 8004023Bh
0x180003c78  jmp     short loc_180003CAE
0x180003c7a  mov     rbx, [rdi+4A8h]
0x180003c81  mov     rcx, rbx; this
0x180003c84  call    ?UpdateLists@CFGControl@@QEAAJXZ; CFGControl::UpdateLists(void)
0x180003c89  mov     rsi, [rbx+110h]
0x180003c90  test    rsi, rsi
0x180003c93  jz      short loc_180003CA9
0x180003c95  mov     rax, [rsi]
0x180003c98  mov     rcx, rsi
0x180003c9b  mov     ebx, r14d
0x180003c9e  mov     rax, [rax+8]
0x180003ca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ca7  jmp     short loc_180003CAE
0x180003ca9  mov     ebx, 80004002h
0x180003cae  mov     rcx, [rsp+58h+arg_0]; this
0x180003cb3  test    rcx, rcx
0x180003cb6  jz      short loc_180003CBD
0x180003cb8  call    ?Unlock@CMsgMutex@@QEAAXXZ; CMsgMutex::Unlock(void)
0x180003cbd  test    ebx, ebx
0x180003cbf  js      short loc_180003CE7
0x180003cc1  xor     edx, edx
0x180003cc3  mov     rcx, rsi
0x180003cc6  call    ??_9IBasicVideo@@$BPI@AA; [thunk]: IBasicVideo::`vcall'{248,{flat}}
0x180003ccb  mov     rdx, [rsi]
0x180003cce  mov     ebx, eax
0x180003cd0  mov     rcx, rsi
0x180003cd3  mov     rax, [rdx+10h]
0x180003cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cdc  test    ebx, ebx
0x180003cde  js      short loc_180003CE7
0x180003ce0  mov     [rdi+4B8h], r14
0x180003ce7  mov     rcx, [rdi+4A0h]
0x180003cee  test    rcx, rcx
0x180003cf1  jz      short loc_180003CFF
0x180003cf3  mov     rax, [rcx]
0x180003cf6  mov     rax, [rax+10h]
0x180003cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cff  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180003d06  mov     rcx, [rdi+470h]
0x180003d0d  test    rcx, rcx
0x180003d10  jz      short loc_180003D1E
0x180003d12  mov     rax, [rcx]
0x180003d15  mov     rax, [rax+10h]
0x180003d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d1e  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180003d25  lea     rbx, [rdi+3C8h]
0x180003d2c  mov     rcx, [rbx+38h]
0x180003d30  lea     rax, ??_7CImplMediaSeeking@CFGControl@@6BIMediaSeeking@@@; const CFGControl::CImplMediaSeeking::`vftable'{for `IMediaSeeking'}
0x180003d37  mov     [rbx], rax
0x180003d3a  lea     rax, ??_7CImplMediaSeeking@CFGControl@@6BCUnknown@@@; const CFGControl::CImplMediaSeeking::`vftable'{for `CUnknown'}
0x180003d41  mov     [rbx+8], rax
0x180003d45  test    rcx, rcx
0x180003d48  jz      short loc_180003D5A
0x180003d4a  mov     rax, [rcx]
0x180003d4d  mov     rax, [rax+10h]
0x180003d51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d56  mov     [rbx+38h], r14
0x180003d5a  mov     rcx, rbx; this
0x180003d5d  call    ?ClearSegments@CImplMediaSeeking@CFGControl@@QEAAXXZ; CFGControl::CImplMediaSeeking::ClearSegments(void)
0x180003d62  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180003d69  lea     rbx, [rdi+350h]
0x180003d70  mov     rcx, [rbx]; Block
0x180003d73  test    rcx, rcx
0x180003d76  jz      short loc_180003DEB
0x180003d78  mov     rdx, [rcx]
0x180003d7b  mov     rax, [rcx+8]
0x180003d7f  test    rdx, rdx
  ... truncated ...
```
