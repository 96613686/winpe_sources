# OnInitOobAssociationCompleteStub(ushort const *,ulong,_DEVPROPERTY *,long,void *)

- ea: `0x14000b7c4`
- end: `0x14000b98b`
- name: `?OnInitOobAssociationCompleteStub@@YAJPEBGKPEAU_DEVPROPERTY@@JPEAX@Z`
- size: `455`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, struct _DEVPROPERTY *, __int64, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000b3c0`
- `0x140017d90`

## callees

- `0x140008eec`
- `0x140008f88`
- `0x14000a8ac`
- `0x14000b7c4`
- `0x140019c5c`
- `0x14001a068`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000b920`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000b920`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000b880`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000b880`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b8f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b8f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b861`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b8e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b861`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b8e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b92a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b92a`

## pseudocode

```c
__int64 __fastcall OnInitOobAssociationCompleteStub(
        const unsigned __int16 *a1,
        unsigned int a2,
        struct _DEVPROPERTY *a3,
        __int64 a4,
        void *a5)
{
  signed int v8; // ebx
  const unsigned __int16 *v9; // rax
  __int64 v10; // rsi
  HANDLE ProcessHeap; // rax
  __int64 v12; // rbx
  unsigned __int16 *v13; // rax
  void *v14; // rsi
  HANDLE v15; // rax
  struct _DEVPROPERTY *v16; // rcx
  void *v17; // rcx
  int v18; // edx
  int v19; // r8d
  signed int LastError; // eax
  int v22; // [rsp+28h] [rbp-60h]

  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      a2,
      (int)a3,
      41,
      &WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids);
  v8 = *((_DWORD *)a5 + 16);
  if ( v8 < 0 )
    goto LABEL_19;
  if ( !a1 )
  {
    v8 = -2147024809;
    goto LABEL_19;
  }
  v9 = a1;
  v10 = 768;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v10;
  }
  while ( v10 );
  v8 = v10 == 0 ? 0x80070057 : 0;
  if ( !v10 )
    goto LABEL_19;
  ProcessHeap = GetProcessHeap();
  v12 = -(__int64)(v10 != 0) & (2 * (768 - v10));
  v13 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, v12 + 2);
  *((_QWORD *)a5 + 9) = v13;
  if ( !v13 )
  {
    v8 = -2147024882;
LABEL_19:
    v14 = (void *)*((_QWORD *)a5 + 9);
    if ( v14 )
    {
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v14);
      *((_QWORD *)a5 + 9) = 0;
    }
    v16 = (struct _DEVPROPERTY *)*((_QWORD *)a5 + 16);
    if ( v16 )
    {
      MidlFreeDevProperties(v16, *((_DWORD *)a5 + 30));
      *((_QWORD *)a5 + 16) = 0;
      *((_DWORD *)a5 + 30) = 0;
    }
    goto LABEL_23;
  }
  v8 = StringCbCopyW(v13, v12 + 2, a1);
  if ( v8 >= 0 )
  {
    if ( a3 )
    {
      if ( a2 )
      {
        v8 = MidlCopyDevProperties(a3, a2, (struct _DEVPROPERTY **)a5 + 16);
        if ( v8 >= 0 )
          *((_DWORD *)a5 + 30) = a2;
      }
    }
  }
  if ( v8 )
    goto LABEL_19;
LABEL_23:
  v17 = (void *)*((_QWORD *)a5 + 12);
  *((_DWORD *)a5 + 16) = v8;
  if ( !SetEvent(v17) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
  }
  *((_DWORD *)a5 + 16) = v8;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v18,
      v19,
      42,
      &WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids,
      v22,
      v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000b7c4  push    rbx
0x14000b7c6  push    rbp
0x14000b7c7  push    rsi
0x14000b7c8  push    rdi
0x14000b7c9  push    r12
0x14000b7cb  push    r13
0x14000b7cd  push    r14
0x14000b7cf  push    r15
0x14000b7d1  sub     rsp, 48h
0x14000b7d5  mov     rdi, [rsp+88h+arg_20]
0x14000b7dd  mov     r12, r8
0x14000b7e0  mov     ebp, edx
0x14000b7e2  mov     r14, rcx
0x14000b7e5  lea     rcx, WPP_RECORDER_INITIALIZED
0x14000b7ec  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000b7f3  lea     rax, WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids
0x14000b7fa  jz      short loc_14000B817
0x14000b7fc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b803  mov     r9d, 29h ; ')'; int
0x14000b809  mov     [rsp+88h+MessageGuid], rax; MessageGuid
0x14000b80e  mov     rcx, [rcx+28h]; int
0x14000b812  call    WPP_RECORDER_SF_s
0x14000b817  mov     ebx, [rdi+40h]
0x14000b81a  xor     r13d, r13d
0x14000b81d  test    ebx, ebx
0x14000b81f  jz      short loc_14000B827
0x14000b821  js      loc_14000B8D9
0x14000b827  test    r14, r14
0x14000b82a  jz      loc_14000B8D4
0x14000b830  mov     r15d, 300h
0x14000b836  mov     rax, r14
0x14000b839  mov     esi, r15d
0x14000b83c  cmp     [rax], r13w
0x14000b840  jz      short loc_14000B84C
0x14000b842  add     rax, 2
0x14000b846  sub     rsi, 1
0x14000b84a  jnz     short loc_14000B83C
0x14000b84c  mov     rax, rsi
0x14000b84f  neg     rax
0x14000b852  sbb     ebx, ebx
0x14000b854  not     ebx
0x14000b856  and     ebx, 80070057h
0x14000b85c  test    rsi, rsi
0x14000b85f  jz      short loc_14000B8D9
0x14000b861  call    cs:__imp_GetProcessHeap
0x14000b867  sub     r15, rsi
0x14000b86a  mov     rcx, rax; hHeap
0x14000b86d  neg     rsi
0x14000b870  sbb     rax, rax
0x14000b873  xor     edx, edx; dwFlags
0x14000b875  lea     rbx, [r15+r15]
0x14000b879  and     rbx, rax
0x14000b87c  lea     r8, [rbx+2]; dwBytes
0x14000b880  call    cs:__imp_HeapAlloc
0x14000b886  mov     [rdi+48h], rax
0x14000b88a  test    rax, rax
0x14000b88d  jnz     short loc_14000B896
0x14000b88f  mov     ebx, 8007000Eh
0x14000b894  jmp     short loc_14000B8D9
0x14000b896  mov     r8, r14; unsigned __int16 *
0x14000b899  lea     rdx, [rbx+2]; unsigned __int64
0x14000b89d  mov     rcx, rax; unsigned __int16 *
0x14000b8a0  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x14000b8a5  mov     ebx, eax
0x14000b8a7  test    eax, eax
0x14000b8a9  js      short loc_14000B8CE
0x14000b8ab  test    r12, r12
0x14000b8ae  jz      short loc_14000B8CE
0x14000b8b0  test    ebp, ebp
0x14000b8b2  jz      short loc_14000B8CE
0x14000b8b4  lea     r8, [rdi+80h]; struct _DEVPROPERTY **
0x14000b8bb  mov     edx, ebp; unsigned int
0x14000b8bd  mov     rcx, r12; struct _DEVPROPERTY *
0x14000b8c0  call    ?MidlCopyDevProperties@@YAJPEAU_DEVPROPERTY@@KPEAPEAU1@@Z; MidlCopyDevProperties(_DEVPROPERTY *,ulong,_DEVPROPERTY * *)
0x14000b8c5  mov     ebx, eax
0x14000b8c7  test    eax, eax
0x14000b8c9  js      short loc_14000B8CE
0x14000b8cb  mov     [rdi+78h], ebp
0x14000b8ce  test    ebx, ebx
0x14000b8d0  jz      short loc_14000B919
0x14000b8d2  jmp     short loc_14000B8D9
0x14000b8d4  mov     ebx, 80070057h
0x14000b8d9  mov     rsi, [rdi+48h]
0x14000b8dd  test    rsi, rsi
0x14000b8e0  jz      short loc_14000B8FA
0x14000b8e2  call    cs:__imp_GetProcessHeap
0x14000b8e8  mov     r8, rsi; lpMem
0x14000b8eb  xor     edx, edx; dwFlags
0x14000b8ed  mov     rcx, rax; hHeap
0x14000b8f0  call    cs:__imp_HeapFree
0x14000b8f6  mov     [rdi+48h], r13
0x14000b8fa  mov     rcx, [rdi+80h]; struct _DEVPROPERTY *
0x14000b901  test    rcx, rcx
0x14000b904  jz      short loc_14000B919
0x14000b906  mov     edx, [rdi+78h]; unsigned int
0x14000b909  call    ?MidlFreeDevProperties@@YAXPEAU_DEVPROPERTY@@K@Z; MidlFreeDevProperties(_DEVPROPERTY *,ulong)
0x14000b90e  mov     [rdi+80h], r13
0x14000b915  mov     [rdi+78h], r13d
0x14000b919  mov     rcx, [rdi+60h]; hEvent
0x14000b91d  mov     [rdi+40h], ebx
0x14000b920  call    cs:__imp_SetEvent
0x14000b926  test    eax, eax
0x14000b928  jnz     short loc_14000B93F
0x14000b92a  call    cs:__imp_GetLastError
0x14000b930  mov     ebx, eax
0x14000b932  test    eax, eax
0x14000b934  jle     short loc_14000B93F
0x14000b936  movzx   ebx, ax
0x14000b939  or      ebx, 80070000h
0x14000b93f  mov     [rdi+40h], ebx
0x14000b942  lea     rax, WPP_RECORDER_INITIALIZED
0x14000b949  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000b950  jz      short loc_14000B978
0x14000b952  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b959  lea     rax, WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids
0x14000b960  mov     r9d, 2Ah ; '*'; int
0x14000b966  mov     dword ptr [rsp+88h+var_58], ebx; char
0x14000b96a  mov     [rsp+88h+MessageGuid], rax; MessageGuid
0x14000b96f  mov     rcx, [rcx+28h]; int
0x14000b973  call    WPP_RECORDER_SF_sd
0x14000b978  mov     eax, ebx
0x14000b97a  add     rsp, 48h
0x14000b97e  pop     r15
0x14000b980  pop     r14
0x14000b982  pop     r13
0x14000b984  pop     r12
0x14000b986  pop     rdi
0x14000b987  pop     rsi
0x14000b988  pop     rbp
0x14000b989  pop     rbx
0x14000b98a  retn
```
