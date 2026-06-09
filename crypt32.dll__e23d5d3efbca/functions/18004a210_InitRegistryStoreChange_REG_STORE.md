# InitRegistryStoreChange(_REG_STORE *)

- ea: `0x18004a210`
- end: `0x18004a321`
- name: `?InitRegistryStoreChange@@YAHPEAU_REG_STORE@@@Z`
- size: `273`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180049cfc`

## callees

- `0x180028d60`
- `0x180046e10`
- `0x18004a210`
- `0x1800961dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a2f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a301`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a2f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a301`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180118108`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180118108`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18004a258`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18004a258`
- `api-ms-win-core-file-l1-1-0!FindCloseChangeNotification` at `0x18004a315`
- `api-ms-win-core-file-l1-1-0!FindCloseChangeNotification` at `0x18004a315`
- `api-ms-win-core-file-l1-1-0!FindFirstChangeNotificationW` at `0x18004a2e5`
- `api-ms-win-core-file-l1-1-0!FindFirstChangeNotificationW` at `0x18004a2e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180118100`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180118100`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18004a28b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18004a28b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004a2a2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18004a2a2`

## pseudocode

```c
__int64 __fastcall InitRegistryStoreChange(PVOID pv)
{
  int v1; // r14d
  _DWORD *v3; // rax
  _QWORD *v4; // rdi
  int v5; // r14d
  unsigned int v6; // esi
  char *EventA; // rax
  char *v8; // rbx
  struct _TP_WAIT *ThreadpoolWait; // rax
  struct _TP_WAIT *v10; // r15
  DWORD LastError; // ecx
  DWORD v13; // esi

  v1 = *((_DWORD *)pv + 18);
  v3 = (_DWORD *)PkiZeroAlloc(0x28u);
  v4 = v3;
  if ( !v3 )
    goto LABEL_9;
  v5 = v1 & 0x40000;
  v6 = 1;
  *v3 = 1;
  if ( v5 )
  {
    v8 = (char *)FindFirstChangeNotificationW(*((LPCWSTR *)pv + 12), 1, 0x1Bu);
    if ( v8 == (char *)-1LL )
    {
      LastError = GetLastError();
      goto LABEL_16;
    }
  }
  else
  {
    EventA = (char *)CreateEventA(0, 0, 0, 0);
    v8 = EventA;
    if ( !EventA || !ILS_RegNotifyChangeKeyValue(*((HKEY *)pv + 8), EventA) )
      goto LABEL_8;
  }
  v4[1] = v8;
  *((_QWORD *)pv + 15) = v4;
  ThreadpoolWait = CreateThreadpoolWait(RegistryStoreChangeCallback, pv, 0);
  v10 = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
LABEL_8:
    if ( (unsigned __int64)(v8 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
LABEL_9:
      PkiDefaultCryptFree(v4);
      v6 = 0;
      *((_QWORD *)pv + 15) = 0;
      return v6;
    }
    v13 = GetLastError();
    if ( v5 )
      FindCloseChangeNotification(v8);
    else
      CloseHandle(v8);
    LastError = v13;
LABEL_16:
    SetLastError(LastError);
    goto LABEL_9;
  }
  SetThreadpoolWait(ThreadpoolWait, v8, 0);
  v4[2] = v10;
  return v6;
}

```

## disassembly

```asm
0x18004a210  push    rbx
0x18004a212  push    rbp
0x18004a213  push    rsi
0x18004a214  push    rdi
0x18004a215  push    r14
0x18004a217  push    r15
0x18004a219  sub     rsp, 28h
0x18004a21d  mov     r14d, [rcx+48h]
0x18004a221  mov     rbp, rcx
0x18004a224  mov     ecx, 28h ; '('; uBytes
0x18004a229  call    PkiZeroAlloc
0x18004a22e  mov     rdi, rax
0x18004a231  test    rax, rax
0x18004a234  jz      loc_18004A2C5
0x18004a23a  and     r14d, 40000h
0x18004a241  mov     esi, 1
0x18004a246  mov     [rax], esi
0x18004a248  jnz     loc_18004A2D9
0x18004a24e  xor     r9d, r9d; lpName
0x18004a251  xor     r8d, r8d; bInitialState
0x18004a254  xor     edx, edx; bManualReset
0x18004a256  xor     ecx, ecx; lpEventAttributes
0x18004a258  call    cs:__imp_CreateEventA
0x18004a25e  mov     rbx, rax
0x18004a261  test    rax, rax
0x18004a264  jz      short loc_18004A2BB
0x18004a266  mov     rcx, [rbp+40h]; HKEY
0x18004a26a  mov     rdx, rax; void *
0x18004a26d  call    ?ILS_RegNotifyChangeKeyValue@@YAHPEAUHKEY__@@PEAX@Z; ILS_RegNotifyChangeKeyValue(HKEY__ *,void *)
0x18004a272  test    eax, eax
0x18004a274  jz      short loc_18004A2BB
0x18004a276  mov     [rdi+8], rbx
0x18004a27a  lea     rcx, RegistryStoreChangeCallback; pfnwa
0x18004a281  xor     r8d, r8d; pcbe
0x18004a284  mov     [rbp+78h], rdi
0x18004a288  mov     rdx, rbp; pv
0x18004a28b  call    cs:__imp_CreateThreadpoolWait
0x18004a291  mov     r15, rax
0x18004a294  test    rax, rax
0x18004a297  jz      short loc_18004A2BB
0x18004a299  xor     r8d, r8d; pftTimeout
0x18004a29c  mov     rdx, rbx; h
0x18004a29f  mov     rcx, rax; pwa
0x18004a2a2  call    cs:__imp_SetThreadpoolWait
0x18004a2a8  mov     [rdi+10h], r15
0x18004a2ac  mov     eax, esi
0x18004a2ae  add     rsp, 28h
0x18004a2b2  pop     r15
0x18004a2b4  pop     r14
0x18004a2b6  pop     rdi
0x18004a2b7  pop     rsi
0x18004a2b8  pop     rbp
0x18004a2b9  pop     rbx
0x18004a2ba  retn
0x18004a2bb  lea     rax, [rbx-1]
0x18004a2bf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004a2c3  jbe     short loc_18004A301
0x18004a2c5  mov     rcx, rdi; hMem
0x18004a2c8  call    PkiDefaultCryptFree
0x18004a2cd  xor     esi, esi
0x18004a2cf  mov     qword ptr [rbp+78h], 0
0x18004a2d7  jmp     short loc_18004A2AC
0x18004a2d9  mov     rcx, [rbp+60h]; lpPathName
0x18004a2dd  mov     r8d, 1Bh; dwNotifyFilter
0x18004a2e3  mov     edx, esi; bWatchSubtree
0x18004a2e5  call    cs:__imp_FindFirstChangeNotificationW
0x18004a2eb  mov     rbx, rax
0x18004a2ee  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004a2f2  jnz     short loc_18004A276
0x18004a2f4  call    cs:__imp_GetLastError
0x18004a2fa  mov     ecx, eax
0x18004a2fc  jmp     loc_180118108
0x18004a301  call    cs:__imp_GetLastError
0x18004a307  mov     rcx, rbx; hObject
0x18004a30a  mov     esi, eax
0x18004a30c  test    r14d, r14d
0x18004a30f  jz      loc_180118100
0x18004a315  call    cs:__imp_FindCloseChangeNotification
0x18004a31b  nop
0x18004a31c  jmp     loc_180118106
0x180118100  call    cs:__imp_CloseHandle
0x180118106  mov     ecx, esi; dwErrCode
0x180118108  call    cs:__imp_SetLastError
0x18011810e  nop
0x18011810f  jmp     loc_18004A2C5
```
