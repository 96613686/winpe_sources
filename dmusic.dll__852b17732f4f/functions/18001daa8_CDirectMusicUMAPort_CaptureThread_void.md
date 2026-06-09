# CDirectMusicUMAPort::CaptureThread(void)

- ea: `0x18001daa8`
- end: `0x18001dd38`
- name: `?CaptureThread@CDirectMusicUMAPort@@AEAAXXZ`
- size: `656`
- prototype: `void __fastcall(CDirectMusicUMAPort *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001da90`

## callees

- `0x1800016d0`
- `0x1800021a8`
- `0x18001daa8`
- `0x18001fb6c`
- `0x1800211cc`
- `0x180021750`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001db2b`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001db2b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001dcf5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001dcf5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001dc89`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001dc89`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001dcc5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001dcc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dbff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dc48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dbff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dc48`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001dbe7`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001dbe7`

## pseudocode

```c
void __fastcall CDirectMusicUMAPort::CaptureThread(CDirectMusicUMAPort *this)
{
  CDirectMusicUMAPort *v1; // r15
  KSSTREAM_HEADER *v2; // rdi
  HANDLE *v3; // rbx
  HANDLE EventA; // rax
  KSSTREAM_HEADER *v5; // rbx
  void **v6; // r13
  unsigned int i; // esi
  HANDLE *v8; // rbx
  unsigned int v9; // edi
  char *v10; // r14
  _DWORD *v11; // r12
  unsigned int v12; // r9d
  void *v13; // rcx
  unsigned int v14; // [rsp+20h] [rbp-2608h]
  unsigned int v15; // [rsp+24h] [rbp-2604h]
  void **v17; // [rsp+38h] [rbp-25F0h]
  HANDLE Handles[59]; // [rsp+60h] [rbp-25C8h] BYREF
  HANDLE v19; // [rsp+238h] [rbp-23F0h] BYREF
  __int64 v20; // [rsp+240h] [rbp-23E8h]
  KSSTREAM_HEADER v21; // [rsp+250h] [rbp-23D8h] BYREF
  _BYTE v22[152]; // [rsp+2558h] [rbp-D0h] BYREF

  v1 = this;
  memset_0(Handles, 0, 0x1E8u);
  memset_0(&v21, 0, 0x23A0u);
  v2 = &v21;
  v3 = Handles;
  do
  {
    EventA = CreateEventA(0, 1, 0, 0);
    *v3 = EventA;
    if ( !EventA )
    {
      if ( (unsigned int)(v3 - Handles) )
      {
        CloseHandle(Handles[0]);
        return;
      }
      v3 = Handles;
      EventA = Handles[0];
    }
    v2[1].Duration = (LONGLONG)EventA;
    v2 = (KSSTREAM_HEADER *)((char *)v2 + 152);
    ++v3;
  }
  while ( v2 <= (KSSTREAM_HEADER *)v22 );
  v5 = &v21;
  v6 = (void **)((char *)v1 + 1320);
  v17 = (void **)((char *)v1 + 1320);
  do
  {
    LOBYTE(v5[1].FrameExtent) = 0;
    v5->Size = 56;
    v5->PresentationTime.Numerator = 1;
    v5->PresentationTime.Denominator = 1;
    v5->FrameExtent = 64;
    v5->Data = &v5[1].FrameExtent;
    PinReadData(*v6, v5, (struct _OVERLAPPED *)&v5[1]);
    v5 = (KSSTREAM_HEADER *)((char *)v5 + 152);
  }
  while ( v5 <= (KSSTREAM_HEADER *)v22 );
  v20 = *((_QWORD *)v1 + 186);
  for ( i = 0; ; i = v9 )
  {
    v15 = i;
    WaitForMultipleObjects(0x3Du, Handles, 0, 0xFFFFFFFF);
    if ( *((_DWORD *)v1 + 376) )
      break;
    v9 = i;
    v14 = i;
    do
    {
      if ( v9 < 0x3C )
      {
        v10 = (char *)&v21 + 152 * v9;
        v5 = (KSSTREAM_HEADER *)v10;
        if ( WaitForSingleObject(*((HANDLE *)v10 + 10), 0) )
          break;
        v11 = v10 + 36;
        v12 = *((_DWORD *)v10 + 9);
        if ( v12 )
        {
          CDirectMusicUMAPort::InputWorkerDataReady(v1, *((_QWORD *)v10 + 1), *((unsigned __int8 **)v10 + 5), v12);
          v13 = (void *)*((_QWORD *)v1 + 201);
          if ( v13 )
          {
            try
            {
              SetEvent(v13);
            }
            catch ( ... )
            {
              v5 = (KSSTREAM_HEADER *)((char *)&v21 + 152 * v9);
              i = v15;
              v9 = v14;
              v1 = this;
              v6 = v17;
              v11 = v10 + 36;
            }
          }
        }
        ResetEvent(*((HANDLE *)v10 + 10));
        *v11 = 0;
        *((_DWORD *)v10 + 12) = 0;
      }
      PinReadData(*v6, v5, (struct _OVERLAPPED *)&v5[1]);
      v9 = v9 + 1 < 0x3C ? v9 + 1 : 0;
      v14 = v9;
    }
    while ( v9 != i );
  }
  v8 = Handles;
  do
    CloseHandle(*v8++);
  while ( v8 <= &v19 );
}

```

## disassembly

```asm
0x18001daa8  mov     [rsp+arg_8], rbx
0x18001daad  mov     [rsp+arg_10], rsi
0x18001dab2  push    rdi
0x18001dab3  push    r12
0x18001dab5  push    r13
0x18001dab7  push    r14
0x18001dab9  push    r15
0x18001dabb  mov     eax, 2600h
0x18001dac0  call    _alloca_probe
0x18001dac5  sub     rsp, rax
0x18001dac8  mov     rax, cs:__security_cookie
0x18001dacf  xor     rax, rsp
0x18001dad2  mov     [rsp+2628h+var_38], rax
0x18001dada  mov     r15, rcx
0x18001dadd  mov     [rsp+2628h+var_25F8], rcx
0x18001dae2  xor     edx, edx; Val
0x18001dae4  mov     r8d, 1E8h; Size
0x18001daea  lea     rcx, [rsp+2628h+Handles]; void *
0x18001daef  call    memset_0
0x18001daf4  xor     edx, edx; Val
0x18001daf6  mov     r8d, 23A0h; Size
0x18001dafc  lea     rcx, [rsp+2628h+var_23D8]; void *
0x18001db04  call    memset_0
0x18001db09  lea     rdi, [rsp+2628h+var_23D8]
0x18001db11  lea     rbx, [rsp+2628h+Handles]
0x18001db16  mov     esi, 1
0x18001db1b  mov     r14d, 98h
0x18001db21  xor     r9d, r9d; lpName
0x18001db24  xor     r8d, r8d; bInitialState
0x18001db27  mov     edx, esi; bManualReset
0x18001db29  xor     ecx, ecx; lpEventAttributes
0x18001db2b  call    cs:__imp_CreateEventA
0x18001db31  mov     [rbx], rax
0x18001db34  test    rax, rax
0x18001db37  jnz     short loc_18001DB57
0x18001db39  lea     rax, [rsp+2628h+Handles]
0x18001db3e  sub     rbx, rax
0x18001db41  sar     rbx, 3
0x18001db45  test    ebx, ebx
0x18001db47  jnz     loc_18001DC43
0x18001db4d  lea     rbx, [rsp+2628h+Handles]
0x18001db52  mov     rax, [rsp+2628h+Handles]
0x18001db57  mov     [rdi+50h], rax
0x18001db5b  add     rdi, r14
0x18001db5e  add     rbx, 8
0x18001db62  lea     rax, [rsp+2628h+var_D0]
0x18001db6a  cmp     rdi, rax
0x18001db6d  jbe     short loc_18001DB21
0x18001db6f  lea     rbx, [rsp+2628h+var_23D8]
0x18001db77  lea     r13, [r15+528h]
0x18001db7e  mov     [rsp+2628h+var_25F0], r13
0x18001db83  lea     rax, [rbx+58h]
0x18001db87  xor     ecx, ecx
0x18001db89  mov     [rax], cl
0x18001db8b  mov     dword ptr [rbx], 38h ; '8'
0x18001db91  mov     [rbx+10h], esi
0x18001db94  mov     [rbx+14h], esi
0x18001db97  mov     dword ptr [rbx+20h], 40h ; '@'
0x18001db9e  mov     [rbx+28h], rax
0x18001dba2  lea     r8, [rbx+38h]; struct _OVERLAPPED *
0x18001dba6  mov     rdx, rbx; struct KSSTREAM_HEADER *
0x18001dba9  mov     rcx, [r13+0]; void *
0x18001dbad  call    ?PinReadData@@YAJPEAXPEAUKSSTREAM_HEADER@@PEAU_OVERLAPPED@@@Z; PinReadData(void *,KSSTREAM_HEADER *,_OVERLAPPED *)
0x18001dbb2  add     rbx, r14
0x18001dbb5  lea     rax, [rsp+2628h+var_D0]
0x18001dbbd  cmp     rbx, rax
0x18001dbc0  jbe     short loc_18001DB83
0x18001dbc2  mov     rax, [r15+5D0h]
0x18001dbc9  mov     [rsp+2628h+var_23E8], rax
0x18001dbd1  xor     esi, esi
0x18001dbd3  mov     [rsp+2628h+var_2604], esi
0x18001dbd7  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001dbdb  xor     r8d, r8d; bWaitAll
0x18001dbde  lea     rdx, [rsp+2628h+Handles]; lpHandles
0x18001dbe3  lea     ecx, [r8+3Dh]; nCount
0x18001dbe7  call    cs:__imp_WaitForMultipleObjects
0x18001dbed  cmp     dword ptr [r15+5E0h], 0
0x18001dbf5  jz      short loc_18001DC50
0x18001dbf7  lea     rbx, [rsp+2628h+Handles]
0x18001dbfc  mov     rcx, [rbx]; hObject
0x18001dbff  call    cs:__imp_CloseHandle
0x18001dc05  add     rbx, 8
0x18001dc09  lea     rax, [rsp+2628h+var_23F0]
0x18001dc11  cmp     rbx, rax
0x18001dc14  jbe     short loc_18001DBFC
0x18001dc16  mov     rcx, [rsp+2628h+var_38]
0x18001dc1e  xor     rcx, rsp; StackCookie
0x18001dc21  call    __security_check_cookie
0x18001dc26  lea     r11, [rsp+2628h+var_28]
0x18001dc2e  mov     rbx, [r11+38h]
0x18001dc32  mov     rsi, [r11+40h]
0x18001dc36  mov     rsp, r11
0x18001dc39  pop     r15
0x18001dc3b  pop     r14
0x18001dc3d  pop     r13
0x18001dc3f  pop     r12
0x18001dc41  pop     rdi
0x18001dc42  retn
0x18001dc43  mov     rcx, [rsp+2628h+Handles]; hObject
0x18001dc48  call    cs:__imp_CloseHandle
0x18001dc4e  jmp     short loc_18001DC16
0x18001dc50  mov     edi, esi
0x18001dc52  mov     [rsp+2628h+var_2608], esi
0x18001dc56  cmp     edi, 3Ch ; '<'
0x18001dc59  jnb     loc_18001DD0B
0x18001dc5f  mov     eax, edi
0x18001dc61  imul    rcx, rax, 98h
0x18001dc68  lea     r14, [rsp+2628h+var_23D8]
0x18001dc70  add     r14, rcx
0x18001dc73  mov     rbx, r14
0x18001dc76  mov     [rsp+2628h+var_2600], rbx
0x18001dc7b  lea     rax, [r14+50h]
0x18001dc7f  mov     [rsp+2628h+var_25D8], rax
0x18001dc84  xor     edx, edx; dwMilliseconds
0x18001dc86  mov     rcx, [rax]; hHandle
0x18001dc89  call    cs:__imp_WaitForSingleObject
0x18001dc8f  test    eax, eax
0x18001dc91  jnz     loc_18001DD31
0x18001dc97  lea     r12, [r14+24h]
0x18001dc9b  mov     [rsp+2628h+var_25E0], r12
0x18001dca0  mov     r9d, [r12]; unsigned int
0x18001dca4  test    r9d, r9d
0x18001dca7  jz      short loc_18001DCED
0x18001dca9  mov     r8, [r14+28h]; unsigned __int8 *
0x18001dcad  mov     rdx, [r14+8]; __int64
0x18001dcb1  mov     rcx, r15; this
0x18001dcb4  call    ?InputWorkerDataReady@CDirectMusicUMAPort@@AEAAX_JPEAEK@Z; CDirectMusicUMAPort::InputWorkerDataReady(__int64,uchar *,ulong)
0x18001dcb9  mov     rcx, [r15+648h]; hEvent
0x18001dcc0  test    rcx, rcx
0x18001dcc3  jz      short loc_18001DCED
0x18001dcc5  call    cs:__imp_SetEvent
0x18001dccb  nop
0x18001dccc  jmp     short loc_18001DCED
0x18001dcce  mov     rbx, [rsp+2628h+var_2600]
0x18001dcd3  mov     esi, [rsp+2628h+var_2604]
0x18001dcd7  mov     edi, [rsp+2628h+var_2608]
0x18001dcdb  mov     r15, [rsp+2628h+var_25F8]
0x18001dce0  mov     r13, [rsp+2628h+var_25F0]
0x18001dce5  mov     r14, rbx
0x18001dce8  mov     r12, [rsp+2628h+var_25E0]
0x18001dced  mov     rcx, [rsp+2628h+var_25D8]
0x18001dcf2  mov     rcx, [rcx]; hEvent
0x18001dcf5  call    cs:__imp_ResetEvent
0x18001dcfb  mov     dword ptr [r12], 0
0x18001dd03  mov     dword ptr [r14+30h], 0
0x18001dd0b  lea     r8, [rbx+38h]; struct _OVERLAPPED *
0x18001dd0f  mov     rdx, rbx; struct KSSTREAM_HEADER *
0x18001dd12  mov     rcx, [r13+0]; void *
0x18001dd16  call    ?PinReadData@@YAJPEAXPEAUKSSTREAM_HEADER@@PEAU_OVERLAPPED@@@Z; PinReadData(void *,KSSTREAM_HEADER *,_OVERLAPPED *)
0x18001dd1b  lea     eax, [rdi+1]
0x18001dd1e  cmp     eax, 3Ch ; '<'
0x18001dd21  sbb     edi, edi
0x18001dd23  and     edi, eax
0x18001dd25  mov     [rsp+2628h+var_2608], edi
0x18001dd29  cmp     edi, esi
0x18001dd2b  jnz     loc_18001DC56
0x18001dd31  mov     esi, edi
0x18001dd33  jmp     loc_18001DBD3
```
