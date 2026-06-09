# PersistObject::Set(PersistObject::PERSIST_OBJECT_MEMBER_ID,ushort const *)

- ea: `0x180017384`
- end: `0x1800174de`
- name: `?Set@PersistObject@@QEAAJW4PERSIST_OBJECT_MEMBER_ID@1@PEBG@Z`
- size: `346`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180016c04`
- `0x180019904`
- `0x18001a458`
- `0x18001adf8`
- `0x180035f9c`

## callees

- `0x180003a14`
- `0x180006090`
- `0x180013d74`
- `0x180015460`
- `0x180017384`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800174bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800174bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800173ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800173ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800174a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800174a2`
- `DMCmnUtils!CopyString` at `0x180017435`
- `DMCmnUtils!CopyString` at `0x180017435`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PersistObject::Set(__int64 a1, unsigned int a2, const unsigned __int16 *a3)
{
  __int64 v4; // rbp
  struct _RTL_CRITICAL_SECTION *v6; // r15
  int Room; // edi
  void *v8; // rax
  _QWORD *v9; // rbx
  int v10; // eax
  __int64 (__fastcall *v11)(__int64, __int64, _QWORD); // rax
  __int64 v12; // rcx
  void *v13; // rcx

  v4 = a2;
  v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
  if ( !a3 )
  {
    Room = -2147467261;
    goto LABEL_20;
  }
  Room = PersistObject::MakeRoom((PersistObject *)a1, v4);
  if ( Room < 0 )
    goto LABEL_20;
  v8 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( !v8 )
  {
    Room = -2147024882;
    goto LABEL_20;
  }
  *(_QWORD *)v8 = 0;
  *((_DWORD *)v8 + 2) = 0;
  *((_QWORD *)v8 + 2) = 0;
  *((_QWORD *)v8 + 3) = 0;
  *(_DWORD *)v8 = 1;
  Room = CopyString(a3, 0xFFFFFFFF, (unsigned __int16 **)v8 + 2);
  if ( Room < 0
    || (v10 = PersistObject::Clear(a1, (unsigned int)v4), Room = v10, v10 != -2147024894)
    && v10 != -2147023728
    && v10 < 0 )
  {
    if ( *(_DWORD *)v9 == 1 )
    {
      v13 = (void *)v9[2];
    }
    else
    {
      if ( *(_DWORD *)v9 != 3 )
      {
LABEL_18:
        operator delete(v9, (const struct std::nothrow_t *)0x20);
        goto LABEL_20;
      }
      v13 = (void *)v9[3];
    }
    LocalFree(v13);
    goto LABEL_18;
  }
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v4) = v9;
  v11 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(a1 + 72);
  if ( v11 && (v12 = *(_QWORD *)(a1 + 88)) != 0 )
    Room = v11(v12, a1, (unsigned int)v4);
  else
    Room = 0;
LABEL_20:
  LeaveCriticalSection(v6);
  return (unsigned int)Room;
}

```

## disassembly

```asm
0x180017384  mov     [rsp+arg_8], rbx
0x180017389  mov     [rsp+arg_10], rbp
0x18001738e  push    rsi
0x18001738f  push    rdi
0x180017390  push    r12
0x180017392  push    r14
0x180017394  push    r15
0x180017396  sub     rsp, 30h
0x18001739a  mov     r12, r8
0x18001739d  mov     ebp, edx
0x18001739f  mov     rsi, rcx
0x1800173a2  lea     r15, [rcx+20h]
0x1800173a6  mov     [rsp+58h+var_38], r15
0x1800173ab  mov     rcx, r15; lpCriticalSection
0x1800173ae  call    cs:__imp_EnterCriticalSection
0x1800173b4  mov     [rsp+58h+var_30], 1
0x1800173b9  test    r12, r12
0x1800173bc  jnz     short loc_1800173C8
0x1800173be  mov     edi, 80004003h
0x1800173c3  jmp     loc_1800174BC
0x1800173c8  mov     edx, ebp; unsigned int
0x1800173ca  mov     rcx, rsi; this
0x1800173cd  call    ?MakeRoom@PersistObject@@AEAAJK@Z; PersistObject::MakeRoom(ulong)
0x1800173d2  mov     edi, eax
0x1800173d4  test    eax, eax
0x1800173d6  js      loc_1800174BC
0x1800173dc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800173e3  mov     ecx, 20h ; ' '; unsigned __int64
0x1800173e8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800173ed  mov     rbx, rax
0x1800173f0  mov     [rsp+58h+arg_0], rax
0x1800173f5  test    rax, rax
0x1800173f8  jz      loc_1800174B7
0x1800173fe  mov     qword ptr [rax], 0
0x180017405  mov     dword ptr [rax+8], 0
0x18001740c  mov     qword ptr [rax+10h], 0
0x180017414  mov     qword ptr [rax+18h], 0
0x18001741c  test    rax, rax
0x18001741f  jz      loc_1800174B7
0x180017425  mov     dword ptr [rax], 1
0x18001742b  lea     r8, [rax+10h]
0x18001742f  or      edx, 0FFFFFFFFh
0x180017432  mov     rcx, r12
0x180017435  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18001743b  mov     edi, eax
0x18001743d  test    eax, eax
0x18001743f  js      short loc_18001748C
0x180017441  mov     edx, ebp
0x180017443  mov     rcx, rsi
0x180017446  call    ?Clear@PersistObject@@QEAAJW4PERSIST_OBJECT_MEMBER_ID@1@@Z; PersistObject::Clear(PersistObject::PERSIST_OBJECT_MEMBER_ID)
0x18001744b  mov     edi, eax
0x18001744d  cmp     eax, 80070002h
0x180017452  jz      short loc_18001745F
0x180017454  cmp     eax, 80070490h
0x180017459  jz      short loc_18001745F
0x18001745b  test    eax, eax
0x18001745d  js      short loc_18001748C
0x18001745f  mov     rax, [rsi+8]
0x180017463  mov     [rax+rbp*8], rbx
0x180017467  mov     rax, [rsi+48h]
0x18001746b  test    rax, rax
0x18001746e  jz      short loc_180017488
0x180017470  mov     rcx, [rsi+58h]
0x180017474  test    rcx, rcx
0x180017477  jz      short loc_180017488
0x180017479  mov     r8d, ebp
0x18001747c  mov     rdx, rsi
0x18001747f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017484  mov     edi, eax
0x180017486  jmp     short loc_1800174BC
0x180017488  xor     edi, edi
0x18001748a  jmp     short loc_1800174BC
0x18001748c  mov     ecx, [rbx]
0x18001748e  sub     ecx, 1
0x180017491  jz      short loc_18001749E
0x180017493  cmp     ecx, 2
0x180017496  jnz     short loc_1800174A8
0x180017498  mov     rcx, [rbx+18h]
0x18001749c  jmp     short loc_1800174A2
0x18001749e  mov     rcx, [rbx+10h]; hMem
0x1800174a2  call    cs:__imp_LocalFree
0x1800174a8  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x1800174ad  mov     rcx, rbx; void *
0x1800174b0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800174b5  jmp     short loc_1800174BC
0x1800174b7  mov     edi, 8007000Eh
0x1800174bc  mov     rcx, r15; lpCriticalSection
0x1800174bf  call    cs:__imp_LeaveCriticalSection
0x1800174c5  mov     eax, edi
0x1800174c7  mov     rbx, [rsp+58h+arg_8]
0x1800174cc  mov     rbp, [rsp+58h+arg_10]
0x1800174d1  add     rsp, 30h
0x1800174d5  pop     r15
0x1800174d7  pop     r14
0x1800174d9  pop     r12
0x1800174db  pop     rdi
0x1800174dc  pop     rsi
0x1800174dd  retn
```
