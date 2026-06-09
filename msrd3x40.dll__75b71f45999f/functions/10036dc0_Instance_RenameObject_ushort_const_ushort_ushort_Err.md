# Instance::RenameObject(ushort const *,ushort *,ushort *,Err &)

- ea: `0x10036dc0`
- end: `0x10037181`
- name: `?RenameObject@Instance@@QAEXPBGPAG1AAVErr@@@Z`
- size: `961`
- prototype: `void __thiscall(Instance *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, struct Err *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x100291a0`
- `0x10036160`

## callees

- `0x1000eb60`
- `0x1000f750`
- `0x10025db0`
- `0x10025f50`
- `0x100260d0`
- `0x100270d0`
- `0x10036dc0`
- `0x10037710`
- `0x10037b10`
- `0x1004dbb0`
- `0x1005e3b0`
- `0x1005e7dc`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
void __thiscall Instance::RenameObject(
        Instance *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        void **a5)
{
  Instance *v5; // edi
  Err *v6; // ecx
  unsigned __int16 *v7; // esi
  Err *v8; // ecx
  void *v9; // eax
  unsigned int v10; // esi
  int v11; // ecx
  int v12; // esi
  unsigned int v13; // ecx
  int v14; // eax
  int v15; // edx
  __int16 v16; // cx
  int v17; // eax
  const unsigned __int16 *v18; // esi
  Instance *v19; // edi
  int v20; // ecx
  int v21; // esi
  unsigned __int16 *v22; // ecx
  const unsigned __int16 *v24; // [esp+0h] [ebp-110h]
  struct Err *v25; // [esp+4h] [ebp-10Ch]
  unsigned int v26[3]; // [esp+3Ch] [ebp-D4h] BYREF
  void *Block; // [esp+48h] [ebp-C8h]
  void *v28; // [esp+4Ch] [ebp-C4h]
  _DWORD v29[3]; // [esp+50h] [ebp-C0h] BYREF
  __int16 v30; // [esp+5Ch] [ebp-B4h]
  int v31; // [esp+60h] [ebp-B0h]
  int v32; // [esp+64h] [ebp-ACh]
  unsigned __int16 *v33; // [esp+68h] [ebp-A8h]
  const unsigned __int16 *v34; // [esp+6Ch] [ebp-A4h]
  unsigned __int16 *v35; // [esp+70h] [ebp-A0h]
  Instance *v36; // [esp+74h] [ebp-9Ch]
  unsigned int v37[34]; // [esp+78h] [ebp-98h] BYREF
  int v38; // [esp+10Ch] [ebp-4h]

  v5 = this;
  v36 = this;
  v35 = a2;
  v34 = a3;
  v33 = a4;
  ValidateName(v24, v25);
  if ( (*(_BYTE *)a5 & 8) == 0 )
  {
    if ( v35 && *v35 )
      Instance::ReadObjectRecord(v5, v35, a3, a5);
    else
      Instance::ReadSysObjRecord(v5, 0xF000000u, a3, a5);
    if ( (*(_BYTE *)a5 & 8) == 0 )
    {
      if ( !WCSICMP(a3, wszMSysAccounts) || !WCSICMP(a3, wszMSysGroups) )
      {
        if ( ((unsigned int)*a5 & 0xFFFFFFFE) != 0 )
        {
          if ( a5[3] )
            operator delete[](a5[3]);
          if ( a5[4] )
            operator delete[](a5[4]);
        }
        *a5 = (void *)8;
        a5[1] = (void *)-1304;
        a5[2] = (void *)-8150;
        Err::CopyString(v6, (wchar_t *)a5 + 6, a3);
        a5[4] = 0;
        v38 = -1;
      }
      if ( (*(_BYTE *)a5 & 8) == 0 )
      {
        v7 = v33;
        if ( !WCSICMP(v33, wszMSysAccounts) || !WCSICMP(v33, wszMSysGroups) )
        {
          if ( ((unsigned int)*a5 & 0xFFFFFFFE) != 0 )
          {
            if ( a5[3] )
              operator delete[](a5[3]);
            if ( a5[4] )
              operator delete[](a5[4]);
          }
          *a5 = (void *)8;
          a5[1] = (void *)-1002;
          a5[2] = (void *)-8198;
          Err::CopyString(v8, (wchar_t *)a5 + 6, v7);
          a5[4] = 0;
          v38 = -1;
        }
        if ( (*(_BYTE *)a5 & 8) == 0 )
        {
          (*(void (__thiscall **)(_DWORD, int, void **))(**((_DWORD **)v5 + 5) + 20))(*((_DWORD *)v5 + 5), 2, a5);
          v5 = v36;
        }
      }
    }
  }
  v9 = *a5;
  if ( ((unsigned __int8)*a5 & 8) != 0 )
  {
    v12 = 0;
  }
  else
  {
    v10 = (*(int (__thiscall **)(_DWORD, _DWORD, unsigned int *, int, _DWORD, void **))(**((_DWORD **)v5 + 5) + 108))(
            *((_DWORD *)v5 + 5),
            *((_DWORD *)v36 + 9),
            v37,
            128,
            0,
            a5);
    v9 = *a5;
    if ( ((unsigned __int8)*a5 & 8) != 0 )
    {
LABEL_38:
      v19 = v36;
      goto LABEL_39;
    }
    v11 = 128;
    if ( v10 < 0x80 )
      v11 = v10;
    v12 = v11;
    v13 = v11 & 0xFFFFFFFE;
    if ( v13 >= 0x82 )
      __report_rangecheckfailure();
    *(_WORD *)((char *)v37 + v13) = 0;
  }
  if ( ((unsigned __int8)v9 & 8) != 0 )
    goto LABEL_38;
  v14 = *((_DWORD *)v36 + 4);
  v15 = *(_DWORD *)(v14 + 224);
  if ( !v15 )
    v15 = *(unsigned __int16 *)(v14 + 86);
  v16 = *(_WORD *)(v14 + 88);
  v17 = *(_DWORD *)(v14 + 92);
  v29[1] = v12;
  v18 = v34;
  v30 = v16;
  v29[0] = v37;
  v19 = v36;
  v31 = v15;
  v29[2] = v17;
  v32 = 0;
  if ( LString::Compare(v29, v34, 2 * wcslen(v34), 0) )
    Err::SetError(a5, -1305, -8300, v18, 0, v20);
LABEL_39:
  if ( (*(_BYTE *)a5 & 8) != 0 )
    goto LABEL_53;
  v21 = *((_DWORD *)v19 + 5);
  v22 = v33;
  v35 = *(unsigned __int16 **)(*(_DWORD *)v21 + 100);
  v34 = v33 + 1;
  while ( *v22++ )
    ;
  ((void (__thiscall *)(int, _DWORD, unsigned __int16 *, int, _DWORD, void **))v35)(
    v21,
    *((_DWORD *)v19 + 9),
    v33,
    2 * (v22 - v34),
    0,
    a5);
  if ( (*(_BYTE *)a5 & 8) != 0
    || ((*(void (__thiscall **)(_DWORD, void **))(**((_DWORD **)v19 + 5) + 28))(*((_DWORD *)v19 + 5), a5),
        (*(_BYTE *)a5 & 8) != 0) )
  {
LABEL_53:
    v26[0] = 1;
    v38 = 2;
    (*(void (__thiscall **)(_DWORD, int, unsigned int *))(**((_DWORD **)v36 + 5) + 20))(*((_DWORD *)v36 + 5), 3, v26);
    if ( (v26[0] & 0xFFFFFFFE) != 0 )
    {
      if ( Block )
        operator delete[](Block);
      if ( v28 )
        operator delete[](v28);
    }
  }
}

```

## disassembly

```asm
0x10036dc0  mov     edi, edi
0x10036dc2  push    ebp
0x10036dc3  mov     ebp, esp
0x10036dc5  push    0FFFFFFFFh
0x10036dc7  push    offset ?RenameObject@Instance@@QAEXPBGPAG1AAVErr@@@Z_SEH
0x10036dcc  mov     eax, large fs:0
0x10036dd2  push    eax
0x10036dd3  sub     esp, 0F4h
0x10036dd9  mov     eax, ___security_cookie
0x10036dde  xor     eax, ebp
0x10036de0  mov     [ebp+var_10], eax
0x10036de3  push    ebx
0x10036de4  push    esi
0x10036de5  push    edi; struct Err *
0x10036de6  push    eax; unsigned int
0x10036de7  lea     eax, [ebp+var_C]
0x10036dea  mov     large fs:0, eax
0x10036df0  mov     edi, ecx
0x10036df2  mov     [ebp+var_9C], edi
0x10036df8  mov     eax, [ebp+arg_0]
0x10036dfb  mov     ebx, [ebp+arg_C]
0x10036dfe  mov     edx, ebx
0x10036e00  mov     esi, [ebp+arg_4]
0x10036e03  mov     [ebp+var_A0], eax
0x10036e09  mov     eax, [ebp+arg_8]
0x10036e0c  mov     ecx, eax
0x10036e0e  mov     [ebp+var_A4], esi
0x10036e14  mov     [ebp+var_A8], eax
0x10036e1a  call    ?ValidateName@@YGXPBGAAVErr@@@Z; ValidateName(ushort const *,Err &)
0x10036e1f  test    byte ptr [ebx], 8
0x10036e22  jnz     loc_10036F74
0x10036e28  mov     eax, [ebp+var_A0]
0x10036e2e  test    eax, eax
0x10036e30  jz      short loc_10036E44
0x10036e32  cmp     word ptr [eax], 0
0x10036e36  jz      short loc_10036E44
0x10036e38  push    ebx; struct Err *
0x10036e39  push    esi; unsigned __int16 *
0x10036e3a  push    eax; unsigned __int16 *
0x10036e3b  mov     ecx, edi; this
0x10036e3d  call    ?ReadObjectRecord@Instance@@QAEXPBG0AAVErr@@@Z; Instance::ReadObjectRecord(ushort const *,ushort const *,Err &)
0x10036e42  jmp     short loc_10036E52
0x10036e44  push    ebx; struct Err *
0x10036e45  push    esi; unsigned __int16 *
0x10036e46  push    0F000000h; unsigned int
0x10036e4b  mov     ecx, edi; this
0x10036e4d  call    ?ReadSysObjRecord@Instance@@QAEXKPBGAAVErr@@@Z; Instance::ReadSysObjRecord(ulong,ushort const *,Err &)
0x10036e52  test    byte ptr [ebx], 8
0x10036e55  jnz     loc_10036F74
0x10036e5b  mov     edx, offset _wszMSysAccounts; "MSysAccounts"
0x10036e60  mov     ecx, esi
0x10036e62  call    _WCSICMP@8; WCSICMP(x,x)
0x10036e67  test    eax, eax
0x10036e69  jz      short loc_10036E7B
0x10036e6b  mov     edx, offset _wszMSysGroups; "MSysGroups"
0x10036e70  mov     ecx, esi
0x10036e72  call    _WCSICMP@8; WCSICMP(x,x)
0x10036e77  test    eax, eax
0x10036e79  jnz     short loc_10036ECF
0x10036e7b  test    dword ptr [ebx], 0FFFFFFFEh
0x10036e81  jz      short loc_10036EA3
0x10036e83  mov     eax, [ebx+0Ch]
0x10036e86  test    eax, eax
0x10036e88  jz      short loc_10036E93
0x10036e8a  push    eax; Block
0x10036e8b  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10036e90  add     esp, 4
0x10036e93  mov     eax, [ebx+10h]
0x10036e96  test    eax, eax
0x10036e98  jz      short loc_10036EA3
0x10036e9a  push    eax; Block
0x10036e9b  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10036ea0  add     esp, 4
0x10036ea3  push    esi; unsigned __int16 *
0x10036ea4  lea     eax, [ebx+0Ch]
0x10036ea7  mov     dword ptr [ebx], 8
0x10036ead  push    eax; unsigned __int16 **
0x10036eae  mov     dword ptr [ebx+4], 0FFFFFAE8h
0x10036eb5  mov     dword ptr [ebx+8], 0FFFFE02Ah
0x10036ebc  call    ?CopyString@Err@@AAEXAAPAGPBG@Z; Err::CopyString(ushort * &,ushort const *)
0x10036ec1  mov     dword ptr [ebx+10h], 0
0x10036ec8  mov     [ebp+var_4], 0FFFFFFFFh
0x10036ecf  test    byte ptr [ebx], 8
0x10036ed2  jnz     loc_10036F74
0x10036ed8  mov     esi, [ebp+var_A8]
0x10036ede  mov     edx, offset _wszMSysAccounts; "MSysAccounts"
0x10036ee3  mov     ecx, esi
0x10036ee5  call    _WCSICMP@8; WCSICMP(x,x)
0x10036eea  test    eax, eax
0x10036eec  jz      short loc_10036EFE
0x10036eee  mov     edx, offset _wszMSysGroups; "MSysGroups"
0x10036ef3  mov     ecx, esi
0x10036ef5  call    _WCSICMP@8; WCSICMP(x,x)
0x10036efa  test    eax, eax
0x10036efc  jnz     short loc_10036F52
0x10036efe  test    dword ptr [ebx], 0FFFFFFFEh
0x10036f04  jz      short loc_10036F26
0x10036f06  mov     eax, [ebx+0Ch]
0x10036f09  test    eax, eax
0x10036f0b  jz      short loc_10036F16
0x10036f0d  push    eax; Block
0x10036f0e  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10036f13  add     esp, 4
0x10036f16  mov     eax, [ebx+10h]
0x10036f19  test    eax, eax
0x10036f1b  jz      short loc_10036F26
0x10036f1d  push    eax; Block
0x10036f1e  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10036f23  add     esp, 4
0x10036f26  push    esi; unsigned __int16 *
0x10036f27  lea     eax, [ebx+0Ch]
0x10036f2a  mov     dword ptr [ebx], 8
0x10036f30  push    eax; unsigned __int16 **
0x10036f31  mov     dword ptr [ebx+4], 0FFFFFC16h
0x10036f38  mov     dword ptr [ebx+8], 0FFFFDFFAh
0x10036f3f  call    ?CopyString@Err@@AAEXAAPAGPBG@Z; Err::CopyString(ushort * &,ushort const *)
0x10036f44  mov     dword ptr [ebx+10h], 0
0x10036f4b  mov     [ebp+var_4], 0FFFFFFFFh
0x10036f52  test    byte ptr [ebx], 8
0x10036f55  jnz     short loc_10036F74
0x10036f57  mov     edi, [edi+14h]
0x10036f5a  push    ebx; unsigned int
0x10036f5b  push    2; void *
0x10036f5d  mov     eax, [edi]
0x10036f5f  mov     esi, [eax+14h]
0x10036f62  mov     ecx, esi
0x10036f64  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10036f6a  mov     ecx, edi
0x10036f6c  call    esi
0x10036f6e  mov     edi, [ebp+var_9C]
0x10036f74  mov     eax, [ebx]
0x10036f76  test    al, 8
0x10036f78  jnz     short loc_10036FD9
0x10036f7a  mov     edi, [edi+14h]
0x10036f7d  push    ebx
0x10036f7e  push    0
0x10036f80  push    80h
0x10036f85  mov     eax, [edi]
0x10036f87  mov     esi, [eax+6Ch]
0x10036f8a  lea     eax, [ebp+var_98]
0x10036f90  push    eax; unsigned int
0x10036f91  mov     eax, [ebp+var_9C]
0x10036f97  mov     ecx, esi
0x10036f99  push    dword ptr [eax+24h]; void *
0x10036f9c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10036fa2  mov     ecx, edi
0x10036fa4  call    esi
0x10036fa6  mov     esi, eax
0x10036fa8  mov     eax, [ebx]
0x10036faa  test    al, 8
0x10036fac  jnz     loc_1003707D
0x10036fb2  mov     ecx, 80h
0x10036fb7  cmp     esi, ecx
0x10036fb9  cmovb   ecx, esi
0x10036fbc  mov     esi, ecx
0x10036fbe  and     ecx, 0FFFFFFFEh
0x10036fc1  cmp     ecx, 82h
0x10036fc7  jnb     loc_1003717C
0x10036fcd  xor     edx, edx
0x10036fcf  mov     word ptr [ebp+ecx+var_98], dx
0x10036fd7  jmp     short loc_10036FDB
0x10036fd9  xor     esi, esi
0x10036fdb  test    al, 8
0x10036fdd  jnz     loc_1003707D
0x10036fe3  mov     edi, [ebp+var_9C]
0x10036fe9  mov     eax, [edi+10h]
0x10036fec  mov     edx, [eax+0E0h]
0x10036ff2  test    edx, edx
0x10036ff4  jnz     short loc_10036FFA
0x10036ff6  movzx   edx, word ptr [eax+56h]
0x10036ffa  movzx   ecx, word ptr [eax+58h]
0x10036ffe  lea     edi, [ebp+var_98]
0x10037004  mov     eax, [eax+5Ch]
0x10037007  mov     [ebp+var_BC], esi
0x1003700d  mov     esi, [ebp+var_A4]
0x10037013  mov     [ebp+var_B4], cx
0x1003701a  mov     ecx, esi
0x1003701c  mov     [ebp+var_C0], edi
0x10037022  mov     edi, [ebp+var_9C]
0x10037028  mov     [ebp+var_B0], edx
0x1003702e  mov     [ebp+var_B8], eax
0x10037034  lea     edx, [ecx+2]
0x10037037  mov     [ebp+var_AC], 0
0x10037041  mov     ax, [ecx]
0x10037044  add     ecx, 2
0x10037047  test    ax, ax
0x1003704a  jnz     short loc_10037041
0x1003704c  sub     ecx, edx
0x1003704e  sar     ecx, 1
0x10037050  push    0
0x10037052  lea     eax, [ecx+ecx]
0x10037055  push    eax
0x10037056  push    esi
0x10037057  lea     ecx, [ebp+var_C0]
0x1003705d  call    ?Compare@LString@@QAE?AW4LCmp@@PAEIW4LSpec@@@Z; LString::Compare(uchar *,uint,LSpec)
0x10037062  test    eax, eax
0x10037064  jz      short loc_10037083
0x10037066  push    ecx
0x10037067  push    0
0x10037069  push    esi
0x1003706a  push    0FFFFDF94h
0x1003706f  push    0FFFFFAE7h
0x10037074  mov     ecx, ebx
0x10037076  call    ?SetError@Err@@QAEXJJPBG0W4ErrAssert@@@Z; Err::SetError(long,long,ushort const *,ushort const *,ErrAssert)
0x1003707b  jmp     short loc_10037083
0x1003707d  mov     edi, [ebp+var_9C]
0x10037083  test    byte ptr [ebx], 8
0x10037086  jnz     short loc_100370F8
0x10037088  mov     esi, [edi+14h]
0x1003708b  mov     edx, [ebp+var_A8]
0x10037091  mov     ecx, edx
0x10037093  mov     eax, [esi]
0x10037095  mov     eax, [eax+64h]
0x10037098  mov     [ebp+var_A0], eax
0x1003709e  lea     eax, [ecx+2]
0x100370a1  mov     [ebp+var_A4], eax
0x100370a7  mov     ax, [ecx]
0x100370aa  add     ecx, 2
0x100370ad  test    ax, ax
0x100370b0  jnz     short loc_100370A7
0x100370b2  sub     ecx, [ebp+var_A4]
0x100370b8  sar     ecx, 1
0x100370ba  push    ebx
0x100370bb  push    0
0x100370bd  lea     eax, [ecx+ecx]
0x100370c0  mov     ecx, [ebp+var_A0]
0x100370c6  push    eax
0x100370c7  push    edx; unsigned int
0x100370c8  push    dword ptr [edi+24h]; void *
0x100370cb  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100370d1  mov     ecx, esi
0x100370d3  call    [ebp+var_A0]
0x100370d9  test    byte ptr [ebx], 8
0x100370dc  jnz     short loc_100370F8
0x100370de  mov     edi, [edi+14h]
0x100370e1  push    ebx; void *
0x100370e2  mov     eax, [edi]
0x100370e4  mov     esi, [eax+1Ch]
0x100370e7  mov     ecx, esi
0x100370e9  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100370ef  mov     ecx, edi
0x100370f1  call    esi
0x100370f3  test    byte ptr [ebx], 8
0x100370f6  jz      short loc_1003715E
0x100370f8  mov     [ebp+var_D4], 1
0x10037102  mov     eax, [ebp+var_9C]
0x10037108  lea     ecx, [ebp+var_D4]
0x1003710e  mov     [ebp+var_4], 2
0x10037115  push    ecx; unsigned int
0x10037116  push    3; void *
0x10037118  mov     edi, [eax+14h]
0x1003711b  mov     eax, [edi]
0x1003711d  mov     esi, [eax+14h]
0x10037120  mov     ecx, esi
0x10037122  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10037128  mov     ecx, edi
0x1003712a  call    esi
0x1003712c  test    [ebp+var_D4], 0FFFFFFFEh
0x10037136  jz      short loc_1003715E
0x10037138  mov     eax, [ebp+Block]
0x1003713e  test    eax, eax
0x10037140  jz      short loc_1003714B
0x10037142  push    eax; Block
0x10037143  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10037148  add     esp, 4
0x1003714b  mov     eax, [ebp+var_C4]
0x10037151  test    eax, eax
0x10037153  jz      short loc_1003715E
0x10037155  push    eax; Block
0x10037156  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1003715b  add     esp, 4
0x1003715e  mov     ecx, [ebp+var_C]
0x10037161  mov     large fs:0, ecx
0x10037168  pop     ecx
0x10037169  pop     edi
0x1003716a  pop     esi
0x1003716b  pop     ebx
0x1003716c  mov     ecx, [ebp+var_10]
0x1003716f  xor     ecx, ebp; StackCookie
0x10037171  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10037176  mov     esp, ebp
0x10037178  pop     ebp
0x10037179  retn    10h
0x1003717c  call    ___report_rangecheckfailure
0x10060ca0  lea     ecx, [ebp+var_E8]; this
0x10060ca6  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x10060cab  lea     ecx, [ebp+var_FC]; this
0x10060cb1  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x10060cb6  lea     ecx, [ebp+var_D4]; this
0x10060cbc  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x10060cc6  nop
0x10060cc7  nop
0x10060cc8  mov     edx, [esp-4+arg_4]
0x10060ccc  lea     eax, [edx+0Ch]
0x10060ccf  mov     ecx, [edx-104h]
0x10060cd5  xor     ecx, eax; StackCookie
0x10060cd7  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10060cdc  mov     ecx, [edx-4]
0x10060cdf  xor     ecx, eax; StackCookie
0x10060ce1  call    @__security_check_cookie@4; __security_check_cookie(x)
  ... truncated ...
```
