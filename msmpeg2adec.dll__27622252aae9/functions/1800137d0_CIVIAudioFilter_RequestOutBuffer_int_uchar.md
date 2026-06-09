# CIVIAudioFilter::RequestOutBuffer(int,uchar * *)

- ea: `0x1800137d0`
- end: `0x180013a39`
- name: `?RequestOutBuffer@CIVIAudioFilter@@MEAAJHPEAPEAE@Z`
- size: `617`
- prototype: `__int64 __fastcall(CIVIAudioFilter *__hidden this, int, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800137d0`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013837`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800138af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800138fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013837`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800138af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800138fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013805`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001387e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800138cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013805`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001387e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800138cc`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180013827`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001389f`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800138ed`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180013827`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001389f`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800138ed`

## pseudocode

```c
__int64 __fastcall CIVIAudioFilter::RequestOutBuffer(struct _RTL_CRITICAL_SECTION *this, int a2, unsigned __int8 **a3)
{
  HANDLE *p_LockSemaphore; // rbx
  int v7; // ebp
  __int64 result; // rax
  unsigned int v9; // r14d
  ULONG_PTR SpinCount; // rbx
  int v11; // eax
  _BYTE *v12; // rcx
  struct _RTL_CRITICAL_SECTION *v13; // rdi
  unsigned int v14; // ebx
  int v15; // eax
  char *v16; // rcx
  int DebugInfo; // ecx
  _BYTE *v18; // [rsp+80h] [rbp+8h] BYREF

  if ( this[408].SpinCount )
  {
    DebugInfo = (int)this[410].DebugInfo;
    if ( DebugInfo + a2 > SHIDWORD(this[410].DebugInfo) )
      return 2147745795LL;
    v13 = this + 409;
    v14 = 0;
    v7 = DebugInfo;
    goto LABEL_30;
  }
  p_LockSemaphore = &this->LockSemaphore;
  if ( this != (struct _RTL_CRITICAL_SECTION *)-24LL )
  {
    EnterCriticalSection(this + 1);
    if ( !*(_DWORD *)p_LockSemaphore )
      EventWrite((REGHANDLE)p_LockSemaphore[1], &MSMPEG2ADEC_GETOUTPUT_START, 0, 0);
    LeaveCriticalSection((LPCRITICAL_SECTION)(p_LockSemaphore + 2));
  }
  v7 = 0;
  result = (*(__int64 (__fastcall **)(ULONG_PTR, ULONG_PTR *, _QWORD, _QWORD, _DWORD))(*(_QWORD *)this[-1].SpinCount
                                                                                     + 128LL))(
             this[-1].SpinCount,
             &this[408].SpinCount,
             0,
             0,
             0);
  v9 = result;
  if ( (int)result < 0 )
  {
    if ( p_LockSemaphore )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(p_LockSemaphore + 2));
      if ( !*(_DWORD *)p_LockSemaphore )
        EventWrite((REGHANDLE)p_LockSemaphore[1], &MSMPEG2ADEC_GETOUTPUT_ERROR, 0, 0);
      LeaveCriticalSection((LPCRITICAL_SECTION)(p_LockSemaphore + 2));
      return v9;
    }
    return result;
  }
  if ( p_LockSemaphore )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(p_LockSemaphore + 2));
    if ( !*(_DWORD *)p_LockSemaphore )
      EventWrite((REGHANDLE)p_LockSemaphore[1], &MSMPEG2ADEC_GETOUTPUT_STOP, 0, 0);
    LeaveCriticalSection((LPCRITICAL_SECTION)(p_LockSemaphore + 2));
  }
  SpinCount = this[408].SpinCount;
  v18 = 0;
  if ( !SpinCount )
    return 2147942487LL;
  result = (*(__int64 (__fastcall **)(ULONG_PTR, _BYTE **))(*(_QWORD *)SpinCount + 24LL))(SpinCount, &v18);
  if ( (int)result >= 0 )
  {
    if ( !v18
      || (v11 = (*(__int64 (__fastcall **)(ULONG_PTR))(*(_QWORD *)SpinCount + 32LL))(SpinCount)) == 0
      || ((v12 = v18) == 0 || v11 <= 0 ? (result = 2147942487LL) : (*v18 = 0, v12[v11 - 1] = 0, result = 0),
          (int)result >= 0) )
    {
      v13 = this + 409;
      result = (*(__int64 (__fastcall **)(ULONG_PTR, struct _RTL_CRITICAL_SECTION *))(*(_QWORD *)this[408].SpinCount
                                                                                    + 24LL))(
                 this[408].SpinCount,
                 this + 409);
      v14 = result;
      if ( (int)result >= 0 )
      {
        v15 = (*(__int64 (__fastcall **)(ULONG_PTR))(*(_QWORD *)this[408].SpinCount + 32LL))(this[408].SpinCount);
        v16 = (char *)this[8].LockSemaphore + (unsigned __int64)this[380].LockSemaphore;
        HIDWORD(this[410].DebugInfo) = v15;
        *(_QWORD *)&this[409].LockCount = v16;
        this[409].OwningThread = 0;
        LODWORD(this[410].DebugInfo) = 0;
        if ( a2 > v15 )
          return 2147745795LL;
LABEL_30:
        *a3 = (unsigned __int8 *)v13->DebugInfo + v7;
        return v14;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800137d0  push    rbx
0x1800137d2  push    rbp
0x1800137d3  push    rsi
0x1800137d4  push    rdi
0x1800137d5  push    r12
0x1800137d7  push    r13
0x1800137d9  push    r14
0x1800137db  push    r15
0x1800137dd  sub     rsp, 38h
0x1800137e1  cmp     qword ptr [rcx+3FE0h], 0
0x1800137e9  mov     r13, r8
0x1800137ec  mov     r12d, edx
0x1800137ef  mov     rsi, rcx
0x1800137f2  jnz     loc_1800139FD
0x1800137f8  lea     rbx, [rcx+18h]
0x1800137fc  test    rbx, rbx
0x1800137ff  jz      short loc_180013843
0x180013801  lea     rcx, [rbx+10h]; lpCriticalSection
0x180013805  call    cs:__imp_EnterCriticalSection
0x18001380c  nop     dword ptr [rax+rax+00h]
0x180013811  cmp     dword ptr [rbx], 0
0x180013814  jnz     short loc_180013833
0x180013816  mov     rcx, [rbx+8]; RegHandle
0x18001381a  lea     rdx, MSMPEG2ADEC_GETOUTPUT_START; EventDescriptor
0x180013821  xor     r9d, r9d; UserData
0x180013824  xor     r8d, r8d; UserDataCount
0x180013827  call    cs:__imp_EventWrite
0x18001382e  nop     dword ptr [rax+rax+00h]
0x180013833  lea     rcx, [rbx+10h]; lpCriticalSection
0x180013837  call    cs:__imp_LeaveCriticalSection
0x18001383e  nop     dword ptr [rax+rax+00h]
0x180013843  mov     rcx, [rsi-8]
0x180013847  lea     rdx, [rsi+3FE0h]
0x18001384e  xor     ebp, ebp
0x180013850  xor     r9d, r9d
0x180013853  xor     r8d, r8d
0x180013856  mov     [rsp+78h+var_58], ebp
0x18001385a  mov     rax, [rcx]
0x18001385d  mov     rax, [rax+80h]
0x180013864  call    cs:__guard_dispatch_icall_fptr
0x18001386a  mov     r14d, eax
0x18001386d  test    eax, eax
0x18001386f  jns     short loc_1800138C3
0x180013871  test    rbx, rbx
0x180013874  jz      loc_180013A27
0x18001387a  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001387e  call    cs:__imp_EnterCriticalSection
0x180013885  nop     dword ptr [rax+rax+00h]
0x18001388a  cmp     [rbx], ebp
0x18001388c  jnz     short loc_1800138AB
0x18001388e  mov     rcx, [rbx+8]; RegHandle
0x180013892  lea     rdx, MSMPEG2ADEC_GETOUTPUT_ERROR; EventDescriptor
0x180013899  xor     r9d, r9d; UserData
0x18001389c  xor     r8d, r8d; UserDataCount
0x18001389f  call    cs:__imp_EventWrite
0x1800138a6  nop     dword ptr [rax+rax+00h]
0x1800138ab  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800138af  call    cs:__imp_LeaveCriticalSection
0x1800138b6  nop     dword ptr [rax+rax+00h]
0x1800138bb  mov     eax, r14d
0x1800138be  jmp     loc_180013A27
0x1800138c3  test    rbx, rbx
0x1800138c6  jz      short loc_180013909
0x1800138c8  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800138cc  call    cs:__imp_EnterCriticalSection
0x1800138d3  nop     dword ptr [rax+rax+00h]
0x1800138d8  cmp     [rbx], ebp
0x1800138da  jnz     short loc_1800138F9
0x1800138dc  mov     rcx, [rbx+8]; RegHandle
0x1800138e0  lea     rdx, MSMPEG2ADEC_GETOUTPUT_STOP; EventDescriptor
0x1800138e7  xor     r9d, r9d; UserData
0x1800138ea  xor     r8d, r8d; UserDataCount
0x1800138ed  call    cs:__imp_EventWrite
0x1800138f4  nop     dword ptr [rax+rax+00h]
0x1800138f9  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800138fd  call    cs:__imp_LeaveCriticalSection
0x180013904  nop     dword ptr [rax+rax+00h]
0x180013909  mov     rbx, [rsi+3FE0h]
0x180013910  mov     [rsp+78h+arg_0], rbp
0x180013918  test    rbx, rbx
0x18001391b  jnz     short loc_180013927
0x18001391d  mov     eax, 80070057h
0x180013922  jmp     loc_180013A27
0x180013927  mov     rax, [rbx]
0x18001392a  lea     rdx, [rsp+78h+arg_0]
0x180013932  mov     rcx, rbx
0x180013935  mov     rax, [rax+18h]
0x180013939  call    cs:__guard_dispatch_icall_fptr
0x18001393f  test    eax, eax
0x180013941  js      loc_180013A27
0x180013947  cmp     [rsp+78h+arg_0], rbp
0x18001394f  jz      short loc_180013991
0x180013951  mov     rax, [rbx]
0x180013954  mov     rcx, rbx
0x180013957  mov     rax, [rax+20h]
0x18001395b  call    cs:__guard_dispatch_icall_fptr
0x180013961  test    eax, eax
0x180013963  jz      short loc_180013991
0x180013965  mov     rcx, [rsp+78h+arg_0]
0x18001396d  test    rcx, rcx
0x180013970  jz      short loc_180013984
0x180013972  test    eax, eax
0x180013974  jle     short loc_180013984
0x180013976  cdqe
0x180013978  mov     [rcx], bpl
0x18001397b  mov     [rax+rcx-1], bpl
0x180013980  mov     eax, ebp
0x180013982  jmp     short loc_180013989
0x180013984  mov     eax, 80070057h
0x180013989  test    eax, eax
0x18001398b  js      loc_180013A27
0x180013991  mov     rcx, [rsi+3FE0h]
0x180013998  lea     rdi, [rsi+3FE8h]
0x18001399f  mov     rdx, rdi
0x1800139a2  mov     rax, [rcx]
0x1800139a5  mov     rax, [rax+18h]
0x1800139a9  call    cs:__guard_dispatch_icall_fptr
0x1800139af  mov     ebx, eax
0x1800139b1  test    eax, eax
0x1800139b3  js      short loc_180013A27
0x1800139b5  mov     rcx, [rsi+3FE0h]
0x1800139bc  mov     rdx, [rcx]
0x1800139bf  mov     rax, [rdx+20h]
0x1800139c3  call    cs:__guard_dispatch_icall_fptr
0x1800139c9  mov     rcx, [rsi+3B78h]
0x1800139d0  add     rcx, [rsi+158h]
0x1800139d7  mov     [rsi+4014h], eax
0x1800139dd  mov     [rsi+3FF0h], rcx
0x1800139e4  mov     [rsi+3FF8h], rbp
0x1800139eb  mov     [rsi+4010h], ebp
0x1800139f1  cmp     r12d, eax
0x1800139f4  jle     short loc_180013A1B
0x1800139f6  mov     eax, 80040003h
0x1800139fb  jmp     short loc_180013A27
0x1800139fd  mov     ecx, [rcx+4010h]
0x180013a03  lea     eax, [rcx+rdx]
0x180013a06  cmp     eax, [rsi+4014h]
0x180013a0c  jg      short loc_1800139F6
0x180013a0e  xor     ebp, ebp
0x180013a10  lea     rdi, [rsi+3FE8h]
0x180013a17  mov     ebx, ebp
0x180013a19  mov     ebp, ecx
0x180013a1b  movsxd  rax, ebp
0x180013a1e  add     rax, [rdi]
0x180013a21  mov     [r13+0], rax
0x180013a25  mov     eax, ebx
0x180013a27  add     rsp, 38h
0x180013a2b  pop     r15
0x180013a2d  pop     r14
0x180013a2f  pop     r13
0x180013a31  pop     r12
0x180013a33  pop     rdi
0x180013a34  pop     rsi
0x180013a35  pop     rbp
0x180013a36  pop     rbx
0x180013a37  retn
```
