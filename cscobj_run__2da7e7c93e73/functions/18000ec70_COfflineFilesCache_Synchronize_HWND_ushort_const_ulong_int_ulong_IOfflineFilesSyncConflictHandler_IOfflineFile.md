# COfflineFilesCache::Synchronize(HWND__ *,ushort const * *,ulong,int,ulong,IOfflineFilesSyncConflictHandler *,IOfflineFilesSyncProgress *,_GUID *)

- ea: `0x18000ec70`
- end: `0x18000f082`
- name: `?Synchronize@COfflineFilesCache@@UEAAJPEAUHWND__@@PEAPEBGKHKPEAUIOfflineFilesSyncConflictHandler@@PEAUIOfflineFilesSyncProgress@@PEAU_GUID@@@Z`
- size: `1042`
- prototype: `__int64 __fastcall(COfflineFilesCache *__hidden this, HWND, const unsigned __int16 **, unsigned int, int, unsigned int, struct IOfflineFilesSyncConflictHandler *, struct IOfflineFilesSyncProgress *, struct _GUID *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callees

- `0x180006c00`
- `0x18000b390`
- `0x18000cd74`
- `0x18000d198`
- `0x18000ec70`
- `0x18000f0e4`
- `0x18000f5a4`
- `0x18000f5cc`
- `0x18000f60c`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall COfflineFilesCache::Synchronize(
        COfflineFilesCache *this,
        HWND a2,
        const unsigned __int16 **a3,
        unsigned int a4,
        int a5,
        unsigned int a6,
        struct IOfflineFilesSyncConflictHandler *a7,
        struct IOfflineFilesSyncProgress *a8,
        struct _GUID *a9)
{
  HWND v11; // rdi
  __int64 result; // rax
  unsigned int v13; // r14d
  const struct _GUID *v14; // rdx
  int v15; // ebx
  COfflineFilesCache *v16; // rcx
  struct IOfflineFilesSyncConflictHandler *v17; // r8
  int v18; // r14d
  int v19; // eax
  __int64 v20; // r9
  enum tagOFFLINEFILES_SYNC_CONFLICT_RESOLVE v21; // esi
  int v22; // r15d
  CUserConflictHandler *v23; // rax
  CUserConflictHandler *v24; // rax
  CUserConflictHandler *v25; // rbx
  struct IOfflineFilesService *v26; // [rsp+50h] [rbp-10h] BYREF
  struct AsyncIOfflineFilesService *v27; // [rsp+58h] [rbp-8h] BYREF
  void *v29; // [rsp+B0h] [rbp+50h] BYREF

  v11 = a2;
  if ( !a3 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_91a48976ead63973ddd357b80bae3284_Traceguids);
    return 2147500035LL;
  }
  v13 = a6;
  if ( (a6 & 0xCFFCC000) != 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        13,
        WPP_91a48976ead63973ddd357b80bae3284_Traceguids,
        a6 & 0xCFFCC000);
    return 2147942487LL;
  }
  v26 = 0;
  v15 = CInterfaceInGITBase::_Unmarshal(
          (COfflineFilesCache *)((char *)this + 32),
          &GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce,
          (void **)&v26);
  if ( v15 >= 0 )
  {
    v16 = (COfflineFilesCache *)a8;
    v29 = 0;
    if ( a8 )
    {
      v15 = CSyncProgressAdapter::CreateInstance(a8, v14, &v29);
      if ( v15 < 0 )
      {
LABEL_58:
        (*(void (__fastcall **)(struct IOfflineFilesService *))(*(_QWORD *)v26 + 16LL))(v26);
        goto LABEL_59;
      }
    }
    v17 = a7;
    if ( a7 )
    {
      ((void (__fastcall *)(struct IOfflineFilesSyncConflictHandler *))a7->lpVtbl->AddRef)(a7);
      v17 = a7;
      goto LABEL_16;
    }
    v20 = v13 & 0xF0000000;
    if ( (v13 & 0xF0000000) != 0 )
    {
      switch ( (_DWORD)v20 )
      {
        case 0x10000000:
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x20) != 0 )
          {
            WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 14, WPP_91a48976ead63973ddd357b80bae3284_Traceguids);
          }
          v21 = OFFLINEFILES_SYNC_CONFLICT_RESOLVE_KEEPLOCAL;
          break;
        case 0x20000000:
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x20) != 0 )
          {
            WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 15, WPP_91a48976ead63973ddd357b80bae3284_Traceguids);
          }
          v21 = OFFLINEFILES_SYNC_CONFLICT_RESOLVE_KEEPREMOTE;
          break;
        case 0x30000000:
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x20) != 0 )
          {
            WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, WPP_91a48976ead63973ddd357b80bae3284_Traceguids);
          }
          v21 = OFFLINEFILES_SYNC_CONFLICT_RESOLVE_KEEPLATEST;
          break;
        default:
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x20) != 0 )
          {
            WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, WPP_91a48976ead63973ddd357b80bae3284_Traceguids, v20);
          }
          v15 = -2147024809;
          goto LABEL_58;
      }
      v15 = -2147024882;
      v22 = -2147024882;
      v23 = (CUserConflictHandler *)operator new(0x10u);
      if ( v23 )
      {
        v24 = CUserConflictHandler::CUserConflictHandler(v23, v21);
        v25 = v24;
        if ( v24 )
        {
          v22 = (**(__int64 (__fastcall ***)(CUserConflictHandler *, GUID *, struct IOfflineFilesSyncConflictHandler **))v24)(
                  v24,
                  &IID_IOfflineFilesSyncConflictHandler,
                  &a7);
          (*(void (__fastcall **)(CUserConflictHandler *))(*(_QWORD *)v25 + 16LL))(v25);
        }
        if ( v22 >= 0 )
        {
          v16 = (COfflineFilesCache *)WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x20) != 0 )
          {
            WPP_SF_d(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              18,
              WPP_91a48976ead63973ddd357b80bae3284_Traceguids,
              (unsigned int)v21);
          }
          v17 = a7;
          v11 = a2;
          goto LABEL_16;
        }
        v15 = v22;
      }
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x20) != 0 )
        WPP_SF_dd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          19,
          WPP_91a48976ead63973ddd357b80bae3284_Traceguids,
          (unsigned int)v21,
          v22);
      goto LABEL_58;
    }
LABEL_16:
    v18 = v13 & 0xFFFFFFF;
    if ( a5 )
    {
      v27 = 0;
      if ( (int)COfflineFilesCache::_CreateAsyncServiceObject(v16, v26, &v27) >= 0 )
      {
        v15 = (*(__int64 (__fastcall **)(struct AsyncIOfflineFilesService *, HWND, const unsigned __int16 **, _QWORD, _DWORD, int, struct IOfflineFilesSyncConflictHandler *, void *, struct _GUID *))(*(_QWORD *)v27 + 72LL))(
                v27,
                v11,
                a3,
                a4,
                0,
                v18,
                a7,
                v29,
                a9);
        (*(void (__fastcall **)(struct AsyncIOfflineFilesService *))(*(_QWORD *)v27 + 16LL))(v27);
LABEL_54:
        if ( v29 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v29 + 16LL))(v29);
        if ( a7 )
          ((void (__fastcall *)(struct IOfflineFilesSyncConflictHandler *))a7->lpVtbl->Release)(a7);
        goto LABEL_58;
      }
      v19 = (*(__int64 (__fastcall **)(struct IOfflineFilesService *, HWND, const unsigned __int16 **, _QWORD, int, int, struct IOfflineFilesSyncConflictHandler *, void *, struct _GUID *))(*(_QWORD *)v26 + 48LL))(
              v26,
              v11,
              a3,
              a4,
              1,
              v18,
              a7,
              v29,
              a9);
    }
    else
    {
      v19 = (*(__int64 (__fastcall **)(struct IOfflineFilesService *, HWND, const unsigned __int16 **, _QWORD, _DWORD, int, struct IOfflineFilesSyncConflictHandler *, void *, struct _GUID *))(*(_QWORD *)v26 + 48LL))(
              v26,
              v11,
              a3,
              a4,
              0,
              v18,
              v17,
              v29,
              a9);
    }
    v15 = v19;
    goto LABEL_54;
  }
LABEL_59:
  result = 0;
  if ( v15 < 0 )
    return (unsigned int)v15;
  return result;
}

```

## disassembly

```asm
0x18000ec70  mov     [rsp-38h+arg_0], rbx
0x18000ec75  mov     [rsp-38h+arg_8], rdx
0x18000ec7a  push    rbp
0x18000ec7b  push    rsi
0x18000ec7c  push    rdi
0x18000ec7d  push    r12
0x18000ec7f  push    r13
0x18000ec81  push    r14
0x18000ec83  push    r15
0x18000ec85  mov     rbp, rsp
0x18000ec88  sub     rsp, 60h
0x18000ec8c  mov     r13d, r9d
0x18000ec8f  mov     r12, r8
0x18000ec92  mov     rdi, rdx
0x18000ec95  test    r8, r8
0x18000ec98  jnz     short loc_18000ECD4
0x18000ec9a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eca1  lea     rdi, WPP_GLOBAL_Control
0x18000eca8  cmp     rcx, rdi
0x18000ecab  jz      short loc_18000ECCA
0x18000ecad  lea     esi, [r8+2]
0x18000ecb1  test    [rcx+1Ch], sil
0x18000ecb5  jz      short loc_18000ECCA
0x18000ecb7  mov     rcx, [rcx+10h]
0x18000ecbb  lea     edx, [rsi+0Ah]
0x18000ecbe  lea     r8, WPP_91a48976ead63973ddd357b80bae3284_Traceguids
0x18000ecc5  call    WPP_SF_
0x18000ecca  mov     eax, 80004003h
0x18000eccf  jmp     loc_18000F06A
0x18000ecd4  mov     r14d, [rbp+arg_28]
0x18000ecd8  mov     r9d, r14d
0x18000ecdb  and     r9d, 0CFFCC000h
0x18000ece2  jz      short loc_18000ED1F
0x18000ece4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eceb  lea     rdi, WPP_GLOBAL_Control
0x18000ecf2  cmp     rcx, rdi
0x18000ecf5  jz      short loc_18000ED15
0x18000ecf7  mov     esi, 2
0x18000ecfc  test    [rcx+1Ch], sil
0x18000ed00  jz      short loc_18000ED15
0x18000ed02  mov     rcx, [rcx+10h]
0x18000ed06  lea     edx, [rsi+0Bh]
0x18000ed09  lea     r8, WPP_91a48976ead63973ddd357b80bae3284_Traceguids
0x18000ed10  call    WPP_SF_d
0x18000ed15  mov     eax, 80070057h
0x18000ed1a  jmp     loc_18000F06A
0x18000ed1f  add     rcx, 20h ; ' '; this
0x18000ed23  mov     [rbp+var_10], 0
0x18000ed2b  lea     r8, [rbp+var_10]; void **
0x18000ed2f  lea     rdx, _GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce; struct _GUID *
0x18000ed36  call    ?_Unmarshal@CInterfaceInGITBase@@IEAAJAEBU_GUID@@PEAPEAX@Z; CInterfaceInGITBase::_Unmarshal(_GUID const &,void * *)
0x18000ed3b  mov     ebx, eax
0x18000ed3d  test    eax, eax
0x18000ed3f  js      loc_18000F063
0x18000ed45  mov     rcx, [rbp+arg_38]; struct IOfflineFilesSyncProgress *
0x18000ed49  mov     [rbp+arg_10], 0
0x18000ed51  test    rcx, rcx
0x18000ed54  jz      short loc_18000ED69
0x18000ed56  lea     r8, [rbp+arg_10]; void **
0x18000ed5a  call    ?CreateInstance@CSyncProgressAdapter@@SAJPEAUIOfflineFilesSyncProgress@@AEBU_GUID@@PEAPEAX@Z; CSyncProgressAdapter::CreateInstance(IOfflineFilesSyncProgress *,_GUID const &,void * *)
0x18000ed5f  mov     ebx, eax
0x18000ed61  test    eax, eax
0x18000ed63  js      loc_18000F053
0x18000ed69  mov     r8, [rbp+arg_30]
0x18000ed6d  test    r8, r8
0x18000ed70  jz      short loc_18000EDEC
0x18000ed72  mov     rax, [r8]
0x18000ed75  mov     rcx, r8
0x18000ed78  mov     rax, [rax+8]
0x18000ed7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed81  mov     r8, [rbp+arg_30]
0x18000ed85  and     r14d, 0FFFFFFFh
0x18000ed8c  cmp     [rbp+arg_20], 0
0x18000ed90  jz      loc_18000EFE7
0x18000ed96  mov     rdx, [rbp+var_10]; struct IOfflineFilesService *
0x18000ed9a  lea     r8, [rbp+var_8]; struct AsyncIOfflineFilesService **
0x18000ed9e  mov     [rbp+var_8], 0
0x18000eda6  call    ?_CreateAsyncServiceObject@COfflineFilesCache@@AEAAJPEAUIOfflineFilesService@@PEAPEAUAsyncIOfflineFilesService@@@Z; COfflineFilesCache::_CreateAsyncServiceObject(IOfflineFilesService *,AsyncIOfflineFilesService * *)
0x18000edab  mov     rdx, [rbp+arg_40]
0x18000edb2  mov     r9d, r13d
0x18000edb5  mov     [rsp+60h+var_20], rdx
0x18000edba  mov     r8, r12
0x18000edbd  mov     rdx, [rbp+arg_10]
0x18000edc1  mov     [rsp+60h+var_28], rdx
0x18000edc6  mov     rdx, [rbp+arg_30]
0x18000edca  mov     [rsp+60h+var_30], rdx
0x18000edcf  mov     rdx, rdi
0x18000edd2  mov     [rsp+60h+var_38], r14d
0x18000edd7  test    eax, eax
0x18000edd9  jns     loc_18000EFBB
0x18000eddf  mov     [rsp+60h+var_40], 1
0x18000ede7  jmp     loc_18000F017
0x18000edec  mov     r9d, r14d
0x18000edef  and     r9d, 0F0000000h
0x18000edf6  jz      short loc_18000ED85
0x18000edf8  cmp     r9d, 10000000h
0x18000edff  jz      loc_18000EEB9
0x18000ee05  cmp     r9d, 20000000h
0x18000ee0c  jz      short loc_18000EE84
0x18000ee0e  cmp     r9d, 30000000h
0x18000ee15  jz      short loc_18000EE4F
0x18000ee17  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee1e  lea     rdi, WPP_GLOBAL_Control
0x18000ee25  cmp     rcx, rdi
0x18000ee28  jz      short loc_18000EE45
0x18000ee2a  test    byte ptr [rcx+1Ch], 20h
0x18000ee2e  jz      short loc_18000EE45
0x18000ee30  mov     rcx, [rcx+10h]
0x18000ee34  lea     r8, WPP_91a48976ead63973ddd357b80bae3284_Traceguids
0x18000ee3b  mov     edx, 11h
0x18000ee40  call    WPP_SF_d
0x18000ee45  mov     ebx, 80070057h
0x18000ee4a  jmp     loc_18000F053
0x18000ee4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee56  lea     rdi, WPP_GLOBAL_Control
0x18000ee5d  cmp     rcx, rdi
0x18000ee60  jz      short loc_18000EE7D
0x18000ee62  test    byte ptr [rcx+1Ch], 20h
0x18000ee66  jz      short loc_18000EE7D
0x18000ee68  mov     rcx, [rcx+10h]
0x18000ee6c  lea     r8, WPP_91a48976ead63973ddd357b80bae3284_Traceguids
0x18000ee73  mov     edx, 10h
0x18000ee78  call    WPP_SF_
0x18000ee7d  mov     esi, 4
0x18000ee82  jmp     short loc_18000EEEC
0x18000ee84  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee8b  lea     rdi, WPP_GLOBAL_Control
0x18000ee92  cmp     rcx, rdi
0x18000ee95  jz      short loc_18000EEB2
0x18000ee97  test    byte ptr [rcx+1Ch], 20h
0x18000ee9b  jz      short loc_18000EEB2
0x18000ee9d  mov     rcx, [rcx+10h]
0x18000eea1  lea     r8, WPP_91a48976ead63973ddd357b80bae3284_Traceguids
0x18000eea8  mov     edx, 0Fh
0x18000eead  call    WPP_SF_
0x18000eeb2  mov     esi, 2
0x18000eeb7  jmp     short loc_18000EEEC
0x18000eeb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eec0  lea     rdi, WPP_GLOBAL_Control
0x18000eec7  cmp     rcx, rdi
0x18000eeca  jz      short loc_18000EEE7
0x18000eecc  test    byte ptr [rcx+1Ch], 20h
0x18000eed0  jz      short loc_18000EEE7
0x18000eed2  mov     rcx, [rcx+10h]
0x18000eed6  lea     r8, WPP_91a48976ead63973ddd357b80bae3284_Traceguids
0x18000eedd  mov     edx, 0Eh
0x18000eee2  call    WPP_SF_
0x18000eee7  mov     esi, 1
0x18000eeec  mov     ebx, 8007000Eh
0x18000eef1  mov     ecx, 10h; Size
0x18000eef6  mov     r15d, ebx
0x18000eef9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000eefe  test    rax, rax
0x18000ef01  jz      short loc_18000EF7F
0x18000ef03  mov     edx, esi; enum tagOFFLINEFILES_SYNC_CONFLICT_RESOLVE
0x18000ef05  mov     rcx, rax; this
0x18000ef08  call    ??0CUserConflictHandler@@AEAA@W4tagOFFLINEFILES_SYNC_CONFLICT_RESOLVE@@@Z; CUserConflictHandler::CUserConflictHandler(tagOFFLINEFILES_SYNC_CONFLICT_RESOLVE)
0x18000ef0d  mov     rbx, rax
0x18000ef10  test    rax, rax
0x18000ef13  jz      short loc_18000EF40
0x18000ef15  mov     rcx, [rax]
0x18000ef18  lea     r8, [rbp+arg_30]
0x18000ef1c  lea     rdx, IID_IOfflineFilesSyncConflictHandler
0x18000ef23  mov     rax, [rcx]
0x18000ef26  mov     rcx, rbx
0x18000ef29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef2e  mov     rcx, [rbx]
0x18000ef31  mov     r15d, eax
0x18000ef34  mov     rax, [rcx+10h]
0x18000ef38  mov     rcx, rbx
0x18000ef3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef40  test    r15d, r15d
0x18000ef43  js      short loc_18000EF7C
0x18000ef45  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef4c  cmp     rcx, rdi
0x18000ef4f  jz      short loc_18000EF6F
0x18000ef51  test    byte ptr [rcx+1Ch], 20h
0x18000ef55  jz      short loc_18000EF6F
0x18000ef57  mov     rcx, [rcx+10h]
0x18000ef5b  lea     r8, WPP_91a48976ead63973ddd357b80bae3284_Traceguids
0x18000ef62  mov     edx, 12h
0x18000ef67  mov     r9d, esi
0x18000ef6a  call    WPP_SF_d
0x18000ef6f  mov     r8, [rbp+arg_30]
0x18000ef73  mov     rdi, [rbp+arg_8]
0x18000ef77  jmp     loc_18000ED85
0x18000ef7c  mov     ebx, r15d
0x18000ef7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef86  cmp     rcx, rdi
0x18000ef89  jz      loc_18000F053
0x18000ef8f  test    byte ptr [rcx+1Ch], 20h
0x18000ef93  jz      loc_18000F053
0x18000ef99  mov     rcx, [rcx+10h]
0x18000ef9d  lea     r8, WPP_91a48976ead63973ddd357b80bae3284_Traceguids
0x18000efa4  mov     edx, 13h
0x18000efa9  mov     [rsp+60h+var_40], r15d
0x18000efae  mov     r9d, esi
0x18000efb1  call    WPP_SF_dd
0x18000efb6  jmp     loc_18000F053
0x18000efbb  mov     rcx, [rbp+var_8]
0x18000efbf  mov     [rsp+60h+var_40], 0
0x18000efc7  mov     rax, [rcx]
0x18000efca  mov     rax, [rax+48h]
0x18000efce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efd3  mov     rcx, [rbp+var_8]
0x18000efd7  mov     ebx, eax
0x18000efd9  mov     rax, [rcx]
0x18000efdc  mov     rax, [rax+10h]
0x18000efe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efe5  jmp     short loc_18000F029
0x18000efe7  mov     rdx, [rbp+arg_40]
0x18000efee  mov     r9d, r13d
0x18000eff1  mov     [rsp+60h+var_20], rdx
0x18000eff6  mov     rdx, [rbp+arg_10]
0x18000effa  mov     [rsp+60h+var_28], rdx
0x18000efff  mov     rdx, rdi
0x18000f002  mov     [rsp+60h+var_30], r8
0x18000f007  mov     r8, r12
0x18000f00a  mov     [rsp+60h+var_38], r14d
0x18000f00f  mov     [rsp+60h+var_40], 0
0x18000f017  mov     rcx, [rbp+var_10]
0x18000f01b  mov     rax, [rcx]
0x18000f01e  mov     rax, [rax+30h]
0x18000f022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f027  mov     ebx, eax
0x18000f029  mov     rcx, [rbp+arg_10]
0x18000f02d  test    rcx, rcx
0x18000f030  jz      short loc_18000F03E
0x18000f032  mov     rax, [rcx]
0x18000f035  mov     rax, [rax+10h]
0x18000f039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f03e  mov     rcx, [rbp+arg_30]
0x18000f042  test    rcx, rcx
0x18000f045  jz      short loc_18000F053
0x18000f047  mov     rax, [rcx]
0x18000f04a  mov     rax, [rax+10h]
0x18000f04e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f053  mov     rcx, [rbp+var_10]
0x18000f057  mov     rax, [rcx]
0x18000f05a  mov     rax, [rax+10h]
0x18000f05e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f063  xor     eax, eax
0x18000f065  test    ebx, ebx
0x18000f067  cmovs   eax, ebx
0x18000f06a  mov     rbx, [rsp+60h+arg_0]
0x18000f072  add     rsp, 60h
0x18000f076  pop     r15
0x18000f078  pop     r14
0x18000f07a  pop     r13
0x18000f07c  pop     r12
0x18000f07e  pop     rdi
0x18000f07f  pop     rsi
0x18000f080  pop     rbp
0x18000f081  retn
```
