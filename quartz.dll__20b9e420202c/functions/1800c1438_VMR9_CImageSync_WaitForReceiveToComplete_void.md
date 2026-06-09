# VMR9::CImageSync::WaitForReceiveToComplete(void)

- ea: `0x1800c1438`
- end: `0x1800c14d8`
- name: `?WaitForReceiveToComplete@CImageSync@VMR9@@AEAAXXZ`
- size: `160`
- prototype: `void __fastcall(VMR9::CImageSync *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800c0590`
- `0x1800c0900`
- `0x1800e7270`
- `0x1800e7470`

## callees

- `0x1800c1438`

## import_xrefs

- `KERNEL32!Sleep` at `0x1800c1482`
- `KERNEL32!Sleep` at `0x1800c1482`
- `KERNEL32!GetCurrentThreadId` at `0x1800c14af`
- `KERNEL32!GetCurrentThreadId` at `0x1800c14af`
- `USER32!GetQueueStatus` at `0x1800c149c`
- `USER32!GetQueueStatus` at `0x1800c149c`
- `USER32!PeekMessageW` at `0x1800c1471`
- `USER32!PeekMessageW` at `0x1800c1471`
- `USER32!PostThreadMessageW` at `0x1800c14c5`
- `USER32!PostThreadMessageW` at `0x1800c14c5`

## pseudocode

```c
void __fastcall VMR9::CImageSync::WaitForReceiveToComplete(VMR9::CImageSync *this)
{
  DWORD CurrentThreadId; // eax
  struct tagMSG Msg; // [rsp+30h] [rbp-38h] BYREF

  while ( *((_DWORD *)this + 68) )
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
0x1800c1438  push    rbx
0x1800c143a  sub     rsp, 60h
0x1800c143e  cmp     dword ptr [rcx+110h], 0
0x1800c1445  mov     rbx, rcx
0x1800c1448  jz      short loc_1800C1497
0x1800c144a  xorps   xmm0, xmm0
0x1800c144d  mov     [rsp+68h+wRemoveMsg], 0; wRemoveMsg
0x1800c1455  xor     r9d, r9d; wMsgFilterMax
0x1800c1458  lea     rcx, [rsp+68h+Msg]; lpMsg
0x1800c145d  xor     r8d, r8d; wMsgFilterMin
0x1800c1460  xor     edx, edx; hWnd
0x1800c1462  movups  xmmword ptr [rsp+68h+Msg.hwnd], xmm0
0x1800c1467  movups  xmmword ptr [rsp+68h+Msg.wParam], xmm0
0x1800c146c  movups  xmmword ptr [rsp+68h+Msg.time], xmm0
0x1800c1471  call    cs:__imp_PeekMessageW
0x1800c1478  nop     dword ptr [rax+rax+00h]
0x1800c147d  mov     ecx, 1; dwMilliseconds
0x1800c1482  call    cs:__imp_Sleep
0x1800c1489  nop     dword ptr [rax+rax+00h]
0x1800c148e  cmp     dword ptr [rbx+110h], 0
0x1800c1495  jnz     short loc_1800C144A
0x1800c1497  mov     ecx, 8; flags
0x1800c149c  call    cs:__imp_GetQueueStatus
0x1800c14a3  nop     dword ptr [rax+rax+00h]
0x1800c14a8  shr     eax, 10h
0x1800c14ab  test    al, 8
0x1800c14ad  jz      short loc_1800C14D1
0x1800c14af  call    cs:__imp_GetCurrentThreadId
0x1800c14b6  nop     dword ptr [rax+rax+00h]
0x1800c14bb  xor     r9d, r9d; lParam
0x1800c14be  xor     r8d, r8d; wParam
0x1800c14c1  mov     ecx, eax; idThread
0x1800c14c3  xor     edx, edx; Msg
0x1800c14c5  call    cs:__imp_PostThreadMessageW
0x1800c14cc  nop     dword ptr [rax+rax+00h]
0x1800c14d1  add     rsp, 60h
0x1800c14d5  pop     rbx
0x1800c14d6  retn
```
