# BackgroundCopyJobNotify::HandleJobCallbackThreadProc(void *)

- ea: `0x1800128a0`
- end: `0x1800128fb`
- name: `?HandleJobCallbackThreadProc@BackgroundCopyJobNotify@@CAKPEAX@Z`
- size: `91`
- prototype: `__int64 __fastcall(struct BackgroundCopyJobNotify::WorkerThreadParam *lpThreadParameter)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180012230`
- `0x18001240c`
- `0x1800128a0`
- `0x180012904`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800128e1`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x1800128e1`

## string_xrefs

- `0x1800128d8`: `BackgroundCopyJobNotify::HandleJobCallbackThreadProc`

## pseudocode

```c
__int64 __fastcall BackgroundCopyJobNotify::HandleJobCallbackThreadProc(
        struct BackgroundCopyJobNotify::WorkerThreadParam *lpThreadParameter)
{
  unsigned int v1; // ebx
  int v2; // eax
  int v3; // r8d
  struct BackgroundCopyJobNotify::WorkerThreadParam *v5; // [rsp+30h] [rbp+8h] BYREF

  v1 = 0;
  v5 = lpThreadParameter;
  if ( *(_DWORD *)lpThreadParameter )
  {
    if ( *(_DWORD *)lpThreadParameter == 1 )
    {
      v2 = BackgroundCopyJobNotify::HandleFileTransferred(lpThreadParameter);
      if ( v2 < 0 )
      {
        v3 = 172;
LABEL_7:
        v1 = ZTraceReportPropagationNoThis(v2, "BackgroundCopyJobNotify::HandleJobCallbackThreadProc", v3);
      }
    }
  }
  else
  {
    v2 = BackgroundCopyJobNotify::HandleJobError(lpThreadParameter);
    if ( v2 < 0 )
    {
      v3 = 167;
      goto LABEL_7;
    }
  }
  std::unique_ptr<BackgroundCopyJobNotify::WorkerThreadParam>::~unique_ptr<BackgroundCopyJobNotify::WorkerThreadParam>(&v5);
  return v1;
}

```

## disassembly

```asm
0x1800128a0  push    rbx
0x1800128a2  sub     rsp, 20h
0x1800128a6  xor     ebx, ebx
0x1800128a8  mov     [rsp+28h+arg_0], rcx
0x1800128ad  mov     edx, [rcx]
0x1800128af  test    edx, edx
0x1800128b1  jz      short loc_1800128C9
0x1800128b3  cmp     edx, 1
0x1800128b6  jnz     short loc_1800128E9
0x1800128b8  call    ?HandleFileTransferred@BackgroundCopyJobNotify@@CAJPEAUWorkerThreadParam@1@@Z; BackgroundCopyJobNotify::HandleFileTransferred(BackgroundCopyJobNotify::WorkerThreadParam *)
0x1800128bd  test    eax, eax
0x1800128bf  jns     short loc_1800128E9
0x1800128c1  mov     r8d, 0ACh
0x1800128c7  jmp     short loc_1800128D8
0x1800128c9  call    ?HandleJobError@BackgroundCopyJobNotify@@CAJPEAUWorkerThreadParam@1@@Z; BackgroundCopyJobNotify::HandleJobError(BackgroundCopyJobNotify::WorkerThreadParam *)
0x1800128ce  test    eax, eax
0x1800128d0  jns     short loc_1800128E9
0x1800128d2  mov     r8d, 0A7h
0x1800128d8  lea     rdx, aBackgroundcopy_4; "BackgroundCopyJobNotify::HandleJobCallb"...
0x1800128df  mov     ecx, eax
0x1800128e1  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x1800128e7  mov     ebx, eax
0x1800128e9  lea     rcx, [rsp+28h+arg_0]
0x1800128ee  call    ??1?$unique_ptr@UWorkerThreadParam@BackgroundCopyJobNotify@@U?$default_delete@UWorkerThreadParam@BackgroundCopyJobNotify@@@std@@@std@@QEAA@XZ; std::unique_ptr<BackgroundCopyJobNotify::WorkerThreadParam>::~unique_ptr<BackgroundCopyJobNotify::WorkerThreadParam>(void)
0x1800128f3  mov     eax, ebx
0x1800128f5  add     rsp, 20h
0x1800128f9  pop     rbx
0x1800128fa  retn
```
