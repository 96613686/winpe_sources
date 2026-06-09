# CCscWmiAsyncThread::Run(void)

- ea: `0x1800267fc`
- end: `0x18002697a`
- name: `?Run@CCscWmiAsyncThread@@QEAAJXZ`
- size: `382`
- prototype: `__int64 __fastcall(CCscWmiAsyncThread *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x1800176e0`
- `0x180017784`
- `0x180019934`

## callees

- `0x180009864`
- `0x18000f5a4`
- `0x18000f5cc`
- `0x180016280`
- `0x1800267fc`
- `0x180026980`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180026847`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180026847`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800268a1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800268a1`

## pseudocode

```c
__int64 __fastcall CCscWmiAsyncThread::Run(CCscWmiAsyncThread *this)
{
  int v2; // ebx
  HANDLE Thread; // rax
  UstVarLib *v4; // rcx
  unsigned int Error; // eax
  __int64 v6; // rcx

  v2 = CCscWmiAsyncThread::_Initialize((void **)this);
  if ( v2 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)this + 2);
    Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CCscWmiAsyncThread::_ThreadProc, this, 0, (LPDWORD)this + 4);
    *((_QWORD *)this + 3) = Thread;
    if ( !Thread )
    {
      Error = UstVarLib::ResultFromLastError(v4);
      v2 = Error;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_c18537868ffb3feea335b692c1d3fa6a_Traceguids, Error);
      CRefCounted::ReleaseReference(this);
      v6 = WPP_GLOBAL_Control;
      goto LABEL_16;
    }
    if ( WaitForSingleObject(*((HANDLE *)this + 6), 0xFFFFFFFF) != -1 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
      {
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_c18537868ffb3feea335b692c1d3fa6a_Traceguids);
        v6 = WPP_GLOBAL_Control;
      }
      v2 = *((_DWORD *)this + 14);
LABEL_16:
      if ( v2 >= 0 )
        return (unsigned int)v2;
      goto LABEL_19;
    }
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_c18537868ffb3feea335b692c1d3fa6a_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
    v2 = -2147467259;
  }
LABEL_19:
  if ( (_UNKNOWN *)v6 != &WPP_GLOBAL_Control && (*(_BYTE *)(v6 + 28) & 2) != 0 )
    WPP_SF_d(*(_QWORD *)(v6 + 16), 13, WPP_c18537868ffb3feea335b692c1d3fa6a_Traceguids, (unsigned int)v2);
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 17) + 32LL))(
    *((_QWORD *)this + 17),
    0,
    (unsigned int)v2,
    0,
    0);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800267fc  mov     [rsp+arg_0], rbx
0x180026801  mov     [rsp+arg_8], rsi
0x180026806  push    rdi
0x180026807  sub     rsp, 30h
0x18002680b  mov     rdi, rcx
0x18002680e  call    ?_Initialize@CCscWmiAsyncThread@@AEAAJXZ; CCscWmiAsyncThread::_Initialize(void)
0x180026813  lea     rsi, WPP_GLOBAL_Control
0x18002681a  mov     ebx, eax
0x18002681c  test    eax, eax
0x18002681e  js      loc_18002691A
0x180026824  lock inc dword ptr [rdi+8]
0x180026828  lea     rax, [rdi+10h]
0x18002682c  mov     r9, rdi; lpParameter
0x18002682f  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180026834  lea     r8, ?_ThreadProc@CCscWmiAsyncThread@@CAKPEAX@Z; lpStartAddress
0x18002683b  xor     edx, edx; dwStackSize
0x18002683d  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180026845  xor     ecx, ecx; lpThreadAttributes
0x180026847  call    cs:__imp_CreateThread
0x18002684d  mov     [rdi+18h], rax
0x180026851  test    rax, rax
0x180026854  jnz     short loc_180026898
0x180026856  call    ?ResultFromLastError@UstVarLib@@YAJXZ; UstVarLib::ResultFromLastError(void)
0x18002685b  mov     ebx, eax
0x18002685d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026864  cmp     rcx, rsi
0x180026867  jz      short loc_180026887
0x180026869  test    byte ptr [rcx+1Ch], 2
0x18002686d  jz      short loc_180026887
0x18002686f  mov     rcx, [rcx+10h]
0x180026873  lea     r8, WPP_c18537868ffb3feea335b692c1d3fa6a_Traceguids
0x18002687a  mov     edx, 0Ah
0x18002687f  mov     r9d, eax
0x180026882  call    WPP_SF_d
0x180026887  mov     rcx, rdi; this
0x18002688a  call    ?ReleaseReference@CRefCounted@@QEAAXXZ; CRefCounted::ReleaseReference(void)
0x18002688f  mov     rcx, cs:WPP_GLOBAL_Control
0x180026896  jmp     short loc_180026914
0x180026898  mov     rcx, [rdi+30h]; hHandle
0x18002689c  or      ebx, 0FFFFFFFFh
0x18002689f  mov     edx, ebx; dwMilliseconds
0x1800268a1  call    cs:__imp_WaitForSingleObject
0x1800268a7  cmp     eax, ebx
0x1800268a9  jnz     short loc_1800268E0
0x1800268ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800268b2  cmp     rcx, rsi
0x1800268b5  jz      short loc_1800268D9
0x1800268b7  test    byte ptr [rcx+1Ch], 2
0x1800268bb  jz      short loc_1800268D9
0x1800268bd  mov     rcx, [rcx+10h]
0x1800268c1  lea     r8, WPP_c18537868ffb3feea335b692c1d3fa6a_Traceguids
0x1800268c8  mov     edx, 0Bh
0x1800268cd  call    WPP_SF_
0x1800268d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800268d9  mov     ebx, 80004005h
0x1800268de  jmp     short loc_180026921
0x1800268e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800268e7  cmp     rcx, rsi
0x1800268ea  jz      short loc_180026911
0x1800268ec  test    dword ptr [rcx+1Ch], 4000000h
0x1800268f3  jz      short loc_180026911
0x1800268f5  mov     rcx, [rcx+10h]
0x1800268f9  lea     r8, WPP_c18537868ffb3feea335b692c1d3fa6a_Traceguids
0x180026900  mov     edx, 0Ch
0x180026905  call    WPP_SF_
0x18002690a  mov     rcx, cs:WPP_GLOBAL_Control
0x180026911  mov     ebx, [rdi+38h]
0x180026914  test    ebx, ebx
0x180026916  jns     short loc_180026968
0x180026918  jmp     short loc_180026921
0x18002691a  mov     rcx, cs:WPP_GLOBAL_Control
0x180026921  cmp     rcx, rsi
0x180026924  jz      short loc_180026944
0x180026926  test    byte ptr [rcx+1Ch], 2
0x18002692a  jz      short loc_180026944
0x18002692c  mov     rcx, [rcx+10h]
0x180026930  lea     r8, WPP_c18537868ffb3feea335b692c1d3fa6a_Traceguids
0x180026937  mov     edx, 0Dh
0x18002693c  mov     r9d, ebx
0x18002693f  call    WPP_SF_d
0x180026944  mov     rcx, [rdi+88h]
0x18002694b  xor     r9d, r9d
0x18002694e  mov     r8d, ebx
0x180026951  mov     qword ptr [rsp+38h+dwCreationFlags], 0
0x18002695a  xor     edx, edx
0x18002695c  mov     rax, [rcx]
0x18002695f  mov     rax, [rax+20h]
0x180026963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026968  mov     rsi, [rsp+38h+arg_8]
0x18002696d  mov     eax, ebx
0x18002696f  mov     rbx, [rsp+38h+arg_0]
0x180026974  add     rsp, 30h
0x180026978  pop     rdi
0x180026979  retn
```
