# KsProxyCameraAccessHandler::Open(void *)

- ea: `0x10037680`
- end: `0x10037715`
- name: `?Open@KsProxyCameraAccessHandler@@UAGJPAX@Z`
- size: `149`
- prototype: `int(KsProxyCameraAccessHandler *__hidden this, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x100075ad`
- `0x1002d510`
- `0x10037680`
- `0x10037eb2`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10037706`
- `KERNEL32!LeaveCriticalSection` at `0x10037706`
- `KERNEL32!EnterCriticalSection` at `0x100376ad`
- `KERNEL32!EnterCriticalSection` at `0x100376ad`

## string_xrefs

- `0x10037695`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\ksproxycameraaccesshandler.cpp`
- `0x100376f3`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\ksproxycameraaccesshandler.cpp`

## pseudocode

```c

```

## disassembly

```asm
0x10037680  mov     edi, edi
0x10037682  push    ebp; char *
0x10037683  mov     ebp, esp
0x10037685  cmp     [ebp+arg_4], 0
0x10037689  push    esi; int
0x1003768a  jnz     short loc_100376A4
0x1003768c  mov     ecx, [ebp+4]
0x1003768f  mov     esi, 80070057h
0x10037694  push    esi; void *
0x10037695  push    offset aMultimediaDsho_2; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x1003769a  push    2Ah ; '*'
0x1003769c  pop     edx
0x1003769d  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x100376a2  jmp     short loc_1003770E
0x100376a4  mov     esi, [ebp+this]
0x100376a7  push    ebx; char *
0x100376a8  push    edi; unsigned int
0x100376a9  lea     edi, [esi+10h]
0x100376ac  push    edi; lpCriticalSection
0x100376ad  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100376b3  lea     ebx, [esi+0Ch]
0x100376b6  cmp     dword ptr [ebx], 0
0x100376b9  jnz     short loc_100376D4
0x100376bb  mov     edx, [ebp+arg_4]
0x100376be  push    ebx
0x100376bf  mov     dword ptr [ebx], 0
0x100376c5  call    ?CreateInstance@ThreadProcHelper@@SGJW4ThreadProcWorkType@@PAXPAPAUIThreadProcHelper@@@Z; ThreadProcHelper::CreateInstance(ThreadProcWorkType,void *,IThreadProcHelper * *)
0x100376ca  mov     esi, eax
0x100376cc  test    esi, esi
0x100376ce  jns     short loc_100376D4
0x100376d0  push    33h ; '3'
0x100376d2  jmp     short loc_100376EE
0x100376d4  mov     eax, [ebx]
0x100376d6  push    eax
0x100376d7  mov     ecx, [eax]
0x100376d9  mov     esi, [ecx+0Ch]
0x100376dc  mov     ecx, esi; this
0x100376de  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100376e4  call    esi
0x100376e6  mov     esi, eax
0x100376e8  test    esi, esi
0x100376ea  jns     short loc_100376FF
0x100376ec  push    36h ; '6'
0x100376ee  mov     ecx, [ebp+4]
0x100376f1  pop     edx
0x100376f2  push    esi; void *
0x100376f3  push    offset aMultimediaDsho_2; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x100376f8  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x100376fd  jmp     short loc_10037701
0x100376ff  xor     esi, esi
0x10037701  test    edi, edi
0x10037703  jz      short loc_1003770C
0x10037705  push    edi; lpCriticalSection
0x10037706  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1003770c  pop     edi
0x1003770d  pop     ebx
0x1003770e  mov     eax, esi
0x10037710  pop     esi
0x10037711  pop     ebp
0x10037712  retn    8
```
