# CChallengeCallback::~CChallengeCallback(void)

- ea: `0x14001687c`
- end: `0x1400168c6`
- name: `??1CChallengeCallback@@IEAA@XZ`
- size: `74`
- prototype: `void __fastcall(CChallengeCallback *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140016c20`

## callees

- `0x140009090`
- `0x14001687c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400168bf`

## pseudocode

```c
void __fastcall CChallengeCallback::~CChallengeCallback(CChallengeCallback *this)
{
  void *v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &CChallengeCallback::`vftable'{for `IAepDevicePresenceChallengeCallback'};
  *((_QWORD *)this + 1) = &CChallengeCallback::`vftable'{for `IServiceProvider'};
  v2 = (void *)*((_QWORD *)this + 3);
  if ( v2 )
    MIDL_user_free(v2);
  v3 = (void *)*((_QWORD *)this + 4);
  if ( v3 )
    MIDL_user_free(v3);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
}

```

## disassembly

```asm
0x14001687c  push    rbx
0x14001687e  sub     rsp, 20h
0x140016882  lea     rax, ??_7CChallengeCallback@@6BIAepDevicePresenceChallengeCallback@@@; const CChallengeCallback::`vftable'{for `IAepDevicePresenceChallengeCallback'}
0x140016889  mov     rbx, rcx
0x14001688c  mov     [rcx], rax
0x14001688f  lea     rax, ??_7CChallengeCallback@@6BIServiceProvider@@@; const CChallengeCallback::`vftable'{for `IServiceProvider'}
0x140016896  mov     [rcx+8], rax
0x14001689a  mov     rcx, [rcx+18h]; void *
0x14001689e  test    rcx, rcx
0x1400168a1  jz      short loc_1400168A8
0x1400168a3  call    MIDL_user_free
0x1400168a8  mov     rcx, [rbx+20h]; void *
0x1400168ac  test    rcx, rcx
0x1400168af  jz      short loc_1400168B6
0x1400168b1  call    MIDL_user_free
0x1400168b6  lea     rcx, [rbx+30h]
0x1400168ba  add     rsp, 20h
0x1400168be  pop     rbx
0x1400168bf  jmp     cs:__imp_DeleteCriticalSection
```
