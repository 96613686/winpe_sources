# VidSchWaitForEvents

- ea: `0x14002d440`
- end: `0x14002d630`
- name: `VidSchWaitForEvents`
- size: `496`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400206d0`
- `0x1400de700`
- `0x1400de9c4`
- `0x140100154`
- `0x1401007b0`
- `0x140100900`
- `0x1401010f0`

## callees

- `0x14002d440`
- `0x14002d640`
- `0x1400dce20`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x14002d517`
- `ntoskrnl!KeReadStateEvent` at `0x14002d517`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14002d4d2`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14002d5c9`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14002d4d2`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14002d5c9`
- `ntoskrnl!PsIsThreadTerminating` at `0x14002d5e5`
- `ntoskrnl!PsIsThreadTerminating` at `0x14002d5e5`
- `ntoskrnl!KeSetEvent` at `0x14002d590`
- `ntoskrnl!KeSetEvent` at `0x14002d590`
- `watchdog!WdLogSingleEntry0` at `0x14002d613`
- `watchdog!WdLogSingleEntry0` at `0x14002d613`
- `dxgkrnl!g_TdrConfig` at `0x14002d481`

## pseudocode

```c
__int64 __fastcall VidSchWaitForEvents(
        struct _VIDSCH_GLOBAL *a1,
        ULONG Count,
        PVOID Object[],
        PLARGE_INTEGER Timeout,
        BOOLEAN Alertable)
{
  union _LARGE_INTEGER *v5; // rbp
  char v9; // r14
  NTSTATUS v10; // eax
  unsigned int v11; // esi
  __int64 i; // rdi
  __int64 result; // rax
  bool v14; // si
  char IsMmIoFlipPending; // al
  __int64 v16; // [rsp+40h] [rbp-48h] BYREF

  v5 = Timeout;
  if ( KeGetCurrentThread() == *((struct _KTHREAD **)a1 + 23) )
  {
    v9 = 0;
    v16 = 0;
    if ( !Timeout )
    {
      v5 = (union _LARGE_INTEGER *)&v16;
      v9 = 1;
      v16 = -(__int64)((10000000 * (unsigned __int64)g_TdrConfig[1]) >> 1);
    }
    while ( 1 )
    {
      v10 = KeWaitForMultipleObjects(Count, Object, WaitAny, Executive, 0, 0, v5, 0);
      v11 = v10;
      if ( !v9 || v10 != 258 )
        break;
      if ( !(unsigned int)VidSchiCheckHwProgress(a1) )
      {
        if ( *((_DWORD *)a1 + 835) )
        {
          for ( i = 0; (unsigned int)i < Count; i = (unsigned int)(i + 1) )
          {
            if ( KeReadStateEvent((PRKEVENT)Object[i]) )
              return (unsigned int)i;
          }
        }
        return v11;
      }
    }
    return v11;
  }
  else
  {
    v14 = *((_DWORD *)a1 + 218) || *((_DWORD *)a1 + 19) || *((_DWORD *)a1 + 20);
    IsMmIoFlipPending = VidSchiIsMmIoFlipPending(a1, 0);
    if ( (v14 || IsMmIoFlipPending) && *((_BYTE *)a1 + 860) )
    {
      *((_QWORD *)a1 + 218) = MEMORY[0xFFFFF78000000320];
      KeSetEvent((PRKEVENT)((char *)a1 + 1712), 0, 1u);
    }
    while ( 1 )
    {
      LODWORD(i) = KeWaitForMultipleObjects(Count, Object, WaitAny, Executive, 0, Alertable, v5, 0);
      if ( Alertable )
      {
        if ( PsIsThreadTerminating(KeGetCurrentThread()) )
          break;
      }
      if ( (_DWORD)i != 257 )
        return (unsigned int)i;
    }
    WdLogSingleEntry0(3);
    result = 3221226166LL;
    WdLogGlobalForLineNumber = 8885;
  }
  return result;
}

```

## disassembly

```asm
0x14002d440  push    rbp
0x14002d442  push    rsi
0x14002d443  push    rdi
0x14002d444  push    r12
0x14002d446  push    r14
0x14002d448  push    r15
0x14002d44a  sub     rsp, 58h
0x14002d44e  mov     rax, gs:188h
0x14002d457  mov     rbp, r9
0x14002d45a  mov     r12, r8
0x14002d45d  mov     r15d, edx
0x14002d460  mov     rdi, rcx
0x14002d463  cmp     rax, [rcx+0B8h]
0x14002d46a  jnz     loc_14002D536
0x14002d470  xor     r14b, r14b
0x14002d473  mov     [rsp+88h+var_48], 0
0x14002d47c  test    r9, r9
0x14002d47f  jnz     short loc_14002D4A5
0x14002d481  mov     rax, cs:?g_TdrConfig@@3U_TDR_CONFIG@@C; _TDR_CONFIG volatile g_TdrConfig
0x14002d488  lea     rbp, [rsp+88h+var_48]
0x14002d48d  mov     r14b, 1
0x14002d490  mov     ecx, [rax+4]
0x14002d493  imul    rcx, 989680h
0x14002d49a  shr     rcx, 1
0x14002d49d  neg     rcx
0x14002d4a0  mov     [rsp+88h+var_48], rcx
0x14002d4a5  mov     [rsp+88h+arg_0], 0
0x14002d4ad  mov     [rsp+88h+WaitBlockArray], 0; WaitBlockArray
0x14002d4b6  xor     r9d, r9d; WaitReason
0x14002d4b9  mov     [rsp+88h+Timeout], rbp; Timeout
0x14002d4be  mov     rdx, r12; Object
0x14002d4c1  mov     [rsp+88h+Alertable], 0; Alertable
0x14002d4c6  mov     ecx, r15d; Count
0x14002d4c9  mov     [rsp+88h+WaitMode], 0; WaitMode
0x14002d4ce  lea     r8d, [r9+1]; WaitType
0x14002d4d2  call    cs:__imp_KeWaitForMultipleObjects
0x14002d4d9  nop     dword ptr [rax+rax+00h]
0x14002d4de  mov     esi, eax
0x14002d4e0  test    r14b, r14b
0x14002d4e3  jz      short loc_14002D52F
0x14002d4e5  cmp     eax, 102h
0x14002d4ea  jnz     short loc_14002D52F
0x14002d4ec  lea     rdx, [rsp+88h+arg_0]
0x14002d4f4  mov     rcx, rdi; struct _VIDSCH_GLOBAL *
0x14002d4f7  call    VidSchiCheckHwProgress
0x14002d4fc  test    eax, eax
0x14002d4fe  jnz     short loc_14002D4AD
0x14002d500  cmp     esi, esi
0x14002d502  jnz     short loc_14002D52F
0x14002d504  cmp     [rdi+0D0Ch], eax
0x14002d50a  jz      short loc_14002D52F
0x14002d50c  xor     edi, edi
0x14002d50e  cmp     edi, r15d
0x14002d511  jnb     short loc_14002D52F
0x14002d513  mov     rcx, [r12+rdi*8]; Event
0x14002d517  call    cs:__imp_KeReadStateEvent
0x14002d51e  nop     dword ptr [rax+rax+00h]
0x14002d523  test    eax, eax
0x14002d525  jnz     loc_14002D5FD
0x14002d52b  inc     edi
0x14002d52d  jmp     short loc_14002D50E
0x14002d52f  mov     eax, esi
0x14002d531  jmp     loc_14002D5FF
0x14002d536  mov     eax, [rcx+368h]
0x14002d53c  test    eax, eax
0x14002d53e  jnz     short loc_14002D553
0x14002d540  mov     eax, [rcx+4Ch]
0x14002d543  test    eax, eax
0x14002d545  jnz     short loc_14002D553
0x14002d547  mov     eax, [rcx+50h]
0x14002d54a  test    eax, eax
0x14002d54c  jnz     short loc_14002D553
0x14002d54e  xor     sil, sil
0x14002d551  jmp     short loc_14002D556
0x14002d553  mov     sil, 1
0x14002d556  xor     edx, edx
0x14002d558  call    VidSchiIsMmIoFlipPending
0x14002d55d  mov     cl, [rdi+35Ch]
0x14002d563  test    sil, sil
0x14002d566  jnz     short loc_14002D56C
0x14002d568  test    al, al
0x14002d56a  jz      short loc_14002D59C
0x14002d56c  test    cl, cl
0x14002d56e  jz      short loc_14002D59C
0x14002d570  mov     rax, 0FFFFF78000000320h
0x14002d57a  lea     rcx, [rdi+6B0h]; Event
0x14002d581  mov     r8b, 1; Wait
0x14002d584  xor     edx, edx; Increment
0x14002d586  mov     rax, [rax]
0x14002d589  mov     [rdi+6D0h], rax
0x14002d590  call    cs:__imp_KeSetEvent
0x14002d597  nop     dword ptr [rax+rax+00h]
0x14002d59c  mov     sil, [rsp+88h+arg_20]
0x14002d5a4  mov     [rsp+88h+WaitBlockArray], 0; WaitBlockArray
0x14002d5ad  xor     r9d, r9d; WaitReason
0x14002d5b0  mov     [rsp+88h+Timeout], rbp; Timeout
0x14002d5b5  mov     rdx, r12; Object
0x14002d5b8  mov     [rsp+88h+Alertable], sil; Alertable
0x14002d5bd  mov     ecx, r15d; Count
0x14002d5c0  mov     [rsp+88h+WaitMode], 0; WaitMode
0x14002d5c5  lea     r8d, [r9+1]; WaitType
0x14002d5c9  call    cs:__imp_KeWaitForMultipleObjects
0x14002d5d0  nop     dword ptr [rax+rax+00h]
0x14002d5d5  mov     edi, eax
0x14002d5d7  test    sil, sil
0x14002d5da  jz      short loc_14002D5F5
0x14002d5dc  mov     rcx, gs:188h; Thread
0x14002d5e5  call    cs:__imp_PsIsThreadTerminating
0x14002d5ec  nop     dword ptr [rax+rax+00h]
0x14002d5f1  test    al, al
0x14002d5f3  jnz     short loc_14002D60E
0x14002d5f5  cmp     edi, 101h
0x14002d5fb  jz      short loc_14002D5A4
0x14002d5fd  mov     eax, edi
0x14002d5ff  add     rsp, 58h
0x14002d603  pop     r15
0x14002d605  pop     r14
0x14002d607  pop     r12
0x14002d609  pop     rdi
0x14002d60a  pop     rsi
0x14002d60b  pop     rbp
0x14002d60c  retn
0x14002d60e  mov     ecx, 3
0x14002d613  call    cs:__imp_WdLogSingleEntry0
0x14002d61a  nop     dword ptr [rax+rax+00h]
0x14002d61f  mov     eax, 0C00002B6h
0x14002d624  mov     cs:WdLogGlobalForLineNumber, 22B5h
0x14002d62e  jmp     short loc_14002D5FF
```
