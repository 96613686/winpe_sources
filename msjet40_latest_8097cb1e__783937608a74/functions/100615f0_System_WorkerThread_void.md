# System::WorkerThread(void *)

- ea: `0x100615f0`
- end: `0x1006189d`
- name: `?WorkerThread@System@@CGHPAX@Z`
- size: `685`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops`

## callees

- `0x10047a9f`
- `0x10056151`
- `0x100568ff`
- `0x10056a81`
- `0x10056f34`
- `0x10061284`
- `0x100614e1`
- `0x100615f0`
- `0x100619d6`
- `0x10074a9b`
- `0x10074cbc`
- `0x1007796a`
- `0x10077aff`
- `0x10123110`
- `0x10123c92`
- `0x10124048`
- `0x1012410f`
- `0x1012413e`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x100616b2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x100616b2`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x10061610`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x10061610`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100617cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100617ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100617cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100617ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10061702`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100617db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10061702`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100617db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1006187c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1006187c`

## pseudocode

```c
DWORD __stdcall System::WorkerThread(LPVOID lpThreadParameter)
{
  struct Err *v1; // ecx
  int v2; // eax
  struct QMsg *MessageW; // eax
  struct QMsg *v4; // edi
  struct _RTL_CRITICAL_SECTION *v5; // ecx
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // esi
  unsigned int v12; // esi
  unsigned int v13; // eax
  _DWORD *v14; // eax
  unsigned int v15; // ecx
  unsigned int v16; // eax
  int v17; // esi
  int IsMember; // esi
  struct Database *v19; // ecx
  struct _RTL_CRITICAL_SECTION *v21; // [esp-4h] [ebp-6Ch]
  int v22[5]; // [esp+10h] [ebp-58h] BYREF
  _DWORD v23[5]; // [esp+24h] [ebp-44h] BYREF
  _DWORD v24[5]; // [esp+38h] [ebp-30h] BYREF
  HANDLE hObject; // [esp+4Ch] [ebp-1Ch] BYREF
  unsigned int v26; // [esp+50h] [ebp-18h]
  Database *v27; // [esp+54h] [ebp-14h]
  unsigned int v28; // [esp+58h] [ebp-10h]
  int v29; // [esp+64h] [ebp-4h]

  v22[0] = 1;
  v29 = 0;
  hObject = CreateEventA(0, 1, 0, 0);
  if ( !hObject )
    System::ErrGetLastError(v1);
  v2 = 1;
  for ( v24[0] = 1; ; v24[0] = 1 )
  {
    LOBYTE(v29) = 2;
    v5 = (struct _RTL_CRITICAL_SECTION *)*((_DWORD *)lpThreadParameter + 7);
    if ( !v5 )
      break;
    MessageW = Queue::GetMessageW(v5, (struct Err *)v24);
    v4 = MessageW;
    if ( (v24[0] & 8) != 0 )
      goto LABEL_5;
    v6 = *(_DWORD *)MessageW;
    if ( !*(_DWORD *)v4 )
    {
      operator delete(v4, 0x18u);
      _InterlockedDecrement(&dword_10130568);
      v2 = v24[0];
      break;
    }
    v7 = v6 - 1;
    if ( !v7 )
    {
      Database::ReadPages(
        *((Database **)v4 + 2),
        (struct Semaphore *)&hObject,
        *((_DWORD *)v4 + 4),
        *((struct Err **)v4 + 5),
        (struct Err *)v24);
      goto LABEL_39;
    }
    v8 = v7 - 1;
    if ( !v8 )
      goto LABEL_37;
    v9 = v8 - 1;
    if ( !v9 )
    {
      v17 = *((_DWORD *)v4 + 2);
      EnterCriticalSection(*((LPCRITICAL_SECTION *)lpThreadParameter + 22));
      IsMember = Collection::IsMember(*((_DWORD *)lpThreadParameter + 21), v17);
      LeaveCriticalSection(*((LPCRITICAL_SECTION *)lpThreadParameter + 22));
      if ( IsMember )
        Connection::CheckDBSignatures(*(Connection **)(*((_DWORD *)v4 + 2) + 64), v19);
      goto LABEL_39;
    }
    v10 = v9 - 1;
    if ( !v10 )
    {
      EnterCriticalSection(*((LPCRITICAL_SECTION *)lpThreadParameter + 22));
      v12 = *((_DWORD *)lpThreadParameter + 17) / 0xAu;
      v13 = *((_DWORD *)lpThreadParameter + 18);
      if ( v13 > *((_DWORD *)lpThreadParameter + 17) )
        v12 += v13 - *((_DWORD *)lpThreadParameter + 17);
      if ( v12 )
      {
        v14 = (_DWORD *)*((_DWORD *)lpThreadParameter + 21);
        v15 = 0;
        v28 = 0;
        v26 = 0;
        if ( v14[2] )
        {
          while ( 1 )
          {
            v23[0] = 1;
            LOBYTE(v29) = 5;
            v27 = *(Database **)(*v14 + 4 * v15);
            v16 = Database::SurrenderMemory(v27, v12, (struct Err *)v23);
            v28 += v16;
            Database::WriteDirtyPages(v27, v23, 0);
            if ( (v23[0] & 8) != 0 )
              Database::TransferError(v27, (struct Err *)v23);
            LOBYTE(v29) = 2;
            if ( v28 >= v12 )
              break;
            v12 -= v28;
            if ( (v23[0] & 0xFFFFFFFE) != 0 )
              Err::Delete((Err *)v23);
            v14 = (_DWORD *)*((_DWORD *)lpThreadParameter + 21);
            v15 = v26 + 1;
            v26 = v15;
            if ( v15 >= v14[2] )
              goto LABEL_34;
          }
          if ( (v23[0] & 0xFFFFFFFE) != 0 )
            Err::Delete((Err *)v23);
        }
      }
LABEL_34:
      v21 = (struct _RTL_CRITICAL_SECTION *)*((_DWORD *)lpThreadParameter + 22);
      *((_DWORD *)lpThreadParameter + 23) = 0;
      LeaveCriticalSection(v21);
      goto LABEL_40;
    }
    if ( v10 == 1 )
    {
      v11 = *((_DWORD *)v4 + 2);
      *(_DWORD *)(v11 + 176) = 0;
      v28 = *(_DWORD *)(v11 + 172);
      if ( v28 )
      {
        if ( v28 - GetTickCount() >= 0x80000000 )
        {
LABEL_37:
          Database::WriteDirtyPages(*((_DWORD *)v4 + 2), v24, 0);
          Database::TransferError(*((Database **)v4 + 2), (struct Err *)v24);
LABEL_39:
          _InterlockedDecrement((volatile signed __int32 *)(*((_DWORD *)v4 + 2) + 212));
          goto LABEL_40;
        }
        *((_DWORD *)v4 + 1) = v28;
        System::Schedule((struct QMsg *)&Sys, v4);
        if ( (v24[0] & 8) == 0 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(v11 + 212));
          *(_DWORD *)(v11 + 176) = v28;
        }
      }
      _InterlockedDecrement((volatile signed __int32 *)(v11 + 212));
    }
LABEL_40:
    operator delete(v4, 0x18u);
LABEL_5:
    if ( (v24[0] & 0xFFFFFFFE) != 0 )
      Err::Delete((Err *)v24);
    v2 = 1;
  }
  if ( (v2 & 0xFFFFFFFE) != 0 )
    Err::Delete((Err *)v24);
  LOBYTE(v29) = 4;
  CloseHandle(hObject);
  if ( (v22[0] & 0xFFFFFFFE) != 0 )
    Err::Delete((Err *)v22);
  return 0;
}

```

## disassembly

```asm
0x100615f0  push    4Ch
0x100615f2  mov     eax, offset loc_101264B4
0x100615f7  call    __EH_prolog3
0x100615fc  xor     ebx, ebx
0x100615fe  inc     ebx
0x100615ff  mov     [ebp+var_58], ebx
0x10061602  push    0; lpName
0x10061604  push    0; bInitialState
0x10061606  push    ebx; bManualReset
0x10061607  push    0; lpEventAttributes
0x10061609  mov     [ebp+var_4], 0
0x10061610  call    ds:__imp__CreateEventA@16; CreateEventA(x,x,x,x)
0x10061616  mov     [ebp+hObject], eax
0x10061619  test    eax, eax
0x1006161b  jnz     short loc_10061626
0x1006161d  lea     eax, [ebp+var_58]
0x10061620  push    eax
0x10061621  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x10061626  mov     eax, ebx
0x10061628  mov     [ebp+var_30], eax
0x1006162b  mov     ebx, [ebp+lpThreadParameter]
0x1006162e  jmp     short loc_10061658
0x10061630  lea     eax, [ebp+var_30]
0x10061633  push    eax; struct Err *
0x10061634  call    ?GetMessageW@Queue@@QAEPAVQMsg@@AAVErr@@@Z; Queue::GetMessageW(Err &)
0x10061639  test    byte ptr [ebp+var_30], 8
0x1006163d  mov     edi, eax
0x1006163f  jz      short loc_10061668
0x10061641  test    [ebp+var_30], 0FFFFFFFEh
0x10061648  jz      short loc_10061652
0x1006164a  lea     ecx, [ebp+var_30]; this
0x1006164d  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x10061652  xor     eax, eax
0x10061654  inc     eax
0x10061655  mov     [ebp+var_30], eax
0x10061658  mov     byte ptr [ebp+var_4], 2
0x1006165c  mov     ecx, [ebx+1Ch]; lpCriticalSection
0x1006165f  test    ecx, ecx
0x10061661  jnz     short loc_10061630
0x10061663  jmp     loc_10061866
0x10061668  mov     eax, [edi]
0x1006166a  sub     eax, 0
0x1006166d  jz      loc_10061852
0x10061673  sub     eax, 1
0x10061676  jz      loc_10061823
0x1006167c  sub     eax, 1
0x1006167f  jz      loc_10061807
0x10061685  sub     eax, 1
0x10061688  jz      loc_100617D5
0x1006168e  sub     eax, 1
0x10061691  jz      short loc_100616FF
0x10061693  sub     eax, 1
0x10061696  jnz     loc_10061843
0x1006169c  mov     esi, [edi+8]
0x1006169f  mov     [esi+0B0h], eax
0x100616a5  mov     eax, [esi+0ACh]
0x100616ab  mov     [ebp+var_10], eax
0x100616ae  test    eax, eax
0x100616b0  jz      short loc_100616F3
0x100616b2  call    ds:__imp__GetTickCount@0; GetTickCount()
0x100616b8  mov     edx, [ebp+var_10]
0x100616bb  mov     ecx, edx
0x100616bd  sub     ecx, eax
0x100616bf  cmp     ecx, 80000000h
0x100616c5  jnb     loc_10061807
0x100616cb  lea     eax, [ebp+var_30]
0x100616ce  mov     [edi+4], edx
0x100616d1  push    eax
0x100616d2  push    edi; struct Err *
0x100616d3  mov     ecx, offset ?Sys@@3VSystem@@A; struct QMsg *
0x100616d8  call    ?Schedule@System@@QAEXPAVQMsg@@AAVErr@@@Z; System::Schedule(QMsg *,Err &)
0x100616dd  test    byte ptr [ebp+var_30], 8
0x100616e1  jnz     short loc_100616F3
0x100616e3  lock inc dword ptr [esi+0D4h]
0x100616ea  mov     eax, [ebp+var_10]
0x100616ed  mov     [esi+0B0h], eax
0x100616f3  lock dec dword ptr [esi+0D4h]
0x100616fa  jmp     loc_10061843
0x100616ff  push    dword ptr [ebx+58h]; lpCriticalSection
0x10061702  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10061708  mov     eax, [ebx+44h]
0x1006170b  xor     edx, edx
0x1006170d  push    0Ah
0x1006170f  pop     ecx
0x10061710  div     ecx
0x10061712  mov     esi, eax
0x10061714  mov     eax, [ebx+48h]
0x10061717  cmp     eax, [ebx+44h]
0x1006171a  jbe     short loc_10061721
0x1006171c  sub     eax, [ebx+44h]
0x1006171f  add     esi, eax
0x10061721  test    esi, esi
0x10061723  jz      loc_100617C3
0x10061729  mov     eax, [ebx+54h]
0x1006172c  xor     ecx, ecx
0x1006172e  mov     [ebp+var_10], 0
0x10061735  mov     [ebp+var_18], ecx
0x10061738  cmp     [eax+8], ecx
0x1006173b  jbe     loc_100617C3
0x10061741  mov     [ebp+var_44], 1
0x10061748  mov     byte ptr [ebp+var_4], 5
0x1006174c  mov     eax, [eax]
0x1006174e  mov     eax, [eax+ecx*4]
0x10061751  lea     ecx, [ebp+var_44]
0x10061754  push    ecx; struct Err *
0x10061755  push    esi; unsigned int
0x10061756  mov     ecx, eax; this
0x10061758  mov     [ebp+var_14], eax
0x1006175b  call    ?SurrenderMemory@Database@@QAEKKAAVErr@@@Z; Database::SurrenderMemory(ulong,Err &)
0x10061760  add     [ebp+var_10], eax
0x10061763  lea     eax, [ebp+var_44]
0x10061766  mov     ecx, [ebp+var_14]
0x10061769  push    0
0x1006176b  push    eax
0x1006176c  call    ?WriteDirtyPages@Database@@QAEXAAVErr@@W4DBWriteOption@@@Z; Database::WriteDirtyPages(Err &,DBWriteOption)
0x10061771  test    byte ptr [ebp+var_44], 8
0x10061775  jz      short loc_10061783
0x10061777  mov     ecx, [ebp+var_14]; this
0x1006177a  lea     eax, [ebp+var_44]
0x1006177d  push    eax; struct Err *
0x1006177e  call    ?TransferError@Database@@QAEXAAVErr@@@Z; Database::TransferError(Err &)
0x10061783  mov     eax, [ebp+var_10]
0x10061786  mov     byte ptr [ebp+var_4], 2
0x1006178a  cmp     eax, esi
0x1006178c  jnb     short loc_100617B2
0x1006178e  sub     esi, eax
0x10061790  test    [ebp+var_44], 0FFFFFFFEh
0x10061797  jz      short loc_100617A1
0x10061799  lea     ecx, [ebp+var_44]; this
0x1006179c  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x100617a1  mov     ecx, [ebp+var_18]
0x100617a4  mov     eax, [ebx+54h]
0x100617a7  inc     ecx
0x100617a8  mov     [ebp+var_18], ecx
0x100617ab  cmp     ecx, [eax+8]
0x100617ae  jb      short loc_10061741
0x100617b0  jmp     short loc_100617C3
0x100617b2  test    [ebp+var_44], 0FFFFFFFEh
0x100617b9  jz      short loc_100617C3
0x100617bb  lea     ecx, [ebp+var_44]; this
0x100617be  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x100617c3  push    dword ptr [ebx+58h]; lpCriticalSection
0x100617c6  mov     dword ptr [ebx+5Ch], 0
0x100617cd  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100617d3  jmp     short loc_10061843
0x100617d5  push    dword ptr [ebx+58h]; lpCriticalSection
0x100617d8  mov     esi, [edi+8]
0x100617db  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100617e1  mov     ecx, [ebx+54h]
0x100617e4  push    esi
0x100617e5  call    ?IsMember@Collection@@QAE?AW4CollBool@@PBX@Z; Collection::IsMember(void const *)
0x100617ea  push    dword ptr [ebx+58h]; lpCriticalSection
0x100617ed  mov     esi, eax
0x100617ef  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100617f5  test    esi, esi
0x100617f7  jz      short loc_10061839
0x100617f9  mov     eax, [edi+8]
0x100617fc  push    ecx; struct Database *
0x100617fd  mov     ecx, [eax+40h]; this
0x10061800  call    ?CheckDBSignatures@Connection@@QAEXPAVDatabase@@@Z; Connection::CheckDBSignatures(Database *)
0x10061805  jmp     short loc_10061839
0x10061807  mov     ecx, [edi+8]
0x1006180a  lea     eax, [ebp+var_30]
0x1006180d  push    0
0x1006180f  push    eax
0x10061810  call    ?WriteDirtyPages@Database@@QAEXAAVErr@@W4DBWriteOption@@@Z; Database::WriteDirtyPages(Err &,DBWriteOption)
0x10061815  mov     ecx, [edi+8]; this
0x10061818  lea     eax, [ebp+var_30]
0x1006181b  push    eax; struct Err *
0x1006181c  call    ?TransferError@Database@@QAEXAAVErr@@@Z; Database::TransferError(Err &)
0x10061821  jmp     short loc_10061839
0x10061823  mov     ecx, [edi+8]; this
0x10061826  lea     eax, [ebp+var_30]
0x10061829  push    eax; struct Err *
0x1006182a  push    dword ptr [edi+14h]; struct Err *
0x1006182d  lea     eax, [ebp+hObject]
0x10061830  push    dword ptr [edi+10h]; unsigned int
0x10061833  push    eax; struct Semaphore *
0x10061834  call    ?ReadPages@Database@@QAEXPAVSemaphore@@KKAAVErr@@@Z; Database::ReadPages(Semaphore *,ulong,ulong,Err &)
0x10061839  mov     eax, [edi+8]
0x1006183c  lock dec dword ptr [eax+0D4h]
0x10061843  push    18h; unsigned int
0x10061845  push    edi; Block
0x10061846  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1006184b  pop     ecx
0x1006184c  pop     ecx
0x1006184d  jmp     loc_10061641
0x10061852  push    18h; unsigned int
0x10061854  push    edi; Block
0x10061855  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1006185a  pop     ecx
0x1006185b  pop     ecx
0x1006185c  lock dec dword_10130568
0x10061863  mov     eax, [ebp+var_30]
0x10061866  test    eax, 0FFFFFFFEh
0x1006186b  jz      short loc_10061875
0x1006186d  lea     ecx, [ebp+var_30]; this
0x10061870  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x10061875  mov     byte ptr [ebp+var_4], 4
0x10061879  push    [ebp+hObject]; hObject
0x1006187c  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10061882  test    [ebp+var_58], 0FFFFFFFEh
0x10061889  jz      short loc_10061893
0x1006188b  lea     ecx, [ebp+var_58]; this
0x1006188e  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x10061893  xor     eax, eax
0x10061895  call    __EH_epilog3
0x1006189a  retn    4
0x10124060  jmp     ds:__imp____std_terminate
0x1012648f  lea     ecx, [ebp+var_58]; this
0x10126492  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x10126497  lea     ecx, [ebp+hObject]; this
0x1012649a  jmp     ??1Semaphore@@QAE@XZ; Semaphore::~Semaphore(void)
0x1012649f  lea     ecx, [ebp+var_30]; this
0x101264a2  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x101264a7  lea     ecx, [ebp+var_44]; this
0x101264aa  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x101264b4  nop
0x101264b5  nop
0x101264b6  mov     edx, [esp-4+arg_4]
0x101264ba  lea     eax, [edx+0Ch]
0x101264bd  mov     ecx, [edx-5Ch]
0x101264c0  xor     ecx, eax; StackCookie
0x101264c2  call    @__security_check_cookie@4; __security_check_cookie(x)
0x101264c7  mov     eax, offset stru_10128BF8
0x101264cc  jmp     ___CxxFrameHandler3
```
