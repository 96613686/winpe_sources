# Document::init(void)

- ea: `0x180035500`
- end: `0x180035681`
- name: `?init@Document@@MEAAXXZ`
- size: `385`
- prototype: `void __fastcall(Document *this)`
- caller_count: `0`
- callee_count: `11`
- tags: `reparse_path, registry_config`

## callees

- `0x180019e20`
- `0x1800349ec`
- `0x180034cc8`
- `0x180034e68`
- `0x18003533c`
- `0x180035448`
- `0x180035500`
- `0x180036128`
- `0x1800367cc`
- `0x180036868`
- `0x1800bcbdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800355f7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800355f7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800355dc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800355dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003565c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003565c`

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
0x180035500  mov     [rsp+arg_0], rbx
0x180035505  mov     [rsp+arg_8], rsi
0x18003550a  push    rdi
0x18003550b  sub     rsp, 30h
0x18003550f  mov     edx, [this+94h]
0x180035515  mov     eax, 100h
0x18003551a  mov     [this+154h], eax
0x180035520  or      edx, 32h
0x180035523  mov     [this+150h], eax
0x180035529  mov     rsi, this
0x18003552c  movzx   eax, cs:?_fNormalizeAttributeValuesDefaultValue@Document@@2_NA; bool Document::_fNormalizeAttributeValuesDefaultValue
0x180035533  shl     eax, 0Eh
0x180035536  xor     eax, edx
0x180035538  and     eax, 4000h
0x18003553d  xor     eax, edx
0x18003553f  mov     [this+94h], eax
0x180035545  mov     eax, [this+98h]
0x18003554b  btr     eax, 9
0x18003554f  bts     eax, 7
0x180035553  mov     [this+98h], eax
0x180035559  call    ?classInit@XMLNames@@SAXXZ; XMLNames::classInit(void)
0x18003555e  call    ?classInit@SchemaNames@@SAXXZ; SchemaNames::classInit(void)
0x180035563  lea     rbx, [rsi+0C0h]
0x18003556a  mov     dl, 1; fNeedCreateNameDef
0x18003556c  mov     this, rbx; ppNSMgr
0x18003556f  call    ?New@NamespaceMgr@@SAXPEAPEAV1@_N@Z; NamespaceMgr::New(NamespaceMgr * *,bool)
0x180035574  mov     rdi, [rbx]
0x180035577  mov     edx, 7; dwFlags
0x18003557c  lea     ecx, [rdx+19h]; initialCapacity
0x18003557f  call    ?newStringHashtable@StringHashtable@@SAPEAV1@HK@Z; StringHashtable::newStringHashtable(int,ulong)
0x180035584  lea     this, [rdi+18h]; ppref
0x180035588  mov     rbx, rax
0x18003558b  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180035590  mov     this, rsi; this
0x180035593  mov     [rdi+18h], rbx
0x180035597  call    ?_createDocNode@Document@@IEAAXXZ; Document::_createDocNode(void)
0x18003559c  lea     rdi, [rsi+0A0h]
0x1800355a3  call    ?newApartmentMutex@ApartmentMutex@@SAPEAV1@XZ; ApartmentMutex::newApartmentMutex(void)
0x1800355a8  mov     this, rdi; ppref
0x1800355ab  mov     rbx, rax
0x1800355ae  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800355b3  mov     [rdi], rbx
0x1800355b6  lea     rdi, [rsi+0A8h]
0x1800355bd  call    ?newCSMutex@CSMutex@@SAPEAV1@XZ; CSMutex::newCSMutex(void)
0x1800355c2  mov     this, rdi; ppref
0x1800355c5  mov     rbx, rax
0x1800355c8  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800355cd  xor     r9d, r9d; lpName
0x1800355d0  mov     [rdi], rbx
0x1800355d3  xor     ecx, ecx; lpEventAttributes
0x1800355d5  lea     edx, [r9+1]; bManualReset
0x1800355d9  mov     r8d, edx; bInitialState
0x1800355dc  call    cs:__imp_CreateEventW
0x1800355e3  nop     dword ptr [rax+rax+00h]
0x1800355e8  mov     [rsi+0B0h], rax
0x1800355ef  test    rax, rax
0x1800355f2  jz      short loc_18003565C
0x1800355f4  mov     this, rax; hEvent
0x1800355f7  call    cs:__imp_ResetEvent
0x1800355fe  nop     dword ptr [rax+rax+00h]
0x180035603  xor     edx, edx; dwFlags
0x180035605  mov     dword ptr [rsi+0B8h], 0
0x18003560f  lea     rdi, [rsi+1A0h]
0x180035616  lea     ecx, [rdx+8]; initialCapacity
0x180035619  call    ?newHashtable@Hashtable@@SAPEAV1@IK@Z; Hashtable::newHashtable(uint,ulong)
0x18003561e  mov     this, rdi; ppref
0x180035621  mov     rbx, rax
0x180035624  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180035629  mov     [rdi], rbx
0x18003562c  mov     eax, 1
0x180035631  mov     dword ptr [rsi+148h], 4
0x18003563b  lock xadd cs:?g_docTimestamps@Document@@0JC, eax; long volatile Document::g_docTimestamps
0x180035643  mov     rbx, [rsp+38h+arg_0]
0x180035648  inc     eax
0x18003564a  mov     [rsi+1F0h], eax
0x180035650  mov     rsi, [rsp+38h+arg_8]
0x180035655  add     rsp, 30h
0x180035659  pop     rdi
0x18003565a  retn
0x18003565c  call    cs:__imp_GetLastError
0x180035663  nop     dword ptr [rax+rax+00h]
0x180035668  test    eax, eax
0x18003566a  jle     short loc_180035674
0x18003566c  movzx   eax, ax
0x18003566f  or      eax, 80070000h
0x180035674  xor     r8d, r8d; a1
0x180035677  mov     edx, eax; resid
0x180035679  mov     ecx, eax; hr
0x18003567b  call    ?throwHR@Exception@@SAXJJPEAVString@@000@Z; Exception::throwHR(long,long,String *,String *,String *,String *)
```
