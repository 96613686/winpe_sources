# CMSMQQueue::Close(void)

- ea: `0x18001a830`
- end: `0x18001a9fa`
- name: `?Close@CMSMQQueue@@UEAAJXZ`
- size: `458`
- prototype: `__int64 __fastcall(CMSMQQueue *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001a6ec`

## callees

- `0x18000178c`
- `0x180005430`
- `0x18000cb34`
- `0x18001a830`
- `0x18001c8e4`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001a9a9`
- `KERNEL32!LeaveCriticalSection` at `0x18001a9d0`
- `KERNEL32!LeaveCriticalSection` at `0x18001a9da`
- `KERNEL32!LeaveCriticalSection` at `0x18001a9e4`
- `KERNEL32!LeaveCriticalSection` at `0x18001a9a9`
- `KERNEL32!LeaveCriticalSection` at `0x18001a9d0`
- `KERNEL32!LeaveCriticalSection` at `0x18001a9da`
- `KERNEL32!LeaveCriticalSection` at `0x18001a9e4`
- `mqrt!MQDeleteCursorMemory` at `0x18001a91e`
- `mqrt!MQDeleteCursorMemory` at `0x18001a91e`
- `mqrt!MQCloseQueue` at `0x18001a8bc`
- `mqrt!MQCloseQueue` at `0x18001a8bc`
- `mqrt!MQACCloseCursor` at `0x18001a87e`
- `mqrt!MQACCloseCursor` at `0x18001a87e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMSMQQueue::Close(CMSMQQueue *this)
{
  struct _RTL_CRITICAL_SECTION *v3; // r14
  unsigned int v4; // esi
  void *v5; // rcx
  int v6; // eax
  __int64 v7; // r8
  int v8; // edi
  void *v9; // rcx
  HRESULT v10; // eax
  __int64 v11; // r8
  struct _RTL_CRITICAL_SECTION *v12; // rbp
  void *v13; // rcx
  int v14; // eax
  __int64 v15; // r8
  _QWORD *v16; // rdi
  __int64 v17; // rdx
  __int64 v18; // rdx
  unsigned int ErrorHelper; // ebx

  if ( !*((_DWORD *)this + 44) )
    return CreateErrorHelper(2147745799LL, 2);
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 112);
  CCriticalSection::Lock((CMSMQQueue *)((char *)this + 112));
  v4 = 0;
  v5 = (void *)*((_QWORD *)this + 27);
  if ( v5 )
  {
    v6 = MQACCloseCursor(v5);
    v4 = v6;
    if ( v6 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v7, (unsigned int)v6);
    }
  }
  v8 = v4;
  v9 = (void *)*((_QWORD *)this + 21);
  if ( v9 != (void *)-1LL )
  {
    v10 = MQCloseQueue(v9);
    v4 = v10;
    if ( v10 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v11, (unsigned int)v10);
    }
    *((_QWORD *)this + 21) = -1;
  }
  v12 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 72);
  CCriticalSection::Lock((CMSMQQueue *)((char *)this + 72));
  CCriticalSection::Lock((CCriticalSection *)&g_csCallback);
  v13 = (void *)*((_QWORD *)this + 27);
  if ( v13 )
  {
    if ( v8 >= 0 )
    {
      v14 = MQDeleteCursorMemory(v13);
      if ( v14 < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v15, (unsigned int)v14);
      }
    }
  }
  *((_QWORD *)this + 27) = 0;
  v16 = (_QWORD *)*((_QWORD *)this + 28);
  if ( v16 )
  {
    CCriticalSection::Lock((CCriticalSection *)&g_csCallback);
    v17 = v16[8];
    if ( v17 )
      *(_QWORD *)(v17 + 72) = v16[9];
    v18 = v16[9];
    if ( v18 )
      *(_QWORD *)(v18 + 64) = v16[8];
    else
      g_pqnodeFirst = (struct QueueNode *)v16[8];
    operator delete(v16);
    LeaveCriticalSection(&g_csCallback);
    *((_QWORD *)this + 28) = 0;
  }
  ErrorHelper = CreateErrorHelper(v4, 2);
  LeaveCriticalSection(&g_csCallback);
  LeaveCriticalSection(v12);
  LeaveCriticalSection(v3);
  return ErrorHelper;
}

```

## disassembly

```asm
0x18001a830  push    rbx
0x18001a832  push    rbp
0x18001a833  push    rsi
0x18001a834  push    rdi
0x18001a835  push    r13
0x18001a837  push    r14
0x18001a839  sub     rsp, 28h
0x18001a83d  mov     rbx, rcx
0x18001a840  cmp     dword ptr [rcx+0B0h], 0
0x18001a847  jnz     short loc_18001A85D
0x18001a849  mov     edx, 2
0x18001a84e  mov     ecx, 80040007h
0x18001a853  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x18001a858  jmp     loc_18001A9ED
0x18001a85d  lea     r14, [rcx+70h]
0x18001a861  mov     rcx, r14; this
0x18001a864  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18001a869  xor     esi, esi
0x18001a86b  mov     rcx, [rbx+0D8h]
0x18001a872  lea     r13, WPP_GLOBAL_Control
0x18001a879  test    rcx, rcx
0x18001a87c  jz      short loc_18001A8AD
0x18001a87e  call    cs:__imp_?MQACCloseCursor@@YAJPEAX@Z; MQACCloseCursor(void *)
0x18001a884  mov     esi, eax
0x18001a886  test    eax, eax
0x18001a888  jns     short loc_18001A8AD
0x18001a88a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a891  cmp     rcx, r13
0x18001a894  jz      short loc_18001A8AD
0x18001a896  test    byte ptr [rcx+1Ch], 1
0x18001a89a  jz      short loc_18001A8AD
0x18001a89c  mov     edx, 0Ah
0x18001a8a1  mov     r9d, eax
0x18001a8a4  mov     rcx, [rcx+10h]
0x18001a8a8  call    WPP_SF_d
0x18001a8ad  mov     edi, esi
0x18001a8af  mov     rcx, [rbx+0A8h]; hQueue
0x18001a8b6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001a8ba  jz      short loc_18001A8F6
0x18001a8bc  call    cs:__imp_MQCloseQueue
0x18001a8c2  mov     esi, eax
0x18001a8c4  test    eax, eax
0x18001a8c6  jns     short loc_18001A8EB
0x18001a8c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a8cf  cmp     rcx, r13
0x18001a8d2  jz      short loc_18001A8EB
0x18001a8d4  test    byte ptr [rcx+1Ch], 1
0x18001a8d8  jz      short loc_18001A8EB
0x18001a8da  mov     edx, 0Bh
0x18001a8df  mov     r9d, eax
0x18001a8e2  mov     rcx, [rcx+10h]
0x18001a8e6  call    WPP_SF_d
0x18001a8eb  mov     qword ptr [rbx+0A8h], 0FFFFFFFFFFFFFFFFh
0x18001a8f6  lea     rbp, [rbx+48h]
0x18001a8fa  mov     rcx, rbp; this
0x18001a8fd  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18001a902  lea     rcx, ?g_csCallback@@3VCCriticalSection@@A; this
0x18001a909  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18001a90e  mov     rcx, [rbx+0D8h]
0x18001a915  test    rcx, rcx
0x18001a918  jz      short loc_18001A94B
0x18001a91a  test    edi, edi
0x18001a91c  js      short loc_18001A94B
0x18001a91e  call    cs:__imp_?MQDeleteCursorMemory@@YAJPEAX@Z; MQDeleteCursorMemory(void *)
0x18001a924  test    eax, eax
0x18001a926  jns     short loc_18001A94B
0x18001a928  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a92f  cmp     rcx, r13
0x18001a932  jz      short loc_18001A94B
0x18001a934  test    byte ptr [rcx+1Ch], 1
0x18001a938  jz      short loc_18001A94B
0x18001a93a  mov     edx, 0Ch
0x18001a93f  mov     r9d, eax
0x18001a942  mov     rcx, [rcx+10h]
0x18001a946  call    WPP_SF_d
0x18001a94b  mov     qword ptr [rbx+0D8h], 0
0x18001a956  mov     rdi, [rbx+0E0h]
0x18001a95d  test    rdi, rdi
0x18001a960  jz      short loc_18001A9BB
0x18001a962  lea     rcx, ?g_csCallback@@3VCCriticalSection@@A; this
0x18001a969  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18001a96e  mov     rdx, [rdi+40h]
0x18001a972  test    rdx, rdx
0x18001a975  jz      short loc_18001A97F
0x18001a977  mov     rax, [rdi+48h]
0x18001a97b  mov     [rdx+48h], rax
0x18001a97f  mov     rdx, [rdi+48h]
0x18001a983  mov     rax, [rdi+40h]
0x18001a987  test    rdx, rdx
0x18001a98a  jz      short loc_18001A992
0x18001a98c  mov     [rdx+40h], rax
0x18001a990  jmp     short loc_18001A999
0x18001a992  mov     cs:?g_pqnodeFirst@@3PEAUQueueNode@@EA, rax; QueueNode * g_pqnodeFirst
0x18001a999  mov     rcx, rdi; Block
0x18001a99c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001a9a1  nop
0x18001a9a2  lea     rcx, ?g_csCallback@@3VCCriticalSection@@A; lpCriticalSection
0x18001a9a9  call    cs:__imp_LeaveCriticalSection
0x18001a9af  nop
0x18001a9b0  mov     qword ptr [rbx+0E0h], 0
0x18001a9bb  mov     edx, 2
0x18001a9c0  mov     ecx, esi
0x18001a9c2  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x18001a9c7  mov     ebx, eax
0x18001a9c9  lea     rcx, ?g_csCallback@@3VCCriticalSection@@A; lpCriticalSection
0x18001a9d0  call    cs:__imp_LeaveCriticalSection
0x18001a9d6  nop
0x18001a9d7  mov     rcx, rbp; lpCriticalSection
0x18001a9da  call    cs:__imp_LeaveCriticalSection
0x18001a9e0  nop
0x18001a9e1  mov     rcx, r14; lpCriticalSection
0x18001a9e4  call    cs:__imp_LeaveCriticalSection
0x18001a9ea  nop
0x18001a9eb  mov     eax, ebx
0x18001a9ed  add     rsp, 28h
0x18001a9f1  pop     r14
0x18001a9f3  pop     r13
0x18001a9f5  pop     rdi
0x18001a9f6  pop     rsi
0x18001a9f7  pop     rbp
0x18001a9f8  pop     rbx
0x18001a9f9  retn
```
