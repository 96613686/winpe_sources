# CADMCOMW::RemoveObjectFromList(int)

- ea: `0x18000dba8`
- end: `0x18000dc54`
- name: `?RemoveObjectFromList@CADMCOMW@@AEAAHH@Z`
- size: `172`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008430`
- `0x18000dc5c`

## callees

- `0x1800097e4`
- `0x18000dba8`
- `0x180010010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000dc22`
- `KERNEL32!LeaveCriticalSection` at `0x18000dc22`
- `KERNEL32!EnterCriticalSection` at `0x18000dbd8`
- `KERNEL32!EnterCriticalSection` at `0x18000dbd8`

## pseudocode

```c
__int64 __fastcall CADMCOMW::RemoveObjectFromList(CADMCOMW *this, int a2)
{
  unsigned int v4; // ebx
  _QWORD *v5; // rax
  _QWORD *v6; // rcx
  _QWORD *v7; // rdx

  v4 = 0;
  CADMCOMW::StopNotifications(this, 0);
  if ( a2 || !CADMCOMW::sm_fShutdownInProgress )
  {
    EnterCriticalSection(&CADMCOMW::sm_csObjectListLock);
    if ( a2 || !CADMCOMW::sm_fShutdownInProgress )
    {
      v5 = (_QWORD *)((char *)this + 144);
      v6 = (_QWORD *)*((_QWORD *)this + 18);
      if ( v6 != (_QWORD *)((char *)this + 144) )
      {
        if ( (_QWORD *)v6[1] != v5 || (v7 = (_QWORD *)*((_QWORD *)this + 19), (_QWORD *)*v7 != v5) )
          __fastfail(3u);
        *v7 = v6;
        v4 = 1;
        v6[1] = v7;
        *((_QWORD *)this + 19) = (char *)this + 144;
        *v5 = v5;
      }
    }
    LeaveCriticalSection(&CADMCOMW::sm_csObjectListLock);
    if ( v4 )
      (*(void (__fastcall **)(CADMCOMW *))(*(_QWORD *)this + 16LL))(this);
  }
  return v4;
}

```

## disassembly

```asm
0x18000dba8  mov     [rsp+arg_0], rbx
0x18000dbad  mov     [rsp+arg_8], rsi
0x18000dbb2  push    rdi
0x18000dbb3  sub     rsp, 20h
0x18000dbb7  mov     esi, edx
0x18000dbb9  mov     rdi, rcx
0x18000dbbc  xor     edx, edx; int
0x18000dbbe  xor     ebx, ebx
0x18000dbc0  call    ?StopNotifications@CADMCOMW@@AEAAJH@Z; CADMCOMW::StopNotifications(int)
0x18000dbc5  test    esi, esi
0x18000dbc7  jnz     short loc_18000DBD1
0x18000dbc9  cmp     cs:?sm_fShutdownInProgress@CADMCOMW@@2HA, ebx; int CADMCOMW::sm_fShutdownInProgress
0x18000dbcf  jnz     short loc_18000DC3B
0x18000dbd1  lea     rcx, ?sm_csObjectListLock@CADMCOMW@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000dbd8  call    cs:__imp_EnterCriticalSection
0x18000dbde  test    esi, esi
0x18000dbe0  jnz     short loc_18000DBEA
0x18000dbe2  cmp     cs:?sm_fShutdownInProgress@CADMCOMW@@2HA, ebx; int CADMCOMW::sm_fShutdownInProgress
0x18000dbe8  jnz     short loc_18000DC1B
0x18000dbea  lea     rax, [rdi+90h]
0x18000dbf1  mov     rcx, [rax]
0x18000dbf4  cmp     rcx, rax
0x18000dbf7  jz      short loc_18000DC1B
0x18000dbf9  cmp     [rcx+8], rax
0x18000dbfd  jnz     short loc_18000DC4D
0x18000dbff  mov     rdx, [rax+8]
0x18000dc03  cmp     [rdx], rax
0x18000dc06  jnz     short loc_18000DC4D
0x18000dc08  mov     [rdx], rcx
0x18000dc0b  mov     ebx, 1
0x18000dc10  mov     [rcx+8], rdx
0x18000dc14  mov     [rax+8], rax
0x18000dc18  mov     [rax], rax
0x18000dc1b  lea     rcx, ?sm_csObjectListLock@CADMCOMW@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000dc22  call    cs:__imp_LeaveCriticalSection
0x18000dc28  test    ebx, ebx
0x18000dc2a  jz      short loc_18000DC3B
0x18000dc2c  mov     rcx, [rdi]
0x18000dc2f  mov     rax, [rcx+10h]
0x18000dc33  mov     rcx, rdi
0x18000dc36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc3b  mov     rsi, [rsp+28h+arg_8]
0x18000dc40  mov     eax, ebx
0x18000dc42  mov     rbx, [rsp+28h+arg_0]
0x18000dc47  add     rsp, 20h
0x18000dc4b  pop     rdi
0x18000dc4c  retn
0x18000dc4d  mov     ecx, 3
0x18000dc52  int     29h; Win8: RtlFailFast(ecx)
```
