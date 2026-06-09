# MidlCopyDasDeviceCreationInfo(_DAS_SW_DEVICE_CREATE_INFO * const,_DAS_SW_DEVICE_CREATE_INFO * *)

- ea: `0x140019b20`
- end: `0x140019c56`
- name: `?MidlCopyDasDeviceCreationInfo@@YAJQEAU_DAS_SW_DEVICE_CREATE_INFO@@PEAPEAU1@@Z`
- size: `310`
- prototype: `__int64 __fastcall(struct _DAS_SW_DEVICE_CREATE_INFO *const, struct _DAS_SW_DEVICE_CREATE_INFO **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000deb0`

## callees

- `0x1400020d0`
- `0x140009060`
- `0x140019b20`
- `0x140019db0`
- `0x140019e10`
- `0x140019f38`

## pseudocode

```c
__int64 __fastcall MidlCopyDasDeviceCreationInfo(
        struct _DAS_SW_DEVICE_CREATE_INFO *const a1,
        struct _DAS_SW_DEVICE_CREATE_INFO **a2)
{
  void *v4; // rax
  void *v5; // rdi
  int v6; // ebx
  _OWORD *v7; // rax
  const unsigned __int16 *v8; // rcx
  const unsigned __int16 *v9; // rcx
  const unsigned __int16 *v10; // rcx
  unsigned __int16 *const *v11; // rcx
  unsigned __int16 *const *v12; // rcx
  const unsigned __int16 *v13; // rcx

  v4 = (void *)DAF_user_alloc(88);
  v5 = v4;
  if ( v4 )
  {
    memset_0(v4, 0, 0x58u);
    *((_DWORD *)v5 + 14) = *((_DWORD *)a1 + 14);
    *(_DWORD *)v5 = 88;
    if ( *((_QWORD *)a1 + 6) )
    {
      v7 = (_OWORD *)DAF_user_alloc(16);
      *((_QWORD *)v5 + 6) = v7;
      if ( !v7 )
      {
        v6 = -2147024882;
LABEL_21:
        MidlFreeDasDeviceCreationInfo((struct _DAS_SW_DEVICE_CREATE_INFO *)v5);
        return (unsigned int)v6;
      }
      *v7 = *(_OWORD *)*((_QWORD *)a1 + 6);
    }
    v8 = (const unsigned __int16 *)*((_QWORD *)a1 + 8);
    v6 = 0;
    if ( v8 )
    {
      v6 = MidlCopyString(v8, (unsigned __int16 **)v5 + 8);
      if ( v6 < 0 )
        goto LABEL_21;
    }
    v9 = (const unsigned __int16 *)*((_QWORD *)a1 + 9);
    if ( v9 )
    {
      v6 = MidlCopyString(v9, (unsigned __int16 **)v5 + 9);
      if ( v6 < 0 )
        goto LABEL_21;
    }
    v10 = (const unsigned __int16 *)*((_QWORD *)a1 + 1);
    if ( v10 )
    {
      v6 = MidlCopyString(v10, (unsigned __int16 **)v5 + 1);
      if ( v6 < 0 )
        goto LABEL_21;
    }
    v11 = (unsigned __int16 *const *)*((_QWORD *)a1 + 5);
    if ( v11 )
    {
      v6 = MidlCopyStringArray(v11, *((_DWORD *)a1 + 8), (unsigned __int16 ***)v5 + 5);
      if ( v6 < 0 )
        goto LABEL_21;
      *((_DWORD *)v5 + 8) = *((_DWORD *)a1 + 8);
    }
    v12 = (unsigned __int16 *const *)*((_QWORD *)a1 + 3);
    if ( v12 )
    {
      v6 = MidlCopyStringArray(v12, *((_DWORD *)a1 + 4), (unsigned __int16 ***)v5 + 3);
      if ( v6 < 0 )
        goto LABEL_21;
      *((_DWORD *)v5 + 4) = *((_DWORD *)a1 + 4);
    }
    v13 = (const unsigned __int16 *)*((_QWORD *)a1 + 10);
    if ( !v13 || (v6 = MidlCopyString(v13, (unsigned __int16 **)v5 + 10), v6 >= 0) )
    {
      *a2 = (struct _DAS_SW_DEVICE_CREATE_INFO *)v5;
      return (unsigned int)v6;
    }
    goto LABEL_21;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x140019b20  push    rbx
0x140019b22  push    rsi
0x140019b23  push    rdi
0x140019b24  push    r14
0x140019b26  sub     rsp, 28h
0x140019b2a  mov     rsi, rcx
0x140019b2d  mov     ebx, 58h ; 'X'
0x140019b32  mov     ecx, ebx
0x140019b34  mov     r14, rdx
0x140019b37  call    DAF_user_alloc
0x140019b3c  mov     rdi, rax
0x140019b3f  test    rax, rax
0x140019b42  jnz     short loc_140019B4E
0x140019b44  mov     ebx, 8007000Eh
0x140019b49  jmp     loc_140019C4A
0x140019b4e  mov     r8, rbx; Size
0x140019b51  xor     edx, edx; Val
0x140019b53  mov     rcx, rdi; void *
0x140019b56  call    memset_0
0x140019b5b  mov     eax, [rsi+38h]
0x140019b5e  mov     [rdi+38h], eax
0x140019b61  mov     [rdi], ebx
0x140019b63  cmp     qword ptr [rsi+30h], 0
0x140019b68  jz      short loc_140019B95
0x140019b6a  mov     ecx, 10h
0x140019b6f  call    DAF_user_alloc
0x140019b74  mov     [rdi+30h], rax
0x140019b78  mov     rcx, rax
0x140019b7b  test    rax, rax
0x140019b7e  jnz     short loc_140019B8A
0x140019b80  mov     ebx, 8007000Eh
0x140019b85  jmp     loc_140019C3D
0x140019b8a  mov     rax, [rsi+30h]
0x140019b8e  movups  xmm0, xmmword ptr [rax]
0x140019b91  movdqu  xmmword ptr [rcx], xmm0
0x140019b95  mov     rcx, [rsi+40h]; unsigned __int16 *
0x140019b99  xor     ebx, ebx
0x140019b9b  test    rcx, rcx
0x140019b9e  jz      short loc_140019BB3
0x140019ba0  lea     rdx, [rdi+40h]; unsigned __int16 **
0x140019ba4  call    ?MidlCopyString@@YAJPEBGPEAPEAG@Z; MidlCopyString(ushort const *,ushort * *)
0x140019ba9  mov     ebx, eax
0x140019bab  test    eax, eax
0x140019bad  js      loc_140019C3D
0x140019bb3  mov     rcx, [rsi+48h]; unsigned __int16 *
0x140019bb7  test    rcx, rcx
0x140019bba  jz      short loc_140019BCB
0x140019bbc  lea     rdx, [rdi+48h]; unsigned __int16 **
0x140019bc0  call    ?MidlCopyString@@YAJPEBGPEAPEAG@Z; MidlCopyString(ushort const *,ushort * *)
0x140019bc5  mov     ebx, eax
0x140019bc7  test    eax, eax
0x140019bc9  js      short loc_140019C3D
0x140019bcb  mov     rcx, [rsi+8]; unsigned __int16 *
0x140019bcf  test    rcx, rcx
0x140019bd2  jz      short loc_140019BE3
0x140019bd4  lea     rdx, [rdi+8]; unsigned __int16 **
0x140019bd8  call    ?MidlCopyString@@YAJPEBGPEAPEAG@Z; MidlCopyString(ushort const *,ushort * *)
0x140019bdd  mov     ebx, eax
0x140019bdf  test    eax, eax
0x140019be1  js      short loc_140019C3D
0x140019be3  mov     rcx, [rsi+28h]; unsigned __int16 **
0x140019be7  test    rcx, rcx
0x140019bea  jz      short loc_140019C04
0x140019bec  mov     edx, [rsi+20h]; unsigned int
0x140019bef  lea     r8, [rdi+28h]; unsigned __int16 ***
0x140019bf3  call    ?MidlCopyStringArray@@YAJPEBQEAGKPEAPEAPEAG@Z; MidlCopyStringArray(ushort * const *,ulong,ushort * * *)
0x140019bf8  mov     ebx, eax
0x140019bfa  test    eax, eax
0x140019bfc  js      short loc_140019C3D
0x140019bfe  mov     eax, [rsi+20h]
0x140019c01  mov     [rdi+20h], eax
0x140019c04  mov     rcx, [rsi+18h]; unsigned __int16 **
0x140019c08  test    rcx, rcx
0x140019c0b  jz      short loc_140019C25
0x140019c0d  mov     edx, [rsi+10h]; unsigned int
0x140019c10  lea     r8, [rdi+18h]; unsigned __int16 ***
0x140019c14  call    ?MidlCopyStringArray@@YAJPEBQEAGKPEAPEAPEAG@Z; MidlCopyStringArray(ushort * const *,ulong,ushort * * *)
0x140019c19  mov     ebx, eax
0x140019c1b  test    eax, eax
0x140019c1d  js      short loc_140019C3D
0x140019c1f  mov     eax, [rsi+10h]
0x140019c22  mov     [rdi+10h], eax
0x140019c25  mov     rcx, [rsi+50h]; unsigned __int16 *
0x140019c29  test    rcx, rcx
0x140019c2c  jz      short loc_140019C47
0x140019c2e  lea     rdx, [rdi+50h]; unsigned __int16 **
0x140019c32  call    ?MidlCopyString@@YAJPEBGPEAPEAG@Z; MidlCopyString(ushort const *,ushort * *)
0x140019c37  mov     ebx, eax
0x140019c39  test    eax, eax
0x140019c3b  jns     short loc_140019C47
0x140019c3d  mov     rcx, rdi; struct _DAS_SW_DEVICE_CREATE_INFO *
0x140019c40  call    ?MidlFreeDasDeviceCreationInfo@@YAXPEAU_DAS_SW_DEVICE_CREATE_INFO@@@Z; MidlFreeDasDeviceCreationInfo(_DAS_SW_DEVICE_CREATE_INFO *)
0x140019c45  jmp     short loc_140019C4A
0x140019c47  mov     [r14], rdi
0x140019c4a  mov     eax, ebx
0x140019c4c  add     rsp, 28h
0x140019c50  pop     r14
0x140019c52  pop     rdi
0x140019c53  pop     rsi
0x140019c54  pop     rbx
0x140019c55  retn
```
