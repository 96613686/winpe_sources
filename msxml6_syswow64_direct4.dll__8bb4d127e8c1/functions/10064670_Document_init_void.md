# Document::init(void)

- ea: `0x10064670`
- end: `0x10064788`
- name: `?init@Document@@MAEXXZ`
- size: `280`
- prototype: `void __thiscall(Document *this)`
- caller_count: `0`
- callee_count: `11`
- tags: `reparse_path, registry_config`

## callees

- `0x10040bb4`
- `0x10053eca`
- `0x10053f10`
- `0x1005411e`
- `0x1005419e`
- `0x1005660f`
- `0x10064670`
- `0x10064cac`
- `0x100886e5`
- `0x1008afc2`
- `0x100a40f7`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x10064744`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x10064744`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x10064717`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x10064717`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10064724`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10064724`

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
0x10064670  mov     edi, edi
0x10064672  push    ebx
0x10064673  mov     ebx, this
0x10064675  mov     eax, 100h
0x1006467a  push    esi
0x1006467b  push    edi
0x1006467c  mov     edx, [ebx+50h]
0x1006467f  mov     [ebx+0BCh], eax
0x10064685  or      edx, 32h
0x10064688  mov     [ebx+0B8h], eax
0x1006468e  movzx   eax, ?_fNormalizeAttributeValuesDefaultValue@Document@@2_NA; bool Document::_fNormalizeAttributeValuesDefaultValue
0x10064695  shl     eax, 0Eh
0x10064698  xor     eax, edx
0x1006469a  and     eax, 4000h
0x1006469f  xor     eax, edx
0x100646a1  mov     [ebx+50h], eax
0x100646a4  mov     eax, [ebx+54h]
0x100646a7  and     eax, 0FFFFFDFFh
0x100646ac  or      eax, 80h
0x100646b1  mov     [ebx+54h], eax
0x100646b4  call    ?classInit@XMLNames@@SGXXZ; XMLNames::classInit(void)
0x100646b9  call    ?classInit@SchemaNames@@SGXXZ; SchemaNames::classInit(void)
0x100646be  mov     dl, 1; fNeedCreateNameDef
0x100646c0  lea     this, [ebx+6Ch]; ppNSMgr
0x100646c3  call    ?New@NamespaceMgr@@SGXPAPAV1@_N@Z; NamespaceMgr::New(NamespaceMgr * *,bool)
0x100646c8  mov     edi, [ebx+6Ch]
0x100646cb  push    7
0x100646cd  pop     edx; dwFlags
0x100646ce  push    20h ; ' '
0x100646d0  pop     this; initialCapacity
0x100646d1  call    ?newStringHashtable@StringHashtable@@SGPAV1@HK@Z; StringHashtable::newStringHashtable(int,ulong)
0x100646d6  lea     this, [edi+0Ch]; ppref
0x100646d9  mov     esi, eax
0x100646db  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x100646e0  mov     this, ebx; this
0x100646e2  mov     [edi+0Ch], esi
0x100646e5  call    ?_createDocNode@Document@@IAEXXZ; Document::_createDocNode(void)
0x100646ea  call    ?newApartmentMutex@ApartmentMutex@@SGPAV1@XZ; ApartmentMutex::newApartmentMutex(void)
0x100646ef  lea     this, [ebx+5Ch]; ppref
0x100646f2  mov     esi, eax
0x100646f4  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x100646f9  mov     [ebx+5Ch], esi
0x100646fc  call    ?newCSMutex@CSMutex@@SGPAV1@XZ; CSMutex::newCSMutex(void)
0x10064701  lea     this, [ebx+60h]; ppref
0x10064704  mov     esi, eax
0x10064706  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1006470b  mov     [ebx+60h], esi
0x1006470e  xor     eax, eax
0x10064710  xor     esi, esi
0x10064712  inc     eax
0x10064713  push    esi; lpName
0x10064714  push    eax; bInitialState
0x10064715  push    eax; a1
0x10064716  push    esi; lpEventAttributes
0x10064717  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x1006471d  mov     [ebx+64h], eax
0x10064720  test    eax, eax
0x10064722  jnz     short loc_10064743
0x10064724  call    ds:__imp__GetLastError@0; GetLastError()
0x1006472a  test    eax, eax
0x1006472c  jle     short loc_10064736
0x1006472e  movzx   eax, ax
0x10064731  or      eax, 80070000h
0x10064736  sub     esp, 0Ch
0x10064739  mov     edx, eax; resid
0x1006473b  mov     this, eax; hr
0x1006473d  push    esi; a1
0x1006473e  call    ?throwHR@Exception@@SGXJJPAVString@@000@Z; Exception::throwHR(long,long,String *,String *,String *,String *)
0x10064743  push    eax; hEvent
0x10064744  call    ds:__imp__ResetEvent@4; ResetEvent(x)
0x1006474a  push    8
0x1006474c  xor     edx, edx; dwFlags
0x1006474e  mov     [ebx+68h], esi
0x10064751  pop     this; initialCapacity
0x10064752  lea     edi, [ebx+0E8h]
0x10064758  call    ?newHashtable@Hashtable@@SGPAV1@IK@Z; Hashtable::newHashtable(uint,ulong)
0x1006475d  mov     this, edi; ppref
0x1006475f  mov     esi, eax
0x10064761  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10064766  xor     eax, eax
0x10064768  mov     [edi], esi
0x1006476a  mov     dword ptr [ebx+0B0h], 4
0x10064774  inc     eax
0x10064775  lock xadd ?g_docTimestamps@Document@@0JC, eax; long volatile Document::g_docTimestamps
0x1006477d  inc     eax
0x1006477e  pop     edi
0x1006477f  pop     esi
0x10064780  mov     [ebx+120h], eax
0x10064786  pop     ebx
0x10064787  retn
```
