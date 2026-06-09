# CImportExportCallback::QueryService(_GUID const &,_GUID const &,void * *)

- ea: `0x1400189e0`
- end: `0x140018ab4`
- name: `?QueryService@CImportExportCallback@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `212`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x1400189e0`
- `0x1400191ec`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140018a85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140018a85`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140018a09`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140018a09`

## pseudocode

```c
__int64 __fastcall CImportExportCallback::QueryService(
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

  v4 = (struct _RTL_CRITICAL_SECTION *)(this + 4);
  v6 = 0;
  v12 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 4));
  if ( *((_DWORD *)this + 18) )
  {
    if ( *((_DWORD *)this + 22) )
    {
      v9 = -2147467259;
    }
    else if ( a4 )
    {
      if ( *(_QWORD *)&GUID_04842ef7_8a90_414d_9056_b793fb8f0ae6.Data1 == *(_QWORD *)&a3->Data1
        && *(_QWORD *)GUID_04842ef7_8a90_414d_9056_b793fb8f0ae6.Data4 == *(_QWORD *)a3->Data4 )
      {
        v10 = CAepStoreAccess::Create(this[2], 0, &v12);
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
0x1400189e0  mov     [rsp+arg_8], rbx
0x1400189e5  mov     [rsp+arg_10], rbp
0x1400189ea  push    rsi
0x1400189eb  push    rdi
0x1400189ec  push    r14
0x1400189ee  sub     rsp, 20h
0x1400189f2  lea     r14, [rcx+20h]
0x1400189f6  mov     rbx, rcx
0x1400189f9  xor     edi, edi
0x1400189fb  mov     rcx, r14; lpCriticalSection
0x1400189fe  mov     rbp, r9
0x140018a01  mov     [rsp+38h+arg_0], rdi
0x140018a06  mov     rsi, r8
0x140018a09  call    cs:__imp_EnterCriticalSection
0x140018a0f  cmp     [rbx+48h], edi
0x140018a12  jnz     short loc_140018A1B
0x140018a14  mov     ebx, 80640013h
0x140018a19  jmp     short loc_140018A82
0x140018a1b  cmp     [rbx+58h], edi
0x140018a1e  jz      short loc_140018A27
0x140018a20  mov     ebx, 80004005h
0x140018a25  jmp     short loc_140018A82
0x140018a27  test    rbp, rbp
0x140018a2a  jnz     short loc_140018A33
0x140018a2c  mov     ebx, 80004003h
0x140018a31  jmp     short loc_140018A82
0x140018a33  mov     rax, qword ptr cs:_GUID_04842ef7_8a90_414d_9056_b793fb8f0ae6.Data1
0x140018a3a  cmp     rax, [rsi]
0x140018a3d  jnz     short loc_140018A7D
0x140018a3f  mov     rax, qword ptr cs:_GUID_04842ef7_8a90_414d_9056_b793fb8f0ae6.Data4
0x140018a46  cmp     rax, [rsi+8]
0x140018a4a  jnz     short loc_140018A7D
0x140018a4c  mov     rcx, [rbx+10h]; Src
0x140018a50  lea     r8, [rsp+38h+arg_0]; struct CAepStoreAccess **
0x140018a55  xor     edx, edx; unsigned __int16 *
0x140018a57  call    ?Create@CAepStoreAccess@@SAJPEBG0PEAPEAV1@@Z; CAepStoreAccess::Create(ushort const *,ushort const *,CAepStoreAccess * *)
0x140018a5c  mov     rdi, [rsp+38h+arg_0]
0x140018a61  mov     ebx, eax
0x140018a63  test    eax, eax
0x140018a65  js      short loc_140018A82
0x140018a67  mov     rcx, [rdi]
0x140018a6a  mov     r8, rbp
0x140018a6d  mov     rdx, rsi
0x140018a70  mov     rax, [rcx]
0x140018a73  mov     rcx, rdi
0x140018a76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018a7b  jmp     short loc_140018A82
0x140018a7d  mov     ebx, 80004002h
0x140018a82  mov     rcx, r14; lpCriticalSection
0x140018a85  call    cs:__imp_LeaveCriticalSection
0x140018a8b  test    rdi, rdi
0x140018a8e  jz      short loc_140018A9F
0x140018a90  mov     rax, [rdi]
0x140018a93  mov     rcx, rdi
0x140018a96  mov     rax, [rax+10h]
0x140018a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018a9f  mov     rbp, [rsp+38h+arg_10]
0x140018aa4  mov     eax, ebx
0x140018aa6  mov     rbx, [rsp+38h+arg_8]
0x140018aab  add     rsp, 20h
0x140018aaf  pop     r14
0x140018ab1  pop     rdi
0x140018ab2  pop     rsi
0x140018ab3  retn
```
