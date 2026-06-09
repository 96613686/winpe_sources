# CDataSource::~CDataSource(void)

- ea: `0x10017960`
- end: `0x10017b43`
- name: `??1CDataSource@@UAE@XZ`
- size: `483`
- prototype: `void __thiscall(CDataSource *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10017930`

## callees

- `0x10017960`
- `0x1001a5e0`
- `0x1001c6d0`
- `0x10020410`
- `0x1004cea1`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x10017b25`
- `KERNEL32!DeleteCriticalSection` at `0x10017b25`
- `KERNEL32!LeaveCriticalSection` at `0x10017b05`
- `KERNEL32!LeaveCriticalSection` at `0x10017b10`
- `KERNEL32!LeaveCriticalSection` at `0x10017b05`
- `KERNEL32!LeaveCriticalSection` at `0x10017b10`
- `KERNEL32!EnterCriticalSection` at `0x10017ac5`
- `KERNEL32!EnterCriticalSection` at `0x10017af3`
- `KERNEL32!EnterCriticalSection` at `0x10017ac5`
- `KERNEL32!EnterCriticalSection` at `0x10017af3`

## pseudocode

```c
void __thiscall CDataSource::~CDataSource(CDataSource *this)
{
  bool v2; // zf
  _DWORD *v3; // eax
  _DWORD *v4; // eax
  _DWORD *v5; // eax
  _DWORD *v6; // eax
  _DWORD *v7; // eax
  _DWORD *v8; // eax
  _DWORD *v9; // eax
  _DWORD *v10; // eax
  _DWORD *v11; // eax
  _DWORD *v12; // eax
  _DWORD *v13; // eax
  _DWORD *v14; // eax
  _DWORD *v15; // eax
  void *v16; // [esp-4h] [ebp-1Ch]
  void *v17; // [esp-4h] [ebp-1Ch]
  void *v18; // [esp-4h] [ebp-1Ch]
  void *v19; // [esp-4h] [ebp-1Ch]
  void *v20; // [esp-4h] [ebp-1Ch]
  void *v21; // [esp-4h] [ebp-1Ch]
  void *v22; // [esp-4h] [ebp-1Ch]
  void *v23; // [esp-4h] [ebp-1Ch]
  void *v24; // [esp-4h] [ebp-1Ch]
  void *v25; // [esp-4h] [ebp-1Ch]
  void *v26; // [esp-4h] [ebp-1Ch]
  void *v27; // [esp-4h] [ebp-1Ch]
  void *v28; // [esp-4h] [ebp-1Ch]

  v2 = *((_DWORD *)this + 4) == 0;
  *(_DWORD *)this = &CDataSource::`vftable';
  if ( !v2 && *((_DWORD *)this + 32) == 1 )
    CDataSource::UtilUninitialize(this);
  v3 = (_DWORD *)*((_DWORD *)this + 3);
  if ( v3 )
  {
    v16 = (void *)*((_DWORD *)this + 3);
    *v3 = &CImpIDBCreateSession::`vftable';
    operator delete(v16);
  }
  v4 = (_DWORD *)*((_DWORD *)this + 4);
  if ( v4 )
  {
    v17 = (void *)*((_DWORD *)this + 4);
    *v4 = &CImpIDBInitialize::`vftable';
    operator delete(v17);
  }
  v5 = (_DWORD *)*((_DWORD *)this + 5);
  if ( v5 )
  {
    v18 = (void *)*((_DWORD *)this + 5);
    *v5 = &CImpIDBProperties::`vftable';
    operator delete(v18);
  }
  v6 = (_DWORD *)*((_DWORD *)this + 6);
  if ( v6 )
  {
    v19 = (void *)*((_DWORD *)this + 6);
    *v6 = &CImpIDBDataSourceAdmin::`vftable';
    operator delete(v19);
  }
  v7 = (_DWORD *)*((_DWORD *)this + 7);
  if ( v7 )
  {
    v20 = (void *)*((_DWORD *)this + 7);
    *v7 = &CImpIDBInfo::`vftable';
    operator delete(v20);
  }
  v8 = (_DWORD *)*((_DWORD *)this + 8);
  if ( v8 )
  {
    v21 = (void *)*((_DWORD *)this + 8);
    *v8 = &CImpIPersist::`vftable';
    operator delete(v21);
  }
  v9 = (_DWORD *)*((_DWORD *)this + 9);
  if ( v9 )
  {
    v22 = (void *)*((_DWORD *)this + 9);
    *v9 = &CImpIJetCompact::`vftable';
    operator delete(v22);
  }
  v10 = (_DWORD *)*((_DWORD *)this + 10);
  if ( v10 )
  {
    v23 = (void *)*((_DWORD *)this + 10);
    *v10 = &CImpIWrapJetTokens::`vftable';
    operator delete(v23);
  }
  v11 = (_DWORD *)*((_DWORD *)this + 11);
  if ( v11 )
  {
    v24 = (void *)*((_DWORD *)this + 11);
    *v11 = &CImpIWrapJetInstance::`vftable';
    operator delete(v24);
  }
  v12 = (_DWORD *)*((_DWORD *)this + 12);
  if ( v12 )
  {
    v25 = (void *)*((_DWORD *)this + 12);
    *v12 = &CImpITrusteeAdmin::`vftable';
    operator delete(v25);
  }
  v13 = (_DWORD *)*((_DWORD *)this + 13);
  if ( v13 )
  {
    v26 = (void *)*((_DWORD *)this + 13);
    *v13 = &CImpITrusteeGroupAdmin::`vftable';
    operator delete(v26);
  }
  v14 = (_DWORD *)*((_DWORD *)this + 14);
  if ( v14 )
  {
    v27 = (void *)*((_DWORD *)this + 14);
    *v14 = &CImpISecurityInfo::`vftable';
    operator delete(v27);
  }
  v15 = (_DWORD *)*((_DWORD *)this + 15);
  if ( v15 )
  {
    v28 = (void *)*((_DWORD *)this + 15);
    *v15 = &CImpIObjectAccessControl::`vftable';
    operator delete(v28);
  }
  EnterCriticalSection(&g_CriticalSection);
  if ( g_pIDataConvert
    && !(*(int (__thiscall **)(_DWORD, LPVOID))(*(_DWORD *)g_pIDataConvert + 8))(
          *(_DWORD *)(*(_DWORD *)g_pIDataConvert + 8),
          g_pIDataConvert) )
  {
    g_pIDataConvert = 0;
  }
  EnterCriticalSection(&g_CriticalSection);
  _InterlockedDecrement(&g_cObj);
  LeaveCriticalSection(&g_CriticalSection);
  LeaveCriticalSection(&g_CriticalSection);
  CSettableProperties::~CSettableProperties((CDataSource *)((char *)this + 152));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 100));
  *((_DWORD *)this + 16) = &CSecuritySession::`vftable';
}

```

## disassembly

```asm
0x10017960  mov     edi, edi
0x10017962  push    ebp
0x10017963  mov     ebp, esp
0x10017965  push    0FFFFFFFFh
0x10017967  push    offset ??1CDataSource@@UAE@XZ_SEH
0x1001796c  mov     eax, large fs:0
0x10017972  push    eax
0x10017973  push    esi
0x10017974  push    edi
0x10017975  mov     eax, ___security_cookie
0x1001797a  xor     eax, ebp
0x1001797c  push    eax
0x1001797d  lea     eax, [ebp+var_C]
0x10017980  mov     large fs:0, eax
0x10017986  mov     edi, ecx
0x10017988  cmp     dword ptr [edi+10h], 0
0x1001798c  mov     dword ptr [edi], offset ??_7CDataSource@@6B@; const CDataSource::`vftable'
0x10017992  jz      short loc_100179A2
0x10017994  cmp     dword ptr [edi+80h], 1
0x1001799b  jnz     short loc_100179A2
0x1001799d  call    ?UtilUninitialize@CDataSource@@QAEJXZ; CDataSource::UtilUninitialize(void)
0x100179a2  mov     eax, [edi+0Ch]
0x100179a5  test    eax, eax
0x100179a7  jz      short loc_100179B8
0x100179a9  push    eax; Block
0x100179aa  mov     dword ptr [eax], offset ??_7CImpIDBCreateSession@@6B@; const CImpIDBCreateSession::`vftable'
0x100179b0  call    ??3@YAXPAX@Z; operator delete(void *)
0x100179b5  add     esp, 4
0x100179b8  mov     eax, [edi+10h]
0x100179bb  test    eax, eax
0x100179bd  jz      short loc_100179CE
0x100179bf  push    eax; Block
0x100179c0  mov     dword ptr [eax], offset ??_7CImpIDBInitialize@@6B@; const CImpIDBInitialize::`vftable'
0x100179c6  call    ??3@YAXPAX@Z; operator delete(void *)
0x100179cb  add     esp, 4
0x100179ce  mov     eax, [edi+14h]
0x100179d1  test    eax, eax
0x100179d3  jz      short loc_100179E4
0x100179d5  push    eax; Block
0x100179d6  mov     dword ptr [eax], offset ??_7CImpIDBProperties@@6B@; const CImpIDBProperties::`vftable'
0x100179dc  call    ??3@YAXPAX@Z; operator delete(void *)
0x100179e1  add     esp, 4
0x100179e4  mov     eax, [edi+18h]
0x100179e7  test    eax, eax
0x100179e9  jz      short loc_100179FA
0x100179eb  push    eax; Block
0x100179ec  mov     dword ptr [eax], offset ??_7CImpIDBDataSourceAdmin@@6B@; const CImpIDBDataSourceAdmin::`vftable'
0x100179f2  call    ??3@YAXPAX@Z; operator delete(void *)
0x100179f7  add     esp, 4
0x100179fa  mov     eax, [edi+1Ch]
0x100179fd  test    eax, eax
0x100179ff  jz      short loc_10017A10
0x10017a01  push    eax; Block
0x10017a02  mov     dword ptr [eax], offset ??_7CImpIDBInfo@@6B@; const CImpIDBInfo::`vftable'
0x10017a08  call    ??3@YAXPAX@Z; operator delete(void *)
0x10017a0d  add     esp, 4
0x10017a10  mov     eax, [edi+20h]
0x10017a13  test    eax, eax
0x10017a15  jz      short loc_10017A26
0x10017a17  push    eax; Block
0x10017a18  mov     dword ptr [eax], offset ??_7CImpIPersist@@6B@; const CImpIPersist::`vftable'
0x10017a1e  call    ??3@YAXPAX@Z; operator delete(void *)
0x10017a23  add     esp, 4
0x10017a26  mov     eax, [edi+24h]
0x10017a29  test    eax, eax
0x10017a2b  jz      short loc_10017A3C
0x10017a2d  push    eax; Block
0x10017a2e  mov     dword ptr [eax], offset ??_7CImpIJetCompact@@6B@; const CImpIJetCompact::`vftable'
0x10017a34  call    ??3@YAXPAX@Z; operator delete(void *)
0x10017a39  add     esp, 4
0x10017a3c  mov     eax, [edi+28h]
0x10017a3f  test    eax, eax
0x10017a41  jz      short loc_10017A52
0x10017a43  push    eax; Block
0x10017a44  mov     dword ptr [eax], offset ??_7CImpIWrapJetTokens@@6B@; const CImpIWrapJetTokens::`vftable'
0x10017a4a  call    ??3@YAXPAX@Z; operator delete(void *)
0x10017a4f  add     esp, 4
0x10017a52  mov     eax, [edi+2Ch]
0x10017a55  test    eax, eax
0x10017a57  jz      short loc_10017A68
0x10017a59  push    eax; Block
0x10017a5a  mov     dword ptr [eax], offset ??_7CImpIWrapJetInstance@@6B@; const CImpIWrapJetInstance::`vftable'
0x10017a60  call    ??3@YAXPAX@Z; operator delete(void *)
0x10017a65  add     esp, 4
0x10017a68  mov     eax, [edi+30h]
0x10017a6b  test    eax, eax
0x10017a6d  jz      short loc_10017A7E
0x10017a6f  push    eax; Block
0x10017a70  mov     dword ptr [eax], offset ??_7CImpITrusteeAdmin@@6B@; const CImpITrusteeAdmin::`vftable'
0x10017a76  call    ??3@YAXPAX@Z; operator delete(void *)
0x10017a7b  add     esp, 4
0x10017a7e  mov     eax, [edi+34h]
0x10017a81  test    eax, eax
0x10017a83  jz      short loc_10017A94
0x10017a85  push    eax; Block
0x10017a86  mov     dword ptr [eax], offset ??_7CImpITrusteeGroupAdmin@@6B@; const CImpITrusteeGroupAdmin::`vftable'
0x10017a8c  call    ??3@YAXPAX@Z; operator delete(void *)
0x10017a91  add     esp, 4
0x10017a94  mov     eax, [edi+38h]
0x10017a97  test    eax, eax
0x10017a99  jz      short loc_10017AAA
0x10017a9b  push    eax; Block
0x10017a9c  mov     dword ptr [eax], offset ??_7CImpISecurityInfo@@6B@; const CImpISecurityInfo::`vftable'
0x10017aa2  call    ??3@YAXPAX@Z; operator delete(void *)
0x10017aa7  add     esp, 4
0x10017aaa  mov     eax, [edi+3Ch]
0x10017aad  test    eax, eax
0x10017aaf  jz      short loc_10017AC0
0x10017ab1  push    eax; Block
0x10017ab2  mov     dword ptr [eax], offset ??_7CImpIObjectAccessControl@@6B@; const CImpIObjectAccessControl::`vftable'
0x10017ab8  call    ??3@YAXPAX@Z; operator delete(void *)
0x10017abd  add     esp, 4
0x10017ac0  push    offset ?g_CriticalSection@@3VCriticalSection@@A; lpCriticalSection
0x10017ac5  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10017acb  mov     ecx, ?g_pIDataConvert@@3PAUIDataConvert@@A; IDataConvert * g_pIDataConvert
0x10017ad1  test    ecx, ecx
0x10017ad3  jz      short loc_10017AEE
0x10017ad5  mov     eax, [ecx]
0x10017ad7  push    ecx
0x10017ad8  mov     esi, [eax+8]
0x10017adb  mov     ecx, esi
0x10017add  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10017ae3  call    esi
0x10017ae5  test    eax, eax
0x10017ae7  jnz     short loc_10017AEE
0x10017ae9  mov     ?g_pIDataConvert@@3PAUIDataConvert@@A, eax; IDataConvert * g_pIDataConvert
0x10017aee  push    offset ?g_CriticalSection@@3VCriticalSection@@A; lpCriticalSection
0x10017af3  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10017af9  lock dec ?g_cObj@@3JA; long g_cObj
0x10017b00  push    offset ?g_CriticalSection@@3VCriticalSection@@A; lpCriticalSection
0x10017b05  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10017b0b  push    offset ?g_CriticalSection@@3VCriticalSection@@A; lpCriticalSection
0x10017b10  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10017b16  lea     ecx, [edi+98h]; this
0x10017b1c  call    ??1CSettableProperties@@UAE@XZ; CSettableProperties::~CSettableProperties(void)
0x10017b21  lea     eax, [edi+64h]
0x10017b24  push    eax; lpCriticalSection
0x10017b25  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x10017b2b  mov     dword ptr [edi+40h], offset ??_7CSecuritySession@@6B@; const CSecuritySession::`vftable'
0x10017b32  mov     ecx, [ebp+var_C]
0x10017b35  mov     large fs:0, ecx
0x10017b3c  pop     ecx
0x10017b3d  pop     edi
0x10017b3e  pop     esi
0x10017b3f  mov     esp, ebp
0x10017b41  pop     ebp
0x10017b42  retn
0x1004e340  nop
0x1004e341  nop
0x1004e342  mov     edx, [esp-4+arg_4]
0x1004e346  lea     eax, [edx+0Ch]
0x1004e349  mov     ecx, [edx-0Ch]
0x1004e34c  xor     ecx, eax; StackCookie
0x1004e34e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004e353  mov     eax, offset stru_1004F608
0x1004e358  jmp     ___CxxFrameHandler3
```
