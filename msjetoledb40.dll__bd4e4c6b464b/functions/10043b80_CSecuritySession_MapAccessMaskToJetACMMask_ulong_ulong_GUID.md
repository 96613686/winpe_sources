# CSecuritySession::MapAccessMaskToJetACMMask(ulong,ulong &,_GUID *)

- ea: `0x10043b80`
- end: `0x10043d1e`
- name: `?MapAccessMaskToJetACMMask@CSecuritySession@@QAEJKAAKPAU_GUID@@@Z`
- size: `414`
- prototype: `int __thiscall(CSecuritySession *__hidden this, unsigned int, unsigned int *, struct _GUID *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10042c60`
- `0x10042ed0`

## callees

- `0x10043b80`

## pseudocode

```c
int __thiscall CSecuritySession::MapAccessMaskToJetACMMask(
        CSecuritySession *this,
        signed int a2,
        unsigned int *a3,
        struct _GUID *a4)
{
  struct _GUID *v4; // esi
  const GUID *v6; // edi
  struct _GUID *v7; // ebx
  bool v8; // cf
  unsigned int v9; // eax
  bool v10; // zf
  const GUID *v11; // edi
  unsigned int v12; // ebx
  unsigned int v13; // eax
  unsigned int v14; // [esp+Ch] [ebp-4h]

  v4 = a4;
  *a3 = 0;
  if ( !a4 )
    return -2147467259;
  if ( (a2 & 0x12000000) != 0 )
  {
    *a3 = 0xFFFFF;
    return 0;
  }
  else
  {
    v6 = &DBOBJECT_DATABASE;
    v14 = 12;
    v7 = a4;
    do
    {
      if ( v6->Data1 != v7->Data1 )
      {
        v11 = &DBOBJECT_COLUMN;
        v12 = 12;
        while ( v11->Data1 == v4->Data1 )
        {
          v11 = (const GUID *)((char *)v11 + 4);
          v4 = (struct _GUID *)((char *)v4 + 4);
          v8 = v12 < 4;
          v12 -= 4;
          if ( v8 )
          {
            if ( (a2 & 0x40000000) != 0 )
              *a3 = 256;
            v10 = (a2 & 0xADFFFFFF) == 0;
            goto LABEL_17;
          }
        }
        v13 = 0;
        if ( a2 < 0 )
        {
          *a3 = 20;
          v13 = 20;
        }
        if ( (a2 & 0x40000000) != 0 )
        {
          v13 |= 0x40u;
          *a3 = v13;
        }
        if ( (a2 & 0x8000) != 0 )
        {
          v13 |= 0x20u;
          *a3 = v13;
        }
        if ( (a2 & 0x10000) != 0 )
        {
          v13 |= 0x80u;
          *a3 = v13;
        }
        if ( (a2 & 0x400) != 0 )
        {
          v13 |= 4u;
          *a3 = v13;
        }
        if ( (a2 & 0x800) != 0 )
        {
          v13 |= 8u;
          *a3 = v13;
        }
        if ( (a2 & 0x40000) != 0 )
        {
          v13 |= 0x40000u;
          *a3 = v13;
        }
        if ( (a2 & 0x80000) != 0 )
        {
          v13 |= 0x80000u;
          *a3 = v13;
        }
        if ( (a2 & 0x20000) != 0 )
        {
          v13 |= 0x20000u;
          *a3 = v13;
        }
        if ( (a2 & 0x100) != 0 )
        {
          v13 |= 0x10000u;
          *a3 = v13;
        }
        if ( (a2 & 0x4000) != 0 )
          *a3 = v13 | 1;
        if ( (a2 & 0x2DF032FF) == 0 )
          return 0;
        return -2147217809;
      }
      v6 = (const GUID *)((char *)v6 + 4);
      v7 = (struct _GUID *)((char *)v7 + 4);
      v8 = v14 < 4;
      v14 -= 4;
    }
    while ( !v8 );
    v9 = 0;
    if ( a2 < 0 )
    {
      *a3 = 2;
      v9 = 2;
    }
    if ( (a2 & 0x200) != 0 )
    {
      v9 |= 4u;
      *a3 = v9;
    }
    if ( (a2 & 0x800) != 0 )
    {
      v9 |= 8u;
      *a3 = v9;
    }
    if ( (a2 & 0x4000) != 0 )
      *a3 = v9 | 1;
    v10 = (a2 & 0x6DFFB5FF) == 0;
LABEL_17:
    if ( v10 )
      return 0;
    return -2147217809;
  }
}

```

## disassembly

```asm
0x10043b80  mov     edi, edi
0x10043b82  push    ebp
0x10043b83  mov     ebp, esp
0x10043b85  push    ecx
0x10043b86  mov     edx, [ebp+arg_4]
0x10043b89  push    ebx
0x10043b8a  push    esi
0x10043b8b  mov     esi, [ebp+arg_8]
0x10043b8e  mov     dword ptr [edx], 0
0x10043b94  push    edi
0x10043b95  test    esi, esi
0x10043b97  jnz     short loc_10043BA7
0x10043b99  pop     edi
0x10043b9a  pop     esi
0x10043b9b  mov     eax, 80004005h
0x10043ba0  pop     ebx
0x10043ba1  mov     esp, ebp
0x10043ba3  pop     ebp
0x10043ba4  retn    0Ch
0x10043ba7  mov     ecx, [ebp+arg_0]
0x10043baa  test    ecx, 12000000h
0x10043bb0  jz      short loc_10043BC3
0x10043bb2  pop     edi
0x10043bb3  pop     esi
0x10043bb4  mov     dword ptr [edx], 0FFFFFh
0x10043bba  xor     eax, eax
0x10043bbc  pop     ebx
0x10043bbd  mov     esp, ebp
0x10043bbf  pop     ebp
0x10043bc0  retn    0Ch
0x10043bc3  mov     edi, offset _DBOBJECT_DATABASE
0x10043bc8  mov     [ebp+var_4], 0Ch
0x10043bcf  mov     ebx, esi
0x10043bd1  mov     eax, [edi]
0x10043bd3  cmp     eax, [ebx]
0x10043bd5  jnz     short loc_10043C32
0x10043bd7  add     edi, 4
0x10043bda  add     ebx, 4
0x10043bdd  sub     [ebp+var_4], 4
0x10043be1  jnb     short loc_10043BD1
0x10043be3  xor     eax, eax
0x10043be5  test    ecx, ecx
0x10043be7  jns     short loc_10043BF4
0x10043be9  mov     dword ptr [edx], 2
0x10043bef  mov     eax, 2
0x10043bf4  test    ecx, 200h
0x10043bfa  jz      short loc_10043C01
0x10043bfc  or      eax, 4
0x10043bff  mov     [edx], eax
0x10043c01  test    ecx, 800h
0x10043c07  jz      short loc_10043C0E
0x10043c09  or      eax, 8
0x10043c0c  mov     [edx], eax
0x10043c0e  test    ecx, 4000h
0x10043c14  jz      short loc_10043C1B
0x10043c16  or      eax, 1
0x10043c19  mov     [edx], eax
0x10043c1b  test    ecx, 6DFFB5FFh
0x10043c21  jnz     loc_10043D10
0x10043c27  xor     eax, eax
0x10043c29  pop     edi
0x10043c2a  pop     esi
0x10043c2b  pop     ebx
0x10043c2c  mov     esp, ebp
0x10043c2e  pop     ebp
0x10043c2f  retn    0Ch
0x10043c32  mov     edi, offset _DBOBJECT_COLUMN
0x10043c37  mov     ebx, 0Ch
0x10043c3c  nop     dword ptr [eax+00h]
0x10043c40  mov     eax, [edi]
0x10043c42  cmp     eax, [esi]
0x10043c44  jnz     short loc_10043C67
0x10043c46  add     edi, 4
0x10043c49  add     esi, 4
0x10043c4c  sub     ebx, 4
0x10043c4f  jnb     short loc_10043C40
0x10043c51  test    ecx, 40000000h
0x10043c57  jz      short loc_10043C5F
0x10043c59  mov     dword ptr [edx], 100h
0x10043c5f  test    ecx, 0ADFFFFFFh
0x10043c65  jmp     short loc_10043C21
0x10043c67  xor     eax, eax
0x10043c69  test    ecx, ecx
0x10043c6b  jns     short loc_10043C78
0x10043c6d  mov     dword ptr [edx], 14h
0x10043c73  mov     eax, 14h
0x10043c78  test    ecx, 40000000h
0x10043c7e  jz      short loc_10043C85
0x10043c80  or      eax, 40h
0x10043c83  mov     [edx], eax
0x10043c85  test    ecx, 8000h
0x10043c8b  jz      short loc_10043C92
0x10043c8d  or      eax, 20h
0x10043c90  mov     [edx], eax
0x10043c92  test    ecx, 10000h
0x10043c98  jz      short loc_10043CA1
0x10043c9a  or      eax, 80h
0x10043c9f  mov     [edx], eax
0x10043ca1  test    ecx, 400h
0x10043ca7  jz      short loc_10043CAE
0x10043ca9  or      eax, 4
0x10043cac  mov     [edx], eax
0x10043cae  test    ecx, 800h
0x10043cb4  jz      short loc_10043CBB
0x10043cb6  or      eax, 8
0x10043cb9  mov     [edx], eax
0x10043cbb  test    ecx, 40000h
0x10043cc1  jz      short loc_10043CCA
0x10043cc3  or      eax, 40000h
0x10043cc8  mov     [edx], eax
0x10043cca  test    ecx, 80000h
0x10043cd0  jz      short loc_10043CD9
0x10043cd2  or      eax, 80000h
0x10043cd7  mov     [edx], eax
0x10043cd9  test    ecx, 20000h
0x10043cdf  jz      short loc_10043CE8
0x10043ce1  or      eax, 20000h
0x10043ce6  mov     [edx], eax
0x10043ce8  test    ecx, 100h
0x10043cee  jz      short loc_10043CF7
0x10043cf0  or      eax, 10000h
0x10043cf5  mov     [edx], eax
0x10043cf7  test    ecx, 4000h
0x10043cfd  jz      short loc_10043D04
0x10043cff  or      eax, 1
0x10043d02  mov     [edx], eax
0x10043d04  test    ecx, 2DF032FFh
0x10043d0a  jz      loc_10043C27
0x10043d10  pop     edi
0x10043d11  pop     esi
0x10043d12  mov     eax, 80040E6Fh
0x10043d17  pop     ebx
0x10043d18  mov     esp, ebp
0x10043d1a  pop     ebp
0x10043d1b  retn    0Ch
```
