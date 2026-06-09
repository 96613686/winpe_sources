# DasHostCompleteDevnodeOperation

- ea: `0x14000da80`
- end: `0x14000dbd9`
- name: `DasHostCompleteDevnodeOperation`
- size: `345`
- prototype: `__int64 __fastcall(RTL_SRWLOCK **, int, unsigned __int8 *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140008eec`
- `0x140008f88`
- `0x14000da80`
- `0x140019db0`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000dae1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000dae1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000db33`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000db33`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000db60`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000db60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000db74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000db74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000db66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000db66`

## pseudocode

```c
__int64 __fastcall DasHostCompleteDevnodeOperation(RTL_SRWLOCK **a1, int a2, unsigned __int8 *a3, int a4)
{
  RTL_SRWLOCK *v4; // r14
  unsigned int v8; // ebx
  RTL_SRWLOCK *Ptr; // rax
  RTL_SRWLOCK *v10; // rdi
  RTL_SRWLOCK *v11; // rcx
  RTL_SRWLOCK **v12; // rdx
  unsigned __int8 **v13; // rsi
  unsigned __int8 *v14; // rcx
  HANDLE ProcessHeap; // rax
  int v16; // edx
  int v17; // r8d
  int v19; // [rsp+28h] [rbp-60h]

  v4 = *a1;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      a2,
      (int)a3,
      24,
      &WPP_390cfc987846301e1004d86ef1b4fc88_Traceguids);
  (*((void (__fastcall **)(RTL_SRWLOCK *))v4->Ptr + 1))(v4);
  AcquireSRWLockExclusive(v4 + 12);
  v8 = 0;
  Ptr = (RTL_SRWLOCK *)v4[10].Ptr;
  if ( Ptr == &v4[10] )
  {
    v10 = 0;
  }
  else
  {
    while ( 1 )
    {
      v10 = Ptr;
      v11 = (RTL_SRWLOCK *)Ptr->Ptr;
      if ( HIDWORD(Ptr[2].Ptr) == a2 )
        break;
      v10 = 0;
      Ptr = (RTL_SRWLOCK *)Ptr->Ptr;
      if ( v11 == &v4[10] )
        goto LABEL_11;
    }
    if ( v11[1].Ptr != Ptr || (v12 = (RTL_SRWLOCK **)Ptr[1].Ptr, *v12 != Ptr) )
      __fastfail(3u);
    *v12 = v11;
    v11[1].Ptr = v12;
  }
LABEL_11:
  ReleaseSRWLockExclusive(v4 + 12);
  if ( v10 )
  {
    v13 = (unsigned __int8 **)v10[3].Ptr;
    if ( a4 >= 0 && a3 )
      a4 = MidlCopyString(a3, v13 + 6);
    v14 = v13[8];
    *((_DWORD *)v13 + 18) = a4;
    SetEvent(v14);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v10);
  }
  else
  {
    v8 = 1;
  }
  (*((void (__fastcall **)(RTL_SRWLOCK *))v4->Ptr + 2))(v4);
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v16,
      v17,
      25,
      &WPP_390cfc987846301e1004d86ef1b4fc88_Traceguids,
      v19,
      v8);
  return v8;
}

```

## disassembly

```asm
0x14000da80  push    rbx
0x14000da82  push    rbp
0x14000da83  push    rsi
0x14000da84  push    rdi
0x14000da85  push    r12
0x14000da87  push    r13
0x14000da89  push    r14
0x14000da8b  push    r15
0x14000da8d  sub     rsp, 48h
0x14000da91  mov     r14, [rcx]
0x14000da94  mov     ebp, r9d
0x14000da97  mov     r15, r8
0x14000da9a  mov     esi, edx
0x14000da9c  lea     rax, WPP_RECORDER_INITIALIZED
0x14000daa3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000daaa  lea     r13, WPP_390cfc987846301e1004d86ef1b4fc88_Traceguids
0x14000dab1  jz      short loc_14000DACE
0x14000dab3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000daba  mov     r9d, 18h; int
0x14000dac0  mov     [rsp+88h+MessageGuid], r13; MessageGuid
0x14000dac5  mov     rcx, [rcx+28h]; int
0x14000dac9  call    WPP_RECORDER_SF_s
0x14000dace  mov     rax, [r14]
0x14000dad1  mov     rcx, r14
0x14000dad4  mov     rax, [rax+8]
0x14000dad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dadd  lea     rcx, [r14+60h]; SRWLock
0x14000dae1  call    cs:__imp_AcquireSRWLockExclusive
0x14000dae7  lea     rdx, [r14+50h]
0x14000daeb  xor     ebx, ebx
0x14000daed  mov     rax, [rdx]
0x14000daf0  cmp     rax, rdx
0x14000daf3  jnz     short loc_14000DAF9
0x14000daf5  mov     edi, ebx
0x14000daf7  jmp     short loc_14000DB2F
0x14000daf9  mov     rdi, rax
0x14000dafc  mov     rcx, [rax]
0x14000daff  cmp     [rax+14h], esi
0x14000db02  jz      short loc_14000DB11
0x14000db04  mov     rdi, rbx
0x14000db07  mov     rax, rcx
0x14000db0a  cmp     rcx, rdx
0x14000db0d  jnz     short loc_14000DAF9
0x14000db0f  jmp     short loc_14000DB2F
0x14000db11  cmp     [rcx+8], rax
0x14000db15  jnz     loc_14000DBD2
0x14000db1b  mov     rdx, [rax+8]
0x14000db1f  cmp     [rdx], rax
0x14000db22  jnz     loc_14000DBD2
0x14000db28  mov     [rdx], rcx
0x14000db2b  mov     [rcx+8], rdx
0x14000db2f  lea     rcx, [r14+60h]; SRWLock
0x14000db33  call    cs:__imp_ReleaseSRWLockExclusive
0x14000db39  test    rdi, rdi
0x14000db3c  jz      short loc_14000DB7C
0x14000db3e  mov     rsi, [rdi+18h]
0x14000db42  test    ebp, ebp
0x14000db44  js      short loc_14000DB59
0x14000db46  test    r15, r15
0x14000db49  jz      short loc_14000DB59
0x14000db4b  lea     rdx, [rsi+30h]; unsigned __int16 **
0x14000db4f  mov     rcx, r15; unsigned __int16 *
0x14000db52  call    ?MidlCopyString@@YAJPEBGPEAPEAG@Z; MidlCopyString(ushort const *,ushort * *)
0x14000db57  mov     ebp, eax
0x14000db59  mov     rcx, [rsi+40h]; hEvent
0x14000db5d  mov     [rsi+48h], ebp
0x14000db60  call    cs:__imp_SetEvent
0x14000db66  call    cs:__imp_GetProcessHeap
0x14000db6c  mov     r8, rdi; lpMem
0x14000db6f  xor     edx, edx; dwFlags
0x14000db71  mov     rcx, rax; hHeap
0x14000db74  call    cs:__imp_HeapFree
0x14000db7a  jmp     short loc_14000DB81
0x14000db7c  mov     ebx, 1
0x14000db81  mov     rax, [r14]
0x14000db84  mov     rcx, r14
0x14000db87  mov     rax, [rax+10h]
0x14000db8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000db90  lea     rax, WPP_RECORDER_INITIALIZED
0x14000db97  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000db9e  jz      short loc_14000DBBF
0x14000dba0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dba7  mov     r9d, 19h; int
0x14000dbad  mov     dword ptr [rsp+88h+var_58], ebx; char
0x14000dbb1  mov     [rsp+88h+MessageGuid], r13; MessageGuid
0x14000dbb6  mov     rcx, [rcx+28h]; int
0x14000dbba  call    WPP_RECORDER_SF_sd
0x14000dbbf  mov     eax, ebx
0x14000dbc1  add     rsp, 48h
0x14000dbc5  pop     r15
0x14000dbc7  pop     r14
0x14000dbc9  pop     r13
0x14000dbcb  pop     r12
0x14000dbcd  pop     rdi
0x14000dbce  pop     rsi
0x14000dbcf  pop     rbp
0x14000dbd0  pop     rbx
0x14000dbd1  retn
0x14000dbd2  mov     ecx, 3
0x14000dbd7  int     29h; Win8: RtlFailFast(ecx)
```
