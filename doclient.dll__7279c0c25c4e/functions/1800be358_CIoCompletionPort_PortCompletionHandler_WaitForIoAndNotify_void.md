# CIoCompletionPort::PortCompletionHandler::WaitForIoAndNotify(void)

- ea: `0x1800be358`
- end: `0x1800be560`
- name: `?WaitForIoAndNotify@PortCompletionHandler@CIoCompletionPort@@QEAAXXZ`
- size: `520`
- prototype: `void __fastcall(CIoCompletionPort::PortCompletionHandler *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800be670`

## callees

- `0x1800196f0`
- `0x1800a1c5c`
- `0x1800a1ea4`
- `0x1800be358`
- `0x1800f82f0`
- `0x1800f8314`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be3c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800be3c0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800be402`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800be402`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800be521`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800be521`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x1800be3b2`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x1800be3b2`

## string_xrefs

- `0x1800be4c4`: `CIoCompletionPort::PortCompletionHandler::WaitForIoAndNotify`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CIoCompletionPort::PortCompletionHandler::WaitForIoAndNotify(RTL_SRWLOCK *this)
{
  unsigned int v2; // ebx
  signed int LastError; // eax
  unsigned __int64 v4; // rax
  LPOVERLAPPED v5; // rdx
  ULONG_PTR Internal; // r8
  _QWORD *Ptr; // r9
  _QWORD *v8; // rax
  _QWORD *v9; // rcx
  __int64 v10; // rcx
  void **v11; // rax
  LPOVERLAPPED *i; // rbx
  LPOVERLAPPED v13; // rcx
  LPOVERLAPPED Overlapped; // [rsp+60h] [rbp+1Fh] BYREF
  LPOVERLAPPED v15; // [rsp+68h] [rbp+27h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+70h] [rbp+2Fh] BYREF
  DWORD v17; // [rsp+78h] [rbp+37h] BYREF
  unsigned int v18; // [rsp+80h] [rbp+3Fh] BYREF
  unsigned __int64 CompletionKey; // [rsp+88h] [rbp+47h] BYREF

  CompletionKey = 0;
  do
  {
    Overlapped = 0;
    NumberOfBytesTransferred = 0;
    if ( GetQueuedCompletionStatus(this->Ptr, &NumberOfBytesTransferred, &CompletionKey, &Overlapped, 0xFFFFFFFF) )
    {
      v2 = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError )
      {
        v2 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v2 = LastError;
      }
      else
      {
        v2 = -2147467259;
      }
    }
    v4 = CompletionKey;
    if ( !CompletionKey )
    {
      AcquireSRWLockShared(this + 5);
      v5 = Overlapped;
      LOBYTE(Overlapped[1].InternalHigh) = 0;
      Internal = v5[1].Internal;
      Ptr = this[3].Ptr;
      v8 = (_QWORD *)Ptr[1];
      v9 = Ptr;
      while ( !*((_BYTE *)v8 + 25) )
      {
        if ( v8[4] >= Internal )
          v9 = v8;
        else
          v8 += 2;
        v8 = (_QWORD *)*v8;
      }
      if ( *((_BYTE *)v9 + 25) || Internal < v9[4] || v9 == Ptr )
      {
        v11 = (void **)this[1].Ptr;
        for ( i = (LPOVERLAPPED *)*v11; i != (LPOVERLAPPED *)v11; i = (LPOVERLAPPED *)*i )
        {
          if ( i[2] == v5 )
            goto LABEL_26;
        }
        LogMessage(
          2u,
          "CIoCompletionPort::PortCompletionHandler::WaitForIoAndNotify",
          0x6Bu,
          "TelemetryAssert (%s): %s",
          "it2 != pendingOverlappedList.end()",
          "Failed");
        DOTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
LABEL_26:
        if ( i != this[1].Ptr )
        {
          i[1]->Internal = (ULONG_PTR)*i;
          (*i)->InternalHigh = (ULONG_PTR)i[1];
          --this[2].Ptr;
          v13 = i[2];
          if ( v13 )
            operator delete(v13);
          operator delete(i);
        }
      }
      else
      {
        v15 = v5;
        v17 = NumberOfBytesTransferred;
        v18 = v2;
        v10 = v9[12];
        if ( !v10 )
          std::_Xbad_function_call();
        (*(void (__fastcall **)(__int64, unsigned int *, DWORD *, LPOVERLAPPED *))(*(_QWORD *)v10 + 16LL))(
          v10,
          &v18,
          &v17,
          &v15);
      }
      ReleaseSRWLockShared(this + 5);
      v4 = CompletionKey;
    }
  }
  while ( v4 != 1 );
}

```

## disassembly

```asm
0x1800be358  mov     rax, rsp
0x1800be35b  mov     [rax+10h], rbx
0x1800be35f  mov     [rax+18h], rsi
0x1800be363  mov     [rax+20h], rdi
0x1800be367  push    rbp
0x1800be368  lea     rbp, [rax-5Fh]
0x1800be36c  sub     rsp, 90h
0x1800be373  mov     rax, cs:__security_cookie
0x1800be37a  xor     rax, rsp
0x1800be37d  mov     [rbp+57h+var_8], rax
0x1800be381  mov     rdi, rcx
0x1800be384  mov     [rbp+57h+CompletionKey], 0
0x1800be38c  mov     [rbp+57h+Overlapped], 0
0x1800be394  mov     [rbp+57h+NumberOfBytesTransferred], 0
0x1800be39b  mov     [rsp+90h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x1800be3a3  lea     r9, [rbp+57h+Overlapped]; lpOverlapped
0x1800be3a7  lea     r8, [rbp+57h+CompletionKey]; lpCompletionKey
0x1800be3ab  lea     rdx, [rbp+57h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1800be3af  mov     rcx, [rdi]; CompletionPort
0x1800be3b2  call    cs:__imp_GetQueuedCompletionStatus
0x1800be3b8  test    eax, eax
0x1800be3ba  jz      short loc_1800BE3C0
0x1800be3bc  xor     ebx, ebx
0x1800be3be  jmp     short loc_1800BE3DF
0x1800be3c0  call    cs:__imp_GetLastError
0x1800be3c6  test    eax, eax
0x1800be3c8  jz      short loc_1800BE3DA
0x1800be3ca  movzx   ebx, ax
0x1800be3cd  or      ebx, 80070000h
0x1800be3d3  test    eax, eax
0x1800be3d5  cmovle  ebx, eax
0x1800be3d8  jmp     short loc_1800BE3DF
0x1800be3da  mov     ebx, 80004005h
0x1800be3df  mov     rax, [rbp+57h+CompletionKey]
0x1800be3e3  test    rax, rax
0x1800be3e6  jnz     loc_1800BE52B
0x1800be3ec  xorps   xmm0, xmm0
0x1800be3ef  movups  [rbp+57h+var_60], xmm0
0x1800be3f3  lea     rsi, [rdi+28h]
0x1800be3f7  mov     qword ptr [rbp+57h+var_60], rsi
0x1800be3fb  mov     byte ptr [rbp+57h+var_60+8], 1
0x1800be3ff  mov     rcx, rsi; SRWLock
0x1800be402  call    cs:__imp_AcquireSRWLockShared
0x1800be408  nop
0x1800be409  mov     rdx, [rbp+57h+Overlapped]
0x1800be40d  xor     eax, eax
0x1800be40f  xchg    al, [rdx+28h]
0x1800be412  mov     r8, [rdx+20h]
0x1800be416  mov     r9, [rdi+18h]
0x1800be41a  mov     rax, [r9+8]
0x1800be41e  xor     ecx, ecx
0x1800be420  mov     [rbp+57h+var_44], ecx
0x1800be423  mov     rcx, r9
0x1800be426  jmp     short loc_1800BE43A
0x1800be428  cmp     [rax+20h], r8
0x1800be42c  jnb     short loc_1800BE434
0x1800be42e  add     rax, 10h
0x1800be432  jmp     short loc_1800BE437
0x1800be434  mov     rcx, rax
0x1800be437  mov     rax, [rax]
0x1800be43a  cmp     byte ptr [rax+19h], 0
0x1800be43e  jz      short loc_1800BE428
0x1800be440  cmp     byte ptr [rcx+19h], 0
0x1800be444  jnz     short loc_1800BE488
0x1800be446  cmp     r8, [rcx+20h]
0x1800be44a  jb      short loc_1800BE488
0x1800be44c  cmp     rcx, r9
0x1800be44f  jz      short loc_1800BE488
0x1800be451  mov     [rbp+57h+var_30], rdx
0x1800be455  mov     eax, [rbp+57h+NumberOfBytesTransferred]
0x1800be458  mov     [rbp+57h+var_20], eax
0x1800be45b  mov     [rbp+57h+var_18], ebx
0x1800be45e  mov     rcx, [rcx+60h]
0x1800be462  test    rcx, rcx
0x1800be465  jz      loc_1800BE55A
0x1800be46b  mov     rax, [rcx]
0x1800be46e  lea     r9, [rbp+57h+var_30]
0x1800be472  lea     r8, [rbp+57h+var_20]
0x1800be476  lea     rdx, [rbp+57h+var_18]
0x1800be47a  mov     rax, [rax+10h]
0x1800be47e  call    _guard_dispatch_icall
0x1800be483  jmp     loc_1800BE51E
0x1800be488  mov     rax, [rdi+8]
0x1800be48c  mov     rbx, [rax]
0x1800be48f  jmp     short loc_1800BE49A
0x1800be491  cmp     [rbx+10h], rdx
0x1800be495  jz      short loc_1800BE4DE
0x1800be497  mov     rbx, [rbx]
0x1800be49a  cmp     rbx, rax
0x1800be49d  jnz     short loc_1800BE491
0x1800be49f  lea     rax, aFailed; "Failed"
0x1800be4a6  mov     [rsp+90h+var_68], rax
0x1800be4ab  lea     rax, aIt2Pendingover; "it2 != pendingOverlappedList.end()"
0x1800be4b2  mov     qword ptr [rsp+90h+dwMilliseconds], rax
0x1800be4b7  lea     r9, aTelemetryasser; "TelemetryAssert (%s): %s"
0x1800be4be  mov     r8d, 6Bh ; 'k'; unsigned int
0x1800be4c4  lea     rdx, aCiocompletionp; "CIoCompletionPort::PortCompletionHandle"...
0x1800be4cb  lea     ecx, [r8-69h]; unsigned __int8
0x1800be4cf  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800be4d4  or      edx, 0FFFFFFFFh; unsigned int
0x1800be4d7  or      ecx, edx; unsigned int
0x1800be4d9  call    ?DOTelemetryAssertTriggered@@YAXII@Z; DOTelemetryAssertTriggered(uint,uint)
0x1800be4de  cmp     rbx, [rdi+8]
0x1800be4e2  jz      short loc_1800BE51E
0x1800be4e4  mov     rcx, [rbx+8]
0x1800be4e8  mov     rax, [rbx]
0x1800be4eb  mov     [rcx], rax
0x1800be4ee  mov     rcx, [rbx]
0x1800be4f1  mov     rax, [rbx+8]
0x1800be4f5  mov     [rcx+8], rax
0x1800be4f9  dec     qword ptr [rdi+10h]
0x1800be4fd  mov     rcx, [rbx+10h]; Block
0x1800be501  test    rcx, rcx
0x1800be504  jz      short loc_1800BE510
0x1800be506  mov     edx, 30h ; '0'
0x1800be50b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800be510  mov     edx, 18h
0x1800be515  mov     rcx, rbx; Block
0x1800be518  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800be51d  nop
0x1800be51e  mov     rcx, rsi; SRWLock
0x1800be521  call    cs:__imp_ReleaseSRWLockShared
0x1800be527  mov     rax, [rbp+57h+CompletionKey]
0x1800be52b  cmp     rax, 1
0x1800be52f  jnz     loc_1800BE38C
0x1800be535  mov     rcx, [rbp+57h+var_8]
0x1800be539  xor     rcx, rsp; StackCookie
0x1800be53c  call    __security_check_cookie
0x1800be541  lea     r11, [rsp+90h+var_s0]
0x1800be549  mov     rbx, [r11+18h]
0x1800be54d  mov     rsi, [r11+20h]
0x1800be551  mov     rdi, [r11+28h]
0x1800be555  mov     rsp, r11
0x1800be558  pop     rbp
0x1800be559  retn
0x1800be55a  call    ?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
```
