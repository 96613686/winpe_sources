# CConnStrParsingManager::InsertConnStrParsingCacheItem(CDPO *)

- ea: `0x180060ca0`
- end: `0x180060e8e`
- name: `?InsertConnStrParsingCacheItem@CConnStrParsingManager@@QEAAJPEAVCDPO@@@Z`
- size: `494`
- prototype: `__int64 __fastcall(CConnStrParsingManager *__hidden this, struct CDPO *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001f680`

## callees

- `0x180013870`
- `0x180015be8`
- `0x180060c50`
- `0x180060c78`
- `0x180060ca0`
- `0x180060e94`

## import_xrefs

- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180060d47`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180060e68`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180060d47`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180060e68`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180060d21`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180060d21`
- `MSDART!?ReadUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180060d0c`
- `MSDART!?ReadUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180060d0c`
- `MSDART!?ReadLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180060ce8`
- `MSDART!?ReadLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180060ce8`
- `MSDART!MpHeapAlloc` at `0x180060d61`
- `MSDART!MpHeapAlloc` at `0x180060d61`

## string_xrefs

- `0x180060e57`: `<CConnStrParsingManager::InsertConnStrParsingCacheItem|OLEDB|ERR> `

## pseudocode

```c
__int64 __fastcall CConnStrParsingManager::InsertConnStrParsingCacheItem(CConnStrParsingManager *this, struct CDPO *a2)
{
  CConnStrParsingManager *v2; // r14
  unsigned int v4; // ebp
  CReaderWriterLock3AR *v5; // rdi
  struct CConnStrParsingCacheItem *v6; // rbx
  __int64 v8; // rax
  __int64 v9; // rbx
  _OWORD *v10; // rax
  unsigned int v11; // r8d
  volatile signed __int32 *v12; // rax
  unsigned int v13; // edx
  CConnStrParsingManager *v14; // [rsp+50h] [rbp+8h] BYREF
  struct tagDBPROPSET *v15; // [rsp+58h] [rbp+10h] BYREF

  v14 = this;
  v2 = _ConnStrParsingManager;
  v4 = CConnStrParsingManager::ComputeHash(*((unsigned __int8 *const *)a2 + 32), *((unsigned int *)a2 + 66));
  v5 = (CConnStrParsingManager *)((char *)v2 + 8 * v4 + 4 * v4 + 512);
  CReaderWriterLock3AR::ReadLock(v5);
  v6 = CConnStrParsingManager::InternalSearchConnStrParsingCacheItem(
         v2,
         v4,
         *((unsigned __int8 **)a2 + 32),
         *((_DWORD *)a2 + 32));
  CReaderWriterLock3AR::ReadUnlock(v5);
  if ( v6 )
    return 0;
  CReaderWriterLock3AR::WriteLock(v5);
  if ( CConnStrParsingManager::InternalSearchConnStrParsingCacheItem(
         v2,
         v4,
         *((unsigned __int8 **)a2 + 32),
         *((_DWORD *)a2 + 32)) )
  {
LABEL_4:
    CReaderWriterLock3AR::WriteUnlock(v5);
    return 0;
  }
  v8 = MpHeapAlloc(g_hHeapHandle, 19922944, 72);
  v14 = (CConnStrParsingManager *)v8;
  v9 = v8;
  if ( v8 )
  {
    *(_DWORD *)(v8 + 32) = 0;
    *(_DWORD *)(v8 + 36) = 1;
    *(_QWORD *)(v8 + 40) = 0;
    *(_DWORD *)(v8 + 48) = 0;
    *(_QWORD *)(v8 + 56) = 0;
    *(_QWORD *)(v8 + 64) = 0;
    *(_OWORD *)v8 = 0;
    *(_OWORD *)(v8 + 16) = 0;
    v10 = (_OWORD *)*((_QWORD *)a2 + 32);
    LODWORD(v14) = 0;
    v15 = 0;
    *(_OWORD *)v9 = *v10;
    *(_OWORD *)(v9 + 16) = v10[1];
    *(_DWORD *)(v9 + 32) = *((_DWORD *)a2 + 32);
    if ( (int)CDPOPropertySetArray::GetPropertiesPrivate(
                (struct CDPO *)((char *)a2 + 184),
                (unsigned int *)&v14,
                &v15,
                0) >= 0 )
    {
      *(_DWORD *)(v9 + 48) = (_DWORD)v14;
      *(_QWORD *)(v9 + 56) = v15;
      v12 = (volatile signed __int32 *)*((_QWORD *)a2 + 15);
      *(_QWORD *)(v9 + 64) = v12;
      _InterlockedIncrement(v12);
      *(_QWORD *)(v9 + 40) = *((_QWORD *)v2 + v4);
      *((_QWORD *)v2 + v4) = v9;
      goto LABEL_4;
    }
    if ( (bidGblFlags & 2) != 0 )
    {
      v11 = 212;
LABEL_12:
      OLEDBTraceErr(-2147024882, L"<CConnStrParsingManager::InsertConnStrParsingCacheItem|OLEDB|ERR> ", v11);
    }
  }
  else
  {
    v9 = 0;
    if ( (bidGblFlags & 2) != 0 )
    {
      v11 = 197;
      goto LABEL_12;
    }
  }
  CReaderWriterLock3AR::WriteUnlock(v5);
  if ( v9 )
    CConnStrParsingCacheItem::`scalar deleting destructor'((CConnStrParsingCacheItem *)v9, v13);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180060ca0  mov     [rsp+arg_10], rbx
0x180060ca5  mov     [rsp+arg_0], rcx
0x180060caa  push    rbp
0x180060cab  push    rsi
0x180060cac  push    rdi
0x180060cad  push    r14
0x180060caf  push    r15
0x180060cb1  sub     rsp, 20h
0x180060cb5  mov     r14, cs:?_ConnStrParsingManager@@3PEAVCConnStrParsingManager@@EA; CConnStrParsingManager * _ConnStrParsingManager
0x180060cbc  mov     rsi, rdx
0x180060cbf  mov     edx, [rdx+108h]; unsigned __int64
0x180060cc5  mov     rcx, [rsi+100h]; unsigned __int8 *
0x180060ccc  call    ?ComputeHash@CConnStrParsingManager@@CAKQEAE_K@Z; CConnStrParsingManager::ComputeHash(uchar * const,unsigned __int64)
0x180060cd1  mov     ebp, eax
0x180060cd3  mov     r15d, eax
0x180060cd6  lea     rcx, ds:80h[rbp*2]
0x180060cde  add     rcx, rbp
0x180060ce1  lea     rdi, [r14+rcx*4]
0x180060ce5  mov     rcx, rdi
0x180060ce8  call    cs:__imp_?ReadLock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::ReadLock(void)
0x180060cee  mov     r9d, [rsi+80h]; unsigned int
0x180060cf5  mov     edx, ebp; unsigned int
0x180060cf7  mov     r8, [rsi+100h]; unsigned __int8 *
0x180060cfe  mov     rcx, r14; this
0x180060d01  call    ?InternalSearchConnStrParsingCacheItem@CConnStrParsingManager@@AEAAPEAVCConnStrParsingCacheItem@@KPEAEK@Z; CConnStrParsingManager::InternalSearchConnStrParsingCacheItem(ulong,uchar *,ulong)
0x180060d06  mov     rcx, rdi
0x180060d09  mov     rbx, rax
0x180060d0c  call    cs:__imp_?ReadUnlock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::ReadUnlock(void)
0x180060d12  test    rbx, rbx
0x180060d15  jz      short loc_180060D1E
0x180060d17  xor     eax, eax
0x180060d19  jmp     loc_180060E7D
0x180060d1e  mov     rcx, rdi
0x180060d21  call    cs:__imp_?WriteLock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteLock(void)
0x180060d27  mov     r9d, [rsi+80h]; unsigned int
0x180060d2e  mov     edx, ebp; unsigned int
0x180060d30  mov     r8, [rsi+100h]; unsigned __int8 *
0x180060d37  mov     rcx, r14; this
0x180060d3a  call    ?InternalSearchConnStrParsingCacheItem@CConnStrParsingManager@@AEAAPEAVCConnStrParsingCacheItem@@KPEAEK@Z; CConnStrParsingManager::InternalSearchConnStrParsingCacheItem(ulong,uchar *,ulong)
0x180060d3f  test    rax, rax
0x180060d42  jz      short loc_180060D4F
0x180060d44  mov     rcx, rdi
0x180060d47  call    cs:__imp_?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteUnlock(void)
0x180060d4d  jmp     short loc_180060D17
0x180060d4f  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180060d56  mov     edx, 1300000h
0x180060d5b  mov     r8d, 48h ; 'H'
0x180060d61  call    cs:__imp_MpHeapAlloc
0x180060d67  mov     [rsp+48h+arg_0], rax
0x180060d6c  mov     rbx, rax
0x180060d6f  mov     ebp, 8007000Eh
0x180060d74  test    rax, rax
0x180060d77  jz      loc_180060E46
0x180060d7d  mov     dword ptr [rax+20h], 0
0x180060d84  xorps   xmm0, xmm0
0x180060d87  mov     dword ptr [rax+24h], 1
0x180060d8e  mov     qword ptr [rax+28h], 0
0x180060d96  mov     dword ptr [rax+30h], 0
0x180060d9d  mov     qword ptr [rax+38h], 0
0x180060da5  mov     qword ptr [rax+40h], 0
0x180060dad  movups  xmmword ptr [rax], xmm0
0x180060db0  movups  xmmword ptr [rax+10h], xmm0
0x180060db4  test    rax, rax
0x180060db7  jz      loc_180060E48
0x180060dbd  mov     rax, [rsi+100h]
0x180060dc4  lea     rcx, [rsi+0B8h]; this
0x180060dcb  xor     r9d, r9d; int
0x180060dce  mov     dword ptr [rsp+48h+arg_0], 0
0x180060dd6  lea     r8, [rsp+48h+arg_8]; struct tagDBPROPSET **
0x180060ddb  mov     [rsp+48h+arg_8], 0
0x180060de4  lea     rdx, [rsp+48h+arg_0]; unsigned int *
0x180060de9  movups  xmm0, xmmword ptr [rax]
0x180060dec  movups  xmmword ptr [rbx], xmm0
0x180060def  movups  xmm1, xmmword ptr [rax+10h]
0x180060df3  movups  xmmword ptr [rbx+10h], xmm1
0x180060df7  mov     eax, [rsi+80h]
0x180060dfd  mov     [rbx+20h], eax
0x180060e00  call    ?GetPropertiesPrivate@CDPOPropertySetArray@@QEAAJPEAKPEAPEAUtagDBPROPSET@@H@Z; CDPOPropertySetArray::GetPropertiesPrivate(ulong *,tagDBPROPSET * *,int)
0x180060e05  test    eax, eax
0x180060e07  jns     short loc_180060E1A
0x180060e09  test    byte ptr cs:_bidGblFlags, 2
0x180060e10  jz      short loc_180060E65
0x180060e12  mov     r8d, 0D4h
0x180060e18  jmp     short loc_180060E57
0x180060e1a  mov     eax, dword ptr [rsp+48h+arg_0]
0x180060e1e  mov     [rbx+30h], eax
0x180060e21  mov     rax, [rsp+48h+arg_8]
0x180060e26  mov     [rbx+38h], rax
0x180060e2a  mov     rax, [rsi+78h]
0x180060e2e  mov     [rbx+40h], rax
0x180060e32  lock inc dword ptr [rax]
0x180060e35  mov     rax, [r14+r15*8]
0x180060e39  mov     [rbx+28h], rax
0x180060e3d  mov     [r14+r15*8], rbx
0x180060e41  jmp     loc_180060D44
0x180060e46  xor     ebx, ebx
0x180060e48  test    byte ptr cs:_bidGblFlags, 2
0x180060e4f  jz      short loc_180060E65
0x180060e51  mov     r8d, 0C5h; unsigned int
0x180060e57  lea     rdx, aCconnstrparsin; "<CConnStrParsingManager::InsertConnStrP"...
0x180060e5e  mov     ecx, ebp; int
0x180060e60  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180060e65  mov     rcx, rdi
0x180060e68  call    cs:__imp_?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteUnlock(void)
0x180060e6e  test    rbx, rbx
0x180060e71  jz      short loc_180060E7B
0x180060e73  mov     rcx, rbx; this
0x180060e76  call    ??_GCConnStrParsingCacheItem@@QEAAPEAXI@Z; CConnStrParsingCacheItem::`scalar deleting destructor'(uint)
0x180060e7b  mov     eax, ebp
0x180060e7d  mov     rbx, [rsp+48h+arg_10]
0x180060e82  add     rsp, 20h
0x180060e86  pop     r15
0x180060e88  pop     r14
0x180060e8a  pop     rdi
0x180060e8b  pop     rsi
0x180060e8c  pop     rbp
0x180060e8d  retn
```
