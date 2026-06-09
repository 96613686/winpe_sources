# InitThreads(DIRECTCOLORCONVFRM *)

- ea: `0x180010f28`
- end: `0x18001117e`
- name: `?InitThreads@@YAHPEAUDIRECTCOLORCONVFRM@@@Z`
- size: `598`
- prototype: `__int64 __fastcall(struct DIRECTCOLORCONVFRM *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011500`

## callees

- `0x180010f28`
- `0x180014410`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001101e`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180011052`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001101e`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180011052`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001106e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001106e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800110bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x1800110bb`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180010fe8`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x180010fe8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800110d2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180011102`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001113f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180011173`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800110d2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180011102`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001113f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180011173`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010fdf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180010fdf`

## pseudocode

```c
__int64 __fastcall InitThreads(struct DIRECTCOLORCONVFRM *a1)
{
  unsigned int v1; // r9d
  unsigned int v3; // edi
  unsigned int v4; // r10d
  unsigned int v5; // r8d
  int v6; // ecx
  HANDLE CurrentThread; // rax
  int ThreadPriority; // esi
  HANDLE Semaphore; // rax
  HANDLE v10; // rax
  HANDLE EventW; // rax
  int v12; // edx
  int v13; // ecx
  void *v14; // rax
  LONG v15; // edx
  void *v16; // rcx
  int v18; // edx
  int v19; // ecx
  void *v20; // rax
  int v21; // edx
  int v22; // ecx
  void *v23; // rax
  int v24; // edx
  int v25; // ecx
  void *v26; // rax
  DWORD dwFlags; // [rsp+20h] [rbp-28h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-28h]
  DWORD dwFlagsb; // [rsp+20h] [rbp-28h]
  DWORD dwFlagsc; // [rsp+20h] [rbp-28h]
  DWORD v31; // [rsp+50h] [rbp+8h] BYREF
  DWORD v32; // [rsp+58h] [rbp+10h] BYREF
  DWORD v33; // [rsp+60h] [rbp+18h] BYREF
  DWORD v34; // [rsp+68h] [rbp+20h] BYREF

  v1 = *((_DWORD *)a1 + 3660);
  v3 = 1;
  if ( v1 > 4 )
  {
    *((_DWORD *)a1 + 3660) = 4;
    v1 = 4;
  }
  v4 = *((_DWORD *)a1 + 3641);
  v5 = (v4 / v1) & 0xFFFFFFFE;
  *((_DWORD *)a1 + 38) = v5;
  if ( ((v4 / v1) & 2) != 0 )
  {
    v5 -= 2;
    *((_DWORD *)a1 + 38) = v5;
  }
  if ( v1 == 1 )
  {
    *((_DWORD *)a1 + 38) = v4;
    v5 = v4;
  }
  v6 = v4;
  if ( v1 != 2 )
    v6 = 2 * v5;
  *((_DWORD *)a1 + 39) = v6;
  if ( v1 == 4 )
    v4 = 3 * v5;
  *((_DWORD *)a1 + 40) = v4;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  if ( v1 >= 2 )
  {
    CurrentThread = GetCurrentThread();
    ThreadPriority = GetThreadPriority(CurrentThread);
    _InterlockedExchange((volatile __int32 *)a1 + 3662, 0);
    _InterlockedExchange((volatile __int32 *)a1 + 3661, 0);
    Semaphore = CreateSemaphoreExW(0, 0, *((_DWORD *)a1 + 3660), 0, 0, 0x1F0003u);
    *((_QWORD *)a1 + 1836) = Semaphore;
    if ( Semaphore )
    {
      v10 = CreateSemaphoreExW(0, 0, *((_DWORD *)a1 + 3660), 0, 0, 0x1F0003u);
      *((_QWORD *)a1 + 1837) = v10;
      if ( v10 )
      {
        EventW = CreateEventW(0, 0, 0, 0);
        *((_QWORD *)a1 + 1838) = EventW;
        if ( EventW )
        {
          v14 = (void *)WMV_CreateThread(v13, v12, (int)threadFuncDirectColorConv0, (int)a1, dwFlags, &v31);
          *((_QWORD *)a1 + 1832) = v14;
          if ( v14 )
          {
            SetThreadPriority(v14, ThreadPriority);
            v20 = (void *)WMV_CreateThread(v19, v18, (int)threadFuncDirectColorConv1, (int)a1, dwFlagsa, &v32);
            *((_QWORD *)a1 + 1833) = v20;
            if ( v20 )
            {
              SetThreadPriority(v20, ThreadPriority);
              if ( *((_DWORD *)a1 + 3660) != 4 )
                return v3;
              v23 = (void *)WMV_CreateThread(v22, v21, (int)threadFuncDirectColorConv2, (int)a1, dwFlagsb, &v33);
              *((_QWORD *)a1 + 1834) = v23;
              if ( v23 )
              {
                SetThreadPriority(v23, ThreadPriority);
                v26 = (void *)WMV_CreateThread(v25, v24, (int)threadFuncDirectColorConv3, (int)a1, dwFlagsc, &v34);
                *((_QWORD *)a1 + 1835) = v26;
                if ( v26 )
                {
                  SetThreadPriority(v26, ThreadPriority);
                  return v3;
                }
              }
            }
          }
          v15 = *((_DWORD *)a1 + 3660);
          v16 = (void *)*((_QWORD *)a1 + 1836);
          *((_DWORD *)a1 + 3659) = 1;
          ReleaseSemaphore(v16, v15, 0);
        }
      }
    }
    return 0;
  }
  return v3;
}

```

## disassembly

```asm
0x180010f28  push    rbx
0x180010f2a  push    rsi
0x180010f2b  push    rdi
0x180010f2c  sub     rsp, 30h
0x180010f30  mov     r9d, [rcx+3930h]
0x180010f37  mov     rbx, rcx
0x180010f3a  mov     edi, 1
0x180010f3f  cmp     r9d, 4
0x180010f43  jbe     short loc_180010F53
0x180010f45  mov     dword ptr [rcx+3930h], 4
0x180010f4f  lea     r9d, [rdi+3]
0x180010f53  mov     r10d, [rcx+38E4h]
0x180010f5a  xor     edx, edx
0x180010f5c  mov     eax, r10d
0x180010f5f  div     r9d
0x180010f62  mov     r8d, eax
0x180010f65  and     r8d, 0FFFFFFFEh
0x180010f69  mov     [rcx+98h], r8d
0x180010f70  test    r8b, 3
0x180010f74  jz      short loc_180010F81
0x180010f76  add     r8d, 0FFFFFFFEh
0x180010f7a  mov     [rcx+98h], r8d
0x180010f81  cmp     r9d, edi
0x180010f84  jnz     short loc_180010F90
0x180010f86  mov     [rcx+98h], r10d
0x180010f8d  mov     r8d, r10d
0x180010f90  cmp     r9d, 2
0x180010f94  lea     eax, [r8+r8]
0x180010f98  mov     ecx, r10d
0x180010f9b  cmovnz  ecx, eax
0x180010f9e  mov     [rbx+9Ch], ecx
0x180010fa4  cmp     r9d, 4
0x180010fa8  jnz     short loc_180010FAE
0x180010faa  lea     r10d, [r8+r8*2]
0x180010fae  mov     [rbx+0A0h], r10d
0x180010fb5  mov     [rsp+48h+arg_0], 0
0x180010fbd  mov     [rsp+48h+arg_8], 0
0x180010fc5  mov     [rsp+48h+arg_10], 0
0x180010fcd  mov     [rsp+48h+arg_18], 0
0x180010fd5  cmp     r9d, 2
0x180010fd9  jb      loc_1800110C3
0x180010fdf  call    cs:__imp_GetCurrentThread
0x180010fe5  mov     rcx, rax; hThread
0x180010fe8  call    cs:__imp_GetThreadPriority
0x180010fee  mov     [rsp+48h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180010ff6  xor     r9d, r9d; lpName
0x180010ff9  mov     esi, eax
0x180010ffb  mov     [rsp+48h+dwFlags], 0; dwFlags
0x180011003  xor     eax, eax
0x180011005  xor     edx, edx; lInitialCount
0x180011007  xchg    eax, [rbx+3938h]
0x18001100d  xor     eax, eax
0x18001100f  xor     ecx, ecx; lpSemaphoreAttributes
0x180011011  xchg    eax, [rbx+3934h]
0x180011017  mov     r8d, [rbx+3930h]; lMaximumCount
0x18001101e  call    cs:__imp_CreateSemaphoreExW
0x180011024  mov     [rbx+3960h], rax
0x18001102b  test    rax, rax
0x18001102e  jz      loc_1800110C1
0x180011034  mov     r8d, [rbx+3930h]; lMaximumCount
0x18001103b  xor     r9d, r9d; lpName
0x18001103e  mov     [rsp+48h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180011046  xor     edx, edx; lInitialCount
0x180011048  xor     ecx, ecx; lpSemaphoreAttributes
0x18001104a  mov     [rsp+48h+dwFlags], 0; ExitCode
0x180011052  call    cs:__imp_CreateSemaphoreExW
0x180011058  mov     [rbx+3968h], rax
0x18001105f  test    rax, rax
0x180011062  jz      short loc_1800110C1
0x180011064  xor     r9d, r9d; lpName
0x180011067  xor     r8d, r8d; bInitialState
0x18001106a  xor     edx, edx; bManualReset
0x18001106c  xor     ecx, ecx; lpEventAttributes
0x18001106e  call    cs:__imp_CreateEventW
0x180011074  mov     [rbx+3970h], rax
0x18001107b  test    rax, rax
0x18001107e  jz      short loc_1800110C1
0x180011080  lea     rax, [rsp+48h+arg_0]
0x180011085  mov     r9, rbx; int
0x180011088  lea     r8, ?threadFuncDirectColorConv0@@YAX_J@Z; int
0x18001108f  mov     qword ptr [rsp+48h+dwDesiredAccess], rax; LPDWORD
0x180011094  call    WMV_CreateThread
0x180011099  mov     [rbx+3940h], rax
0x1800110a0  test    rax, rax
0x1800110a3  jnz     short loc_1800110CD
0x1800110a5  mov     edx, [rbx+3930h]; lReleaseCount
0x1800110ab  xor     r8d, r8d; lpPreviousCount
0x1800110ae  mov     rcx, [rbx+3960h]; hSemaphore
0x1800110b5  mov     [rbx+392Ch], edi
0x1800110bb  call    cs:__imp_ReleaseSemaphore
0x1800110c1  xor     edi, edi
0x1800110c3  mov     eax, edi
0x1800110c5  add     rsp, 30h
0x1800110c9  pop     rdi
0x1800110ca  pop     rsi
0x1800110cb  pop     rbx
0x1800110cc  retn
0x1800110cd  mov     edx, esi; nPriority
0x1800110cf  mov     rcx, rax; hThread
0x1800110d2  call    cs:__imp_SetThreadPriority
0x1800110d8  lea     rax, [rsp+48h+arg_8]
0x1800110dd  mov     r9, rbx; int
0x1800110e0  lea     r8, ?threadFuncDirectColorConv1@@YAX_J@Z; int
0x1800110e7  mov     qword ptr [rsp+48h+dwDesiredAccess], rax; LPDWORD
0x1800110ec  call    WMV_CreateThread
0x1800110f1  mov     [rbx+3948h], rax
0x1800110f8  test    rax, rax
0x1800110fb  jz      short loc_1800110A5
0x1800110fd  mov     edx, esi; nPriority
0x1800110ff  mov     rcx, rax; hThread
0x180011102  call    cs:__imp_SetThreadPriority
0x180011108  cmp     dword ptr [rbx+3930h], 4
0x18001110f  jnz     short loc_1800110C3
0x180011111  lea     rax, [rsp+48h+arg_10]
0x180011116  mov     r9, rbx; int
0x180011119  lea     r8, ?threadFuncDirectColorConv2@@YAX_J@Z; int
0x180011120  mov     qword ptr [rsp+48h+dwDesiredAccess], rax; LPDWORD
0x180011125  call    WMV_CreateThread
0x18001112a  mov     [rbx+3950h], rax
0x180011131  test    rax, rax
0x180011134  jz      loc_1800110A5
0x18001113a  mov     edx, esi; nPriority
0x18001113c  mov     rcx, rax; hThread
0x18001113f  call    cs:__imp_SetThreadPriority
0x180011145  lea     rax, [rsp+48h+arg_18]
0x18001114a  mov     r9, rbx; int
0x18001114d  lea     r8, ?threadFuncDirectColorConv3@@YAX_J@Z; int
0x180011154  mov     qword ptr [rsp+48h+dwDesiredAccess], rax; LPDWORD
0x180011159  call    WMV_CreateThread
0x18001115e  mov     [rbx+3958h], rax
0x180011165  test    rax, rax
0x180011168  jz      loc_1800110A5
0x18001116e  mov     edx, esi; nPriority
0x180011170  mov     rcx, rax; hThread
0x180011173  call    cs:__imp_SetThreadPriority
0x180011179  jmp     loc_1800110C3
```
