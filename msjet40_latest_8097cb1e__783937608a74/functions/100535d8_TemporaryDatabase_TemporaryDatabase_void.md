# TemporaryDatabase::~TemporaryDatabase(void)

- ea: `0x100535d8`
- end: `0x10053682`
- name: `??1TemporaryDatabase@@EAE@XZ`
- size: `170`
- prototype: `void __usercall(TemporaryDatabase *__hidden this@<ecx>)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x100532a0`

## callees

- `0x100532cd`
- `0x100535d8`
- `0x10057673`
- `0x100774c3`
- `0x10123110`
- `0x10123ca8`
- `0x10124048`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10053665`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10053665`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10053645`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10053645`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1005360c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1005360c`

## pseudocode

```c
void __thiscall TemporaryDatabase::~TemporaryDatabase(TemporaryDatabase *this)
{
  unsigned int v2; // edi
  PageDesc *PD; // eax
  PageDesc *v4; // ebx
  unsigned int v5; // [esp+10h] [ebp-10h]

  *(_DWORD *)this = &TemporaryDatabase::`vftable';
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  v2 = 0;
  v5 = 44 * *((_DWORD *)this + 36);
  if ( v5 )
  {
    do
    {
      PD = Database::GetPD(this, v2);
      v4 = PD;
      if ( PD )
      {
        PageDesc::RemovePageFromCache(PD);
        *((_BYTE *)v4 + 88) &= ~8u;
      }
      ++v2;
    }
    while ( v2 < v5 );
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  operator delete[](*((void **)this + 247));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1012));
  Database::~Database(this);
}

```

## disassembly

```asm
0x100535d8  mov     edi, edi
0x100535da  push    ebp
0x100535db  mov     ebp, esp
0x100535dd  push    0FFFFFFFFh
0x100535df  push    offset ??1TemporaryDatabase@@EAE@XZ_SEH
0x100535e4  mov     eax, large fs:0
0x100535ea  push    eax
0x100535eb  push    ecx
0x100535ec  push    ebx
0x100535ed  push    esi
0x100535ee  push    edi
0x100535ef  mov     eax, ___security_cookie
0x100535f4  xor     eax, ebp
0x100535f6  push    eax
0x100535f7  lea     eax, [ebp+var_C]
0x100535fa  mov     large fs:0, eax
0x10053600  mov     esi, ecx
0x10053602  lea     eax, [esi+68h]
0x10053605  mov     dword ptr [esi], offset ??_7TemporaryDatabase@@6B@; const TemporaryDatabase::`vftable'
0x1005360b  push    eax; lpCriticalSection
0x1005360c  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10053612  imul    eax, [esi+90h], 2Ch ; ','
0x10053619  xor     edi, edi
0x1005361b  mov     [ebp+var_10], eax
0x1005361e  test    eax, eax
0x10053620  jz      short loc_10053641
0x10053622  push    edi; unsigned int
0x10053623  mov     ecx, esi; this
0x10053625  call    ?GetPD@Database@@QAEPAVPageDesc@@K@Z; Database::GetPD(ulong)
0x1005362a  mov     ebx, eax
0x1005362c  test    ebx, ebx
0x1005362e  jz      short loc_1005363B
0x10053630  mov     ecx, ebx; this
0x10053632  call    ?RemovePageFromCache@PageDesc@@QAEXXZ; PageDesc::RemovePageFromCache(void)
0x10053637  and     byte ptr [ebx+58h], 0F7h
0x1005363b  inc     edi
0x1005363c  cmp     edi, [ebp+var_10]
0x1005363f  jb      short loc_10053622
0x10053641  lea     eax, [esi+68h]
0x10053644  push    eax; lpCriticalSection
0x10053645  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1005364b  push    dword ptr [esi+3DCh]; Block
0x10053651  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10053656  pop     ecx
0x10053657  lea     eax, [esi+3F4h]
0x1005365d  mov     [ebp+var_4], 0
0x10053664  push    eax; lpCriticalSection
0x10053665  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x1005366b  mov     ecx, esi; this
0x1005366d  call    ??1Database@@MAE@XZ; Database::~Database(void)
0x10053672  mov     ecx, [ebp+var_C]
0x10053675  mov     large fs:0, ecx
0x1005367c  pop     ecx
0x1005367d  pop     edi
0x1005367e  pop     esi
0x1005367f  pop     ebx
0x10053680  leave
0x10053681  retn
0x10124060  jmp     ds:__imp____std_terminate
0x101254a4  nop
0x101254a5  nop
0x101254a6  mov     edx, [esp-4+arg_4]
0x101254aa  lea     eax, [edx+0Ch]
0x101254ad  mov     ecx, [edx-14h]
0x101254b0  xor     ecx, eax; StackCookie
0x101254b2  call    @__security_check_cookie@4; __security_check_cookie(x)
0x101254b7  mov     eax, offset stru_10127A7C
0x101254bc  jmp     ___CxxFrameHandler3
```
