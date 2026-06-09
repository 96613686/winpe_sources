# CDataSource::AttemptInitialize(int)

- ea: `0x10018f30`
- end: `0x10019066`
- name: `?AttemptInitialize@CDataSource@@QAGJH@Z`
- size: `310`
- prototype: `int __cdecl(CDataSource *__hidden this, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1001a2a0`

## callees

- `0x10018f30`
- `0x10019070`
- `0x1001f2d0`
- `0x10020c40`
- `0x10020c90`

## pseudocode

```c
int __fastcall CDataSource::AttemptInitialize(_DWORD *a1, int a2)
{
  const struct _GUID *v3; // esi
  JoltProperties *v4; // ebx
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int result; // eax
  int v9; // esi
  bool v10; // zf
  unsigned int v12; // [esp+14h] [ebp-Ch] BYREF
  int v13; // [esp+18h] [ebp-8h] BYREF
  int v14; // [esp+1Ch] [ebp-4h]

  v14 = 1;
  v3 = 0;
  v4 = (JoltProperties *)a1[40];
  v13 = 0;
  if ( JoltProperties::BinarySearch(v4, 0x3Bu, &v12) < 0
    || (v5 = *((_DWORD *)v4 + 4), *(_WORD *)(v5 + 48 * v12 + 16) != 8)
    || (v3 = *(const struct _GUID **)(v5 + 48 * v12 + 24)) == 0
    || !LOWORD(v3->Data1) )
  {
    v14 = 0;
  }
  if ( JoltProperties::BinarySearch(v4, 0xA0u, &v12) >= 0 )
  {
    v6 = *((_DWORD *)v4 + 4);
    if ( *(_WORD *)(v6 + 48 * v12 + 16) == 8 )
      v3 = *(const struct _GUID **)(v6 + 48 * v12 + 24);
  }
  if ( (!v3 || !LOWORD(v3->Data1)) && !v14 )
    goto LABEL_20;
  if ( JoltProperties::BinarySearch(v4, 0xCu, &v12) >= 0 )
  {
    v7 = *((_DWORD *)v4 + 4);
    if ( *(_WORD *)(v7 + 48 * v12 + 16) == 8 )
      v3 = *(const struct _GUID **)(v7 + 48 * v12 + 24);
  }
  if ( !v3 || !LOWORD(v3->Data1) )
    goto LABEL_20;
  CSettableProperties::SetPropertiesReadOnly((CSettableProperties *)(a1 + 38));
  a1[32] = 1;
  if ( a2 != 1 )
    return 0;
  result = CDataSource::OpenSessionAndDatabase((CDataSource *)a1, (const wchar_t *)a1, v3, &v13);
  v9 = result;
  if ( result < 0 )
  {
    v10 = v13 == -1902;
    a1[32] = 0;
    if ( !v10 )
    {
LABEL_21:
      CSettableProperties::SetPropertiesToTemplateRW((CSettableProperties *)(a1 + 38));
      return v9;
    }
LABEL_20:
    v9 = -2147217843;
    goto LABEL_21;
  }
  return result;
}

```

## disassembly

```asm
0x10018f30  mov     edi, edi
0x10018f32  push    ebp
0x10018f33  mov     ebp, esp
0x10018f35  sub     esp, 14h
0x10018f38  push    ebx
0x10018f39  push    esi
0x10018f3a  push    edi
0x10018f3b  mov     edi, ecx
0x10018f3d  mov     [ebp+var_10], edx
0x10018f40  lea     eax, [ebp+var_C]
0x10018f43  mov     [ebp+var_4], 1
0x10018f4a  push    eax; unsigned int *
0x10018f4b  xor     esi, esi
0x10018f4d  mov     ebx, [edi+0A0h]
0x10018f53  mov     ecx, ebx; this
0x10018f55  push    3Bh ; ';'; unsigned int
0x10018f57  mov     [ebp+var_8], esi
0x10018f5a  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10018f5f  lea     edx, [esi+8]
0x10018f62  test    eax, eax
0x10018f64  js      short loc_10018F87
0x10018f66  mov     eax, [ebp+var_C]
0x10018f69  lea     ecx, [eax+eax*2]
0x10018f6c  mov     eax, [ebx+10h]
0x10018f6f  add     ecx, ecx
0x10018f71  cmp     dx, [eax+ecx*8+10h]
0x10018f76  jnz     short loc_10018F87
0x10018f78  mov     esi, [eax+ecx*8+18h]
0x10018f7c  test    esi, esi
0x10018f7e  jz      short loc_10018F87
0x10018f80  xor     eax, eax
0x10018f82  cmp     ax, [esi]
0x10018f85  jnz     short loc_10018F8E
0x10018f87  mov     [ebp+var_4], 0
0x10018f8e  lea     eax, [ebp+var_C]
0x10018f91  mov     ecx, ebx; this
0x10018f93  push    eax; unsigned int *
0x10018f94  push    0A0h; unsigned int
0x10018f99  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10018f9e  test    eax, eax
0x10018fa0  js      short loc_10018FBD
0x10018fa2  mov     eax, [ebp+var_C]
0x10018fa5  mov     edx, 8
0x10018faa  lea     ecx, [eax+eax*2]
0x10018fad  mov     eax, [ebx+10h]
0x10018fb0  add     ecx, ecx
0x10018fb2  cmp     dx, [eax+ecx*8+10h]
0x10018fb7  jnz     short loc_10018FBD
0x10018fb9  mov     esi, [eax+ecx*8+18h]
0x10018fbd  test    esi, esi
0x10018fbf  jz      short loc_10018FC8
0x10018fc1  xor     eax, eax
0x10018fc3  cmp     ax, [esi]
0x10018fc6  jnz     short loc_10018FCE
0x10018fc8  cmp     [ebp+var_4], 0
0x10018fcc  jz      short loc_10019044
0x10018fce  lea     eax, [ebp+var_C]
0x10018fd1  mov     ecx, ebx; this
0x10018fd3  push    eax; unsigned int *
0x10018fd4  push    0Ch; unsigned int
0x10018fd6  call    ?BinarySearch@JoltProperties@@IBEJKAAK@Z; JoltProperties::BinarySearch(ulong,ulong &)
0x10018fdb  test    eax, eax
0x10018fdd  js      short loc_10018FFA
0x10018fdf  mov     eax, [ebp+var_C]
0x10018fe2  mov     edx, 8
0x10018fe7  lea     ecx, [eax+eax*2]
0x10018fea  mov     eax, [ebx+10h]
0x10018fed  add     ecx, ecx
0x10018fef  cmp     dx, [eax+ecx*8+10h]
0x10018ff4  jnz     short loc_10018FFA
0x10018ff6  mov     esi, [eax+ecx*8+18h]
0x10018ffa  test    esi, esi
0x10018ffc  jz      short loc_10019044
0x10018ffe  xor     eax, eax
0x10019000  cmp     ax, [esi]
0x10019003  jz      short loc_10019044
0x10019005  lea     ecx, [edi+98h]; this
0x1001900b  call    ?SetPropertiesReadOnly@CSettableProperties@@QAEJXZ; CSettableProperties::SetPropertiesReadOnly(void)
0x10019010  cmp     [ebp+var_10], 1
0x10019014  mov     dword ptr [edi+80h], 1
0x1001901e  jnz     short loc_1001905D
0x10019020  lea     eax, [ebp+var_8]
0x10019023  mov     ecx, edi; this
0x10019025  push    eax; int *
0x10019026  call    ?OpenSessionAndDatabase@CDataSource@@QAEJAAJ@Z; CDataSource::OpenSessionAndDatabase(long &)
0x1001902b  mov     esi, eax
0x1001902d  test    esi, esi
0x1001902f  jns     short loc_10019056
0x10019031  cmp     [ebp+var_8], 0FFFFF892h
0x10019038  mov     dword ptr [edi+80h], 0
0x10019042  jnz     short loc_10019049
0x10019044  mov     esi, 80040E4Dh
0x10019049  lea     ecx, [edi+98h]; this
0x1001904f  call    ?SetPropertiesToTemplateRW@CSettableProperties@@QAEJXZ; CSettableProperties::SetPropertiesToTemplateRW(void)
0x10019054  mov     eax, esi
0x10019056  pop     edi
0x10019057  pop     esi
0x10019058  pop     ebx
0x10019059  mov     esp, ebp
0x1001905b  pop     ebp
0x1001905c  retn
0x1001905d  pop     edi
0x1001905e  pop     esi
0x1001905f  xor     eax, eax
0x10019061  pop     ebx
0x10019062  mov     esp, ebp
0x10019064  pop     ebp
0x10019065  retn
```
