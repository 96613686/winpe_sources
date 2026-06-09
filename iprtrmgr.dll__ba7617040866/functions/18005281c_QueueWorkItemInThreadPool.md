# QueueWorkItemInThreadPool

- ea: `0x18005281c`
- end: `0x180052951`
- name: `QueueWorkItemInThreadPool`
- size: `309`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180010260`
- `0x1800106a0`

## callees

- `0x18000ac60`
- `0x18005281c`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!CreateThreadpoolWork` at `0x18005289a`
- `KERNEL32!CreateThreadpoolWork` at `0x18005289a`
- `KERNEL32!SubmitThreadpoolWork` at `0x1800528fc`
- `KERNEL32!SubmitThreadpoolWork` at `0x1800528fc`
- `KERNEL32!CloseThreadpoolWork` at `0x180052905`
- `KERNEL32!CloseThreadpoolWork` at `0x180052905`
- `KERNEL32!GetLastError` at `0x1800528a8`
- `KERNEL32!GetLastError` at `0x1800528a8`

## string_xrefs

- `0x180052866`: `QueueWorkItemInThreadPool`
- `0x1800528bb`: `QueueWorkItemInThreadPool: CreateThreadPoolWork failed with error = %d`
- `0x180052914`: `Leaving: QueueWorkItemInThreadPool`

## pseudocode

```c
__int64 __fastcall QueueWorkItemInThreadPool(__int64 a1, __int64 a2, void *a3)
{
  char *v3; // rbx
  unsigned int v5; // ebx
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v7; // rdi
  DWORD LastError; // eax
  int v10; // [rsp+30h] [rbp-818h] BYREF
  _BYTE v11[2044]; // [rsp+34h] [rbp-814h] BYREF

  v3 = (char *)g_hDDEventThreadPool;
  v10 = 0;
  memset_0(v11, 0, sizeof(v11));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"QueueWorkItemInThreadPool");
  if ( v3 )
  {
    ThreadpoolWork = CreateThreadpoolWork(HandleDemandDialEvent, a3, (PTP_CALLBACK_ENVIRON)(v3 + 16));
    v7 = ThreadpoolWork;
    if ( ThreadpoolWork )
    {
      v5 = 0;
      SubmitThreadpoolWork(ThreadpoolWork);
      CloseThreadpoolWork(v7);
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v10) = 0;
        FormatRRASErrorString(
          &v10,
          L"QueueWorkItemInThreadPool: CreateThreadPoolWork failed with error = %d",
          LastError);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v10);
      }
    }
  }
  else
  {
    v5 = 87;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"Leaving: QueueWorkItemInThreadPool");
  return v5;
}

```

## disassembly

```asm
0x18005281c  mov     [rsp+arg_0], rbx
0x180052821  push    rdi
0x180052822  sub     rsp, 840h
0x180052829  mov     rax, cs:__security_cookie
0x180052830  xor     rax, rsp
0x180052833  mov     [rsp+848h+var_18], rax
0x18005283b  mov     rbx, cs:g_hDDEventThreadPool
0x180052842  lea     rcx, [rsp+848h+var_814]; void *
0x180052847  mov     rdi, r8
0x18005284a  xor     eax, eax
0x18005284c  mov     r8d, 7FCh; Size
0x180052852  mov     [rsp+848h+var_818], eax
0x180052856  xor     edx, edx; Val
0x180052858  call    memset_0
0x18005285d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180052864  jz      short loc_180052880
0x180052866  lea     r8, aQueueworkitemi; "QueueWorkItemInThreadPool"
0x18005286d  lea     rdx, RasRtrmgrTraceInfo
0x180052874  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18005287b  call    McTemplateU0z_EventWriteTransfer
0x180052880  test    rbx, rbx
0x180052883  jnz     short loc_18005288C
0x180052885  mov     ebx, 57h ; 'W'
0x18005288a  jmp     short loc_18005290B
0x18005288c  lea     r8, [rbx+10h]; pcbe
0x180052890  mov     rdx, rdi; pv
0x180052893  lea     rcx, HandleDemandDialEvent; pfnwk
0x18005289a  call    cs:__imp_CreateThreadpoolWork
0x1800528a0  mov     rdi, rax
0x1800528a3  test    rax, rax
0x1800528a6  jnz     short loc_1800528F7
0x1800528a8  call    cs:__imp_GetLastError
0x1800528ae  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800528b5  mov     ebx, eax
0x1800528b7  jz      short loc_18005290B
0x1800528b9  xor     ecx, ecx
0x1800528bb  lea     rdx, aQueueworkitemi_0; "QueueWorkItemInThreadPool: CreateThread"...
0x1800528c2  mov     word ptr [rsp+848h+var_818], cx
0x1800528c7  mov     r8d, eax
0x1800528ca  lea     rcx, [rsp+848h+var_818]
0x1800528cf  call    FormatRRASErrorString
0x1800528d4  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800528db  jz      short loc_18005290B
0x1800528dd  lea     r8, [rsp+848h+var_818]
0x1800528e2  lea     rdx, RasRtrMgrTraceError
0x1800528e9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800528f0  call    McTemplateU0z_EventWriteTransfer
0x1800528f5  jmp     short loc_18005290B
0x1800528f7  mov     rcx, rdi; pwk
0x1800528fa  xor     ebx, ebx
0x1800528fc  call    cs:__imp_SubmitThreadpoolWork
0x180052902  mov     rcx, rdi; pwk
0x180052905  call    cs:__imp_CloseThreadpoolWork
0x18005290b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180052912  jz      short loc_18005292E
0x180052914  lea     r8, aLeavingQueuewo; "Leaving: QueueWorkItemInThreadPool"
0x18005291b  lea     rdx, RasRtrmgrTraceInfo
0x180052922  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180052929  call    McTemplateU0z_EventWriteTransfer
0x18005292e  mov     eax, ebx
0x180052930  mov     rcx, [rsp+848h+var_18]
0x180052938  xor     rcx, rsp; StackCookie
0x18005293b  call    __security_check_cookie
0x180052940  mov     rbx, [rsp+848h+arg_0]
0x180052948  add     rsp, 840h
0x18005294f  pop     rdi
0x180052950  retn
```
