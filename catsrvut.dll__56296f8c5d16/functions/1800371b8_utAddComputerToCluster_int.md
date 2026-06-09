# utAddComputerToCluster(int)

- ea: `0x1800371b8`
- end: `0x180037436`
- name: `?utAddComputerToCluster@@YAJH@Z`
- size: `638`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180035c30`

## callees

- `0x180010f64`
- `0x180035344`
- `0x1800371b8`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `KERNEL32!GetComputerNameW` at `0x1800372a8`
- `KERNEL32!GetComputerNameW` at `0x1800372a8`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180037208`
- `CLBCatQ!GetSimpleTableDispenser` at `0x180037208`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall utAddComputerToCluster(int a1)
{
  int SimpleTableDispenser; // ebx
  __int64 v2; // rax
  unsigned __int16 *v3; // rax
  int v4; // r8d
  int v5; // edx
  struct IUnknown *v7; // [rsp+50h] [rbp-9h] BYREF
  struct IUnknown *v8; // [rsp+58h] [rbp-1h] BYREF
  DWORD nSize; // [rsp+60h] [rbp+7h] BYREF
  int v10; // [rsp+64h] [rbp+Bh] BYREF
  int v11; // [rsp+68h] [rbp+Fh] BYREF
  struct IUnknown *v12; // [rsp+70h] [rbp+17h] BYREF
  __int64 v13; // [rsp+78h] [rbp+1Fh] BYREF
  char *v14; // [rsp+80h] [rbp+27h] BYREF
  WCHAR Buffer[16]; // [rsp+88h] [rbp+2Fh] BYREF

  v13 = 0;
  v12 = 0;
  v8 = 0;
  v7 = 0;
  nSize = 0;
  if ( a1 )
  {
    SimpleTableDispenser = GetSimpleTableDispenser(&IID_ISimpleTableDispenser, &v13);
    if ( SimpleTableDispenser >= 0 )
    {
      SimpleTableDispenser = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64 *, _QWORD, _QWORD, int, _DWORD, struct IUnknown **))(*(_QWORD *)v13 + 24LL))(
                               v13,
                               &didCOMSERVICES,
                               &TID_SERVERGROUP,
                               0,
                               0,
                               1,
                               0,
                               &v12);
      if ( SimpleTableDispenser >= 0 )
      {
        ATL::AtlComQIPtrAssign(&v8, v12, &IID_ISimpleTableRead);
        ATL::AtlComQIPtrAssign(&v7, v12, &IID_ISimpleTableWrite);
        nSize = 16;
        if ( !v8 )
          goto LABEL_27;
        if ( !v7 )
          goto LABEL_27;
        if ( !GetComputerNameW(Buffer, &nSize) )
          goto LABEL_27;
        v2 = -1;
        do
          ++v2;
        while ( Buffer[v2] );
        if ( v2 )
        {
          SimpleTableDispenser = ((__int64 (__fastcall *)(struct IUnknown *))v8->lpVtbl[1].QueryInterface)(v8);
          if ( SimpleTableDispenser >= 0 )
          {
            if ( ((int (__fastcall *)(struct IUnknown *))v8->lpVtbl[1].AddRef)(v8) < 0 )
              goto LABEL_23;
            while ( !((unsigned int (__fastcall *)(struct IUnknown *))v8->lpVtbl[1].Release)(v8) )
            {
              v11 = 0;
              v10 = 0;
              v14 = 0;
              SimpleTableDispenser = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, int *, int *, char **))v8->lpVtbl[2].Release)(
                                       v8,
                                       0,
                                       &v11,
                                       &v10,
                                       &v14);
              if ( SimpleTableDispenser >= 0 && v10 && v11 == 130 )
              {
                v3 = (unsigned __int16 *)v14;
                do
                {
                  v4 = *(unsigned __int16 *)((char *)v3 + (char *)Buffer - v14);
                  v5 = *v3 - v4;
                  if ( v5 )
                    break;
                  ++v3;
                }
                while ( v4 );
                if ( !v5 )
                  goto LABEL_28;
              }
            }
            if ( SimpleTableDispenser >= 0 )
            {
LABEL_23:
              SimpleTableDispenser = ((__int64 (__fastcall *)(struct IUnknown *))v7->lpVtbl[5].QueryInterface)(v7);
              if ( SimpleTableDispenser >= 0 )
              {
                SimpleTableDispenser = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, _QWORD, WCHAR *))v7->lpVtbl[6].Release)(
                                         v7,
                                         0,
                                         0,
                                         Buffer);
                if ( SimpleTableDispenser >= 0 )
                {
                  SimpleTableDispenser = ((__int64 (__fastcall *)(struct IUnknown *))v7->lpVtbl[6].QueryInterface)(v7);
                  if ( SimpleTableDispenser >= 0 )
                    SimpleTableDispenser = ((__int64 (__fastcall *)(struct IUnknown *))v7->lpVtbl[4].QueryInterface)(v7);
                }
              }
            }
          }
        }
        else
        {
LABEL_27:
          SimpleTableDispenser = -2147418113;
        }
      }
    }
  }
  else
  {
    SimpleTableDispenser = 0;
  }
LABEL_28:
  ATL::CComPtr<ISimpleTableDispenser>::~CComPtr<ISimpleTableDispenser>((__int64 *)&v7);
  ATL::CComPtr<ISimpleTableDispenser>::~CComPtr<ISimpleTableDispenser>((__int64 *)&v8);
  ATL::CComPtr<ISimpleTableDispenser>::~CComPtr<ISimpleTableDispenser>((__int64 *)&v12);
  ATL::CComPtr<ISimpleTableDispenser>::~CComPtr<ISimpleTableDispenser>(&v13);
  return (unsigned int)SimpleTableDispenser;
}

```

## disassembly

```asm
0x1800371b8  mov     [rsp-8+arg_0], rbx
0x1800371bd  mov     [rsp-8+arg_8], rdi
0x1800371c2  push    rbp
0x1800371c3  lea     rbp, [rsp-57h]
0x1800371c8  sub     rsp, 0B0h
0x1800371cf  mov     rax, cs:__security_cookie
0x1800371d6  xor     rax, rsp
0x1800371d9  mov     [rbp+57h+var_8], rax
0x1800371dd  xor     edi, edi
0x1800371df  mov     [rbp+57h+var_38], rdi
0x1800371e3  mov     [rbp+57h+var_40], rdi
0x1800371e7  mov     [rbp+57h+var_58], rdi
0x1800371eb  mov     [rbp+57h+var_60], rdi
0x1800371ef  mov     [rbp+57h+nSize], edi
0x1800371f2  test    ecx, ecx
0x1800371f4  jnz     short loc_1800371FD
0x1800371f6  mov     ebx, edi
0x1800371f8  jmp     loc_1800373EC
0x1800371fd  lea     rdx, [rbp+57h+var_38]
0x180037201  lea     rcx, IID_ISimpleTableDispenser
0x180037208  call    cs:__imp_GetSimpleTableDispenser
0x18003720e  mov     ebx, eax
0x180037210  test    eax, eax
0x180037212  js      loc_1800373EC
0x180037218  mov     rcx, [rbp+57h+var_38]
0x18003721c  mov     rax, [rcx]
0x18003721f  lea     rdx, [rbp+57h+var_40]
0x180037223  mov     [rsp+0B0h+var_78], rdx
0x180037228  mov     [rsp+0B0h+var_80], edi
0x18003722c  mov     [rsp+0B0h+var_88], 1
0x180037234  mov     [rsp+0B0h+var_90], rdi
0x180037239  xor     r9d, r9d
0x18003723c  lea     r8, TID_SERVERGROUP
0x180037243  lea     rdx, didCOMSERVICES
0x18003724a  mov     rax, [rax+18h]
0x18003724e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037253  mov     ebx, eax
0x180037255  test    eax, eax
0x180037257  js      loc_1800373EC
0x18003725d  lea     r8, IID_ISimpleTableRead; struct _GUID *
0x180037264  mov     rdx, [rbp+57h+var_40]; struct IUnknown *
0x180037268  lea     rcx, [rbp+57h+var_58]; struct IUnknown **
0x18003726c  call    ?AtlComQIPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@AEBU_GUID@@@Z; ATL::AtlComQIPtrAssign(IUnknown * *,IUnknown *,_GUID const &)
0x180037271  lea     r8, IID_ISimpleTableWrite; struct _GUID *
0x180037278  mov     rdx, [rbp+57h+var_40]; struct IUnknown *
0x18003727c  lea     rcx, [rbp+57h+var_60]; struct IUnknown **
0x180037280  call    ?AtlComQIPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@AEBU_GUID@@@Z; ATL::AtlComQIPtrAssign(IUnknown * *,IUnknown *,_GUID const &)
0x180037285  mov     [rbp+57h+nSize], 10h
0x18003728c  cmp     [rbp+57h+var_58], rdi
0x180037290  jz      loc_1800373E7
0x180037296  cmp     [rbp+57h+var_60], rdi
0x18003729a  jz      loc_1800373E7
0x1800372a0  lea     rdx, [rbp+57h+nSize]; nSize
0x1800372a4  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x1800372a8  call    cs:__imp_GetComputerNameW
0x1800372ae  test    eax, eax
0x1800372b0  jz      loc_1800373E7
0x1800372b6  lea     rcx, [rbp+57h+Buffer]
0x1800372ba  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800372be  inc     rax
0x1800372c1  cmp     [rcx+rax*2], di
0x1800372c5  jnz     short loc_1800372BE
0x1800372c7  test    rax, rax
0x1800372ca  jz      loc_1800373E7
0x1800372d0  mov     rcx, [rbp+57h+var_58]
0x1800372d4  mov     rax, [rcx]
0x1800372d7  mov     rax, [rax+18h]
0x1800372db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800372e0  mov     ebx, eax
0x1800372e2  test    eax, eax
0x1800372e4  js      loc_1800373EC
0x1800372ea  mov     rcx, [rbp+57h+var_58]
0x1800372ee  mov     rax, [rcx]
0x1800372f1  mov     rax, [rax+20h]
0x1800372f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800372fa  test    eax, eax
0x1800372fc  js      loc_180037382
0x180037302  mov     rcx, [rbp+57h+var_58]
0x180037306  mov     rax, [rcx]
0x180037309  mov     rax, [rax+28h]
0x18003730d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037312  test    eax, eax
0x180037314  jnz     short loc_18003737E
0x180037316  mov     [rbp+57h+var_48], edi
0x180037319  mov     [rbp+57h+var_4C], edi
0x18003731c  mov     [rbp+57h+var_30], rdi
0x180037320  mov     rcx, [rbp+57h+var_58]
0x180037324  mov     rax, [rcx]
0x180037327  lea     rdx, [rbp+57h+var_30]
0x18003732b  mov     [rsp+0B0h+var_90], rdx
0x180037330  lea     r9, [rbp+57h+var_4C]
0x180037334  lea     r8, [rbp+57h+var_48]
0x180037338  xor     edx, edx
0x18003733a  mov     rax, [rax+40h]
0x18003733e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037343  mov     ebx, eax
0x180037345  test    eax, eax
0x180037347  js      short loc_180037302
0x180037349  cmp     [rbp+57h+var_4C], edi
0x18003734c  jbe     short loc_180037302
0x18003734e  cmp     [rbp+57h+var_48], 82h
0x180037355  jnz     short loc_180037302
0x180037357  mov     rax, [rbp+57h+var_30]
0x18003735b  lea     rcx, [rbp+57h+Buffer]
0x18003735f  sub     rcx, rax
0x180037362  movzx   edx, word ptr [rax]
0x180037365  movzx   r8d, word ptr [rax+rcx]
0x18003736a  sub     edx, r8d
0x18003736d  jnz     short loc_180037378
0x18003736f  add     rax, 2
0x180037373  test    r8d, r8d
0x180037376  jnz     short loc_180037362
0x180037378  test    edx, edx
0x18003737a  jnz     short loc_180037302
0x18003737c  jmp     short loc_1800373EC
0x18003737e  test    ebx, ebx
0x180037380  js      short loc_1800373EC
0x180037382  mov     rcx, [rbp+57h+var_60]
0x180037386  mov     rax, [rcx]
0x180037389  mov     rax, [rax+78h]
0x18003738d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037392  mov     ebx, eax
0x180037394  test    eax, eax
0x180037396  js      short loc_1800373EC
0x180037398  mov     rcx, [rbp+57h+var_60]
0x18003739c  mov     rax, [rcx]
0x18003739f  lea     r9, [rbp+57h+Buffer]
0x1800373a3  xor     r8d, r8d
0x1800373a6  xor     edx, edx
0x1800373a8  mov     rax, [rax+0A0h]
0x1800373af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800373b4  mov     ebx, eax
0x1800373b6  test    eax, eax
0x1800373b8  js      short loc_1800373EC
0x1800373ba  mov     rcx, [rbp+57h+var_60]
0x1800373be  mov     rax, [rcx]
0x1800373c1  mov     rax, [rax+90h]
0x1800373c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800373cd  mov     ebx, eax
0x1800373cf  test    eax, eax
0x1800373d1  js      short loc_1800373EC
0x1800373d3  mov     rcx, [rbp+57h+var_60]
0x1800373d7  mov     rax, [rcx]
0x1800373da  mov     rax, [rax+60h]
0x1800373de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800373e3  mov     ebx, eax
0x1800373e5  jmp     short loc_1800373EC
0x1800373e7  mov     ebx, 8000FFFFh
0x1800373ec  lea     rcx, [rbp+57h+var_60]
0x1800373f0  call    ??1?$CComPtr@UISimpleTableDispenser@@@ATL@@QEAA@XZ; ATL::CComPtr<ISimpleTableDispenser>::~CComPtr<ISimpleTableDispenser>(void)
0x1800373f5  nop
0x1800373f6  lea     rcx, [rbp+57h+var_58]
0x1800373fa  call    ??1?$CComPtr@UISimpleTableDispenser@@@ATL@@QEAA@XZ; ATL::CComPtr<ISimpleTableDispenser>::~CComPtr<ISimpleTableDispenser>(void)
0x1800373ff  nop
0x180037400  lea     rcx, [rbp+57h+var_40]
0x180037404  call    ??1?$CComPtr@UISimpleTableDispenser@@@ATL@@QEAA@XZ; ATL::CComPtr<ISimpleTableDispenser>::~CComPtr<ISimpleTableDispenser>(void)
0x180037409  nop
0x18003740a  lea     rcx, [rbp+57h+var_38]
0x18003740e  call    ??1?$CComPtr@UISimpleTableDispenser@@@ATL@@QEAA@XZ; ATL::CComPtr<ISimpleTableDispenser>::~CComPtr<ISimpleTableDispenser>(void)
0x180037413  mov     eax, ebx
0x180037415  mov     rcx, [rbp+57h+var_8]
0x180037419  xor     rcx, rsp; StackCookie
0x18003741c  call    __security_check_cookie
0x180037421  lea     r11, [rsp+0B0h+var_s0]
0x180037429  mov     rbx, [r11+10h]
0x18003742d  mov     rdi, [r11+18h]
0x180037431  mov     rsp, r11
0x180037434  pop     rbp
0x180037435  retn
```
