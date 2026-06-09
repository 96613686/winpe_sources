# CMit::Start(void)

- ea: `0x1801e6e04`
- end: `0x1801e6ec2`
- name: `?Start@CMit@@QEAAJXZ`
- size: `190`
- prototype: `__int64 __fastcall(CMit *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180184e3c`

## callees

- `0x180050270`
- `0x1801e6e04`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1801e6eb2`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1801e6eb2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1801e6ea8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1801e6ea8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801e6e6c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801e6e6c`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x1801e6e99`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x1801e6e99`

## string_xrefs

- `0x1801e6e8f`: `DWM Master Input Thread`

## pseudocode

```c
__int64 __fastcall CMit::Start(HANDLE *this)
{
  unsigned int v2; // ebx
  HANDLE v3; // rax
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  if ( *((_BYTE *)this + 32) )
  {
    v2 = -2147467260;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_180357030, 2u, -2147467260, 0x61u, 0);
  }
  else
  {
    ThreadId = 0;
    v3 = CreateThread(0, 0, CMit::RunInputThreadStatic, this, 4u, &ThreadId);
    this[2] = v3;
    if ( v3 )
    {
      SetThreadDescription(v3, L"DWM Master Input Thread");
      SetThreadPriority(this[2], 16);
      ResumeThread(this[2]);
      return 0;
    }
    else
    {
      v2 = -2147024882;
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_180357030, 2u, -2147024882, 0x73u, 0);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1801e6e04  push    rbx
0x1801e6e06  sub     rsp, 30h
0x1801e6e0a  cmp     byte ptr [rcx+20h], 0
0x1801e6e0e  mov     rbx, rcx
0x1801e6e11  jz      short loc_1801E6E44
0x1801e6e13  mov     [rsp+38h+lpThreadId], 0; void *
0x1801e6e1c  mov     ebx, 80004004h
0x1801e6e21  mov     [rsp+38h+dwCreationFlags], 61h ; 'a'; unsigned int
0x1801e6e29  mov     r8d, 2; unsigned int
0x1801e6e2f  lea     rdx, qword_180357030; int *
0x1801e6e36  mov     r9d, ebx; int
0x1801e6e39  lea     ecx, [r8+12h]; unsigned int
0x1801e6e3d  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801e6e42  jmp     short loc_1801E6EBA
0x1801e6e44  lea     rax, [rsp+38h+ThreadId]
0x1801e6e49  mov     [rsp+38h+ThreadId], 0
0x1801e6e51  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1801e6e56  lea     r8, ?RunInputThreadStatic@CMit@@SAKPEAX@Z; lpStartAddress
0x1801e6e5d  mov     r9, rbx; lpParameter
0x1801e6e60  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x1801e6e68  xor     edx, edx; dwStackSize
0x1801e6e6a  xor     ecx, ecx; lpThreadAttributes
0x1801e6e6c  call    cs:__imp_CreateThread
0x1801e6e72  mov     [rbx+10h], rax
0x1801e6e76  test    rax, rax
0x1801e6e79  jnz     short loc_1801E6E8F
0x1801e6e7b  mov     [rsp+38h+lpThreadId], rax
0x1801e6e80  mov     ebx, 8007000Eh
0x1801e6e85  mov     [rsp+38h+dwCreationFlags], 73h ; 's'
0x1801e6e8d  jmp     short loc_1801E6E29
0x1801e6e8f  lea     rdx, aDwmMasterInput; "DWM Master Input Thread"
0x1801e6e96  mov     rcx, rax; hThread
0x1801e6e99  call    cs:__imp_SetThreadDescription
0x1801e6e9f  mov     rcx, [rbx+10h]; hThread
0x1801e6ea3  mov     edx, 10h; nPriority
0x1801e6ea8  call    cs:__imp_SetThreadPriority
0x1801e6eae  mov     rcx, [rbx+10h]; hThread
0x1801e6eb2  call    cs:__imp_ResumeThread
0x1801e6eb8  xor     ebx, ebx
0x1801e6eba  mov     eax, ebx
0x1801e6ebc  add     rsp, 30h
0x1801e6ec0  pop     rbx
0x1801e6ec1  retn
```
