# CSessionProperties::DoResultantActions(_GUID const &,ulong,CDBSession *)

- ea: `0x10021cf0`
- end: `0x10021ef9`
- name: `?DoResultantActions@CSessionProperties@@UAEJABU_GUID@@KPAVCDBSession@@@Z`
- size: `521`
- prototype: `int __thiscall(CSessionProperties *__hidden this, const struct _GUID *, unsigned int, struct CDBSession *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1001f2d0`
- `0x10021cf0`

## import_xrefs

- `msjet40!__imp__JetSetSystemParameter@20` at `0x10021ed3`
- `msjet40!__imp__JetSetSystemParameter@20` at `0x10021ed3`
- `msjet40!__imp__JetConnectionControl@12` at `0x10021e0e`
- `msjet40!__imp__JetConnectionControl@12` at `0x10021e0e`

## pseudocode

```c
int __thiscall CSessionProperties::DoResultantActions(
        CSessionProperties *this,
        const struct _GUID *a2,
        unsigned int a3,
        struct CDBSession *a4)
{
  int v4; // edi
  int v5; // eax
  __int128 *v6; // edx
  const struct _GUID *v7; // ecx
  unsigned int v8; // esi
  bool v9; // cf
  __int128 *v10; // edx
  __int128 *v11; // ecx
  unsigned int v12; // esi
  int v13; // edi
  int v14; // eax
  int v15; // eax
  int v16; // eax
  JoltProperties *v18; // edi
  unsigned int v19; // ecx
  int v20; // eax
  JoltProperties *v21; // edi
  int v22; // eax
  int v23; // eax
  int v24; // ecx
  CSessionProperties *v25; // [esp+10h] [ebp-30h]
  JoltProperties **v26; // [esp+10h] [ebp-30h]
  int v27; // [esp+14h] [ebp-2Ch]
  unsigned int v28; // [esp+18h] [ebp-28h] BYREF
  int v29; // [esp+1Ch] [ebp-24h] BYREF
  __int128 v30; // [esp+20h] [ebp-20h] BYREF
  __int128 v31; // [esp+30h] [ebp-10h] BYREF

  v25 = this;
  v4 = 0;
  v29 = *(_DWORD *)(*((_DWORD *)a4 + 21) + 96);
LABEL_2:
  v5 = *((_DWORD *)this + v4 + 2);
  v6 = &v30;
  v7 = a2;
  v8 = 12;
  v30 = *(_OWORD *)(v5 + 20);
  do
  {
    if ( v7->Data1 != *(_DWORD *)v6 )
    {
      if ( (unsigned int)++v4 >= 2 )
        return 0;
      this = v25;
      goto LABEL_2;
    }
    v7 = (const struct _GUID *)((char *)v7 + 4);
    v6 = (__int128 *)((char *)v6 + 4);
    v9 = v8 < 4;
    v8 -= 4;
  }
  while ( !v9 );
  v10 = &v31;
  v11 = &xmmword_10005450;
  v12 = 12;
  v26 = (JoltProperties **)((char *)v25 + 4 * v4 + 8);
  v31 = *(_OWORD *)((char *)*v26 + 20);
  while ( *(_DWORD *)v11 == *(_DWORD *)v10 )
  {
    v11 = (__int128 *)((char *)v11 + 4);
    v10 = (__int128 *)((char *)v10 + 4);
    v9 = v12 < 4;
    v12 -= 4;
    if ( v9 )
    {
      v13 = 0;
      v27 = 0;
      v14 = 0;
      while ( dword_10051810[2 * v14] != a3 )
      {
        if ( (unsigned int)++v14 >= 0xF )
          goto LABEL_15;
      }
      v13 = 1;
      v27 = v14;
LABEL_15:
      if ( a3 == 264 )
      {
        if ( JoltProperties::BinarySearch(*v26, 0x108u, &v28) >= 0
          && (v15 = *((_DWORD *)*v26 + 4), *(_WORD *)(v15 + 48 * v28 + 16) == 3) )
        {
          v16 = *(_DWORD *)(v15 + 48 * v28 + 24);
        }
        else
        {
          v16 = 0;
        }
        if ( (int)JetConnectionControl(*((_DWORD *)a4 + 4), *((_DWORD *)a4 + 5), v16) < 0 )
          return -2147467259;
      }
      if ( v13 )
      {
        switch ( a3 )
        {
          case 0xE3u:
          case 0xE7u:
          case 0xF9u:
          case 0x113u:
          case 0x115u:
            v18 = *v26;
            if ( JoltProperties::BinarySearch(*v26, a3, &v28) < 0 )
              goto LABEL_30;
            v19 = *((_DWORD *)v18 + 4) + 48 * v28;
            if ( *(_WORD *)(v19 + 16) != 11 )
              goto LABEL_30;
            v20 = *(_WORD *)(v19 + 24) == 0xFFFF;
            break;
          default:
            v21 = *v26;
            if ( JoltProperties::BinarySearch(*v26, a3, &v28) >= 0
              && (v22 = *((_DWORD *)v21 + 4), *(_WORD *)(v22 + 48 * v28 + 16) == 3) )
            {
              v20 = *(_DWORD *)(v22 + 48 * v28 + 24);
            }
            else
            {
LABEL_30:
              v20 = 0;
            }
            break;
        }
        v23 = JetSetSystemParameter(&v29, *((_DWORD *)a4 + 4), dword_10051814[2 * v27], v20, 0);
        v24 = 0;
        if ( v23 < 0 )
          return -2147467259;
        return v24;
      }
      return 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x10021cf0  mov     edi, edi
0x10021cf2  push    ebp
0x10021cf3  mov     ebp, esp
0x10021cf5  and     esp, 0FFFFFFF0h
0x10021cf8  sub     esp, 38h
0x10021cfb  mov     eax, [ebp+arg_8]
0x10021cfe  push    esi
0x10021cff  push    edi
0x10021d00  mov     [esp+40h+var_30], ecx
0x10021d04  xor     edi, edi
0x10021d06  mov     eax, [eax+54h]
0x10021d09  mov     eax, [eax+60h]
0x10021d0c  mov     [esp+40h+var_24], eax
0x10021d10  mov     eax, [ecx+edi*4+8]
0x10021d14  lea     edx, [esp+40h+var_20]
0x10021d18  mov     ecx, [ebp+arg_0]
0x10021d1b  mov     esi, 0Ch
0x10021d20  movups  xmm0, xmmword ptr [eax+14h]
0x10021d24  movups  [esp+40h+var_20], xmm0
0x10021d29  nop     dword ptr [eax+00000000h]
0x10021d30  mov     eax, [ecx]
0x10021d32  cmp     eax, [edx]
0x10021d34  jnz     short loc_10021DA5
0x10021d36  add     ecx, 4
0x10021d39  add     edx, 4
0x10021d3c  sub     esi, 4
0x10021d3f  jnb     short loc_10021D30
0x10021d41  mov     eax, [esp+40h+var_30]
0x10021d45  lea     edx, [esp+40h+var_10]
0x10021d49  mov     ecx, offset xmmword_10005450
0x10021d4e  mov     esi, 0Ch
0x10021d53  lea     eax, [eax+edi*4]
0x10021d56  add     eax, 8
0x10021d59  mov     [esp+40h+var_30], eax
0x10021d5d  mov     eax, [eax]
0x10021d5f  movups  xmm0, xmmword ptr [eax+14h]
0x10021d63  movups  [esp+40h+var_10], xmm0
0x10021d68  nop     dword ptr [eax+eax+00000000h]
0x10021d70  mov     eax, [ecx]
0x10021d72  cmp     eax, [edx]
0x10021d74  jnz     loc_10021EEF
0x10021d7a  add     ecx, 4
0x10021d7d  add     edx, 4
0x10021d80  sub     esi, 4
0x10021d83  jnb     short loc_10021D70
0x10021d85  mov     esi, [ebp+arg_4]
0x10021d88  xor     edi, edi
0x10021d8a  mov     [esp+40h+var_2C], 0
0x10021d92  xor     eax, eax
0x10021d94  cmp     dword_10051810[eax*8], esi
0x10021d9b  jz      short loc_10021DB8
0x10021d9d  inc     eax
0x10021d9e  cmp     eax, 0Fh
0x10021da1  jb      short loc_10021D94
0x10021da3  jmp     short loc_10021DC1
0x10021da5  inc     edi
0x10021da6  cmp     edi, 2
0x10021da9  jnb     loc_10021EEF
0x10021daf  mov     ecx, [esp+40h+var_30]
0x10021db3  jmp     loc_10021D10
0x10021db8  mov     edi, 1
0x10021dbd  mov     [esp+40h+var_2C], eax
0x10021dc1  cmp     esi, 108h
0x10021dc7  jnz     short loc_10021E25
0x10021dc9  lea     eax, [esp+40h+var_28]
0x10021dcd  push    eax; unsigned int *
0x10021dce  mov     eax, [esp+44h+var_30]
0x10021dd2  push    esi; unsigned int
0x10021dd3  mov     ecx, [eax]; this
0x10021dd5  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10021dda  test    eax, eax
0x10021ddc  js      short loc_10021E02
0x10021dde  mov     eax, [esp+40h+var_28]
0x10021de2  mov     edx, [esp+40h+var_30]
0x10021de6  lea     ecx, [eax+eax*2]
0x10021de9  mov     eax, [edx]
0x10021deb  add     ecx, ecx
0x10021ded  mov     edx, 3
0x10021df2  mov     eax, [eax+10h]
0x10021df5  cmp     dx, [eax+ecx*8+10h]
0x10021dfa  jnz     short loc_10021E02
0x10021dfc  mov     eax, [eax+ecx*8+18h]
0x10021e00  jmp     short loc_10021E04
0x10021e02  xor     eax, eax
0x10021e04  push    eax
0x10021e05  mov     eax, [ebp+arg_8]
0x10021e08  push    dword ptr [eax+14h]
0x10021e0b  push    dword ptr [eax+10h]
0x10021e0e  call    ds:__imp__JetConnectionControl@12; JetConnectionControl(x,x,x)
0x10021e14  test    eax, eax
0x10021e16  jns     short loc_10021E25
0x10021e18  mov     eax, 80004005h
0x10021e1d  pop     edi
0x10021e1e  pop     esi
0x10021e1f  mov     esp, ebp
0x10021e21  pop     ebp
0x10021e22  retn    0Ch
0x10021e25  test    edi, edi
0x10021e27  jz      loc_10021EEF
0x10021e2d  lea     eax, [esi-0E3h]; switch 51 cases
0x10021e33  cmp     eax, 32h
0x10021e36  ja      short def_10021E3F; jumptable 10021E3F default case, cases 228-230,232-248,250-274,276
0x10021e38  movzx   eax, ds:byte_10021F04[eax]
0x10021e3f  jmp     ds:jpt_10021E3F[eax*4]; switch jump
0x10021e46  mov     eax, [esp+40h+var_30]; jumptable 10021E3F cases 227,231,249,275,277
0x10021e4a  mov     edi, [eax]
0x10021e4c  lea     eax, [esp+40h+var_28]
0x10021e50  push    eax; unsigned int *
0x10021e51  push    esi; unsigned int
0x10021e52  mov     ecx, edi; this
0x10021e54  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10021e59  test    eax, eax
0x10021e5b  js      short loc_10021EB8
0x10021e5d  mov     eax, [esp+40h+var_28]
0x10021e61  lea     ecx, [eax+eax*2]
0x10021e64  mov     eax, 0Bh
0x10021e69  shl     ecx, 4
0x10021e6c  add     ecx, [edi+10h]
0x10021e6f  cmp     ax, [ecx+10h]
0x10021e73  jnz     short loc_10021EB8
0x10021e75  or      edx, 0FFFFFFFFh
0x10021e78  xor     eax, eax
0x10021e7a  cmp     dx, [ecx+18h]
0x10021e7e  setz    al
0x10021e81  jmp     short loc_10021EBA
0x10021e83  mov     eax, [esp+40h+var_30]; jumptable 10021E3F default case, cases 228-230,232-248,250-274,276
0x10021e87  mov     edi, [eax]
0x10021e89  lea     eax, [esp+40h+var_28]
0x10021e8d  push    eax; unsigned int *
0x10021e8e  push    esi; unsigned int
0x10021e8f  mov     ecx, edi; this
0x10021e91  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10021e96  test    eax, eax
0x10021e98  js      short loc_10021EB8
0x10021e9a  mov     eax, [esp+40h+var_28]
0x10021e9e  mov     edx, 3
0x10021ea3  lea     ecx, [eax+eax*2]
0x10021ea6  mov     eax, [edi+10h]
0x10021ea9  add     ecx, ecx
0x10021eab  cmp     dx, [eax+ecx*8+10h]
0x10021eb0  jnz     short loc_10021EB8
0x10021eb2  mov     eax, [eax+ecx*8+18h]
0x10021eb6  jmp     short loc_10021EBA
0x10021eb8  xor     eax, eax
0x10021eba  push    0
0x10021ebc  push    eax
0x10021ebd  mov     eax, [esp+48h+var_2C]
0x10021ec1  push    dword_10051814[eax*8]
0x10021ec8  mov     eax, [ebp+arg_8]
0x10021ecb  push    dword ptr [eax+10h]
0x10021ece  lea     eax, [esp+50h+var_24]
0x10021ed2  push    eax
0x10021ed3  call    ds:__imp__JetSetSystemParameter@20; JetSetSystemParameter(x,x,x,x,x)
0x10021ed9  xor     ecx, ecx
0x10021edb  mov     edx, 80004005h
0x10021ee0  test    eax, eax
0x10021ee2  cmovs   ecx, edx
0x10021ee5  mov     eax, ecx
0x10021ee7  pop     edi
0x10021ee8  pop     esi
0x10021ee9  mov     esp, ebp
0x10021eeb  pop     ebp
0x10021eec  retn    0Ch
0x10021eef  xor     eax, eax
0x10021ef1  pop     edi
0x10021ef2  pop     esi
0x10021ef3  mov     esp, ebp
0x10021ef5  pop     ebp
0x10021ef6  retn    0Ch
```
