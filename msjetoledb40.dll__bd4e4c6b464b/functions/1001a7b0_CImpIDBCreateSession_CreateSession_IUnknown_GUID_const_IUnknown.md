# CImpIDBCreateSession::CreateSession(IUnknown *,_GUID const &,IUnknown * *)

- ea: `0x1001a7b0`
- end: `0x1001a960`
- name: `?CreateSession@CImpIDBCreateSession@@UAGJPAUIUnknown@@ABU_GUID@@PAPAU2@@Z`
- size: `432`
- prototype: `int(CImpIDBCreateSession *__hidden this, struct IUnknown *, const struct _GUID *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops`

## callees

- `0x1000ba90`
- `0x10015c70`
- `0x10015dc0`
- `0x10016690`
- `0x10019070`
- `0x1001a7b0`
- `0x1001c380`
- `0x1001c6d0`
- `0x1004ce5d`
- `0x1004cea1`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1001a944`
- `KERNEL32!LeaveCriticalSection` at `0x1001a944`
- `KERNEL32!EnterCriticalSection` at `0x1001a7f4`
- `KERNEL32!EnterCriticalSection` at `0x1001a7f4`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1001a7e1`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1001a7e1`

## pseudocode

```c
int __stdcall CImpIDBCreateSession::CreateSession(
        CDataSource **this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        struct IUnknown **a4)
{
  CDBSession *v4; // edi
  CImpIDBCreateSession *v5; // ebx
  struct _RTL_CRITICAL_SECTION *v6; // esi
  int v7; // ebx
  CDataSource *v8; // ecx
  CDBSession *v9; // eax
  CDBSession *v10; // eax
  const struct _GUID *v11; // edx
  GUID *v12; // ecx
  bool v13; // cf
  const struct _GUID *v15; // [esp+0h] [ebp-28h]
  int v16; // [esp+4h] [ebp-24h]
  CDBSession *v17; // [esp+14h] [ebp-14h]
  int v18[4]; // [esp+18h] [ebp-10h] BYREF

  v4 = 0;
  v18[0] = 0;
  SetErrorInfo(0, 0);
  v5 = (CImpIDBCreateSession *)this;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this[2] + 100);
  EnterCriticalSection(v6);
  v18[3] = 0;
  if ( a4 )
  {
    *a4 = 0;
    v8 = this[2];
    if ( *((_DWORD *)v8 + 32) )
    {
      if ( *((_DWORD *)v8 + 36) == -1 || *((_DWORD *)v8 + 37) == -1 )
      {
        v7 = CDataSource::OpenSessionAndDatabase(v8, 0, (const struct _GUID *)v6, v18);
        if ( v7 < 0 )
          goto LABEL_23;
        v5 = (CImpIDBCreateSession *)this;
      }
      v9 = (CDBSession *)operator new(0x9Cu);
      if ( !v9 || (v10 = CDBSession::CDBSession(v9, a2), v4 = v10, (v17 = v10) == 0) )
      {
        v7 = -2147024882;
        goto LABEL_23;
      }
      v7 = CDBSession::FInit(
             v10,
             *((struct CDataSource **)v5 + 2),
             *(_DWORD *)(*((_DWORD *)v5 + 2) + 144),
             *(_DWORD *)(*((_DWORD *)v5 + 2) + 148));
      if ( v7 < 0 )
      {
LABEL_20:
        CDBSession::~CDBSession(v4);
        operator delete(v4);
        goto LABEL_23;
      }
      *((_DWORD *)this[2] + 37) = -1;
      *((_DWORD *)this[2] + 36) = -1;
      if ( a2 )
      {
        v11 = a3;
        v12 = &IID_IUnknown;
        v18[0] = 12;
        while ( v12->Data1 == v11->Data1 )
        {
          v12 = (GUID *)((char *)v12 + 4);
          v11 = (const struct _GUID *)((char *)v11 + 4);
          v13 = v18[0] < 4u;
          v18[0] -= 4;
          if ( v13 )
            goto LABEL_16;
        }
        v7 = -2147217886;
      }
      else
      {
LABEL_16:
        (**(void (__thiscall ***)(_DWORD, CDBSession *, const struct _GUID *, struct IUnknown **))v4)(
          **(_DWORD **)v4,
          v4,
          a3,
          a4);
        if ( *a4 )
          goto LABEL_23;
        v4 = v17;
        v7 = -2147467262;
      }
    }
    else
    {
      v7 = -2147418113;
    }
  }
  else
  {
    v7 = -2147024809;
  }
  CExtError::SendHRtoOLEAuto(v7, (__int128 *)&IID_IDBCreateSession, 0, v15, v16);
  if ( v4 )
    goto LABEL_20;
LABEL_23:
  if ( v6 )
    LeaveCriticalSection(v6);
  return v7;
}

```

## disassembly

```asm
0x1001a7b0  mov     edi, edi
0x1001a7b2  push    ebp
0x1001a7b3  mov     ebp, esp
0x1001a7b5  push    0FFFFFFFFh
0x1001a7b7  push    offset ?DropColumn@CImpITableDef@@UAGJPAUtagDBID@@0@Z_SEH
0x1001a7bc  mov     eax, large fs:0
0x1001a7c2  push    eax
0x1001a7c3  sub     esp, 0Ch
0x1001a7c6  push    ebx
0x1001a7c7  push    esi
0x1001a7c8  push    edi; int
0x1001a7c9  mov     eax, ___security_cookie
0x1001a7ce  xor     eax, ebp
0x1001a7d0  push    eax; struct _GUID *
0x1001a7d1  lea     eax, [ebp+var_C]
0x1001a7d4  mov     large fs:0, eax
0x1001a7da  xor     edi, edi
0x1001a7dc  push    edi; perrinfo
0x1001a7dd  push    edi; dwReserved
0x1001a7de  mov     [ebp+var_10], edi
0x1001a7e1  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1001a7e7  mov     ebx, [ebp+this]
0x1001a7ea  mov     esi, [ebx+8]
0x1001a7ed  add     esi, 64h ; 'd'
0x1001a7f0  push    esi; lpCriticalSection
0x1001a7f1  mov     [ebp+var_18], esi
0x1001a7f4  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001a7fa  mov     eax, [ebp+arg_C]
0x1001a7fd  mov     [ebp+var_4], edi
0x1001a800  test    eax, eax
0x1001a802  jnz     short loc_1001A80E
0x1001a804  mov     ebx, 80070057h
0x1001a809  jmp     loc_1001A90B
0x1001a80e  mov     dword ptr [eax], 0
0x1001a814  mov     ecx, [ebx+8]; this
0x1001a817  cmp     dword ptr [ecx+80h], 0
0x1001a81e  jnz     short loc_1001A82A
0x1001a820  mov     ebx, 8000FFFFh
0x1001a825  jmp     loc_1001A90B
0x1001a82a  cmp     dword ptr [ecx+90h], 0FFFFFFFFh
0x1001a831  jz      short loc_1001A83C
0x1001a833  cmp     dword ptr [ecx+94h], 0FFFFFFFFh
0x1001a83a  jnz     short loc_1001A852
0x1001a83c  lea     eax, [ebp+var_10]
0x1001a83f  push    eax; int *
0x1001a840  call    ?OpenSessionAndDatabase@CDataSource@@QAEJAAJ@Z; CDataSource::OpenSessionAndDatabase(long &)
0x1001a845  mov     ebx, eax
0x1001a847  test    ebx, ebx
0x1001a849  js      loc_1001A93F
0x1001a84f  mov     ebx, [ebp+this]
0x1001a852  push    9Ch; Size
0x1001a857  call    ??2@YAPAXI@Z; operator new(uint)
0x1001a85c  add     esp, 4
0x1001a85f  mov     [ebp+var_14], eax
0x1001a862  test    eax, eax
0x1001a864  jz      loc_1001A93A
0x1001a86a  push    [ebp+arg_4]; struct IUnknown *
0x1001a86d  mov     ecx, eax; this
0x1001a86f  call    ??0CDBSession@@QAE@PAUIUnknown@@@Z; CDBSession::CDBSession(IUnknown *)
0x1001a874  mov     edi, eax
0x1001a876  mov     [ebp+var_14], edi
0x1001a879  test    edi, edi
0x1001a87b  jz      loc_1001A93A
0x1001a881  mov     ecx, [ebx+8]
0x1001a884  push    dword ptr [ecx+94h]; unsigned int
0x1001a88a  push    dword ptr [ecx+90h]; unsigned int
0x1001a890  push    ecx; struct CDataSource *
0x1001a891  mov     ecx, edi; this
0x1001a893  call    ?FInit@CDBSession@@QAEJPAVCDataSource@@KK@Z; CDBSession::FInit(CDataSource *,ulong,ulong)
0x1001a898  mov     ebx, eax
0x1001a89a  test    ebx, ebx
0x1001a89c  js      loc_1001A921
0x1001a8a2  cmp     [ebp+arg_4], 0
0x1001a8a6  mov     ecx, [ebp+this]
0x1001a8a9  mov     eax, [ecx+8]
0x1001a8ac  mov     dword ptr [eax+94h], 0FFFFFFFFh
0x1001a8b6  mov     eax, [ecx+8]
0x1001a8b9  mov     dword ptr [eax+90h], 0FFFFFFFFh
0x1001a8c3  jz      short loc_1001A8E6
0x1001a8c5  mov     edx, [ebp+arg_8]
0x1001a8c8  mov     ecx, offset _IID_IUnknown
0x1001a8cd  mov     [ebp+var_10], 0Ch
0x1001a8d4  mov     eax, [ecx]
0x1001a8d6  cmp     eax, [edx]
0x1001a8d8  jnz     short loc_1001A933
0x1001a8da  add     ecx, 4
0x1001a8dd  add     edx, 4
0x1001a8e0  sub     [ebp+var_10], 4
0x1001a8e4  jnb     short loc_1001A8D4
0x1001a8e6  push    [ebp+arg_C]
0x1001a8e9  mov     eax, [edi]
0x1001a8eb  push    [ebp+arg_8]
0x1001a8ee  push    edi
0x1001a8ef  mov     edi, [eax]
0x1001a8f1  mov     ecx, edi
0x1001a8f3  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001a8f9  call    edi
0x1001a8fb  mov     eax, [ebp+arg_C]
0x1001a8fe  cmp     dword ptr [eax], 0
0x1001a901  jnz     short loc_1001A93F
0x1001a903  mov     edi, [ebp+var_14]
0x1001a906  mov     ebx, 80004002h
0x1001a90b  push    0; int
0x1001a90d  push    offset _IID_IDBCreateSession; int
0x1001a912  mov     edx, ebx
0x1001a914  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x1001a919  test    ebx, ebx
0x1001a91b  jns     short loc_1001A93F
0x1001a91d  test    edi, edi
0x1001a91f  jz      short loc_1001A93F
0x1001a921  mov     ecx, edi; this
0x1001a923  call    ??1CDBSession@@QAE@XZ; CDBSession::~CDBSession(void)
0x1001a928  push    edi; Block
0x1001a929  call    ??3@YAXPAX@Z; operator delete(void *)
0x1001a92e  add     esp, 4
0x1001a931  jmp     short loc_1001A93F
0x1001a933  mov     ebx, 80040E22h
0x1001a938  jmp     short loc_1001A90B
0x1001a93a  mov     ebx, 8007000Eh
0x1001a93f  test    esi, esi
0x1001a941  jz      short loc_1001A94A
0x1001a943  push    esi; lpCriticalSection
0x1001a944  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001a94a  mov     eax, ebx
0x1001a94c  mov     ecx, [ebp+var_C]
0x1001a94f  mov     large fs:0, ecx
0x1001a956  pop     ecx
0x1001a957  pop     edi
0x1001a958  pop     esi
0x1001a959  pop     ebx
0x1001a95a  mov     esp, ebp
0x1001a95c  pop     ebp
0x1001a95d  retn    10h
0x1004dd50  lea     ecx, [ebp+var_18]; this
0x1004dd53  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004dd5d  nop
0x1004dd5e  nop
0x1004dd5f  mov     edx, [esp-4+arg_4]
0x1004dd63  lea     eax, [edx+0Ch]
0x1004dd66  mov     ecx, [edx-1Ch]
0x1004dd69  xor     ecx, eax; StackCookie
0x1004dd6b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004dd70  mov     eax, offset stru_1004F354
0x1004dd75  jmp     ___CxxFrameHandler3
```
