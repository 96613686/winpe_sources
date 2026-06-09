# COConnectionPoint::Terminate(int)

- ea: `0x18000d6a4`
- end: `0x18000d883`
- name: `?Terminate@COConnectionPoint@@QEAAJH@Z`
- size: `479`
- prototype: `__int64 __fastcall(COConnectionPoint *__hidden this, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180001bd4`
- `0x1800068d4`
- `0x180009920`

## callees

- `0x1800010b0`
- `0x18000d6a4`
- `0x180010010`

## import_xrefs

- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d862`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d862`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d6cc`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d6cc`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18000d76d`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18000d7e5`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18000d76d`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ` at `0x18000d7e5`

## pseudocode

```c
__int64 __fastcall COConnectionPoint::Terminate(COConnectionPoint *this, int a2)
{
  _QWORD *v4; // rdi
  unsigned int v5; // esi
  struct CEtwTracer *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rax
  int v10; // eax
  int v12; // [rsp+70h] [rbp+8h] BYREF

  v12 = 0;
  CReaderWriterLock3::WriteLock((COConnectionPoint *)((char *)this + 8));
  if ( !*((_DWORD *)this + 10) )
  {
    v4 = (_QWORD *)((char *)this + 48);
    if ( *((_QWORD *)this + 4) )
    {
      if ( *v4 )
      {
        v5 = 0;
        if ( *((_DWORD *)this + 7) )
        {
          v6 = g_pEtwCoAdminTracer;
          do
          {
            if ( *(_DWORD *)(*((_QWORD *)this + 4) + 8LL * v5 + 4) )
            {
              if ( a2 && *((_DWORD *)v6 + 2) && (*((_BYTE *)v6 + 40) & 2) != 0 && *((_DWORD *)v6 + 11) >= 4u )
              {
                v7 = *((_QWORD *)this + 2);
                if ( v7 )
                  v8 = *(_DWORD *)(v7 + 168);
                else
                  v8 = 0;
                v12 = v8;
                CEtwTracer::EtwTraceEvent(v6, (const struct _GUID *)IISAdminShutdownGuid, 0xCu, &v12, 4, 0, 0);
              }
              (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v4 + 32LL))(
                *v4,
                *(unsigned int *)(*((_QWORD *)this + 4) + 8LL * v5 + 4));
              v6 = g_pEtwCoAdminTracer;
              if ( a2
                && *((_DWORD *)g_pEtwCoAdminTracer + 2)
                && (*((_BYTE *)g_pEtwCoAdminTracer + 40) & 2) != 0
                && *((_DWORD *)g_pEtwCoAdminTracer + 11) >= 4u )
              {
                v9 = *((_QWORD *)this + 2);
                if ( v9 )
                  v10 = *(_DWORD *)(v9 + 168);
                else
                  v10 = 0;
                v12 = v10;
                CEtwTracer::EtwTraceEvent(
                  g_pEtwCoAdminTracer,
                  (const struct _GUID *)IISAdminShutdownGuid,
                  0xDu,
                  &v12,
                  4,
                  0,
                  0);
                v6 = g_pEtwCoAdminTracer;
              }
              *(_DWORD *)(*((_QWORD *)this + 4) + 8LL * v5 + 4) = 0;
            }
            if ( *(_DWORD *)(*((_QWORD *)this + 4) + 8LL * v5) )
            {
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 32LL))(*v4);
              v6 = g_pEtwCoAdminTracer;
              *(_DWORD *)(*((_QWORD *)this + 4) + 8LL * v5) = 0;
            }
            ++v5;
          }
          while ( v5 < *((_DWORD *)this + 7) );
        }
      }
      operator delete[](*((void **)this + 4));
      *((_QWORD *)this + 4) = 0;
    }
    if ( *v4 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 16LL))(*v4);
      *v4 = 0;
    }
    *((_QWORD *)this + 3) = 0;
    *((_DWORD *)this + 10) = 1;
  }
  CReaderWriterLock3::WriteUnlock((COConnectionPoint *)((char *)this + 8));
  return 0;
}

```

## disassembly

```asm
0x18000d6a4  mov     [rsp+arg_8], rbx
0x18000d6a9  mov     [rsp+arg_10], rbp
0x18000d6ae  push    rsi
0x18000d6af  push    rdi
0x18000d6b0  push    r12
0x18000d6b2  push    r14
0x18000d6b4  push    r15
0x18000d6b6  sub     rsp, 40h
0x18000d6ba  mov     rbx, rcx
0x18000d6bd  xor     r12d, r12d
0x18000d6c0  add     rcx, 8
0x18000d6c4  mov     [rsp+68h+arg_0], r12d
0x18000d6c9  mov     r15d, edx
0x18000d6cc  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000d6d2  mov     eax, [rbx+28h]
0x18000d6d5  test    eax, eax
0x18000d6d7  jnz     loc_18000D85E
0x18000d6dd  lea     rdi, [rbx+30h]
0x18000d6e1  cmp     [rbx+20h], r12
0x18000d6e5  jz      loc_18000D83C
0x18000d6eb  cmp     [rdi], r12
0x18000d6ee  jz      loc_18000D82F
0x18000d6f4  mov     esi, r12d
0x18000d6f7  cmp     [rbx+1Ch], r12d
0x18000d6fb  jbe     loc_18000D82F
0x18000d701  mov     rcx, cs:?g_pEtwCoAdminTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwCoAdminTracer
0x18000d708  mov     rax, [rbx+20h]
0x18000d70c  mov     ebp, esi
0x18000d70e  cmp     [rax+rbp*8+4], r12d
0x18000d713  jz      loc_18000D7FB
0x18000d719  test    r15d, r15d
0x18000d71c  jz      short loc_18000D773
0x18000d71e  cmp     [rcx+8], r12d
0x18000d722  jz      short loc_18000D773
0x18000d724  test    byte ptr [rcx+28h], 2
0x18000d728  jz      short loc_18000D773
0x18000d72a  cmp     dword ptr [rcx+2Ch], 4
0x18000d72e  jb      short loc_18000D773
0x18000d730  mov     rax, [rbx+10h]
0x18000d734  test    rax, rax
0x18000d737  jnz     short loc_18000D73E
0x18000d739  mov     eax, r12d
0x18000d73c  jmp     short loc_18000D744
0x18000d73e  mov     eax, [rax+0A8h]
0x18000d744  mov     [rsp+68h+var_38], r12
0x18000d749  lea     r9, [rsp+68h+arg_0]
0x18000d74e  mov     [rsp+68h+var_40], r12
0x18000d753  lea     rdx, IISAdminShutdownGuid
0x18000d75a  mov     r8d, 0Ch
0x18000d760  mov     [rsp+68h+var_48], 4
0x18000d769  mov     [rsp+68h+arg_0], eax
0x18000d76d  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x18000d773  mov     rcx, [rdi]
0x18000d776  mov     rdx, [rbx+20h]
0x18000d77a  mov     rax, [rcx]
0x18000d77d  mov     edx, [rdx+rbp*8+4]
0x18000d781  mov     rax, [rax+20h]
0x18000d785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d78a  mov     rcx, cs:?g_pEtwCoAdminTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwCoAdminTracer
0x18000d791  test    r15d, r15d
0x18000d794  jz      short loc_18000D7F2
0x18000d796  cmp     [rcx+8], r12d
0x18000d79a  jz      short loc_18000D7F2
0x18000d79c  test    byte ptr [rcx+28h], 2
0x18000d7a0  jz      short loc_18000D7F2
0x18000d7a2  cmp     dword ptr [rcx+2Ch], 4
0x18000d7a6  jb      short loc_18000D7F2
0x18000d7a8  mov     rax, [rbx+10h]
0x18000d7ac  test    rax, rax
0x18000d7af  jnz     short loc_18000D7B6
0x18000d7b1  mov     eax, r12d
0x18000d7b4  jmp     short loc_18000D7BC
0x18000d7b6  mov     eax, [rax+0A8h]
0x18000d7bc  mov     [rsp+68h+var_38], r12
0x18000d7c1  lea     r9, [rsp+68h+arg_0]
0x18000d7c6  mov     [rsp+68h+var_40], r12
0x18000d7cb  lea     rdx, IISAdminShutdownGuid
0x18000d7d2  mov     r8d, 0Dh
0x18000d7d8  mov     [rsp+68h+var_48], 4
0x18000d7e1  mov     [rsp+68h+arg_0], eax
0x18000d7e5  call    cs:__imp_?EtwTraceEvent@CEtwTracer@@QEAAKPEBU_GUID@@KZZ; CEtwTracer::EtwTraceEvent(_GUID const *,ulong,...)
0x18000d7eb  mov     rcx, cs:?g_pEtwCoAdminTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwCoAdminTracer
0x18000d7f2  mov     rax, [rbx+20h]
0x18000d7f6  mov     [rax+rbp*8+4], r12d
0x18000d7fb  mov     rax, [rbx+20h]
0x18000d7ff  mov     edx, [rax+rbp*8]
0x18000d802  test    edx, edx
0x18000d804  jz      short loc_18000D824
0x18000d806  mov     rcx, [rdi]
0x18000d809  mov     rax, [rcx]
0x18000d80c  mov     rax, [rax+20h]
0x18000d810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d815  mov     rax, [rbx+20h]
0x18000d819  mov     rcx, cs:?g_pEtwCoAdminTracer@@3PEAVCEtwTracer@@EA; CEtwTracer * g_pEtwCoAdminTracer
0x18000d820  mov     [rax+rbp*8], r12d
0x18000d824  inc     esi
0x18000d826  cmp     esi, [rbx+1Ch]
0x18000d829  jb      loc_18000D708
0x18000d82f  mov     rcx, [rbx+20h]; Block
0x18000d833  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000d838  mov     [rbx+20h], r12
0x18000d83c  mov     rcx, [rdi]
0x18000d83f  test    rcx, rcx
0x18000d842  jz      short loc_18000D853
0x18000d844  mov     rax, [rcx]
0x18000d847  mov     rax, [rax+10h]
0x18000d84b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d850  mov     [rdi], r12
0x18000d853  mov     [rbx+18h], r12
0x18000d857  mov     dword ptr [rbx+28h], 1
0x18000d85e  lea     rcx, [rbx+8]
0x18000d862  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000d868  lea     r11, [rsp+68h+var_28]
0x18000d86d  xor     eax, eax
0x18000d86f  mov     rbx, [r11+38h]
0x18000d873  mov     rbp, [r11+40h]
0x18000d877  mov     rsp, r11
0x18000d87a  pop     r15
0x18000d87c  pop     r14
0x18000d87e  pop     r12
0x18000d880  pop     rdi
0x18000d881  pop     rsi
0x18000d882  retn
```
