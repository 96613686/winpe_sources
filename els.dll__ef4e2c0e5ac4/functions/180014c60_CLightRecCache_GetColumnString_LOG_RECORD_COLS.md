# CLightRecCache::GetColumnString(LOG_RECORD_COLS)

- ea: `0x180014c60`
- end: `0x180014dcf`
- name: `?GetColumnString@CLightRecCache@@QEAAPEAGW4LOG_RECORD_COLS@@@Z`
- size: `367`
- prototype: `wchar_t *__fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18001c1f0`

## callees

- `0x180004710`
- `0x180004774`
- `0x1800047bc`
- `0x180014c60`
- `0x180014dd8`
- `0x180019ae4`
- `0x180019b68`
- `0x18001b2b4`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180014d64`
- `msvcrt!swprintf_s` at `0x180014d64`

## pseudocode

```c
wchar_t *__fastcall CLightRecCache::GetColumnString(__int64 a1, int a2)
{
  int v3; // edx
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  __int64 v10; // rdx
  CSharedStringArray *v11; // rcx
  unsigned int v12; // edx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rbx
  const unsigned __int16 *SourceStrFromHandle; // rax
  CCategories *Categories; // rax

  if ( !a2 )
    return (wchar_t *)&g_awszEventType + 50 * *(unsigned __int8 *)(*(_QWORD *)(a1 + 32) + 18LL) - 100;
  v3 = a2 - 1;
  if ( !v3 )
    return GetDateStr(**(_DWORD **)(a1 + 32), (unsigned __int16 *)(a1 + 104), 0x104u);
  v4 = v3 - 1;
  if ( !v4 )
    return GetTimeStr(**(_DWORD **)(a1 + 32), (unsigned __int16 *)(a1 + 104), 0x104u);
  v5 = v4 - 1;
  if ( !v5 )
    return (wchar_t *)CLightRecCache::GetSourceStr((CLightRecCache *)a1);
  v6 = v5 - 1;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        if ( v8 != 1 )
          return (wchar_t *)&String;
        v10 = *(_QWORD *)(a1 + 32);
        v11 = *(CSharedStringArray **)(a1 + 80);
        v12 = *(_DWORD *)(v10 + 8);
      }
      else
      {
        v13 = *(_QWORD *)(a1 + 32);
        v11 = *(CSharedStringArray **)(a1 + 88);
        v12 = *(_DWORD *)(v13 + 4);
      }
      return CSharedStringArray::GetStringFromHandle(v11, v12);
    }
    swprintf_s((wchar_t *const)(a1 + 104), 0x104u, L"%u", *(unsigned __int16 *)(*(_QWORD *)(a1 + 32) + 16LL));
  }
  else
  {
    v14 = *(_QWORD *)(a1 + 32);
    if ( *(_DWORD *)(v14 + 24) == 1 && *(_DWORD *)(v14 + 20) != -1 )
    {
      v11 = *(CSharedStringArray **)(a1 + 96);
      v12 = *(_DWORD *)(v14 + 20);
      return CSharedStringArray::GetStringFromHandle(v11, v12);
    }
    if ( !*(_WORD *)(v14 + 12) )
      return &g_wszNone;
    v15 = *(_QWORD *)(a1 + 56);
    SourceStrFromHandle = CSources::GetSourceStrFromHandle((CSources *)(v15 + 4784), *(_WORD *)(v14 + 14));
    Categories = CSources::GetCategories((CSources *)(v15 + 4784), SourceStrFromHandle);
    if ( Categories )
      return (wchar_t *)CCategories::GetName(Categories, *(unsigned __int16 *)(*(_QWORD *)(a1 + 32) + 12LL));
    swprintf_s((wchar_t *const)(a1 + 104), 0x104u, L"(%u)", *(unsigned __int16 *)(*(_QWORD *)(a1 + 32) + 12LL));
  }
  return (wchar_t *)(a1 + 104);
}

```

## disassembly

```asm
0x180014c60  mov     [rsp+arg_0], rbx
0x180014c65  mov     [rsp+arg_8], rsi
0x180014c6a  push    rdi
0x180014c6b  sub     rsp, 20h
0x180014c6f  xor     esi, esi
0x180014c71  mov     rdi, rcx
0x180014c74  test    edx, edx
0x180014c76  jz      loc_180014DA5
0x180014c7c  sub     edx, 1
0x180014c7f  jz      loc_180014D8E
0x180014c85  sub     edx, 1
0x180014c88  jz      loc_180014D77
0x180014c8e  sub     edx, 1
0x180014c91  jz      loc_180014D70
0x180014c97  sub     edx, 1
0x180014c9a  jz      short loc_180014CE3
0x180014c9c  sub     edx, 1
0x180014c9f  jz      short loc_180014CD1
0x180014ca1  sub     edx, 1
0x180014ca4  jz      short loc_180014CC4
0x180014ca6  cmp     edx, 1
0x180014ca9  jz      short loc_180014CB7
0x180014cab  lea     rax, String
0x180014cb2  jmp     loc_180014DBF
0x180014cb7  mov     rdx, [rcx+20h]
0x180014cbb  mov     rcx, [rcx+50h]
0x180014cbf  mov     edx, [rdx+8]
0x180014cc2  jmp     short loc_180014CFB
0x180014cc4  mov     rdx, [rcx+20h]
0x180014cc8  mov     rcx, [rcx+58h]
0x180014ccc  mov     edx, [rdx+4]
0x180014ccf  jmp     short loc_180014CFB
0x180014cd1  mov     rcx, [rcx+20h]
0x180014cd5  lea     r8, aU_0; "%u"
0x180014cdc  movzx   r9d, word ptr [rcx+10h]
0x180014ce1  jmp     short loc_180014D5B
0x180014ce3  mov     rdx, [rcx+20h]
0x180014ce7  cmp     dword ptr [rdx+18h], 1
0x180014ceb  jnz     short loc_180014D05
0x180014ced  mov     eax, [rdx+14h]
0x180014cf0  cmp     eax, 0FFFFFFFFh
0x180014cf3  jz      short loc_180014D05
0x180014cf5  mov     rcx, [rcx+60h]; this
0x180014cf9  mov     edx, eax; unsigned int
0x180014cfb  call    ?GetStringFromHandle@CSharedStringArray@@QEAAPEAGK@Z; CSharedStringArray::GetStringFromHandle(ulong)
0x180014d00  jmp     loc_180014DBF
0x180014d05  cmp     [rdx+0Ch], si
0x180014d09  jnz     short loc_180014D17
0x180014d0b  lea     rax, ?g_wszNone@@3PAGA; ushort near * g_wszNone
0x180014d12  jmp     loc_180014DBF
0x180014d17  mov     rbx, [rcx+38h]
0x180014d1b  movzx   edx, word ptr [rdx+0Eh]; unsigned __int16
0x180014d1f  lea     rcx, [rbx+12B0h]; this
0x180014d26  call    ?GetSourceStrFromHandle@CSources@@QEAAPEBGG@Z; CSources::GetSourceStrFromHandle(ushort)
0x180014d2b  mov     rdx, rax; unsigned __int16 *
0x180014d2e  lea     rcx, [rbx+12B0h]; this
0x180014d35  call    ?GetCategories@CSources@@QEAAPEAVCCategories@@PEBG@Z; CSources::GetCategories(ushort const *)
0x180014d3a  mov     rcx, [rdi+20h]
0x180014d3e  movzx   edx, word ptr [rcx+0Ch]; unsigned int
0x180014d42  test    rax, rax
0x180014d45  jz      short loc_180014D51
0x180014d47  mov     rcx, rax; this
0x180014d4a  call    ?GetName@CCategories@@QEAAPEBGK@Z; CCategories::GetName(ulong)
0x180014d4f  jmp     short loc_180014DBF
0x180014d51  mov     r9d, edx
0x180014d54  lea     r8, aU_1; "(%u)"
0x180014d5b  mov     edx, 104h; BufferCount
0x180014d60  lea     rcx, [rdi+68h]; Buffer
0x180014d64  call    cs:__imp_swprintf_s
0x180014d6a  lea     rax, [rdi+68h]
0x180014d6e  jmp     short loc_180014DBF
0x180014d70  call    ?GetSourceStr@CLightRecCache@@QEAAPEBGXZ; CLightRecCache::GetSourceStr(void)
0x180014d75  jmp     short loc_180014DBF
0x180014d77  lea     rdx, [rcx+68h]; unsigned __int16 *
0x180014d7b  mov     r8d, 104h; unsigned int
0x180014d81  mov     rcx, [rcx+20h]
0x180014d85  mov     ecx, [rcx]; unsigned int
0x180014d87  call    ?GetTimeStr@@YAPEAGKPEAGK@Z; GetTimeStr(ulong,ushort *,ulong)
0x180014d8c  jmp     short loc_180014DBF
0x180014d8e  lea     rdx, [rcx+68h]; unsigned __int16 *
0x180014d92  mov     r8d, 104h; unsigned int
0x180014d98  mov     rcx, [rcx+20h]
0x180014d9c  mov     ecx, [rcx]; unsigned int
0x180014d9e  call    ?GetDateStr@@YAPEAGKPEAGK@Z; GetDateStr(ulong,ushort *,ulong)
0x180014da3  jmp     short loc_180014DBF
0x180014da5  mov     rax, [rcx+20h]
0x180014da9  movzx   ecx, byte ptr [rax+12h]
0x180014dad  sub     rcx, 2
0x180014db1  imul    rax, rcx, 64h ; 'd'
0x180014db5  lea     rcx, ?g_awszEventType@@3PAY0DC@GA; ushort (near * g_awszEventType)[50]
0x180014dbc  add     rax, rcx
0x180014dbf  mov     rbx, [rsp+28h+arg_0]
0x180014dc4  mov     rsi, [rsp+28h+arg_8]
0x180014dc9  add     rsp, 20h
0x180014dcd  pop     rdi
0x180014dce  retn
```
