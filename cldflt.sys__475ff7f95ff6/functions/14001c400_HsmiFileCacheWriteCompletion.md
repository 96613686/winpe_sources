# HsmiFileCacheWriteCompletion

- ea: `0x14001c400`
- end: `0x14001c5ce`
- name: `HsmiFileCacheWriteCompletion`
- size: `462`
- prototype: `void __fastcall(PFLT_CALLBACK_DATA CallbackData, _DWORD *Context)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140003c50`
- `0x140010644`
- `0x14001c400`
- `0x14001caa4`
- `0x14001cb00`
- `0x14001cf10`
- `0x14001d114`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001c584`
- `ntoskrnl!IofCompleteRequest` at `0x14001c584`
- `FLTMGR!FltFreeCallbackData` at `0x14001c557`
- `FLTMGR!FltFreeCallbackData` at `0x14001c557`

## pseudocode

```c
void __fastcall HsmiFileCacheWriteCompletion(PFLT_CALLBACK_DATA CallbackData, _DWORD *Context)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  LARGE_INTEGER ByteOffset; // r15
  ULONG Length; // r14d
  NTSTATUS Status; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  int Information; // ebp
  __int64 v11; // r8
  unsigned int v12; // ebx
  int v13; // esi
  __int64 v14; // r8

  Iopb = CallbackData->Iopb;
  ByteOffset = Iopb->Parameters.Read.ByteOffset;
  Length = Iopb->Parameters.Read.Length;
  Iopb->Parameters.Create.EaBuffer = 0;
  Status = CallbackData->IoStatus.Status;
  HsmDbgBreakOnStatus(Status);
  Information = CallbackData->IoStatus.Information;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qqdD(
      WPP_GLOBAL_Control->AttachedDevice,
      v8,
      v9,
      CallbackData,
      Context,
      Status,
      CallbackData->IoStatus.Information);
  }
  if ( Status >= 0 )
  {
    if ( Status == 259 )
    {
      Status = -1073741595;
      HsmDbgBreakOnStatus(-1073741595);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 83, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids);
      }
    }
    else if ( Length == Information )
    {
      Context[12] = CallbackData->IoStatus.Status;
      *((_QWORD *)Context + 7) = CallbackData->IoStatus.Information;
    }
    else
    {
      Status = -1073741595;
      HsmDbgBreakOnStatus(-1073741595);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))WPP_SF_iDDd)(
          WPP_GLOBAL_Control->AttachedDevice,
          84,
          v11,
          (LARGE_INTEGER)ByteOffset.QuadPart,
          Length,
          Information);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))WPP_SF_qiDd)(
      WPP_GLOBAL_Control->AttachedDevice,
      82,
      v9,
      CallbackData,
      (LARGE_INTEGER)ByteOffset.QuadPart,
      Length,
      Status);
  }
  FltFreeCallbackData(CallbackData);
  if ( Status < 0 )
  {
    Context[12] = Status;
    *((_QWORD *)Context + 7) = 0;
  }
  v12 = Context[12];
  HsmDbgBreakOnStatus(v12);
  v13 = Context[14];
  IofCompleteRequest((PIRP)Context, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_dD(WPP_GLOBAL_Control->AttachedDevice, 85, v14, v12, v13);
  }
}

```

## disassembly

```asm
0x14001c400  push    rbx
0x14001c402  push    rbp
0x14001c403  push    rsi
0x14001c404  push    rdi
0x14001c405  push    r13
0x14001c407  push    r14
0x14001c409  push    r15
0x14001c40b  sub     rsp, 40h
0x14001c40f  mov     rax, [rcx+10h]
0x14001c413  mov     rsi, rcx
0x14001c416  mov     rdi, rdx
0x14001c419  mov     r15, [rax+28h]
0x14001c41d  mov     r14d, [rax+18h]
0x14001c421  mov     qword ptr [rax+38h], 0
0x14001c429  mov     ebx, [rcx+18h]
0x14001c42c  mov     ecx, ebx
0x14001c42e  call    HsmDbgBreakOnStatus
0x14001c433  mov     ebp, [rsi+20h]
0x14001c436  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c43d  lea     r13, WPP_GLOBAL_Control
0x14001c444  cmp     rcx, r13
0x14001c447  jz      short loc_14001C46F
0x14001c449  mov     eax, [rcx+2Ch]
0x14001c44c  test    al, 8
0x14001c44e  jz      short loc_14001C46F
0x14001c450  cmp     byte ptr [rcx+29h], 5
0x14001c454  jb      short loc_14001C46F
0x14001c456  mov     rcx, [rcx+18h]
0x14001c45a  mov     r9, rsi
0x14001c45d  mov     [rsp+78h+var_48], ebp
0x14001c461  mov     [rsp+78h+var_50], ebx
0x14001c465  mov     [rsp+78h+var_58], rdi
0x14001c46a  call    WPP_SF_qqdD
0x14001c46f  test    ebx, ebx
0x14001c471  jns     short loc_14001C4BC
0x14001c473  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c47a  cmp     rcx, r13
0x14001c47d  jz      loc_14001C554
0x14001c483  mov     eax, [rcx+2Ch]
0x14001c486  test    al, 8
0x14001c488  jz      loc_14001C554
0x14001c48e  cmp     byte ptr [rcx+29h], 2
0x14001c492  jb      loc_14001C554
0x14001c498  mov     rcx, [rcx+18h]
0x14001c49c  mov     edx, 52h ; 'R'
0x14001c4a1  mov     [rsp+78h+var_48], ebx
0x14001c4a5  mov     r9, rsi
0x14001c4a8  mov     [rsp+78h+var_50], r14d
0x14001c4ad  mov     [rsp+78h+var_58], r15
0x14001c4b2  call    WPP_SF_qiDd
0x14001c4b7  jmp     loc_14001C554
0x14001c4bc  cmp     ebx, 103h
0x14001c4c2  jnz     short loc_14001C500
0x14001c4c4  mov     ecx, 0C00000E5h
0x14001c4c9  mov     ebx, ecx
0x14001c4cb  call    HsmDbgBreakOnStatus
0x14001c4d0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c4d7  cmp     rcx, r13
0x14001c4da  jz      short loc_14001C554
0x14001c4dc  mov     eax, [rcx+2Ch]
0x14001c4df  test    al, 8
0x14001c4e1  jz      short loc_14001C554
0x14001c4e3  cmp     byte ptr [rcx+29h], 2
0x14001c4e7  jb      short loc_14001C554
0x14001c4e9  mov     rcx, [rcx+18h]
0x14001c4ed  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001c4f4  mov     edx, 53h ; 'S'
0x14001c4f9  call    WPP_SF_
0x14001c4fe  jmp     short loc_14001C554
0x14001c500  cmp     r14d, ebp
0x14001c503  jz      short loc_14001C546
0x14001c505  mov     ecx, 0C00000E5h
0x14001c50a  mov     ebx, ecx
0x14001c50c  call    HsmDbgBreakOnStatus
0x14001c511  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c518  cmp     rcx, r13
0x14001c51b  jz      short loc_14001C554
0x14001c51d  mov     eax, [rcx+2Ch]
0x14001c520  test    al, 8
0x14001c522  jz      short loc_14001C554
0x14001c524  cmp     byte ptr [rcx+29h], 2
0x14001c528  jb      short loc_14001C554
0x14001c52a  mov     rcx, [rcx+18h]
0x14001c52e  mov     edx, 54h ; 'T'
0x14001c533  mov     [rsp+78h+var_50], ebp
0x14001c537  mov     r9, r15
0x14001c53a  mov     dword ptr [rsp+78h+var_58], r14d
0x14001c53f  call    WPP_SF_iDDd
0x14001c544  jmp     short loc_14001C554
0x14001c546  mov     eax, [rsi+18h]
0x14001c549  mov     [rdi+30h], eax
0x14001c54c  mov     rax, [rsi+20h]
0x14001c550  mov     [rdi+38h], rax
0x14001c554  mov     rcx, rsi; CallbackData
0x14001c557  call    cs:__imp_FltFreeCallbackData
0x14001c55e  nop     dword ptr [rax+rax+00h]
0x14001c563  test    ebx, ebx
0x14001c565  jns     short loc_14001C572
0x14001c567  mov     [rdi+30h], ebx
0x14001c56a  mov     qword ptr [rdi+38h], 0
0x14001c572  mov     ebx, [rdi+30h]
0x14001c575  mov     ecx, ebx
0x14001c577  call    HsmDbgBreakOnStatus
0x14001c57c  mov     esi, [rdi+38h]
0x14001c57f  xor     edx, edx; PriorityBoost
0x14001c581  mov     rcx, rdi; Irp
0x14001c584  call    cs:__imp_IofCompleteRequest
0x14001c58b  nop     dword ptr [rax+rax+00h]
0x14001c590  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c597  cmp     rcx, r13
0x14001c59a  jz      short loc_14001C5BE
0x14001c59c  mov     eax, [rcx+2Ch]
0x14001c59f  test    al, 8
0x14001c5a1  jz      short loc_14001C5BE
0x14001c5a3  cmp     byte ptr [rcx+29h], 5
0x14001c5a7  jb      short loc_14001C5BE
0x14001c5a9  mov     rcx, [rcx+18h]
0x14001c5ad  mov     edx, 55h ; 'U'
0x14001c5b2  mov     r9d, ebx
0x14001c5b5  mov     dword ptr [rsp+78h+var_58], esi
0x14001c5b9  call    WPP_SF_dD
0x14001c5be  add     rsp, 40h
0x14001c5c2  pop     r15
0x14001c5c4  pop     r14
0x14001c5c6  pop     r13
0x14001c5c8  pop     rdi
0x14001c5c9  pop     rsi
0x14001c5ca  pop     rbp
0x14001c5cb  pop     rbx
0x14001c5cc  retn
```
