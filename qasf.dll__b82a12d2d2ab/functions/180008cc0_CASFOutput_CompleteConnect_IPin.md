# CASFOutput::CompleteConnect(IPin *)

- ea: `0x180008cc0`
- end: `0x180008edf`
- name: `?CompleteConnect@CASFOutput@@UEAAJPEAUIPin@@@Z`
- size: `543`
- prototype: `__int64 __fastcall(CASFOutput *__hidden this, struct IPin *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x180008cc0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFOutput::CompleteConnect(CASFOutput *this, struct IPin *a2)
{
  __int64 v3; // rcx
  __int64 v4; // rdx
  int v5; // edi
  unsigned int v6; // eax
  unsigned int v7; // ecx
  void (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v9; // rdx
  void (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v12; // [rsp+30h] [rbp-38h] BYREF
  int v13; // [rsp+38h] [rbp-30h]
  int v14; // [rsp+3Ch] [rbp-2Ch]
  unsigned int v15; // [rsp+40h] [rbp-28h] BYREF
  __int64 v16; // [rsp+48h] [rbp-20h] BYREF
  __int64 v17; // [rsp+50h] [rbp-18h] BYREF

  v3 = *((_QWORD *)this + 37);
  if ( !*(_DWORD *)(v3 + 448) )
    return (unsigned int)(*(__int64 (__fastcall **)(CASFOutput *, _QWORD, char *))(*(_QWORD *)this + 112LL))(
                           this,
                           *((_QWORD *)this + 28),
                           (char *)this + 216);
  v4 = *((unsigned int *)this + 76);
  v15 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned int *))(**(_QWORD **)(v3 + 352) + 160LL))(
         *(_QWORD *)(v3 + 352),
         v4,
         &v15);
  if ( v5 >= 0 )
  {
    v6 = v15;
    if ( v15 <= *((_DWORD *)this + 78) )
      v6 = *((_DWORD *)this + 78);
    else
      *((_DWORD *)this + 78) = v15;
    v7 = *((_DWORD *)this + 36);
    if ( v7 > v6 )
      *((_DWORD *)this + 78) = v7;
  }
  HIDWORD(v12) = 299081927;
  v13 = -1073707847;
  v14 = -982307249;
  if ( *((_DWORD *)this + 31) == 299081927 && *((_DWORD *)this + 32) == v13 && *((_DWORD *)this + 33) == v14 )
  {
    v5 = -2147467262;
    v8 = *(void (__fastcall ****)(_QWORD, GUID *, __int64 *))(*((_QWORD *)this + 37) + 344LL);
    v12 = 0;
    if ( !v8 )
      return (unsigned int)v5;
    (**v8)(v8, &IID_IWMReaderAccelerator, &v12);
    if ( !v12 )
      return (unsigned int)v5;
    v9 = *((unsigned int *)this + 76);
    v17 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, __int64 *))(*(_QWORD *)v12 + 24LL))(
           v12,
           v9,
           &GUID_d98ee251_34e0_4a2d_9312_9b4c788d9fa1,
           &v17);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v17 + 32LL))(v17, (char *)this + 104);
      if ( v5 >= 0 )
      {
        v10 = *(void (__fastcall ****)(_QWORD, GUID *, __int64 *))(*((_QWORD *)this + 37) + 344LL);
        v16 = 0;
        if ( v10 )
        {
          (**v10)(v10, &IID_IWMReaderAccelerator, &v16);
          if ( v16 )
          {
            v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v16 + 32LL))(
                   v16,
                   *((unsigned int *)this + 76),
                   (char *)this + 104);
            if ( v16 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          }
        }
      }
    }
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  if ( v5 >= 0 )
    return (unsigned int)(*(__int64 (__fastcall **)(CASFOutput *, _QWORD, char *))(*(_QWORD *)this + 112LL))(
                           this,
                           *((_QWORD *)this + 28),
                           (char *)this + 216);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180008cc0  push    rbp
0x180008cc2  push    rbx
0x180008cc3  push    rsi
0x180008cc4  push    rdi
0x180008cc5  mov     rbp, rsp
0x180008cc8  sub     rsp, 68h
0x180008ccc  mov     rax, cs:__security_cookie
0x180008cd3  xor     rax, rsp
0x180008cd6  mov     [rbp+var_10], rax
0x180008cda  mov     rbx, rcx
0x180008cdd  mov     rcx, [rcx+128h]
0x180008ce4  cmp     dword ptr [rcx+1C0h], 0
0x180008ceb  jz      loc_180008EA9
0x180008cf1  mov     edx, [rbx+130h]
0x180008cf7  lea     r8, [rbp+var_28]
0x180008cfb  mov     [rbp+var_28], 0
0x180008d02  mov     rcx, [rcx+160h]
0x180008d09  mov     rax, [rcx]
0x180008d0c  mov     rax, [rax+0A0h]
0x180008d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d18  mov     edi, eax
0x180008d1a  test    eax, eax
0x180008d1c  js      short loc_180008D45
0x180008d1e  mov     ecx, [rbx+138h]
0x180008d24  mov     eax, [rbp+var_28]
0x180008d27  cmp     eax, ecx
0x180008d29  jbe     short loc_180008D33
0x180008d2b  mov     [rbx+138h], eax
0x180008d31  jmp     short loc_180008D35
0x180008d33  mov     eax, ecx
0x180008d35  mov     ecx, [rbx+90h]
0x180008d3b  cmp     ecx, eax
0x180008d3d  jbe     short loc_180008D45
0x180008d3f  mov     [rbx+138h], ecx
0x180008d45  mov     dword ptr [rbp+var_38+4], 11D3A0C7h
0x180008d4c  mov     eax, dword ptr [rbp+var_38+4]
0x180008d4f  mov     [rbp+var_30], 0C00084B9h
0x180008d56  mov     [rbp+var_2C], 0C5732E4Fh
0x180008d5d  cmp     [rbx+7Ch], eax
0x180008d60  jnz     loc_180008EA5
0x180008d66  mov     eax, [rbp+var_30]
0x180008d69  cmp     [rbx+80h], eax
0x180008d6f  jnz     loc_180008EA5
0x180008d75  mov     eax, [rbp+var_2C]
0x180008d78  cmp     [rbx+84h], eax
0x180008d7e  jnz     loc_180008EA5
0x180008d84  mov     rax, [rbx+128h]
0x180008d8b  mov     edi, 80004002h
0x180008d90  mov     rcx, [rax+158h]
0x180008d97  mov     qword ptr [rbp-38h], 0
0x180008d9f  test    rcx, rcx
0x180008da2  jz      loc_180008EC8
0x180008da8  mov     rax, [rcx]
0x180008dab  lea     r8, [rbp+var_38]
0x180008daf  lea     rdx, IID_IWMReaderAccelerator
0x180008db6  mov     rax, [rax]
0x180008db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dbe  mov     rcx, [rbp+var_38]
0x180008dc2  test    rcx, rcx
0x180008dc5  jz      loc_180008EC8
0x180008dcb  mov     edx, [rbx+130h]
0x180008dd1  lea     r9, [rbp+var_18]
0x180008dd5  mov     [rbp+var_18], 0
0x180008ddd  lea     r8, _GUID_d98ee251_34e0_4a2d_9312_9b4c788d9fa1
0x180008de4  mov     rax, [rcx]
0x180008de7  mov     rax, [rax+18h]
0x180008deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008df0  mov     edi, eax
0x180008df2  test    eax, eax
0x180008df4  js      loc_180008E7B
0x180008dfa  mov     rcx, [rbp+var_18]
0x180008dfe  lea     rdx, [rbx+68h]
0x180008e02  mov     rax, [rcx]
0x180008e05  mov     rax, [rax+20h]
0x180008e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e0e  mov     edi, eax
0x180008e10  test    eax, eax
0x180008e12  js      short loc_180008E7B
0x180008e14  mov     rax, [rbx+128h]
0x180008e1b  mov     rcx, [rax+158h]
0x180008e22  mov     [rbp+var_20], 0
0x180008e2a  test    rcx, rcx
0x180008e2d  jz      short loc_180008E7B
0x180008e2f  mov     rax, [rcx]
0x180008e32  lea     r8, [rbp+var_20]
0x180008e36  lea     rdx, IID_IWMReaderAccelerator
0x180008e3d  mov     rax, [rax]
0x180008e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e45  mov     rcx, [rbp+var_20]
0x180008e49  test    rcx, rcx
0x180008e4c  jz      short loc_180008E7B
0x180008e4e  mov     rax, [rcx]
0x180008e51  lea     r8, [rbx+68h]
0x180008e55  mov     edx, [rbx+130h]
0x180008e5b  mov     rax, [rax+20h]
0x180008e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e64  mov     rcx, [rbp+var_20]
0x180008e68  mov     edi, eax
0x180008e6a  test    rcx, rcx
0x180008e6d  jz      short loc_180008E7B
0x180008e6f  mov     rax, [rcx]
0x180008e72  mov     rax, [rax+10h]
0x180008e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e7b  mov     rcx, [rbp+var_18]
0x180008e7f  test    rcx, rcx
0x180008e82  jz      short loc_180008E90
0x180008e84  mov     rax, [rcx]
0x180008e87  mov     rax, [rax+10h]
0x180008e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e90  mov     rcx, [rbp+var_38]
0x180008e94  test    rcx, rcx
0x180008e97  jz      short loc_180008EA5
0x180008e99  mov     rax, [rcx]
0x180008e9c  mov     rax, [rax+10h]
0x180008ea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ea5  test    edi, edi
0x180008ea7  js      short loc_180008EC8
0x180008ea9  mov     rax, [rbx]
0x180008eac  lea     r8, [rbx+0D8h]
0x180008eb3  mov     rdx, [rbx+0E0h]
0x180008eba  mov     rcx, rbx
0x180008ebd  mov     rax, [rax+70h]
0x180008ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ec6  mov     edi, eax
0x180008ec8  mov     eax, edi
0x180008eca  mov     rcx, [rbp+var_10]
0x180008ece  xor     rcx, rsp; StackCookie
0x180008ed1  call    __security_check_cookie
0x180008ed6  add     rsp, 68h
0x180008eda  pop     rdi
0x180008edb  pop     rsi
0x180008edc  pop     rbx
0x180008edd  pop     rbp
0x180008ede  retn
```
