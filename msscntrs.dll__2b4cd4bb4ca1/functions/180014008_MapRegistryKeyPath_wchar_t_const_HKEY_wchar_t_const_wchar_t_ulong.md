# MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)

- ea: `0x180014008`
- end: `0x1800140d2`
- name: `?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z`
- size: `202`
- prototype: `bool __fastcall(const wchar_t *, HKEY, const wchar_t *, wchar_t *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800142d8`
- `0x180014394`

## callees

- `0x180014008`
- `0x1800140d8`
- `0x180014480`
- `0x1800156a4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180014098`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180014098`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001402f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001402f`

## pseudocode

```c
bool __fastcall MapRegistryKeyPath(const wchar_t *a1, HKEY a2, const wchar_t *a3, wchar_t *a4)
{
  unsigned int v6; // ebx
  __int64 v7; // rdi
  unsigned int v8; // r9d

  if ( a2 != HKEY_LOCAL_MACHINE || !a3 || !(unsigned __int8)RtlIsStateSeparationEnabled(a1) )
    return 0;
  v6 = 0;
  while ( 1 )
  {
    v7 = v6;
    if ( !wcscmp_0(off_1800212E0[69 * v6], L"WSearch") )
      break;
    if ( ++v6 >= 2 )
    {
      v7 = 2;
      goto LABEL_9;
    }
  }
  if ( v6 < 2uLL )
    return InitOnceExecuteOnce(
             (PINIT_ONCE)&qword_180022388[v7],
             lambda_cd2099a84e29dd60a3ce15c92771ff9c_::_lambda_invoker_cdecl_,
             (PVOID)v7,
             0)
        && CSearchRegistryRedirectHelper::MapRegistryKeyPath(
             (CSearchRegistryRedirectHelper *)&qword_1800212F8[69 * v7],
             a3,
             a4,
             v8) >= 0;
LABEL_9:
  MicrosoftTelemetryAssertTriggeredNoArgs();
  return InitOnceExecuteOnce(
           (PINIT_ONCE)&qword_180022388[v7],
           lambda_cd2099a84e29dd60a3ce15c92771ff9c_::_lambda_invoker_cdecl_,
           (PVOID)v7,
           0)
      && CSearchRegistryRedirectHelper::MapRegistryKeyPath(
           (CSearchRegistryRedirectHelper *)&qword_1800212F8[69 * v7],
           a3,
           a4,
           v8) >= 0;
}

```

## disassembly

```asm
0x180014008  push    rbx
0x18001400a  push    rbp
0x18001400b  push    rsi
0x18001400c  push    rdi
0x18001400d  push    r14
0x18001400f  sub     rsp, 20h
0x180014013  mov     rbp, r9
0x180014016  mov     rsi, r8
0x180014019  cmp     rdx, 0FFFFFFFF80000002h
0x180014020  jnz     loc_1800140C5
0x180014026  test    r8, r8
0x180014029  jz      loc_1800140C5
0x18001402f  call    cs:__imp_RtlIsStateSeparationEnabled
0x180014035  test    al, al
0x180014037  jz      loc_1800140C5
0x18001403d  xor     ebx, ebx
0x18001403f  lea     r14, cs:180000000h
0x180014046  mov     edi, ebx
0x180014048  lea     rdx, aWsearch; "WSearch"
0x18001404f  imul    rcx, rdi, 228h
0x180014056  mov     rcx, [rcx+r14+212E0h]; String1
0x18001405e  call    wcscmp_0
0x180014063  test    eax, eax
0x180014065  jz      short loc_180014075
0x180014067  inc     ebx
0x180014069  cmp     ebx, 2
0x18001406c  jb      short loc_180014046
0x18001406e  mov     edi, 2
0x180014073  jmp     short loc_18001407B
0x180014075  cmp     rdi, 2
0x180014079  jb      short loc_180014080
0x18001407b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180014080  lea     rcx, rva qword_180022388[r14]
0x180014087  xor     r9d, r9d; Context
0x18001408a  lea     rcx, [rcx+rdi*8]; InitOnce
0x18001408e  mov     r8, rdi; Parameter
0x180014091  lea     rdx, _lambda_cd2099a84e29dd60a3ce15c92771ff9c____lambda_invoker_cdecl_; InitFn
0x180014098  call    cs:__imp_InitOnceExecuteOnce
0x18001409e  test    eax, eax
0x1800140a0  jz      short loc_1800140C5
0x1800140a2  lea     rax, qword_1800212F8
0x1800140a9  mov     r8, rbp; wchar_t *
0x1800140ac  imul    rcx, rdi, 228h
0x1800140b3  mov     rdx, rsi; wchar_t *
0x1800140b6  add     rcx, rax; this
0x1800140b9  call    ?MapRegistryKeyPath@CSearchRegistryRedirectHelper@@QEAAJPEB_WPEA_WK@Z; CSearchRegistryRedirectHelper::MapRegistryKeyPath(wchar_t const *,wchar_t *,ulong)
0x1800140be  test    eax, eax
0x1800140c0  setns   al
0x1800140c3  jmp     short loc_1800140C7
0x1800140c5  xor     al, al
0x1800140c7  add     rsp, 20h
0x1800140cb  pop     r14
0x1800140cd  pop     rdi
0x1800140ce  pop     rsi
0x1800140cf  pop     rbp
0x1800140d0  pop     rbx
0x1800140d1  retn
```
