# boost::asio::detail::select_reactor::cancel_ops_unlocked(unsigned __int64,boost::system::error_code const &)

- ea: `0x18016aef0`
- end: `0x18016b0c5`
- name: `?cancel_ops_unlocked@select_reactor@detail@asio@boost@@AEAAX_KAEBVerror_code@system@4@@Z`
- size: `469`
- prototype: `void __fastcall(boost::asio::detail::select_reactor *__hidden this, unsigned __int64, const struct boost::system::error_code *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18016ae64`

## callees

- `0x18016addc`
- `0x18016aef0`
- `0x18016eea8`
- `0x18032f050`
- `0x180375c40`

## import_xrefs

- `KERNEL32!PostQueuedCompletionStatus` at `0x18016afdf`
- `KERNEL32!PostQueuedCompletionStatus` at `0x18016afdf`
- `KERNEL32!EnterCriticalSection` at `0x18016afff`
- `KERNEL32!EnterCriticalSection` at `0x18016afff`
- `KERNEL32!LeaveCriticalSection` at `0x18016b04c`
- `KERNEL32!LeaveCriticalSection` at `0x18016b04c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall boost::asio::detail::select_reactor::cancel_ops_unlocked(
        boost::asio::detail::select_reactor *this,
        unsigned __int64 a2,
        const struct boost::system::error_code *a3)
{
  int v3; // eax
  char v7; // r15
  _QWORD *v8; // rbx
  __int64 v9; // rdi
  __int64 v10; // rbp
  _QWORD *v11; // rax
  _QWORD *v12; // rdx
  __int64 v13; // rdi
  LPOVERLAPPED Internal; // rsi
  LPOVERLAPPED v15; // rbx
  LPOVERLAPPED v16; // r14
  unsigned __int64 v17; // r12
  __int64 v18; // rax
  LPOVERLAPPED v19; // rdi
  LPOVERLAPPED lpOverlapped[2]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v21; // [rsp+40h] [rbp-48h]

  v7 = 0;
  *(_OWORD *)lpOverlapped = 0;
  v8 = (_QWORD *)((char *)this + 152);
  v9 = (unsigned int)(v3 - 76);
  v10 = (unsigned int)(v3 - 79);
  do
  {
    if ( !v8[1] )
      goto LABEL_8;
    v11 = *(_QWORD **)(*v8 + 16 * (a2 % v8[1]));
    v12 = (_QWORD *)*(v8 - 4);
    if ( v11 != v12 )
    {
      while ( v11 != **(_QWORD ***)(*v8 + 16 * (a2 % v8[1]) + 8) )
      {
        if ( v11[2] == a2 )
        {
          v12 = v11;
          goto LABEL_9;
        }
        v11 = (_QWORD *)*v11;
      }
LABEL_8:
      v12 = (_QWORD *)*(v8 - 4);
    }
LABEL_9:
    if ( (unsigned __int8)boost::asio::detail::reactor_op_queue<unsigned __int64>::cancel_operations(
                            v8 - 5,
                            v12,
                            lpOverlapped,
                            a3)
      || v7 )
    {
      v7 = v10;
    }
    v8 += 7;
    v9 -= v10;
  }
  while ( v9 );
  v13 = *((_QWORD *)this + 6);
  Internal = lpOverlapped[0];
  v15 = lpOverlapped[0];
  if ( lpOverlapped[0] )
  {
    v16 = lpOverlapped[0];
    v17 = (unsigned __int64)lpOverlapped[1];
    while ( 1 )
    {
      Internal = (LPOVERLAPPED)Internal[1].Internal;
      v17 &= -(__int64)(Internal != 0);
      v16[1].Internal = 0;
      v15[1].Offset = v10;
      v16 = Internal;
      if ( !PostQueuedCompletionStatus(*(HANDLE *)(v13 + 48), 0, 0, v15) )
        break;
      v15 = Internal;
      if ( !Internal )
        goto LABEL_25;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(v13 + 104));
    v15[1].Internal = 0;
    v18 = *(_QWORD *)(v13 + 160);
    if ( v18 )
      *(_QWORD *)(v18 + 32) = v15;
    else
      *(_QWORD *)(v13 + 152) = v15;
    *(_QWORD *)(v13 + 160) = v15;
    if ( Internal )
    {
      v15[1].Internal = (ULONG_PTR)Internal;
      *(_QWORD *)(v13 + 160) = v17;
      Internal = 0;
    }
    _InterlockedExchange((volatile __int32 *)(v13 + 96), v10);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 104));
LABEL_25:
    v15 = 0;
  }
  if ( v7 )
    boost::asio::detail::socket_select_interrupter::interrupt((char *)this + 96);
  if ( v15 )
  {
    v19 = v15;
    do
    {
      Internal = (LPOVERLAPPED)Internal[1].Internal;
      v19[1].Internal = 0;
      v19 = Internal;
      *(_OWORD *)lpOverlapped = 0;
      v21 = 0;
      ((void (__fastcall *)(_QWORD, LPOVERLAPPED, LPOVERLAPPED *, _QWORD))v15[1].InternalHigh)(0, v15, lpOverlapped, 0);
      v15 = Internal;
    }
    while ( Internal );
  }
}

```

## disassembly

```asm
0x18016aef0  mov     [rsp+arg_10], rbx
0x18016aef5  push    rbp
0x18016aef6  push    rsi
0x18016aef7  push    rdi
0x18016aef8  push    r12
0x18016aefa  push    r13
0x18016aefc  push    r14
0x18016aefe  push    r15
0x18016af00  mov     eax, 50h
0x18016af05  call    _alloca_probe
0x18016af0a  sub     rsp, rax
0x18016af0d  mov     r14, r8
0x18016af10  mov     rsi, rdx
0x18016af13  mov     r13, rcx
0x18016af16  xor     r15b, r15b
0x18016af19  xorps   xmm1, xmm1
0x18016af1c  movdqu  xmmword ptr [rsp+88h+lpOverlapped], xmm1
0x18016af22  lea     rbx, [rcx+98h]
0x18016af29  lea     edi, [rax-4Ch]
0x18016af2c  lea     ebp, [rax-4Fh]
0x18016af2f  cmp     qword ptr [rbx+8], 0
0x18016af34  jz      short loc_18016AF6E
0x18016af36  xor     edx, edx
0x18016af38  mov     rax, rsi
0x18016af3b  div     qword ptr [rbx+8]
0x18016af3f  mov     rcx, rdx
0x18016af42  add     rcx, rcx
0x18016af45  mov     r8, [rbx]
0x18016af48  mov     rax, [r8+rcx*8]
0x18016af4c  mov     rdx, [rbx-20h]
0x18016af50  cmp     rax, rdx
0x18016af53  jz      short loc_18016AF72
0x18016af55  mov     rcx, [r8+rcx*8+8]
0x18016af5a  jmp     short loc_18016AF69
0x18016af5c  cmp     [rax+10h], rsi
0x18016af60  jz      loc_18016AFF3
0x18016af66  mov     rax, [rax]
0x18016af69  cmp     rax, [rcx]
0x18016af6c  jnz     short loc_18016AF5C
0x18016af6e  mov     rdx, [rbx-20h]
0x18016af72  lea     rcx, [rbx-28h]
0x18016af76  mov     r9, r14
0x18016af79  lea     r8, [rsp+88h+lpOverlapped]
0x18016af7e  call    ?cancel_operations@?$reactor_op_queue@_K@detail@asio@boost@@QEAA_NV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@_KUmapped_type@?$reactor_op_queue@_K@detail@asio@boost@@@std@@@std@@@std@@@std@@AEAV?$op_queue@Vwin_iocp_operation@detail@asio@boost@@@234@AEBVerror_code@system@4@@Z; boost::asio::detail::reactor_op_queue<unsigned __int64>::cancel_operations(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64,boost::asio::detail::reactor_op_queue<unsigned __int64>::mapped_type>>>>,boost::asio::detail::op_queue<boost::asio::detail::win_iocp_operation> &,boost::system::error_code const &)
0x18016af83  test    al, al
0x18016af85  jnz     short loc_18016AF8C
0x18016af87  test    r15b, r15b
0x18016af8a  jz      short loc_18016AF8F
0x18016af8c  mov     r15b, bpl
0x18016af8f  add     rbx, 38h ; '8'
0x18016af93  sub     rdi, rbp
0x18016af96  jnz     short loc_18016AF2F
0x18016af98  mov     rdi, [r13+30h]
0x18016af9c  mov     rsi, [rsp+88h+lpOverlapped]
0x18016afa1  mov     rbx, rsi
0x18016afa4  test    rsi, rsi
0x18016afa7  jz      loc_18016B054
0x18016afad  mov     r14, rbx
0x18016afb0  mov     r12, [rsp+88h+lpOverlapped+8]
0x18016afb5  mov     rsi, [rsi+20h]
0x18016afb9  mov     rax, rsi
0x18016afbc  neg     rax
0x18016afbf  sbb     rcx, rcx
0x18016afc2  and     r12, rcx
0x18016afc5  mov     qword ptr [r14+20h], 0
0x18016afcd  mov     [rbx+30h], ebp
0x18016afd0  mov     r14, rsi
0x18016afd3  mov     r9, rbx; lpOverlapped
0x18016afd6  xor     r8d, r8d; dwCompletionKey
0x18016afd9  xor     edx, edx; dwNumberOfBytesTransferred
0x18016afdb  mov     rcx, [rdi+30h]; CompletionPort
0x18016afdf  call    cs:__imp_PostQueuedCompletionStatus
0x18016afe5  test    eax, eax
0x18016afe7  jz      short loc_18016AFFB
0x18016afe9  mov     rbx, rsi
0x18016afec  test    rsi, rsi
0x18016afef  jnz     short loc_18016AFB5
0x18016aff1  jmp     short loc_18016B052
0x18016aff3  mov     rdx, rax
0x18016aff6  jmp     loc_18016AF72
0x18016affb  lea     rcx, [rdi+68h]; lpCriticalSection
0x18016afff  call    cs:__imp_EnterCriticalSection
0x18016b005  mov     qword ptr [rbx+20h], 0
0x18016b00d  mov     rax, [rdi+0A0h]
0x18016b014  test    rax, rax
0x18016b017  jz      short loc_18016B01F
0x18016b019  mov     [rax+20h], rbx
0x18016b01d  jmp     short loc_18016B026
0x18016b01f  mov     [rdi+98h], rbx
0x18016b026  mov     [rdi+0A0h], rbx
0x18016b02d  test    rsi, rsi
0x18016b030  jz      short loc_18016B045
0x18016b032  mov     [rbx+20h], rsi
0x18016b036  mov     [rdi+0A0h], r12
0x18016b03d  xorps   xmm0, xmm0
0x18016b040  movq    rsi, xmm0
0x18016b045  xchg    ebp, [rdi+60h]
0x18016b048  lea     rcx, [rdi+68h]; lpCriticalSection
0x18016b04c  call    cs:__imp_LeaveCriticalSection
0x18016b052  xor     ebx, ebx
0x18016b054  test    r15b, r15b
0x18016b057  jz      short loc_18016B063
0x18016b059  lea     rcx, [r13+60h]
0x18016b05d  call    ?interrupt@socket_select_interrupter@detail@asio@boost@@QEAAXXZ; boost::asio::detail::socket_select_interrupter::interrupt(void)
0x18016b062  nop
0x18016b063  test    rbx, rbx
0x18016b066  jz      short loc_18016B0AD
0x18016b068  mov     rdi, rbx
0x18016b06b  mov     rax, [rsi+20h]
0x18016b06f  mov     rsi, rax
0x18016b072  mov     qword ptr [rdi+20h], 0
0x18016b07a  mov     rdi, rax
0x18016b07d  xorps   xmm0, xmm0
0x18016b080  movups  xmmword ptr [rsp+88h+lpOverlapped], xmm0
0x18016b085  mov     [rsp+88h+var_48], 0
0x18016b08e  xor     r9d, r9d
0x18016b091  lea     r8, [rsp+88h+lpOverlapped]
0x18016b096  mov     rdx, rbx
0x18016b099  xor     ecx, ecx
0x18016b09b  mov     rax, [rbx+28h]
0x18016b09f  call    cs:__guard_dispatch_icall_fptr
0x18016b0a5  mov     rbx, rdi
0x18016b0a8  test    rdi, rdi
0x18016b0ab  jnz     short loc_18016B06B
0x18016b0ad  mov     rbx, [rsp+88h+arg_10]
0x18016b0b5  add     rsp, 50h
0x18016b0b9  pop     r15
0x18016b0bb  pop     r14
0x18016b0bd  pop     r13
0x18016b0bf  pop     r12
0x18016b0c1  pop     rdi
0x18016b0c2  pop     rsi
0x18016b0c3  pop     rbp
0x18016b0c4  retn
```
