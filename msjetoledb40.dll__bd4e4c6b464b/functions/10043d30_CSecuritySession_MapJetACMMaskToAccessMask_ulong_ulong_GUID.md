# CSecuritySession::MapJetACMMaskToAccessMask(ulong,ulong &,_GUID *)

- ea: `0x10043d30`
- end: `0x10043e8e`
- name: `?MapJetACMMaskToAccessMask@CSecuritySession@@QAEJKAAKPAU_GUID@@@Z`
- size: `350`
- prototype: `int __thiscall(CSecuritySession *__hidden this, unsigned int, unsigned int *, struct _GUID *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10042630`

## callees

- `0x10043d30`

## pseudocode

```c
int __thiscall CSecuritySession::MapJetACMMaskToAccessMask(
        CSecuritySession *this,
        unsigned int a2,
        unsigned int *a3,
        struct _GUID *a4)
{
  int result; // eax
  struct _GUID *v5; // edi
  const GUID *v6; // esi
  struct _GUID *v7; // ebx
  bool v8; // cf
  unsigned int v9; // eax
  const GUID *v10; // esi
  unsigned int v11; // ebx
  unsigned int v12; // [esp+0h] [ebp-4h]

  *a3 = 0;
  if ( a2 == 0xFFFFF )
  {
    *a3 = 0x10000000;
    return 0;
  }
  else
  {
    v5 = a4;
    v6 = &DBOBJECT_DATABASE;
    v7 = a4;
    v12 = 12;
    while ( v6->Data1 == v7->Data1 )
    {
      v6 = (const GUID *)((char *)v6 + 4);
      v7 = (struct _GUID *)((char *)v7 + 4);
      v8 = v12 < 4;
      v12 -= 4;
      if ( v8 )
      {
        v9 = 0;
        if ( (a2 & 2) != 0 )
        {
          *a3 = 0x80000000;
          v9 = 0x80000000;
        }
        if ( (a2 & 4) != 0 )
        {
          v9 |= 0x200u;
          *a3 = v9;
        }
        if ( (a2 & 8) != 0 )
        {
          v9 |= 0x800u;
LABEL_37:
          *a3 = v9;
        }
        goto LABEL_38;
      }
    }
    v10 = &DBOBJECT_COLUMN;
    v11 = 12;
    while ( v10->Data1 == v5->Data1 )
    {
      v10 = (const GUID *)((char *)v10 + 4);
      v5 = (struct _GUID *)((char *)v5 + 4);
      v8 = v11 < 4;
      v11 -= 4;
      if ( v8 )
      {
        result = 0;
        if ( (a2 & 0x100) != 0 )
          *a3 = 0x40000000;
        return result;
      }
    }
    v9 = 0;
    if ( (a2 & 0x10) != 0 )
    {
      *a3 = 0x80000000;
      v9 = 0x80000000;
    }
    if ( (a2 & 0x40) != 0 )
    {
      v9 |= 0x40000000u;
      *a3 = v9;
    }
    if ( (a2 & 0x20) != 0 )
    {
      v9 |= 0x8000u;
      *a3 = v9;
    }
    if ( (a2 & 0x80u) != 0 )
    {
      v9 |= 0x10000u;
      *a3 = v9;
    }
    if ( (a2 & 4) != 0 )
    {
      v9 |= 0x400u;
      *a3 = v9;
    }
    if ( (a2 & 8) != 0 )
    {
      v9 |= 0x800u;
      *a3 = v9;
    }
    if ( (a2 & 0x80000) != 0 )
    {
      v9 |= 0x80000u;
      *a3 = v9;
    }
    if ( (a2 & 0x20000) != 0 )
    {
      v9 |= 0x20000u;
      *a3 = v9;
    }
    if ( (a2 & 0x40000) != 0 )
    {
      v9 |= 0x40000u;
      *a3 = v9;
    }
    if ( (a2 & 0x10000) != 0 )
    {
      v9 |= 0x100u;
      goto LABEL_37;
    }
LABEL_38:
    if ( (a2 & 1) != 0 )
      *a3 = v9 | 0x4000;
    return 0;
  }
}

```

## disassembly

```asm
0x10043d30  mov     edi, edi
0x10043d32  push    ebp
0x10043d33  mov     ebp, esp
0x10043d35  push    ecx
0x10043d36  mov     edx, [ebp+arg_4]
0x10043d39  mov     ecx, [ebp+arg_0]
0x10043d3c  mov     dword ptr [edx], 0
0x10043d42  cmp     ecx, 0FFFFFh
0x10043d48  jnz     short loc_10043D58
0x10043d4a  mov     dword ptr [edx], 10000000h
0x10043d50  xor     eax, eax
0x10043d52  mov     esp, ebp
0x10043d54  pop     ebp
0x10043d55  retn    0Ch
0x10043d58  push    ebx
0x10043d59  push    esi
0x10043d5a  push    edi
0x10043d5b  mov     edi, [ebp+arg_8]
0x10043d5e  mov     esi, offset _DBOBJECT_DATABASE
0x10043d63  mov     ebx, edi
0x10043d65  mov     [ebp+var_4], 0Ch
0x10043d6c  nop     dword ptr [eax+00h]
0x10043d70  mov     eax, [esi]
0x10043d72  cmp     eax, [ebx]
0x10043d74  jnz     short loc_10043DB3
0x10043d76  add     esi, 4
0x10043d79  add     ebx, 4
0x10043d7c  sub     [ebp+var_4], 4
0x10043d80  jnb     short loc_10043D70
0x10043d82  xor     eax, eax
0x10043d84  test    cl, 2
0x10043d87  jz      short loc_10043D94
0x10043d89  mov     dword ptr [edx], 80000000h
0x10043d8f  mov     eax, 80000000h
0x10043d94  test    cl, 4
0x10043d97  jz      short loc_10043DA0
0x10043d99  or      eax, 200h
0x10043d9e  mov     [edx], eax
0x10043da0  test    cl, 8
0x10043da3  jz      loc_10043E77
0x10043da9  or      eax, 800h
0x10043dae  jmp     loc_10043E75
0x10043db3  mov     esi, offset _DBOBJECT_COLUMN
0x10043db8  mov     ebx, 0Ch
0x10043dbd  nop     dword ptr [eax]
0x10043dc0  mov     eax, [esi]
0x10043dc2  cmp     eax, [edi]
0x10043dc4  jnz     short loc_10043DEE
0x10043dc6  add     esi, 4
0x10043dc9  add     edi, 4
0x10043dcc  sub     ebx, 4
0x10043dcf  jnb     short loc_10043DC0
0x10043dd1  xor     eax, eax
0x10043dd3  test    ecx, 100h
0x10043dd9  jz      loc_10043E85
0x10043ddf  pop     edi
0x10043de0  pop     esi
0x10043de1  mov     dword ptr [edx], 40000000h
0x10043de7  pop     ebx
0x10043de8  mov     esp, ebp
0x10043dea  pop     ebp
0x10043deb  retn    0Ch
0x10043dee  xor     eax, eax
0x10043df0  test    cl, 10h
0x10043df3  jz      short loc_10043E00
0x10043df5  mov     dword ptr [edx], 80000000h
0x10043dfb  mov     eax, 80000000h
0x10043e00  test    cl, 40h
0x10043e03  jz      short loc_10043E0C
0x10043e05  or      eax, 40000000h
0x10043e0a  mov     [edx], eax
0x10043e0c  test    cl, 20h
0x10043e0f  jz      short loc_10043E18
0x10043e11  or      eax, 8000h
0x10043e16  mov     [edx], eax
0x10043e18  test    cl, cl
0x10043e1a  jns     short loc_10043E23
0x10043e1c  or      eax, 10000h
0x10043e21  mov     [edx], eax
0x10043e23  test    cl, 4
0x10043e26  jz      short loc_10043E2F
0x10043e28  or      eax, 400h
0x10043e2d  mov     [edx], eax
0x10043e2f  test    cl, 8
0x10043e32  jz      short loc_10043E3B
0x10043e34  or      eax, 800h
0x10043e39  mov     [edx], eax
0x10043e3b  test    ecx, 80000h
0x10043e41  jz      short loc_10043E4A
0x10043e43  or      eax, 80000h
0x10043e48  mov     [edx], eax
0x10043e4a  test    ecx, 20000h
0x10043e50  jz      short loc_10043E59
0x10043e52  or      eax, 20000h
0x10043e57  mov     [edx], eax
0x10043e59  test    ecx, 40000h
0x10043e5f  jz      short loc_10043E68
0x10043e61  or      eax, 40000h
0x10043e66  mov     [edx], eax
0x10043e68  test    ecx, 10000h
0x10043e6e  jz      short loc_10043E77
0x10043e70  or      eax, 100h
0x10043e75  mov     [edx], eax
0x10043e77  test    cl, 1
0x10043e7a  jz      short loc_10043E83
0x10043e7c  or      eax, 4000h
0x10043e81  mov     [edx], eax
0x10043e83  xor     eax, eax
0x10043e85  pop     edi
0x10043e86  pop     esi
0x10043e87  pop     ebx
0x10043e88  mov     esp, ebp
0x10043e8a  pop     ebp
0x10043e8b  retn    0Ch
```
