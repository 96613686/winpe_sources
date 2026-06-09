# WindowFromAccessibleObject

- ea: `0x180015360`
- end: `0x180015723`
- name: `WindowFromAccessibleObject`
- size: `963`
- prototype: `HRESULT __stdcall(IAccessible *, HWND *phwnd)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014e00`
- `0x180015320`

## callees

- `0x180015360`
- `0x180049010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800156c0`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800156c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800156fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800156fb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800156d6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800156d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800156e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800156e2`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18001567f`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterThreadInterfaceInStream` at `0x18001567f`

## pseudocode

```c
HRESULT __stdcall WindowFromAccessibleObject(IAccessible *a1, HWND *phwnd)
{
  struct IAccessibleVtbl *lpVtbl; // rax
  struct IAccessibleVtbl *v5; // rax
  HRESULT v6; // ebx
  IUnknown *v7; // rdi
  struct IUnknownVtbl *v8; // rax
  int v9; // ebx
  IUnknown *v10; // rsi
  struct IUnknownVtbl *v11; // rax
  int v13; // ebx
  HWND v14; // rax
  void *v15; // rax
  void *v16; // rdi
  signed int LastError; // eax
  __int64 v18; // [rsp+30h] [rbp-39h] BYREF
  __int64 v19; // [rsp+38h] [rbp-31h] BYREF
  LPUNKNOWN pUnk; // [rsp+40h] [rbp-29h] BYREF
  LPSTREAM ppStm; // [rsp+48h] [rbp-21h] BYREF
  __int128 v22; // [rsp+50h] [rbp-19h] BYREF
  __int64 v23; // [rsp+60h] [rbp-9h]
  __int128 v24; // [rsp+70h] [rbp+7h] BYREF
  __int64 v25; // [rsp+80h] [rbp+17h]
  HWND v26; // [rsp+D8h] [rbp+6Fh] BYREF
  IAccessible *v27; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v28; // [rsp+E8h] [rbp+7Fh] BYREF

  v28 = 0;
  if ( phwnd && a1 )
  {
    *phwnd = 0;
    lpVtbl = a1->lpVtbl;
    v27 = a1;
    v18 = 0;
    if ( ((__int64 (__fastcall *)(IAccessible *, GUID *, __int64 *))lpVtbl->QueryInterface)(a1, &IID_IOleWindow, &v18) >= 0 )
    {
      v26 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64, HWND *))(*(_QWORD *)v18 + 24LL))(v18, &v26);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      if ( v13 >= 0 )
      {
        v14 = v26;
        if ( v26 )
          goto LABEL_30;
      }
    }
    v24 = 0;
    DWORD2(v24) = 0;
    LOWORD(v24) = 3;
    v25 = 0;
    v23 = 0;
    v5 = a1->lpVtbl;
    v22 = 0;
    if ( !((unsigned int (__fastcall *)(IAccessible *, __int64, __int128 *, __int128 *))v5->accNavigate)(
            a1,
            10,
            &v24,
            &v22)
      && (_WORD)v22 == 3 )
    {
      v14 = (HWND)SDWORD2(v22);
      if ( DWORD2(v22) )
      {
LABEL_30:
        *phwnd = v14;
        return 0;
      }
    }
    v6 = 0;
LABEL_6:
    v7 = (IUnknown *)v27;
    while ( 1 )
    {
      if ( !v7 || v6 < 0 )
        return v6;
      v8 = v7->lpVtbl;
      v19 = 0;
      if ( ((unsigned __int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))v8->QueryInterface)(
             v7,
             &IID_IServiceProvider,
             &v19)
        || !v19 )
      {
        break;
      }
      pUnk = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, GUID *, GUID *, LPUNKNOWN *))(*(_QWORD *)v19 + 24LL))(
             v19,
             &IIS_AccWrapBase_GetIUnknown,
             &IID_IAccessible,
             &pUnk);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      v10 = pUnk;
      if ( !v9 )
        goto LABEL_12;
      if ( !pUnk )
        break;
LABEL_13:
      v11 = v10->lpVtbl;
      v26 = 0;
      v6 = ((__int64 (__fastcall *)(IUnknown *, GUID *, HWND *))v11->QueryInterface)(v10, &IID_IOleWindow, &v26);
      if ( v6 >= 0 )
      {
        if ( !v26
          || (v6 = (*(__int64 (__fastcall **)(HWND, HWND *))(*(_QWORD *)v26 + 24LL))(v26, phwnd),
              (*(void (__fastcall **)(HWND))(*(_QWORD *)v26 + 16LL))(v26),
              v6 >= 0) )
        {
          ((void (__fastcall *)(IUnknown *))v10->lpVtbl->Release)(v10);
LABEL_24:
          if ( v27 != a1 )
            ((void (__fastcall *)(IAccessible *))v27->lpVtbl->Release)(v27);
          return v6;
        }
      }
      if ( v6 == -2147417843 )
      {
        ppStm = 0;
        v6 = CoMarshalInterThreadInterfaceInStream(&IID_IAccessible, v10, &ppStm);
        if ( !v6 )
        {
          *(_QWORD *)&v24 = ppStm;
          v25 = 0;
          *((_QWORD *)&v24 + 1) = phwnd;
          LODWORD(v26) = 0;
          v15 = (void *)_o__beginthreadex(0, 0, STA_Thread, &v24, 0, &v26);
          v16 = v15;
          if ( v15 )
          {
            WaitForSingleObject(v15, 0xFFFFFFFF);
            v6 = v25;
            CloseHandle(v16);
          }
          else
          {
            LastError = GetLastError();
            v6 = LastError;
            if ( LastError > 0 )
              v6 = (unsigned __int16)LastError | 0x80070000;
          }
        }
      }
      ((void (__fastcall *)(IUnknown *))v10->lpVtbl->Release)(v10);
      if ( v6 >= 0 )
        goto LABEL_24;
LABEL_16:
      v28 = 0;
      v6 = ((__int64 (__fastcall *)(IAccessible *, __int64 *))v27->lpVtbl->get_accParent)(v27, &v28);
      if ( v27 != a1 )
        ((void (__fastcall *)(IAccessible *))v27->lpVtbl->Release)(v27);
      v27 = 0;
      v7 = 0;
      if ( v6 >= 0 && v28 )
      {
        v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, IAccessible **))v28)(v28, &IID_IAccessible, &v27);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        goto LABEL_6;
      }
    }
    v10 = v7;
    ((void (__fastcall *)(IUnknown *))v7->lpVtbl->AddRef)(v7);
LABEL_12:
    if ( !v10 )
      goto LABEL_16;
    goto LABEL_13;
  }
  return -2147024809;
}

```

## disassembly

```asm
0x180015360  push    rbp
0x180015362  push    r12
0x180015364  push    r14
0x180015366  push    r15
0x180015368  lea     rbp, [rsp-3Fh]
0x18001536d  sub     rsp, 0A8h
0x180015374  xor     r12d, r12d
0x180015377  mov     r15, rdx
0x18001537a  mov     [rbp+57h+arg_18], r12
0x18001537e  mov     r14, rcx
0x180015381  test    rdx, rdx
0x180015384  jz      loc_180015719
0x18001538a  test    rcx, rcx
0x18001538d  jz      loc_180015719
0x180015393  mov     [rdx], r12
0x180015396  lea     r8, [rbp+57h+var_90]
0x18001539a  mov     rax, [rcx]
0x18001539d  lea     rdx, IID_IOleWindow
0x1800153a4  mov     [rsp+0C0h+var_20], rbx
0x1800153ac  mov     [rbp+57h+arg_10], rcx
0x1800153b0  mov     [rbp+57h+var_90], r12
0x1800153b4  mov     rax, [rax]
0x1800153b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153bc  test    eax, eax
0x1800153be  jns     loc_18001560E
0x1800153c4  xorps   xmm0, xmm0
0x1800153c7  lea     r9, [rbp+57h+var_70]
0x1800153cb  movups  [rbp+57h+var_50], xmm0
0x1800153cf  mov     dword ptr [rbp+57h+var_50+8], r12d
0x1800153d3  lea     r8, [rbp+57h+var_50]
0x1800153d7  xor     ecx, ecx
0x1800153d9  mov     eax, 3
0x1800153de  mov     word ptr [rbp+57h+var_50], ax
0x1800153e2  mov     edx, 0Ah
0x1800153e7  xor     eax, eax
0x1800153e9  mov     [rbp+57h+var_40], rcx
0x1800153ed  mov     [rbp+57h+var_60], rax
0x1800153f1  mov     rcx, r14
0x1800153f4  mov     rax, [r14]
0x1800153f7  movups  [rbp+57h+var_70], xmm0
0x1800153fb  movups  xmm0, [rbp+57h+var_50]
0x1800153ff  mov     rax, [rax+0B8h]
0x180015406  movaps  [rbp+57h+var_50], xmm0
0x18001540a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001540f  test    eax, eax
0x180015411  jz      loc_180015654
0x180015417  mov     [rsp+0C0h+var_30], rdi
0x18001541f  mov     ebx, r12d
0x180015422  mov     [rsp+0C0h+var_28], rsi
0x18001542a  mov     rdi, [rbp+57h+arg_10]
0x18001542e  test    rdi, rdi
0x180015431  jz      loc_1800155CE
0x180015437  test    ebx, ebx
0x180015439  js      loc_1800155CE
0x18001543f  mov     rax, [rdi]
0x180015442  lea     r8, [rbp+57h+var_88]
0x180015446  lea     rdx, IID_IServiceProvider
0x18001544d  mov     [rbp+57h+var_88], r12
0x180015451  mov     rcx, rdi
0x180015454  mov     rax, [rax]
0x180015457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001545c  test    eax, eax
0x18001545e  jnz     loc_1800155F7
0x180015464  mov     rcx, [rbp+57h+var_88]
0x180015468  test    rcx, rcx
0x18001546b  jz      loc_1800155F7
0x180015471  mov     [rbp+57h+pUnk], r12
0x180015475  lea     r9, [rbp+57h+pUnk]
0x180015479  mov     rax, [rcx]
0x18001547c  lea     r8, IID_IAccessible
0x180015483  lea     rdx, ?IIS_AccWrapBase_GetIUnknown@@3U_GUID@@A; _GUID IIS_AccWrapBase_GetIUnknown
0x18001548a  mov     rax, [rax+18h]
0x18001548e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015493  mov     rcx, [rbp+57h+var_88]
0x180015497  mov     ebx, eax
0x180015499  mov     rdx, [rcx]
0x18001549c  mov     rax, [rdx+10h]
0x1800154a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154a5  mov     rsi, [rbp+57h+pUnk]
0x1800154a9  test    ebx, ebx
0x1800154ab  jnz     loc_1800156ED
0x1800154b1  test    rsi, rsi
0x1800154b4  jz      short loc_180015500
0x1800154b6  mov     rax, [rsi]
0x1800154b9  lea     r8, [rbp+57h+arg_8]
0x1800154bd  lea     rdx, IID_IOleWindow
0x1800154c4  mov     [rbp+57h+arg_8], r12
0x1800154c8  mov     rcx, rsi
0x1800154cb  mov     rax, [rax]
0x1800154ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154d3  mov     ebx, eax
0x1800154d5  test    eax, eax
0x1800154d7  jns     loc_180015578
0x1800154dd  cmp     ebx, 8001010Dh
0x1800154e3  jz      loc_18001566D
0x1800154e9  mov     rax, [rsi]
0x1800154ec  mov     rcx, rsi
0x1800154ef  mov     rax, [rax+10h]
0x1800154f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154f8  test    ebx, ebx
0x1800154fa  jns     loc_1800155B9
0x180015500  mov     rcx, [rbp+57h+arg_10]
0x180015504  lea     rdx, [rbp+57h+arg_18]
0x180015508  mov     [rbp+57h+arg_18], r12
0x18001550c  mov     rax, [rcx]
0x18001550f  mov     rax, [rax+38h]
0x180015513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015518  mov     rcx, [rbp+57h+arg_10]
0x18001551c  mov     ebx, eax
0x18001551e  cmp     rcx, r14
0x180015521  jz      short loc_18001552F
0x180015523  mov     rax, [rcx]
0x180015526  mov     rax, [rax+10h]
0x18001552a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001552f  mov     [rbp+57h+arg_10], r12
0x180015533  mov     rdi, r12
0x180015536  test    ebx, ebx
0x180015538  js      loc_18001542E
0x18001553e  mov     rcx, [rbp+57h+arg_18]
0x180015542  test    rcx, rcx
0x180015545  jz      loc_18001542E
0x18001554b  mov     rax, [rcx]
0x18001554e  lea     r8, [rbp+57h+arg_10]
0x180015552  lea     rdx, IID_IAccessible
0x180015559  mov     rax, [rax]
0x18001555c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015561  mov     rcx, [rbp+57h+arg_18]
0x180015565  mov     ebx, eax
0x180015567  mov     rax, [rcx]
0x18001556a  mov     rax, [rax+10h]
0x18001556e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015573  jmp     loc_18001542A
0x180015578  mov     rcx, [rbp+57h+arg_8]
0x18001557c  test    rcx, rcx
0x18001557f  jz      short loc_1800155AA
0x180015581  mov     rax, [rcx]
0x180015584  mov     rdx, r15
0x180015587  mov     rax, [rax+18h]
0x18001558b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015590  mov     rcx, [rbp+57h+arg_8]
0x180015594  mov     ebx, eax
0x180015596  mov     rax, [rcx]
0x180015599  mov     rax, [rax+10h]
0x18001559d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155a2  test    ebx, ebx
0x1800155a4  js      loc_1800154DD
0x1800155aa  mov     rax, [rsi]
0x1800155ad  mov     rcx, rsi
0x1800155b0  mov     rax, [rax+10h]
0x1800155b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155b9  mov     rcx, [rbp+57h+arg_10]
0x1800155bd  cmp     rcx, r14
0x1800155c0  jz      short loc_1800155CE
0x1800155c2  mov     rax, [rcx]
0x1800155c5  mov     rax, [rax+10h]
0x1800155c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155ce  mov     rdi, [rsp+0C0h+var_30]
0x1800155d6  mov     eax, ebx
0x1800155d8  mov     rsi, [rsp+0C0h+var_28]
0x1800155e0  mov     rbx, [rsp+0C0h+var_20]
0x1800155e8  add     rsp, 0A8h
0x1800155ef  pop     r15
0x1800155f1  pop     r14
0x1800155f3  pop     r12
0x1800155f5  pop     rbp
0x1800155f6  retn
0x1800155f7  mov     rax, [rdi]
0x1800155fa  mov     rcx, rdi
0x1800155fd  mov     rsi, rdi
0x180015600  mov     rax, [rax+8]
0x180015604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015609  jmp     loc_1800154B1
0x18001560e  mov     rcx, [rbp+57h+var_90]
0x180015612  lea     rdx, [rbp+57h+arg_8]
0x180015616  mov     [rbp+57h+arg_8], r12
0x18001561a  mov     rax, [rcx]
0x18001561d  mov     rax, [rax+18h]
0x180015621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015626  mov     rcx, [rbp+57h+var_90]
0x18001562a  mov     ebx, eax
0x18001562c  mov     rdx, [rcx]
0x18001562f  mov     rax, [rdx+10h]
0x180015633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015638  test    ebx, ebx
0x18001563a  js      loc_1800153C4
0x180015640  mov     rax, [rbp+57h+arg_8]
0x180015644  test    rax, rax
0x180015647  jz      loc_1800153C4
0x18001564d  mov     [r15], rax
0x180015650  xor     eax, eax
0x180015652  jmp     short loc_1800155E0
0x180015654  cmp     word ptr [rbp+57h+var_70], 3
0x180015659  jnz     loc_180015417
0x18001565f  movsxd  rax, dword ptr [rbp+57h+var_70+8]
0x180015663  test    eax, eax
0x180015665  jz      loc_180015417
0x18001566b  jmp     short loc_18001564D
0x18001566d  lea     r8, [rbp+57h+ppStm]; ppStm
0x180015671  mov     [rbp+57h+ppStm], r12
0x180015675  mov     rdx, rsi; pUnk
0x180015678  lea     rcx, IID_IAccessible; riid
0x18001567f  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180015685  mov     ebx, eax
0x180015687  test    eax, eax
0x180015689  jnz     loc_1800154E9
0x18001568f  mov     rax, [rbp+57h+ppStm]
0x180015693  lea     r9, [rbp+57h+var_50]
0x180015697  mov     qword ptr [rbp+57h+var_50], rax
0x18001569b  lea     r8, STA_Thread
0x1800156a2  lea     rax, [rbp+57h+arg_8]
0x1800156a6  mov     [rbp+57h+var_40], r12
0x1800156aa  mov     [rsp+0C0h+var_98], rax
0x1800156af  xor     edx, edx
0x1800156b1  xor     ecx, ecx
0x1800156b3  mov     [rsp+0C0h+var_A0], r12d
0x1800156b8  mov     qword ptr [rbp+57h+var_50+8], r15
0x1800156bc  mov     dword ptr [rbp+57h+arg_8], r12d
0x1800156c0  call    cs:__imp__o__beginthreadex
0x1800156c6  mov     rdi, rax
0x1800156c9  test    rax, rax
0x1800156cc  jz      short loc_1800156FB
0x1800156ce  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800156d3  mov     rcx, rax; hHandle
0x1800156d6  call    cs:__imp_WaitForSingleObject
0x1800156dc  mov     ebx, dword ptr [rbp+57h+var_40]
0x1800156df  mov     rcx, rdi; hObject
0x1800156e2  call    cs:__imp_CloseHandle
0x1800156e8  jmp     loc_1800154E9
0x1800156ed  test    rsi, rsi
0x1800156f0  jnz     loc_1800154B6
0x1800156f6  jmp     loc_1800155F7
0x1800156fb  call    cs:__imp_GetLastError
0x180015701  mov     ebx, eax
0x180015703  test    eax, eax
0x180015705  jle     loc_1800154E9
0x18001570b  movzx   ebx, ax
0x18001570e  or      ebx, 80070000h
0x180015714  jmp     loc_1800154E9
0x180015719  mov     eax, 80070057h
0x18001571e  jmp     loc_1800155E8
```
