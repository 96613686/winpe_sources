# CContainer::ParseDescriptor(IStream *,_DMUS_OBJECTDESC *)

- ea: `0x18000eee0`
- end: `0x18000f230`
- name: `?ParseDescriptor@CContainer@@UEAAJPEAUIStream@@PEAU_DMUS_OBJECTDESC@@@Z`
- size: `848`
- prototype: `__int64 __fastcall(CContainer *__hidden this, struct IStream *, struct _DMUS_OBJECTDESC *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800015d0`
- `0x18000df2c`
- `0x18000eee0`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CContainer::ParseDescriptor(CContainer *this, struct IStream *a2, struct _DMUS_OBJECTDESC *a3)
{
  __int64 result; // rax
  __int64 v6; // rdi
  int v7; // esi
  int v8; // esi
  __int64 v9; // r8
  __int64 v10; // r8
  unsigned int v11; // ebx
  int v12; // [rsp+30h] [rbp-29h] BYREF
  __int64 v13; // [rsp+38h] [rbp-21h] BYREF
  __int64 v14; // [rsp+40h] [rbp-19h] BYREF
  int v15; // [rsp+48h] [rbp-11h]
  __int64 v16; // [rsp+4Ch] [rbp-Dh]
  __int128 v17; // [rsp+58h] [rbp-1h] BYREF
  int v18; // [rsp+68h] [rbp+Fh]
  __int64 v19; // [rsp+70h] [rbp+17h] BYREF
  int v20; // [rsp+78h] [rbp+1Fh]
  __int64 v21; // [rsp+7Ch] [rbp+23h]

  if ( !a2 || !a2->lpVtbl || !a2->lpVtbl->QueryInterface )
    return 2147500035LL;
  if ( !a3 || *(_DWORD *)a3 < 0x358u )
    return 2147942487LL;
  if ( *((_BYTE *)this + 864) )
    return 142086678;
  v13 = 0;
  result = AllocRIFFStream(a2, &v13);
  if ( (int)result >= 0 )
  {
    v6 = v13;
    v19 = 0;
    v21 = 0;
    v20 = 1313033540;
    v7 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD, __int64))(*(_QWORD *)v13 + 24LL))(v13, &v19, 0, 32);
    if ( v7 < 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      return (unsigned int)v7;
    }
    *((_DWORD *)a3 + 1) = 2;
    v18 = 0;
    v14 = 0;
    *(GUID *)((char *)a3 + 24) = CLSID_DirectMusicContainer;
    v16 = 0;
    v12 = 0;
    v17 = 0;
    v15 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *, _QWORD))(*(_QWORD *)v6 + 24LL))(v6, &v14, &v19, 0);
    if ( v8 >= 0 )
    {
      while ( (_DWORD)v14 != 1414744396 )
      {
        switch ( (_DWORD)v14 )
        {
          case 0x64697567:
            if ( HIDWORD(v14) != 16 )
              goto LABEL_37;
            v8 = ((__int64 (__fastcall *)(struct IStream *, char *, __int64, int *))a2->lpVtbl->Read)(
                   a2,
                   (char *)a3 + 8,
                   16,
                   &v12);
            if ( v8 < 0 )
              goto LABEL_40;
            if ( v12 == 16 )
              *((_DWORD *)a3 + 1) |= 1u;
            break;
          case 0x65746164:
            v8 = ((__int64 (__fastcall *)(struct IStream *, char *, __int64, int *))a2->lpVtbl->Read)(
                   a2,
                   (char *)a3 + 40,
                   8,
                   &v12);
            if ( v8 < 0 )
              goto LABEL_40;
            *((_DWORD *)a3 + 1) |= 0x100u;
            break;
          case 0x67746163:
            v9 = HIDWORD(v14);
            if ( HIDWORD(v14) > 0x80 )
              v9 = 128;
            v8 = ((__int64 (__fastcall *)(struct IStream *, char *, __int64, int *))a2->lpVtbl->Read)(
                   a2,
                   (char *)a3 + 184,
                   v9,
                   &v12);
            if ( v8 < 0 )
              goto LABEL_40;
            *((_DWORD *)a3 + 1) |= 8u;
            break;
          case 0x73726576:
            v8 = ((__int64 (__fastcall *)(struct IStream *, char *, __int64, int *))a2->lpVtbl->Read)(
                   a2,
                   (char *)a3 + 48,
                   8,
                   &v12);
            if ( v8 < 0 )
              goto LABEL_40;
            *((_DWORD *)a3 + 1) |= 0x80u;
            break;
          default:
            goto LABEL_37;
        }
LABEL_38:
        v8 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v6 + 32LL))(v6, &v14, 0);
        if ( v8 >= 0 )
        {
          LODWORD(v14) = 0;
          v15 = 0;
          v8 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *, _QWORD))(*(_QWORD *)v6 + 24LL))(
                 v6,
                 &v14,
                 &v19,
                 0);
          if ( v8 >= 0 )
            continue;
        }
        goto LABEL_40;
      }
      if ( v15 == 1330007637 )
      {
        while ( !(*(unsigned int (__fastcall **)(__int64, __int128 *, __int64 *, _QWORD))(*(_QWORD *)v6 + 24LL))(
                   v6,
                   &v17,
                   &v14,
                   0) )
        {
          if ( (_DWORD)v17 == 1296125525 )
          {
            v10 = DWORD1(v17);
            if ( DWORD1(v17) > 0x80 )
              v10 = 128;
            v8 = ((__int64 (__fastcall *)(struct IStream *, char *, __int64, int *))a2->lpVtbl->Read)(
                   a2,
                   (char *)a3 + 56,
                   v10,
                   &v12);
            if ( v8 >= 0 )
              *((_DWORD *)a3 + 1) |= 4u;
          }
          (*(void (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)v6 + 32LL))(v6, &v17, 0);
        }
      }
LABEL_37:
      if ( v8 < 0 )
        goto LABEL_40;
      goto LABEL_38;
    }
LABEL_40:
    v11 = 0;
    if ( v8 != -2005396976 )
      v11 = v8;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    return v11;
  }
  return result;
}

```

## disassembly

```asm
0x18000eee0  mov     [rsp-8+arg_0], rbx
0x18000eee5  mov     [rsp-8+arg_18], rsi
0x18000eeea  push    rbp
0x18000eeeb  push    rdi
0x18000eeec  push    r12
0x18000eeee  push    r14
0x18000eef0  push    r15
0x18000eef2  lea     rbp, [rsp-37h]
0x18000eef7  sub     rsp, 90h
0x18000eefe  mov     rax, cs:__security_cookie
0x18000ef05  xor     rax, rsp
0x18000ef08  mov     [rbp+57h+var_28], rax
0x18000ef0c  xor     r15d, r15d
0x18000ef0f  mov     rbx, r8
0x18000ef12  mov     r14, rdx
0x18000ef15  test    rdx, rdx
0x18000ef18  jz      loc_18000F203
0x18000ef1e  mov     rax, [rdx]
0x18000ef21  test    rax, rax
0x18000ef24  jz      loc_18000F203
0x18000ef2a  cmp     [rax], r15
0x18000ef2d  jz      loc_18000F203
0x18000ef33  test    rbx, rbx
0x18000ef36  jz      loc_18000F1FC
0x18000ef3c  cmp     dword ptr [r8], 358h
0x18000ef43  jb      loc_18000F1FC
0x18000ef49  cmp     [rcx+360h], r15b
0x18000ef50  jz      short loc_18000EF5C
0x18000ef52  mov     eax, 8781216h
0x18000ef57  jmp     loc_18000F208
0x18000ef5c  lea     rdx, [rbp+57h+var_78]
0x18000ef60  mov     [rbp+57h+var_78], r15
0x18000ef64  mov     rcx, r14
0x18000ef67  call    AllocRIFFStream
0x18000ef6c  test    eax, eax
0x18000ef6e  js      loc_18000F208
0x18000ef74  mov     rdi, [rbp+57h+var_78]
0x18000ef78  lea     rdx, [rbp+57h+var_40]
0x18000ef7c  mov     [rbp+57h+var_40], r15
0x18000ef80  mov     r9d, 20h ; ' '
0x18000ef86  mov     [rbp+57h+var_34], r15
0x18000ef8a  xor     r8d, r8d
0x18000ef8d  mov     [rbp+57h+var_38], 4E434D44h
0x18000ef94  mov     rcx, rdi
0x18000ef97  mov     rax, [rdi]
0x18000ef9a  mov     rax, [rax+18h]
0x18000ef9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efa3  mov     esi, eax
0x18000efa5  mov     rcx, rdi
0x18000efa8  test    eax, eax
0x18000efaa  jns     short loc_18000EFBF
0x18000efac  mov     rdx, [rdi]
0x18000efaf  mov     rax, [rdx+10h]
0x18000efb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efb8  mov     eax, esi
0x18000efba  jmp     loc_18000F208
0x18000efbf  xor     eax, eax
0x18000efc1  mov     dword ptr [rbx+4], 2
0x18000efc8  movups  xmm0, xmmword ptr cs:CLSID_DirectMusicContainer.Data1
0x18000efcf  mov     [rbp+57h+var_48], eax
0x18000efd2  lea     r8, [rbp+57h+var_40]
0x18000efd6  mov     [rbp+57h+var_70], r15
0x18000efda  lea     rdx, [rbp+57h+var_70]
0x18000efde  movdqu  xmmword ptr [rbx+18h], xmm0
0x18000efe3  mov     [rbp+57h+var_64], r15
0x18000efe7  xor     r9d, r9d
0x18000efea  xorps   xmm0, xmm0
0x18000efed  mov     [rbp+57h+var_80], r15d
0x18000eff1  movups  [rbp+57h+var_58], xmm0
0x18000eff5  mov     [rbp+57h+var_68], r15d
0x18000eff9  mov     rax, [rdi]
0x18000effc  mov     rax, [rax+18h]
0x18000f000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f005  mov     esi, eax
0x18000f007  test    eax, eax
0x18000f009  js      loc_18000F1DD
0x18000f00f  mov     r12d, 80h
0x18000f015  mov     eax, dword ptr [rbp+57h+var_70]
0x18000f018  cmp     eax, 5453494Ch
0x18000f01d  jz      loc_18000F11D
0x18000f023  cmp     eax, 64697567h
0x18000f028  jz      loc_18000F0E0
0x18000f02e  cmp     eax, 65746164h
0x18000f033  jz      short loc_18000F0AF
0x18000f035  cmp     eax, 67746163h
0x18000f03a  jz      short loc_18000F077
0x18000f03c  cmp     eax, 73726576h
0x18000f041  jnz     loc_18000F191
0x18000f047  mov     rax, [r14]
0x18000f04a  lea     rdx, [rbx+30h]
0x18000f04e  lea     r9, [rbp+57h+var_80]
0x18000f052  mov     r8d, 8
0x18000f058  mov     rcx, r14
0x18000f05b  mov     rax, [rax+18h]
0x18000f05f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f064  mov     esi, eax
0x18000f066  test    eax, eax
0x18000f068  js      loc_18000F1DD
0x18000f06e  or      [rbx+4], r12d
0x18000f072  jmp     loc_18000F195
0x18000f077  mov     r8d, dword ptr [rbp+57h+var_70+4]
0x18000f07b  lea     rdx, [rbx+0B8h]
0x18000f082  mov     rax, [r14]
0x18000f085  lea     r9, [rbp+57h+var_80]
0x18000f089  cmp     r8d, r12d
0x18000f08c  mov     rcx, r14
0x18000f08f  cmova   r8d, r12d
0x18000f093  mov     rax, [rax+18h]
0x18000f097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f09c  mov     esi, eax
0x18000f09e  test    eax, eax
0x18000f0a0  js      loc_18000F1DD
0x18000f0a6  or      dword ptr [rbx+4], 8
0x18000f0aa  jmp     loc_18000F195
0x18000f0af  mov     rax, [r14]
0x18000f0b2  lea     rdx, [rbx+28h]
0x18000f0b6  lea     r9, [rbp+57h+var_80]
0x18000f0ba  mov     r8d, 8
0x18000f0c0  mov     rcx, r14
0x18000f0c3  mov     rax, [rax+18h]
0x18000f0c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0cc  mov     esi, eax
0x18000f0ce  test    eax, eax
0x18000f0d0  js      loc_18000F1DD
0x18000f0d6  bts     dword ptr [rbx+4], 8
0x18000f0db  jmp     loc_18000F195
0x18000f0e0  cmp     dword ptr [rbp+57h+var_70+4], 10h
0x18000f0e4  jnz     loc_18000F191
0x18000f0ea  mov     rax, [r14]
0x18000f0ed  lea     rdx, [rbx+8]
0x18000f0f1  lea     r9, [rbp+57h+var_80]
0x18000f0f5  mov     r8d, 10h
0x18000f0fb  mov     rcx, r14
0x18000f0fe  mov     rax, [rax+18h]
0x18000f102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f107  mov     esi, eax
0x18000f109  test    eax, eax
0x18000f10b  js      loc_18000F1DD
0x18000f111  cmp     [rbp+57h+var_80], 10h
0x18000f115  jnz     short loc_18000F195
0x18000f117  or      dword ptr [rbx+4], 1
0x18000f11b  jmp     short loc_18000F195
0x18000f11d  cmp     [rbp+57h+var_68], 4F464E55h
0x18000f124  jnz     short loc_18000F191
0x18000f126  mov     rax, [rdi]
0x18000f129  lea     r8, [rbp+57h+var_70]
0x18000f12d  xor     r9d, r9d
0x18000f130  lea     rdx, [rbp+57h+var_58]
0x18000f134  mov     rcx, rdi
0x18000f137  mov     rax, [rax+18h]
0x18000f13b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f140  test    eax, eax
0x18000f142  jnz     short loc_18000F191
0x18000f144  cmp     dword ptr [rbp+57h+var_58], 4D414E55h
0x18000f14b  jnz     short loc_18000F179
0x18000f14d  mov     r8d, dword ptr [rbp+57h+var_58+4]
0x18000f151  lea     rdx, [rbx+38h]
0x18000f155  mov     rax, [r14]
0x18000f158  lea     r9, [rbp+57h+var_80]
0x18000f15c  cmp     r8d, r12d
0x18000f15f  mov     rcx, r14
0x18000f162  cmova   r8d, r12d
0x18000f166  mov     rax, [rax+18h]
0x18000f16a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f16f  mov     esi, eax
0x18000f171  test    eax, eax
0x18000f173  js      short loc_18000F179
0x18000f175  or      dword ptr [rbx+4], 4
0x18000f179  mov     rax, [rdi]
0x18000f17c  lea     rdx, [rbp+57h+var_58]
0x18000f180  xor     r8d, r8d
0x18000f183  mov     rcx, rdi
0x18000f186  mov     rax, [rax+20h]
0x18000f18a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f18f  jmp     short loc_18000F126
0x18000f191  test    esi, esi
0x18000f193  js      short loc_18000F1DD
0x18000f195  mov     rax, [rdi]
0x18000f198  lea     rdx, [rbp+57h+var_70]
0x18000f19c  xor     r8d, r8d
0x18000f19f  mov     rcx, rdi
0x18000f1a2  mov     rax, [rax+20h]
0x18000f1a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1ab  mov     esi, eax
0x18000f1ad  test    eax, eax
0x18000f1af  js      short loc_18000F1DD
0x18000f1b1  mov     dword ptr [rbp+57h+var_70], r15d
0x18000f1b5  lea     r8, [rbp+57h+var_40]
0x18000f1b9  mov     [rbp+57h+var_68], r15d
0x18000f1bd  lea     rdx, [rbp+57h+var_70]
0x18000f1c1  mov     rax, [rdi]
0x18000f1c4  xor     r9d, r9d
0x18000f1c7  mov     rcx, rdi
0x18000f1ca  mov     rax, [rax+18h]
0x18000f1ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1d3  mov     esi, eax
0x18000f1d5  test    eax, eax
0x18000f1d7  jns     loc_18000F015
0x18000f1dd  mov     rcx, [rdi]
0x18000f1e0  cmp     esi, 88781210h
0x18000f1e6  mov     ebx, r15d
0x18000f1e9  cmovnz  ebx, esi
0x18000f1ec  mov     rax, [rcx+10h]
0x18000f1f0  mov     rcx, rdi
0x18000f1f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1f8  mov     eax, ebx
0x18000f1fa  jmp     short loc_18000F208
0x18000f1fc  mov     eax, 80070057h
0x18000f201  jmp     short loc_18000F208
0x18000f203  mov     eax, 80004003h
0x18000f208  mov     rcx, [rbp+57h+var_28]
0x18000f20c  xor     rcx, rsp; StackCookie
0x18000f20f  call    __security_check_cookie
0x18000f214  lea     r11, [rsp+0B0h+var_20]
0x18000f21c  mov     rbx, [r11+30h]
0x18000f220  mov     rsi, [r11+48h]
0x18000f224  mov     rsp, r11
0x18000f227  pop     r15
0x18000f229  pop     r14
0x18000f22b  pop     r12
0x18000f22d  pop     rdi
0x18000f22e  pop     rbp
0x18000f22f  retn
```
