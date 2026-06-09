# CVSyncProvider::AddClient(VSyncClientInfo const *,ulong *)

- ea: `0x1806cf000`
- end: `0x1806cf2eb`
- name: `?AddClient@CVSyncProvider@@UEAAJPEBUVSyncClientInfo@@PEAK@Z`
- size: `747`
- prototype: `__int64 __fastcall(CVSyncProvider *__hidden this, const struct VSyncClientInfo *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x1801cd5ac`
- `0x1805559a0`
- `0x1806847a8`
- `0x1806cf000`
- `0x18072a270`
- `0x181076570`
- `0x181076624`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x1806cf16a`
- `KERNEL32!MapViewOfFile` at `0x1806cf16a`
- `KERNEL32!OpenProcess` at `0x1806cf093`
- `KERNEL32!OpenProcess` at `0x1806cf093`
- `KERNEL32!UnmapViewOfFile` at `0x1806cf17c`
- `KERNEL32!UnmapViewOfFile` at `0x1806cf17c`
- `KERNEL32!LeaveCriticalSection` at `0x1806cf2b4`
- `KERNEL32!LeaveCriticalSection` at `0x1806cf2b4`
- `KERNEL32!EnterCriticalSection` at `0x1806cf205`
- `KERNEL32!EnterCriticalSection` at `0x1806cf205`
- `KERNEL32!SetEvent` at `0x1806cf2ab`
- `KERNEL32!SetEvent` at `0x1806cf2ab`
- `KERNEL32!GetCurrentProcess` at `0x1806cf119`
- `KERNEL32!GetCurrentProcess` at `0x1806cf1b0`
- `KERNEL32!GetCurrentProcess` at `0x1806cf119`
- `KERNEL32!GetCurrentProcess` at `0x1806cf1b0`
- `USER32!PostMessageW` at `0x1806cf26f`
- `USER32!PostMessageW` at `0x1806cf26f`
- `USER32!GetWindowThreadProcessId` at `0x1806cf102`
- `USER32!GetWindowThreadProcessId` at `0x1806cf102`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1806cf13f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1806cf1d6`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1806cf13f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1806cf1d6`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessIdOfThread` at `0x1806cf0ec`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessIdOfThread` at `0x1806cf0ec`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1806cf0bf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1806cf0bf`

## pseudocode

```c
__int64 __fastcall CVSyncProvider::AddClient(CVSyncProvider *this, const struct VSyncClientInfo *a2, unsigned int *a3)
{
  _QWORD *v3; // rax
  _QWORD *v4; // rsi
  __int128 v5; // xmm1
  unsigned int v6; // edx
  void *v7; // rbx
  unsigned int v8; // ebx
  void *v9; // rcx
  int v10; // edi
  DWORD WindowThreadProcessId; // eax
  HANDLE CurrentProcess; // rax
  _DWORD *v13; // rax
  const void *v14; // rcx
  _DWORD *v15; // rdi
  HANDLE v16; // rax
  unsigned int v17; // edx
  __int64 v18; // rdx
  DWORD dwProcessId; // [rsp+40h] [rbp-30h] BYREF
  _QWORD *v21; // [rsp+48h] [rbp-28h] BYREF
  HANDLE v22; // [rsp+50h] [rbp-20h] BYREF
  HANDLE TargetHandle; // [rsp+58h] [rbp-18h] BYREF
  HANDLE v24[2]; // [rsp+60h] [rbp-10h] BYREF

  v3 = (_QWORD *)MemoryProtection::HeapAllocClear<1>(g_hProcessHeap, 88);
  v4 = v3;
  if ( v3 )
  {
    *v3 = v3;
    v3[1] = v3;
    v3[2] = 0;
    v3[3] = 0;
    v3[4] = 0;
    v3[5] = 0;
    v3[7] = 0;
    v3[9] = 0;
    v3[10] = 0;
  }
  else
  {
    v4 = 0;
  }
  v21 = v4;
  v5 = *((_OWORD *)a2 + 1);
  *((_OWORD *)v4 + 1) = *(_OWORD *)a2;
  *((_OWORD *)v4 + 2) = v5;
  v4[4] = 0;
  v4[3] = 0;
  v22 = OpenProcess(0x100040u, 0, *((_DWORD *)v4 + 4));
  v7 = v22;
  if ( v22 )
  {
    v24[0] = OpenThread(0x100040u, 0, *((_DWORD *)v4 + 5));
    TSmartHandle<void *,&int CloseHandle(void *)>::operator=(v4 + 9, v24);
    v9 = (void *)v4[9];
    if ( v9
      && (v10 = *((_DWORD *)v4 + 4), GetProcessIdOfThread(v9) == v10)
      && (dwProcessId = 0,
          WindowThreadProcessId = GetWindowThreadProcessId((HWND)v4[5], &dwProcessId),
          dwProcessId == *((_DWORD *)v4 + 4))
      && WindowThreadProcessId == *((_DWORD *)v4 + 5) )
    {
      TargetHandle = 0;
      CurrentProcess = GetCurrentProcess();
      if ( !DuplicateHandle(v7, *((HANDLE *)a2 + 1), CurrentProcess, &TargetHandle, 0, 0, 2u) )
        goto LABEL_12;
      v13 = MapViewOfFile(TargetHandle, 6u, 0, 0, 0x28u);
      v14 = (const void *)v4[7];
      v15 = v13;
      if ( v14 )
        UnmapViewOfFile(v14);
      v4[7] = v15;
      if ( v15
        && (v4[8] = v15, *v15 == -838796627)
        && *(_DWORD *)(v4[8] + 4LL) == 1
        && *(_DWORD *)(v4[8] + 8LL) >= 0x28u
        && (v16 = GetCurrentProcess(), DuplicateHandle(v7, *((HANDLE *)a2 + 2), v16, (LPHANDLE)v4 + 10, 0, 0, 2u)) )
      {
        v4[4] = v4[10];
        if ( *((_DWORD *)this + 20) >= 0x3Eu )
          CVSyncProvider::PruneDeadClients(this);
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
        if ( *((_DWORD *)this + 20) < 0x3Eu )
        {
          v8 = 0;
          if ( *((_BYTE *)this + 104) )
          {
            *(_DWORD *)(v4[8] + 20LL) = *((_DWORD *)this + 27);
            *(_DWORD *)(v4[8] + 16LL) = 1;
            if ( *(int *)(v4[8] + 20LL) < 0 )
              PostMessageW((HWND)v4[5], 0x402u, *(int *)(v4[8] + 20LL), *(unsigned int *)(v4[8] + 36LL));
          }
          v17 = *((_DWORD *)this + 21);
          v21 = 0;
          *((_DWORD *)this + 21) = v17 + 1;
          *((_DWORD *)v4 + 12) = v17;
          *a3 = v17;
          v18 = *((_QWORD *)this + 7);
          v4[1] = (char *)this + 56;
          *v4 = v18;
          *(_QWORD *)(v18 + 8) = v4;
          *(_QWORD *)v4[1] = v4;
          ++*((_DWORD *)this + 20);
          SetEvent(*((HANDLE *)this + 12));
        }
        else
        {
          v8 = -2147467259;
          *(_DWORD *)(v4[8] + 16LL) = 1;
          *(_DWORD *)(v4[8] + 20LL) = -2147467259;
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
      }
      else
      {
LABEL_12:
        v8 = -2147418113;
      }
      TSmartHandle<void *,&int CloseHandle(void *)>::~TSmartHandle<void *,&int CloseHandle(void *)>(&TargetHandle);
    }
    else
    {
      v8 = -2147418113;
    }
    TSmartHandle<void *,&int CloseHandle(void *)>::~TSmartHandle<void *,&int CloseHandle(void *)>(&v22);
    TSmartMemory<CVSyncProvider::VSyncClient>::~TSmartMemory<CVSyncProvider::VSyncClient>(&v21);
  }
  else
  {
    v8 = -2147418113;
    CVSyncProvider::VSyncClient::`scalar deleting destructor'((CVSyncProvider::VSyncClient *)v4, v6);
  }
  return v8;
}

```

## disassembly

```asm
0x1806cf000  mov     rax, rsp
0x1806cf003  mov     [rax+20h], rbx
0x1806cf007  mov     [rax+18h], r8
0x1806cf00b  mov     [rax+10h], rdx
0x1806cf00f  mov     [rax+8], rcx
0x1806cf013  push    rbp
0x1806cf014  push    rsi
0x1806cf015  push    rdi
0x1806cf016  push    r14
0x1806cf018  push    r15
0x1806cf01a  mov     rbp, rsp
0x1806cf01d  sub     rsp, 70h
0x1806cf021  mov     rcx, cs:g_hProcessHeap
0x1806cf028  mov     edx, 58h ; 'X'
0x1806cf02d  call    ??$HeapAllocClear@$00@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAllocClear<1>(void *,unsigned __int64)
0x1806cf032  xor     r15d, r15d
0x1806cf035  mov     rsi, rax
0x1806cf038  test    rax, rax
0x1806cf03b  jz      short loc_1806CF062
0x1806cf03d  mov     [rax], rax
0x1806cf040  mov     [rax+8], rax
0x1806cf044  mov     [rax+10h], r15
0x1806cf048  mov     [rax+18h], r15
0x1806cf04c  mov     [rax+20h], r15
0x1806cf050  mov     [rax+28h], r15
0x1806cf054  mov     [rax+38h], r15
0x1806cf058  mov     [rax+48h], r15
0x1806cf05c  mov     [rax+50h], r15
0x1806cf060  jmp     short loc_1806CF065
0x1806cf062  mov     rsi, r15
0x1806cf065  mov     r14, [rbp+arg_8]
0x1806cf069  mov     edi, 100040h
0x1806cf06e  xor     edx, edx; bInheritHandle
0x1806cf070  mov     [rbp+var_28], rsi
0x1806cf074  mov     ecx, edi; dwDesiredAccess
0x1806cf076  movups  xmm0, xmmword ptr [r14]
0x1806cf07a  movups  xmm1, xmmword ptr [r14+10h]
0x1806cf07f  movups  xmmword ptr [rsi+10h], xmm0
0x1806cf083  movups  xmmword ptr [rsi+20h], xmm1
0x1806cf087  mov     [rsi+20h], r15
0x1806cf08b  mov     [rsi+18h], r15
0x1806cf08f  mov     r8d, [rsi+10h]; dwProcessId
0x1806cf093  call    cs:__imp_OpenProcess
0x1806cf099  mov     [rbp+var_20], rax
0x1806cf09d  mov     rbx, rax
0x1806cf0a0  test    rax, rax
0x1806cf0a3  jnz     short loc_1806CF0B7
0x1806cf0a5  mov     rcx, rsi; this
0x1806cf0a8  mov     ebx, 8000FFFFh
0x1806cf0ad  call    ??_GVSyncClient@CVSyncProvider@@QEAAPEAXI@Z; CVSyncProvider::VSyncClient::`scalar deleting destructor'(uint)
0x1806cf0b2  jmp     loc_1806CF2D5
0x1806cf0b7  mov     r8d, [rsi+14h]; dwThreadId
0x1806cf0bb  xor     edx, edx; bInheritHandle
0x1806cf0bd  mov     ecx, edi; dwDesiredAccess
0x1806cf0bf  call    cs:__imp_OpenThread
0x1806cf0c5  lea     rdx, [rbp+var_10]
0x1806cf0c9  mov     [rbp+var_10], rax
0x1806cf0cd  lea     rcx, [rsi+48h]
0x1806cf0d1  call    ??4?$TSmartHandle@PEAX$1?CloseHandle@@YAHPEAX@Z@@QEAAAEAPEAXAEBQEAX@Z; TSmartHandle<void *,&CloseHandle(void *)>::operator=(void * const &)
0x1806cf0d6  mov     rcx, [rsi+48h]; Thread
0x1806cf0da  test    rcx, rcx
0x1806cf0dd  jnz     short loc_1806CF0E9
0x1806cf0df  mov     ebx, 8000FFFFh
0x1806cf0e4  jmp     loc_1806CF2C3
0x1806cf0e9  mov     edi, [rsi+10h]
0x1806cf0ec  call    cs:__imp_GetProcessIdOfThread
0x1806cf0f2  cmp     eax, edi
0x1806cf0f4  jnz     short loc_1806CF0DF
0x1806cf0f6  mov     [rbp+dwProcessId], r15d
0x1806cf0fa  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x1806cf0fe  mov     rcx, [rsi+28h]; hWnd
0x1806cf102  call    cs:__imp_GetWindowThreadProcessId
0x1806cf108  mov     ecx, [rsi+10h]
0x1806cf10b  cmp     [rbp+dwProcessId], ecx
0x1806cf10e  jnz     short loc_1806CF0DF
0x1806cf110  cmp     eax, [rsi+14h]
0x1806cf113  jnz     short loc_1806CF0DF
0x1806cf115  mov     [rbp+TargetHandle], r15
0x1806cf119  call    cs:__imp_GetCurrentProcess
0x1806cf11f  mov     rdx, [r14+8]; hSourceHandle
0x1806cf123  lea     r9, [rbp+TargetHandle]; lpTargetHandle
0x1806cf127  mov     [rsp+70h+dwOptions], 2; dwOptions
0x1806cf12f  mov     r8, rax; hTargetProcessHandle
0x1806cf132  mov     [rsp+70h+bInheritHandle], r15d; bInheritHandle
0x1806cf137  mov     rcx, rbx; hSourceProcessHandle
0x1806cf13a  mov     [rsp+70h+dwDesiredAccess], r15d; dwDesiredAccess
0x1806cf13f  call    cs:__imp_DuplicateHandle
0x1806cf145  test    eax, eax
0x1806cf147  jnz     short loc_1806CF153
0x1806cf149  mov     ebx, 8000FFFFh
0x1806cf14e  jmp     loc_1806CF2BA
0x1806cf153  mov     rcx, [rbp+TargetHandle]; hFileMappingObject
0x1806cf157  xor     r9d, r9d; dwFileOffsetLow
0x1806cf15a  xor     r8d, r8d; dwFileOffsetHigh
0x1806cf15d  mov     qword ptr [rsp+70h+dwDesiredAccess], 28h ; '('; dwNumberOfBytesToMap
0x1806cf166  lea     edx, [r9+6]; dwDesiredAccess
0x1806cf16a  call    cs:__imp_MapViewOfFile
0x1806cf170  mov     rcx, [rsi+38h]; lpBaseAddress
0x1806cf174  mov     rdi, rax
0x1806cf177  test    rcx, rcx
0x1806cf17a  jz      short loc_1806CF182
0x1806cf17c  call    cs:__imp_UnmapViewOfFile
0x1806cf182  mov     [rsi+38h], rdi
0x1806cf186  test    rdi, rdi
0x1806cf189  jz      short loc_1806CF149
0x1806cf18b  mov     [rsi+40h], rdi
0x1806cf18f  mov     eax, [rdi]
0x1806cf191  cmp     eax, 0CE00FAADh
0x1806cf196  jnz     short loc_1806CF149
0x1806cf198  mov     rax, [rsi+40h]
0x1806cf19c  mov     ecx, [rax+4]
0x1806cf19f  cmp     ecx, 1
0x1806cf1a2  jnz     short loc_1806CF149
0x1806cf1a4  mov     rax, [rsi+40h]
0x1806cf1a8  mov     ecx, [rax+8]
0x1806cf1ab  cmp     ecx, 28h ; '('
0x1806cf1ae  jb      short loc_1806CF149
0x1806cf1b0  call    cs:__imp_GetCurrentProcess
0x1806cf1b6  mov     rdx, [r14+10h]; hSourceHandle
0x1806cf1ba  lea     r9, [rsi+50h]; lpTargetHandle
0x1806cf1be  mov     [rsp+70h+dwOptions], 2; dwOptions
0x1806cf1c6  mov     r8, rax; hTargetProcessHandle
0x1806cf1c9  mov     [rsp+70h+bInheritHandle], r15d; bInheritHandle
0x1806cf1ce  mov     rcx, rbx; hSourceProcessHandle
0x1806cf1d1  mov     [rsp+70h+dwDesiredAccess], r15d; dwDesiredAccess
0x1806cf1d6  call    cs:__imp_DuplicateHandle
0x1806cf1dc  test    eax, eax
0x1806cf1de  jz      loc_1806CF149
0x1806cf1e4  mov     rdi, [rbp+arg_0]
0x1806cf1e8  mov     rax, [rsi+50h]
0x1806cf1ec  mov     [rsi+20h], rax
0x1806cf1f0  cmp     dword ptr [rdi+50h], 3Eh ; '>'
0x1806cf1f4  jb      short loc_1806CF1FE
0x1806cf1f6  mov     rcx, rdi; this
0x1806cf1f9  call    ?PruneDeadClients@CVSyncProvider@@AEAAXXZ; CVSyncProvider::PruneDeadClients(void)
0x1806cf1fe  lea     r14, [rdi+8]
0x1806cf202  mov     rcx, r14; lpCriticalSection
0x1806cf205  call    cs:__imp_EnterCriticalSection
0x1806cf20b  cmp     dword ptr [rdi+50h], 3Eh ; '>'
0x1806cf20f  jb      short loc_1806CF22D
0x1806cf211  mov     rax, [rsi+40h]
0x1806cf215  mov     ebx, 80004005h
0x1806cf21a  mov     dword ptr [rax+10h], 1
0x1806cf221  mov     rax, [rsi+40h]
0x1806cf225  mov     [rax+14h], ebx
0x1806cf228  jmp     loc_1806CF2B1
0x1806cf22d  mov     ebx, r15d
0x1806cf230  cmp     [rdi+68h], r15b
0x1806cf234  jz      short loc_1806CF275
0x1806cf236  mov     rcx, [rsi+40h]
0x1806cf23a  mov     eax, [rdi+6Ch]
0x1806cf23d  mov     [rcx+14h], eax
0x1806cf240  mov     rax, [rsi+40h]
0x1806cf244  mov     dword ptr [rax+10h], 1
0x1806cf24b  mov     rax, [rsi+40h]
0x1806cf24f  mov     ecx, [rax+14h]
0x1806cf252  test    ecx, ecx
0x1806cf254  jns     short loc_1806CF275
0x1806cf256  mov     rax, [rsi+40h]
0x1806cf25a  mov     edx, 402h; Msg
0x1806cf25f  mov     r9d, [rax+24h]; lParam
0x1806cf263  mov     rax, [rsi+40h]
0x1806cf267  movsxd  r8, dword ptr [rax+14h]; wParam
0x1806cf26b  mov     rcx, [rsi+28h]; hWnd
0x1806cf26f  call    cs:__imp_PostMessageW
0x1806cf275  mov     edx, [rdi+54h]
0x1806cf278  mov     [rbp+var_28], r15
0x1806cf27c  lea     eax, [rdx+1]
0x1806cf27f  mov     [rdi+54h], eax
0x1806cf282  mov     rax, [rbp+arg_10]
0x1806cf286  mov     [rsi+30h], edx
0x1806cf289  mov     [rax], edx
0x1806cf28b  lea     rax, [rdi+38h]
0x1806cf28f  mov     rdx, [rax]
0x1806cf292  mov     [rsi+8], rax
0x1806cf296  mov     [rsi], rdx
0x1806cf299  mov     [rdx+8], rsi
0x1806cf29d  mov     rax, [rsi+8]
0x1806cf2a1  mov     [rax], rsi
0x1806cf2a4  inc     dword ptr [rdi+50h]
0x1806cf2a7  mov     rcx, [rdi+60h]; hEvent
0x1806cf2ab  call    cs:__imp_SetEvent
0x1806cf2b1  mov     rcx, r14; lpCriticalSection
0x1806cf2b4  call    cs:__imp_LeaveCriticalSection
0x1806cf2ba  lea     rcx, [rbp+TargetHandle]
0x1806cf2be  call    ??1?$TSmartHandle@PEAX$1?CloseHandle@@YAHPEAX@Z@@QEAA@XZ; TSmartHandle<void *,&CloseHandle(void *)>::~TSmartHandle<void *,&CloseHandle(void *)>(void)
0x1806cf2c3  lea     rcx, [rbp+var_20]
0x1806cf2c7  call    ??1?$TSmartHandle@PEAX$1?CloseHandle@@YAHPEAX@Z@@QEAA@XZ; TSmartHandle<void *,&CloseHandle(void *)>::~TSmartHandle<void *,&CloseHandle(void *)>(void)
0x1806cf2cc  lea     rcx, [rbp+var_28]
0x1806cf2d0  call    ??1?$TSmartMemory@UVSyncClient@CVSyncProvider@@@@QEAA@XZ; TSmartMemory<CVSyncProvider::VSyncClient>::~TSmartMemory<CVSyncProvider::VSyncClient>(void)
0x1806cf2d5  mov     eax, ebx
0x1806cf2d7  mov     rbx, [rsp+70h+arg_18]
0x1806cf2df  add     rsp, 70h
0x1806cf2e3  pop     r15
0x1806cf2e5  pop     r14
0x1806cf2e7  pop     rdi
0x1806cf2e8  pop     rsi
0x1806cf2e9  pop     rbp
0x1806cf2ea  retn
```
