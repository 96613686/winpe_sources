# CServerVCChannel::CreateStaticChannel(char const *,ulong)

- ea: `0x140026048`
- end: `0x140026167`
- name: `?CreateStaticChannel@CServerVCChannel@@QEAAJPEBDK@Z`
- size: `287`
- prototype: `int(CServerVCChannel *__hidden this, const char *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140026358`

## callees

- `0x140004b1c`
- `0x140005704`
- `0x140026048`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026070`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026108`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026070`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026108`
- `WTSAPI32!WTSFreeMemory` at `0x140026157`
- `WTSAPI32!WTSFreeMemory` at `0x140026157`
- `WTSAPI32!WTSVirtualChannelOpen` at `0x14002605e`
- `WTSAPI32!WTSVirtualChannelOpen` at `0x14002605e`
- `WTSAPI32!WTSVirtualChannelQuery` at `0x1400260fe`
- `WTSAPI32!WTSVirtualChannelQuery` at `0x1400260fe`

## pseudocode

```c
__int64 __fastcall CServerVCChannel::CreateStaticChannel(CHAR *this, const char *a2, DWORD a3)
{
  HANDLE v4; // rax
  signed int LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v7; // rdx
  _QWORD *v8; // rcx
  PVOID ppBuffer; // [rsp+40h] [rbp+8h] BYREF
  const char *pBytesReturned; // [rsp+48h] [rbp+10h] BYREF

  pBytesReturned = a2;
  v4 = WTSVirtualChannelOpen(0, a3, this + 80);
  *((_QWORD *)this + 44) = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 18;
    goto LABEL_6;
  }
  LODWORD(pBytesReturned) = 0;
  ppBuffer = 0;
  if ( WTSVirtualChannelQuery(v4, WTSVirtualFileHandle, &ppBuffer, (DWORD *)&pBytesReturned) )
  {
    v8 = ppBuffer;
    *((_DWORD *)this + 90) = 1;
    *((_QWORD *)this + 43) = *v8;
    WTSFreeMemory(v8);
    return 0;
  }
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 19;
LABEL_6:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
      CurrentThreadActivityIdPrefix,
      LastError);
  }
LABEL_7:
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError >= 0 )
    return (unsigned int)-2147467259;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140026048  mov     [rsp+pBytesReturned], rdx
0x14002604d  push    rbx
0x14002604e  sub     rsp, 30h
0x140026052  mov     edx, r8d; SessionId
0x140026055  mov     rbx, rcx
0x140026058  lea     r8, [rcx+50h]; pVirtualName
0x14002605c  xor     ecx, ecx; hServer
0x14002605e  call    cs:__imp_WTSVirtualChannelOpen
0x140026064  mov     [rbx+160h], rax
0x14002606b  test    rax, rax
0x14002606e  jnz     short loc_1400260DB
0x140026070  call    cs:__imp_GetLastError
0x140026076  mov     ebx, eax
0x140026078  mov     rax, cs:WPP_GLOBAL_Control
0x14002607f  lea     rcx, WPP_GLOBAL_Control
0x140026086  cmp     rax, rcx
0x140026089  jz      short loc_1400260BF
0x14002608b  test    byte ptr [rax+1Ch], 8
0x14002608f  jz      short loc_1400260BF
0x140026091  cmp     byte ptr [rax+19h], 2
0x140026095  jb      short loc_1400260BF
0x140026097  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14002609c  mov     edx, 12h
0x1400260a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400260a8  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x1400260af  mov     r9d, eax
0x1400260b2  mov     [rsp+38h+var_18], ebx
0x1400260b6  mov     rcx, [rcx+10h]
0x1400260ba  call    WPP_SF_Dd
0x1400260bf  test    ebx, ebx
0x1400260c1  jle     short loc_1400260CC
0x1400260c3  movzx   ebx, bx
0x1400260c6  or      ebx, 80070000h
0x1400260cc  test    ebx, ebx
0x1400260ce  mov     eax, 80004005h
0x1400260d3  cmovns  ebx, eax
0x1400260d6  jmp     loc_14002615F
0x1400260db  lea     r9, [rsp+38h+pBytesReturned]; pBytesReturned
0x1400260e0  mov     dword ptr [rsp+38h+pBytesReturned], 0
0x1400260e8  lea     r8, [rsp+38h+ppBuffer]; ppBuffer
0x1400260ed  mov     [rsp+38h+ppBuffer], 0
0x1400260f6  mov     edx, 1; WTS_VIRTUAL_CLASS
0x1400260fb  mov     rcx, rax; hChannelHandle
0x1400260fe  call    cs:__imp_WTSVirtualChannelQuery
0x140026104  test    eax, eax
0x140026106  jnz     short loc_14002613E
0x140026108  call    cs:__imp_GetLastError
0x14002610e  mov     ebx, eax
0x140026110  mov     rax, cs:WPP_GLOBAL_Control
0x140026117  lea     rcx, WPP_GLOBAL_Control
0x14002611e  cmp     rax, rcx
0x140026121  jz      short loc_1400260BF
0x140026123  test    byte ptr [rax+1Ch], 8
0x140026127  jz      short loc_1400260BF
0x140026129  cmp     byte ptr [rax+19h], 2
0x14002612d  jb      short loc_1400260BF
0x14002612f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140026134  mov     edx, 13h
0x140026139  jmp     loc_1400260A1
0x14002613e  mov     rcx, [rsp+38h+ppBuffer]; pMemory
0x140026143  mov     dword ptr [rbx+168h], 1
0x14002614d  mov     rax, [rcx]
0x140026150  mov     [rbx+158h], rax
0x140026157  call    cs:__imp_WTSFreeMemory
0x14002615d  xor     ebx, ebx
0x14002615f  mov     eax, ebx
0x140026161  add     rsp, 30h
0x140026165  pop     rbx
0x140026166  retn
```
