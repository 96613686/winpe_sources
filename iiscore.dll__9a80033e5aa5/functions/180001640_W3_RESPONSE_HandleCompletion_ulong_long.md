# W3_RESPONSE::HandleCompletion(ulong,long)

- ea: `0x180001640`
- end: `0x180001849`
- name: `?HandleCompletion@W3_RESPONSE@@UEAA?AW4ASYNC_STATUS@@KJ@Z`
- size: `521`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001640`
- `0x180001850`
- `0x1800021c8`
- `0x1800038f0`
- `0x180008930`
- `0x18002507c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001834`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001834`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001727`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001727`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001712`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001828`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001712`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001828`

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
0x180001640  mov     [rsp+arg_0], rbx
0x180001645  mov     [rsp+arg_8], edx
0x180001649  push    rbp
0x18000164a  push    rsi
0x18000164b  push    rdi
0x18000164c  sub     rsp, 40h
0x180001650  mov     rax, [rcx+30h]
0x180001654  mov     rbx, rcx
0x180001657  xor     ebp, ebp
0x180001659  mov     esi, r8d
0x18000165c  mov     edi, edx
0x18000165e  mov     r9, [rax+188h]
0x180001665  add     [r9+2510h], edx
0x18000166c  mov     rcx, [rcx+30h]
0x180001670  cmp     [rcx+238Ah], bpl
0x180001677  jnz     loc_180001739
0x18000167d  test    esi, esi
0x18000167f  js      short loc_180001691
0x180001681  mov     rcx, [rbx+618h]
0x180001688  test    rcx, rcx
0x18000168b  jnz     loc_18000177A
0x180001691  mov     rcx, rbx; this
0x180001694  call    ?ResetIoCompletionContext@IISCORE_ASYNC_CONTEXT@@QEAAPEAVW3_CONTEXT_BASE@@XZ; IISCORE_ASYNC_CONTEXT::ResetIoCompletionContext(void)
0x180001699  mov     rcx, [rax+50h]
0x18000169d  lock dec dword ptr [rcx+34h]
0x1800016a1  mov     rax, [rbx+30h]
0x1800016a5  mov     rcx, [rax+188h]
0x1800016ac  and     dword ptr [rcx+248Ch], 0FFFFFFFDh
0x1800016b3  mov     [rbx+250h], bp
0x1800016ba  mov     [rbx+258h], rbp
0x1800016c1  mov     [rbx+618h], rbp
0x1800016c8  mov     [rbx+610h], ebp
0x1800016ce  cmp     [rbx+60Dh], bpl
0x1800016d5  jz      short loc_1800016FC
0x1800016d7  mov     edi, ebp
0x1800016d9  cmp     [rbx+600h], ebp
0x1800016df  ja      short loc_18000170B
0x1800016e1  mov     edi, ebp
0x1800016e3  mov     [rbx+600h], ebp
0x1800016e9  cmp     [rbx+604h], ebp
0x1800016ef  ja      loc_180001821
0x1800016f5  mov     [rbx+604h], rbp
0x1800016fc  xor     eax, eax
0x1800016fe  mov     rbx, [rsp+58h+arg_0]
0x180001703  add     rsp, 40h
0x180001707  pop     rdi
0x180001708  pop     rsi
0x180001709  pop     rbp
0x18000170a  retn
0x18000170b  lea     rcx, [rbx+5A0h]
0x180001712  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180001718  mov     ecx, edi
0x18000171a  xor     edx, edx; dwFlags
0x18000171c  mov     r8, [rax+rcx*8]; lpMem
0x180001720  mov     rcx, cs:?sm_hResponseBufferHeap@W3_RESPONSE@@0PEAXEA; hHeap
0x180001727  call    cs:__imp_HeapFree
0x18000172d  inc     edi
0x18000172f  cmp     edi, [rbx+600h]
0x180001735  jnb     short loc_1800016E1
0x180001737  jmp     short loc_18000170B
0x180001739  lea     rax, [rcx+8]
0x18000173d  neg     rcx
0x180001740  sbb     rcx, rcx
0x180001743  xor     edx, edx
0x180001745  and     rcx, rax
0x180001748  lea     r8d, [rdx+4]
0x18000174c  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x180001751  test    eax, eax
0x180001753  jz      loc_18000167D
0x180001759  mov     rax, [rbx+30h]
0x18000175d  mov     r9d, esi; unsigned int
0x180001760  mov     r8d, edi; unsigned int
0x180001763  lea     rdx, [rax+8]; struct _GUID *
0x180001767  neg     rax
0x18000176a  sbb     rcx, rcx
0x18000176d  and     rcx, rdx; struct IHttpTraceContext *
0x180001770  call    ?RaiseEvent@GENERAL_FLUSH_RESPONSE_END@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@KK@Z; IISGeneralEvents::GENERAL_FLUSH_RESPONSE_END::RaiseEvent(IHttpTraceContext *,_GUID const *,ulong,ulong)
0x180001775  jmp     loc_18000167D
0x18000177a  mov     rax, [rbx+30h]
0x18000177e  lea     rdx, [rsp+58h+arg_8]
0x180001783  mov     r9d, [rbx+614h]; unsigned int
0x18000178a  xor     r8d, r8d; int
0x18000178d  mov     [rsp+58h+arg_10], ebp
0x180001791  mov     rdi, [rax+188h]
0x180001798  movzx   eax, word ptr [rbx+610h]
0x18000179f  mov     [rbx+258h], rcx
0x1800017a6  mov     rcx, [rbx+620h]
0x1800017ad  mov     [rbx+250h], ax
0x1800017b4  mov     [rbx+618h], rbp
0x1800017bb  mov     [rbx+610h], ebp
0x1800017c1  mov     [rbx+614h], ebp
0x1800017c7  mov     [rbx+620h], rbp
0x1800017ce  mov     rax, [rdi+24D8h]
0x1800017d5  mov     [rbx+8], rax
0x1800017d9  lea     rax, [rsp+58h+arg_10]
0x1800017de  mov     [rsp+58h+var_28], rax; int *
0x1800017e3  mov     [rsp+58h+var_30], rdx; unsigned int *
0x1800017e8  lea     edx, [r8+1]; int
0x1800017ec  mov     [rsp+58h+var_38], rcx; struct _HTTP_LOG_DATA *
0x1800017f1  mov     rcx, rbx; this
0x1800017f4  mov     [rdi+24D8h], rbx
0x1800017fb  call    ?ResumeResponseTransfer@W3_RESPONSE@@AEAAJHHKPEAU_HTTP_LOG_DATA@@PEAKPEAH@Z; W3_RESPONSE::ResumeResponseTransfer(int,int,ulong,_HTTP_LOG_DATA *,ulong *,int *)
0x180001800  test    eax, eax
0x180001802  js      short loc_180001814
0x180001804  cmp     [rsp+58h+arg_10], ebp
0x180001808  jz      short loc_180001814
0x18000180a  mov     eax, 1
0x18000180f  jmp     loc_1800016FE
0x180001814  mov     rcx, rdi; this
0x180001817  call    ?PopAsyncSendContext@W3_MAIN_CONTEXT@@QEAAPEAVIISCORE_ASYNC_CONTEXT@@XZ; W3_MAIN_CONTEXT::PopAsyncSendContext(void)
0x18000181c  jmp     loc_180001691
0x180001821  lea     rcx, [rbx+5D0h]
0x180001828  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000182e  mov     ecx, edi
0x180001830  mov     rcx, [rax+rcx*8]; hObject
0x180001834  call    cs:__imp_CloseHandle
0x18000183a  inc     edi
0x18000183c  cmp     edi, [rbx+604h]
0x180001842  jb      short loc_180001821
0x180001844  jmp     loc_1800016F5
```
