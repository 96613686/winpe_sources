# SuCleanup(void)

- ea: `0x18003558c`
- end: `0x18003567b`
- name: `?SuCleanup@@YAHXZ`
- size: `239`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180013920`

## callees

- `0x180007adc`
- `0x1800353e0`
- `0x18003558c`
- `0x180036874`
- `0x1800375ee`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800355a8`
- `KERNEL32!SetLastError` at `0x1800355a8`
- `KERNEL32!CloseThreadpool` at `0x18003562e`
- `KERNEL32!CloseThreadpool` at `0x18003562e`
- `KERNEL32!CloseHandle` at `0x1800355d7`
- `KERNEL32!CloseHandle` at `0x1800355d7`
- `KERNEL32!GetLastError` at `0x1800355f3`
- `KERNEL32!GetLastError` at `0x1800355f3`

## pseudocode

```c
__int64 __fastcall SuCleanup(void **a1)
{
  unsigned int v1; // ebx
  const char *v2; // rdi
  char LastError; // al
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d

  SiAcquireSpinLock(a1);
  if ( ReferenceCount )
  {
    if ( ReferenceCount != 1 )
    {
      v1 = 1;
      --ReferenceCount;
      goto LABEL_10;
    }
    v1 = CloseHandle(Spaceport);
    if ( v1 )
    {
      Spaceport = (HANDLE)-1LL;
      CloseThreadpool(Threadpool);
      Threadpool = 0;
      memset_0(&ModuleName, 0, 0x208u);
      McGenEventUnregister_EventUnregister(SpaceApiProvider_Context);
      --ReferenceCount;
      goto LABEL_10;
    }
    v2 = "CloseHandle";
  }
  else
  {
    SetLastError(6u);
    v1 = 0;
    v2 = "ReferenceCount == 0";
  }
  if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 1) != 0 )
  {
    LastError = GetLastError();
    McTemplateK0zssq_EventWriteTransfer(
      v4,
      (unsigned int)CleanupApiFailed,
      v5,
      v6,
      (__int64)"SuCleanup",
      (__int64)v2,
      LastError);
  }
LABEL_10:
  _InterlockedExchange64((volatile __int64 *)&Lock, 0);
  return v1;
}

```

## disassembly

```asm
0x18003558c  mov     [rsp+arg_0], rbx
0x180035591  push    rdi
0x180035592  sub     rsp, 40h
0x180035596  call    ?SiAcquireSpinLock@@YAXPEAPEAX@Z; SiAcquireSpinLock(void * *)
0x18003559b  mov     eax, cs:?ReferenceCount@@3KA; ulong ReferenceCount
0x1800355a1  test    eax, eax
0x1800355a3  jnz     short loc_1800355B9
0x1800355a5  lea     ecx, [rax+6]; dwErrCode
0x1800355a8  call    cs:__imp_SetLastError
0x1800355ae  xor     ebx, ebx
0x1800355b0  lea     rdi, aReferencecount; "ReferenceCount == 0"
0x1800355b7  jmp     short loc_1800355EA
0x1800355b9  cmp     eax, 1
0x1800355bc  jz      short loc_1800355D0
0x1800355be  dec     eax
0x1800355c0  mov     ebx, 1
0x1800355c5  mov     cs:?ReferenceCount@@3KA, eax; ulong ReferenceCount
0x1800355cb  jmp     loc_180035665
0x1800355d0  mov     rcx, cs:?Spaceport@@3PEAXEA; hObject
0x1800355d7  call    cs:__imp_CloseHandle
0x1800355dd  mov     ebx, eax
0x1800355df  test    eax, eax
0x1800355e1  jnz     short loc_18003561C
0x1800355e3  lea     rdi, aClosehandle; "CloseHandle"
0x1800355ea  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 1
0x1800355f1  jz      short loc_180035665
0x1800355f3  call    cs:__imp_GetLastError
0x1800355f9  mov     [rsp+48h+var_18], eax
0x1800355fd  lea     rdx, CleanupApiFailed
0x180035604  lea     rax, aSucleanup; "SuCleanup"
0x18003560b  mov     [rsp+48h+var_20], rdi
0x180035610  mov     [rsp+48h+var_28], rax
0x180035615  call    McTemplateK0zssq_EventWriteTransfer
0x18003561a  jmp     short loc_180035665
0x18003561c  mov     rcx, cs:?Threadpool@@3PEAU_TP_POOL@@EA; ptpp
0x180035623  mov     cs:?Spaceport@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * Spaceport
0x18003562e  call    cs:__imp_CloseThreadpool
0x180035634  xor     edx, edx; Val
0x180035636  mov     cs:?Threadpool@@3PEAU_TP_POOL@@EA, 0; _TP_POOL * Threadpool
0x180035641  mov     r8d, 208h; Size
0x180035647  lea     rcx, ?ModuleName@@3PAGA; void *
0x18003564e  call    memset_0
0x180035653  lea     rcx, SpaceApiProvider_Context
0x18003565a  call    McGenEventUnregister_EventUnregister
0x18003565f  dec     cs:?ReferenceCount@@3KA; ulong ReferenceCount
0x180035665  xor     eax, eax
0x180035667  xchg    rax, cs:?Lock@@3PEAXEA; void * Lock
0x18003566e  mov     eax, ebx
0x180035670  mov     rbx, [rsp+48h+arg_0]
0x180035675  add     rsp, 40h
0x180035679  pop     rdi
0x18003567a  retn
```
