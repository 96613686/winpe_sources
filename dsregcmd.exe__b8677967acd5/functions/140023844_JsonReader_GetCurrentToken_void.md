# JsonReader::GetCurrentToken(void)

- ea: `0x140023844`
- end: `0x14002399b`
- name: `?GetCurrentToken@JsonReader@@AEAA?AW4JSON_PARSER_TOKEN@@XZ`
- size: `343`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400239a4`
- `0x140023c5c`
- `0x140023e64`

## callees

- `0x14001c78c`
- `0x140023844`
- `0x14002c3e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall JsonReader::GetCurrentToken(__int64 a1)
{
  __int64 v1; // r8
  __int64 v2; // r9
  __int64 v3; // r11
  unsigned int v4; // edx
  unsigned __int64 v5; // r10
  __int64 v6; // rcx
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  bool v11; // zf
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-18h] BYREF

  v1 = *(unsigned int *)(a1 + 48);
  v2 = *(_QWORD *)(a1 + 40);
  v3 = a1;
  v4 = 10;
  if ( *(_WORD *)(v2 + 2 * v1) )
  {
    do
    {
      v5 = *(unsigned __int16 *)(v2 + 2LL * (unsigned int)v1);
      if ( (unsigned int)v5 > 0x20 || (v6 = 0x100002200LL, !_bittest64(&v6, v5)) )
      {
        LODWORD(a1) = v1;
        if ( (_WORD)v5 != 10 )
          break;
      }
      a1 = (unsigned int)(v1 + 1);
      *(_DWORD *)(v3 + 48) = a1;
      LODWORD(v1) = v1 + 1;
    }
    while ( *(_WORD *)(v2 + 2 * a1) );
  }
  else
  {
    LODWORD(a1) = *(_DWORD *)(a1 + 48);
  }
  v7 = *(unsigned __int16 *)(v2 + 2LL * (unsigned int)a1);
  if ( v7 > 0x37 )
  {
    if ( v7 > 0x66 )
    {
      switch ( v7 )
      {
        case 'n':
          return 1;
        case 't':
          return 3;
        case '{':
          return 6;
        case '}':
          return 7;
      }
    }
    else
    {
      if ( v7 == 102 )
        return 2;
      v16 = v7 - 56;
      if ( !v16 )
        return 4;
      v17 = v16 - 1;
      if ( !v17 )
        return 4;
      v18 = v17 - 1;
      if ( !v18 )
        return 8;
      v19 = v18 - 33;
      if ( !v19 )
        return 9;
      if ( v19 == 2 )
        return v4;
    }
    goto LABEL_47;
  }
  if ( v7 == 55 )
    return 4;
  if ( v7 > 0x31 )
  {
    v12 = v7 - 50;
    if ( !v12 )
      return 4;
    v13 = v12 - 1;
    if ( !v13 )
      return 4;
    v14 = v13 - 1;
    if ( !v14 )
      return 4;
    v15 = v14 - 1;
    if ( !v15 )
      return 4;
    v11 = v15 == 1;
LABEL_25:
    if ( v11 )
      return 4;
LABEL_47:
    JsonException::JsonException((JsonException *)pExceptionObject, -895090681);
    throw (JsonException *)pExceptionObject;
  }
  if ( v7 == 49 )
    return 4;
  if ( v7 )
  {
    v8 = v7 - 34;
    if ( v8 )
    {
      v9 = v8 - 10;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          v11 = v10 == 3;
          goto LABEL_25;
        }
        return 4;
      }
      return 11;
    }
    else
    {
      return 5;
    }
  }
  else
  {
    return 12;
  }
}

```

## disassembly

```asm
0x140023844  push    rbx
0x140023846  sub     rsp, 30h
0x14002384a  mov     r8d, [rcx+30h]
0x14002384e  xor     ebx, ebx
0x140023850  mov     r9, [rcx+28h]
0x140023854  mov     r11, rcx
0x140023857  mov     edx, 0Ah
0x14002385c  cmp     [r9+r8*2], bx
0x140023861  jz      short loc_14002389E
0x140023863  mov     eax, r8d
0x140023866  movzx   r10d, word ptr [r9+rax*2]
0x14002386b  cmp     r10d, 20h ; ' '
0x14002386f  ja      short loc_140023881
0x140023871  mov     rcx, 100002200h
0x14002387b  bt      rcx, r10
0x14002387f  jb      short loc_14002388A
0x140023881  mov     ecx, r8d
0x140023884  cmp     r10w, dx
0x140023888  jnz     short loc_1400238A1
0x14002388a  lea     ecx, [r8+1]
0x14002388e  mov     [r11+30h], ecx
0x140023892  mov     r8d, ecx
0x140023895  cmp     [r9+rcx*2], bx
0x14002389a  jnz     short loc_140023863
0x14002389c  jmp     short loc_1400238A1
0x14002389e  mov     ecx, r8d
0x1400238a1  mov     eax, ecx
0x1400238a3  movzx   ecx, word ptr [r9+rax*2]
0x1400238a8  cmp     ecx, 37h ; '7'
0x1400238ab  ja      short loc_14002390F
0x1400238ad  jz      short loc_140023908
0x1400238af  cmp     ecx, 31h ; '1'
0x1400238b2  ja      short loc_1400238EF
0x1400238b4  jz      short loc_140023908
0x1400238b6  test    ecx, ecx
0x1400238b8  jz      short loc_1400238E5
0x1400238ba  sub     ecx, 22h ; '"'
0x1400238bd  jz      short loc_1400238DB
0x1400238bf  sub     ecx, edx
0x1400238c1  jz      short loc_1400238D1
0x1400238c3  sub     ecx, 1
0x1400238c6  jz      short loc_140023908
0x1400238c8  mov     edx, 3
0x1400238cd  cmp     ecx, edx
0x1400238cf  jmp     short loc_140023906
0x1400238d1  mov     edx, 0Bh
0x1400238d6  jmp     loc_140023972
0x1400238db  mov     edx, 5
0x1400238e0  jmp     loc_140023972
0x1400238e5  mov     edx, 0Ch
0x1400238ea  jmp     loc_140023972
0x1400238ef  sub     ecx, 32h ; '2'
0x1400238f2  jz      short loc_140023908
0x1400238f4  sub     ecx, 1
0x1400238f7  jz      short loc_140023908
0x1400238f9  sub     ecx, 1
0x1400238fc  jz      short loc_140023908
0x1400238fe  sub     ecx, 1
0x140023901  jz      short loc_140023908
0x140023903  cmp     ecx, 1
0x140023906  jnz     short loc_14002397A
0x140023908  mov     edx, 4
0x14002390d  jmp     short loc_140023972
0x14002390f  cmp     ecx, 66h ; 'f'
0x140023912  ja      short loc_140023946
0x140023914  jz      short loc_14002393F
0x140023916  sub     ecx, 38h ; '8'
0x140023919  jz      short loc_140023908
0x14002391b  sub     ecx, 1
0x14002391e  jz      short loc_140023908
0x140023920  sub     ecx, 1
0x140023923  jz      short loc_140023938
0x140023925  sub     ecx, 21h ; '!'
0x140023928  jz      short loc_140023931
0x14002392a  cmp     ecx, 2
0x14002392d  jnz     short loc_14002397A
0x14002392f  jmp     short loc_140023972
0x140023931  mov     edx, 9
0x140023936  jmp     short loc_140023972
0x140023938  mov     edx, 8
0x14002393d  jmp     short loc_140023972
0x14002393f  mov     edx, 2
0x140023944  jmp     short loc_140023972
0x140023946  cmp     ecx, 6Eh ; 'n'
0x140023949  jz      short loc_14002396D
0x14002394b  cmp     ecx, 74h ; 't'
0x14002394e  jz      short loc_140023966
0x140023950  cmp     ecx, 7Bh ; '{'
0x140023953  jz      short loc_14002395F
0x140023955  cmp     ecx, 7Dh ; '}'
0x140023958  jnz     short loc_14002397A
0x14002395a  lea     edx, [rcx-76h]
0x14002395d  jmp     short loc_140023972
0x14002395f  mov     edx, 6
0x140023964  jmp     short loc_140023972
0x140023966  mov     edx, 3
0x14002396b  jmp     short loc_140023972
0x14002396d  mov     edx, 1
0x140023972  mov     eax, edx
0x140023974  add     rsp, 30h
0x140023978  pop     rbx
0x140023979  retn
0x14002397a  mov     edx, 0CAA60007h; int
0x14002397f  lea     rcx, [rsp+38h+pExceptionObject]; this
0x140023984  call    ??0JsonException@@QEAA@J@Z; JsonException::JsonException(long)
0x140023989  lea     rdx, _TI2?AVJsonException@@; pThrowInfo
0x140023990  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x140023995  call    _CxxThrowException_0
```
