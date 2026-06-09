# CScheduleCF::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180006dd0`
- end: `0x180006ead`
- name: `?CreateInstance@CScheduleCF@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `221`
- prototype: `__int64 __fastcall(CScheduleCF *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180006dd0`
- `0x180006ec0`
- `0x180009ef8`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006e39`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006e39`

## pseudocode

```c
__int64 __fastcall CScheduleCF::CreateInstance(
        CScheduleCF *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  char *v6; // rdi
  int v7; // ebp
  __int64 v8; // rax
  unsigned int v9; // ebx

  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  v6 = (char *)operator new(0x50u);
  if ( !v6 )
    return 2147942414LL;
  *((_DWORD *)v6 + 12) = 1;
  *(_QWORD *)v6 = &CSchedule::`vftable';
  *((_QWORD *)v6 + 7) = 0;
  *((_QWORD *)v6 + 8) = 0;
  *((_DWORD *)v6 + 18) = 1;
  _InterlockedIncrement((volatile signed __int32 *)&CDll::s_cObjs);
  InitializeCriticalSection((LPCRITICAL_SECTION)(v6 + 8));
  v7 = CSchedule::Init((CSchedule *)v6);
  v8 = *(_QWORD *)v6;
  if ( v7 < 0 )
  {
    (*(void (__fastcall **)(char *))(v8 + 16))(v6);
    return (unsigned int)v7;
  }
  else
  {
    v9 = (*(__int64 (__fastcall **)(char *, const struct _GUID *, void **))v8)(v6, a3, a4);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
    return v9;
  }
}

```

## disassembly

```asm
0x180006dd0  mov     [rsp+arg_10], rbx
0x180006dd5  push    rsi
0x180006dd6  sub     rsp, 20h
0x180006dda  mov     rbx, r9
0x180006ddd  mov     rsi, r8
0x180006de0  test    r9, r9
0x180006de3  jz      loc_180006E89
0x180006de9  mov     [rsp+28h+arg_0], rbp
0x180006dee  mov     ecx, 50h ; 'P'; Size
0x180006df3  xor     ebp, ebp
0x180006df5  mov     [rsp+28h+arg_8], rdi
0x180006dfa  mov     [r9], rbp
0x180006dfd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006e02  mov     rdi, rax
0x180006e05  test    rax, rax
0x180006e08  jz      loc_180006E99
0x180006e0e  lea     rax, ??_7CSchedule@@6B@; const CSchedule::`vftable'
0x180006e15  mov     dword ptr [rdi+30h], 1
0x180006e1c  mov     [rdi], rax
0x180006e1f  mov     [rdi+38h], rbp
0x180006e23  mov     [rdi+40h], rbp
0x180006e27  mov     dword ptr [rdi+48h], 1
0x180006e2e  lock inc cs:?s_cObjs@CDll@@2KA; ulong CDll::s_cObjs
0x180006e35  lea     rcx, [rdi+8]; lpCriticalSection
0x180006e39  call    cs:__imp_InitializeCriticalSection
0x180006e3f  mov     rcx, rdi; this
0x180006e42  call    ?Init@CSchedule@@QEAAJXZ; CSchedule::Init(void)
0x180006e47  mov     ebp, eax
0x180006e49  mov     rcx, rdi
0x180006e4c  mov     rax, [rdi]
0x180006e4f  test    ebp, ebp
0x180006e51  js      short loc_180006EA0
0x180006e53  mov     rax, [rax]
0x180006e56  mov     r8, rbx
0x180006e59  mov     rdx, rsi
0x180006e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e61  mov     rcx, [rdi]
0x180006e64  mov     ebx, eax
0x180006e66  mov     rax, [rcx+10h]
0x180006e6a  mov     rcx, rdi
0x180006e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e72  mov     eax, ebx
0x180006e74  mov     rbp, [rsp+28h+arg_0]
0x180006e79  mov     rdi, [rsp+28h+arg_8]
0x180006e7e  mov     rbx, [rsp+28h+arg_10]
0x180006e83  add     rsp, 20h
0x180006e87  pop     rsi
0x180006e88  retn
0x180006e89  mov     rbx, [rsp+28h+arg_10]
0x180006e8e  mov     eax, 80070057h
0x180006e93  add     rsp, 20h
0x180006e97  pop     rsi
0x180006e98  retn
0x180006e99  mov     eax, 8007000Eh
0x180006e9e  jmp     short loc_180006E74
0x180006ea0  mov     rax, [rax+10h]
0x180006ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ea9  mov     eax, ebp
0x180006eab  jmp     short loc_180006E74
```
