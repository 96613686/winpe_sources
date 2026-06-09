# PersistObject::Set(PersistObject::PERSIST_OBJECT_MEMBER_ID,ushort const *)

- ea: `0x18002a978`
- end: `0x18002aaa7`
- name: `?Set@PersistObject@@QEAAJW4PERSIST_OBJECT_MEMBER_ID@1@PEBG@Z`
- size: `303`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18002812c`

## callees

- `0x180002558`
- `0x180028630`
- `0x180029dec`
- `0x18002a978`
- `0x18003f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002aa82`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002aa82`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a99a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a99a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002aa92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002aa92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aa79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aa79`
- `DMCmnUtils!CopyString` at `0x18002aa1e`
- `DMCmnUtils!CopyString` at `0x18002aa1e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PersistObject::Set(__int64 a1, unsigned int a2, const unsigned __int16 *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rbp
  int Room; // edi
  void *v8; // rax
  _QWORD *v9; // rbx
  __int64 (__fastcall *v10)(__int64, __int64, _QWORD); // rax
  __int64 v11; // rcx
  void *v12; // rcx

  v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
  if ( !a3 )
  {
    Room = -2147467261;
    goto LABEL_18;
  }
  Room = PersistObject::MakeRoom((PersistObject *)a1, a2);
  if ( Room < 0 )
    goto LABEL_18;
  v8 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( !v8 )
  {
    Room = -2147024882;
    goto LABEL_18;
  }
  *(_QWORD *)v8 = 0;
  *((_DWORD *)v8 + 2) = 0;
  *((_QWORD *)v8 + 2) = 0;
  *((_QWORD *)v8 + 3) = 0;
  *(_DWORD *)v8 = 1;
  Room = CopyString(a3, 0xFFFFFFFF, (unsigned __int16 **)v8 + 2);
  if ( Room < 0
    || (Room = PersistObject::InsertValue((PersistObject *)a1, a2, (struct PersistObject::PersistValue *)v9), Room < 0) )
  {
    if ( *(_DWORD *)v9 == 1 )
    {
      v12 = (void *)v9[2];
    }
    else
    {
      if ( *(_DWORD *)v9 != 3 )
      {
LABEL_16:
        operator delete(v9);
        goto LABEL_18;
      }
      v12 = (void *)v9[3];
    }
    LocalFree(v12);
    goto LABEL_16;
  }
  v10 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(a1 + 72);
  if ( v10 && (v11 = *(_QWORD *)(a1 + 88)) != 0 )
    Room = v10(v11, a1, a2);
  else
    Room = 0;
LABEL_18:
  LeaveCriticalSection(v6);
  return (unsigned int)Room;
}

```

## disassembly

```asm
0x18002a978  push    rbx
0x18002a97a  push    rbp
0x18002a97b  push    rsi
0x18002a97c  push    rdi
0x18002a97d  push    r14
0x18002a97f  push    r15
0x18002a981  sub     rsp, 38h
0x18002a985  mov     r15, r8
0x18002a988  mov     r14d, edx
0x18002a98b  mov     rsi, rcx
0x18002a98e  lea     rbp, [rcx+20h]
0x18002a992  mov     [rsp+68h+var_48], rbp
0x18002a997  mov     rcx, rbp; lpCriticalSection
0x18002a99a  call    cs:__imp_EnterCriticalSection
0x18002a9a0  mov     [rsp+68h+var_40], 1
0x18002a9a5  test    r15, r15
0x18002a9a8  jnz     short loc_18002A9B4
0x18002a9aa  mov     edi, 80004003h
0x18002a9af  jmp     loc_18002AA8F
0x18002a9b4  mov     edx, r14d; unsigned int
0x18002a9b7  mov     rcx, rsi; this
0x18002a9ba  call    ?MakeRoom@PersistObject@@AEAAJK@Z; PersistObject::MakeRoom(ulong)
0x18002a9bf  mov     edi, eax
0x18002a9c1  test    eax, eax
0x18002a9c3  js      loc_18002AA8F
0x18002a9c9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002a9d0  mov     ecx, 20h ; ' '; unsigned __int64
0x18002a9d5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002a9da  mov     rbx, rax
0x18002a9dd  mov     [rsp+68h+arg_0], rax
0x18002a9e2  test    rax, rax
0x18002a9e5  jz      loc_18002AA8A
0x18002a9eb  mov     qword ptr [rax], 0
0x18002a9f2  mov     dword ptr [rax+8], 0
0x18002a9f9  mov     qword ptr [rax+10h], 0
0x18002aa01  mov     qword ptr [rax+18h], 0
0x18002aa09  test    rax, rax
0x18002aa0c  jz      short loc_18002AA8A
0x18002aa0e  mov     dword ptr [rax], 1
0x18002aa14  lea     r8, [rax+10h]
0x18002aa18  or      edx, 0FFFFFFFFh
0x18002aa1b  mov     rcx, r15
0x18002aa1e  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18002aa24  mov     edi, eax
0x18002aa26  test    eax, eax
0x18002aa28  js      short loc_18002AA63
0x18002aa2a  mov     r8, rbx; struct PersistObject::PersistValue *
0x18002aa2d  mov     edx, r14d; unsigned int
0x18002aa30  mov     rcx, rsi; this
0x18002aa33  call    ?InsertValue@PersistObject@@AEAAJKPEAVPersistValue@1@@Z; PersistObject::InsertValue(ulong,PersistObject::PersistValue *)
0x18002aa38  mov     edi, eax
0x18002aa3a  test    eax, eax
0x18002aa3c  js      short loc_18002AA63
0x18002aa3e  mov     rax, [rsi+48h]
0x18002aa42  test    rax, rax
0x18002aa45  jz      short loc_18002AA5F
0x18002aa47  mov     rcx, [rsi+58h]
0x18002aa4b  test    rcx, rcx
0x18002aa4e  jz      short loc_18002AA5F
0x18002aa50  mov     r8d, r14d
0x18002aa53  mov     rdx, rsi
0x18002aa56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa5b  mov     edi, eax
0x18002aa5d  jmp     short loc_18002AA8F
0x18002aa5f  xor     edi, edi
0x18002aa61  jmp     short loc_18002AA8F
0x18002aa63  mov     ecx, [rbx]
0x18002aa65  sub     ecx, 1
0x18002aa68  jz      short loc_18002AA75
0x18002aa6a  cmp     ecx, 2
0x18002aa6d  jnz     short loc_18002AA7F
0x18002aa6f  mov     rcx, [rbx+18h]
0x18002aa73  jmp     short loc_18002AA79
0x18002aa75  mov     rcx, [rbx+10h]; hMem
0x18002aa79  call    cs:__imp_LocalFree
0x18002aa7f  mov     rcx, rbx
0x18002aa82  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002aa88  jmp     short loc_18002AA8F
0x18002aa8a  mov     edi, 8007000Eh
0x18002aa8f  mov     rcx, rbp; lpCriticalSection
0x18002aa92  call    cs:__imp_LeaveCriticalSection
0x18002aa98  mov     eax, edi
0x18002aa9a  add     rsp, 38h
0x18002aa9e  pop     r15
0x18002aaa0  pop     r14
0x18002aaa2  pop     rdi
0x18002aaa3  pop     rsi
0x18002aaa4  pop     rbp
0x18002aaa5  pop     rbx
0x18002aaa6  retn
```
