# PROTOCOL_BINDING_TABLE::Contains(_HTTP_REQUEST_V2 *,CONFIG_DATA_INSERT *)

- ea: `0x180057b64`
- end: `0x180057eb3`
- name: `?Contains@PROTOCOL_BINDING_TABLE@@QEAAJPEAU_HTTP_REQUEST_V2@@PEAUCONFIG_DATA_INSERT@@@Z`
- size: `847`
- prototype: `__int64 __fastcall(PROTOCOL_BINDING_TABLE *__hidden this, struct _HTTP_REQUEST_V2 *, struct CONFIG_DATA_INSERT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18005b640`

## callees

- `0x180050f2c`
- `0x180057a98`
- `0x180057b64`
- `0x180058038`
- `0x180058208`
- `0x1800583a8`
- `0x180059288`
- `0x180059300`
- `0x180059394`
- `0x18006101a`
- `0x180061060`

## import_xrefs

- `msvcrt!_wcsupr` at `0x180057c18`
- `msvcrt!_wcsupr` at `0x180057c18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180057e6c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180057e6c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180057c3e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180057c3e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180057e63`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180057e77`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180057e81`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180057e63`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180057e77`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180057e81`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180057c04`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180057c04`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180057dad`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180057dad`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180057bbe`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180057be7`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180057d28`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180057bbe`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180057be7`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180057d28`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180057d41`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180057d41`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180057d5b`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180057d94`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180057dc7`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180057d5b`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180057d94`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180057dc7`

## pseudocode

```c
__int64 __fastcall PROTOCOL_BINDING_TABLE::Contains(
        RTL_SRWLOCK *this,
        struct _HTTP_REQUEST_V2 *a2,
        struct CONFIG_DATA_INSERT *a3)
{
  const unsigned __int16 *pAbsPath; // rdx
  int Key; // ebx
  int v8; // r8d
  struct STATIC_WSTRING_HASH_RECORD *v9; // rax
  PROTOCOL_BINDING_ENTRY *v10; // r10
  SOCKADDR *pLocalAddress; // rdx
  PROTOCOL_BINDING_TABLE *v12; // rcx
  struct IP_LIST_ENTRY *v13; // r15
  const unsigned __int16 *ApplicationPoolFromRequest; // rax
  PROTOCOL_BINDING_TABLE *v15; // rcx
  unsigned int v16; // r9d
  int v17; // r8d
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rax
  struct IP_LIST_ENTRY *IpEntry; // rax
  struct IP_LIST_ENTRY *v22; // r15
  PROTOCOL_BINDING_TABLE *v23; // rcx
  const unsigned __int16 *v24; // rax
  int v26; // [rsp+30h] [rbp-D0h] BYREF
  struct IP_LIST_ENTRY *v27; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v28[32]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v29; // [rsp+60h] [rbp-A0h]
  _BYTE v30[32]; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *String; // [rsp+98h] [rbp-68h]
  _BYTE v32[32]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v33; // [rsp+D0h] [rbp-30h]
  unsigned __int16 v34[4]; // [rsp+E8h] [rbp-18h] BYREF
  int v35; // [rsp+F0h] [rbp-10h]
  unsigned __int16 v36[32]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v37[256]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v38[512]; // [rsp+340h] [rbp+240h] BYREF

  memset_0(v37, 0, sizeof(v37));
  STRU::STRU((STRU *)v32, v37, 0x100u);
  memset_0(v38, 0, sizeof(v38));
  STRU::STRU((STRU *)v30, v38, 0x200u);
  pAbsPath = a2->CookedUrl.pAbsPath;
  *(_QWORD *)v34 = 0;
  v35 = 0;
  v27 = 0;
  Key = STRU::Copy((STRU *)v30, pAbsPath);
  if ( Key >= 0 )
  {
    _wcsupr(String);
    Key = PROTOCOL_BINDING_ENTRY::GetKey(a2, (struct STRU *)v32);
    if ( Key >= 0 )
    {
      AcquireSRWLockShared(this + 134);
      v9 = STATIC_WSTRING_HASH::FindKey((STATIC_WSTRING_HASH *)&this[1], v33, v8);
      v10 = (PROTOCOL_BINDING_ENTRY *)(((unsigned __int64)v9 - 8) & -(__int64)(v9 != 0));
      if ( !v10 )
        goto LABEL_10;
      pLocalAddress = a2->Address.pLocalAddress;
      v26 = 0;
      Key = PROTOCOL_BINDING_ENTRY::QueryIsIpScoped(
              v10,
              pLocalAddress,
              (struct PROTOCOL_BINDING_TABLE *)this,
              &v26,
              &v27);
      if ( Key >= 0 )
      {
        if ( !v26 )
          goto LABEL_10;
        v13 = v27;
        *((_DWORD *)a3 + 6) = 1;
        *(_DWORD *)a3 = *((_DWORD *)v13 + 2);
        Key = PROTOCOL_BINDING_TABLE::GetBindingInfo(v12, a2, a3);
        if ( Key >= 0 )
        {
          ApplicationPoolFromRequest = PROTOCOL_BINDING_TABLE::QueryApplicationPoolFromRequest(
                                         (PROTOCOL_BINDING_TABLE *)this,
                                         *((const unsigned __int16 **)v13 + 6),
                                         String);
          if ( !ApplicationPoolFromRequest )
          {
            *((_DWORD *)a3 + 6) = 2;
            Key = -2147023728;
            goto LABEL_24;
          }
          Key = PROTOCOL_BINDING_TABLE::CheckStatusAndReEvaluateRequest(
                  (PROTOCOL_BINDING_TABLE *)this,
                  ApplicationPoolFromRequest,
                  a3);
          if ( Key < 0 )
            goto LABEL_24;
LABEL_10:
          if ( *((_DWORD *)a3 + 6) == 1 )
            goto LABEL_24;
          memset_0(v36, 0, sizeof(v36));
          STRU::STRU((STRU *)v28, v36, 0x20u);
          Key = STRU::Copy((STRU *)v28, a2->CookedUrl.pFullUrl, a2->CookedUrl.pHost - a2->CookedUrl.pFullUrl);
          if ( Key >= 0 )
          {
            Key = STRU::Append((STRU *)v28, 0x2Au);
            if ( Key >= 0 )
            {
              Key = PROTOCOL_BINDING_TABLE::GetPort(v15, a2, v34, v16, 0);
              if ( Key >= 0 )
              {
                Key = STRU::Append((STRU *)v28, 0x3Au);
                if ( Key >= 0 )
                {
                  Key = STRU::Append((STRU *)v28, v34);
                  if ( Key >= 0 )
                  {
                    Key = STRU::Append((STRU *)v28, 0x2Fu);
                    if ( Key >= 0 )
                    {
                      v18 = (__int64)STATIC_WSTRING_HASH::FindKey((STATIC_WSTRING_HASH *)&this[1], v29, v17);
                      v19 = v18 - 8;
                      v20 = -v18;
                      if ( (v19 & -(__int64)(v20 != 0)) == 0 )
                        goto LABEL_22;
                      IpEntry = PROTOCOL_BINDING_ENTRY::QueryIpEntry(
                                  (PROTOCOL_BINDING_ENTRY *)(v19 & -(__int64)(v20 != 0)),
                                  L"*",
                                  (struct PROTOCOL_BINDING_TABLE *)this);
                      v22 = IpEntry;
                      if ( !IpEntry )
                        goto LABEL_22;
                      *((_DWORD *)a3 + 6) = 1;
                      v23 = (PROTOCOL_BINDING_TABLE *)*((unsigned int *)IpEntry + 2);
                      *(_DWORD *)a3 = (_DWORD)v23;
                      Key = PROTOCOL_BINDING_TABLE::GetBindingInfo(v23, a2, a3);
                      if ( Key >= 0 )
                      {
                        v24 = PROTOCOL_BINDING_TABLE::QueryApplicationPoolFromRequest(
                                (PROTOCOL_BINDING_TABLE *)this,
                                *((const unsigned __int16 **)v22 + 6),
                                String);
                        if ( v24 )
                        {
                          Key = PROTOCOL_BINDING_TABLE::CheckStatusAndReEvaluateRequest(
                                  (PROTOCOL_BINDING_TABLE *)this,
                                  v24,
                                  a3);
                          goto LABEL_23;
                        }
LABEL_22:
                        *((_DWORD *)a3 + 6) = 2;
                        Key = -2147023728;
                      }
                    }
                  }
                }
              }
            }
          }
LABEL_23:
          STRU::~STRU((STRU *)v28);
        }
      }
LABEL_24:
      ReleaseSRWLockShared(this + 134);
    }
  }
  STRU::~STRU((STRU *)v30);
  STRU::~STRU((STRU *)v32);
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x180057b64  mov     [rsp-8+arg_18], rbx
0x180057b69  push    rbp
0x180057b6a  push    rsi
0x180057b6b  push    rdi
0x180057b6c  push    r12
0x180057b6e  push    r13
0x180057b70  push    r14
0x180057b72  push    r15
0x180057b74  lea     rbp, [rsp-650h]
0x180057b7c  sub     rsp, 750h
0x180057b83  mov     rax, cs:__security_cookie
0x180057b8a  xor     rax, rsp
0x180057b8d  mov     [rbp+680h+var_40], rax
0x180057b94  mov     rdi, r8
0x180057b97  mov     r14, rdx
0x180057b9a  mov     rsi, rcx
0x180057b9d  mov     ebx, 200h
0x180057ba2  mov     r8d, ebx; Size
0x180057ba5  lea     rcx, [rbp+680h+var_640]; void *
0x180057ba9  xor     edx, edx; Val
0x180057bab  call    memset_0
0x180057bb0  mov     r8d, 100h
0x180057bb6  lea     rdx, [rbp+680h+var_640]
0x180057bba  lea     rcx, [rbp+680h+var_6D0]
0x180057bbe  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180057bc4  xor     edx, edx; Val
0x180057bc6  lea     rcx, [rbp+680h+var_440]; void *
0x180057bcd  mov     r8d, 400h; Size
0x180057bd3  call    memset_0
0x180057bd8  mov     r8d, ebx
0x180057bdb  lea     rdx, [rbp+680h+var_440]
0x180057be2  lea     rcx, [rsp+780h+var_708]
0x180057be7  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180057bed  mov     rdx, [r14+58h]
0x180057bf1  lea     rcx, [rsp+780h+var_708]
0x180057bf6  xor     eax, eax
0x180057bf8  mov     qword ptr [rbp+680h+var_698], rax
0x180057bfc  mov     [rbp+680h+var_690], eax
0x180057bff  mov     [rsp+780h+var_748], rax
0x180057c04  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180057c0a  mov     ebx, eax
0x180057c0c  test    eax, eax
0x180057c0e  js      loc_180057E72
0x180057c14  mov     rcx, [rbp+680h+String]; String
0x180057c18  call    cs:__imp__wcsupr
0x180057c1e  lea     rdx, [rbp+680h+var_6D0]; struct STRU *
0x180057c22  mov     rcx, r14; struct _HTTP_REQUEST_V2 *
0x180057c25  call    ?GetKey@PROTOCOL_BINDING_ENTRY@@SAJPEAU_HTTP_REQUEST_V2@@PEAVSTRU@@@Z; PROTOCOL_BINDING_ENTRY::GetKey(_HTTP_REQUEST_V2 *,STRU *)
0x180057c2a  mov     ebx, eax
0x180057c2c  test    eax, eax
0x180057c2e  js      loc_180057E72
0x180057c34  lea     r12, [rsi+430h]
0x180057c3b  mov     rcx, r12; SRWLock
0x180057c3e  call    cs:__imp_AcquireSRWLockShared
0x180057c44  mov     rdx, [rbp+680h+var_6B0]; unsigned __int16 *
0x180057c48  lea     rcx, [rsi+8]; this
0x180057c4c  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x180057c51  lea     rcx, [rax-8]
0x180057c55  neg     rax
0x180057c58  sbb     r10, r10
0x180057c5b  and     r10, rcx
0x180057c5e  jz      loc_180057D00
0x180057c64  mov     rdx, [r14+70h]; pSockaddr
0x180057c68  lea     rax, [rsp+780h+var_748]
0x180057c6d  lea     r9, [rsp+780h+var_750]; int *
0x180057c72  mov     [rsp+780h+var_760], rax; struct IP_LIST_ENTRY **
0x180057c77  mov     r8, rsi; struct PROTOCOL_BINDING_TABLE *
0x180057c7a  mov     [rsp+780h+var_750], 0
0x180057c82  mov     rcx, r10; this
0x180057c85  call    ?QueryIsIpScoped@PROTOCOL_BINDING_ENTRY@@QEAAJPEAUsockaddr@@PEAVPROTOCOL_BINDING_TABLE@@PEAHPEAPEAVIP_LIST_ENTRY@@@Z; PROTOCOL_BINDING_ENTRY::QueryIsIpScoped(sockaddr *,PROTOCOL_BINDING_TABLE *,int *,IP_LIST_ENTRY * *)
0x180057c8a  mov     ebx, eax
0x180057c8c  test    eax, eax
0x180057c8e  js      loc_180057E69
0x180057c94  cmp     [rsp+780h+var_750], 0
0x180057c99  jz      short loc_180057D00
0x180057c9b  mov     r15, [rsp+780h+var_748]
0x180057ca0  mov     r8, rdi; struct CONFIG_DATA_INSERT *
0x180057ca3  mov     dword ptr [rdi+18h], 1
0x180057caa  mov     rdx, r14; struct _HTTP_REQUEST_V2 *
0x180057cad  mov     eax, [r15+8]
0x180057cb1  mov     [rdi], eax
0x180057cb3  call    ?GetBindingInfo@PROTOCOL_BINDING_TABLE@@AEAAJPEAU_HTTP_REQUEST_V2@@PEAUCONFIG_DATA_INSERT@@@Z; PROTOCOL_BINDING_TABLE::GetBindingInfo(_HTTP_REQUEST_V2 *,CONFIG_DATA_INSERT *)
0x180057cb8  mov     ebx, eax
0x180057cba  test    eax, eax
0x180057cbc  js      loc_180057E69
0x180057cc2  mov     r8, [rbp+680h+String]; unsigned __int16 *
0x180057cc6  mov     rcx, rsi; this
0x180057cc9  mov     rdx, [r15+30h]; unsigned __int16 *
0x180057ccd  call    ?QueryApplicationPoolFromRequest@PROTOCOL_BINDING_TABLE@@AEAAPEBGPEBG0@Z; PROTOCOL_BINDING_TABLE::QueryApplicationPoolFromRequest(ushort const *,ushort const *)
0x180057cd2  test    rax, rax
0x180057cd5  jnz     short loc_180057CE8
0x180057cd7  mov     dword ptr [rdi+18h], 2
0x180057cde  mov     ebx, 80070490h
0x180057ce3  jmp     loc_180057E69
0x180057ce8  mov     r8, rdi; struct CONFIG_DATA_INSERT *
0x180057ceb  mov     rdx, rax; unsigned __int16 *
0x180057cee  mov     rcx, rsi; this
0x180057cf1  call    ?CheckStatusAndReEvaluateRequest@PROTOCOL_BINDING_TABLE@@AEAAJPEBGPEAUCONFIG_DATA_INSERT@@@Z; PROTOCOL_BINDING_TABLE::CheckStatusAndReEvaluateRequest(ushort const *,CONFIG_DATA_INSERT *)
0x180057cf6  mov     ebx, eax
0x180057cf8  test    eax, eax
0x180057cfa  js      loc_180057E69
0x180057d00  cmp     dword ptr [rdi+18h], 1
0x180057d04  jz      loc_180057E69
0x180057d0a  xor     edx, edx; Val
0x180057d0c  lea     rcx, [rbp+680h+var_680]; void *
0x180057d10  lea     r8d, [rdx+40h]; Size
0x180057d14  call    memset_0
0x180057d19  mov     r8d, 20h ; ' '
0x180057d1f  lea     rdx, [rbp+680h+var_680]
0x180057d23  lea     rcx, [rsp+780h+var_740]
0x180057d28  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180057d2e  mov     rdx, [r14+48h]
0x180057d32  lea     rcx, [rsp+780h+var_740]
0x180057d37  mov     r8, [r14+50h]
0x180057d3b  sub     r8, rdx
0x180057d3e  sar     r8, 1
0x180057d41  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180057d47  lea     rcx, [rsp+780h+var_740]
0x180057d4c  mov     ebx, eax
0x180057d4e  test    eax, eax
0x180057d50  js      loc_180057E63
0x180057d56  mov     edx, 2Ah ; '*'
0x180057d5b  call    cs:__imp_?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x180057d61  mov     ebx, eax
0x180057d63  test    eax, eax
0x180057d65  js      loc_180057E5E
0x180057d6b  lea     r8, [rbp+680h+var_698]; unsigned __int16 *
0x180057d6f  mov     [rsp+780h+var_760], 0; unsigned __int16 **
0x180057d78  mov     rdx, r14; struct _HTTP_REQUEST_V2 *
0x180057d7b  call    ?GetPort@PROTOCOL_BINDING_TABLE@@AEAAJPEAU_HTTP_REQUEST_V2@@PEAGKPEAPEBG@Z; PROTOCOL_BINDING_TABLE::GetPort(_HTTP_REQUEST_V2 *,ushort *,ulong,ushort const * *)
0x180057d80  lea     rcx, [rsp+780h+var_740]
0x180057d85  mov     ebx, eax
0x180057d87  test    eax, eax
0x180057d89  js      loc_180057E63
0x180057d8f  mov     edx, 3Ah ; ':'
0x180057d94  call    cs:__imp_?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x180057d9a  lea     rcx, [rsp+780h+var_740]
0x180057d9f  mov     ebx, eax
0x180057da1  test    eax, eax
0x180057da3  js      loc_180057E63
0x180057da9  lea     rdx, [rbp+680h+var_698]
0x180057dad  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180057db3  lea     rcx, [rsp+780h+var_740]
0x180057db8  mov     ebx, eax
0x180057dba  test    eax, eax
0x180057dbc  js      loc_180057E63
0x180057dc2  mov     edx, 2Fh ; '/'
0x180057dc7  call    cs:__imp_?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x180057dcd  mov     ebx, eax
0x180057dcf  test    eax, eax
0x180057dd1  js      loc_180057E5E
0x180057dd7  mov     rdx, [rsp+780h+var_720]; unsigned __int16 *
0x180057ddc  lea     rcx, [rsi+8]; this
0x180057de0  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x180057de5  lea     rcx, [rax-8]
0x180057de9  neg     rax
0x180057dec  sbb     r9, r9
0x180057def  and     r9, rcx
0x180057df2  jz      short loc_180057E52
0x180057df4  mov     r8, rsi; struct PROTOCOL_BINDING_TABLE *
0x180057df7  lea     rdx, asc_180067B9C; "*"
0x180057dfe  mov     rcx, r9; this
0x180057e01  call    ?QueryIpEntry@PROTOCOL_BINDING_ENTRY@@QEAAPEAVIP_LIST_ENTRY@@PEBGPEAVPROTOCOL_BINDING_TABLE@@@Z; PROTOCOL_BINDING_ENTRY::QueryIpEntry(ushort const *,PROTOCOL_BINDING_TABLE *)
0x180057e06  mov     r15, rax
0x180057e09  test    rax, rax
0x180057e0c  jz      short loc_180057E52
0x180057e0e  mov     dword ptr [rdi+18h], 1
0x180057e15  mov     r8, rdi; struct CONFIG_DATA_INSERT *
0x180057e18  mov     ecx, [rax+8]; this
0x180057e1b  mov     rdx, r14; struct _HTTP_REQUEST_V2 *
0x180057e1e  mov     [rdi], ecx
0x180057e20  call    ?GetBindingInfo@PROTOCOL_BINDING_TABLE@@AEAAJPEAU_HTTP_REQUEST_V2@@PEAUCONFIG_DATA_INSERT@@@Z; PROTOCOL_BINDING_TABLE::GetBindingInfo(_HTTP_REQUEST_V2 *,CONFIG_DATA_INSERT *)
0x180057e25  mov     ebx, eax
0x180057e27  test    eax, eax
0x180057e29  js      short loc_180057E5E
0x180057e2b  mov     r8, [rbp+680h+String]; unsigned __int16 *
0x180057e2f  mov     rcx, rsi; this
0x180057e32  mov     rdx, [r15+30h]; unsigned __int16 *
0x180057e36  call    ?QueryApplicationPoolFromRequest@PROTOCOL_BINDING_TABLE@@AEAAPEBGPEBG0@Z; PROTOCOL_BINDING_TABLE::QueryApplicationPoolFromRequest(ushort const *,ushort const *)
0x180057e3b  test    rax, rax
0x180057e3e  jz      short loc_180057E52
0x180057e40  mov     r8, rdi; struct CONFIG_DATA_INSERT *
0x180057e43  mov     rdx, rax; unsigned __int16 *
0x180057e46  mov     rcx, rsi; this
0x180057e49  call    ?CheckStatusAndReEvaluateRequest@PROTOCOL_BINDING_TABLE@@AEAAJPEBGPEAUCONFIG_DATA_INSERT@@@Z; PROTOCOL_BINDING_TABLE::CheckStatusAndReEvaluateRequest(ushort const *,CONFIG_DATA_INSERT *)
0x180057e4e  mov     ebx, eax
0x180057e50  jmp     short loc_180057E5E
0x180057e52  mov     dword ptr [rdi+18h], 2
0x180057e59  mov     ebx, 80070490h
0x180057e5e  lea     rcx, [rsp+780h+var_740]
0x180057e63  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180057e69  mov     rcx, r12; SRWLock
0x180057e6c  call    cs:__imp_ReleaseSRWLockShared
0x180057e72  lea     rcx, [rsp+780h+var_708]
0x180057e77  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180057e7d  lea     rcx, [rbp+680h+var_6D0]
0x180057e81  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180057e87  mov     eax, ebx
0x180057e89  mov     rcx, [rbp+680h+var_40]
0x180057e90  xor     rcx, rsp; StackCookie
0x180057e93  call    __security_check_cookie
0x180057e98  mov     rbx, [rsp+780h+arg_18]
0x180057ea0  add     rsp, 750h
0x180057ea7  pop     r15
0x180057ea9  pop     r14
0x180057eab  pop     r13
0x180057ead  pop     r12
0x180057eaf  pop     rdi
0x180057eb0  pop     rsi
0x180057eb1  pop     rbp
0x180057eb2  retn
```
