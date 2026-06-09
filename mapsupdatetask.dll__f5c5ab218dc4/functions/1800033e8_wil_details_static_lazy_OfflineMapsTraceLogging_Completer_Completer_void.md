# wil::details::static_lazy<OfflineMapsTraceLogging>::Completer::~Completer(void)

- ea: `0x1800033e8`
- end: `0x1800034bb`
- name: `??1Completer@?$static_lazy@VOfflineMapsTraceLogging@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800055b0`

## callees

- `0x180001be0`
- `0x1800033e8`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000349e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000349e`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000345e`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000345e`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180003476`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180003476`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<OfflineMapsTraceLogging>::Completer::~Completer(_DWORD *a1)
{
  __int64 v2; // rbx
  ULONGLONG *v3; // rsi
  bool v4; // zf
  __int64 v5; // rax
  GUID ProviderId; // [rsp+20h] [rbp-48h] BYREF

  if ( !a1[2] )
  {
    v2 = *(_QWORD *)a1;
    v3 = *(ULONGLONG **)(*(_QWORD *)a1 + 32LL);
    *(_QWORD *)(v2 + 16) = v3;
    *(_BYTE *)(v2 + 24) = 1;
    v4 = v3[4] == 0;
    ProviderId = *(GUID *)(v3[1] - 16);
    if ( !v4 )
      __fastfail(5u);
    v3[5] = 0;
    v3[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v3, v3 + 4) )
      EventSetInformation(
        v3[4],
        2,
        v3[1],
        *(unsigned __int16 *)v3[1],
        *(_QWORD *)&ProviderId.Data1,
        *(_QWORD *)ProviderId.Data4);
    v5 = *(_QWORD *)(v2 + 8);
    *(_DWORD *)(v2 + 28) = 1;
    (*(void (__fastcall **)(__int64))(v5 + 8))(v2 + 8);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x1800033e8  push    rbx
0x1800033ea  push    rsi
0x1800033eb  push    rdi
0x1800033ec  push    r14
0x1800033ee  sub     rsp, 48h
0x1800033f2  mov     rax, cs:__security_cookie
0x1800033f9  xor     rax, rsp
0x1800033fc  mov     [rsp+68h+var_38], rax
0x180003401  cmp     dword ptr [rcx+8], 0
0x180003405  mov     rdi, rcx
0x180003408  jnz     loc_180003494
0x18000340e  mov     rbx, [rcx]
0x180003411  mov     rsi, [rbx+20h]
0x180003415  mov     [rbx+10h], rsi
0x180003419  mov     byte ptr [rbx+18h], 1
0x18000341d  mov     rax, [rsi+8]
0x180003421  lea     r14, [rsi+20h]
0x180003425  cmp     qword ptr [r14], 0
0x180003429  movups  xmm0, xmmword ptr [rax-10h]
0x18000342d  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x180003433  jz      short loc_18000343C
0x180003435  mov     ecx, 5
0x18000343a  int     29h; Win8: RtlFailFast(ecx)
0x18000343c  mov     r9, r14; RegHandle
0x18000343f  mov     qword ptr [rsi+28h], 0
0x180003447  mov     r8, rsi; CallbackContext
0x18000344a  mov     qword ptr [rsi+30h], 0
0x180003452  lea     rdx, _tlgEnableCallback; EnableCallback
0x180003459  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x18000345e  call    cs:__imp_EventRegister
0x180003464  test    eax, eax
0x180003466  jnz     short loc_18000347C
0x180003468  mov     r8, [rsi+8]
0x18000346c  lea     edx, [rax+2]
0x18000346f  mov     rcx, [r14]
0x180003472  movzx   r9d, word ptr [r8]
0x180003476  call    cs:__imp_EventSetInformation
0x18000347c  mov     rax, [rbx+8]
0x180003480  lea     rcx, [rbx+8]
0x180003484  mov     dword ptr [rbx+1Ch], 1
0x18000348b  mov     rax, [rax+8]
0x18000348f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003494  mov     rcx, [rdi]; lpInitOnce
0x180003497  mov     edx, [rdi+8]; dwFlags
0x18000349a  lea     r8, [rcx+8]; lpContext
0x18000349e  call    cs:__imp_InitOnceComplete
0x1800034a4  mov     rcx, [rsp+68h+var_38]
0x1800034a9  xor     rcx, rsp; StackCookie
0x1800034ac  call    __security_check_cookie
0x1800034b1  add     rsp, 48h
0x1800034b5  pop     r14
0x1800034b7  pop     rdi
0x1800034b8  pop     rsi
0x1800034b9  pop     rbx
0x1800034ba  retn
```
