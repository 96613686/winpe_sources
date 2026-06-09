# OneCore::Base::Telemetry::OneSettingsQuery::ParseJsonResult(char *)

- ea: `0x180004ef4`
- end: `0x1800051ab`
- name: `?ParseJsonResult@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAD@Z`
- size: `695`
- prototype: `int(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, char *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800051b4`
- `0x180006c40`

## callees

- `0x180002c04`
- `0x180002eb0`
- `0x180003094`
- `0x180004ef4`
- `0x180005a6c`
- `0x1800191ba`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800050de`
- `msvcrt!_wtoi` at `0x1800050de`
- `KERNEL32!HeapAlloc` at `0x180004f61`
- `KERNEL32!HeapAlloc` at `0x180004f61`
- `KERNEL32!GetProcessHeap` at `0x180004f53`
- `KERNEL32!GetProcessHeap` at `0x180004f99`
- `KERNEL32!GetProcessHeap` at `0x180004fd4`
- `KERNEL32!GetProcessHeap` at `0x180005063`
- `KERNEL32!GetProcessHeap` at `0x180004f53`
- `KERNEL32!GetProcessHeap` at `0x180004f99`
- `KERNEL32!GetProcessHeap` at `0x180004fd4`
- `KERNEL32!GetProcessHeap` at `0x180005063`
- `KERNEL32!HeapFree` at `0x180004fa7`
- `KERNEL32!HeapFree` at `0x180004fe2`
- `KERNEL32!HeapFree` at `0x18000502e`
- `KERNEL32!HeapFree` at `0x18000504f`
- `KERNEL32!HeapFree` at `0x180004fa7`
- `KERNEL32!HeapFree` at `0x180004fe2`
- `KERNEL32!HeapFree` at `0x18000502e`
- `KERNEL32!HeapFree` at `0x18000504f`
- `KERNEL32!MultiByteToWideChar` at `0x180004f42`
- `KERNEL32!MultiByteToWideChar` at `0x180004f8f`
- `KERNEL32!MultiByteToWideChar` at `0x180004f42`
- `KERNEL32!MultiByteToWideChar` at `0x180004f8f`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::ParseJsonResult(
        OneCore::Base::Telemetry::OneSettingsQuery *this,
        char *a2)
{
  unsigned __int64 *v4; // rsi
  unsigned int cchWideChar; // edi
  HANDLE ProcessHeap; // rax
  WCHAR *lpWideCharStr; // rax
  WCHAR *v8; // rbx
  int v9; // ebx
  HANDLE v10; // rax
  void *v11; // rbx
  HANDLE v12; // rax
  HANDLE *v13; // rdi
  void *v14; // r8
  void *v15; // r8
  HANDLE v16; // rax
  unsigned __int64 v17; // r15
  const wchar_t ***v18; // rax
  const wchar_t **v19; // rbx
  const wchar_t *v20; // rcx
  const wchar_t *v21; // rax
  unsigned __int64 *v22; // r13
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // r14
  __int64 *v25; // rdx
  unsigned __int64 v26; // rax
  unsigned __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v31; // [rsp+30h] [rbp-10h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-8h]
  unsigned __int64 *v33; // [rsp+90h] [rbp+50h] BYREF
  unsigned __int64 *v34; // [rsp+98h] [rbp+58h] BYREF

  v34 = 0;
  lpMem = 0;
  v33 = 0;
  v31 = 0;
  v4 = 0;
  cchWideChar = MultiByteToWideChar(0xFDE9u, 0, a2, -1, 0, 0);
  if ( !cchWideChar )
  {
LABEL_6:
    v9 = -2147024883;
    goto LABEL_11;
  }
  ProcessHeap = GetProcessHeap();
  lpWideCharStr = (WCHAR *)HeapAlloc(ProcessHeap, 0, 2LL * cchWideChar);
  v8 = lpWideCharStr;
  if ( lpWideCharStr )
  {
    if ( MultiByteToWideChar(0xFDE9u, 0, a2, -1, lpWideCharStr, cchWideChar) )
    {
      lpMem = v8;
      v9 = JsonHelpersInternal::JsonReader::ReadJsonObjectAlloc((JsonHelpersInternal::JsonReader *)&v31, &v33);
      if ( v9 >= 0 )
      {
        v11 = lpMem;
        if ( lpMem )
        {
          v12 = GetProcessHeap();
          HeapFree(v12, 0, v11);
          lpMem = 0;
        }
        v4 = v33;
        v9 = 0;
        v34 = v33;
        v31 = 0;
        v33 = 0;
      }
      goto LABEL_11;
    }
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v8);
    goto LABEL_6;
  }
  v9 = -2147024882;
LABEL_11:
  CleanupJsonObject(&v33);
  if ( v9 < 0 )
    goto LABEL_37;
  v13 = (HANDLE *)((char *)this + 1608);
  RtlNameValueArray::Clear((OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1608));
  v14 = (void *)*((_QWORD *)this + 206);
  if ( v14 )
    HeapFree(*v13, 0, v14);
  *(_OWORD *)v13 = 0;
  *(_OWORD *)((char *)this + 1624) = 0;
  *(_OWORD *)((char *)this + 1640) = 0;
  v15 = (void *)*((_QWORD *)this + 206);
  if ( v15 )
    HeapFree(0, 0, v15);
  *(_OWORD *)v13 = 0;
  *(_OWORD *)((char *)this + 1624) = 0;
  *(_OWORD *)((char *)this + 1640) = 0;
  v16 = GetProcessHeap();
  *((_QWORD *)this + 205) = 16;
  v17 = 0;
  *v13 = v16;
  *((_QWORD *)this + 203) = 0;
  *((_QWORD *)this + 204) = 0;
  *((_QWORD *)this + 206) = 0;
  *((_QWORD *)this + 202) = 8;
  if ( !v4[2] )
  {
LABEL_36:
    v9 = 0;
    goto LABEL_37;
  }
  while ( 1 )
  {
    v18 = 0;
    if ( v17 < v4[2] )
    {
      if ( !is_mul_ok(v4[1], v17) || (v18 = (const wchar_t ***)(v4[5] + v4[1] * v17), (unsigned __int64)v18 < v4[5]) )
        v18 = 0;
    }
    v19 = *v18;
    if ( !wcscmp_0(**v18, L"refreshInterval") )
    {
      v20 = v19[1];
      if ( !*(_DWORD *)v20 )
        *((_DWORD *)this + 6) = _wtoi(*((const wchar_t **)v20 + 1));
      goto LABEL_35;
    }
    if ( !wcscmp_0(*v19, L"settings") )
    {
      v21 = v19[1];
      if ( *(_DWORD *)v21 != 5 )
      {
        v9 = -2147418113;
        goto LABEL_37;
      }
      v22 = (unsigned __int64 *)*((_QWORD *)v21 + 1);
      v23 = v22[2];
      if ( v23 )
        break;
    }
LABEL_35:
    if ( ++v17 >= v4[2] )
      goto LABEL_36;
  }
  v24 = 0;
  while ( 1 )
  {
    v25 = 0;
    if ( v24 < v23 )
    {
      v26 = v22[1] * v24;
      if ( !is_mul_ok(v22[1], v24) || (v27 = v22[5], v25 = (__int64 *)(v27 + v26), v27 + v26 < v27) )
        v25 = 0;
    }
    v28 = *v25;
    v29 = *(_QWORD *)(v28 + 8);
    if ( !*(_DWORD *)v29 )
    {
      v9 = RtlNameValueArray::Append(
             (OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1608),
             *(const unsigned __int16 **)v28,
             *(const unsigned __int16 **)(v29 + 8));
      if ( v9 < 0 )
        break;
    }
    v23 = v22[2];
    if ( ++v24 >= v23 )
      goto LABEL_35;
  }
LABEL_37:
  CleanupJsonObject(&v34);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180004ef4  mov     [rsp-38h+arg_0], rbx
0x180004ef9  push    rbp
0x180004efa  push    rsi
0x180004efb  push    rdi
0x180004efc  push    r12
0x180004efe  push    r13
0x180004f00  push    r14
0x180004f02  push    r15
0x180004f04  mov     rbp, rsp
0x180004f07  sub     rsp, 40h
0x180004f0b  xor     r13d, r13d
0x180004f0e  mov     r14, rdx
0x180004f11  mov     r12, rcx
0x180004f14  mov     [rsp+40h+cchWideChar], r13d; cchWideChar
0x180004f19  mov     r8, rdx; lpMultiByteStr
0x180004f1c  mov     [rsp+40h+lpWideCharStr], r13; lpWideCharStr
0x180004f21  or      r15d, 0FFFFFFFFh
0x180004f25  mov     [rbp+arg_18], r13
0x180004f29  mov     r9d, r15d; cbMultiByte
0x180004f2c  mov     [rbp+lpMem], r13
0x180004f30  xor     edx, edx; dwFlags
0x180004f32  mov     [rbp+arg_10], r13
0x180004f36  mov     ecx, 0FDE9h; CodePage
0x180004f3b  mov     [rbp+var_10], r13
0x180004f3f  mov     esi, r13d
0x180004f42  call    cs:__imp_MultiByteToWideChar
0x180004f48  mov     edi, eax
0x180004f4a  test    eax, eax
0x180004f4c  jz      short loc_180004FAD
0x180004f4e  mov     ebx, edi
0x180004f50  add     rbx, rbx
0x180004f53  call    cs:__imp_GetProcessHeap
0x180004f59  mov     r8, rbx; dwBytes
0x180004f5c  xor     edx, edx; dwFlags
0x180004f5e  mov     rcx, rax; hHeap
0x180004f61  call    cs:__imp_HeapAlloc
0x180004f67  mov     rbx, rax
0x180004f6a  test    rax, rax
0x180004f6d  jnz     short loc_180004F79
0x180004f6f  mov     ebx, 8007000Eh
0x180004f74  jmp     loc_180004FFF
0x180004f79  mov     [rsp+40h+cchWideChar], edi; cchWideChar
0x180004f7d  mov     r9d, r15d; cbMultiByte
0x180004f80  mov     r8, r14; lpMultiByteStr
0x180004f83  mov     [rsp+40h+lpWideCharStr], rbx; lpWideCharStr
0x180004f88  xor     edx, edx; dwFlags
0x180004f8a  mov     ecx, 0FDE9h; CodePage
0x180004f8f  call    cs:__imp_MultiByteToWideChar
0x180004f95  test    eax, eax
0x180004f97  jnz     short loc_180004FB4
0x180004f99  call    cs:__imp_GetProcessHeap
0x180004f9f  mov     r8, rbx; lpMem
0x180004fa2  xor     edx, edx; dwFlags
0x180004fa4  mov     rcx, rax; hHeap
0x180004fa7  call    cs:__imp_HeapFree
0x180004fad  mov     ebx, 8007000Dh
0x180004fb2  jmp     short loc_180004FFF
0x180004fb4  lea     rdx, [rbp+arg_10]
0x180004fb8  mov     [rbp+lpMem], rbx
0x180004fbc  lea     rcx, [rbp+var_10]; this
0x180004fc0  call    ?ReadJsonObjectAlloc@JsonReader@JsonHelpersInternal@@QEAAJPEAPEAV?$RtlArray@PEAUJsonKeyValuePair@@@@@Z; JsonHelpersInternal::JsonReader::ReadJsonObjectAlloc(RtlArray<JsonKeyValuePair *> * *)
0x180004fc5  mov     ebx, eax
0x180004fc7  test    eax, eax
0x180004fc9  js      short loc_180004FFF
0x180004fcb  mov     rbx, [rbp+lpMem]
0x180004fcf  test    rbx, rbx
0x180004fd2  jz      short loc_180004FEC
0x180004fd4  call    cs:__imp_GetProcessHeap
0x180004fda  mov     r8, rbx; lpMem
0x180004fdd  xor     edx, edx; dwFlags
0x180004fdf  mov     rcx, rax; hHeap
0x180004fe2  call    cs:__imp_HeapFree
0x180004fe8  mov     [rbp+lpMem], r13
0x180004fec  mov     rsi, [rbp+arg_10]
0x180004ff0  mov     ebx, r13d
0x180004ff3  mov     [rbp+arg_18], rsi
0x180004ff7  mov     [rbp+var_10], r13
0x180004ffb  mov     [rbp+arg_10], r13
0x180004fff  lea     rcx, [rbp+arg_10]
0x180005003  call    ?CleanupJsonObject@@YAXPEAPEAV?$RtlArray@PEAUJsonKeyValuePair@@@@@Z; CleanupJsonObject(RtlArray<JsonKeyValuePair *> * *)
0x180005008  test    ebx, ebx
0x18000500a  js      loc_180005181
0x180005010  lea     rdi, [r12+648h]
0x180005018  mov     rcx, rdi; this
0x18000501b  call    ?Clear@RtlNameValueArray@@QEAAXXZ; RtlNameValueArray::Clear(void)
0x180005020  mov     r8, [rdi+28h]; lpMem
0x180005024  test    r8, r8
0x180005027  jz      short loc_180005034
0x180005029  mov     rcx, [rdi]; hHeap
0x18000502c  xor     edx, edx; dwFlags
0x18000502e  call    cs:__imp_HeapFree
0x180005034  xorps   xmm0, xmm0
0x180005037  movups  xmmword ptr [rdi], xmm0
0x18000503a  movups  xmmword ptr [rdi+10h], xmm0
0x18000503e  movups  xmmword ptr [rdi+20h], xmm0
0x180005042  mov     r8, [rdi+28h]; lpMem
0x180005046  test    r8, r8
0x180005049  jz      short loc_180005055
0x18000504b  xor     edx, edx; dwFlags
0x18000504d  xor     ecx, ecx; hHeap
0x18000504f  call    cs:__imp_HeapFree
0x180005055  xorps   xmm0, xmm0
0x180005058  movups  xmmword ptr [rdi], xmm0
0x18000505b  movups  xmmword ptr [rdi+10h], xmm0
0x18000505f  movups  xmmword ptr [rdi+20h], xmm0
0x180005063  call    cs:__imp_GetProcessHeap
0x180005069  mov     qword ptr [rdi+20h], 10h
0x180005071  mov     r15, r13
0x180005074  mov     [rdi], rax
0x180005077  mov     [rdi+10h], r13
0x18000507b  mov     [rdi+18h], r13
0x18000507f  mov     [rdi+28h], r13
0x180005083  mov     qword ptr [rdi+8], 8
0x18000508b  cmp     [rsi+10h], r13
0x18000508f  jbe     loc_18000517E
0x180005095  mov     rax, r13
0x180005098  cmp     r15, [rsi+10h]
0x18000509c  jnb     short loc_1800050B7
0x18000509e  mov     rax, r15
0x1800050a1  mul     qword ptr [rsi+8]
0x1800050a5  test    rdx, rdx
0x1800050a8  jnz     short loc_1800050B4
0x1800050aa  add     rax, [rsi+28h]
0x1800050ae  cmp     rax, [rsi+28h]
0x1800050b2  jnb     short loc_1800050B7
0x1800050b4  mov     rax, r13
0x1800050b7  mov     rbx, [rax]
0x1800050ba  lea     rdx, aRefreshinterva; "refreshInterval"
0x1800050c1  mov     rcx, [rbx]; String1
0x1800050c4  call    wcscmp_0
0x1800050c9  test    eax, eax
0x1800050cb  jnz     short loc_1800050EE
0x1800050cd  mov     rcx, [rbx+8]
0x1800050d1  cmp     [rcx], r13d
0x1800050d4  jnz     loc_180005171
0x1800050da  mov     rcx, [rcx+8]; String
0x1800050de  call    cs:__imp__wtoi
0x1800050e4  mov     [r12+18h], eax
0x1800050e9  jmp     loc_180005171
0x1800050ee  mov     rcx, [rbx]; String1
0x1800050f1  lea     rdx, aSettings; "settings"
0x1800050f8  call    wcscmp_0
0x1800050fd  test    eax, eax
0x1800050ff  jnz     short loc_180005171
0x180005101  mov     rax, [rbx+8]
0x180005105  cmp     dword ptr [rax], 5
0x180005108  jnz     loc_1800051A4
0x18000510e  mov     r13, [rax+8]
0x180005112  mov     rax, [r13+10h]
0x180005116  test    rax, rax
0x180005119  jz      short loc_18000516E
0x18000511b  xor     r14d, r14d
0x18000511e  xor     edx, edx
0x180005120  cmp     r14, rax
0x180005123  jnb     short loc_180005140
0x180005125  mov     rax, r14
0x180005128  mul     qword ptr [r13+8]
0x18000512c  test    rdx, rdx
0x18000512f  jnz     short loc_18000513E
0x180005131  mov     rcx, [r13+28h]
0x180005135  lea     rdx, [rcx+rax]
0x180005139  cmp     rdx, rcx
0x18000513c  jnb     short loc_180005140
0x18000513e  xor     edx, edx
0x180005140  mov     rdx, [rdx]
0x180005143  mov     r8, [rdx+8]
0x180005147  cmp     dword ptr [r8], 0
0x18000514b  jnz     short loc_180005162
0x18000514d  mov     r8, [r8+8]; unsigned __int16 *
0x180005151  mov     rcx, rdi; this
0x180005154  mov     rdx, [rdx]; unsigned __int16 *
0x180005157  call    ?Append@RtlNameValueArray@@QEAAKPEBG0@Z; RtlNameValueArray::Append(ushort const *,ushort const *)
0x18000515c  mov     ebx, eax
0x18000515e  test    eax, eax
0x180005160  js      short loc_180005181
0x180005162  mov     rax, [r13+10h]
0x180005166  inc     r14
0x180005169  cmp     r14, rax
0x18000516c  jb      short loc_18000511E
0x18000516e  xor     r13d, r13d
0x180005171  inc     r15
0x180005174  cmp     r15, [rsi+10h]
0x180005178  jb      loc_180005095
0x18000517e  mov     ebx, r13d
0x180005181  lea     rcx, [rbp+arg_18]
0x180005185  call    ?CleanupJsonObject@@YAXPEAPEAV?$RtlArray@PEAUJsonKeyValuePair@@@@@Z; CleanupJsonObject(RtlArray<JsonKeyValuePair *> * *)
0x18000518a  mov     eax, ebx
0x18000518c  mov     rbx, [rsp+40h+arg_0]
0x180005194  add     rsp, 40h
0x180005198  pop     r15
0x18000519a  pop     r14
0x18000519c  pop     r13
0x18000519e  pop     r12
0x1800051a0  pop     rdi
0x1800051a1  pop     rsi
0x1800051a2  pop     rbp
0x1800051a3  retn
0x1800051a4  mov     ebx, 8000FFFFh
0x1800051a9  jmp     short loc_180005181
```
