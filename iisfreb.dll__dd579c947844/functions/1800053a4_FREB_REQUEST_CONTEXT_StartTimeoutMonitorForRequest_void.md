# FREB_REQUEST_CONTEXT::StartTimeoutMonitorForRequest(void)

- ea: `0x1800053a4`
- end: `0x1800054df`
- name: `?StartTimeoutMonitorForRequest@FREB_REQUEST_CONTEXT@@QEAAXXZ`
- size: `315`
- prototype: `void __fastcall(FREB_REQUEST_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800023cc`

## callees

- `0x1800053a4`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800053cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800053cb`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800054d0`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800054d0`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180005486`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180005486`

## pseudocode

```c
void __fastcall FREB_REQUEST_CONTEXT::StartTimeoutMonitorForRequest(FREB_REQUEST_CONTEXT *this)
{
  __int64 v1; // rdi
  int v3; // edi
  DWORD TickCount; // r8d
  _DWORD *v5; // rax
  DWORD v6; // eax
  unsigned int v7; // r8d
  FREB_TIMEOUT_MONITOR_LIST *v8; // rbp
  __int64 v9; // rsi
  unsigned int v10; // edi
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  char *v15; // rdx
  __int64 *v16; // rax

  v1 = *((_QWORD *)this + 10);
  if ( v1 )
  {
    v3 = *(_DWORD *)(v1 + 176);
    if ( v3 )
    {
      TickCount = GetTickCount();
      v5 = (_DWORD *)*((_QWORD *)this + 12);
      if ( v5 == (_DWORD *)((char *)this + 96) )
        v6 = TickCount;
      else
        v6 = v5[26];
      v7 = TickCount - v6;
      if ( v7 < 1000 * v3 )
      {
        v8 = FREB_REQUEST_CONTEXT::sm_pTimeoutMonitor;
        v9 = (__int64)this + 36;
        v10 = v3 - v7 / 0x3E8;
        if ( !v10 )
          v10 = 1;
        v11 = (v10 + *((_DWORD *)FREB_REQUEST_CONTEXT::sm_pTimeoutMonitor + 1800) + 1) % 0x12C;
        if ( !this )
          v9 = 28;
        *(_DWORD *)v9 = v11;
        v12 = (__int64)this + 32;
        v13 = 8 * v11 + 4800;
        if ( !this )
          v12 = 24;
        *(_DWORD *)v12 = v10 / 0x12C;
        CReaderWriterLock3::WriteLock((FREB_TIMEOUT_MONITOR_LIST *)((char *)v8 + v13));
        v14 = (__int64)this + 16;
        if ( !this )
          v14 = 8;
        v15 = (char *)v8 + 16 * *(unsigned int *)v9;
        v16 = (__int64 *)*((_QWORD *)v15 + 1);
        if ( (char *)*v16 != v15 )
          __fastfail(3u);
        *(_QWORD *)v14 = v15;
        *(_QWORD *)(v14 + 8) = v16;
        *v16 = v14;
        *((_QWORD *)v15 + 1) = v14;
        CReaderWriterLock3::WriteUnlock((FREB_TIMEOUT_MONITOR_LIST *)((char *)v8 + 8 * *(unsigned int *)v9 + 4800));
      }
      else
      {
        (**((void (__fastcall ***)(char *))this + 1))((char *)this + 8);
      }
    }
  }
}

```

## disassembly

```asm
0x1800053a4  push    rbx
0x1800053a6  push    rbp
0x1800053a7  push    rsi
0x1800053a8  push    rdi
0x1800053a9  sub     rsp, 28h
0x1800053ad  mov     rdi, [rcx+50h]
0x1800053b1  mov     rbx, rcx
0x1800053b4  test    rdi, rdi
0x1800053b7  jz      loc_1800054D6
0x1800053bd  mov     edi, [rdi+0B0h]
0x1800053c3  test    edi, edi
0x1800053c5  jz      loc_1800054D6
0x1800053cb  call    cs:__imp_GetTickCount
0x1800053d1  lea     rdx, [rbx+60h]
0x1800053d5  mov     r8d, eax
0x1800053d8  mov     rax, [rdx]
0x1800053db  cmp     rax, rdx
0x1800053de  jz      short loc_1800053E5
0x1800053e0  mov     eax, [rax+68h]
0x1800053e3  jmp     short loc_1800053E8
0x1800053e5  mov     eax, r8d
0x1800053e8  sub     r8d, eax
0x1800053eb  imul    eax, edi, 3E8h
0x1800053f1  cmp     r8d, eax
0x1800053f4  jb      short loc_18000540A
0x1800053f6  lea     rcx, [rbx+8]
0x1800053fa  mov     rax, [rcx]
0x1800053fd  mov     rax, [rax]
0x180005400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005405  jmp     loc_1800054D6
0x18000540a  mov     rbp, cs:?sm_pTimeoutMonitor@FREB_REQUEST_CONTEXT@@0PEAVFREB_TIMEOUT_MONITOR_LIST@@EA; FREB_TIMEOUT_MONITOR_LIST * FREB_REQUEST_CONTEXT::sm_pTimeoutMonitor
0x180005411  lea     rsi, [rbx+24h]
0x180005415  mov     r9d, 1B4E81B5h
0x18000541b  mov     eax, 10624DD3h
0x180005420  mul     r8d
0x180005423  mov     r8d, [rbp+1C20h]
0x18000542a  mov     eax, 1
0x18000542f  shr     edx, 6
0x180005432  sub     edi, edx
0x180005434  cmovz   edi, eax
0x180005437  inc     r8d
0x18000543a  add     r8d, edi
0x18000543d  mov     eax, r9d
0x180005440  mul     r8d
0x180005443  mov     eax, r9d
0x180005446  shr     edx, 5
0x180005449  imul    ecx, edx, 12Ch
0x18000544f  mov     edx, 1Ch
0x180005454  sub     r8d, ecx
0x180005457  mov     ecx, r8d
0x18000545a  test    rbx, rbx
0x18000545d  mov     r8d, 18h
0x180005463  cmovz   rsi, rdx
0x180005467  mul     edi
0x180005469  mov     [rsi], ecx
0x18000546b  lea     rax, [rbx+20h]
0x18000546f  shr     edx, 5
0x180005472  lea     rcx, ds:12C0h[rcx*8]
0x18000547a  test    rbx, rbx
0x18000547d  cmovz   rax, r8
0x180005481  add     rcx, rbp
0x180005484  mov     [rax], edx
0x180005486  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000548c  mov     edx, [rsi]
0x18000548e  lea     rcx, [rbx+10h]
0x180005492  test    rbx, rbx
0x180005495  mov     eax, 8
0x18000549a  cmovz   rcx, rax
0x18000549e  shl     rdx, 4
0x1800054a2  add     rdx, rbp
0x1800054a5  mov     rax, [rdx+8]
0x1800054a9  cmp     [rax], rdx
0x1800054ac  jz      short loc_1800054B5
0x1800054ae  mov     ecx, 3
0x1800054b3  int     29h; Win8: RtlFailFast(ecx)
0x1800054b5  mov     [rcx], rdx
0x1800054b8  mov     [rcx+8], rax
0x1800054bc  mov     [rax], rcx
0x1800054bf  mov     [rdx+8], rcx
0x1800054c3  lea     rcx, [rbp+12C0h]
0x1800054ca  mov     eax, [rsi]
0x1800054cc  lea     rcx, [rcx+rax*8]
0x1800054d0  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800054d6  add     rsp, 28h
0x1800054da  pop     rdi
0x1800054db  pop     rsi
0x1800054dc  pop     rbp
0x1800054dd  pop     rbx
0x1800054de  retn
```
