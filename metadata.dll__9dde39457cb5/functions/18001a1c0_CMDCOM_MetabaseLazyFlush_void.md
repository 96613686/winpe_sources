# CMDCOM::MetabaseLazyFlush(void *)

- ea: `0x18001a1c0`
- end: `0x18001a2af`
- name: `?MetabaseLazyFlush@CMDCOM@@CAXPEAX@Z`
- size: `239`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18001a1c0`
- `0x180031010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001a22e`
- `KERNEL32!LeaveCriticalSection` at `0x18001a22e`
- `KERNEL32!EnterCriticalSection` at `0x18001a1d8`
- `KERNEL32!EnterCriticalSection` at `0x18001a1d8`
- `IisRTL!ScheduleWorkItem` at `0x18001a216`
- `IisRTL!ScheduleWorkItem` at `0x18001a216`
- `IisRTL!RemoveWorkItem` at `0x18001a1e6`
- `IisRTL!RemoveWorkItem` at `0x18001a1e6`

## pseudocode

```c
void __fastcall CMDCOM::MetabaseLazyFlush(__int64 *a1)
{
  int v2; // esi
  bool v3; // cc
  unsigned int v4; // eax
  unsigned int v5; // r8d
  __int64 v6; // rax
  unsigned int v7; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)a1 + 2);
  if ( *((_DWORD *)a1 + 13) )
  {
    RemoveWorkItem(*((_DWORD *)a1 + 14));
    v3 = *((_DWORD *)a1 + 16) <= 0x1Eu;
    *((_DWORD *)a1 + 14) = 0;
    if ( v3 || (v4 = *((_DWORD *)a1 + 17), v4 >= 5) )
    {
      a1[8] = 0;
    }
    else
    {
      v5 = *((_DWORD *)a1 + 15);
      *((_DWORD *)a1 + 16) = 0;
      *((_DWORD *)a1 + 17) = v4 + 1;
      *((_DWORD *)a1 + 14) = ScheduleWorkItem((void (*)(void *))CMDCOM::MetabaseLazyFlush, a1, v5, 0);
      v2 = 1;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)a1 + 2);
  if ( *((_DWORD *)a1 + 13) && !v2 )
  {
    v6 = *a1;
    v7 = 0;
    if ( (*(int (__fastcall **)(__int64 *, _QWORD, _QWORD, __int64, int, unsigned int *))(v6 + 280))(
           a1,
           0,
           0,
           1,
           100,
           &v7) >= 0 )
    {
      (*(void (__fastcall **)(__int64 *, _QWORD))(*a1 + 304))(a1, v7);
      (*(void (__fastcall **)(__int64 *, _QWORD))(*a1 + 288))(a1, v7);
    }
  }
}

```

## disassembly

```asm
0x18001a1c0  mov     [rsp+arg_8], rbx
0x18001a1c5  mov     [rsp+arg_10], rsi
0x18001a1ca  push    rdi
0x18001a1cb  sub     rsp, 40h
0x18001a1cf  mov     rbx, rcx
0x18001a1d2  xor     esi, esi
0x18001a1d4  add     rcx, 50h ; 'P'; lpCriticalSection
0x18001a1d8  call    cs:__imp_EnterCriticalSection
0x18001a1de  cmp     [rbx+34h], esi
0x18001a1e1  jz      short loc_18001A22A
0x18001a1e3  mov     ecx, [rbx+38h]
0x18001a1e6  call    cs:__imp_?RemoveWorkItem@@YAHK@Z; RemoveWorkItem(ulong)
0x18001a1ec  cmp     dword ptr [rbx+40h], 1Eh
0x18001a1f0  mov     [rbx+38h], esi
0x18001a1f3  jbe     short loc_18001A226
0x18001a1f5  mov     eax, [rbx+44h]
0x18001a1f8  cmp     eax, 5
0x18001a1fb  jnb     short loc_18001A226
0x18001a1fd  mov     r8d, [rbx+3Ch]
0x18001a201  lea     rcx, ?MetabaseLazyFlush@CMDCOM@@CAXPEAX@Z; CMDCOM::MetabaseLazyFlush(void *)
0x18001a208  inc     eax
0x18001a20a  mov     [rbx+40h], esi
0x18001a20d  xor     r9d, r9d
0x18001a210  mov     [rbx+44h], eax
0x18001a213  mov     rdx, rbx
0x18001a216  call    cs:__imp_?ScheduleWorkItem@@YAKP6AXPEAX@Z0KH@Z; ScheduleWorkItem(void (*)(void *),void *,ulong,int)
0x18001a21c  mov     [rbx+38h], eax
0x18001a21f  mov     esi, 1
0x18001a224  jmp     short loc_18001A22A
0x18001a226  mov     [rbx+40h], rsi
0x18001a22a  lea     rcx, [rbx+50h]; lpCriticalSection
0x18001a22e  call    cs:__imp_LeaveCriticalSection
0x18001a234  cmp     dword ptr [rbx+34h], 0
0x18001a238  jz      short loc_18001A29F
0x18001a23a  test    esi, esi
0x18001a23c  jnz     short loc_18001A29F
0x18001a23e  mov     rax, [rbx]
0x18001a241  lea     rcx, [rsp+48h+arg_0]
0x18001a246  mov     [rsp+48h+var_20], rcx
0x18001a24b  lea     r9d, [rsi+1]
0x18001a24f  xor     r8d, r8d
0x18001a252  mov     [rsp+48h+arg_0], esi
0x18001a256  xor     edx, edx
0x18001a258  mov     [rsp+48h+var_28], 64h ; 'd'
0x18001a260  mov     rax, [rax+118h]
0x18001a267  mov     rcx, rbx
0x18001a26a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a26f  test    eax, eax
0x18001a271  js      short loc_18001A29F
0x18001a273  mov     rax, [rbx]
0x18001a276  mov     rcx, rbx
0x18001a279  mov     edx, [rsp+48h+arg_0]
0x18001a27d  mov     rax, [rax+130h]
0x18001a284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a289  mov     rax, [rbx]
0x18001a28c  mov     rcx, rbx
0x18001a28f  mov     edx, [rsp+48h+arg_0]
0x18001a293  mov     rax, [rax+120h]
0x18001a29a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a29f  mov     rbx, [rsp+48h+arg_8]
0x18001a2a4  mov     rsi, [rsp+48h+arg_10]
0x18001a2a9  add     rsp, 40h
0x18001a2ad  pop     rdi
0x18001a2ae  retn
```
