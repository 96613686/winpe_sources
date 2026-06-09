# Instance::CreateObject(ulong,ushort *,ushort,Err &)

- ea: `0x10036a70`
- end: `0x10036dac`
- name: `?CreateObject@Instance@@QAEXKPAGGAAVErr@@@Z`
- size: `828`
- prototype: `void __thiscall(Instance *__hidden this, unsigned int, unsigned __int16 *, unsigned __int16, struct Err *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x100290e0`

## callees

- `0x1000eb60`
- `0x10025ee0`
- `0x10025f50`
- `0x10026020`
- `0x100270d0`
- `0x100272b0`
- `0x10036a70`
- `0x10037710`
- `0x1005e7e8`

## pseudocode

```c
void __thiscall Instance::CreateObject(
        Instance *this,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned __int16 a4,
        struct Err *a5)
{
  struct Err *v5; // esi
  int v7; // ecx
  unsigned int v8; // eax
  int v9; // eax
  unsigned __int16 *v10; // ebx
  int v11; // ecx
  unsigned int v12; // [esp+BCh] [ebp-2Ch]
  unsigned __int16 *v13; // [esp+C0h] [ebp-28h]
  const unsigned __int16 *v14; // [esp+C8h] [ebp-20h]
  double *v15; // [esp+C8h] [ebp-20h]
  struct Err *v16; // [esp+CCh] [ebp-1Ch]
  unsigned int v18; // [esp+D8h] [ebp-10h] BYREF
  unsigned int v19; // [esp+DCh] [ebp-Ch] BYREF
  unsigned int v20[2]; // [esp+E0h] [ebp-8h] BYREF

  v5 = a5;
  v18 = -1;
  v19 = 0;
  ValidateName(v14, v16);
  if ( a4 == 3 && a2 != 251658240 )
    Err::SetError(v5, -1003, v7);
  (*(void (__thiscall **)(_DWORD, const unsigned __int16 *, struct Err *))(**((_DWORD **)this + 5) + 8))(
    *((_DWORD *)this + 5),
    L"Id",
    v5);
  if ( (*(_BYTE *)v5 & 8) == 0 )
  {
    (*(void (__thiscall **)(_DWORD, unsigned int *, int, _DWORD, struct Err *))(**(_DWORD **)(*((_DWORD *)this + 5) + 36)
                                                                              + 24))(
      *(_DWORD *)(*((_DWORD *)this + 5) + 36),
      &v18,
      4,
      0,
      v5);
    (*(void (__thiscall **)(_DWORD, int, struct Err *))(**(_DWORD **)(*((_DWORD *)this + 5) + 36) + 28))(
      *(_DWORD *)(*((_DWORD *)this + 5) + 36),
      2,
      v5);
    if ( (*(_DWORD *)v5 & 8) != 0 && (*(_DWORD *)v5 & 1) == 0 && *((_DWORD *)v5 + 1) == -1601 )
    {
      Err::Reset(v5);
      v8 = 0x80000000;
    }
    else
    {
      (*(void (__thiscall **)(_DWORD, _DWORD, unsigned int *, int, _DWORD, struct Err *))(**((_DWORD **)this + 5) + 108))(
        *((_DWORD *)this + 5),
        *((_DWORD *)this + 8),
        &v18,
        4,
        0,
        v5);
      v8 = v18 + 1;
    }
    v18 = v8;
    GetDateTime(v15);
    while ( 1 )
    {
      if ( (*(_BYTE *)v5 & 8) == 0 )
        (*(void (__thiscall **)(_DWORD, _DWORD, struct Err *))(**((_DWORD **)this + 5) + 20))(
          *((_DWORD *)this + 5),
          0,
          v5);
      (*(void (__thiscall **)(_DWORD, _DWORD, unsigned int *, int, _DWORD, struct Err *))(**((_DWORD **)this + 5) + 100))(
        *((_DWORD *)this + 5),
        *((_DWORD *)this + 7),
        &a2,
        4,
        0,
        v5);
      (*(void (__thiscall **)(_DWORD, _DWORD, unsigned int *, int, _DWORD, struct Err *))(**((_DWORD **)this + 5) + 100))(
        *((_DWORD *)this + 5),
        *((_DWORD *)this + 8),
        &v18,
        4,
        0,
        v5);
      (*(void (__thiscall **)(_DWORD, _DWORD, unsigned __int16 *, unsigned int, _DWORD, struct Err *))(**((_DWORD **)this + 5) + 100))(
        *((_DWORD *)this + 5),
        *((_DWORD *)this + 9),
        a3,
        2 * wcslen(a3),
        0,
        v5);
      (*(void (__thiscall **)(_DWORD, _DWORD, unsigned __int16 *, int, _DWORD, struct Err *))(**((_DWORD **)this + 5)
                                                                                            + 100))(
        *((_DWORD *)this + 5),
        *((_DWORD *)this + 10),
        &a4,
        2,
        0,
        v5);
      (*(void (__thiscall **)(_DWORD, _DWORD, unsigned int *, int, _DWORD, struct Err *))(**((_DWORD **)this + 5) + 100))(
        *((_DWORD *)this + 5),
        *((_DWORD *)this + 14),
        &v19,
        4,
        0,
        v5);
      (*(void (__thiscall **)(_DWORD, _DWORD, unsigned int *, int, _DWORD, struct Err *))(**((_DWORD **)this + 5) + 100))(
        *((_DWORD *)this + 5),
        *((_DWORD *)this + 11),
        v20,
        8,
        0,
        v5);
      (*(void (__thiscall **)(_DWORD, _DWORD, unsigned int *, int, _DWORD, struct Err *))(**((_DWORD **)this + 5) + 100))(
        *((_DWORD *)this + 5),
        *((_DWORD *)this + 12),
        v20,
        8,
        0,
        v5);
      if ( (*(_BYTE *)v5 & 8) != 0
        || ((*(void (__thiscall **)(_DWORD, struct Err *))(**((_DWORD **)this + 5) + 28))(*((_DWORD *)this + 5), v5),
            (*(_BYTE *)v5 & 8) != 0) )
      {
        (*(void (__thiscall **)(_DWORD, int, struct Err *))(**((_DWORD **)this + 5) + 20))(*((_DWORD *)this + 5), 3, v5);
      }
      v9 = *(_DWORD *)v5;
      if ( (*(_DWORD *)v5 & 8) == 0 || (v9 & 1) != 0 || *((_DWORD *)v5 + 1) != -1605 )
        break;
      if ( (v9 & 0xFFFFFFFE) != 0 )
      {
        if ( *((_DWORD *)v5 + 3) )
          operator delete[](*((void **)v5 + 3));
        if ( *((_DWORD *)v5 + 4) )
          operator delete[](*((void **)v5 + 4));
      }
      v10 = a3;
      v13 = a3;
      v12 = a2;
      *(_DWORD *)v5 = 1;
      Instance::ReadSysObjRecord(this, v12, v13, (void **)v5);
      if ( (*(_DWORD *)v5 & 8) == 0 )
      {
        Err::SetError(v5, -1314, -8243, v10, 0, v11);
        return;
      }
      if ( (*(_DWORD *)v5 & 0xFFFFFFFE) != 0 )
      {
        if ( *((_DWORD *)v5 + 3) )
          operator delete[](*((void **)v5 + 3));
        if ( *((_DWORD *)v5 + 4) )
          operator delete[](*((void **)v5 + 4));
      }
      ++v18;
      *(_DWORD *)v5 = 1;
    }
  }
}

```

## disassembly

```asm
0x10036a70  mov     edi, edi
0x10036a72  push    ebp
0x10036a73  mov     ebp, esp
0x10036a75  and     esp, 0FFFFFFF8h
0x10036a78  sub     esp, 14h
0x10036a7b  push    ebx
0x10036a7c  push    esi; struct Err *
0x10036a7d  mov     esi, [ebp+arg_C]
0x10036a80  mov     ebx, ecx
0x10036a82  mov     ecx, [ebp+arg_4]
0x10036a85  mov     edx, esi
0x10036a87  push    edi; unsigned int
0x10036a88  mov     [esp+20h+var_14], ebx
0x10036a8c  mov     [esp+20h+var_10], 0FFFFFFFFh
0x10036a94  mov     [esp+20h+var_C], 0
0x10036a9c  call    ?ValidateName@@YGXPBGAAVErr@@@Z; ValidateName(ushort const *,Err &)
0x10036aa1  cmp     [ebp+arg_8], 3
0x10036aa6  jnz     short loc_10036ABE
0x10036aa8  cmp     [ebp+arg_0], 0F000000h
0x10036aaf  jz      short loc_10036ABE
0x10036ab1  push    ecx
0x10036ab2  push    0FFFFFC15h
0x10036ab7  mov     ecx, esi
0x10036ab9  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10036abe  mov     ebx, [ebx+14h]
0x10036ac1  push    esi; unsigned int
0x10036ac2  push    offset aId; "Id"
0x10036ac7  mov     eax, [ebx]
0x10036ac9  mov     edi, [eax+8]
0x10036acc  mov     ecx, edi
0x10036ace  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10036ad4  mov     ecx, ebx
0x10036ad6  call    edi
0x10036ad8  test    byte ptr [esi], 8
0x10036adb  jnz     loc_10036DA3
0x10036ae1  mov     eax, [esp+20h+var_14]
0x10036ae5  push    esi
0x10036ae6  push    0
0x10036ae8  push    4; unsigned int
0x10036aea  mov     eax, [eax+14h]
0x10036aed  mov     ebx, [eax+24h]
0x10036af0  lea     eax, [esp+2Ch+var_10]
0x10036af4  push    eax; void *
0x10036af5  mov     edi, [ebx]
0x10036af7  mov     edi, [edi+18h]
0x10036afa  mov     ecx, edi
0x10036afc  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10036b02  mov     ecx, ebx
0x10036b04  call    edi
0x10036b06  mov     ecx, [esp+20h+var_14]
0x10036b0a  push    esi; unsigned int
0x10036b0b  push    2; void *
0x10036b0d  mov     eax, [ecx+14h]
0x10036b10  mov     ebx, [eax+24h]
0x10036b13  mov     eax, [ebx]
0x10036b15  mov     edi, [eax+1Ch]
0x10036b18  mov     ecx, edi
0x10036b1a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10036b20  mov     ecx, ebx
0x10036b22  call    edi
0x10036b24  mov     eax, [esi]
0x10036b26  test    al, 8
0x10036b28  jz      short loc_10036B45
0x10036b2a  test    al, 1
0x10036b2c  jnz     short loc_10036B45
0x10036b2e  cmp     dword ptr [esi+4], 0FFFFF9BFh
0x10036b35  jnz     short loc_10036B45
0x10036b37  mov     ecx, esi; this
0x10036b39  call    ?Reset@Err@@QAEXXZ; Err::Reset(void)
0x10036b3e  mov     eax, 80000000h
0x10036b43  jmp     short loc_10036B6F
0x10036b45  mov     eax, [esp+20h+var_14]
0x10036b49  lea     ecx, [esp+20h+var_10]
0x10036b4d  push    esi
0x10036b4e  push    0
0x10036b50  push    4
0x10036b52  mov     ebx, [eax+14h]
0x10036b55  push    ecx; unsigned int
0x10036b56  push    dword ptr [eax+20h]; void *
0x10036b59  mov     edi, [ebx]
0x10036b5b  mov     edi, [edi+6Ch]
0x10036b5e  mov     ecx, edi
0x10036b60  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10036b66  mov     ecx, ebx
0x10036b68  call    edi
0x10036b6a  mov     eax, [esp+20h+var_10]
0x10036b6e  inc     eax
0x10036b6f  lea     ecx, [esp+20h+var_8]
0x10036b73  mov     [esp+20h+var_10], eax
0x10036b77  call    ?GetDateTime@@YGXPAN@Z; GetDateTime(double *)
0x10036b7c  nop     dword ptr [eax+00h]
0x10036b80  test    byte ptr [esi], 8
0x10036b83  jnz     short loc_10036BA0
0x10036b85  mov     eax, [esp+20h+var_14]
0x10036b89  push    esi; unsigned int
0x10036b8a  push    0; void *
0x10036b8c  mov     ebx, [eax+14h]
0x10036b8f  mov     eax, [ebx]
0x10036b91  mov     edi, [eax+14h]
0x10036b94  mov     ecx, edi
0x10036b96  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10036b9c  mov     ecx, ebx
0x10036b9e  call    edi
0x10036ba0  mov     eax, [esp+20h+var_14]
0x10036ba4  lea     ecx, [ebp+arg_0]
0x10036ba7  push    esi
0x10036ba8  push    0
0x10036baa  push    4
0x10036bac  mov     ebx, [eax+14h]
0x10036baf  push    ecx; unsigned int
0x10036bb0  push    dword ptr [eax+1Ch]; void *
0x10036bb3  mov     edi, [ebx]
0x10036bb5  mov     edi, [edi+64h]
0x10036bb8  mov     ecx, edi
0x10036bba  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10036bc0  mov     ecx, ebx
0x10036bc2  call    edi
0x10036bc4  mov     eax, [esp+20h+var_14]
0x10036bc8  lea     ecx, [esp+20h+var_10]
0x10036bcc  push    esi
0x10036bcd  push    0
0x10036bcf  push    4
0x10036bd1  mov     ebx, [eax+14h]
0x10036bd4  push    ecx; unsigned int
0x10036bd5  push    dword ptr [eax+20h]; void *
0x10036bd8  mov     edi, [ebx]
0x10036bda  mov     edi, [edi+64h]
0x10036bdd  mov     ecx, edi
0x10036bdf  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10036be5  mov     ecx, ebx
0x10036be7  call    edi
0x10036be9  mov     ecx, [ebp+arg_4]
0x10036bec  lea     edx, [ecx+2]
0x10036bef  nop
0x10036bf0  mov     ax, [ecx]
0x10036bf3  add     ecx, 2
0x10036bf6  test    ax, ax
0x10036bf9  jnz     short loc_10036BF0
0x10036bfb  sub     ecx, edx
0x10036bfd  mov     edx, [esp+20h+var_14]
0x10036c01  sar     ecx, 1
0x10036c03  push    esi
0x10036c04  push    0
0x10036c06  mov     ebx, [edx+14h]
0x10036c09  lea     eax, [ecx+ecx]
0x10036c0c  push    eax
0x10036c0d  push    [ebp+arg_4]; unsigned int
0x10036c10  mov     edi, [ebx]
0x10036c12  push    dword ptr [edx+24h]; void *
0x10036c15  mov     edi, [edi+64h]
0x10036c18  mov     ecx, edi
0x10036c1a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10036c20  mov     ecx, ebx
0x10036c22  call    edi
0x10036c24  mov     eax, [esp+20h+var_14]
0x10036c28  lea     ecx, [ebp+arg_8]
0x10036c2b  push    esi
0x10036c2c  push    0
0x10036c2e  push    2
0x10036c30  mov     ebx, [eax+14h]
0x10036c33  push    ecx; unsigned int
0x10036c34  push    dword ptr [eax+28h]; void *
0x10036c37  mov     edi, [ebx]
0x10036c39  mov     edi, [edi+64h]
0x10036c3c  mov     ecx, edi
0x10036c3e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10036c44  mov     ecx, ebx
0x10036c46  call    edi
0x10036c48  mov     eax, [esp+20h+var_14]
0x10036c4c  lea     ecx, [esp+20h+var_C]
0x10036c50  push    esi
0x10036c51  push    0
0x10036c53  push    4
0x10036c55  mov     ebx, [eax+14h]
0x10036c58  push    ecx; unsigned int
0x10036c59  push    dword ptr [eax+38h]; void *
0x10036c5c  mov     edi, [ebx]
0x10036c5e  mov     edi, [edi+64h]
0x10036c61  mov     ecx, edi
0x10036c63  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10036c69  mov     ecx, ebx
0x10036c6b  call    edi
0x10036c6d  mov     eax, [esp+20h+var_14]
0x10036c71  lea     ecx, [esp+20h+var_8]
0x10036c75  push    esi
0x10036c76  push    0
0x10036c78  push    8
0x10036c7a  mov     ebx, [eax+14h]
0x10036c7d  push    ecx; unsigned int
0x10036c7e  push    dword ptr [eax+2Ch]; void *
0x10036c81  mov     edi, [ebx]
0x10036c83  mov     edi, [edi+64h]
0x10036c86  mov     ecx, edi
0x10036c88  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10036c8e  mov     ecx, ebx
0x10036c90  call    edi
0x10036c92  mov     eax, [esp+20h+var_14]
0x10036c96  lea     ecx, [esp+20h+var_8]
0x10036c9a  push    esi
0x10036c9b  push    0
0x10036c9d  push    8
0x10036c9f  mov     ebx, [eax+14h]
0x10036ca2  push    ecx; unsigned int
0x10036ca3  push    dword ptr [eax+30h]; void *
0x10036ca6  mov     edi, [ebx]
0x10036ca8  mov     edi, [edi+64h]
0x10036cab  mov     ecx, edi
0x10036cad  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10036cb3  mov     ecx, ebx
0x10036cb5  call    edi
0x10036cb7  test    byte ptr [esi], 8
0x10036cba  jnz     short loc_10036CDA
0x10036cbc  mov     eax, [esp+20h+var_14]
0x10036cc0  push    esi; void *
0x10036cc1  mov     ebx, [eax+14h]
0x10036cc4  mov     eax, [ebx]
0x10036cc6  mov     edi, [eax+1Ch]
0x10036cc9  mov     ecx, edi
0x10036ccb  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10036cd1  mov     ecx, ebx
0x10036cd3  call    edi
0x10036cd5  test    byte ptr [esi], 8
0x10036cd8  jz      short loc_10036CF5
0x10036cda  mov     eax, [esp+20h+var_14]
0x10036cde  push    esi; unsigned int
0x10036cdf  push    3; void *
0x10036ce1  mov     ebx, [eax+14h]
0x10036ce4  mov     eax, [ebx]
0x10036ce6  mov     edi, [eax+14h]
0x10036ce9  mov     ecx, edi
0x10036ceb  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10036cf1  mov     ecx, ebx
0x10036cf3  call    edi
0x10036cf5  mov     eax, [esi]
0x10036cf7  test    al, 8
0x10036cf9  jz      loc_10036DA3
0x10036cff  test    al, 1
0x10036d01  jnz     loc_10036DA3
0x10036d07  cmp     dword ptr [esi+4], 0FFFFF9BBh
0x10036d0e  jnz     loc_10036DA3
0x10036d14  test    eax, 0FFFFFFFEh
0x10036d19  jz      short loc_10036D3B
0x10036d1b  mov     eax, [esi+0Ch]
0x10036d1e  test    eax, eax
0x10036d20  jz      short loc_10036D2B
0x10036d22  push    eax; Block
0x10036d23  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10036d28  add     esp, 4
0x10036d2b  mov     eax, [esi+10h]
0x10036d2e  test    eax, eax
0x10036d30  jz      short loc_10036D3B
0x10036d32  push    eax; Block
0x10036d33  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10036d38  add     esp, 4
0x10036d3b  mov     ebx, [ebp+arg_4]
0x10036d3e  mov     ecx, [esp+20h+var_14]; this
0x10036d42  push    esi; struct Err *
0x10036d43  push    ebx; unsigned __int16 *
0x10036d44  push    [ebp+arg_0]; unsigned int
0x10036d47  mov     dword ptr [esi], 1
0x10036d4d  call    ?ReadSysObjRecord@Instance@@QAEXKPBGAAVErr@@@Z; Instance::ReadSysObjRecord(ulong,ushort const *,Err &)
0x10036d52  mov     eax, [esi]
0x10036d54  test    al, 8
0x10036d56  jz      short loc_10036D8E
0x10036d58  test    eax, 0FFFFFFFEh
0x10036d5d  jz      short loc_10036D7F
0x10036d5f  mov     eax, [esi+0Ch]
0x10036d62  test    eax, eax
0x10036d64  jz      short loc_10036D6F
0x10036d66  push    eax; Block
0x10036d67  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10036d6c  add     esp, 4
0x10036d6f  mov     eax, [esi+10h]
0x10036d72  test    eax, eax
0x10036d74  jz      short loc_10036D7F
0x10036d76  push    eax; Block
0x10036d77  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10036d7c  add     esp, 4
0x10036d7f  inc     [esp+20h+var_10]
0x10036d83  mov     dword ptr [esi], 1
0x10036d89  jmp     loc_10036B80
0x10036d8e  push    ecx
0x10036d8f  push    0
0x10036d91  push    ebx
0x10036d92  push    0FFFFDFCDh
0x10036d97  push    0FFFFFADEh
0x10036d9c  mov     ecx, esi
0x10036d9e  call    ?SetError@Err@@QAEXJJPBG0W4ErrAssert@@@Z; Err::SetError(long,long,ushort const *,ushort const *,ErrAssert)
0x10036da3  pop     edi
0x10036da4  pop     esi
0x10036da5  pop     ebx
0x10036da6  mov     esp, ebp
0x10036da8  pop     ebp
0x10036da9  retn    10h
```
