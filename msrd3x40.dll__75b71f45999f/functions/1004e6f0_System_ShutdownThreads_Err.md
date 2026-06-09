# System::ShutdownThreads(Err &)

- ea: `0x1004e6f0`
- end: `0x1004e924`
- name: `?ShutdownThreads@System@@QAEXAAVErr@@@Z`
- size: `564`
- prototype: `void __thiscall(struct Err *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x10027bf0`

## callees

- `0x10012dd0`
- `0x1004e6f0`
- `0x1004eda0`
- `0x1005ce60`
- `0x1005e74d`
- `0x1005e798`
- `0x1005e7e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1004e7fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1004e7fe`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1004e84b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1004e889`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1004e84b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1004e889`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1004e8ce`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1004e8ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1004e83f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1004e83f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1004e85d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1004e89b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1004e85d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1004e89b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1004e764`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1004e764`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1004e8d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1004e8d6`

## pseudocode

```c
void __thiscall System::ShutdownThreads(struct Err *this, void **a2)
{
  unsigned int v2; // edi
  unsigned int i; // ecx
  HANDLE *v4; // eax
  unsigned int v5; // edi
  char *v6; // edi
  int v7; // ecx
  struct Err *v8; // ecx
  struct Err *v9; // ecx
  unsigned int j; // edi
  HANDLE *v11; // esi
  unsigned int v12; // [esp+Ch] [ebp-1Ch]
  __int64 v13; // [esp+1Ch] [ebp-Ch]
  int v14; // [esp+24h] [ebp-4h]

  if ( dword_100668B8 )
  {
    Queue::CancelMessages(&stru_100668BC, 0, (struct Err *)a2);
    if ( ((unsigned int)*a2 & 0xFFFFFFFE) != 0 )
    {
      if ( a2[3] )
        operator delete[](a2[3]);
      if ( a2[4] )
        operator delete[](a2[4]);
    }
    *a2 = (void *)1;
    v2 = 0;
    for ( i = dword_100668B4; v2 < i; ++v2 )
    {
      v4 = (HANDLE *)*((_DWORD *)dword_100668B8 + v2);
      if ( v4 )
      {
        SetThreadPriority(*v4, 2);
        i = dword_100668B4;
      }
    }
    v5 = 0;
    v12 = 0;
    if ( i )
    {
      while ( 1 )
      {
        if ( ((unsigned int)*a2 & 0xFFFFFFFE) != 0 )
        {
          if ( a2[3] )
            operator delete[](a2[3]);
          if ( a2[4] )
            operator delete[](a2[4]);
        }
        *a2 = (void *)1;
        if ( !*((_DWORD *)dword_100668B8 + v5) )
          goto LABEL_25;
        v6 = (char *)operator new(0x18u);
        *(_QWORD *)(v6 + 12) = v13;
        *((_DWORD *)v6 + 5) = v14;
        *(_DWORD *)v6 = 0;
        *((_DWORD *)v6 + 1) = 0;
        *((_DWORD *)v6 + 2) = 0;
        *((_DWORD *)v6 + 3) = 0;
        EnterCriticalSection(&stru_100668BC);
        v7 = dword_100668E0;
        if ( dword_100668E0 < (unsigned int)dword_100668DC )
          goto LABEL_21;
        Collection::Grow((Collection *)&dword_100668D8, dword_100668E0 + 1, (struct Err *)a2);
        if ( (*(_BYTE *)a2 & 8) == 0 )
          break;
LABEL_22:
        LeaveCriticalSection(&stru_100668BC);
        if ( !SetEvent(hEvent) )
          System::ErrGetLastError(v8);
        Sleep(0xAu);
        v5 = v12;
LABEL_25:
        i = dword_100668B4;
        v12 = ++v5;
        if ( v5 >= dword_100668B4 )
          goto LABEL_26;
      }
      v7 = dword_100668E0;
LABEL_21:
      *(_DWORD *)(dword_100668D8 + 4 * v7) = v6;
      ++dword_100668E0;
      goto LABEL_22;
    }
LABEL_26:
    if ( dword_10066974 )
    {
      do
      {
        if ( !SetEvent(hEvent) )
          System::ErrGetLastError(v9);
        Sleep(0xAu);
      }
      while ( dword_10066974 );
      i = dword_100668B4;
    }
    for ( j = 0; j < i; ++j )
    {
      v11 = (HANDLE *)*((_DWORD *)dword_100668B8 + j);
      if ( v11 )
      {
        if ( *v11 )
        {
          WaitForSingleObject(*v11, 0x3E8u);
          CloseHandle(*v11);
          *v11 = 0;
        }
        operator delete(v11, 4u);
        *((_DWORD *)dword_100668B8 + j) = 0;
        i = dword_100668B4;
      }
    }
    operator delete[](dword_100668B8);
    dword_100668B8 = 0;
  }
}

```

## disassembly

```asm
0x1004e6f0  mov     edi, edi
0x1004e6f2  push    ebp
0x1004e6f3  mov     ebp, esp
0x1004e6f5  and     esp, 0FFFFFFF8h
0x1004e6f8  sub     esp, 20h
0x1004e6fb  cmp     dword_100668B8, 0
0x1004e702  push    esi
0x1004e703  push    edi
0x1004e704  jz      loc_1004E91C
0x1004e70a  mov     esi, [ebp+arg_0]
0x1004e70d  mov     ecx, offset stru_100668BC; lpCriticalSection
0x1004e712  push    esi; struct Err *
0x1004e713  push    0; struct Database *
0x1004e715  call    ?CancelMessages@Queue@@QAEKPAVDatabase@@AAVErr@@@Z; Queue::CancelMessages(Database *,Err &)
0x1004e71a  test    dword ptr [esi], 0FFFFFFFEh
0x1004e720  jz      short loc_1004E742
0x1004e722  mov     eax, [esi+0Ch]
0x1004e725  test    eax, eax
0x1004e727  jz      short loc_1004E732
0x1004e729  push    eax; Block
0x1004e72a  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004e72f  add     esp, 4
0x1004e732  mov     eax, [esi+10h]
0x1004e735  test    eax, eax
0x1004e737  jz      short loc_1004E742
0x1004e739  push    eax; Block
0x1004e73a  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004e73f  add     esp, 4
0x1004e742  mov     dword ptr [esi], 1
0x1004e748  xor     edi, edi
0x1004e74a  mov     ecx, dword_100668B4
0x1004e750  test    ecx, ecx
0x1004e752  jz      short loc_1004E775
0x1004e754  mov     eax, dword_100668B8
0x1004e759  mov     eax, [eax+edi*4]
0x1004e75c  test    eax, eax
0x1004e75e  jz      short loc_1004E770
0x1004e760  push    2; nPriority
0x1004e762  push    dword ptr [eax]; hThread
0x1004e764  call    ds:__imp__SetThreadPriority@8; SetThreadPriority(x,x)
0x1004e76a  mov     ecx, dword_100668B4
0x1004e770  inc     edi
0x1004e771  cmp     edi, ecx
0x1004e773  jb      short loc_1004E754
0x1004e775  xor     edi, edi
0x1004e777  mov     [esp+28h+var_1C], edi
0x1004e77b  test    ecx, ecx
0x1004e77d  jz      loc_1004E87A
0x1004e783  test    dword ptr [esi], 0FFFFFFFEh
0x1004e789  jz      short loc_1004E7AB
0x1004e78b  mov     eax, [esi+0Ch]
0x1004e78e  test    eax, eax
0x1004e790  jz      short loc_1004E79B
0x1004e792  push    eax; Block
0x1004e793  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004e798  add     esp, 4
0x1004e79b  mov     eax, [esi+10h]
0x1004e79e  test    eax, eax
0x1004e7a0  jz      short loc_1004E7AB
0x1004e7a2  push    eax; Block
0x1004e7a3  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004e7a8  add     esp, 4
0x1004e7ab  mov     dword ptr [esi], 1
0x1004e7b1  mov     eax, dword_100668B8
0x1004e7b6  cmp     dword ptr [eax+edi*4], 0
0x1004e7ba  jz      loc_1004E867
0x1004e7c0  push    18h; Size
0x1004e7c2  call    ??2@YAPAXI@Z; operator new(uint)
0x1004e7c7  movq    xmm0, [esp+2Ch+var_C]
0x1004e7cd  mov     edi, eax
0x1004e7cf  mov     ecx, [esp+2Ch+var_4]
0x1004e7d3  add     esp, 4
0x1004e7d6  movq    qword ptr [edi+0Ch], xmm0
0x1004e7db  mov     [edi+14h], ecx
0x1004e7de  push    offset stru_100668BC; lpCriticalSection
0x1004e7e3  mov     dword ptr [edi], 0
0x1004e7e9  mov     dword ptr [edi+4], 0
0x1004e7f0  mov     dword ptr [edi+8], 0
0x1004e7f7  mov     dword ptr [edi+0Ch], 0
0x1004e7fe  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1004e804  mov     ecx, dword_100668E0
0x1004e80a  cmp     ecx, dword_100668DC
0x1004e810  jb      short loc_1004E82C
0x1004e812  lea     eax, [ecx+1]
0x1004e815  mov     ecx, offset dword_100668D8; this
0x1004e81a  push    esi; struct Err *
0x1004e81b  push    eax; unsigned int
0x1004e81c  call    ?Grow@Collection@@QAEXKAAVErr@@@Z; Collection::Grow(ulong,Err &)
0x1004e821  test    byte ptr [esi], 8
0x1004e824  jnz     short loc_1004E83A
0x1004e826  mov     ecx, dword_100668E0
0x1004e82c  mov     eax, dword_100668D8
0x1004e831  mov     [eax+ecx*4], edi
0x1004e834  inc     dword_100668E0
0x1004e83a  push    offset stru_100668BC; lpCriticalSection
0x1004e83f  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1004e845  push    hEvent; hEvent
0x1004e84b  call    ds:__imp__SetEvent@4; SetEvent(x)
0x1004e851  test    eax, eax
0x1004e853  jnz     short loc_1004E85B
0x1004e855  push    esi
0x1004e856  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x1004e85b  push    0Ah; dwMilliseconds
0x1004e85d  call    ds:__imp__Sleep@4; Sleep(x)
0x1004e863  mov     edi, [esp+28h+var_1C]
0x1004e867  mov     ecx, dword_100668B4
0x1004e86d  inc     edi
0x1004e86e  mov     [esp+28h+var_1C], edi
0x1004e872  cmp     edi, ecx
0x1004e874  jb      loc_1004E783
0x1004e87a  cmp     dword_10066974, 0
0x1004e881  jz      short loc_1004E8B0
0x1004e883  push    hEvent; hEvent
0x1004e889  call    ds:__imp__SetEvent@4; SetEvent(x)
0x1004e88f  test    eax, eax
0x1004e891  jnz     short loc_1004E899
0x1004e893  push    esi
0x1004e894  call    ?ErrGetLastError@System@@QAEJAAVErr@@@Z; System::ErrGetLastError(Err &)
0x1004e899  push    0Ah; dwMilliseconds
0x1004e89b  call    ds:__imp__Sleep@4; Sleep(x)
0x1004e8a1  cmp     dword_10066974, 0
0x1004e8a8  jnz     short loc_1004E883
0x1004e8aa  mov     ecx, dword_100668B4
0x1004e8b0  xor     edi, edi
0x1004e8b2  test    ecx, ecx
0x1004e8b4  jz      short loc_1004E904
0x1004e8b6  mov     eax, dword_100668B8
0x1004e8bb  mov     esi, [eax+edi*4]
0x1004e8be  test    esi, esi
0x1004e8c0  jz      short loc_1004E8FF
0x1004e8c2  mov     eax, [esi]
0x1004e8c4  test    eax, eax
0x1004e8c6  jz      short loc_1004E8E2
0x1004e8c8  push    3E8h; dwMilliseconds
0x1004e8cd  push    eax; hHandle
0x1004e8ce  call    ds:__imp__WaitForSingleObject@8; WaitForSingleObject(x,x)
0x1004e8d4  push    dword ptr [esi]; hObject
0x1004e8d6  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1004e8dc  mov     dword ptr [esi], 0
0x1004e8e2  push    4; unsigned int
0x1004e8e4  push    esi; Block
0x1004e8e5  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1004e8ea  mov     eax, dword_100668B8
0x1004e8ef  add     esp, 8
0x1004e8f2  mov     dword ptr [eax+edi*4], 0
0x1004e8f9  mov     ecx, dword_100668B4
0x1004e8ff  inc     edi
0x1004e900  cmp     edi, ecx
0x1004e902  jb      short loc_1004E8B6
0x1004e904  push    dword_100668B8; Block
0x1004e90a  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004e90f  add     esp, 4
0x1004e912  mov     dword_100668B8, 0
0x1004e91c  pop     edi
0x1004e91d  pop     esi
0x1004e91e  mov     esp, ebp
0x1004e920  pop     ebp
0x1004e921  retn    4
```
