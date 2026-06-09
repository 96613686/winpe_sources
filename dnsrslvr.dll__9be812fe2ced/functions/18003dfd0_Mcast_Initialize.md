# Mcast_Initialize

- ea: `0x18003dfd0`
- end: `0x18003e1cd`
- name: `Mcast_Initialize`
- size: `509`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001c550`

## callees

- `0x18001cc2c`
- `0x18001cd24`
- `0x18003dfd0`
- `0x18003e1d4`
- `0x18004b858`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e0e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e138`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e0e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e138`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003e0c5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003e0c5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003e17a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003e17a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003e126`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003e126`

## pseudocode

```c
__int64 Mcast_Initialize()
{
  unsigned int v0; // eax
  unsigned int v1; // ebx
  __int64 v2; // rdx
  DWORD LastError; // eax
  DWORD v4; // eax

  if ( (BYTE2(xmmword_1800AB5A0) & 1) != 0 )
    WPP_SF_(1040, 78, WPP_85ecdf2cec3f31b172fd057429574cdd_Traceguids);
  if ( g_pMcastNetInfoCopy || g_pMcastInfo || g_ResponderStop || g_hResponderThread )
    Mcast_Destroy();
  if ( g_fVelocityNetinfoCleanup )
  {
    v0 = GrabNetworkInfo(0, &g_pMcastNetInfoCopy, 0);
    v1 = v0;
    if ( v0 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      {
        v2 = 79;
LABEL_28:
        WPP_SF_d(1035, v2, WPP_85ecdf2cec3f31b172fd057429574cdd_Traceguids, v0);
        goto LABEL_29;
      }
      goto LABEL_29;
    }
  }
  else
  {
    v0 = GrabNetworkInfoOld(0, 1, &g_pMcastNetInfoCopy, 0);
    v1 = v0;
    if ( v0 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      {
        v2 = 80;
        goto LABEL_28;
      }
LABEL_29:
      Mcast_Destroy();
      goto LABEL_30;
    }
  }
  v1 = Mcast_Build(&g_pMcastInfo, g_pMcastNetInfoCopy, 0);
  if ( v1 )
    goto LABEL_29;
  if ( !g_pMcastInfo )
    goto LABEL_30;
  g_McastVerifyInfo = (__int128)_mm_load_si128((const __m128i *)&_xmm);
  g_ResponderStop = CreateEventW(0, 1, 0, 0);
  if ( !g_ResponderStop )
  {
    v1 = 14;
    if ( SBYTE3(xmmword_1800AB5A0) < 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(1055, 81, WPP_85ecdf2cec3f31b172fd057429574cdd_Traceguids, LastError);
    }
    goto LABEL_29;
  }
  g_hResponderThread = CreateThread(0, 0, Responder_Thread, 0, 0, &g_ResponderThreadId);
  if ( g_hResponderThread )
  {
    if ( g_hMcastThread && g_McastVerify )
      SetEvent(g_McastVerify);
  }
  else
  {
    v4 = GetLastError();
    v1 = v4;
    if ( SBYTE3(xmmword_1800AB5A0) < 0 )
      WPP_SF_d(1055, 82, WPP_85ecdf2cec3f31b172fd057429574cdd_Traceguids, v4);
    if ( v1 )
      goto LABEL_29;
  }
LABEL_30:
  if ( (BYTE2(xmmword_1800AB5A0) & 1) != 0 )
    WPP_SF_(1040, 83, WPP_85ecdf2cec3f31b172fd057429574cdd_Traceguids);
  return v1;
}

```

## disassembly

```asm
0x18003dfd0  mov     [rsp+arg_0], rbx
0x18003dfd5  push    rsi
0x18003dfd6  sub     rsp, 30h
0x18003dfda  test    byte ptr cs:xmmword_1800AB5A0+2, 1
0x18003dfe1  lea     rsi, WPP_85ecdf2cec3f31b172fd057429574cdd_Traceguids
0x18003dfe8  jz      short loc_18003DFFC
0x18003dfea  mov     edx, 4Eh ; 'N'
0x18003dfef  mov     ecx, 410h
0x18003dff4  mov     r8, rsi
0x18003dff7  call    WPP_SF_
0x18003dffc  cmp     cs:g_pMcastNetInfoCopy, 0
0x18003e004  jnz     short loc_18003E024
0x18003e006  cmp     cs:g_pMcastInfo, 0
0x18003e00e  jnz     short loc_18003E024
0x18003e010  cmp     cs:g_ResponderStop, 0
0x18003e018  jnz     short loc_18003E024
0x18003e01a  cmp     cs:g_hResponderThread, 0
0x18003e022  jz      short loc_18003E029
0x18003e024  call    Mcast_Destroy
0x18003e029  xor     ecx, ecx
0x18003e02b  cmp     cs:g_fVelocityNetinfoCleanup, ecx
0x18003e031  jz      short loc_18003E05F
0x18003e033  xor     r8d, r8d
0x18003e036  lea     rdx, g_pMcastNetInfoCopy
0x18003e03d  call    GrabNetworkInfo
0x18003e042  mov     ebx, eax
0x18003e044  test    eax, eax
0x18003e046  jz      short loc_18003E07C
0x18003e048  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003e04f  jz      loc_18003E1A0
0x18003e055  mov     edx, 4Fh ; 'O'
0x18003e05a  jmp     loc_18003E190
0x18003e05f  xor     r9d, r9d
0x18003e062  lea     r8, g_pMcastNetInfoCopy
0x18003e069  lea     edx, [r9+1]
0x18003e06d  call    GrabNetworkInfoOld
0x18003e072  mov     ebx, eax
0x18003e074  test    eax, eax
0x18003e076  jnz     loc_18003E182
0x18003e07c  mov     rdx, cs:g_pMcastNetInfoCopy
0x18003e083  lea     rcx, g_pMcastInfo
0x18003e08a  xor     r8d, r8d
0x18003e08d  call    Mcast_Build
0x18003e092  mov     ebx, eax
0x18003e094  test    eax, eax
0x18003e096  jnz     loc_18003E1A0
0x18003e09c  cmp     cs:g_pMcastInfo, 0
0x18003e0a4  jz      loc_18003E1A5
0x18003e0aa  movdqa  xmm0, cs:__xmm@00000000000000010000000000000000
0x18003e0b2  lea     edx, [rax+1]; bManualReset
0x18003e0b5  xor     r9d, r9d; lpName
0x18003e0b8  xor     r8d, r8d; bInitialState
0x18003e0bb  xor     ecx, ecx; lpEventAttributes
0x18003e0bd  movdqu  cs:g_McastVerifyInfo, xmm0
0x18003e0c5  call    cs:__imp_CreateEventW
0x18003e0cb  mov     cs:g_ResponderStop, rax
0x18003e0d2  test    rax, rax
0x18003e0d5  jnz     short loc_18003E104
0x18003e0d7  lea     ebx, [rax+0Eh]
0x18003e0da  cmp     byte ptr cs:xmmword_1800AB5A0+3, al
0x18003e0e0  jge     loc_18003E1A0
0x18003e0e6  call    cs:__imp_GetLastError
0x18003e0ec  lea     edx, [rbx+43h]
0x18003e0ef  mov     ecx, 41Fh
0x18003e0f4  mov     r9d, eax
0x18003e0f7  mov     r8, rsi
0x18003e0fa  call    WPP_SF_d
0x18003e0ff  jmp     loc_18003E1A0
0x18003e104  lea     rax, g_ResponderThreadId
0x18003e10b  xor     r9d, r9d; lpParameter
0x18003e10e  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18003e113  lea     r8, Responder_Thread; lpStartAddress
0x18003e11a  xor     edx, edx; dwStackSize
0x18003e11c  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18003e124  xor     ecx, ecx; lpThreadAttributes
0x18003e126  call    cs:__imp_CreateThread
0x18003e12c  mov     cs:g_hResponderThread, rax
0x18003e133  test    rax, rax
0x18003e136  jnz     short loc_18003E164
0x18003e138  call    cs:__imp_GetLastError
0x18003e13e  mov     ebx, eax
0x18003e140  cmp     byte ptr cs:xmmword_1800AB5A0+3, 0
0x18003e147  jge     short loc_18003E15E
0x18003e149  mov     edx, 52h ; 'R'
0x18003e14e  mov     ecx, 41Fh
0x18003e153  mov     r9d, eax
0x18003e156  mov     r8, rsi
0x18003e159  call    WPP_SF_d
0x18003e15e  test    ebx, ebx
0x18003e160  jnz     short loc_18003E1A0
0x18003e162  jmp     short loc_18003E1A5
0x18003e164  cmp     cs:g_hMcastThread, 0
0x18003e16c  jz      short loc_18003E1A5
0x18003e16e  mov     rcx, cs:g_McastVerify; hEvent
0x18003e175  test    rcx, rcx
0x18003e178  jz      short loc_18003E1A5
0x18003e17a  call    cs:__imp_SetEvent
0x18003e180  jmp     short loc_18003E1A5
0x18003e182  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18003e189  jz      short loc_18003E1A0
0x18003e18b  mov     edx, 50h ; 'P'
0x18003e190  mov     r9d, eax
0x18003e193  mov     r8, rsi
0x18003e196  mov     ecx, 40Bh
0x18003e19b  call    WPP_SF_d
0x18003e1a0  call    Mcast_Destroy
0x18003e1a5  test    byte ptr cs:xmmword_1800AB5A0+2, 1
0x18003e1ac  jz      short loc_18003E1C0
0x18003e1ae  mov     edx, 53h ; 'S'
0x18003e1b3  mov     ecx, 410h
0x18003e1b8  mov     r8, rsi
0x18003e1bb  call    WPP_SF_
0x18003e1c0  mov     eax, ebx
0x18003e1c2  mov     rbx, [rsp+38h+arg_0]
0x18003e1c7  add     rsp, 30h
0x18003e1cb  pop     rsi
0x18003e1cc  retn
```
