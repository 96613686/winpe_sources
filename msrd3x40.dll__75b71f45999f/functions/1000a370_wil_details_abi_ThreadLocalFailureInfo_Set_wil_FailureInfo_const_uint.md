# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1000a370`
- end: `0x1000a4c2`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QAEXABUFailureInfo@3@I@Z`
- size: `338`
- prototype: `void __thiscall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1000a6c0`

## callees

- `0x10008950`
- `0x1000a370`
- `0x1000dbb0`
- `0x1000dc30`
- `0x1005f180`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000a452`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000a452`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000a45c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000a45c`

## pseudocode

```c
void __thiscall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        unsigned int a3)
{
  const struct wil::FailureInfo *v3; // edx
  char *v5; // eax
  const char *v6; // ecx
  unsigned int v7; // ebx
  const char *v8; // ecx
  unsigned int v9; // esi
  _WORD *v10; // ecx
  int v11; // ecx
  SIZE_T v13; // eax
  SIZE_T *v14; // ebx
  void *v15; // esi
  HANDLE ProcessHeap; // eax
  char *v17; // ecx
  char *v18; // esi
  void *v19; // eax
  void *v20; // eax
  void *v21; // eax
  int v22; // [esp+Ch] [ebp-Ch]
  SIZE_T v23; // [esp+10h] [ebp-8h]
  _WORD *v24; // [esp+14h] [ebp-4h]
  LPVOID v25; // [esp+14h] [ebp-4h]

  v3 = a2;
  *((_DWORD *)this + 1) = a3;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_DWORD *)this + 3) = 0;
  *((_WORD *)this + 8) = *((_WORD *)a2 + 20);
  *((_BYTE *)this + 18) = *(_BYTE *)a2;
  *((_DWORD *)this + 5) = 0;
  *((_DWORD *)this + 6) = *((_DWORD *)a2 + 20);
  *((_DWORD *)this + 7) = *((_DWORD *)a2 + 21);
  v5 = (char *)this + 32;
  *((_DWORD *)this + 8) = 0;
  v6 = (const char *)*((_DWORD *)a2 + 9);
  v22 = (int)v5;
  if ( v6 )
    v7 = strlen(v6) + 1;
  else
    v7 = 1;
  v8 = (const char *)*((_DWORD *)a2 + 19);
  if ( v8 )
    v9 = strlen(v8) + 1;
  else
    v9 = 1;
  v10 = (_WORD *)*((_DWORD *)a2 + 5);
  if ( v10 )
  {
    v24 = v10 + 1;
    while ( *v10++ )
      ;
    v11 = 2 * (v10 - v24) + 2;
  }
  else
  {
    v11 = 2;
  }
  v13 = v7 + v11 + v9;
  v23 = v13;
  v14 = (SIZE_T *)((char *)this + 40);
  if ( !*((_DWORD *)this + 9) || *v14 < v13 )
  {
    v25 = wil::details::ProcessHeapAlloc(8u, v13);
    if ( v25 )
    {
      v15 = (void *)*((_DWORD *)this + 9);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v15);
      *((_DWORD *)this + 9) = v25;
      *v14 = v23;
    }
    v3 = a2;
  }
  v17 = (char *)*((_DWORD *)this + 9);
  if ( v17 )
  {
    v18 = &v17[*v14];
    v19 = (void *)wil::details::WriteResultString<char const *>(v17, *((void **)v3 + 9), (int)this + 12);
    v20 = (void *)wil::details::WriteResultString<char const *>(v19, *((void **)a2 + 19), (int)this + 20);
    v21 = (void *)wil::details::WriteResultString<unsigned short const *>(v20, *((void **)a2 + 5), v22);
    memset(v21, 0, v18 - (_BYTE *)v21);
  }
}

```

## disassembly

```asm
0x1000a370  mov     edi, edi
0x1000a372  push    ebp
0x1000a373  mov     ebp, esp
0x1000a375  sub     esp, 0Ch
0x1000a378  mov     edx, [ebp+arg_0]
0x1000a37b  mov     eax, [ebp+arg_4]
0x1000a37e  push    ebx; unsigned int
0x1000a37f  push    esi; unsigned int
0x1000a380  push    edi; this
0x1000a381  mov     edi, ecx
0x1000a383  mov     [edi+4], eax
0x1000a386  mov     eax, [edx+8]
0x1000a389  mov     [edi+8], eax
0x1000a38c  mov     dword ptr [edi+0Ch], 0
0x1000a393  mov     ax, [edx+28h]
0x1000a397  mov     [edi+10h], ax
0x1000a39b  mov     al, [edx]
0x1000a39d  mov     [edi+12h], al
0x1000a3a0  mov     dword ptr [edi+14h], 0
0x1000a3a7  mov     eax, [edx+50h]
0x1000a3aa  mov     [edi+18h], eax
0x1000a3ad  mov     eax, [edx+54h]
0x1000a3b0  mov     [edi+1Ch], eax
0x1000a3b3  lea     eax, [edi+20h]
0x1000a3b6  mov     dword ptr [eax], 0
0x1000a3bc  mov     ecx, [edx+24h]
0x1000a3bf  mov     [ebp+var_C], eax
0x1000a3c2  test    ecx, ecx
0x1000a3c4  jnz     short loc_1000A3CB
0x1000a3c6  lea     ebx, [ecx+1]
0x1000a3c9  jmp     short loc_1000A3DC
0x1000a3cb  lea     esi, [ecx+1]
0x1000a3ce  mov     edi, edi
0x1000a3d0  mov     al, [ecx]
0x1000a3d2  inc     ecx
0x1000a3d3  test    al, al
0x1000a3d5  jnz     short loc_1000A3D0
0x1000a3d7  sub     ecx, esi
0x1000a3d9  lea     ebx, [ecx+1]
0x1000a3dc  mov     ecx, [edx+4Ch]
0x1000a3df  test    ecx, ecx
0x1000a3e1  jnz     short loc_1000A3E8
0x1000a3e3  lea     esi, [ecx+1]
0x1000a3e6  jmp     short loc_1000A3FC
0x1000a3e8  lea     esi, [ecx+1]
0x1000a3eb  nop     dword ptr [eax+eax+00h]
0x1000a3f0  mov     al, [ecx]
0x1000a3f2  inc     ecx
0x1000a3f3  test    al, al
0x1000a3f5  jnz     short loc_1000A3F0
0x1000a3f7  sub     ecx, esi
0x1000a3f9  lea     esi, [ecx+1]
0x1000a3fc  mov     ecx, [edx+14h]
0x1000a3ff  test    ecx, ecx
0x1000a401  jnz     short loc_1000A40A
0x1000a403  mov     ecx, 2
0x1000a408  jmp     short loc_1000A427
0x1000a40a  lea     eax, [ecx+2]
0x1000a40d  mov     [ebp+var_4], eax
0x1000a410  mov     ax, [ecx]
0x1000a413  add     ecx, 2
0x1000a416  test    ax, ax
0x1000a419  jnz     short loc_1000A410
0x1000a41b  sub     ecx, [ebp+var_4]
0x1000a41e  sar     ecx, 1
0x1000a420  lea     ecx, ds:2[ecx*2]
0x1000a427  lea     eax, [ecx+esi]
0x1000a42a  add     eax, ebx
0x1000a42c  cmp     dword ptr [edi+24h], 0
0x1000a430  mov     [ebp+var_8], eax
0x1000a433  lea     ebx, [edi+28h]
0x1000a436  jz      short loc_1000A43C
0x1000a438  cmp     [ebx], eax
0x1000a43a  jnb     short loc_1000A470
0x1000a43c  mov     edx, eax
0x1000a43e  mov     ecx, 8
0x1000a443  call    ?ProcessHeapAlloc@details@wil@@YGPAXKI@Z; wil::details::ProcessHeapAlloc(ulong,uint)
0x1000a448  mov     [ebp+var_4], eax
0x1000a44b  test    eax, eax
0x1000a44d  jz      short loc_1000A46D
0x1000a44f  mov     esi, [edi+24h]
0x1000a452  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x1000a458  push    esi; lpMem
0x1000a459  push    0; dwFlags
0x1000a45b  push    eax; hHeap
0x1000a45c  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x1000a462  mov     eax, [ebp+var_4]
0x1000a465  mov     [edi+24h], eax
0x1000a468  mov     eax, [ebp+var_8]
0x1000a46b  mov     [ebx], eax
0x1000a46d  mov     edx, [ebp+arg_0]
0x1000a470  mov     ecx, [edi+24h]; void *
0x1000a473  test    ecx, ecx
0x1000a475  jz      short loc_1000A4B9
0x1000a477  mov     esi, [ebx]
0x1000a479  lea     eax, [edi+0Ch]
0x1000a47c  push    eax; int
0x1000a47d  push    dword ptr [edx+24h]; Src
0x1000a480  add     esi, ecx
0x1000a482  mov     edx, esi
0x1000a484  call    ??$WriteResultString@PBD@details@wil@@YGPAEPAE0PBDPAPBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1000a489  lea     ecx, [edi+14h]
0x1000a48c  mov     edx, esi
0x1000a48e  mov     edi, [ebp+arg_0]
0x1000a491  push    ecx; int
0x1000a492  mov     ecx, eax; void *
0x1000a494  push    dword ptr [edi+4Ch]; Src
0x1000a497  call    ??$WriteResultString@PBD@details@wil@@YGPAEPAE0PBDPAPBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1000a49c  push    [ebp+var_C]; int
0x1000a49f  mov     edx, esi
0x1000a4a1  mov     ecx, eax; void *
0x1000a4a3  push    dword ptr [edi+14h]; Src
0x1000a4a6  call    ??$WriteResultString@PBG@details@wil@@YGPAEPAE0PBGPAPBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x1000a4ab  sub     esi, eax
0x1000a4ad  push    esi; Size
0x1000a4ae  push    0; Val
0x1000a4b0  push    eax; void *
0x1000a4b1  call    _memset
0x1000a4b6  add     esp, 0Ch
0x1000a4b9  pop     edi
0x1000a4ba  pop     esi
0x1000a4bb  pop     ebx
0x1000a4bc  mov     esp, ebp
0x1000a4be  pop     ebp
0x1000a4bf  retn    8
```
