# CDiaDataSource::~CDiaDataSource(void)

- ea: `0x1800ad080`
- end: `0x1800ad1e6`
- name: `??1CDiaDataSource@@UEAA@XZ`
- size: `358`
- prototype: `void __fastcall(CDiaDataSource *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800ad430`

## callees

- `0x18002bf30`
- `0x1800ad080`
- `0x1801d63b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800ad0c4`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800ad0c4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ad139`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ad139`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CDiaDataSource::~CDiaDataSource(CDiaDataSource *this)
{
  FILE *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx

  *(_QWORD *)this = &CDiaDataSource::`vftable'{for `IDiaDataSource11Internal'};
  *((_QWORD *)this + 1) = &CDiaDataSource::`vftable'{for `IDiaDataSourceEx2'};
  *((_QWORD *)this + 2) = &CDiaDataSource::`vftable'{for `CDiaBase'};
  if ( !*((_BYTE *)this + 33) )
  {
    v2 = (FILE *)*((_QWORD *)this + 80);
    if ( v2 )
    {
      fclose(v2);
      *((_QWORD *)this + 80) = 0;
    }
    v3 = *((_QWORD *)this + 5);
    if ( v3 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 88LL))(v3);
      *((_QWORD *)this + 5) = 0;
    }
    v4 = *((_QWORD *)this + 81);
    if ( v4 )
    {
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v4 + 8) + 24LL))(v4 + 8, 1);
      *((_QWORD *)this + 81) = 0;
    }
    *((_BYTE *)this + 33) = 1;
  }
  *((_QWORD *)this + 87) = &CComAutoCriticalSection::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 704));
  v5 = *((_QWORD *)this + 79);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  v6 = *((_QWORD *)this + 78);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = *((_QWORD *)this + 77);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v8 = *((_QWORD *)this + 76);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  v9 = *((_QWORD *)this + 75);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  std::vector<unsigned __int64>::~vector<unsigned __int64>((char *)this + 576);
  *((_QWORD *)this + 2) = &CDiaBase::`vftable';
  _InterlockedDecrement(&CDiaBase::m_objects);
}

```

## disassembly

```asm
0x1800ad080  push    rbx
0x1800ad082  sub     rsp, 30h
0x1800ad086  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800ad08f  mov     rbx, rcx
0x1800ad092  lea     rax, ??_7CDiaDataSource@@6BIDiaDataSource11Internal@@@; const CDiaDataSource::`vftable'{for `IDiaDataSource11Internal'}
0x1800ad099  mov     [rcx], rax
0x1800ad09c  lea     rax, ??_7CDiaDataSource@@6BIDiaDataSourceEx2@@@; const CDiaDataSource::`vftable'{for `IDiaDataSourceEx2'}
0x1800ad0a3  mov     [rcx+8], rax
0x1800ad0a7  lea     rax, ??_7CDiaDataSource@@6BCDiaBase@@@; const CDiaDataSource::`vftable'{for `CDiaBase'}
0x1800ad0ae  mov     [rcx+10h], rax
0x1800ad0b2  cmp     byte ptr [rcx+21h], 0
0x1800ad0b6  jnz     short loc_1800AD124
0x1800ad0b8  mov     rcx, [rcx+280h]; Stream
0x1800ad0bf  test    rcx, rcx
0x1800ad0c2  jz      short loc_1800AD0D5
0x1800ad0c4  call    cs:__imp_fclose
0x1800ad0ca  mov     qword ptr [rbx+280h], 0
0x1800ad0d5  mov     rcx, [rbx+28h]
0x1800ad0d9  test    rcx, rcx
0x1800ad0dc  jz      short loc_1800AD0F3
0x1800ad0de  mov     rax, [rcx]
0x1800ad0e1  mov     rax, [rax+58h]
0x1800ad0e5  call    cs:__guard_dispatch_icall_fptr
0x1800ad0eb  mov     qword ptr [rbx+28h], 0
0x1800ad0f3  mov     rcx, [rbx+288h]
0x1800ad0fa  test    rcx, rcx
0x1800ad0fd  jz      short loc_1800AD120
0x1800ad0ff  add     rcx, 8
0x1800ad103  mov     rax, [rcx]
0x1800ad106  mov     edx, 1
0x1800ad10b  mov     rax, [rax+18h]
0x1800ad10f  call    cs:__guard_dispatch_icall_fptr
0x1800ad115  mov     qword ptr [rbx+288h], 0
0x1800ad120  mov     byte ptr [rbx+21h], 1
0x1800ad124  lea     rax, ??_7CComAutoCriticalSection@@6B@; const CComAutoCriticalSection::`vftable'
0x1800ad12b  mov     [rbx+2B8h], rax
0x1800ad132  lea     rcx, [rbx+2C0h]; lpCriticalSection
0x1800ad139  call    cs:__imp_DeleteCriticalSection
0x1800ad13f  nop
0x1800ad140  mov     rcx, [rbx+278h]
0x1800ad147  test    rcx, rcx
0x1800ad14a  jz      short loc_1800AD15A
0x1800ad14c  mov     rax, [rcx]
0x1800ad14f  mov     rax, [rax+10h]
0x1800ad153  call    cs:__guard_dispatch_icall_fptr
0x1800ad159  nop
0x1800ad15a  mov     rcx, [rbx+270h]
0x1800ad161  test    rcx, rcx
0x1800ad164  jz      short loc_1800AD174
0x1800ad166  mov     rax, [rcx]
0x1800ad169  mov     rax, [rax+10h]
0x1800ad16d  call    cs:__guard_dispatch_icall_fptr
0x1800ad173  nop
0x1800ad174  mov     rcx, [rbx+268h]
0x1800ad17b  test    rcx, rcx
0x1800ad17e  jz      short loc_1800AD18E
0x1800ad180  mov     rax, [rcx]
0x1800ad183  mov     rax, [rax+10h]
0x1800ad187  call    cs:__guard_dispatch_icall_fptr
0x1800ad18d  nop
0x1800ad18e  mov     rcx, [rbx+260h]
0x1800ad195  test    rcx, rcx
0x1800ad198  jz      short loc_1800AD1A8
0x1800ad19a  mov     rax, [rcx]
0x1800ad19d  mov     rax, [rax+10h]
0x1800ad1a1  call    cs:__guard_dispatch_icall_fptr
0x1800ad1a7  nop
0x1800ad1a8  mov     rcx, [rbx+258h]
0x1800ad1af  test    rcx, rcx
0x1800ad1b2  jz      short loc_1800AD1C2
0x1800ad1b4  mov     rax, [rcx]
0x1800ad1b7  mov     rax, [rax+10h]
0x1800ad1bb  call    cs:__guard_dispatch_icall_fptr
0x1800ad1c1  nop
0x1800ad1c2  lea     rcx, [rbx+240h]
0x1800ad1c9  call    ??1?$vector@_KV?$allocator@_K@std@@@std@@QEAA@XZ; std::vector<unsigned __int64>::~vector<unsigned __int64>(void)
0x1800ad1ce  lea     rax, ??_7CDiaBase@@6B@; const CDiaBase::`vftable'
0x1800ad1d5  mov     [rbx+10h], rax
0x1800ad1d9  lock dec cs:?m_objects@CDiaBase@@2JA; long CDiaBase::m_objects
0x1800ad1e0  add     rsp, 30h
0x1800ad1e4  pop     rbx
0x1800ad1e5  retn
```
