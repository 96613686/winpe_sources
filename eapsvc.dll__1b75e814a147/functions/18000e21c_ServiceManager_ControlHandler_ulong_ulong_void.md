# ServiceManager::ControlHandler(ulong,ulong,void *)

- ea: `0x18000e21c`
- end: `0x18000e2b3`
- name: `?ControlHandler@ServiceManager@@AEAAKKKPEAX@Z`
- size: `151`
- prototype: `__int64 __fastcall(HANDLE *this, int, unsigned int, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x18000e200`

## callees

- `0x18000d338`
- `0x18000e21c`
- `0x18000e3fc`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000e28c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000e28c`

## pseudocode

```c
__int64 __fastcall ServiceManager::ControlHandler(HANDLE *this, int a2, unsigned int a3, void *a4)
{
  unsigned int v4; // ebx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  const Exception *v10; // [rsp+20h] [rbp-18h] BYREF
  const Exception *v11; // [rsp+28h] [rbp-10h] BYREF

  v4 = 0;
  v5 = a2 - 1;
  if ( !v5 )
  {
LABEL_11:
    if ( !SetEvent(this[12]) )
      SystemError::Throw(L"SetEvent");
    return v4;
  }
  v6 = v5 - 3;
  if ( !v6 )
    return (unsigned int)ServiceManager::ReportStatusNoThrow((ServiceManager *)this, 0, 0);
  v7 = v6 - 1;
  if ( !v7 )
  {
    *((_BYTE *)this + 64) = 1;
    goto LABEL_11;
  }
  v8 = v7 - 8;
  if ( v8 )
  {
    if ( v8 != 1 )
      return 120;
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      (*((void (__fastcall **)(HANDLE *, _QWORD, void *))*this + 3))(this, a3, a4);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &Exception `RTTI Type Descriptor', &v10) )
      {
        v4 = (*(__int64 (__fastcall **)(const Exception *))(*(_QWORD *)v10 + 16LL))(v10);
        __eh34_try_continuation(0, &Exception `RTTI Type Descriptor', &loc_18000E262);
      }
    }
  }
  else
  {
    if ( !*((_BYTE *)this + 140) )
      return 120;
    if ( __eh34_try(-1, 2) )
    {
      __eh34_scope_strut(2);
      (*((void (__fastcall **)(HANDLE *, _QWORD, void *))*this + 4))(this, a3, a4);
    }
    if ( __eh34_catch(2) )
    {
      if ( __eh34_catch_type(2, &Exception `RTTI Type Descriptor', &v11) )
      {
        v4 = (*(__int64 (__fastcall **)(const Exception *))(*(_QWORD *)v11 + 16LL))(v11);
        __eh34_try_continuation(2, &Exception `RTTI Type Descriptor', &loc_18000E262);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000e21c  push    rbx
0x18000e21e  sub     rsp, 30h
0x18000e222  mov     r10d, r8d
0x18000e225  xor     ebx, ebx
0x18000e227  sub     edx, 1
0x18000e22a  jz      short loc_18000E288
0x18000e22c  sub     edx, 3
0x18000e22f  jz      short loc_18000E298
0x18000e231  sub     edx, 1
0x18000e234  jz      short loc_18000E284
0x18000e236  sub     edx, 8
0x18000e239  jz      short loc_18000E268
0x18000e23b  cmp     edx, 1
0x18000e23e  jz      short loc_18000E24D
0x18000e240  mov     ebx, 78h ; 'x'
0x18000e245  mov     eax, ebx
0x18000e247  add     rsp, 30h
0x18000e24b  pop     rbx
0x18000e24c  retn
0x18000e24d  mov     rax, [rcx]
0x18000e250  mov     r8, r9
0x18000e253  mov     edx, r10d
0x18000e256  mov     rax, [rax+18h]
0x18000e25a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e25f  nop
0x18000e260  jmp     short loc_18000E245
0x18000e262  mov     ebx, [rsp+38h+arg_8]
0x18000e266  jmp     short loc_18000E245
0x18000e268  cmp     [rcx+8Ch], bl
0x18000e26e  jz      short loc_18000E240
0x18000e270  mov     rax, [rcx]
0x18000e273  mov     r8, r9
0x18000e276  mov     edx, r10d
0x18000e279  mov     rax, [rax+20h]
0x18000e27d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e282  jmp     short loc_18000E260
0x18000e284  mov     byte ptr [rcx+40h], 1
0x18000e288  mov     rcx, [rcx+60h]; hEvent
0x18000e28c  call    cs:__imp_SetEvent
0x18000e292  test    eax, eax
0x18000e294  jz      short loc_18000E2A6
0x18000e296  jmp     short loc_18000E245
0x18000e298  xor     r8d, r8d; unsigned int
0x18000e29b  xor     edx, edx; unsigned int
0x18000e29d  call    ?ReportStatusNoThrow@ServiceManager@@AEAAKKK@Z; ServiceManager::ReportStatusNoThrow(ulong,ulong)
0x18000e2a2  mov     ebx, eax
0x18000e2a4  jmp     short loc_18000E245
0x18000e2a6  lea     rcx, aSetevent; "SetEvent"
0x18000e2ad  call    ?Throw@SystemError@@SAXPEB_W@Z; SystemError::Throw(wchar_t const *)
```
