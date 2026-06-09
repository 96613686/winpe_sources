# CASFReader::NonDelegatingQueryInterface(_GUID const &,void * *)

- ea: `0x18000bae0`
- end: `0x18000bbfd`
- name: `?NonDelegatingQueryInterface@CASFReader@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `285`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180005450`
- `0x18000bae0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::NonDelegatingQueryInterface(CASFReader *this, const struct _GUID *a2, void **a3)
{
  __int64 (__fastcall ***v3)(_QWORD, const struct _GUID *, void **); // r9
  unsigned __int64 v5; // rax
  void *v6; // rcx

  v3 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*((_QWORD *)this + 60);
  if ( v3 )
    return (**v3)(*((_QWORD *)this + 60), a2, a3);
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IFileSourceFilter.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IFileSourceFilter.Data4 )
  {
    v5 = (unsigned __int64)this + 120;
  }
  else if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IAMExtendedSeeking.Data1
         && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IAMExtendedSeeking.Data4 )
  {
    v5 = (unsigned __int64)this + 128;
  }
  else if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IWMHeaderInfo.Data1
         && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IWMHeaderInfo.Data4 )
  {
    v5 = (unsigned __int64)this + 136;
  }
  else if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IWMReaderAdvanced.Data1
         && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IWMReaderAdvanced.Data4
         || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IWMReaderAdvanced2.Data1
         && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IWMReaderAdvanced2.Data4 )
  {
    v5 = (unsigned __int64)this + 144;
  }
  else
  {
    if ( *(_QWORD *)&a2->Data1 != *(_QWORD *)&IID_IServiceProvider.Data1
      || *(_QWORD *)a2->Data4 != *(_QWORD *)IID_IServiceProvider.Data4 )
    {
      return CBaseFilter::NonDelegatingQueryInterface(this, a2, a3);
    }
    v5 = (unsigned __int64)this + 152;
  }
  v6 = (void *)(v5 & -(__int64)(this != 0));
  if ( !a3 )
    return 2147500035LL;
  *a3 = v6;
  (*(void (__fastcall **)(void *))(*(_QWORD *)v6 + 8LL))(v6);
  return 0;
}

```

## disassembly

```asm
0x18000bae0  sub     rsp, 28h
0x18000bae4  mov     r9, [rcx+1E0h]
0x18000baeb  test    r9, r9
0x18000baee  jz      short loc_18000BB02
0x18000baf0  mov     rax, [r9]
0x18000baf3  mov     rcx, r9
0x18000baf6  mov     rax, [rax]
0x18000baf9  add     rsp, 28h
0x18000bafd  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb02  mov     rax, [rdx]
0x18000bb05  cmp     rax, qword ptr cs:IID_IFileSourceFilter.Data1
0x18000bb0c  jnz     short loc_18000BB4D
0x18000bb0e  mov     rax, [rdx+8]
0x18000bb12  cmp     rax, qword ptr cs:IID_IFileSourceFilter.Data4
0x18000bb19  jnz     short loc_18000BB4D
0x18000bb1b  lea     rax, [rcx+78h]
0x18000bb1f  neg     rcx
0x18000bb22  sbb     rcx, rcx
0x18000bb25  and     rcx, rax
0x18000bb28  test    r8, r8
0x18000bb2b  jnz     short loc_18000BB37
0x18000bb2d  mov     eax, 80004003h
0x18000bb32  add     rsp, 28h
0x18000bb36  retn
0x18000bb37  mov     [r8], rcx
0x18000bb3a  mov     rax, [rcx]
0x18000bb3d  mov     rax, [rax+8]
0x18000bb41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb46  xor     eax, eax
0x18000bb48  add     rsp, 28h
0x18000bb4c  retn
0x18000bb4d  mov     rax, [rdx]
0x18000bb50  cmp     rax, qword ptr cs:IID_IAMExtendedSeeking.Data1
0x18000bb57  jnz     short loc_18000BB6F
0x18000bb59  mov     rax, [rdx+8]
0x18000bb5d  cmp     rax, qword ptr cs:IID_IAMExtendedSeeking.Data4
0x18000bb64  jnz     short loc_18000BB6F
0x18000bb66  lea     rax, [rcx+80h]
0x18000bb6d  jmp     short loc_18000BB1F
0x18000bb6f  mov     rax, [rdx]
0x18000bb72  cmp     rax, qword ptr cs:IID_IWMHeaderInfo.Data1
0x18000bb79  jnz     short loc_18000BB91
0x18000bb7b  mov     rax, [rdx+8]
0x18000bb7f  cmp     rax, qword ptr cs:IID_IWMHeaderInfo.Data4
0x18000bb86  jnz     short loc_18000BB91
0x18000bb88  lea     rax, [rcx+88h]
0x18000bb8f  jmp     short loc_18000BB1F
0x18000bb91  mov     rax, [rdx]
0x18000bb94  cmp     rax, qword ptr cs:IID_IWMReaderAdvanced.Data1
0x18000bb9b  jnz     short loc_18000BBB6
0x18000bb9d  mov     rax, [rdx+8]
0x18000bba1  cmp     rax, qword ptr cs:IID_IWMReaderAdvanced.Data4
0x18000bba8  jnz     short loc_18000BBB6
0x18000bbaa  lea     rax, [rcx+90h]
0x18000bbb1  jmp     loc_18000BB1F
0x18000bbb6  mov     rax, [rdx]
0x18000bbb9  cmp     rax, qword ptr cs:IID_IWMReaderAdvanced2.Data1
0x18000bbc0  jnz     short loc_18000BBCF
0x18000bbc2  mov     rax, [rdx+8]
0x18000bbc6  cmp     rax, qword ptr cs:IID_IWMReaderAdvanced2.Data4
0x18000bbcd  jz      short loc_18000BBAA
0x18000bbcf  mov     rax, [rdx]
0x18000bbd2  cmp     rax, qword ptr cs:IID_IServiceProvider.Data1
0x18000bbd9  jnz     short loc_18000BBF4
0x18000bbdb  mov     rax, [rdx+8]
0x18000bbdf  cmp     rax, qword ptr cs:IID_IServiceProvider.Data4
0x18000bbe6  jnz     short loc_18000BBF4
0x18000bbe8  lea     rax, [rcx+98h]
0x18000bbef  jmp     loc_18000BB1F
0x18000bbf4  add     rsp, 28h
0x18000bbf8  jmp     ?NonDelegatingQueryInterface@CBaseFilter@@UEAAJAEBU_GUID@@PEAPEAX@Z; CBaseFilter::NonDelegatingQueryInterface(_GUID const &,void * *)
```
