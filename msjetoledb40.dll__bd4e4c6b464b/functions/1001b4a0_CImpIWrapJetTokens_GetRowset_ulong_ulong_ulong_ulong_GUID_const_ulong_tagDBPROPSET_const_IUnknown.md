# CImpIWrapJetTokens::GetRowset(ulong,ulong,ulong,ulong,_GUID const &,ulong,tagDBPROPSET * const,IUnknown * *)

- ea: `0x1001b4a0`
- end: `0x1001b6c6`
- name: `?GetRowset@CImpIWrapJetTokens@@UAGJKKKKABU_GUID@@KQAUtagDBPROPSET@@PAPAUIUnknown@@@Z`
- size: `550`
- prototype: `int __stdcall(CImpIWrapJetTokens *__hidden this, unsigned int, unsigned int, unsigned int, unsigned int, const struct _GUID *, unsigned int, struct tagDBPROPSET *const, struct IUnknown **)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops`

## callees

- `0x1000ba90`
- `0x1000e8d0`
- `0x10015c70`
- `0x10015dc0`
- `0x10016040`
- `0x1001b4a0`
- `0x1001c6d0`
- `0x10020410`
- `0x100204c0`
- `0x100207d0`
- `0x100215b0`
- `0x10027cf0`
- `0x10028340`
- `0x1004ce5d`
- `0x1004cea1`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1001b6a2`
- `KERNEL32!LeaveCriticalSection` at `0x1001b6a2`
- `KERNEL32!EnterCriticalSection` at `0x1001b501`
- `KERNEL32!EnterCriticalSection` at `0x1001b501`

## pseudocode

```c
int __stdcall CImpIWrapJetTokens::GetRowset(
        CImpIWrapJetTokens *this,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        const struct _GUID *a6,
        unsigned int a7,
        struct tagDBPROPSET *const a8,
        struct IUnknown **a9)
{
  struct _RTL_CRITICAL_SECTION *v9; // esi
  int v10; // eax
  int v11; // edi
  CDBSession *v12; // eax
  CDBSession *v13; // eax
  CDBSession *v14; // ebx
  CRowset *v15; // eax
  _DWORD v17[4]; // [esp+10h] [ebp-28h] BYREF
  int v18; // [esp+20h] [ebp-18h]
  LPCRITICAL_SECTION v19; // [esp+24h] [ebp-14h]
  CRowset *v20; // [esp+28h] [ebp-10h]
  int v21; // [esp+34h] [ebp-4h]

  memset(&v17[1], 0, 12);
  v17[0] = &CRowsetProperties::`vftable';
  v18 = 0;
  v21 = 0;
  v19 = (LPCRITICAL_SECTION)(*((_DWORD *)this + 2) + 100);
  v9 = v19;
  EnterCriticalSection(v19);
  LOBYTE(v21) = 1;
  v10 = *((_DWORD *)this + 2);
  if ( *(_DWORD *)(v10 + 128) == 1 )
  {
    v11 = -2147467259;
  }
  else
  {
    *(_DWORD *)(v10 + 128) = 1;
    *(_DWORD *)(*((_DWORD *)this + 2) + 96) = a2;
    v12 = (CDBSession *)operator new(0x9Cu);
    v20 = v12;
    if ( v12 && (v13 = CDBSession::CDBSession(v12, 0), (v14 = v13) != 0) )
    {
      v11 = CDBSession::FInit(v13);
      if ( v11 >= 0 )
      {
        *((_DWORD *)v14 + 4) = a3;
        *((_DWORD *)v14 + 5) = a4;
        *((_DWORD *)v14 + 38) = 1;
        (*(void (__thiscall **)(_DWORD, _DWORD))(**((_DWORD **)this + 2) + 4))(
          *(_DWORD *)(**((_DWORD **)this + 2) + 4),
          *((_DWORD *)this + 2));
        *((_DWORD *)v14 + 21) = *((_DWORD *)this + 2);
        v15 = (CRowset *)operator new(0xF0u);
        v20 = v15;
        if ( v15 && (v20 = CRowset::CRowset(v15, 0)) != 0 )
        {
          v11 = CSettableProperties::FInit((CSettableProperties *)v17);
          if ( v11 >= 0 )
          {
            v11 = CRowsetProperties::CopyPropertiesFromStaticTable(
                    (CRowsetProperties *)v17,
                    (const struct DBInfoProps *)&rgDBInfoProps);
            if ( v11 >= 0 )
            {
              v18 = *((_DWORD *)this + 2) + 152;
              v11 = CSettableProperties::SetProperties((CSettableProperties *)v17, a7, a8, 0);
              if ( v11 >= 0 )
              {
                v11 = CRowset::FInit(
                        (int)v20,
                        (int)v14,
                        0,
                        0,
                        0,
                        a5,
                        (struct CSettableProperties *)v17,
                        3,
                        0,
                        0,
                        0,
                        1,
                        0,
                        0,
                        &GUID_NULL);
                if ( v11 >= 0 )
                {
                  v11 = (**(int (__thiscall ***)(_DWORD, CRowset *, const struct _GUID *, struct IUnknown **))v20)(
                          **(_DWORD **)v20,
                          v20,
                          a6,
                          a9);
                  if ( v11 >= 0 )
                    goto LABEL_20;
                }
              }
            }
          }
        }
        else
        {
          v11 = -2147024882;
        }
      }
      CDBSession::~CDBSession(v14);
      operator delete(v14);
    }
    else
    {
      v11 = -2147024882;
    }
  }
  if ( a9 && *a9 )
    operator delete(*a9);
LABEL_20:
  if ( v9 )
    LeaveCriticalSection(v9);
  CSettableProperties::~CSettableProperties((CSettableProperties *)v17);
  return v11;
}

```

## disassembly

```asm
0x1001b4a0  mov     edi, edi
0x1001b4a2  push    ebp
0x1001b4a3  mov     ebp, esp
0x1001b4a5  push    0FFFFFFFFh
0x1001b4a7  push    offset ?GetRowset@CImpIWrapJetTokens@@UAGJKKKKABU_GUID@@KQAUtagDBPROPSET@@PAPAUIUnknown@@@Z_SEH
0x1001b4ac  mov     eax, large fs:0
0x1001b4b2  push    eax
0x1001b4b3  sub     esp, 1Ch
0x1001b4b6  push    ebx
0x1001b4b7  push    esi
0x1001b4b8  push    edi
0x1001b4b9  mov     eax, ___security_cookie
0x1001b4be  xor     eax, ebp
0x1001b4c0  push    eax
0x1001b4c1  lea     eax, [ebp+var_C]
0x1001b4c4  mov     large fs:0, eax
0x1001b4ca  mov     [ebp+var_24], 0
0x1001b4d1  mov     [ebp+var_20], 0
0x1001b4d8  mov     [ebp+var_1C], 0
0x1001b4df  mov     [ebp+var_28], offset ??_7CRowsetProperties@@6B@; const CRowsetProperties::`vftable'
0x1001b4e6  mov     [ebp+var_18], 0
0x1001b4ed  mov     ebx, [ebp+this]
0x1001b4f0  mov     [ebp+var_4], 0
0x1001b4f7  mov     esi, [ebx+8]
0x1001b4fa  add     esi, 64h ; 'd'
0x1001b4fd  push    esi; lpCriticalSection
0x1001b4fe  mov     [ebp+var_14], esi
0x1001b501  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001b507  mov     byte ptr [ebp+var_4], 1
0x1001b50b  mov     eax, [ebx+8]
0x1001b50e  cmp     dword ptr [eax+80h], 1
0x1001b515  jnz     short loc_1001B521
0x1001b517  mov     edi, 80004005h
0x1001b51c  jmp     loc_1001B687
0x1001b521  mov     dword ptr [eax+80h], 1
0x1001b52b  mov     ecx, [ebx+8]
0x1001b52e  mov     eax, [ebp+arg_4]
0x1001b531  push    9Ch; Size
0x1001b536  mov     [ecx+60h], eax
0x1001b539  call    ??2@YAPAXI@Z; operator new(uint)
0x1001b53e  add     esp, 4
0x1001b541  mov     [ebp+var_10], eax
0x1001b544  test    eax, eax
0x1001b546  jz      loc_1001B682
0x1001b54c  push    0; struct IUnknown *
0x1001b54e  mov     ecx, eax; this
0x1001b550  call    ??0CDBSession@@QAE@PAUIUnknown@@@Z; CDBSession::CDBSession(IUnknown *)
0x1001b555  mov     ebx, eax
0x1001b557  test    ebx, ebx
0x1001b559  jz      loc_1001B682
0x1001b55f  mov     ecx, ebx; this
0x1001b561  call    ?FInit@CDBSession@@QAEJXZ; CDBSession::FInit(void)
0x1001b566  mov     edi, eax
0x1001b568  test    edi, edi
0x1001b56a  js      loc_1001B670
0x1001b570  mov     eax, [ebp+arg_8]
0x1001b573  mov     [ebx+10h], eax
0x1001b576  mov     eax, [ebp+arg_C]
0x1001b579  mov     [ebx+14h], eax
0x1001b57c  mov     eax, [ebp+this]
0x1001b57f  mov     dword ptr [ebx+98h], 1
0x1001b589  mov     eax, [eax+8]
0x1001b58c  push    eax
0x1001b58d  mov     ecx, [eax]
0x1001b58f  mov     edi, [ecx+4]
0x1001b592  mov     ecx, edi
0x1001b594  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001b59a  call    edi
0x1001b59c  mov     ecx, [ebp+this]
0x1001b59f  push    0F0h; Size
0x1001b5a4  mov     eax, [ecx+8]
0x1001b5a7  mov     [ebx+54h], eax
0x1001b5aa  call    ??2@YAPAXI@Z; operator new(uint)
0x1001b5af  add     esp, 4
0x1001b5b2  mov     [ebp+var_10], eax
0x1001b5b5  test    eax, eax
0x1001b5b7  jz      loc_1001B66B
0x1001b5bd  push    0; struct IUnknown *
0x1001b5bf  mov     ecx, eax; this
0x1001b5c1  call    ??0CRowset@@QAE@PAUIUnknown@@@Z; CRowset::CRowset(IUnknown *)
0x1001b5c6  mov     [ebp+var_10], eax
0x1001b5c9  test    eax, eax
0x1001b5cb  jz      loc_1001B66B
0x1001b5d1  lea     ecx, [ebp+var_28]; this
0x1001b5d4  call    ?FInit@CSettableProperties@@QAEJXZ; CSettableProperties::FInit(void)
0x1001b5d9  mov     edi, eax
0x1001b5db  test    edi, edi
0x1001b5dd  js      loc_1001B670
0x1001b5e3  push    offset ?rgDBInfoProps@@3QBUDBInfoProps@@B; struct DBInfoProps *
0x1001b5e8  lea     ecx, [ebp+var_28]; this
0x1001b5eb  call    ?CopyPropertiesFromStaticTable@CRowsetProperties@@QAEJPBUDBInfoProps@@@Z; CRowsetProperties::CopyPropertiesFromStaticTable(DBInfoProps const *)
0x1001b5f0  mov     edi, eax
0x1001b5f2  test    edi, edi
0x1001b5f4  js      short loc_1001B670
0x1001b5f6  mov     eax, [ebp+this]
0x1001b5f9  lea     ecx, [ebp+var_28]; this
0x1001b5fc  push    0; struct CDBSession *
0x1001b5fe  push    [ebp+arg_1C]; struct tagDBPROPSET *
0x1001b601  mov     eax, [eax+8]
0x1001b604  push    [ebp+arg_18]; unsigned int
0x1001b607  add     eax, 98h
0x1001b60c  mov     [ebp+var_18], eax
0x1001b60f  call    ?SetProperties@CSettableProperties@@QAEJKPAUtagDBPROPSET@@PAVCDBSession@@@Z; CSettableProperties::SetProperties(ulong,tagDBPROPSET *,CDBSession *)
0x1001b614  mov     edi, eax
0x1001b616  test    edi, edi
0x1001b618  js      short loc_1001B670
0x1001b61a  push    offset _GUID_NULL
0x1001b61f  push    0
0x1001b621  push    0
0x1001b623  mov     ecx, [ebp+var_10]
0x1001b626  lea     eax, [ebp+var_28]
0x1001b629  push    1
0x1001b62b  push    0
0x1001b62d  push    0
0x1001b62f  push    0
0x1001b631  push    3
0x1001b633  push    eax
0x1001b634  push    [ebp+arg_10]
0x1001b637  xor     edx, edx
0x1001b639  push    0
0x1001b63b  push    0
0x1001b63d  push    0
0x1001b63f  push    ebx
0x1001b640  call    ?FInit@CRowset@@QAGJKPAVCDBSession@@PAVCCommand@@PAG2KABVCRowsetProperties@@W4eJetCursorType@@PAXPAKPAVColumnData@@HKQAUtagDBPROPSET@@ABU_GUID@@@Z; CRowset::FInit(ulong,CDBSession *,CCommand *,ushort *,ushort *,ulong,CRowsetProperties const &,eJetCursorType,void *,ulong *,ColumnData *,int,ulong,tagDBPROPSET * const,_GUID const &)
0x1001b645  mov     edi, eax
0x1001b647  test    edi, edi
0x1001b649  js      short loc_1001B670
0x1001b64b  mov     ecx, [ebp+var_10]
0x1001b64e  push    [ebp+arg_20]
0x1001b651  push    [ebp+arg_14]
0x1001b654  mov     eax, [ecx]
0x1001b656  push    ecx
0x1001b657  mov     edi, [eax]
0x1001b659  mov     ecx, edi
0x1001b65b  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001b661  call    edi
0x1001b663  mov     edi, eax
0x1001b665  test    edi, edi
0x1001b667  jns     short loc_1001B69D
0x1001b669  jmp     short loc_1001B670
0x1001b66b  mov     edi, 8007000Eh
0x1001b670  mov     ecx, ebx; this
0x1001b672  call    ??1CDBSession@@QAE@XZ; CDBSession::~CDBSession(void)
0x1001b677  push    ebx; Block
0x1001b678  call    ??3@YAXPAX@Z; operator delete(void *)
0x1001b67d  add     esp, 4
0x1001b680  jmp     short loc_1001B687
0x1001b682  mov     edi, 8007000Eh
0x1001b687  mov     eax, [ebp+arg_20]
0x1001b68a  test    eax, eax
0x1001b68c  jz      short loc_1001B69D
0x1001b68e  mov     eax, [eax]
0x1001b690  test    eax, eax
0x1001b692  jz      short loc_1001B69D
0x1001b694  push    eax; Block
0x1001b695  call    ??3@YAXPAX@Z; operator delete(void *)
0x1001b69a  add     esp, 4
0x1001b69d  test    esi, esi
0x1001b69f  jz      short loc_1001B6A8
0x1001b6a1  push    esi; lpCriticalSection
0x1001b6a2  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001b6a8  lea     ecx, [ebp+var_28]; this
0x1001b6ab  call    ??1CSettableProperties@@UAE@XZ; CSettableProperties::~CSettableProperties(void)
0x1001b6b0  mov     eax, edi
0x1001b6b2  mov     ecx, [ebp+var_C]
0x1001b6b5  mov     large fs:0, ecx
0x1001b6bc  pop     ecx
0x1001b6bd  pop     edi
0x1001b6be  pop     esi
0x1001b6bf  pop     ebx
0x1001b6c0  mov     esp, ebp
0x1001b6c2  pop     ebp
0x1001b6c3  retn    24h ; '$'
0x1004e4d0  lea     ecx, [ebp+var_28]; this
0x1004e4d3  jmp     ??1CTableProperties@@UAE@XZ; CTableProperties::~CTableProperties(void)
0x1004e4d8  lea     ecx, [ebp+var_14]; this
0x1004e4db  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004e4e5  nop
0x1004e4e6  nop
0x1004e4e7  mov     edx, [esp-4+arg_4]
0x1004e4eb  lea     eax, [edx+0Ch]
0x1004e4ee  mov     ecx, [edx-2Ch]
0x1004e4f1  xor     ecx, eax; StackCookie
0x1004e4f3  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004e4f8  mov     eax, offset stru_1004F908
0x1004e4fd  jmp     ___CxxFrameHandler3
```
