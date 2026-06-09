# ProvisioningTask::StartDownloadThread(IStream *)

- ea: `0x18003771c`
- end: `0x18003778f`
- name: `?StartDownloadThread@ProvisioningTask@@AEAAJPEAUIStream@@@Z`
- size: `115`
- prototype: `HRESULT __fastcall(ProvisioningTask *this, IStream *pStream)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180037540`

## callees

- `0x18003771c`
- `0x18006f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180037778`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180037778`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18003775a`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18003775a`

## pseudocode

```c
__int64 __fastcall ProvisioningTask::StartDownloadThread(ProvisioningTask *this, IStream *pStream)
{
  void *v4; // rax

  pStream->AddRef(pStream);
  v4 = (void *)_o__beginthreadex(0, 0, RefreshTaskThreadThunk, pStream, 0, 0);
  this->m_taskThread = v4;
  if ( v4 )
    return 0;
  pStream->Release(pStream);
  return *(unsigned int *)_o__errno();
}

```

## disassembly

```asm
0x18003771c  mov     [rsp+arg_0], rbx
0x180037721  push    rdi
0x180037722  sub     rsp, 30h
0x180037726  mov     rax, [pStream]
0x180037729  mov     rbx, this
0x18003772c  mov     this, pStream
0x18003772f  mov     rdi, pStream
0x180037732  mov     rax, [rax+8]
0x180037736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003773b  mov     r9, rdi
0x18003773e  mov     [rsp+38h+var_10], 0
0x180037747  lea     r8, ?RefreshTaskThreadThunk@@YAIPEAX@Z; RefreshTaskThreadThunk(void *)
0x18003774e  mov     [rsp+38h+var_18], 0
0x180037756  xor     edx, edx
0x180037758  xor     ecx, ecx
0x18003775a  call    cs:__imp__o__beginthreadex
0x180037760  mov     [rbx+40h], rax
0x180037764  test    rax, rax
0x180037767  jnz     short loc_180037782
0x180037769  mov     rax, [rdi]
0x18003776c  mov     this, rdi
0x18003776f  mov     rax, [rax+10h]
0x180037773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037778  call    cs:__imp__o__errno
0x18003777e  mov     eax, [rax]
0x180037780  jmp     short loc_180037784
0x180037782  xor     eax, eax
0x180037784  mov     rbx, [rsp+38h+arg_0]
0x180037789  add     rsp, 30h
0x18003778d  pop     rdi
0x18003778e  retn
```
