# FrsReadOnlyFilter::SendMessageW(_DFSRRO_MESSAGE *,ulong)

- ea: `0x1401cd800`
- end: `0x1401cd9a5`
- name: `?SendMessageW@FrsReadOnlyFilter@@AEAAPEAVFrsStatus@@PEAU_DFSRRO_MESSAGE@@K@Z`
- size: `421`
- prototype: `struct FrsStatus *(FrsReadOnlyFilter *__hidden this, struct _DFSRRO_MESSAGE *, unsigned int)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x1401ccc94`
- `0x1401cd5ac`
- `0x1401cd9ac`
- `0x1401cdbf8`

## callees

- `0x1401b89c8`
- `0x1401b8a38`
- `0x1401b9494`
- `0x1401cd800`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1401cd830`
- `KERNEL32!GetCurrentThreadId` at `0x1401cd895`
- `KERNEL32!GetCurrentThreadId` at `0x1401cd8b8`
- `KERNEL32!GetCurrentThreadId` at `0x1401cd8f2`
- `KERNEL32!GetCurrentThreadId` at `0x1401cd92f`
- `KERNEL32!GetCurrentThreadId` at `0x1401cd94a`
- `KERNEL32!GetCurrentThreadId` at `0x1401cd830`
- `KERNEL32!GetCurrentThreadId` at `0x1401cd895`
- `KERNEL32!GetCurrentThreadId` at `0x1401cd8b8`
- `KERNEL32!GetCurrentThreadId` at `0x1401cd8f2`
- `KERNEL32!GetCurrentThreadId` at `0x1401cd92f`
- `KERNEL32!GetCurrentThreadId` at `0x1401cd94a`
- `FLTLIB!FilterSendMessage` at `0x1401cd880`
- `FLTLIB!FilterSendMessage` at `0x1401cd880`

## string_xrefs

- `0x1401cd851`: `base\fs\remotefs\frs\src\readonly\frsreadonlyfilter.cpp`
- `0x1401cd84a`: `FrsReadOnlyFilter::SendMessageW`

## pseudocode

```c
struct FrsStatus *__fastcall FrsReadOnlyFilter::SendMessageW(
        FrsReadOnlyFilter *this,
        struct _DFSRRO_MESSAGE *a2,
        DWORD a3)
{
  __int64 v3; // rdi
  CREWLock *v4; // rbp
  unsigned int *v5; // rsi
  DWORD CurrentThreadId; // eax
  char *v10; // rcx
  HRESULT v11; // ebx
  __int64 v12; // rcx
  DWORD v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rax
  DWORD v16; // eax
  DWORD v17; // eax
  __int64 v18; // rcx
  int v20; // [rsp+30h] [rbp-48h]
  DWORD v21; // [rsp+38h] [rbp-40h]
  DWORD BytesReturned; // [rsp+80h] [rbp+8h] BYREF

  v3 = 0;
  v4 = (FrsReadOnlyFilter *)((char *)this + 48);
  BytesReturned = 0;
  v5 = 0;
  CurrentThreadId = GetCurrentThreadId();
  CREWLock::AcquireReadLock(v4, CurrentThreadId);
  v10 = (char *)*((_QWORD *)this + 5);
  if ( (unsigned __int64)(v10 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v21 = GetCurrentThreadId();
    v20 = 943;
    goto LABEL_9;
  }
  v11 = FilterSendMessage(v10, a2, a3, 0, 0, &BytesReturned);
  if ( v11 == -2147024890 )
  {
    v21 = GetCurrentThreadId();
    v20 = 929;
LABEL_9:
    v15 = FrsStatusList::PushNewError(
            v12,
            9076,
            0,
            3,
            "base\\fs\\remotefs\\frs\\src\\readonly\\frsreadonlyfilter.cpp",
            "FrsReadOnlyFilter::SendMessageW",
            v20,
            v21,
            0);
    goto LABEL_10;
  }
  if ( v11 >= 0 )
    goto LABEL_11;
  v13 = GetCurrentThreadId();
  v14 = v11 & 0x1FFF0000;
  if ( (_DWORD)v14 == 458752 )
    v11 = (unsigned __int16)v11;
  v15 = FrsStatusList::PushNewError(
          v14,
          (unsigned int)v11,
          0,
          1,
          "base\\fs\\remotefs\\frs\\src\\readonly\\frsreadonlyfilter.cpp",
          "FrsReadOnlyFilter::SendMessageW",
          935,
          v13,
          0);
LABEL_10:
  v5 = (unsigned int *)v15;
LABEL_11:
  v16 = GetCurrentThreadId();
  CREWLock::Release(v4, v16);
  if ( v5 )
  {
    v17 = GetCurrentThreadId();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v18,
                                 v5[1],
                                 v5[2],
                                 *v5,
                                 "base\\fs\\remotefs\\frs\\src\\readonly\\frsreadonlyfilter.cpp",
                                 "FrsReadOnlyFilter::SendMessageW",
                                 948,
                                 v17,
                                 v5);
  }
  return (struct FrsStatus *)v3;
}

```

## disassembly

```asm
0x1401cd800  mov     rax, rsp
0x1401cd803  mov     [rax+10h], rbx
0x1401cd807  mov     [rax+18h], rbp
0x1401cd80b  mov     [rax+20h], rsi
0x1401cd80f  push    rdi
0x1401cd810  push    r12
0x1401cd812  push    r13
0x1401cd814  push    r14
0x1401cd816  push    r15
0x1401cd818  sub     rsp, 50h
0x1401cd81c  xor     edi, edi
0x1401cd81e  lea     rbp, [rcx+30h]
0x1401cd822  mov     [rax+8], edi
0x1401cd825  mov     esi, edi
0x1401cd827  mov     r14d, r8d
0x1401cd82a  mov     r15, rdx
0x1401cd82d  mov     rbx, rcx
0x1401cd830  call    cs:__imp_GetCurrentThreadId
0x1401cd837  nop     dword ptr [rax+rax+00h]
0x1401cd83c  mov     edx, eax; unsigned __int64
0x1401cd83e  mov     rcx, rbp; this
0x1401cd841  call    ?AcquireReadLock@CREWLock@@QEAAX_K@Z; CREWLock::AcquireReadLock(unsigned __int64)
0x1401cd846  mov     rcx, [rbx+28h]; hPort
0x1401cd84a  lea     r12, aFrsreadonlyfil_11; "FrsReadOnlyFilter::SendMessageW"
0x1401cd851  lea     r13, aBaseFsRemotefs_37; "base\\fs\\remotefs\\frs\\src\\readonly"...
0x1401cd858  lea     rax, [rcx-1]
0x1401cd85c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1401cd860  ja      loc_1401CD8F2
0x1401cd866  lea     rax, [rsp+78h+BytesReturned]
0x1401cd86e  xor     r9d, r9d; lpOutBuffer
0x1401cd871  mov     [rsp+78h+lpBytesReturned], rax; lpBytesReturned
0x1401cd876  mov     r8d, r14d; dwInBufferSize
0x1401cd879  mov     rdx, r15; lpInBuffer
0x1401cd87c  mov     [rsp+78h+dwOutBufferSize], edi; dwOutBufferSize
0x1401cd880  call    cs:__imp_FilterSendMessage
0x1401cd887  nop     dword ptr [rax+rax+00h]
0x1401cd88c  mov     ebx, eax
0x1401cd88e  cmp     eax, 80070006h
0x1401cd893  jnz     short loc_1401CD8B4
0x1401cd895  call    cs:__imp_GetCurrentThreadId
0x1401cd89c  nop     dword ptr [rax+rax+00h]
0x1401cd8a1  mov     [rsp+78h+var_38], rdi
0x1401cd8a6  mov     [rsp+78h+var_40], eax
0x1401cd8aa  mov     [rsp+78h+var_48], 3A1h
0x1401cd8b2  jmp     short loc_1401CD90F
0x1401cd8b4  test    ebx, ebx
0x1401cd8b6  jns     short loc_1401CD92F
0x1401cd8b8  call    cs:__imp_GetCurrentThreadId
0x1401cd8bf  nop     dword ptr [rax+rax+00h]
0x1401cd8c4  mov     ecx, ebx
0x1401cd8c6  and     ecx, 1FFF0000h
0x1401cd8cc  cmp     ecx, 70000h
0x1401cd8d2  jnz     short loc_1401CD8D7
0x1401cd8d4  movzx   ebx, bx
0x1401cd8d7  mov     [rsp+78h+var_38], rdi
0x1401cd8dc  mov     r9d, 1
0x1401cd8e2  mov     [rsp+78h+var_40], eax
0x1401cd8e6  mov     edx, ebx
0x1401cd8e8  mov     [rsp+78h+var_48], 3A7h
0x1401cd8f0  jmp     short loc_1401CD91A
0x1401cd8f2  call    cs:__imp_GetCurrentThreadId
0x1401cd8f9  nop     dword ptr [rax+rax+00h]
0x1401cd8fe  mov     [rsp+78h+var_38], rdi
0x1401cd903  mov     [rsp+78h+var_40], eax
0x1401cd907  mov     [rsp+78h+var_48], 3AFh
0x1401cd90f  mov     r9d, 3
0x1401cd915  mov     edx, 2374h
0x1401cd91a  mov     [rsp+78h+lpBytesReturned], r12
0x1401cd91f  xor     r8d, r8d
0x1401cd922  mov     qword ptr [rsp+78h+dwOutBufferSize], r13
0x1401cd927  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401cd92c  mov     rsi, rax
0x1401cd92f  call    cs:__imp_GetCurrentThreadId
0x1401cd936  nop     dword ptr [rax+rax+00h]
0x1401cd93b  mov     edx, eax; unsigned __int64
0x1401cd93d  mov     rcx, rbp; this
0x1401cd940  call    ?Release@CREWLock@@QEAAX_K@Z; CREWLock::Release(unsigned __int64)
0x1401cd945  test    rsi, rsi
0x1401cd948  jz      short loc_1401CD983
0x1401cd94a  call    cs:__imp_GetCurrentThreadId
0x1401cd951  nop     dword ptr [rax+rax+00h]
0x1401cd956  mov     r9d, [rsi]
0x1401cd959  mov     r8d, [rsi+8]
0x1401cd95d  mov     edx, [rsi+4]
0x1401cd960  mov     [rsp+78h+var_38], rsi
0x1401cd965  mov     [rsp+78h+var_40], eax
0x1401cd969  mov     [rsp+78h+var_48], 3B4h
0x1401cd971  mov     [rsp+78h+lpBytesReturned], r12
0x1401cd976  mov     qword ptr [rsp+78h+dwOutBufferSize], r13
0x1401cd97b  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401cd980  mov     rdi, rax
0x1401cd983  lea     r11, [rsp+78h+var_28]
0x1401cd988  mov     rax, rdi
0x1401cd98b  mov     rbx, [r11+38h]
0x1401cd98f  mov     rbp, [r11+40h]
0x1401cd993  mov     rsi, [r11+48h]
0x1401cd997  mov     rsp, r11
0x1401cd99a  pop     r15
0x1401cd99c  pop     r14
0x1401cd99e  pop     r13
0x1401cd9a0  pop     r12
0x1401cd9a2  pop     rdi
0x1401cd9a3  retn
```
