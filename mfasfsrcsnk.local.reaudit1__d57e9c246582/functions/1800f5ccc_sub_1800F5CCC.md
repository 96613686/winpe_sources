# sub_1800F5CCC

- ea: `0x1800f5ccc`
- end: `0x1800f60b7`
- name: `sub_1800F5CCC`
- size: `1003`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800f366c`

## callees

- `0x1800018b0`
- `0x180005d20`
- `0x18000ae10`
- `0x18003f940`
- `0x180051e44`
- `0x1800620b4`
- `0x180083a48`
- `0x1800f5ccc`
- `0x180146950`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1800f5d91`
- `MFPlat!MFCreateMediaType` at `0x1800f5d91`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5db3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5e72`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5f2d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5fe4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5db3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5e72`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5f2d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f5fe4`

## pseudocode

```c
__int64 __fastcall sub_1800F5CCC(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rdi
  int v7; // ebx
  __int128 v8; // xmm0
  __int64 v9; // rdx
  HRESULT v10; // ebx
  __int64 (__fastcall ***v11)(); // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 (__fastcall ***v16)(); // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 (__fastcall ***v20)(); // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 (__fastcall ***v24)(); // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  _BYTE v28[8]; // [rsp+30h] [rbp-58h] BYREF
  IMFMediaType *ppMFType; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v30[16]; // [rsp+40h] [rbp-48h] BYREF

  ppMFType = 0;
  sub_18000AE10(v28, "CMFVideoThumbnail::SetSupportedMediaType", 1978);
  if ( *(_BYTE *)(qword_180171350 + 8) && *(_QWORD *)(a1 + 400) )
  {
    v6 = sub_1800018B0(qword_180171350);
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 400) + 296LL))(*(_QWORD *)(a1 + 400));
    v8 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 400) + 280LL))(
                      *(_QWORD *)(a1 + 400),
                      v30);
    *(_DWORD *)(v6 + 2016) = v7;
    *(_OWORD *)(v6 + 2000) = v8;
  }
  sub_1800620B4(&ppMFType);
  v10 = MFCreateMediaType(&ppMFType);
  if ( v10 >= 0 )
  {
    v10 = ((__int64 (__fastcall *)(IMFMediaType *, __int64 *, const char *))ppMFType->lpVtbl->SetGUID)(
            ppMFType,
            qword_180156A10,
            "vids");
    if ( v10 >= 0 )
    {
      v10 = ((__int64 (__fastcall *)(IMFMediaType *, __int64 *, __int64))ppMFType->lpVtbl->SetGUID)(
              ppMFType,
              qword_180156A20,
              a3);
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, IMFMediaType *))(*(_QWORD *)a2 + 56LL))(
                a2,
                *(unsigned int *)(a1 + 24),
                0,
                ppMFType);
        if ( v10 < 0 )
        {
          v24 = (__int64 (__fastcall ***)())qword_180171350;
          if ( !qword_180171350 )
          {
            v25 = MFGetCallStackTracingWeakReference(0, v23);
            qword_180171350 = v25;
            if ( v25 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
            {
              v24 = (__int64 (__fastcall ***)())qword_180171350;
            }
            else
            {
              v24 = &off_1801703B0;
              qword_180171350 = (__int64)&off_1801703B0;
            }
          }
          if ( *((_BYTE *)v24 + 8) )
          {
            v26 = sub_1800018B0(v24);
            if ( *(_DWORD *)(v26 + 1996) != v10 )
              sub_180083A48(v26, "CMFVideoThumbnail::SetSupportedMediaType", 1987, (unsigned int)v10);
          }
          if ( byte_1801712C8 )
          {
            v14 = 206;
            goto LABEL_48;
          }
        }
      }
      else
      {
        v20 = (__int64 (__fastcall ***)())qword_180171350;
        if ( !qword_180171350 )
        {
          v21 = MFGetCallStackTracingWeakReference(0, v19);
          qword_180171350 = v21;
          if ( v21 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
          {
            v20 = (__int64 (__fastcall ***)())qword_180171350;
          }
          else
          {
            v20 = &off_1801703B0;
            qword_180171350 = (__int64)&off_1801703B0;
          }
        }
        if ( *((_BYTE *)v20 + 8) )
        {
          v22 = sub_1800018B0(v20);
          if ( *(_DWORD *)(v22 + 1996) != v10 )
            sub_180083A48(v22, "CMFVideoThumbnail::SetSupportedMediaType", 1981, (unsigned int)v10);
        }
        if ( byte_1801712C8 )
        {
          v14 = 205;
          goto LABEL_48;
        }
      }
    }
    else
    {
      v16 = (__int64 (__fastcall ***)())qword_180171350;
      if ( !qword_180171350 )
      {
        v17 = MFGetCallStackTracingWeakReference(0, v15);
        qword_180171350 = v17;
        if ( v17 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
        {
          v16 = (__int64 (__fastcall ***)())qword_180171350;
        }
        else
        {
          v16 = &off_1801703B0;
          qword_180171350 = (__int64)&off_1801703B0;
        }
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v18 = sub_1800018B0(v16);
        if ( *(_DWORD *)(v18 + 1996) != v10 )
          sub_180083A48(v18, "CMFVideoThumbnail::SetSupportedMediaType", 1980, (unsigned int)v10);
      }
      if ( byte_1801712C8 )
      {
        v14 = 204;
        goto LABEL_48;
      }
    }
  }
  else
  {
    v11 = (__int64 (__fastcall ***)())qword_180171350;
    if ( !qword_180171350 )
    {
      v12 = MFGetCallStackTracingWeakReference(0, v9);
      qword_180171350 = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 (__fastcall ***)())qword_180171350;
      }
      else
      {
        v11 = &off_1801703B0;
        qword_180171350 = (__int64)&off_1801703B0;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      v13 = sub_1800018B0(v11);
      if ( *(_DWORD *)(v13 + 1996) != v10 )
        sub_180083A48(v13, "CMFVideoThumbnail::SetSupportedMediaType", 1978, (unsigned int)v10);
    }
    if ( byte_1801712C8 )
    {
      v14 = 203;
LABEL_48:
      sub_180051E44(*((_QWORD *)RequestContext + 2), v14, &stru_1801626E8, a1, v10);
    }
  }
  sub_180005D20();
  sub_1800620B4(&ppMFType);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800f5ccc  mov     [rsp+arg_18], rbx
0x1800f5cd1  push    rbp
0x1800f5cd2  push    rsi
0x1800f5cd3  push    rdi
0x1800f5cd4  push    r12
0x1800f5cd6  push    r14
0x1800f5cd8  sub     rsp, 60h
0x1800f5cdc  mov     rax, cs:__security_cookie
0x1800f5ce3  xor     rax, rsp
0x1800f5ce6  mov     [rsp+88h+var_38], rax
0x1800f5ceb  mov     rbp, r8
0x1800f5cee  mov     [rsp+88h+ppMFType], 0
0x1800f5cf7  mov     r14, rdx
0x1800f5cfa  lea     r12, aCmfvideothumbn_20; "CMFVideoThumbnail::SetSupportedMediaTyp"...
0x1800f5d01  mov     rsi, rcx
0x1800f5d04  mov     rdx, r12
0x1800f5d07  mov     r8d, 7BAh
0x1800f5d0d  lea     rcx, [rsp+88h+var_58]
0x1800f5d12  call    sub_18000AE10
0x1800f5d17  mov     rcx, cs:qword_180171350
0x1800f5d1e  cmp     byte ptr [rcx+8], 0
0x1800f5d22  jz      short loc_1800F5D82
0x1800f5d24  cmp     qword ptr [rsi+190h], 0
0x1800f5d2c  jz      short loc_1800F5D82
0x1800f5d2e  call    sub_1800018B0
0x1800f5d33  mov     rdx, [rsi+190h]
0x1800f5d3a  mov     rdi, rax
0x1800f5d3d  mov     rcx, [rdx]
0x1800f5d40  mov     rax, [rcx+128h]
0x1800f5d47  mov     rcx, rdx
0x1800f5d4a  call    cs:__guard_dispatch_icall_fptr
0x1800f5d50  mov     r8, [rsi+190h]
0x1800f5d57  lea     rdx, [rsp+88h+var_48]
0x1800f5d5c  mov     ebx, eax
0x1800f5d5e  mov     rcx, [r8]
0x1800f5d61  mov     rax, [rcx+118h]
0x1800f5d68  mov     rcx, r8
0x1800f5d6b  call    cs:__guard_dispatch_icall_fptr
0x1800f5d71  movups  xmm0, xmmword ptr [rax]
0x1800f5d74  mov     [rdi+7E0h], ebx
0x1800f5d7a  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800f5d82  lea     rcx, [rsp+88h+ppMFType]
0x1800f5d87  call    sub_1800620B4
0x1800f5d8c  lea     rcx, [rsp+88h+ppMFType]; ppMFType
0x1800f5d91  call    cs:MFCreateMediaType
0x1800f5d98  nop     dword ptr [rax+rax+00h]
0x1800f5d9d  mov     ebx, eax
0x1800f5d9f  test    eax, eax
0x1800f5da1  jns     loc_1800F5E39
0x1800f5da7  mov     rcx, cs:qword_180171350
0x1800f5dae  test    rcx, rcx
0x1800f5db1  jnz     short loc_1800F5DFB
0x1800f5db3  call    cs:MFGetCallStackTracingWeakReference
0x1800f5dba  nop     dword ptr [rax+rax+00h]
0x1800f5dbf  mov     cs:qword_180171350, rax
0x1800f5dc6  mov     rcx, rax
0x1800f5dc9  test    rax, rax
0x1800f5dcc  jz      short loc_1800F5DED
0x1800f5dce  mov     rax, [rax]
0x1800f5dd1  mov     edx, 7F0h
0x1800f5dd6  mov     rax, [rax+8]
0x1800f5dda  call    cs:__guard_dispatch_icall_fptr
0x1800f5de0  test    eax, eax
0x1800f5de2  jz      short loc_1800F5DED
0x1800f5de4  mov     rcx, cs:qword_180171350
0x1800f5deb  jmp     short loc_1800F5DFB
0x1800f5ded  lea     rcx, off_1801703B0
0x1800f5df4  mov     cs:qword_180171350, rcx
0x1800f5dfb  cmp     byte ptr [rcx+8], 0
0x1800f5dff  jz      short loc_1800F5E22
0x1800f5e01  call    sub_1800018B0
0x1800f5e06  cmp     [rax+7CCh], ebx
0x1800f5e0c  jz      short loc_1800F5E22
0x1800f5e0e  mov     r9d, ebx
0x1800f5e11  mov     r8d, 7BAh
0x1800f5e17  mov     rdx, r12
0x1800f5e1a  mov     rcx, rax
0x1800f5e1d  call    sub_180083A48
0x1800f5e22  cmp     cs:byte_1801712C8, 1
0x1800f5e29  jb      loc_1800F607F
0x1800f5e2f  mov     edx, 0CBh
0x1800f5e34  jmp     loc_1800F6061
0x1800f5e39  mov     rcx, [rsp+88h+ppMFType]
0x1800f5e3e  lea     r8, aVids; "vids"
0x1800f5e45  lea     rdx, qword_180156A10
0x1800f5e4c  mov     rax, [rcx]
0x1800f5e4f  mov     rax, [rax+0C0h]
0x1800f5e56  call    cs:__guard_dispatch_icall_fptr
0x1800f5e5c  mov     ebx, eax
0x1800f5e5e  test    eax, eax
0x1800f5e60  jns     loc_1800F5EF8
0x1800f5e66  mov     rcx, cs:qword_180171350
0x1800f5e6d  test    rcx, rcx
0x1800f5e70  jnz     short loc_1800F5EBA
0x1800f5e72  call    cs:MFGetCallStackTracingWeakReference
0x1800f5e79  nop     dword ptr [rax+rax+00h]
0x1800f5e7e  mov     cs:qword_180171350, rax
0x1800f5e85  mov     rcx, rax
0x1800f5e88  test    rax, rax
0x1800f5e8b  jz      short loc_1800F5EAC
0x1800f5e8d  mov     rax, [rax]
0x1800f5e90  mov     edx, 7F0h
0x1800f5e95  mov     rax, [rax+8]
0x1800f5e99  call    cs:__guard_dispatch_icall_fptr
0x1800f5e9f  test    eax, eax
0x1800f5ea1  jz      short loc_1800F5EAC
0x1800f5ea3  mov     rcx, cs:qword_180171350
0x1800f5eaa  jmp     short loc_1800F5EBA
0x1800f5eac  lea     rcx, off_1801703B0
0x1800f5eb3  mov     cs:qword_180171350, rcx
0x1800f5eba  cmp     byte ptr [rcx+8], 0
0x1800f5ebe  jz      short loc_1800F5EE1
0x1800f5ec0  call    sub_1800018B0
0x1800f5ec5  cmp     [rax+7CCh], ebx
0x1800f5ecb  jz      short loc_1800F5EE1
0x1800f5ecd  mov     r9d, ebx
0x1800f5ed0  mov     r8d, 7BCh
0x1800f5ed6  mov     rdx, r12
0x1800f5ed9  mov     rcx, rax
0x1800f5edc  call    sub_180083A48
0x1800f5ee1  cmp     cs:byte_1801712C8, 1
0x1800f5ee8  jb      loc_1800F607F
0x1800f5eee  mov     edx, 0CCh
0x1800f5ef3  jmp     loc_1800F6061
0x1800f5ef8  mov     rcx, [rsp+88h+ppMFType]
0x1800f5efd  lea     rdx, qword_180156A20
0x1800f5f04  mov     r8, rbp
0x1800f5f07  mov     rax, [rcx]
0x1800f5f0a  mov     rax, [rax+0C0h]
0x1800f5f11  call    cs:__guard_dispatch_icall_fptr
0x1800f5f17  mov     ebx, eax
0x1800f5f19  test    eax, eax
0x1800f5f1b  jns     loc_1800F5FB3
0x1800f5f21  mov     rcx, cs:qword_180171350
0x1800f5f28  test    rcx, rcx
0x1800f5f2b  jnz     short loc_1800F5F75
0x1800f5f2d  call    cs:MFGetCallStackTracingWeakReference
0x1800f5f34  nop     dword ptr [rax+rax+00h]
0x1800f5f39  mov     cs:qword_180171350, rax
0x1800f5f40  mov     rcx, rax
0x1800f5f43  test    rax, rax
0x1800f5f46  jz      short loc_1800F5F67
0x1800f5f48  mov     rax, [rax]
0x1800f5f4b  mov     edx, 7F0h
0x1800f5f50  mov     rax, [rax+8]
0x1800f5f54  call    cs:__guard_dispatch_icall_fptr
0x1800f5f5a  test    eax, eax
0x1800f5f5c  jz      short loc_1800F5F67
0x1800f5f5e  mov     rcx, cs:qword_180171350
0x1800f5f65  jmp     short loc_1800F5F75
0x1800f5f67  lea     rcx, off_1801703B0
0x1800f5f6e  mov     cs:qword_180171350, rcx
0x1800f5f75  cmp     byte ptr [rcx+8], 0
0x1800f5f79  jz      short loc_1800F5F9C
0x1800f5f7b  call    sub_1800018B0
0x1800f5f80  cmp     [rax+7CCh], ebx
0x1800f5f86  jz      short loc_1800F5F9C
0x1800f5f88  mov     r9d, ebx
0x1800f5f8b  mov     r8d, 7BDh
0x1800f5f91  mov     rdx, r12
0x1800f5f94  mov     rcx, rax
0x1800f5f97  call    sub_180083A48
0x1800f5f9c  cmp     cs:byte_1801712C8, 1
0x1800f5fa3  jb      loc_1800F607F
0x1800f5fa9  mov     edx, 0CDh
0x1800f5fae  jmp     loc_1800F6061
0x1800f5fb3  mov     rax, [r14]
0x1800f5fb6  xor     r8d, r8d
0x1800f5fb9  mov     r9, [rsp+88h+ppMFType]
0x1800f5fbe  mov     rcx, r14
0x1800f5fc1  mov     edx, [rsi+18h]
0x1800f5fc4  mov     rax, [rax+38h]
0x1800f5fc8  call    cs:__guard_dispatch_icall_fptr
0x1800f5fce  mov     ebx, eax
0x1800f5fd0  test    eax, eax
0x1800f5fd2  jns     loc_1800F607F
0x1800f5fd8  mov     rcx, cs:qword_180171350
0x1800f5fdf  test    rcx, rcx
0x1800f5fe2  jnz     short loc_1800F602C
0x1800f5fe4  call    cs:MFGetCallStackTracingWeakReference
0x1800f5feb  nop     dword ptr [rax+rax+00h]
0x1800f5ff0  mov     cs:qword_180171350, rax
0x1800f5ff7  mov     rcx, rax
0x1800f5ffa  test    rax, rax
0x1800f5ffd  jz      short loc_1800F601E
0x1800f5fff  mov     rax, [rax]
0x1800f6002  mov     edx, 7F0h
0x1800f6007  mov     rax, [rax+8]
0x1800f600b  call    cs:__guard_dispatch_icall_fptr
0x1800f6011  test    eax, eax
0x1800f6013  jz      short loc_1800F601E
0x1800f6015  mov     rcx, cs:qword_180171350
0x1800f601c  jmp     short loc_1800F602C
0x1800f601e  lea     rcx, off_1801703B0
0x1800f6025  mov     cs:qword_180171350, rcx
0x1800f602c  cmp     byte ptr [rcx+8], 0
0x1800f6030  jz      short loc_1800F6053
0x1800f6032  call    sub_1800018B0
0x1800f6037  cmp     [rax+7CCh], ebx
0x1800f603d  jz      short loc_1800F6053
0x1800f603f  mov     r9d, ebx
0x1800f6042  mov     r8d, 7C3h
0x1800f6048  mov     rdx, r12
0x1800f604b  mov     rcx, rax
0x1800f604e  call    sub_180083A48
0x1800f6053  cmp     cs:byte_1801712C8, 1
0x1800f605a  jb      short loc_1800F607F
0x1800f605c  mov     edx, 0CEh
0x1800f6061  mov     rcx, cs:RequestContext
0x1800f6068  lea     r8, stru_1801626E8
0x1800f606f  mov     r9, rsi
0x1800f6072  mov     [rsp+88h+var_68], ebx
0x1800f6076  mov     rcx, [rcx+10h]
0x1800f607a  call    sub_180051E44
0x1800f607f  lea     rcx, [rsp+88h+var_58]
0x1800f6084  call    sub_180005D20
0x1800f6089  lea     rcx, [rsp+88h+ppMFType]
0x1800f608e  call    sub_1800620B4
0x1800f6093  mov     eax, ebx
0x1800f6095  mov     rcx, [rsp+88h+var_38]
0x1800f609a  xor     rcx, rsp; StackCookie
0x1800f609d  call    __security_check_cookie
0x1800f60a2  mov     rbx, [rsp+88h+arg_18]
0x1800f60aa  add     rsp, 60h
0x1800f60ae  pop     r14
0x1800f60b0  pop     r12
0x1800f60b2  pop     rdi
0x1800f60b3  pop     rsi
0x1800f60b4  pop     rbp
0x1800f60b5  retn
```
