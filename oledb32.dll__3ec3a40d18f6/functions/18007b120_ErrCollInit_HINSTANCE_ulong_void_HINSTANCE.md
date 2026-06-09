# ErrCollInit(HINSTANCE__ *,ulong,void *,HINSTANCE__ *)

- ea: `0x18007b120`
- end: `0x18007b368`
- name: `?ErrCollInit@@YAHPEAUHINSTANCE__@@KPEAX0@Z`
- size: `584`
- prototype: `__int64 __fastcall(HINSTANCE, unsigned int, void *, HINSTANCE)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180011370`

## callees

- `0x180013870`
- `0x180022c34`
- `0x18007b120`
- `0x18007b480`
- `0x180087010`

## import_xrefs

- `MSDART!GetIUMS` at `0x18007b2d1`
- `MSDART!GetIUMS` at `0x18007b2d1`
- `MSDART!MPDeleteCriticalSection` at `0x18007b331`
- `MSDART!MPDeleteCriticalSection` at `0x18007b33e`
- `MSDART!MPDeleteCriticalSection` at `0x18007b34b`
- `MSDART!MPDeleteCriticalSection` at `0x18007b331`
- `MSDART!MPDeleteCriticalSection` at `0x18007b33e`
- `MSDART!MPDeleteCriticalSection` at `0x18007b34b`
- `MSDART!MpHeapAlloc` at `0x18007b1d9`
- `MSDART!MpHeapAlloc` at `0x18007b23a`
- `MSDART!MpHeapAlloc` at `0x18007b1d9`
- `MSDART!MpHeapAlloc` at `0x18007b23a`
- `MSDART!MPInitializeCriticalSectionAndSpinCount` at `0x18007b186`
- `MSDART!MPInitializeCriticalSectionAndSpinCount` at `0x18007b19d`
- `MSDART!MPInitializeCriticalSectionAndSpinCount` at `0x18007b1b4`
- `MSDART!MPInitializeCriticalSectionAndSpinCount` at `0x18007b186`
- `MSDART!MPInitializeCriticalSectionAndSpinCount` at `0x18007b19d`
- `MSDART!MPInitializeCriticalSectionAndSpinCount` at `0x18007b1b4`
- `ole32!CoGetMalloc` at `0x18007b162`
- `ole32!CoGetMalloc` at `0x18007b162`

## pseudocode

```c
__int64 __fastcall ErrCollInit(HINSTANCE a1, __int64 a2, void *a3, HINSTANCE a4)
{
  unsigned int v4; // edi
  HRESULT Malloc; // eax
  CExtBuffer *v6; // rax
  CExtBuffer *v7; // rax
  HINSTANCE v9; // [rsp+50h] [rbp+8h] BYREF
  __int64 v10; // [rsp+60h] [rbp+18h] BYREF

  v9 = a1;
  v10 = 0;
  v4 = 0;
  if ( !(_DWORD)a2 )
  {
    v9 = 0;
    GetIUMS(&v9, a2, a3, a4);
    if ( !v9 )
    {
      g_fProcessDetaching = 1;
      if ( g_pErrorCollectionListHeader || g_pErrInfoCollection || g_pClassFactoryCollection )
        ReleaseObjectCollections();
      if ( g_pIMalloc )
      {
        ((void (__fastcall *)(LPMALLOC))g_pIMalloc->lpVtbl->Release)(g_pIMalloc);
        g_pIMalloc = 0;
      }
      MPDeleteCriticalSection(&g_csErrorCollection);
      MPDeleteCriticalSection(&g_csErrInfoCollection);
      MPDeleteCriticalSection(&g_csClassFactoryCollection);
    }
    return 1;
  }
  if ( (_DWORD)a2 == 1 )
  {
    g_hLocalInst = a4;
    Malloc = CoGetMalloc(1u, &g_pIMalloc);
    if ( g_pIMalloc && Malloc >= 0 )
    {
      if ( (unsigned int)MPInitializeCriticalSectionAndSpinCount(&g_csErrorCollection, 0)
        && (unsigned int)MPInitializeCriticalSectionAndSpinCount(&g_csErrInfoCollection, 0)
        && (unsigned int)MPInitializeCriticalSectionAndSpinCount(&g_csClassFactoryCollection, 0) )
      {
        g_pErrorCollectionListHeader = 0;
        v6 = (CExtBuffer *)MpHeapAlloc(g_hHeapHandle, 19922944, 40);
        if ( v6 )
        {
          *(_QWORD *)v6 = 0;
          *((_QWORD *)v6 + 1) = 0;
          *((_QWORD *)v6 + 2) = 0;
          *((_QWORD *)v6 + 3) = 0;
          *((_QWORD *)v6 + 4) = 0;
          g_pErrInfoCollection = v6;
          if ( (unsigned int)CExtBuffer::FInit(v6, 8u, &v10, 0xAu, 0xAu) )
          {
            v7 = (CExtBuffer *)MpHeapAlloc(g_hHeapHandle, 19922944, 40);
            if ( v7 )
            {
              *(_QWORD *)v7 = 0;
              *((_QWORD *)v7 + 1) = 0;
              *((_QWORD *)v7 + 2) = 0;
              *((_QWORD *)v7 + 3) = 0;
              *((_QWORD *)v7 + 4) = 0;
              g_pClassFactoryCollection = v7;
              if ( (unsigned int)CExtBuffer::FInit(v7, 8u, &v10, 0xAu, 0xAu) )
                return 1;
            }
            else
            {
              g_pClassFactoryCollection = 0;
            }
          }
        }
        else
        {
          g_pErrInfoCollection = 0;
        }
      }
    }
    else if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(Malloc, L"<ErrCollInit|OLEDB|ERR> ", 0x44u);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18007b120  mov     rax, rsp
0x18007b123  mov     [rax+10h], rbp
0x18007b127  mov     [rax+20h], rsi
0x18007b12b  mov     [rax+18h], r8
0x18007b12f  mov     [rax+8], rcx
0x18007b133  push    rdi
0x18007b134  sub     rsp, 40h
0x18007b138  xor     esi, esi
0x18007b13a  mov     [rax+18h], rsi
0x18007b13e  mov     edi, esi
0x18007b140  test    edx, edx
0x18007b142  jz      loc_18007B2C7
0x18007b148  cmp     edx, 1
0x18007b14b  jnz     loc_18007B356
0x18007b151  lea     rdx, ?g_pIMalloc@@3PEAUIMalloc@@EA; ppMalloc
0x18007b158  mov     cs:?g_hLocalInst@@3PEAUHINSTANCE__@@EA, r9; HINSTANCE__ * g_hLocalInst
0x18007b15f  lea     ecx, [rsi+1]; dwMemContext
0x18007b162  call    cs:__imp_CoGetMalloc
0x18007b168  cmp     cs:?g_pIMalloc@@3PEAUIMalloc@@EA, rsi; IMalloc * g_pIMalloc
0x18007b16f  jz      loc_18007B2A1
0x18007b175  test    eax, eax
0x18007b177  js      loc_18007B2A1
0x18007b17d  xor     edx, edx
0x18007b17f  lea     rcx, ?g_csErrorCollection@@3PEAVCCriticalSection@@EA; CCriticalSection * g_csErrorCollection
0x18007b186  call    cs:__imp_MPInitializeCriticalSectionAndSpinCount
0x18007b18c  test    eax, eax
0x18007b18e  jz      loc_18007B356
0x18007b194  xor     edx, edx
0x18007b196  lea     rcx, ?g_csErrInfoCollection@@3PEAVCCriticalSection@@EA; CCriticalSection * g_csErrInfoCollection
0x18007b19d  call    cs:__imp_MPInitializeCriticalSectionAndSpinCount
0x18007b1a3  test    eax, eax
0x18007b1a5  jz      loc_18007B356
0x18007b1ab  xor     edx, edx
0x18007b1ad  lea     rcx, ?g_csClassFactoryCollection@@3PEAVCCriticalSection@@EA; CCriticalSection * g_csClassFactoryCollection
0x18007b1b4  call    cs:__imp_MPInitializeCriticalSectionAndSpinCount
0x18007b1ba  test    eax, eax
0x18007b1bc  jz      loc_18007B356
0x18007b1c2  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18007b1c9  lea     r8d, [rsi+28h]
0x18007b1cd  mov     edx, 1300000h
0x18007b1d2  mov     cs:?g_pErrorCollectionListHeader@@3REAVCError@@EA, rsi; CError * g_pErrorCollectionListHeader
0x18007b1d9  call    cs:__imp_MpHeapAlloc
0x18007b1df  mov     [rsp+48h+var_18], rax
0x18007b1e4  test    rax, rax
0x18007b1e7  jz      loc_18007B295
0x18007b1ed  lea     ebp, [rsi+0Ah]
0x18007b1f0  mov     [rax], rsi
0x18007b1f3  mov     r9d, ebp; unsigned __int64
0x18007b1f6  mov     [rax+8], rsi
0x18007b1fa  lea     r8, [rsp+48h+arg_10]; void *
0x18007b1ff  mov     [rax+10h], rsi
0x18007b203  lea     edx, [rsi+8]; unsigned __int64
0x18007b206  mov     [rax+18h], rsi
0x18007b20a  mov     rcx, rax; this
0x18007b20d  mov     [rax+20h], rsi
0x18007b211  mov     cs:?g_pErrInfoCollection@@3PEAVCExtBuffer@@EA, rax; CExtBuffer * g_pErrInfoCollection
0x18007b218  mov     [rsp+48h+var_28], rbp; unsigned __int64
0x18007b21d  call    ?FInit@CExtBuffer@@QEAAH_KPEAX00@Z; CExtBuffer::FInit(unsigned __int64,void *,unsigned __int64,unsigned __int64)
0x18007b222  test    eax, eax
0x18007b224  jz      loc_18007B356
0x18007b22a  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18007b231  lea     r8d, [rsi+28h]
0x18007b235  mov     edx, 1300000h
0x18007b23a  call    cs:__imp_MpHeapAlloc
0x18007b240  mov     [rsp+48h+var_18], rax
0x18007b245  test    rax, rax
0x18007b248  jz      short loc_18007B289
0x18007b24a  mov     r9d, ebp; unsigned __int64
0x18007b24d  mov     [rax], rsi
0x18007b250  lea     r8, [rsp+48h+arg_10]; void *
0x18007b255  mov     [rax+8], rsi
0x18007b259  lea     edx, [rsi+8]; unsigned __int64
0x18007b25c  mov     [rax+10h], rsi
0x18007b260  mov     rcx, rax; this
0x18007b263  mov     [rax+18h], rsi
0x18007b267  mov     [rax+20h], rsi
0x18007b26b  mov     cs:?g_pClassFactoryCollection@@3PEAVCExtBuffer@@EA, rax; CExtBuffer * g_pClassFactoryCollection
0x18007b272  mov     [rsp+48h+var_28], rbp; unsigned __int64
0x18007b277  call    ?FInit@CExtBuffer@@QEAAH_KPEAX00@Z; CExtBuffer::FInit(unsigned __int64,void *,unsigned __int64,unsigned __int64)
0x18007b27c  test    eax, eax
0x18007b27e  jz      loc_18007B356
0x18007b284  jmp     loc_18007B351
0x18007b289  mov     cs:?g_pClassFactoryCollection@@3PEAVCExtBuffer@@EA, rsi; CExtBuffer * g_pClassFactoryCollection
0x18007b290  jmp     loc_18007B356
0x18007b295  mov     cs:?g_pErrInfoCollection@@3PEAVCExtBuffer@@EA, rsi; CExtBuffer * g_pErrInfoCollection
0x18007b29c  jmp     loc_18007B356
0x18007b2a1  test    byte ptr cs:_bidGblFlags, 2
0x18007b2a8  jz      loc_18007B356
0x18007b2ae  mov     r8d, 44h ; 'D'; unsigned int
0x18007b2b4  lea     rdx, aErrcollinitOle; "<ErrCollInit|OLEDB|ERR> "
0x18007b2bb  mov     ecx, eax; int
0x18007b2bd  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18007b2c2  jmp     loc_18007B356
0x18007b2c7  lea     rcx, [rsp+48h+arg_0]
0x18007b2cc  mov     [rsp+48h+arg_0], rsi
0x18007b2d1  call    cs:__imp_GetIUMS
0x18007b2d7  cmp     [rsp+48h+arg_0], rsi
0x18007b2dc  jnz     short loc_18007B351
0x18007b2de  mov     rax, cs:?g_pErrorCollectionListHeader@@3REAVCError@@EA; CError * g_pErrorCollectionListHeader
0x18007b2e5  mov     cs:?g_fProcessDetaching@@3HA, 1; int g_fProcessDetaching
0x18007b2ef  test    rax, rax
0x18007b2f2  jnz     short loc_18007B306
0x18007b2f4  cmp     cs:?g_pErrInfoCollection@@3PEAVCExtBuffer@@EA, rsi; CExtBuffer * g_pErrInfoCollection
0x18007b2fb  jnz     short loc_18007B306
0x18007b2fd  cmp     cs:?g_pClassFactoryCollection@@3PEAVCExtBuffer@@EA, rsi; CExtBuffer * g_pClassFactoryCollection
0x18007b304  jz      short loc_18007B30B
0x18007b306  call    ?ReleaseObjectCollections@@YAXXZ; ReleaseObjectCollections(void)
0x18007b30b  mov     rcx, cs:?g_pIMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pIMalloc
0x18007b312  test    rcx, rcx
0x18007b315  jz      short loc_18007B32A
0x18007b317  mov     rax, [rcx]
0x18007b31a  mov     rax, [rax+10h]
0x18007b31e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b323  mov     cs:?g_pIMalloc@@3PEAUIMalloc@@EA, rsi; IMalloc * g_pIMalloc
0x18007b32a  lea     rcx, ?g_csErrorCollection@@3PEAVCCriticalSection@@EA; CCriticalSection * g_csErrorCollection
0x18007b331  call    cs:__imp_MPDeleteCriticalSection
0x18007b337  lea     rcx, ?g_csErrInfoCollection@@3PEAVCCriticalSection@@EA; CCriticalSection * g_csErrInfoCollection
0x18007b33e  call    cs:__imp_MPDeleteCriticalSection
0x18007b344  lea     rcx, ?g_csClassFactoryCollection@@3PEAVCCriticalSection@@EA; CCriticalSection * g_csClassFactoryCollection
0x18007b34b  call    cs:__imp_MPDeleteCriticalSection
0x18007b351  mov     edi, 1
0x18007b356  mov     rbp, [rsp+48h+arg_8]
0x18007b35b  mov     eax, edi
0x18007b35d  mov     rsi, [rsp+48h+arg_18]
0x18007b362  add     rsp, 40h
0x18007b366  pop     rdi
0x18007b367  retn
```
