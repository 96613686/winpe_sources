# System::WorkerThread(void *)

- ea: `0x1004f3b0`
- end: `0x1004f78d`
- name: `?WorkerThread@System@@CGHPAX@Z`
- size: `989`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops`

## callees

- `0x1000f750`
- `0x10018b80`
- `0x10023420`
- `0x10023900`
- `0x10023bb0`
- `0x10025e60`
- `0x1004eda0`
- `0x1004f130`
- `0x1004f3b0`
- `0x1005cbe0`
- `0x1005cd30`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e7e8`
- `0x1005f064`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1004f3f0`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1004f3f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1004f4ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1004f52c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1004f58b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1004f60a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1004f4ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1004f52c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1004f58b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1004f60a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1004f509`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1004f558`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1004f627`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1004f6b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1004f509`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1004f558`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1004f627`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1004f6b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1004f748`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1004f748`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1004f493`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1004f493`

## pseudocode

```c
ULONG __stdcall System::WorkerThread(char *Parameter)
{
  struct Err *v1; // ecx
  char *v2; // esi
  struct _RTL_CRITICAL_SECTION *v3; // ecx
  struct QMsg *MessageW; // ebx
  void *v5; // eax
  int v6; // esi
  int v7; // edi
  int v8; // esi
  int v9; // ebx
  unsigned int v10; // esi
  unsigned int v11; // edi
  struct Database *v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // eax
  unsigned int v15; // ebx
  unsigned int v16; // edi
  int v17; // esi
  unsigned int v18; // eax
  int v19; // eax
  _DWORD v21[3]; // [esp+24h] [ebp-44h] BYREF
  void *Block; // [esp+30h] [ebp-38h]
  void *v23; // [esp+34h] [ebp-34h]
  _DWORD v24[3]; // [esp+38h] [ebp-30h] BYREF
  void *v25; // [esp+44h] [ebp-24h]
  void *v26; // [esp+48h] [ebp-20h]
  HANDLE hObject; // [esp+4Ch] [ebp-1Ch] BYREF
  int v28; // [esp+50h] [ebp-18h]
  struct QMsg *v29; // [esp+54h] [ebp-14h]
  unsigned int v30; // [esp+58h] [ebp-10h]
  int v31; // [esp+64h] [ebp-4h]

  v31 = 0;
  hObject = CreateEventA(0, 1, 0, 0);
  if ( !hObject )
    System::ErrGetLastError(v1);
  v2 = Parameter;
LABEL_4:
  v3 = (struct _RTL_CRITICAL_SECTION *)(v2 + 28);
  while ( 1 )
  {
    while ( 1 )
    {
      v24[0] = 1;
      LOBYTE(v31) = 2;
      MessageW = Queue::GetMessageW(v3, (struct Err *)v24);
      v29 = MessageW;
      if ( (v24[0] & 8) == 0 )
        break;
      v3 = (struct _RTL_CRITICAL_SECTION *)(v2 + 28);
      if ( (v24[0] & 0xFFFFFFFE) != 0 )
      {
        v5 = v25;
LABEL_49:
        if ( v5 )
          operator delete[](v5);
        goto LABEL_51;
      }
    }
    switch ( *(_DWORD *)MessageW )
    {
      case 0:
        operator delete(MessageW, 0x18u);
        _InterlockedDecrement(&dword_10066974);
        if ( (v24[0] & 0xFFFFFFFE) != 0 )
        {
          if ( v25 )
            operator delete[](v25);
          if ( v26 )
            operator delete[](v26);
        }
        CloseHandle(hObject);
        return 0;
      case 1:
        Database::ReadPages(
          *((Database **)MessageW + 2),
          (struct Semaphore *)&hObject,
          *((_DWORD *)MessageW + 4),
          *((struct Err **)MessageW + 5),
          (struct Err *)v24);
        _InterlockedDecrement((volatile signed __int32 *)(*((_DWORD *)MessageW + 2) + 216));
        goto LABEL_47;
      case 2:
        goto LABEL_15;
      case 3:
        v9 = *((_DWORD *)MessageW + 2);
        EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 176));
        v10 = 0;
        v11 = *((_DWORD *)Parameter + 43);
        if ( v11 )
        {
          do
          {
            if ( *(_DWORD *)(*((_DWORD *)Parameter + 41) + 4 * v10) == v9 )
              break;
            ++v10;
          }
          while ( v10 < v11 );
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 176));
        MessageW = v29;
        if ( v10 != v11 )
          Connection::CheckDBSignatures(*(Connection **)(*((_DWORD *)v29 + 2) + 60), v12);
        _InterlockedDecrement((volatile signed __int32 *)(*((_DWORD *)MessageW + 2) + 216));
        v2 = Parameter;
        goto LABEL_47;
      case 4:
        EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 176));
        v13 = *((_DWORD *)v2 + 36);
        v14 = *((_DWORD *)v2 + 37);
        v15 = v13 / 0xA;
        if ( v14 > v13 )
          v15 += v14 - v13;
        if ( !v15 )
          goto LABEL_46;
        v16 = 0;
        v30 = 0;
        v28 = 0;
        if ( !*((_DWORD *)v2 + 43) )
          goto LABEL_46;
        break;
      case 5:
        v6 = *((_DWORD *)MessageW + 2);
        v7 = *(_DWORD *)(v6 + 176);
        *(_DWORD *)(v6 + 180) = 0;
        if ( !v7 )
          goto LABEL_14;
        if ( v7 - GetTickCount() >= 0x80000000 )
        {
LABEL_15:
          Database::WriteDirtyPages(*((Database **)MessageW + 2), (struct Err *)v24);
          v8 = *((_DWORD *)MessageW + 2);
          EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 112));
          if ( v24[0] > *(_DWORD *)(v8 + 196) )
            Err::operator=(v24);
          LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 112));
          _InterlockedDecrement((volatile signed __int32 *)(*((_DWORD *)MessageW + 2) + 216));
          v2 = Parameter;
        }
        else
        {
          *((_DWORD *)MessageW + 1) = v7;
          System::Schedule((struct QMsg *)&Sys, MessageW, (struct Err *)v24);
          if ( (v24[0] & 8) == 0 )
          {
            _InterlockedIncrement((volatile signed __int32 *)(v6 + 216));
            *(_DWORD *)(v6 + 180) = v7;
          }
LABEL_14:
          _InterlockedDecrement((volatile signed __int32 *)(v6 + 216));
          v2 = Parameter;
        }
        goto LABEL_47;
      default:
        goto LABEL_47;
    }
    while ( 1 )
    {
      v21[0] = 1;
      LOBYTE(v31) = 3;
      v17 = *(_DWORD *)(*((_DWORD *)v2 + 41) + 4 * v16);
      v18 = Database::SurrenderMemory((Database *)v17, v15, (struct Err *)v21);
      v30 += v18;
      Database::WriteDirtyPages((Database *)v17, (struct Err *)v21);
      v19 = v21[0];
      if ( (v21[0] & 8) != 0 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)(v17 + 112));
        if ( v21[0] > *(_DWORD *)(v17 + 196) )
          Err::operator=(v21);
        LeaveCriticalSection((LPCRITICAL_SECTION)(v17 + 112));
        v19 = v21[0];
        v16 = v28;
      }
      if ( v30 >= v15 )
        break;
      v15 -= v30;
      if ( (v19 & 0xFFFFFFFE) != 0 )
      {
        if ( Block )
          operator delete[](Block);
        if ( v23 )
          operator delete[](v23);
      }
      v2 = Parameter;
      v28 = ++v16;
      if ( v16 >= *((_DWORD *)Parameter + 43) )
        goto LABEL_46;
    }
    if ( (v19 & 0xFFFFFFFE) != 0 )
    {
      if ( Block )
        operator delete[](Block);
      if ( v23 )
        operator delete[](v23);
    }
    v2 = Parameter;
LABEL_46:
    *((_DWORD *)v2 + 50) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 176));
    MessageW = v29;
LABEL_47:
    operator delete(MessageW, 0x18u);
    v3 = (struct _RTL_CRITICAL_SECTION *)(v2 + 28);
    if ( (v24[0] & 0xFFFFFFFE) != 0 )
    {
      v5 = v25;
      if ( v25 )
        goto LABEL_49;
LABEL_51:
      v3 = (struct _RTL_CRITICAL_SECTION *)(v2 + 28);
      if ( v26 )
      {
        operator delete[](v26);
        goto LABEL_4;
      }
    }
  }
}

```

## disassembly

```asm
0x1004f3b0  mov     edi, edi
0x1004f3b2  push    ebp
0x1004f3b3  mov     ebp, esp
0x1004f3b5  push    0FFFFFFFFh
0x1004f3b7  push    offset ?WorkerThread@System@@CGHPAX@Z_SEH
0x1004f3bc  mov     eax, large fs:0
0x1004f3c2  push    eax
0x1004f3c3  sub     esp, 4Ch
0x1004f3c6  push    ebx
0x1004f3c7  push    esi
0x1004f3c8  push    edi
0x1004f3c9  mov     eax, ___security_cookie
0x1004f3ce  xor     eax, ebp
0x1004f3d0  push    eax
0x1004f3d1  lea     eax, [ebp+var_C]
0x1004f3d4  mov     large fs:0, eax
0x1004f3da  mov     [ebp+var_58], 1
0x1004f3e1  push    0; lpName
0x1004f3e3  push    0; bInitialState
0x1004f3e5  push    1; bManualReset
0x1004f3e7  push    0; lpEventAttributes
0x1004f3e9  mov     [ebp+var_4], 0
0x1004f3f0  call    ds:__imp__CreateEventA@16; CreateEventA(x,x,x,x)
0x1004f3f6  mov     [ebp+hObject], eax
0x1004f3f9  test    eax, eax
0x1004f3fb  jnz     short loc_1004F406
0x1004f3fd  lea     eax, [ebp+var_58]
0x1004f400  push    eax
0x1004f401  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x1004f406  mov     esi, [ebp+Parameter]
0x1004f409  lea     ecx, [esi+1Ch]; lpCriticalSection
0x1004f40c  nop     dword ptr [eax+00h]
0x1004f410  mov     [ebp+var_30], 1
0x1004f417  lea     eax, [ebp+var_30]
0x1004f41a  mov     byte ptr [ebp+var_4], 2
0x1004f41e  push    eax; struct Err *
0x1004f41f  call    ?GetMessageW@Queue@@QAEPAVQMsg@@AAVErr@@@Z; Queue::GetMessageW(Err &)
0x1004f424  mov     ecx, [ebp+var_30]
0x1004f427  mov     ebx, eax
0x1004f429  mov     [ebp+var_14], ebx
0x1004f42c  test    cl, 8
0x1004f42f  jz      short loc_1004F444
0x1004f431  test    ecx, 0FFFFFFFEh
0x1004f437  lea     ecx, [esi+1Ch]
0x1004f43a  jz      short loc_1004F410
0x1004f43c  mov     eax, [ebp+var_24]
0x1004f43f  jmp     loc_1004F6DE
0x1004f444  mov     eax, [ebx]
0x1004f446  cmp     eax, 5; switch 6 cases
0x1004f449  ja      def_1004F44F; jumptable 1004F44F default case
0x1004f44f  jmp     ds:jpt_1004F44F[eax*4]; switch jump
0x1004f456  mov     ecx, [ebx+8]; jumptable 1004F44F case 1
0x1004f459  lea     eax, [ebp+var_30]
0x1004f45c  push    eax; struct Err *
0x1004f45d  push    dword ptr [ebx+14h]; struct Err *
0x1004f460  lea     eax, [ebp+hObject]
0x1004f463  push    dword ptr [ebx+10h]; unsigned int
0x1004f466  push    eax; struct Semaphore *
0x1004f467  call    ?ReadPages@Database@@QAEXPAVSemaphore@@KKAAVErr@@@Z; Database::ReadPages(Semaphore *,ulong,ulong,Err &)
0x1004f46c  mov     eax, [ebx+8]
0x1004f46f  add     eax, 0D8h
0x1004f474  lock dec dword ptr [eax]
0x1004f477  jmp     def_1004F44F; jumptable 1004F44F default case
0x1004f47c  mov     esi, [ebx+8]; jumptable 1004F44F case 5
0x1004f47f  mov     edi, [esi+0B0h]
0x1004f485  mov     dword ptr [esi+0B4h], 0
0x1004f48f  test    edi, edi
0x1004f491  jz      short loc_1004F4CA
0x1004f493  call    ds:__imp__GetTickCount@0; GetTickCount()
0x1004f499  mov     ecx, edi
0x1004f49b  sub     ecx, eax
0x1004f49d  cmp     ecx, 80000000h
0x1004f4a3  jnb     short loc_1004F4D9; jumptable 1004F44F case 2
0x1004f4a5  lea     eax, [ebp+var_30]
0x1004f4a8  mov     [ebx+4], edi
0x1004f4ab  push    eax
0x1004f4ac  push    ebx; struct Err *
0x1004f4ad  mov     ecx, offset ?Sys@@3VSystem@@A; lpParameter
0x1004f4b2  call    ?Schedule@System@@QAEXPAVQMsg@@AAVErr@@@Z; System::Schedule(QMsg *,Err &)
0x1004f4b7  test    byte ptr [ebp+var_30], 8
0x1004f4bb  jnz     short loc_1004F4CA
0x1004f4bd  lock inc dword ptr [esi+0D8h]
0x1004f4c4  mov     [esi+0B4h], edi
0x1004f4ca  lock dec dword ptr [esi+0D8h]
0x1004f4d1  mov     esi, [ebp+Parameter]
0x1004f4d4  jmp     def_1004F44F; jumptable 1004F44F default case
0x1004f4d9  mov     ecx, [ebx+8]; jumptable 1004F44F case 2
0x1004f4dc  lea     eax, [ebp+var_30]
0x1004f4df  push    eax; struct Err *
0x1004f4e0  call    ?WriteDirtyPages@Database@@QAEXAAVErr@@@Z; Database::WriteDirtyPages(Err &)
0x1004f4e5  mov     esi, [ebx+8]
0x1004f4e8  lea     edi, [esi+70h]
0x1004f4eb  push    edi; lpCriticalSection
0x1004f4ec  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1004f4f2  mov     eax, [ebp+var_30]
0x1004f4f5  lea     ecx, [esi+0C4h]
0x1004f4fb  cmp     eax, [ecx]
0x1004f4fd  jle     short loc_1004F508
0x1004f4ff  lea     eax, [ebp+var_30]
0x1004f502  push    eax
0x1004f503  call    ??4Err@@QAEAAV0@ABV0@@Z; Err::operator=(Err const &)
0x1004f508  push    edi; lpCriticalSection
0x1004f509  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1004f50f  mov     eax, [ebx+8]
0x1004f512  add     eax, 0D8h
0x1004f517  lock dec dword ptr [eax]
0x1004f51a  mov     esi, [ebp+Parameter]
0x1004f51d  jmp     def_1004F44F; jumptable 1004F44F default case
0x1004f522  mov     ebx, [ebx+8]; jumptable 1004F44F case 3
0x1004f525  lea     eax, [esi+0B0h]
0x1004f52b  push    eax; lpCriticalSection
0x1004f52c  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1004f532  mov     ecx, [ebp+Parameter]
0x1004f535  xor     esi, esi
0x1004f537  mov     edi, [ecx+0ACh]
0x1004f53d  test    edi, edi
0x1004f53f  jz      short loc_1004F551
0x1004f541  mov     eax, [ecx+0A4h]
0x1004f547  cmp     [eax+esi*4], ebx
0x1004f54a  jz      short loc_1004F551
0x1004f54c  inc     esi
0x1004f54d  cmp     esi, edi
0x1004f54f  jb      short loc_1004F547
0x1004f551  lea     eax, [ecx+0B0h]
0x1004f557  push    eax; lpCriticalSection
0x1004f558  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1004f55e  mov     ebx, [ebp+var_14]
0x1004f561  cmp     esi, edi
0x1004f563  jz      short loc_1004F571
0x1004f565  push    ecx; struct Database *
0x1004f566  mov     ecx, [ebx+8]
0x1004f569  mov     ecx, [ecx+3Ch]; this
0x1004f56c  call    ?CheckDBSignatures@Connection@@QAEXPAVDatabase@@@Z; Connection::CheckDBSignatures(Database *)
0x1004f571  mov     eax, [ebx+8]
0x1004f574  add     eax, 0D8h
0x1004f579  lock dec dword ptr [eax]
0x1004f57c  mov     esi, [ebp+Parameter]
0x1004f57f  jmp     def_1004F44F; jumptable 1004F44F default case
0x1004f584  lea     eax, [esi+0B0h]; jumptable 1004F44F case 4
0x1004f58a  push    eax; lpCriticalSection
0x1004f58b  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1004f591  mov     ecx, [esi+90h]
0x1004f597  mov     eax, 0CCCCCCCDh
0x1004f59c  mul     ecx
0x1004f59e  mov     eax, [esi+94h]
0x1004f5a4  mov     ebx, edx
0x1004f5a6  shr     ebx, 3
0x1004f5a9  cmp     eax, ecx
0x1004f5ab  jbe     short loc_1004F5B1
0x1004f5ad  sub     eax, ecx
0x1004f5af  add     ebx, eax
0x1004f5b1  test    ebx, ebx
0x1004f5b3  jz      loc_1004F6A2
0x1004f5b9  xor     edi, edi
0x1004f5bb  mov     [ebp+var_10], 0
0x1004f5c2  mov     [ebp+var_18], edi
0x1004f5c5  cmp     [esi+0ACh], edi
0x1004f5cb  jbe     loc_1004F6A2
0x1004f5d1  mov     [ebp+var_44], 1
0x1004f5d8  mov     byte ptr [ebp+var_4], 3
0x1004f5dc  mov     eax, [esi+0A4h]
0x1004f5e2  mov     esi, [eax+edi*4]
0x1004f5e5  lea     eax, [ebp+var_44]
0x1004f5e8  push    eax; struct Err *
0x1004f5e9  push    ebx; unsigned int
0x1004f5ea  mov     ecx, esi; this
0x1004f5ec  call    ?SurrenderMemory@Database@@QAEKKAAVErr@@@Z; Database::SurrenderMemory(ulong,Err &)
0x1004f5f1  add     [ebp+var_10], eax
0x1004f5f4  mov     ecx, esi; this
0x1004f5f6  lea     eax, [ebp+var_44]
0x1004f5f9  push    eax; struct Err *
0x1004f5fa  call    ?WriteDirtyPages@Database@@QAEXAAVErr@@@Z; Database::WriteDirtyPages(Err &)
0x1004f5ff  mov     eax, [ebp+var_44]
0x1004f602  test    al, 8
0x1004f604  jz      short loc_1004F633
0x1004f606  lea     edi, [esi+70h]
0x1004f609  push    edi; lpCriticalSection
0x1004f60a  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1004f610  mov     eax, [ebp+var_44]
0x1004f613  lea     ecx, [esi+0C4h]
0x1004f619  cmp     eax, [ecx]
0x1004f61b  jle     short loc_1004F626
0x1004f61d  lea     eax, [ebp+var_44]
0x1004f620  push    eax
0x1004f621  call    ??4Err@@QAEAAV0@ABV0@@Z; Err::operator=(Err const &)
0x1004f626  push    edi; lpCriticalSection
0x1004f627  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1004f62d  mov     eax, [ebp+var_44]
0x1004f630  mov     edi, [ebp+var_18]
0x1004f633  mov     ecx, [ebp+var_10]
0x1004f636  cmp     ecx, ebx
0x1004f638  jnb     short loc_1004F678
0x1004f63a  sub     ebx, ecx
0x1004f63c  test    eax, 0FFFFFFFEh
0x1004f641  jz      short loc_1004F663
0x1004f643  mov     eax, [ebp+Block]
0x1004f646  test    eax, eax
0x1004f648  jz      short loc_1004F653
0x1004f64a  push    eax; Block
0x1004f64b  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004f650  add     esp, 4
0x1004f653  mov     eax, [ebp+var_34]
0x1004f656  test    eax, eax
0x1004f658  jz      short loc_1004F663
0x1004f65a  push    eax; Block
0x1004f65b  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004f660  add     esp, 4
0x1004f663  mov     esi, [ebp+Parameter]
0x1004f666  inc     edi
0x1004f667  mov     [ebp+var_18], edi
0x1004f66a  cmp     edi, [esi+0ACh]
0x1004f670  jb      loc_1004F5D1
0x1004f676  jmp     short loc_1004F6A2
0x1004f678  test    eax, 0FFFFFFFEh
0x1004f67d  jz      short loc_1004F69F
0x1004f67f  mov     eax, [ebp+Block]
0x1004f682  test    eax, eax
0x1004f684  jz      short loc_1004F68F
0x1004f686  push    eax; Block
0x1004f687  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004f68c  add     esp, 4
0x1004f68f  mov     eax, [ebp+var_34]
0x1004f692  test    eax, eax
0x1004f694  jz      short loc_1004F69F
0x1004f696  push    eax; Block
0x1004f697  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004f69c  add     esp, 4
0x1004f69f  mov     esi, [ebp+Parameter]
0x1004f6a2  lea     eax, [esi+0B0h]
0x1004f6a8  mov     dword ptr [esi+0C8h], 0
0x1004f6b2  push    eax; lpCriticalSection
0x1004f6b3  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1004f6b9  mov     ebx, [ebp+var_14]
0x1004f6bc  push    18h; jumptable 1004F44F default case
0x1004f6be  push    ebx; Block
0x1004f6bf  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1004f6c4  add     esp, 8
0x1004f6c7  lea     ecx, [esi+1Ch]
0x1004f6ca  test    [ebp+var_30], 0FFFFFFFEh
0x1004f6d1  jz      loc_1004F410
0x1004f6d7  mov     eax, [ebp+var_24]
0x1004f6da  test    eax, eax
0x1004f6dc  jz      short loc_1004F6EB
0x1004f6de  test    eax, eax
0x1004f6e0  jz      short loc_1004F6EB
0x1004f6e2  push    eax; Block
0x1004f6e3  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004f6e8  add     esp, 4
0x1004f6eb  mov     eax, [ebp+var_20]
0x1004f6ee  lea     ecx, [esi+1Ch]
0x1004f6f1  test    eax, eax
0x1004f6f3  jz      loc_1004F410
0x1004f6f9  lea     ecx, [esi+1Ch]
0x1004f6fc  push    eax; Block
0x1004f6fd  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004f702  add     esp, 4
0x1004f705  jmp     loc_1004F409
0x1004f70a  push    18h; jumptable 1004F44F case 0
0x1004f70c  push    ebx; Block
0x1004f70d  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1004f712  add     esp, 8
0x1004f715  lock dec dword_10066974
0x1004f71c  test    [ebp+var_30], 0FFFFFFFEh
0x1004f723  jz      short loc_1004F745
0x1004f725  mov     eax, [ebp+var_24]
0x1004f728  test    eax, eax
0x1004f72a  jz      short loc_1004F735
0x1004f72c  push    eax; Block
0x1004f72d  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004f732  add     esp, 4
0x1004f735  mov     eax, [ebp+var_20]
0x1004f738  test    eax, eax
0x1004f73a  jz      short loc_1004F745
0x1004f73c  push    eax; Block
0x1004f73d  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004f742  add     esp, 4
0x1004f745  push    [ebp+hObject]; hObject
0x1004f748  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1004f74e  test    [ebp+var_58], 0FFFFFFFEh
0x1004f755  jz      short loc_1004F777
0x1004f757  mov     eax, [ebp+var_4C]
0x1004f75a  test    eax, eax
0x1004f75c  jz      short loc_1004F767
0x1004f75e  push    eax; Block
0x1004f75f  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004f764  add     esp, 4
0x1004f767  mov     eax, [ebp+var_48]
0x1004f76a  test    eax, eax
0x1004f76c  jz      short loc_1004F777
0x1004f76e  push    eax; Block
0x1004f76f  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004f774  add     esp, 4
0x1004f777  xor     eax, eax
0x1004f779  mov     ecx, [ebp+var_C]
0x1004f77c  mov     large fs:0, ecx
0x1004f783  pop     ecx
0x1004f784  pop     edi
0x1004f785  pop     esi
0x1004f786  pop     ebx
0x1004f787  mov     esp, ebp
  ... truncated ...
```
