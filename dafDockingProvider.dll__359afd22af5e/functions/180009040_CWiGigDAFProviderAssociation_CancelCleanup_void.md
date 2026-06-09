# CWiGigDAFProviderAssociation::CancelCleanup(void)

- ea: `0x180009040`
- end: `0x18000909f`
- name: `?CancelCleanup@CWiGigDAFProviderAssociation@@AEAAJXZ`
- size: `95`
- prototype: `__int64 __fastcall(HANDLE *this)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180008ac0`
- `0x1800093c0`
- `0x180009660`
- `0x18000a428`
- `0x18000a810`
- `0x18000af40`
- `0x18000b660`

## callees

- `0x180009040`
- `0x18000c308`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009084`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009084`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000908e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000908e`

## pseudocode

```c
__int64 __fastcall CWiGigDAFProviderAssociation::CancelCleanup(HANDLE *this)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 152, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
  }
  if ( !SetEvent(this[8]) )
    GetLastError();
  return 2147943623LL;
}

```

## disassembly

```asm
0x180009040  push    rbx
0x180009042  sub     rsp, 20h
0x180009046  mov     rbx, rcx
0x180009049  mov     rcx, cs:WPP_GLOBAL_Control
0x180009050  lea     rax, WPP_GLOBAL_Control
0x180009057  cmp     rcx, rax
0x18000905a  jz      short loc_180009080
0x18000905c  cmp     byte ptr [rcx+19h], 3
0x180009060  jb      short loc_180009080
0x180009062  test    byte ptr [rcx+1Ch], 1
0x180009066  jz      short loc_180009080
0x180009068  mov     rcx, [rcx+10h]
0x18000906c  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x180009073  mov     edx, 98h
0x180009078  mov     r9, rbx
0x18000907b  call    WPP_SF_q
0x180009080  mov     rcx, [rbx+40h]; hEvent
0x180009084  call    cs:__imp_SetEvent
0x18000908a  test    eax, eax
0x18000908c  jnz     short loc_180009094
0x18000908e  call    cs:__imp_GetLastError
0x180009094  mov     eax, 800704C7h
0x180009099  add     rsp, 20h
0x18000909d  pop     rbx
0x18000909e  retn
```
