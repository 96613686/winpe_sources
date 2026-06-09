# TextSpecRead(x,x,x,x,x)

- ea: `0x1001c250`
- end: `0x1001c37c`
- name: `_TextSpecRead@20`
- size: `300`
- prototype: `int __stdcall(int, JET_TABLEID tableid, int, int, JET_TABLEID)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1000f0e0`
- `0x10010020`
- `0x10011d90`

## callees

- `0x10018b90`
- `0x10019f20`
- `0x1001ba80`
- `0x1001c250`
- `0x1002b620`

## import_xrefs

- `KERNEL32!GetACP` at `0x1001c346`
- `KERNEL32!GetACP` at `0x1001c346`

## pseudocode

```c
JET_ERR __stdcall TextSpecRead(int a1, const WCHAR *tableid, void *a3, int a4, JET_TABLEID a5)
{
  JET_ERR v5; // esi
  int v6; // edi
  _DWORD *v7; // ebx
  int v8; // ebp
  int v9; // eax
  JET_TABLEID v10; // esi
  bool v11; // zf
  int v13; // [esp+Ch] [ebp-4h] BYREF

  v5 = 0;
  if ( a5 )
  {
    v7 = (_DWORD *)a1;
    v8 = *(_DWORD *)(a1 + 4);
    v9 = OpenIMEXSpec(v8, &tableid, &a5);
    v6 = a4;
    if ( v9 )
    {
      v5 = AccessSpecRead(a1, *(_DWORD *)(v8 + 40), *(_DWORD *)(v8 + 44), (JET_TABLEID)tableid, a5, a3, a4);
      if ( !v5 )
      {
        v10 = a5;
        JetCloseTable(*(_DWORD *)(v8 + 40), (JET_TABLEID)tableid);
        JetCloseTable(*(_DWORD *)(v8 + 40), v10);
        v5 = 0;
      }
    }
    *(_DWORD *)(v6 + 28) = *(_DWORD *)(a1 + 852);
    *(_DWORD *)(v6 + 52) = *(unsigned __int8 *)(a1 + 856);
    *(_DWORD *)(v6 + 36) = *(_DWORD *)(a1 + 864);
    *(_DWORD *)(v6 + 44) = *(_DWORD *)(a1 + 868);
  }
  else
  {
    v6 = a4;
    v5 = INIFileSpecRead(tableid, (int)a3, a4, &v13);
    v7 = (_DWORD *)a1;
    if ( !v13 )
      *(_DWORD *)(v6 + 36) = *(_DWORD *)(a1 + 864);
    *(_DWORD *)(v6 + 44) = *(_DWORD *)(a1 + 868);
  }
  v11 = *(_DWORD *)(v6 + 52) == 2;
  *(_DWORD *)(v6 + 40) = v7[218];
  *(_DWORD *)(v6 + 824) = v7[220];
  if ( v11 )
  {
    *(_DWORD *)(v6 + 28) = 1;
    *(_DWORD *)(v6 + 32) = 0;
    *(_DWORD *)(v6 + 36) = GetACP();
    *(_DWORD *)(v6 + 52) = 2;
    *(_DWORD *)(v6 + 56) = 851977;
    *(_DWORD *)(v6 + 60) = 10;
    *(_WORD *)(v6 + 72) = 34;
  }
  *(_DWORD *)(v6 + 20) = v7[8];
  return v5;
}

```

## disassembly

```asm
0x1001c250  push    ecx
0x1001c251  push    ebx
0x1001c252  push    esi
0x1001c253  xor     esi, esi
0x1001c255  push    edi
0x1001c256  cmp     [esp+10h+arg_10], esi
0x1001c25a  jnz     short loc_1001C297
0x1001c25c  mov     edi, [esp+10h+arg_C]
0x1001c260  lea     eax, [esp+10h+var_4]
0x1001c264  push    eax; int
0x1001c265  push    edi; int
0x1001c266  push    [esp+18h+arg_8]; int
0x1001c26a  push    [esp+1Ch+tableid]; pszSrc
0x1001c26e  call    INIFileSpecRead
0x1001c273  cmp     [esp+10h+var_4], 0
0x1001c278  mov     esi, eax
0x1001c27a  mov     ebx, [esp+10h+arg_0]
0x1001c27e  jnz     short loc_1001C289
0x1001c280  mov     ecx, [ebx+360h]
0x1001c286  mov     [edi+24h], ecx
0x1001c289  mov     ecx, [ebx+364h]
0x1001c28f  mov     [edi+2Ch], ecx
0x1001c292  jmp     loc_1001C31D
0x1001c297  mov     ebx, [esp+10h+arg_0]
0x1001c29b  lea     eax, [esp+10h+arg_10]
0x1001c29f  push    ebp
0x1001c2a0  push    eax
0x1001c2a1  lea     eax, [esp+18h+tableid]
0x1001c2a5  mov     ebp, [ebx+4]
0x1001c2a8  push    eax
0x1001c2a9  push    ebp
0x1001c2aa  call    OpenIMEXSpec
0x1001c2af  mov     edi, [esp+14h+arg_C]
0x1001c2b3  test    eax, eax
0x1001c2b5  jz      short loc_1001C2F7
0x1001c2b7  push    edi; int
0x1001c2b8  push    [esp+18h+arg_8]; int
0x1001c2bc  push    [esp+1Ch+arg_10]; JET_TABLEID
0x1001c2c0  push    [esp+20h+tableid]; tableid
0x1001c2c4  push    dword ptr [ebp+2Ch]; int
0x1001c2c7  push    dword ptr [ebp+28h]; sesid
0x1001c2ca  push    ebx; int
0x1001c2cb  call    AccessSpecRead
0x1001c2d0  mov     esi, eax
0x1001c2d2  mov     [esp+14h+arg_0], esi
0x1001c2d6  test    esi, esi
0x1001c2d8  jnz     short loc_1001C2F7
0x1001c2da  push    [esp+14h+tableid]; tableid
0x1001c2de  mov     esi, [esp+18h+arg_10]
0x1001c2e2  push    dword ptr [ebp+28h]; sesid
0x1001c2e5  call    _JetCloseTable@8; JetCloseTable(x,x)
0x1001c2ea  push    esi; tableid
0x1001c2eb  push    dword ptr [ebp+28h]; sesid
0x1001c2ee  call    _JetCloseTable@8; JetCloseTable(x,x)
0x1001c2f3  mov     esi, [esp+14h+arg_0]
0x1001c2f7  mov     eax, [ebx+354h]
0x1001c2fd  mov     [edi+1Ch], eax
0x1001c300  movzx   eax, byte ptr [ebx+358h]
0x1001c307  mov     [edi+34h], eax
0x1001c30a  mov     eax, [ebx+360h]
0x1001c310  mov     [edi+24h], eax
0x1001c313  mov     eax, [ebx+364h]
0x1001c319  mov     [edi+2Ch], eax
0x1001c31c  pop     ebp
0x1001c31d  cmp     dword ptr [edi+34h], 2
0x1001c321  mov     eax, [ebx+368h]
0x1001c327  mov     [edi+28h], eax
0x1001c32a  mov     eax, [ebx+370h]
0x1001c330  mov     [edi+338h], eax
0x1001c336  jnz     short loc_1001C36D
0x1001c338  mov     dword ptr [edi+1Ch], 1
0x1001c33f  mov     dword ptr [edi+20h], 0
0x1001c346  call    ds:__imp__GetACP@0; GetACP()
0x1001c34c  mov     [edi+24h], eax
0x1001c34f  mov     eax, 22h ; '"'
0x1001c354  mov     dword ptr [edi+34h], 2
0x1001c35b  mov     dword ptr [edi+38h], 0D0009h
0x1001c362  mov     dword ptr [edi+3Ch], 0Ah
0x1001c369  mov     [edi+48h], ax
0x1001c36d  mov     eax, [ebx+20h]
0x1001c370  mov     [edi+14h], eax
0x1001c373  mov     eax, esi
0x1001c375  pop     edi
0x1001c376  pop     esi
0x1001c377  pop     ebx
0x1001c378  pop     ecx
0x1001c379  retn    14h
```
