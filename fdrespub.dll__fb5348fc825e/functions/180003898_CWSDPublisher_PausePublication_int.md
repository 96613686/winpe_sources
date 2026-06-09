# CWSDPublisher::PausePublication(int)

- ea: `0x180003898`
- end: `0x180003994`
- name: `?PausePublication@CWSDPublisher@@QEAAJH@Z`
- size: `252`
- prototype: `__int64 __fastcall(CWSDPublisher *this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180001e60`

## callees

- `0x180001f24`
- `0x180001f70`
- `0x18000356c`
- `0x180003898`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003941`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003941`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800038de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800038de`

## pseudocode

```c
__int64 __fastcall CWSDPublisher::PausePublication(CWSDPublisher *this)
{
  unsigned int v2; // edi
  __int64 v3; // rcx
  unsigned int v4; // eax
  __int64 v5; // rcx
  int v6; // eax
  bool v7; // cf

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids);
  v2 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  if ( *((_DWORD *)this + 5) )
  {
    v3 = *((_QWORD *)this + 9);
    if ( v3 )
    {
      v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 40LL))(v3);
      *((_DWORD *)this + 6) = 1;
      v2 = v4;
      if ( v4 )
        goto LABEL_12;
    }
    else
    {
      v5 = *((_QWORD *)this + 5);
      if ( v5 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
        *((_QWORD *)this + 5) = 0;
      }
      *(_QWORD *)((char *)this + 20) = 0;
    }
  }
  LogEvent(&EventPause, L"PausePublication");
LABEL_12:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v6 = 0;
  if ( v2 )
    v7 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
  else
    v7 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    LOBYTE(v6) = !v7;
    if ( v6 )
      WPP_SF_sqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids);
  }
  return v2;
}

```

## disassembly

```asm
0x180003898  push    rbx
0x18000389a  push    rsi
0x18000389b  push    rdi
0x18000389c  push    r14
0x18000389e  sub     rsp, 38h
0x1800038a2  mov     rbx, rcx
0x1800038a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038ac  lea     r14, WPP_GLOBAL_Control
0x1800038b3  cmp     rcx, r14
0x1800038b6  jz      short loc_1800038D8
0x1800038b8  cmp     byte ptr [rcx+19h], 4
0x1800038bc  jb      short loc_1800038D8
0x1800038be  mov     rcx, [rcx+10h]
0x1800038c2  lea     r8, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids
0x1800038c9  mov     edx, 15h
0x1800038ce  mov     [rsp+58h+var_38], rbx
0x1800038d3  call    WPP_SF_sq
0x1800038d8  lea     rcx, [rbx+60h]; lpCriticalSection
0x1800038dc  xor     edi, edi
0x1800038de  call    cs:__imp_EnterCriticalSection
0x1800038e4  cmp     [rbx+14h], edi
0x1800038e7  jz      short loc_18000392A
0x1800038e9  mov     rcx, [rbx+48h]
0x1800038ed  test    rcx, rcx
0x1800038f0  jz      short loc_18000390D
0x1800038f2  mov     rax, [rcx]
0x1800038f5  mov     rax, [rax+28h]
0x1800038f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038fe  mov     dword ptr [rbx+18h], 1
0x180003905  mov     edi, eax
0x180003907  test    eax, eax
0x180003909  jnz     short loc_18000393D
0x18000390b  jmp     short loc_18000392A
0x18000390d  mov     rcx, [rbx+28h]
0x180003911  test    rcx, rcx
0x180003914  jz      short loc_180003926
0x180003916  mov     rax, [rcx]
0x180003919  mov     rax, [rax+10h]
0x18000391d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003922  mov     [rbx+28h], rdi
0x180003926  mov     [rbx+14h], rdi
0x18000392a  lea     rdx, aPausepublicati; "PausePublication"
0x180003931  lea     rcx, EventPause; struct _EVENT_DESCRIPTOR *
0x180003938  call    ?LogEvent@@YAJPEBU_EVENT_DESCRIPTOR@@PEBG@Z; LogEvent(_EVENT_DESCRIPTOR const *,ushort const *)
0x18000393d  lea     rcx, [rbx+60h]; lpCriticalSection
0x180003941  call    cs:__imp_LeaveCriticalSection
0x180003947  mov     rcx, cs:WPP_GLOBAL_Control
0x18000394e  xor     eax, eax
0x180003950  test    edi, edi
0x180003952  jnz     short loc_18000395A
0x180003954  cmp     byte ptr [rcx+19h], 4
0x180003958  jmp     short loc_18000395E
0x18000395a  cmp     byte ptr [rcx+19h], 2
0x18000395e  setnb   al
0x180003961  cmp     rcx, r14
0x180003964  jz      short loc_180003988
0x180003966  test    eax, eax
0x180003968  jz      short loc_180003988
0x18000396a  mov     rcx, [rcx+10h]
0x18000396e  lea     r8, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids
0x180003975  mov     edx, 16h
0x18000397a  mov     [rsp+58h+var_30], edi
0x18000397e  mov     [rsp+58h+var_38], rbx
0x180003983  call    WPP_SF_sqd
0x180003988  mov     eax, edi
0x18000398a  add     rsp, 38h
0x18000398e  pop     r14
0x180003990  pop     rdi
0x180003991  pop     rsi
0x180003992  pop     rbx
0x180003993  retn
```
