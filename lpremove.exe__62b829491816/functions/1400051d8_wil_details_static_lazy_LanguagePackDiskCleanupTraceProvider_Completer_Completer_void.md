# wil::details::static_lazy<LanguagePackDiskCleanupTraceProvider>::Completer::~Completer(void)

- ea: `0x1400051d8`
- end: `0x1400052ab`
- name: `??1Completer@?$static_lazy@VLanguagePackDiskCleanupTraceProvider@@@details@wil@@QEAA@XZ`
- size: `211`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140007eac`

## callees

- `0x140002190`
- `0x1400051d8`
- `0x140011010`

## import_xrefs

- `ADVAPI32!EventRegister` at `0x14000524e`
- `ADVAPI32!EventRegister` at `0x14000524e`
- `ADVAPI32!EventSetInformation` at `0x140005266`
- `ADVAPI32!EventSetInformation` at `0x140005266`
- `KERNEL32!InitOnceComplete` at `0x14000528e`
- `KERNEL32!InitOnceComplete` at `0x14000528e`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<LanguagePackDiskCleanupTraceProvider>::Completer::~Completer(_DWORD *a1)
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
0x1400051d8  push    rbx
0x1400051da  push    rsi
0x1400051db  push    rdi
0x1400051dc  push    r14
0x1400051de  sub     rsp, 48h
0x1400051e2  mov     rax, cs:__security_cookie
0x1400051e9  xor     rax, rsp
0x1400051ec  mov     [rsp+68h+var_38], rax
0x1400051f1  cmp     dword ptr [rcx+8], 0
0x1400051f5  mov     rdi, rcx
0x1400051f8  jnz     loc_140005284
0x1400051fe  mov     rbx, [rcx]
0x140005201  mov     rsi, [rbx+20h]
0x140005205  mov     [rbx+10h], rsi
0x140005209  mov     byte ptr [rbx+18h], 1
0x14000520d  mov     rax, [rsi+8]
0x140005211  lea     r14, [rsi+20h]
0x140005215  cmp     qword ptr [r14], 0
0x140005219  movups  xmm0, xmmword ptr [rax-10h]
0x14000521d  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x140005223  jz      short loc_14000522C
0x140005225  mov     ecx, 5
0x14000522a  int     29h; Win8: RtlFailFast(ecx)
0x14000522c  mov     r9, r14; RegHandle
0x14000522f  mov     qword ptr [rsi+28h], 0
0x140005237  mov     r8, rsi; CallbackContext
0x14000523a  mov     qword ptr [rsi+30h], 0
0x140005242  lea     rdx, _tlgEnableCallback; EnableCallback
0x140005249  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x14000524e  call    cs:__imp_EventRegister
0x140005254  test    eax, eax
0x140005256  jnz     short loc_14000526C
0x140005258  mov     r8, [rsi+8]
0x14000525c  lea     edx, [rax+2]
0x14000525f  mov     rcx, [r14]
0x140005262  movzx   r9d, word ptr [r8]
0x140005266  call    cs:__imp_EventSetInformation
0x14000526c  mov     rax, [rbx+8]
0x140005270  lea     rcx, [rbx+8]
0x140005274  mov     dword ptr [rbx+1Ch], 1
0x14000527b  mov     rax, [rax+8]
0x14000527f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005284  mov     rcx, [rdi]; lpInitOnce
0x140005287  mov     edx, [rdi+8]; dwFlags
0x14000528a  lea     r8, [rcx+8]; lpContext
0x14000528e  call    cs:__imp_InitOnceComplete
0x140005294  mov     rcx, [rsp+68h+var_38]
0x140005299  xor     rcx, rsp; StackCookie
0x14000529c  call    __security_check_cookie
0x1400052a1  add     rsp, 48h
0x1400052a5  pop     r14
0x1400052a7  pop     rdi
0x1400052a8  pop     rsi
0x1400052a9  pop     rbx
0x1400052aa  retn
```
