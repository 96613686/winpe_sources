# CTSBufferResult::CreateInstance(CTSObjectPool<CTSBufferResult> *,ulong,void *,CTSBufferResult * *)

- ea: `0x180029688`
- end: `0x1800297dd`
- name: `?CreateInstance@CTSBufferResult@@SAJPEAV?$CTSObjectPool@VCTSBufferResult@@@@KPEAXPEAPEAV1@@Z`
- size: `341`
- prototype: `__int64 __fastcall(__int64, unsigned int, void *, struct CTSBufferResult **)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x1800248a0`
- `0x1800249b0`
- `0x180027e10`

## callees

- `0x1800010f8`
- `0x18001d114`
- `0x1800294b0`
- `0x180029688`
- `0x180029818`
- `0x180029bac`
- `0x18002a1c4`
- `0x18002c010`

## string_xrefs

- `0x18002979e`: `CTSBufferResult::CreateInstance failed!`

## pseudocode

```c
__int64 __fastcall CTSBufferResult::CreateInstance(__int64 a1, unsigned int a2, void *a3, struct CTSBufferResult **a4)
{
  __int64 v7; // rdx
  int PooledObject; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  int ActivityIdPrefix; // eax
  int v12; // edx
  const char *v13; // rcx
  CTSBufferResult *v14; // rdi
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  int v22; // [rsp+28h] [rbp-20h]
  CTSBufferResult *v23; // [rsp+68h] [rbp+20h] BYREF

  v23 = 0;
  *a4 = 0;
  PooledObject = CTSObjectPool<CTSBufferResult>::GetPooledObject(a1, &v23);
  if ( PooledObject >= 0 )
  {
    v14 = v23;
    PooledObject = CTSBufferResult::InitializeForReuse(v23, a2, a3);
    if ( PooledObject < 0 )
    {
      if ( (unsigned int)dword_180044008 > 4 )
      {
        v23 = (CTSBufferResult *)"Can't reuse buffer result from pool, so creating new one.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v15,
          (__int64)word_18003FED2,
          v16,
          v17,
          (const unsigned __int16 **)&v23);
      }
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v14 + 4) + 16LL))(*((_QWORD *)v14 + 4));
      PooledObject = CTSBufferResult::CreateInstance(a4, a2, a3);
      if ( PooledObject < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v18, v19, v20);
        v12 = 33;
        v13 = "CTSBufferResult::CreateInstance failed!";
        goto LABEL_15;
      }
    }
    else
    {
      *a4 = v14;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v7, v9, v10);
    v12 = 32;
    v13 = "GetPooledObject(CTSBufferResult) failed";
LABEL_15:
    v22 = PooledObject;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      (unsigned int)WPP_45c8207700f83d40fa4666bbba92ada0_Traceguids,
      ActivityIdPrefix,
      (__int64)v13,
      v22);
  }
  return (unsigned int)PooledObject;
}

```

## disassembly

```asm
0x180029688  mov     rax, rsp
0x18002968b  mov     [rax+8], rbx
0x18002968f  mov     [rax+10h], rbp
0x180029693  push    rsi
0x180029694  push    rdi
0x180029695  push    r14
0x180029697  sub     rsp, 30h
0x18002969b  mov     rsi, r9
0x18002969e  mov     qword ptr [rax+20h], 0
0x1800296a6  mov     rbp, r8
0x1800296a9  mov     r14d, edx
0x1800296ac  lea     rdx, [rax+20h]
0x1800296b0  mov     qword ptr [r9], 0
0x1800296b7  call    ?GetPooledObject@?$CTSObjectPool@VCTSBufferResult@@@@QEAAJPEAPEAVCTSBufferResult@@H@Z; CTSObjectPool<CTSBufferResult>::GetPooledObject(CTSBufferResult * *,int)
0x1800296bc  mov     ebx, eax
0x1800296be  test    eax, eax
0x1800296c0  jns     short loc_180029703
0x1800296c2  mov     rax, cs:WPP_GLOBAL_Control
0x1800296c9  lea     rcx, WPP_GLOBAL_Control
0x1800296d0  cmp     rax, rcx
0x1800296d3  jz      loc_1800297C8
0x1800296d9  test    byte ptr [rax+1Ch], 8
0x1800296dd  jz      loc_1800297C8
0x1800296e3  cmp     byte ptr [rax+19h], 2
0x1800296e7  jb      loc_1800297C8
0x1800296ed  call    RdpX_GetActivityIdPrefix
0x1800296f2  mov     edx, 20h ; ' '
0x1800296f7  lea     rcx, aGetpooledobjec; "GetPooledObject(CTSBufferResult) failed"
0x1800296fe  jmp     loc_1800297A5
0x180029703  mov     rdi, [rsp+48h+arg_18]
0x180029708  mov     r8, rbp; void *
0x18002970b  mov     rcx, rdi; this
0x18002970e  mov     edx, r14d; unsigned int
0x180029711  call    ?InitializeForReuse@CTSBufferResult@@IEAAJKPEAX@Z; CTSBufferResult::InitializeForReuse(ulong,void *)
0x180029716  mov     ebx, eax
0x180029718  test    eax, eax
0x18002971a  js      short loc_180029724
0x18002971c  mov     [rsi], rdi
0x18002971f  jmp     loc_1800297C8
0x180029724  mov     eax, cs:dword_180044008
0x18002972a  cmp     eax, 4
0x18002972d  jbe     short loc_180029751
0x18002972f  lea     rax, aCanTReuseBuffe; "Can't reuse buffer result from pool, so"...
0x180029736  mov     [rsp+48h+arg_18], rax
0x18002973b  lea     rdx, word_18003FED2
0x180029742  lea     rax, [rsp+48h+arg_18]
0x180029747  mov     [rsp+48h+var_28], rax
0x18002974c  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180029751  mov     rcx, [rdi+20h]
0x180029755  mov     rax, [rcx]
0x180029758  mov     rax, [rax+10h]
0x18002975c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029761  mov     r8, rbp; void *
0x180029764  mov     edx, r14d; unsigned int
0x180029767  mov     rcx, rsi; struct CTSBufferResult **
0x18002976a  call    ?CreateInstance@CTSBufferResult@@SAJPEAPEAV1@KPEAX@Z; CTSBufferResult::CreateInstance(CTSBufferResult * *,ulong,void *)
0x18002976f  mov     ebx, eax
0x180029771  test    eax, eax
0x180029773  jns     short loc_1800297C8
0x180029775  mov     rax, cs:WPP_GLOBAL_Control
0x18002977c  lea     rcx, WPP_GLOBAL_Control
0x180029783  cmp     rax, rcx
0x180029786  jz      short loc_1800297C8
0x180029788  test    byte ptr [rax+1Ch], 8
0x18002978c  jz      short loc_1800297C8
0x18002978e  cmp     byte ptr [rax+19h], 2
0x180029792  jb      short loc_1800297C8
0x180029794  call    RdpX_GetActivityIdPrefix
0x180029799  mov     edx, 21h ; '!'
0x18002979e  lea     rcx, aCtsbufferresul_0; "CTSBufferResult::CreateInstance failed!"
0x1800297a5  mov     [rsp+48h+var_20], ebx
0x1800297a9  lea     r8, WPP_45c8207700f83d40fa4666bbba92ada0_Traceguids
0x1800297b0  mov     [rsp+48h+var_28], rcx
0x1800297b5  mov     r9d, eax
0x1800297b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800297bf  mov     rcx, [rcx+10h]
0x1800297c3  call    WPP_SF_DsD
0x1800297c8  mov     rbp, [rsp+48h+arg_8]
0x1800297cd  mov     eax, ebx
0x1800297cf  mov     rbx, [rsp+48h+arg_0]
0x1800297d4  add     rsp, 30h
0x1800297d8  pop     r14
0x1800297da  pop     rdi
0x1800297db  pop     rsi
0x1800297dc  retn
```
