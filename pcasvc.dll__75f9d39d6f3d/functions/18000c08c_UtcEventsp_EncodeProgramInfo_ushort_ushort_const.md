# UtcEventsp_EncodeProgramInfo(ushort * *,ushort const *)

- ea: `0x18000c08c`
- end: `0x18000c55a`
- name: `?UtcEventsp_EncodeProgramInfo@@YAKPEAPEAGPEBG@Z`
- size: `1230`
- prototype: `unsigned int(unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800473a0`

## callees

- `0x180007b3c`
- `0x18000a57c`
- `0x18000a750`
- `0x18000b76c`
- `0x18000c08c`
- `0x18000c560`
- `0x180012920`
- `0x180019c84`
- `0x18001cbac`
- `0x18002ae2c`
- `0x180056256`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18000c246`
- `msvcrt!swprintf_s` at `0x18000c246`
- `ntdll!RtlFreeHeap` at `0x18000c440`
- `ntdll!RtlFreeHeap` at `0x18000c462`
- `ntdll!RtlFreeHeap` at `0x18000c440`
- `ntdll!RtlFreeHeap` at `0x18000c462`
- `ntdll!RtlAllocateHeap` at `0x18000c3f6`
- `ntdll!RtlAllocateHeap` at `0x18000c3f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c4cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c4cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c11e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c11e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18000c325`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18000c325`

## string_xrefs

- `0x18000c4dc`: `Failed to open key [%d]`
- `0x18000c532`: `Failed to compute program Id [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall UtcEventsp_EncodeProgramInfo(unsigned __int16 **a1, const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  int UInt32; // ebx
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rax
  __int64 *v9; // rax
  int v10; // eax
  const unsigned __int16 *FileNameW; // rax
  unsigned int i; // edi
  const unsigned __int16 **v13; // rax
  const unsigned __int16 *v14; // rdx
  const unsigned __int16 *v15; // r9
  unsigned __int16 v16; // ax
  unsigned __int16 *v17; // rcx
  size_t v18; // rdi
  unsigned __int16 *Heap; // rax
  unsigned __int16 *v20; // rsi
  const char *v22; // r9
  int v23; // r8d
  int v24; // r8d
  unsigned __int16 *v25; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE HeapHandle; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v28; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v29; // [rsp+50h] [rbp-B0h]
  PVOID P; // [rsp+68h] [rbp-98h]
  SIZE_T Size[2]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v32; // [rsp+88h] [rbp-78h]
  void *Src[2]; // [rsp+98h] [rbp-68h]
  _QWORD v34[3]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v35; // [rsp+C0h] [rbp-40h]
  wchar_t Buffer[20]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 v37[48]; // [rsp+F0h] [rbp-10h] BYREF

  hKey = 0;
  RtlStringArray::RtlStringArray((RtlStringArray *)&HeapHandle);
  *(_OWORD *)Size = 0;
  v32 = 0;
  *(_OWORD *)Src = 0;
  Size[0] = (SIZE_T)NtCurrentPeb()->ProcessHeap;
  *((_QWORD *)&v32 + 1) = 4096;
  v25 = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 1u, &hKey);
  if ( v4 )
  {
    v22 = "Failed to open key [%d]";
    v23 = 274;
LABEL_57:
    AslLogCallPrintf(1, (unsigned int)"UtcEventsp_EncodeProgramInfo", v23, (_DWORD)v22);
    goto LABEL_44;
  }
  if ( (int)AslRegistryGetString(&v25, hKey, L"DisplayName") < 0 )
  {
    RtlStringArray::Append((RtlStringArray *)&HeapHandle, &sourceString, 0);
  }
  else
  {
    RtlStringArray::Append((RtlStringArray *)&HeapHandle, v25, 0);
    AslFree(NtCurrentPeb()->ProcessHeap, v25);
    v25 = 0;
  }
  if ( (int)AslRegistryGetString(&v25, hKey, L"Publisher") < 0 )
  {
    RtlStringArray::Append((RtlStringArray *)&HeapHandle, &sourceString, 0);
  }
  else
  {
    RtlStringArray::Append((RtlStringArray *)&HeapHandle, v25, 0);
    AslFree(NtCurrentPeb()->ProcessHeap, v25);
    v25 = 0;
  }
  if ( (int)AslRegistryGetString(&v25, hKey, L"DisplayVersion") < 0 )
  {
    RtlStringArray::Append((RtlStringArray *)&HeapHandle, &sourceString, 0);
  }
  else
  {
    RtlStringArray::Append((RtlStringArray *)&HeapHandle, v25, 0);
    AslFree(NtCurrentPeb()->ProcessHeap, v25);
  }
  LODWORD(v25) = 0;
  UInt32 = AslRegistryGetUInt32(&v25, hKey, L"Language");
  swprintf_s(Buffer, 0x10u, L"%d", (unsigned int)v25);
  RtlStringArray::Append((RtlStringArray *)&HeapHandle, Buffer, 0);
  if ( v29 != 4 )
  {
    v4 = 8;
    v24 = 334;
LABEL_60:
    AslLogCallPrintf(1, (unsigned int)"UtcEventsp_EncodeProgramInfo", v24, (unsigned int)"Out of memory");
    goto LABEL_44;
  }
  if ( is_mul_ok(v28, 0) )
    v6 = P;
  else
    v6 = 0;
  v34[0] = *v6;
  if ( !is_mul_ok(v28, 1u) || (v7 = (char *)P + v28, (char *)P + v28 < P) )
    v7 = 0;
  v34[1] = *v7;
  if ( !is_mul_ok(v28, 2u) || (v8 = (char *)P + 2 * v28, v8 < P) )
    v8 = 0;
  v34[2] = *v8;
  if ( UInt32 < 0 )
  {
    v35 = 0;
  }
  else
  {
    if ( !is_mul_ok(v28, 3u) || (v9 = (__int64 *)((char *)P + 3 * v28), v9 < P) )
      v9 = 0;
    v35 = *v9;
  }
  v10 = AeComputeProgramIdentityHash(v34, v37);
  if ( v10 < 0 )
  {
    v4 = (unsigned __int16)v10;
    v22 = "Failed to compute program Id [%d]";
    v23 = 350;
    goto LABEL_57;
  }
  v4 = RtlStringArray::Append((RtlStringArray *)&HeapHandle, v37, 0);
  if ( v4 )
  {
    v24 = 356;
    goto LABEL_60;
  }
  FileNameW = PathFindFileNameW(a2);
  v4 = RtlStringArray::Append((RtlStringArray *)&HeapHandle, FileNameW, 0);
  if ( v4 )
  {
    v24 = 366;
    goto LABEL_60;
  }
  for ( i = 0; i < v29; ++i )
  {
    if ( !is_mul_ok(v28, i) || (v13 = (const unsigned __int16 **)((char *)P + v28 * i), v13 < P) )
      v13 = 0;
    v14 = *v13;
    v15 = &dword_1800FF0F4;
    if ( i != v29 - 1 )
      v15 = L",";
    v16 = *v14;
    if ( *v14 )
    {
      v17 = (unsigned __int16 *)v14;
      do
      {
        if ( v16 == 59 || v16 == 44 )
          *v17 = 95;
        v16 = *++v17;
      }
      while ( *v17 );
    }
    v4 = RtlMemoryStream::WriteString((RtlMemoryStream *)Size, v14, v15);
    if ( v4 )
    {
      v24 = 386;
      goto LABEL_60;
    }
  }
  v18 = Size[1];
  v4 = 8;
  Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Size[1]);
  v20 = Heap;
  if ( !Heap )
  {
    v24 = 398;
    goto LABEL_60;
  }
  if ( v18 )
    memcpy_0(Heap, Src[1], v18);
  *a1 = v20;
  v4 = 0;
LABEL_44:
  if ( hKey )
    RegCloseKey(hKey);
  if ( Src[1] )
    RtlFreeHeap((HANDLE)Size[0], 0, Src[1]);
  RtlStringArray::Clear((RtlStringArray *)&HeapHandle);
  if ( P )
    RtlFreeHeap(HeapHandle, 0, P);
  return v4;
}

```

## disassembly

```asm
0x18000c08c  mov     [rsp-8+arg_10], rbx
0x18000c091  mov     [rsp-8+arg_18], rsi
0x18000c096  push    rbp
0x18000c097  push    rdi
0x18000c098  push    r12
0x18000c09a  push    r14
0x18000c09c  push    r15
0x18000c09e  lea     rbp, [rsp-60h]
0x18000c0a3  sub     rsp, 160h
0x18000c0aa  mov     rax, cs:__security_cookie
0x18000c0b1  xor     rax, rsp
0x18000c0b4  mov     [rbp+80h+var_30], rax
0x18000c0b8  mov     rdi, rdx
0x18000c0bb  mov     r14, rcx
0x18000c0be  xor     r15d, r15d
0x18000c0c1  mov     [rsp+180h+hKey], r15
0x18000c0c6  lea     rcx, [rsp+180h+HeapHandle]; this
0x18000c0cb  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x18000c0d0  nop
0x18000c0d1  xorps   xmm0, xmm0
0x18000c0d4  movups  xmmword ptr [rsp+180h+Size], xmm0
0x18000c0d9  movups  [rbp+80h+var_F8], xmm0
0x18000c0dd  movups  xmmword ptr [rbp+80h+Src], xmm0
0x18000c0e1  mov     rax, gs:60h
0x18000c0ea  mov     rcx, [rax+30h]
0x18000c0ee  mov     [rsp+180h+Size], rcx
0x18000c0f3  mov     qword ptr [rbp+80h+var_F8+8], 1000h
0x18000c0fb  mov     [rsp+180h+var_150], r15
0x18000c100  lea     rax, [rsp+180h+hKey]
0x18000c105  mov     [rsp+180h+phkResult], rax; phkResult
0x18000c10a  lea     r12d, [r15+1]
0x18000c10e  mov     r9d, r12d; samDesired
0x18000c111  xor     r8d, r8d; ulOptions
0x18000c114  mov     rdx, rdi; lpSubKey
0x18000c117  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c11e  call    cs:__imp_RegOpenKeyExW
0x18000c124  mov     ebx, eax
0x18000c126  test    eax, eax
0x18000c128  jnz     loc_18000C4D8
0x18000c12e  lea     r8, aDisplayname; "DisplayName"
0x18000c135  mov     rdx, [rsp+180h+hKey]
0x18000c13a  lea     rcx, [rsp+180h+var_150]
0x18000c13f  call    AslRegistryGetString
0x18000c144  lea     rbx, sourceString
0x18000c14b  xor     r8d, r8d; unsigned __int64
0x18000c14e  lea     rcx, [rsp+180h+HeapHandle]; this
0x18000c153  test    eax, eax
0x18000c155  js      loc_18000C49D
0x18000c15b  mov     rdx, [rsp+180h+var_150]; unsigned __int16 *
0x18000c160  call    ?Append@RtlStringArray@@QEAAJPEBG_K@Z; RtlStringArray::Append(ushort const *,unsigned __int64)
0x18000c165  mov     rcx, gs:60h
0x18000c16e  mov     rdx, [rsp+180h+var_150]
0x18000c173  mov     rcx, [rcx+30h]
0x18000c177  call    AslFree
0x18000c17c  mov     [rsp+180h+var_150], r15
0x18000c181  lea     r8, aPublisher_0; "Publisher"
0x18000c188  mov     rdx, [rsp+180h+hKey]
0x18000c18d  lea     rcx, [rsp+180h+var_150]
0x18000c192  call    AslRegistryGetString
0x18000c197  xor     r8d, r8d; unsigned __int64
0x18000c19a  lea     rcx, [rsp+180h+HeapHandle]; this
0x18000c19f  test    eax, eax
0x18000c1a1  js      loc_18000C4AA
0x18000c1a7  mov     rdx, [rsp+180h+var_150]; unsigned __int16 *
0x18000c1ac  call    ?Append@RtlStringArray@@QEAAJPEBG_K@Z; RtlStringArray::Append(ushort const *,unsigned __int64)
0x18000c1b1  mov     rcx, gs:60h
0x18000c1ba  mov     rdx, [rsp+180h+var_150]
0x18000c1bf  mov     rcx, [rcx+30h]
0x18000c1c3  call    AslFree
0x18000c1c8  mov     [rsp+180h+var_150], r15
0x18000c1cd  lea     r8, ValueName; "DisplayVersion"
0x18000c1d4  mov     rdx, [rsp+180h+hKey]
0x18000c1d9  lea     rcx, [rsp+180h+var_150]
0x18000c1de  call    AslRegistryGetString
0x18000c1e3  xor     r8d, r8d; unsigned __int64
0x18000c1e6  lea     rcx, [rsp+180h+HeapHandle]; this
0x18000c1eb  test    eax, eax
0x18000c1ed  js      loc_18000C4B7
0x18000c1f3  mov     rdx, [rsp+180h+var_150]; unsigned __int16 *
0x18000c1f8  call    ?Append@RtlStringArray@@QEAAJPEBG_K@Z; RtlStringArray::Append(ushort const *,unsigned __int64)
0x18000c1fd  mov     rcx, gs:60h
0x18000c206  mov     rdx, [rsp+180h+var_150]
0x18000c20b  mov     rcx, [rcx+30h]
0x18000c20f  call    AslFree
0x18000c214  mov     dword ptr [rsp+180h+var_150], r15d
0x18000c219  lea     r8, aLanguage; "Language"
0x18000c220  mov     rdx, [rsp+180h+hKey]
0x18000c225  lea     rcx, [rsp+180h+var_150]
0x18000c22a  call    AslRegistryGetUInt32
0x18000c22f  mov     ebx, eax
0x18000c231  mov     r9d, dword ptr [rsp+180h+var_150]
0x18000c236  lea     r8, aD; "%d"
0x18000c23d  mov     edx, 10h; BufferCount
0x18000c242  lea     rcx, [rbp+80h+Buffer]; Buffer
0x18000c246  call    cs:__imp_swprintf_s
0x18000c24c  xor     r8d, r8d; unsigned __int64
0x18000c24f  lea     rdx, [rbp+80h+Buffer]; unsigned __int16 *
0x18000c253  lea     rcx, [rsp+180h+HeapHandle]; this
0x18000c258  call    ?Append@RtlStringArray@@QEAAJPEBG_K@Z; RtlStringArray::Append(ushort const *,unsigned __int64)
0x18000c25d  cmp     [rsp+180h+var_130], 4
0x18000c263  jnz     loc_18000C4FD
0x18000c269  mov     r8, [rsp+180h+var_138]
0x18000c26e  xor     eax, eax
0x18000c270  mul     r8
0x18000c273  mov     rcx, [rsp+180h+P]
0x18000c278  test    rdx, rdx
0x18000c27b  jnz     short loc_18000C285
0x18000c27d  add     rax, rcx
0x18000c280  cmp     rax, rcx
0x18000c283  jnb     short loc_18000C288
0x18000c285  mov     rax, r15
0x18000c288  mov     rax, [rax]
0x18000c28b  mov     [rbp+80h+var_D8], rax
0x18000c28f  mov     rax, r12
0x18000c292  mul     r8
0x18000c295  test    rdx, rdx
0x18000c298  jnz     short loc_18000C2A2
0x18000c29a  add     rax, rcx
0x18000c29d  cmp     rax, rcx
0x18000c2a0  jnb     short loc_18000C2A5
0x18000c2a2  mov     rax, r15
0x18000c2a5  mov     rax, [rax]
0x18000c2a8  mov     [rbp+80h+var_D0], rax
0x18000c2ac  mov     eax, 2
0x18000c2b1  mul     r8
0x18000c2b4  test    rdx, rdx
0x18000c2b7  jnz     short loc_18000C2C1
0x18000c2b9  add     rax, rcx
0x18000c2bc  cmp     rax, rcx
0x18000c2bf  jnb     short loc_18000C2C4
0x18000c2c1  mov     rax, r15
0x18000c2c4  mov     rax, [rax]
0x18000c2c7  mov     [rbp+80h+var_C8], rax
0x18000c2cb  test    ebx, ebx
0x18000c2cd  js      loc_18000C4C4
0x18000c2d3  mov     eax, 3
0x18000c2d8  mul     r8
0x18000c2db  test    rdx, rdx
0x18000c2de  jnz     short loc_18000C2E8
0x18000c2e0  add     rax, rcx
0x18000c2e3  cmp     rax, rcx
0x18000c2e6  jnb     short loc_18000C2EB
0x18000c2e8  mov     rax, r15
0x18000c2eb  mov     rax, [rax]
0x18000c2ee  mov     [rbp+80h+var_C0], rax
0x18000c2f2  lea     rdx, [rbp+80h+var_90]
0x18000c2f6  lea     rcx, [rbp+80h+var_D8]
0x18000c2fa  call    AeComputeProgramIdentityHash
0x18000c2ff  test    eax, eax
0x18000c301  js      loc_18000C52B
0x18000c307  xor     r8d, r8d; unsigned __int64
0x18000c30a  lea     rdx, [rbp+80h+var_90]; unsigned __int16 *
0x18000c30e  lea     rcx, [rsp+180h+HeapHandle]; this
0x18000c313  call    ?Append@RtlStringArray@@QEAAJPEBG_K@Z; RtlStringArray::Append(ushort const *,unsigned __int64)
0x18000c318  mov     ebx, eax
0x18000c31a  test    eax, eax
0x18000c31c  jnz     loc_18000C541
0x18000c322  mov     rcx, rdi; pszPath
0x18000c325  call    cs:__imp_PathFindFileNameW
0x18000c32b  mov     rdx, rax; unsigned __int16 *
0x18000c32e  xor     r8d, r8d; unsigned __int64
0x18000c331  lea     rcx, [rsp+180h+HeapHandle]; this
0x18000c336  call    ?Append@RtlStringArray@@QEAAJPEBG_K@Z; RtlStringArray::Append(ushort const *,unsigned __int64)
0x18000c33b  mov     ebx, eax
0x18000c33d  test    eax, eax
0x18000c33f  jnz     loc_18000C549
0x18000c345  mov     edi, r15d
0x18000c348  mov     r9, [rsp+180h+var_130]
0x18000c34d  mov     r8d, edi
0x18000c350  cmp     r8, r9
0x18000c353  jnb     loc_18000C3DB
0x18000c359  mov     eax, r8d
0x18000c35c  mul     [rsp+180h+var_138]
0x18000c361  test    rdx, rdx
0x18000c364  jnz     short loc_18000C372
0x18000c366  add     rax, [rsp+180h+P]
0x18000c36b  cmp     rax, [rsp+180h+P]
0x18000c370  jnb     short loc_18000C375
0x18000c372  mov     rax, r15
0x18000c375  mov     rdx, [rax]; unsigned __int16 *
0x18000c378  lea     rax, [r9-1]
0x18000c37c  lea     rcx, asc_1800FF818; ","
0x18000c383  lea     r9, dword_1800FF0F4
0x18000c38a  cmp     r8, rax
0x18000c38d  cmovnz  r9, rcx
0x18000c391  movzx   eax, word ptr [rdx]
0x18000c394  test    ax, ax
0x18000c397  jz      short loc_18000C3BC
0x18000c399  mov     rcx, rdx
0x18000c39c  cmp     ax, 3Bh ; ';'
0x18000c3a0  jz      loc_18000C493
0x18000c3a6  cmp     ax, 2Ch ; ','
0x18000c3aa  jz      loc_18000C493
0x18000c3b0  add     rcx, 2
0x18000c3b4  movzx   eax, word ptr [rcx]
0x18000c3b7  test    ax, ax
0x18000c3ba  jnz     short loc_18000C39C
0x18000c3bc  mov     r8, r9; unsigned __int16 *
0x18000c3bf  lea     rcx, [rsp+180h+Size]; this
0x18000c3c4  call    ?WriteString@RtlMemoryStream@@QEAAKPEBG0@Z; RtlMemoryStream::WriteString(ushort const *,ushort const *)
0x18000c3c9  mov     ebx, eax
0x18000c3cb  test    eax, eax
0x18000c3cd  jnz     loc_18000C551
0x18000c3d3  add     edi, r12d
0x18000c3d6  jmp     loc_18000C348
0x18000c3db  mov     rdi, [rbp+80h+Size+8]
0x18000c3df  mov     rcx, gs:60h
0x18000c3e8  mov     r8, rdi; Size
0x18000c3eb  mov     ebx, 8
0x18000c3f0  mov     edx, ebx; Flags
0x18000c3f2  mov     rcx, [rcx+30h]; HeapHandle
0x18000c3f6  call    cs:__imp_RtlAllocateHeap
0x18000c3fc  mov     rsi, rax
0x18000c3ff  test    rax, rax
0x18000c402  jz      loc_18000C50A
0x18000c408  test    rdi, rdi
0x18000c40b  jz      short loc_18000C41C
0x18000c40d  mov     r8, rdi; Size
0x18000c410  mov     rdx, [rbp+80h+Src+8]; Src
0x18000c414  mov     rcx, rax; void *
0x18000c417  call    memcpy_0
0x18000c41c  mov     [r14], rsi
0x18000c41f  mov     ebx, r15d
0x18000c422  mov     rcx, [rsp+180h+hKey]; hKey
0x18000c427  test    rcx, rcx
0x18000c42a  jnz     loc_18000C4CD
0x18000c430  mov     r8, [rbp+80h+Src+8]; P
0x18000c434  test    r8, r8
0x18000c437  jz      short loc_18000C447
0x18000c439  xor     edx, edx; Flags
0x18000c43b  mov     rcx, [rsp+180h+Size]; HeapHandle
0x18000c440  call    cs:__imp_RtlFreeHeap
0x18000c446  nop
0x18000c447  lea     rcx, [rsp+180h+HeapHandle]; this
0x18000c44c  call    ?Clear@RtlStringArray@@QEAAXXZ; RtlStringArray::Clear(void)
0x18000c451  mov     r8, [rsp+180h+P]; P
0x18000c456  test    r8, r8
0x18000c459  jz      short loc_18000C469
0x18000c45b  xor     edx, edx; Flags
0x18000c45d  mov     rcx, [rsp+180h+HeapHandle]; HeapHandle
0x18000c462  call    cs:__imp_RtlFreeHeap
0x18000c468  nop
0x18000c469  mov     eax, ebx
0x18000c46b  mov     rcx, [rbp+80h+var_30]
0x18000c46f  xor     rcx, rsp; StackCookie
0x18000c472  call    __security_check_cookie
0x18000c477  lea     r11, [rsp+180h+var_20]
0x18000c47f  mov     rbx, [r11+40h]
0x18000c483  mov     rsi, [r11+48h]
0x18000c487  mov     rsp, r11
0x18000c48a  pop     r15
0x18000c48c  pop     r14
0x18000c48e  pop     r12
0x18000c490  pop     rdi
0x18000c491  pop     rbp
0x18000c492  retn
0x18000c493  mov     word ptr [rcx], 5Fh ; '_'
0x18000c498  jmp     loc_18000C3B0
0x18000c49d  mov     rdx, rbx; unsigned __int16 *
0x18000c4a0  call    ?Append@RtlStringArray@@QEAAJPEBG_K@Z; RtlStringArray::Append(ushort const *,unsigned __int64)
0x18000c4a5  jmp     loc_18000C181
0x18000c4aa  mov     rdx, rbx; unsigned __int16 *
0x18000c4ad  call    ?Append@RtlStringArray@@QEAAJPEBG_K@Z; RtlStringArray::Append(ushort const *,unsigned __int64)
0x18000c4b2  jmp     loc_18000C1CD
0x18000c4b7  mov     rdx, rbx; unsigned __int16 *
0x18000c4ba  call    ?Append@RtlStringArray@@QEAAJPEBG_K@Z; RtlStringArray::Append(ushort const *,unsigned __int64)
0x18000c4bf  jmp     loc_18000C214
0x18000c4c4  mov     [rbp+80h+var_C0], r15
0x18000c4c8  jmp     loc_18000C2F2
0x18000c4cd  call    cs:__imp_RegCloseKey
0x18000c4d3  jmp     loc_18000C430
0x18000c4d8  mov     dword ptr [rsp+180h+phkResult], eax
0x18000c4dc  lea     r9, aFailedToOpenKe_2; "Failed to open key [%d]"
0x18000c4e3  mov     r8d, 112h
0x18000c4e9  lea     rdx, aUtceventspEnco; "UtcEventsp_EncodeProgramInfo"
0x18000c4f0  mov     ecx, r12d
0x18000c4f3  call    AslLogCallPrintf
0x18000c4f8  jmp     loc_18000C422
0x18000c4fd  mov     ebx, 8
0x18000c502  mov     r8d, 14Eh
0x18000c508  jmp     short loc_18000C510
0x18000c50a  mov     r8d, 18Eh
0x18000c510  lea     r9, aOutOfMemory; "Out of memory"
0x18000c517  lea     rdx, aUtceventspEnco; "UtcEventsp_EncodeProgramInfo"
0x18000c51e  mov     ecx, r12d
0x18000c521  call    AslLogCallPrintf
0x18000c526  jmp     loc_18000C422
0x18000c52b  movzx   ebx, ax
0x18000c52e  mov     dword ptr [rsp+180h+phkResult], ebx
0x18000c532  lea     r9, aFailedToComput; "Failed to compute program Id [%d]"
0x18000c539  mov     r8d, 15Eh
0x18000c53f  jmp     short loc_18000C4E9
0x18000c541  mov     r8d, 164h
0x18000c547  jmp     short loc_18000C510
0x18000c549  mov     r8d, 16Eh
0x18000c54f  jmp     short loc_18000C510
0x18000c551  mov     r8d, 182h
0x18000c557  jmp     short loc_18000C510
```
