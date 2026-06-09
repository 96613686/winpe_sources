# CASFReader::CheckMetadataForVIH2Props(CASFOutput *,ushort,long *,long *)

- ea: `0x180008b9c`
- end: `0x180008cb3`
- name: `?CheckMetadataForVIH2Props@CASFReader@@AEAAJPEAVCASFOutput@@GPEAJ1@Z`
- size: `279`
- prototype: `__int64 __fastcall(CASFReader *this, struct CASFOutput *, __int16, int *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ab04`

## callees

- `0x180001460`
- `0x180008b9c`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::CheckMetadataForVIH2Props(
        CASFReader *this,
        struct CASFOutput *a2,
        __int16 a3,
        int *a4,
        int *a5)
{
  int (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // rcx
  int v8; // eax
  __int64 v9; // rcx
  __int16 v11; // [rsp+40h] [rbp-38h] BYREF
  __int16 v12; // [rsp+48h] [rbp-30h] BYREF
  int v13; // [rsp+50h] [rbp-28h] BYREF
  int v14; // [rsp+54h] [rbp-24h] BYREF
  __int64 v15; // [rsp+58h] [rbp-20h] BYREF

  v5 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 43);
  v12 = a3;
  v15 = 0;
  if ( (**v5)(v5, &IID_IWMHeaderInfo, &v15) >= 0 )
  {
    v14 = 0;
    v11 = 4;
    v13 = 0;
    if ( (*(int (__fastcall **)(__int64, __int16 *, const wchar_t *, int *, int *, __int16 *))(*(_QWORD *)v15 + 40LL))(
           v15,
           &v12,
           L"AspectRatioX",
           &v14,
           &v13,
           &v11) >= 0 )
    {
      v8 = v13;
      v9 = v15;
      *((_DWORD *)a2 + 103) = 1;
      *a4 = v8;
      if ( (*(int (__fastcall **)(__int64, __int16 *, const wchar_t *, int *, int *, __int16 *))(*(_QWORD *)v9 + 40LL))(
             v9,
             &v12,
             L"AspectRatioY",
             &v14,
             &v13,
             &v11) >= 0 )
        *a5 = v13;
    }
  }
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  return 0;
}

```

## disassembly

```asm
0x180008b9c  push    rbp
0x180008b9e  push    rbx
0x180008b9f  push    rsi
0x180008ba0  push    rdi
0x180008ba1  mov     rbp, rsp
0x180008ba4  sub     rsp, 78h
0x180008ba8  mov     rax, cs:__security_cookie
0x180008baf  xor     rax, rsp
0x180008bb2  mov     [rbp+var_18], rax
0x180008bb6  mov     rcx, [rcx+158h]
0x180008bbd  mov     rdi, rdx
0x180008bc0  mov     rbx, [rbp+arg_20]
0x180008bc4  lea     rdx, IID_IWMHeaderInfo
0x180008bcb  mov     [rbp+var_30], r8w
0x180008bd0  mov     rsi, r9
0x180008bd3  mov     [rbp+var_20], 0
0x180008bdb  lea     r8, [rbp+var_20]
0x180008bdf  mov     rax, [rcx]
0x180008be2  mov     rax, [rax]
0x180008be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bea  test    eax, eax
0x180008bec  js      loc_180008C87
0x180008bf2  mov     rcx, [rbp+var_20]
0x180008bf6  lea     rdx, [rbp+var_38]
0x180008bfa  mov     [rsp+78h+var_50], rdx
0x180008bff  lea     r9, [rbp+var_24]
0x180008c03  mov     eax, 4
0x180008c08  mov     [rbp+var_24], 0
0x180008c0f  mov     [rbp+var_38], ax
0x180008c13  lea     rdx, [rbp+var_28]
0x180008c17  mov     [rbp+var_28], 0
0x180008c1e  lea     r8, aAspectratiox; "AspectRatioX"
0x180008c25  mov     rax, [rcx]
0x180008c28  mov     [rsp+78h+var_58], rdx
0x180008c2d  lea     rdx, [rbp+var_30]
0x180008c31  mov     rax, [rax+28h]
0x180008c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c3a  test    eax, eax
0x180008c3c  js      short loc_180008C87
0x180008c3e  mov     eax, [rbp+var_28]
0x180008c41  lea     rdx, [rbp+var_38]
0x180008c45  mov     rcx, [rbp+var_20]
0x180008c49  lea     r9, [rbp+var_24]
0x180008c4d  mov     [rsp+78h+var_50], rdx
0x180008c52  lea     r8, aAspectratioy; "AspectRatioY"
0x180008c59  mov     dword ptr [rdi+19Ch], 1
0x180008c63  lea     rdx, [rbp+var_28]
0x180008c67  mov     [rsi], eax
0x180008c69  mov     rax, [rcx]
0x180008c6c  mov     [rsp+78h+var_58], rdx
0x180008c71  lea     rdx, [rbp+var_30]
0x180008c75  mov     rax, [rax+28h]
0x180008c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c7e  test    eax, eax
0x180008c80  js      short loc_180008C87
0x180008c82  mov     eax, [rbp+var_28]
0x180008c85  mov     [rbx], eax
0x180008c87  mov     rcx, [rbp+var_20]
0x180008c8b  test    rcx, rcx
0x180008c8e  jz      short loc_180008C9C
0x180008c90  mov     rax, [rcx]
0x180008c93  mov     rax, [rax+10h]
0x180008c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c9c  xor     eax, eax
0x180008c9e  mov     rcx, [rbp+var_18]
0x180008ca2  xor     rcx, rsp; StackCookie
0x180008ca5  call    __security_check_cookie
0x180008caa  add     rsp, 78h
0x180008cae  pop     rdi
0x180008caf  pop     rsi
0x180008cb0  pop     rbx
0x180008cb1  pop     rbp
0x180008cb2  retn
```
