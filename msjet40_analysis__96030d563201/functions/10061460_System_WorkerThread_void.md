# System::WorkerThread(void *)

- ea: `0x10061460`
- end: `0x1006170d`
- name: `?WorkerThread@System@@CGHPAX@Z`
- size: `685`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops`

## callees

- `0x1004791f`
- `0x10055fc1`
- `0x1005676f`
- `0x100568f1`
- `0x10056da4`
- `0x100610f0`
- `0x1006134d`
- `0x10061460`
- `0x10061846`
- `0x1007490b`
- `0x10074b2c`
- `0x100777da`
- `0x1007796f`
- `0x10122f60`
- `0x10123ae2`
- `0x10123e98`
- `0x10123f5f`
- `0x10123f8e`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10061522`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10061522`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x10061480`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x10061480`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1006163d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1006165f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1006163d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1006165f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10061572`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1006164b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10061572`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1006164b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100616ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100616ec`

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
      _InterlockedDecrement(&dword_101304D0);
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
0x10061460  push    4Ch
0x10061462  mov     eax, offset loc_10126304
0x10061467  call    __EH_prolog3
0x1006146c  xor     ebx, ebx
0x1006146e  inc     ebx
0x1006146f  mov     [ebp+var_58], ebx
0x10061472  push    0; lpName
0x10061474  push    0; bInitialState
0x10061476  push    ebx; bManualReset
0x10061477  push    0; lpEventAttributes
0x10061479  mov     [ebp+var_4], 0
0x10061480  call    ds:__imp__CreateEventA@16; CreateEventA(x,x,x,x)
0x10061486  mov     [ebp+hObject], eax
0x10061489  test    eax, eax
0x1006148b  jnz     short loc_10061496
0x1006148d  lea     eax, [ebp+var_58]
0x10061490  push    eax
0x10061491  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x10061496  mov     eax, ebx
0x10061498  mov     [ebp+var_30], eax
0x1006149b  mov     ebx, [ebp+lpThreadParameter]
0x1006149e  jmp     short loc_100614C8
0x100614a0  lea     eax, [ebp+var_30]
0x100614a3  push    eax; struct Err *
0x100614a4  call    ?GetMessageW@Queue@@QAEPAVQMsg@@AAVErr@@@Z; Queue::GetMessageW(Err &)
0x100614a9  test    byte ptr [ebp+var_30], 8
0x100614ad  mov     edi, eax
0x100614af  jz      short loc_100614D8
0x100614b1  test    [ebp+var_30], 0FFFFFFFEh
0x100614b8  jz      short loc_100614C2
0x100614ba  lea     ecx, [ebp+var_30]; this
0x100614bd  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x100614c2  xor     eax, eax
0x100614c4  inc     eax
0x100614c5  mov     [ebp+var_30], eax
0x100614c8  mov     byte ptr [ebp+var_4], 2
0x100614cc  mov     ecx, [ebx+1Ch]; lpCriticalSection
0x100614cf  test    ecx, ecx
0x100614d1  jnz     short loc_100614A0
0x100614d3  jmp     loc_100616D6
0x100614d8  mov     eax, [edi]
0x100614da  sub     eax, 0
0x100614dd  jz      loc_100616C2
0x100614e3  sub     eax, 1
0x100614e6  jz      loc_10061693
0x100614ec  sub     eax, 1
0x100614ef  jz      loc_10061677
0x100614f5  sub     eax, 1
0x100614f8  jz      loc_10061645
0x100614fe  sub     eax, 1
0x10061501  jz      short loc_1006156F
0x10061503  sub     eax, 1
0x10061506  jnz     loc_100616B3
0x1006150c  mov     esi, [edi+8]
0x1006150f  mov     [esi+0B0h], eax
0x10061515  mov     eax, [esi+0ACh]
0x1006151b  mov     [ebp+var_10], eax
0x1006151e  test    eax, eax
0x10061520  jz      short loc_10061563
0x10061522  call    ds:__imp__GetTickCount@0; GetTickCount()
0x10061528  mov     edx, [ebp+var_10]
0x1006152b  mov     ecx, edx
0x1006152d  sub     ecx, eax
0x1006152f  cmp     ecx, 80000000h
0x10061535  jnb     loc_10061677
0x1006153b  lea     eax, [ebp+var_30]
0x1006153e  mov     [edi+4], edx
0x10061541  push    eax
0x10061542  push    edi; struct Err *
0x10061543  mov     ecx, offset ?Sys@@3VSystem@@A; struct QMsg *
0x10061548  call    ?Schedule@System@@QAEXPAVQMsg@@AAVErr@@@Z; System::Schedule(QMsg *,Err &)
0x1006154d  test    byte ptr [ebp+var_30], 8
0x10061551  jnz     short loc_10061563
0x10061553  lock inc dword ptr [esi+0D4h]
0x1006155a  mov     eax, [ebp+var_10]
0x1006155d  mov     [esi+0B0h], eax
0x10061563  lock dec dword ptr [esi+0D4h]
0x1006156a  jmp     loc_100616B3
0x1006156f  push    dword ptr [ebx+58h]; lpCriticalSection
0x10061572  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10061578  mov     eax, [ebx+44h]
0x1006157b  xor     edx, edx
0x1006157d  push    0Ah
0x1006157f  pop     ecx
0x10061580  div     ecx
0x10061582  mov     esi, eax
0x10061584  mov     eax, [ebx+48h]
0x10061587  cmp     eax, [ebx+44h]
0x1006158a  jbe     short loc_10061591
0x1006158c  sub     eax, [ebx+44h]
0x1006158f  add     esi, eax
0x10061591  test    esi, esi
0x10061593  jz      loc_10061633
0x10061599  mov     eax, [ebx+54h]
0x1006159c  xor     ecx, ecx
0x1006159e  mov     [ebp+var_10], 0
0x100615a5  mov     [ebp+var_18], ecx
0x100615a8  cmp     [eax+8], ecx
0x100615ab  jbe     loc_10061633
0x100615b1  mov     [ebp+var_44], 1
0x100615b8  mov     byte ptr [ebp+var_4], 5
0x100615bc  mov     eax, [eax]
0x100615be  mov     eax, [eax+ecx*4]
0x100615c1  lea     ecx, [ebp+var_44]
0x100615c4  push    ecx; struct Err *
0x100615c5  push    esi; unsigned int
0x100615c6  mov     ecx, eax; this
0x100615c8  mov     [ebp+var_14], eax
0x100615cb  call    ?SurrenderMemory@Database@@QAEKKAAVErr@@@Z; Database::SurrenderMemory(ulong,Err &)
0x100615d0  add     [ebp+var_10], eax
0x100615d3  lea     eax, [ebp+var_44]
0x100615d6  mov     ecx, [ebp+var_14]
0x100615d9  push    0
0x100615db  push    eax
0x100615dc  call    ?WriteDirtyPages@Database@@QAEXAAVErr@@W4DBWriteOption@@@Z; Database::WriteDirtyPages(Err &,DBWriteOption)
0x100615e1  test    byte ptr [ebp+var_44], 8
0x100615e5  jz      short loc_100615F3
0x100615e7  mov     ecx, [ebp+var_14]; this
0x100615ea  lea     eax, [ebp+var_44]
0x100615ed  push    eax; struct Err *
0x100615ee  call    ?TransferError@Database@@QAEXAAVErr@@@Z; Database::TransferError(Err &)
0x100615f3  mov     eax, [ebp+var_10]
0x100615f6  mov     byte ptr [ebp+var_4], 2
0x100615fa  cmp     eax, esi
0x100615fc  jnb     short loc_10061622
0x100615fe  sub     esi, eax
0x10061600  test    [ebp+var_44], 0FFFFFFFEh
0x10061607  jz      short loc_10061611
0x10061609  lea     ecx, [ebp+var_44]; this
0x1006160c  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x10061611  mov     ecx, [ebp+var_18]
0x10061614  mov     eax, [ebx+54h]
0x10061617  inc     ecx
0x10061618  mov     [ebp+var_18], ecx
0x1006161b  cmp     ecx, [eax+8]
0x1006161e  jb      short loc_100615B1
0x10061620  jmp     short loc_10061633
0x10061622  test    [ebp+var_44], 0FFFFFFFEh
0x10061629  jz      short loc_10061633
0x1006162b  lea     ecx, [ebp+var_44]; this
0x1006162e  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x10061633  push    dword ptr [ebx+58h]; lpCriticalSection
0x10061636  mov     dword ptr [ebx+5Ch], 0
0x1006163d  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10061643  jmp     short loc_100616B3
0x10061645  push    dword ptr [ebx+58h]; lpCriticalSection
0x10061648  mov     esi, [edi+8]
0x1006164b  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10061651  mov     ecx, [ebx+54h]
0x10061654  push    esi
0x10061655  call    ?IsMember@Collection@@QAE?AW4CollBool@@PBX@Z; Collection::IsMember(void const *)
0x1006165a  push    dword ptr [ebx+58h]; lpCriticalSection
0x1006165d  mov     esi, eax
0x1006165f  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10061665  test    esi, esi
0x10061667  jz      short loc_100616A9
0x10061669  mov     eax, [edi+8]
0x1006166c  push    ecx; struct Database *
0x1006166d  mov     ecx, [eax+40h]; this
0x10061670  call    ?CheckDBSignatures@Connection@@QAEXPAVDatabase@@@Z; Connection::CheckDBSignatures(Database *)
0x10061675  jmp     short loc_100616A9
0x10061677  mov     ecx, [edi+8]
0x1006167a  lea     eax, [ebp+var_30]
0x1006167d  push    0
0x1006167f  push    eax
0x10061680  call    ?WriteDirtyPages@Database@@QAEXAAVErr@@W4DBWriteOption@@@Z; Database::WriteDirtyPages(Err &,DBWriteOption)
0x10061685  mov     ecx, [edi+8]; this
0x10061688  lea     eax, [ebp+var_30]
0x1006168b  push    eax; struct Err *
0x1006168c  call    ?TransferError@Database@@QAEXAAVErr@@@Z; Database::TransferError(Err &)
0x10061691  jmp     short loc_100616A9
0x10061693  mov     ecx, [edi+8]; this
0x10061696  lea     eax, [ebp+var_30]
0x10061699  push    eax; struct Err *
0x1006169a  push    dword ptr [edi+14h]; struct Err *
0x1006169d  lea     eax, [ebp+hObject]
0x100616a0  push    dword ptr [edi+10h]; unsigned int
0x100616a3  push    eax; struct Semaphore *
0x100616a4  call    ?ReadPages@Database@@QAEXPAVSemaphore@@KKAAVErr@@@Z; Database::ReadPages(Semaphore *,ulong,ulong,Err &)
0x100616a9  mov     eax, [edi+8]
0x100616ac  lock dec dword ptr [eax+0D4h]
0x100616b3  push    18h; unsigned int
0x100616b5  push    edi; Block
0x100616b6  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x100616bb  pop     ecx
0x100616bc  pop     ecx
0x100616bd  jmp     loc_100614B1
0x100616c2  push    18h; unsigned int
0x100616c4  push    edi; Block
0x100616c5  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x100616ca  pop     ecx
0x100616cb  pop     ecx
0x100616cc  lock dec dword_101304D0
0x100616d3  mov     eax, [ebp+var_30]
0x100616d6  test    eax, 0FFFFFFFEh
0x100616db  jz      short loc_100616E5
0x100616dd  lea     ecx, [ebp+var_30]; this
0x100616e0  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x100616e5  mov     byte ptr [ebp+var_4], 4
0x100616e9  push    [ebp+hObject]; hObject
0x100616ec  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x100616f2  test    [ebp+var_58], 0FFFFFFFEh
0x100616f9  jz      short loc_10061703
0x100616fb  lea     ecx, [ebp+var_58]; this
0x100616fe  call    ?Delete@Err@@AAEXXZ; Err::Delete(void)
0x10061703  xor     eax, eax
0x10061705  call    __EH_epilog3
0x1006170a  retn    4
0x10123eb0  jmp     ds:__imp____std_terminate
0x101262df  lea     ecx, [ebp+var_58]; this
0x101262e2  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x101262e7  lea     ecx, [ebp+hObject]; this
0x101262ea  jmp     ??1Semaphore@@QAE@XZ; Semaphore::~Semaphore(void)
0x101262ef  lea     ecx, [ebp+var_30]; this
0x101262f2  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x101262f7  lea     ecx, [ebp+var_44]; this
0x101262fa  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x10126304  nop
0x10126305  nop
0x10126306  mov     edx, [esp-4+arg_4]
0x1012630a  lea     eax, [edx+0Ch]
0x1012630d  mov     ecx, [edx-5Ch]
0x10126310  xor     ecx, eax; StackCookie
0x10126312  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10126317  mov     eax, offset stru_10128A48
0x1012631c  jmp     ___CxxFrameHandler3
```
