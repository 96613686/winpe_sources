# ATL::CComCreator<ATL::CComAggObject<CPortableWorkspaceLauncher>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000bcc4`
- end: `0x18000bdaa`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCPortableWorkspaceLauncher@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `230`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000bcb0`

## callees

- `0x1800016e4`
- `0x18000bcc4`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CPortableWorkspaceLauncher>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v7; // edi
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  _DWORD *v10; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = operator new(0x20u);
    v9 = v8;
    if ( v8 )
    {
      v8[2] = 0;
      *(_QWORD *)v8 = &ATL::CComAggObject<CPortableWorkspaceLauncher>::`vftable';
      *((_QWORD *)v8 + 2) = &ATL::CComContainedObject<CPortableWorkspaceLauncher>::`vftable';
      *((_QWORD *)v8 + 3) = a1;
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v10 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v9 = v10;
  }
  if ( v9 )
  {
    v7 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v9)(v9, v4, v3);
    if ( v7 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x18000bcc4  mov     [rsp+arg_10], r8
0x18000bcc9  mov     [rsp+arg_8], rdx
0x18000bcce  push    rbx
0x18000bccf  push    rsi
0x18000bcd0  push    rdi
0x18000bcd1  push    r14
0x18000bcd3  push    r15
0x18000bcd5  sub     rsp, 30h
0x18000bcd9  mov     rsi, r8
0x18000bcdc  mov     r14, rdx
0x18000bcdf  mov     r15, rcx
0x18000bce2  test    r8, r8
0x18000bce5  jnz     short loc_18000BCF1
0x18000bce7  mov     eax, 80004003h
0x18000bcec  jmp     loc_18000BD9E
0x18000bcf1  mov     qword ptr [r8], 0
0x18000bcf8  mov     edi, 8007000Eh
0x18000bcfd  mov     [rsp+58h+arg_18], edi
0x18000bd01  mov     [rsp+58h+var_38], 0
0x18000bd0a  mov     ecx, 20h ; ' '; Size
0x18000bd0f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bd14  mov     rbx, rax
0x18000bd17  test    rbx, rbx
0x18000bd1a  jz      short loc_18000BD4F
0x18000bd1c  mov     dword ptr [rax+8], 0
0x18000bd23  lea     rax, ??_7?$CComAggObject@VCPortableWorkspaceLauncher@@@ATL@@6B@; const ATL::CComAggObject<CPortableWorkspaceLauncher>::`vftable'
0x18000bd2a  mov     [rbx], rax
0x18000bd2d  lea     rax, ??_7?$CComContainedObject@VCPortableWorkspaceLauncher@@@ATL@@6B@; const ATL::CComContainedObject<CPortableWorkspaceLauncher>::`vftable'
0x18000bd34  mov     [rbx+10h], rax
0x18000bd38  mov     [rbx+18h], r15
0x18000bd3c  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000bd43  mov     rax, [rcx]
0x18000bd46  mov     rax, [rax+8]
0x18000bd4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd4f  mov     [rsp+58h+var_38], rbx
0x18000bd54  jmp     short loc_18000BD69
0x18000bd56  mov     rsi, [rsp+58h+arg_10]
0x18000bd5b  mov     r14, [rsp+58h+arg_8]
0x18000bd60  mov     edi, [rsp+58h+arg_18]
0x18000bd64  mov     rbx, [rsp+58h+var_38]
0x18000bd69  test    rbx, rbx
0x18000bd6c  jz      short loc_18000BD9C
0x18000bd6e  mov     rax, [rbx]
0x18000bd71  mov     r8, rsi
0x18000bd74  mov     rdx, r14
0x18000bd77  mov     rcx, rbx
0x18000bd7a  mov     rax, [rax]
0x18000bd7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd82  mov     edi, eax
0x18000bd84  test    eax, eax
0x18000bd86  jz      short loc_18000BD9C
0x18000bd88  mov     rdx, [rbx]
0x18000bd8b  mov     rax, [rdx+18h]
0x18000bd8f  mov     edx, 1
0x18000bd94  mov     rcx, rbx
0x18000bd97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd9c  mov     eax, edi
0x18000bd9e  add     rsp, 30h
0x18000bda2  pop     r15
0x18000bda4  pop     r14
0x18000bda6  pop     rdi
0x18000bda7  pop     rsi
0x18000bda8  pop     rbx
0x18000bda9  retn
```
