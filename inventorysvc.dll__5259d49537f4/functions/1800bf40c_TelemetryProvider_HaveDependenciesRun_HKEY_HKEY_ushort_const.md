# TelemetryProvider::HaveDependenciesRun(HKEY__ *,HKEY__ *,ushort const *)

- ea: `0x1800bf40c`
- end: `0x1800bf5cf`
- name: `?HaveDependenciesRun@TelemetryProvider@@AEAAJPEAUHKEY__@@0PEBG@Z`
- size: `451`
- prototype: `int(TelemetryProvider *__hidden this, HKEY, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800bf5d8`

## callees

- `0x1800152d0`
- `0x1800bf2bc`
- `0x1800bf40c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bf4fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bf519`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bf4fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bf519`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bf527`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bf527`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bf508`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bf508`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bf4a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bf4a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bf463`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bf463`

## string_xrefs

- `0x1800bf5bd`: `StringCbCopyW failed [%#x]`

## pseudocode

```c
__int64 __fastcall TelemetryProvider::HaveDependenciesRun(
        TelemetryProvider *this,
        HKEY a2,
        HKEY a3,
        const unsigned __int16 *a4)
{
  const unsigned __int16 *v4; // rbx
  __int64 v8; // rdi
  __int64 v9; // rax
  unsigned int v10; // ebx
  void *v12; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int64 v14; // rdi
  HANDLE v15; // rax
  _WORD *v16; // rax
  _WORD *v17; // r8
  const char *v18; // r9
  __int64 v19; // r8
  unsigned __int64 v20; // rdi
  __int64 v21; // rax
  _WORD *v22; // rcx
  PHKEY phkResult; // [rsp+20h] [rbp-48h]
  HKEY hKey; // [rsp+88h] [rbp+20h] BYREF

  v4 = a4;
  if ( !a4 )
    return 0;
  v8 = -1;
  while ( 1 )
  {
    if ( !*v4 )
      return 0;
    hKey = 0;
    if ( RegOpenKeyExW(a2, v4, 0, 0x20019u, &hKey) )
    {
      AslLogCallPrintf(
        1,
        "TelemetryProvider::HaveDependenciesRun",
        653,
        "Dependent TelemetryProvider %ls doesn't exist! [%#x]",
        v4,
        -2147418113);
      goto LABEL_7;
    }
    RegCloseKey(hKey);
    if ( TelemetryProvider::GetOverdueTimeForProvider(a2, a3, v4) )
      break;
LABEL_7:
    v9 = -1;
    do
      ++v9;
    while ( v4[v9] );
    v4 += v9 + 1;
    if ( !v4 )
      return 0;
  }
  do
    ++v8;
  while ( v4[v8] );
  v12 = (void *)*((_QWORD *)this + 3);
  if ( v12 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v12);
    *((_QWORD *)this + 3) = 0;
  }
  v14 = (unsigned int)(2 * v8 + 2);
  v15 = GetProcessHeap();
  v16 = HeapAlloc(v15, 0, (unsigned int)v14);
  *((_QWORD *)this + 3) = v16;
  v17 = v16;
  if ( !v16 )
  {
    v10 = -2147024882;
    v18 = "HeapAlloc failed [%#x]";
    v19 = 672;
LABEL_17:
    LODWORD(phkResult) = v10;
    AslLogCallPrintf(1, "TelemetryProvider::HaveDependenciesRun", v19, v18, phkResult);
    return v10;
  }
  v20 = v14 >> 1;
  if ( !v20 )
  {
    v10 = -2147024809;
LABEL_28:
    v18 = "StringCbCopyW failed [%#x]";
    v19 = 679;
    goto LABEL_17;
  }
  v21 = 2147483646;
  do
  {
    if ( !v21 )
      break;
    if ( !*v4 )
      break;
    *v17++ = *v4++;
    --v21;
    --v20;
  }
  while ( v20 );
  v22 = v17 - 1;
  v10 = v20 == 0 ? 0x8007007A : 0;
  if ( v20 )
    v22 = v17;
  *v22 = 0;
  if ( !v20 )
    goto LABEL_28;
  return 0;
}

```

## disassembly

```asm
0x1800bf40c  push    rbx
0x1800bf40e  push    rbp
0x1800bf40f  push    rsi
0x1800bf410  push    rdi
0x1800bf411  push    r14
0x1800bf413  push    r15
0x1800bf415  sub     rsp, 38h
0x1800bf419  xor     r15d, r15d
0x1800bf41c  mov     rbx, r9
0x1800bf41f  mov     r14, r8
0x1800bf422  mov     rsi, rdx
0x1800bf425  mov     rbp, rcx
0x1800bf428  test    r9, r9
0x1800bf42b  jz      loc_1800BF4D5
0x1800bf431  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800bf435  cmp     [rbx], r15w
0x1800bf439  jz      loc_1800BF4D5
0x1800bf43f  lea     rax, [rsp+68h+hKey]
0x1800bf447  mov     [rsp+68h+hKey], r15
0x1800bf44f  mov     r9d, 20019h; samDesired
0x1800bf455  mov     [rsp+68h+phkResult], rax; phkResult
0x1800bf45a  xor     r8d, r8d; ulOptions
0x1800bf45d  mov     rdx, rbx; lpSubKey
0x1800bf460  mov     rcx, rsi; hKey
0x1800bf463  call    cs:__imp_RegOpenKeyExW
0x1800bf469  test    eax, eax
0x1800bf46b  jz      short loc_1800BF49A
0x1800bf46d  mov     [rsp+68h+var_40], 8000FFFFh
0x1800bf475  lea     r9, aDependentTelem; "Dependent TelemetryProvider %ls doesn't"...
0x1800bf47c  mov     r8d, 28Dh
0x1800bf482  mov     [rsp+68h+phkResult], rbx
0x1800bf487  lea     rdx, aTelemetryprovi_8; "TelemetryProvider::HaveDependenciesRun"
0x1800bf48e  mov     ecx, 1
0x1800bf493  call    AslLogCallPrintf
0x1800bf498  jmp     short loc_1800BF4BA
0x1800bf49a  mov     rcx, [rsp+68h+hKey]; hKey
0x1800bf4a2  call    cs:__imp_RegCloseKey
0x1800bf4a8  mov     r8, rbx; unsigned __int16 *
0x1800bf4ab  mov     rdx, r14; HKEY
0x1800bf4ae  mov     rcx, rsi; HKEY
0x1800bf4b1  call    ?GetOverdueTimeForProvider@TelemetryProvider@@CAKPEAUHKEY__@@0PEBG@Z; TelemetryProvider::GetOverdueTimeForProvider(HKEY__ *,HKEY__ *,ushort const *)
0x1800bf4b6  test    eax, eax
0x1800bf4b8  jnz     short loc_1800BF4E7
0x1800bf4ba  mov     rax, rdi
0x1800bf4bd  inc     rax
0x1800bf4c0  cmp     [rbx+rax*2], r15w
0x1800bf4c5  jnz     short loc_1800BF4BD
0x1800bf4c7  lea     rbx, [rbx+rax*2]
0x1800bf4cb  add     rbx, 2
0x1800bf4cf  jnz     loc_1800BF435
0x1800bf4d5  mov     ebx, r15d
0x1800bf4d8  mov     eax, ebx
0x1800bf4da  add     rsp, 38h
0x1800bf4de  pop     r15
0x1800bf4e0  pop     r14
0x1800bf4e2  pop     rdi
0x1800bf4e3  pop     rsi
0x1800bf4e4  pop     rbp
0x1800bf4e5  pop     rbx
0x1800bf4e6  retn
0x1800bf4e7  inc     rdi
0x1800bf4ea  cmp     [rbx+rdi*2], r15w
0x1800bf4ef  jnz     short loc_1800BF4E7
0x1800bf4f1  mov     rsi, [rbp+18h]
0x1800bf4f5  test    rsi, rsi
0x1800bf4f8  jz      short loc_1800BF512
0x1800bf4fa  call    cs:__imp_GetProcessHeap
0x1800bf500  mov     r8, rsi; lpMem
0x1800bf503  xor     edx, edx; dwFlags
0x1800bf505  mov     rcx, rax; hHeap
0x1800bf508  call    cs:__imp_HeapFree
0x1800bf50e  mov     [rbp+18h], r15
0x1800bf512  lea     edi, ds:2[rdi*2]
0x1800bf519  call    cs:__imp_GetProcessHeap
0x1800bf51f  mov     r8d, edi; dwBytes
0x1800bf522  xor     edx, edx; dwFlags
0x1800bf524  mov     rcx, rax; hHeap
0x1800bf527  call    cs:__imp_HeapAlloc
0x1800bf52d  mov     [rbp+18h], rax
0x1800bf531  mov     r8, rax
0x1800bf534  test    rax, rax
0x1800bf537  jnz     short loc_1800BF565
0x1800bf539  mov     ebx, 8007000Eh
0x1800bf53e  lea     r9, aHeapallocFaile; "HeapAlloc failed [%#x]"
0x1800bf545  mov     r8d, 2A0h
0x1800bf54b  lea     rdx, aTelemetryprovi_8; "TelemetryProvider::HaveDependenciesRun"
0x1800bf552  mov     dword ptr [rsp+68h+phkResult], ebx
0x1800bf556  mov     ecx, 1
0x1800bf55b  call    AslLogCallPrintf
0x1800bf560  jmp     loc_1800BF4D8
0x1800bf565  shr     rdi, 1
0x1800bf568  jz      short loc_1800BF5B8
0x1800bf56a  mov     eax, 7FFFFFFEh
0x1800bf56f  test    rax, rax
0x1800bf572  jz      short loc_1800BF591
0x1800bf574  movzx   ecx, word ptr [rbx]
0x1800bf577  test    cx, cx
0x1800bf57a  jz      short loc_1800BF591
0x1800bf57c  mov     [r8], cx
0x1800bf580  add     rbx, 2
0x1800bf584  add     r8, 2
0x1800bf588  dec     rax
0x1800bf58b  sub     rdi, 1
0x1800bf58f  jnz     short loc_1800BF56F
0x1800bf591  mov     rax, rdi
0x1800bf594  lea     rcx, [r8-2]
0x1800bf598  neg     rax
0x1800bf59b  sbb     ebx, ebx
0x1800bf59d  not     ebx
0x1800bf59f  and     ebx, 8007007Ah
0x1800bf5a5  test    rdi, rdi
0x1800bf5a8  cmovnz  rcx, r8
0x1800bf5ac  mov     [rcx], r15w
0x1800bf5b0  jnz     loc_1800BF4D5
0x1800bf5b6  jmp     short loc_1800BF5BD
0x1800bf5b8  mov     ebx, 80070057h
0x1800bf5bd  lea     r9, aStringcbcopywF; "StringCbCopyW failed [%#x]"
0x1800bf5c4  mov     r8d, 2A7h
0x1800bf5ca  jmp     loc_1800BF54B
```
