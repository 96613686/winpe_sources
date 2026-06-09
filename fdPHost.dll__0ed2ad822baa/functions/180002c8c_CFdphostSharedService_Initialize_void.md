# CFdphostSharedService::Initialize(void *)

- ea: `0x180002c8c`
- end: `0x180002d3b`
- name: `?Initialize@CFdphostSharedService@@QEAAJPEAX@Z`
- size: `175`
- prototype: `__int64 __fastcall(CFdphostSharedService *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180001950`

## callees

- `0x180002c8c`
- `0x180002f84`
- `0x18000303c`

## import_xrefs

- `combase!__imp_CoGetSharedServiceId` at `0x180002cd3`
- `combase!__imp_CoGetSharedServiceId` at `0x180002cd3`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180002ce7`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180002ce7`

## pseudocode

```c
__int64 __fastcall CFdphostSharedService::Initialize(CFdphostSharedService *this, void *a2)
{
  HANDLE v2; // rsi
  struct CFdphostSharedService *v3; // rdi
  unsigned int SharedServiceId; // ebx
  unsigned int v5; // eax
  _QWORD *v6; // rcx
  bool v7; // cf

  v2 = g_hServiceStopEvent;
  v3 = g_pSharedService;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 24);
  SharedServiceId = CoGetSharedServiceId((char *)v3 + 24, a2);
  if ( SharedServiceId || (v5 = CoRegisterServerShutdownDelay(v2, 60000), (SharedServiceId = v5) != 0) )
  {
    v6 = WPP_GLOBAL_Control;
    v5 = 0;
    v7 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    v7 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u;
  }
  if ( v6 != &WPP_GLOBAL_Control )
  {
    LOBYTE(v5) = !v7;
    if ( v5 )
      WPP_SF_sqd(v6[2], 25);
  }
  return SharedServiceId;
}

```

## disassembly

```asm
0x180002c8c  push    rbx
0x180002c8e  push    rbp
0x180002c8f  push    rsi
0x180002c90  push    rdi
0x180002c91  sub     rsp, 38h
0x180002c95  mov     rsi, cs:?g_hServiceStopEvent@@3PEAXEA; void * g_hServiceStopEvent
0x180002c9c  mov     rdi, cs:?g_pSharedService@@3PEAVCFdphostSharedService@@EA; CFdphostSharedService * g_pSharedService
0x180002ca3  mov     rcx, cs:WPP_GLOBAL_Control
0x180002caa  lea     rbp, WPP_GLOBAL_Control
0x180002cb1  cmp     rcx, rbp
0x180002cb4  jz      short loc_180002CCF
0x180002cb6  cmp     byte ptr [rcx+19h], 4
0x180002cba  jb      short loc_180002CCF
0x180002cbc  mov     rcx, [rcx+10h]
0x180002cc0  mov     edx, 18h
0x180002cc5  mov     [rsp+58h+var_38], rdi
0x180002cca  call    WPP_SF_sq
0x180002ccf  lea     rcx, [rdi+18h]
0x180002cd3  call    cs:__imp_CoGetSharedServiceId
0x180002cd9  mov     ebx, eax
0x180002cdb  test    eax, eax
0x180002cdd  jnz     short loc_180002D00
0x180002cdf  mov     edx, 0EA60h
0x180002ce4  mov     rcx, rsi
0x180002ce7  call    cs:__imp_CoRegisterServerShutdownDelay
0x180002ced  mov     ebx, eax
0x180002cef  test    eax, eax
0x180002cf1  jnz     short loc_180002D00
0x180002cf3  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cfa  cmp     byte ptr [rcx+19h], 4
0x180002cfe  jmp     short loc_180002D0D
0x180002d00  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d07  xor     eax, eax
0x180002d09  cmp     byte ptr [rcx+19h], 2
0x180002d0d  setnb   al
0x180002d10  cmp     rcx, rbp
0x180002d13  jz      short loc_180002D30
0x180002d15  test    eax, eax
0x180002d17  jz      short loc_180002D30
0x180002d19  mov     rcx, [rcx+10h]
0x180002d1d  mov     edx, 19h
0x180002d22  mov     [rsp+58h+var_30], ebx
0x180002d26  mov     [rsp+58h+var_38], rdi
0x180002d2b  call    WPP_SF_sqd
0x180002d30  mov     eax, ebx
0x180002d32  add     rsp, 38h
0x180002d36  pop     rdi
0x180002d37  pop     rsi
0x180002d38  pop     rbp
0x180002d39  pop     rbx
0x180002d3a  retn
```
