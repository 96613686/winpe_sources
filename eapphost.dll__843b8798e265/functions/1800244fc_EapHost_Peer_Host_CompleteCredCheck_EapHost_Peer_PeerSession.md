# EapHost::Peer::Host::CompleteCredCheck(EapHost::Peer::PeerSession &)

- ea: `0x1800244fc`
- end: `0x1800245fe`
- name: `?CompleteCredCheck@Host@Peer@EapHost@@QEAAXAEAVPeerSession@23@@Z`
- size: `258`
- prototype: `void __fastcall(EapHost::Peer::Host *__hidden this, struct EapHost::Peer::PeerSession *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180025770`
- `0x1800263cc`

## callees

- `0x18000a24c`
- `0x180024318`
- `0x1800244fc`
- `0x18002aad0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180024534`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002454a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180024534`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002454a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800245c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800245c9`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002457f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002457f`

## pseudocode

```c
void __fastcall EapHost::Peer::Host::CompleteCredCheck(
        EapHost::Peer::Host *this,
        struct EapHost::Peer::PeerSession *a2)
{
  HANDLE CurrentProcess; // rax
  void *v5; // rdi
  void *v6; // rbx
  HANDLE v7; // rax
  __int128 v8; // xmm0
  DWORD LastError; // eax
  HANDLE TargetHandle; // [rsp+80h] [rbp+18h] BYREF

  EapHost::Peer::Host::CaptureSessionCreds((__int64)this, 1, (__int64)a2);
  if ( EapHost::Peer::Host::SessionCredsWereChanged(this) )
  {
    TargetHandle = (HANDLE)-1LL;
    CurrentProcess = GetCurrentProcess();
    v5 = (void *)*((_QWORD *)a2 + 25);
    v6 = CurrentProcess;
    v7 = GetCurrentProcess();
    if ( DuplicateHandle(v7, v5, v6, &TargetHandle, 0, 0, 2u) )
    {
      v8 = *(_OWORD *)((char *)a2 + 244);
      *((_QWORD *)this + 4) = TargetHandle;
      *((_OWORD *)this + 1) = v8;
      *((_DWORD *)this + 10) = 1;
    }
    else if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids, LastError);
    }
  }
}

```

## disassembly

```asm
0x1800244fc  push    rbx
0x1800244fe  push    rbp
0x1800244ff  push    rsi
0x180024500  push    rdi
0x180024501  sub     rsp, 48h
0x180024505  mov     rbp, rdx
0x180024508  mov     r8, rdx
0x18002450b  mov     edx, 1
0x180024510  mov     rsi, rcx
0x180024513  call    ?CaptureSessionCreds@Host@Peer@EapHost@@AEAAXW4SessionCredType@123@AEAVPeerSession@23@@Z; EapHost::Peer::Host::CaptureSessionCreds(EapHost::Peer::Host::SessionCredType,EapHost::Peer::PeerSession &)
0x180024518  mov     rcx, rsi; this
0x18002451b  call    ?SessionCredsWereChanged@Host@Peer@EapHost@@AEAA_NXZ; EapHost::Peer::Host::SessionCredsWereChanged(void)
0x180024520  test    al, al
0x180024522  jz      loc_1800245F4
0x180024528  mov     [rsp+68h+TargetHandle], 0FFFFFFFFFFFFFFFFh
0x180024534  call    cs:__imp_GetCurrentProcess
0x18002453b  nop     dword ptr [rax+rax+00h]
0x180024540  mov     rdi, [rbp+0C8h]
0x180024547  mov     rbx, rax
0x18002454a  call    cs:__imp_GetCurrentProcess
0x180024551  nop     dword ptr [rax+rax+00h]
0x180024556  mov     [rsp+68h+dwOptions], 2; dwOptions
0x18002455e  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x180024566  mov     rcx, rax; hSourceProcessHandle
0x180024569  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x180024571  mov     r8, rbx; hTargetProcessHandle
0x180024574  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x18002457c  mov     rdx, rdi; hSourceHandle
0x18002457f  call    cs:__imp_DuplicateHandle
0x180024586  nop     dword ptr [rax+rax+00h]
0x18002458b  test    eax, eax
0x18002458d  jz      short loc_1800245B0
0x18002458f  movups  xmm0, xmmword ptr [rbp+0F4h]
0x180024596  mov     rax, [rsp+68h+TargetHandle]
0x18002459e  mov     [rsi+20h], rax
0x1800245a2  movdqu  xmmword ptr [rsi+10h], xmm0
0x1800245a7  mov     dword ptr [rsi+28h], 1
0x1800245ae  jmp     short loc_1800245F4
0x1800245b0  mov     rax, cs:WPP_GLOBAL_Control
0x1800245b7  lea     rcx, WPP_GLOBAL_Control
0x1800245be  cmp     rax, rcx
0x1800245c1  jz      short loc_1800245F4
0x1800245c3  test    byte ptr [rax+1Ch], 4
0x1800245c7  jz      short loc_1800245F4
0x1800245c9  call    cs:__imp_GetLastError
0x1800245d0  nop     dword ptr [rax+rax+00h]
0x1800245d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800245dc  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x1800245e3  mov     edx, 22h ; '"'
0x1800245e8  mov     r9d, eax
0x1800245eb  mov     rcx, [rcx+10h]
0x1800245ef  call    WPP_SF_d
0x1800245f4  add     rsp, 48h
0x1800245f8  pop     rdi
0x1800245f9  pop     rsi
0x1800245fa  pop     rbp
0x1800245fb  pop     rbx
0x1800245fc  retn
```
