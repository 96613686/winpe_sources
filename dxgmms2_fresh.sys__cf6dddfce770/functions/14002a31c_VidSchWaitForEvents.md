# VidSchWaitForEvents

- ea: `0x14002a31c`
- end: `0x14002a50c`
- name: `VidSchWaitForEvents`
- size: `496`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14001eb70`
- `0x1400e6b60`
- `0x1400e6e24`
- `0x140109254`
- `0x1401098b0`
- `0x140109a00`
- `0x14010a1f0`

## callees

- `0x14002a31c`
- `0x14002a520`
- `0x1400e5280`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x14002a3f3`
- `ntoskrnl!KeReadStateEvent` at `0x14002a3f3`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14002a3ae`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14002a4a5`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14002a3ae`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14002a4a5`
- `ntoskrnl!PsIsThreadTerminating` at `0x14002a4c1`
- `ntoskrnl!PsIsThreadTerminating` at `0x14002a4c1`
- `ntoskrnl!KeSetEvent` at `0x14002a46c`
- `ntoskrnl!KeSetEvent` at `0x14002a46c`
- `watchdog!WdLogSingleEntry0` at `0x14002a4ef`
- `watchdog!WdLogSingleEntry0` at `0x14002a4ef`
- `dxgkrnl!g_TdrConfig` at `0x14002a35d`

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
      v16 = -(__int64)((10000000 * (unsigned __int64)(unsigned int)g_TdrConfig[1]) >> 1);
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
0x14002a31c  push    rbp
0x14002a31e  push    rsi
0x14002a31f  push    rdi
0x14002a320  push    r12
0x14002a322  push    r14
0x14002a324  push    r15
0x14002a326  sub     rsp, 58h
0x14002a32a  mov     rax, gs:188h
0x14002a333  mov     rbp, r9
0x14002a336  mov     r12, r8
0x14002a339  mov     r15d, edx
0x14002a33c  mov     rdi, rcx
0x14002a33f  cmp     rax, [rcx+0B8h]
0x14002a346  jnz     loc_14002A412
0x14002a34c  xor     r14b, r14b
0x14002a34f  mov     [rsp+88h+var_48], 0
0x14002a358  test    r9, r9
0x14002a35b  jnz     short loc_14002A381
0x14002a35d  mov     rax, cs:?g_TdrConfig@@3U_TDR_CONFIG@@C; _TDR_CONFIG volatile g_TdrConfig
0x14002a364  lea     rbp, [rsp+88h+var_48]
0x14002a369  mov     r14b, 1
0x14002a36c  mov     ecx, [rax+4]
0x14002a36f  imul    rcx, 989680h
0x14002a376  shr     rcx, 1
0x14002a379  neg     rcx
0x14002a37c  mov     [rsp+88h+var_48], rcx
0x14002a381  mov     [rsp+88h+arg_0], 0
0x14002a389  mov     [rsp+88h+WaitBlockArray], 0; WaitBlockArray
0x14002a392  xor     r9d, r9d; WaitReason
0x14002a395  mov     [rsp+88h+Timeout], rbp; Timeout
0x14002a39a  mov     rdx, r12; Object
0x14002a39d  mov     [rsp+88h+Alertable], 0; Alertable
0x14002a3a2  mov     ecx, r15d; Count
0x14002a3a5  mov     [rsp+88h+WaitMode], 0; WaitMode
0x14002a3aa  lea     r8d, [r9+1]; WaitType
0x14002a3ae  call    cs:__imp_KeWaitForMultipleObjects
0x14002a3b5  nop     dword ptr [rax+rax+00h]
0x14002a3ba  mov     esi, eax
0x14002a3bc  test    r14b, r14b
0x14002a3bf  jz      short loc_14002A40B
0x14002a3c1  cmp     eax, 102h
0x14002a3c6  jnz     short loc_14002A40B
0x14002a3c8  lea     rdx, [rsp+88h+arg_0]
0x14002a3d0  mov     rcx, rdi; struct _VIDSCH_GLOBAL *
0x14002a3d3  call    VidSchiCheckHwProgress
0x14002a3d8  test    eax, eax
0x14002a3da  jnz     short loc_14002A389
0x14002a3dc  cmp     esi, esi
0x14002a3de  jnz     short loc_14002A40B
0x14002a3e0  cmp     [rdi+0D0Ch], eax
0x14002a3e6  jz      short loc_14002A40B
0x14002a3e8  xor     edi, edi
0x14002a3ea  cmp     edi, r15d
0x14002a3ed  jnb     short loc_14002A40B
0x14002a3ef  mov     rcx, [r12+rdi*8]; Event
0x14002a3f3  call    cs:__imp_KeReadStateEvent
0x14002a3fa  nop     dword ptr [rax+rax+00h]
0x14002a3ff  test    eax, eax
0x14002a401  jnz     loc_14002A4D9
0x14002a407  inc     edi
0x14002a409  jmp     short loc_14002A3EA
0x14002a40b  mov     eax, esi
0x14002a40d  jmp     loc_14002A4DB
0x14002a412  mov     eax, [rcx+368h]
0x14002a418  test    eax, eax
0x14002a41a  jnz     short loc_14002A42F
0x14002a41c  mov     eax, [rcx+4Ch]
0x14002a41f  test    eax, eax
0x14002a421  jnz     short loc_14002A42F
0x14002a423  mov     eax, [rcx+50h]
0x14002a426  test    eax, eax
0x14002a428  jnz     short loc_14002A42F
0x14002a42a  xor     sil, sil
0x14002a42d  jmp     short loc_14002A432
0x14002a42f  mov     sil, 1
0x14002a432  xor     edx, edx
0x14002a434  call    VidSchiIsMmIoFlipPending
0x14002a439  mov     cl, [rdi+35Ch]
0x14002a43f  test    sil, sil
0x14002a442  jnz     short loc_14002A448
0x14002a444  test    al, al
0x14002a446  jz      short loc_14002A478
0x14002a448  test    cl, cl
0x14002a44a  jz      short loc_14002A478
0x14002a44c  mov     rax, 0FFFFF78000000320h
0x14002a456  lea     rcx, [rdi+6B0h]; Event
0x14002a45d  mov     r8b, 1; Wait
0x14002a460  xor     edx, edx; Increment
0x14002a462  mov     rax, [rax]
0x14002a465  mov     [rdi+6D0h], rax
0x14002a46c  call    cs:__imp_KeSetEvent
0x14002a473  nop     dword ptr [rax+rax+00h]
0x14002a478  mov     sil, [rsp+88h+arg_20]
0x14002a480  mov     [rsp+88h+WaitBlockArray], 0; WaitBlockArray
0x14002a489  xor     r9d, r9d; WaitReason
0x14002a48c  mov     [rsp+88h+Timeout], rbp; Timeout
0x14002a491  mov     rdx, r12; Object
0x14002a494  mov     [rsp+88h+Alertable], sil; Alertable
0x14002a499  mov     ecx, r15d; Count
0x14002a49c  mov     [rsp+88h+WaitMode], 0; WaitMode
0x14002a4a1  lea     r8d, [r9+1]; WaitType
0x14002a4a5  call    cs:__imp_KeWaitForMultipleObjects
0x14002a4ac  nop     dword ptr [rax+rax+00h]
0x14002a4b1  mov     edi, eax
0x14002a4b3  test    sil, sil
0x14002a4b6  jz      short loc_14002A4D1
0x14002a4b8  mov     rcx, gs:188h; Thread
0x14002a4c1  call    cs:__imp_PsIsThreadTerminating
0x14002a4c8  nop     dword ptr [rax+rax+00h]
0x14002a4cd  test    al, al
0x14002a4cf  jnz     short loc_14002A4EA
0x14002a4d1  cmp     edi, 101h
0x14002a4d7  jz      short loc_14002A480
0x14002a4d9  mov     eax, edi
0x14002a4db  add     rsp, 58h
0x14002a4df  pop     r15
0x14002a4e1  pop     r14
0x14002a4e3  pop     r12
0x14002a4e5  pop     rdi
0x14002a4e6  pop     rsi
0x14002a4e7  pop     rbp
0x14002a4e8  retn
0x14002a4ea  mov     ecx, 3
0x14002a4ef  call    cs:__imp_WdLogSingleEntry0
0x14002a4f6  nop     dword ptr [rax+rax+00h]
0x14002a4fb  mov     eax, 0C00002B6h
0x14002a500  mov     cs:WdLogGlobalForLineNumber, 22B5h
0x14002a50a  jmp     short loc_14002A4DB
```
