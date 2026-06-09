# CBaseRenderer::WaitForReceiveToComplete(void)

- ea: `0x18014b6cc`
- end: `0x18014b76a`
- name: `?WaitForReceiveToComplete@CBaseRenderer@@QEAAXXZ`
- size: `158`
- prototype: `void __fastcall(CBaseRenderer *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180035bc0`
- `0x18014b4f0`

## callees

- `0x18014b6cc`

## import_xrefs

- `KERNEL32!Sleep` at `0x18014b715`
- `KERNEL32!Sleep` at `0x18014b715`
- `KERNEL32!GetCurrentThreadId` at `0x18014b741`
- `KERNEL32!GetCurrentThreadId` at `0x18014b741`
- `USER32!GetQueueStatus` at `0x18014b72e`
- `USER32!GetQueueStatus` at `0x18014b72e`
- `USER32!PeekMessageW` at `0x18014b704`
- `USER32!PeekMessageW` at `0x18014b704`
- `USER32!PostThreadMessageW` at `0x18014b757`
- `USER32!PostThreadMessageW` at `0x18014b757`

## pseudocode

```c
void __fastcall CBaseRenderer::WaitForReceiveToComplete(CBaseRenderer *this)
{
  int i; // eax
  DWORD CurrentThreadId; // eax
  struct tagMSG Msg; // [rsp+30h] [rbp-38h] BYREF

  for ( i = *((_DWORD *)this + 72); i; i = *((_DWORD *)this + 72) )
  {
    memset(&Msg, 0, sizeof(Msg));
    PeekMessageW(&Msg, 0, 0, 0, 0);
    Sleep(1u);
  }
  if ( (GetQueueStatus(8u) & 0x80000) != 0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    PostThreadMessageW(CurrentThreadId, 0, 0, 0);
  }
}

```

## disassembly

```asm
0x18014b6cc  push    rbx
0x18014b6ce  sub     rsp, 60h
0x18014b6d2  mov     eax, [rcx+120h]
0x18014b6d8  mov     rbx, rcx
0x18014b6db  jmp     short loc_18014B727
0x18014b6dd  xorps   xmm0, xmm0
0x18014b6e0  mov     [rsp+68h+wRemoveMsg], 0; wRemoveMsg
0x18014b6e8  xor     r9d, r9d; wMsgFilterMax
0x18014b6eb  lea     rcx, [rsp+68h+Msg]; lpMsg
0x18014b6f0  xor     r8d, r8d; wMsgFilterMin
0x18014b6f3  xor     edx, edx; hWnd
0x18014b6f5  movups  xmmword ptr [rsp+68h+Msg.hwnd], xmm0
0x18014b6fa  movups  xmmword ptr [rsp+68h+Msg.wParam], xmm0
0x18014b6ff  movups  xmmword ptr [rsp+68h+Msg.time], xmm0
0x18014b704  call    cs:__imp_PeekMessageW
0x18014b70b  nop     dword ptr [rax+rax+00h]
0x18014b710  mov     ecx, 1; dwMilliseconds
0x18014b715  call    cs:__imp_Sleep
0x18014b71c  nop     dword ptr [rax+rax+00h]
0x18014b721  mov     eax, [rbx+120h]
0x18014b727  test    eax, eax
0x18014b729  jnz     short loc_18014B6DD
0x18014b72b  lea     ecx, [rax+8]; flags
0x18014b72e  call    cs:__imp_GetQueueStatus
0x18014b735  nop     dword ptr [rax+rax+00h]
0x18014b73a  shr     eax, 10h
0x18014b73d  test    al, 8
0x18014b73f  jz      short loc_18014B763
0x18014b741  call    cs:__imp_GetCurrentThreadId
0x18014b748  nop     dword ptr [rax+rax+00h]
0x18014b74d  xor     r9d, r9d; lParam
0x18014b750  xor     r8d, r8d; wParam
0x18014b753  mov     ecx, eax; idThread
0x18014b755  xor     edx, edx; Msg
0x18014b757  call    cs:__imp_PostThreadMessageW
0x18014b75e  nop     dword ptr [rax+rax+00h]
0x18014b763  add     rsp, 60h
0x18014b767  pop     rbx
0x18014b768  retn
```
