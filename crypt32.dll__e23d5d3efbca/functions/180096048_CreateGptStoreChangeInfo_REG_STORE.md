# CreateGptStoreChangeInfo(_REG_STORE *)

- ea: `0x180096048`
- end: `0x1800961d3`
- name: `?CreateGptStoreChangeInfo@@YAPEAU_GPT_STORE_CHANGE_INFO@@PEAU_REG_STORE@@@Z`
- size: `395`
- prototype: `struct _GPT_STORE_CHANGE_INFO *__fastcall(struct _REG_STORE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180049f10`

## callees

- `0x180045014`
- `0x180046e10`
- `0x18005de50`
- `0x180096048`
- `0x1800961dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096090`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009616a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096090`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009616a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009608a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800960a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009608a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800960a4`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800960ec`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180096105`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800960ec`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180096105`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009613a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009613a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18009619f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18009619f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800961c4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800961c4`
- `api-ms-win-security-grouppolicy-l1-1-0!RegisterGPNotificationInternal` at `0x180096123`
- `api-ms-win-security-grouppolicy-l1-1-0!RegisterGPNotificationInternal` at `0x180096123`

## pseudocode

```c
struct _GPT_STORE_CHANGE_INFO *__fastcall CreateGptStoreChangeInfo(struct _REG_STORE *a1)
{
  struct _GPT_STORE_CHANGE_INFO *v2; // rbx
  int v3; // eax
  int v4; // eax
  int v5; // eax
  DWORD LastError; // ebx
  HANDLE EventA; // rax
  HANDLE v9; // rax
  unsigned int v10; // edi
  HKEY v11; // rax
  struct _TP_WAIT *ThreadpoolWait; // rax
  struct _TP_WAIT *v13; // rsi
  struct _GPT_STORE_CHANGE_INFO *v14; // [rsp+38h] [rbp+10h] BYREF

  v14 = (struct _GPT_STORE_CHANGE_INFO *)PkiZeroAlloc(0x48u);
  v2 = v14;
  if ( !v14 )
    goto LABEL_6;
  v3 = *((_DWORD *)a1 + 28);
  *(_DWORD *)v14 = v3;
  v4 = v3 - 2;
  if ( v4 )
  {
    v5 = v4 - 1;
    if ( v5 )
    {
      if ( v5 != 1 )
      {
        SetLastError(0x80070057);
        goto LABEL_6;
      }
      *((_QWORD *)v2 + 1) = *((_QWORD *)a1 + 12);
      *((_QWORD *)v2 + 2) = a1;
    }
    else
    {
      *((_QWORD *)v2 + 1) = -2147483646;
    }
  }
  else
  {
    *((_QWORD *)v2 + 1) = -2147483647;
  }
  EventA = CreateEventA(0, 0, 0, 0);
  *((_QWORD *)v2 + 4) = EventA;
  if ( !EventA )
    goto LABEL_6;
  v9 = CreateEventA(0, 0, 0, 0);
  *((_QWORD *)v2 + 6) = v9;
  if ( !v9 )
    goto LABEL_6;
  if ( (unsigned int)RegisterGPNotificationInternal(v9, *(_DWORD *)v2 == 3) )
  {
    v10 = 1;
  }
  else
  {
    v10 = 0;
    CloseHandle(*((HANDLE *)v2 + 6));
    *((_QWORD *)v2 + 6) = 0;
  }
  v11 = OpenSubKeyEx(*((HKEY *)v2 + 1), L"Software\\Policies\\Microsoft\\SystemCertificates", 0x8000, 0);
  *((_QWORD *)v2 + 3) = v11;
  if ( v11 )
  {
    if ( !ILS_RegNotifyChangeKeyValue(v11, *((void **)v2 + 4)) )
      goto LABEL_6;
  }
  else if ( !v10 )
  {
    if ( GetLastError() == 2 )
      return v2;
    goto LABEL_6;
  }
  ThreadpoolWait = CreateThreadpoolWait(GptWaitForCallback, v2, 0);
  v13 = ThreadpoolWait;
  if ( ThreadpoolWait )
  {
    SetThreadpoolWait(ThreadpoolWait, *((HANDLE *)v2 + 2 * v10 + 4), 0);
    *((_QWORD *)v2 + 5) = v13;
    return v2;
  }
LABEL_6:
  LastError = GetLastError();
  FreeGptStoreChangeInfo(&v14);
  SetLastError(LastError);
  return v14;
}

```

## disassembly

```asm
0x180096048  mov     [rsp+arg_0], rbx
0x18009604d  mov     [rsp+arg_10], rsi
0x180096052  push    rdi
0x180096053  sub     rsp, 20h
0x180096057  mov     rdi, rcx
0x18009605a  mov     ecx, 48h ; 'H'; uBytes
0x18009605f  call    PkiZeroAlloc
0x180096064  mov     [rsp+28h+arg_8], rax
0x180096069  mov     rbx, rax
0x18009606c  test    rax, rax
0x18009606f  jz      short loc_180096090
0x180096071  mov     eax, [rdi+70h]
0x180096074  mov     [rbx], eax
0x180096076  sub     eax, 2
0x180096079  jz      short loc_1800960DA
0x18009607b  sub     eax, 1
0x18009607e  jz      short loc_1800960D0
0x180096080  cmp     eax, 1
0x180096083  jz      short loc_1800960C2
0x180096085  mov     ecx, 80070057h; dwErrCode
0x18009608a  call    cs:__imp_SetLastError
0x180096090  call    cs:__imp_GetLastError
0x180096096  lea     rcx, [rsp+28h+arg_8]; struct _GPT_STORE_CHANGE_INFO **
0x18009609b  mov     ebx, eax
0x18009609d  call    ?FreeGptStoreChangeInfo@@YAXPEAPEAU_GPT_STORE_CHANGE_INFO@@@Z; FreeGptStoreChangeInfo(_GPT_STORE_CHANGE_INFO * *)
0x1800960a2  mov     ecx, ebx; dwErrCode
0x1800960a4  call    cs:__imp_SetLastError
0x1800960aa  mov     rbx, [rsp+28h+arg_8]
0x1800960af  mov     rsi, [rsp+28h+arg_10]
0x1800960b4  mov     rax, rbx
0x1800960b7  mov     rbx, [rsp+28h+arg_0]
0x1800960bc  add     rsp, 20h
0x1800960c0  pop     rdi
0x1800960c1  retn
0x1800960c2  mov     rax, [rdi+60h]
0x1800960c6  mov     [rbx+8], rax
0x1800960ca  mov     [rbx+10h], rdi
0x1800960ce  jmp     short loc_1800960E2
0x1800960d0  mov     qword ptr [rbx+8], 0FFFFFFFF80000002h
0x1800960d8  jmp     short loc_1800960E2
0x1800960da  mov     qword ptr [rbx+8], 0FFFFFFFF80000001h
0x1800960e2  xor     r9d, r9d; lpName
0x1800960e5  xor     r8d, r8d; bInitialState
0x1800960e8  xor     edx, edx; bManualReset
0x1800960ea  xor     ecx, ecx; lpEventAttributes
0x1800960ec  call    cs:__imp_CreateEventA
0x1800960f2  mov     [rbx+20h], rax
0x1800960f6  test    rax, rax
0x1800960f9  jz      short loc_180096090
0x1800960fb  xor     r9d, r9d; lpName
0x1800960fe  xor     r8d, r8d; bInitialState
0x180096101  xor     edx, edx; bManualReset
0x180096103  xor     ecx, ecx; lpEventAttributes
0x180096105  call    cs:__imp_CreateEventA
0x18009610b  mov     [rbx+30h], rax
0x18009610f  test    rax, rax
0x180096112  jz      loc_180096090
0x180096118  xor     edx, edx
0x18009611a  mov     rcx, rax
0x18009611d  cmp     dword ptr [rbx], 3
0x180096120  setz    dl
0x180096123  call    cs:__imp_RegisterGPNotificationInternal
0x180096129  test    eax, eax
0x18009612b  jz      short loc_180096134
0x18009612d  mov     edi, 1
0x180096132  jmp     short loc_180096144
0x180096134  mov     rcx, [rbx+30h]; hObject
0x180096138  xor     edi, edi
0x18009613a  call    cs:__imp_CloseHandle
0x180096140  mov     [rbx+30h], rdi
0x180096144  mov     rcx, [rbx+8]; HKEY
0x180096148  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\SystemCe"...
0x18009614f  xor     r9d, r9d; unsigned int *
0x180096152  mov     r8d, 8000h; unsigned int
0x180096158  call    ?OpenSubKeyEx@@YAPEAUHKEY__@@PEAU1@PEBGKPEAK@Z; OpenSubKeyEx(HKEY__ *,ushort const *,ulong,ulong *)
0x18009615d  mov     [rbx+18h], rax
0x180096161  test    rax, rax
0x180096164  jnz     short loc_18009617E
0x180096166  test    edi, edi
0x180096168  jnz     short loc_180096192
0x18009616a  call    cs:__imp_GetLastError
0x180096170  cmp     eax, 2
0x180096173  jnz     loc_180096090
0x180096179  jmp     loc_1800960AF
0x18009617e  mov     rdx, [rbx+20h]; void *
0x180096182  mov     rcx, rax; HKEY
0x180096185  call    ?ILS_RegNotifyChangeKeyValue@@YAHPEAUHKEY__@@PEAX@Z; ILS_RegNotifyChangeKeyValue(HKEY__ *,void *)
0x18009618a  test    eax, eax
0x18009618c  jz      loc_180096090
0x180096192  xor     r8d, r8d; pcbe
0x180096195  lea     rcx, ?GptWaitForCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18009619c  mov     rdx, rbx; pv
0x18009619f  call    cs:__imp_CreateThreadpoolWait
0x1800961a5  mov     rsi, rax
0x1800961a8  test    rax, rax
0x1800961ab  jz      loc_180096090
0x1800961b1  mov     edx, edi
0x1800961b3  xor     r8d, r8d; pftTimeout
0x1800961b6  add     rdx, 2
0x1800961ba  mov     rcx, rax; pwa
0x1800961bd  add     rdx, rdx
0x1800961c0  mov     rdx, [rbx+rdx*8]; h
0x1800961c4  call    cs:__imp_SetThreadpoolWait
0x1800961ca  mov     [rbx+28h], rsi
0x1800961ce  jmp     loc_1800960AF
```
