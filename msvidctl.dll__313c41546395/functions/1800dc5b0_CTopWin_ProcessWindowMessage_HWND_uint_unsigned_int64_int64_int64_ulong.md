# CTopWin::ProcessWindowMessage(HWND__ *,uint,unsigned __int64,__int64,__int64 &,ulong)

- ea: `0x1800dc5b0`
- end: `0x1800dc742`
- name: `?ProcessWindowMessage@CTopWin@@UEAAHPEAUHWND__@@I_K_JAEA_JK@Z`
- size: `402`
- prototype: `__int64 __fastcall(CTopWin *__hidden this, HWND, unsigned int, unsigned __int64, __int64, __int64 *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180006b38`
- `0x1800c1858`
- `0x1800cc868`
- `0x1800ce6c0`
- `0x1800dc5b0`
- `0x1800dc748`
- `0x1800f8010`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x1800dc6d8`
- `USER32!SystemParametersInfoW` at `0x1800dc6f0`
- `USER32!SystemParametersInfoW` at `0x1800dc6d8`
- `USER32!SystemParametersInfoW` at `0x1800dc6f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTopWin::ProcessWindowMessage(
        CTopWin *this,
        HWND a2,
        const struct tagRECT *a3,
        unsigned __int64 a4,
        __int64 a5)
{
  __int64 v5; // rcx
  CGraphReentrancyLock *v7; // r10
  UINT pvParam; // [rsp+40h] [rbp-18h] BYREF
  _QWORD v9[2]; // [rsp+48h] [rbp-10h] BYREF
  __int16 v10; // [rsp+60h] [rbp+8h] BYREF

  v5 = *((_QWORD *)this + 8);
  if ( !v5 )
    return 0;
  if ( (_DWORD)a3 != 126 )
  {
    if ( (_DWORD)a3 == 275 )
    {
      if ( *(_DWORD *)(v5 + 552) == 2 && *(_QWORD *)(v5 + 704) )
      {
        ATL::CComQIPtr<IMSVidVideoRenderer2,&__s_GUID const _GUID_6bdd5c1e_2810_4159_94bc_05511ae8549b>::CComQIPtr<IMSVidVideoRenderer2,&__s_GUID const _GUID_6bdd5c1e_2810_4159_94bc_05511ae8549b>(v9);
        if ( v9[0] )
        {
          v10 = 0;
          if ( (*(int (__fastcall **)(_QWORD, __int16 *))(*(_QWORD *)v9[0] + 416LL))(v9[0], &v10) >= 0 && v10 == -1 )
          {
            pvParam = 0;
            if ( SystemParametersInfoW(0xEu, 0, &pvParam, 0) )
              SystemParametersInfoW(0xFu, pvParam, 0, 0);
          }
        }
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(v9);
      }
      return 0;
    }
    if ( (_DWORD)a3 != 536 && (_DWORD)a3 != 537 )
    {
      switch ( (_DWORD)a3 )
      {
        case 0x400:
          v7 = (CGraphReentrancyLock *)(v5 + 488);
          if ( *(_BYTE *)(v5 + 488) )
          {
            LODWORD(a3) = 1024;
            goto LABEL_11;
          }
          CVidCtl::InPlaceActivate((CVidCtl *)v5, -5, a3);
          break;
        case 0x401:
          v7 = (CGraphReentrancyLock *)(v5 + 488);
          if ( *(_BYTE *)(v5 + 488) )
          {
            LODWORD(a3) = 1025;
            goto LABEL_11;
          }
          CVidCtl::OnSizeChange((CVidCtl *)v5);
          break;
        case 0x465:
          goto LABEL_10;
      }
      return 0;
    }
  }
LABEL_10:
  v7 = (CGraphReentrancyLock *)(v5 + 488);
  if ( *(_BYTE *)(v5 + 488) )
  {
LABEL_11:
    CGraphReentrancyLock::Q(v7, a2, (unsigned int)a3, a4, a5);
    return 1;
  }
  return (**(__int64 (__fastcall ***)(__int64, HWND))(v5 + 112))(v5 + 112, a2);
}

```

## disassembly

```asm
0x1800dc5b0  sub     rsp, 58h
0x1800dc5b4  mov     r11, rdx
0x1800dc5b7  mov     rcx, [rcx+40h]; this
0x1800dc5bb  test    rcx, rcx
0x1800dc5be  jnz     short loc_1800DC5C7
0x1800dc5c0  xor     eax, eax
0x1800dc5c2  jmp     loc_1800DC73D
0x1800dc5c7  mov     eax, r8d
0x1800dc5ca  sub     eax, 7Eh ; '~'
0x1800dc5cd  jz      short loc_1800DC5F7
0x1800dc5cf  sub     eax, 95h
0x1800dc5d4  jz      loc_1800DC66A
0x1800dc5da  sub     eax, 105h
0x1800dc5df  jz      short loc_1800DC5F7
0x1800dc5e1  sub     eax, 1
0x1800dc5e4  jz      short loc_1800DC5F7
0x1800dc5e6  sub     eax, 1E7h
0x1800dc5eb  jz      short loc_1800DC646
0x1800dc5ed  sub     eax, 1
0x1800dc5f0  jz      short loc_1800DC627
0x1800dc5f2  cmp     eax, 64h ; 'd'
0x1800dc5f5  jnz     short loc_1800DC5C0
0x1800dc5f7  lea     r10, [rcx+1E8h]
0x1800dc5fe  cmp     byte ptr [r10], 0
0x1800dc602  jz      loc_1800DC706
0x1800dc608  mov     rax, [rsp+58h+arg_20]
0x1800dc610  mov     [rsp+58h+var_38], rax; __int64
0x1800dc615  mov     rcx, r10; this
0x1800dc618  call    ?Q@CGraphReentrancyLock@@QEAAXPEAUHWND__@@I_K_J@Z; CGraphReentrancyLock::Q(HWND__ *,uint,unsigned __int64,__int64)
0x1800dc61d  mov     eax, 1
0x1800dc622  jmp     loc_1800DC73D
0x1800dc627  lea     r10, [rcx+1E8h]
0x1800dc62e  cmp     byte ptr [r10], 0
0x1800dc632  jz      short loc_1800DC63C
0x1800dc634  mov     r8d, 401h
0x1800dc63a  jmp     short loc_1800DC608
0x1800dc63c  call    ?OnSizeChange@CVidCtl@@IEAAXXZ; CVidCtl::OnSizeChange(void)
0x1800dc641  jmp     loc_1800DC5C0
0x1800dc646  lea     r10, [rcx+1E8h]
0x1800dc64d  cmp     byte ptr [r10], 0
0x1800dc651  jz      short loc_1800DC65B
0x1800dc653  mov     r8d, 400h; struct tagRECT *
0x1800dc659  jmp     short loc_1800DC608
0x1800dc65b  mov     edx, 0FFFFFFFBh; int
0x1800dc660  call    ?InPlaceActivate@CVidCtl@@QEAAJJPEBUtagRECT@@@Z; CVidCtl::InPlaceActivate(long,tagRECT const *)
0x1800dc665  jmp     loc_1800DC5C0
0x1800dc66a  cmp     dword ptr [rcx+228h], 2
0x1800dc671  jnz     loc_1800DC5C0
0x1800dc677  mov     rdx, [rcx+2C0h]
0x1800dc67e  test    rdx, rdx
0x1800dc681  jz      loc_1800DC5C0
0x1800dc687  lea     rcx, [rsp+58h+var_10]
0x1800dc68c  call    ??0?$CComQIPtr@UIMSVidVideoRenderer2@@$1?_GUID_6bdd5c1e_2810_4159_94bc_05511ae8549b@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IMSVidVideoRenderer2,&__s_GUID const _GUID_6bdd5c1e_2810_4159_94bc_05511ae8549b>::CComQIPtr<IMSVidVideoRenderer2,&__s_GUID const _GUID_6bdd5c1e_2810_4159_94bc_05511ae8549b>(IUnknown *)
0x1800dc691  nop
0x1800dc692  mov     rcx, [rsp+58h+var_10]
0x1800dc697  test    rcx, rcx
0x1800dc69a  jz      short loc_1800DC6F7
0x1800dc69c  xor     eax, eax
0x1800dc69e  mov     [rsp+58h+arg_0], ax
0x1800dc6a3  mov     rax, [rcx]
0x1800dc6a6  lea     rdx, [rsp+58h+arg_0]
0x1800dc6ab  mov     rax, [rax+1A0h]
0x1800dc6b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc6b7  test    eax, eax
0x1800dc6b9  js      short loc_1800DC6F7
0x1800dc6bb  cmp     [rsp+58h+arg_0], 0FFFFh
0x1800dc6c1  jnz     short loc_1800DC6F7
0x1800dc6c3  mov     [rsp+58h+pvParam], 0
0x1800dc6cb  xor     r9d, r9d; fWinIni
0x1800dc6ce  lea     r8, [rsp+58h+pvParam]; pvParam
0x1800dc6d3  xor     edx, edx; uiParam
0x1800dc6d5  lea     ecx, [rdx+0Eh]; uiAction
0x1800dc6d8  call    cs:__imp_SystemParametersInfoW
0x1800dc6de  test    eax, eax
0x1800dc6e0  jz      short loc_1800DC6F7
0x1800dc6e2  xor     r9d, r9d; fWinIni
0x1800dc6e5  xor     r8d, r8d; pvParam
0x1800dc6e8  mov     edx, [rsp+58h+pvParam]; uiParam
0x1800dc6ec  lea     ecx, [r9+0Fh]; uiAction
0x1800dc6f0  call    cs:__imp_SystemParametersInfoW
0x1800dc6f6  nop
0x1800dc6f7  lea     rcx, [rsp+58h+var_10]
0x1800dc6fc  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800dc701  jmp     loc_1800DC5C0
0x1800dc706  add     rcx, 70h ; 'p'
0x1800dc70a  mov     rax, [rcx]
0x1800dc70d  mov     edx, [rsp+58h+arg_30]
0x1800dc714  mov     [rsp+58h+var_28], edx
0x1800dc718  mov     rdx, [rsp+58h+arg_28]
0x1800dc720  mov     [rsp+58h+var_30], rdx
0x1800dc725  mov     rdx, [rsp+58h+arg_20]
0x1800dc72d  mov     [rsp+58h+var_38], rdx
0x1800dc732  mov     rdx, r11
0x1800dc735  mov     rax, [rax]
0x1800dc738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc73d  add     rsp, 58h
0x1800dc741  retn
```
