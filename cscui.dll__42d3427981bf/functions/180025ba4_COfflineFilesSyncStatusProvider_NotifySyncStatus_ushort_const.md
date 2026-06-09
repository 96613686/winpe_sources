# COfflineFilesSyncStatusProvider::_NotifySyncStatus(ushort const *)

- ea: `0x180025ba4`
- end: `0x180025e90`
- name: `?_NotifySyncStatus@COfflineFilesSyncStatusProvider@@AEAAJPEBG@Z`
- size: `748`
- prototype: `__int64 __fastcall(COfflineFilesSyncStatusProvider *__hidden this, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `12`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180021d20`
- `0x180021e00`
- `0x180021eb0`
- `0x180022000`
- `0x180025a30`

## callees

- `0x180002810`
- `0x180005b70`
- `0x180007280`
- `0x18000735c`
- `0x180013dfc`
- `0x180025ba4`
- `0x180025e98`
- `0x180025f4c`
- `0x18003fc84`
- `0x18004c636`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025dda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025dda`
- `ntdll!RtlReleaseResource` at `0x180025e23`
- `ntdll!RtlReleaseResource` at `0x180025e23`
- `ntdll!RtlAcquireResourceShared` at `0x180025c6c`
- `ntdll!RtlAcquireResourceShared` at `0x180025c6c`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180025d1f`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180025d1f`

## pseudocode

```c
__int64 __fastcall COfflineFilesSyncStatusProvider::_NotifySyncStatus(
        COfflineFilesSyncStatusProvider *this,
        const unsigned __int16 *a2)
{
  HRESULT v4; // edi
  const unsigned __int16 *ConstBuffer; // rax
  int Entry; // eax
  void *v7; // r15
  __int64 v8; // rcx
  unsigned __int16 i; // r14
  __int64 v10; // rbx
  unsigned __int16 v12; // [rsp+30h] [rbp-D0h] BYREF
  void *ppv; // [rsp+38h] [rbp-C8h] BYREF
  int v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v16[260]; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+258h] [rbp+158h]
  _WORD *v18; // [rsp+260h] [rbp+160h]
  _WORD *v19; // [rsp+268h] [rbp+168h]
  _WORD *v20; // [rsp+270h] [rbp+170h]
  __int64 v21; // [rsp+278h] [rbp+178h]
  __int64 v22; // [rsp+280h] [rbp+180h]
  LPVOID pv[26]; // [rsp+290h] [rbp+190h] BYREF

  v4 = 0;
  v14 = 0;
  v15 = 0;
  if ( *((_QWORD *)this + 2) )
  {
    v16[0] = 0;
    v21 = 520;
    v19 = v16;
    v20 = v16;
    v22 = 520;
    v18 = v16;
    v17 = 34078720;
    v4 = CPath::Copy((CPath *)v16, a2);
    if ( v4 >= 0 )
    {
      v4 = CPath::StripToUNCServerShare((CPath *)v16);
      if ( v4 >= 0 )
      {
        RtlAcquireResourceShared((PRTL_RESOURCE)((char *)this + 48), 1u);
        if ( *((_QWORD *)this + 5) )
        {
          ppv = 0;
          ConstBuffer = CPath::_GetConstBuffer((CPath *)v16);
          Entry = CSyncItemLog::QueryEntry(
                    *((CSyncItemLog **)this + 5),
                    ConstBuffer,
                    (struct IOfflineFilesSyncItem **)&ppv,
                    0);
          v4 = Entry;
          if ( Entry >= 0 )
          {
            v7 = ppv;
            (*(void (__fastcall **)(void *, int *))(*(_QWORD *)ppv + 128LL))(ppv, &v14);
            (*(void (__fastcall **)(void *, __int64 *))(*(_QWORD *)v7 + 104LL))(v7, &v15);
            ppv = 0;
            v4 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
            if ( v4 >= 0 )
            {
              v4 = COfflineFilesSyncStatusProvider::_SetSyncStatus(v8, ppv, &xmmword_180069580, 4, v14, &v15);
              if ( v4 >= 0 )
              {
                COfflineFilesSyncStatusProvider::_NotifySyncStatusToSyncIntegrationManager(
                  this,
                  a2,
                  (struct IPropertyStore *)ppv);
                memset_0(pv, 0, sizeof(pv));
                v12 = 0;
                v4 = (*(__int64 (__fastcall **)(void *, LPVOID *, unsigned __int16 *))(*(_QWORD *)v7 + 168LL))(
                       v7,
                       pv,
                       &v12);
                if ( v4 >= 0 )
                {
                  for ( i = 0; i < v12; pv[v10] = 0 )
                  {
                    v10 = i;
                    COfflineFilesSyncStatusProvider::_NotifySyncStatusToSyncIntegrationManager(
                      this,
                      (const unsigned __int16 *)pv[i],
                      (struct IPropertyStore *)ppv);
                    CoTaskMemFree(pv[i++]);
                  }
                }
              }
              (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
            }
            (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 16LL))(v7);
          }
          else if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              13,
              (unsigned int)WPP_bd52cef1c0fb35253f437009e409cb02_Traceguids,
              (_DWORD)a2,
              Entry);
          }
        }
        RtlReleaseResource((PRTL_RESOURCE)((char *)this + 48));
      }
    }
    CPath::~CPath((CPath *)v16);
  }
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      (unsigned int)WPP_bd52cef1c0fb35253f437009e409cb02_Traceguids,
      (_DWORD)a2,
      v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180025ba4  mov     [rsp-8+arg_10], rbx
0x180025ba9  push    rbp
0x180025baa  push    rsi
0x180025bab  push    rdi
0x180025bac  push    r12
0x180025bae  push    r13
0x180025bb0  push    r14
0x180025bb2  push    r15
0x180025bb4  lea     rbp, [rsp-270h]
0x180025bbc  sub     rsp, 370h
0x180025bc3  mov     rax, cs:__security_cookie
0x180025bca  xor     rax, rsp
0x180025bcd  mov     [rbp+2A0h+var_40], rax
0x180025bd4  xor     ebx, ebx
0x180025bd6  lea     r14, WPP_GLOBAL_Control
0x180025bdd  mov     r12, rdx
0x180025be0  mov     rsi, rcx
0x180025be3  mov     edi, ebx
0x180025be5  mov     [rsp+3A0h+var_360], ebx
0x180025be9  mov     [rsp+3A0h+var_358], rbx
0x180025bee  cmp     [rcx+10h], rbx
0x180025bf2  jz      loc_180025E33
0x180025bf8  mov     ecx, 208h
0x180025bfd  mov     [rsp+3A0h+var_350], bx
0x180025c02  lea     rax, [rsp+3A0h+var_350]
0x180025c07  mov     [rbp+2A0h+var_128], rcx
0x180025c0e  mov     [rbp+2A0h+var_138], rax
0x180025c15  lea     rax, [rsp+3A0h+var_350]
0x180025c1a  mov     [rbp+2A0h+var_130], rax
0x180025c21  lea     rax, [rsp+3A0h+var_350]
0x180025c26  mov     [rbp+2A0h+var_120], rcx
0x180025c2d  lea     rcx, [rsp+3A0h+var_350]; this
0x180025c32  mov     [rbp+2A0h+var_140], rax
0x180025c39  mov     [rbp+2A0h+var_148], 2080000h
0x180025c43  call    ?Copy@CPath@@QEAAJPEBG@Z; CPath::Copy(ushort const *)
0x180025c48  mov     edi, eax
0x180025c4a  test    eax, eax
0x180025c4c  js      loc_180025E29
0x180025c52  lea     rcx, [rsp+3A0h+var_350]; this
0x180025c57  call    ?StripToUNCServerShare@CPath@@QEAAJXZ; CPath::StripToUNCServerShare(void)
0x180025c5c  mov     edi, eax
0x180025c5e  test    eax, eax
0x180025c60  js      loc_180025E29
0x180025c66  mov     dl, 1; Wait
0x180025c68  lea     rcx, [rsi+30h]; Resource
0x180025c6c  call    cs:__imp_RtlAcquireResourceShared
0x180025c72  cmp     [rsi+28h], rbx
0x180025c76  jz      loc_180025E1F
0x180025c7c  lea     rcx, [rsp+3A0h+var_350]; this
0x180025c81  mov     [rsp+3A0h+ppv], rbx
0x180025c86  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x180025c8b  mov     rcx, [rsi+28h]; this
0x180025c8f  lea     r8, [rsp+3A0h+ppv]; struct IOfflineFilesSyncItem **
0x180025c94  mov     rdx, rax; unsigned __int16 *
0x180025c97  xor     r9d, r9d; unsigned __int16 *
0x180025c9a  call    ?QueryEntry@CSyncItemLog@@QEAAJPEBGPEAPEAUIOfflineFilesSyncItem@@0@Z; CSyncItemLog::QueryEntry(ushort const *,IOfflineFilesSyncItem * *,ushort const *)
0x180025c9f  mov     edi, eax
0x180025ca1  test    eax, eax
0x180025ca3  jns     short loc_180025CDE
0x180025ca5  mov     rcx, cs:WPP_GLOBAL_Control
0x180025cac  cmp     rcx, r14
0x180025caf  jz      loc_180025E1F
0x180025cb5  test    byte ptr [rcx+1Ch], 2
0x180025cb9  jz      loc_180025E1F
0x180025cbf  mov     rcx, [rcx+10h]
0x180025cc3  lea     edx, [rbx+0Dh]
0x180025cc6  mov     r9, r12
0x180025cc9  mov     [rsp+3A0h+var_380], eax
0x180025ccd  lea     r8, WPP_bd52cef1c0fb35253f437009e409cb02_Traceguids
0x180025cd4  call    WPP_SF_Sd
0x180025cd9  jmp     loc_180025E1F
0x180025cde  mov     r15, [rsp+3A0h+ppv]
0x180025ce3  lea     rdx, [rsp+3A0h+var_360]
0x180025ce8  mov     rcx, r15
0x180025ceb  mov     rax, [r15]
0x180025cee  mov     rax, [rax+80h]
0x180025cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025cfa  mov     rax, [r15]
0x180025cfd  lea     rdx, [rsp+3A0h+var_358]
0x180025d02  mov     rcx, r15
0x180025d05  mov     rax, [rax+68h]
0x180025d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d0e  lea     rdx, [rsp+3A0h+ppv]; ppv
0x180025d13  mov     [rsp+3A0h+ppv], rbx
0x180025d18  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180025d1f  call    cs:__imp_PSCreateMemoryPropertyStore
0x180025d25  mov     edi, eax
0x180025d27  test    eax, eax
0x180025d29  js      loc_180025E10
0x180025d2f  mov     rdx, [rsp+3A0h+ppv]
0x180025d34  lea     rax, [rsp+3A0h+var_358]
0x180025d39  mov     [rsp+3A0h+var_378], rax
0x180025d3e  lea     r8, xmmword_180069580
0x180025d45  mov     eax, [rsp+3A0h+var_360]
0x180025d49  mov     r9d, 4
0x180025d4f  mov     [rsp+3A0h+var_380], eax
0x180025d53  call    ?_SetSyncStatus@COfflineFilesSyncStatusProvider@@AEAAJPEAUIPropertyStore@@PEBU_tagpropertykey@@IW4_SYNC_STATUS_TYPE@@PEAU_FILETIME@@@Z; COfflineFilesSyncStatusProvider::_SetSyncStatus(IPropertyStore *,_tagpropertykey const *,uint,_SYNC_STATUS_TYPE,_FILETIME *)
0x180025d58  mov     edi, eax
0x180025d5a  test    eax, eax
0x180025d5c  js      loc_180025DFF
0x180025d62  mov     r8, [rsp+3A0h+ppv]; struct IPropertyStore *
0x180025d67  mov     rdx, r12; unsigned __int16 *
0x180025d6a  mov     rcx, rsi; this
0x180025d6d  call    ?_NotifySyncStatusToSyncIntegrationManager@COfflineFilesSyncStatusProvider@@AEAAJPEBGPEAUIPropertyStore@@@Z; COfflineFilesSyncStatusProvider::_NotifySyncStatusToSyncIntegrationManager(ushort const *,IPropertyStore *)
0x180025d72  xor     edx, edx; Val
0x180025d74  lea     rcx, [rbp+2A0h+pv]; void *
0x180025d7b  mov     r8d, 0D0h; Size
0x180025d81  call    memset_0
0x180025d86  mov     [rsp+3A0h+var_370], bx
0x180025d8b  lea     r8, [rsp+3A0h+var_370]
0x180025d90  mov     rax, [r15]
0x180025d93  lea     rdx, [rbp+2A0h+pv]
0x180025d9a  mov     rcx, r15
0x180025d9d  mov     rax, [rax+0A8h]
0x180025da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025da9  mov     edi, eax
0x180025dab  test    eax, eax
0x180025dad  js      short loc_180025DFF
0x180025daf  mov     r14d, ebx
0x180025db2  cmp     bx, [rsp+3A0h+var_370]
0x180025db7  jnb     short loc_180025DF8
0x180025db9  mov     r8, [rsp+3A0h+ppv]; struct IPropertyStore *
0x180025dbe  mov     rcx, rsi; this
0x180025dc1  movzx   ebx, r14w
0x180025dc5  mov     rdx, [rbp+rbx*8+2A0h+pv]; unsigned __int16 *
0x180025dcd  call    ?_NotifySyncStatusToSyncIntegrationManager@COfflineFilesSyncStatusProvider@@AEAAJPEBGPEAUIPropertyStore@@@Z; COfflineFilesSyncStatusProvider::_NotifySyncStatusToSyncIntegrationManager(ushort const *,IPropertyStore *)
0x180025dd2  mov     rcx, [rbp+rbx*8+2A0h+pv]; pv
0x180025dda  call    cs:__imp_CoTaskMemFree
0x180025de0  inc     r14w
0x180025de4  mov     [rbp+rbx*8+2A0h+pv], 0
0x180025df0  cmp     r14w, [rsp+3A0h+var_370]
0x180025df6  jb      short loc_180025DB9
0x180025df8  lea     r14, WPP_GLOBAL_Control
0x180025dff  mov     rcx, [rsp+3A0h+ppv]
0x180025e04  mov     rax, [rcx]
0x180025e07  mov     rax, [rax+10h]
0x180025e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e10  mov     rax, [r15]
0x180025e13  mov     rcx, r15
0x180025e16  mov     rax, [rax+10h]
0x180025e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e1f  lea     rcx, [rsi+30h]; Resource
0x180025e23  call    cs:__imp_RtlReleaseResource
0x180025e29  lea     rcx, [rsp+3A0h+var_350]; this
0x180025e2e  call    ??1CPath@@QEAA@XZ; CPath::~CPath(void)
0x180025e33  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e3a  cmp     rcx, r14
0x180025e3d  jz      short loc_180025E64
0x180025e3f  test    dword ptr [rcx+1Ch], 4000000h
0x180025e46  jz      short loc_180025E64
0x180025e48  mov     rcx, [rcx+10h]
0x180025e4c  lea     r8, WPP_bd52cef1c0fb35253f437009e409cb02_Traceguids
0x180025e53  mov     edx, 0Eh
0x180025e58  mov     [rsp+3A0h+var_380], edi
0x180025e5c  mov     r9, r12
0x180025e5f  call    WPP_SF_Sd
0x180025e64  mov     eax, edi
0x180025e66  mov     rcx, [rbp+2A0h+var_40]
0x180025e6d  xor     rcx, rsp; StackCookie
0x180025e70  call    __security_check_cookie
0x180025e75  mov     rbx, [rsp+3A0h+arg_10]
0x180025e7d  add     rsp, 370h
0x180025e84  pop     r15
0x180025e86  pop     r14
0x180025e88  pop     r13
0x180025e8a  pop     r12
0x180025e8c  pop     rdi
0x180025e8d  pop     rsi
0x180025e8e  pop     rbp
0x180025e8f  retn
```
