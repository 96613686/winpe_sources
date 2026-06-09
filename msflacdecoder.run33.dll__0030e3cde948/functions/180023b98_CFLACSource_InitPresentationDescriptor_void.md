# CFLACSource::InitPresentationDescriptor(void)

- ea: `0x180023b98`
- end: `0x180023d63`
- name: `?InitPresentationDescriptor@CFLACSource@@AEAAJXZ`
- size: `459`
- prototype: `__int64 __fastcall(CFLACSource *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180023d6c`

## callees

- `0x180020398`
- `0x180020484`
- `0x180021b54`
- `0x180023b98`
- `0x180056010`

## import_xrefs

- `MFPlat!MFCreatePresentationDescriptor` at `0x180023c51`
- `MFPlat!MFCreatePresentationDescriptor` at `0x180023c51`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFLACSource::InitPresentationDescriptor(CFLACSource *this)
{
  __int64 v2; // rcx
  int v3; // ecx
  __int64 v4; // rdx
  _QWORD *v5; // rdi
  HRESULT v7; // [rsp+50h] [rbp+10h]
  IMFStreamDescriptor *apStreamDescriptors; // [rsp+58h] [rbp+18h] BYREF

  apStreamDescriptors = 0;
  v2 = *((_QWORD *)this + 22);
  if ( !v2 )
  {
    v7 = -2147467261;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      return (unsigned int)v7;
    v4 = 141;
    goto LABEL_4;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, IMFStreamDescriptor **))(*(_QWORD *)v2 + 64LL))(v2, &apStreamDescriptors);
  if ( v7 >= 0 )
  {
    v5 = (_QWORD *)((char *)this + 240);
    v7 = MFCreatePresentationDescriptor(1u, &apStreamDescriptors, (IMFPresentationDescriptor **)this + 30);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v5 + 280LL))(*v5, 0);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(_QWORD, const IID *, _QWORD))(*(_QWORD *)*v5 + 176LL))(
               *v5,
               &MF_PD_DURATION,
               *((_QWORD *)this + 45));
        if ( v7 >= 0 )
        {
          v7 = (*(__int64 (__fastcall **)(_QWORD, const IID *, const wchar_t *))(*(_QWORD *)*v5 + 200LL))(
                 *v5,
                 &MF_PD_MIME_TYPE,
                 L"audio/flac");
          if ( v7 >= 0 )
          {
            *((_DWORD *)this + 56) = 2;
            v7 = CFLACSource::CompleteOpen(this, 0);
          }
          else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v4 = 146;
            goto LABEL_4;
          }
        }
        else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v4 = 145;
          goto LABEL_4;
        }
      }
      else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v4 = 144;
        goto LABEL_4;
      }
    }
    else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v4 = 143;
      goto LABEL_4;
    }
  }
  else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v4 = 142;
LABEL_4:
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids, this, v3);
  }
  if ( apStreamDescriptors )
    ((void (__fastcall *)(IMFStreamDescriptor *))apStreamDescriptors->lpVtbl->Release)(apStreamDescriptors);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180023b98  mov     [rsp-8+arg_10], rbx
0x180023b9d  mov     [rsp-8+arg_18], rdi
0x180023ba2  push    rbp
0x180023ba3  mov     rbp, rsp
0x180023ba6  sub     rsp, 40h
0x180023baa  mov     rbx, rcx
0x180023bad  mov     [rbp+arg_0], 0
0x180023bb4  mov     [rbp+var_10], rcx
0x180023bb8  lea     rax, [rbp+arg_0]
0x180023bbc  mov     [rbp+var_8], rax
0x180023bc0  mov     [rbp+apStreamDescriptors], 0
0x180023bc8  mov     rcx, [rcx+0B0h]
0x180023bcf  test    rcx, rcx
0x180023bd2  jnz     short loc_180023C11
0x180023bd4  mov     ecx, 80004003h
0x180023bd9  mov     [rbp+arg_0], ecx
0x180023bdc  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180023be1  cmp     al, 1
0x180023be3  jb      loc_180023D50
0x180023be9  mov     edx, 8Dh
0x180023bee  mov     [rsp+40h+var_20], ecx
0x180023bf2  mov     r9, rbx
0x180023bf5  lea     r8, WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids
0x180023bfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c03  mov     rcx, [rcx+10h]
0x180023c07  call    WPP_SF_qd
0x180023c0c  jmp     loc_180023D3A
0x180023c11  mov     rax, [rcx]
0x180023c14  lea     rdx, [rbp+apStreamDescriptors]
0x180023c18  mov     rax, [rax+40h]
0x180023c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c21  mov     ecx, eax
0x180023c23  mov     [rbp+arg_0], eax
0x180023c26  test    eax, eax
0x180023c28  jns     short loc_180023C3E
0x180023c2a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180023c2f  cmp     al, 1
0x180023c31  jb      loc_180023D3A
0x180023c37  mov     edx, 8Eh
0x180023c3c  jmp     short loc_180023BEE
0x180023c3e  lea     rdi, [rbx+0F0h]
0x180023c45  mov     r8, rdi; ppPresentationDescriptor
0x180023c48  lea     rdx, [rbp+apStreamDescriptors]; apStreamDescriptors
0x180023c4c  mov     ecx, 1; cStreamDescriptors
0x180023c51  call    cs:__imp_MFCreatePresentationDescriptor
0x180023c57  mov     ecx, eax
0x180023c59  mov     [rbp+arg_0], eax
0x180023c5c  test    eax, eax
0x180023c5e  jns     short loc_180023C77
0x180023c60  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180023c65  cmp     al, 1
0x180023c67  jb      loc_180023D3A
0x180023c6d  mov     edx, 8Fh
0x180023c72  jmp     loc_180023BEE
0x180023c77  mov     rcx, [rdi]
0x180023c7a  mov     rax, [rcx]
0x180023c7d  xor     edx, edx
0x180023c7f  mov     rax, [rax+118h]
0x180023c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c8b  mov     ecx, eax
0x180023c8d  mov     [rbp+arg_0], eax
0x180023c90  test    eax, eax
0x180023c92  jns     short loc_180023CAB
0x180023c94  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180023c99  cmp     al, 1
0x180023c9b  jb      loc_180023D3A
0x180023ca1  mov     edx, 90h
0x180023ca6  jmp     loc_180023BEE
0x180023cab  mov     rcx, [rdi]
0x180023cae  mov     rax, [rcx]
0x180023cb1  mov     r8, [rbx+168h]
0x180023cb8  lea     rdx, MF_PD_DURATION
0x180023cbf  mov     rax, [rax+0B0h]
0x180023cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ccb  mov     ecx, eax
0x180023ccd  mov     [rbp+arg_0], eax
0x180023cd0  test    eax, eax
0x180023cd2  jns     short loc_180023CE7
0x180023cd4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180023cd9  cmp     al, 1
0x180023cdb  jb      short loc_180023D3A
0x180023cdd  mov     edx, 91h
0x180023ce2  jmp     loc_180023BEE
0x180023ce7  mov     rcx, [rdi]
0x180023cea  mov     rax, [rcx]
0x180023ced  lea     r8, aAudioFlac; "audio/flac"
0x180023cf4  lea     rdx, MF_PD_MIME_TYPE
0x180023cfb  mov     rax, [rax+0C8h]
0x180023d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d07  mov     ecx, eax
0x180023d09  mov     [rbp+arg_0], eax
0x180023d0c  test    eax, eax
0x180023d0e  jns     short loc_180023D23
0x180023d10  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180023d15  cmp     al, 1
0x180023d17  jb      short loc_180023D3A
0x180023d19  mov     edx, 92h
0x180023d1e  jmp     loc_180023BEE
0x180023d23  mov     dword ptr [rbx+0E0h], 2
0x180023d2d  xor     edx, edx; int
0x180023d2f  mov     rcx, rbx; this
0x180023d32  call    ?CompleteOpen@CFLACSource@@AEAAJJ@Z; CFLACSource::CompleteOpen(long)
0x180023d37  mov     [rbp+arg_0], eax
0x180023d3a  mov     rcx, [rbp+apStreamDescriptors]
0x180023d3e  test    rcx, rcx
0x180023d41  jz      short loc_180023D50
0x180023d43  mov     rax, [rcx]
0x180023d46  mov     rax, [rax+10h]
0x180023d4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d4f  nop
0x180023d50  mov     eax, [rbp+arg_0]
0x180023d53  mov     rbx, [rsp+40h+arg_10]
0x180023d58  mov     rdi, [rsp+40h+arg_18]
0x180023d5d  add     rsp, 40h
0x180023d61  pop     rbp
0x180023d62  retn
```
