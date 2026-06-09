# EtwpCopyLogfileInfo(_TRACELOG_CONTEXT *,_EVENT_TRACE_LOGFILEW *)

- ea: `0x18000485c`
- end: `0x1800049d6`
- name: `?EtwpCopyLogfileInfo@@YAKPEAU_TRACELOG_CONTEXT@@PEAU_EVENT_TRACE_LOGFILEW@@@Z`
- size: `378`
- prototype: `unsigned int __fastcall(struct _TRACELOG_CONTEXT *, struct _EVENT_TRACE_LOGFILEW *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007060`

## callees

- `0x18000202c`
- `0x18000485c`
- `0x180006180`

## pseudocode

```c
__int64 __fastcall EtwpCopyLogfileInfo(struct _TRACELOG_CONTEXT *a1, struct _EVENT_TRACE_LOGFILEW *a2)
{
  _QWORD *v2; // rbx
  __int64 v4; // rcx
  struct _EVENT_TRACE_LOGFILEW *v6; // r8
  _OWORD *v7; // rax
  __int128 v8; // xmm1
  __int64 v9; // rax
  unsigned __int64 v10; // rbp
  unsigned __int64 v11; // rax
  unsigned __int16 *v12; // rax
  unsigned int v13; // ebx
  __int64 v14; // r11
  LPWSTR LoggerName; // r8
  __int64 v16; // rcx
  unsigned int v17; // ebp
  unsigned __int64 v18; // rax
  unsigned __int16 *v19; // rax
  __int64 v20; // r11

  v2 = (_QWORD *)((char *)a1 + 80);
  v4 = 3;
  v6 = a2;
  v7 = v2;
  do
  {
    *v7 = *(_OWORD *)&v6->LogFileName;
    v7[1] = *(_OWORD *)&v6->CurrentTime;
    v7[2] = *(_OWORD *)&v6->CurrentEvent.Header.Size;
    v7[3] = *(_OWORD *)&v6->CurrentEvent.Header.TimeStamp.LowPart;
    v7[4] = *(union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *)((char *)&v6->CurrentEvent.Header.24 + 8);
    v7[5] = *(_OWORD *)&v6->CurrentEvent.InstanceId;
    v7[6] = *(_OWORD *)v6->CurrentEvent.ParentGuid.Data4;
    v8 = *(_OWORD *)&v6->CurrentEvent.MofLength;
    v6 = (struct _EVENT_TRACE_LOGFILEW *)((char *)v6 + 128);
    v7[7] = v8;
    v7 += 8;
    --v4;
  }
  while ( v4 );
  *v7 = *(_OWORD *)&v6->LogFileName;
  v7[1] = *(_OWORD *)&v6->CurrentTime;
  v7[2] = *(_OWORD *)&v6->CurrentEvent.Header.Size;
  v7[3] = *(_OWORD *)&v6->CurrentEvent.Header.TimeStamp.LowPart;
  if ( !*((_QWORD *)a1 + 63) )
    *((_QWORD *)a1 + 63) = EtwpDefaultEventCallback;
  *((_DWORD *)a1 + 8) = a2->LogfileHeader.ReservedFlags;
  *v2 = 0;
  *((_QWORD *)a1 + 11) = 0;
  if ( a2->LogFileName )
  {
    v9 = -1;
    do
      ++v9;
    while ( a2->LogFileName[v9] );
    v10 = (unsigned int)(v9 + 1);
    v11 = 2 * v10;
    if ( !is_mul_ok(v10, 2u) )
      v11 = -1;
    v12 = (unsigned __int16 *)operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v12 )
      return 14;
    StringCchCopyW(v12, v10, a2->LogFileName);
    *v2 = v14;
  }
  LoggerName = a2->LoggerName;
  v13 = 0;
  if ( !LoggerName )
    return v13;
  v16 = -1;
  do
    ++v16;
  while ( LoggerName[v16] );
  v17 = v16 + 1;
  v18 = 2LL * (unsigned int)(v16 + 1);
  if ( !is_mul_ok((unsigned int)(v16 + 1), 2u) )
    v18 = -1;
  v19 = (unsigned __int16 *)operator new[](v18, (const struct std::nothrow_t *)&std::nothrow);
  if ( v19 )
  {
    StringCchCopyW(v19, v17, a2->LoggerName);
    *((_QWORD *)a1 + 11) = v20;
    return v13;
  }
  return 14;
}

```

## disassembly

```asm
0x18000485c  push    rbx
0x18000485e  push    rbp
0x18000485f  push    rsi
0x180004860  push    rdi
0x180004861  push    r14
0x180004863  push    r15
0x180004865  sub     rsp, 28h
0x180004869  lea     rbx, [rcx+50h]
0x18000486d  mov     rdi, rcx
0x180004870  mov     ecx, 3
0x180004875  mov     rsi, rdx
0x180004878  mov     r8, rdx
0x18000487b  mov     rax, rbx
0x18000487e  lea     edx, [rcx+7Dh]
0x180004881  movups  xmm0, xmmword ptr [r8]
0x180004885  movups  xmmword ptr [rax], xmm0
0x180004888  movups  xmm1, xmmword ptr [r8+10h]
0x18000488d  movups  xmmword ptr [rax+10h], xmm1
0x180004891  movups  xmm0, xmmword ptr [r8+20h]
0x180004896  movups  xmmword ptr [rax+20h], xmm0
0x18000489a  movups  xmm1, xmmword ptr [r8+30h]
0x18000489f  movups  xmmword ptr [rax+30h], xmm1
0x1800048a3  movups  xmm0, xmmword ptr [r8+40h]
0x1800048a8  movups  xmmword ptr [rax+40h], xmm0
0x1800048ac  movups  xmm1, xmmword ptr [r8+50h]
0x1800048b1  movups  xmmword ptr [rax+50h], xmm1
0x1800048b5  movups  xmm0, xmmword ptr [r8+60h]
0x1800048ba  movups  xmmword ptr [rax+60h], xmm0
0x1800048be  movups  xmm1, xmmword ptr [r8+70h]
0x1800048c3  add     r8, rdx
0x1800048c6  movups  xmmword ptr [rax+70h], xmm1
0x1800048ca  add     rax, rdx
0x1800048cd  sub     rcx, 1
0x1800048d1  jnz     short loc_180004881
0x1800048d3  movups  xmm0, xmmword ptr [r8]
0x1800048d7  xor     r14d, r14d
0x1800048da  movups  xmmword ptr [rax], xmm0
0x1800048dd  movups  xmm1, xmmword ptr [r8+10h]
0x1800048e2  movups  xmmword ptr [rax+10h], xmm1
0x1800048e6  movups  xmm0, xmmword ptr [r8+20h]
0x1800048eb  movups  xmmword ptr [rax+20h], xmm0
0x1800048ef  movups  xmm1, xmmword ptr [r8+30h]
0x1800048f4  movups  xmmword ptr [rax+30h], xmm1
0x1800048f8  cmp     [rdi+1F8h], r14
0x1800048ff  jnz     short loc_18000490F
0x180004901  lea     rax, ?EtwpDefaultEventCallback@@YAXPEAU_EVENT_TRACE@@@Z; EtwpDefaultEventCallback(_EVENT_TRACE *)
0x180004908  mov     [rdi+1F8h], rax
0x18000490f  mov     eax, [rsi+188h]
0x180004915  or      r15, 0FFFFFFFFFFFFFFFFh
0x180004919  mov     [rdi+20h], eax
0x18000491c  mov     [rbx], r14
0x18000491f  mov     [rdi+58h], r14
0x180004923  mov     rcx, [rsi]
0x180004926  test    rcx, rcx
0x180004929  jz      short loc_180004976
0x18000492b  mov     rax, r15
0x18000492e  inc     rax
0x180004931  cmp     [rcx+rax*2], r14w
0x180004936  jnz     short loc_18000492E
0x180004938  lea     ebp, [rax+1]
0x18000493b  mov     eax, 2
0x180004940  mul     rbp
0x180004943  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000494a  cmovb   rax, r15
0x18000494e  mov     rcx, rax; unsigned __int64
0x180004951  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180004956  mov     r11, rax
0x180004959  test    rax, rax
0x18000495c  jnz     short loc_180004965
0x18000495e  mov     ebx, 0Eh
0x180004963  jmp     short loc_1800049C7
0x180004965  mov     r8, [rsi]; unsigned __int16 *
0x180004968  mov     rdx, rbp; unsigned __int64
0x18000496b  mov     rcx, r11; unsigned __int16 *
0x18000496e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004973  mov     [rbx], r11
0x180004976  mov     r8, [rsi+8]
0x18000497a  mov     ebx, r14d
0x18000497d  test    r8, r8
0x180004980  jz      short loc_1800049C7
0x180004982  mov     rcx, r15
0x180004985  inc     rcx
0x180004988  cmp     [r8+rcx*2], r14w
0x18000498d  jnz     short loc_180004985
0x18000498f  lea     ebp, [rcx+1]
0x180004992  mov     eax, 2
0x180004997  mul     rbp
0x18000499a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800049a1  cmovb   rax, r15
0x1800049a5  mov     rcx, rax; unsigned __int64
0x1800049a8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800049ad  mov     r11, rax
0x1800049b0  test    rax, rax
0x1800049b3  jz      short loc_18000495E
0x1800049b5  mov     r8, [rsi+8]; unsigned __int16 *
0x1800049b9  mov     edx, ebp; unsigned __int64
0x1800049bb  mov     rcx, rax; unsigned __int16 *
0x1800049be  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800049c3  mov     [rdi+58h], r11
0x1800049c7  mov     eax, ebx
0x1800049c9  add     rsp, 28h
0x1800049cd  pop     r15
0x1800049cf  pop     r14
0x1800049d1  pop     rdi
0x1800049d2  pop     rsi
0x1800049d3  pop     rbp
0x1800049d4  pop     rbx
0x1800049d5  retn
```
