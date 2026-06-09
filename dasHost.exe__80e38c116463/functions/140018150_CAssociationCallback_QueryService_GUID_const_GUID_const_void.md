# CAssociationCallback::QueryService(_GUID const &,_GUID const &,void * *)

- ea: `0x140018150`
- end: `0x14001821a`
- name: `?QueryService@CAssociationCallback@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `202`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x140018150`
- `0x1400191ec`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400181eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400181eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140018179`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140018179`

## pseudocode

```c
__int64 __fastcall CAssociationCallback::QueryService(
        const unsigned __int16 **this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  struct CAepStoreAccess *v6; // rdi
  unsigned int v9; // ebx
  int v10; // eax
  struct CAepStoreAccess *v12; // [rsp+40h] [rbp+8h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)(this + 12);
  v6 = 0;
  v12 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 12));
  if ( *((_DWORD *)this + 22) )
  {
    if ( a4 )
    {
      if ( *(_QWORD *)&GUID_04842ef7_8a90_414d_9056_b793fb8f0ae6.Data1 == *(_QWORD *)&a3->Data1
        && *(_QWORD *)GUID_04842ef7_8a90_414d_9056_b793fb8f0ae6.Data4 == *(_QWORD *)a3->Data4 )
      {
        v10 = CAepStoreAccess::Create(this[3], this[4], &v12);
        v6 = v12;
        v9 = v10;
        if ( v10 >= 0 )
          (**(void (__fastcall ***)(struct CAepStoreAccess *, const struct _GUID *, void **))v12)(v12, a3, a4);
      }
      else
      {
        v9 = -2147467262;
      }
    }
    else
    {
      v9 = -2147467261;
    }
  }
  else
  {
    v9 = -2140930029;
  }
  LeaveCriticalSection(v4);
  if ( v6 )
    (*(void (__fastcall **)(struct CAepStoreAccess *))(*(_QWORD *)v6 + 16LL))(v6);
  return v9;
}

```

## disassembly

```asm
0x140018150  mov     [rsp+arg_8], rbx
0x140018155  mov     [rsp+arg_10], rbp
0x14001815a  push    rsi
0x14001815b  push    rdi
0x14001815c  push    r14
0x14001815e  sub     rsp, 20h
0x140018162  lea     r14, [rcx+60h]
0x140018166  mov     rbx, rcx
0x140018169  xor     edi, edi
0x14001816b  mov     rcx, r14; lpCriticalSection
0x14001816e  mov     rbp, r9
0x140018171  mov     [rsp+38h+arg_0], rdi
0x140018176  mov     rsi, r8
0x140018179  call    cs:__imp_EnterCriticalSection
0x14001817f  cmp     [rbx+58h], edi
0x140018182  jnz     short loc_14001818B
0x140018184  mov     ebx, 80640013h
0x140018189  jmp     short loc_1400181E8
0x14001818b  test    rbp, rbp
0x14001818e  jnz     short loc_140018197
0x140018190  mov     ebx, 80004003h
0x140018195  jmp     short loc_1400181E8
0x140018197  mov     rax, qword ptr cs:_GUID_04842ef7_8a90_414d_9056_b793fb8f0ae6.Data1
0x14001819e  cmp     rax, [rsi]
0x1400181a1  jnz     short loc_1400181E3
0x1400181a3  mov     rax, qword ptr cs:_GUID_04842ef7_8a90_414d_9056_b793fb8f0ae6.Data4
0x1400181aa  cmp     rax, [rsi+8]
0x1400181ae  jnz     short loc_1400181E3
0x1400181b0  mov     rdx, [rbx+20h]; unsigned __int16 *
0x1400181b4  lea     r8, [rsp+38h+arg_0]; struct CAepStoreAccess **
0x1400181b9  mov     rcx, [rbx+18h]; Src
0x1400181bd  call    ?Create@CAepStoreAccess@@SAJPEBG0PEAPEAV1@@Z; CAepStoreAccess::Create(ushort const *,ushort const *,CAepStoreAccess * *)
0x1400181c2  mov     rdi, [rsp+38h+arg_0]
0x1400181c7  mov     ebx, eax
0x1400181c9  test    eax, eax
0x1400181cb  js      short loc_1400181E8
0x1400181cd  mov     rcx, [rdi]
0x1400181d0  mov     r8, rbp
0x1400181d3  mov     rdx, rsi
0x1400181d6  mov     rax, [rcx]
0x1400181d9  mov     rcx, rdi
0x1400181dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400181e1  jmp     short loc_1400181E8
0x1400181e3  mov     ebx, 80004002h
0x1400181e8  mov     rcx, r14; lpCriticalSection
0x1400181eb  call    cs:__imp_LeaveCriticalSection
0x1400181f1  test    rdi, rdi
0x1400181f4  jz      short loc_140018205
0x1400181f6  mov     rax, [rdi]
0x1400181f9  mov     rcx, rdi
0x1400181fc  mov     rax, [rax+10h]
0x140018200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018205  mov     rbp, [rsp+38h+arg_10]
0x14001820a  mov     eax, ebx
0x14001820c  mov     rbx, [rsp+38h+arg_8]
0x140018211  add     rsp, 20h
0x140018215  pop     r14
0x140018217  pop     rdi
0x140018218  pop     rsi
0x140018219  retn
```
