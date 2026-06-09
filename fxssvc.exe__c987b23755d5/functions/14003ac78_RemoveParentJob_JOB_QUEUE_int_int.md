# RemoveParentJob(_JOB_QUEUE *,int,int)

- ea: `0x14003ac78`
- end: `0x14003b13c`
- name: `?RemoveParentJob@@YAHPEAU_JOB_QUEUE@@HH@Z`
- size: `1220`
- prototype: `__int64 __fastcall(struct _JOB_QUEUE *, int, int)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x14001cf70`
- `0x140037b14`
- `0x14003bf04`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140004b98`
- `0x140004e68`
- `0x1400354bc`
- `0x1400382a4`
- `0x14003a3d8`
- `0x14003ac78`
- `0x14003b234`
- `0x14003da1c`
- `0x14003e488`
- `0x14005584c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003adf3`
- `KERNEL32!GetLastError` at `0x14003ae86`
- `KERNEL32!GetLastError` at `0x14003af0c`
- `KERNEL32!GetLastError` at `0x14003afa0`
- `KERNEL32!GetLastError` at `0x14003b047`
- `KERNEL32!GetLastError` at `0x14003b0bc`
- `KERNEL32!GetLastError` at `0x14003b116`
- `KERNEL32!GetLastError` at `0x14003adf3`
- `KERNEL32!GetLastError` at `0x14003ae86`
- `KERNEL32!GetLastError` at `0x14003af0c`
- `KERNEL32!GetLastError` at `0x14003afa0`
- `KERNEL32!GetLastError` at `0x14003b047`
- `KERNEL32!GetLastError` at `0x14003b0bc`
- `KERNEL32!GetLastError` at `0x14003b116`
- `KERNEL32!DeleteFileW` at `0x14003aeea`
- `KERNEL32!DeleteFileW` at `0x14003af7e`
- `KERNEL32!DeleteFileW` at `0x14003b025`
- `KERNEL32!DeleteFileW` at `0x14003aeea`
- `KERNEL32!DeleteFileW` at `0x14003af7e`
- `KERNEL32!DeleteFileW` at `0x14003b025`
- `KERNEL32!EnterCriticalSection` at `0x14003acd3`
- `KERNEL32!EnterCriticalSection` at `0x14003acd3`
- `KERNEL32!LeaveCriticalSection` at `0x14003ad2e`
- `KERNEL32!LeaveCriticalSection` at `0x14003ad2e`
- `KERNEL32!CancelWaitableTimer` at `0x14003adce`
- `KERNEL32!CancelWaitableTimer` at `0x14003adce`

## pseudocode

```c
__int64 __fastcall RemoveParentJob(struct _LIST_ENTRY *a1, int a2, int a3)
{
  struct _LIST_ENTRY *i; // rbx
  int v8; // edx
  DWORD LastError; // eax
  struct _LIST_ENTRY *Blink; // rax
  struct _LIST_ENTRY *Flink; // rcx
  CMapDeviceId *v12; // rcx
  DWORD v13; // eax
  char v14; // al
  char v15; // al
  char v16; // al
  int v17; // edx
  DWORD v18; // eax
  DWORD v19; // eax

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 247, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
  }
  EnterCriticalSection(&g_CsQueue);
  for ( i = g_QueueListHead.Flink; ; i = i->Flink )
  {
    if ( i == &g_QueueListHead )
      goto LABEL_9;
    if ( i == a1 )
      break;
  }
  if ( !i )
  {
LABEL_9:
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        248,
        &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
        LODWORD(a1[2].Flink),
        (_DWORD)a1);
    }
    goto LABEL_13;
  }
  if ( LODWORD(i[3].Flink) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        249,
        &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
        LODWORD(i[2].Flink),
        i[3].Flink);
    }
    goto LABEL_13;
  }
  if ( HIDWORD(i[3].Flink) )
  {
    _JOB_QUEUE::PutStatus((_JOB_QUEUE *)i, 4u);
    goto LABEL_13;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      250,
      &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
      LODWORD(i[2].Flink));
  }
  if ( !CancelWaitableTimer(g_hQueueTimer)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 251, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, LastError);
  }
  Blink = i->Blink;
  Flink = i->Flink;
  Blink->Flink = i->Flink;
  Flink->Blink = Blink;
  i->Flink = 0;
  i->Blink = 0;
  if ( !a2 )
    goto LABEL_41;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      252,
      &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
      LODWORD(i[2].Flink));
  }
  if ( (unsigned int)RemoveParentRecipients((struct _JOB_QUEUE *)i, v8) )
    goto LABEL_41;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 253, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v13);
LABEL_41:
    v12 = WPP_GLOBAL_Control;
  }
  if ( !i[3].Blink )
    goto LABEL_53;
  if ( v12 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 4) != 0 && *((_BYTE *)v12 + 25) >= 5u )
    WPP_SF_DS(
      *((_QWORD *)v12 + 2),
      254,
      (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
      i[2].Flink,
      (__int64)i[3].Blink);
  if ( DeleteFileW((LPCWSTR)i[3].Blink) )
    goto LABEL_52;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = GetLastError();
    WPP_SF_lSl(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      255,
      (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
      i[2].Flink,
      (__int64)i[3].Blink,
      v14);
LABEL_52:
    v12 = WPP_GLOBAL_Control;
  }
LABEL_53:
  if ( i[4].Blink )
  {
    if ( v12 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 4) != 0 && *((_BYTE *)v12 + 25) >= 5u )
      WPP_SF_DS(
        *((_QWORD *)v12 + 2),
        256,
        (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
        i[2].Flink,
        (__int64)i[4].Blink);
    if ( !DeleteFileW((LPCWSTR)i[4].Blink) )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_64;
      }
      v15 = GetLastError();
      WPP_SF_lSl(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        257,
        (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
        i[2].Flink,
        (__int64)i[4].Blink,
        v15);
    }
    v12 = WPP_GLOBAL_Control;
  }
LABEL_64:
  if ( i[11].Blink && !LODWORD(i[12].Flink) )
  {
    if ( v12 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 4) != 0 && *((_BYTE *)v12 + 25) >= 5u )
      WPP_SF_DS(
        *((_QWORD *)v12 + 2),
        258,
        (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
        i[2].Flink,
        (__int64)i[11].Blink);
    if ( !DeleteFileW((LPCWSTR)i[11].Blink)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = GetLastError();
      WPP_SF_lSl(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        259,
        (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
        i[2].Flink,
        (__int64)i[11].Blink,
        v16);
    }
  }
  SafeDecIdleCounter(&g_dwQueueCount);
  if ( a3
    && !CreateFaxEvent(0, 0x17u, (unsigned int)i[2].Flink, i[25].Blink)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v18 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 260, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v18);
  }
  FreeParentQueueEntry((struct _JOB_QUEUE *)i, v17);
  if ( !(unsigned int)StartJobQueueTimer()
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v19 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 261, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v19);
  }
LABEL_13:
  LeaveCriticalSection(&g_CsQueue);
  return 1;
}

```

## disassembly

```asm
0x14003ac78  push    rbx
0x14003ac7a  push    rbp
0x14003ac7b  push    rsi
0x14003ac7c  push    rdi
0x14003ac7d  push    r12
0x14003ac7f  push    r13
0x14003ac81  push    r15
0x14003ac83  sub     rsp, 30h
0x14003ac87  mov     ebp, r8d
0x14003ac8a  mov     esi, edx
0x14003ac8c  mov     rdi, rcx
0x14003ac8f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ac96  lea     r12, WPP_GLOBAL_Control
0x14003ac9d  lea     r13, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003aca4  mov     r15d, 4
0x14003acaa  cmp     rcx, r12
0x14003acad  jz      short loc_14003ACCC
0x14003acaf  test    [rcx+1Ch], r15b
0x14003acb3  jz      short loc_14003ACCC
0x14003acb5  cmp     byte ptr [rcx+19h], 5
0x14003acb9  jb      short loc_14003ACCC
0x14003acbb  mov     rcx, [rcx+10h]
0x14003acbf  mov     edx, 0F7h
0x14003acc4  mov     r8, r13
0x14003acc7  call    WPP_SF_
0x14003accc  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003acd3  call    cs:__imp_EnterCriticalSection
0x14003acd9  mov     rbx, cs:?g_QueueListHead@@3U_LIST_ENTRY@@A.Flink; _LIST_ENTRY g_QueueListHead ...
0x14003ace0  lea     rax, ?g_QueueListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_QueueListHead
0x14003ace7  jmp     short loc_14003ACF1
0x14003ace9  cmp     rbx, rdi
0x14003acec  jz      short loc_14003AD48
0x14003acee  mov     rbx, [rbx]
0x14003acf1  cmp     rbx, rax
0x14003acf4  jnz     short loc_14003ACE9
0x14003acf6  mov     rcx, cs:WPP_GLOBAL_Control
0x14003acfd  cmp     rcx, r12
0x14003ad00  jz      short loc_14003AD27
0x14003ad02  test    [rcx+1Ch], r15b
0x14003ad06  jz      short loc_14003AD27
0x14003ad08  cmp     byte ptr [rcx+19h], 3
0x14003ad0c  jb      short loc_14003AD27
0x14003ad0e  mov     r9d, [rdi+20h]
0x14003ad12  mov     edx, 0F8h
0x14003ad17  mov     rcx, [rcx+10h]
0x14003ad1b  mov     r8, r13
0x14003ad1e  mov     dword ptr [rsp+68h+var_48], edi
0x14003ad22  call    WPP_SF_dd
0x14003ad27  lea     rcx, ?g_CsQueue@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14003ad2e  call    cs:__imp_LeaveCriticalSection
0x14003ad34  mov     eax, 1
0x14003ad39  add     rsp, 30h
0x14003ad3d  pop     r15
0x14003ad3f  pop     r13
0x14003ad41  pop     r12
0x14003ad43  pop     rdi
0x14003ad44  pop     rsi
0x14003ad45  pop     rbp
0x14003ad46  pop     rbx
0x14003ad47  retn
0x14003ad48  test    rbx, rbx
0x14003ad4b  jz      short loc_14003ACF6
0x14003ad4d  mov     eax, [rbx+30h]
0x14003ad50  test    eax, eax
0x14003ad52  jz      short loc_14003AD87
0x14003ad54  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ad5b  cmp     rcx, r12
0x14003ad5e  jz      short loc_14003AD27
0x14003ad60  test    [rcx+1Ch], r15b
0x14003ad64  jz      short loc_14003AD27
0x14003ad66  cmp     byte ptr [rcx+19h], 3
0x14003ad6a  jb      short loc_14003AD27
0x14003ad6c  mov     r9d, [rbx+20h]
0x14003ad70  mov     edx, 0F9h
0x14003ad75  mov     rcx, [rcx+10h]
0x14003ad79  mov     r8, r13
0x14003ad7c  mov     dword ptr [rsp+68h+var_48], eax
0x14003ad80  call    WPP_SF_dd
0x14003ad85  jmp     short loc_14003AD27
0x14003ad87  cmp     dword ptr [rbx+34h], 0
0x14003ad8b  jbe     short loc_14003AD9A
0x14003ad8d  mov     edx, r15d; unsigned int
0x14003ad90  mov     rcx, rbx; this
0x14003ad93  call    ?PutStatus@_JOB_QUEUE@@QEAAXK@Z; _JOB_QUEUE::PutStatus(ulong)
0x14003ad98  jmp     short loc_14003AD27
0x14003ad9a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ada1  cmp     rcx, r12
0x14003ada4  jz      short loc_14003ADC7
0x14003ada6  test    [rcx+1Ch], r15b
0x14003adaa  jz      short loc_14003ADC7
0x14003adac  cmp     byte ptr [rcx+19h], 5
0x14003adb0  jb      short loc_14003ADC7
0x14003adb2  mov     r9d, [rbx+20h]
0x14003adb6  mov     edx, 0FAh
0x14003adbb  mov     rcx, [rcx+10h]
0x14003adbf  mov     r8, r13
0x14003adc2  call    WPP_SF_d
0x14003adc7  mov     rcx, cs:?g_hQueueTimer@@3PEAXEA; hTimer
0x14003adce  call    cs:__imp_CancelWaitableTimer
0x14003add4  mov     dil, 2
0x14003add7  test    eax, eax
0x14003add9  jnz     short loc_14003AE14
0x14003addb  mov     rax, cs:WPP_GLOBAL_Control
0x14003ade2  cmp     rax, r12
0x14003ade5  jz      short loc_14003AE14
0x14003ade7  test    [rax+1Ch], r15b
0x14003adeb  jz      short loc_14003AE14
0x14003aded  cmp     [rax+19h], dil
0x14003adf1  jb      short loc_14003AE14
0x14003adf3  call    cs:__imp_GetLastError
0x14003adf9  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ae00  mov     edx, 0FBh
0x14003ae05  mov     r9d, eax
0x14003ae08  mov     r8, r13
0x14003ae0b  mov     rcx, [rcx+10h]
0x14003ae0f  call    WPP_SF_d
0x14003ae14  mov     rax, [rbx+8]
0x14003ae18  mov     rcx, [rbx]
0x14003ae1b  mov     [rax], rcx
0x14003ae1e  mov     [rcx+8], rax
0x14003ae22  mov     qword ptr [rbx], 0
0x14003ae29  mov     qword ptr [rbx+8], 0
0x14003ae31  test    esi, esi
0x14003ae33  jz      short loc_14003AEA7
0x14003ae35  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ae3c  cmp     rcx, r12
0x14003ae3f  jz      short loc_14003AE62
0x14003ae41  test    [rcx+1Ch], r15b
0x14003ae45  jz      short loc_14003AE62
0x14003ae47  cmp     byte ptr [rcx+19h], 5
0x14003ae4b  jb      short loc_14003AE62
0x14003ae4d  mov     r9d, [rbx+20h]
0x14003ae51  mov     edx, 0FCh
0x14003ae56  mov     rcx, [rcx+10h]
0x14003ae5a  mov     r8, r13
0x14003ae5d  call    WPP_SF_d
0x14003ae62  mov     rcx, rbx; struct _JOB_QUEUE *
0x14003ae65  call    ?RemoveParentRecipients@@YAHPEAU_JOB_QUEUE@@H@Z; RemoveParentRecipients(_JOB_QUEUE *,int)
0x14003ae6a  test    eax, eax
0x14003ae6c  jnz     short loc_14003AEA7
0x14003ae6e  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ae75  cmp     rcx, r12
0x14003ae78  jz      short loc_14003AEAE
0x14003ae7a  test    [rcx+1Ch], r15b
0x14003ae7e  jz      short loc_14003AEAE
0x14003ae80  cmp     [rcx+19h], dil
0x14003ae84  jb      short loc_14003AEAE
0x14003ae86  call    cs:__imp_GetLastError
0x14003ae8c  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ae93  mov     edx, 0FDh
0x14003ae98  mov     r9d, eax
0x14003ae9b  mov     r8, r13
0x14003ae9e  mov     rcx, [rcx+10h]
0x14003aea2  call    WPP_SF_d
0x14003aea7  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aeae  mov     rax, [rbx+38h]
0x14003aeb2  test    rax, rax
0x14003aeb5  jz      loc_14003AF42
0x14003aebb  cmp     rcx, r12
0x14003aebe  jz      short loc_14003AEE6
0x14003aec0  test    [rcx+1Ch], r15b
0x14003aec4  jz      short loc_14003AEE6
0x14003aec6  cmp     byte ptr [rcx+19h], 5
0x14003aeca  jb      short loc_14003AEE6
0x14003aecc  mov     r9d, [rbx+20h]
0x14003aed0  mov     edx, 0FEh
0x14003aed5  mov     rcx, [rcx+10h]
0x14003aed9  mov     r8, r13
0x14003aedc  mov     [rsp+68h+var_48], rax
0x14003aee1  call    WPP_SF_DS
0x14003aee6  mov     rcx, [rbx+38h]; lpFileName
0x14003aeea  call    cs:__imp_DeleteFileW
0x14003aef0  test    eax, eax
0x14003aef2  jnz     short loc_14003AF3B
0x14003aef4  mov     rcx, cs:WPP_GLOBAL_Control
0x14003aefb  cmp     rcx, r12
0x14003aefe  jz      short loc_14003AF42
0x14003af00  test    [rcx+1Ch], r15b
0x14003af04  jz      short loc_14003AF42
0x14003af06  cmp     [rcx+19h], dil
0x14003af0a  jb      short loc_14003AF42
0x14003af0c  call    cs:__imp_GetLastError
0x14003af12  mov     rcx, cs:WPP_GLOBAL_Control
0x14003af19  mov     edx, 0FFh
0x14003af1e  mov     r9d, [rbx+20h]
0x14003af22  mov     r8, r13
0x14003af25  mov     [rsp+68h+var_40], eax
0x14003af29  mov     rax, [rbx+38h]
0x14003af2d  mov     rcx, [rcx+10h]
0x14003af31  mov     [rsp+68h+var_48], rax
0x14003af36  call    WPP_SF_lSl
0x14003af3b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003af42  mov     rax, [rbx+48h]
0x14003af46  test    rax, rax
0x14003af49  jz      loc_14003AFD6
0x14003af4f  cmp     rcx, r12
0x14003af52  jz      short loc_14003AF7A
0x14003af54  test    [rcx+1Ch], r15b
0x14003af58  jz      short loc_14003AF7A
0x14003af5a  cmp     byte ptr [rcx+19h], 5
0x14003af5e  jb      short loc_14003AF7A
0x14003af60  mov     r9d, [rbx+20h]
0x14003af64  mov     edx, 100h
0x14003af69  mov     rcx, [rcx+10h]
0x14003af6d  mov     r8, r13
0x14003af70  mov     [rsp+68h+var_48], rax
0x14003af75  call    WPP_SF_DS
0x14003af7a  mov     rcx, [rbx+48h]; lpFileName
0x14003af7e  call    cs:__imp_DeleteFileW
0x14003af84  test    eax, eax
0x14003af86  jnz     short loc_14003AFCF
0x14003af88  mov     rcx, cs:WPP_GLOBAL_Control
0x14003af8f  cmp     rcx, r12
0x14003af92  jz      short loc_14003AFD6
0x14003af94  test    [rcx+1Ch], r15b
0x14003af98  jz      short loc_14003AFD6
0x14003af9a  cmp     [rcx+19h], dil
0x14003af9e  jb      short loc_14003AFD6
0x14003afa0  call    cs:__imp_GetLastError
0x14003afa6  mov     rcx, cs:WPP_GLOBAL_Control
0x14003afad  mov     edx, 101h
0x14003afb2  mov     r9d, [rbx+20h]
0x14003afb6  mov     r8, r13
0x14003afb9  mov     [rsp+68h+var_40], eax
0x14003afbd  mov     rax, [rbx+48h]
0x14003afc1  mov     rcx, [rcx+10h]
0x14003afc5  mov     [rsp+68h+var_48], rax
0x14003afca  call    WPP_SF_lSl
0x14003afcf  mov     rcx, cs:WPP_GLOBAL_Control
0x14003afd6  mov     rax, [rbx+0B8h]
0x14003afdd  test    rax, rax
0x14003afe0  jz      loc_14003B079
0x14003afe6  cmp     dword ptr [rbx+0C0h], 0
0x14003afed  jnz     loc_14003B079
0x14003aff3  cmp     rcx, r12
0x14003aff6  jz      short loc_14003B01E
0x14003aff8  test    [rcx+1Ch], r15b
0x14003affc  jz      short loc_14003B01E
0x14003affe  cmp     byte ptr [rcx+19h], 5
0x14003b002  jb      short loc_14003B01E
0x14003b004  mov     r9d, [rbx+20h]
0x14003b008  mov     edx, 102h
0x14003b00d  mov     rcx, [rcx+10h]
0x14003b011  mov     r8, r13
0x14003b014  mov     [rsp+68h+var_48], rax
0x14003b019  call    WPP_SF_DS
0x14003b01e  mov     rcx, [rbx+0B8h]; lpFileName
0x14003b025  call    cs:__imp_DeleteFileW
0x14003b02b  test    eax, eax
0x14003b02d  jnz     short loc_14003B079
0x14003b02f  mov     rax, cs:WPP_GLOBAL_Control
0x14003b036  cmp     rax, r12
0x14003b039  jz      short loc_14003B079
0x14003b03b  test    [rax+1Ch], r15b
0x14003b03f  jz      short loc_14003B079
0x14003b041  cmp     [rax+19h], dil
0x14003b045  jb      short loc_14003B079
0x14003b047  call    cs:__imp_GetLastError
0x14003b04d  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b054  mov     edx, 103h
0x14003b059  mov     r9d, [rbx+20h]
0x14003b05d  mov     r8, r13
0x14003b060  mov     [rsp+68h+var_40], eax
0x14003b064  mov     rax, [rbx+0B8h]
0x14003b06b  mov     rcx, [rcx+10h]
0x14003b06f  mov     [rsp+68h+var_48], rax
0x14003b074  call    WPP_SF_lSl
0x14003b079  lea     rcx, ?g_dwQueueCount@@3KA; unsigned int *
0x14003b080  call    ?SafeDecIdleCounter@@YAXPEAK@Z; SafeDecIdleCounter(ulong *)
0x14003b085  test    ebp, ebp
0x14003b087  jz      short loc_14003B0DD
0x14003b089  mov     r9, [rbx+198h]; void *
0x14003b090  mov     edx, 17h; unsigned int
0x14003b095  mov     r8d, [rbx+20h]; unsigned int
0x14003b099  xor     ecx, ecx; unsigned int
0x14003b09b  call    ?CreateFaxEvent@@YAHKKKPEAX@Z; CreateFaxEvent(ulong,ulong,ulong,void *)
0x14003b0a0  test    eax, eax
0x14003b0a2  jnz     short loc_14003B0DD
0x14003b0a4  mov     rax, cs:WPP_GLOBAL_Control
0x14003b0ab  cmp     rax, r12
0x14003b0ae  jz      short loc_14003B0DD
0x14003b0b0  test    [rax+1Ch], r15b
0x14003b0b4  jz      short loc_14003B0DD
0x14003b0b6  cmp     [rax+19h], dil
0x14003b0ba  jb      short loc_14003B0DD
0x14003b0bc  call    cs:__imp_GetLastError
0x14003b0c2  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b0c9  mov     edx, 104h
0x14003b0ce  mov     r9d, eax
0x14003b0d1  mov     r8, r13
0x14003b0d4  mov     rcx, [rcx+10h]
0x14003b0d8  call    WPP_SF_d
0x14003b0dd  mov     rcx, rbx; this
0x14003b0e0  call    ?FreeParentQueueEntry@@YAXPEAU_JOB_QUEUE@@H@Z; FreeParentQueueEntry(_JOB_QUEUE *,int)
0x14003b0e5  call    ?StartJobQueueTimer@@YAHXZ; StartJobQueueTimer(void)
0x14003b0ea  test    eax, eax
0x14003b0ec  jnz     loc_14003AD27
0x14003b0f2  mov     rax, cs:WPP_GLOBAL_Control
0x14003b0f9  cmp     rax, r12
0x14003b0fc  jz      loc_14003AD27
  ... truncated ...
```
