# Document::init(void)

- ea: `0x1800398d0`
- end: `0x180039a3e`
- name: `?init@Document@@MEAAXXZ`
- size: `366`
- prototype: `void __fastcall(Document *this)`
- caller_count: `0`
- callee_count: `11`
- tags: `reparse_path, registry_config`

## callees

- `0x18000d7d0`
- `0x180038ca8`
- `0x18003933c`
- `0x1800393d0`
- `0x1800398d0`
- `0x180039b18`
- `0x180039c18`
- `0x180039cc0`
- `0x18003a0c0`
- `0x18003a284`
- `0x1800bb62c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800399c1`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800399c1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800399ac`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800399ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039a1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039a1f`

## pseudocode

```c
void __fastcall Document::init(Document *this)
{
  unsigned int dwFlags; // edx
  NamespaceMgr *p; // rdi
  StringHashtable *v4; // rbx
  ApartmentMutex *v5; // rbx
  CSMutex *v6; // rbx
  HANDLE EventW; // rax
  Hashtable *v8; // rbx
  signed int LastError; // eax
  String *v10; // r9
  String *v11; // [rsp+20h] [rbp-18h]
  String *v12; // [rsp+28h] [rbp-10h]

  dwFlags = this->_dwFlags;
  this->_ulMaxElementDepthLimitInSecure = 256;
  this->_ulMaxElementDepth = 256;
  this->_dwFlags = (dwFlags | 0x32)
                 ^ (((unsigned __int16)dwFlags | 0x32)
                  ^ (Document::_fNormalizeAttributeValuesDefaultValue << 14))
                 & 0x4000;
  *((_DWORD *)&this->0 + 1) = *((_DWORD *)&this->0 + 1) & 0xFFFFFD7F | 0x80;
  XMLNames::classInit();
  SchemaNames::classInit();
  NamespaceMgr::New(&this->_pNamespaceMgr._p, 1);
  p = this->_pNamespaceMgr._p;
  v4 = StringHashtable::newStringHashtable(32, 7u);
  release(&p->_pAtoms._p);
  p->_pAtoms._p = v4;
  Document::_createDocNode(this);
  v5 = ApartmentMutex::newApartmentMutex();
  release(&this->_pMutex._p);
  this->_pMutex._p = v5;
  v6 = CSMutex::newCSMutex();
  release(&this->_pMutexLoad._p);
  this->_pMutexLoad._p = v6;
  EventW = CreateEventW(0, 1, 1, 0);
  this->_hEventLoad = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Exception::throwHR(LastError, LastError, 0, v10, v11, v12);
  }
  ResetEvent(EventW);
  this->_dwLoadThreadId = 0;
  v8 = Hashtable::newHashtable(8u, 0);
  release(&this->_pLockedElements._p);
  this->_pLockedElements._p = v8;
  this->_dwLoadState = 4;
  this->_timestamp = _InterlockedIncrement(&Document::g_docTimestamps);
}

```

## disassembly

```asm
0x1800398d0  mov     [rsp+arg_0], rbx
0x1800398d5  mov     [rsp+arg_8], rsi
0x1800398da  push    rdi
0x1800398db  sub     rsp, 30h
0x1800398df  mov     edx, [this+94h]
0x1800398e5  mov     eax, 100h
0x1800398ea  mov     [this+154h], eax
0x1800398f0  or      edx, 32h
0x1800398f3  mov     [this+150h], eax
0x1800398f9  mov     rsi, this
0x1800398fc  movzx   eax, cs:?_fNormalizeAttributeValuesDefaultValue@Document@@2_NA; bool Document::_fNormalizeAttributeValuesDefaultValue
0x180039903  shl     eax, 0Eh
0x180039906  xor     eax, edx
0x180039908  and     eax, 4000h
0x18003990d  xor     eax, edx
0x18003990f  mov     [this+94h], eax
0x180039915  mov     eax, [this+98h]
0x18003991b  btr     eax, 9
0x18003991f  bts     eax, 7
0x180039923  mov     [this+98h], eax
0x180039929  call    ?classInit@XMLNames@@SAXXZ; XMLNames::classInit(void)
0x18003992e  call    ?classInit@SchemaNames@@SAXXZ; SchemaNames::classInit(void)
0x180039933  lea     rbx, [rsi+0C0h]
0x18003993a  mov     dl, 1; fNeedCreateNameDef
0x18003993c  mov     this, rbx; ppNSMgr
0x18003993f  call    ?New@NamespaceMgr@@SAXPEAPEAV1@_N@Z; NamespaceMgr::New(NamespaceMgr * *,bool)
0x180039944  mov     rdi, [rbx]
0x180039947  mov     edx, 7; dwFlags
0x18003994c  lea     ecx, [rdx+19h]; initialCapacity
0x18003994f  call    ?newStringHashtable@StringHashtable@@SAPEAV1@HK@Z; StringHashtable::newStringHashtable(int,ulong)
0x180039954  lea     this, [rdi+18h]; ppref
0x180039958  mov     rbx, rax
0x18003995b  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180039960  mov     this, rsi; this
0x180039963  mov     [rdi+18h], rbx
0x180039967  call    ?_createDocNode@Document@@IEAAXXZ; Document::_createDocNode(void)
0x18003996c  lea     rdi, [rsi+0A0h]
0x180039973  call    ?newApartmentMutex@ApartmentMutex@@SAPEAV1@XZ; ApartmentMutex::newApartmentMutex(void)
0x180039978  mov     this, rdi; ppref
0x18003997b  mov     rbx, rax
0x18003997e  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180039983  mov     [rdi], rbx
0x180039986  lea     rdi, [rsi+0A8h]
0x18003998d  call    ?newCSMutex@CSMutex@@SAPEAV1@XZ; CSMutex::newCSMutex(void)
0x180039992  mov     this, rdi; ppref
0x180039995  mov     rbx, rax
0x180039998  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x18003999d  xor     r9d, r9d; lpName
0x1800399a0  mov     [rdi], rbx
0x1800399a3  xor     ecx, ecx; lpEventAttributes
0x1800399a5  lea     edx, [r9+1]; bManualReset
0x1800399a9  mov     r8d, edx; bInitialState
0x1800399ac  call    cs:__imp_CreateEventW
0x1800399b2  mov     [rsi+0B0h], rax
0x1800399b9  test    rax, rax
0x1800399bc  jz      short loc_180039A1F
0x1800399be  mov     this, rax; hEvent
0x1800399c1  call    cs:__imp_ResetEvent
0x1800399c7  xor     edx, edx; dwFlags
0x1800399c9  mov     dword ptr [rsi+0B8h], 0
0x1800399d3  lea     rdi, [rsi+1A0h]
0x1800399da  lea     ecx, [rdx+8]; initialCapacity
0x1800399dd  call    ?newHashtable@Hashtable@@SAPEAV1@IK@Z; Hashtable::newHashtable(uint,ulong)
0x1800399e2  mov     this, rdi; ppref
0x1800399e5  mov     rbx, rax
0x1800399e8  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800399ed  mov     [rdi], rbx
0x1800399f0  mov     eax, 1
0x1800399f5  mov     dword ptr [rsi+148h], 4
0x1800399ff  lock xadd cs:?g_docTimestamps@Document@@0JC, eax; long volatile Document::g_docTimestamps
0x180039a07  mov     rbx, [rsp+38h+arg_0]
0x180039a0c  inc     eax
0x180039a0e  mov     [rsi+1F0h], eax
0x180039a14  mov     rsi, [rsp+38h+arg_8]
0x180039a19  add     rsp, 30h
0x180039a1d  pop     rdi
0x180039a1e  retn
0x180039a1f  call    cs:__imp_GetLastError
0x180039a25  test    eax, eax
0x180039a27  jle     short loc_180039A31
0x180039a29  movzx   eax, ax
0x180039a2c  or      eax, 80070000h
0x180039a31  xor     r8d, r8d; a1
0x180039a34  mov     edx, eax; resid
0x180039a36  mov     ecx, eax; hr
0x180039a38  call    ?throwHR@Exception@@SAXJJPEAVString@@000@Z; Exception::throwHR(long,long,String *,String *,String *,String *)
```
