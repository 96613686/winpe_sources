# CAssociationCallback::OnEnumCeremoniesComplete(ulong,_CEREMONY const *,long)

- ea: `0x140017ad0`
- end: `0x140017b6d`
- name: `?OnEnumCeremoniesComplete@CAssociationCallback@@UEAAJKPEBU_CEREMONY@@J@Z`
- size: `157`
- prototype: `__int64 __fastcall(CAssociationCallback *this, unsigned int, const struct _CEREMONY *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009060`
- `0x14000b494`
- `0x140017ad0`
- `0x14001a83c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140017b5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140017b5c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140017b31`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140017b31`

## pseudocode

```c
__int64 __fastcall CAssociationCallback::OnEnumCeremoniesComplete(
        CAssociationCallback *this,
        unsigned int a2,
        const struct _CEREMONY *a3,
        int a4)
{
  int v4; // edi
  unsigned int v7; // ebx
  size_t v8; // rsi
  void *v9; // rax
  struct _RTL_CRITICAL_SECTION *v10; // rsi

  v4 = a4;
  if ( !a4 )
  {
    if ( !a2 )
      return (unsigned int)-2147024809;
    *((_DWORD *)this + 20) = a2;
    v8 = 20LL * a2;
    v9 = (void *)DAF_user_alloc(v8);
    *((_QWORD *)this + 11) = v9;
    if ( v9 )
      memcpy_0(v9, a3, v8);
    else
      v4 = -2147024882;
  }
  v10 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 112);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  if ( *((_DWORD *)this + 26) )
    v7 = OnEnumCeremoniesCompleteStub(
           *((_DWORD *)this + 20),
           *((const struct _CEREMONY **)this + 11),
           v4,
           *((void **)this + 4));
  else
    v7 = -2140930029;
  LeaveCriticalSection(v10);
  return v7;
}

```

## disassembly

```asm
0x140017ad0  push    rbx
0x140017ad2  push    rbp
0x140017ad3  push    rsi
0x140017ad4  push    rdi
0x140017ad5  sub     rsp, 28h
0x140017ad9  mov     edi, r9d
0x140017adc  mov     rbp, r8
0x140017adf  mov     rbx, rcx
0x140017ae2  test    r9d, r9d
0x140017ae5  jnz     short loc_140017B2A
0x140017ae7  test    edx, edx
0x140017ae9  jnz     short loc_140017AF2
0x140017aeb  mov     ebx, 80070057h
0x140017af0  jmp     short loc_140017B62
0x140017af2  test    r9d, r9d
0x140017af5  jnz     short loc_140017B2A
0x140017af7  mov     eax, edx
0x140017af9  mov     [rcx+50h], edx
0x140017afc  lea     rsi, [rax+rax*4]
0x140017b00  shl     rsi, 2
0x140017b04  mov     rcx, rsi
0x140017b07  call    DAF_user_alloc
0x140017b0c  mov     [rbx+58h], rax
0x140017b10  test    rax, rax
0x140017b13  jnz     short loc_140017B1C
0x140017b15  mov     edi, 8007000Eh
0x140017b1a  jmp     short loc_140017B2A
0x140017b1c  mov     r8, rsi; Size
0x140017b1f  mov     rdx, rbp; Src
0x140017b22  mov     rcx, rax; void *
0x140017b25  call    memcpy_0
0x140017b2a  lea     rsi, [rbx+70h]
0x140017b2e  mov     rcx, rsi; lpCriticalSection
0x140017b31  call    cs:__imp_EnterCriticalSection
0x140017b37  cmp     dword ptr [rbx+68h], 0
0x140017b3b  jz      short loc_140017B54
0x140017b3d  mov     r9, [rbx+20h]; void *
0x140017b41  mov     r8d, edi; int
0x140017b44  mov     rdx, [rbx+58h]; struct _CEREMONY *
0x140017b48  mov     ecx, [rbx+50h]; unsigned int
0x140017b4b  call    ?OnEnumCeremoniesCompleteStub@@YAJKPEBU_CEREMONY@@JPEAX@Z; OnEnumCeremoniesCompleteStub(ulong,_CEREMONY const *,long,void *)
0x140017b50  mov     ebx, eax
0x140017b52  jmp     short loc_140017B59
0x140017b54  mov     ebx, 80640013h
0x140017b59  mov     rcx, rsi; lpCriticalSection
0x140017b5c  call    cs:__imp_LeaveCriticalSection
0x140017b62  mov     eax, ebx
0x140017b64  add     rsp, 28h
0x140017b68  pop     rdi
0x140017b69  pop     rsi
0x140017b6a  pop     rbp
0x140017b6b  pop     rbx
0x140017b6c  retn
```
