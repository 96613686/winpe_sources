# HsmiFileCacheWriteCompletion

- ea: `0x14001c380`
- end: `0x14001c54e`
- name: `HsmiFileCacheWriteCompletion`
- size: `462`
- prototype: `void __stdcall(PFLT_CALLBACK_DATA CallbackData, PFLT_CONTEXT Context)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140003c50`
- `0x1400105c4`
- `0x14001c380`
- `0x14001ca24`
- `0x14001ca80`
- `0x14001ce90`
- `0x14001d094`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001c504`
- `ntoskrnl!IofCompleteRequest` at `0x14001c504`
- `FLTMGR!FltFreeCallbackData` at `0x14001c4d7`
- `FLTMGR!FltFreeCallbackData` at `0x14001c4d7`

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
  NTSTATUS v15; // [rsp+28h] [rbp-50h]

  Iopb = CallbackData->Iopb;
  ByteOffset = Iopb->Parameters.Read.ByteOffset;
  Length = Iopb->Parameters.Read.Length;
  Iopb->Parameters.Create.EaBuffer = 0;
  Status = CallbackData->IoStatus.Status;
  HsmDbgBreakOnStatus((unsigned int)Status);
  Information = CallbackData->IoStatus.Information;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    v15 = Status;
    WPP_SF_qqdD(WPP_GLOBAL_Control->AttachedDevice, v8, v9, CallbackData, Context);
  }
  if ( Status >= 0 )
  {
    if ( Status == 259 )
    {
      Status = -1073741595;
      HsmDbgBreakOnStatus(3221225701LL);
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
      HsmDbgBreakOnStatus(3221225701LL);
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
    WPP_SF_dD(WPP_GLOBAL_Control->AttachedDevice, 85, v14, v12, v13, v15);
  }
}

```

## disassembly

```asm
0x14001c380  push    rbx
0x14001c382  push    rbp
0x14001c383  push    rsi
0x14001c384  push    rdi
0x14001c385  push    r13
0x14001c387  push    r14
0x14001c389  push    r15
0x14001c38b  sub     rsp, 40h
0x14001c38f  mov     rax, [rcx+10h]
0x14001c393  mov     rsi, rcx
0x14001c396  mov     rdi, rdx
0x14001c399  mov     r15, [rax+28h]
0x14001c39d  mov     r14d, [rax+18h]
0x14001c3a1  mov     qword ptr [rax+38h], 0
0x14001c3a9  mov     ebx, [rcx+18h]
0x14001c3ac  mov     ecx, ebx
0x14001c3ae  call    HsmDbgBreakOnStatus
0x14001c3b3  mov     ebp, [rsi+20h]
0x14001c3b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c3bd  lea     r13, WPP_GLOBAL_Control
0x14001c3c4  cmp     rcx, r13
0x14001c3c7  jz      short loc_14001C3EF
0x14001c3c9  mov     eax, [rcx+2Ch]
0x14001c3cc  test    al, 8
0x14001c3ce  jz      short loc_14001C3EF
0x14001c3d0  cmp     byte ptr [rcx+29h], 5
0x14001c3d4  jb      short loc_14001C3EF
0x14001c3d6  mov     rcx, [rcx+18h]
0x14001c3da  mov     r9, rsi
0x14001c3dd  mov     [rsp+78h+var_48], ebp
0x14001c3e1  mov     [rsp+78h+var_50], ebx
0x14001c3e5  mov     [rsp+78h+var_58], rdi
0x14001c3ea  call    WPP_SF_qqdD
0x14001c3ef  test    ebx, ebx
0x14001c3f1  jns     short loc_14001C43C
0x14001c3f3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c3fa  cmp     rcx, r13
0x14001c3fd  jz      loc_14001C4D4
0x14001c403  mov     eax, [rcx+2Ch]
0x14001c406  test    al, 8
0x14001c408  jz      loc_14001C4D4
0x14001c40e  cmp     byte ptr [rcx+29h], 2
0x14001c412  jb      loc_14001C4D4
0x14001c418  mov     rcx, [rcx+18h]
0x14001c41c  mov     edx, 52h ; 'R'
0x14001c421  mov     [rsp+78h+var_48], ebx
0x14001c425  mov     r9, rsi
0x14001c428  mov     [rsp+78h+var_50], r14d
0x14001c42d  mov     [rsp+78h+var_58], r15
0x14001c432  call    WPP_SF_qiDd
0x14001c437  jmp     loc_14001C4D4
0x14001c43c  cmp     ebx, 103h
0x14001c442  jnz     short loc_14001C480
0x14001c444  mov     ecx, 0C00000E5h
0x14001c449  mov     ebx, ecx
0x14001c44b  call    HsmDbgBreakOnStatus
0x14001c450  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c457  cmp     rcx, r13
0x14001c45a  jz      short loc_14001C4D4
0x14001c45c  mov     eax, [rcx+2Ch]
0x14001c45f  test    al, 8
0x14001c461  jz      short loc_14001C4D4
0x14001c463  cmp     byte ptr [rcx+29h], 2
0x14001c467  jb      short loc_14001C4D4
0x14001c469  mov     rcx, [rcx+18h]
0x14001c46d  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001c474  mov     edx, 53h ; 'S'
0x14001c479  call    WPP_SF_
0x14001c47e  jmp     short loc_14001C4D4
0x14001c480  cmp     r14d, ebp
0x14001c483  jz      short loc_14001C4C6
0x14001c485  mov     ecx, 0C00000E5h
0x14001c48a  mov     ebx, ecx
0x14001c48c  call    HsmDbgBreakOnStatus
0x14001c491  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c498  cmp     rcx, r13
0x14001c49b  jz      short loc_14001C4D4
0x14001c49d  mov     eax, [rcx+2Ch]
0x14001c4a0  test    al, 8
0x14001c4a2  jz      short loc_14001C4D4
0x14001c4a4  cmp     byte ptr [rcx+29h], 2
0x14001c4a8  jb      short loc_14001C4D4
0x14001c4aa  mov     rcx, [rcx+18h]
0x14001c4ae  mov     edx, 54h ; 'T'
0x14001c4b3  mov     [rsp+78h+var_50], ebp
0x14001c4b7  mov     r9, r15
0x14001c4ba  mov     dword ptr [rsp+78h+var_58], r14d
0x14001c4bf  call    WPP_SF_iDDd
0x14001c4c4  jmp     short loc_14001C4D4
0x14001c4c6  mov     eax, [rsi+18h]
0x14001c4c9  mov     [rdi+30h], eax
0x14001c4cc  mov     rax, [rsi+20h]
0x14001c4d0  mov     [rdi+38h], rax
0x14001c4d4  mov     rcx, rsi; CallbackData
0x14001c4d7  call    cs:__imp_FltFreeCallbackData
0x14001c4de  nop     dword ptr [rax+rax+00h]
0x14001c4e3  test    ebx, ebx
0x14001c4e5  jns     short loc_14001C4F2
0x14001c4e7  mov     [rdi+30h], ebx
0x14001c4ea  mov     qword ptr [rdi+38h], 0
0x14001c4f2  mov     ebx, [rdi+30h]
0x14001c4f5  mov     ecx, ebx
0x14001c4f7  call    HsmDbgBreakOnStatus
0x14001c4fc  mov     esi, [rdi+38h]
0x14001c4ff  xor     edx, edx; PriorityBoost
0x14001c501  mov     rcx, rdi; Irp
0x14001c504  call    cs:__imp_IofCompleteRequest
0x14001c50b  nop     dword ptr [rax+rax+00h]
0x14001c510  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c517  cmp     rcx, r13
0x14001c51a  jz      short loc_14001C53E
0x14001c51c  mov     eax, [rcx+2Ch]
0x14001c51f  test    al, 8
0x14001c521  jz      short loc_14001C53E
0x14001c523  cmp     byte ptr [rcx+29h], 5
0x14001c527  jb      short loc_14001C53E
0x14001c529  mov     rcx, [rcx+18h]
0x14001c52d  mov     edx, 55h ; 'U'
0x14001c532  mov     r9d, ebx
0x14001c535  mov     dword ptr [rsp+78h+var_58], esi
0x14001c539  call    WPP_SF_dD
0x14001c53e  add     rsp, 40h
0x14001c542  pop     r15
0x14001c544  pop     r14
0x14001c546  pop     r13
0x14001c548  pop     rdi
0x14001c549  pop     rsi
0x14001c54a  pop     rbp
0x14001c54b  pop     rbx
0x14001c54c  retn
```
