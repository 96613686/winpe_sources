# CMsftRawCDImageCreator::AddSpecialPregap(IStream *)

- ea: `0x18003c3d0`
- end: `0x18003c6ee`
- name: `?AddSpecialPregap@CMsftRawCDImageCreator@@UEAAJPEAUIStream@@@Z`
- size: `798`
- prototype: `__int64 __fastcall(CMsftRawCDImageCreator *this, struct IStream *, const struct _GUID *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002fc8`
- `0x18000ea20`
- `0x1800140f4`
- `0x180016778`
- `0x18003c3d0`
- `0x180040d54`
- `0x18004a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18003c51b`
- `ole32!CoCreateInstance` at `0x18003c5c9`
- `ole32!CoCreateInstance` at `0x18003c51b`
- `ole32!CoCreateInstance` at `0x18003c5c9`

## pseudocode

```c
__int64 __fastcall CMsftRawCDImageCreator::AddSpecialPregap(
        CMsftRawCDImageCreator *this,
        struct IStream *a2,
        const struct _GUID *a3)
{
  signed int v5; // ebx
  PVOID *v6; // rcx
  HRESULT Instance; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  struct IStream *v11; // [rsp+60h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+10h] BYREF

  v5 = 0;
  ppv = 0;
  v11 = 0;
  if ( !*((_WORD *)this + 36) )
    goto LABEL_6;
  v5 = -2136339968;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 87), 40, &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids);
LABEL_6:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)this + 27) )
  {
    v5 = -2136339964;
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 708) & 0x10) != 0 && *((_BYTE *)v6 + 705) >= 3u )
    {
      WPP_SF_(v6[87], 41, &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( *((_WORD *)this + 43) )
  {
    v5 = -2136339964;
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 708) & 0x10) != 0 && *((_BYTE *)v6 + 705) >= 3u )
    {
      WPP_SF_(v6[87], 42, &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( !a2 )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 708) & 0x10) != 0 && *((_BYTE *)v6 + 705) >= 3u )
      WPP_SF_(v6[87], 43, &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids);
    v5 = -2147467261;
    goto LABEL_53;
  }
  if ( v5 >= 0 )
  {
    Instance = CoCreateInstance(&CLSID_MsftStreamZero, 0, 0x17u, &GUID_0000000c_0000_0000_c000_000000000046, &ppv);
    v5 = Instance;
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 48LL))(ppv, 352800);
      v5 = Instance;
      if ( Instance >= 0 )
      {
        Instance = CoCreateInstance(
                     &CLSID_MsftStreamConcatenate,
                     0,
                     0x17u,
                     &GUID_27354146_7f64_5b0f_8f00_5d77afbe261e,
                     (LPVOID *)&v11);
        v5 = Instance;
        if ( Instance >= 0 )
        {
          Instance = (*(__int64 (__fastcall **)(struct IStream *, LPVOID, struct IStream *))(*(_QWORD *)v11 + 112LL))(
                       v11,
                       ppv,
                       a2);
          v5 = Instance;
          if ( Instance >= 0 )
          {
            Instance = CTrackData::Init((struct IUnknown **)this + 16, IMAPI_CD_SECTOR_AUDIO, v11);
            v5 = Instance;
            if ( Instance >= 0 )
            {
              *((_WORD *)this + 43) = -1;
              *((_WORD *)this + 21665) = -1;
            }
            else
            {
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
              {
                v9 = 48;
                goto LABEL_49;
              }
            }
          }
          else
          {
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
            {
              v9 = 47;
              goto LABEL_49;
            }
          }
        }
        else
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
          {
            v9 = 46;
            goto LABEL_49;
          }
        }
      }
      else
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
        {
          v9 = 45;
          goto LABEL_49;
        }
      }
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
      {
        v9 = 44;
LABEL_49:
        WPP_SF_d(v8[87], v9, &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids, (unsigned int)Instance);
      }
    }
  }
  if ( (v5 & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(v5, (int)&CLSID_MsftRawCDImageCreator, a3);
LABEL_53:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003c3d0  mov     [rsp+arg_10], rbx
0x18003c3d5  push    rbp
0x18003c3d6  push    rsi
0x18003c3d7  push    rdi
0x18003c3d8  push    r12
0x18003c3da  push    r13
0x18003c3dc  sub     rsp, 30h
0x18003c3e0  xor     ebp, ebp
0x18003c3e2  lea     r13, WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids
0x18003c3e9  lea     r12, WPP_GLOBAL_Control
0x18003c3f0  mov     rsi, rdx
0x18003c3f3  mov     rdi, rcx
0x18003c3f6  mov     ebx, ebp
0x18003c3f8  mov     [rsp+58h+arg_8], rbp
0x18003c3fd  mov     [rsp+58h+arg_0], rbp
0x18003c402  cmp     [rcx+48h], bp
0x18003c406  jz      short loc_18003C43D
0x18003c408  mov     ebx, 80AA0A00h
0x18003c40d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c414  cmp     rcx, r12
0x18003c417  jz      short loc_18003C444
0x18003c419  test    byte ptr [rcx+2C4h], 10h
0x18003c420  jz      short loc_18003C444
0x18003c422  cmp     byte ptr [rcx+2C1h], 3
0x18003c429  jb      short loc_18003C444
0x18003c42b  mov     rcx, [rcx+2B8h]
0x18003c432  lea     edx, [rbp+28h]
0x18003c435  mov     r8, r13
0x18003c438  call    WPP_SF_
0x18003c43d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c444  cmp     [rdi+6Ch], ebp
0x18003c447  jz      short loc_18003C480
0x18003c449  mov     ebx, 80AA0A04h
0x18003c44e  cmp     rcx, r12
0x18003c451  jz      short loc_18003C480
0x18003c453  test    byte ptr [rcx+2C4h], 10h
0x18003c45a  jz      short loc_18003C480
0x18003c45c  cmp     byte ptr [rcx+2C1h], 3
0x18003c463  jb      short loc_18003C480
0x18003c465  mov     rcx, [rcx+2B8h]
0x18003c46c  mov     edx, 29h ; ')'
0x18003c471  mov     r8, r13
0x18003c474  call    WPP_SF_
0x18003c479  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c480  cmp     [rdi+56h], bp
0x18003c484  jz      short loc_18003C4BD
0x18003c486  mov     ebx, 80AA0A04h
0x18003c48b  cmp     rcx, r12
0x18003c48e  jz      short loc_18003C4BD
0x18003c490  test    byte ptr [rcx+2C4h], 10h
0x18003c497  jz      short loc_18003C4BD
0x18003c499  cmp     byte ptr [rcx+2C1h], 3
0x18003c4a0  jb      short loc_18003C4BD
0x18003c4a2  mov     rcx, [rcx+2B8h]
0x18003c4a9  mov     edx, 2Ah ; '*'
0x18003c4ae  mov     r8, r13
0x18003c4b1  call    WPP_SF_
0x18003c4b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c4bd  test    rsi, rsi
0x18003c4c0  jnz     short loc_18003C4F5
0x18003c4c2  cmp     rcx, r12
0x18003c4c5  jz      short loc_18003C4EB
0x18003c4c7  test    byte ptr [rcx+2C4h], 10h
0x18003c4ce  jz      short loc_18003C4EB
0x18003c4d0  cmp     byte ptr [rcx+2C1h], 3
0x18003c4d7  jb      short loc_18003C4EB
0x18003c4d9  mov     rcx, [rcx+2B8h]
0x18003c4e0  lea     edx, [rsi+2Bh]
0x18003c4e3  mov     r8, r13
0x18003c4e6  call    WPP_SF_
0x18003c4eb  mov     ebx, 80004003h
0x18003c4f0  jmp     loc_18003C6C7
0x18003c4f5  test    ebx, ebx
0x18003c4f7  js      loc_18003C6AB
0x18003c4fd  xor     edx, edx; pUnkOuter
0x18003c4ff  lea     rax, [rsp+58h+arg_8]
0x18003c504  lea     r9, _GUID_0000000c_0000_0000_c000_000000000046; riid
0x18003c50b  mov     [rsp+58h+ppv], rax; ppv
0x18003c510  lea     rcx, CLSID_MsftStreamZero; rclsid
0x18003c517  lea     r8d, [rdx+17h]; dwClsContext
0x18003c51b  call    cs:__imp_CoCreateInstance
0x18003c521  mov     ebx, eax
0x18003c523  test    eax, eax
0x18003c525  jns     short loc_18003C55B
0x18003c527  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c52e  cmp     rcx, r12
0x18003c531  jz      loc_18003C6AB
0x18003c537  test    byte ptr [rcx+2C4h], 10h
0x18003c53e  jz      loc_18003C6AB
0x18003c544  cmp     byte ptr [rcx+2C1h], 3
0x18003c54b  jb      loc_18003C6AB
0x18003c551  mov     edx, 2Ch ; ','
0x18003c556  jmp     loc_18003C689
0x18003c55b  mov     rcx, [rsp+58h+arg_8]
0x18003c560  mov     edx, 56220h
0x18003c565  mov     rax, [rcx]
0x18003c568  mov     rax, [rax+30h]
0x18003c56c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c571  mov     ebx, eax
0x18003c573  test    eax, eax
0x18003c575  jns     short loc_18003C5AB
0x18003c577  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c57e  cmp     rcx, r12
0x18003c581  jz      loc_18003C6AB
0x18003c587  test    byte ptr [rcx+2C4h], 10h
0x18003c58e  jz      loc_18003C6AB
0x18003c594  cmp     byte ptr [rcx+2C1h], 3
0x18003c59b  jb      loc_18003C6AB
0x18003c5a1  mov     edx, 2Dh ; '-'
0x18003c5a6  jmp     loc_18003C689
0x18003c5ab  xor     edx, edx; pUnkOuter
0x18003c5ad  lea     rax, [rsp+58h+arg_0]
0x18003c5b2  lea     r9, _GUID_27354146_7f64_5b0f_8f00_5d77afbe261e; riid
0x18003c5b9  mov     [rsp+58h+ppv], rax; ppv
0x18003c5be  lea     rcx, CLSID_MsftStreamConcatenate; rclsid
0x18003c5c5  lea     r8d, [rdx+17h]; dwClsContext
0x18003c5c9  call    cs:__imp_CoCreateInstance
0x18003c5cf  mov     ebx, eax
0x18003c5d1  test    eax, eax
0x18003c5d3  jns     short loc_18003C609
0x18003c5d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c5dc  cmp     rcx, r12
0x18003c5df  jz      loc_18003C6AB
0x18003c5e5  test    byte ptr [rcx+2C4h], 10h
0x18003c5ec  jz      loc_18003C6AB
0x18003c5f2  cmp     byte ptr [rcx+2C1h], 3
0x18003c5f9  jb      loc_18003C6AB
0x18003c5ff  mov     edx, 2Eh ; '.'
0x18003c604  jmp     loc_18003C689
0x18003c609  mov     rcx, [rsp+58h+arg_0]
0x18003c60e  mov     r8, rsi
0x18003c611  mov     rdx, [rsp+58h+arg_8]
0x18003c616  mov     rax, [rcx]
0x18003c619  mov     rax, [rax+70h]
0x18003c61d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c622  mov     ebx, eax
0x18003c624  test    eax, eax
0x18003c626  jns     short loc_18003C64D
0x18003c628  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c62f  cmp     rcx, r12
0x18003c632  jz      short loc_18003C6AB
0x18003c634  test    byte ptr [rcx+2C4h], 10h
0x18003c63b  jz      short loc_18003C6AB
0x18003c63d  cmp     byte ptr [rcx+2C1h], 3
0x18003c644  jb      short loc_18003C6AB
0x18003c646  mov     edx, 2Fh ; '/'
0x18003c64b  jmp     short loc_18003C689
0x18003c64d  mov     r8, [rsp+58h+arg_0]; struct IStream *
0x18003c652  lea     rcx, [rdi+80h]; this
0x18003c659  xor     edx, edx; enum _IMAPI_CD_SECTOR_TYPE
0x18003c65b  call    ?Init@CTrackData@@QEAAJW4_IMAPI_CD_SECTOR_TYPE@@PEAUIStream@@@Z; CTrackData::Init(_IMAPI_CD_SECTOR_TYPE,IStream *)
0x18003c660  mov     ebx, eax
0x18003c662  test    eax, eax
0x18003c664  jns     short loc_18003C69D
0x18003c666  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c66d  cmp     rcx, r12
0x18003c670  jz      short loc_18003C6AB
0x18003c672  test    byte ptr [rcx+2C4h], 10h
0x18003c679  jz      short loc_18003C6AB
0x18003c67b  cmp     byte ptr [rcx+2C1h], 3
0x18003c682  jb      short loc_18003C6AB
0x18003c684  mov     edx, 30h ; '0'
0x18003c689  mov     rcx, [rcx+2B8h]
0x18003c690  mov     r9d, eax
0x18003c693  mov     r8, r13
0x18003c696  call    WPP_SF_d
0x18003c69b  jmp     short loc_18003C6AB
0x18003c69d  or      eax, 0FFFFFFFFh
0x18003c6a0  mov     [rdi+56h], ax
0x18003c6a4  mov     [rdi+0A942h], ax
0x18003c6ab  mov     eax, ebx
0x18003c6ad  and     eax, 80FF0000h
0x18003c6b2  cmp     eax, 80AA0000h
0x18003c6b7  jnz     short loc_18003C6C7
0x18003c6b9  lea     rdx, CLSID_MsftRawCDImageCreator; int
0x18003c6c0  mov     ecx, ebx; dwMessageId
0x18003c6c2  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x18003c6c7  lea     rcx, [rsp+58h+arg_0]
0x18003c6cc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003c6d1  lea     rcx, [rsp+58h+arg_8]
0x18003c6d6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003c6db  mov     eax, ebx
0x18003c6dd  mov     rbx, [rsp+58h+arg_10]
0x18003c6e2  add     rsp, 30h
0x18003c6e6  pop     r13
0x18003c6e8  pop     r12
0x18003c6ea  pop     rdi
0x18003c6eb  pop     rsi
0x18003c6ec  pop     rbp
0x18003c6ed  retn
```
