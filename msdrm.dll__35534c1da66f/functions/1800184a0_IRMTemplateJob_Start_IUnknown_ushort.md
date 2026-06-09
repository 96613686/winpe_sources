# IRMTemplateJob::Start(IUnknown *,ushort *)

- ea: `0x1800184a0`
- end: `0x180018641`
- name: `?Start@IRMTemplateJob@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `417`
- prototype: `__int64 __fastcall(IRMTemplateJob *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001244`
- `0x180001284`
- `0x1800184a0`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180018531`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180018531`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018542`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800185af`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800185af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018573`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018573`
- `ATL!__imp_AtlComPtrAssign` at `0x180018520`
- `ATL!__imp_AtlComPtrAssign` at `0x180018520`

## pseudocode

```c
__int64 __fastcall IRMTemplateJob::Start(IRMTemplateJob *this, struct IUnknown *a2, unsigned __int16 *a3)
{
  __int64 v5; // rcx
  signed int v6; // ebx
  _QWORD *v7; // rax
  _QWORD *v8; // rdi
  void *v9; // rcx
  DWORD v10; // eax
  signed int LastError; // eax
  void *v12; // rcx
  HANDLE Thread; // rax
  __int64 v15; // [rsp+58h] [rbp+10h] BYREF

  v5 = 0;
  v15 = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    goto LABEL_26;
  }
  v7 = operator new(0x10u);
  v8 = v7;
  if ( !v7 )
  {
    v6 = -2147024882;
    v8 = 0;
    goto LABEL_19;
  }
  *v7 = 0;
  v7[1] = this;
  v6 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_ITaskHandlerStatus,
         &v15);
  if ( v6 < 0 )
    goto LABEL_19;
  AtlComPtrAssign(v8, v15);
  v9 = (void *)*((_QWORD *)this + 3);
  if ( v9 )
  {
    v10 = WaitForSingleObject(v9, 0);
    if ( v10 )
    {
      if ( v10 == 258 )
      {
        v6 = -2147168456;
        goto LABEL_19;
      }
      goto LABEL_8;
    }
    v12 = (void *)*((_QWORD *)this + 3);
    if ( v12 )
    {
      CloseHandle(v12);
      *((_QWORD *)this + 3) = 0;
    }
  }
  (*(void (__fastcall **)(IRMTemplateJob *))(*(_QWORD *)this + 8LL))(this);
  Thread = CreateThread(0, 0, IRMTemplateJob::TemplateJobStartProc, v8, 0, 0);
  *((_QWORD *)this + 3) = Thread;
  if ( Thread )
  {
LABEL_25:
    v5 = v15;
    goto LABEL_26;
  }
  (*(void (__fastcall **)(IRMTemplateJob *))(*(_QWORD *)this + 16LL))(this);
LABEL_8:
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 >= 0 )
    v6 = -2147467259;
LABEL_19:
  v5 = v15;
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v15 + 32LL))(v15, (unsigned int)v6);
    v5 = v15;
  }
  if ( v8 )
  {
    if ( *v8 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 16LL))(*v8);
    operator delete(v8);
    goto LABEL_25;
  }
LABEL_26:
  if ( v5 )
    (*(void (__fastcall **)(__int64, struct IUnknown *, unsigned __int16 *))(*(_QWORD *)v5 + 16LL))(v5, a2, a3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800184a0  mov     rax, rsp
0x1800184a3  push    rdi
0x1800184a4  sub     rsp, 40h
0x1800184a8  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x1800184b0  mov     [rax+8], rbx
0x1800184b4  mov     [rax+18h], rsi
0x1800184b8  mov     rbx, rdx
0x1800184bb  mov     rsi, rcx
0x1800184be  xor     ecx, ecx
0x1800184c0  mov     [rax+10h], rcx
0x1800184c4  test    rdx, rdx
0x1800184c7  jnz     short loc_1800184D3
0x1800184c9  mov     ebx, 80070057h
0x1800184ce  jmp     loc_18001861D
0x1800184d3  mov     ecx, 10h; Size
0x1800184d8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800184dd  mov     rdi, rax
0x1800184e0  test    rax, rax
0x1800184e3  jz      loc_1800185D2
0x1800184e9  mov     qword ptr [rax], 0
0x1800184f0  mov     [rax+8], rsi
0x1800184f4  mov     rax, [rbx]
0x1800184f7  lea     r8, [rsp+48h+arg_8]
0x1800184fc  lea     rdx, IID_ITaskHandlerStatus
0x180018503  mov     rcx, rbx
0x180018506  mov     rax, [rax]
0x180018509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001850e  mov     ebx, eax
0x180018510  test    eax, eax
0x180018512  js      loc_1800185D9
0x180018518  mov     rdx, [rsp+48h+arg_8]
0x18001851d  mov     rcx, rdi
0x180018520  call    cs:__imp_AtlComPtrAssign
0x180018526  mov     rcx, [rsi+18h]; hHandle
0x18001852a  test    rcx, rcx
0x18001852d  jz      short loc_180018581
0x18001852f  xor     edx, edx; dwMilliseconds
0x180018531  call    cs:__imp_WaitForSingleObject
0x180018537  test    eax, eax
0x180018539  jz      short loc_18001856A
0x18001853b  cmp     eax, 102h
0x180018540  jz      short loc_180018563
0x180018542  call    cs:__imp_GetLastError
0x180018548  mov     ebx, eax
0x18001854a  test    eax, eax
0x18001854c  jle     short loc_180018557
0x18001854e  movzx   ebx, ax
0x180018551  or      ebx, 80070000h
0x180018557  mov     eax, 80004005h
0x18001855c  test    ebx, ebx
0x18001855e  cmovns  ebx, eax
0x180018561  jmp     short loc_1800185D9
0x180018563  mov     ebx, 8004CF38h
0x180018568  jmp     short loc_1800185D9
0x18001856a  mov     rcx, [rsi+18h]; hObject
0x18001856e  test    rcx, rcx
0x180018571  jz      short loc_180018581
0x180018573  call    cs:__imp_CloseHandle
0x180018579  mov     qword ptr [rsi+18h], 0
0x180018581  mov     rax, [rsi]
0x180018584  mov     rcx, rsi
0x180018587  mov     rax, [rax+8]
0x18001858b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018590  mov     [rsp+48h+lpThreadId], 0; lpThreadId
0x180018599  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x1800185a1  mov     r9, rdi; lpParameter
0x1800185a4  lea     r8, ?TemplateJobStartProc@IRMTemplateJob@@CAKPEAX@Z; lpStartAddress
0x1800185ab  xor     edx, edx; dwStackSize
0x1800185ad  xor     ecx, ecx; lpThreadAttributes
0x1800185af  call    cs:__imp_CreateThread
0x1800185b5  mov     [rsi+18h], rax
0x1800185b9  test    rax, rax
0x1800185bc  jnz     short loc_180018618
0x1800185be  mov     rax, [rsi]
0x1800185c1  mov     rcx, rsi
0x1800185c4  mov     rax, [rax+10h]
0x1800185c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185cd  jmp     loc_180018542
0x1800185d2  mov     ebx, 8007000Eh
0x1800185d7  xor     edi, edi
0x1800185d9  mov     rcx, [rsp+48h+arg_8]
0x1800185de  test    rcx, rcx
0x1800185e1  jz      short loc_1800185F6
0x1800185e3  mov     rax, [rcx]
0x1800185e6  mov     edx, ebx
0x1800185e8  mov     rax, [rax+20h]
0x1800185ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185f1  mov     rcx, [rsp+48h+arg_8]
0x1800185f6  test    rdi, rdi
0x1800185f9  jz      short loc_18001861D
0x1800185fb  mov     rcx, [rdi]
0x1800185fe  test    rcx, rcx
0x180018601  jz      short loc_180018610
0x180018603  mov     rax, [rcx]
0x180018606  mov     rax, [rax+10h]
0x18001860a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001860f  nop
0x180018610  mov     rcx, rdi; Block
0x180018613  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018618  mov     rcx, [rsp+48h+arg_8]
0x18001861d  test    rcx, rcx
0x180018620  jz      short loc_18001862F
0x180018622  mov     rax, [rcx]
0x180018625  mov     rax, [rax+10h]
0x180018629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001862e  nop
0x18001862f  mov     eax, ebx
0x180018631  mov     rbx, [rsp+48h+arg_0]
0x180018636  mov     rsi, [rsp+48h+arg_10]
0x18001863b  add     rsp, 40h
0x18001863f  pop     rdi
0x180018640  retn
```
