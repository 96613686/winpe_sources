# STTABLE::Initialize(ulong,ulong (*)(STBUFF *),int (*)(STBUFF *,STBUFF *))

- ea: `0x180003244`
- end: `0x1800033b3`
- name: `?Initialize@STTABLE@@QEAAJKP6AKPEAVSTBUFF@@@ZP6AH00@Z@Z`
- size: `367`
- prototype: `__int64 __fastcall(STTABLE *__hidden this, unsigned int, unsigned int (*)(struct STBUFF *), int (*)(struct STBUFF *, struct STBUFF *))`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003ec0`
- `0x180005d74`

## callees

- `0x180001008`
- `0x180001fa4`
- `0x180003244`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003361`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000336d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003361`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000336d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800032d9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003338`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800032d9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003338`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800032f1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000334c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800032f1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000334c`

## pseudocode

```c
__int64 __fastcall STTABLE::Initialize(
        STTABLE *this,
        unsigned int a2,
        unsigned int (*a3)(struct STBUFF *),
        int (*a4)(struct STBUFF *, struct STBUFF *))
{
  int v7; // edi
  __int64 v8; // r15
  __int64 v9; // rbp
  char *v10; // rax
  struct _RTL_CRITICAL_SECTION *v11; // rbx
  struct _RTL_CRITICAL_SECTION_DEBUG *EventW; // rax
  HANDLE v13; // rax

  v7 = STBUFF::Resize((const void **)this + 1, 8 * a2);
  if ( v7 >= 0 )
  {
    v8 = *((_QWORD *)this + 2);
    v9 = 0;
    if ( a2 )
    {
      while ( 1 )
      {
        v10 = (char *)operator new(0x60u);
        v11 = (struct _RTL_CRITICAL_SECTION *)v10;
        if ( !v10 )
          break;
        *((_DWORD *)v10 + 6) = 0;
        *(_QWORD *)v10 = &STTABLE_BUCKET::`vftable';
        *((_QWORD *)v10 + 2) = v10 + 8;
        *((_QWORD *)v10 + 11) = CompareClientKeys;
        *((_QWORD *)v10 + 1) = v10 + 8;
        if ( !*((_DWORD *)v10 + 6) )
        {
          *(_QWORD *)(v10 + 28) = 0;
          if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)v10 + 1, 0x64u) )
            goto LABEL_14;
          EventW = (struct _RTL_CRITICAL_SECTION_DEBUG *)CreateEventW(0, 0, 0, 0);
          v11[2].DebugInfo = EventW;
          if ( !EventW )
          {
            DeleteCriticalSection(v11 + 1);
LABEL_14:
            v7 = -2147467259;
            ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64))v11->DebugInfo->Type)(v11, 1);
            return (unsigned int)v7;
          }
          LODWORD(v11->LockSemaphore) = 1;
        }
        *(_QWORD *)(v8 + 8 * v9) = v11;
        v7 = 0;
        ++*((_DWORD *)this + 26);
        v9 = (unsigned int)(v9 + 1);
        if ( (unsigned int)v9 >= a2 )
          goto LABEL_9;
      }
      return (unsigned int)-2147024882;
    }
    else
    {
LABEL_9:
      if ( !*((_DWORD *)this + 28) )
      {
        *(_QWORD *)((char *)this + 116) = 0;
        if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 128), 0x64u) )
        {
          v13 = CreateEventW(0, 0, 0, 0);
          *((_QWORD *)this + 21) = v13;
          if ( v13 )
            *((_DWORD *)this + 28) = 1;
          else
            DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
        }
      }
      *((_QWORD *)this + 22) = a3;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180003244  push    rbx
0x180003246  push    rbp
0x180003247  push    rsi
0x180003248  push    rdi
0x180003249  push    r12
0x18000324b  push    r14
0x18000324d  push    r15
0x18000324f  sub     rsp, 20h
0x180003253  mov     r14d, edx
0x180003256  mov     rsi, rcx
0x180003259  lea     edx, ds:0[rdx*8]; unsigned int
0x180003260  add     rcx, 8; this
0x180003264  mov     r12, r8
0x180003267  call    ?Resize@STBUFF@@QEAAJK@Z; STBUFF::Resize(ulong)
0x18000326c  mov     edi, eax
0x18000326e  test    eax, eax
0x180003270  js      loc_1800033A2
0x180003276  mov     r15, [rsi+10h]
0x18000327a  xor     ebp, ebp
0x18000327c  test    r14d, r14d
0x18000327f  jz      loc_18000331B
0x180003285  mov     ecx, 60h ; '`'; Size
0x18000328a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000328f  mov     rbx, rax
0x180003292  test    rax, rax
0x180003295  jz      loc_18000338D
0x18000329b  mov     dword ptr [rbx+18h], 0
0x1800032a2  lea     rax, ??_7STTABLE_BUCKET@@6B@; const STTABLE_BUCKET::`vftable'
0x1800032a9  mov     [rbx], rax
0x1800032ac  lea     rcx, [rbx+8]
0x1800032b0  lea     rax, ?CompareClientKeys@@YAHPEAVSTBUFF@@0@Z; CompareClientKeys(STBUFF *,STBUFF *)
0x1800032b7  mov     [rbx+10h], rcx
0x1800032bb  mov     [rbx+58h], rax
0x1800032bf  mov     [rcx], rcx
0x1800032c2  cmp     dword ptr [rbx+18h], 0
0x1800032c6  jnz     short loc_180003307
0x1800032c8  mov     edx, 64h ; 'd'; dwSpinCount
0x1800032cd  mov     qword ptr [rbx+1Ch], 0
0x1800032d5  lea     rcx, [rbx+28h]; lpCriticalSection
0x1800032d9  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800032df  test    eax, eax
0x1800032e1  jz      loc_180003373
0x1800032e7  xor     r9d, r9d; lpName
0x1800032ea  xor     r8d, r8d; bInitialState
0x1800032ed  xor     edx, edx; bManualReset
0x1800032ef  xor     ecx, ecx; lpEventAttributes
0x1800032f1  call    cs:__imp_CreateEventW
0x1800032f7  mov     [rbx+50h], rax
0x1800032fb  test    rax, rax
0x1800032fe  jz      short loc_180003369
0x180003300  mov     dword ptr [rbx+18h], 1
0x180003307  mov     [r15+rbp*8], rbx
0x18000330b  xor     edi, edi
0x18000330d  inc     dword ptr [rsi+68h]
0x180003310  inc     ebp
0x180003312  cmp     ebp, r14d
0x180003315  jb      loc_180003285
0x18000331b  cmp     dword ptr [rsi+70h], 0
0x18000331f  jnz     short loc_18000339B
0x180003321  lea     rbx, [rsi+80h]
0x180003328  mov     qword ptr [rsi+74h], 0
0x180003330  mov     rcx, rbx; lpCriticalSection
0x180003333  mov     edx, 64h ; 'd'; dwSpinCount
0x180003338  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000333e  test    eax, eax
0x180003340  jz      short loc_18000339B
0x180003342  xor     r9d, r9d; lpName
0x180003345  xor     r8d, r8d; bInitialState
0x180003348  xor     edx, edx; bManualReset
0x18000334a  xor     ecx, ecx; lpEventAttributes
0x18000334c  call    cs:__imp_CreateEventW
0x180003352  mov     [rsi+0A8h], rax
0x180003359  test    rax, rax
0x18000335c  jnz     short loc_180003394
0x18000335e  mov     rcx, rbx; lpCriticalSection
0x180003361  call    cs:__imp_DeleteCriticalSection
0x180003367  jmp     short loc_18000339B
0x180003369  lea     rcx, [rbx+28h]; lpCriticalSection
0x18000336d  call    cs:__imp_DeleteCriticalSection
0x180003373  mov     rax, [rbx]
0x180003376  mov     edx, 1
0x18000337b  mov     rcx, rbx
0x18000337e  mov     edi, 80004005h
0x180003383  mov     rax, [rax]
0x180003386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000338b  jmp     short loc_1800033A2
0x18000338d  mov     edi, 8007000Eh
0x180003392  jmp     short loc_1800033A2
0x180003394  mov     dword ptr [rsi+70h], 1
0x18000339b  mov     [rsi+0B0h], r12
0x1800033a2  mov     eax, edi
0x1800033a4  add     rsp, 20h
0x1800033a8  pop     r15
0x1800033aa  pop     r14
0x1800033ac  pop     r12
0x1800033ae  pop     rdi
0x1800033af  pop     rsi
0x1800033b0  pop     rbp
0x1800033b1  pop     rbx
0x1800033b2  retn
```
