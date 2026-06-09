# WaitForCatrootChangesCallback

- ea: `0x180012f70`
- end: `0x180013097`
- name: `WaitForCatrootChangesCallback`
- size: `295`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000be40`
- `0x180012e48`
- `0x180012ef4`
- `0x180012f70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013015`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013015`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001302f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001302f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001306c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001306c`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180012fb6`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180012fb6`

## pseudocode

```c
void __fastcall WaitForCatrootChangesCallback(
        PTP_CALLBACK_INSTANCE Instance,
        char *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  DWORD v6; // ecx
  unsigned int *v7; // rdi
  unsigned __int64 v8; // rdx
  _WORD *v9; // rax
  char v10; // bl
  DWORD NumberOfBytesTransferred; // [rsp+20h] [rbp-28h] BYREF

  NumberOfBytesTransferred = 0;
  if ( !g_CatalogChangesShuttingDown )
  {
    if ( GetOverlappedResult(*(HANDLE *)Context, (LPOVERLAPPED)(Context + 8), &NumberOfBytesTransferred, 0)
      && !g_CatrootChangesSyncInFlight )
    {
      v6 = NumberOfBytesTransferred;
      v7 = (unsigned int *)(Context + 40);
      while ( v6 > 0x10 )
      {
        v8 = (unsigned __int64)v7 + 2 * ((unsigned __int64)v7[2] >> 1) + 12;
        v9 = v7 + 3;
        if ( (unsigned __int64)(v7 + 3) < v8 )
        {
          while ( *v9 != 92 )
          {
            if ( (unsigned __int64)++v9 >= v8 )
              goto LABEL_12;
          }
          if ( v9 )
          {
            EnterCriticalSection(&g_IgnoreListCS);
            v10 = IsFileNameOnIgnoreListLocked(v7 + 3, v7[2]);
            LeaveCriticalSection(&g_IgnoreListCS);
            if ( !v10 )
            {
              if ( !_InterlockedCompareExchange(&g_CatrootChangesSyncInFlight, 1, 0) )
                SubmitThreadpoolWork(g_CatrootSyncWork);
              break;
            }
            v6 = NumberOfBytesTransferred;
          }
        }
LABEL_12:
        if ( !*v7 )
          break;
        v6 -= *v7;
        NumberOfBytesTransferred = v6;
        v7 = (unsigned int *)((char *)v7 + *v7);
      }
    }
    SubmitWaitForCatrootChanges(Wait, (__int64)Context);
  }
}

```

## disassembly

```asm
0x180012f70  mov     [rsp+arg_0], rbx
0x180012f75  push    rbp
0x180012f76  push    rsi
0x180012f77  push    rdi
0x180012f78  sub     rsp, 30h
0x180012f7c  mov     rax, cs:__security_cookie
0x180012f83  xor     rax, rsp
0x180012f86  mov     [rsp+48h+var_20], rax
0x180012f8b  mov     al, cs:?g_CatalogChangesShuttingDown@@3EA; uchar g_CatalogChangesShuttingDown
0x180012f91  mov     rbp, r8
0x180012f94  mov     [rsp+48h+NumberOfBytesTransferred], 0
0x180012f9c  mov     rsi, rdx
0x180012f9f  test    al, al
0x180012fa1  jnz     loc_18001307D
0x180012fa7  mov     rcx, [rsi]; hFile
0x180012faa  lea     r8, [rsp+48h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180012faf  add     rdx, 8; lpOverlapped
0x180012fb3  xor     r9d, r9d; bWait
0x180012fb6  call    cs:__imp_GetOverlappedResult
0x180012fbc  test    eax, eax
0x180012fbe  jz      loc_180013072
0x180012fc4  mov     eax, cs:?g_CatrootChangesSyncInFlight@@3JA; long g_CatrootChangesSyncInFlight
0x180012fca  test    eax, eax
0x180012fcc  jnz     loc_180013072
0x180012fd2  mov     ecx, [rsp+48h+NumberOfBytesTransferred]
0x180012fd6  lea     rdi, [rsi+28h]
0x180012fda  jmp     short loc_18001304D
0x180012fdc  mov     eax, [rdi+8]
0x180012fdf  lea     rbx, [rdi+0Ch]
0x180012fe3  shr     rax, 1
0x180012fe6  lea     rdx, [rbx+rax*2]
0x180012fea  mov     rax, rbx
0x180012fed  cmp     rbx, rdx
0x180012ff0  jnb     short loc_18001303D
0x180012ff2  mov     r8d, 5Ch ; '\'
0x180012ff8  cmp     r8w, [rax]
0x180012ffc  jz      short loc_180013009
0x180012ffe  add     rax, 2
0x180013002  cmp     rax, rdx
0x180013005  jb      short loc_180012FF2
0x180013007  jmp     short loc_18001303D
0x180013009  test    rax, rax
0x18001300c  jz      short loc_18001303D
0x18001300e  lea     rcx, ?g_IgnoreListCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180013015  call    cs:__imp_EnterCriticalSection
0x18001301b  mov     edx, [rdi+8]
0x18001301e  mov     rcx, rbx
0x180013021  call    IsFileNameOnIgnoreListLocked
0x180013026  lea     rcx, ?g_IgnoreListCS@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001302d  mov     bl, al
0x18001302f  call    cs:__imp_LeaveCriticalSection
0x180013035  test    bl, bl
0x180013037  jz      short loc_180013054
0x180013039  mov     ecx, [rsp+48h+NumberOfBytesTransferred]
0x18001303d  cmp     dword ptr [rdi], 0
0x180013040  jz      short loc_180013072
0x180013042  sub     ecx, [rdi]
0x180013044  mov     [rsp+48h+NumberOfBytesTransferred], ecx
0x180013048  mov     eax, [rdi]
0x18001304a  add     rdi, rax
0x18001304d  cmp     ecx, 10h
0x180013050  ja      short loc_180012FDC
0x180013052  jmp     short loc_180013072
0x180013054  mov     ecx, 1
0x180013059  xor     eax, eax
0x18001305b  lock cmpxchg cs:?g_CatrootChangesSyncInFlight@@3JA, ecx; long g_CatrootChangesSyncInFlight
0x180013063  jnz     short loc_180013072
0x180013065  mov     rcx, cs:?g_CatrootSyncWork@@3PEAU_TP_WORK@@EA; pwk
0x18001306c  call    cs:__imp_SubmitThreadpoolWork
0x180013072  mov     rdx, rsi
0x180013075  mov     rcx, rbp; pwa
0x180013078  call    SubmitWaitForCatrootChanges
0x18001307d  mov     rcx, [rsp+48h+var_20]
0x180013082  xor     rcx, rsp; StackCookie
0x180013085  call    __security_check_cookie
0x18001308a  mov     rbx, [rsp+48h+arg_0]
0x18001308f  add     rsp, 30h
0x180013093  pop     rdi
0x180013094  pop     rsi
0x180013095  pop     rbp
0x180013096  retn
```
