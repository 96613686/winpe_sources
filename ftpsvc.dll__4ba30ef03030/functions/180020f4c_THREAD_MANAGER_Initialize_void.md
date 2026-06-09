# THREAD_MANAGER::Initialize(void)

- ea: `0x180020f4c`
- end: `0x180021184`
- name: `?Initialize@THREAD_MANAGER@@AEAAJXZ`
- size: `568`
- prototype: `__int64 __fastcall(THREAD_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800205f8`

## callees

- `0x180001210`
- `0x180020c84`
- `0x180020f4c`
- `0x180049010`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x180020f73`
- `KERNEL32!GetModuleFileNameW` at `0x180020f73`
- `KERNEL32!CreateEventW` at `0x180020f91`
- `KERNEL32!CreateEventW` at `0x180020fae`
- `KERNEL32!CreateEventW` at `0x180020f91`
- `KERNEL32!CreateEventW` at `0x180020fae`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18002107a`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18002107a`
- `KERNEL32!GetLastError` at `0x180021156`
- `KERNEL32!GetLastError` at `0x180021156`
- `KERNEL32!HeapFree` at `0x1800210f8`
- `KERNEL32!HeapFree` at `0x180021143`
- `KERNEL32!HeapFree` at `0x1800210f8`
- `KERNEL32!HeapFree` at `0x180021143`
- `KERNEL32!CloseHandle` at `0x180021095`
- `KERNEL32!CloseHandle` at `0x1800210ab`
- `KERNEL32!CloseHandle` at `0x180021095`
- `KERNEL32!CloseHandle` at `0x1800210ab`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x18002111e`
- `KERNEL32!DeleteProcThreadAttributeList` at `0x18002111e`
- `KERNEL32!GetProcessHeap` at `0x1800210ea`
- `KERNEL32!GetProcessHeap` at `0x180021135`
- `KERNEL32!GetProcessHeap` at `0x1800210ea`
- `KERNEL32!GetProcessHeap` at `0x180021135`
- `KERNEL32!GetNumaNodeProcessorMaskEx` at `0x18002103b`
- `KERNEL32!GetNumaNodeProcessorMaskEx` at `0x18002103b`

## pseudocode

```c
__int64 __fastcall THREAD_MANAGER::Initialize(THREAD_MANAGER *this)
{
  HANDLE *v2; // rbx
  HANDLE EventW; // rax
  HANDLE v4; // rax
  AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP *v5; // rax
  AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP *v6; // rcx
  signed int v7; // edi
  USHORT v8; // di
  __int64 v9; // r14
  __int64 v10; // rdx
  unsigned int i; // ecx
  void *v12; // rcx
  void (__fastcall ***v13)(_QWORD, __int64); // rcx
  void *v14; // rbx
  HANDLE ProcessHeap; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v16; // rcx
  void *v17; // rbx
  HANDLE v18; // rax
  signed int LastError; // eax

  v2 = (HANDLE *)((char *)this + 88);
  if ( !GetModuleFileNameW(g_hModuleW3TP, &g_szModuleName, 0x104u)
    || (EventW = CreateEventW(0, 0, 0, 0), (*v2 = EventW) == 0)
    || (v4 = CreateEventW(0, 1, 0, 0), (*((_QWORD *)this + 12) = v4) == 0) )
  {
LABEL_20:
    v7 = -2147467259;
    goto LABEL_21;
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 14) + 88LL) == 1 )
  {
    v5 = (AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP *)operator new(0x18u);
    v6 = v5;
    if ( v5 )
    {
      *(_QWORD *)v5 = &AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::`vftable';
      *((_WORD *)v5 + 4) = 0;
      *((_DWORD *)v5 + 3) = 0;
      *((_QWORD *)v5 + 2) = 0;
    }
    else
    {
      v6 = 0;
    }
    *((_QWORD *)this + 17) = v6;
    if ( !v6 )
    {
      v7 = -2147024888;
LABEL_21:
      if ( *v2 )
      {
        CloseHandle(*v2);
        *v2 = 0;
      }
      v12 = (void *)*((_QWORD *)this + 12);
      if ( v12 )
      {
        CloseHandle(v12);
        *((_QWORD *)this + 12) = 0;
      }
      v13 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 17);
      if ( v13 )
      {
        (**v13)(v13, 1);
        *((_QWORD *)this + 17) = 0;
      }
      v14 = (void *)*((_QWORD *)this + 19);
      if ( v14 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v14);
        *((_QWORD *)this + 19) = 0;
      }
      v16 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)*((_QWORD *)this + 21);
      if ( v16 )
      {
        if ( *((_DWORD *)this + 46) )
        {
          DeleteProcThreadAttributeList(v16);
          *((_DWORD *)this + 46) = 0;
        }
        v17 = (void *)*((_QWORD *)this + 21);
        v18 = GetProcessHeap();
        HeapFree(v18, 0, v17);
        *((_QWORD *)this + 21) = 0;
      }
      return (unsigned int)v7;
    }
    v7 = AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::Initialize(v6);
    if ( v7 < 0 )
      goto LABEL_21;
  }
  if ( !*((_DWORD *)this + 36) )
  {
LABEL_19:
    if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 8), 0x80000000) )
      return 0;
    goto LABEL_20;
  }
  v8 = 0;
  while ( 1 )
  {
    v9 = *((_QWORD *)this + 19) + 24LL * v8;
    if ( !GetNumaNodeProcessorMaskEx(v8, (PGROUP_AFFINITY)v9) )
      break;
    v10 = *(_QWORD *)v9;
    for ( i = 0; i < 0x40; ++i )
    {
      if ( _bittest64(&v10, i) )
        ++*(_BYTE *)(v9 + 16);
    }
    if ( (unsigned int)++v8 > *((_DWORD *)this + 40) )
      goto LABEL_19;
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 < 0 )
    goto LABEL_21;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180020f4c  push    rbx
0x180020f4e  push    rsi
0x180020f4f  push    rdi
0x180020f50  push    r14
0x180020f52  push    r15
0x180020f54  sub     rsp, 20h
0x180020f58  mov     rsi, rcx
0x180020f5b  lea     rbx, [rcx+58h]
0x180020f5f  mov     rcx, cs:?g_hModuleW3TP@@3PEAUHINSTANCE__@@EA; hModule
0x180020f66  lea     rdx, ?g_szModuleName@@3PAGA; lpFilename
0x180020f6d  mov     r8d, 104h; nSize
0x180020f73  call    cs:__imp_GetModuleFileNameW
0x180020f79  mov     r15d, 1
0x180020f7f  test    eax, eax
0x180020f81  jz      loc_180021088
0x180020f87  xor     r9d, r9d; lpName
0x180020f8a  xor     r8d, r8d; bInitialState
0x180020f8d  xor     edx, edx; bManualReset
0x180020f8f  xor     ecx, ecx; lpEventAttributes
0x180020f91  call    cs:__imp_CreateEventW
0x180020f97  mov     [rbx], rax
0x180020f9a  test    rax, rax
0x180020f9d  jz      loc_180021088
0x180020fa3  xor     r9d, r9d; lpName
0x180020fa6  xor     r8d, r8d; bInitialState
0x180020fa9  mov     edx, r15d; bManualReset
0x180020fac  xor     ecx, ecx; lpEventAttributes
0x180020fae  call    cs:__imp_CreateEventW
0x180020fb4  mov     [rsi+60h], rax
0x180020fb8  test    rax, rax
0x180020fbb  jz      loc_180021088
0x180020fc1  mov     rax, [rsi+70h]
0x180020fc5  cmp     [rax+58h], r15d
0x180020fc9  jnz     short loc_180021018
0x180020fcb  lea     ecx, [r15+17h]; Size
0x180020fcf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020fd4  mov     rcx, rax
0x180020fd7  test    rax, rax
0x180020fda  jz      short loc_180020FF5
0x180020fdc  lea     rax, ??_7AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP@@6B@; const AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::`vftable'
0x180020fe3  mov     [rcx], rax
0x180020fe6  xor     eax, eax
0x180020fe8  mov     [rcx+8], ax
0x180020fec  mov     [rcx+0Ch], eax
0x180020fef  mov     [rcx+10h], rax
0x180020ff3  jmp     short loc_180020FF7
0x180020ff5  xor     ecx, ecx; this
0x180020ff7  mov     [rsi+88h], rcx
0x180020ffe  test    rcx, rcx
0x180021001  jnz     short loc_18002100D
0x180021003  mov     edi, 80070008h
0x180021008  jmp     loc_18002108D
0x18002100d  call    ?Initialize@AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP@@QEAAJXZ; AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::Initialize(void)
0x180021012  mov     edi, eax
0x180021014  test    eax, eax
0x180021016  js      short loc_18002108D
0x180021018  cmp     dword ptr [rsi+90h], 0
0x18002101f  jz      short loc_180021071
0x180021021  xor     edi, edi
0x180021023  movzx   eax, di
0x180021026  lea     rcx, [rax+rax*2]
0x18002102a  mov     rax, [rsi+98h]
0x180021031  lea     r14, [rax+rcx*8]
0x180021035  movzx   ecx, di; Node
0x180021038  mov     rdx, r14; ProcessorMask
0x18002103b  call    cs:__imp_GetNumaNodeProcessorMaskEx
0x180021041  test    eax, eax
0x180021043  jz      loc_180021156
0x180021049  mov     rdx, [r14]
0x18002104c  xor     ecx, ecx
0x18002104e  mov     eax, ecx
0x180021050  bt      rdx, rax
0x180021054  jnb     short loc_18002105A
0x180021056  add     [r14+10h], r15b
0x18002105a  add     ecx, r15d
0x18002105d  cmp     ecx, 40h ; '@'
0x180021060  jb      short loc_18002104E
0x180021062  add     di, r15w
0x180021066  movzx   eax, di
0x180021069  cmp     eax, [rsi+0A0h]
0x18002106f  jbe     short loc_180021023
0x180021071  lea     rcx, [rsi+8]; lpCriticalSection
0x180021075  mov     edx, 80000000h; dwSpinCount
0x18002107a  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180021080  test    eax, eax
0x180021082  jnz     loc_180021174
0x180021088  mov     edi, 80004005h
0x18002108d  mov     rcx, [rbx]; hObject
0x180021090  test    rcx, rcx
0x180021093  jz      short loc_1800210A2
0x180021095  call    cs:__imp_CloseHandle
0x18002109b  mov     qword ptr [rbx], 0
0x1800210a2  mov     rcx, [rsi+60h]; hObject
0x1800210a6  test    rcx, rcx
0x1800210a9  jz      short loc_1800210B9
0x1800210ab  call    cs:__imp_CloseHandle
0x1800210b1  mov     qword ptr [rsi+60h], 0
0x1800210b9  mov     rcx, [rsi+88h]
0x1800210c0  test    rcx, rcx
0x1800210c3  jz      short loc_1800210DE
0x1800210c5  mov     rax, [rcx]
0x1800210c8  mov     edx, r15d
0x1800210cb  mov     rax, [rax]
0x1800210ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210d3  mov     qword ptr [rsi+88h], 0
0x1800210de  mov     rbx, [rsi+98h]
0x1800210e5  test    rbx, rbx
0x1800210e8  jz      short loc_180021109
0x1800210ea  call    cs:__imp_GetProcessHeap
0x1800210f0  mov     r8, rbx; lpMem
0x1800210f3  xor     edx, edx; dwFlags
0x1800210f5  mov     rcx, rax; hHeap
0x1800210f8  call    cs:__imp_HeapFree
0x1800210fe  mov     qword ptr [rsi+98h], 0
0x180021109  mov     rcx, [rsi+0A8h]; lpAttributeList
0x180021110  test    rcx, rcx
0x180021113  jz      short loc_180021176
0x180021115  cmp     dword ptr [rsi+0B8h], 0
0x18002111c  jz      short loc_18002112E
0x18002111e  call    cs:__imp_DeleteProcThreadAttributeList
0x180021124  mov     dword ptr [rsi+0B8h], 0
0x18002112e  mov     rbx, [rsi+0A8h]
0x180021135  call    cs:__imp_GetProcessHeap
0x18002113b  mov     r8, rbx; lpMem
0x18002113e  xor     edx, edx; dwFlags
0x180021140  mov     rcx, rax; hHeap
0x180021143  call    cs:__imp_HeapFree
0x180021149  mov     qword ptr [rsi+0A8h], 0
0x180021154  jmp     short loc_180021176
0x180021156  call    cs:__imp_GetLastError
0x18002115c  mov     edi, eax
0x18002115e  test    eax, eax
0x180021160  jle     short loc_18002116B
0x180021162  movzx   edi, ax
0x180021165  or      edi, 80070000h
0x18002116b  test    edi, edi
0x18002116d  jns     short loc_180021176
0x18002116f  jmp     loc_18002108D
0x180021174  xor     edi, edi
0x180021176  mov     eax, edi
0x180021178  add     rsp, 20h
0x18002117c  pop     r15
0x18002117e  pop     r14
0x180021180  pop     rdi
0x180021181  pop     rsi
0x180021182  pop     rbx
0x180021183  retn
```
