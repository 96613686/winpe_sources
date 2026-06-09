# CmsRestarter::RedoPass(void)

- ea: `0x1c004c070`
- end: `0x1c004c0cf`
- name: `?RedoPass@CmsRestarter@@AEAAJXZ`
- size: `95`
- prototype: `__int64 __fastcall(CmsRestarter *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1c004bc94`

## callees

- `0x1c003f0f4`
- `0x1c004a320`
- `0x1c004c070`
- `0x1c004c748`
- `0x1c006af80`
- `0x1c00e0a08`
- `0x1c00e5b4c`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0085f77`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0085f77`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0085ddf`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0085e2a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0085eae`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0085ee4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0085ddf`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0085e2a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0085eae`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0085ee4`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0085f8e`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0085f8e`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c0085fc4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1c0085fc4`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c0085d8c`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c00860c7`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c0085d8c`
- `ntoskrnl!IoGetActivityIdThread` at `0x1c00860c7`
- `ntoskrnl!KeSetEvent` at `0x1c0085f52`
- `ntoskrnl!KeSetEvent` at `0x1c0085f52`

## pseudocode

```c
__int64 __fastcall CmsRestarter::RedoPass(CmsRestarter *this)
{
  int v2; // ebp
  int v4; // ebx
  __int64 v5; // rdi
  int ActivityIdThread; // eax
  SIZE_T v7; // rdx
  PVOID PoolWithTag; // rax
  unsigned int v9; // eax
  unsigned int v10; // edi
  PVOID v11; // rax
  PVOID v12; // rbx
  __int64 v13; // rcx
  PVOID v14; // rax
  _QWORD *v15; // rax
  unsigned int i; // ebx
  unsigned int v17; // eax
  int v18; // ecx
  __int64 *v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rax
  int v22; // ecx
  __int64 v23; // rbx
  __int64 v24; // rdi
  int v25; // eax
  __int64 v26; // [rsp+50h] [rbp+8h] BYREF

  v26 = 0;
  v2 = 0;
  if ( dword_1C012D0B4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
  {
    v4 = *((_DWORD *)this + 8);
    v5 = *((_QWORD *)this + 5);
    ActivityIdThread = IoGetActivityIdThread();
    McTemplateK0iix_EtwWriteTransfer(
      (unsigned int)MinstoreEventProvider_Context,
      (unsigned int)RedoPassStart,
      ActivityIdThread,
      v5,
      0,
      v4);
  }
  if ( *((_DWORD *)this + 44) )
  {
    v7 = 8LL * *((unsigned int *)this + 51);
    *((_DWORD *)this + 4) = 4;
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, v7, 0x6950534Du);
    *((_QWORD *)this + 26) = PoolWithTag;
    if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, 8LL * *((unsigned int *)this + 51));
      v9 = *((_DWORD *)this + 51);
      v10 = 0;
      if ( v9 )
      {
        while ( 1 )
        {
          v11 = ExAllocatePoolWithTag((POOL_TYPE)512, 0xF8u, 0x6950534Du);
          v12 = v11;
          if ( v11 )
            memset(v11, 0, 0xF8u);
          else
            v12 = 0;
          *(_QWORD *)(*((_QWORD *)this + 26) + 8LL * v10) = v12;
          v13 = *(_QWORD *)(*((_QWORD *)this + 26) + 8LL * v10);
          if ( !v13 )
            break;
          *(_DWORD *)(v13 + 240) = v10;
          CmsLogRedoQueue::Initialize(*(CmsLogRedoQueue **)(*((_QWORD *)this + 26) + 8LL * v10), this);
          v9 = *((_DWORD *)this + 51);
          if ( ++v10 >= v9 )
            goto LABEL_15;
        }
      }
      else
      {
LABEL_15:
        v14 = ExAllocatePoolWithTag((POOL_TYPE)512, v9, 0x6950534Du);
        *((_QWORD *)this + 38) = v14;
        if ( v14 )
        {
          memset(v14, 0, *((unsigned int *)this + 51));
          v15 = ExAllocatePoolWithTag((POOL_TYPE)512, 0x28u, 0x6950534Du);
          if ( v15 )
          {
            v15[1] = 0;
            v15[2] = 0;
            v15[3] = 0;
            v15[4] = 0;
            *v15 = v15;
          }
          else
          {
            v15 = 0;
          }
          *((_QWORD *)this + 15) = v15;
          if ( v15 )
          {
            v2 = MlLogScanLog(
                   *(_QWORD *)(*(_QWORD *)this + 72LL),
                   *((_QWORD *)this + 1),
                   *((_QWORD *)this + 5),
                   (unsigned int)&CmsRestarter::RedoOneMergedRecordBlock,
                   (__int64)this,
                   (__int64)&v26);
            KeSetEvent((PRKEVENT)((char *)this + 256), 0, 0);
            if ( v2 < 0 && *((int *)this + 50) >= 0 )
            {
              ExAcquirePushLockExclusiveEx((char *)this + 216, 0);
              *((_DWORD *)this + 50) = v2;
              ExReleasePushLockEx((char *)this + 216, 0);
            }
            for ( i = 0; i < *((_DWORD *)this + 51); ++i )
              KeWaitForSingleObject((PVOID)(*(_QWORD *)(*((_QWORD *)this + 26) + 8LL * i) + 40LL), Executive, 0, 0, 0);
            if ( v2 >= 0 )
            {
              v2 = *((_DWORD *)this + 50);
              *((_QWORD *)this + 13) = v26;
              if ( v2 >= 0 )
              {
                v17 = *((_DWORD *)this + 51);
                v18 = *((_DWORD *)this + 44);
                if ( v17 )
                {
                  v19 = (__int64 *)*((_QWORD *)this + 26);
                  v20 = v17;
                  do
                  {
                    v21 = *v19++;
                    v18 -= *(_DWORD *)(v21 + 8);
                    *((_DWORD *)this + 44) = v18;
                    --v20;
                  }
                  while ( v20 );
                }
                v22 = v18 - *((_DWORD *)this + 45);
                *((_DWORD *)this + 44) = v22;
                if ( v22 )
                {
                  v2 = -1073741774;
                }
                else
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  {
                    WPP_SF_qq(
                      WPP_GLOBAL_Control->AttachedDevice,
                      20,
                      WPP_a26a0f824fd733884f700469454722c9_Traceguids,
                      *((_QWORD *)this + 23),
                      *((_QWORD *)this + 24));
                  }
                  v2 = CmsObjectTable::SetMinimumNewObjectId(
                         *(PKGUARDED_MUTEX *)(*((_QWORD *)this + 1) + 3096LL),
                         (CmsRestarter *)((char *)this + 184));
                  if ( v2 == -1073741811 )
                    v2 = 0;
                }
              }
            }
            goto LABEL_3;
          }
        }
      }
    }
    v2 = -1073741670;
  }
LABEL_3:
  if ( dword_1C012D0B4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
  {
    v23 = *((_QWORD *)this + 12);
    v24 = *((_QWORD *)this + 5);
    v25 = IoGetActivityIdThread();
    McTemplateK0iix_EtwWriteTransfer(
      (unsigned int)MinstoreEventProvider_Context,
      (unsigned int)RedoPassEnd,
      v25,
      v24,
      v23,
      0);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1c004c070  mov     [rsp+arg_8], rbx
0x1c004c075  mov     [rsp+arg_10], rbp
0x1c004c07a  push    rsi
0x1c004c07b  push    rdi
0x1c004c07c  push    r14
0x1c004c07e  sub     rsp, 30h
0x1c004c082  xor     eax, eax
0x1c004c084  xor     r14d, r14d
0x1c004c087  cmp     cs:dword_1C012D0B4, 1
0x1c004c08e  mov     rsi, rcx
0x1c004c091  mov     [rsp+48h+arg_0], rax
0x1c004c096  mov     ebp, r14d
0x1c004c099  jz      loc_1C0085D78
0x1c004c09f  cmp     [rsi+0B0h], r14d
0x1c004c0a6  jnz     loc_1C0085DC1
0x1c004c0ac  cmp     cs:dword_1C012D0B4, 1
0x1c004c0b3  jz      loc_1C00860B2
0x1c004c0b9  mov     rbx, [rsp+48h+arg_8]
0x1c004c0be  mov     eax, ebp
0x1c004c0c0  mov     rbp, [rsp+48h+arg_10]
0x1c004c0c5  add     rsp, 30h
0x1c004c0c9  pop     r14
0x1c004c0cb  pop     rdi
0x1c004c0cc  pop     rsi
0x1c004c0cd  retn
0x1c0085d78  test    cs:Microsoft_Windows_MinstoreEnableBits, 1
0x1c0085d7f  jz      loc_1C004C09F
0x1c0085d85  mov     ebx, [rcx+20h]
0x1c0085d88  mov     rdi, [rcx+28h]
0x1c0085d8c  call    cs:__imp_IoGetActivityIdThread
0x1c0085d93  nop     dword ptr [rax+rax+00h]
0x1c0085d98  mov     [rsp+48h+var_20], rbx
0x1c0085d9d  lea     rdx, RedoPassStart
0x1c0085da4  mov     r8, rax
0x1c0085da7  mov     [rsp+48h+Timeout], r14
0x1c0085dac  mov     r9, rdi
0x1c0085daf  lea     rcx, MinstoreEventProvider_Context
0x1c0085db6  call    McTemplateK0iix_EtwWriteTransfer
0x1c0085dbb  nop
0x1c0085dbc  jmp     loc_1C004C09F
0x1c0085dc1  mov     edx, [rsi+0CCh]
0x1c0085dc7  mov     ebp, 6950534Dh
0x1c0085dcc  shl     rdx, 3; NumberOfBytes
0x1c0085dd0  mov     r8d, ebp; Tag
0x1c0085dd3  mov     ecx, 200h; PoolType
0x1c0085dd8  mov     dword ptr [rsi+10h], 4
0x1c0085ddf  call    cs:__imp_ExAllocatePoolWithTag
0x1c0085de6  nop     dword ptr [rax+rax+00h]
0x1c0085deb  mov     [rsi+0D0h], rax
0x1c0085df2  test    rax, rax
0x1c0085df5  jz      short loc_1C0085E50
0x1c0085df7  mov     r8d, [rsi+0CCh]
0x1c0085dfe  xor     edx, edx; Val
0x1c0085e00  shl     r8, 3; Size
0x1c0085e04  mov     rcx, rax; void *
0x1c0085e07  call    memset
0x1c0085e0c  mov     eax, [rsi+0CCh]
0x1c0085e12  mov     edi, r14d
0x1c0085e15  test    eax, eax
0x1c0085e17  jz      loc_1C0085EA4
0x1c0085e1d  mov     r8d, ebp; Tag
0x1c0085e20  mov     edx, 0F8h; NumberOfBytes
0x1c0085e25  mov     ecx, 200h; PoolType
0x1c0085e2a  call    cs:__imp_ExAllocatePoolWithTag
0x1c0085e31  nop     dword ptr [rax+rax+00h]
0x1c0085e36  mov     rbx, rax
0x1c0085e39  test    rax, rax
0x1c0085e3c  jz      short loc_1C0085E5A
0x1c0085e3e  xor     edx, edx; Val
0x1c0085e40  mov     r8d, 0F8h; Size
0x1c0085e46  mov     rcx, rax; void *
0x1c0085e49  call    memset
0x1c0085e4e  jmp     short loc_1C0085E5D
0x1c0085e50  mov     ebp, 0C000009Ah
0x1c0085e55  jmp     loc_1C004C0AC
0x1c0085e5a  mov     rbx, r14
0x1c0085e5d  mov     rax, [rsi+0D0h]
0x1c0085e64  mov     r8d, edi
0x1c0085e67  mov     [rax+r8*8], rbx
0x1c0085e6b  mov     rax, [rsi+0D0h]
0x1c0085e72  mov     rcx, [rax+r8*8]
0x1c0085e76  test    rcx, rcx
0x1c0085e79  jz      short loc_1C0085E50
0x1c0085e7b  mov     [rcx+0F0h], edi
0x1c0085e81  mov     rdx, rsi; struct CmsRestarter *
0x1c0085e84  mov     rcx, [rsi+0D0h]
0x1c0085e8b  mov     rcx, [rcx+r8*8]; this
0x1c0085e8f  call    ?Initialize@CmsLogRedoQueue@@QEAAXPEAVCmsRestarter@@@Z; CmsLogRedoQueue::Initialize(CmsRestarter *)
0x1c0085e94  mov     eax, [rsi+0CCh]
0x1c0085e9a  inc     edi
0x1c0085e9c  cmp     edi, eax
0x1c0085e9e  jb      loc_1C0085E1D
0x1c0085ea4  mov     edx, eax; NumberOfBytes
0x1c0085ea6  mov     r8d, ebp; Tag
0x1c0085ea9  mov     ecx, 200h; PoolType
0x1c0085eae  call    cs:__imp_ExAllocatePoolWithTag
0x1c0085eb5  nop     dword ptr [rax+rax+00h]
0x1c0085eba  mov     [rsi+130h], rax
0x1c0085ec1  test    rax, rax
0x1c0085ec4  jz      short loc_1C0085E50
0x1c0085ec6  mov     r8d, [rsi+0CCh]; Size
0x1c0085ecd  xor     edx, edx; Val
0x1c0085ecf  mov     rcx, rax; void *
0x1c0085ed2  call    memset
0x1c0085ed7  mov     r8d, ebp; Tag
0x1c0085eda  mov     edx, 28h ; '('; NumberOfBytes
0x1c0085edf  mov     ecx, 200h; PoolType
0x1c0085ee4  call    cs:__imp_ExAllocatePoolWithTag
0x1c0085eeb  nop     dword ptr [rax+rax+00h]
0x1c0085ef0  test    rax, rax
0x1c0085ef3  jz      short loc_1C0085F0A
0x1c0085ef5  mov     [rax+8], r14
0x1c0085ef9  mov     [rax+10h], r14
0x1c0085efd  mov     [rax+18h], r14
0x1c0085f01  mov     [rax+20h], r14
0x1c0085f05  mov     [rax], rax
0x1c0085f08  jmp     short loc_1C0085F0D
0x1c0085f0a  mov     rax, r14
0x1c0085f0d  mov     [rsi+78h], rax
0x1c0085f11  test    rax, rax
0x1c0085f14  jz      loc_1C0085E50
0x1c0085f1a  mov     rcx, [rsi]
0x1c0085f1d  lea     rax, [rsp+48h+arg_0]
0x1c0085f22  mov     r8, [rsi+28h]
0x1c0085f26  lea     r9, ?RedoOneMergedRecordBlock@CmsRestarter@@CAJT_ML_LSN@@PEAXK1@Z; CmsRestarter::RedoOneMergedRecordBlock(_ML_LSN,void *,ulong,void *)
0x1c0085f2d  mov     rdx, [rsi+8]
0x1c0085f31  mov     [rsp+48h+var_20], rax
0x1c0085f36  mov     rcx, [rcx+48h]
0x1c0085f3a  mov     [rsp+48h+Timeout], rsi
0x1c0085f3f  call    MlLogScanLog
0x1c0085f44  lea     rcx, [rsi+100h]; Event
0x1c0085f4b  xor     r8d, r8d; Wait
0x1c0085f4e  xor     edx, edx; Increment
0x1c0085f50  mov     ebp, eax
0x1c0085f52  call    cs:__imp_KeSetEvent
0x1c0085f59  nop     dword ptr [rax+rax+00h]
0x1c0085f5e  test    ebp, ebp
0x1c0085f60  jns     short loc_1C0085F9A
0x1c0085f62  cmp     [rsi+0C8h], r14d
0x1c0085f69  jl      short loc_1C0085F9A
0x1c0085f6b  lea     rbx, [rsi+0D8h]
0x1c0085f72  xor     edx, edx
0x1c0085f74  mov     rcx, rbx
0x1c0085f77  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c0085f7e  nop     dword ptr [rax+rax+00h]
0x1c0085f83  xor     edx, edx
0x1c0085f85  mov     [rsi+0C8h], ebp
0x1c0085f8b  mov     rcx, rbx
0x1c0085f8e  call    cs:__imp_ExReleasePushLockEx
0x1c0085f95  nop     dword ptr [rax+rax+00h]
0x1c0085f9a  mov     ebx, r14d
0x1c0085f9d  cmp     [rsi+0CCh], r14d
0x1c0085fa4  jbe     short loc_1C0085FDA
0x1c0085fa6  mov     rax, [rsi+0D0h]
0x1c0085fad  xor     r9d, r9d; Alertable
0x1c0085fb0  mov     ecx, ebx
0x1c0085fb2  xor     r8d, r8d; WaitMode
0x1c0085fb5  xor     edx, edx; WaitReason
0x1c0085fb7  mov     [rsp+48h+Timeout], r14; Timeout
0x1c0085fbc  mov     rcx, [rax+rcx*8]
0x1c0085fc0  add     rcx, 28h ; '('; Object
0x1c0085fc4  call    cs:__imp_KeWaitForSingleObject
0x1c0085fcb  nop     dword ptr [rax+rax+00h]
0x1c0085fd0  inc     ebx
0x1c0085fd2  cmp     ebx, [rsi+0CCh]
0x1c0085fd8  jb      short loc_1C0085FA6
0x1c0085fda  test    ebp, ebp
0x1c0085fdc  js      loc_1C004C0AC
0x1c0085fe2  mov     rax, [rsp+48h+arg_0]
0x1c0085fe7  mov     ebp, [rsi+0C8h]
0x1c0085fed  mov     [rsi+68h], rax
0x1c0085ff1  test    ebp, ebp
0x1c0085ff3  js      loc_1C004C0AC
0x1c0085ff9  mov     eax, [rsi+0CCh]
0x1c0085fff  mov     ecx, [rsi+0B0h]
0x1c0086005  test    eax, eax
0x1c0086007  jz      short loc_1C0086029
0x1c0086009  mov     rdx, [rsi+0D0h]
0x1c0086010  mov     r8d, eax
0x1c0086013  mov     rax, [rdx]
0x1c0086016  lea     rdx, [rdx+8]
0x1c008601a  sub     ecx, [rax+8]
0x1c008601d  mov     [rsi+0B0h], ecx
0x1c0086023  sub     r8, 1
0x1c0086027  jnz     short loc_1C0086013
0x1c0086029  sub     ecx, [rsi+0B4h]
0x1c008602f  mov     [rsi+0B0h], ecx
0x1c0086035  jz      short loc_1C0086041
0x1c0086037  mov     ebp, 0C0000032h
0x1c008603c  jmp     loc_1C004C0AC
0x1c0086041  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0086048  lea     rax, WPP_GLOBAL_Control
0x1c008604f  cmp     rcx, rax
0x1c0086052  jz      short loc_1C008608B
0x1c0086054  test    dword ptr [rcx+2Ch], 1000h
0x1c008605b  jz      short loc_1C008608B
0x1c008605d  cmp     byte ptr [rcx+29h], 2
0x1c0086061  jb      short loc_1C008608B
0x1c0086063  mov     rax, [rsi+0C0h]
0x1c008606a  lea     r8, WPP_a26a0f824fd733884f700469454722c9_Traceguids
0x1c0086071  mov     r9, [rsi+0B8h]
0x1c0086078  mov     edx, 14h
0x1c008607d  mov     rcx, [rcx+18h]
0x1c0086081  mov     [rsp+48h+Timeout], rax
0x1c0086086  call    WPP_SF_qq
0x1c008608b  mov     rax, [rsi+8]
0x1c008608f  lea     rdx, [rsi+0B8h]; union _SmsBigIdentifier *
0x1c0086096  mov     rcx, [rax+0C18h]; Mutex
0x1c008609d  call    ?SetMinimumNewObjectId@CmsObjectTable@@QEAAJPEAT_SmsBigIdentifier@@@Z; CmsObjectTable::SetMinimumNewObjectId(_SmsBigIdentifier *)
0x1c00860a2  cmp     eax, 0C000000Dh
0x1c00860a7  mov     ebp, eax
0x1c00860a9  cmovz   ebp, r14d
0x1c00860ad  jmp     loc_1C004C0AC
0x1c00860b2  test    cs:Microsoft_Windows_MinstoreEnableBits, 1
0x1c00860b9  jz      loc_1C004C0B9
0x1c00860bf  mov     rbx, [rsi+60h]
0x1c00860c3  mov     rdi, [rsi+28h]
0x1c00860c7  call    cs:__imp_IoGetActivityIdThread
0x1c00860ce  nop     dword ptr [rax+rax+00h]
0x1c00860d3  mov     [rsp+48h+var_20], r14
0x1c00860d8  lea     rdx, RedoPassEnd
0x1c00860df  mov     r8, rax
0x1c00860e2  mov     [rsp+48h+Timeout], rbx
0x1c00860e7  mov     r9, rdi
0x1c00860ea  lea     rcx, MinstoreEventProvider_Context
0x1c00860f1  call    McTemplateK0iix_EtwWriteTransfer
0x1c00860f6  nop
0x1c00860f7  jmp     loc_1C004C0B9
```
