# CQueryCallback::OnQueryStateUpdate(_DEV_QUERY_STATE)

- ea: `0x1400173a0`
- end: `0x14001743c`
- name: `?OnQueryStateUpdate@CQueryCallback@@UEAAJW4_DEV_QUERY_STATE@@@Z`
- size: `156`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140017450`
- `0x140017460`

## callees

- `0x14000a268`
- `0x1400173a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14001742b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x14001742b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400173d6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400173d6`

## pseudocode

```c
__int64 __fastcall CQueryCallback::OnQueryStateUpdate(__int64 a1, unsigned int a2)
{
  int v2; // r8d
  unsigned int StateUpdateStub; // ebx
  int v6; // r8d
  __int64 v7; // rdx

  v2 = *(_DWORD *)(a1 + 108);
  StateUpdateStub = 0;
  if ( v2 )
  {
    v6 = v2 - 1;
    if ( v6 )
    {
      if ( v6 != 1 )
      {
LABEL_5:
        if ( !a2 || StateUpdateStub )
          return StateUpdateStub;
        goto LABEL_7;
      }
    }
    else if ( (*(_DWORD *)(a1 + 92) & 1) != 0 )
    {
      StateUpdateStub = a2 != 2 ? 0x80640015 : 0;
      goto LABEL_5;
    }
    StateUpdateStub = -2140930027;
    goto LABEL_5;
  }
  if ( !a2 )
    return StateUpdateStub;
  if ( a2 - 1 > 1 )
    return (unsigned int)-2140930027;
LABEL_7:
  AcquireSRWLockShared((PSRWLOCK)(a1 + 96));
  if ( *(_DWORD *)(a1 + 104) )
  {
    StateUpdateStub = OnQueryStateUpdateStub(a2, v7, *(_QWORD *)(a1 + 48));
    *(_DWORD *)(a1 + 108) = a2;
  }
  else
  {
    StateUpdateStub = -2140930029;
  }
  ReleaseSRWLockShared((PSRWLOCK)(a1 + 96));
  return StateUpdateStub;
}

```

## disassembly

```asm
0x1400173a0  push    rbx
0x1400173a2  push    rbp
0x1400173a3  push    rsi
0x1400173a4  push    rdi
0x1400173a5  sub     rsp, 28h
0x1400173a9  mov     r8d, [rcx+6Ch]
0x1400173ad  xor     ebx, ebx
0x1400173af  mov     esi, edx
0x1400173b1  mov     rdi, rcx
0x1400173b4  test    r8d, r8d
0x1400173b7  jz      short loc_14001740F
0x1400173b9  sub     r8d, 1
0x1400173bd  jz      short loc_1400173F4
0x1400173bf  cmp     r8d, 1
0x1400173c3  jnz     short loc_1400173CA
0x1400173c5  mov     ebx, 80640015h
0x1400173ca  test    esi, esi
0x1400173cc  jz      short loc_140017431
0x1400173ce  test    ebx, ebx
0x1400173d0  jnz     short loc_140017431
0x1400173d2  add     rcx, 60h ; '`'; SRWLock
0x1400173d6  call    cs:__imp_AcquireSRWLockShared
0x1400173dc  cmp     dword ptr [rdi+68h], 0
0x1400173e0  jz      short loc_140017422
0x1400173e2  mov     r8, [rdi+30h]
0x1400173e6  mov     ecx, esi
0x1400173e8  call    ?OnQueryStateUpdateStub@@YAJW4_DEV_QUERY_STATE@@W4_DAF_SECONDARY_QUERY_STATE@@PEAX@Z; OnQueryStateUpdateStub(_DEV_QUERY_STATE,_DAF_SECONDARY_QUERY_STATE,void *)
0x1400173ed  mov     ebx, eax
0x1400173ef  mov     [rdi+6Ch], esi
0x1400173f2  jmp     short loc_140017427
0x1400173f4  mov     eax, [rcx+5Ch]
0x1400173f7  test    al, 1
0x1400173f9  jz      short loc_1400173C5
0x1400173fb  mov     eax, 2
0x140017400  mov     ebx, 80640015h
0x140017405  sub     eax, esi
0x140017407  neg     eax
0x140017409  sbb     eax, eax
0x14001740b  and     ebx, eax
0x14001740d  jmp     short loc_1400173CA
0x14001740f  test    esi, esi
0x140017411  jz      short loc_140017431
0x140017413  lea     eax, [rdx-1]
0x140017416  cmp     eax, 1
0x140017419  jbe     short loc_1400173D2
0x14001741b  mov     ebx, 80640015h
0x140017420  jmp     short loc_140017431
0x140017422  mov     ebx, 80640013h
0x140017427  lea     rcx, [rdi+60h]; SRWLock
0x14001742b  call    cs:__imp_ReleaseSRWLockShared
0x140017431  mov     eax, ebx
0x140017433  add     rsp, 28h
0x140017437  pop     rdi
0x140017438  pop     rsi
0x140017439  pop     rbp
0x14001743a  pop     rbx
0x14001743b  retn
```
