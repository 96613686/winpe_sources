# W3_RESPONSE::HandleCompletion(ulong,long)

- ea: `0x1800016a0`
- end: `0x1800018c2`
- name: `?HandleCompletion@W3_RESPONSE@@UEAA?AW4ASYNC_STATUS@@KJ@Z`
- size: `546`
- prototype: `__int64 __fastcall(__int64, unsigned int, signed int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800016a0`
- `0x1800018c8`
- `0x180003be0`
- `0x180009030`
- `0x180017964`
- `0x18002704c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800018a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800018a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000178e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000178e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001773`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001895`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001773`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001895`

## pseudocode

```c
__int64 __fastcall W3_RESPONSE::HandleCompletion(__int64 a1, unsigned int a2, signed int a3)
{
  __int64 v6; // rcx
  __int64 v7; // rcx
  unsigned int i; // edi
  unsigned int v9; // edi
  LPVOID *Ptr; // rax
  __int64 v12; // rax
  unsigned int v13; // r9d
  W3_MAIN_CONTEXT *v14; // rdi
  struct _HTTP_LOG_DATA *v15; // rcx
  HANDLE *v16; // rax
  unsigned int v17; // [rsp+68h] [rbp+10h] BYREF
  int v18; // [rsp+70h] [rbp+18h] BYREF

  v17 = a2;
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 48) + 392LL) + 9488LL) += a2;
  v6 = *(_QWORD *)(a1 + 48);
  if ( *(_BYTE *)(v6 + 9098)
    && (unsigned int)WWWServerTraceProvider::CheckTracingEnabled((v6 + 8) & -(__int64)(v6 != 0), 0, 4) )
  {
    IISGeneralEvents::GENERAL_FLUSH_RESPONSE_END::RaiseEvent(
      (struct IHttpTraceContext *)((*(_QWORD *)(a1 + 48) + 8LL) & -(__int64)(*(_QWORD *)(a1 + 48) != 0)),
      (const struct _GUID *)(*(_QWORD *)(a1 + 48) + 8LL),
      a2,
      a3);
  }
  if ( a3 >= 0 )
  {
    v7 = *(_QWORD *)(a1 + 1560);
    if ( v7 )
    {
      v12 = *(_QWORD *)(a1 + 48);
      v13 = *(_DWORD *)(a1 + 1556);
      v18 = 0;
      v14 = *(W3_MAIN_CONTEXT **)(v12 + 392);
      LOWORD(v12) = *(_WORD *)(a1 + 1552);
      *(_QWORD *)(a1 + 600) = v7;
      v15 = *(struct _HTTP_LOG_DATA **)(a1 + 1568);
      *(_WORD *)(a1 + 592) = v12;
      *(_QWORD *)(a1 + 1560) = 0;
      *(_DWORD *)(a1 + 1552) = 0;
      *(_DWORD *)(a1 + 1556) = 0;
      *(_QWORD *)(a1 + 1568) = 0;
      *(_QWORD *)(a1 + 8) = *((_QWORD *)v14 + 1179);
      *((_QWORD *)v14 + 1179) = a1;
      if ( (int)W3_RESPONSE::ResumeResponseTransfer((W3_RESPONSE *)a1, 1, 0, v13, v15, &v17, &v18) >= 0 && v18 )
        return 1;
      W3_MAIN_CONTEXT::PopAsyncSendContext(v14);
    }
  }
  _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)IISCORE_ASYNC_CONTEXT::ResetIoCompletionContext((IISCORE_ASYNC_CONTEXT *)a1)
                                                    + 10)
                                                  + 52LL));
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 48) + 392LL) + 9356LL) &= ~2u;
  *(_WORD *)(a1 + 592) = 0;
  *(_QWORD *)(a1 + 600) = 0;
  *(_QWORD *)(a1 + 1560) = 0;
  *(_DWORD *)(a1 + 1552) = 0;
  if ( *(_BYTE *)(a1 + 1549) )
  {
    for ( i = 0; i < *(_DWORD *)(a1 + 1536); ++i )
    {
      Ptr = (LPVOID *)BUFFER::QueryPtr((BUFFER *)(a1 + 1440));
      HeapFree(W3_RESPONSE::sm_hResponseBufferHeap, 0, Ptr[i]);
    }
    v9 = 0;
    for ( *(_DWORD *)(a1 + 1536) = 0; v9 < *(_DWORD *)(a1 + 1540); ++v9 )
    {
      v16 = (HANDLE *)BUFFER::QueryPtr((BUFFER *)(a1 + 1488));
      CloseHandle(v16[v9]);
    }
    *(_QWORD *)(a1 + 1540) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800016a0  mov     [rsp+arg_0], rbx
0x1800016a5  mov     [rsp+arg_8], edx
0x1800016a9  push    rbp
0x1800016aa  push    rsi
0x1800016ab  push    rdi
0x1800016ac  sub     rsp, 40h
0x1800016b0  mov     rax, [rcx+30h]
0x1800016b4  mov     rbx, rcx
0x1800016b7  xor     ebp, ebp
0x1800016b9  mov     esi, r8d
0x1800016bc  mov     edi, edx
0x1800016be  mov     r9, [rax+188h]
0x1800016c5  add     [r9+2510h], edx
0x1800016cc  mov     rcx, [rcx+30h]
0x1800016d0  cmp     [rcx+238Ah], bpl
0x1800016d7  jnz     loc_1800017A6
0x1800016dd  test    esi, esi
0x1800016df  js      short loc_1800016F1
0x1800016e1  mov     rcx, [rbx+618h]
0x1800016e8  test    rcx, rcx
0x1800016eb  jnz     loc_1800017E7
0x1800016f1  mov     rcx, rbx; this
0x1800016f4  call    ?ResetIoCompletionContext@IISCORE_ASYNC_CONTEXT@@QEAAPEAVW3_CONTEXT_BASE@@XZ; IISCORE_ASYNC_CONTEXT::ResetIoCompletionContext(void)
0x1800016f9  mov     rcx, [rax+50h]
0x1800016fd  lock dec dword ptr [rcx+34h]
0x180001701  mov     rax, [rbx+30h]
0x180001705  mov     rcx, [rax+188h]
0x18000170c  and     dword ptr [rcx+248Ch], 0FFFFFFFDh
0x180001713  mov     [rbx+250h], bp
0x18000171a  mov     [rbx+258h], rbp
0x180001721  mov     [rbx+618h], rbp
0x180001728  mov     [rbx+610h], ebp
0x18000172e  cmp     [rbx+60Dh], bpl
0x180001735  jz      short loc_18000175C
0x180001737  mov     edi, ebp
0x180001739  cmp     [rbx+600h], ebp
0x18000173f  ja      short loc_18000176C
0x180001741  mov     edi, ebp
0x180001743  mov     [rbx+600h], ebp
0x180001749  cmp     [rbx+604h], ebp
0x18000174f  ja      loc_18000188E
0x180001755  mov     [rbx+604h], rbp
0x18000175c  xor     eax, eax
0x18000175e  mov     rbx, [rsp+58h+arg_0]
0x180001763  add     rsp, 40h
0x180001767  pop     rdi
0x180001768  pop     rsi
0x180001769  pop     rbp
0x18000176a  retn
0x18000176c  lea     rcx, [rbx+5A0h]
0x180001773  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000177a  nop     dword ptr [rax+rax+00h]
0x18000177f  mov     ecx, edi
0x180001781  xor     edx, edx; dwFlags
0x180001783  mov     r8, [rax+rcx*8]; lpMem
0x180001787  mov     rcx, cs:?sm_hResponseBufferHeap@W3_RESPONSE@@0PEAXEA; hHeap
0x18000178e  call    cs:__imp_HeapFree
0x180001795  nop     dword ptr [rax+rax+00h]
0x18000179a  inc     edi
0x18000179c  cmp     edi, [rbx+600h]
0x1800017a2  jnb     short loc_180001741
0x1800017a4  jmp     short loc_18000176C
0x1800017a6  lea     rax, [rcx+8]
0x1800017aa  neg     rcx
0x1800017ad  sbb     rcx, rcx
0x1800017b0  xor     edx, edx
0x1800017b2  and     rcx, rax
0x1800017b5  lea     r8d, [rdx+4]
0x1800017b9  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x1800017be  test    eax, eax
0x1800017c0  jz      loc_1800016DD
0x1800017c6  mov     rax, [rbx+30h]
0x1800017ca  mov     r9d, esi; unsigned int
0x1800017cd  mov     r8d, edi; unsigned int
0x1800017d0  lea     rdx, [rax+8]; struct _GUID *
0x1800017d4  neg     rax
0x1800017d7  sbb     rcx, rcx
0x1800017da  and     rcx, rdx; struct IHttpTraceContext *
0x1800017dd  call    ?RaiseEvent@GENERAL_FLUSH_RESPONSE_END@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KK@Z; IISGeneralEvents::GENERAL_FLUSH_RESPONSE_END::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,ulong)
0x1800017e2  jmp     loc_1800016DD
0x1800017e7  mov     rax, [rbx+30h]
0x1800017eb  lea     rdx, [rsp+58h+arg_8]
0x1800017f0  mov     r9d, [rbx+614h]; unsigned int
0x1800017f7  xor     r8d, r8d; int
0x1800017fa  mov     [rsp+58h+arg_10], ebp
0x1800017fe  mov     rdi, [rax+188h]
0x180001805  movzx   eax, word ptr [rbx+610h]
0x18000180c  mov     [rbx+258h], rcx
0x180001813  mov     rcx, [rbx+620h]
0x18000181a  mov     [rbx+250h], ax
0x180001821  mov     [rbx+618h], rbp
0x180001828  mov     [rbx+610h], ebp
0x18000182e  mov     [rbx+614h], ebp
0x180001834  mov     [rbx+620h], rbp
0x18000183b  mov     rax, [rdi+24D8h]
0x180001842  mov     [rbx+8], rax
0x180001846  lea     rax, [rsp+58h+arg_10]
0x18000184b  mov     [rsp+58h+var_28], rax; int *
0x180001850  mov     [rsp+58h+var_30], rdx; unsigned int *
0x180001855  lea     edx, [r8+1]; int
0x180001859  mov     [rsp+58h+var_38], rcx; struct _HTTP_LOG_DATA *
0x18000185e  mov     rcx, rbx; this
0x180001861  mov     [rdi+24D8h], rbx
0x180001868  call    ?ResumeResponseTransfer@W3_RESPONSE@@AEAAJHHKPEAU_HTTP_LOG_DATA@@PEAKPEAH@Z; W3_RESPONSE::ResumeResponseTransfer(int,int,ulong,_HTTP_LOG_DATA *,ulong *,int *)
0x18000186d  test    eax, eax
0x18000186f  js      short loc_180001881
0x180001871  cmp     [rsp+58h+arg_10], ebp
0x180001875  jz      short loc_180001881
0x180001877  mov     eax, 1
0x18000187c  jmp     loc_18000175E
0x180001881  mov     rcx, rdi; this
0x180001884  call    ?PopAsyncSendContext@W3_MAIN_CONTEXT@@QEAAPEAVIISCORE_ASYNC_CONTEXT@@XZ; W3_MAIN_CONTEXT::PopAsyncSendContext(void)
0x180001889  jmp     loc_1800016F1
0x18000188e  lea     rcx, [rbx+5D0h]
0x180001895  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000189c  nop     dword ptr [rax+rax+00h]
0x1800018a1  mov     ecx, edi
0x1800018a3  mov     rcx, [rax+rcx*8]; hObject
0x1800018a7  call    cs:__imp_CloseHandle
0x1800018ae  nop     dword ptr [rax+rax+00h]
0x1800018b3  inc     edi
0x1800018b5  cmp     edi, [rbx+604h]
0x1800018bb  jb      short loc_18000188E
0x1800018bd  jmp     loc_180001755
```
