# TemporaryDatabase::~TemporaryDatabase(void)

- ea: `0x10053448`
- end: `0x100534f2`
- name: `??1TemporaryDatabase@@EAE@XZ`
- size: `170`
- prototype: `void __usercall(TemporaryDatabase *__hidden this@<ecx>)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x10053110`

## callees

- `0x1005313d`
- `0x10053448`
- `0x100574e3`
- `0x10077333`
- `0x10122f60`
- `0x10123af8`
- `0x10123e98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x100534d5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x100534d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100534b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100534b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1005347c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1005347c`

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
0x10053448  mov     edi, edi
0x1005344a  push    ebp
0x1005344b  mov     ebp, esp
0x1005344d  push    0FFFFFFFFh
0x1005344f  push    offset ??1TemporaryDatabase@@EAE@XZ_SEH
0x10053454  mov     eax, large fs:0
0x1005345a  push    eax
0x1005345b  push    ecx
0x1005345c  push    ebx
0x1005345d  push    esi
0x1005345e  push    edi
0x1005345f  mov     eax, ___security_cookie
0x10053464  xor     eax, ebp
0x10053466  push    eax
0x10053467  lea     eax, [ebp+var_C]
0x1005346a  mov     large fs:0, eax
0x10053470  mov     esi, ecx
0x10053472  lea     eax, [esi+68h]
0x10053475  mov     dword ptr [esi], offset ??_7TemporaryDatabase@@6B@; const TemporaryDatabase::`vftable'
0x1005347b  push    eax; lpCriticalSection
0x1005347c  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10053482  imul    eax, [esi+90h], 2Ch ; ','
0x10053489  xor     edi, edi
0x1005348b  mov     [ebp+var_10], eax
0x1005348e  test    eax, eax
0x10053490  jz      short loc_100534B1
0x10053492  push    edi; unsigned int
0x10053493  mov     ecx, esi; this
0x10053495  call    ?GetPD@Database@@QAEPAVPageDesc@@K@Z; Database::GetPD(ulong)
0x1005349a  mov     ebx, eax
0x1005349c  test    ebx, ebx
0x1005349e  jz      short loc_100534AB
0x100534a0  mov     ecx, ebx; this
0x100534a2  call    ?RemovePageFromCache@PageDesc@@QAEXXZ; PageDesc::RemovePageFromCache(void)
0x100534a7  and     byte ptr [ebx+58h], 0F7h
0x100534ab  inc     edi
0x100534ac  cmp     edi, [ebp+var_10]
0x100534af  jb      short loc_10053492
0x100534b1  lea     eax, [esi+68h]
0x100534b4  push    eax; lpCriticalSection
0x100534b5  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100534bb  push    dword ptr [esi+3DCh]; Block
0x100534c1  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100534c6  pop     ecx
0x100534c7  lea     eax, [esi+3F4h]
0x100534cd  mov     [ebp+var_4], 0
0x100534d4  push    eax; lpCriticalSection
0x100534d5  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x100534db  mov     ecx, esi; this
0x100534dd  call    ??1Database@@MAE@XZ; Database::~Database(void)
0x100534e2  mov     ecx, [ebp+var_C]
0x100534e5  mov     large fs:0, ecx
0x100534ec  pop     ecx
0x100534ed  pop     edi
0x100534ee  pop     esi
0x100534ef  pop     ebx
0x100534f0  leave
0x100534f1  retn
0x10123eb0  jmp     ds:__imp____std_terminate
0x101252f4  nop
0x101252f5  nop
0x101252f6  mov     edx, [esp-4+arg_4]
0x101252fa  lea     eax, [edx+0Ch]
0x101252fd  mov     ecx, [edx-14h]
0x10125300  xor     ecx, eax; StackCookie
0x10125302  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10125307  mov     eax, offset stru_101278CC
0x1012530c  jmp     ___CxxFrameHandler3
```
