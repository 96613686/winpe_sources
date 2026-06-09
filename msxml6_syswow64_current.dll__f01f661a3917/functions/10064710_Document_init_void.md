# Document::init(void)

- ea: `0x10064710`
- end: `0x10064828`
- name: `?init@Document@@MAEXXZ`
- size: `280`
- prototype: `void __thiscall(Document *this)`
- caller_count: `0`
- callee_count: `11`
- tags: `reparse_path, registry_config`

## callees

- `0x10040c44`
- `0x10053f5a`
- `0x10053fa0`
- `0x100541ae`
- `0x1005422e`
- `0x1005669f`
- `0x10064710`
- `0x10064d4c`
- `0x100886a5`
- `0x1008af82`
- `0x100a3fe7`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x100647e4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x100647e4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x100647b7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x100647b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100647c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100647c4`

## pseudocode

```c
void __thiscall Document::init(Document *this)
{
  unsigned int dwFlags; // edx
  NamespaceMgr *p; // edi
  StringHashtable *v4; // esi
  ApartmentMutex *v5; // esi
  CSMutex *v6; // esi
  HANDLE EventW; // eax
  Hashtable *v8; // esi
  int v9; // [esp-Ch] [ebp-18h]
  struct String *v10; // [esp-8h] [ebp-14h]
  struct String *v11; // [esp-4h] [ebp-10h]
  struct String *v12; // [esp+0h] [ebp-Ch]
  struct String *v13; // [esp+4h] [ebp-8h]

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
    GetLastError();
    Exception::throwHR(0, v9, v10, v11, v12, v13);
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
0x10064710  mov     edi, edi
0x10064712  push    ebx
0x10064713  mov     ebx, this
0x10064715  mov     eax, 100h
0x1006471a  push    esi
0x1006471b  push    edi
0x1006471c  mov     edx, [ebx+50h]
0x1006471f  mov     [ebx+0BCh], eax
0x10064725  or      edx, 32h
0x10064728  mov     [ebx+0B8h], eax
0x1006472e  movzx   eax, ?_fNormalizeAttributeValuesDefaultValue@Document@@2_NA; bool Document::_fNormalizeAttributeValuesDefaultValue
0x10064735  shl     eax, 0Eh
0x10064738  xor     eax, edx
0x1006473a  and     eax, 4000h
0x1006473f  xor     eax, edx
0x10064741  mov     [ebx+50h], eax
0x10064744  mov     eax, [ebx+54h]
0x10064747  and     eax, 0FFFFFDFFh
0x1006474c  or      eax, 80h
0x10064751  mov     [ebx+54h], eax
0x10064754  call    ?classInit@XMLNames@@SGXXZ; XMLNames::classInit(void)
0x10064759  call    ?classInit@SchemaNames@@SGXXZ; SchemaNames::classInit(void)
0x1006475e  mov     dl, 1; fNeedCreateNameDef
0x10064760  lea     this, [ebx+6Ch]; ppNSMgr
0x10064763  call    ?New@NamespaceMgr@@SGXPAPAV1@_N@Z; NamespaceMgr::New(NamespaceMgr * *,bool)
0x10064768  mov     edi, [ebx+6Ch]
0x1006476b  push    7
0x1006476d  pop     edx; dwFlags
0x1006476e  push    20h ; ' '
0x10064770  pop     this; initialCapacity
0x10064771  call    ?newStringHashtable@StringHashtable@@SGPAV1@HK@Z; StringHashtable::newStringHashtable(int,ulong)
0x10064776  lea     this, [edi+0Ch]; ppref
0x10064779  mov     esi, eax
0x1006477b  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10064780  mov     this, ebx; this
0x10064782  mov     [edi+0Ch], esi
0x10064785  call    ?_createDocNode@Document@@IAEXXZ; Document::_createDocNode(void)
0x1006478a  call    ?newApartmentMutex@ApartmentMutex@@SGPAV1@XZ; ApartmentMutex::newApartmentMutex(void)
0x1006478f  lea     this, [ebx+5Ch]; ppref
0x10064792  mov     esi, eax
0x10064794  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10064799  mov     [ebx+5Ch], esi
0x1006479c  call    ?newCSMutex@CSMutex@@SGPAV1@XZ; CSMutex::newCSMutex(void)
0x100647a1  lea     this, [ebx+60h]; ppref
0x100647a4  mov     esi, eax
0x100647a6  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x100647ab  mov     [ebx+60h], esi
0x100647ae  xor     eax, eax
0x100647b0  xor     esi, esi
0x100647b2  inc     eax
0x100647b3  push    esi; lpName
0x100647b4  push    eax; bInitialState
0x100647b5  push    eax; a1
0x100647b6  push    esi; lpEventAttributes
0x100647b7  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x100647bd  mov     [ebx+64h], eax
0x100647c0  test    eax, eax
0x100647c2  jnz     short loc_100647E3
0x100647c4  call    ds:__imp__GetLastError@0; GetLastError()
0x100647ca  test    eax, eax
0x100647cc  jle     short loc_100647D6
0x100647ce  movzx   eax, ax
0x100647d1  or      eax, 80070000h
0x100647d6  sub     esp, 0Ch
0x100647d9  mov     edx, eax; resid
0x100647db  mov     this, eax; hr
0x100647dd  push    esi; a1
0x100647de  call    ?throwHR@Exception@@SGXJJPAVString@@000@Z; Exception::throwHR(long,long,String *,String *,String *,String *)
0x100647e3  push    eax; hEvent
0x100647e4  call    ds:__imp__ResetEvent@4; ResetEvent(x)
0x100647ea  push    8
0x100647ec  xor     edx, edx; dwFlags
0x100647ee  mov     [ebx+68h], esi
0x100647f1  pop     this; initialCapacity
0x100647f2  lea     edi, [ebx+0E8h]
0x100647f8  call    ?newHashtable@Hashtable@@SGPAV1@IK@Z; Hashtable::newHashtable(uint,ulong)
0x100647fd  mov     this, edi; ppref
0x100647ff  mov     esi, eax
0x10064801  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10064806  xor     eax, eax
0x10064808  mov     [edi], esi
0x1006480a  mov     dword ptr [ebx+0B0h], 4
0x10064814  inc     eax
0x10064815  lock xadd ?g_docTimestamps@Document@@0JC, eax; long volatile Document::g_docTimestamps
0x1006481d  inc     eax
0x1006481e  pop     edi
0x1006481f  pop     esi
0x10064820  mov     [ebx+120h], eax
0x10064826  pop     ebx
0x10064827  retn
```
