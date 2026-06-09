# CASFReaderCallback::NonDelegatingQueryInterface(_GUID const &,void * *)

- ea: `0x18000bc10`
- end: `0x18000bca4`
- name: `?NonDelegatingQueryInterface@CASFReaderCallback@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `148`
- prototype: `__int64 __fastcall(CASFReaderCallback *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006e78`
- `0x18000bc10`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReaderCallback::NonDelegatingQueryInterface(
        CASFReaderCallback *this,
        const struct _GUID *a2,
        void **a3)
{
  unsigned int v3; // ebx
  void *v4; // rcx
  void (*v5)(void); // rax
  void *v7; // rcx

  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IWMReaderCallback.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IWMReaderCallback.Data4 )
  {
    v3 = 0;
    v4 = (void *)(((unsigned __int64)this + 24) & -(__int64)(this != 0));
    if ( !a3 )
      return (unsigned int)-2147467261;
    *a3 = v4;
    v5 = *(void (**)(void))(*(_QWORD *)v4 + 8LL);
LABEL_6:
    v5();
    return v3;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IWMReaderCallbackAdvanced.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IWMReaderCallbackAdvanced.Data4 )
  {
    v3 = 0;
    v7 = (void *)(((unsigned __int64)this + 32) & -(__int64)(this != 0));
    if ( !a3 )
      return (unsigned int)-2147467261;
    *a3 = v7;
    v5 = *(void (**)(void))(*(_QWORD *)v7 + 8LL);
    goto LABEL_6;
  }
  return CUnknown::NonDelegatingQueryInterface(this, a2, a3);
}

```

## disassembly

```asm
0x18000bc10  push    rbx
0x18000bc12  sub     rsp, 20h
0x18000bc16  mov     rax, [rdx]
0x18000bc19  cmp     rax, qword ptr cs:IID_IWMReaderCallback.Data1
0x18000bc20  jnz     short loc_18000BC61
0x18000bc22  mov     rax, [rdx+8]
0x18000bc26  cmp     rax, qword ptr cs:IID_IWMReaderCallback.Data4
0x18000bc2d  jnz     short loc_18000BC61
0x18000bc2f  lea     rax, [rcx+18h]
0x18000bc33  neg     rcx
0x18000bc36  sbb     rcx, rcx
0x18000bc39  xor     ebx, ebx
0x18000bc3b  and     rcx, rax
0x18000bc3e  test    r8, r8
0x18000bc41  jnz     short loc_18000BC4A
0x18000bc43  mov     ebx, 80004003h
0x18000bc48  jmp     short loc_18000BC59
0x18000bc4a  mov     [r8], rcx
0x18000bc4d  mov     rdx, [rcx]
0x18000bc50  mov     rax, [rdx+8]
0x18000bc54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc59  mov     eax, ebx
0x18000bc5b  add     rsp, 20h
0x18000bc5f  pop     rbx
0x18000bc60  retn
0x18000bc61  mov     rax, [rdx]
0x18000bc64  cmp     rax, qword ptr cs:IID_IWMReaderCallbackAdvanced.Data1
0x18000bc6b  jnz     short loc_18000BC9A
0x18000bc6d  mov     rax, [rdx+8]
0x18000bc71  cmp     rax, qword ptr cs:IID_IWMReaderCallbackAdvanced.Data4
0x18000bc78  jnz     short loc_18000BC9A
0x18000bc7a  lea     rax, [rcx+20h]
0x18000bc7e  neg     rcx
0x18000bc81  sbb     rcx, rcx
0x18000bc84  xor     ebx, ebx
0x18000bc86  and     rcx, rax; this
0x18000bc89  test    r8, r8
0x18000bc8c  jz      short loc_18000BC43
0x18000bc8e  mov     [r8], rcx
0x18000bc91  mov     rax, [rcx]
0x18000bc94  mov     rax, [rax+8]
0x18000bc98  jmp     short loc_18000BC54
0x18000bc9a  add     rsp, 20h
0x18000bc9e  pop     rbx
0x18000bc9f  jmp     ?NonDelegatingQueryInterface@CUnknown@@UEAAJAEBU_GUID@@PEAPEAX@Z; CUnknown::NonDelegatingQueryInterface(_GUID const &,void * *)
```
