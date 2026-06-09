# CServerVCChannel::CreateStaticChannel(char const *,ulong)

- ea: `0x18001fd68`
- end: `0x18001fe87`
- name: `?CreateStaticChannel@CServerVCChannel@@QEAAJPEBDK@Z`
- size: `287`
- prototype: `__int64 __fastcall(CHAR *this, const char *, DWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180020078`

## callees

- `0x18001d04c`
- `0x18001ef44`
- `0x18001fd68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe28`
- `WTSAPI32!WTSFreeMemory` at `0x18001fe77`
- `WTSAPI32!WTSFreeMemory` at `0x18001fe77`
- `WTSAPI32!WTSVirtualChannelOpen` at `0x18001fd7e`
- `WTSAPI32!WTSVirtualChannelOpen` at `0x18001fd7e`
- `WTSAPI32!WTSVirtualChannelQuery` at `0x18001fe1e`
- `WTSAPI32!WTSVirtualChannelQuery` at `0x18001fe1e`

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
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
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
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 19;
LABEL_6:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      &WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
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
0x18001fd68  mov     [rsp+pBytesReturned], rdx
0x18001fd6d  push    rbx
0x18001fd6e  sub     rsp, 30h
0x18001fd72  mov     edx, r8d; SessionId
0x18001fd75  mov     rbx, rcx
0x18001fd78  lea     r8, [rcx+50h]; pVirtualName
0x18001fd7c  xor     ecx, ecx; hServer
0x18001fd7e  call    cs:__imp_WTSVirtualChannelOpen
0x18001fd84  mov     [rbx+160h], rax
0x18001fd8b  test    rax, rax
0x18001fd8e  jnz     short loc_18001FDFB
0x18001fd90  call    cs:__imp_GetLastError
0x18001fd96  mov     ebx, eax
0x18001fd98  mov     rax, cs:WPP_GLOBAL_Control
0x18001fd9f  lea     rcx, WPP_GLOBAL_Control
0x18001fda6  cmp     rax, rcx
0x18001fda9  jz      short loc_18001FDDF
0x18001fdab  test    byte ptr [rax+1Ch], 8
0x18001fdaf  jz      short loc_18001FDDF
0x18001fdb1  cmp     byte ptr [rax+19h], 2
0x18001fdb5  jb      short loc_18001FDDF
0x18001fdb7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001fdbc  mov     edx, 12h
0x18001fdc1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fdc8  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x18001fdcf  mov     r9d, eax
0x18001fdd2  mov     [rsp+38h+var_18], ebx
0x18001fdd6  mov     rcx, [rcx+10h]
0x18001fdda  call    WPP_SF_Dd
0x18001fddf  test    ebx, ebx
0x18001fde1  jle     short loc_18001FDEC
0x18001fde3  movzx   ebx, bx
0x18001fde6  or      ebx, 80070000h
0x18001fdec  test    ebx, ebx
0x18001fdee  mov     eax, 80004005h
0x18001fdf3  cmovns  ebx, eax
0x18001fdf6  jmp     loc_18001FE7F
0x18001fdfb  lea     r9, [rsp+38h+pBytesReturned]; pBytesReturned
0x18001fe00  mov     dword ptr [rsp+38h+pBytesReturned], 0
0x18001fe08  lea     r8, [rsp+38h+ppBuffer]; ppBuffer
0x18001fe0d  mov     [rsp+38h+ppBuffer], 0
0x18001fe16  mov     edx, 1; WTS_VIRTUAL_CLASS
0x18001fe1b  mov     rcx, rax; hChannelHandle
0x18001fe1e  call    cs:__imp_WTSVirtualChannelQuery
0x18001fe24  test    eax, eax
0x18001fe26  jnz     short loc_18001FE5E
0x18001fe28  call    cs:__imp_GetLastError
0x18001fe2e  mov     ebx, eax
0x18001fe30  mov     rax, cs:WPP_GLOBAL_Control
0x18001fe37  lea     rcx, WPP_GLOBAL_Control
0x18001fe3e  cmp     rax, rcx
0x18001fe41  jz      short loc_18001FDDF
0x18001fe43  test    byte ptr [rax+1Ch], 8
0x18001fe47  jz      short loc_18001FDDF
0x18001fe49  cmp     byte ptr [rax+19h], 2
0x18001fe4d  jb      short loc_18001FDDF
0x18001fe4f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001fe54  mov     edx, 13h
0x18001fe59  jmp     loc_18001FDC1
0x18001fe5e  mov     rcx, [rsp+38h+ppBuffer]; pMemory
0x18001fe63  mov     dword ptr [rbx+168h], 1
0x18001fe6d  mov     rax, [rcx]
0x18001fe70  mov     [rbx+158h], rax
0x18001fe77  call    cs:__imp_WTSFreeMemory
0x18001fe7d  xor     ebx, ebx
0x18001fe7f  mov     eax, ebx
0x18001fe81  add     rsp, 30h
0x18001fe85  pop     rbx
0x18001fe86  retn
```
