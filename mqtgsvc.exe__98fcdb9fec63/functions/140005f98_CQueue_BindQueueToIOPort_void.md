# CQueue::BindQueueToIOPort(void)

- ea: `0x140005f98`
- end: `0x1400060aa`
- name: `?BindQueueToIOPort@CQueue@@QEAAJXZ`
- size: `274`
- prototype: `__int64 __fastcall(CQueue *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400062c8`

## callees

- `0x140003d08`
- `0x140005b38`
- `0x140005f98`
- `0x140007594`
- `0x14001c9a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000605a`
- `KERNEL32!GetLastError` at `0x14000605a`
- `KERNEL32!CreateIoCompletionPort` at `0x140005fe0`
- `KERNEL32!CreateIoCompletionPort` at `0x140005fe0`

## pseudocode

```c
__int64 __fastcall CQueue::BindQueueToIOPort(CQueue *this)
{
  unsigned int v2; // edi
  HANDLE IoCompletionPort; // rsi
  void *v4; // rcx
  char LastError; // cl
  CReadWriteLock *v7; // [rsp+40h] [rbp+8h] BYREF

  v2 = 0;
  if ( !*((_BYTE *)this + 18) )
  {
    IoCompletionPort = 0;
    v7 = (CQueue *)((char *)this + 176);
    CReadWriteLock::LockRead((CQueue *)((char *)this + 176));
    v4 = (void *)*((_QWORD *)this + 3);
    if ( v4 )
      IoCompletionPort = CreateIoCompletionPort(v4, **((HANDLE **)this + 7), 0, 0);
    CSR::~CSR(&v7);
    if ( IoCompletionPort )
    {
      *((_BYTE *)this + 18) = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), LastError);
      }
      return (unsigned int)-1072820736;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140005f98  mov     [rsp+arg_8], rbx
0x140005f9d  mov     [rsp+arg_10], rsi
0x140005fa2  push    rdi
0x140005fa3  sub     rsp, 30h
0x140005fa7  mov     rbx, rcx
0x140005faa  xor     edi, edi
0x140005fac  cmp     [rcx+12h], dil
0x140005fb0  jnz     loc_140006098
0x140005fb6  xor     esi, esi
0x140005fb8  add     rcx, 0B0h; this
0x140005fbf  mov     [rsp+38h+arg_0], rcx
0x140005fc4  call    ?LockRead@CReadWriteLock@@QEAAXXZ; CReadWriteLock::LockRead(void)
0x140005fc9  nop
0x140005fca  mov     rcx, [rbx+18h]; FileHandle
0x140005fce  test    rcx, rcx
0x140005fd1  jz      short loc_140005FE9
0x140005fd3  mov     rdx, [rbx+38h]
0x140005fd7  xor     r9d, r9d; NumberOfConcurrentThreads
0x140005fda  xor     r8d, r8d; CompletionKey
0x140005fdd  mov     rdx, [rdx]; ExistingCompletionPort
0x140005fe0  call    cs:__imp_CreateIoCompletionPort
0x140005fe6  mov     rsi, rax
0x140005fe9  lea     rcx, [rsp+38h+arg_0]; this
0x140005fee  call    ??1CSR@@QEAA@XZ; CSR::~CSR(void)
0x140005ff3  test    rsi, rsi
0x140005ff6  jz      short loc_140006041
0x140005ff8  mov     byte ptr [rbx+12h], 1
0x140005ffc  lea     rax, WPP_GLOBAL_Control
0x140006003  mov     rcx, cs:WPP_GLOBAL_Control
0x14000600a  cmp     rcx, rax
0x14000600d  jz      loc_140006098
0x140006013  test    byte ptr [rcx+1Ch], 4
0x140006017  jz      short loc_140006098
0x140006019  mov     rax, [rbx+60h]
0x14000601d  test    rax, rax
0x140006020  jz      short loc_140006027
0x140006022  mov     r9, [rax]
0x140006025  jmp     short loc_14000602A
0x140006027  xor     r9d, r9d
0x14000602a  mov     edx, 15h
0x14000602f  lea     r8, WPP_81c52ba4630d30a3481546cc16d5e3ae_Traceguids
0x140006036  mov     rcx, [rcx+10h]; LoggerHandle
0x14000603a  call    WPP_SF_S
0x14000603f  jmp     short loc_140006098
0x140006041  lea     rax, WPP_GLOBAL_Control
0x140006048  mov     rcx, cs:WPP_GLOBAL_Control
0x14000604f  cmp     rcx, rax
0x140006052  jz      short loc_140006093
0x140006054  test    byte ptr [rcx+1Ch], 1
0x140006058  jz      short loc_140006093
0x14000605a  call    cs:__imp_GetLastError
0x140006060  mov     ecx, eax
0x140006062  mov     rax, [rbx+60h]
0x140006066  test    rax, rax
0x140006069  jz      short loc_140006070
0x14000606b  mov     r9, [rax]
0x14000606e  jmp     short loc_140006073
0x140006070  xor     r9d, r9d
0x140006073  mov     edx, 16h
0x140006078  mov     dword ptr [rsp+38h+var_18], ecx; char
0x14000607c  lea     r8, WPP_81c52ba4630d30a3481546cc16d5e3ae_Traceguids
0x140006083  mov     rcx, cs:WPP_GLOBAL_Control
0x14000608a  mov     rcx, [rcx+10h]; LoggerHandle
0x14000608e  call    WPP_SF_Sd
0x140006093  mov     edi, 0C00E0E00h
0x140006098  mov     eax, edi
0x14000609a  mov     rbx, [rsp+38h+arg_8]
0x14000609f  mov     rsi, [rsp+38h+arg_10]
0x1400060a4  add     rsp, 30h
0x1400060a8  pop     rdi
0x1400060a9  retn
```
