# GameInputWatcher::WaitCallback(void)

- ea: `0x180065adc`
- end: `0x180065be6`
- name: `?WaitCallback@GameInputWatcher@@AEAAXXZ`
- size: `266`
- prototype: `void __fastcall(GameInputWatcher *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180065ac0`

## callees

- `0x180065adc`
- `0x1800f07c4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180065bc9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180065bc9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180065b77`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180065b77`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180065b09`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180065b09`
- `api-ms-win-core-file-l2-1-0!ReadDirectoryChangesW` at `0x180065bb4`
- `api-ms-win-core-file-l2-1-0!ReadDirectoryChangesW` at `0x180065bb4`

## string_xrefs

- `0x180065b35`: `GameInput.dll`
- `0x180065b49`: `GameInputRedist.dll`

## pseudocode

```c
void __fastcall GameInputWatcher::WaitCallback(GameInputWatcher *this)
{
  struct _OVERLAPPED *lpOverlapped; // rbp
  unsigned int *i; // rbx
  struct _TP_TIMER *v4; // rcx
  DWORD NumberOfBytesTransferred; // [rsp+60h] [rbp+8h] BYREF
  struct _FILETIME pftDueTime; // [rsp+68h] [rbp+10h] BYREF

  lpOverlapped = (struct _OVERLAPPED *)((char *)this + 32);
  NumberOfBytesTransferred = 0;
  if ( GetOverlappedResult(*((HANDLE *)this + 2), (LPOVERLAPPED)this + 1, &NumberOfBytesTransferred, 1) )
  {
    for ( i = (unsigned int *)*((_QWORD *)this + 8); ; i = (unsigned int *)((char *)i + *i) )
    {
      *((_WORD *)i + ((unsigned __int64)i[2] >> 1) + 6) = 0;
      if ( (i[1] == 1 || i[1] == 3)
        && (!wcsicmp((const wchar_t *)i + 6, L"GameInput.dll")
         || !wcsicmp((const wchar_t *)i + 6, L"GameInputRedist.dll")) )
      {
        v4 = *(struct _TP_TIMER **)this;
        pftDueTime = (struct _FILETIME)-10000000LL;
        SetThreadpoolTimer(v4, &pftDueTime, 0, 0x3E8u);
        return;
      }
      if ( !*i )
        break;
    }
    if ( ReadDirectoryChangesW(*((HANDLE *)this + 2), *((LPVOID *)this + 8), 0x1000u, 0, 0x59u, 0, lpOverlapped, 0) )
      SetThreadpoolWait(*((PTP_WAIT *)this + 1), *((HANDLE *)this + 3), 0);
  }
}

```

## disassembly

```asm
0x180065adc  mov     [rsp+arg_10], rbx
0x180065ae1  push    rbp
0x180065ae2  push    rsi
0x180065ae3  push    rdi
0x180065ae4  sub     rsp, 40h
0x180065ae8  lea     rbp, [rcx+20h]
0x180065aec  mov     [rsp+58h+NumberOfBytesTransferred], 0
0x180065af4  mov     rdi, rcx
0x180065af7  lea     r8, [rsp+58h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180065afc  mov     rcx, [rcx+10h]; hFile
0x180065b00  mov     rdx, rbp; lpOverlapped
0x180065b03  mov     r9d, 1; bWait
0x180065b09  call    cs:__imp_GetOverlappedResult
0x180065b0f  test    eax, eax
0x180065b11  jz      loc_180065BCF
0x180065b17  mov     rbx, [rdi+40h]
0x180065b1b  mov     ecx, [rbx+8]
0x180065b1e  xor     eax, eax
0x180065b20  shr     rcx, 1
0x180065b23  mov     [rbx+rcx*2+0Ch], ax
0x180065b28  mov     ecx, [rbx+4]
0x180065b2b  sub     ecx, 1
0x180065b2e  jz      short loc_180065B35
0x180065b30  cmp     ecx, 2
0x180065b33  jnz     short loc_180065B7F
0x180065b35  lea     rdx, aGameinputDll; "GameInput.dll"
0x180065b3c  lea     rcx, [rbx+0Ch]; String1
0x180065b40  call    _wcsicmp
0x180065b45  test    eax, eax
0x180065b47  jz      short loc_180065B5D
0x180065b49  lea     rdx, aGameinputredis; "GameInputRedist.dll"
0x180065b50  lea     rcx, [rbx+0Ch]; String1
0x180065b54  call    _wcsicmp
0x180065b59  test    eax, eax
0x180065b5b  jnz     short loc_180065B7F
0x180065b5d  mov     rcx, [rdi]; pti
0x180065b60  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x180065b65  mov     r9d, 3E8h; msWindowLength
0x180065b6b  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], 0FFFFFFFFFF676980h
0x180065b74  xor     r8d, r8d; msPeriod
0x180065b77  call    cs:__imp_SetThreadpoolTimer
0x180065b7d  jmp     short loc_180065BCF
0x180065b7f  cmp     dword ptr [rbx], 0
0x180065b82  jnz     short loc_180065BDC
0x180065b84  mov     rdx, [rdi+40h]; lpBuffer
0x180065b88  xor     r9d, r9d; bWatchSubtree
0x180065b8b  mov     rcx, [rdi+10h]; hDirectory
0x180065b8f  mov     r8d, 1000h; nBufferLength
0x180065b95  mov     [rsp+58h+lpCompletionRoutine], 0; lpCompletionRoutine
0x180065b9e  mov     [rsp+58h+lpOverlapped], rbp; lpOverlapped
0x180065ba3  mov     [rsp+58h+lpBytesReturned], 0; lpBytesReturned
0x180065bac  mov     [rsp+58h+dwNotifyFilter], 59h ; 'Y'; dwNotifyFilter
0x180065bb4  call    cs:__imp_ReadDirectoryChangesW
0x180065bba  test    eax, eax
0x180065bbc  jz      short loc_180065BCF
0x180065bbe  mov     rdx, [rdi+18h]; h
0x180065bc2  xor     r8d, r8d; pftTimeout
0x180065bc5  mov     rcx, [rdi+8]; pwa
0x180065bc9  call    cs:__imp_SetThreadpoolWait
0x180065bcf  mov     rbx, [rsp+58h+arg_10]
0x180065bd4  add     rsp, 40h
0x180065bd8  pop     rdi
0x180065bd9  pop     rsi
0x180065bda  pop     rbp
0x180065bdb  retn
0x180065bdc  mov     eax, [rbx]
0x180065bde  add     rbx, rax
0x180065be1  jmp     loc_180065B1B
```
